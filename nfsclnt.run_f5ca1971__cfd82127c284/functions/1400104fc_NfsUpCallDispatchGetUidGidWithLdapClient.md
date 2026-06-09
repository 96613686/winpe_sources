# NfsUpCallDispatchGetUidGidWithLdapClient

- ea: `0x1400104fc`
- end: `0x140010a14`
- name: `NfsUpCallDispatchGetUidGidWithLdapClient`
- size: `1304`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400072b8`

## callees

- `0x1400104fc`
- `0x140017b10`
- `0x140017c6c`
- `0x14001830e`
- `0x140018350`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14001076b`
- `ADVAPI32!EventWrite` at `0x1400108dd`
- `ADVAPI32!EventWrite` at `0x140010999`
- `ADVAPI32!EventWrite` at `0x14001076b`
- `ADVAPI32!EventWrite` at `0x1400108dd`
- `ADVAPI32!EventWrite` at `0x140010999`
- `ADVAPI32!EventEnabled` at `0x140010749`
- `ADVAPI32!EventEnabled` at `0x1400108bb`
- `ADVAPI32!EventEnabled` at `0x140010977`
- `ADVAPI32!EventEnabled` at `0x140010749`
- `ADVAPI32!EventEnabled` at `0x1400108bb`
- `ADVAPI32!EventEnabled` at `0x140010977`
- `msvcrt!_wtoi` at `0x140010866`
- `msvcrt!_wtoi` at `0x140010925`
- `msvcrt!_wtoi` at `0x140010866`
- `msvcrt!_wtoi` at `0x140010925`
- `msvcrt!wcsnlen` at `0x14001070d`
- `msvcrt!wcsnlen` at `0x140010880`
- `msvcrt!wcsnlen` at `0x14001093c`
- `msvcrt!wcsnlen` at `0x14001070d`
- `msvcrt!wcsnlen` at `0x140010880`
- `msvcrt!wcsnlen` at `0x14001093c`
- `msvcrt!_snwprintf_s` at `0x1400106ca`
- `msvcrt!_snwprintf_s` at `0x1400107c3`
- `msvcrt!_snwprintf_s` at `0x1400106ca`
- `msvcrt!_snwprintf_s` at `0x1400107c3`
- `WLDAP32!__imp_ldap_first_entry` at `0x140010822`
- `WLDAP32!__imp_ldap_first_entry` at `0x140010822`
- `WLDAP32!__imp_ldap_msgfree` at `0x1400109d1`
- `WLDAP32!__imp_ldap_msgfree` at `0x1400109d1`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140010859`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140010918`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140010859`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140010918`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140010848`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140010904`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140010848`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140010904`
- `WLDAP32!__imp_ldap_search_sW` at `0x140010801`
- `WLDAP32!__imp_ldap_search_sW` at `0x140010801`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1400108f0`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1400109ac`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1400108f0`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1400109ac`

## pseudocode

