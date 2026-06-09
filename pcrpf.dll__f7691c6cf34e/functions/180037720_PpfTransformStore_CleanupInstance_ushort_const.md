# PpfTransformStore::CleanupInstance(ushort const *)

- ea: `0x180037720`
- end: `0x180037964`
- name: `?CleanupInstance@PpfTransformStore@@SAJPEBG@Z`
- size: `580`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b140`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x1800181fc`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x180037720`
- `0x180039210`

## import_xrefs

- `ntdll!NtCreateRegistryTransaction` at `0x1800377bc`
- `ntdll!NtCreateRegistryTransaction` at `0x1800377bc`
- `ntdll!NtCommitRegistryTransaction` at `0x1800378e6`
- `ntdll!NtCommitRegistryTransaction` at `0x1800378e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037838`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800378b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037911`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037838`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800378b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037911`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003784c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800378c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037925`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003784c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800378c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037925`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800377f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003793f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800377f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003793f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180037884`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180037884`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall PpfTransformStore::CleanupInstance(unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  int v4; // eax
  int TransformsKeyPath; // eax
  unsigned int v6; // edi
  void *v7; // rbx
  HANDLE v8; // rax
  HANDLE v9; // rcx
  bool v10; // cc
  void *v11; // rbx
  unsigned int v12; // eax
  int v13; // eax
  HANDLE v14; // rax
  int v15; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v18; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  HANDLE hObject; // [rsp+60h] [rbp+30h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  v18 = (unsigned int)a1;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
    0x26Au,
    "PpfTransformStore::CleanupInstance",
    "Cleaning up instance: '%ws'");
  if ( *a1 )
  {
    hKey = 0;
    v3 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)&hKey);
    v2 = v3;
    if ( v3 >= 0 )
    {
      hObject = 0;
      v4 = NtCreateRegistryTransaction(&hObject, 2031679, 0, 0);
      if ( v4 >= 0 )
      {
        lpMem = 0;
        TransformsKeyPath = GetTransformsKeyPath(a1, (__int64 *)&lpMem);
        v6 = TransformsKeyPath;
        if ( TransformsKeyPath >= 0 )
        {
          v11 = lpMem;
          v12 = RegDeleteTreeW(hKey, (LPCWSTR)lpMem);
          if ( (v12 & 0xFFFFFFFD) != 0 )
          {
            v13 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x278,
                    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
                    (const char *)v12,
                    v18);
          }
          else
          {
            v15 = NtCommitRegistryTransaction(hObject, 0);
            if ( v15 >= 0 )
            {
              if ( v11 )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v11);
              }
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(hObject);
              v2 = 0;
              goto LABEL_27;
            }
            v13 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x27B,
                    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
                    (const char *)(unsigned int)v15,
                    v18);
          }
          v6 = v13;
          if ( v11 )
          {
            v14 = GetProcessHeap();
            HeapFree(v14, 0, v11);
          }
          v9 = hObject;
          v10 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x274,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
            (const char *)(unsigned int)TransformsKeyPath,
            v18);
          v7 = lpMem;
          if ( lpMem )
          {
            v8 = GetProcessHeap();
            HeapFree(v8, 0, v7);
          }
          v9 = hObject;
          v10 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
        }
        if ( v10 )
          CloseHandle(v9);
        v2 = v6;
      }
      else
      {
        v2 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x271,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
               (const char *)(unsigned int)v4,
               v18);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26E,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
        (const char *)(unsigned int)v3,
        v18);
    }
LABEL_27:
    PpfSystemCcsKey::~PpfSystemCcsKey(&hKey);
    return v2;
  }
  v2 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x26B,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
    (const char *)0x80070057LL,
    v18);
  return v2;
}

