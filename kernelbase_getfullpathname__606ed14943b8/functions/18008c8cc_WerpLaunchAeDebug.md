# WerpLaunchAeDebug

- ea: `0x18008c8cc`
- end: `0x18008d2cf`
- name: `WerpLaunchAeDebug`
- size: `2563`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180120ea0`

## callees

- `0x18004b490`
- `0x18004b9d0`
- `0x180053c30`
- `0x18008c7f0`
- `0x18008c8cc`
- `0x18008d2e0`
- `0x18008d8f0`
- `0x18008d990`
- `0x18008d9f0`
- `0x18008e220`
- `0x1800b8f50`
- `0x1800eb920`
- `0x1800f6f50`
- `0x1800fe770`
- `0x180130e98`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18008cf9f`
- `ntdll!RtlSetLastWin32Error` at `0x18008cf9f`
- `ntdll!RtlSetCurrentTransaction` at `0x18008cdbf`
- `ntdll!RtlSetCurrentTransaction` at `0x18008d20f`
- `ntdll!RtlSetCurrentTransaction` at `0x18008cdbf`
- `ntdll!RtlSetCurrentTransaction` at `0x18008d20f`
- `ntdll!NtQuerySystemInformation` at `0x18008ca97`
- `ntdll!NtQuerySystemInformation` at `0x18008ca97`
- `ntdll!RtlGetCurrentTransaction` at `0x18008cdad`
- `ntdll!RtlGetCurrentTransaction` at `0x18008cdad`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18008ccc7`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18008ccc7`
- `ntdll!DbgPrintEx` at `0x18008cd35`
- `ntdll!DbgPrintEx` at `0x18008cd9c`
- `ntdll!DbgPrintEx` at `0x18008ceb1`
- `ntdll!DbgPrintEx` at `0x18008ceeb`
- `ntdll!DbgPrintEx` at `0x18008cf74`
- `ntdll!DbgPrintEx` at `0x18008cd35`
- `ntdll!DbgPrintEx` at `0x18008cd9c`
- `ntdll!DbgPrintEx` at `0x18008ceb1`
- `ntdll!DbgPrintEx` at `0x18008ceeb`
- `ntdll!DbgPrintEx` at `0x18008cf74`
- `ntdll!NtQueryInformationProcess` at `0x18008ce79`
- `ntdll!NtQueryInformationProcess` at `0x18008ce79`
- `ntdll!RtlGetNtSystemRoot` at `0x18008ccdf`
- `ntdll!RtlGetNtSystemRoot` at `0x18008ccdf`
- `ntdll!NtWaitForMultipleObjects` at `0x18008d19e`
- `ntdll!NtWaitForMultipleObjects` at `0x18008d19e`
- `ntdll!NtAllocateVirtualMemory` at `0x18008c9e1`
- `ntdll!NtAllocateVirtualMemory` at `0x18008cb0b`
- `ntdll!NtAllocateVirtualMemory` at `0x18008c9e1`
- `ntdll!NtAllocateVirtualMemory` at `0x18008cb0b`

## string_xrefs

