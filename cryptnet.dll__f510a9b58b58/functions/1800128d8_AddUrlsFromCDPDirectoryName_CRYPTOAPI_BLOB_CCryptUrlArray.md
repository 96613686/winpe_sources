# AddUrlsFromCDPDirectoryName(_CRYPTOAPI_BLOB *,CCryptUrlArray *)

- ea: `0x1800128d8`
- end: `0x180012b44`
- name: `?AddUrlsFromCDPDirectoryName@@YAHPEAU_CRYPTOAPI_BLOB@@PEAVCCryptUrlArray@@@Z`
- size: `620`
- prototype: `__int64 __fastcall(PCERT_NAME_BLOB pName, struct CCryptUrlArray *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013c80`
- `0x1800141e0`

## callees

- `0x180003640`
- `0x180007c00`
- `0x18000a990`
- `0x1800127c8`
- `0x1800128d8`
- `0x1800139c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012aef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012aef`
- `CRYPT32!CertNameToStrW` at `0x180012949`
- `CRYPT32!CertNameToStrW` at `0x18001298a`
- `CRYPT32!CertNameToStrW` at `0x180012949`
- `CRYPT32!CertNameToStrW` at `0x18001298a`

## string_xrefs

- `0x1800128f7`: `DirectoryNameLdapHostPorts`
- `0x180012910`: `DirectoryNameLdapSuffix`

## pseudocode

```c
__int64 __fastcall AddUrlsFromCDPDirectoryName(PCERT_NAME_BLOB pName, struct CCryptUrlArray *a2)
{
  unsigned __int16 *v3; // rsi
  unsigned __int16 *CDPOIDFunctionValue; // rax
  __int64 *v5; // r13
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // r15
  unsigned int v8; // ebp
  DWORD v9; // eax
  DWORD csz; // ebx
  WCHAR *v11; // rax
  DWORD v12; // eax
  unsigned __int16 v13; // cx
  DWORD v14; // edx
  const unsigned __int16 *v15; // rdi
  __int64 v16; // r14
  __int64 v17; // rax
  unsigned __int64 v18; // rbx
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // r12
  __int64 v21; // rcx
  const wchar_t *v22; // r8
  unsigned __int64 v23; // rdx
  unsigned __int16 *v24; // rcx
  int v25; // ebx
  DWORD v28; // [rsp+80h] [rbp+18h]

  v3 = 0;
  CDPOIDFunctionValue = GetCDPOIDFunctionValue(L"DirectoryNameLdapHostPorts");
  v5 = &qword_180029D28;
  if ( CDPOIDFunctionValue )
    v5 = (__int64 *)CDPOIDFunctionValue;
  v6 = GetCDPOIDFunctionValue(L"DirectoryNameLdapSuffix");
  v7 = L"?certificateRevocationList;binary,authorityRevocationList;binary,deltaRevocationList;binary";
  if ( v6 )
    v7 = v6;
  v8 = 1;
  v9 = CertNameToStrW(1u, pName, 0x2000003u, 0, 0);
  csz = v9;
  if ( v9 > 1 )
  {
    v11 = (WCHAR *)operator new(saturated_mul(v9, 2u));
    v3 = v11;
    if ( v11 )
    {
      v12 = CertNameToStrW(1u, pName, 0x2000003u, v11, csz);
      if ( v12 <= 1 )
        goto LABEL_36;
      v13 = *(_WORD *)v5;
      v14 = v12 + 8;
      v28 = v12 + 8;
      v15 = (const unsigned __int16 *)v5;
      while ( 1 )
      {
        if ( v13 == 32 )
        {
          do
            ++v15;
          while ( *v15 == 32 );
        }
        if ( v15 )
        {
          v16 = -1;
          do
            ++v16;
          while ( v15[v16] );
        }
        else
        {
          LODWORD(v16) = 0;
        }
        if ( v7 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
        }
        else
        {
          LODWORD(v17) = 0;
        }
        v18 = (unsigned int)v16 + v14 + (_DWORD)v17;
        v19 = (unsigned __int16 *)operator new(saturated_mul(v18, 2u));
        v20 = v19;
        if ( !v19 )
          break;
        if ( v18 )
        {
          if ( v18 <= 0x7FFFFFFF )
          {
            v21 = 2147483646;
            v22 = L"ldap://";
            v23 = v18;
            do
            {
              if ( !v21 )
                break;
              if ( !*v22 )
                break;
              *v19++ = *v22++;
              --v21;
              --v23;
            }
            while ( v23 );
            v24 = v19 - 1;
            if ( v23 )
              v24 = v19;
            *v24 = 0;
          }
          else
          {
            *v19 = 0;
          }
        }
        StringCchCatW(v20, v18, v15);
        StringCchCatW(v20, v18, L"/");
        StringCchCatW(v20, v18, v3);
        StringCchCatW(v20, v18, v7);
        v25 = CCryptUrlArray::AddUrl(a2, v20, 1);
        operator delete(v20);
        if ( !v25 )
          goto LABEL_36;
        v15 += (unsigned int)(v16 + 1);
        v13 = *v15;
        if ( !*v15 )
          goto LABEL_37;
        v14 = v28;
      }
    }
    SetLastError(0x8007000E);
  }
LABEL_36:
  v8 = 0;
  if ( v3 )
LABEL_37:
    operator delete(v3);
  if ( v5 != &qword_180029D28 )
    operator delete(v5);
  if ( v7 != L"?certificateRevocationList;binary,authorityRevocationList;binary,deltaRevocationList;binary" )
    operator delete(v7);
  return v8;
}

```

