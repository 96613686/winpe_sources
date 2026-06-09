# MiniDumpProvideDump

- ea: `0x18000f8e8`
- end: `0x180010058`
- name: `MiniDumpProvideDump`
- size: `1904`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *, __int64, __int64, __int64, int *, struct _MINIDUMP_EXCEPTION_INFORMATION64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800100f0`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x1800053dc`
- `0x1800058d0`
- `0x18000670c`
- `0x180006a58`
- `0x180007234`
- `0x180007960`
- `0x18000c19c`
- `0x18000d460`
- `0x18000f8e8`
- `0x180019e3c`
- `0x18001a010`
- `0x18001ad48`
- `0x18001f334`
- `0x180026934`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000f9b4`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000f9b4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000f9d1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000f9e7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000f9fd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fa13`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fa29`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000f9d1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000f9e7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000f9fd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fa13`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fa29`

## string_xrefs

- `0x18000faef`: `MiniDumpWithMemoryCompressed and MiniDumpWithFullMemory are both set, ignore MiniDumpWithFullMemory.`
- `0x18000ff63`: `Write.Start failed, 0x%08x`
- `0x18000f99b`: `dbghelp.dll`
- `0x18000fa1d`: `SymFunctionTableAccess64AccessRoutines`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MiniDumpProvideDump(
        __int64 a1,
        int a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        struct _MINIDUMP_EXCEPTION_INFORMATION64 *a8,
        __int64 a9,
        __int64 a10)
{
  HMODULE Library; // rax
  FARPROC v12; // rax
  const char *v13; // r8
  int v15; // ebx
  unsigned int v16; // ecx
  unsigned int v17; // edi
  int SystemType; // ebx
  _QWORD *v19; // rbx
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // eax
  int v23; // ecx
  struct _MINIDUMP_USER_STREAM *v24; // r13
  struct _EXCEPTION_INFO *v25; // rcx
  void *v26; // r9
  char v27; // al
  struct _INTERNAL_PROCESS *v28; // r14
  struct _MINIDUMP_EXCEPTION_INFORMATION64 **i; // rbx
  unsigned int v30; // r9d
  unsigned __int64 v31; // r8
  unsigned int v32; // r14d
  __int64 v33; // rdx
  unsigned int v34; // eax
  int v35; // eax
  bool v36; // zf
  unsigned int v37; // [rsp+40h] [rbp-C0h] BYREF
  struct _INTERNAL_PROCESS *v38; // [rsp+48h] [rbp-B8h] BYREF
  struct _LIST_ENTRY v39; // [rsp+50h] [rbp-B0h] BYREF
  FARPROC ProcAddress; // [rsp+60h] [rbp-A0h] BYREF
  FARPROC v41; // [rsp+68h] [rbp-98h]
  FARPROC v42; // [rsp+70h] [rbp-90h]
  FARPROC v43; // [rsp+78h] [rbp-88h]
  FARPROC v44; // [rsp+80h] [rbp-80h]
  HMODULE hModule; // [rsp+88h] [rbp-78h]
  int v46; // [rsp+90h] [rbp-70h]
  _QWORD *v47; // [rsp+98h] [rbp-68h]
  struct _MINIDUMP_EXCEPTION_INFORMATION64 *v48; // [rsp+A0h] [rbp-60h]
  __int64 v49; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-48h]
  _OWORD v52[3]; // [rsp+C0h] [rbp-40h] BYREF
  int v53; // [rsp+F0h] [rbp-10h]
  int v54; // [rsp+100h] [rbp+0h] BYREF
  __int64 v55; // [rsp+104h] [rbp+4h]
  int v56; // [rsp+10Ch] [rbp+Ch]
  int v57; // [rsp+110h] [rbp+10h]
  char v58[1292]; // [rsp+114h] [rbp+14h] BYREF
  __int64 v59; // [rsp+620h] [rbp+520h] BYREF
  int v60; // [rsp+628h] [rbp+528h]
  _QWORD *v61; // [rsp+630h] [rbp+530h]
  __int64 v62; // [rsp+638h] [rbp+538h]
  __int64 v63; // [rsp+640h] [rbp+540h]
  __int64 v64; // [rsp+648h] [rbp+548h]
  FARPROC *p_ProcAddress; // [rsp+650h] [rbp+550h]
  unsigned int v66; // [rsp+658h] [rbp+558h]
  __int64 (__fastcall *v67)(__int64, int *, _OWORD *); // [rsp+660h] [rbp+560h]
  struct _EXCEPTION_INFO *v68; // [rsp+668h] [rbp+568h] BYREF
  __int64 v69; // [rsp+670h] [rbp+570h]
  int v70; // [rsp+678h] [rbp+578h]
  int v71; // [rsp+6ACh] [rbp+5ACh]
  unsigned int v72; // [rsp+6CCh] [rbp+5CCh]
  __int64 v73; // [rsp+6D0h] [rbp+5D0h]
  int v74; // [rsp+6D8h] [rbp+5D8h]
  int v75; // [rsp+6DCh] [rbp+5DCh]
  int v76; // [rsp+6E0h] [rbp+5E0h]
  unsigned int v77; // [rsp+6E8h] [rbp+5E8h]
  __int64 v78; // [rsp+6F0h] [rbp+5F0h]
  int v79; // [rsp+6F8h] [rbp+5F8h]
  _BYTE v80[160]; // [rsp+700h] [rbp+600h] BYREF
  __int64 v81; // [rsp+7A0h] [rbp+6A0h]

  v51 = a5;
  v47 = a3;
  v46 = a2;
  v50 = a1;
  v48 = a8;
  v38 = 0;
  memset_0(v80, 0, 0xF0u);
  memset_0(&v59, 0, 0xE0u);
  ProcAddress = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v39 = 0;
  v44 = 0;
  Library = LoadLibraryExW(L"dbghelp.dll", 0, 0);
  hModule = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "StackWalk64");
    v41 = GetProcAddress(hModule, "SymInitialize");
    v42 = GetProcAddress(hModule, "SymCleanup");
    v43 = GetProcAddress(hModule, "SymRegisterFunctionEntryCallback64");
    v12 = GetProcAddress(hModule, "SymFunctionTableAccess64AccessRoutines");
    v44 = v12;
    if ( !ProcAddress || !v41 || !v42 || !v43 || !v12 )
      UplevelCalls::CleanupStackWalk((UplevelCalls *)&ProcAddress);
  }
  if ( (*a7 & 0xF8000000) != 0 )
  {
    v13 = "Invalid dump type 0x%x";
LABEL_10:
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD))(*(_QWORD *)a6 + 8LL))(
      a6,
      4,
      v13,
      (unsigned int)*a7);
LABEL_11:
    UplevelCalls::CleanupStackWalk((UplevelCalls *)&ProcAddress);
    return 2147942487LL;
  }
  if ( (*a7 & 0x300000) == 0x300000 )
  {
    v13 = "AVX XState info is not allowed in Triage dump files due to potential PII exposure.\n"
          "Triage dumps cannot contain PII. 0x%x";
    goto LABEL_10;
  }
  if ( (*a7 & 0x2020000) == 0x2020000 )
    goto LABEL_11;
  v15 = *a7 | 0x20000;
  if ( (*a7 & 0x2000002) != 2 )
    v15 = *a7;
  if ( (v15 & 0x4000002) == 0x4000002 )
  {
    v15 &= ~2u;
    (*(void (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)a6 + 8LL))(
      a6,
      2,
      "MiniDumpWithMemoryCompressed and MiniDumpWithFullMemory are both set, ignore MiniDumpWithFullMemory.");
  }
  v16 = v15 & 0xFBFE7DBD;
  if ( (v15 & 0x400) == 0 )
    v16 = v15;
  v17 = v16 & 0xFFE65CA6;
  if ( (v16 & 0x4000002) == 0 )
    v17 = v16;
  if ( (v17 & 0x100000) != 0 )
    v17 = v17 & 0xFFFBFF7F | 0x80;
  if ( (v17 & 0x4000806) == 0 || !(*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a4 + 8LL))(a4, 0) )
  {
    v19 = v47;
    if ( (v17 & 0x100000) == 0 )
    {
      v20 = *((_QWORD *)a7 + 1);
      if ( v20 )
      {
        v21 = *v47;
        v49 = 0;
        v37 = 0;
        if ( !(*(unsigned int (__fastcall **)(_QWORD *, __int64, __int64, __int64 *, int, unsigned int *))(v21 + 232))(
                v47,
                v50,
                v20 + 816,
                &v49,
                8,
                &v37)
          && v37 == 8
          && (v49 & 0x800) != 0 )
        {
          v17 |= 0x200000u;
        }
      }
    }
    v38 = 0;
    v61 = v19;
    v39.Blink = &v39;
    v39.Flink = &v39;
    v59 = v50;
    v60 = v46;
    v63 = v51;
    p_ProcAddress = &ProcAddress;
    v78 = *((_QWORD *)a7 + 1);
    v62 = a4;
    v64 = a6;
    v66 = v17;
    v68 = 0;
    v73 = 0;
    v76 = 1;
    v77 = v17;
    v79 = 0;
    v70 = 0;
    v74 = (v17 & 0x10200) != 0 ? 16 : 11;
    v75 = (1 << ((v17 & 0x10200) != 0 ? 16 : 11)) - 1;
    if ( a10 )
    {
      v67 = *(__int64 (__fastcall **)(__int64, int *, _OWORD *))a10;
      v69 = *(_QWORD *)(a10 + 8);
    }
    else
    {
      v67 = 0;
      v69 = 0;
    }
    SystemType = GetSystemType((struct _MINIDUMP_STATE *)&v59);
    if ( SystemType )
      goto LABEL_80;
    v79 = v71;
    memset_0(v58, 0, sizeof(v58));
    v55 = v59;
    v54 = v60;
    memset(v52, 0, sizeof(v52));
    v57 = v70;
    LODWORD(v52[0]) = v70;
    v56 = 15;
    v53 = 0;
    if ( v67 )
    {
      v22 = v67(v69, &v54, v52);
      v23 = v70;
      if ( v22 )
        v23 = v52[0];
      v70 = v23;
    }
    SystemType = GetExceptionInfo((struct _MINIDUMP_STATE *)&v59, v48, &v68);
    if ( SystemType )
      goto LABEL_76;
    if ( a9 )
    {
      v24 = *(struct _MINIDUMP_USER_STREAM **)(a9 + 4);
      v37 = *(_DWORD *)a9;
    }
    else
    {
      v24 = 0;
      v37 = 0;
    }
    SystemType = GenGetProcessInfo(v17, (struct _MINIDUMP_STATE *)&v59, &v38, &v39);
    if ( SystemType )
      goto LABEL_76;
    v25 = v68;
    if ( v68 )
    {
      v26 = (void *)*((_QWORD *)v68 + 20);
      if ( v26 )
      {
        GenFilterContext((struct _MINIDUMP_STATE *)&v59, v38, 0, v26, *((_DWORD *)v68 + 42), 1u);
        v25 = v68;
      }
      if ( v25 && (v17 & 0x4000002) == 0 && v72 )
        GenAddMemoryBlock(
          (struct _MINIDUMP_STATE *)&v59,
          (__int64)v38,
          6u,
          0,
          *(_QWORD *)((char *)v25 + 20) - ((unsigned __int64)v72 >> 1),
          v72);
    }
    v27 = v66;
    v28 = v38;
    if ( (v66 & 0x18) != 0 )
    {
      SystemType = FilterOrScanMemory((struct _MINIDUMP_STATE *)&v59, v38);
      if ( SystemType )
        goto LABEL_76;
      v27 = v66;
    }
    if ( (v27 & 0x40) != 0 )
    {
      for ( i = (struct _MINIDUMP_EXCEPTION_INFORMATION64 **)*((_QWORD *)v28 + 13);
            i != (struct _MINIDUMP_EXCEPTION_INFORMATION64 **)((char *)v28 + 104);
            i = (struct _MINIDUMP_EXCEPTION_INFORMATION64 **)v48 )
      {
        v30 = *((_DWORD *)i - 14) - *((_DWORD *)i - 12);
        v31 = (unsigned __int64)*(i - 6);
        v48 = *i;
        if ( (unsigned int)AddIndirectMemory((struct _MINIDUMP_STATE *)&v59, v28, v31, v30)
          || (unsigned int)AddIndirectMemory(
                             (struct _MINIDUMP_STATE *)&v59,
                             v28,
                             (unsigned __int64)*(i - 4),
                             *((_DWORD *)i - 6)) )
        {
          break;
        }
      }
    }
    SystemType = ExecuteCallbacks((struct _MINIDUMP_STATE *)&v59, v38);
    if ( SystemType )
      goto LABEL_76;
    v32 = v37;
    SystemType = CalculateStreamInfo(
                   (struct _MINIDUMP_STATE *)&v59,
                   v38,
                   (struct _MINIDUMP_STREAM_INFO *)v80,
                   v68 != 0,
                   v24,
                   v37,
                   &v39);
    if ( SystemType )
      goto LABEL_76;
    if ( (v17 & 0x4000806) != 0 )
      v33 = 0;
    else
      v33 = v81;
    v34 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 16LL))(a4, v33);
    SystemType = v34;
    if ( !v34 )
    {
      SystemType = WriteDumpData(
                     (struct _MINIDUMP_STATE *)&v59,
                     (struct _MINIDUMP_STREAM_INFO *)v80,
                     v38,
                     v68,
                     v24,
                     v32,
                     &v39);
      v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 40LL))(a4);
      v36 = SystemType == 0;
      if ( SystemType >= 0 )
      {
        if ( v35 < 0 )
        {
          SystemType = v35;
          goto LABEL_76;
        }
        v36 = SystemType == 0;
      }
      if ( v36 )
        WriteKernelMinidump((struct _MINIDUMP_STATE *)&v59, v38);
      goto LABEL_76;
    }
    (*(void (**)(__int64, __int64, const char *, ...))(*(_QWORD *)a6 + 8LL))(a6, 4, "Write.Start failed, 0x%08x", v34);
LABEL_76:
    if ( v68 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 24LL))(v63);
    if ( v38 )
      GenFreeProcessObject((struct _MINIDUMP_STATE *)&v59, v38, &v39);
    goto LABEL_80;
  }
  (*(void (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)a6 + 8LL))(
    a6,
    4,
    "Dump type requires streaming but output provider does not support streaming");
  SystemType = -2147024809;
LABEL_80:
  UplevelCalls::CleanupStackWalk((UplevelCalls *)&ProcAddress);
  return (unsigned int)SystemType;
}

```

