# LocalAccountManager::DecryptAuthBuffer(uchar *,ulong,ushort * *,ushort * *)

- ea: `0x18002fe80`
- end: `0x18003000e`
- name: `?DecryptAuthBuffer@LocalAccountManager@@UEAAJPEAEKPEAPEAG1@Z`
- size: `398`
- prototype: `int(LocalAccountManager *__hidden this, unsigned __int8 *, unsigned int, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008524`
- `0x18001e9a4`
- `0x18002fe80`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fefc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fefc`
- `credui!CredUnPackAuthenticationBufferW` at `0x18002fed8`
- `credui!CredUnPackAuthenticationBufferW` at `0x18002ff5f`
- `credui!CredUnPackAuthenticationBufferW` at `0x18002fed8`
- `credui!CredUnPackAuthenticationBufferW` at `0x18002ff5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ff14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ff27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ff14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ff27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ffdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ffdc`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18002ff92`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18002ff92`

## string_xrefs

- `0x18002fee7`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002ff6d`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LocalAccountManager::DecryptAuthBuffer(
        LocalAccountManager *this,
        unsigned __int8 *a2,
        DWORD a3,
        unsigned __int16 **a4,
        unsigned __int16 **pcchMaxPassword)
{
  unsigned __int16 **v8; // r14
  const char *v9; // r9
  __int64 v10; // rdx
  unsigned __int16 *v12; // rbx
  unsigned __int16 *pszPassword; // rdi
  const char *v14; // r9
  unsigned int LastError; // ebx
  __int64 v16; // rax
  unsigned __int16 *i; // rcx
  LPMALLOC ppMalloc; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int16 *v19; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  DWORD pcchMaxUserName; // [rsp+C8h] [rbp+60h] BYREF

  *a4 = 0;
  v8 = pcchMaxPassword;
  *pcchMaxPassword = 0;
  pcchMaxUserName = 0;
  LODWORD(pcchMaxPassword) = 0;
  if ( CredUnPackAuthenticationBufferW(1u, a2, a3, 0, &pcchMaxUserName, 0, 0, 0, (DWORD *)&pcchMaxPassword) )
  {
    v10 = 230;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v10,
             (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
             v9);
  }
  if ( GetLastError() != 122 )
  {
    v10 = 231;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v10,
             (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
             v9);
  }
  v12 = (unsigned __int16 *)CoTaskMemAlloc(2LL * pcchMaxUserName);
  v19 = v12;
  pszPassword = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)pcchMaxPassword);
  if ( CredUnPackAuthenticationBufferW(1u, a2, a3, v12, &pcchMaxUserName, 0, 0, pszPassword, (DWORD *)&pcchMaxPassword) )
  {
    v19 = 0;
    *a4 = v12;
    *v8 = pszPassword;
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xEA,
                  (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
                  v14);
    if ( pszPassword )
    {
      ppMalloc = 0;
      if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
      {
        v16 = ((__int64 (__fastcall *)(LPMALLOC, unsigned __int16 *))ppMalloc->lpVtbl->GetSize)(ppMalloc, pszPassword);
        if ( v16 != -1 )
        {
          for ( i = pszPassword; v16; --v16 )
          {
            *(_BYTE *)i = 0;
            i = (unsigned __int16 *)((char *)i + 1);
          }
        }
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      }
      CoTaskMemFree(pszPassword);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
  return LastError;
}

```

## disassembly

```asm
0x18002fe80  mov     r11, rsp
0x18002fe83  push    rbp
0x18002fe84  push    rbx
0x18002fe85  push    rsi
0x18002fe86  push    rdi
0x18002fe87  push    r12
0x18002fe89  push    r13
0x18002fe8b  push    r14
0x18002fe8d  push    r15
0x18002fe8f  mov     rbp, rsp
0x18002fe92  sub     rsp, 68h
0x18002fe96  mov     rsi, r9
0x18002fe99  mov     r15d, r8d
0x18002fe9c  mov     r12, rdx
0x18002fe9f  xor     r13d, r13d
0x18002fea2  mov     [r9], r13
0x18002fea5  mov     r14, qword ptr [rbp+arg_20]
0x18002fea9  mov     [r14], r13
0x18002feac  mov     [rbp+arg_18], r13d
0x18002feb0  mov     [rbp+arg_20], r13d
0x18002feb4  lea     rax, [rbp+arg_20]
0x18002feb8  mov     [r11-68h], rax
0x18002febc  mov     [r11-70h], r13
0x18002fec0  mov     [r11-78h], r13
0x18002fec4  mov     [r11-80h], r13
0x18002fec8  lea     rax, [rbp+arg_18]
0x18002fecc  mov     [rsp+68h+pcchMaxUserName], rax; pcchMaxUserName
0x18002fed1  xor     r9d, r9d; pszUserName
0x18002fed4  lea     ecx, [r13+1]; dwFlags
0x18002fed8  call    cs:__imp_CredUnPackAuthenticationBufferW
0x18002fede  test    eax, eax
0x18002fee0  jz      short loc_18002FEFC
0x18002fee2  mov     edx, 0E6h; void *
0x18002fee7  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002feee  mov     rcx, [rbp+40h]; this
0x18002fef2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002fef7  jmp     loc_18002FFFD
0x18002fefc  call    cs:__imp_GetLastError
0x18002ff02  cmp     eax, 7Ah ; 'z'
0x18002ff05  jz      short loc_18002FF0E
0x18002ff07  mov     edx, 0E7h
0x18002ff0c  jmp     short loc_18002FEE7
0x18002ff0e  mov     ecx, [rbp+arg_18]
0x18002ff11  add     rcx, rcx; cb
0x18002ff14  call    cs:__imp_CoTaskMemAlloc
0x18002ff1a  mov     rbx, rax
0x18002ff1d  mov     [rbp+var_10], rax
0x18002ff21  mov     ecx, [rbp+arg_20]
0x18002ff24  add     rcx, rcx; cb
0x18002ff27  call    cs:__imp_CoTaskMemAlloc
0x18002ff2d  mov     rdi, rax
0x18002ff30  lea     rax, [rbp+arg_20]
0x18002ff34  mov     [rsp+68h+pcchMaxPassword], rax; pcchMaxPassword
0x18002ff39  mov     [rsp+68h+pszPassword], rdi; pszPassword
0x18002ff3e  mov     [rsp+68h+pcchMaxDomainName], r13; pcchMaxDomainName
0x18002ff43  mov     [rsp+68h+pszDomainName], r13; pszDomainName
0x18002ff48  lea     rax, [rbp+arg_18]
0x18002ff4c  mov     [rsp+68h+pcchMaxUserName], rax; pcchMaxUserName
0x18002ff51  mov     r9, rbx; pszUserName
0x18002ff54  mov     r8d, r15d; cbAuthBuffer
0x18002ff57  mov     rdx, r12; pAuthBuffer
0x18002ff5a  mov     ecx, 1; dwFlags
0x18002ff5f  call    cs:__imp_CredUnPackAuthenticationBufferW
0x18002ff65  test    eax, eax
0x18002ff67  jnz     short loc_18002FFE5
0x18002ff69  mov     rcx, [rbp+40h]; this
0x18002ff6d  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002ff74  mov     edx, 0EAh; void *
0x18002ff79  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ff7e  mov     ebx, eax
0x18002ff80  test    rdi, rdi
0x18002ff83  jz      short loc_18002FFE3
0x18002ff85  mov     [rbp+ppMalloc], r13
0x18002ff89  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x18002ff8d  mov     ecx, 1; dwMemContext
0x18002ff92  call    cs:__imp_CoGetMalloc
0x18002ff98  test    eax, eax
0x18002ff9a  js      short loc_18002FFD9
0x18002ff9c  mov     rcx, [rbp+ppMalloc]
0x18002ffa0  mov     rax, [rcx]
0x18002ffa3  mov     rdx, rdi
0x18002ffa6  mov     rax, [rax+30h]
0x18002ffaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffaf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ffb3  jz      short loc_18002FFC9
0x18002ffb5  mov     rcx, rdi
0x18002ffb8  test    rax, rax
0x18002ffbb  jz      short loc_18002FFC9
0x18002ffbd  mov     [rcx], r13b
0x18002ffc0  inc     rcx
0x18002ffc3  sub     rax, 1
0x18002ffc7  jnz     short loc_18002FFBD
0x18002ffc9  mov     rcx, [rbp+ppMalloc]
0x18002ffcd  mov     rax, [rcx]
0x18002ffd0  mov     rax, [rax+10h]
0x18002ffd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffd9  mov     rcx, rdi; pv
0x18002ffdc  call    cs:__imp_CoTaskMemFree
0x18002ffe2  nop
0x18002ffe3  jmp     short loc_18002FFF2
0x18002ffe5  mov     [rbp+var_10], r13
0x18002ffe9  mov     [rsi], rbx
0x18002ffec  mov     [r14], rdi
0x18002ffef  mov     ebx, r13d
0x18002fff2  lea     rcx, [rbp+var_10]
0x18002fff6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002fffb  mov     eax, ebx
0x18002fffd  add     rsp, 68h
0x180030001  pop     r15
0x180030003  pop     r14
0x180030005  pop     r13
0x180030007  pop     r12
0x180030009  pop     rdi
0x18003000a  pop     rsi
0x18003000b  pop     rbx
0x18003000c  pop     rbp
0x18003000d  retn
```