- `0x18008cd12`: `WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printing the debugger path with 0x%x\n`
- `0x18008cfd3`: `WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n`
- `0x18008d043`: `WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n`
- `0x18008cceb`: `%s\system32\%s`
- `0x18008d094`: `WER/CrashAPI/%u:%u: ERROR UpdateProcThreadAttribute failed: 0x%x\n`
- `0x18008cd79`: `WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printng the debugger commandline with 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpLaunchAeDebug(__int64 a1, __int64 a2, __int64 a3, _OWORD *a4, ULONG_PTR a5)
{
  _DWORD *v5; // r12
  struct _PROC_THREAD_ATTRIBUTE_LIST *v8; // rdi
  __int64 v9; // rsi
  signed int LastErrorValue; // r14d
  wchar_t *v11; // rbx
  int UniqueProcess; // r13d
  NTSTATUS v13; // eax
  HANDLE v14; // rcx
  char *v15; // rax
  char *v16; // rsi
  NTSTATUS v17; // eax
  _BYTE *v18; // r13
  __int128 v19; // xmm0
  __int64 v20; // rcx
  __int128 v21; // xmm1
  char *v22; // rax
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  ULONG_PTR v41; // r14
  const wchar_t *v42; // r15
  __int64 NtSystemRoot; // rax
  int v44; // eax
  const CHAR *v45; // r8
  int v46; // eax
  _DWORD *v47; // r12
  unsigned int v48; // r14d
  unsigned int v49; // r8d
  NTSTATUS InformationProcess; // eax
  int v51; // r9d
  int v52; // eax
  ULONG v53; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v54; // rax
  NTSTATUS v55; // eax
  HANDLE v56; // rcx
  ULONG AllocationType[2]; // [rsp+20h] [rbp-E0h]
  ULONG Protect[2]; // [rsp+28h] [rbp-D8h]
  char ProcessInformation[4]; // [rsp+60h] [rbp-A0h] BYREF
  int Value; // [rsp+64h] [rbp-9Ch] BYREF
  PVOID BaseAddress; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  DWORD ProcessId; // [rsp+78h] [rbp-88h]
  ULONG_PTR RegionSize; // [rsp+80h] [rbp-80h] BYREF
  ULONG_PTR Size; // [rsp+88h] [rbp-78h] BYREF
  __int64 CurrentTransaction; // [rsp+90h] [rbp-70h]
  HANDLE v68[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h]
  ULONG_PTR v70; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE Object[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v73; // [rsp+E0h] [rbp-20h] BYREF
  char v74[8]; // [rsp+E8h] [rbp-18h] BYREF
  const WCHAR *v75; // [rsp+F0h] [rbp-10h]
  struct _PROC_THREAD_ATTRIBUTE_LIST *v76; // [rsp+148h] [rbp+48h]
  __int64 SystemInformation; // [rsp+150h] [rbp+50h] BYREF
  int v78; // [rsp+158h] [rbp+58h]
  _DWORD Buffer[4]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v80; // [rsp+170h] [rbp+70h]
  __int64 v81; // [rsp+178h] [rbp+78h]
  __int64 v82; // [rsp+180h] [rbp+80h]
  __int128 v83; // [rsp+188h] [rbp+88h]
  __int128 v84; // [rsp+198h] [rbp+98h]
  __int128 v85; // [rsp+1A8h] [rbp+A8h]
  __int128 v86; // [rsp+1B8h] [rbp+B8h]
  __int128 v87; // [rsp+1C8h] [rbp+C8h]
  __int128 v88; // [rsp+1D8h] [rbp+D8h]
  __int128 v89; // [rsp+1E8h] [rbp+E8h]
  __int128 v90; // [rsp+1F8h] [rbp+F8h]
  __int128 v91; // [rsp+208h] [rbp+108h]
  __int64 v92; // [rsp+218h] [rbp+118h]
  char v93; // [rsp+220h] [rbp+120h] BYREF

  v5 = 0;
  Size = a5;
  hObject = 0;
  v73 = 0;
  memset_0(v74, 0, 0x68u);
  *(&EventAttributes.nLength + 1) = 0;
  v69 = 0;
  SystemInformation = 0;
  v78 = 0;
  *(&EventAttributes.bInheritHandle + 1) = 0;
  *(_OWORD *)v68 = 0;
  v8 = 0;
  v9 = 0;
  *(_OWORD *)Object = 0;
  CurrentTransaction = 0;
  memset_0(Buffer, 0, 0x590u);
  Value = -1;
  ProcessInformation[0] = 0;
  ProcessId = GetProcessId((HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( !ProcessId )
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    v11 = 0;
    if ( LastErrorValue > 0 )
      LastErrorValue = (unsigned __int16)LastErrorValue | 0x80070000;
    goto LABEL_71;
  }
  RegionSize = 1232;
  BaseAddress = 0;
  UniqueProcess = (int)NtCurrentTeb()->ClientId.UniqueProcess;
  v13 = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x1000u, 4u);
  if ( v13 < 0 )
  {
    BaseSetLastNTError((unsigned int)v13);
    v11 = 0;
    goto LABEL_87;
  }
  v11 = (wchar_t *)BaseAddress;
  if ( !BaseAddress )
  {
LABEL_87:
    LastErrorValue = -2147024882;
    goto LABEL_71;
  }
  v14 = hObject;
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.bInheritHandle = 1;
  v15 = (char *)hObject + 1;
  hObject = 0;
  if ( (unsigned __int64)v15 > 1 )
    CloseHandle(v14);
  DuplicateHandle(
    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
    (HANDLE)0xFFFFFFFFFFFFFFFELL,
    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
    &hObject,
    0,
    1,
    2u);
  v16 = (char *)CreateEventExW(&EventAttributes, 0, 1u, 0x1F0003u);
  if ( v16 == (char *)-1LL
    || v16 + 1 == (char *)1
    || !a3
    || NtQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0) < 0 )
  {
    goto LABEL_21;
  }
  Buffer[2] = GetThreadId((HANDLE)0xFFFFFFFFFFFFFFFELL);
  Buffer[1] = (unsigned __int16)SystemInformation;
  v80 = *(_QWORD *)(a3 + 16);
  Buffer[0] = 40;
  Buffer[3] = 0;
  if ( ProcessId == UniqueProcess )
  {
    v81 = a3;
    v5 = Buffer;
    v82 = (__int64)a4;
LABEL_21:
    v18 = 0;
    goto LABEL_22;
  }
  v70 = 1424;
  BaseAddress = 0;
  v17 = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &v70, 0x1000u, 4u);
  if ( v17 < 0 )
  {
    BaseSetLastNTError((unsigned int)v17);
    v18 = 0;
  }
  else
  {
    v18 = BaseAddress;
    if ( BaseAddress )
    {
      v19 = *(_OWORD *)a3;
      v20 = 9;
      v21 = *(_OWORD *)(a3 + 16);
      v92 = *(_QWORD *)(a3 + 144);
      v22 = &v93;
      v83 = v19;
      v23 = *(_OWORD *)(a3 + 32);
      v84 = v21;
      v24 = *(_OWORD *)(a3 + 48);
      v85 = v23;
      v25 = *(_OWORD *)(a3 + 64);
      v86 = v24;
      v26 = *(_OWORD *)(a3 + 80);
      v87 = v25;
      v27 = *(_OWORD *)(a3 + 96);
      v88 = v26;
      v28 = *(_OWORD *)(a3 + 112);
      v89 = v27;
      v29 = *(_OWORD *)(a3 + 128);
      v90 = v28;
      v91 = v29;
      do
      {
        v30 = a4[1];
        *(_OWORD *)v22 = *a4;
        v31 = a4[2];
        *((_OWORD *)v22 + 1) = v30;
        v32 = a4[3];
        *((_OWORD *)v22 + 2) = v31;
        v33 = a4[4];
        *((_OWORD *)v22 + 3) = v32;
        v34 = a4[5];
        *((_OWORD *)v22 + 4) = v33;
        v35 = a4[6];
        *((_OWORD *)v22 + 5) = v34;
        v36 = a4[7];
        a4 += 8;
        *((_OWORD *)v22 + 6) = v35;
        *((_OWORD *)v22 + 7) = v36;
        v22 += 128;
        --v20;
      }
      while ( v20 );
      v37 = a4[1];
      *(_OWORD *)v22 = *a4;
      v38 = a4[2];
      *((_OWORD *)v22 + 1) = v37;
      v39 = a4[3];
      *((_OWORD *)v22 + 2) = v38;
      v40 = a4[4];
      *((_OWORD *)v22 + 3) = v39;
      *((_OWORD *)v22 + 4) = v40;
      RegionSize = v18 - (_BYTE *)Buffer;
      v81 = (__int64)(v18 + 40);
      v82 = (__int64)(v18 + 192);
      if ( WriteProcessMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, v18, Buffer, 0x590u, &RegionSize) )
      {
        if ( RegionSize == 1424 )
          v5 = v18;
      }
    }
  }
LABEL_22:
  v41 = Size + 4;
  if ( *(_WORD *)(Size + 4) == 34 || RtlDetermineDosPathNameType_U((PCWSTR)(Size + 4)) != RtlPathTypeRelative )
  {
    v42 = (const wchar_t *)v41;
  }
  else
  {
    v42 = v11 + 323;
    NtSystemRoot = RtlGetNtSystemRoot();
    v44 = StringCchPrintfW(v11 + 323, 0x125u, L"%s\\system32\\%s", NtSystemRoot, v41);
    LastErrorValue = v44;
    if ( v44 < 0 )
    {
      Protect[0] = v44;
      v45 = "WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printing the debugger path with 0x%x\n";
      AllocationType[0] = 4834;
      goto LABEL_26;
    }
  }
  v46 = StringCchPrintfW(v11, 0x143u, v42, ProcessId, v16, v5);
  LastErrorValue = v46;
  if ( v46 >= 0 )
  {
    CurrentTransaction = RtlGetCurrentTransaction();
    RtlSetCurrentTransaction(0);
    v47 = (_DWORD *)Size;
    LODWORD(v73) = 112;
    v75 = &word_18029DECC;
    v48 = (*(_DWORD *)Size & 4) != 0 ? 0x40000 : 0;
    if ( (*(_DWORD *)Size & 4) != 0 )
    {
      v49 = (*(_DWORD *)Size >> 3) & 0xF;
      if ( v49 < 4 || v49 == 5 || v49 == 6 || v49 == 7 )
      {
        Value = (*(_DWORD *)Size >> 3) & 0xF;
      }
      else
      {
        Value = -1;
        if ( v49 == 14 )
        {
          ProcessInformation[0] = 0;
          InformationProcess = NtQueryInformationProcess(
                                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                 ProcessAffinityUpdateMode|ProcessUserModeIOPL,
                                 ProcessInformation,
                                 1u,
                                 0);
          v51 = (int)NtCurrentTeb()->ClientId.UniqueProcess;
          if ( InformationProcess >= 0 )
          {
            DbgPrintEx(
              0x96u,
              2u,
              "WER/CrashAPI/%u:%u: TRACE Faulting process protection/signer: %02x/%02x\n",
              v51,
              4908,
              ProcessInformation[0] & 7,
              (unsigned __int8)ProcessInformation[0] >> 4);
            if ( (ProcessInformation[0] & 7u) >= 3 || (ProcessInformation[0] & 0xF0u) >= 0x90 )
              v52 = -1;
            else
              v52 = *((_DWORD *)qword_1802E1360
                    + 9 * (ProcessInformation[0] & 7)
                    + ((unsigned __int64)(unsigned __int8)ProcessInformation[0] >> 4));
            Value = v52;
          }
          else
          {
            DbgPrintEx(
              0x96u,
              1u,
              "WER/CrashAPI/%u:%u: WARNING NtQueryInformationProcess/ProcessProtectionInformation failed: NTSTATUS %08X\n",
              v51,
              4903,
              InformationProcess);
          }
        }
      }
    }
    DbgPrintEx(
      0x96u,
      2u,
      "WER/CrashAPI/%u:%u: TRACE Mapped protection level %02X -> %08X\n",
      LODWORD(NtCurrentTeb()->ClientId.UniqueProcess),
      4922,
      (*v47 >> 3) & 0xF,
      Value);
    if ( (*(_BYTE *)v47 & 4) != 0 && Value != -1 )
    {
      RtlSetLastWin32Error(0x7Au);
      v53 = NtCurrentTeb()->LastErrorValue;
      Size = 48;
      if ( v53 != 122 )
      {
        Protect[0] = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        v45 = "WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n";
        AllocationType[0] = 4937;
        LastErrorValue = Protect[0];
        goto LABEL_26;
      }
      v54 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)VirtualAllocExNuma(
                                                    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                                    0,
                                                    0x30u,
                                                    0x1000u,
                                                    4u,
                                                    0xFFFFFFFF);
      v8 = v54;
      if ( !v54 )
      {
        LastErrorValue = -2147024882;
        v45 = "WER/CrashAPI/%u:%u: ERROR Failed to allocate attribute list: 0x%x\n";
        Protect[0] = -2147024882;
        AllocationType[0] = 4950;
        goto LABEL_26;
      }
      if ( !InitializeProcThreadAttributeList(v54, 1u, 0, &Size) )
      {
        Protect[0] = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        v45 = "WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n";
        AllocationType[0] = 4962;
        LastErrorValue = Protect[0];
        goto LABEL_26;
      }
      if ( !UpdateProcThreadAttribute(v8, 0, 0x2000Bu, &Value, 4u, 0, 0) )
      {
        Protect[0] = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        v45 = "WER/CrashAPI/%u:%u: ERROR UpdateProcThreadAttribute failed: 0x%x\n";
        AllocationType[0] = 4978;
        LastErrorValue = Protect[0];
        goto LABEL_26;
      }
      v76 = v8;
      v48 |= 0x80000u;
    }
    if ( v68[0] )
      CloseHandle(v68[0]);
    if ( v68[1] )
      CloseHandle(v68[1]);
    v69 = 0;
    *(_OWORD *)v68 = 0;
    if ( (unsigned int)CreateProcessInternalW(0, 0, v11, 0, 0, 1, v48, 0, 0, (__int64)&v73, (__int64)v68) )
    {
      LastErrorValue = 0;
      if ( (unsigned __int64)(v16 + 1) > 1 )
      {
        Object[1] = v68[0];
        Object[0] = v16;
        while ( 1 )
        {
          v55 = NtWaitForMultipleObjects(2u, Object, WaitAny, 1u, 0);
          if ( !v55 )
            break;
          if ( v55 == 1 )
          {
            LastErrorValue = -2147023829;
            goto LABEL_66;
          }
        }
      }
      goto LABEL_66;
    }
    Protect[0] = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
    v45 = "WER/CrashAPI/%u:%u: ERROR Debugger spawn failed: 0x%x\n";
    AllocationType[0] = 5003;
    LastErrorValue = Protect[0];
  }
  else
  {
    Protect[0] = v46;
    v45 = "WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printng the debugger commandline with 0x%x\n";
    AllocationType[0] = 4855;
  }
LABEL_26:
  DbgPrintEx(
    0x96u,
    0,
    v45,
    LODWORD(NtCurrentTeb()->ClientId.UniqueProcess),
    *(_QWORD *)AllocationType,
    *(_QWORD *)Protect);
LABEL_66:
  if ( v18 )
    VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v18, 0, 0x8000u);
  if ( (unsigned __int64)(v16 + 1) > 1 )
    CloseHandle(v16);
  v9 = CurrentTransaction;
LABEL_71:
  v56 = hObject;
  hObject = 0;
  if ( (unsigned __int64)v56 + 1 > 1 )
    CloseHandle(v56);
  if ( v9 )
    RtlSetCurrentTransaction(v9);
  if ( v11 )
    VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v11, 0, 0x8000u);
  if ( v8 )
    VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v8, 0, 0x8000u);
  if ( v68[0] )
    CloseHandle(v68[0]);
  if ( v68[1] )
    CloseHandle(v68[1]);
  v69 = 0;
  *(_OWORD *)v68 = 0;
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)LastErrorValue;
}

```

