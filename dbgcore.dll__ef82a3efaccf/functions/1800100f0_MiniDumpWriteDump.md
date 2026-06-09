# MiniDumpWriteDump

- ea: `0x1800100f0`
- end: `0x180010542`
- name: `MiniDumpWriteDump`
- size: `1106`
- prototype: `BOOL __stdcall(HANDLE hProcess, DWORD ProcessId, HANDLE hFile, MINIDUMP_TYPE DumpType, PMINIDUMP_EXCEPTION_INFORMATION ExceptionParam, PMINIDUMP_USER_STREAM_INFORMATION UserStreamParam, PMINIDUMP_CALLBACK_INFORMATION CallbackParam)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001710`
- `0x180006194`
- `0x1800062f4`
- `0x1800081c4`
- `0x18000f8e8`
- `0x1800100f0`
- `0x1800106fc`
- `0x180010974`
- `0x180010a7c`
- `0x180010bbc`
- `0x180010d10`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800101c8`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800101c8`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800104a6`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800104a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800101ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800101ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001051a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001051a`
- `RPCRT4!UuidCreate` at `0x18001019f`
- `RPCRT4!UuidCreate` at `0x18001019f`

## string_xrefs

- `0x1800104c0`: `MiniDumpCreateLiveAllocationProvider`
- `0x180010275`: `DetermineSystemProvider`
- `0x180010317`: `SysProv->ReadAllVirtual`
- `0x180010462`: `MiniDumpCompletedWithSuccess`
- `0x1800104de`: `MiniDumpCompletedWithFailure`

## pseudocode

