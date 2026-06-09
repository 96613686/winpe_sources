# CheckOUAccess(ldap *,ldapmsg *,void *,int *)

- ea: `0x180095314`
- end: `0x1800956fd`
- name: `?CheckOUAccess@@YAHPEAUldap@@PEAUldapmsg@@PEAXPEAH@Z`
- size: `1001`
- prototype: `__int64 __fastcall(LDAP *ExternalHandle, LDAPMessage *Message, void *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e060`

## callees

- `0x180075ec0`
- `0x18007d320`
- `0x180095314`
- `0x1800a9e10`
- `0x1800bb958`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800954f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009552e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009566a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009569b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800954f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009552e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009566a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009569b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800954cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800954cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800956c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800956c3`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800956cc`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800956cc`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180095375`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180095375`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18009544e`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18009544e`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800956d5`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800956d5`

## string_xrefs

- `0x18009533b`: `nTSecurityDescriptor`
- `0x1800953a6`: `CheckOUAccess:  Object can not be accessed.`
- `0x1800953ca`: `CheckOUAccess:  Object can not be accessed.`
- `0x1800953fe`: `CheckOUAccess:  ldap_get_values failed with 0x%x`
- `0x18009542e`: `CheckOUAccess:  ldap_get_values failed with 0x%x`
- `0x180095479`: `CheckOUAccess:  ldap_get_values_len failed with 0x%x`
- `0x1800954ab`: `CheckOUAccess:  ldap_get_values_len failed with 0x%x`
- `0x1800954fc`: `CheckOUAccess:  Failed to allocate memory for SD with  %d`
- `0x180095534`: `CheckOUAccess:  Failed to allocate memory for SD with  %d`
- `0x180095670`: `CheckOUAccess:  RsopAccessCheckByType failed with  %d`
- `0x1800956a1`: `CheckOUAccess:  RsopAccessCheckByType failed with  %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CheckOUAccess(LDAP *ExternalHandle, LDAPMessage *Message, void *a3, int *a4)
{
  unsigned int v7; // esi
  PWCHAR *valuesW; // r12
  struct berval **values_lenW; // rax
  struct berval **v10; // rdi
  HLOCAL v11; // rax
  void *v12; // r14
  void (*v13)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v14; // eax
  DWORD v15; // eax
  struct berval *v16; // rdx
  size_t bv_len; // r8
  PCHAR bv_val; // rdx
  void (*v19)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  DWORD v21; // eax
  bool v23[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+68h] [rbp-98h] BYREF
  int v25; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v26[4]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v27[4]; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v28[4]; // [rsp+A8h] [rbp-58h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+B8h] [rbp-48h] BYREF
  struct _OBJECT_TYPE_LIST v30; // [rsp+C8h] [rbp-38h] BYREF
  int v31; // [rsp+D8h] [rbp-28h]
  _DWORD *v32; // [rsp+E0h] [rbp-20h]
  int v33; // [rsp+E8h] [rbp-18h]
  _DWORD *v34; // [rsp+F0h] [rbp-10h]
  WCHAR attr[8]; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v36[2]; // [rsp+108h] [rbp+8h]

  *(_OWORD *)attr = *(_OWORD *)L"nTSecurityDescriptor";
  v7 = 0;
  *a4 = 0;
  v36[0] = *(_OWORD *)L"tyDescriptor";
  *(_OWORD *)((char *)v36 + 10) = *(_OWORD *)L"criptor";
  valuesW = ldap_get_valuesW(ExternalHandle, Message, attr);
  if ( valuesW )
  {
    values_lenW = ldap_get_values_lenW(ExternalHandle, Message, attr);
    v10 = values_lenW;
    if ( values_lenW )
    {
      v11 = LocalAlloc(0x40u, (*values_lenW)->bv_len);
      v12 = v11;
      if ( v11 )
      {
        *(_DWORD *)&v30.Level = 0;
        v30.ObjectType = (GUID *)v26;
        *(_DWORD *)&v23[4] = 0;
        v16 = *v10;
        v32 = v27;
        v34 = v28;
        v26[0] = -1080657243;
        v26[1] = 298847718;
        v26[2] = -1442806366;
        v26[3] = -498520064;
        v28[0] = -217171009;
        v28[1] = 298950640;
        v28[2] = 950;
        v28[3] = -1050213384;
        v27[0] = -217171010;
        v27[1] = 298950640;
        v27[2] = 950;
        v27[3] = -1050213384;
        v31 = 1;
        v33 = 1;
        GenericMapping.GenericRead = 131220;
        GenericMapping.GenericWrite = 131112;
        GenericMapping.GenericExecute = 131076;
        GenericMapping.GenericAll = 983551;
        bv_len = v16->bv_len;
        bv_val = v16->bv_val;
        *(_DWORD *)v23 = 1;
        memcpy_0(v11, bv_val, bv_len);
        if ( (int)RsopAccessCheckByTypeInternal(
                    v12,
                    &v30,
                    3u,
                    &GenericMapping,
                    (int)&v25,
                    (int)&v24,
                    (bool)&v23[4],
                    (__int64)v23) >= 0 )
        {
          v7 = 1;
          *a4 = *(_DWORD *)v23;
        }
        else if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v19 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            LastError = GetLastError();
            v19(2u, L"CheckOUAccess:  RsopAccessCheckByType failed with  %d", LastError);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v21 = GetLastError();
            RedirectDebugMsg(2u, L"CheckOUAccess:  RsopAccessCheckByType failed with  %d", v21);
          }
        }
        LocalFree(v12);
      }
      else if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v13 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v14 = GetLastError();
          v13(2u, L"CheckOUAccess:  Failed to allocate memory for SD with  %d", v14);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v15 = GetLastError();
          RedirectDebugMsg(2u, L"CheckOUAccess:  Failed to allocate memory for SD with  %d", v15);
        }
      }
      ldap_value_free_len(v10);
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CheckOUAccess:  ldap_get_values_len failed with 0x%x", ExternalHandle->ld_errno);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CheckOUAccess:  ldap_get_values_len failed with 0x%x", ExternalHandle->ld_errno);
      }
    }
    ldap_value_freeW(valuesW);
  }
  else if ( ExternalHandle->ld_errno == 16 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CheckOUAccess:  Object can not be accessed.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CheckOUAccess:  Object can not be accessed.");
      }
    }
    return 1;
  }
  else if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"CheckOUAccess:  ldap_get_values failed with 0x%x");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"CheckOUAccess:  ldap_get_values failed with 0x%x");
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180095314  push    rbp
0x180095316  push    rbx
0x180095317  push    rsi
0x180095318  push    rdi
0x180095319  push    r12
0x18009531b  push    r13
0x18009531d  push    r14
0x18009531f  push    r15
0x180095321  lea     rbp, [rsp-38h]
0x180095326  sub     rsp, 138h
0x18009532d  mov     rax, cs:__security_cookie
0x180095334  xor     rax, rsp
0x180095337  mov     [rbp+70h+var_48], rax
0x18009533b  movups  xmm0, xmmword ptr cs:aNtsecuritydesc; "nTSecurityDescriptor"
0x180095342  mov     r13, r8
0x180095345  xor     r14d, r14d
0x180095348  movups  xmm1, xmmword ptr cs:aNtsecuritydesc+10h; "tyDescriptor"
0x18009534f  lea     r8, [rbp+70h+attr]; attr
0x180095353  mov     r15, r9
0x180095356  movups  xmmword ptr [rbp+70h+attr], xmm0
0x18009535a  mov     rdi, rdx
0x18009535d  mov     rbx, rcx
0x180095360  movups  xmm0, xmmword ptr cs:aNtsecuritydesc+1Ah; "criptor"
0x180095367  mov     esi, r14d
0x18009536a  mov     [r9], r14d
0x18009536d  movups  xmmword ptr [rbp+70h+var_68], xmm1
0x180095371  movups  xmmword ptr [rbp+70h+var_68+0Ah], xmm0
0x180095375  call    cs:__imp_ldap_get_valuesW
0x18009537b  mov     r12, rax
0x18009537e  test    rax, rax
0x180095381  jnz     loc_180095444
0x180095387  mov     r8d, [rbx+74h]
0x18009538b  cmp     r8d, 10h
0x18009538f  jnz     short loc_1800953E5
0x180095391  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180095398  jz      short loc_1800953DB
0x18009539a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800953a1  test    rax, rax
0x1800953a4  jz      short loc_1800953B8
0x1800953a6  lea     rdx, aCheckouaccessO; "CheckOUAccess:  Object can not be acces"...
0x1800953ad  lea     ecx, [r14+4]
0x1800953b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800953b6  jmp     short loc_1800953DB
0x1800953b8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800953bf  jz      short loc_1800953DB
0x1800953c1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800953c8  jz      short loc_1800953DB
0x1800953ca  lea     rdx, aCheckouaccessO; "CheckOUAccess:  Object can not be acces"...
0x1800953d1  mov     ecx, 4; unsigned int
0x1800953d6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800953db  mov     esi, 1
0x1800953e0  jmp     loc_1800956DB
0x1800953e5  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800953ec  jz      loc_1800956DB
0x1800953f2  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800953f9  test    rax, rax
0x1800953fc  jz      short loc_180095414
0x1800953fe  lea     rdx, aCheckouaccessL; "CheckOUAccess:  ldap_get_values failed "...
0x180095405  mov     ecx, 2
0x18009540a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009540f  jmp     loc_1800956DB
0x180095414  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18009541b  jz      loc_1800956DB
0x180095421  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180095428  jz      loc_1800956DB
0x18009542e  lea     rdx, aCheckouaccessL; "CheckOUAccess:  ldap_get_values failed "...
0x180095435  mov     ecx, 2; unsigned int
0x18009543a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009543f  jmp     loc_1800956DB
0x180095444  lea     r8, [rbp+70h+attr]; attr
0x180095448  mov     rdx, rdi; Message
0x18009544b  mov     rcx, rbx; ExternalHandle
0x18009544e  call    cs:__imp_ldap_get_values_lenW
0x180095454  mov     rdi, rax
0x180095457  test    rax, rax
0x18009545a  jnz     short loc_1800954C1
0x18009545c  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180095463  jz      loc_1800956D2
0x180095469  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180095470  test    rax, rax
0x180095473  jz      short loc_18009548D
0x180095475  mov     r8d, [rbx+74h]
0x180095479  lea     rdx, aCheckouaccessL_0; "CheckOUAccess:  ldap_get_values_len fai"...
0x180095480  lea     ecx, [rdi+2]
0x180095483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095488  jmp     loc_1800956D2
0x18009548d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180095494  jz      loc_1800956D2
0x18009549a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800954a1  jz      loc_1800956D2
0x1800954a7  mov     r8d, [rbx+74h]
0x1800954ab  lea     rdx, aCheckouaccessL_0; "CheckOUAccess:  ldap_get_values_len fai"...
0x1800954b2  mov     ecx, 2; unsigned int
0x1800954b7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800954bc  jmp     loc_1800956D2
0x1800954c1  mov     rax, [rax]
0x1800954c4  mov     ecx, 40h ; '@'; uFlags
0x1800954c9  mov     edx, [rax]; uBytes
0x1800954cb  call    cs:__imp_LocalAlloc
0x1800954d1  xor     edx, edx
0x1800954d3  mov     r14, rax
0x1800954d6  test    rax, rax
0x1800954d9  jnz     short loc_18009554D
0x1800954db  cmp     cs:?g_dwDebugLevel@@3KA, edx; ulong g_dwDebugLevel
0x1800954e1  jz      loc_1800956C9
0x1800954e7  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800954ee  test    rbx, rbx
0x1800954f1  jz      short loc_180095514
0x1800954f3  call    cs:__imp_GetLastError
0x1800954f9  mov     r8d, eax
0x1800954fc  lea     rdx, aCheckouaccessF; "CheckOUAccess:  Failed to allocate memo"...
0x180095503  mov     rax, rbx
0x180095506  lea     ecx, [r14+2]
0x18009550a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009550f  jmp     loc_1800956C9
0x180095514  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rdx; void * g_lpDebugMsgContextInstance
0x18009551b  jz      loc_1800956C9
0x180095521  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rdx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180095528  jz      loc_1800956C9
0x18009552e  call    cs:__imp_GetLastError
0x180095534  lea     rdx, aCheckouaccessF; "CheckOUAccess:  Failed to allocate memo"...
0x18009553b  mov     ecx, 2; unsigned int
0x180095540  mov     r8d, eax
0x180095543  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180095548  jmp     loc_1800956C9
0x18009554d  mov     dword ptr [rbp+70h+var_A8.Level], edx
0x180095550  lea     rax, [rbp+70h+var_E8]
0x180095554  mov     [rbp+70h+var_A8.ObjectType], rax
0x180095558  mov     ebx, 1
0x18009555d  mov     dword ptr [rsp+170h+var_110+4], edx
0x180095561  lea     rax, [rbp+70h+var_D8]
0x180095565  mov     rdx, [rdi]
0x180095568  mov     rcx, r14; void *
0x18009556b  mov     [rbp+70h+var_90], rax
0x18009556f  lea     rax, [rbp+70h+var_C8]
0x180095573  mov     [rbp+70h+var_80], rax
0x180095577  mov     [rbp+70h+var_E8], 0BF967AA5h
0x18009557e  mov     [rbp+70h+var_E4], 11D00DE6h
0x180095585  mov     [rbp+70h+var_E0], 0AA0085A2h
0x18009558c  mov     [rbp+70h+var_DC], 0E2493000h
0x180095593  mov     [rbp+70h+var_C8], 0F30E3BBFh
0x18009559a  mov     [rbp+70h+var_C4], 11D19FF0h
0x1800955a1  mov     [rbp+70h+var_C0], 3B6h
0x1800955a8  mov     [rbp+70h+var_BC], 0C16703F8h
0x1800955af  mov     [rbp+70h+var_D8], 0F30E3BBEh
0x1800955b6  mov     [rbp+70h+var_D4], 11D19FF0h
0x1800955bd  mov     [rbp+70h+var_D0], 3B6h
0x1800955c4  mov     [rbp+70h+var_CC], 0C16703F8h
0x1800955cb  mov     [rbp+70h+var_98], ebx
0x1800955ce  mov     [rbp+70h+var_88], ebx
0x1800955d1  mov     [rbp+70h+var_B8.GenericRead], 20094h
0x1800955d8  mov     [rbp+70h+var_B8.GenericWrite], 20028h
0x1800955df  mov     [rbp+70h+var_B8.GenericExecute], 20004h
0x1800955e6  mov     [rbp+70h+var_B8.GenericAll], 0F01FFh
0x1800955ed  mov     r8d, [rdx]; Size
0x1800955f0  mov     rdx, [rdx+8]; Src
0x1800955f4  mov     dword ptr [rsp+170h+var_110], ebx
0x1800955f8  call    memcpy_0
0x1800955fd  lea     rax, [rsp+170h+var_110]
0x180095602  mov     r8, r13
0x180095605  mov     [rsp+170h+var_120], rax; __int64
0x18009560a  lea     r9d, [rbx+0Fh]
0x18009560e  lea     rax, [rsp+170h+var_110+4]
0x180095613  xor     edx, edx
0x180095615  mov     qword ptr [rsp+170h+var_128], rax; bool
0x18009561a  mov     rcx, r14; pSecurityDescriptor
0x18009561d  lea     rax, [rsp+170h+var_108]
0x180095622  mov     qword ptr [rsp+170h+var_130], rax; int
0x180095627  lea     rax, [rsp+170h+var_100]
0x18009562c  mov     qword ptr [rsp+170h+var_138], rax; int
0x180095631  lea     rax, [rbp+70h+var_B8]
0x180095635  mov     [rsp+170h+GenericMapping], rax; GenericMapping
0x18009563a  lea     rax, [rbp+70h+var_A8]
0x18009563e  mov     [rsp+170h+var_148], 3; unsigned int
0x180095646  mov     [rsp+170h+var_150], rax; struct _OBJECT_TYPE_LIST *
0x18009564b  call    RsopAccessCheckByTypeInternal
0x180095650  xor     ecx, ecx
0x180095652  test    eax, eax
0x180095654  jns     short loc_1800956B7
0x180095656  cmp     cs:?g_dwDebugLevel@@3KA, ecx; ulong g_dwDebugLevel
0x18009565c  jz      short loc_1800956C0
0x18009565e  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180095665  test    rbx, rbx
0x180095668  jz      short loc_180095689
0x18009566a  call    cs:__imp_GetLastError
0x180095670  lea     rdx, aCheckouaccessR; "CheckOUAccess:  RsopAccessCheckByType f"...
0x180095677  mov     ecx, 2
0x18009567c  mov     r8d, eax
0x18009567f  mov     rax, rbx
0x180095682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095687  jmp     short loc_1800956C0
0x180095689  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rcx; void * g_lpDebugMsgContextInstance
0x180095690  jz      short loc_1800956C0
0x180095692  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rcx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180095699  jz      short loc_1800956C0
0x18009569b  call    cs:__imp_GetLastError
0x1800956a1  lea     rdx, aCheckouaccessR; "CheckOUAccess:  RsopAccessCheckByType f"...
0x1800956a8  mov     ecx, 2; unsigned int
0x1800956ad  mov     r8d, eax
0x1800956b0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800956b5  jmp     short loc_1800956C0
0x1800956b7  mov     eax, dword ptr [rsp+170h+var_110]
0x1800956bb  mov     esi, ebx
0x1800956bd  mov     [r15], eax
0x1800956c0  mov     rcx, r14; hMem
0x1800956c3  call    cs:__imp_LocalFree
0x1800956c9  mov     rcx, rdi; vals
0x1800956cc  call    cs:__imp_ldap_value_free_len
0x1800956d2  mov     rcx, r12; vals
0x1800956d5  call    cs:__imp_ldap_value_freeW
0x1800956db  mov     eax, esi
0x1800956dd  mov     rcx, [rbp+70h+var_48]
0x1800956e1  xor     rcx, rsp; StackCookie
0x1800956e4  call    __security_check_cookie
0x1800956e9  add     rsp, 138h
0x1800956f0  pop     r15
0x1800956f2  pop     r14
0x1800956f4  pop     r13
0x1800956f6  pop     r12
0x1800956f8  pop     rdi
0x1800956f9  pop     rsi
0x1800956fa  pop     rbx
0x1800956fb  pop     rbp
0x1800956fc  retn
```