## disassembly

```asm
0x18000f8e8  push    rbp
0x18000f8ea  push    rbx
0x18000f8eb  push    rsi
0x18000f8ec  push    rdi
0x18000f8ed  push    r12
0x18000f8ef  push    r13
0x18000f8f1  push    r14
0x18000f8f3  push    r15
0x18000f8f5  lea     rbp, [rsp-708h]
0x18000f8fd  sub     rsp, 808h
0x18000f904  mov     rax, cs:__security_cookie
0x18000f90b  xor     rax, rsp
0x18000f90e  mov     [rbp+740h+var_50], rax
0x18000f915  mov     rax, [rbp+740h+arg_20]
0x18000f91c  xor     edi, edi
0x18000f91e  mov     r14, [rbp+740h+arg_40]
0x18000f925  mov     r12, r9
0x18000f928  mov     r15, [rbp+740h+arg_48]
0x18000f92f  mov     r13, [rbp+740h+arg_30]
0x18000f936  mov     rsi, [rbp+740h+arg_28]
0x18000f93d  mov     [rbp+740h+var_788], rax
0x18000f941  mov     rax, [rbp+740h+arg_38]
0x18000f948  mov     [rbp+740h+var_7A8], r8
0x18000f94c  mov     r8d, 0F0h; Size
0x18000f952  mov     [rbp+740h+var_7B0], edx
0x18000f955  xor     edx, edx; Val
0x18000f957  mov     [rbp+740h+var_790], rcx
0x18000f95b  lea     rcx, [rbp+740h+var_140]; void *
0x18000f962  mov     [rbp+740h+var_7A0], rax
0x18000f966  mov     [rsp+840h+var_7F8], rdi
0x18000f96b  call    memset_0
0x18000f970  xor     edx, edx; Val
0x18000f972  lea     rcx, [rbp+740h+var_220]; void *
0x18000f979  mov     r8d, 0E0h; Size
0x18000f97f  call    memset_0
0x18000f984  xorps   xmm0, xmm0
0x18000f987  mov     [rsp+840h+var_7E0], rdi
0x18000f98c  xor     r8d, r8d; dwFlags
0x18000f98f  mov     [rsp+840h+var_7D8], rdi
0x18000f994  xor     edx, edx; hFile
0x18000f996  mov     [rsp+840h+var_7D0], rdi
0x18000f99b  lea     rcx, aDbghelpDll; "dbghelp.dll"
0x18000f9a2  mov     [rsp+840h+var_7C8], rdi
0x18000f9a7  movups  xmmword ptr [rsp+840h+var_7F0.Flink], xmm0
0x18000f9ac  mov     [rbp+740h+var_7C0], rdi
0x18000f9b0  mov     [rbp+740h+hModule], rdi
0x18000f9b4  call    cs:__imp_LoadLibraryExW
0x18000f9ba  mov     [rbp+740h+hModule], rax
0x18000f9be  test    rax, rax
0x18000f9c1  jz      loc_18000FA5E
0x18000f9c7  lea     rdx, aStackwalk64; "StackWalk64"
0x18000f9ce  mov     rcx, rax; hModule
0x18000f9d1  call    cs:__imp_GetProcAddress
0x18000f9d7  mov     rcx, [rbp+740h+hModule]; hModule
0x18000f9db  lea     rdx, aSyminitialize; "SymInitialize"
0x18000f9e2  mov     [rsp+840h+var_7E0], rax
0x18000f9e7  call    cs:__imp_GetProcAddress
0x18000f9ed  mov     rcx, [rbp+740h+hModule]; hModule
0x18000f9f1  lea     rdx, aSymcleanup; "SymCleanup"
0x18000f9f8  mov     [rsp+840h+var_7D8], rax
0x18000f9fd  call    cs:__imp_GetProcAddress
0x18000fa03  mov     rcx, [rbp+740h+hModule]; hModule
0x18000fa07  lea     rdx, aSymregisterfun; "SymRegisterFunctionEntryCallback64"
0x18000fa0e  mov     [rsp+840h+var_7D0], rax
0x18000fa13  call    cs:__imp_GetProcAddress
0x18000fa19  mov     rcx, [rbp+740h+hModule]; hModule
0x18000fa1d  lea     rdx, aSymfunctiontab; "SymFunctionTableAccess64AccessRoutines"
0x18000fa24  mov     [rsp+840h+var_7C8], rax
0x18000fa29  call    cs:__imp_GetProcAddress
0x18000fa2f  mov     [rbp+740h+var_7C0], rax
0x18000fa33  cmp     [rsp+840h+var_7E0], rdi
0x18000fa38  jz      short loc_18000FA54
0x18000fa3a  cmp     [rsp+840h+var_7D8], rdi
0x18000fa3f  jz      short loc_18000FA54
0x18000fa41  cmp     [rsp+840h+var_7D0], rdi
0x18000fa46  jz      short loc_18000FA54
0x18000fa48  cmp     [rsp+840h+var_7C8], rdi
0x18000fa4d  jz      short loc_18000FA54
0x18000fa4f  test    rax, rax
0x18000fa52  jnz     short loc_18000FA5E
0x18000fa54  lea     rcx, [rsp+840h+var_7E0]; this
0x18000fa59  call    ?CleanupStackWalk@UplevelCalls@@AEAAXXZ; UplevelCalls::CleanupStackWalk(void)
0x18000fa5e  test    dword ptr [r13+0], 0F8000000h
0x18000fa66  jz      short loc_18000FA9B
0x18000fa68  lea     r8, aInvalidDumpTyp; "Invalid dump type 0x%x"
0x18000fa6f  mov     rax, [rsi]
0x18000fa72  mov     edx, 4
0x18000fa77  mov     r9d, [r13+0]
0x18000fa7b  mov     rcx, rsi
0x18000fa7e  mov     rax, [rax+8]
0x18000fa82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa87  lea     rcx, [rsp+840h+var_7E0]; this
0x18000fa8c  call    ?CleanupStackWalk@UplevelCalls@@AEAAXXZ; UplevelCalls::CleanupStackWalk(void)
0x18000fa91  mov     eax, 80070057h
0x18000fa96  jmp     loc_180010035
0x18000fa9b  mov     eax, [r13+0]
0x18000fa9f  mov     ecx, 300000h
0x18000faa4  and     eax, ecx
0x18000faa6  cmp     eax, ecx
0x18000faa8  jnz     short loc_18000FAB3
0x18000faaa  lea     r8, aAvxXstateInfoI; "AVX XState info is not allowed in Triag"...
0x18000fab1  jmp     short loc_18000FA6F
0x18000fab3  mov     eax, [r13+0]
0x18000fab7  mov     ecx, 2020000h
0x18000fabc  and     eax, ecx
0x18000fabe  cmp     eax, ecx
0x18000fac0  jz      short loc_18000FA87
0x18000fac2  mov     eax, [r13+0]
0x18000fac6  mov     ecx, 4000002h
0x18000facb  mov     ebx, [r13+0]
0x18000facf  and     eax, 2000002h
0x18000fad4  bts     ebx, 11h
0x18000fad8  mov     edx, 2
0x18000fadd  cmp     eax, edx
0x18000fadf  cmovnz  ebx, [r13+0]
0x18000fae4  mov     eax, ebx
0x18000fae6  and     eax, ecx
0x18000fae8  cmp     eax, ecx
0x18000faea  jnz     short loc_18000FB05
0x18000faec  mov     rax, [rsi]
0x18000faef  lea     r8, aMinidumpwithme; "MiniDumpWithMemoryCompressed and MiniDu"...
0x18000faf6  and     ebx, 0FFFFFFFDh
0x18000faf9  mov     rcx, rsi
0x18000fafc  mov     rax, [rax+8]
0x18000fb00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb05  mov     ecx, ebx
0x18000fb07  and     ecx, 0FBFE7DBDh
0x18000fb0d  bt      ebx, 0Ah
0x18000fb11  cmovnb  ecx, ebx
0x18000fb14  xor     edx, edx
0x18000fb16  mov     edi, ecx
0x18000fb18  and     edi, 0FFE65CA6h
0x18000fb1e  test    ecx, 4000002h
0x18000fb24  cmovz   edi, ecx
0x18000fb27  bt      edi, 14h
0x18000fb2b  jnb     short loc_18000FB35
0x18000fb2d  btr     edi, 12h
0x18000fb31  bts     edi, 7
0x18000fb35  test    edi, 4000806h
0x18000fb3b  jz      short loc_18000FB78
0x18000fb3d  mov     rax, [r12]
0x18000fb41  mov     rcx, r12
0x18000fb44  mov     rax, [rax+8]
0x18000fb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb4d  xor     edx, edx
0x18000fb4f  test    eax, eax
0x18000fb51  jz      short loc_18000FB78
0x18000fb53  mov     rax, [rsi]
0x18000fb56  lea     r8, aDumpTypeRequir; "Dump type requires streaming but output"...
0x18000fb5d  mov     edx, 4
0x18000fb62  mov     rcx, rsi
0x18000fb65  mov     rax, [rax+8]
0x18000fb69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb6e  mov     ebx, 80070057h
0x18000fb73  jmp     loc_180010029
0x18000fb78  bt      edi, 14h
0x18000fb7c  mov     rbx, [rbp+740h+var_7A8]
0x18000fb80  jb      short loc_18000FBE1
0x18000fb82  mov     r8, [r13+8]
0x18000fb86  test    r8, r8
0x18000fb89  jz      short loc_18000FBE1
0x18000fb8b  mov     rax, [rbx]
0x18000fb8e  lea     rcx, [rsp+840h+var_800]
0x18000fb93  mov     qword ptr [rsp+840h+var_818], rcx
0x18000fb98  lea     r9, [rbp+740h+var_798]
0x18000fb9c  mov     [rbp+740h+var_798], rdx
0x18000fba0  add     r8, 330h
0x18000fba7  mov     [rsp+840h+var_800], edx
0x18000fbab  mov     rcx, rbx
0x18000fbae  mov     rax, [rax+0E8h]
0x18000fbb5  mov     rdx, [rbp+740h+var_790]
0x18000fbb9  mov     dword ptr [rsp+840h+var_820], 8
0x18000fbc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbc6  xor     edx, edx
0x18000fbc8  test    eax, eax
0x18000fbca  jnz     short loc_18000FBE1
0x18000fbcc  cmp     [rsp+840h+var_800], 8
0x18000fbd1  jnz     short loc_18000FBE1
0x18000fbd3  test    [rbp+740h+var_798], 800h
0x18000fbdb  jz      short loc_18000FBE1
0x18000fbdd  bts     edi, 15h
0x18000fbe1  mov     r8d, 1
0x18000fbe7  mov     [rsp+840h+var_7F8], rdx
0x18000fbec  lea     rax, [rsp+840h+var_7F0]
0x18000fbf1  mov     [rbp+740h+var_210], rbx
0x18000fbf8  mov     [rsp+840h+var_7F0.Blink], rax
0x18000fbfd  lea     rax, [rsp+840h+var_7F0]
0x18000fc02  mov     [rsp+840h+var_7F0.Flink], rax
0x18000fc07  mov     rax, [rbp+740h+var_790]
0x18000fc0b  mov     [rbp+740h+var_220], rax
0x18000fc12  mov     eax, [rbp+740h+var_7B0]
0x18000fc15  mov     [rbp+740h+var_218], eax
0x18000fc1b  mov     rax, [rbp+740h+var_788]
0x18000fc1f  mov     [rbp+740h+var_200], rax
0x18000fc26  lea     rax, [rsp+840h+var_7E0]
0x18000fc2b  mov     [rbp+740h+var_1F0], rax
0x18000fc32  mov     rax, [r13+8]
0x18000fc36  mov     [rbp+740h+var_150], rax
0x18000fc3d  mov     eax, edi
0x18000fc3f  and     eax, 10200h
0x18000fc44  mov     [rbp+740h+var_208], r12
0x18000fc4b  neg     eax
0x18000fc4d  mov     [rbp+740h+var_1F8], rsi
0x18000fc54  mov     eax, r8d
0x18000fc57  mov     [rbp+740h+var_1E8], edi
0x18000fc5d  sbb     ecx, ecx
0x18000fc5f  mov     [rbp+740h+var_1D8], rdx
0x18000fc66  and     ecx, 5
0x18000fc69  mov     [rbp+740h+var_170], 0
0x18000fc74  add     ecx, 0Bh
0x18000fc77  mov     [rbp+740h+var_160], r8d
0x18000fc7e  shl     eax, cl
0x18000fc80  sub     eax, r8d
0x18000fc83  mov     [rbp+740h+var_158], edi
0x18000fc89  mov     [rbp+740h+var_148], edx
0x18000fc8f  mov     [rbp+740h+var_1C8], edx
0x18000fc95  mov     [rbp+740h+var_168], ecx
0x18000fc9b  mov     [rbp+740h+var_164], eax
0x18000fca1  test    r15, r15
0x18000fca4  jz      short loc_18000FCBD
0x18000fca6  mov     rax, [r15]
0x18000fca9  mov     [rbp+740h+var_1E0], rax
0x18000fcb0  mov     rax, [r15+8]
0x18000fcb4  mov     [rbp+740h+var_1D0], rax
0x18000fcbb  jmp     short loc_18000FCD3
0x18000fcbd  mov     [rbp+740h+var_1E0], 0
0x18000fcc8  mov     [rbp+740h+var_1D0], 0
0x18000fcd3  lea     rcx, [rbp+740h+var_220]; struct _MINIDUMP_STATE *
0x18000fcda  call    ?GetSystemType@@YAJPEAU_MINIDUMP_STATE@@@Z; GetSystemType(_MINIDUMP_STATE *)
0x18000fcdf  mov     ebx, eax
0x18000fce1  test    eax, eax
0x18000fce3  jnz     loc_180010029
0x18000fce9  mov     eax, [rbp+740h+var_194]
0x18000fcef  lea     rcx, [rbp+740h+var_72C]; void *
0x18000fcf3  xor     edx, edx; Val
0x18000fcf5  mov     [rbp+740h+var_148], eax
0x18000fcfb  mov     r8d, 50Ch; Size
0x18000fd01  call    memset_0
0x18000fd06  mov     rax, [rbp+740h+var_220]
0x18000fd0d  xorps   xmm0, xmm0
0x18000fd10  mov     [rbp+740h+var_73C], rax
0x18000fd14  xor     ecx, ecx
0x18000fd16  mov     eax, [rbp+740h+var_218]
0x18000fd1c  mov     [rbp+740h+var_740], eax
0x18000fd1f  mov     eax, [rbp+740h+var_1C8]
0x18000fd25  movups  [rbp+740h+var_780], xmm0
0x18000fd29  mov     [rbp+740h+var_730], eax
0x18000fd2c  mov     dword ptr [rbp+740h+var_780], eax
0x18000fd2f  mov     rax, [rbp+740h+var_1E0]
0x18000fd36  mov     [rbp+740h+var_734], 0Fh
0x18000fd3d  mov     [rbp+740h+var_750], ecx
0x18000fd40  movups  [rbp+740h+var_770], xmm0
0x18000fd44  movups  [rbp+740h+var_760], xmm0
0x18000fd48  test    rax, rax
0x18000fd4b  jz      short loc_18000FD73
0x18000fd4d  mov     rcx, [rbp+740h+var_1D0]
0x18000fd54  lea     r8, [rbp+740h+var_780]
0x18000fd58  lea     rdx, [rbp+740h+var_740]
0x18000fd5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd61  mov     ecx, [rbp+740h+var_1C8]
0x18000fd67  test    eax, eax
0x18000fd69  cmovnz  ecx, dword ptr [rbp+740h+var_780]
0x18000fd6d  mov     [rbp+740h+var_1C8], ecx
0x18000fd73  mov     rdx, [rbp+740h+var_7A0]; struct _MINIDUMP_EXCEPTION_INFORMATION64 *
0x18000fd77  lea     r8, [rbp+740h+var_1D8]; struct _EXCEPTION_INFO **
0x18000fd7e  lea     rcx, [rbp+740h+var_220]; struct _MINIDUMP_STATE *
0x18000fd85  call    ?GetExceptionInfo@@YAJPEAU_MINIDUMP_STATE@@PEBU_MINIDUMP_EXCEPTION_INFORMATION64@@PEAPEAU_EXCEPTION_INFO@@@Z; GetExceptionInfo(_MINIDUMP_STATE *,_MINIDUMP_EXCEPTION_INFORMATION64 const *,_EXCEPTION_INFO * *)
0x18000fd8a  mov     ebx, eax
0x18000fd8c  test    eax, eax
0x18000fd8e  jnz     loc_18000FFEF
0x18000fd94  test    r14, r14
0x18000fd97  jz      short loc_18000FDA7
0x18000fd99  mov     r13, [r14+4]
0x18000fd9d  mov     r14d, [r14]
0x18000fda0  mov     [rsp+840h+var_800], r14d
0x18000fda5  jmp     short loc_18000FDAF
0x18000fda7  xor     r13d, r13d
0x18000fdaa  mov     [rsp+840h+var_800], r13d
0x18000fdaf  lea     r9, [rsp+840h+var_7F0]; struct _LIST_ENTRY *
0x18000fdb4  mov     ecx, edi; unsigned int
0x18000fdb6  lea     r8, [rsp+840h+var_7F8]; struct _INTERNAL_PROCESS **
0x18000fdbb  lea     rdx, [rbp+740h+var_220]; struct _MINIDUMP_STATE *
0x18000fdc2  call    ?GenGetProcessInfo@@YAJKPEAU_MINIDUMP_STATE@@PEAPEAU_INTERNAL_PROCESS@@PEAU_LIST_ENTRY@@@Z; GenGetProcessInfo(ulong,_MINIDUMP_STATE *,_INTERNAL_PROCESS * *,_LIST_ENTRY *)
0x18000fdc7  mov     ebx, eax
0x18000fdc9  test    eax, eax
0x18000fdcb  jnz     loc_18000FFEF
0x18000fdd1  mov     rcx, [rbp+740h+var_1D8]
0x18000fdd8  test    rcx, rcx
0x18000fddb  jz      short loc_18000FE57
0x18000fddd  mov     r9, [rcx+0A0h]; void *
0x18000fde4  test    r9, r9
0x18000fde7  jz      short loc_18000FE13
0x18000fde9  mov     eax, [rcx+0A8h]
0x18000fdef  xor     r8d, r8d; struct _INTERNAL_THREAD *
0x18000fdf2  mov     rdx, [rsp+840h+var_7F8]; struct _INTERNAL_PROCESS *
0x18000fdf7  lea     rcx, [rbp+740h+var_220]; struct _MINIDUMP_STATE *
0x18000fdfe  mov     byte ptr [rsp+840h+var_818], 1; unsigned __int8
0x18000fe03  mov     dword ptr [rsp+840h+var_820], eax; unsigned int
0x18000fe07  call    ?GenFilterContext@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@PEAXKE@Z; GenFilterContext(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,void *,ulong,uchar)
0x18000fe0c  mov     rcx, [rbp+740h+var_1D8]
  ... truncated ...
```
