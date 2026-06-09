# LocalAccountManager::PackAuthBuffer(ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x1800306a0`
- end: `0x1800307a6`
- name: `?PackAuthBuffer@LocalAccountManager@@UEAAJPEBG0PEAPEAEPEAK@Z`
- size: `262`
- prototype: `int(LocalAccountManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008524`
- `0x180008544`
- `0x18001e9a4`
- `0x1800306a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306fa`
- `credui!CredPackAuthenticationBufferW` at `0x1800306d5`
- `credui!CredPackAuthenticationBufferW` at `0x180030757`
- `credui!CredPackAuthenticationBufferW` at `0x1800306d5`
- `credui!CredPackAuthenticationBufferW` at `0x180030757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003070e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003070e`

## string_xrefs

- `0x1800306e9`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x180030729`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x180030766`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`

## pseudocode

```c
__int64 __fastcall LocalAccountManager::PackAuthBuffer(
        LocalAccountManager *this,
        WCHAR *a2,
        WCHAR *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int *v5; // rdi
  const char *v9; // r9
  __int64 v10; // rdx
  unsigned int *v12; // rax
  unsigned __int8 *v13; // rbx
  unsigned int LastError; // ebx
  const char *v15; // r9
  int pcbPackedCredentials; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = a5;
  *a4 = 0;
  *v5 = 0;
  if ( CredPackAuthenticationBufferW(1u, a2, a3, 0, v5) )
  {
    v10 = 209;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v10,
             (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
             v9);
  }
  if ( GetLastError() != 122 )
  {
    v10 = 210;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v10,
             (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
             v9);
  }
  v12 = (unsigned int *)CoTaskMemAlloc(*v5);
  a5 = v12;
  v13 = (unsigned __int8 *)v12;
  if ( v12 )
  {
    if ( CredPackAuthenticationBufferW(1u, a2, a3, (PBYTE)v12, v5) )
    {
      *a4 = v13;
      LastError = 0;
      a5 = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xD6,
                    (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
                    v15);
    }
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
      (const char *)0x8007000ELL,
      pcbPackedCredentials);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&a5);
  return LastError;
}

```

## disassembly

```asm
0x1800306a0  push    rbx
0x1800306a2  push    rbp
0x1800306a3  push    rsi
0x1800306a4  push    rdi
0x1800306a5  push    r14
0x1800306a7  sub     rsp, 30h
0x1800306ab  mov     rdi, [rsp+58h+arg_20]
0x1800306b3  mov     rsi, r9
0x1800306b6  mov     qword ptr [r9], 0
0x1800306bd  mov     rbp, r8
0x1800306c0  xor     r9d, r9d; pPackedCredentials
0x1800306c3  mov     qword ptr [rsp+58h+pcbPackedCredentials], rdi; int
0x1800306c8  mov     r14, rdx
0x1800306cb  mov     dword ptr [rdi], 0
0x1800306d1  lea     ecx, [r9+1]; dwFlags
0x1800306d5  call    cs:__imp_CredPackAuthenticationBufferW
0x1800306db  test    eax, eax
0x1800306dd  jz      short loc_1800306FA
0x1800306df  mov     edx, 0D1h; void *
0x1800306e4  mov     rcx, [rsp+58h]; this
0x1800306e9  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x1800306f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800306f5  jmp     loc_18003079B
0x1800306fa  call    cs:__imp_GetLastError
0x180030700  cmp     eax, 7Ah ; 'z'
0x180030703  jz      short loc_18003070C
0x180030705  mov     edx, 0D2h
0x18003070a  jmp     short loc_1800306E4
0x18003070c  mov     ecx, [rdi]; cb
0x18003070e  call    cs:__imp_CoTaskMemAlloc
0x180030714  mov     [rsp+58h+arg_20], rax
0x18003071c  mov     rbx, rax
0x18003071f  test    rax, rax
0x180030722  jnz     short loc_180030744
0x180030724  mov     rcx, [rsp+58h]; this
0x180030729  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x180030730  mov     ebx, 8007000Eh
0x180030735  mov     edx, 0D4h; void *
0x18003073a  mov     r9d, ebx; char *
0x18003073d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030742  jmp     short loc_18003078C
0x180030744  mov     r9, rbx; pPackedCredentials
0x180030747  mov     qword ptr [rsp+58h+pcbPackedCredentials], rdi; pcbPackedCredentials
0x18003074c  mov     r8, rbp; pszPassword
0x18003074f  mov     rdx, r14; pszUserName
0x180030752  mov     ecx, 1; dwFlags
0x180030757  call    cs:__imp_CredPackAuthenticationBufferW
0x18003075d  test    eax, eax
0x18003075f  jnz     short loc_18003077B
0x180030761  mov     rcx, [rsp+58h]; this
0x180030766  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18003076d  mov     edx, 0D6h; void *
0x180030772  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180030777  mov     ebx, eax
0x180030779  jmp     short loc_18003078C
0x18003077b  mov     [rsi], rbx
0x18003077e  xor     ebx, ebx
0x180030780  mov     [rsp+58h+arg_20], 0
0x18003078c  lea     rcx, [rsp+58h+arg_20]
0x180030794  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180030799  mov     eax, ebx
0x18003079b  add     rsp, 30h
0x18003079f  pop     r14
0x1800307a1  pop     rdi
0x1800307a2  pop     rsi
0x1800307a3  pop     rbp
0x1800307a4  pop     rbx
0x1800307a5  retn
```
