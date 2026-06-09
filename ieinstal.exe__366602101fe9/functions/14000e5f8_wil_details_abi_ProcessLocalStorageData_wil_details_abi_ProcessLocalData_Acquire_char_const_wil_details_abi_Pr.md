# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000e5f8`
- end: `0x14000e8bd`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14000efb0`

## callees

- `0x140006070`
- `0x14000e5f8`
- `0x14000e8c4`
- `0x14000ee68`
- `0x14000f768`
- `0x14000fe50`
- `0x140010114`
- `0x1400104bc`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000e73f`
- `KERNEL32!CloseHandle` at `0x14000e7c9`
- `KERNEL32!CloseHandle` at `0x14000e80a`
- `KERNEL32!CloseHandle` at `0x14000e73f`
- `KERNEL32!CloseHandle` at `0x14000e7c9`
- `KERNEL32!CloseHandle` at `0x14000e80a`
- `KERNEL32!GetCurrentProcessId` at `0x14000e633`
- `KERNEL32!GetCurrentProcessId` at `0x14000e633`
- `KERNEL32!CreateMutexExW` at `0x14000e675`
- `KERNEL32!CreateMutexExW` at `0x14000e675`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000e6a1`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000e6a1`
- `KERNEL32!ReleaseMutex` at `0x14000e728`
- `KERNEL32!ReleaseMutex` at `0x14000e7ab`
- `KERNEL32!ReleaseMutex` at `0x14000e7ee`
- `KERNEL32!ReleaseMutex` at `0x14000e728`
- `KERNEL32!ReleaseMutex` at `0x14000e7ab`
- `KERNEL32!ReleaseMutex` at `0x14000e7ee`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned int v14; // r8d
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // ebx
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  hObject = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v37 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v37);
  if ( 4 * v37 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_21;
  }
  v23 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
          Name,
          &hObject,
          a2);
  v25 = v23;
  if ( v23 >= 0 )
  {
    v6 = hObject;
LABEL_21:
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v24, (const char *)(unsigned int)v23, 120);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x14000e5f8  mov     [rsp-8+arg_10], rbx
0x14000e5fd  mov     [rsp-8+arg_18], rsi
0x14000e602  push    rbp
0x14000e603  push    rdi
0x14000e604  push    r14
0x14000e606  lea     rbp, [rsp-160h]
0x14000e60e  sub     rsp, 260h
0x14000e615  mov     rax, cs:__security_cookie
0x14000e61c  xor     rax, rsp
0x14000e61f  mov     [rbp+170h+var_20], rax
0x14000e626  mov     r14, rdx
0x14000e629  mov     qword ptr [rdx], 0
0x14000e630  mov     rbx, rcx
0x14000e633  call    cs:__imp_GetCurrentProcessId
0x14000e63a  nop     dword ptr [rax+rax+00h]
0x14000e63f  mov     [rsp+270h+var_248], rbx
0x14000e644  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000e64b  mov     r9d, eax
0x14000e64e  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x14000e656  mov     edx, 104h; unsigned __int64
0x14000e65b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000e660  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000e665  mov     r9d, 1F0001h; dwDesiredAccess
0x14000e66b  lea     rdx, [rsp+270h+Name]; lpName
0x14000e670  xor     r8d, r8d; dwFlags
0x14000e673  xor     ecx, ecx; lpMutexAttributes
0x14000e675  call    cs:__imp_CreateMutexExW
0x14000e67c  nop     dword ptr [rax+rax+00h]
0x14000e681  mov     [rsp+270h+hObject], rax
0x14000e686  mov     rbx, rax
0x14000e689  test    rax, rax
0x14000e68c  jnz     short loc_14000E698
0x14000e68e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000e693  jmp     loc_14000E81C
0x14000e698  xor     r8d, r8d; bAlertable
0x14000e69b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000e69e  mov     rcx, rbx; hHandle
0x14000e6a1  call    cs:__imp_WaitForSingleObjectEx
0x14000e6a8  nop     dword ptr [rax+rax+00h]
0x14000e6ad  cmp     eax, 102h
0x14000e6b2  jz      short loc_14000E6C4
0x14000e6b4  test    eax, 0FFFFFF7Fh
0x14000e6b9  jnz     loc_14000E856
0x14000e6bf  mov     rdi, rbx
0x14000e6c2  jmp     short loc_14000E6C6
0x14000e6c4  xor     edi, edi
0x14000e6c6  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x14000e6cb  mov     [rsp+270h+var_238], 0
0x14000e6d4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000e6d9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000e6de  mov     esi, eax
0x14000e6e0  test    eax, eax
0x14000e6e2  jns     short loc_14000E75A
0x14000e6e4  mov     rcx, [rbp+178h]; this
0x14000e6eb  mov     r9d, eax; char *
0x14000e6ee  mov     edx, 66h ; 'f'; void *
0x14000e6f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e6f8  mov     rcx, [rbp+178h]; this
0x14000e6ff  mov     r9d, esi; char *
0x14000e702  mov     edx, 6Fh ; 'o'; void *
0x14000e707  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e70c  mov     rcx, [rbp+178h]; this
0x14000e713  mov     r9d, esi; char *
0x14000e716  mov     edx, 12Eh; void *
0x14000e71b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e720  test    rdi, rdi
0x14000e723  jz      short loc_14000E73C
0x14000e725  mov     rcx, rdi; hMutex
0x14000e728  call    cs:__imp_ReleaseMutex
0x14000e72f  nop     dword ptr [rax+rax+00h]
0x14000e734  test    eax, eax
0x14000e736  jz      loc_14000E863
0x14000e73c  mov     rcx, rbx; hObject
0x14000e73f  call    cs:__imp_CloseHandle
0x14000e746  nop     dword ptr [rax+rax+00h]
0x14000e74b  test    eax, eax
0x14000e74d  jz      loc_14000E875
0x14000e753  mov     eax, esi
0x14000e755  jmp     loc_14000E81C
0x14000e75a  mov     rax, [rsp+270h+var_238]
0x14000e75f  lea     rcx, ds:0[rax*4]
0x14000e767  test    rcx, rcx
0x14000e76a  jz      short loc_14000E777
0x14000e76c  mov     [r14], rcx
0x14000e76f  mov     eax, [rcx]
0x14000e771  inc     eax
0x14000e773  mov     [rcx], eax
0x14000e775  jmp     short loc_14000E7E6
0x14000e777  mov     r8, r14
0x14000e77a  lea     rdx, [rsp+270h+hObject]
0x14000e77f  lea     rcx, [rsp+270h+Name]
0x14000e784  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000e789  mov     ebx, eax
0x14000e78b  test    eax, eax
0x14000e78d  jns     short loc_14000E7E1
0x14000e78f  mov     rcx, [rbp+178h]; this
0x14000e796  mov     r9d, eax; char *
0x14000e799  mov     edx, 137h; void *
0x14000e79e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e7a3  test    rdi, rdi
0x14000e7a6  jz      short loc_14000E7BF
0x14000e7a8  mov     rcx, rdi; hMutex
0x14000e7ab  call    cs:__imp_ReleaseMutex
0x14000e7b2  nop     dword ptr [rax+rax+00h]
0x14000e7b7  test    eax, eax
0x14000e7b9  jz      loc_14000E887
0x14000e7bf  mov     rcx, [rsp+270h+hObject]; hObject
0x14000e7c4  test    rcx, rcx
0x14000e7c7  jz      short loc_14000E7DD
0x14000e7c9  call    cs:__imp_CloseHandle
0x14000e7d0  nop     dword ptr [rax+rax+00h]
0x14000e7d5  test    eax, eax
0x14000e7d7  jz      loc_14000E899
0x14000e7dd  mov     eax, ebx
0x14000e7df  jmp     short loc_14000E81C
0x14000e7e1  mov     rbx, [rsp+270h+hObject]
0x14000e7e6  test    rdi, rdi
0x14000e7e9  jz      short loc_14000E802
0x14000e7eb  mov     rcx, rdi; hMutex
0x14000e7ee  call    cs:__imp_ReleaseMutex
0x14000e7f5  nop     dword ptr [rax+rax+00h]
0x14000e7fa  test    eax, eax
0x14000e7fc  jz      loc_14000E8AB
0x14000e802  test    rbx, rbx
0x14000e805  jz      short loc_14000E81A
0x14000e807  mov     rcx, rbx; hObject
0x14000e80a  call    cs:__imp_CloseHandle
0x14000e811  nop     dword ptr [rax+rax+00h]
0x14000e816  test    eax, eax
0x14000e818  jz      short loc_14000E844
0x14000e81a  xor     eax, eax
0x14000e81c  mov     rcx, [rbp+170h+var_20]
0x14000e823  xor     rcx, rsp; StackCookie
0x14000e826  call    __security_check_cookie
0x14000e82b  lea     r11, [rsp+270h+var_10]
0x14000e833  mov     rbx, [r11+30h]
0x14000e837  mov     rsi, [r11+38h]
0x14000e83b  mov     rsp, r11
0x14000e83e  pop     r14
0x14000e840  pop     rdi
0x14000e841  pop     rbp
0x14000e842  retn
0x14000e844  mov     rcx, [rbp+178h]; this
0x14000e84b  mov     edx, 0A0Bh; void *
0x14000e850  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e856  mov     rcx, [rbp+178h]; this
0x14000e85d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000e863  mov     rcx, [rbp+178h]; this
0x14000e86a  mov     edx, 0A15h; void *
0x14000e86f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e875  mov     rcx, [rbp+178h]; this
0x14000e87c  mov     edx, 0A0Bh; void *
0x14000e881  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e887  mov     rcx, [rbp+178h]; this
0x14000e88e  mov     edx, 0A15h; void *
0x14000e893  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e899  mov     rcx, [rbp+178h]; this
0x14000e8a0  mov     edx, 0A0Bh; void *
0x14000e8a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e8ab  mov     rcx, [rbp+178h]; this
0x14000e8b2  mov     edx, 0A15h; void *
0x14000e8b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
