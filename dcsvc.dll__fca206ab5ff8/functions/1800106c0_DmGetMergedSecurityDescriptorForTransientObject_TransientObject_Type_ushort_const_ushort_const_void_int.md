# DmGetMergedSecurityDescriptorForTransientObject(TransientObject_Type,ushort const *,ushort const *,void * *,int *)

- ea: `0x1800106c0`
- end: `0x1800109dd`
- name: `?DmGetMergedSecurityDescriptorForTransientObject@@YAJW4TransientObject_Type@@PEBG1PEAPEAXPEAH@Z`
- size: `797`
- prototype: `__int64(__int64, __int64, __int64, void **, ...)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180007b9c`
- `0x18000f178`
- `0x180010404`

## callees

- `0x1800081a4`
- `0x1800081c4`
- `0x18000ef00`
- `0x1800106c0`
- `0x180010f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010749`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010801`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010749`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107ee`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180010718`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800107d0`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180010718`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800107d0`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180010741`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180010795`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800107a4`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800107f9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18001095d`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18001096c`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180010992`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800109bd`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180010741`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180010795`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800107a4`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800107f9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18001095d`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18001096c`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180010992`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800109bd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180010863`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180010897`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180010863`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180010897`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x1800108bc`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x1800108bc`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800108e0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800108e0`

## string_xrefs

- `0x18001077d`: `onecoreuap\admin\dm\configmanager2\service\cmlockservice\cmlockserviceapiimpl.cpp`
- `0x180010876`: `onecoreuap\admin\dm\configmanager2\service\cmlockservice\cmlockserviceapiimpl.cpp`
- `0x180010928`: `onecoreuap\admin\dm\configmanager2\service\cmlockservice\cmlockserviceapiimpl.cpp`
- `0x180010940`: `onecoreuap\admin\dm\configmanager2\service\cmlockservice\cmlockserviceapiimpl.cpp`

## pseudocode

```c
__int64 DmGetMergedSecurityDescriptorForTransientObject(__int64 a1, __int64 a2, __int64 a3, void **a4, ...)
{
  int *v4; // r15
  __int64 v5; // rbx
  unsigned int v6; // r14d
  int v7; // esi
  unsigned int v8; // edi
  PSECURITY_DESCRIPTOR *v9; // r14
  void *v10; // r13
  PSECURITY_DESCRIPTOR v11; // r12
  DWORD LastError; // ebx
  __int64 v13; // rdx
  PSECURITY_DESCRIPTOR *v15; // r14
  void *v16; // r13
  PSECURITY_DESCRIPTOR v17; // r12
  DWORD v18; // ebx
  PSECURITY_DESCRIPTOR v19; // rbx
  PSECURITY_DESCRIPTOR v20; // rdi
  const char *v21; // r9
  __int64 v22; // rdx
  int v23; // eax
  DWORD ExplicitEntriesFromAclW; // eax
  unsigned int v25; // r8d
  __int64 v26; // rdx
  unsigned int v27; // ebx
  int updated; // eax
  PSECURITY_DESCRIPTOR v29; // rax
  PSECURITY_DESCRIPTOR v30; // rax
  PSECURITY_DESCRIPTOR v31; // [rsp+20h] [rbp-50h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+28h] [rbp-48h] BYREF
  WINBOOL bDaclPresent; // [rsp+30h] [rbp-40h] BYREF
  ULONG pcCountOfExplicitEntries; // [rsp+34h] [rbp-3Ch] BYREF
  PSECURITY_DESCRIPTOR *p_pSecurityDescriptor; // [rsp+38h] [rbp-38h]
  void *v36; // [rsp+40h] [rbp-30h] BYREF
  char v37; // [rsp+48h] [rbp-28h]
  PACL pacl; // [rsp+50h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-18h] BYREF
  PEXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp-10h] BYREF
  PACL NewAcl; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  unsigned int v43; // [rsp+B0h] [rbp+40h]
  int *bDaclDefaulted; // [rsp+D0h] [rbp+60h] BYREF
  va_list bDaclDefaulteda; // [rsp+D0h] [rbp+60h]
  va_list va1; // [rsp+D8h] [rbp+68h] BYREF

  va_start(va1, a4);
  va_start(bDaclDefaulteda, a4);
  bDaclDefaulted = va_arg(va1, int *);
  v43 = a1;
  v4 = bDaclDefaulted;
  p_pSecurityDescriptor = &pSecurityDescriptor;
  v5 = a3;
  *a4 = 0;
  v31 = 0;
  v6 = a1;
  pSecurityDescriptor = 0;
  v7 = 1;
  *v4 = 0;
  v37 = 1;
  v36 = 0;
  v8 = QueryTransientObjectSecurityDescriptor(a1, a2, &v36);
  if ( v37 )
  {
    v9 = p_pSecurityDescriptor;
    v10 = v36;
    v11 = *p_pSecurityDescriptor;
    if ( *p_pSecurityDescriptor )
    {
      LastError = GetLastError();
      FreeTransientObjectSecurityDescriptor(v11);
      SetLastError(LastError);
      v5 = a3;
    }
    *v9 = v10;
    v6 = v43;
  }
  if ( (int)(v8 + 0x80000000) >= 0 && v8 != -1073741772 )
  {
    v13 = 967;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\dm\\configmanager2\\service\\cmlockservice\\cmlockserviceapiimpl.cpp",
      (const char *)v8,
      (int)v31);
    if ( pSecurityDescriptor )
      FreeTransientObjectSecurityDescriptor(pSecurityDescriptor);
    if ( v31 )
      FreeTransientObjectSecurityDescriptor(v31);
    return v8;
  }
  if ( v5 )
  {
    v36 = 0;
    p_pSecurityDescriptor = &v31;
    v37 = 1;
    v8 = QueryTransientObjectSecurityDescriptor(v6, v5, &v36);
    if ( v37 )
    {
      v15 = p_pSecurityDescriptor;
      v16 = v36;
      v17 = *p_pSecurityDescriptor;
      if ( *p_pSecurityDescriptor )
      {
        v18 = GetLastError();
        FreeTransientObjectSecurityDescriptor(v17);
        SetLastError(v18);
      }
      *v15 = v16;
    }
    if ( ((v8 + 0x80000000) & 0x80000000) == 0 && v8 != -1073741772 )
    {
      v13 = 979;
      goto LABEL_8;
    }
  }
  v19 = v31;
  if ( !v31 )
  {
    v30 = pSecurityDescriptor;
    if ( pSecurityDescriptor )
    {
      pSecurityDescriptor = 0;
      *a4 = v30;
      *v4 = 1;
    }
    goto LABEL_47;
  }
  v20 = pSecurityDescriptor;
  if ( !pSecurityDescriptor )
  {
    v29 = v31;
    v19 = 0;
    v31 = 0;
    *a4 = v29;
LABEL_43:
    *v4 = v7;
    if ( v20 )
    {
      FreeTransientObjectSecurityDescriptor(v20);
      v19 = v31;
    }
LABEL_47:
    if ( v19 )
      FreeTransientObjectSecurityDescriptor(v19);
    return 0;
  }
  pDacl = 0;
  bDaclPresent = 0;
  LODWORD(bDaclDefaulted) = 0;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, (LPBOOL)bDaclDefaulteda) )
  {
    v22 = 898;
LABEL_25:
    v23 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v22,
            (unsigned int)"onecoreuap\\admin\\dm\\configmanager2\\service\\cmlockservice\\cmlockserviceapiimpl.cpp",
            v21);
    goto LABEL_33;
  }
  pacl = 0;
  if ( !GetSecurityDescriptorDacl(v19, &bDaclPresent, &pacl, (LPBOOL)bDaclDefaulteda) )
  {
    v22 = 906;
    goto LABEL_25;
  }
  pcCountOfExplicitEntries = 0;
  pListOfExplicitEntries = 0;
  ExplicitEntriesFromAclW = GetExplicitEntriesFromAclW(pacl, &pcCountOfExplicitEntries, &pListOfExplicitEntries);
  if ( ExplicitEntriesFromAclW )
  {
    v26 = 914;
  }
  else
  {
    NewAcl = 0;
    ExplicitEntriesFromAclW = SetEntriesInAclW(pcCountOfExplicitEntries, pListOfExplicitEntries, pDacl, &NewAcl);
    if ( !ExplicitEntriesFromAclW )
    {
      updated = UpdateSecurityDescriptor(v20, NewAcl, a4);
      v27 = updated;
      if ( updated >= 0 )
        goto LABEL_34;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A0,
        (unsigned int)"onecoreuap\\admin\\dm\\configmanager2\\service\\cmlockservice\\cmlockserviceapiimpl.cpp",
        (const char *)(unsigned int)updated,
        (int)v31);
      goto LABEL_37;
    }
    v26 = 922;
  }
  v23 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v26,
          v25,
          (const char *)ExplicitEntriesFromAclW,
          (unsigned int)v31);
