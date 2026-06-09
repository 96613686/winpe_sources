# PlaiSetEtwSecurity(_GUID const *,ushort const *)

- ea: `0x1800bd0c0`
- end: `0x1800bd5fa`
- name: `?PlaiSetEtwSecurity@@YAJPEBU_GUID@@PEBG@Z`
- size: `1338`
- prototype: `int(const struct _GUID *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800018b0`
- `0x1800cc090`
- `0x1800dbfb0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800bd0c0`
- `0x1801147b8`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd2c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd2c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd37d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800bd2bb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800bd2bb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800bd36f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800bd36f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd5cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd5cc`
- `api-ms-win-eventing-controller-l1-1-0!EventAccessRemove` at `0x1800bd4ce`
- `api-ms-win-eventing-controller-l1-1-0!EventAccessRemove` at `0x1800bd4ce`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800bd437`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800bd437`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bd1e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bd1e0`

## string_xrefs

- `0x1800bd1b0`: `PlaiSetEtwSecurity`
- `0x1800bd28c`: `PlaiSetEtwSecurity`
- `0x1800bd567`: `PlaiSetEtwSecurity`

## pseudocode

```c
__int64 __fastcall PlaiSetEtwSecurity(const struct _GUID *a1, const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rax
  int *v6; // r9
  int *v7; // rax
  DWORD v8; // eax
  int v9; // eax
  __int64 v10; // rax
  DWORD v11; // eax
  int v12; // eax
  __int64 v13; // rax
  SECURITY_INFORMATION v14; // edi
  DWORD LastError; // eax
  int v16; // eax
  __int64 v17; // rax
  DWORD v18; // eax
  int v19; // eax
  __int64 v20; // rax
  ULONG v21; // eax
  int v22; // eax
  __int64 v23; // rax
  int v25; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL bDaclPresent; // [rsp+80h] [rbp-80h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+84h] [rbp-7Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  PACL pSacl; // [rsp+90h] [rbp-70h] BYREF
  PACL pDacl; // [rsp+98h] [rbp-68h] BYREF
  GUID Guid; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v33; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pObjectName[39]; // [rsp+B2h] [rbp-4Eh] BYREF
  unsigned __int16 v35[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v36[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v37[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v38[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v39[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v40[64]; // [rsp+380h] [rbp+280h] BYREF

  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  SecurityDescriptor = 0;
  Guid = 0;
  if ( a2 && *a2 )
  {
    v3 = PlaiGuidToString(a1, &v33, 0x28u);
    v4 = v3;
    if ( v3 >= 0 )
    {
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(a2, 1u, &SecurityDescriptor, 0)
        || (v8 = GetLastError(), v9 = PlaiHResultFromWin32(v8), v4 = v9, v9 >= 0) )
      {
        if ( GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted)
          || (v11 = GetLastError(), v12 = PlaiHResultFromWin32(v11), v4 = v12, v12 >= 0) )
        {
          v14 = 0;
          if ( bDaclPresent )
            v14 = 4;
          if ( GetSecurityDescriptorSacl(SecurityDescriptor, &bDaclPresent, &pSacl, &bDaclDefaulted)
            || (LastError = GetLastError(), v16 = PlaiHResultFromWin32(LastError), v4 = v16, v16 >= 0) )
          {
            if ( bDaclPresent )
              v14 |= 8u;
            pObjectName[36] = 0;
            v18 = SetNamedSecurityInfoW(pObjectName, SE_WMIGUID_OBJECT, v14, 0, 0, pDacl, pSacl);
            v19 = PlaiHResultFromWin32(v18);
            v4 = v19;
            if ( v19 >= 0 )
              goto LABEL_53;
            v26 = 0;
            v25 = v19;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_53;
            }
            PlaiWhoAmI(v39, 0x4000000000000800uLL);
            v20 = -1;
            do
              ++v20;
            while ( v39[v20] );
          }
          else
          {
            v26 = 0;
            v25 = v16;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_53;
            }
            PlaiWhoAmI(v38, 0x4000000000000800uLL);
            v17 = -1;
            do
              ++v17;
            while ( v38[v17] );
          }
        }
        else
        {
          v26 = 0;
          v25 = v12;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_53;
          }
          PlaiWhoAmI(v37, 0x4000000000000800uLL);
          v13 = -1;
          do
            ++v13;
          while ( v37[v13] );
        }
      }
      else
      {
        v26 = 0;
        v25 = v9;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_53;
        }
        PlaiWhoAmI(v36, 0x4000000000000800uLL);
        v10 = -1;
        do
          ++v10;
        while ( v36[v10] );
      }
      v6 = &v25;
      v7 = &v26;
LABEL_52:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v6, 4, byte_180147320, 1, v7, 4);
      goto LABEL_53;
    }
    v25 = 0;
    v26 = v3;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v35, 0x4000000000000800uLL);
      v5 = -1;
      do
        ++v5;
      while ( v35[v5] );
      v6 = &v26;
      v7 = &v25;
      goto LABEL_52;
    }
  }
  else
  {
    Guid = *a1;
    v21 = EventAccessRemove(&Guid);
    v22 = PlaiHResultFromWin32(v21);
    v4 = v22;
    if ( v22 < 0 )
    {
      v26 = 0;
      v25 = v22;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v40, 0x4000000000000800uLL);
          v23 = -1;
          do
            ++v23;
          while ( v40[v23] );
          v6 = &v25;
          v7 = &v26;
          goto LABEL_52;
        }
      }
    }
  }
LABEL_53:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x1800bd0c0  mov     [rsp-8+arg_10], rbx
0x1800bd0c5  push    rbp
0x1800bd0c6  push    rsi
0x1800bd0c7  push    rdi
0x1800bd0c8  push    r14
0x1800bd0ca  push    r15
0x1800bd0cc  lea     rbp, [rsp-310h]
0x1800bd0d4  sub     rsp, 410h
0x1800bd0db  mov     rax, cs:__security_cookie
0x1800bd0e2  xor     rax, rsp
0x1800bd0e5  mov     [rbp+330h+var_30], rax
0x1800bd0ec  xor     r15d, r15d
0x1800bd0ef  xorps   xmm0, xmm0
0x1800bd0f2  mov     [rbp+330h+pDacl], r15
0x1800bd0f6  mov     rdi, rdx
0x1800bd0f9  mov     [rbp+330h+pSacl], r15
0x1800bd0fd  mov     [rbp+330h+bDaclPresent], r15d
0x1800bd101  mov     [rbp+330h+bDaclDefaulted], r15d
0x1800bd105  mov     [rbp+330h+SecurityDescriptor], r15
0x1800bd109  movups  xmmword ptr [rbp+330h+Guid.Data1], xmm0
0x1800bd10d  test    rdx, rdx
0x1800bd110  jz      loc_1800BD4C2
0x1800bd116  cmp     r15w, [rdx]
0x1800bd11a  jz      loc_1800BD4C2
0x1800bd120  lea     r8d, [r15+28h]; unsigned __int64
0x1800bd124  lea     rdx, [rbp+330h+var_380]; unsigned __int16 *
0x1800bd128  call    ?PlaiGuidToString@@YAJPEBU_GUID@@PEAG_K@Z; PlaiGuidToString(_GUID const *,ushort *,unsigned __int64)
0x1800bd12d  mov     ebx, eax
0x1800bd12f  test    eax, eax
0x1800bd131  jns     loc_1800BD1CF
0x1800bd137  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800bd13e  mov     [rsp+430h+var_3C0], r15d
0x1800bd143  mov     [rsp+430h+var_3B8], eax
0x1800bd147  jz      loc_1800BD5C3
0x1800bd14d  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bd157  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bd15e  jz      loc_1800BD5C3
0x1800bd164  mov     rax, cs:qword_180169748
0x1800bd16b  and     rax, rdx
0x1800bd16e  cmp     cs:qword_180169748, rax
0x1800bd175  jnz     loc_1800BD5C3
0x1800bd17b  lea     rcx, [rbp+330h+var_330]; unsigned __int16 *
0x1800bd17f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bd184  lea     rcx, [rbp+330h+var_330]
0x1800bd188  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bd18c  inc     rax
0x1800bd18f  cmp     [rcx+rax*2], r15w
0x1800bd194  jnz     short loc_1800BD18C
0x1800bd196  lea     ecx, [rax+rax]
0x1800bd199  lea     rax, [rbp+330h+var_330]
0x1800bd19d  add     rcx, 2
0x1800bd1a1  mov     [rsp+430h+var_3D0], rcx
0x1800bd1a6  lea     r9, [rsp+430h+var_3B8]
0x1800bd1ab  mov     [rsp+430h+var_3D8], rax
0x1800bd1b0  lea     rax, aPlaisetetwsecu; "PlaiSetEtwSecurity"
0x1800bd1b7  mov     [rsp+430h+var_3E0], 13h
0x1800bd1c0  mov     [rsp+430h+var_3E8], rax
0x1800bd1c5  lea     rax, [rsp+430h+var_3C0]
0x1800bd1ca  jmp     loc_1800BD581
0x1800bd1cf  xor     r9d, r9d; SecurityDescriptorSize
0x1800bd1d2  lea     r8, [rbp+330h+SecurityDescriptor]; SecurityDescriptor
0x1800bd1d6  mov     rcx, rdi; StringSecurityDescriptor
0x1800bd1d9  lea     r14d, [r9+1]
0x1800bd1dd  mov     edx, r14d; StringSDRevision
0x1800bd1e0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800bd1e6  test    eax, eax
0x1800bd1e8  jnz     loc_1800BD2AB
0x1800bd1ee  call    cs:__imp_GetLastError
0x1800bd1f4  mov     ecx, eax; unsigned int
0x1800bd1f6  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800bd1fb  mov     ebx, eax
0x1800bd1fd  test    eax, eax
0x1800bd1ff  jns     loc_1800BD2AB
0x1800bd205  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800bd20c  mov     [rsp+430h+var_3B8], r15d
0x1800bd211  mov     [rsp+430h+var_3C0], eax
0x1800bd215  jz      loc_1800BD5C3
0x1800bd21b  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bd225  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bd22c  jz      loc_1800BD5C3
0x1800bd232  mov     rax, cs:qword_180169748
0x1800bd239  and     rax, rdx
0x1800bd23c  cmp     cs:qword_180169748, rax
0x1800bd243  jnz     loc_1800BD5C3
0x1800bd249  lea     rcx, [rbp+330h+var_2B0]; unsigned __int16 *
0x1800bd250  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bd255  lea     rcx, [rbp+330h+var_2B0]
0x1800bd25c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bd260  inc     rax
0x1800bd263  cmp     [rcx+rax*2], r15w
0x1800bd268  jnz     short loc_1800BD260
0x1800bd26a  lea     ecx, [rax+rax]
0x1800bd26d  lea     rax, [rbp+330h+var_2B0]
0x1800bd274  mov     esi, 4
0x1800bd279  add     rcx, 2
0x1800bd27d  lea     r9, [rsp+430h+var_3C0]
0x1800bd282  mov     [rsp+430h+var_3D0], rcx
0x1800bd287  mov     [rsp+430h+var_3D8], rax
0x1800bd28c  lea     rax, aPlaisetetwsecu; "PlaiSetEtwSecurity"
0x1800bd293  mov     [rsp+430h+var_3E0], 13h
0x1800bd29c  mov     [rsp+430h+var_3E8], rax
0x1800bd2a1  lea     rax, [rsp+430h+var_3B8]
0x1800bd2a6  jmp     loc_1800BD58A
0x1800bd2ab  mov     rcx, [rbp+330h+SecurityDescriptor]; pSecurityDescriptor
0x1800bd2af  lea     r9, [rbp+330h+bDaclDefaulted]; lpbDaclDefaulted
0x1800bd2b3  lea     r8, [rbp+330h+pDacl]; pDacl
0x1800bd2b7  lea     rdx, [rbp+330h+bDaclPresent]; lpbDaclPresent
0x1800bd2bb  call    cs:__imp_GetSecurityDescriptorDacl
0x1800bd2c1  test    eax, eax
0x1800bd2c3  jnz     loc_1800BD350
0x1800bd2c9  call    cs:__imp_GetLastError
0x1800bd2cf  mov     ecx, eax; unsigned int
0x1800bd2d1  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800bd2d6  mov     ebx, eax
0x1800bd2d8  test    eax, eax
0x1800bd2da  jns     short loc_1800BD350
0x1800bd2dc  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800bd2e3  mov     [rsp+430h+var_3B8], r15d
0x1800bd2e8  mov     [rsp+430h+var_3C0], eax
0x1800bd2ec  jz      loc_1800BD5C3
0x1800bd2f2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bd2fc  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bd303  jz      loc_1800BD5C3
0x1800bd309  mov     rax, cs:qword_180169748
0x1800bd310  and     rax, rdx
0x1800bd313  cmp     cs:qword_180169748, rax
0x1800bd31a  jnz     loc_1800BD5C3
0x1800bd320  lea     rcx, [rbp+330h+var_230]; unsigned __int16 *
0x1800bd327  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bd32c  lea     rcx, [rbp+330h+var_230]
0x1800bd333  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bd337  inc     rax
0x1800bd33a  cmp     [rcx+rax*2], r15w
0x1800bd33f  jnz     short loc_1800BD337
0x1800bd341  lea     ecx, [rax+rax]
0x1800bd344  lea     rax, [rbp+330h+var_230]
0x1800bd34b  jmp     loc_1800BD274
0x1800bd350  cmp     [rbp+330h+bDaclPresent], r15d
0x1800bd354  lea     r9, [rbp+330h+bDaclDefaulted]; lpbSaclDefaulted
0x1800bd358  mov     rcx, [rbp+330h+SecurityDescriptor]; pSecurityDescriptor
0x1800bd35c  lea     r8, [rbp+330h+pSacl]; pSacl
0x1800bd360  mov     edi, r15d
0x1800bd363  lea     rdx, [rbp+330h+bDaclPresent]; lpbSaclPresent
0x1800bd367  mov     esi, 4
0x1800bd36c  cmovnz  edi, esi
0x1800bd36f  call    cs:__imp_GetSecurityDescriptorSacl
0x1800bd375  test    eax, eax
0x1800bd377  jnz     loc_1800BD404
0x1800bd37d  call    cs:__imp_GetLastError
0x1800bd383  mov     ecx, eax; unsigned int
0x1800bd385  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800bd38a  mov     ebx, eax
0x1800bd38c  test    eax, eax
0x1800bd38e  jns     short loc_1800BD404
0x1800bd390  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800bd397  mov     [rsp+430h+var_3B8], r15d
0x1800bd39c  mov     [rsp+430h+var_3C0], eax
0x1800bd3a0  jz      loc_1800BD5C3
0x1800bd3a6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bd3b0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bd3b7  jz      loc_1800BD5C3
0x1800bd3bd  mov     rax, cs:qword_180169748
0x1800bd3c4  and     rax, rdx
0x1800bd3c7  cmp     cs:qword_180169748, rax
0x1800bd3ce  jnz     loc_1800BD5C3
0x1800bd3d4  lea     rcx, [rbp+330h+var_1B0]; unsigned __int16 *
0x1800bd3db  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bd3e0  lea     rcx, [rbp+330h+var_1B0]
0x1800bd3e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bd3eb  inc     rax
0x1800bd3ee  cmp     [rcx+rax*2], r15w
0x1800bd3f3  jnz     short loc_1800BD3EB
0x1800bd3f5  lea     ecx, [rax+rax]
0x1800bd3f8  lea     rax, [rbp+330h+var_1B0]
0x1800bd3ff  jmp     loc_1800BD279
0x1800bd404  cmp     [rbp+330h+bDaclPresent], r15d
0x1800bd408  jz      short loc_1800BD40D
0x1800bd40a  or      edi, 8
0x1800bd40d  mov     rax, [rbp+330h+pSacl]
0x1800bd411  lea     rcx, [rbp+330h+pObjectName]; pObjectName
0x1800bd415  mov     [rsp+430h+var_400], rax; pSacl
0x1800bd41a  xor     r9d, r9d; psidOwner
0x1800bd41d  mov     rax, [rbp+330h+pDacl]
0x1800bd421  mov     r8d, edi; SecurityInfo
0x1800bd424  mov     [rsp+430h+var_408], rax; pDacl
0x1800bd429  mov     [rsp+430h+psidGroup], r15; psidGroup
0x1800bd42e  lea     edx, [r9+0Bh]; ObjectType
0x1800bd432  mov     [rbp+330h+var_336], r15w
0x1800bd437  call    cs:__imp_SetNamedSecurityInfoW
0x1800bd43d  mov     ecx, eax; unsigned int
0x1800bd43f  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800bd444  mov     ebx, eax
0x1800bd446  test    eax, eax
0x1800bd448  jns     loc_1800BD5C3
0x1800bd44e  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800bd455  mov     [rsp+430h+var_3B8], r15d
0x1800bd45a  mov     [rsp+430h+var_3C0], eax
0x1800bd45e  jz      loc_1800BD5C3
0x1800bd464  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bd46e  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bd475  jz      loc_1800BD5C3
0x1800bd47b  mov     rax, cs:qword_180169748
0x1800bd482  and     rax, rdx
0x1800bd485  cmp     cs:qword_180169748, rax
0x1800bd48c  jnz     loc_1800BD5C3
0x1800bd492  lea     rcx, [rbp+330h+var_130]; unsigned __int16 *
0x1800bd499  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bd49e  lea     rcx, [rbp+330h+var_130]
0x1800bd4a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bd4a9  inc     rax
0x1800bd4ac  cmp     [rcx+rax*2], r15w
0x1800bd4b1  jnz     short loc_1800BD4A9
0x1800bd4b3  lea     ecx, [rax+rax]
0x1800bd4b6  lea     rax, [rbp+330h+var_130]
0x1800bd4bd  jmp     loc_1800BD279
0x1800bd4c2  movups  xmm0, xmmword ptr [rcx]
0x1800bd4c5  lea     rcx, [rbp+330h+Guid]; Guid
0x1800bd4c9  movdqu  xmmword ptr [rbp+330h+Guid.Data1], xmm0
0x1800bd4ce  call    cs:__imp_EventAccessRemove
0x1800bd4d4  mov     ecx, eax; unsigned int
0x1800bd4d6  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800bd4db  mov     ebx, eax
0x1800bd4dd  test    eax, eax
0x1800bd4df  jns     loc_1800BD5C3
0x1800bd4e5  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800bd4ec  mov     [rsp+430h+var_3B8], r15d
0x1800bd4f1  mov     [rsp+430h+var_3C0], eax
0x1800bd4f5  jz      loc_1800BD5C3
0x1800bd4fb  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bd505  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bd50c  jz      loc_1800BD5C3
0x1800bd512  mov     rax, cs:qword_180169748
0x1800bd519  and     rax, rdx
0x1800bd51c  cmp     cs:qword_180169748, rax
0x1800bd523  jnz     loc_1800BD5C3
0x1800bd529  lea     rcx, [rbp+330h+var_B0]; unsigned __int16 *
0x1800bd530  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bd535  lea     rcx, [rbp+330h+var_B0]
0x1800bd53c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bd540  inc     rax
0x1800bd543  cmp     [rcx+rax*2], r15w
0x1800bd548  jnz     short loc_1800BD540
0x1800bd54a  lea     ecx, [rax+rax]
0x1800bd54d  lea     rax, [rbp+330h+var_B0]
0x1800bd554  add     rcx, 2
0x1800bd558  mov     [rsp+430h+var_3D0], rcx
0x1800bd55d  lea     r9, [rsp+430h+var_3C0]
0x1800bd562  mov     [rsp+430h+var_3D8], rax
0x1800bd567  lea     rax, aPlaisetetwsecu; "PlaiSetEtwSecurity"
0x1800bd56e  mov     [rsp+430h+var_3E0], 13h
0x1800bd577  mov     [rsp+430h+var_3E8], rax
0x1800bd57c  lea     rax, [rsp+430h+var_3B8]
0x1800bd581  mov     esi, 4
0x1800bd586  lea     r14d, [rsi-3]
0x1800bd58a  mov     [rsp+430h+var_3F0], rsi
0x1800bd58f  lea     rdx, PLA_EVENT_ERROR
0x1800bd596  mov     [rsp+430h+var_3F8], rax
0x1800bd59b  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800bd5a2  lea     rax, byte_180147320
0x1800bd5a9  mov     [rsp+430h+var_400], r14
0x1800bd5ae  mov     [rsp+430h+var_408], rax
0x1800bd5b3  mov     r8d, 5
0x1800bd5b9  mov     [rsp+430h+psidGroup], rsi
0x1800bd5be  call    EventingWriteEvent
0x1800bd5c3  mov     rcx, [rbp+330h+SecurityDescriptor]; hMem
0x1800bd5c7  test    rcx, rcx
0x1800bd5ca  jz      short loc_1800BD5D2
0x1800bd5cc  call    cs:__imp_LocalFree
0x1800bd5d2  mov     eax, ebx
0x1800bd5d4  mov     rcx, [rbp+330h+var_30]
0x1800bd5db  xor     rcx, rsp; StackCookie
0x1800bd5de  call    __security_check_cookie
0x1800bd5e3  mov     rbx, [rsp+430h+arg_10]
0x1800bd5eb  add     rsp, 410h
0x1800bd5f2  pop     r15
0x1800bd5f4  pop     r14
0x1800bd5f6  pop     rdi
0x1800bd5f7  pop     rsi
0x1800bd5f8  pop     rbp
0x1800bd5f9  retn
```
