# PpfTransformStore::OpenTransformsKey(ulong,bool,HKEY__ * *,void * *)

- ea: `0x1800395d4`
- end: `0x1800398ac`
- name: `?OpenTransformsKey@PpfTransformStore@@AEAAJK_NPEAPEAUHKEY__@@PEAPEAX@Z`
- size: `728`
- prototype: `__int64 __fastcall(PpfTransformStore *this, REGSAM, char, HKEY *, void **hObject)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18003796c`
- `0x180039354`
- `0x1800398b4`
- `0x18003b418`

## callees

- `0x180009c64`
- `0x18000b5c8`
- `0x18000dfe0`
- `0x1800181fc`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x180039210`
- `0x1800395d4`

## import_xrefs

- `ntdll!NtCreateRegistryTransaction` at `0x1800396d7`
- `ntdll!NtCreateRegistryTransaction` at `0x1800396d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800397cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039868`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800397cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039868`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800397e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003987c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800397e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003987c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039750`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039731`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039713`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039713`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039742`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039856`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039742`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039856`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039823`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039823`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180039788`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180039788`

## string_xrefs

- `0x18003969f`: `PpfTransformStore::OpenTransformsKey`
- `0x180039698`: `Opening transforms key: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall PpfTransformStore::OpenTransformsKey(
        PpfTransformStore *this,
        REGSAM a2,
        char a3,
        HKEY *a4,
        void **hObject)
{
  void **v8; // r14
  int v9; // eax
  unsigned int v10; // ebx
  void **v11; // rcx
  int TransformsKeyPath; // eax
  int v13; // edi
  void **v14; // rbx
  int v15; // eax
  int v16; // eax
  void **hTransaction; // r15
  HKEY v18; // rsi
  DWORD LastError; // edi
  unsigned int v20; // eax
  HKEY v21; // rax
  HANDLE v22; // rax
  unsigned int v24; // eax
  HANDLE ProcessHeap; // rax
  int phkResult; // [rsp+20h] [rbp-38h]
  int phkResulta; // [rsp+20h] [rbp-38h]
  unsigned int phkResultb; // [rsp+20h] [rbp-38h]
  unsigned int phkResultc; // [rsp+20h] [rbp-38h]
  HKEY v30[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  HKEY hKey; // [rsp+A0h] [rbp+48h] BYREF

  hKey = (HKEY)this;
  v8 = hObject;
  if ( a3 != (hObject != 0) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)a4);
  v30[0] = 0;
  v9 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)v30);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)(unsigned int)v9,
      phkResult);
LABEL_28:
    PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)v30);
    return v10;
  }
  hObject = 0;
  v11 = &qword_180072C30;
  if ( (unsigned __int64)qword_180072C48 > 7 )
    v11 = (void **)qword_180072C30;
  TransformsKeyPath = GetTransformsKeyPath(v11, &hObject);
  v13 = TransformsKeyPath;
  if ( TransformsKeyPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)(unsigned int)TransformsKeyPath,
      phkResult);
    v14 = hObject;
LABEL_25:
    if ( v14 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
    }
    v10 = v13;
    goto LABEL_28;
  }
  v14 = hObject;
  phkResulta = (int)hObject;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
    0x2Fu,
    "PpfTransformStore::OpenTransformsKey",
    "Opening transforms key: %ws");
  hKey = 0;
  if ( a3 )
  {
    hObject = 0;
    v15 = NtCreateRegistryTransaction(&hObject, 2031679, 0, 0);
    if ( v15 < 0 )
    {
      v16 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x35,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
              (const char *)(unsigned int)v15,
              phkResulta);
      goto LABEL_11;
    }
    hTransaction = hObject;
    v18 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v18);
      SetLastError(LastError);
    }
    hKey = 0;
    v20 = RegOpenKeyTransactedW(v30[0], (LPCWSTR)v14, 0, a2, &hKey, hTransaction, 0);
    if ( v20 )
    {
      v16 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x38,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
              (const char *)v20,
              phkResultb);
LABEL_11:
      v13 = v16;
      if ( (unsigned __int64)hObject - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject);
      goto LABEL_23;
    }
    *v8 = hObject;
  }
  else
  {
    v24 = RegOpenKeyExW(v30[0], (LPCWSTR)v14, 0, a2, &hKey);
    if ( v24 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x3E,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
              (const char *)v24,
              phkResultc);
LABEL_23:
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_25;
    }
  }
  v21 = hKey;
  hKey = 0;
  *a4 = v21;
  if ( v14 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v14);
  }
  PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)v30);
  return 0;
}

```

