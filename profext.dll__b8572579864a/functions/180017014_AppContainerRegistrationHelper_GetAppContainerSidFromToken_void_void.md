# AppContainerRegistrationHelper::GetAppContainerSidFromToken(void *,void * *)

- ea: `0x180017014`
- end: `0x180017197`
- name: `?GetAppContainerSidFromToken@AppContainerRegistrationHelper@@SAJPEAXPEAPEAX@Z`
- size: `387`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002a80`
- `0x18000ca58`
- `0x18001fed0`

## callees

- `0x1800044e0`
- `0x180004594`
- `0x18000c770`
- `0x18000f41c`
- `0x18000f6cc`
- `0x18000f864`
- `0x180017014`
- `0x180022830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800170cb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800170cb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001712b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001712b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017054`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800170db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800170db`

## string_xrefs

- `0x180017068`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800170a1`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180017102`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180017146`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::GetAppContainerSidFromToken(void *a1, void **a2)
{
  const char *v3; // r9
  unsigned int IsChildAppContainerSid; // ebx
  __int64 v6; // rdx
  SIZE_T LengthSid; // rdi
  void *v8; // rax
  void *v9; // rbx
  const char *ReturnLength; // [rsp+20h] [rbp-39h]
  char *v11; // [rsp+28h] [rbp-31h]
  int v12[2]; // [rsp+30h] [rbp-29h] BYREF
  DWORD v13; // [rsp+38h] [rbp-21h] BYREF
  PSID TokenInformation[10]; // [rsp+40h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v13 = 76;
  if ( !GetTokenInformation(a1, TokenAppContainerSid, TokenInformation, 0x4Cu, &v13) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x188,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
             v3);
  v12[0] = 0;
  IsChildAppContainerSid = AppContainerRegistrationHelper::IsChildAppContainerSid(TokenInformation[0], v12);
  if ( (IsChildAppContainerSid & 0x80000000) == 0 )
  {
    if ( !v12[0] )
    {
      LengthSid = GetLengthSid(TokenInformation[0]);
      v8 = CoTaskMemAlloc(LengthSid);
      *(_QWORD *)v12 = v8;
      v9 = v8;
      if ( v8 )
      {
        if ( CopySid(LengthSid, v8, TokenInformation[0]) )
        {
          *a2 = v9;
          IsChildAppContainerSid = 0;
          *(_QWORD *)v12 = 0;
        }
        else
        {
          LODWORD(ReturnLength) = LengthSid;
          IsChildAppContainerSid = wil::details::in1diag3::Return_GetLastErrorMsg(
                                     retaddr,
                                     (void *)0x199,
                                     (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                                     "len %d",
                                     ReturnLength);
        }
      }
      else
      {
        LODWORD(v11) = LengthSid;
        IsChildAppContainerSid = -2147024882;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)0x8007000ELL,
          (int)"len %d",
          v11,
          0);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v12);
      return IsChildAppContainerSid;
    }
    IsChildAppContainerSid = -2147024809;
    v6 = 398;
  }
  else
  {
    v6 = 397;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)IsChildAppContainerSid,
    (int)ReturnLength);
  return IsChildAppContainerSid;
}

```

## disassembly

