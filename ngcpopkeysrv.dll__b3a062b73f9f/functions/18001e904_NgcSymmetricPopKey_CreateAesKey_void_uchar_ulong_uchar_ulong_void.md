# NgcSymmetricPopKey::CreateAesKey(void *,uchar *,ulong,uchar *,ulong,void * *)

- ea: `0x18001e904`
- end: `0x18001ea4a`
- name: `?CreateAesKey@NgcSymmetricPopKey@@IEAAJPEAXPEAEK1KPEAPEAX@Z`
- size: `326`
- prototype: `__int64 __fastcall(NgcSymmetricPopKey *this, void *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, void **)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ea50`
- `0x18001ebe0`
- `0x18001ed50`
- `0x18001eee0`

## callees

- `0x180004de0`
- `0x18000b0fc`
- `0x18001368c`
- `0x1800137f4`
- `0x18001e904`
- `0x180028010`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001e9b9`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001e9b9`

## string_xrefs

- `0x18001e9c7`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001e96a`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`
- `0x18001ea04`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcSymmetricPopKey::CreateAesKey(
        NgcSymmetricPopKey *this,
        void *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        void **a7)
{
  int v8; // eax
  int v9; // ebx
  NTSTATUS v10; // eax
  BCRYPT_KEY_HANDLE v11; // rdi
  int pbSecret; // [rsp+20h] [rbp-41h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-21h] BYREF
  BCRYPT_KEY_HANDLE v15; // [rsp+48h] [rbp-19h] BYREF
  UCHAR v16[32]; // [rsp+50h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+47h]

  v8 = (*(__int64 (__fastcall **)(NgcSymmetricPopKey *, unsigned __int8 *, _QWORD, unsigned __int8 *))(*(_QWORD *)this + 48LL))(
         this,
         a3,
         a4,
         a5);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v15 = 0;
    phKey = 0;
    v10 = BCryptGenerateSymmetricKey(a2, &phKey, 0, 0, v16, 0x20u, 0);
    if ( v10 >= 0 )
    {
      v11 = phKey;
      v9 = 0;
      v15 = phKey;
      phKey = 0;
    }
    else
    {
      v9 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x1D8,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v10,
             pbSecret);
      v11 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    if ( v9 >= 0 )
    {
      v15 = 0;
      v9 = 0;
      *a7 = v11;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
        (const char *)(unsigned int)v9,
        pbSecret);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
      (const char *)(unsigned int)v8,
      a6);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001e904  push    rbp
0x18001e906  push    rbx
0x18001e907  push    rsi
0x18001e908  push    rdi
0x18001e909  lea     rbp, [rsp-27h]
0x18001e90e  sub     rsp, 88h
0x18001e915  mov     rax, cs:__security_cookie
0x18001e91c  xor     rax, rsp
0x18001e91f  mov     [rbp+3Fh+var_30], rax
0x18001e923  mov     rax, [rcx]
0x18001e926  mov     rdi, rdx
0x18001e929  mov     r10d, [rbp+3Fh+arg_28]
0x18001e92d  lea     rdx, [rbp+3Fh+var_50]
0x18001e931  mov     rsi, [rbp+3Fh+arg_30]
0x18001e935  mov     ebx, r9d
0x18001e938  mov     r9, [rbp+3Fh+arg_20]
0x18001e93c  mov     r11, r8
0x18001e93f  mov     rax, [rax+30h]
0x18001e943  mov     r8d, ebx
0x18001e946  mov     [rsp+0A0h+dwFlags], 20h ; ' '
0x18001e94e  mov     qword ptr [rsp+0A0h+cbSecret], rdx
0x18001e953  mov     rdx, r11
0x18001e956  mov     dword ptr [rsp+0A0h+pbSecret], r10d; int
0x18001e95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e960  mov     ebx, eax
0x18001e962  test    eax, eax
0x18001e964  jns     short loc_18001E983
0x18001e966  mov     rcx, [rbp+47h]; this
0x18001e96a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001e971  mov     r9d, eax; char *
0x18001e974  mov     edx, 68h ; 'h'; void *
0x18001e979  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e97e  jmp     loc_18001EA30
0x18001e983  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x18001e98b  lea     rax, [rbp+3Fh+var_50]
0x18001e98f  mov     [rsp+0A0h+cbSecret], 20h ; ' '; cbSecret
0x18001e997  lea     rdx, [rbp+3Fh+phKey]; phKey
0x18001e99b  xor     r9d, r9d; cbKeyObject
0x18001e99e  mov     [rsp+0A0h+pbSecret], rax; int
0x18001e9a3  xor     r8d, r8d; pbKeyObject
0x18001e9a6  mov     [rbp+3Fh+var_58], 0
0x18001e9ae  mov     rcx, rdi; hAlgorithm
0x18001e9b1  mov     [rbp+3Fh+phKey], 0
0x18001e9b9  call    cs:__imp_BCryptGenerateSymmetricKey
0x18001e9bf  test    eax, eax
0x18001e9c1  jns     short loc_18001E9E1
0x18001e9c3  mov     rcx, [rbp+47h]; this
0x18001e9c7  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001e9ce  mov     r9d, eax; char *
0x18001e9d1  mov     edx, 1D8h; void *
0x18001e9d6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001e9db  mov     ebx, eax
0x18001e9dd  xor     edi, edi
0x18001e9df  jmp     short loc_18001E9F3
0x18001e9e1  mov     rdi, [rbp+3Fh+phKey]
0x18001e9e5  xor     ebx, ebx
0x18001e9e7  mov     [rbp+3Fh+var_58], rdi
0x18001e9eb  mov     [rbp+3Fh+phKey], 0
0x18001e9f3  lea     rcx, [rbp+3Fh+phKey]
0x18001e9f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001e9fc  test    ebx, ebx
0x18001e9fe  jns     short loc_18001EA1A
0x18001ea00  mov     rcx, [rbp+47h]; this
0x18001ea04  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ea0b  mov     r9d, ebx; char *
0x18001ea0e  mov     edx, 71h ; 'q'; void *
0x18001ea13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ea18  jmp     short loc_18001EA27
0x18001ea1a  mov     [rbp+3Fh+var_58], 0
0x18001ea22  xor     ebx, ebx
0x18001ea24  mov     [rsi], rdi
0x18001ea27  lea     rcx, [rbp+3Fh+var_58]
0x18001ea2b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ea30  mov     eax, ebx
0x18001ea32  mov     rcx, [rbp+3Fh+var_30]
0x18001ea36  xor     rcx, rsp; StackCookie
0x18001ea39  call    __security_check_cookie
0x18001ea3e  add     rsp, 88h
0x18001ea45  pop     rdi
0x18001ea46  pop     rsi
0x18001ea47  pop     rbx
0x18001ea48  pop     rbp
0x18001ea49  retn
```
