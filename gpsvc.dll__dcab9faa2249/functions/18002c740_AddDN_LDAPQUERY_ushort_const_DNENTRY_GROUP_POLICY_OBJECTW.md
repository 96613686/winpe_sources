# AddDN(_LDAPQUERY * *,ushort const *,_DNENTRY *,_GROUP_POLICY_OBJECTW *)

- ea: `0x18002c740`
- end: `0x18002ca0a`
- name: `?AddDN@@YAHPEAPEAU_LDAPQUERY@@PEBGPEAU_DNENTRY@@PEAU_GROUP_POLICY_OBJECTW@@@Z`
- size: `714`
- prototype: `__int64 __fastcall(struct _LDAPQUERY **, const unsigned __int16 *, struct _DNENTRY *, struct _GROUP_POLICY_OBJECTW *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d188`
- `0x180039364`

## callees

- `0x18002c740`
- `0x18002ca10`
- `0x18002ce54`
- `0x18007060c`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c962`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c9f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c962`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c9f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c94e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c94e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c7f5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c821`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c8c6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c7f5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c821`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c8c6`

## string_xrefs

- `0x18002c7d9`: `cn=configuration`
- `0x18002c866`: `AddDN: DN %s is under cn=configuration container. queueing for rebinding`
- `0x18002c88e`: `AddDN: DN %s is under cn=configuration container. queueing for rebinding`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AddDN(
        struct _LDAPQUERY **a1,
        const unsigned __int16 *a2,
        struct _DNENTRY *a3,
        struct _GROUP_POLICY_OBJECTW *a4)
{
  __int64 v8; // r14
  DWORD LastError; // ebx
  __int64 v10; // rsi
  unsigned int inserted; // edi
  const unsigned __int16 *v12; // rdi
  int v13; // eax
  struct _LDAPQUERY *v14; // rax
  struct _LDAPQUERY *v15; // rdi
  struct _LDAPQUERY *v16; // rax

  v8 = (__int64)*a1;
  LastError = GetLastError();
  v10 = 0;
  if ( a2 )
  {
    v12 = a2;
    while ( 1 )
    {
      if ( !*v12 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"AddDN: Domain not found for <%s>. Exiting.", a2);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"AddDN: Domain not found for <%s>. Exiting.", a2);
          }
        }
        SetLastError(0xDu);
        return 0;
      }
      if ( CompareStringW(0x7Fu, 1u, v12, 16, L"cn=configuration", 16) == 2 )
        break;
      if ( CompareStringW(0x7Fu, 1u, v12, 3, L"DC=", 3) == 2 )
        goto LABEL_25;
      while ( *v12 && *v12 != 44 )
        ++v12;
      if ( *v12 == 44 )
        ++v12;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"AddDN: DN %s is under cn=configuration container. queueing for rebinding", a2);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"AddDN: DN %s is under cn=configuration container. queueing for rebinding", a2);
      }
    }
LABEL_25:
    while ( v8 )
    {
      v13 = CompareStringW(0x7Fu, 1u, v12, -1, *(PCNZWCH *)v8, -1);
      if ( v13 == 2 )
      {
        inserted = InsertDN((struct _LDAPQUERY *)v8, a2, a3, a4);
        goto LABEL_38;
      }
      if ( v13 == 1 )
      {
        v14 = AllocLdapQuery(v12);
        v15 = v14;
        if ( !v14 )
          goto LABEL_30;
        if ( (unsigned int)InsertDN(v14, a2, a3, a4) )
        {
          *((_QWORD *)v15 + 7) = v8;
          goto LABEL_40;
        }
LABEL_36:
        LastError = GetLastError();
        FreeLdapQuery(v15);
LABEL_37:
        inserted = 0;
        goto LABEL_38;
      }
      v10 = v8;
      v8 = *(_QWORD *)(v8 + 56);
    }
    v16 = AllocLdapQuery(v12);
    v15 = v16;
    if ( !v16 )
    {
LABEL_30:
      LastError = GetLastError();
      goto LABEL_37;
    }
    if ( !(unsigned int)InsertDN(v16, a2, a3, a4) )
      goto LABEL_36;
    *((_QWORD *)v15 + 7) = 0;
LABEL_40:
    if ( v10 )
      *(_QWORD *)(v10 + 56) = v15;
    else
      *a1 = v15;
    SetLastError(LastError);
    return 1;
  }
  else
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"AddDN: Null pwszDN. Exiting.");
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"AddDN: Null pwszDN. Exiting.");
      }
    }
    inserted = 0;
LABEL_38:
    SetLastError(LastError);
    return inserted;
  }
}

```