```asm
0x180017014  mov     [rsp-8+arg_10], rbx
0x180017019  push    rbp
0x18001701a  push    rsi
0x18001701b  push    rdi
0x18001701c  lea     rbp, [rsp-47h]
0x180017021  sub     rsp, 0A0h
0x180017028  mov     rax, cs:__security_cookie
0x18001702f  xor     rax, rsp
0x180017032  mov     [rbp+57h+var_20], rax
0x180017036  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18001703c  lea     rax, [rbp+57h+var_78]
0x180017040  mov     rsi, rdx
0x180017043  mov     [rbp+57h+var_78], r9d
0x180017047  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18001704b  mov     [rsp+0B0h+ReturnLength], rax; int
0x180017050  lea     edx, [r9-2Dh]; TokenInformationClass
0x180017054  call    cs:__imp_GetTokenInformation
0x18001705b  nop     dword ptr [rax+rax+00h]
0x180017060  test    eax, eax
0x180017062  jnz     short loc_18001707E
0x180017064  mov     rcx, [rbp+5Fh]; this
0x180017068  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001706f  mov     edx, 188h; void *
0x180017074  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017079  jmp     loc_180017177
0x18001707e  mov     rcx, [rbp+57h+TokenInformation]; void *
0x180017082  lea     rdx, [rbp+57h+var_80]; int *
0x180017086  mov     [rbp+57h+var_80], 0
0x18001708d  call    ?IsChildAppContainerSid@AppContainerRegistrationHelper@@CAJQEAXPEAH@Z; AppContainerRegistrationHelper::IsChildAppContainerSid(void * const,int *)
0x180017092  mov     ebx, eax
0x180017094  test    eax, eax
0x180017096  jns     short loc_1800170B5
0x180017098  mov     edx, 18Dh; void *
0x18001709d  mov     rcx, [rbp+5Fh]; this
0x1800170a1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800170a8  mov     r9d, ebx; char *
0x1800170ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800170b0  jmp     loc_180017175
0x1800170b5  cmp     [rbp+57h+var_80], 0
0x1800170b9  jz      short loc_1800170C7
0x1800170bb  mov     ebx, 80070057h
0x1800170c0  mov     edx, 18Eh
0x1800170c5  jmp     short loc_18001709D
0x1800170c7  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x1800170cb  call    cs:__imp_GetLengthSid
0x1800170d2  nop     dword ptr [rax+rax+00h]
0x1800170d7  mov     ecx, eax; cb
0x1800170d9  mov     edi, eax
0x1800170db  call    cs:__imp_CoTaskMemAlloc
0x1800170e2  nop     dword ptr [rax+rax+00h]
0x1800170e7  mov     qword ptr [rbp+57h+var_80], rax
0x1800170eb  mov     rbx, rax
0x1800170ee  test    rax, rax
0x1800170f1  jnz     short loc_180017122
0x1800170f3  mov     rcx, [rbp+5Fh]; this
0x1800170f7  lea     r9, aLenD; "len %d"
0x1800170fe  mov     dword ptr [rsp+0B0h+var_88], edi; char *
0x180017102  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017109  mov     [rsp+0B0h+ReturnLength], r9; int
0x18001710e  mov     ebx, 8007000Eh
0x180017113  mov     r9d, ebx; char *
0x180017116  mov     edx, 193h; void *
0x18001711b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017120  jmp     short loc_18001716C
0x180017122  mov     r8, [rbp+57h+TokenInformation]; pSourceSid
0x180017126  mov     rdx, rbx; pDestinationSid
0x180017129  mov     ecx, edi; nDestinationSidLength
0x18001712b  call    cs:__imp_CopySid
0x180017132  nop     dword ptr [rax+rax+00h]
0x180017137  test    eax, eax
0x180017139  jnz     short loc_18001715F
0x18001713b  mov     rcx, [rbp+5Fh]; this
0x18001713f  lea     r9, aLenD; "len %d"
0x180017146  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001714d  mov     dword ptr [rsp+0B0h+ReturnLength], edi; char *
0x180017151  mov     edx, 199h; void *
0x180017156  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18001715b  mov     ebx, eax
0x18001715d  jmp     short loc_18001716C
0x18001715f  mov     [rsi], rbx
0x180017162  xor     ebx, ebx
0x180017164  mov     qword ptr [rbp+57h+var_80], 0
0x18001716c  lea     rcx, [rbp+57h+var_80]
0x180017170  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180017175  mov     eax, ebx
0x180017177  mov     rcx, [rbp+57h+var_20]
0x18001717b  xor     rcx, rsp; StackCookie
0x18001717e  call    __security_check_cookie
0x180017183  mov     rbx, [rsp+0B0h+arg_10]
0x18001718b  add     rsp, 0A0h
0x180017192  pop     rdi
0x180017193  pop     rsi
0x180017194  pop     rbp
0x180017195  retn
```