```c
__int64 __fastcall NfsUpCallDispatchGetUidGidWithLdapClient(
        unsigned int *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5)
{
  _DWORD *v5; // r12
  unsigned __int16 v9; // r15
  _BYTE *v10; // rsi
  char v11; // di
  int v12; // ebx
  unsigned int v13; // ecx
  unsigned int v14; // r8d
  unsigned int v15; // r11d
  __int64 v16; // r10
  __int64 v17; // r9
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rax
  int v21; // r15d
  ULONG v22; // eax
  LDAPMessage *entry; // rax
  LDAPMessage *v24; // r14
  PWCHAR *valuesW; // rax
  const wchar_t **v26; // rsi
  char v27; // r12
  int v28; // eax
  PWCHAR *v29; // rax
  int v30; // r14d
  const wchar_t **v31; // rsi
  int v32; // eax
  __int64 result; // rax
  LDAPMessage *res; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v35; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v36; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v37; // [rsp+5Ah] [rbp-A6h]
  int v38; // [rsp+5Ch] [rbp-A4h]
  char *v39; // [rsp+60h] [rbp-A0h]
  __int128 v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  LDAP *ld; // [rsp+80h] [rbp-80h] BYREF
  PWSTR base; // [rsp+88h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+2A0h] [rbp+1A0h] BYREF
  PWSTR attrs[4]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t Buffer[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wchar_t filter[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v5 = a5;
  v41 = (__int64)a5;
  memset_0(Buffer, 0, 0x208u);
  memset_0(filter, 0, 0x208u);
  attrs[0] = (PWSTR)L"uidNumber";
  attrs[2] = 0;
  attrs[1] = (PWSTR)L"gidNumber";
  res = 0;
  v37 = 0;
  v9 = 0;
  v38 = 0;
  v10 = 0;
  v35 = 0;
  v40 = 0;
  memset_0(&ld, 0, 0x218u);
  v11 = 1;
  if ( a2 < 0x28 )
    goto LABEL_2;
  v13 = a1[5];
  if ( v13 > 0xFFFF
    || (v14 = a1[7], v14 > 0xFFFF)
    || (v15 = a1[9], v15 > 0xFFFF)
    || (v16 = a1[4], (unsigned int)(v16 - 40) > 0xFFD7)
    || (v17 = a1[6], (unsigned int)(v17 - 40) > 0xFFD7)
    || (v18 = a1[8], (unsigned int)(v18 - 40) > 0xFFD7) )
  {
    v12 = -1073741811;
  }
  else
  {
    if ( a2 < (unsigned int)v16 + v13 || a2 < (unsigned int)v17 + v14 || a2 < (unsigned int)v18 + v15 )
    {
LABEL_2:
      v12 = -2147483643;
      goto LABEL_20;
    }
    LOWORD(v40) = a1[5];
    WORD1(v40) = v13;
    *((_QWORD *)&v40 + 1) = (char *)a1 + v16;
    v10 = (char *)a1 + v18;
    v39 = (char *)a1 + v18;
    LOWORD(v35) = v14;
    WORD1(v35) = v14;
    *((_QWORD *)&v35 + 1) = (char *)a1 + v17;
    v9 = v15;
    v36 = v15;
    v37 = v15;
    _snwprintf_s(Buffer, 0x104u, 0x103u, L"%wZ\\%wZ", &v40, &v35);
    v12 = NfsConnectLdapEx(&v40, &v35, &v36, &ld);
    if ( v12 < 0 )
    {
      v19 = wcsnlen(Buffer, 0x103u);
      UserData.Ptr = (ULONGLONG)Buffer;
      UserData.Size = 2 * v19 + 2;
      UserData.Reserved = 0;
      if ( RegHandle && EventEnabled(RegHandle, &EVENT_WARN_NFS_LDAP_CONNECTION_FAILED_FOR_USER) )
        EventWrite(RegHandle, &EVENT_WARN_NFS_LDAP_CONNECTION_FAILED_FOR_USER, 1u, &UserData);
    }
    else if ( !ld || !base )
    {
      v12 = -1073741823;
    }
  }
LABEL_20:
  if ( v9 )
  {
    v20 = v9;
    v21 = 0;
    do
    {
      *v10++ = 0;
      --v20;
    }
    while ( v20 );
  }
  else
  {
    v21 = 0;
  }
  if ( v12 < 0 )
    goto LABEL_47;
  _snwprintf_s(filter, 0x104u, 0x103u, L"(sAMAccountName=%wZ)", &v35);
  filter[259] = 0;
  v22 = ldap_search_sW(ld, base, 2u, filter, attrs, 0, &res);
  if ( v22 )
  {
    v12 = -1073741823;
    *(_DWORD *)(a3 + 32) = v22;
    goto LABEL_47;
  }
  entry = ldap_first_entry(ld, res);
  v24 = entry;
  if ( !entry )
  {
    v12 = -1073741823;
    goto LABEL_47;
  }
  valuesW = ldap_get_valuesW(ld, entry, (const PWSTR)L"uidNumber");
  v26 = (const wchar_t **)valuesW;
  if ( valuesW && ldap_count_valuesW(valuesW) )
  {
    v21 = _wtoi(*v26);
    v27 = 1;
LABEL_37:
    ldap_value_freeW((PWCHAR *)v26);
    goto LABEL_38;
  }
  v28 = wcsnlen(Buffer, 0x103u);
  UserData.Reserved = 0;
  UserData.Ptr = (ULONGLONG)Buffer;
  UserData.Size = 2 * v28 + 2;
  if ( RegHandle && EventEnabled(RegHandle, &EVENT_WARN_NFS_RFC2307_UIDNUMBER_NOT_SET_FOR_USER) )
    EventWrite(RegHandle, &EVENT_WARN_NFS_RFC2307_UIDNUMBER_NOT_SET_FOR_USER, 1u, &UserData);
  v27 = 0;
  if ( v26 )
    goto LABEL_37;
LABEL_38:
  v29 = ldap_get_valuesW(ld, v24, (const PWSTR)L"gidNumber");
  v30 = 0;
  v31 = (const wchar_t **)v29;
  if ( v29 && ldap_count_valuesW(v29) )
  {
    v30 = _wtoi(*v31);
  }
  else
  {
    v32 = wcsnlen(Buffer, 0x103u);
    UserData.Reserved = 0;
    UserData.Ptr = (ULONGLONG)Buffer;
    UserData.Size = 2 * v32 + 2;
    if ( RegHandle && EventEnabled(RegHandle, &EVENT_WARN_NFS_RFC2307_GIDNUMBER_NOT_SET_FOR_USER) )
      EventWrite(RegHandle, &EVENT_WARN_NFS_RFC2307_GIDNUMBER_NOT_SET_FOR_USER, 1u, &UserData);
    v11 = 0;
    if ( !v31 )
      goto LABEL_46;
  }
  ldap_value_freeW((PWCHAR *)v31);
LABEL_46:
  *(_BYTE *)(a3 + 40) = v27;
  v5 = (_DWORD *)v41;
  *(_DWORD *)(a3 + 44) = v21;
  *(_DWORD *)(a3 + 48) = v30;
  *(_BYTE *)(a3 + 41) = v11;
LABEL_47:
  if ( res )
    ldap_msgfree(res);
  NfsDisconnectLdap(&ld);
  result = (unsigned int)v12;
  *v5 = 52;
  return result;
}

```

