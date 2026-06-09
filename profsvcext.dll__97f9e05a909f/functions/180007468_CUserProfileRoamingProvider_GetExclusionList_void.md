# CUserProfileRoamingProvider::_GetExclusionList(void)

- ea: `0x180007468`
- end: `0x1800075d0`
- name: `?_GetExclusionList@CUserProfileRoamingProvider@@AEAAJXZ`
- size: `360`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007bd0`
- `0x180012314`

## callees

- `0x180006a80`
- `0x180006a9c`
- `0x180007468`
- `0x1800075d8`
- `0x18000927c`
- `0x18000fca8`
- `0x180013aac`
- `0x180015534`
- `0x180020010`

## string_xrefs

- `0x1800074b4`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800074ff`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x18000753b`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180007599`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_GetExclusionList(CUserProfileRoamingProvider *this)
{
  void *v2; // rax
  int v3; // eax
  unsigned int v4; // ebx
  const unsigned __int16 *v5; // rax
  unsigned int *v6; // r8
  int ExclusionListFromFile; // eax
  const unsigned __int16 *v8; // rax
  unsigned int *v9; // r8
  int v10; // eax
  unsigned __int16 *v11; // rbx
  int v12; // eax
  __int64 v14; // [rsp+20h] [rbp-10h] BYREF
  char v15; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  unsigned __int16 *v17; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int16 *v18; // [rsp+58h] [rbp+28h] BYREF

  v18 = 0;
  v17 = 0;
  v14 = 0;
  v15 = 0;
  v2 = (void *)(***((__int64 (__fastcall ****)(_QWORD))this + 1))(*((_QWORD *)this + 1));
  v3 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v14, v2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v18 = 0;
    v5 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
    ExclusionListFromFile = GetExclusionListFromFile(v5, &v18, v6);
    if ( ExclusionListFromFile < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x94B,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)ExclusionListFromFile);
    v17 = 0;
    v8 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 72LL))(*((_QWORD *)this + 1));
    v10 = GetExclusionListFromFile(v8, &v17, v9);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x94E,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v10);
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v14);
    v11 = v18;
    if ( v18
      && v17
      && StringIsEqual(v18, v17)
      && *v11
      && (v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 1) + 112LL))(
                  *((_QWORD *)this + 1),
                  v11),
          v4 = v12,
          v12 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x957,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v12,
        v14);
    }
    else
    {
      v4 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x948,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v3,
      v14);
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v14);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
  return v4;
}

```

## disassembly

```asm
0x180007468  mov     [rsp-18h+arg_10], rbx
0x18000746d  push    rbp
0x18000746e  push    rsi
0x18000746f  push    rdi
0x180007470  mov     rbp, rsp
0x180007473  sub     rsp, 30h
0x180007477  mov     rdi, rcx
0x18000747a  xor     esi, esi
0x18000747c  mov     [rbp+arg_8], rsi
0x180007480  mov     [rbp+arg_0], rsi
0x180007484  mov     [rbp+var_10], rsi
0x180007488  mov     [rbp+var_8], sil
0x18000748c  mov     rcx, [rcx+8]
0x180007490  mov     rax, [rcx]
0x180007493  mov     rax, [rax]
0x180007496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000749b  mov     rdx, rax; void *
0x18000749e  lea     rcx, [rbp+var_10]; this
0x1800074a2  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x1800074a7  mov     ebx, eax
0x1800074a9  test    eax, eax
0x1800074ab  jns     short loc_1800074D4
0x1800074ad  mov     rcx, [rbp+18h]; this
0x1800074b1  mov     r9d, eax; char *
0x1800074b4  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800074bb  mov     edx, 948h; void *
0x1800074c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074c5  nop
0x1800074c6  lea     rcx, [rbp+var_10]; this
0x1800074ca  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800074cf  jmp     loc_1800075AE
0x1800074d4  mov     [rbp+arg_8], rsi
0x1800074d8  mov     rcx, [rdi+8]
0x1800074dc  mov     rax, [rcx]
0x1800074df  mov     rax, [rax+50h]
0x1800074e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074e8  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x1800074ec  mov     rcx, rax; unsigned __int16 *
0x1800074ef  call    ?GetExclusionListFromFile@@YAJPEBGPEAPEAGPEAK@Z; GetExclusionListFromFile(ushort const *,ushort * *,ulong *)
0x1800074f4  mov     rcx, [rbp+18h]; this
0x1800074f8  test    eax, eax
0x1800074fa  jns     short loc_180007510
0x1800074fc  mov     r9d, eax; char *
0x1800074ff  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180007506  mov     edx, 94Bh; void *
0x18000750b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007510  mov     [rbp+arg_0], rsi
0x180007514  mov     rcx, [rdi+8]
0x180007518  mov     rax, [rcx]
0x18000751b  mov     rax, [rax+48h]
0x18000751f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007524  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x180007528  mov     rcx, rax; unsigned __int16 *
0x18000752b  call    ?GetExclusionListFromFile@@YAJPEBGPEAPEAGPEAK@Z; GetExclusionListFromFile(ushort const *,ushort * *,ulong *)
0x180007530  mov     rcx, [rbp+18h]; this
0x180007534  test    eax, eax
0x180007536  jns     short loc_18000754D
0x180007538  mov     r9d, eax; char *
0x18000753b  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180007542  mov     edx, 94Eh; void *
0x180007547  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000754c  nop
0x18000754d  lea     rcx, [rbp+var_10]; this
0x180007551  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180007556  mov     rbx, [rbp+arg_8]
0x18000755a  test    rbx, rbx
0x18000755d  jz      short loc_1800075AC
0x18000755f  mov     rdx, [rbp+arg_0]; unsigned __int16 *
0x180007563  test    rdx, rdx
0x180007566  jz      short loc_1800075AC
0x180007568  mov     rcx, rbx; unsigned __int16 *
0x18000756b  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180007570  test    eax, eax
0x180007572  jz      short loc_1800075AC
0x180007574  cmp     [rbx], si
0x180007577  jz      short loc_1800075AC
0x180007579  mov     rcx, [rdi+8]
0x18000757d  mov     rax, [rcx]
0x180007580  mov     rdx, rbx
0x180007583  mov     rax, [rax+70h]
0x180007587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000758c  mov     ebx, eax
0x18000758e  test    eax, eax
0x180007590  jns     short loc_1800075AC
0x180007592  mov     rcx, [rbp+18h]; this
0x180007596  mov     r9d, eax; char *
0x180007599  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800075a0  mov     edx, 957h; void *
0x1800075a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075aa  jmp     short loc_1800075AE
0x1800075ac  mov     ebx, esi
0x1800075ae  lea     rcx, [rbp+arg_0]
0x1800075b2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800075b7  nop
0x1800075b8  lea     rcx, [rbp+arg_8]
0x1800075bc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800075c1  mov     eax, ebx
0x1800075c3  mov     rbx, [rsp+30h+arg_10]
0x1800075c8  add     rsp, 30h
0x1800075cc  pop     rdi
0x1800075cd  pop     rsi
0x1800075ce  pop     rbp
0x1800075cf  retn
```
