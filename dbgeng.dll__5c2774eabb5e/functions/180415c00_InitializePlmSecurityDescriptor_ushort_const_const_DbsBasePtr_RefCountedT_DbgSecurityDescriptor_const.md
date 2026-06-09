# InitializePlmSecurityDescriptor(ushort const * const,DbsBasePtr<RefCountedT<DbgSecurityDescriptor>> * const)

- ea: `0x180415c00`
- end: `0x180416159`
- name: `?InitializePlmSecurityDescriptor@@YAJQEBGQEAV?$DbsBasePtr@V?$RefCountedT@VDbgSecurityDescriptor@@@@@@@Z`
- size: `1369`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cc5f0`

## callees

- `0x1800974e4`
- `0x18009a0d4`
- `0x1800f0f40`
- `0x1800f1750`
- `0x180415c00`
- `0x180417608`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180415dae`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180415dae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415e3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180416009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180416020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041608e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804160a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415e3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180416009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180416020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041608e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804160a5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180415ff9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180415ff9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180415e2d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180415e2d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180415f73`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180415f73`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415ce2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415d10`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415d58`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415dd4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415e8b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415f32`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415fd7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180416057`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1804160dc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18041611e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415ce2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415d10`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415d58`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415dd4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415e8b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415f32`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180415fd7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180416057`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1804160dc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18041611e`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x180415ece`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x180415ece`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180415c8b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180415c8b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180415d81`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180415d81`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18041607e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18041607e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InitializePlmSecurityDescriptor(unsigned __int16 *a1, __int64 a2)
{
  signed int v4; // eax
  int v5; // esi
  PSID *v6; // rbx
  PSID *v7; // rdi
  PSID *v9; // rbx
  PSID *v10; // rdi
  PSID *v11; // rbx
  PSID *v12; // rdi
  int v13; // edi
  int v14; // esi
  void **v15; // rbx
  DWORD v16; // ebx
  struct _ACL *v17; // rdi
  PSID *v18; // rbx
  PSID *v19; // rdi
  _QWORD *v20; // rax
  unsigned int v21; // ebx
  signed int v22; // eax
  PSID *v23; // rdi
  PSID *v24; // rsi
  void **i; // rbx
  signed int LastError; // eax
  PSID *v27; // rdi
  PSID *v28; // rsi
  void **j; // rbx
  signed int v30; // eax
  PSID *v31; // rdi
  PSID *v32; // rsi
  signed int v33; // eax
  PSID *v34; // rdi
  PSID *v35; // rsi
  signed int v36; // eax
  PSID *v37; // rdi
  PSID *v38; // rsi
  PSID *v39; // rbx
  PSID *v40; // rdi
  void **v41; // [rsp+68h] [rbp-9h] BYREF
  void ***v42; // [rsp+70h] [rbp-1h] BYREF
  void *v43[2]; // [rsp+78h] [rbp+7h] BYREF
  __int64 v44; // [rsp+88h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+1Fh] BYREF

  v44 = -2;
  *(_OWORD *)v43 = 0;
  v41 = v43;
  v42 = &v41;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, v43) )
  {
    if ( a1 )
    {
      v5 = DbgDeriveAppContainerSidFromAppContainerName(a1, &v43[1]);
      if ( v5 < 0 )
      {
        v11 = v41;
        v12 = v41 + 2;
        while ( v11 != v12 )
        {
          if ( *v11 )
            FreeSid(*v11);
          ++v11;
        }
        return (unsigned int)v5;
      }
    }
    v13 = 0;
    v14 = 0;
    v15 = v43;
    do
    {
      if ( *v15 )
      {
        v13 += GetLengthSid(*v15);
        ++v14;
      }
      ++v15;
    }
    while ( v15 != (void **)&v44 );
    v16 = 2 * (v13 + 8 * v14) + 8;
    v17 = (struct _ACL *)malloc(v16 + 40LL);
    if ( !v17 )
    {
      v18 = v41;
      v19 = v41 + 2;
      while ( v18 != v19 )
      {
        if ( *v18 )
          FreeSid(*v18);
        ++v18;
      }
      return 2147942414LL;
    }
    v20 = operator new(0x18u);
    v20[2] = 0;
    v20[1] = 0;
    *v20 = &DbgSecurityDescriptor::`vftable';
    *((_DWORD *)v20 + 4) = 1;
    v20[1] = v17;
    v42 = (void ***)v20;
    if ( InitializeAcl(v17 + 5, v16, 2u) )
    {
      for ( i = v43; i != (void **)&v44; ++i )
      {
        if ( *i && !AddAccessDeniedAce(v17 + 5, 2u, 0xC0000u, *i) )
        {
          if ( GetLastError() )
          {
            LastError = GetLastError();
            v21 = LastError;
            if ( LastError > 0 )
              v21 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v21 = -2147467259;
          }
          DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::~DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>(&v42);
          v27 = v41;
          v28 = v41 + 2;
          while ( v27 != v28 )
          {
            if ( *v27 )
              FreeSid(*v27);
            ++v27;
          }
          return v21;
        }
      }
      for ( j = v43; j != (void **)&v44; ++j )
      {
        if ( *j && !AddAccessAllowedAce(v17 + 5, 2u, 0x10000000u, *j) )
        {
          if ( GetLastError() )
          {
            v30 = GetLastError();
            v21 = v30;
            if ( v30 > 0 )
              v21 = (unsigned __int16)v30 | 0x80070000;
          }
          else
          {
            v21 = -2147467259;
          }
          DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::~DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>(&v42);
          v31 = v41;
          v32 = v41 + 2;
          while ( v31 != v32 )
          {
            if ( *v31 )
              FreeSid(*v31);
            ++v31;
          }
          return v21;
        }
      }
      if ( InitializeSecurityDescriptor(v17, 1u) )
      {
        if ( SetSecurityDescriptorDacl(v17, 1, v17 + 5, 0) )
        {
          DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::operator=(a2, &v42);
          DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::~DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>(&v42);
          v39 = v41;
          v40 = v41 + 2;
          while ( v39 != v40 )
          {
            if ( *v39 )
              FreeSid(*v39);
            ++v39;
          }
          return 0;
        }
        if ( GetLastError() )
        {
          v36 = GetLastError();
          v21 = v36;
          if ( v36 > 0 )
            v21 = (unsigned __int16)v36 | 0x80070000;
        }
        else
        {
          v21 = -2147467259;
        }
        DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::~DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>(&v42);
        v37 = v41;
        v38 = v41 + 2;
        while ( v37 != v38 )
        {
          if ( *v37 )
            FreeSid(*v37);
          ++v37;
        }
      }
      else
      {
        if ( GetLastError() )
        {
          v33 = GetLastError();
          v21 = v33;
          if ( v33 > 0 )
            v21 = (unsigned __int16)v33 | 0x80070000;
        }
        else
        {
          v21 = -2147467259;
        }
        DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::~DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>(&v42);
        v34 = v41;
        v35 = v41 + 2;
        while ( v34 != v35 )
        {
          if ( *v34 )
            FreeSid(*v34);
          ++v34;
        }
      }
    }
    else
    {
      if ( GetLastError() )
      {
        v22 = GetLastError();
        v21 = v22;
        if ( v22 > 0 )
          v21 = (unsigned __int16)v22 | 0x80070000;
      }
      else
      {
        v21 = -2147467259;
      }
      DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::~DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>(&v42);
      v23 = v41;
      v24 = v41 + 2;
      while ( v23 != v24 )
      {
        if ( *v23 )
          FreeSid(*v23);
        ++v23;
      }
    }
    return v21;
  }
  if ( GetLastError() )
  {
    v4 = GetLastError();
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    v5 = -2147024776;
    if ( v4 == -2147024776 )
    {
      v6 = v41;
      v7 = v41 + 2;
      while ( v6 != v7 )
      {
        if ( *v6 )
          FreeSid(*v6);
        ++v6;
      }
      return (unsigned int)v5;
    }
  }
  v9 = v41;
  v10 = v41 + 2;
  while ( v9 != v10 )
  {
    if ( *v9 )
      FreeSid(*v9);
    ++v9;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180415c00  mov     r11, rsp
0x180415c03  push    rbp
0x180415c04  push    rsi
0x180415c05  push    rdi
0x180415c06  push    r14
0x180415c08  push    r15
0x180415c0a  lea     rbp, [r11-5Fh]
0x180415c0e  sub     rsp, 0A0h
0x180415c15  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x180415c1d  mov     [r11+18h], rbx
0x180415c21  mov     rax, cs:__security_cookie
0x180415c28  xor     rax, rsp
0x180415c2b  mov     [rbp+57h+var_30], rax
0x180415c2f  mov     r14, rdx
0x180415c32  mov     rbx, rcx
0x180415c35  xorps   xmm0, xmm0
0x180415c38  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x180415c3d  lea     rax, [rbp+57h+var_50]
0x180415c41  mov     [rbp+57h+var_60], rax
0x180415c45  lea     rax, [rbp+57h+var_60]
0x180415c49  mov     [rbp+57h+var_58], rax
0x180415c4d  xor     r15d, r15d
0x180415c50  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x180415c54  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 100h
0x180415c5a  lea     rax, [rbp+57h+var_50]
0x180415c5e  mov     [r11-78h], rax
0x180415c62  mov     [r11-80h], r15d
0x180415c66  mov     [rsp+40h], r15d; nSubAuthority6
0x180415c6b  mov     [rsp+0C0h+nSubAuthority5], r15d; nSubAuthority5
0x180415c70  mov     [rsp+0C0h+nSubAuthority4], r15d; nSubAuthority4
0x180415c75  mov     [rsp+0C0h+nSubAuthority3], r15d; nSubAuthority3
0x180415c7a  mov     [rsp+0C0h+nSubAuthority2], r15d; nSubAuthority2
0x180415c7f  xor     r9d, r9d; nSubAuthority1
0x180415c82  xor     r8d, r8d; nSubAuthority0
0x180415c85  mov     dl, 1; nSubAuthorityCount
0x180415c87  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180415c8b  call    cs:__imp_AllocateAndInitializeSid
0x180415c92  nop     dword ptr [rax+rax+00h]
0x180415c97  test    eax, eax
0x180415c99  jnz     loc_180415D2F
0x180415c9f  call    cs:__imp_GetLastError
0x180415ca6  nop     dword ptr [rax+rax+00h]
0x180415cab  test    eax, eax
0x180415cad  jz      short loc_180415CFE
0x180415caf  call    cs:__imp_GetLastError
0x180415cb6  nop     dword ptr [rax+rax+00h]
0x180415cbb  test    eax, eax
0x180415cbd  jle     short loc_180415CC7
0x180415cbf  movzx   eax, ax
0x180415cc2  or      eax, 80070000h
0x180415cc7  mov     esi, 80070078h
0x180415ccc  cmp     eax, esi
0x180415cce  jnz     short loc_180415CFE
0x180415cd0  mov     rbx, [rbp+57h+var_60]
0x180415cd4  lea     rdi, [rbx+10h]
0x180415cd8  jmp     short loc_180415CF2
0x180415cda  mov     rcx, [rbx]; pSid
0x180415cdd  test    rcx, rcx
0x180415ce0  jz      short loc_180415CEE
0x180415ce2  call    cs:__imp_FreeSid
0x180415ce9  nop     dword ptr [rax+rax+00h]
0x180415cee  add     rbx, 8
0x180415cf2  cmp     rbx, rdi
0x180415cf5  jnz     short loc_180415CDA
0x180415cf7  mov     eax, esi
0x180415cf9  jmp     loc_180416135
0x180415cfe  mov     rbx, [rbp+57h+var_60]
0x180415d02  lea     rdi, [rbx+10h]
0x180415d06  jmp     short loc_180415D20
0x180415d08  mov     rcx, [rbx]; pSid
0x180415d0b  test    rcx, rcx
0x180415d0e  jz      short loc_180415D1C
0x180415d10  call    cs:__imp_FreeSid
0x180415d17  nop     dword ptr [rax+rax+00h]
0x180415d1c  add     rbx, 8
0x180415d20  cmp     rbx, rdi
0x180415d23  jnz     short loc_180415D08
0x180415d25  mov     eax, 80004005h
0x180415d2a  jmp     loc_180416135
0x180415d2f  test    rbx, rbx
0x180415d32  jz      short loc_180415D6F
0x180415d34  lea     rdx, [rbp+57h+var_50+8]; void **
0x180415d38  mov     rcx, rbx; unsigned __int16 *
0x180415d3b  call    ?DbgDeriveAppContainerSidFromAppContainerName@@YAJPEBGPEAPEAX@Z; DbgDeriveAppContainerSidFromAppContainerName(ushort const *,void * *)
0x180415d40  mov     esi, eax
0x180415d42  test    eax, eax
0x180415d44  jns     short loc_180415D6F
0x180415d46  mov     rbx, [rbp+57h+var_60]
0x180415d4a  lea     rdi, [rbx+10h]
0x180415d4e  jmp     short loc_180415D68
0x180415d50  mov     rcx, [rbx]; pSid
0x180415d53  test    rcx, rcx
0x180415d56  jz      short loc_180415D64
0x180415d58  call    cs:__imp_FreeSid
0x180415d5f  nop     dword ptr [rax+rax+00h]
0x180415d64  add     rbx, 8
0x180415d68  cmp     rbx, rdi
0x180415d6b  jnz     short loc_180415D50
0x180415d6d  jmp     short loc_180415CF7
0x180415d6f  mov     edi, r15d
0x180415d72  mov     esi, r15d
0x180415d75  lea     rbx, [rbp+57h+var_50]
0x180415d79  mov     rcx, [rbx]; pSid
0x180415d7c  test    rcx, rcx
0x180415d7f  jz      short loc_180415D91
0x180415d81  call    cs:__imp_GetLengthSid
0x180415d88  nop     dword ptr [rax+rax+00h]
0x180415d8d  add     edi, eax
0x180415d8f  inc     esi
0x180415d91  add     rbx, 8
0x180415d95  lea     rax, [rbp+57h+var_40]
0x180415d99  cmp     rbx, rax
0x180415d9c  jnz     short loc_180415D79
0x180415d9e  lea     eax, [rdi+rsi*8]
0x180415da1  lea     ebx, ds:8[rax*2]
0x180415da8  mov     ecx, ebx
0x180415daa  add     rcx, 28h ; '('; Size
0x180415dae  call    cs:__imp_malloc
0x180415db5  nop     dword ptr [rax+rax+00h]
0x180415dba  mov     rdi, rax
0x180415dbd  test    rax, rax
0x180415dc0  jnz     short loc_180415DF3
0x180415dc2  mov     rbx, [rbp+57h+var_60]
0x180415dc6  lea     rdi, [rbx+10h]
0x180415dca  jmp     short loc_180415DE4
0x180415dcc  mov     rcx, [rbx]; pSid
0x180415dcf  test    rcx, rcx
0x180415dd2  jz      short loc_180415DE0
0x180415dd4  call    cs:__imp_FreeSid
0x180415ddb  nop     dword ptr [rax+rax+00h]
0x180415de0  add     rbx, 8
0x180415de4  cmp     rbx, rdi
0x180415de7  jnz     short loc_180415DCC
0x180415de9  mov     eax, 8007000Eh
0x180415dee  jmp     loc_180416135
0x180415df3  mov     ecx, 18h; Size
0x180415df8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180415dfd  mov     [rax+10h], r15
0x180415e01  mov     [rax+8], r15
0x180415e05  lea     rcx, ??_7DbgSecurityDescriptor@@6B@; const DbgSecurityDescriptor::`vftable'
0x180415e0c  mov     [rax], rcx
0x180415e0f  mov     dword ptr [rax+10h], 1
0x180415e16  mov     [rax+8], rdi
0x180415e1a  mov     [rbp+57h+var_58], rax
0x180415e1e  lea     rsi, [rdi+28h]
0x180415e22  mov     r8d, 2; dwAclRevision
0x180415e28  mov     edx, ebx; nAclLength
0x180415e2a  mov     rcx, rsi; pAcl
0x180415e2d  call    cs:__imp_InitializeAcl
0x180415e34  nop     dword ptr [rax+rax+00h]
0x180415e39  test    eax, eax
0x180415e3b  jnz     short loc_180415EA7
0x180415e3d  call    cs:__imp_GetLastError
0x180415e44  nop     dword ptr [rax+rax+00h]
0x180415e49  test    eax, eax
0x180415e4b  jnz     short loc_180415E54
0x180415e4d  mov     ebx, 80004005h
0x180415e52  jmp     short loc_180415E6F
0x180415e54  call    cs:__imp_GetLastError
0x180415e5b  nop     dword ptr [rax+rax+00h]
0x180415e60  mov     ebx, eax
0x180415e62  test    eax, eax
0x180415e64  jle     short loc_180415E6F
0x180415e66  movzx   ebx, ax
0x180415e69  or      ebx, 80070000h
0x180415e6f  lea     rcx, [rbp+57h+var_58]
0x180415e73  call    ??1?$DbsBasePtr@V?$RefCountedT@VDbgSecurityDescriptor@@@@@@QEAA@XZ; DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::~DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>(void)
0x180415e78  nop
0x180415e79  mov     rdi, [rbp+57h+var_60]
0x180415e7d  lea     rsi, [rdi+10h]
0x180415e81  jmp     short loc_180415E9B
0x180415e83  mov     rcx, [rdi]; pSid
0x180415e86  test    rcx, rcx
0x180415e89  jz      short loc_180415E97
0x180415e8b  call    cs:__imp_FreeSid
0x180415e92  nop     dword ptr [rax+rax+00h]
0x180415e97  add     rdi, 8
0x180415e9b  cmp     rdi, rsi
0x180415e9e  jnz     short loc_180415E83
0x180415ea0  mov     eax, ebx
0x180415ea2  jmp     loc_180416135
0x180415ea7  lea     rbx, [rbp+57h+var_50]
0x180415eab  lea     rax, [rbp+57h+var_40]
0x180415eaf  cmp     rbx, rax
0x180415eb2  jz      loc_180415F4C
0x180415eb8  mov     r9, [rbx]; pSid
0x180415ebb  test    r9, r9
0x180415ebe  jz      short loc_180415EDE
0x180415ec0  mov     edx, 2; dwAceRevision
0x180415ec5  mov     r8d, 0C0000h; AccessMask
0x180415ecb  mov     rcx, rsi; pAcl
0x180415ece  call    cs:__imp_AddAccessDeniedAce
0x180415ed5  nop     dword ptr [rax+rax+00h]
0x180415eda  test    eax, eax
0x180415edc  jz      short loc_180415EE4
0x180415ede  add     rbx, 8
0x180415ee2  jmp     short loc_180415EAB
0x180415ee4  call    cs:__imp_GetLastError
0x180415eeb  nop     dword ptr [rax+rax+00h]
0x180415ef0  test    eax, eax
0x180415ef2  jnz     short loc_180415EFB
0x180415ef4  mov     ebx, 80004005h
0x180415ef9  jmp     short loc_180415F16
0x180415efb  call    cs:__imp_GetLastError
0x180415f02  nop     dword ptr [rax+rax+00h]
0x180415f07  mov     ebx, eax
0x180415f09  test    eax, eax
0x180415f0b  jle     short loc_180415F16
0x180415f0d  movzx   ebx, ax
0x180415f10  or      ebx, 80070000h
0x180415f16  lea     rcx, [rbp+57h+var_58]
0x180415f1a  call    ??1?$DbsBasePtr@V?$RefCountedT@VDbgSecurityDescriptor@@@@@@QEAA@XZ; DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::~DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>(void)
0x180415f1f  nop
0x180415f20  mov     rdi, [rbp+57h+var_60]
0x180415f24  lea     rsi, [rdi+10h]
0x180415f28  jmp     short loc_180415F42
0x180415f2a  mov     rcx, [rdi]; pSid
0x180415f2d  test    rcx, rcx
0x180415f30  jz      short loc_180415F3E
0x180415f32  call    cs:__imp_FreeSid
0x180415f39  nop     dword ptr [rax+rax+00h]
0x180415f3e  add     rdi, 8
0x180415f42  cmp     rdi, rsi
0x180415f45  jnz     short loc_180415F2A
0x180415f47  jmp     loc_180415EA0
0x180415f4c  lea     rbx, [rbp+57h+var_50]
0x180415f50  lea     rax, [rbp+57h+var_40]
0x180415f54  cmp     rbx, rax
0x180415f57  jz      loc_180415FF1
0x180415f5d  mov     r9, [rbx]; pSid
0x180415f60  test    r9, r9
0x180415f63  jz      short loc_180415F83
0x180415f65  mov     edx, 2; dwAceRevision
0x180415f6a  mov     r8d, 10000000h; AccessMask
0x180415f70  mov     rcx, rsi; pAcl
0x180415f73  call    cs:__imp_AddAccessAllowedAce
0x180415f7a  nop     dword ptr [rax+rax+00h]
0x180415f7f  test    eax, eax
0x180415f81  jz      short loc_180415F89
0x180415f83  add     rbx, 8
0x180415f87  jmp     short loc_180415F50
0x180415f89  call    cs:__imp_GetLastError
0x180415f90  nop     dword ptr [rax+rax+00h]
0x180415f95  test    eax, eax
0x180415f97  jnz     short loc_180415FA0
0x180415f99  mov     ebx, 80004005h
0x180415f9e  jmp     short loc_180415FBB
0x180415fa0  call    cs:__imp_GetLastError
0x180415fa7  nop     dword ptr [rax+rax+00h]
0x180415fac  mov     ebx, eax
0x180415fae  test    eax, eax
0x180415fb0  jle     short loc_180415FBB
0x180415fb2  movzx   ebx, ax
0x180415fb5  or      ebx, 80070000h
0x180415fbb  lea     rcx, [rbp+57h+var_58]
0x180415fbf  call    ??1?$DbsBasePtr@V?$RefCountedT@VDbgSecurityDescriptor@@@@@@QEAA@XZ; DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::~DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>(void)
0x180415fc4  nop
0x180415fc5  mov     rdi, [rbp+57h+var_60]
0x180415fc9  lea     rsi, [rdi+10h]
0x180415fcd  jmp     short loc_180415FE7
0x180415fcf  mov     rcx, [rdi]; pSid
0x180415fd2  test    rcx, rcx
0x180415fd5  jz      short loc_180415FE3
0x180415fd7  call    cs:__imp_FreeSid
0x180415fde  nop     dword ptr [rax+rax+00h]
0x180415fe3  add     rdi, 8
0x180415fe7  cmp     rdi, rsi
0x180415fea  jnz     short loc_180415FCF
0x180415fec  jmp     loc_180415EA0
0x180415ff1  mov     edx, 1; dwRevision
0x180415ff6  mov     rcx, rdi; pSecurityDescriptor
0x180415ff9  call    cs:__imp_InitializeSecurityDescriptor
0x180416000  nop     dword ptr [rax+rax+00h]
0x180416005  test    eax, eax
0x180416007  jnz     short loc_180416071
0x180416009  call    cs:__imp_GetLastError
0x180416010  nop     dword ptr [rax+rax+00h]
0x180416015  test    eax, eax
0x180416017  jnz     short loc_180416020
0x180416019  mov     ebx, 80004005h
0x18041601e  jmp     short loc_18041603B
0x180416020  call    cs:__imp_GetLastError
0x180416027  nop     dword ptr [rax+rax+00h]
0x18041602c  mov     ebx, eax
0x18041602e  test    eax, eax
0x180416030  jle     short loc_18041603B
0x180416032  movzx   ebx, ax
0x180416035  or      ebx, 80070000h
0x18041603b  lea     rcx, [rbp+57h+var_58]
0x18041603f  call    ??1?$DbsBasePtr@V?$RefCountedT@VDbgSecurityDescriptor@@@@@@QEAA@XZ; DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>::~DbsBasePtr<RefCountedT<DbgSecurityDescriptor>>(void)
0x180416044  nop
0x180416045  mov     rdi, [rbp+57h+var_60]
0x180416049  lea     rsi, [rdi+10h]
0x18041604d  jmp     short loc_180416067
0x18041604f  mov     rcx, [rdi]; pSid
0x180416052  test    rcx, rcx
0x180416055  jz      short loc_180416063
0x180416057  call    cs:__imp_FreeSid
0x18041605e  nop     dword ptr [rax+rax+00h]
0x180416063  add     rdi, 8
  ... truncated ...
```
