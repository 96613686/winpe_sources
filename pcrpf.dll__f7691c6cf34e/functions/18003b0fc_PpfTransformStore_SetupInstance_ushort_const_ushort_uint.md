# PpfTransformStore::SetupInstance(ushort const *,ushort,uint)

- ea: `0x18003b0fc`
- end: `0x18003b40f`
- name: `?SetupInstance@PpfTransformStore@@SAJPEBGGI@Z`
- size: `787`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001b930`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x1800181fc`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x180039210`
- `0x18003b0fc`

## import_xrefs

- `ntdll!NtCreateRegistryTransaction` at `0x18003b1aa`
- `ntdll!NtCreateRegistryTransaction` at `0x18003b1aa`
- `ntdll!NtCommitRegistryTransaction` at `0x18003b36c`
- `ntdll!NtCommitRegistryTransaction` at `0x18003b36c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b226`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b3af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b226`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b3af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b23a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b3c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b23a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b3c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b1e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b254`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b3dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b1e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b254`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b3dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b2e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b39e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b2e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b39e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b317`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b34c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b317`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b34c`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18003b2ad`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18003b2ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall PpfTransformStore::SetupInstance(const unsigned __int16 *a1, unsigned __int16 a2, int a3)
{
  int v3; // esi
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  int TransformsKeyPath; // eax
  unsigned int v9; // edi
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  HANDLE v16; // rax
  int dwOptions; // [rsp+20h] [rbp-60h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-60h]
  HKEY phkResult; // [rsp+60h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  int Data; // [rsp+B0h] [rbp+30h] BYREF
  int v25; // [rsp+C0h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+C8h] [rbp+48h] BYREF

  v25 = a3;
  v3 = a2;
  dwOptions = (int)a1;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
    0x227u,
    "PpfTransformStore::SetupInstance",
    "Setting up instance: '%ws'");
  if ( *a1 )
  {
    hKey[0] = 0;
    v6 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)hKey);
    v5 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22B,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
        (const char *)(unsigned int)v6,
        dwOptions);
LABEL_33:
      PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)hKey);
      return v5;
    }
    hObject = 0;
    v7 = NtCreateRegistryTransaction(&hObject, 2031679, 0, 0);
    if ( v7 < 0 )
    {
      v5 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x22E,
             (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
             (const char *)(unsigned int)v7,
             dwOptions);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      goto LABEL_33;
    }
    lpMem = 0;
    TransformsKeyPath = GetTransformsKeyPath(a1, &lpMem);
    v9 = TransformsKeyPath;
    if ( TransformsKeyPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x231,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
        (const char *)(unsigned int)TransformsKeyPath,
        dwOptions);
      v10 = lpMem;
LABEL_10:
      if ( v10 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v10);
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v5 = v9;
      goto LABEL_33;
    }
    phkResult = 0;
    v10 = lpMem;
    v12 = RegCreateKeyTransactedW(hKey[0], (LPCWSTR)lpMem, 0, 0, 1u, 0x20006u, 0, &phkResult, 0, hObject, 0);
    if ( v12 )
    {
      v13 = 564;
    }
    else
    {
      Data = v3;
      v12 = RegSetValueExW(phkResult, L"LogDigestAlgID", 0, 4u, (const BYTE *)&Data, 4u);
      if ( v12 )
      {
        v13 = 568;
      }
      else
      {
        v12 = RegSetValueExW(phkResult, L"LogSupportedDigestAlgIDBitmap", 0, 4u, (const BYTE *)&v25, 4u);
        if ( !v12 )
        {
          v15 = NtCommitRegistryTransaction(hObject, 0);
          if ( v15 >= 0 )
          {
            if ( phkResult )
              RegCloseKey(phkResult);
            if ( v10 )
            {
              v16 = GetProcessHeap();
              HeapFree(v16, 0, v10);
            }
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
            v5 = 0;
            goto LABEL_33;
          }
          v14 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x23D,
                  (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
                  (const char *)(unsigned int)v15,
                  dwOptionsa);
          goto LABEL_18;
        }
        v13 = 571;
      }
    }
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v13,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
            (const char *)v12,
            dwOptionsa);
LABEL_18:
    v9 = v14;
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_10;
  }
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x228,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
    (const char *)0x80070057LL,
    dwOptions);
  return v5;
}