## disassembly

```asm
0x1800128d8  mov     [rsp+arg_0], rbx
0x1800128dd  mov     [rsp+arg_8], rdx
0x1800128e2  push    rbp
0x1800128e3  push    rsi
0x1800128e4  push    rdi
0x1800128e5  push    r12
0x1800128e7  push    r13
0x1800128e9  push    r14
0x1800128eb  push    r15
0x1800128ed  sub     rsp, 30h
0x1800128f1  mov     rdi, rcx
0x1800128f4  xor     r12d, r12d
0x1800128f7  lea     rcx, pwszValueName; "DirectoryNameLdapHostPorts"
0x1800128fe  mov     esi, r12d
0x180012901  call    ?GetCDPOIDFunctionValue@@YAPEAGPEBG@Z; GetCDPOIDFunctionValue(ushort const *)
0x180012906  test    rax, rax
0x180012909  lea     r13, qword_180029D28
0x180012910  lea     rcx, aDirectorynamel_0; "DirectoryNameLdapSuffix"
0x180012917  cmovnz  r13, rax
0x18001291b  call    ?GetCDPOIDFunctionValue@@YAPEAGPEBG@Z; GetCDPOIDFunctionValue(ushort const *)
0x180012920  test    rax, rax
0x180012923  mov     [rsp+68h+csz], r12d; csz
0x180012928  lea     r15, aCertificaterev; "?certificateRevocationList;binary,autho"...
0x18001292f  mov     r14d, 2000003h
0x180012935  cmovnz  r15, rax
0x180012939  lea     ebp, [r12+1]
0x18001293e  xor     r9d, r9d; psz
0x180012941  mov     r8d, r14d; dwStrType
0x180012944  mov     rdx, rdi; pName
0x180012947  mov     ecx, ebp; dwCertEncodingType
0x180012949  call    cs:__imp_CertNameToStrW
0x18001294f  mov     ebx, eax
0x180012951  cmp     eax, ebp
0x180012953  jbe     loc_180012AF5
0x180012959  lea     rcx, [rbp-2]
0x18001295d  lea     eax, [rbp+1]
0x180012960  mul     rbx
0x180012963  cmovb   rax, rcx
0x180012967  mov     rcx, rax; uBytes
0x18001296a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001296f  mov     rsi, rax
0x180012972  test    rax, rax
0x180012975  jz      loc_180012AEA
0x18001297b  mov     r9, rax; psz
0x18001297e  mov     [rsp+68h+csz], ebx; csz
0x180012982  mov     r8d, r14d; dwStrType
0x180012985  mov     rdx, rdi; pName
0x180012988  mov     ecx, ebp; dwCertEncodingType
0x18001298a  call    cs:__imp_CertNameToStrW
0x180012990  cmp     eax, ebp
0x180012992  jbe     loc_180012AF5
0x180012998  movzx   ecx, word ptr [r13+0]
0x18001299d  lea     edx, [rax+8]
0x1800129a0  mov     [rsp+68h+arg_10], edx
0x1800129a7  mov     rdi, r13
0x1800129aa  mov     eax, 20h ; ' '
0x1800129af  cmp     ax, cx
0x1800129b2  jnz     short loc_1800129BD
0x1800129b4  add     rdi, 2
0x1800129b8  cmp     ax, [rdi]
0x1800129bb  jz      short loc_1800129B4
0x1800129bd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800129c1  test    rdi, rdi
0x1800129c4  jz      short loc_1800129D5
0x1800129c6  mov     r14, rcx
0x1800129c9  inc     r14
0x1800129cc  cmp     [rdi+r14*2], r12w
0x1800129d1  jnz     short loc_1800129C9
0x1800129d3  jmp     short loc_1800129D8
0x1800129d5  mov     r14d, r12d
0x1800129d8  test    r15, r15
0x1800129db  jz      short loc_1800129EC
0x1800129dd  mov     rax, rcx
0x1800129e0  inc     rax
0x1800129e3  cmp     [r15+rax*2], r12w
0x1800129e8  jnz     short loc_1800129E0
0x1800129ea  jmp     short loc_1800129EF
0x1800129ec  mov     eax, r12d
0x1800129ef  lea     ebx, [rdx+rax]
0x1800129f2  mov     eax, 2
0x1800129f7  add     ebx, r14d
0x1800129fa  mul     rbx
0x1800129fd  cmovb   rax, rcx
0x180012a01  mov     rcx, rax; uBytes
0x180012a04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012a09  xor     r10d, r10d
0x180012a0c  mov     r12, rax
0x180012a0f  test    rax, rax
0x180012a12  jz      loc_180012AE7
0x180012a18  test    rbx, rbx
0x180012a1b  jz      short loc_180012A6D
0x180012a1d  cmp     rbx, 7FFFFFFFh
0x180012a24  jbe     short loc_180012A2C
0x180012a26  mov     [rax], r10w
0x180012a2a  jmp     short loc_180012A6D
0x180012a2c  mov     ecx, 7FFFFFFEh
0x180012a31  lea     r8, aLdap_1; "ldap://"
0x180012a38  mov     rdx, rbx
0x180012a3b  test    rcx, rcx
0x180012a3e  jz      short loc_180012A5E
0x180012a40  movzx   r9d, word ptr [r8]
0x180012a44  test    r9w, r9w
0x180012a48  jz      short loc_180012A5E
0x180012a4a  mov     [rax], r9w
0x180012a4e  add     r8, 2
0x180012a52  add     rax, 2
0x180012a56  sub     rcx, rbp
0x180012a59  sub     rdx, rbp
0x180012a5c  jnz     short loc_180012A3B
0x180012a5e  test    rdx, rdx
0x180012a61  lea     rcx, [rax-2]
0x180012a65  cmovnz  rcx, rax
0x180012a69  mov     [rcx], r10w
0x180012a6d  mov     r8, rdi; unsigned __int16 *
0x180012a70  mov     rdx, rbx; unsigned __int64
0x180012a73  mov     rcx, r12; unsigned __int16 *
0x180012a76  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012a7b  lea     r8, asc_180029C68; "/"
0x180012a82  mov     rdx, rbx; unsigned __int64
0x180012a85  mov     rcx, r12; unsigned __int16 *
0x180012a88  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012a8d  mov     r8, rsi; unsigned __int16 *
0x180012a90  mov     rdx, rbx; unsigned __int64
0x180012a93  mov     rcx, r12; unsigned __int16 *
0x180012a96  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012a9b  mov     r8, r15; unsigned __int16 *
0x180012a9e  mov     rdx, rbx; unsigned __int64
0x180012aa1  mov     rcx, r12; unsigned __int16 *
0x180012aa4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012aa9  mov     rcx, [rsp+68h+arg_8]; this
0x180012aae  mov     r8d, ebp; int
0x180012ab1  mov     rdx, r12; Src
0x180012ab4  call    ?AddUrl@CCryptUrlArray@@QEAAHPEAGH@Z; CCryptUrlArray::AddUrl(ushort *,int)
0x180012ab9  mov     rcx, r12; hMem
0x180012abc  mov     ebx, eax
0x180012abe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012ac3  xor     r12d, r12d
0x180012ac6  test    ebx, ebx
0x180012ac8  jz      short loc_180012AF5
0x180012aca  lea     eax, [r14+1]
0x180012ace  lea     rdi, [rdi+rax*2]
0x180012ad2  movzx   ecx, word ptr [rdi]
0x180012ad5  cmp     r12w, cx
0x180012ad9  jz      short loc_180012AFD
0x180012adb  mov     edx, [rsp+68h+arg_10]
0x180012ae2  jmp     loc_1800129AA
0x180012ae7  xor     r12d, r12d
0x180012aea  mov     ecx, 8007000Eh; dwErrCode
0x180012aef  call    cs:__imp_SetLastError
0x180012af5  mov     ebp, r12d
0x180012af8  test    rsi, rsi
0x180012afb  jz      short loc_180012B05
0x180012afd  mov     rcx, rsi; hMem
0x180012b00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012b05  lea     rax, qword_180029D28
0x180012b0c  cmp     r13, rax
0x180012b0f  jz      short loc_180012B19
0x180012b11  mov     rcx, r13; hMem
0x180012b14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012b19  lea     rax, aCertificaterev; "?certificateRevocationList;binary,autho"...
0x180012b20  cmp     r15, rax
0x180012b23  jz      short loc_180012B2D
0x180012b25  mov     rcx, r15; hMem
0x180012b28  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012b2d  mov     rbx, [rsp+68h+arg_0]
0x180012b32  mov     eax, ebp
0x180012b34  add     rsp, 30h
0x180012b38  pop     r15
0x180012b3a  pop     r14
0x180012b3c  pop     r13
0x180012b3e  pop     r12
0x180012b40  pop     rdi
0x180012b41  pop     rsi
0x180012b42  pop     rbp
0x180012b43  retn
```
