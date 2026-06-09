# LdapConvertLdapResultMessage

- ea: `0x180011eb4`
- end: `0x180012291`
- name: `LdapConvertLdapResultMessage`
- size: `989`
- prototype: `__int64 __fastcall(LDAP *ld, LDAPMessage *res, __int16, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180011134`

## callees

- `0x1800013fc`
- `0x180002d24`
- `0x180007c00`
- `0x18000a990`
- `0x18000bb78`
- `0x180011eb4`
- `0x180026552`
- `0x18002656a`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800121b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800121ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800121f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012287`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800121b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800121ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800121f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012287`
- `CRYPT32!CryptMemAlloc` at `0x180012094`
- `CRYPT32!CryptMemAlloc` at `0x180012094`
- `CRYPT32!CryptMemFree` at `0x1800121e3`
- `CRYPT32!CryptMemFree` at `0x18001221f`
- `CRYPT32!CryptMemFree` at `0x18001226e`
- `CRYPT32!CryptMemFree` at `0x1800121e3`
- `CRYPT32!CryptMemFree` at `0x18001221f`
- `CRYPT32!CryptMemFree` at `0x18001226e`
- `ntdll!_ltoa` at `0x180011fb4`
- `ntdll!_ltoa` at `0x180011fb4`
- `WLDAP32!__imp_ldap_first_entry` at `0x180011f73`
- `WLDAP32!__imp_ldap_first_entry` at `0x180011f73`
- `WLDAP32!__imp_ldap_next_entry` at `0x180012159`
- `WLDAP32!__imp_ldap_next_entry` at `0x180012159`
- `WLDAP32!__imp_ldap_value_free_len` at `0x180012128`
- `WLDAP32!__imp_ldap_value_free_len` at `0x180012128`
- `WLDAP32!__imp_ldap_first_attributeA` at `0x180011fda`
- `WLDAP32!__imp_ldap_first_attributeA` at `0x180011fda`
- `WLDAP32!__imp_ldap_get_values_lenA` at `0x180011ffe`
- `WLDAP32!__imp_ldap_get_values_lenA` at `0x180011ffe`
- `WLDAP32!__imp_ldap_next_attributeA` at `0x180012139`
- `WLDAP32!__imp_ldap_next_attributeA` at `0x180012139`

## string_xrefs

- `0x18001219f`: `CRYPTNET.DLL --> Exceeded MaxUrlRetrievalByteCount for: Ldap Url\n`

## pseudocode

