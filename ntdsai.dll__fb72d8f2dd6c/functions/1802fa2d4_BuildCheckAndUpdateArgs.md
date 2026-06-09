# BuildCheckAndUpdateArgs

- ea: `0x1802fa2d4`
- end: `0x1802fac9c`
- name: `BuildCheckAndUpdateArgs`
- size: `2504`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1802fb900`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x180021aa3`
- `0x18002a0bc`
- `0x18016ae88`
- `0x1802fa2d4`
- `0x1802fe968`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1802fa4a8`
- `RPCRT4!RpcRevertToSelf` at `0x1802fa4a8`
- `RPCRT4!RpcImpersonateClient` at `0x1802fa436`
- `RPCRT4!RpcImpersonateClient` at `0x1802fa436`
- `WLDAP32!__imp_ldap_unbind` at `0x1802fab65`
- `WLDAP32!__imp_ldap_unbind` at `0x180470078`
- `WLDAP32!__imp_ldap_unbind` at `0x1802fab65`
- `WLDAP32!__imp_ldap_unbind` at `0x180470078`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1802fa40b`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1802fa40b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1802fa611`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1802fa611`
- `WLDAP32!__imp_ldap_first_entry` at `0x1802fa633`
- `WLDAP32!__imp_ldap_first_entry` at `0x1802fa633`
- `WLDAP32!__imp_ldap_msgfree` at `0x1802fabcf`
- `WLDAP32!__imp_ldap_msgfree` at `0x1804700ea`
- `WLDAP32!__imp_ldap_msgfree` at `0x1802fabcf`
- `WLDAP32!__imp_ldap_msgfree` at `0x1804700ea`
- `WLDAP32!__imp_ldap_bind_sW` at `0x1802fa47a`
- `WLDAP32!__imp_ldap_bind_sW` at `0x1802fa47a`
- `WLDAP32!__imp_ldap_count_values_len` at `0x1802fa667`
- `WLDAP32!__imp_ldap_count_values_len` at `0x1802fa667`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1802fabbc`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1804700d7`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1802fabbc`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1804700d7`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1802fa651`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1802fa651`
- `WLDAP32!__imp_ldap_initW` at `0x1802fa38b`
- `WLDAP32!__imp_ldap_initW` at `0x1802fa38b`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x1802fa605`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x1802fa605`
- `WLDAP32!__imp_ldap_set_option` at `0x1802fa3b3`
- `WLDAP32!__imp_ldap_set_option` at `0x1802fa3d1`
- `WLDAP32!__imp_ldap_set_option` at `0x1802fa3ef`
- `WLDAP32!__imp_ldap_set_option` at `0x1802fa3b3`
- `WLDAP32!__imp_ldap_set_option` at `0x1802fa3d1`
- `WLDAP32!__imp_ldap_set_option` at `0x1802fa3ef`
- `ntdll!RtlFreeHeap` at `0x1802fa7ae`
- `ntdll!RtlFreeHeap` at `0x1802fab86`
- `ntdll!RtlFreeHeap` at `0x180470099`
- `ntdll!RtlFreeHeap` at `0x1802fa7ae`
- `ntdll!RtlFreeHeap` at `0x1802fab86`
- `ntdll!RtlFreeHeap` at `0x180470099`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1802fa6d9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1802fa7d7`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1802fa6d9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1802fa7d7`
- `ntdll!RtlNtStatusToDosError` at `0x1802fa6e5`
- `ntdll!RtlNtStatusToDosError` at `0x1802fa7e5`
- `ntdll!RtlNtStatusToDosError` at `0x1802fa6e5`
- `ntdll!RtlNtStatusToDosError` at `0x1802fa7e5`
- `ntdll!RtlLengthSid` at `0x1802fa4b6`
- `ntdll!RtlLengthSid` at `0x1802fa934`
- `ntdll!RtlLengthSid` at `0x1802faaa5`
- `ntdll!RtlLengthSid` at `0x1802fa4b6`
- `ntdll!RtlLengthSid` at `0x1802fa934`
- `ntdll!RtlLengthSid` at `0x1802faaa5`

## string_xrefs

- `0x1802fa512`: `<SID=`
- `0x1802fa327`: `sidHistory`

## pseudocode