```c
BOOL __stdcall MiniDumpWriteDump(
        HANDLE hProcess,
        DWORD ProcessId,
        HANDLE hFile,
        MINIDUMP_TYPE DumpType,
        PMINIDUMP_EXCEPTION_INFORMATION ExceptionParam,
        PMINIDUMP_USER_STREAM_INFORMATION UserStreamParam,
        PMINIDUMP_CALLBACK_INFORMATION CallbackParam)
{
  __int16 v7; // r13
  struct _TEB *v8; // rax
  struct MiniDumpOutputProvider *v9; // rsi
  const unsigned __int16 *v10; // rdx
  HANDLE v11; // rax
  void *v12; // rbx
  signed int LastError; // eax
  struct MiniDumpAllocationProvider *v14; // rdi
  struct MiniDumpAllocationProvider **v15; // rax
  struct MiniDumpStatusProvider *v16; // r15
  int v17; // eax
  DWORD v18; // ebx
  struct MiniDumpSystemProvider *v19; // r14
  const unsigned __int16 *v20; // rdx
  struct _MINIDUMP_CALLBACK_INFORMATION *v21; // rsi
  int v22; // eax
  const unsigned __int16 *v23; // rdx
  PEXCEPTION_RECORD ExceptionRecord; // rcx
  PCONTEXT ContextRecord; // rax
  PEXCEPTION_POINTERS ExceptionPointers; // rax
  unsigned __int64 v27; // rax
  struct _TEB *v28; // rax
  struct _TEB *v30; // rax
  __int64 v31; // [rsp+48h] [rbp-A9h]
  struct _GUID v32; // [rsp+50h] [rbp-A1h] BYREF
  __int64 v33; // [rsp+60h] [rbp-91h]
  struct MiniDumpOutputProvider *v34; // [rsp+70h] [rbp-81h] BYREF
  MINIDUMP_TYPE v35; // [rsp+78h] [rbp-79h]
  DWORD v36; // [rsp+7Ch] [rbp-75h]
  struct HPSS__ *v37; // [rsp+80h] [rbp-71h]
  _BYTE v38[24]; // [rsp+88h] [rbp-69h] BYREF
  struct MiniDumpSystemProvider *v39; // [rsp+A0h] [rbp-51h] BYREF
  void *v40[2]; // [rsp+A8h] [rbp-49h] BYREF
  struct _MINIDUMP_CALLBACK_INFORMATION *v41; // [rsp+B8h] [rbp-39h]
  PMINIDUMP_USER_STREAM_INFORMATION v42; // [rsp+C0h] [rbp-31h]
  __int64 v43; // [rsp+C8h] [rbp-29h]
  UUID Uuid; // [rsp+D0h] [rbp-21h] BYREF

  v43 = -2;
  v35 = DumpType;
  v40[0] = hFile;
  v36 = ProcessId;
  v37 = (struct HPSS__ *)hProcess;
  v42 = UserStreamParam;
  v41 = CallbackParam;
  v7 = NtCurrentTeb()->SameTebFlags >> 15;
  if ( Win32::FileAPIs::ScopedDisableBrokering::IsRequiredApiSetPresent() && !(_BYTE)v7 )
  {
    v8 = NtCurrentTeb();
    v8->SameTebFlags |= 0x8000u;
  }
  v39 = 0;
  v9 = 0;
  v34 = 0;
  memset(v38, 0, sizeof(v38));
  Uuid = 0;
  UuidCreate(&Uuid);
  TelemetryInitialize();
  v32 = Uuid;
  TelemetryLogAction(&v32, v10);
  v11 = HeapCreate(0, 0x10000u, 0);
  v12 = v11;
  if ( v11 )
  {
    v14 = (struct MiniDumpAllocationProvider *)HeapAlloc(v11, 0, 0x10u);
    if ( !v14 )
    {
      HeapDestroy(v12);
      LastError = -2147024882;
LABEL_47:
      v18 = LastError;
      v32 = Uuid;
      TelemetryLogFunctionCallWithResult(&v32, L"MiniDumpCreateLiveAllocationProvider", LastError);
LABEL_48:
      v32 = Uuid;
      TelemetryLogActionWithResult(&v32, L"MiniDumpCompletedWithFailure", v18);
      TelemetryUninitialize();
      if ( Win32::FileAPIs::ScopedDisableBrokering::IsRequiredApiSetPresent() && !(_BYTE)v7 )
      {
        v30 = NtCurrentTeb();
        v30->SameTebFlags &= ~0x8000u;
      }
      SetLastError(v18);
      return 0;
    }
    *(_QWORD *)v14 = &Win32LiveAllocationProvider::`vftable';
    *((_QWORD *)v14 + 1) = v12;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = 0;
    if ( LastError )
      goto LABEL_47;
  }
  v15 = (struct MiniDumpAllocationProvider **)(*(__int64 (__fastcall **)(struct MiniDumpAllocationProvider *, __int64))(*(_QWORD *)v14 + 8LL))(
                                                v14,
                                                16);
  if ( v15 )
    *v15 = v14;
  v16 = (struct MiniDumpStatusProvider *)(v15 + 1);
  if ( v15 == (struct MiniDumpAllocationProvider **)-8LL )
  {
    v18 = -2147024882;
    v32 = Uuid;
    TelemetryLogFunctionCallWithResult(&v32, L"DetermineStatusProvider", -2147024882);
    goto LABEL_39;
  }
  *(_QWORD *)v16 = &NullStatusProvider::`vftable';
  v17 = DetermineSystemProvider(v14, v16, v37, CallbackParam, &v39);
  v18 = v17;
  v19 = v39;
  if ( v17 )
  {
    v20 = L"DetermineSystemProvider";
LABEL_32:
    v32 = Uuid;
    TelemetryLogFunctionCallWithResult(&v32, v20, v17);
    goto LABEL_33;
  }
  v21 = v41;
  v22 = DetermineOutputProvider(v14, v40[0], v41, &v34);
  v18 = v22;
  if ( v22 )
  {
    v23 = L"DetermineOutputProvider";
LABEL_18:
    v32 = Uuid;
    TelemetryLogFunctionCallWithResult(&v32, v23, v22);
    v9 = v34;
    goto LABEL_33;
  }
  if ( ExceptionParam )
  {
    *(_DWORD *)v38 = ExceptionParam->ThreadId;
    *(_DWORD *)&v38[20] = ExceptionParam->ClientPointers;
    if ( *(_DWORD *)&v38[20] )
    {
      *(_OWORD *)v40 = 0;
      v22 = (*(__int64 (__fastcall **)(struct MiniDumpSystemProvider *, struct HPSS__ *, PEXCEPTION_POINTERS, void **, int))(*(_QWORD *)v19 + 240LL))(
              v19,
              v37,
              ExceptionParam->ExceptionPointers,
              v40,
              16);
      v18 = v22;
      if ( v22 )
      {
        v23 = L"SysProv->ReadAllVirtual";
        goto LABEL_18;
      }
      ExceptionRecord = (PEXCEPTION_RECORD)v40[0];
      ContextRecord = (PCONTEXT)v40[1];
    }
    else
    {
      ExceptionPointers = ExceptionParam->ExceptionPointers;
      if ( !ExceptionPointers )
      {
        *(_OWORD *)&v38[4] = 0;
        ExceptionRecord = 0;
        goto LABEL_28;
      }
      ExceptionRecord = ExceptionPointers->ExceptionRecord;
      ContextRecord = ExceptionPointers->ContextRecord;
    }
    *(_QWORD *)&v38[4] = ExceptionRecord;
    *(_QWORD *)&v38[12] = ContextRecord;
LABEL_28:
    v27 = (unsigned __int64)v38 & -(__int64)(ExceptionRecord != 0);
    goto LABEL_30;
  }
  v27 = 0;
LABEL_30:
  *(_DWORD *)&v32.Data2 = 0;
  v33 = 0;
  v32.Data1 = v35;
  *(_QWORD *)v32.Data4 = 2147353560;
  v31 = (__int64)v21;
  v9 = v34;
  v17 = MiniDumpProvideDump(
          (_DWORD)v37,
          v36,
          (_DWORD)v19,
          (_DWORD)v34,
          (__int64)v14,
          (__int64)v16,
          (__int64)&v32,
          v27,
          (__int64)v42,
          v31);
  v18 = v17;
  if ( v17 )
  {
    v20 = L"MiniDumpProvideDump";
    goto LABEL_32;
  }
LABEL_33:
  if ( v19 )
    (**(void (__fastcall ***)(struct MiniDumpSystemProvider *))v19)(v19);
  if ( v9 )
    (**(void (__fastcall ***)(struct MiniDumpOutputProvider *))v9)(v9);
  (**(void (__fastcall ***)(struct MiniDumpStatusProvider *))v16)(v16);
LABEL_39:
  if ( v14 )
    (**(void (__fastcall ***)(struct MiniDumpAllocationProvider *))v14)(v14);
  if ( v18 )
    goto LABEL_48;
  v32 = Uuid;
  TelemetryLogActionWithResult(&v32, L"MiniDumpCompletedWithSuccess", 0);
  TelemetryUninitialize();
  if ( Win32::FileAPIs::ScopedDisableBrokering::IsRequiredApiSetPresent() && !(_BYTE)v7 )
  {
    v28 = NtCurrentTeb();
    v28->SameTebFlags &= ~0x8000u;
  }
  return 1;
}

```