## disassembly

```asm
0x18008c8cc  mov     [rsp-8+arg_0], rbx
0x18008c8d1  push    rbp
0x18008c8d2  push    rsi
0x18008c8d3  push    rdi
0x18008c8d4  push    r12
0x18008c8d6  push    r13
0x18008c8d8  push    r14
0x18008c8da  push    r15
0x18008c8dc  lea     rbp, [rsp-600h]
0x18008c8e4  sub     rsp, 700h
0x18008c8eb  mov     rax, cs:__security_cookie
0x18008c8f2  xor     rax, rsp
0x18008c8f5  mov     [rbp+630h+var_40], rax
0x18008c8fc  mov     rax, [rbp+630h+arg_20]
0x18008c903  lea     rcx, [rbp+630h+var_648]; void *
0x18008c907  xor     r12d, r12d
0x18008c90a  mov     [rbp+630h+Size], rax
0x18008c90e  mov     r15, r8
0x18008c911  mov     [rsp+730h+hObject], r12
0x18008c916  xor     edx, edx; Val
0x18008c918  mov     [rbp+630h+var_650], r12
0x18008c91c  mov     r14, r9
0x18008c91f  lea     r8d, [r12+68h]; Size
0x18008c924  call    memset_0
0x18008c929  xor     eax, eax
0x18008c92b  mov     dword ptr [rbp+630h+EventAttributes+4], r12d
0x18008c92f  xorps   xmm0, xmm0
0x18008c932  mov     [rbp+630h+var_688], rax
0x18008c936  xor     edx, edx; Val
0x18008c938  mov     [rbp+630h+SystemInformation], rax
0x18008c93c  mov     r8d, 590h; Size
0x18008c942  mov     [rbp+630h+var_5D8], eax
0x18008c945  lea     rcx, [rbp+630h+Buffer]; void *
0x18008c949  mov     dword ptr [rbp+630h+EventAttributes+14h], r12d
0x18008c94d  movups  xmmword ptr [rbp+630h+var_698], xmm0
0x18008c951  mov     edi, r12d
0x18008c954  mov     esi, r12d
0x18008c957  movups  xmmword ptr [rbp+630h+Object], xmm0
0x18008c95b  mov     [rbp+630h+var_6A0], r12
0x18008c95f  call    memset_0
0x18008c964  or      rcx, 0FFFFFFFFFFFFFFFFh; Process
0x18008c968  mov     [rsp+730h+Value], 0FFFFFFFFh
0x18008c970  mov     [rsp+730h+ProcessInformation], r12b
0x18008c975  call    GetProcessId
0x18008c97a  mov     [rsp+730h+var_6B8], eax
0x18008c97e  test    eax, eax
0x18008c980  jnz     short loc_18008C9A7
0x18008c982  mov     r14d, gs:68h
0x18008c98b  mov     ebx, r12d
0x18008c98e  test    r14d, r14d
0x18008c991  jle     loc_18008D1EE
0x18008c997  movzx   r14d, r14w
0x18008c99b  or      r14d, 80070000h
0x18008c9a2  jmp     loc_18008D1EE
0x18008c9a7  mov     rax, gs:30h
0x18008c9b0  lea     r9, [rbp+630h+RegionSize]; RegionSize
0x18008c9b4  mov     [rsp+730h+Protect], 4; Protect
0x18008c9bc  lea     rdx, [rsp+730h+BaseAddress]; BaseAddress
0x18008c9c1  xor     r8d, r8d; ZeroBits
0x18008c9c4  mov     [rbp+630h+RegionSize], 4D0h
0x18008c9cc  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18008c9d0  mov     [rsp+730h+BaseAddress], r12
0x18008c9d5  mov     r13d, [rax+40h]
0x18008c9d9  mov     [rsp+730h+AllocationType], 1000h; AllocationType
0x18008c9e1  call    cs:__imp_NtAllocateVirtualMemory
0x18008c9e8  nop     dword ptr [rax+rax+00h]
0x18008c9ed  test    eax, eax
0x18008c9ef  js      loc_18008D2BA
0x18008c9f5  mov     rbx, [rsp+730h+BaseAddress]
0x18008c9fa  test    rbx, rbx
0x18008c9fd  jz      loc_18008D2C4
0x18008ca03  mov     rcx, [rsp+730h+hObject]; hObject
0x18008ca08  mov     [rbp+630h+EventAttributes.nLength], 18h
0x18008ca0f  mov     [rbp+630h+EventAttributes.lpSecurityDescriptor], rsi
0x18008ca13  mov     [rbp+630h+EventAttributes.bInheritHandle], 1
0x18008ca1a  lea     rax, [rcx+1]
0x18008ca1e  mov     [rsp+730h+hObject], rsi
0x18008ca23  cmp     rax, 1
0x18008ca27  jbe     short loc_18008CA2E
0x18008ca29  call    CloseHandle
0x18008ca2e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008ca32  mov     [rsp+730h+dwOptions], 2; dwOptions
0x18008ca3a  mov     [rsp+730h+Protect], 1; bInheritHandle
0x18008ca42  lea     r9, [rsp+730h+hObject]; lpTargetHandle
0x18008ca47  mov     r8, rax; hTargetProcessHandle
0x18008ca4a  mov     [rsp+730h+AllocationType], esi; dwDesiredAccess
0x18008ca4e  mov     rcx, rax; hSourceProcessHandle
0x18008ca51  lea     rdx, [rax-1]; hSourceHandle
0x18008ca55  call    DuplicateHandle
0x18008ca5a  xor     edx, edx; lpName
0x18008ca5c  lea     rcx, [rbp+630h+EventAttributes]; lpEventAttributes
0x18008ca60  mov     r9d, 1F0003h; dwDesiredAccess
0x18008ca66  lea     r8d, [rdx+1]; dwFlags
0x18008ca6a  call    CreateEventExW
0x18008ca6f  mov     rsi, rax
0x18008ca72  inc     rax
0x18008ca75  cmp     rax, 1
0x18008ca79  jbe     loc_18008CCAE
0x18008ca7f  test    r15, r15
0x18008ca82  jz      loc_18008CCAE
0x18008ca88  xor     r9d, r9d; ReturnLength
0x18008ca8b  lea     rdx, [rbp+630h+SystemInformation]; SystemInformation
0x18008ca8f  lea     r8d, [r9+0Ch]; SystemInformationLength
0x18008ca93  lea     ecx, [r9+1]; SystemInformationClass
0x18008ca97  call    cs:__imp_NtQuerySystemInformation
0x18008ca9e  nop     dword ptr [rax+rax+00h]
0x18008caa3  test    eax, eax
0x18008caa5  js      loc_18008CCAE
0x18008caab  mov     rcx, 0FFFFFFFFFFFFFFFEh; Thread
0x18008cab2  call    GetThreadId
0x18008cab7  mov     [rbp+630h+var_5C8], eax
0x18008caba  movzx   eax, word ptr [rbp+630h+SystemInformation]
0x18008cabe  mov     [rbp+630h+var_5CC], eax
0x18008cac1  mov     rax, [r15+10h]
0x18008cac5  mov     [rbp+630h+var_5C0], rax
0x18008cac9  mov     [rbp+630h+Buffer], 28h ; '('
0x18008cad0  mov     [rbp+630h+var_5C4], edi
0x18008cad3  cmp     [rsp+730h+var_6B8], r13d
0x18008cad8  jz      loc_18008CC9F
0x18008cade  mov     [rsp+730h+Protect], 4; Protect
0x18008cae6  lea     r9, [rbp+630h+var_680]; RegionSize
0x18008caea  xor     r8d, r8d; ZeroBits
0x18008caed  mov     [rsp+730h+AllocationType], 1000h; AllocationType
0x18008caf5  lea     rdx, [rsp+730h+BaseAddress]; BaseAddress
0x18008cafa  mov     [rbp+630h+var_680], 590h
0x18008cb02  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18008cb06  mov     [rsp+730h+BaseAddress], rdi
0x18008cb0b  call    cs:__imp_NtAllocateVirtualMemory
0x18008cb12  nop     dword ptr [rax+rax+00h]
0x18008cb17  test    eax, eax
0x18008cb19  js      loc_18008CC93
0x18008cb1f  mov     r13, [rsp+730h+BaseAddress]
0x18008cb24  test    r13, r13
0x18008cb27  jz      loc_18008CCB1
0x18008cb2d  movups  xmm0, xmmword ptr [r15]
0x18008cb31  mov     rax, [r15+90h]
0x18008cb38  mov     ecx, 9
0x18008cb3d  movups  xmm1, xmmword ptr [r15+10h]
0x18008cb42  mov     [rbp+630h+var_518], rax
0x18008cb49  lea     rax, [rbp+630h+var_510]
0x18008cb50  movups  [rbp+630h+var_5A8], xmm0
0x18008cb57  lea     edx, [rcx+77h]
0x18008cb5a  movups  xmm0, xmmword ptr [r15+20h]
0x18008cb5f  movups  [rbp+630h+var_598], xmm1
0x18008cb66  movups  xmm1, xmmword ptr [r15+30h]
0x18008cb6b  movups  [rbp+630h+var_588], xmm0
0x18008cb72  movups  xmm0, xmmword ptr [r15+40h]
0x18008cb77  movups  [rbp+630h+var_578], xmm1
0x18008cb7e  movups  xmm1, xmmword ptr [r15+50h]
0x18008cb83  movups  [rbp+630h+var_568], xmm0
0x18008cb8a  movups  xmm0, xmmword ptr [r15+60h]
0x18008cb8f  movups  [rbp+630h+var_558], xmm1
0x18008cb96  movups  xmm1, xmmword ptr [r15+70h]
0x18008cb9b  movups  [rbp+630h+var_548], xmm0
0x18008cba2  movups  xmm0, xmmword ptr [r15+80h]
0x18008cbaa  movups  [rbp+630h+var_538], xmm1
0x18008cbb1  movups  [rbp+630h+var_528], xmm0
0x18008cbb8  movups  xmm0, xmmword ptr [r14]
0x18008cbbc  movups  xmm1, xmmword ptr [r14+10h]
0x18008cbc1  movups  xmmword ptr [rax], xmm0
0x18008cbc4  movups  xmm0, xmmword ptr [r14+20h]
0x18008cbc9  movups  xmmword ptr [rax+10h], xmm1
0x18008cbcd  movups  xmm1, xmmword ptr [r14+30h]
0x18008cbd2  movups  xmmword ptr [rax+20h], xmm0
0x18008cbd6  movups  xmm0, xmmword ptr [r14+40h]
0x18008cbdb  movups  xmmword ptr [rax+30h], xmm1
0x18008cbdf  movups  xmm1, xmmword ptr [r14+50h]
0x18008cbe4  movups  xmmword ptr [rax+40h], xmm0
0x18008cbe8  movups  xmm0, xmmword ptr [r14+60h]
0x18008cbed  movups  xmmword ptr [rax+50h], xmm1
0x18008cbf1  movups  xmm1, xmmword ptr [r14+70h]
0x18008cbf6  add     r14, rdx
0x18008cbf9  movups  xmmword ptr [rax+60h], xmm0
0x18008cbfd  movups  xmmword ptr [rax+70h], xmm1
0x18008cc01  add     rax, rdx
0x18008cc04  sub     rcx, 1
0x18008cc08  jnz     short loc_18008CBB8
0x18008cc0a  movups  xmm0, xmmword ptr [r14]
0x18008cc0e  mov     rcx, r13
0x18008cc11  lea     r8, [rbp+630h+Buffer]; lpBuffer
0x18008cc15  movups  xmm1, xmmword ptr [r14+10h]
0x18008cc1a  mov     rdx, r13; lpBaseAddress
0x18008cc1d  movups  xmmword ptr [rax], xmm0
0x18008cc20  movups  xmm0, xmmword ptr [r14+20h]
0x18008cc25  movups  xmmword ptr [rax+10h], xmm1
0x18008cc29  movups  xmm1, xmmword ptr [r14+30h]
0x18008cc2e  movups  xmmword ptr [rax+20h], xmm0
0x18008cc32  movups  xmm0, xmmword ptr [r14+40h]
0x18008cc37  mov     r14d, 590h
0x18008cc3d  movups  xmmword ptr [rax+30h], xmm1
0x18008cc41  mov     r9d, r14d; nSize
0x18008cc44  movups  xmmword ptr [rax+40h], xmm0
0x18008cc48  lea     rax, [rbp+630h+Buffer]
0x18008cc4c  sub     rcx, rax
0x18008cc4f  lea     rax, [rbp+630h+var_5A8]
0x18008cc56  add     rax, rcx
0x18008cc59  mov     [rbp+630h+RegionSize], rcx
0x18008cc5d  mov     [rbp+630h+var_5B8], rax
0x18008cc61  lea     rax, [rbp+630h+var_510]
0x18008cc68  add     rax, rcx
0x18008cc6b  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x18008cc6f  mov     [rbp+630h+var_5B0], rax
0x18008cc76  lea     rax, [rbp+630h+RegionSize]
0x18008cc7a  mov     qword ptr [rsp+730h+AllocationType], rax; lpNumberOfBytesWritten
0x18008cc7f  call    WriteProcessMemory
0x18008cc84  test    eax, eax
0x18008cc86  jz      short loc_18008CCB1
0x18008cc88  cmp     [rbp+630h+RegionSize], r14
0x18008cc8c  jnz     short loc_18008CCB1
0x18008cc8e  mov     r12, r13
0x18008cc91  jmp     short loc_18008CCB1
0x18008cc93  mov     ecx, eax
0x18008cc95  call    BaseSetLastNTError
0x18008cc9a  xor     r13d, r13d
0x18008cc9d  jmp     short loc_18008CCB1
0x18008cc9f  mov     [rbp+630h+var_5B8], r15
0x18008cca3  lea     r12, [rbp+630h+Buffer]
0x18008cca7  mov     [rbp+630h+var_5B0], r14
0x18008ccae  mov     r13, rdi
0x18008ccb1  mov     r14, [rbp+630h+Size]
0x18008ccb5  add     r14, 4
0x18008ccb9  cmp     word ptr [r14], 22h ; '"'
0x18008ccbe  jz      loc_18008CD49
0x18008ccc4  mov     rcx, r14; Path
0x18008ccc7  call    cs:__imp_RtlDetermineDosPathNameType_U
0x18008ccce  nop     dword ptr [rax+rax+00h]
0x18008ccd3  cmp     eax, 5
0x18008ccd6  jnz     short loc_18008CD49
0x18008ccd8  lea     r15, [rbx+286h]
0x18008ccdf  call    cs:__imp_RtlGetNtSystemRoot
0x18008cce6  nop     dword ptr [rax+rax+00h]
0x18008cceb  lea     r8, aSSystem32S; "%s\\system32\\%s"
0x18008ccf2  mov     qword ptr [rsp+730h+AllocationType], r14
0x18008ccf7  mov     r9, rax
0x18008ccfa  mov     edx, 125h; unsigned __int64
0x18008ccff  mov     rcx, r15; wchar_t *
0x18008cd02  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008cd07  mov     r14d, eax
0x18008cd0a  test    eax, eax
0x18008cd0c  jns     short loc_18008CD4C
0x18008cd0e  mov     [rsp+730h+Protect], eax
0x18008cd12  lea     r8, aWerCrashapiUUE_9; "WER/CrashAPI/%u:%u: ERROR StringCchPrin"...
0x18008cd19  mov     [rsp+730h+AllocationType], 12E2h
0x18008cd21  mov     ecx, 96h; ComponentId
0x18008cd26  mov     r9, gs:30h
0x18008cd2f  xor     edx, edx; Level
0x18008cd31  mov     r9d, [r9+40h]
0x18008cd35  call    cs:__imp_DbgPrintEx
0x18008cd3c  nop     dword ptr [rax+rax+00h]
0x18008cd41  xor     r12d, r12d
0x18008cd44  jmp     loc_18008D1BE
0x18008cd49  mov     r15, r14
0x18008cd4c  mov     r9d, [rsp+730h+var_6B8]
0x18008cd51  mov     r8, r15; wchar_t *
0x18008cd54  mov     qword ptr [rsp+730h+Protect], r12
0x18008cd59  mov     edx, 143h; unsigned __int64
0x18008cd5e  mov     rcx, rbx; wchar_t *
0x18008cd61  mov     qword ptr [rsp+730h+AllocationType], rsi
0x18008cd66  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008cd6b  xor     r12d, r12d
0x18008cd6e  mov     r14d, eax
0x18008cd71  test    eax, eax
0x18008cd73  jns     short loc_18008CDAD
0x18008cd75  mov     [rsp+730h+Protect], eax
0x18008cd79  lea     r8, aWerCrashapiUUE_30; "WER/CrashAPI/%u:%u: ERROR StringCchPrin"...
0x18008cd80  mov     [rsp+730h+AllocationType], 12F7h
0x18008cd88  mov     ecx, 96h; ComponentId
0x18008cd8d  mov     r9, gs:30h
0x18008cd96  xor     edx, edx; Level
0x18008cd98  mov     r9d, [r9+40h]
0x18008cd9c  call    cs:__imp_DbgPrintEx
0x18008cda3  nop     dword ptr [rax+rax+00h]
0x18008cda8  jmp     loc_18008D1BE
0x18008cdad  call    cs:__imp_RtlGetCurrentTransaction
0x18008cdb4  nop     dword ptr [rax+rax+00h]
0x18008cdb9  xor     ecx, ecx
0x18008cdbb  mov     [rbp+630h+var_6A0], rax
0x18008cdbf  call    cs:__imp_RtlSetCurrentTransaction
0x18008cdc6  nop     dword ptr [rax+rax+00h]
0x18008cdcb  mov     r12, [rbp+630h+Size]
0x18008cdcf  lea     rax, word_18029DECC
0x18008cdd6  mov     dword ptr [rbp+630h+var_650], 70h ; 'p'
0x18008cddd  mov     r15d, 96h
0x18008cde3  mov     [rbp+630h+var_640], rax
0x18008cde7  mov     r8d, [r12]
0x18008cdeb  mov     edx, r8d
0x18008cdee  and     edx, 4
0x18008cdf1  mov     ecx, edx
0x18008cdf3  neg     ecx
0x18008cdf5  sbb     r14d, r14d
0x18008cdf8  and     r14d, 40000h
0x18008cdff  test    edx, edx
0x18008ce01  jz      loc_18008CF3A
0x18008ce07  shr     r8d, 3
0x18008ce0b  and     r8d, 0Fh
0x18008ce0f  mov     eax, r8d
0x18008ce12  jz      loc_18008CF35
0x18008ce18  sub     eax, 1
0x18008ce1b  jz      loc_18008CF35
0x18008ce21  sub     eax, 1
  ... truncated ...
```
