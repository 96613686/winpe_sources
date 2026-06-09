# Pku2uMapCredsToProviderHResult(_PKU2U_SECONDARY_CREDENTIAL *)

- ea: `0x18002e234`
- end: `0x18002e538`
- name: `?Pku2uMapCredsToProviderHResult@@YAJPEAU_PKU2U_SECONDARY_CREDENTIAL@@@Z`
- size: `772`
- prototype: `__int64 __fastcall(struct _PKU2U_SECONDARY_CREDENTIAL *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007f40`
- `0x180009070`

## callees

- `0x1800139e0`
- `0x1800210f0`
- `0x1800264a4`
- `0x18002dc24`
- `0x18002e234`
- `0x18002e6a8`
- `0x18002e738`
- `0x1800320d0`
- `0x180044cac`
- `0x180046010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18002e416`
- `ntdll!RtlFreeUnicodeString` at `0x18002e48e`
- `ntdll!RtlFreeUnicodeString` at `0x18002e4dc`
- `ntdll!RtlFreeUnicodeString` at `0x18002e416`
- `ntdll!RtlFreeUnicodeString` at `0x18002e48e`
- `ntdll!RtlFreeUnicodeString` at `0x18002e4dc`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e513`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e513`
- `ntdll!RtlEnterCriticalSection` at `0x18002e2b8`
- `ntdll!RtlEnterCriticalSection` at `0x18002e2b8`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstMapUserCredsToProvider` at `0x18002e3ee`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstMapUserCredsToProvider` at `0x18002e3ee`

## string_xrefs

- `0x18002e267`: `onecore\ds\security\protocols\pku2u\credapi.cxx`
- `0x18002e391`: `onecore\ds\security\protocols\pku2u\credapi.cxx`
- `0x18002e3ff`: `onecore\ds\security\protocols\pku2u\credapi.cxx`
- `0x18002e477`: `onecore\ds\security\protocols\pku2u\credapi.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Pku2uMapCredsToProviderHResult(struct _RTL_CRITICAL_SECTION *a1)
{
  __int64 v1; // rdx
  unsigned int inited; // ebx
  char *v3; // rbx
  int v4; // r8d
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int Src; // [rsp+20h] [rbp-49h]
  int Srca; // [rsp+20h] [rbp-49h]
  unsigned __int16 v11; // [rsp+30h] [rbp-39h] BYREF
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+38h] [rbp-31h] BYREF
  __int64 v13; // [rsp+40h] [rbp-29h] BYREF
  void *v14; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-19h] BYREF
  int v16[4]; // [rsp+60h] [rbp-9h] BYREF
  int v17[4]; // [rsp+70h] [rbp+7h] BYREF
  struct _RTL_CRITICAL_SECTION **v18; // [rsp+80h] [rbp+17h]
  char v19; // [rsp+88h] [rbp+1Fh]
  void **v20; // [rsp+90h] [rbp+27h]
  unsigned __int16 *v21; // [rsp+98h] [rbp+2Fh]
  char v22; // [rsp+A0h] [rbp+37h]
  GUID v23; // [rsp+A8h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v12 = a1;
  if ( a1 )
  {
    if ( LODWORD(a1->SpinCount) )
    {
      v1 = 1090;
      goto LABEL_3;
    }
    if ( !a1->LockSemaphore )
    {
      v1 = 1091;
      goto LABEL_3;
    }
    inited = PrimaryCredInitCritSec(a1 + 1);
    if ( (inited & 0x80000000) != 0 )
    {
      v1 = 1093;
      goto LABEL_4;
    }
    RtlEnterCriticalSection(v12 + 1);
    v18 = &v12;
    v19 = 1;
    if ( !HIDWORD(v12[2].DebugInfo) )
    {
      v3 = (char *)v12->LockSemaphore + *((unsigned int *)v12->LockSemaphore + 19);
      v14 = &v3[*((unsigned int *)v3 + 5)];
      v11 = *((_WORD *)v3 + 12);
      ((void (__fastcall *)(void *, _QWORD))Pku2uGlobalLsaFunctions->LsaUnprotectMemory)(v14, v11);
      v20 = &v14;
      v21 = &v11;
      v22 = 1;
      *(_OWORD *)v17 = 0;
      HIWORD(v17[0]) = 2 * *((_WORD *)v3 + 4);
      LOWORD(v17[0]) = HIWORD(v17[0]);
      *(_QWORD *)&v17[2] = &v3[*((unsigned int *)v3 + 1)];
      *(_OWORD *)v16 = 0;
      HIWORD(v16[0]) = 2 * *((_WORD *)v3 + 8);
      LOWORD(v16[0]) = HIWORD(v16[0]);
      *(_QWORD *)&v16[2] = &v3[*((unsigned int *)v3 + 3)];
      v13 = 0;
      v5 = SspiHelperConstructAuthEx2FromStrings((int)v17, (int)v16, v4, v11, v14, (__int64)&v13);
      if ( v5 < 0 )
      {
        inited = wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)0x468,
                   (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
                   (const char *)(unsigned int)v5,
                   Srca);
        wil::details::unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&void SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&void SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>(&v13);
        ((void (__fastcall *)(void *, _QWORD))Pku2uGlobalLsaFunctions->LsaProtectMemory)(v14, v11);
LABEL_20:
        RtlLeaveCriticalSection(v12 + 1);
        return inited;
      }
      v23 = GUID_NULL;
      UnicodeString = 0;
      v6 = IntPstMapUserCredsToProvider(v13, &v23, &UnicodeString);
      if ( v6 < 0 )
      {
        inited = wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)0x470,
                   (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
                   (const char *)(unsigned int)v6,
                   Srca);
        RtlFreeUnicodeString(&UnicodeString);
        wil::details::unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&void SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&void SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>(&v13);
        ((void (__fastcall *)(void *, _QWORD))Pku2uGlobalLsaFunctions->LsaProtectMemory)(v14, v11);
        goto LABEL_20;
      }
      *(GUID *)&v12[3].DebugInfo = v23;
      v7 = KerbDuplicateStringEx((struct _UNICODE_STRING *)&v12[2].LockSemaphore, &UnicodeString, 1u, 0);
      if ( v7 < 0 )
      {
        inited = wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)0x476,
                   (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
                   (const char *)(unsigned int)v7,
                   Srca);
        RtlFreeUnicodeString(&UnicodeString);
        wil::details::unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&void SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&void SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>(&v13);
        ((void (__fastcall *)(void *, _QWORD))Pku2uGlobalLsaFunctions->LsaProtectMemory)(v14, v11);
        goto LABEL_20;
      }
      Pku2uInitTicketCache((struct _PKU2U_TICKET_CACHE *)&v12[3].OwningThread);
      HIDWORD(v12[2].DebugInfo) = 1;
      RtlFreeUnicodeString(&UnicodeString);
      wil::details::unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&void SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&void SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>(&v13);
      ((void (__fastcall *)(void *, _QWORD))Pku2uGlobalLsaFunctions->LsaProtectMemory)(v14, v11);
    }
    inited = 0;
    goto LABEL_20;
  }
  v1 = 1089;
LABEL_3:
  inited = -2147024809;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v1,
    (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
    (const char *)inited,
    Src);
  return inited;
}

```