```c
__int64 BuildCheckAndUpdateArgs(__int64 a1, int a2, WCHAR *a3, ...)
{
  size_t v4; // rbx
  LDAP *v5; // r14
  ULONG v6; // edi
  ULONG v7; // r13d
  void ***v8; // r12
  _DWORD *v9; // rsi
  LDAP *v10; // rax
  size_t *v11; // r8
  int v12; // r9d
  int v13; // ebx
  RPC_STATUS v14; // eax
  WCHAR *v15; // r8
  WCHAR *v16; // rax
  __int64 v17; // r11
  _WORD *v18; // r11
  unsigned int v19; // r9d
  unsigned int v20; // r10d
  __int16 v21; // r8
  __int16 v22; // cx
  _WORD *v23; // r11
  ULONG v24; // eax
  struct berval **values_lenW; // rax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  void *v29; // rcx
  int v30; // eax
  __int64 v31; // rax
  _DWORD *v32; // rax
  __int64 *v33; // rbx
  __int64 v34; // rbx
  __int64 *v35; // rbx
  __int64 v36; // rbx
  __int64 v37; // rdx
  _DWORD *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rcx
  _DWORD *v41; // r14
  void *v42; // rdx
  __int64 *v43; // rbx
  size_t *v44; // rsi
  struct _UNICODE_STRING UnicodeString; // [rsp+A8h] [rbp-90h] BYREF
  ULONG v47; // [rsp+B8h] [rbp-80h]
  PWSTR base; // [rsp+C0h] [rbp-78h]
  struct berval **vals; // [rsp+C8h] [rbp-70h]
  PLDAPMessage Message; // [rsp+D0h] [rbp-68h] BYREF
  int invalue; // [rsp+D8h] [rbp-60h] BYREF
  size_t v52; // [rsp+E0h] [rbp-58h]
  _WORD *v53; // [rsp+E8h] [rbp-50h]
  LDAP *v54; // [rsp+F0h] [rbp-48h]
  size_t v55; // [rsp+F8h] [rbp-40h]
  PWSTR attr[2]; // [rsp+100h] [rbp-38h] BYREF
  __int64 v57; // [rsp+158h] [rbp+20h] BYREF
  va_list va; // [rsp+158h] [rbp+20h]
  PWCHAR cred; // [rsp+160h] [rbp+28h]
  PSID Sid; // [rsp+168h] [rbp+30h]
  __int64 v61; // [rsp+170h] [rbp+38h] BYREF
  va_list va1; // [rsp+170h] [rbp+38h]
  __int64 v63; // [rsp+178h] [rbp+40h]
  _DWORD *v64; // [rsp+180h] [rbp+48h]
  void ***v65; // [rsp+188h] [rbp+50h]
  __int64 *v66; // [rsp+190h] [rbp+58h]
  size_t *v67; // [rsp+198h] [rbp+60h]
  size_t Size; // [rsp+1A0h] [rbp+68h]
  _DWORD *v69; // [rsp+1A8h] [rbp+70h]
  va_list va2; // [rsp+1B0h] [rbp+78h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v57 = va_arg(va1, _QWORD);
  cred = va_arg(va1, PWCHAR);
  Sid = va_arg(va1, PSID);
  va_copy(va2, va1);
  v61 = va_arg(va2, _QWORD);
  v63 = va_arg(va2, _QWORD);
  v64 = va_arg(va2, _DWORD *);
  v65 = va_arg(va2, void ***);
  v66 = va_arg(va2, __int64 *);
  v67 = va_arg(va2, size_t *);
  Size = va_arg(va2, _QWORD);
  v69 = va_arg(va2, _DWORD *);
  LODWORD(v4) = 0;
  v5 = 0;
  v54 = 0;
  v6 = 0;
  invalue = 3;
  LODWORD(v61) = 1;
  *(_QWORD *)&UnicodeString.Length = 0;
  UnicodeString.Buffer = 0;
  base = 0;
  attr[0] = L"sidHistory";
  attr[1] = 0;
  Message = 0;
  vals = 0;
  v7 = 0;
  v47 = 0;
  *v64 = 0;
  v8 = v65;
  *v65 = 0;
  *v66 = 0;
  *v67 = 0;
  v9 = (_DWORD *)Size;
  *(_DWORD *)Size = 0;
  if ( a2 )
  {
    v10 = ldap_initW(a3, 0x185u);
    v5 = v10;
    v54 = v10;
    if ( !v10
      || ldap_set_option(v10, 17, &invalue)
      || ldap_set_option(v5, 149, va1)
      || ldap_set_option(v5, 152, va1)
      || ldap_set_optionW(v5, 59, va) )
    {
      v6 = 8207;
      *v9 = 18484464;
      goto LABEL_63;
    }
    v13 = v63;
    if ( (_DWORD)v63 )
    {
      AssignAuthzClientContext(a1 + 5960, 0);
      v14 = RpcImpersonateClient(0);
      if ( v14 )
      {
        v6 = v14;
        *v9 = 18484473;
        goto LABEL_62;
      }
      *v69 = 1;
    }
    v15 = 0;
    if ( !v13 )
      v15 = cred;
    LODWORD(v4) = 0;
    if ( ldap_bind_sW(v5, 0, v15, 0x486u) )
    {
      v6 = 8233;
      *v9 = 18484484;
      goto LABEL_63;
    }
    if ( *v69 )
    {
      *v69 = 0;
      RpcRevertToSelf();
    }
    LODWORD(Size) = RtlLengthSid(Sid);
    v4 = (unsigned int)(2 * Size) + 7LL;
    v16 = (WCHAR *)THAlloc_(a1, 1, 2 * (int)v4, 1, 0, 18484500);
    base = v16;
    if ( !v16 )
    {
      v6 = 8;
      *v9 = 18484502;
      goto LABEL_62;
    }
    StringCchCopyW(v16, v4, L"<SID=");
    v18 = (_WORD *)(v17 + 10);
    v53 = v18;
    LODWORD(v4) = 0;
    v19 = 0;
    v20 = Size;
    while ( v19 < v20 )
    {
      v21 = *((_BYTE *)Sid + v19) & 0xF;
      v22 = *((_BYTE *)Sid + v19) >> 4;
      *v18 = v22 + ((unsigned __int8)v22 < 0xAu ? 48 : 55);
      v23 = v18 + 1;
      *v23 = v21 + ((unsigned __int8)v21 < 0xAu ? 48 : 55);
      v18 = v23 + 1;
      v53 = v18;
      ++v19;
    }
    *v18 = 62;
    v24 = ldap_search_ext_sW(v5, base, 0, (const PWSTR)L"objectClass=*", attr, 0, 0, 0, 0, 0x2710u, &Message);
    if ( v24 )
    {
      v6 = LdapMapErrorToWin32(v24);
      *v9 = 18484522;
      goto LABEL_63;
    }
    if ( ldap_first_entry(v5, Message) )
    {
      values_lenW = ldap_get_values_lenW(v5, Message, attr[0]);
      vals = values_lenW;
      if ( values_lenW )
      {
        v7 = ldap_count_values_len(values_lenW);
        v47 = v7;
      }
    }
  }
  v26 = THAlloc_(a1, 1, 8 * (v7 + 1), 1, 0, 18484545);
  *v8 = (void **)v26;
  if ( !v26 )
  {
    v6 = 8;
    *v9 = 18484547;
    goto LABEL_63;
  }
  v27 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( v27 < 0 )
  {
    v6 = RtlNtStatusToDosError(v27);
    *v9 = 18484556;
    goto LABEL_63;
  }
  v28 = -1;
  do
    ++v28;
  while ( UnicodeString.Buffer[v28] );
  Size = (unsigned int)(2 * v28 + 2);
  v4 = (size_t)*v8;
  *(_QWORD *)v4 = THAlloc_(a1, 1, 2 * (int)v28 + 2, 1, 0, 18484561);
  v29 = **v8;
  LODWORD(v4) = 0;
  if ( !v29 )
  {
    v6 = 8;
    *v9 = 18484563;
    goto LABEL_63;
  }
  while ( 1 )
  {
    memcpy_0(v29, UnicodeString.Buffer, Size);
    ++*v64;
    if ( (unsigned int)v4 >= v7 )
      break;
    if ( UnicodeString.Buffer )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UnicodeString.Buffer);
      UnicodeString.Buffer = 0;
    }
    v30 = RtlConvertSidToUnicodeString(&UnicodeString, vals[(unsigned int)v4]->bv_val, 1u);
    if ( v30 < 0 )
    {
      v6 = RtlNtStatusToDosError(v30);
      *v9 = 18484581;
      goto LABEL_62;
    }
    v31 = -1;
    do
      ++v31;
    while ( UnicodeString.Buffer[v31] );
    Size = (unsigned int)(2 * v31 + 2);
    v4 = (unsigned int)(v4 + 1);
    (*v8)[v4] = (void *)THAlloc_(a1, 1, 2 * (int)v31 + 2, 1, 0, 18484586);
    v29 = (*v8)[v4];
    if ( !v29 )
    {
      v6 = 8;
      *v9 = 18484588;
      goto LABEL_62;
    }
  }
  v32 = (_DWORD *)THAlloc_(a1, 1, 96, 1, 0, 18484597);
  v33 = v66;
  *v66 = (__int64)v32;
  if ( v32 )
  {
    *v32 = 589970;
    v34 = *v33;
    *(_QWORD *)(v34 + 16) = THAlloc_(a1, 1, 16, 1, 0, 18484604);
    v35 = v66;
    if ( *(_QWORD *)(*v66 + 16) )
    {
      *(_DWORD *)(*v66 + 8) = 1;
      LODWORD(Size) = RtlLengthSid(Sid);
      v52 = (unsigned int)Size;
      v36 = *(_QWORD *)(*v35 + 16);
      *(_QWORD *)(v36 + 8) = THAlloc_(a1, 1, Size, 1, 0, 18484612);
      v4 = (size_t)v66;
      v37 = *(_QWORD *)(*v66 + 16);
      if ( *(_QWORD *)(v37 + 8) )
      {
        *(_DWORD *)v37 = Size;
        memcpy_0(*(void **)(*(_QWORD *)(*(_QWORD *)v4 + 16LL) + 8LL), Sid, v52);
        LODWORD(v4) = 0;
        if ( !v7 )
          goto LABEL_63;
        v38 = (_DWORD *)THAlloc_(a1, 1, 96, 1, 0, 18484623);
        v11 = v67;
        *v67 = (size_t)v38;
        if ( !v38 )
        {
          v6 = 8;
          *v9 = 18484625;
          goto LABEL_63;
        }
        *v38 = 590433;
        v4 = *v11;
        *(_QWORD *)(v4 + 16) = THAlloc_(a1, 1, 16 * v7, 1, 0, 18484632);
        LODWORD(v4) = 0;
        if ( !*(_QWORD *)(*v67 + 16) )
        {
          v6 = 8;
          *v9 = 18484634;
          goto LABEL_63;
        }
        *(_DWORD *)(*v67 + 8) = v7;
        while ( (unsigned int)v4 < v7 )
        {
          v52 = (size_t)&vals[(unsigned int)v4];
          LODWORD(Size) = RtlLengthSid(*(PSID *)(*(_QWORD *)v52 + 8LL));
          v55 = (unsigned int)Size;
          v39 = THAlloc_(a1, 1, Size, 1, 0, 18484642);
          v11 = v67;
          *(_QWORD *)(*(_QWORD *)(*v67 + 16) + 16LL * (unsigned int)v4 + 8) = v39;
          v40 = *(_QWORD *)(*v11 + 16);
          if ( !*(_QWORD *)(v40 + 16LL * (unsigned int)v4 + 8) )
          {
            v6 = 8;
            *v9 = 18484644;
            break;
          }
          *(_DWORD *)(v40 + 16LL * (unsigned int)v4) = Size;
          memcpy_0(
            *(void **)(*(_QWORD *)(*v11 + 16) + 16LL * (unsigned int)v4 + 8),
            *(const void **)(*(_QWORD *)v52 + 8LL),
            v55);
          LODWORD(v4) = v4 + 1;
          v7 = v47;
        }
      }
      else
      {
        v6 = 8;
        *v9 = 18484614;
      }
    }
    else
    {
      v6 = 8;
      *v9 = 18484606;
    }
  }
  else
  {
    v6 = 8;
    *v9 = 18484599;
  }
LABEL_62:
  LODWORD(v4) = 0;
LABEL_63:
  if ( v5 )
    ldap_unbind(v5);
  if ( UnicodeString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UnicodeString.Buffer);
  if ( base )
    THFreeAux(a1, (_DWORD)base, (_DWORD)v11, v12, 18484665);
  if ( vals )
    ldap_value_free_len(vals);
  if ( Message )
    ldap_msgfree(Message);
  if ( v6 )
  {
    v41 = v64;
    if ( *v8 )
    {
      if ( *v64 )
      {
        do
        {
          v42 = (*v8)[(unsigned int)v4];
          if ( v42 )
          {
            THFreeAux(a1, (_DWORD)v42, (_DWORD)v11, v12, 18484681);
            (*v8)[(unsigned int)v4] = 0;
          }
          LODWORD(v4) = v4 + 1;
        }
        while ( (unsigned int)v4 < *v41 );
      }
      if ( *v8 )
        THFreeAux(a1, (unsigned int)*v8, (_DWORD)v11, v12, 18484684);
      *v8 = 0;
    }
    v43 = v66;
    THFreeATTR(a1, *v66, 1);
    v44 = v67;
    THFreeATTR(a1, *v67, 1);
    *v41 = 0;
    *v8 = 0;
    *v43 = 0;
    *v44 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1802fa2d4  mov     r11, rsp
0x1802fa2d7  mov     [r11+10h], rbx
0x1802fa2db  mov     [r11+18h], rsi
0x1802fa2df  mov     [r11+20h], r9
0x1802fa2e3  mov     [r11+8], rcx
0x1802fa2e7  push    rdi
0x1802fa2e8  push    r12
0x1802fa2ea  push    r13
0x1802fa2ec  push    r14
0x1802fa2ee  push    r15
0x1802fa2f0  sub     rsp, 0D0h
0x1802fa2f7  mov     r15, rcx
0x1802fa2fa  xor     ebx, ebx
0x1802fa2fc  mov     r14d, ebx
0x1802fa2ff  mov     [r11-48h], rbx
0x1802fa303  mov     edi, ebx
0x1802fa305  mov     [rsp+0F8h+var_98], ebx
0x1802fa309  mov     dword ptr [r11-60h], 3
0x1802fa311  mov     dword ptr [r11+38h], 1
0x1802fa319  mov     qword ptr [rsp+0F8h+UnicodeString.Length], rbx
0x1802fa31e  mov     [rsp+0F8h+UnicodeString.Buffer], rbx
0x1802fa323  mov     [r11-78h], rbx
0x1802fa327  lea     rax, aSidhistory; "sidHistory"
0x1802fa32e  mov     [r11-38h], rax
0x1802fa332  mov     [r11-30h], rbx
0x1802fa336  mov     [r11-68h], rbx
0x1802fa33a  mov     [r11-70h], rbx
0x1802fa33e  mov     r13d, ebx
0x1802fa341  mov     [rsp+0F8h+var_80], ebx
0x1802fa345  mov     rax, [rsp+0F8h+arg_40]
0x1802fa34d  mov     [rax], ebx
0x1802fa34f  mov     r12, [rsp+0F8h+arg_48]
0x1802fa357  mov     [r12], rbx
0x1802fa35b  mov     rax, [rsp+0F8h+arg_50]
0x1802fa363  mov     [rax], rbx
0x1802fa366  mov     rax, [rsp+0F8h+arg_58]
0x1802fa36e  mov     [rax], rbx
0x1802fa371  mov     rsi, [rsp+0F8h+Size]
0x1802fa379  mov     [rsi], ebx
0x1802fa37b  test    edx, edx
0x1802fa37d  jz      loc_1802FA674
0x1802fa383  mov     edx, 185h; PortNumber
0x1802fa388  mov     rcx, r8; HostName
0x1802fa38b  call    cs:__imp_ldap_initW
0x1802fa391  mov     r14, rax
0x1802fa394  mov     [rsp+0F8h+var_48], rax
0x1802fa39c  test    rax, rax
0x1802fa39f  jz      loc_1802FA6B5
0x1802fa3a5  lea     r8, [rsp+0F8h+invalue]; invalue
0x1802fa3ad  lea     edx, [rbx+11h]; option
0x1802fa3b0  mov     rcx, rax; ld
0x1802fa3b3  call    cs:__imp_ldap_set_option
0x1802fa3b9  test    eax, eax
0x1802fa3bb  jnz     loc_1802FA6B5
0x1802fa3c1  lea     r8, [rsp+0F8h+arg_30]; invalue
0x1802fa3c9  mov     edx, 95h; option
0x1802fa3ce  mov     rcx, r14; ld
0x1802fa3d1  call    cs:__imp_ldap_set_option
0x1802fa3d7  test    eax, eax
0x1802fa3d9  jnz     loc_1802FA6B5
0x1802fa3df  lea     r8, [rsp+0F8h+arg_30]; invalue
0x1802fa3e7  mov     edx, 98h; option
0x1802fa3ec  mov     rcx, r14; ld
0x1802fa3ef  call    cs:__imp_ldap_set_option
0x1802fa3f5  test    eax, eax
0x1802fa3f7  jnz     loc_1802FA6B5
0x1802fa3fd  lea     r8, [rsp+0F8h+arg_18]; invalue
0x1802fa405  lea     edx, [rbx+3Bh]; option
0x1802fa408  mov     rcx, r14; ld
0x1802fa40b  call    cs:__imp_ldap_set_optionW
0x1802fa411  test    eax, eax
0x1802fa413  jnz     loc_1802FA6B5
0x1802fa419  mov     ebx, dword ptr [rsp+0F8h+arg_38]
0x1802fa420  xor     eax, eax
0x1802fa422  test    ebx, ebx
0x1802fa424  jz      short loc_1802FA461
0x1802fa426  lea     rcx, [r15+1748h]
0x1802fa42d  xor     edx, edx
0x1802fa42f  call    AssignAuthzClientContext
0x1802fa434  xor     ecx, ecx; BindingHandle
0x1802fa436  call    cs:__imp_RpcImpersonateClient
0x1802fa43c  test    eax, eax
0x1802fa43e  jz      short loc_1802FA451
0x1802fa440  mov     edi, eax
0x1802fa442  mov     [rsp+0F8h+var_98], eax
0x1802fa446  mov     dword ptr [rsi], 11A0CF9h
0x1802fa44c  jmp     loc_1802FAB5B
0x1802fa451  mov     rax, [rsp+0F8h+arg_68]
0x1802fa459  mov     dword ptr [rax], 1
0x1802fa45f  xor     eax, eax
0x1802fa461  mov     r8, rax
0x1802fa464  test    ebx, ebx
0x1802fa466  cmovz   r8, [rsp+0F8h+cred]; cred
0x1802fa46f  xor     edx, edx; dn
0x1802fa471  mov     r9d, 486h; method
0x1802fa477  mov     rcx, r14; ld
0x1802fa47a  call    cs:__imp_ldap_bind_sW
0x1802fa480  xor     ebx, ebx
0x1802fa482  test    eax, eax
0x1802fa484  jz      short loc_1802FA49A
0x1802fa486  mov     edi, 2029h
0x1802fa48b  mov     [rsp+0F8h+var_98], edi
0x1802fa48f  mov     dword ptr [rsi], 11A0D04h
0x1802fa495  jmp     loc_1802FAB5D
0x1802fa49a  mov     rax, [rsp+0F8h+arg_68]
0x1802fa4a2  cmp     [rax], ebx
0x1802fa4a4  jz      short loc_1802FA4AE
0x1802fa4a6  mov     [rax], ebx
0x1802fa4a8  call    cs:__imp_RpcRevertToSelf
0x1802fa4ae  mov     rcx, [rsp+0F8h+Sid]; Sid
0x1802fa4b6  call    cs:__imp_RtlLengthSid
0x1802fa4bc  mov     dword ptr [rsp+0F8h+Size], eax
0x1802fa4c3  lea     ebx, [rax+rax]
0x1802fa4c6  add     rbx, 7
0x1802fa4ca  lea     r8, [rbx+rbx]
0x1802fa4ce  mov     [rsp+0F8h+attrsonly], 11A0D14h
0x1802fa4d6  mov     dword ptr [rsp+0F8h+attrs], 0
0x1802fa4de  mov     eax, 1
0x1802fa4e3  mov     r9d, eax
0x1802fa4e6  mov     edx, eax
0x1802fa4e8  mov     rcx, r15
0x1802fa4eb  call    THAlloc_
0x1802fa4f0  mov     r11, rax
0x1802fa4f3  mov     [rsp+0F8h+base], rax
0x1802fa4fb  test    rax, rax
0x1802fa4fe  jnz     short loc_1802FA512
0x1802fa500  lea     edi, [rax+8]
0x1802fa503  mov     [rsp+0F8h+var_98], edi
0x1802fa507  mov     dword ptr [rsi], 11A0D16h
0x1802fa50d  jmp     loc_1802FAB5B
0x1802fa512  lea     r8, aSid_2; "<SID="
0x1802fa519  mov     rdx, rbx; cchDest
0x1802fa51c  mov     rcx, r11; pszDest
0x1802fa51f  call    StringCchCopyW
0x1802fa524  add     r11, 0Ah
0x1802fa528  mov     [rsp+0F8h+var_50], r11
0x1802fa530  xor     ebx, ebx
0x1802fa532  mov     r9d, ebx
0x1802fa535  mov     [rsp+0F8h+var_94], ebx
0x1802fa539  mov     r10d, dword ptr [rsp+0F8h+Size]
0x1802fa541  cmp     r9d, r10d
0x1802fa544  jnb     short loc_1802FA5B2
0x1802fa546  mov     ecx, r9d
0x1802fa549  mov     rax, [rsp+0F8h+Sid]
0x1802fa551  mov     dl, [rcx+rax]
0x1802fa554  mov     al, dl
0x1802fa556  and     al, 0Fh
0x1802fa558  movzx   r8d, al
0x1802fa55c  shr     dl, 4
0x1802fa55f  movzx   ecx, dl
0x1802fa562  cmp     cl, 0Ah
0x1802fa565  sbb     ax, ax
0x1802fa568  mov     dx, 0FFF9h
0x1802fa56c  and     ax, dx
0x1802fa56f  add     ax, 37h ; '7'
0x1802fa573  add     ax, cx
0x1802fa576  mov     [r11], ax
0x1802fa57a  add     r11, 2
0x1802fa57e  mov     [rsp+0F8h+var_50], r11
0x1802fa586  cmp     r8b, 0Ah
0x1802fa58a  sbb     ax, ax
0x1802fa58d  and     ax, dx
0x1802fa590  add     ax, 37h ; '7'
0x1802fa594  add     ax, r8w
0x1802fa598  mov     [r11], ax
0x1802fa59c  add     r11, 2
0x1802fa5a0  mov     [rsp+0F8h+var_50], r11
0x1802fa5a8  inc     r9d
0x1802fa5ab  mov     [rsp+0F8h+var_94], r9d
0x1802fa5b0  jmp     short loc_1802FA541
0x1802fa5b2  mov     eax, 3Eh ; '>'
0x1802fa5b7  mov     [r11], ax
0x1802fa5bb  lea     rax, [rsp+0F8h+Message]
0x1802fa5c3  mov     [rsp+0F8h+res], rax; res
0x1802fa5c8  mov     [rsp+0F8h+SizeLimit], 2710h; SizeLimit
0x1802fa5d0  mov     [rsp+0F8h+timeout], rbx; timeout
0x1802fa5d5  mov     [rsp+0F8h+ClientControls], rbx; ClientControls
0x1802fa5da  mov     [rsp+0F8h+ServerControls], rbx; ServerControls
0x1802fa5df  mov     [rsp+0F8h+attrsonly], ebx; attrsonly
0x1802fa5e3  lea     rax, [rsp+0F8h+attr]
0x1802fa5eb  mov     [rsp+0F8h+attrs], rax; attrs
0x1802fa5f0  lea     r9, aObjectclass_2; "objectClass=*"
0x1802fa5f7  xor     r8d, r8d; scope
0x1802fa5fa  mov     rdx, [rsp+0F8h+base]; base
0x1802fa602  mov     rcx, r14; ld
0x1802fa605  call    cs:__imp_ldap_search_ext_sW
0x1802fa60b  test    eax, eax
0x1802fa60d  jz      short loc_1802FA628
0x1802fa60f  mov     ecx, eax; LdapError
0x1802fa611  call    cs:__imp_LdapMapErrorToWin32
0x1802fa617  mov     edi, eax
0x1802fa619  mov     [rsp+0F8h+var_98], eax
0x1802fa61d  mov     dword ptr [rsi], 11A0D2Ah
0x1802fa623  jmp     loc_1802FAB5D
0x1802fa628  mov     rdx, [rsp+0F8h+Message]; res
0x1802fa630  mov     rcx, r14; ld
0x1802fa633  call    cs:__imp_ldap_first_entry
0x1802fa639  test    rax, rax
0x1802fa63c  jz      short loc_1802FA674
0x1802fa63e  mov     r8, [rsp+0F8h+attr]; attr
0x1802fa646  mov     rdx, [rsp+0F8h+Message]; Message
0x1802fa64e  mov     rcx, r14; ExternalHandle
0x1802fa651  call    cs:__imp_ldap_get_values_lenW
0x1802fa657  mov     [rsp+0F8h+vals], rax
0x1802fa65f  test    rax, rax
0x1802fa662  jz      short loc_1802FA674
0x1802fa664  mov     rcx, rax; vals
0x1802fa667  call    cs:__imp_ldap_count_values_len
0x1802fa66d  mov     r13d, eax
0x1802fa670  mov     [rsp+0F8h+var_80], eax
0x1802fa674  lea     r8d, [r13+1]
0x1802fa678  shl     r8, 3
0x1802fa67c  mov     [rsp+0F8h+attrsonly], 11A0D41h
0x1802fa684  mov     dword ptr [rsp+0F8h+attrs], ebx
0x1802fa688  mov     eax, 1
0x1802fa68d  mov     r9d, eax
0x1802fa690  mov     edx, eax
0x1802fa692  mov     rcx, r15
0x1802fa695  call    THAlloc_
0x1802fa69a  mov     [r12], rax
0x1802fa69e  test    rax, rax
0x1802fa6a1  jnz     short loc_1802FA6C9
0x1802fa6a3  lea     edi, [rax+8]
0x1802fa6a6  mov     [rsp+0F8h+var_98], edi
0x1802fa6aa  mov     dword ptr [rsi], 11A0D43h
0x1802fa6b0  jmp     loc_1802FAB5D
0x1802fa6b5  mov     edi, 200Fh
0x1802fa6ba  mov     [rsp+0F8h+var_98], edi
0x1802fa6be  mov     dword ptr [rsi], 11A0CF0h
0x1802fa6c4  jmp     loc_1802FAB5D
0x1802fa6c9  mov     r8b, 1; AllocateDestinationString
0x1802fa6cc  mov     rdx, [rsp+0F8h+Sid]; Sid
0x1802fa6d4  lea     rcx, [rsp+0F8h+UnicodeString]; UnicodeString
0x1802fa6d9  call    cs:__imp_RtlConvertSidToUnicodeString
0x1802fa6df  test    eax, eax
0x1802fa6e1  jns     short loc_1802FA6FC
0x1802fa6e3  mov     ecx, eax; Status
0x1802fa6e5  call    cs:__imp_RtlNtStatusToDosError
0x1802fa6eb  mov     edi, eax
0x1802fa6ed  mov     [rsp+0F8h+var_98], eax
0x1802fa6f1  mov     dword ptr [rsi], 11A0D4Ch
0x1802fa6f7  jmp     loc_1802FAB5D
0x1802fa6fc  mov     rcx, [rsp+0F8h+UnicodeString.Buffer]
0x1802fa701  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802fa705  inc     rax
0x1802fa708  cmp     [rcx+rax*2], bx
0x1802fa70c  jnz     short loc_1802FA705
0x1802fa70e  lea     eax, ds:2[rax*2]
0x1802fa715  mov     [rsp+0F8h+Size], rax
0x1802fa71d  mov     rbx, [r12]
0x1802fa721  mov     [rsp+0F8h+attrsonly], 11A0D51h
0x1802fa729  mov     dword ptr [rsp+0F8h+attrs], 0
0x1802fa731  mov     ecx, 1
0x1802fa736  mov     r9d, ecx
0x1802fa739  mov     r8d, eax
0x1802fa73c  mov     edx, ecx
0x1802fa73e  mov     rcx, r15
0x1802fa741  call    THAlloc_
0x1802fa746  mov     [rbx], rax
0x1802fa749  mov     rax, [r12]
0x1802fa74d  mov     rcx, [rax]; void *
0x1802fa750  xor     ebx, ebx
0x1802fa752  test    rcx, rcx
0x1802fa755  jnz     short loc_1802FA769
0x1802fa757  lea     edi, [rcx+8]
0x1802fa75a  mov     [rsp+0F8h+var_98], edi
0x1802fa75e  mov     dword ptr [rsi], 11A0D53h
0x1802fa764  jmp     loc_1802FAB5D
0x1802fa769  mov     r8, [rsp+0F8h+Size]; Size
0x1802fa771  mov     rdx, [rsp+0F8h+UnicodeString.Buffer]; Src
0x1802fa776  call    memcpy_0
0x1802fa77b  mov     rax, [rsp+0F8h+arg_40]
0x1802fa783  inc     dword ptr [rax]
0x1802fa785  mov     [rsp+0F8h+var_94], ebx
0x1802fa789  cmp     ebx, r13d
0x1802fa78c  jnb     loc_1802FA888
0x1802fa792  cmp     [rsp+0F8h+UnicodeString.Buffer], 0
0x1802fa798  jz      short loc_1802FA7BD
0x1802fa79a  mov     rcx, gs:60h
0x1802fa7a3  mov     r8, [rsp+0F8h+UnicodeString.Buffer]; P
0x1802fa7a8  xor     edx, edx; Flags
0x1802fa7aa  mov     rcx, [rcx+30h]; HeapHandle
0x1802fa7ae  call    cs:__imp_RtlFreeHeap
0x1802fa7b4  mov     [rsp+0F8h+UnicodeString.Buffer], 0
0x1802fa7bd  mov     eax, ebx
0x1802fa7bf  mov     rcx, [rsp+0F8h+vals]
0x1802fa7c7  mov     rdx, [rcx+rax*8]
0x1802fa7cb  mov     r8b, 1; AllocateDestinationString
0x1802fa7ce  mov     rdx, [rdx+8]; Sid
0x1802fa7d2  lea     rcx, [rsp+0F8h+UnicodeString]; UnicodeString
0x1802fa7d7  call    cs:__imp_RtlConvertSidToUnicodeString
0x1802fa7dd  xor     edx, edx
0x1802fa7df  test    eax, eax
0x1802fa7e1  jns     short loc_1802FA7FC
0x1802fa7e3  mov     ecx, eax; Status
0x1802fa7e5  call    cs:__imp_RtlNtStatusToDosError
0x1802fa7eb  mov     edi, eax
0x1802fa7ed  mov     [rsp+0F8h+var_98], eax
0x1802fa7f1  mov     dword ptr [rsi], 11A0D65h
0x1802fa7f7  jmp     loc_1802FAB5B
  ... truncated ...
```