```

## disassembly

```asm
0x180037720  push    rbp
0x180037722  push    rbx
0x180037723  push    rsi
0x180037724  push    rdi
0x180037725  push    r14
0x180037727  mov     rbp, rsp
0x18003772a  sub     rsp, 30h
0x18003772e  mov     rdi, rcx
0x180037731  mov     qword ptr [rsp+30h+var_10], rcx; int
0x180037736  lea     r9, aCleaningUpInst; "Cleaning up instance: '%ws'"
0x18003773d  lea     r8, aPpftransformst_2; "PpfTransformStore::CleanupInstance"
0x180037744  mov     edx, 26Ah; unsigned int
0x180037749  lea     r14, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037750  mov     rcx, r14; char *
0x180037753  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180037758  xor     esi, esi
0x18003775a  cmp     [rdi], si
0x18003775d  jnz     short loc_18003777D
0x18003775f  mov     rcx, [rbp+28h]; this
0x180037763  mov     ebx, 80070057h
0x180037768  mov     r9d, ebx; char *
0x18003776b  mov     r8, r14; unsigned int
0x18003776e  mov     edx, 26Bh; void *
0x180037773  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037778  jmp     loc_180037956
0x18003777d  mov     [rbp+hKey], rsi
0x180037781  lea     rcx, [rbp+hKey]; this
0x180037785  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x18003778a  mov     ebx, eax
0x18003778c  test    eax, eax
0x18003778e  jns     short loc_1800377A9
0x180037790  mov     rcx, [rbp+28h]; this
0x180037794  mov     r9d, eax; char *
0x180037797  mov     r8, r14; unsigned int
0x18003779a  mov     edx, 26Eh; void *
0x18003779f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800377a4  jmp     loc_18003794D
0x1800377a9  mov     [rbp+hObject], rsi
0x1800377ad  xor     r9d, r9d
0x1800377b0  xor     r8d, r8d
0x1800377b3  mov     edx, 1F003Fh
0x1800377b8  lea     rcx, [rbp+hObject]
0x1800377bc  call    cs:__imp_NtCreateRegistryTransaction
0x1800377c3  nop     dword ptr [rax+rax+00h]
0x1800377c8  test    eax, eax
0x1800377ca  jns     short loc_180037805
0x1800377cc  mov     rcx, [rbp+28h]; this
0x1800377d0  mov     r9d, eax; char *
0x1800377d3  mov     r8, r14; unsigned int
0x1800377d6  mov     edx, 271h; void *
0x1800377db  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800377e0  mov     ebx, eax
0x1800377e2  mov     rcx, [rbp+hObject]; hObject
0x1800377e6  lea     rdx, [rcx-1]
0x1800377ea  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800377ee  ja      loc_18003794D
0x1800377f4  call    cs:__imp_CloseHandle
0x1800377fb  nop     dword ptr [rax+rax+00h]
0x180037800  jmp     loc_18003794D
0x180037805  mov     [rbp+lpMem], rsi
0x180037809  lea     rdx, [rbp+lpMem]
0x18003780d  mov     rcx, rdi
0x180037810  call    GetTransformsKeyPath
0x180037815  mov     edi, eax
0x180037817  test    eax, eax
0x180037819  jns     short loc_180037879
0x18003781b  mov     rcx, [rbp+28h]; this
0x18003781f  mov     r9d, eax; char *
0x180037822  mov     r8, r14; unsigned int
0x180037825  mov     edx, 274h; void *
0x18003782a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003782f  mov     rbx, [rbp+lpMem]
0x180037833  test    rbx, rbx
0x180037836  jz      short loc_180037858
0x180037838  call    cs:__imp_GetProcessHeap
0x18003783f  nop     dword ptr [rax+rax+00h]
0x180037844  mov     rcx, rax; hHeap
0x180037847  mov     r8, rbx; lpMem
0x18003784a  xor     edx, edx; dwFlags
0x18003784c  call    cs:__imp_HeapFree
0x180037853  nop     dword ptr [rax+rax+00h]
0x180037858  mov     rcx, [rbp+hObject]; hObject
0x18003785c  lea     rax, [rcx-1]
0x180037860  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037864  ja      short loc_180037872
0x180037866  call    cs:__imp_CloseHandle
0x18003786d  nop     dword ptr [rax+rax+00h]
0x180037872  mov     ebx, edi
0x180037874  jmp     loc_18003794D
0x180037879  mov     rbx, [rbp+lpMem]
0x18003787d  mov     rdx, rbx; lpSubKey
0x180037880  mov     rcx, [rbp+hKey]; hKey
0x180037884  call    cs:__imp_RegDeleteTreeW
0x18003788b  nop     dword ptr [rax+rax+00h]
0x180037890  test    eax, 0FFFFFFFDh
0x180037895  jz      short loc_1800378E0
0x180037897  mov     rcx, [rbp+28h]; this
0x18003789b  mov     r9d, eax; char *
0x18003789e  mov     r8, r14; unsigned int
0x1800378a1  mov     edx, 278h; void *
0x1800378a6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800378ab  mov     edi, eax
0x1800378ad  test    rbx, rbx
0x1800378b0  jz      short loc_1800378D2
0x1800378b2  call    cs:__imp_GetProcessHeap
0x1800378b9  nop     dword ptr [rax+rax+00h]
0x1800378be  mov     rcx, rax; hHeap
0x1800378c1  mov     r8, rbx; lpMem
0x1800378c4  xor     edx, edx; dwFlags
0x1800378c6  call    cs:__imp_HeapFree
0x1800378cd  nop     dword ptr [rax+rax+00h]
0x1800378d2  mov     rcx, [rbp+hObject]
0x1800378d6  lea     rdx, [rcx-1]
0x1800378da  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800378de  jmp     short loc_180037864
0x1800378e0  xor     edx, edx
0x1800378e2  mov     rcx, [rbp+hObject]
0x1800378e6  call    cs:__imp_NtCommitRegistryTransaction
0x1800378ed  nop     dword ptr [rax+rax+00h]
0x1800378f2  test    eax, eax
0x1800378f4  jns     short loc_18003790C
0x1800378f6  mov     rcx, [rbp+28h]; this
0x1800378fa  mov     r9d, eax; char *
0x1800378fd  mov     r8, r14; unsigned int
0x180037900  mov     edx, 27Bh; void *
0x180037905  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18003790a  jmp     short loc_1800378AB
0x18003790c  test    rbx, rbx
0x18003790f  jz      short loc_180037931
0x180037911  call    cs:__imp_GetProcessHeap
0x180037918  nop     dword ptr [rax+rax+00h]
0x18003791d  mov     rcx, rax; hHeap
0x180037920  mov     r8, rbx; lpMem
0x180037923  xor     edx, edx; dwFlags
0x180037925  call    cs:__imp_HeapFree
0x18003792c  nop     dword ptr [rax+rax+00h]
0x180037931  mov     rcx, [rbp+hObject]; hObject
0x180037935  lea     rax, [rcx-1]
0x180037939  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003793d  ja      short loc_18003794B
0x18003793f  call    cs:__imp_CloseHandle
0x180037946  nop     dword ptr [rax+rax+00h]
0x18003794b  mov     ebx, esi
0x18003794d  lea     rcx, [rbp+hKey]; this
0x180037951  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180037956  mov     eax, ebx
0x180037958  add     rsp, 30h
0x18003795c  pop     r14
0x18003795e  pop     rdi
0x18003795f  pop     rsi
0x180037960  pop     rbx
0x180037961  pop     rbp
0x180037962  retn
```