## disassembly

```asm
0x1800100f0  push    rbp
0x1800100f2  push    rbx
0x1800100f3  push    rsi
0x1800100f4  push    rdi
0x1800100f5  push    r12
0x1800100f7  push    r13
0x1800100f9  push    r14
0x1800100fb  push    r15
0x1800100fd  lea     rbp, [rsp-7]
0x180010102  sub     rsp, 0F8h
0x180010109  mov     [rbp+3Fh+var_68], 0FFFFFFFFFFFFFFFEh
0x180010111  mov     rax, cs:__security_cookie
0x180010118  xor     rax, rsp
0x18001011b  mov     [rbp+3Fh+var_50], rax
0x18001011f  mov     [rbp+3Fh+var_B8], r9d
0x180010123  mov     [rbp+3Fh+var_88], r8
0x180010127  mov     [rbp+3Fh+var_B4], edx
0x18001012a  mov     [rbp+3Fh+var_B0], rcx
0x18001012e  mov     r12, [rbp+3Fh+ExceptionParam]
0x180010132  mov     rax, [rbp+3Fh+UserStreamParam]
0x180010136  mov     [rbp+3Fh+var_70], rax
0x18001013a  mov     r14, [rbp+3Fh+CallbackParam]
0x18001013e  mov     [rbp+3Fh+var_78], r14
0x180010142  mov     rax, gs:30h
0x18001014b  movzx   r13d, word ptr [rax+17EEh]
0x180010153  shr     r13w, 0Fh
0x180010158  call    ?IsRequiredApiSetPresent@ScopedDisableBrokering@FileAPIs@Win32@@SA_NXZ; Win32::FileAPIs::ScopedDisableBrokering::IsRequiredApiSetPresent(void)
0x18001015d  test    al, al
0x18001015f  jz      short loc_18001017B
0x180010161  test    r13b, r13b
0x180010164  jnz     short loc_18001017B
0x180010166  mov     rax, gs:30h
0x18001016f  mov     ecx, 8000h
0x180010174  or      [rax+17EEh], cx
0x18001017b  mov     [rbp+3Fh+var_90], 0
0x180010183  xor     esi, esi
0x180010185  mov     [rsp+130h+var_C0], rsi
0x18001018a  xorps   xmm0, xmm0
0x18001018d  xor     eax, eax
0x18001018f  movups  [rbp+3Fh+var_A8], xmm0
0x180010193  mov     [rbp+3Fh+var_98], rax
0x180010197  movups  xmmword ptr [rbp+3Fh+Uuid.Data1], xmm0
0x18001019b  lea     rcx, [rbp+3Fh+Uuid]; Uuid
0x18001019f  call    cs:__imp_UuidCreate
0x1800101a5  call    ?TelemetryInitialize@@YAXXZ; TelemetryInitialize(void)
0x1800101aa  movaps  xmm0, xmmword ptr [rbp+3Fh+Uuid.Data1]
0x1800101ae  movdqa  xmmword ptr [rsp+130h+var_E0.Data1], xmm0
0x1800101b4  lea     rcx, [rsp+130h+var_E0]; struct _GUID
0x1800101b9  call    ?TelemetryLogAction@@YAXU_GUID@@PEBG@Z; TelemetryLogAction(_GUID,ushort const *)
0x1800101be  xor     r8d, r8d; dwMaximumSize
0x1800101c1  mov     edx, 10000h; dwInitialSize
0x1800101c6  xor     ecx, ecx; flOptions
0x1800101c8  call    cs:__imp_HeapCreate
0x1800101ce  mov     rbx, rax
0x1800101d1  lea     r15d, [rsi+10h]
0x1800101d5  test    rax, rax
0x1800101d8  jnz     short loc_1800101F7
0x1800101da  call    cs:__imp_GetLastError
0x1800101e0  test    eax, eax
0x1800101e2  jle     short loc_1800101EC
0x1800101e4  movzx   eax, ax
0x1800101e7  or      eax, 80070000h
0x1800101ec  xor     edi, edi
0x1800101ee  test    eax, eax
0x1800101f0  jz      short loc_18001021F
0x1800101f2  jmp     loc_1800104B1
0x1800101f7  mov     r8, r15; dwBytes
0x1800101fa  xor     edx, edx; dwFlags
0x1800101fc  mov     rcx, rbx; hHeap
0x1800101ff  call    cs:__imp_HeapAlloc
0x180010205  mov     rdi, rax
0x180010208  test    rax, rax
0x18001020b  jz      loc_1800104A3
0x180010211  lea     rax, ??_7Win32LiveAllocationProvider@@6B@; const Win32LiveAllocationProvider::`vftable'
0x180010218  mov     [rdi], rax
0x18001021b  mov     [rdi+8], rbx
0x18001021f  mov     rax, [rdi]
0x180010222  mov     edx, r15d
0x180010225  mov     rcx, rdi
0x180010228  mov     rax, [rax+8]
0x18001022c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010231  test    rax, rax
0x180010234  jz      short loc_180010239
0x180010236  mov     [rax], rdi
0x180010239  lea     r15, [rax+8]
0x18001023d  test    r15, r15
0x180010240  jz      loc_180010419
0x180010246  lea     rax, ??_7NullStatusProvider@@6B@; const NullStatusProvider::`vftable'
0x18001024d  mov     [r15], rax
0x180010250  lea     rax, [rbp+3Fh+var_90]
0x180010254  mov     [rsp+130h+var_110], rax; struct MiniDumpSystemProvider **
0x180010259  mov     r9, r14; struct _MINIDUMP_CALLBACK_INFORMATION *
0x18001025c  mov     r8, [rbp+3Fh+var_B0]; struct HPSS__ *
0x180010260  mov     rdx, r15; struct MiniDumpStatusProvider *
0x180010263  mov     rcx, rdi; struct MiniDumpAllocationProvider *
0x180010266  call    ?DetermineSystemProvider@@YAJPEAVMiniDumpAllocationProvider@@PEAVMiniDumpStatusProvider@@PEAXQEAU_MINIDUMP_CALLBACK_INFORMATION@@PEAPEAVMiniDumpSystemProvider@@@Z; DetermineSystemProvider(MiniDumpAllocationProvider *,MiniDumpStatusProvider *,void *,_MINIDUMP_CALLBACK_INFORMATION * const,MiniDumpSystemProvider * *)
0x18001026b  mov     ebx, eax
0x18001026d  mov     r14, [rbp+3Fh+var_90]
0x180010271  test    eax, eax
0x180010273  jz      short loc_180010281
0x180010275  lea     rdx, aDeterminesyste; "DetermineSystemProvider"
0x18001027c  jmp     loc_1800103CC
0x180010281  lea     r9, [rsp+130h+var_C0]; struct MiniDumpOutputProvider **
0x180010286  mov     rsi, [rbp+3Fh+var_78]
0x18001028a  mov     r8, rsi; struct _MINIDUMP_CALLBACK_INFORMATION *
0x18001028d  mov     rdx, [rbp+3Fh+var_88]; void *
0x180010291  mov     rcx, rdi; struct MiniDumpAllocationProvider *
0x180010294  call    ?DetermineOutputProvider@@YAJPEAVMiniDumpAllocationProvider@@PEAXQEAU_MINIDUMP_CALLBACK_INFORMATION@@PEAPEAVMiniDumpOutputProvider@@@Z; DetermineOutputProvider(MiniDumpAllocationProvider *,void *,_MINIDUMP_CALLBACK_INFORMATION * const,MiniDumpOutputProvider * *)
0x180010299  mov     ebx, eax
0x18001029b  test    eax, eax
0x18001029d  jz      short loc_1800102C7
0x18001029f  lea     rdx, aDetermineoutpu; "DetermineOutputProvider"
0x1800102a6  movaps  xmm0, xmmword ptr [rbp+3Fh+Uuid.Data1]
0x1800102aa  mov     r8d, eax; int
0x1800102ad  movdqa  xmmword ptr [rsp+130h+var_E0.Data1], xmm0
0x1800102b3  lea     rcx, [rsp+130h+var_E0]; struct _GUID
0x1800102b8  call    ?TelemetryLogFunctionCallWithResult@@YAXU_GUID@@PEBGJ@Z; TelemetryLogFunctionCallWithResult(_GUID,ushort const *,long)
0x1800102bd  mov     rsi, [rsp+130h+var_C0]
0x1800102c2  jmp     loc_1800103E3
0x1800102c7  test    r12, r12
0x1800102ca  jz      loc_18001035E
0x1800102d0  mov     eax, [r12]
0x1800102d4  mov     dword ptr [rbp+3Fh+var_A8], eax
0x1800102d7  mov     eax, [r12+0Ch]
0x1800102dc  mov     dword ptr [rbp+3Fh+var_98+4], eax
0x1800102df  test    eax, eax
0x1800102e1  jz      short loc_18001032A
0x1800102e3  xorps   xmm0, xmm0
0x1800102e6  movups  xmmword ptr [rbp+3Fh+var_88], xmm0
0x1800102ea  mov     rax, [r14]
0x1800102ed  mov     dword ptr [rsp+130h+var_110], 10h
0x1800102f5  lea     r9, [rbp+3Fh+var_88]
0x1800102f9  mov     r8, [r12+4]
0x1800102fe  mov     rdx, [rbp+3Fh+var_B0]
0x180010302  mov     rcx, r14
0x180010305  mov     rax, [rax+0F0h]
0x18001030c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010311  mov     ebx, eax
0x180010313  test    eax, eax
0x180010315  jz      short loc_180010320
0x180010317  lea     rdx, aSysprovReadall; "SysProv->ReadAllVirtual"
0x18001031e  jmp     short loc_1800102A6
0x180010320  mov     rcx, [rbp+3Fh+var_88]
0x180010324  mov     rax, [rbp+3Fh+var_88+8]
0x180010328  jmp     short loc_18001033B
0x18001032a  mov     rax, [r12+4]
0x18001032f  test    rax, rax
0x180010332  jz      short loc_180010345
0x180010334  mov     rcx, [rax]
0x180010337  mov     rax, [rax+8]
0x18001033b  mov     qword ptr [rbp+3Fh+var_A8+4], rcx
0x18001033f  mov     qword ptr [rbp+3Fh+var_A8+0Ch], rax
0x180010343  jmp     short loc_18001034F
0x180010345  xorps   xmm0, xmm0
0x180010348  movdqu  [rbp+3Fh+var_A8+4], xmm0
0x18001034d  xor     ecx, ecx
0x18001034f  neg     rcx
0x180010352  sbb     rax, rax
0x180010355  lea     rcx, [rbp+3Fh+var_A8]
0x180010359  and     rax, rcx
0x18001035c  jmp     short loc_180010360
0x18001035e  xor     eax, eax
0x180010360  mov     dword ptr [rsp+130h+var_E0.Data2], 0
0x180010368  mov     [rsp+130h+var_D0], 0
0x180010371  mov     ecx, [rbp+3Fh+var_B8]
0x180010374  mov     [rsp+130h+var_E0.Data1], ecx
0x180010378  mov     qword ptr [rsp+130h+var_E0.Data4], 7FFE03D8h
0x180010381  mov     [rsp+130h+var_E8], rsi
0x180010386  mov     rcx, [rbp+3Fh+var_70]
0x18001038a  mov     [rsp+130h+var_F0], rcx
0x18001038f  mov     [rsp+130h+var_F8], rax
0x180010394  lea     rax, [rsp+130h+var_E0]
0x180010399  mov     [rsp+130h+var_100], rax
0x18001039e  mov     [rsp+130h+var_108], r15
0x1800103a3  mov     [rsp+130h+var_110], rdi
0x1800103a8  mov     rsi, [rsp+130h+var_C0]
0x1800103ad  mov     r9, rsi
0x1800103b0  mov     r8, r14
0x1800103b3  mov     edx, [rbp+3Fh+var_B4]
0x1800103b6  mov     rcx, [rbp+3Fh+var_B0]
0x1800103ba  call    MiniDumpProvideDump
0x1800103bf  mov     ebx, eax
0x1800103c1  test    eax, eax
0x1800103c3  jz      short loc_1800103E3
0x1800103c5  lea     rdx, aMinidumpprovid; "MiniDumpProvideDump"
0x1800103cc  movaps  xmm0, xmmword ptr [rbp+3Fh+Uuid.Data1]
0x1800103d0  movdqa  xmmword ptr [rsp+130h+var_E0.Data1], xmm0
0x1800103d6  mov     r8d, eax; int
0x1800103d9  lea     rcx, [rsp+130h+var_E0]; struct _GUID
0x1800103de  call    ?TelemetryLogFunctionCallWithResult@@YAXU_GUID@@PEBGJ@Z; TelemetryLogFunctionCallWithResult(_GUID,ushort const *,long)
0x1800103e3  test    r14, r14
0x1800103e6  jz      short loc_1800103F6
0x1800103e8  mov     rax, [r14]
0x1800103eb  mov     rcx, r14
0x1800103ee  mov     rax, [rax]
0x1800103f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103f6  test    rsi, rsi
0x1800103f9  jz      short loc_180010409
0x1800103fb  mov     rax, [rsi]
0x1800103fe  mov     rcx, rsi
0x180010401  mov     rax, [rax]
0x180010404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010409  mov     rax, [r15]
0x18001040c  mov     rcx, r15
0x18001040f  mov     rax, [rax]
0x180010412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010417  jmp     short loc_18001043E
0x180010419  mov     eax, 8007000Eh
0x18001041e  mov     ebx, eax
0x180010420  movaps  xmm0, xmmword ptr [rbp+3Fh+Uuid.Data1]
0x180010424  movdqa  xmmword ptr [rsp+130h+var_E0.Data1], xmm0
0x18001042a  mov     r8d, eax; int
0x18001042d  lea     rdx, aDeterminestatu; "DetermineStatusProvider"
0x180010434  lea     rcx, [rsp+130h+var_E0]; struct _GUID
0x180010439  call    ?TelemetryLogFunctionCallWithResult@@YAXU_GUID@@PEBGJ@Z; TelemetryLogFunctionCallWithResult(_GUID,ushort const *,long)
0x18001043e  test    rdi, rdi
0x180010441  jz      short loc_180010451
0x180010443  mov     rax, [rdi]
0x180010446  mov     rcx, rdi
0x180010449  mov     rax, [rax]
0x18001044c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010451  test    ebx, ebx
0x180010453  jnz     short loc_1800104D1
0x180010455  movaps  xmm0, xmmword ptr [rbp+3Fh+Uuid.Data1]
0x180010459  movdqa  xmmword ptr [rsp+130h+var_E0.Data1], xmm0
0x18001045f  xor     r8d, r8d; int
0x180010462  lea     rdx, aMinidumpcomple; "MiniDumpCompletedWithSuccess"
0x180010469  lea     rcx, [rsp+130h+var_E0]; struct _GUID
0x18001046e  call    ?TelemetryLogActionWithResult@@YAXU_GUID@@PEBGJ@Z; TelemetryLogActionWithResult(_GUID,ushort const *,long)
0x180010473  call    ?TelemetryUninitialize@@YAXXZ; TelemetryUninitialize(void)
0x180010478  nop
0x180010479  call    ?IsRequiredApiSetPresent@ScopedDisableBrokering@FileAPIs@Win32@@SA_NXZ; Win32::FileAPIs::ScopedDisableBrokering::IsRequiredApiSetPresent(void)
0x18001047e  test    al, al
0x180010480  jz      short loc_18001049C
0x180010482  test    r13b, r13b
0x180010485  jnz     short loc_18001049C
0x180010487  mov     rax, gs:30h
0x180010490  mov     ecx, 7FFFh
0x180010495  and     [rax+17EEh], cx
0x18001049c  mov     eax, 1
0x1800104a1  jmp     short loc_180010522
0x1800104a3  mov     rcx, rbx; hHeap
0x1800104a6  call    cs:__imp_HeapDestroy
0x1800104ac  mov     eax, 8007000Eh
0x1800104b1  mov     ebx, eax
0x1800104b3  movaps  xmm0, xmmword ptr [rbp+3Fh+Uuid.Data1]
0x1800104b7  movdqa  xmmword ptr [rsp+130h+var_E0.Data1], xmm0
0x1800104bd  mov     r8d, eax; int
0x1800104c0  lea     rdx, aMinidumpcreate; "MiniDumpCreateLiveAllocationProvider"
0x1800104c7  lea     rcx, [rsp+130h+var_E0]; struct _GUID
0x1800104cc  call    ?TelemetryLogFunctionCallWithResult@@YAXU_GUID@@PEBGJ@Z; TelemetryLogFunctionCallWithResult(_GUID,ushort const *,long)
0x1800104d1  movaps  xmm0, xmmword ptr [rbp+3Fh+Uuid.Data1]
0x1800104d5  movdqa  xmmword ptr [rsp+130h+var_E0.Data1], xmm0
0x1800104db  mov     r8d, ebx; int
0x1800104de  lea     rdx, aMinidumpcomple_0; "MiniDumpCompletedWithFailure"
0x1800104e5  lea     rcx, [rsp+130h+var_E0]; struct _GUID
0x1800104ea  call    ?TelemetryLogActionWithResult@@YAXU_GUID@@PEBGJ@Z; TelemetryLogActionWithResult(_GUID,ushort const *,long)
0x1800104ef  call    ?TelemetryUninitialize@@YAXXZ; TelemetryUninitialize(void)
0x1800104f4  nop
0x1800104f5  call    ?IsRequiredApiSetPresent@ScopedDisableBrokering@FileAPIs@Win32@@SA_NXZ; Win32::FileAPIs::ScopedDisableBrokering::IsRequiredApiSetPresent(void)
0x1800104fa  test    al, al
0x1800104fc  jz      short loc_180010518
0x1800104fe  test    r13b, r13b
0x180010501  jnz     short loc_180010518
0x180010503  mov     rax, gs:30h
0x18001050c  mov     ecx, 7FFFh
0x180010511  and     [rax+17EEh], cx
0x180010518  mov     ecx, ebx; dwErrCode
0x18001051a  call    cs:__imp_SetLastError
0x180010520  xor     eax, eax
0x180010522  mov     rcx, [rbp+3Fh+var_50]
0x180010526  xor     rcx, rsp; StackCookie
0x180010529  call    __security_check_cookie
0x18001052e  add     rsp, 0F8h
0x180010535  pop     r15
0x180010537  pop     r14
0x180010539  pop     r13
0x18001053b  pop     r12
0x18001053d  pop     rdi
0x18001053e  pop     rsi
0x18001053f  pop     rbx
0x180010540  pop     rbp
0x180010541  retn
```