## disassembly

```asm
0x1400104fc  mov     [rsp-8+arg_8], rbx
0x140010501  push    rbp
0x140010502  push    rsi
0x140010503  push    rdi
0x140010504  push    r12
0x140010506  push    r13
0x140010508  push    r14
0x14001050a  push    r15
0x14001050c  lea     rbp, [rsp-600h]
0x140010514  sub     rsp, 700h
0x14001051b  mov     rax, cs:__security_cookie
0x140010522  xor     rax, rsp
0x140010525  mov     [rbp+630h+var_40], rax
0x14001052c  mov     r12, [rbp+630h+arg_20]
0x140010533  mov     r13, r8
0x140010536  mov     r14d, edx
0x140010539  mov     [rsp+730h+var_6B8], r12
0x14001053e  mov     rbx, rcx
0x140010541  mov     edi, 208h
0x140010546  mov     r8d, edi; Size
0x140010549  lea     rcx, [rbp+630h+Buffer]; void *
0x140010550  xor     edx, edx; Val
0x140010552  call    memset_0
0x140010557  mov     r8d, edi; Size
0x14001055a  lea     rcx, [rbp+630h+filter]; void *
0x140010561  xor     edx, edx; Val
0x140010563  call    memset_0
0x140010568  xor     ecx, ecx
0x14001056a  lea     rax, attr; "uidNumber"
0x140010571  mov     [rbp+630h+var_480], rax
0x140010578  lea     r8d, [rdi+10h]; Size
0x14001057c  lea     rax, aGidnumber; "gidNumber"
0x140010583  mov     [rbp+630h+var_470], rcx
0x14001058a  mov     [rbp+630h+var_478], rax
0x140010591  xorps   xmm0, xmm0
0x140010594  xor     eax, eax
0x140010596  mov     [rsp+730h+var_6F0], rcx
0x14001059b  xorps   xmm1, xmm1
0x14001059e  mov     [rsp+730h+var_6D6], cx
0x1400105a3  mov     r15d, ecx
0x1400105a6  mov     [rsp+730h+var_6D4], eax
0x1400105aa  mov     esi, ecx
0x1400105ac  xor     edx, edx; Val
0x1400105ae  lea     rcx, [rbp+630h+ld]; void *
0x1400105b2  movups  [rsp+730h+var_6E8], xmm0
0x1400105b7  movups  [rsp+730h+var_6C8], xmm1
0x1400105bc  call    memset_0
0x1400105c1  lea     edi, [rsi+1]
0x1400105c4  cmp     r14d, 28h ; '('
0x1400105c8  jnb     short loc_1400105D4
0x1400105ca  mov     ebx, 80000005h
0x1400105cf  jmp     loc_140010778
0x1400105d4  mov     ecx, [rbx+14h]
0x1400105d7  mov     eax, 0FFFFh
0x1400105dc  cmp     ecx, eax
0x1400105de  ja      loc_140010773
0x1400105e4  mov     r8d, [rbx+1Ch]
0x1400105e8  cmp     r8d, eax
0x1400105eb  ja      loc_140010773
0x1400105f1  mov     r11d, [rbx+24h]
0x1400105f5  cmp     r11d, eax
0x1400105f8  ja      loc_140010773
0x1400105fe  mov     r10d, [rbx+10h]
0x140010602  mov     edx, 0FFD7h
0x140010607  lea     eax, [r10-28h]
0x14001060b  cmp     eax, edx
0x14001060d  ja      loc_140010773
0x140010613  mov     r9d, [rbx+18h]
0x140010617  lea     eax, [r9-28h]
0x14001061b  cmp     eax, edx
0x14001061d  ja      loc_140010773
0x140010623  mov     edx, [rbx+20h]
0x140010626  lea     eax, [rdx-28h]
0x140010629  cmp     eax, 0FFD7h
0x14001062e  ja      loc_140010773
0x140010634  lea     eax, [r10+rcx]
0x140010638  cmp     r14d, eax
0x14001063b  jb      short loc_1400105CA
0x14001063d  lea     eax, [r9+r8]
0x140010641  cmp     r14d, eax
0x140010644  jb      short loc_1400105CA
0x140010646  lea     eax, [rdx+r11]
0x14001064a  cmp     r14d, eax
0x14001064d  jb      loc_1400105CA
0x140010653  movzx   eax, cx
0x140010656  mov     word ptr [rsp+730h+var_6C8], cx
0x14001065b  lea     rax, [rbx+r10]
0x14001065f  mov     word ptr [rsp+730h+var_6C8+2], cx
0x140010664  mov     qword ptr [rsp+730h+var_6C8+8], rax
0x140010669  lea     rsi, [rbx+rdx]
0x14001066d  movzx   eax, r8w
0x140010671  mov     [rsp+730h+var_6D0], rsi
0x140010676  mov     word ptr [rsp+730h+var_6E8], ax
0x14001067b  lea     rcx, [rbp+630h+Buffer]; Buffer
0x140010682  mov     word ptr [rsp+730h+var_6E8+2], ax
0x140010687  mov     r14d, 103h
0x14001068d  lea     rax, [rbx+r9]
0x140010691  mov     r8d, r14d; MaxCount
0x140010694  mov     qword ptr [rsp+730h+var_6E8+8], rax
0x140010699  lea     r9, aWzWz; "%wZ\\%wZ"
0x1400106a0  movzx   eax, r11w
0x1400106a4  movzx   r15d, ax
0x1400106a8  mov     [rsp+730h+var_6D8], ax
0x1400106ad  mov     [rsp+730h+var_6D6], ax
0x1400106b2  lea     edx, [r14+1]; BufferCount
0x1400106b6  lea     rax, [rsp+730h+var_6E8]
0x1400106bb  mov     qword ptr [rsp+730h+attrsonly], rax
0x1400106c0  lea     rax, [rsp+730h+var_6C8]
0x1400106c5  mov     [rsp+730h+attrs], rax
0x1400106ca  call    cs:__imp__snwprintf_s
0x1400106d0  lea     r9, [rbp+630h+ld]
0x1400106d4  lea     r8, [rsp+730h+var_6D8]
0x1400106d9  lea     rdx, [rsp+730h+var_6E8]
0x1400106de  lea     rcx, [rsp+730h+var_6C8]
0x1400106e3  call    NfsConnectLdapEx
0x1400106e8  mov     ebx, eax
0x1400106ea  xor     eax, eax
0x1400106ec  test    ebx, ebx
0x1400106ee  js      short loc_140010703
0x1400106f0  cmp     [rbp+630h+ld], rax
0x1400106f4  jz      short loc_1400106FC
0x1400106f6  cmp     [rbp+630h+base], rax
0x1400106fa  jnz     short loc_140010778
0x1400106fc  mov     ebx, 0C0000001h
0x140010701  jmp     short loc_140010778
0x140010703  mov     rdx, r14; MaxCount
0x140010706  lea     rcx, [rbp+630h+Buffer]; Source
0x14001070d  call    cs:__imp_wcsnlen
0x140010713  lea     rcx, [rbp+630h+Buffer]
0x14001071a  mov     [rbp+630h+UserData.Ptr], rcx
0x140010721  mov     rcx, cs:RegHandle; RegHandle
0x140010728  lea     eax, ds:2[rax*2]
0x14001072f  mov     [rbp+630h+UserData.Size], eax
0x140010735  xor     eax, eax
0x140010737  mov     dword ptr [rbp+630h+UserData.0Ch], eax
0x14001073d  test    rcx, rcx
0x140010740  jz      short loc_140010778
0x140010742  lea     rdx, EVENT_WARN_NFS_LDAP_CONNECTION_FAILED_FOR_USER; EventDescriptor
0x140010749  call    cs:__imp_EventEnabled
0x14001074f  test    al, al
0x140010751  jz      short loc_140010778
0x140010753  mov     rcx, cs:RegHandle; RegHandle
0x14001075a  lea     r9, [rbp+630h+UserData]; UserData
0x140010761  mov     r8d, edi; UserDataCount
0x140010764  lea     rdx, EVENT_WARN_NFS_LDAP_CONNECTION_FAILED_FOR_USER; EventDescriptor
0x14001076b  call    cs:__imp_EventWrite
0x140010771  jmp     short loc_140010778
0x140010773  mov     ebx, 0C000000Dh
0x140010778  test    r15w, r15w
0x14001077c  jz      short loc_140010797
0x14001077e  movzx   eax, r15w
0x140010782  xor     r15d, r15d
0x140010785  test    rax, rax
0x140010788  jz      short loc_14001079A
0x14001078a  mov     [rsi], r15b
0x14001078d  add     rsi, rdi
0x140010790  sub     rax, rdi
0x140010793  jnz     short loc_14001078A
0x140010795  jmp     short loc_14001079A
0x140010797  xor     r15d, r15d
0x14001079a  test    ebx, ebx
0x14001079c  js      loc_1400109C7
0x1400107a2  mov     edx, 104h; BufferCount
0x1400107a7  lea     rax, [rsp+730h+var_6E8]
0x1400107ac  lea     r9, aSamaccountname; "(sAMAccountName=%wZ)"
0x1400107b3  mov     [rsp+730h+attrs], rax
0x1400107b8  lea     rcx, [rbp+630h+filter]; Buffer
0x1400107bf  lea     r8d, [rdx-1]; MaxCount
0x1400107c3  call    cs:__imp__snwprintf_s
0x1400107c9  mov     rdx, [rbp+630h+base]; base
0x1400107cd  lea     rax, [rsp+730h+var_6F0]
0x1400107d2  mov     rcx, [rbp+630h+ld]; ld
0x1400107d6  lea     r9, [rbp+630h+filter]; filter
0x1400107dd  mov     [rsp+730h+res], rax; res
0x1400107e2  mov     r8d, 2; scope
0x1400107e8  lea     rax, [rbp+630h+var_480]
0x1400107ef  mov     [rsp+730h+attrsonly], r15d; attrsonly
0x1400107f4  mov     [rsp+730h+attrs], rax; attrs
0x1400107f9  mov     [rbp+630h+var_4A], r15w
0x140010801  call    cs:__imp_ldap_search_sW
0x140010807  test    eax, eax
0x140010809  jz      short loc_140010819
0x14001080b  mov     ebx, 0C0000001h
0x140010810  mov     [r13+20h], eax
0x140010814  jmp     loc_1400109C7
0x140010819  mov     rdx, [rsp+730h+var_6F0]; res
0x14001081e  mov     rcx, [rbp+630h+ld]; ld
0x140010822  call    cs:__imp_ldap_first_entry
0x140010828  mov     r14, rax
0x14001082b  test    rax, rax
0x14001082e  jnz     short loc_14001083A
0x140010830  mov     ebx, 0C0000001h
0x140010835  jmp     loc_1400109C7
0x14001083a  mov     rcx, [rbp+630h+ld]; ld
0x14001083e  lea     r8, attr; "uidNumber"
0x140010845  mov     rdx, r14; entry
0x140010848  call    cs:__imp_ldap_get_valuesW
0x14001084e  mov     rsi, rax
0x140010851  test    rax, rax
0x140010854  jz      short loc_140010874
0x140010856  mov     rcx, rax; vals
0x140010859  call    cs:__imp_ldap_count_valuesW
0x14001085f  test    eax, eax
0x140010861  jz      short loc_140010874
0x140010863  mov     rcx, [rsi]; String
0x140010866  call    cs:__imp__wtoi
0x14001086c  mov     r15d, eax
0x14001086f  mov     r12b, dil
0x140010872  jmp     short loc_1400108ED
0x140010874  mov     edx, 103h; MaxCount
0x140010879  lea     rcx, [rbp+630h+Buffer]; Source
0x140010880  call    cs:__imp_wcsnlen
0x140010886  lea     rcx, [rbp+630h+Buffer]
0x14001088d  mov     dword ptr [rbp+630h+UserData.0Ch], r15d
0x140010894  mov     [rbp+630h+UserData.Ptr], rcx
0x14001089b  mov     rcx, cs:RegHandle; RegHandle
0x1400108a2  lea     eax, ds:2[rax*2]
0x1400108a9  mov     [rbp+630h+UserData.Size], eax
0x1400108af  test    rcx, rcx
0x1400108b2  jz      short loc_1400108E3
0x1400108b4  lea     rdx, EVENT_WARN_NFS_RFC2307_UIDNUMBER_NOT_SET_FOR_USER; EventDescriptor
0x1400108bb  call    cs:__imp_EventEnabled
0x1400108c1  test    al, al
0x1400108c3  jz      short loc_1400108E3
0x1400108c5  mov     rcx, cs:RegHandle; RegHandle
0x1400108cc  lea     r9, [rbp+630h+UserData]; UserData
0x1400108d3  mov     r8d, edi; UserDataCount
0x1400108d6  lea     rdx, EVENT_WARN_NFS_RFC2307_UIDNUMBER_NOT_SET_FOR_USER; EventDescriptor
0x1400108dd  call    cs:__imp_EventWrite
0x1400108e3  xor     ecx, ecx
0x1400108e5  mov     r12b, cl
0x1400108e8  test    rsi, rsi
0x1400108eb  jz      short loc_1400108F6
0x1400108ed  mov     rcx, rsi; vals
0x1400108f0  call    cs:__imp_ldap_value_freeW
0x1400108f6  mov     rcx, [rbp+630h+ld]; ld
0x1400108fa  lea     r8, aGidnumber; "gidNumber"
0x140010901  mov     rdx, r14; entry
0x140010904  call    cs:__imp_ldap_get_valuesW
0x14001090a  xor     r14d, r14d
0x14001090d  mov     rsi, rax
0x140010910  test    rax, rax
0x140010913  jz      short loc_140010930
0x140010915  mov     rcx, rax; vals
0x140010918  call    cs:__imp_ldap_count_valuesW
0x14001091e  test    eax, eax
0x140010920  jz      short loc_140010930
0x140010922  mov     rcx, [rsi]; String
0x140010925  call    cs:__imp__wtoi
0x14001092b  mov     r14d, eax
0x14001092e  jmp     short loc_1400109A9
0x140010930  mov     edx, 103h; MaxCount
0x140010935  lea     rcx, [rbp+630h+Buffer]; Source
0x14001093c  call    cs:__imp_wcsnlen
0x140010942  lea     rcx, [rbp+630h+Buffer]
0x140010949  mov     dword ptr [rbp+630h+UserData.0Ch], r14d
0x140010950  mov     [rbp+630h+UserData.Ptr], rcx
0x140010957  mov     rcx, cs:RegHandle; RegHandle
0x14001095e  lea     eax, ds:2[rax*2]
0x140010965  mov     [rbp+630h+UserData.Size], eax
0x14001096b  test    rcx, rcx
0x14001096e  jz      short loc_14001099F
0x140010970  lea     rdx, EVENT_WARN_NFS_RFC2307_GIDNUMBER_NOT_SET_FOR_USER; EventDescriptor
0x140010977  call    cs:__imp_EventEnabled
0x14001097d  test    al, al
0x14001097f  jz      short loc_14001099F
0x140010981  mov     rcx, cs:RegHandle; RegHandle
0x140010988  lea     r9, [rbp+630h+UserData]; UserData
0x14001098f  mov     r8d, edi; UserDataCount
0x140010992  lea     rdx, EVENT_WARN_NFS_RFC2307_GIDNUMBER_NOT_SET_FOR_USER; EventDescriptor
0x140010999  call    cs:__imp_EventWrite
0x14001099f  xor     ecx, ecx
0x1400109a1  mov     dil, cl
0x1400109a4  test    rsi, rsi
0x1400109a7  jz      short loc_1400109B2
0x1400109a9  mov     rcx, rsi; vals
0x1400109ac  call    cs:__imp_ldap_value_freeW
0x1400109b2  mov     [r13+28h], r12b
0x1400109b6  mov     r12, [rsp+730h+var_6B8]
0x1400109bb  mov     [r13+2Ch], r15d
0x1400109bf  mov     [r13+30h], r14d
0x1400109c3  mov     [r13+29h], dil
0x1400109c7  mov     rcx, [rsp+730h+var_6F0]; res
0x1400109cc  test    rcx, rcx
0x1400109cf  jz      short loc_1400109D7
0x1400109d1  call    cs:__imp_ldap_msgfree
0x1400109d7  lea     rcx, [rbp+630h+ld]
0x1400109db  call    NfsDisconnectLdap
0x1400109e0  mov     eax, ebx
0x1400109e2  mov     dword ptr [r12], 34h ; '4'
0x1400109ea  mov     rcx, [rbp+630h+var_40]
0x1400109f1  xor     rcx, rsp; StackCookie
0x1400109f4  call    __security_check_cookie
0x1400109f9  mov     rbx, [rsp+730h+arg_8]
0x140010a01  add     rsp, 700h
0x140010a08  pop     r15
0x140010a0a  pop     r14
0x140010a0c  pop     r13
0x140010a0e  pop     r12
0x140010a10  pop     rdi
  ... truncated ...
```