LABEL_33:
  v27 = v23;
  if ( v23 >= 0 )
  {
LABEL_34:
    v19 = v31;
    v7 = 0;
    v20 = pSecurityDescriptor;
    goto LABEL_43;
  }
LABEL_37:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3DD,
    (unsigned int)"onecoreuap\\admin\\dm\\configmanager2\\service\\cmlockservice\\cmlockserviceapiimpl.cpp",
    (const char *)v27,
    (int)v31);
  if ( pSecurityDescriptor )
    FreeTransientObjectSecurityDescriptor(pSecurityDescriptor);
  if ( v31 )
    FreeTransientObjectSecurityDescriptor(v31);
  return v27;
}

```

## disassembly

```asm
0x1800106c0  mov     rax, rsp
0x1800106c3  mov     [rax+10h], rbx
0x1800106c7  mov     [rax+20h], r9
0x1800106cb  mov     [rax+18h], r8
0x1800106cf  mov     [rax+8], ecx
0x1800106d2  push    rbp
0x1800106d3  push    rsi
0x1800106d4  push    rdi
0x1800106d5  push    r12
0x1800106d7  push    r13
0x1800106d9  push    r14
0x1800106db  push    r15
0x1800106dd  mov     rbp, rsp
0x1800106e0  sub     rsp, 70h
0x1800106e4  mov     r15, [rbp+bDaclDefaulted]
0x1800106e8  lea     rax, [rbp+pSecurityDescriptor]
0x1800106ec  xor     r12d, r12d
0x1800106ef  mov     [rbp+var_38], rax
0x1800106f3  mov     rbx, r8
0x1800106f6  mov     [r9], r12
0x1800106f9  lea     r8, [rbp+var_30]
0x1800106fd  mov     [rbp+var_50], r12
0x180010701  mov     r14d, ecx
0x180010704  mov     [rbp+pSecurityDescriptor], r12
0x180010708  lea     esi, [r12+1]
0x18001070d  mov     [r15], r12d
0x180010710  mov     [rbp+var_28], sil
0x180010714  mov     [rbp+var_30], r12
0x180010718  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18001071e  mov     edi, eax
0x180010720  cmp     [rbp+var_28], r12b
0x180010724  jz      short loc_18001075D
0x180010726  mov     r14, [rbp+var_38]
0x18001072a  mov     r13, [rbp+var_30]
0x18001072e  mov     r12, [r14]
0x180010731  test    r12, r12
0x180010734  jz      short loc_180010753
0x180010736  call    cs:__imp_GetLastError
0x18001073c  mov     rcx, r12
0x18001073f  mov     ebx, eax
0x180010741  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180010747  mov     ecx, ebx; dwErrCode
0x180010749  call    cs:__imp_SetLastError
0x18001074f  mov     rbx, [rbp+arg_10]
0x180010753  mov     [r14], r13
0x180010756  xor     r12d, r12d
0x180010759  mov     r14d, [rbp+arg_0]
0x18001075d  mov     r13d, 80000000h
0x180010763  lea     eax, [rdi+r13]
0x180010767  test    r13d, eax
0x18001076a  jnz     short loc_1800107B1
0x18001076c  cmp     edi, 0C0000034h
0x180010772  jz      short loc_1800107B1
0x180010774  mov     edx, 3C7h; void *
0x180010779  mov     rcx, [rbp+38h]; this
0x18001077d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\configmanager2\\"...
0x180010784  mov     r9d, edi; char *
0x180010787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001078c  mov     rcx, [rbp+pSecurityDescriptor]
0x180010790  test    rcx, rcx
0x180010793  jz      short loc_18001079B
0x180010795  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18001079b  mov     rcx, [rbp+var_50]
0x18001079f  test    rcx, rcx
0x1800107a2  jz      short loc_1800107AA
0x1800107a4  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800107aa  mov     eax, edi
0x1800107ac  jmp     loc_1800109C5
0x1800107b1  test    rbx, rbx
0x1800107b4  jz      short loc_18001082E
0x1800107b6  lea     rax, [rbp+var_50]
0x1800107ba  mov     [rbp+var_30], r12
0x1800107be  lea     r8, [rbp+var_30]
0x1800107c2  mov     [rbp+var_38], rax
0x1800107c6  mov     rdx, rbx
0x1800107c9  mov     [rbp+var_28], sil
0x1800107cd  mov     ecx, r14d
0x1800107d0  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x1800107d6  mov     edi, eax
0x1800107d8  cmp     [rbp+var_28], r12b
0x1800107dc  jz      short loc_180010813
0x1800107de  mov     r14, [rbp+var_38]
0x1800107e2  mov     r13, [rbp+var_30]
0x1800107e6  mov     r12, [r14]
0x1800107e9  test    r12, r12
0x1800107ec  jz      short loc_180010807
0x1800107ee  call    cs:__imp_GetLastError
0x1800107f4  mov     rcx, r12
0x1800107f7  mov     ebx, eax
0x1800107f9  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800107ff  mov     ecx, ebx; dwErrCode
0x180010801  call    cs:__imp_SetLastError
0x180010807  mov     [r14], r13
0x18001080a  xor     r12d, r12d
0x18001080d  mov     r13d, 80000000h
0x180010813  lea     eax, [rdi+r13]
0x180010817  test    r13d, eax
0x18001081a  jnz     short loc_18001082E
0x18001081c  cmp     edi, 0C0000034h
0x180010822  jz      short loc_18001082E
0x180010824  mov     edx, 3D3h
0x180010829  jmp     loc_180010779
0x18001082e  mov     rbx, [rbp+var_50]
0x180010832  test    rbx, rbx
0x180010835  jz      loc_18001099E
0x18001083b  mov     rdi, [rbp+pSecurityDescriptor]
0x18001083f  test    rdi, rdi
0x180010842  jz      loc_180010976
0x180010848  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18001084c  mov     [rbp+pDacl], r12
0x180010850  lea     r8, [rbp+pDacl]; pDacl
0x180010854  mov     [rbp+bDaclPresent], r12d
0x180010858  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18001085c  mov     dword ptr [rbp+bDaclDefaulted], r12d
0x180010860  mov     rcx, rdi; pSecurityDescriptor
0x180010863  call    cs:__imp_GetSecurityDescriptorDacl
0x180010869  test    eax, eax
0x18001086b  jnz     short loc_180010884
0x18001086d  mov     edx, 382h; void *
0x180010872  mov     rcx, [rbp+38h]; this
0x180010876  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\configmanager2\\"...
0x18001087d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010882  jmp     short loc_1800108FB
0x180010884  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180010888  mov     [rbp+pacl], r12
0x18001088c  lea     r8, [rbp+pacl]; pDacl
0x180010890  mov     rcx, rbx; pSecurityDescriptor
0x180010893  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180010897  call    cs:__imp_GetSecurityDescriptorDacl
0x18001089d  test    eax, eax
0x18001089f  jnz     short loc_1800108A8
0x1800108a1  mov     edx, 38Ah
0x1800108a6  jmp     short loc_180010872
0x1800108a8  mov     rcx, [rbp+pacl]; pacl
0x1800108ac  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800108b0  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x1800108b4  mov     [rbp+pcCountOfExplicitEntries], r12d
0x1800108b8  mov     [rbp+pListOfExplicitEntries], r12
0x1800108bc  call    cs:__imp_GetExplicitEntriesFromAclW
0x1800108c2  test    eax, eax
0x1800108c4  jz      short loc_1800108CD
0x1800108c6  mov     edx, 392h
0x1800108cb  jmp     short loc_1800108EF
0x1800108cd  mov     r8, [rbp+pDacl]; OldAcl
0x1800108d1  lea     r9, [rbp+NewAcl]; NewAcl
0x1800108d5  mov     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800108d9  mov     ecx, [rbp+pcCountOfExplicitEntries]; cCountOfExplicitEntries
0x1800108dc  mov     [rbp+NewAcl], r12
0x1800108e0  call    cs:__imp_SetEntriesInAclW
0x1800108e6  test    eax, eax
0x1800108e8  jz      short loc_18001090E
0x1800108ea  mov     edx, 39Ah; void *
0x1800108ef  mov     rcx, [rbp+38h]; this
0x1800108f3  mov     r9d, eax; char *
0x1800108f6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800108fb  mov     ebx, eax
0x1800108fd  test    eax, eax
0x1800108ff  js      short loc_18001093C
0x180010901  mov     rbx, [rbp+var_50]
0x180010905  mov     esi, r12d
0x180010908  mov     rdi, [rbp+pSecurityDescriptor]
0x18001090c  jmp     short loc_180010987
0x18001090e  mov     r8, [rbp+arg_18]; void **
0x180010912  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x180010915  mov     rdx, [rbp+NewAcl]; struct _ACL *
0x180010919  call    ?UpdateSecurityDescriptor@@YAJPEAXPEAU_ACL@@PEAPEAX@Z; UpdateSecurityDescriptor(void *,_ACL *,void * *)
0x18001091e  mov     ebx, eax
0x180010920  test    eax, eax
0x180010922  jns     short loc_180010901
0x180010924  mov     rcx, [rbp+38h]; this
0x180010928  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\configmanager2\\"...
0x18001092f  mov     r9d, eax; char *
0x180010932  mov     edx, 3A0h; void *
0x180010937  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001093c  mov     rcx, [rbp+38h]; this
0x180010940  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\configmanager2\\"...
0x180010947  mov     r9d, ebx; char *
0x18001094a  mov     edx, 3DDh; void *
0x18001094f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010954  mov     rcx, [rbp+pSecurityDescriptor]
0x180010958  test    rcx, rcx
0x18001095b  jz      short loc_180010963
0x18001095d  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180010963  mov     rcx, [rbp+var_50]
0x180010967  test    rcx, rcx
0x18001096a  jz      short loc_180010972
0x18001096c  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180010972  mov     eax, ebx
0x180010974  jmp     short loc_1800109C5
0x180010976  mov     rcx, [rbp+arg_18]
0x18001097a  mov     rax, rbx
0x18001097d  mov     rbx, r12
0x180010980  mov     [rbp+var_50], rbx
0x180010984  mov     [rcx], rax
0x180010987  mov     [r15], esi
0x18001098a  test    rdi, rdi
0x18001098d  jz      short loc_1800109B5
0x18001098f  mov     rcx, rdi
0x180010992  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180010998  mov     rbx, [rbp+var_50]
0x18001099c  jmp     short loc_1800109B5
0x18001099e  mov     rax, [rbp+pSecurityDescriptor]
0x1800109a2  test    rax, rax
0x1800109a5  jz      short loc_1800109B5
0x1800109a7  mov     rcx, [rbp+arg_18]
0x1800109ab  mov     [rbp+pSecurityDescriptor], r12
0x1800109af  mov     [rcx], rax
0x1800109b2  mov     [r15], esi
0x1800109b5  test    rbx, rbx
0x1800109b8  jz      short loc_1800109C3
0x1800109ba  mov     rcx, rbx
0x1800109bd  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800109c3  xor     eax, eax
0x1800109c5  mov     rbx, [rsp+70h+arg_8]
0x1800109cd  add     rsp, 70h
0x1800109d1  pop     r15
0x1800109d3  pop     r14
0x1800109d5  pop     r13
0x1800109d7  pop     r12
0x1800109d9  pop     rdi
0x1800109da  pop     rsi
0x1800109db  pop     rbp
0x1800109dc  retn
```