## disassembly

```asm
0x18002e234  mov     [rsp-8+arg_8], rbx
0x18002e239  push    rbp
0x18002e23a  lea     rbp, [rsp-57h]
0x18002e23f  sub     rsp, 0C0h
0x18002e246  mov     rax, cs:__security_cookie
0x18002e24d  xor     rax, rsp
0x18002e250  mov     [rbp+57h+var_8], rax
0x18002e254  mov     [rbp+57h+var_88], rcx
0x18002e258  test    rcx, rcx
0x18002e25b  jnz     short loc_18002E27F
0x18002e25d  mov     edx, 441h; void *
0x18002e262  mov     ebx, 80070057h
0x18002e267  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002e26e  mov     r9d, ebx; char *
0x18002e271  mov     rcx, [rbp+5Fh]; this
0x18002e275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e27a  jmp     loc_18002E519
0x18002e27f  cmp     dword ptr [rcx+20h], 0
0x18002e283  jz      short loc_18002E28C
0x18002e285  mov     edx, 442h
0x18002e28a  jmp     short loc_18002E262
0x18002e28c  cmp     qword ptr [rcx+18h], 0
0x18002e291  jnz     short loc_18002E29A
0x18002e293  mov     edx, 443h
0x18002e298  jmp     short loc_18002E262
0x18002e29a  add     rcx, 28h ; '('; CriticalSection
0x18002e29e  call    ?PrimaryCredInitCritSec@@YAJPEAU_PKU2U_PRIMARY_CREDENTIAL@@@Z; PrimaryCredInitCritSec(_PKU2U_PRIMARY_CREDENTIAL *)
0x18002e2a3  mov     ebx, eax
0x18002e2a5  test    eax, eax
0x18002e2a7  jns     short loc_18002E2B0
0x18002e2a9  mov     edx, 445h
0x18002e2ae  jmp     short loc_18002E267
0x18002e2b0  mov     rcx, [rbp+57h+var_88]
0x18002e2b4  add     rcx, 28h ; '('; CriticalSection
0x18002e2b8  call    cs:__imp_RtlEnterCriticalSection
0x18002e2be  lea     rax, [rbp+57h+var_88]
0x18002e2c2  mov     [rbp+57h+var_40], rax
0x18002e2c6  mov     [rbp+57h+var_38], 1
0x18002e2ca  mov     rax, [rbp+57h+var_88]
0x18002e2ce  cmp     dword ptr [rax+54h], 0
0x18002e2d2  jnz     loc_18002E509
0x18002e2d8  mov     rcx, [rax+18h]
0x18002e2dc  mov     ebx, [rcx+4Ch]
0x18002e2df  add     rbx, rcx
0x18002e2e2  mov     ecx, [rbx+14h]
0x18002e2e5  add     rcx, rbx
0x18002e2e8  mov     [rbp+57h+var_78], rcx
0x18002e2ec  movzx   eax, word ptr [rbx+18h]
0x18002e2f0  mov     [rbp+57h+var_90], ax
0x18002e2f4  mov     edx, eax
0x18002e2f6  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002e2fd  mov     rax, [rax+168h]
0x18002e304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e309  lea     rax, [rbp+57h+var_78]
0x18002e30d  mov     [rbp+57h+var_30], rax
0x18002e311  lea     rax, [rbp+57h+var_90]
0x18002e315  mov     [rbp+57h+var_28], rax
0x18002e319  mov     [rbp+57h+var_20], 1
0x18002e31d  xorps   xmm0, xmm0
0x18002e320  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18002e324  movzx   eax, word ptr [rbx+8]
0x18002e328  add     ax, ax
0x18002e32b  mov     word ptr [rbp+57h+var_50+2], ax
0x18002e32f  mov     word ptr [rbp+57h+var_50], ax
0x18002e333  mov     eax, [rbx+4]
0x18002e336  add     rax, rbx
0x18002e339  mov     qword ptr [rbp+57h+var_50+8], rax
0x18002e33d  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18002e341  movzx   eax, word ptr [rbx+10h]
0x18002e345  add     ax, ax
0x18002e348  mov     word ptr [rbp+57h+var_60+2], ax
0x18002e34c  mov     word ptr [rbp+57h+var_60], ax
0x18002e350  mov     eax, [rbx+0Ch]
0x18002e353  add     rax, rbx
0x18002e356  mov     qword ptr [rbp+57h+var_60+8], rax
0x18002e35a  mov     [rbp+57h+var_80], 0
0x18002e362  mov     rax, [rbp+57h+var_78]
0x18002e366  lea     rcx, [rbp+57h+var_80]
0x18002e36a  mov     [rsp+0C0h+var_98], rcx; __int64
0x18002e36f  mov     [rsp+0C0h+Src], rax; int
0x18002e374  movzx   r9d, [rbp+57h+var_90]; int
0x18002e379  lea     rdx, [rbp+57h+var_60]; int
0x18002e37d  lea     rcx, [rbp+57h+var_50]; int
0x18002e381  call    SspiHelperConstructAuthEx2FromStrings
0x18002e386  test    eax, eax
0x18002e388  jns     short loc_18002E3CF
0x18002e38a  mov     rcx, [rbp+5Fh]; this
0x18002e38e  mov     r9d, eax; char *
0x18002e391  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002e398  mov     edx, 468h; void *
0x18002e39d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002e3a2  mov     ebx, eax
0x18002e3a4  lea     rcx, [rbp+57h+var_80]
0x18002e3a8  call    ??1?$unique_storage@U?$resource_policy@PEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@P6AXPEAX@Z$1?SspiFreeAuthIdentity@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>(void)
0x18002e3ad  nop
0x18002e3ae  movzx   edx, [rbp+57h+var_90]
0x18002e3b2  mov     rcx, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002e3b9  mov     rax, [rcx+160h]
0x18002e3c0  mov     rcx, [rbp+57h+var_78]
0x18002e3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3c9  nop
0x18002e3ca  jmp     loc_18002E50B
0x18002e3cf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002e3d6  movdqu  [rbp+57h+var_18], xmm0
0x18002e3db  xorps   xmm0, xmm0
0x18002e3de  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x18002e3e2  lea     r8, [rbp+57h+UnicodeString]
0x18002e3e6  lea     rdx, [rbp+57h+var_18]
0x18002e3ea  mov     rcx, [rbp+57h+var_80]
0x18002e3ee  call    cs:__imp_IntPstMapUserCredsToProvider
0x18002e3f4  test    eax, eax
0x18002e3f6  jns     short loc_18002E448
0x18002e3f8  mov     rcx, [rbp+5Fh]; this
0x18002e3fc  mov     r9d, eax; char *
0x18002e3ff  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002e406  mov     edx, 470h; void *
0x18002e40b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002e410  mov     ebx, eax
0x18002e412  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18002e416  call    cs:__imp_RtlFreeUnicodeString
0x18002e41c  nop
0x18002e41d  lea     rcx, [rbp+57h+var_80]
0x18002e421  call    ??1?$unique_storage@U?$resource_policy@PEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@P6AXPEAX@Z$1?SspiFreeAuthIdentity@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>(void)
0x18002e426  nop
0x18002e427  movzx   edx, [rbp+57h+var_90]
0x18002e42b  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002e432  mov     rcx, [rbp+57h+var_78]
0x18002e436  mov     rax, [rax+160h]
0x18002e43d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e442  nop
0x18002e443  jmp     loc_18002E50B
0x18002e448  movups  xmm0, [rbp+57h+var_18]
0x18002e44c  mov     rax, [rbp+57h+var_88]
0x18002e450  movdqu  xmmword ptr [rax+78h], xmm0
0x18002e455  mov     rcx, [rbp+57h+var_88]
0x18002e459  add     rcx, 68h ; 'h'; struct _UNICODE_STRING *
0x18002e45d  xor     r9d, r9d; unsigned __int8
0x18002e460  mov     r8b, 1; unsigned __int8
0x18002e463  lea     rdx, [rbp+57h+UnicodeString]; struct _UNICODE_STRING *
0x18002e467  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@EE@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar,uchar)
0x18002e46c  test    eax, eax
0x18002e46e  jns     short loc_18002E4BD
0x18002e470  mov     rcx, [rbp+5Fh]; this
0x18002e474  mov     r9d, eax; char *
0x18002e477  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002e47e  mov     edx, 476h; void *
0x18002e483  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002e488  mov     ebx, eax
0x18002e48a  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18002e48e  call    cs:__imp_RtlFreeUnicodeString
0x18002e494  nop
0x18002e495  lea     rcx, [rbp+57h+var_80]
0x18002e499  call    ??1?$unique_storage@U?$resource_policy@PEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@P6AXPEAX@Z$1?SspiFreeAuthIdentity@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>(void)
0x18002e49e  nop
0x18002e49f  movzx   edx, [rbp+57h+var_90]
0x18002e4a3  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002e4aa  mov     rcx, [rbp+57h+var_78]
0x18002e4ae  mov     rax, [rax+160h]
0x18002e4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4ba  nop
0x18002e4bb  jmp     short loc_18002E50B
0x18002e4bd  mov     rcx, [rbp+57h+var_88]
0x18002e4c1  add     rcx, 88h; struct _PKU2U_TICKET_CACHE *
0x18002e4c8  call    ?Pku2uInitTicketCache@@YAXPEAU_PKU2U_TICKET_CACHE@@@Z; Pku2uInitTicketCache(_PKU2U_TICKET_CACHE *)
0x18002e4cd  mov     rax, [rbp+57h+var_88]
0x18002e4d1  mov     dword ptr [rax+54h], 1
0x18002e4d8  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18002e4dc  call    cs:__imp_RtlFreeUnicodeString
0x18002e4e2  nop
0x18002e4e3  lea     rcx, [rbp+57h+var_80]
0x18002e4e7  call    ??1?$unique_storage@U?$resource_policy@PEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@P6AXPEAX@Z$1?SspiFreeAuthIdentity@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SEC_WINNT_AUTH_IDENTITY_EX2 *,void (*)(void *),&SspiFreeAuthIdentity(void *),wistd::integral_constant<unsigned __int64,0>,_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 *,0,std::nullptr_t>>(void)
0x18002e4ec  nop
0x18002e4ed  movzx   edx, [rbp+57h+var_90]
0x18002e4f1  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002e4f8  mov     rcx, [rbp+57h+var_78]
0x18002e4fc  mov     rax, [rax+160h]
0x18002e503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e508  nop
0x18002e509  xor     ebx, ebx
0x18002e50b  mov     rcx, [rbp+57h+var_88]
0x18002e50f  add     rcx, 28h ; '('; CriticalSection
0x18002e513  call    cs:__imp_RtlLeaveCriticalSection
0x18002e519  mov     eax, ebx
0x18002e51b  mov     rcx, [rbp+57h+var_8]
0x18002e51f  xor     rcx, rsp; StackCookie
0x18002e522  call    __security_check_cookie
0x18002e527  mov     rbx, [rsp+0C0h+arg_8]
0x18002e52f  add     rsp, 0C0h
0x18002e536  pop     rbp
0x18002e537  retn
```