## disassembly

```asm
0x1800395d4  mov     [rsp-40h+hKey], rcx
0x1800395d9  push    rbp
0x1800395da  push    rbx
0x1800395db  push    rsi
0x1800395dc  push    rdi
0x1800395dd  push    r12
0x1800395df  push    r13
0x1800395e1  push    r14
0x1800395e3  push    r15
0x1800395e5  mov     rbp, rsp
0x1800395e8  sub     rsp, 58h
0x1800395ec  mov     r13, r9
0x1800395ef  movzx   esi, r8b
0x1800395f3  mov     r12d, edx
0x1800395f6  mov     rcx, [rbp+40h]; this
0x1800395fa  xor     r15d, r15d
0x1800395fd  mov     r10d, r15d
0x180039600  mov     r14, [rbp+hObject]
0x180039604  test    r14, r14
0x180039607  setnz   r10b
0x18003960b  cmp     esi, r10d
0x18003960e  jnz     loc_18003989A
0x180039614  mov     [rbp+var_18], r15
0x180039618  lea     rcx, [rbp+var_18]; this
0x18003961c  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x180039621  mov     ebx, eax
0x180039623  test    eax, eax
0x180039625  jns     short loc_180039643
0x180039627  mov     rcx, [rbp+40h]; this
0x18003962b  mov     r9d, eax; char *
0x18003962e  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180039635  lea     edx, [r15+2Bh]; void *
0x180039639  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003963e  jmp     loc_18003988A
0x180039643  mov     [rbp+hObject], r15
0x180039647  lea     rcx, qword_180072C30
0x18003964e  cmp     cs:qword_180072C48, 7
0x180039656  cmova   rcx, cs:qword_180072C30
0x18003965e  lea     rdx, [rbp+hObject]
0x180039662  call    GetTransformsKeyPath
0x180039667  mov     edi, eax
0x180039669  test    eax, eax
0x18003966b  jns     short loc_18003968F
0x18003966d  mov     rcx, [rbp+40h]; this
0x180039671  mov     r9d, eax; char *
0x180039674  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003967b  mov     edx, 2Eh ; '.'; void *
0x180039680  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039685  nop
0x180039686  mov     rbx, [rbp+hObject]
0x18003968a  jmp     loc_180039863
0x18003968f  mov     rbx, [rbp+hObject]
0x180039693  mov     [rsp+58h+phkResult], rbx; int
0x180039698  lea     r9, aOpeningTransfo; "Opening transforms key: %ws"
0x18003969f  lea     r8, aPpftransformst_1; "PpfTransformStore::OpenTransformsKey"
0x1800396a6  mov     edx, 2Fh ; '/'; unsigned int
0x1800396ab  lea     rcx, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800396b2  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800396b7  mov     [rbp+hKey], r15
0x1800396bb  test    sil, sil
0x1800396be  jz      loc_18003980D
0x1800396c4  mov     [rbp+hObject], r15
0x1800396c8  xor     r9d, r9d
0x1800396cb  xor     r8d, r8d
0x1800396ce  mov     edx, 1F003Fh
0x1800396d3  lea     rcx, [rbp+hObject]
0x1800396d7  call    cs:__imp_NtCreateRegistryTransaction
0x1800396de  nop     dword ptr [rax+rax+00h]
0x1800396e3  test    eax, eax
0x1800396e5  jns     short loc_180039724
0x1800396e7  mov     rcx, [rbp+40h]; this
0x1800396eb  mov     r9d, eax; char *
0x1800396ee  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800396f5  mov     edx, 35h ; '5'; void *
0x1800396fa  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800396ff  mov     edi, eax
0x180039701  mov     rcx, [rbp+hObject]; hObject
0x180039705  lea     rdx, [rcx-1]
0x180039709  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003970d  ja      loc_18003984D
0x180039713  call    cs:__imp_CloseHandle
0x18003971a  nop     dword ptr [rax+rax+00h]
0x18003971f  jmp     loc_18003984D
0x180039724  mov     r15, [rbp+hObject]
0x180039728  mov     rsi, [rbp+hKey]
0x18003972c  test    rsi, rsi
0x18003972f  jz      short loc_18003975C
0x180039731  call    cs:__imp_GetLastError
0x180039738  nop     dword ptr [rax+rax+00h]
0x18003973d  mov     edi, eax
0x18003973f  mov     rcx, rsi; hKey
0x180039742  call    cs:__imp_RegCloseKey
0x180039749  nop     dword ptr [rax+rax+00h]
0x18003974e  mov     ecx, edi; dwErrCode
0x180039750  call    cs:__imp_SetLastError
0x180039757  nop     dword ptr [rax+rax+00h]
0x18003975c  mov     [rbp+hKey], 0
0x180039764  mov     [rsp+58h+pExtendedParemeter], 0; pExtendedParemeter
0x18003976d  mov     [rsp+58h+hTransaction], r15; hTransaction
0x180039772  lea     rax, [rbp+hKey]
0x180039776  mov     [rsp+58h+phkResult], rax; unsigned int
0x18003977b  mov     r9d, r12d; samDesired
0x18003977e  xor     r8d, r8d; ulOptions
0x180039781  mov     rdx, rbx; lpSubKey
0x180039784  mov     rcx, [rbp+var_18]; hKey
0x180039788  call    cs:__imp_RegOpenKeyTransactedW
0x18003978f  nop     dword ptr [rax+rax+00h]
0x180039794  xor     r15d, r15d
0x180039797  test    eax, eax
0x180039799  jz      short loc_1800397B7
0x18003979b  mov     rcx, [rbp+40h]; this
0x18003979f  mov     r9d, eax; char *
0x1800397a2  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800397a9  lea     edx, [r15+38h]; void *
0x1800397ad  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800397b2  jmp     loc_1800396FF
0x1800397b7  mov     rax, [rbp+hObject]
0x1800397bb  mov     [r14], rax
0x1800397be  mov     rax, [rbp+hKey]
0x1800397c2  mov     [rbp+hKey], r15
0x1800397c6  mov     [r13+0], rax
0x1800397ca  test    rbx, rbx
0x1800397cd  jz      short loc_1800397F0
0x1800397cf  call    cs:__imp_GetProcessHeap
0x1800397d6  nop     dword ptr [rax+rax+00h]
0x1800397db  mov     rcx, rax; hHeap
0x1800397de  mov     r8, rbx; lpMem
0x1800397e1  xor     edx, edx; dwFlags
0x1800397e3  call    cs:__imp_HeapFree
0x1800397ea  nop     dword ptr [rax+rax+00h]
0x1800397ef  nop
0x1800397f0  lea     rcx, [rbp+var_18]; this
0x1800397f4  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x1800397f9  xor     eax, eax
0x1800397fb  add     rsp, 58h
0x1800397ff  pop     r15
0x180039801  pop     r14
0x180039803  pop     r13
0x180039805  pop     r12
0x180039807  pop     rdi
0x180039808  pop     rsi
0x180039809  pop     rbx
0x18003980a  pop     rbp
0x18003980b  retn
0x18003980d  lea     rax, [rbp+hKey]
0x180039811  mov     [rsp+58h+phkResult], rax; unsigned int
0x180039816  mov     r9d, r12d; samDesired
0x180039819  xor     r8d, r8d; ulOptions
0x18003981c  mov     rdx, rbx; lpSubKey
0x18003981f  mov     rcx, [rbp+var_18]; hKey
0x180039823  call    cs:__imp_RegOpenKeyExW
0x18003982a  nop     dword ptr [rax+rax+00h]
0x18003982f  test    eax, eax
0x180039831  jz      short loc_1800397BE
0x180039833  mov     rcx, [rbp+40h]; this
0x180039837  mov     r9d, eax; char *
0x18003983a  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180039841  mov     edx, 3Eh ; '>'; void *
0x180039846  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003984b  mov     edi, eax
0x18003984d  mov     rcx, [rbp+hKey]; hKey
0x180039851  test    rcx, rcx
0x180039854  jz      short loc_180039863
0x180039856  call    cs:__imp_RegCloseKey
0x18003985d  nop     dword ptr [rax+rax+00h]
0x180039862  nop
0x180039863  test    rbx, rbx
0x180039866  jz      short loc_180039888
0x180039868  call    cs:__imp_GetProcessHeap
0x18003986f  nop     dword ptr [rax+rax+00h]
0x180039874  mov     r8, rbx; lpMem
0x180039877  xor     edx, edx; dwFlags
0x180039879  mov     rcx, rax; hHeap
0x18003987c  call    cs:__imp_HeapFree
0x180039883  nop     dword ptr [rax+rax+00h]
0x180039888  mov     ebx, edi
0x18003988a  lea     rcx, [rbp+var_18]; this
0x18003988e  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180039893  mov     eax, ebx
0x180039895  jmp     loc_1800397FB
0x18003989a  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800398a1  mov     edx, 28h ; '('; void *
0x1800398a6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