```c
__int64 __fastcall LdapConvertLdapResultMessage(LDAP *ld, LDAPMessage *res, __int16 a3, __int64 a4, _DWORD *a5)
{
  int v5; // r15d
  LDAP *v6; // r13
  unsigned int v7; // edi
  __int64 v8; // r12
  void *v10; // rax
  void *v11; // rbx
  unsigned int v12; // esi
  LDAPMessage *v13; // r14
  int v14; // r12d
  __int64 v15; // rax
  CHAR *attributeA; // r13
  struct berval **values_lenA; // rbx
  unsigned __int64 v18; // rdi
  struct berval *v19; // rax
  size_t bv_len; // r15
  unsigned int v21; // eax
  __int64 v22; // rax
  ULONG v23; // r12d
  unsigned __int8 *v24; // rax
  unsigned __int8 *v25; // r14
  unsigned __int8 *v26; // rcx
  int v27; // r9d
  DWORD v28; // ecx
  unsigned int j; // r14d
  LDAPMessage *entry; // [rsp+28h] [rbp-79h]
  unsigned int Size; // [rsp+30h] [rbp-71h]
  unsigned int Size_4; // [rsp+34h] [rbp-6Dh]
  unsigned int v34; // [rsp+38h] [rbp-69h]
  unsigned int v35; // [rsp+3Ch] [rbp-65h]
  int i; // [rsp+40h] [rbp-61h]
  int v37; // [rsp+44h] [rbp-5Dh]
  struct berval **vals; // [rsp+50h] [rbp-51h]
  unsigned int v41; // [rsp+60h] [rbp-41h] BYREF
  void *v42; // [rsp+68h] [rbp-39h]
  int v43; // [rsp+70h] [rbp-31h]
  int v44; // [rsp+74h] [rbp-2Dh]
  BerElement *ptr; // [rsp+78h] [rbp-29h] BYREF
  __int64 v46; // [rsp+80h] [rbp-21h]
  char Buffer[40]; // [rsp+88h] [rbp-19h] BYREF

  v5 = 0;
  v6 = ld;
  ptr = 0;
  v41 = 0;
  v7 = 0;
  v46 = a4;
  v8 = a4;
  v44 = 5;
  v10 = operator new(0xA0u);
  v42 = v10;
  v11 = v10;
  if ( v10 )
  {
    v12 = 1;
    memset_0(v10, 0, 0xA0u);
    v43 = 10;
  }
  else
  {
    v43 = 0;
    SetLastError(0x8007000E);
    v12 = 0;
  }
  Size = 0;
  Size_4 = 0;
  v34 = 0;
  if ( a5 && *a5 > 0x10u )
    v34 = a5[4];
  entry = ldap_first_entry(v6, res);
  v13 = entry;
  v37 = 0;
  if ( entry )
  {
    while ( v12 )
    {
      v14 = a3 & 0x8000;
      if ( a3 < 0 )
      {
        _ltoa(v5, Buffer, 10);
        v15 = -1;
        do
          ++v15;
        while ( Buffer[v15] );
        Size = v15 + 1;
      }
      attributeA = ldap_first_attributeA(v6, v13, &ptr);
      if ( attributeA )
      {
        do
        {
          if ( !v12 )
            break;
          values_lenA = ldap_get_values_lenA(ld, v13, attributeA);
          vals = values_lenA;
          v12 &= -(values_lenA != 0);
          if ( v12 )
          {
            v18 = 0;
            for ( i = 0; ; i = v18 )
            {
              v19 = values_lenA[v18];
              if ( !v19 )
                goto LABEL_32;
              bv_len = v19->bv_len;
              v21 = bv_len + Size_4;
              Size_4 = v21;
              if ( v21 < (unsigned int)bv_len )
              {
                SetLastError(0x216u);
                goto LABEL_41;
              }
              if ( v34 && v21 > v34 )
              {
                I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> Exceeded MaxUrlRetrievalByteCount for: Ldap Url\n");
                SetLastError(0xDu);
                CryptDiagAddActionWithLastError(L"CheckMaxUrlRetrievalByteCount");
LABEL_41:
                v12 = 0;
                goto LABEL_32;
              }
              if ( v14 )
              {
                v22 = -1;
                do
                  ++v22;
                while ( attributeA[v22] );
                v35 = v22 + 1;
                v23 = Size + bv_len + v22 + 1;
                if ( v23 < (unsigned int)bv_len )
                {
                  v28 = 534;
                  goto LABEL_43;
                }
                values_lenA = vals;
              }
              else
              {
                v35 = 0;
                v23 = bv_len;
              }
              v24 = (unsigned __int8 *)CryptMemAlloc(v23);
              v25 = v24;
              if ( !v24 )
                break;
              v26 = v24;
              if ( a3 < 0 )
              {
                memcpy_0(v24, Buffer, Size);
                v18 = (unsigned __int64)&v25[Size];
                memcpy_0((void *)v18, attributeA, v35);
                v26 = (unsigned __int8 *)(v18 + v35);
                LODWORD(v18) = i;
                values_lenA = vals;
              }
              memcpy_0(v26, values_lenA[(unsigned int)v18]->bv_val, bv_len);
              v12 = CCryptBlobArray::AddBlob((CCryptBlobArray *)&v41, v23, v25, v27);
              if ( !v12 )
              {
                CryptMemFree(v25);
                goto LABEL_44;
              }
              v14 = a3 & 0x8000;
              v18 = (unsigned int)(v18 + 1);
            }
            v28 = -2147024882;
LABEL_43:
            SetLastError(v28);
            v12 = 0;
LABEL_44:
            v14 = a3 & 0x8000;
LABEL_32:
            v13 = entry;
          }
          else
          {
            v12 = 0;
          }
          ldap_value_free_len(vals);
          attributeA = ldap_next_attributeA(ld, v13, ptr);
        }
        while ( attributeA );
        v5 = v37;
      }
      v6 = ld;
      ++v5;
      entry = ldap_next_entry(ld, v13);
      v37 = v5;
      v13 = entry;
      if ( !entry )
      {
        v11 = v42;
        v7 = v41;
        v8 = v46;
        goto LABEL_37;
      }
    }
    v11 = v42;
    v7 = v41;
  }
  else
  {
LABEL_37:
    if ( v12 )
    {
      if ( v7 )
      {
        *(_DWORD *)v8 = v7;
        *(_QWORD *)(v8 + 8) = v11;
      }
      else
      {
        operator delete(v11);
        SetLastError(0x80092004);
        return 0;
      }
      return v12;
    }
  }
  for ( j = 0; j < v7; ++j )
    CryptMemFree(*((LPVOID *)v11 + 2 * j + 1));
  operator delete(v11);
  return v12;
}

```