```

## disassembly

```asm
0x18003b0fc  mov     [rsp-28h+arg_8], rbx
0x18003b101  mov     [rsp-28h+arg_10], r8d
0x18003b106  push    rbp
0x18003b107  push    rsi
0x18003b108  push    rdi
0x18003b109  push    r14
0x18003b10b  push    r15
0x18003b10d  mov     rbp, rsp
0x18003b110  sub     rsp, 80h
0x18003b117  movzx   esi, dx
0x18003b11a  mov     rdi, rcx
0x18003b11d  mov     qword ptr [rsp+80h+dwOptions], rcx; int
0x18003b122  lea     r9, aSettingUpInsta; "Setting up instance: '%ws'"
0x18003b129  lea     r8, aPpftransformst_7; "PpfTransformStore::SetupInstance"
0x18003b130  mov     edx, 227h; unsigned int
0x18003b135  lea     r15, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003b13c  mov     rcx, r15; char *
0x18003b13f  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003b144  xor     r14d, r14d
0x18003b147  cmp     [rdi], r14w
0x18003b14b  jnz     short loc_18003B16B
0x18003b14d  mov     rcx, [rbp+28h]; this
0x18003b151  mov     ebx, 80070057h
0x18003b156  mov     r9d, ebx; char *
0x18003b159  mov     r8, r15; unsigned int
0x18003b15c  mov     edx, 228h; void *
0x18003b161  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b166  jmp     loc_18003B3F5
0x18003b16b  mov     [rbp+hKey], r14
0x18003b16f  lea     rcx, [rbp+hKey]; this
0x18003b173  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x18003b178  mov     ebx, eax
0x18003b17a  test    eax, eax
0x18003b17c  jns     short loc_18003B197
0x18003b17e  mov     rcx, [rbp+28h]; this
0x18003b182  mov     r9d, eax; char *
0x18003b185  mov     r8, r15; unsigned int
0x18003b188  mov     edx, 22Bh; void *
0x18003b18d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b192  jmp     loc_18003B3EC
0x18003b197  mov     [rbp+hObject], r14
0x18003b19b  xor     r9d, r9d
0x18003b19e  xor     r8d, r8d
0x18003b1a1  mov     edx, 1F003Fh
0x18003b1a6  lea     rcx, [rbp+hObject]
0x18003b1aa  call    cs:__imp_NtCreateRegistryTransaction
0x18003b1b1  nop     dword ptr [rax+rax+00h]
0x18003b1b6  test    eax, eax
0x18003b1b8  jns     short loc_18003B1F3
0x18003b1ba  mov     rcx, [rbp+28h]; this
0x18003b1be  mov     r9d, eax; char *
0x18003b1c1  mov     r8, r15; unsigned int
0x18003b1c4  mov     edx, 22Eh; void *
0x18003b1c9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18003b1ce  mov     ebx, eax
0x18003b1d0  mov     rcx, [rbp+hObject]; hObject
0x18003b1d4  lea     rdx, [rcx-1]
0x18003b1d8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003b1dc  ja      loc_18003B3EC
0x18003b1e2  call    cs:__imp_CloseHandle
0x18003b1e9  nop     dword ptr [rax+rax+00h]
0x18003b1ee  jmp     loc_18003B3EC
0x18003b1f3  mov     [rbp+lpMem], r14
0x18003b1f7  lea     rdx, [rbp+lpMem]
0x18003b1fb  mov     rcx, rdi
0x18003b1fe  call    GetTransformsKeyPath
0x18003b203  mov     edi, eax
0x18003b205  test    eax, eax
0x18003b207  jns     short loc_18003B267
0x18003b209  mov     rcx, [rbp+28h]; this
0x18003b20d  mov     r9d, eax; char *
0x18003b210  mov     r8, r15; unsigned int
0x18003b213  mov     edx, 231h; void *
0x18003b218  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b21d  mov     rbx, [rbp+lpMem]
0x18003b221  test    rbx, rbx
0x18003b224  jz      short loc_18003B246
0x18003b226  call    cs:__imp_GetProcessHeap
0x18003b22d  nop     dword ptr [rax+rax+00h]
0x18003b232  mov     rcx, rax; hHeap
0x18003b235  mov     r8, rbx; lpMem
0x18003b238  xor     edx, edx; dwFlags
0x18003b23a  call    cs:__imp_HeapFree
0x18003b241  nop     dword ptr [rax+rax+00h]
0x18003b246  mov     rcx, [rbp+hObject]; hObject
0x18003b24a  lea     rax, [rcx-1]
0x18003b24e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b252  ja      short loc_18003B260
0x18003b254  call    cs:__imp_CloseHandle
0x18003b25b  nop     dword ptr [rax+rax+00h]
0x18003b260  mov     ebx, edi
0x18003b262  jmp     loc_18003B3EC
0x18003b267  mov     rax, [rbp+hObject]
0x18003b26b  mov     [rbp+var_20], r14
0x18003b26f  mov     [rsp+80h+pExtendedParemeter], r14; pExtendedParemeter
0x18003b274  mov     [rsp+80h+hTransaction], rax; hTransaction
0x18003b279  mov     [rsp+80h+lpdwDisposition], r14; lpdwDisposition
0x18003b27e  lea     rax, [rbp+var_20]
0x18003b282  mov     [rsp+80h+phkResult], rax; phkResult
0x18003b287  mov     [rsp+80h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003b28c  mov     [rsp+80h+samDesired], 20006h; samDesired
0x18003b294  mov     [rsp+80h+dwOptions], 1; unsigned int
0x18003b29c  xor     r9d, r9d; lpClass
0x18003b29f  xor     r8d, r8d; Reserved
0x18003b2a2  mov     rbx, [rbp+lpMem]
0x18003b2a6  mov     rdx, rbx; lpSubKey
0x18003b2a9  mov     rcx, [rbp+hKey]; hKey
0x18003b2ad  call    cs:__imp_RegCreateKeyTransactedW
0x18003b2b4  nop     dword ptr [rax+rax+00h]
0x18003b2b9  test    eax, eax
0x18003b2bb  jz      short loc_18003B2F1
0x18003b2bd  mov     edx, 234h; void *
0x18003b2c2  mov     r8, r15; unsigned int
0x18003b2c5  mov     r9d, eax; char *
0x18003b2c8  mov     rcx, [rbp+28h]; this
0x18003b2cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003b2d1  mov     rcx, [rbp+var_20]; hKey
0x18003b2d5  test    rcx, rcx
0x18003b2d8  mov     edi, eax
0x18003b2da  jz      loc_18003B221
0x18003b2e0  call    cs:__imp_RegCloseKey
0x18003b2e7  nop     dword ptr [rax+rax+00h]
0x18003b2ec  jmp     loc_18003B221
0x18003b2f1  mov     [rbp+Data], esi
0x18003b2f4  mov     edi, 4
0x18003b2f9  mov     [rsp+80h+samDesired], edi; cbData
0x18003b2fd  lea     rax, [rbp+Data]
0x18003b301  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18003b306  mov     r9d, edi; dwType
0x18003b309  xor     r8d, r8d; Reserved
0x18003b30c  lea     rdx, aLogdigestalgid; "LogDigestAlgID"
0x18003b313  mov     rcx, [rbp+var_20]; hKey
0x18003b317  call    cs:__imp_RegSetValueExW
0x18003b31e  nop     dword ptr [rax+rax+00h]
0x18003b323  test    eax, eax
0x18003b325  jz      short loc_18003B32E
0x18003b327  mov     edx, 238h
0x18003b32c  jmp     short loc_18003B2C2
0x18003b32e  mov     [rsp+80h+samDesired], edi; cbData
0x18003b332  lea     rax, [rbp+arg_10]
0x18003b336  mov     qword ptr [rsp+80h+dwOptions], rax; int
0x18003b33b  mov     r9d, edi; dwType
0x18003b33e  xor     r8d, r8d; Reserved
0x18003b341  lea     rdx, aLogsupporteddi; "LogSupportedDigestAlgIDBitmap"
0x18003b348  mov     rcx, [rbp+var_20]; hKey
0x18003b34c  call    cs:__imp_RegSetValueExW
0x18003b353  nop     dword ptr [rax+rax+00h]
0x18003b358  test    eax, eax
0x18003b35a  jz      short loc_18003B366
0x18003b35c  mov     edx, 23Bh
0x18003b361  jmp     loc_18003B2C2
0x18003b366  xor     edx, edx
0x18003b368  mov     rcx, [rbp+hObject]
0x18003b36c  call    cs:__imp_NtCommitRegistryTransaction
0x18003b373  nop     dword ptr [rax+rax+00h]
0x18003b378  test    eax, eax
0x18003b37a  jns     short loc_18003B395
0x18003b37c  mov     rcx, [rbp+28h]; this
0x18003b380  mov     r9d, eax; char *
0x18003b383  mov     r8, r15; unsigned int
0x18003b386  mov     edx, 23Dh; void *
0x18003b38b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18003b390  jmp     loc_18003B2D1
0x18003b395  mov     rcx, [rbp+var_20]; hKey
0x18003b399  test    rcx, rcx
0x18003b39c  jz      short loc_18003B3AA
0x18003b39e  call    cs:__imp_RegCloseKey
0x18003b3a5  nop     dword ptr [rax+rax+00h]
0x18003b3aa  test    rbx, rbx
0x18003b3ad  jz      short loc_18003B3CF
0x18003b3af  call    cs:__imp_GetProcessHeap
0x18003b3b6  nop     dword ptr [rax+rax+00h]
0x18003b3bb  mov     rcx, rax; hHeap
0x18003b3be  mov     r8, rbx; lpMem
0x18003b3c1  xor     edx, edx; dwFlags
0x18003b3c3  call    cs:__imp_HeapFree
0x18003b3ca  nop     dword ptr [rax+rax+00h]
0x18003b3cf  mov     rcx, [rbp+hObject]; hObject
0x18003b3d3  lea     rax, [rcx-1]
0x18003b3d7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b3db  ja      short loc_18003B3E9
0x18003b3dd  call    cs:__imp_CloseHandle
0x18003b3e4  nop     dword ptr [rax+rax+00h]
0x18003b3e9  mov     ebx, r14d
0x18003b3ec  lea     rcx, [rbp+hKey]; this
0x18003b3f0  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x18003b3f5  mov     eax, ebx
0x18003b3f7  mov     rbx, [rsp+80h+arg_8]
0x18003b3ff  add     rsp, 80h
0x18003b406  pop     r15
0x18003b408  pop     r14
0x18003b40a  pop     rdi
0x18003b40b  pop     rsi
0x18003b40c  pop     rbp
0x18003b40d  retn
```