## disassembly

```asm
0x18002c740  push    rbx
0x18002c742  push    rbp
0x18002c743  push    rsi
0x18002c744  push    rdi
0x18002c745  push    r12
0x18002c747  push    r13
0x18002c749  push    r14
0x18002c74b  push    r15
0x18002c74d  sub     rsp, 38h
0x18002c751  mov     r12, r9
0x18002c754  mov     r13, r8
0x18002c757  mov     rbp, rdx
0x18002c75a  mov     r15, rcx
0x18002c75d  mov     r14, [rcx]
0x18002c760  call    cs:__imp_GetLastError
0x18002c766  mov     ebx, eax
0x18002c768  mov     [rsp+78h+arg_0], eax
0x18002c76f  xor     esi, esi
0x18002c771  test    rbp, rbp
0x18002c774  jnz     short loc_18002C7C5
0x18002c776  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18002c77c  jz      short loc_18002C7BE
0x18002c77e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002c785  test    rax, rax
0x18002c788  jz      short loc_18002C79B
0x18002c78a  lea     rdx, aAdddnNullPwszd; "AddDN: Null pwszDN. Exiting."
0x18002c791  lea     ecx, [rsi+2]
0x18002c794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c799  jmp     short loc_18002C7BE
0x18002c79b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18002c7a2  jz      short loc_18002C7BE
0x18002c7a4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002c7ab  jz      short loc_18002C7BE
0x18002c7ad  lea     rdx, aAdddnNullPwszd; "AddDN: Null pwszDN. Exiting."
0x18002c7b4  mov     ecx, 2; unsigned int
0x18002c7b9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002c7be  mov     edi, esi
0x18002c7c0  jmp     loc_18002C960
0x18002c7c5  mov     rdi, rbp
0x18002c7c8  cmp     [rdi], si
0x18002c7cb  jz      loc_18002C994
0x18002c7d1  mov     [rsp+78h+cchCount2], 10h; cchCount2
0x18002c7d9  lea     rax, aCnConfiguratio; "cn=configuration"
0x18002c7e0  mov     [rsp+78h+lpString2], rax; lpString2
0x18002c7e5  mov     r9d, 10h; cchCount1
0x18002c7eb  mov     r8, rdi; lpString1
0x18002c7ee  lea     edx, [r9-0Fh]; dwCmpFlags
0x18002c7f2  lea     ecx, [rdx+7Eh]; Locale
0x18002c7f5  call    cs:__imp_CompareStringW
0x18002c7fb  cmp     eax, 2
0x18002c7fe  jz      short loc_18002C84F
0x18002c800  mov     ecx, 3
0x18002c805  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x18002c809  lea     rax, aDc; "DC="
0x18002c810  mov     [rsp+78h+lpString2], rax; lpString2
0x18002c815  mov     r9d, ecx; cchCount1
0x18002c818  mov     r8, rdi; lpString1
0x18002c81b  lea     edx, [rcx-2]; dwCmpFlags
0x18002c81e  lea     ecx, [rdx+7Eh]; Locale
0x18002c821  call    cs:__imp_CompareStringW
0x18002c827  cmp     eax, 2
0x18002c82a  jz      short loc_18002C89F
0x18002c82c  jmp     short loc_18002C838
0x18002c82e  cmp     ax, 2Ch ; ','
0x18002c832  jz      short loc_18002C840
0x18002c834  add     rdi, 2
0x18002c838  movzx   eax, word ptr [rdi]
0x18002c83b  test    ax, ax
0x18002c83e  jnz     short loc_18002C82E
0x18002c840  cmp     word ptr [rdi], 2Ch ; ','
0x18002c844  jnz     short loc_18002C7C8
0x18002c846  add     rdi, 2
0x18002c84a  jmp     loc_18002C7C8
0x18002c84f  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18002c855  jz      short loc_18002C89F
0x18002c857  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002c85e  test    rax, rax
0x18002c861  jz      short loc_18002C879
0x18002c863  mov     r8, rbp
0x18002c866  lea     rdx, aAdddnDnSIsUnde; "AddDN: DN %s is under cn=configuration "...
0x18002c86d  mov     ecx, 4
0x18002c872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c877  jmp     short loc_18002C89F
0x18002c879  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18002c880  jz      short loc_18002C89F
0x18002c882  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002c889  jz      short loc_18002C89F
0x18002c88b  mov     r8, rbp
0x18002c88e  lea     rdx, aAdddnDnSIsUnde; "AddDN: DN %s is under cn=configuration "...
0x18002c895  mov     ecx, 4; unsigned int
0x18002c89a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002c89f  test    r14, r14
0x18002c8a2  jz      loc_18002C929
0x18002c8a8  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002c8b0  mov     rax, [r14]
0x18002c8b3  mov     [rsp+78h+lpString2], rax; lpString2
0x18002c8b8  or      r9d, 0FFFFFFFFh; cchCount1
0x18002c8bc  mov     r8, rdi; lpString1
0x18002c8bf  lea     edx, [r9+2]; dwCmpFlags
0x18002c8c3  lea     ecx, [rdx+7Eh]; Locale
0x18002c8c6  call    cs:__imp_CompareStringW
0x18002c8cc  cmp     eax, 2
0x18002c8cf  jz      short loc_18002C914
0x18002c8d1  cmp     eax, 1
0x18002c8d4  jz      short loc_18002C8DF
0x18002c8d6  mov     rsi, r14
0x18002c8d9  mov     r14, [r14+38h]
0x18002c8dd  jmp     short loc_18002C89F
0x18002c8df  mov     rcx, rdi; unsigned __int16 *
0x18002c8e2  call    ?AllocLdapQuery@@YAPEAU_LDAPQUERY@@PEBG@Z; AllocLdapQuery(ushort const *)
0x18002c8e7  mov     rdi, rax
0x18002c8ea  test    rax, rax
0x18002c8ed  jnz     short loc_18002C8F9
0x18002c8ef  call    cs:__imp_GetLastError
0x18002c8f5  mov     ebx, eax
0x18002c8f7  jmp     short loc_18002C95E
0x18002c8f9  mov     r9, r12; struct _GROUP_POLICY_OBJECTW *
0x18002c8fc  mov     r8, r13; struct _DNENTRY *
0x18002c8ff  mov     rdx, rbp; unsigned __int16 *
0x18002c902  mov     rcx, rdi; struct _LDAPQUERY *
0x18002c905  call    ?InsertDN@@YAHPEAU_LDAPQUERY@@PEBGPEAU_DNENTRY@@PEAU_GROUP_POLICY_OBJECTW@@@Z; InsertDN(_LDAPQUERY *,ushort const *,_DNENTRY *,_GROUP_POLICY_OBJECTW *)
0x18002c90a  test    eax, eax
0x18002c90c  jz      short loc_18002C94E
0x18002c90e  mov     [rdi+38h], r14
0x18002c912  jmp     short loc_18002C977
0x18002c914  mov     r9, r12; struct _GROUP_POLICY_OBJECTW *
0x18002c917  mov     r8, r13; struct _DNENTRY *
0x18002c91a  mov     rdx, rbp; unsigned __int16 *
0x18002c91d  mov     rcx, r14; struct _LDAPQUERY *
0x18002c920  call    ?InsertDN@@YAHPEAU_LDAPQUERY@@PEBGPEAU_DNENTRY@@PEAU_GROUP_POLICY_OBJECTW@@@Z; InsertDN(_LDAPQUERY *,ushort const *,_DNENTRY *,_GROUP_POLICY_OBJECTW *)
0x18002c925  mov     edi, eax
0x18002c927  jmp     short loc_18002C960
0x18002c929  mov     rcx, rdi; unsigned __int16 *
0x18002c92c  call    ?AllocLdapQuery@@YAPEAU_LDAPQUERY@@PEBG@Z; AllocLdapQuery(ushort const *)
0x18002c931  mov     rdi, rax
0x18002c934  test    rax, rax
0x18002c937  jz      short loc_18002C8EF
0x18002c939  mov     r9, r12; struct _GROUP_POLICY_OBJECTW *
0x18002c93c  mov     r8, r13; struct _DNENTRY *
0x18002c93f  mov     rdx, rbp; unsigned __int16 *
0x18002c942  mov     rcx, rax; struct _LDAPQUERY *
0x18002c945  call    ?InsertDN@@YAHPEAU_LDAPQUERY@@PEBGPEAU_DNENTRY@@PEAU_GROUP_POLICY_OBJECTW@@@Z; InsertDN(_LDAPQUERY *,ushort const *,_DNENTRY *,_GROUP_POLICY_OBJECTW *)
0x18002c94a  test    eax, eax
0x18002c94c  jnz     short loc_18002C96F
0x18002c94e  call    cs:__imp_GetLastError
0x18002c954  mov     ebx, eax
0x18002c956  mov     rcx, rdi; hMem
0x18002c959  call    ?FreeLdapQuery@@YAXPEAU_LDAPQUERY@@@Z; FreeLdapQuery(_LDAPQUERY *)
0x18002c95e  xor     edi, edi
0x18002c960  mov     ecx, ebx; dwErrCode
0x18002c962  call    cs:__imp_SetLastError
0x18002c968  mov     eax, edi
0x18002c96a  jmp     loc_18002C9F9
0x18002c96f  mov     qword ptr [rdi+38h], 0
0x18002c977  test    rsi, rsi
0x18002c97a  jnz     short loc_18002C981
0x18002c97c  mov     [r15], rdi
0x18002c97f  jmp     short loc_18002C985
0x18002c981  mov     [rsi+38h], rdi
0x18002c985  mov     ecx, ebx; dwErrCode
0x18002c987  call    cs:__imp_SetLastError
0x18002c98d  mov     eax, 1
0x18002c992  jmp     short loc_18002C9F9
0x18002c994  mov     ebx, 0Dh
0x18002c999  mov     [rsp+78h+arg_0], ebx
0x18002c9a0  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18002c9a6  jz      short loc_18002C9EF
0x18002c9a8  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002c9af  test    rax, rax
0x18002c9b2  jz      short loc_18002C9C8
0x18002c9b4  mov     r8, rbp
0x18002c9b7  lea     rdx, aAdddnDomainNot; "AddDN: Domain not found for <%s>. Exiti"...
0x18002c9be  lea     ecx, [rbx-0Bh]
0x18002c9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9c6  jmp     short loc_18002C9EF
0x18002c9c8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18002c9cf  jz      short loc_18002C9EF
0x18002c9d1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002c9d8  jz      short loc_18002C9EF
0x18002c9da  mov     r8, rbp
0x18002c9dd  lea     rdx, aAdddnDomainNot; "AddDN: Domain not found for <%s>. Exiti"...
0x18002c9e4  mov     ecx, 2; unsigned int
0x18002c9e9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002c9ee  nop
0x18002c9ef  mov     ecx, ebx; dwErrCode
0x18002c9f1  call    cs:__imp_SetLastError
0x18002c9f7  xor     eax, eax
0x18002c9f9  add     rsp, 38h
0x18002c9fd  pop     r15
0x18002c9ff  pop     r14
0x18002ca01  pop     r13
0x18002ca03  pop     r12
0x18002ca05  pop     rdi
0x18002ca06  pop     rsi
0x18002ca07  pop     rbp
0x18002ca08  pop     rbx
0x18002ca09  retn
```