## disassembly

```asm
0x180011eb4  mov     [rsp-8+arg_10], rbx
0x180011eb9  push    rbp
0x180011eba  push    rsi
0x180011ebb  push    rdi
0x180011ebc  push    r12
0x180011ebe  push    r13
0x180011ec0  push    r14
0x180011ec2  push    r15
0x180011ec4  lea     rbp, [rsp-1Fh]
0x180011ec9  sub     rsp, 0C0h
0x180011ed0  mov     rax, cs:__security_cookie
0x180011ed7  xor     rax, rsp
0x180011eda  mov     [rbp+4Fh+var_40], rax
0x180011ede  xor     r15d, r15d
0x180011ee1  mov     [rbp+4Fh+ExternalHandle], rcx
0x180011ee5  mov     r13, rcx
0x180011ee8  mov     [rbp+4Fh+ptr], r15
0x180011eec  mov     ecx, 0A0h; uBytes
0x180011ef1  mov     [rbp+4Fh+var_90], r15d
0x180011ef5  mov     edi, r15d
0x180011ef8  mov     [rbp+4Fh+var_70], r9
0x180011efc  mov     r12, r9
0x180011eff  mov     [rbp+4Fh+var_A8], r8d
0x180011f03  mov     r14, rdx
0x180011f06  mov     [rbp+4Fh+var_7C], 5
0x180011f0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011f12  mov     [rbp+4Fh+var_88], rax
0x180011f16  mov     rbx, rax
0x180011f19  test    rax, rax
0x180011f1c  jz      short loc_180011F3B
0x180011f1e  xor     edx, edx; Val
0x180011f20  lea     esi, [r15+1]
0x180011f24  mov     r8d, 0A0h; Size
0x180011f2a  mov     rcx, rax; void *
0x180011f2d  call    memset_0
0x180011f32  mov     [rbp+4Fh+var_80], 0Ah
0x180011f39  jmp     short loc_180011F4D
0x180011f3b  mov     ecx, 8007000Eh; dwErrCode
0x180011f40  mov     [rbp+4Fh+var_80], r15d
0x180011f44  call    cs:__imp_SetLastError
0x180011f4a  mov     esi, r15d
0x180011f4d  mov     rax, [rbp+4Fh+arg_20]
0x180011f51  mov     dword ptr [rbp+4Fh+Size], r15d
0x180011f55  mov     dword ptr [rbp+4Fh+Size+4], r15d
0x180011f59  mov     [rbp+4Fh+var_B8], r15d
0x180011f5d  test    rax, rax
0x180011f60  jz      short loc_180011F6D
0x180011f62  cmp     dword ptr [rax], 10h
0x180011f65  jbe     short loc_180011F6D
0x180011f67  mov     eax, [rax+10h]
0x180011f6a  mov     [rbp+4Fh+var_B8], eax
0x180011f6d  mov     rdx, r14; res
0x180011f70  mov     rcx, r13; ld
0x180011f73  call    cs:__imp_ldap_first_entry
0x180011f79  mov     [rbp+4Fh+entry], rax
0x180011f7d  mov     r14, rax
0x180011f80  mov     [rbp+4Fh+var_AC], r15d
0x180011f84  test    rax, rax
0x180011f87  jz      loc_180012181
0x180011f8d  test    esi, esi
0x180011f8f  jz      loc_180012206
0x180011f95  mov     r12d, [rbp+4Fh+var_A8]
0x180011f99  and     r12d, 8000h
0x180011fa0  mov     [rsp+0F0h+var_D0], r12d
0x180011fa5  jz      short loc_180011FD0
0x180011fa7  mov     r8d, 0Ah; Radix
0x180011fad  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x180011fb1  mov     ecx, r15d; Value
0x180011fb4  call    cs:__imp__ltoa
0x180011fba  lea     rcx, [rbp+4Fh+Buffer]
0x180011fbe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011fc2  inc     rax
0x180011fc5  cmp     byte ptr [rcx+rax], 0
0x180011fc9  jnz     short loc_180011FC2
0x180011fcb  inc     eax
0x180011fcd  mov     dword ptr [rbp+4Fh+Size], eax
0x180011fd0  lea     r8, [rbp+4Fh+ptr]; ptr
0x180011fd4  mov     rdx, r14; entry
0x180011fd7  mov     rcx, r13; ld
0x180011fda  call    cs:__imp_ldap_first_attributeA
0x180011fe0  mov     r13, rax
0x180011fe3  test    rax, rax
0x180011fe6  jz      loc_18001214F
0x180011fec  test    esi, esi
0x180011fee  jz      loc_18001214B
0x180011ff4  mov     rcx, [rbp+4Fh+ExternalHandle]; ExternalHandle
0x180011ff8  mov     r8, r13; attr
0x180011ffb  mov     rdx, r14; Message
0x180011ffe  call    cs:__imp_ldap_get_values_lenA
0x180012004  mov     rbx, rax
0x180012007  mov     [rbp+4Fh+vals], rax
0x18001200b  neg     rax
0x18001200e  sbb     ecx, ecx
0x180012010  and     esi, ecx
0x180012012  jz      loc_1800121FF
0x180012018  xor     edi, edi
0x18001201a  mov     dword ptr [rbp+4Fh+var_B4+4], edi
0x18001201d  mov     rax, [rbx+rdi*8]
0x180012021  test    rax, rax
0x180012024  jz      loc_180012120
0x18001202a  mov     r15d, [rax]
0x18001202d  mov     eax, dword ptr [rbp+4Fh+Size+4]
0x180012030  add     eax, r15d
0x180012033  mov     dword ptr [rbp+4Fh+Size+4], eax
0x180012036  cmp     eax, r15d
0x180012039  jb      loc_1800121F2
0x18001203f  mov     ecx, [rbp+4Fh+var_B8]
0x180012042  test    ecx, ecx
0x180012044  jz      short loc_18001204E
0x180012046  cmp     eax, ecx
0x180012048  ja      loc_18001219F
0x18001204e  test    r12d, r12d
0x180012051  jz      short loc_180012087
0x180012053  test    r13, r13
0x180012056  jz      short loc_180012068
0x180012058  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001205c  inc     rax
0x18001205f  cmp     byte ptr [rax+r13], 0
0x180012064  jnz     short loc_18001205C
0x180012066  jmp     short loc_18001206A
0x180012068  xor     eax, eax
0x18001206a  lea     ebx, [rax+1]
0x18001206d  lea     r12d, [r15+rbx]
0x180012071  mov     dword ptr [rbp+4Fh+var_B4], ebx
0x180012074  add     r12d, dword ptr [rbp+4Fh+Size]
0x180012078  cmp     r12d, r15d
0x18001207b  jb      loc_1800121C9
0x180012081  mov     rbx, [rbp+4Fh+vals]
0x180012085  jmp     short loc_180012091
0x180012087  mov     dword ptr [rbp+4Fh+var_B4], 0
0x18001208e  mov     r12d, r15d
0x180012091  mov     ecx, r12d; cbSize
0x180012094  call    cs:__imp_CryptMemAlloc
0x18001209a  mov     r14, rax
0x18001209d  test    rax, rax
0x1800120a0  jz      loc_1800121EB
0x1800120a6  cmp     [rsp+0F0h+var_D0], 0
0x1800120ab  mov     rcx, rax; void *
0x1800120ae  jz      short loc_1800120DF
0x1800120b0  mov     ebx, dword ptr [rbp+4Fh+Size]
0x1800120b3  lea     rdx, [rbp+4Fh+Buffer]; Src
0x1800120b7  mov     r8d, ebx; Size
0x1800120ba  call    memcpy_0
0x1800120bf  lea     rdi, [rbx+r14]
0x1800120c3  mov     rdx, r13; Src
0x1800120c6  mov     ebx, dword ptr [rbp+4Fh+var_B4]
0x1800120c9  mov     rcx, rdi; void *
0x1800120cc  mov     r8d, ebx; Size
0x1800120cf  call    memcpy_0
0x1800120d4  lea     rcx, [rdi+rbx]; void *
0x1800120d8  mov     edi, dword ptr [rbp+4Fh+var_B4+4]
0x1800120db  mov     rbx, [rbp+4Fh+vals]
0x1800120df  mov     edx, edi
0x1800120e1  mov     r8, r15; Size
0x1800120e4  mov     rdx, [rbx+rdx*8]
0x1800120e8  mov     rdx, [rdx+8]; Src
0x1800120ec  call    memcpy_0
0x1800120f1  test    esi, esi
0x1800120f3  jz      short loc_18001210E
0x1800120f5  mov     r8, r14; unsigned __int8 *
0x1800120f8  lea     rcx, [rbp+4Fh+var_90]; this
0x1800120fc  mov     edx, r12d; unsigned int
0x1800120ff  call    ?AddBlob@CCryptBlobArray@@QEAAHKPEAEH@Z; CCryptBlobArray::AddBlob(ulong,uchar *,int)
0x180012104  mov     esi, eax
0x180012106  test    eax, eax
0x180012108  jz      loc_1800121E0
0x18001210e  mov     r12d, [rsp+0F0h+var_D0]
0x180012113  inc     edi
0x180012115  mov     dword ptr [rbp+4Fh+var_B4+4], edi
0x180012118  test    esi, esi
0x18001211a  jnz     loc_18001201D
0x180012120  mov     r14, [rbp+4Fh+entry]
0x180012124  mov     rcx, [rbp+4Fh+vals]; vals
0x180012128  call    cs:__imp_ldap_value_free_len
0x18001212e  mov     r8, [rbp+4Fh+ptr]; ptr
0x180012132  mov     rdx, r14; entry
0x180012135  mov     rcx, [rbp+4Fh+ExternalHandle]; ld
0x180012139  call    cs:__imp_ldap_next_attributeA
0x18001213f  mov     r13, rax
0x180012142  test    rax, rax
0x180012145  jnz     loc_180011FEC
0x18001214b  mov     r15d, [rbp+4Fh+var_AC]
0x18001214f  mov     r13, [rbp+4Fh+ExternalHandle]
0x180012153  mov     rdx, r14; entry
0x180012156  mov     rcx, r13; ld
0x180012159  call    cs:__imp_ldap_next_entry
0x18001215f  inc     r15d
0x180012162  mov     [rbp+4Fh+entry], rax
0x180012166  mov     [rbp+4Fh+var_AC], r15d
0x18001216a  mov     r14, rax
0x18001216d  test    rax, rax
0x180012170  jnz     loc_180011F8D
0x180012176  mov     rbx, [rbp+4Fh+var_88]
0x18001217a  mov     edi, [rbp+4Fh+var_90]
0x18001217d  mov     r12, [rbp+4Fh+var_70]
0x180012181  test    esi, esi
0x180012183  jz      loc_18001220D
0x180012189  test    edi, edi
0x18001218b  jz      loc_18001225E
0x180012191  mov     [r12], edi
0x180012195  mov     [r12+8], rbx
0x18001219a  jmp     loc_180012235
0x18001219f  lea     rcx, aCryptnetDllExc; "CRYPTNET.DLL --> Exceeded MaxUrlRetriev"...
0x1800121a6  call    ?I_CryptNetDebugErrorPrintfA@@YAXPEBDZZ; I_CryptNetDebugErrorPrintfA(char const *,...)
0x1800121ab  mov     ecx, 0Dh; dwErrCode
0x1800121b0  call    cs:__imp_SetLastError
0x1800121b6  lea     rcx, aCheckmaxurlret; "CheckMaxUrlRetrievalByteCount"
0x1800121bd  call    CryptDiagAddActionWithLastError
0x1800121c2  xor     esi, esi
0x1800121c4  jmp     loc_180012120
0x1800121c9  mov     ecx, 216h; dwErrCode
0x1800121ce  call    cs:__imp_SetLastError
0x1800121d4  xor     esi, esi
0x1800121d6  mov     r12d, [rsp+0F0h+var_D0]
0x1800121db  jmp     loc_180012120
0x1800121e0  mov     rcx, r14; pv
0x1800121e3  call    cs:__imp_CryptMemFree
0x1800121e9  jmp     short loc_1800121D6
0x1800121eb  mov     ecx, 8007000Eh
0x1800121f0  jmp     short loc_1800121CE
0x1800121f2  mov     ecx, 216h; dwErrCode
0x1800121f7  call    cs:__imp_SetLastError
0x1800121fd  jmp     short loc_1800121C2
0x1800121ff  xor     esi, esi
0x180012201  jmp     loc_180012124
0x180012206  mov     rbx, [rbp+4Fh+var_88]
0x18001220a  mov     edi, [rbp+4Fh+var_90]
0x18001220d  xor     r14d, r14d
0x180012210  test    edi, edi
0x180012212  jz      short loc_18001222D
0x180012214  mov     ecx, r14d
0x180012217  add     rcx, rcx
0x18001221a  mov     rcx, [rbx+rcx*8+8]; pv
0x18001221f  call    cs:__imp_CryptMemFree
0x180012225  inc     r14d
0x180012228  cmp     r14d, edi
0x18001222b  jb      short loc_180012214
0x18001222d  mov     rcx, rbx; hMem
0x180012230  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012235  mov     eax, esi
0x180012237  mov     rcx, [rbp+4Fh+var_40]
0x18001223b  xor     rcx, rsp; StackCookie
0x18001223e  call    __security_check_cookie
0x180012243  mov     rbx, [rsp+0F0h+arg_10]
0x18001224b  add     rsp, 0C0h
0x180012252  pop     r15
0x180012254  pop     r14
0x180012256  pop     r13
0x180012258  pop     r12
0x18001225a  pop     rdi
0x18001225b  pop     rsi
0x18001225c  pop     rbp
0x18001225d  retn
0x18001225e  xor     esi, esi
0x180012260  test    edi, edi
0x180012262  jz      short loc_18001227A
0x180012264  mov     ecx, esi
0x180012266  add     rcx, rcx
0x180012269  mov     rcx, [rbx+rcx*8+8]; pv
0x18001226e  call    cs:__imp_CryptMemFree
0x180012274  inc     esi
0x180012276  cmp     esi, edi
0x180012278  jb      short loc_180012264
0x18001227a  mov     rcx, rbx; hMem
0x18001227d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012282  mov     ecx, 80092004h; dwErrCode
0x180012287  call    cs:__imp_SetLastError
0x18001228d  xor     esi, esi
0x18001228f  jmp     short loc_180012235
```
