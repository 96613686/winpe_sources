# CryptUIDisplayCerts(int,ulong,void *,HWND__ *,_EAPTLS_USER_DIALOG *,ulong *,_CERT_CONTEXT const * * *)

- ea: `0x1800738b4`
- end: `0x180073b52`
- name: `?CryptUIDisplayCerts@@YAKHKPEAXPEAUHWND__@@PEAU_EAPTLS_USER_DIALOG@@PEAKPEAPEAPEBU_CERT_CONTEXT@@@Z`
- size: `670`
- prototype: `unsigned int(int, unsigned int, void *, HWND, struct _EAPTLS_USER_DIALOG *, unsigned int *, const struct _CERT_CONTEXT ***)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014a70`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180010140`
- `0x180072f38`
- `0x1800738b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800738f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800738f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073a6d`
- `CRYPT32!CertCloseStore` at `0x180073b25`
- `CRYPT32!CertCloseStore` at `0x180073b25`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180073a5d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180073a5d`
- `CRYPT32!CertFreeCertificateContext` at `0x180073b34`
- `CRYPT32!CertFreeCertificateContext` at `0x180073b34`
- `CRYPT32!CertOpenStore` at `0x1800738e1`
- `CRYPT32!CertOpenStore` at `0x1800738e1`
- `ext-ms-win-security-cryptui-l1-1-0!CryptUIDlgSelectCertificateFromStore` at `0x180073a01`
- `ext-ms-win-security-cryptui-l1-1-0!CryptUIDlgSelectCertificateFromStore` at `0x180073a01`

## pseudocode

```c
__int64 __fastcall CryptUIDisplayCerts(__int64 a1, __int64 a2, void *a3, HWND a4, struct _EAPTLS_USER_DIALOG *a5)
{
  HCERTSTORE v7; // rbp
  const CERT_CONTEXT *v8; // r15
  DWORD v9; // eax
  unsigned int v10; // edi
  _QWORD *i; // rdi
  struct _EAPTLS_CERT_NODE *v12; // r8
  __int64 **v13; // r14
  struct _EAPTLS_CERT_NODE *j; // rdi
  __int64 v15; // r9
  const CERT_CONTEXT *v16; // rax
  DWORD LastError; // eax
  _QWORD *k; // r8
  __int64 *m; // rdx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rcx

  v7 = CertOpenStore((LPCSTR)2, 0x10001u, 0, 0, 0);
  if ( v7 )
  {
    if ( (*(_BYTE *)a5 & 4) != 0 )
    {
      for ( i = (_QWORD *)*((_QWORD *)a5 + 3); i; i = (_QWORD *)*i )
      {
        v12 = (struct _EAPTLS_CERT_NODE *)i[2];
        if ( v12 && v12 != *((struct _EAPTLS_CERT_NODE **)a5 + 2) )
          AddCertToStore(a3, v7, v12);
      }
      v13 = (__int64 **)((char *)a5 + 8);
    }
    else
    {
      v13 = (__int64 **)((char *)a5 + 8);
      for ( j = (struct _EAPTLS_CERT_NODE *)*((_QWORD *)a5 + 1); j; j = *(struct _EAPTLS_CERT_NODE **)j )
      {
        if ( j != *((struct _EAPTLS_CERT_NODE **)a5 + 2) )
          AddCertToStore(a3, v7, j);
      }
    }
    v15 = *((_QWORD *)a5 + 2);
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          &WPP_c4e812f99669349517681909258710e2_Traceguids,
          *(_QWORD *)(v15 + 32));
      AddCertToStore(a3, v7, *((struct _EAPTLS_CERT_NODE **)a5 + 2));
    }
    v16 = CryptUIDlgSelectCertificateFromStore(v7, a4, 0, 0, 0, 0, 0);
    v8 = v16;
    if ( v16 )
    {
      *(_DWORD *)(*((_QWORD *)a5 + 4) + 16LL) = 20;
      if ( CertGetCertificateContextProperty(
             v16,
             3u,
             (void *)(*((_QWORD *)a5 + 4) + 20LL),
             (DWORD *)(*((_QWORD *)a5 + 4) + 16LL)) )
      {
        v10 = 0;
        if ( (*(_BYTE *)a5 & 4) != 0 )
        {
          for ( k = (_QWORD *)*((_QWORD *)a5 + 3); k; k = (_QWORD *)*k )
          {
            m = (__int64 *)k[2];
            if ( m )
            {
              v20 = *((_QWORD *)a5 + 4);
              v21 = *(__int64 *)((char *)m + 12) - *(_QWORD *)(v20 + 20);
              if ( !v21 )
              {
                v21 = *(__int64 *)((char *)m + 20) - *(_QWORD *)(v20 + 28);
                if ( !v21 )
                  v21 = *((unsigned int *)m + 7) - (unsigned __int64)*(unsigned int *)(v20 + 36);
              }
              if ( !v21 )
                goto LABEL_44;
            }
          }
        }
        else
        {
          for ( m = *v13; m; m = (__int64 *)*m )
          {
            v22 = *((_QWORD *)a5 + 4);
            v23 = *(__int64 *)((char *)m + 12) - *(_QWORD *)(v22 + 20);
            if ( !v23 )
            {
              v23 = *(__int64 *)((char *)m + 20) - *(_QWORD *)(v22 + 28);
              if ( !v23 )
                v23 = *((unsigned int *)m + 7) - (unsigned __int64)*(unsigned int *)(v22 + 36);
            }
            if ( !v23 )
            {
LABEL_44:
              *((_QWORD *)a5 + 2) = m;
              break;
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_c4e812f99669349517681909258710e2_Traceguids, LastError);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c4e812f99669349517681909258710e2_Traceguids);
      v10 = 1223;
    }
    CertCloseStore(v7, 0);
  }
  else
  {
    v8 = 0;
    v9 = GetLastError();
    v10 = v9;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_c4e812f99669349517681909258710e2_Traceguids, v9);
  }
  CertFreeCertificateContext(v8);
  return v10;
}

```

## disassembly

```asm
0x1800738b4  push    rbx
0x1800738b6  push    rbp
0x1800738b7  push    rsi
0x1800738b8  push    rdi
0x1800738b9  push    r12
0x1800738bb  push    r14
0x1800738bd  push    r15
0x1800738bf  sub     rsp, 40h
0x1800738c3  mov     r12, r9
0x1800738c6  mov     [rsp+78h+pvPara], 0; pvPara
0x1800738cf  xor     r9d, r9d; dwFlags
0x1800738d2  mov     r15, r8
0x1800738d5  xor     r8d, r8d; hCryptProv
0x1800738d8  mov     edx, 10001h; dwEncodingType
0x1800738dd  lea     ecx, [r9+2]; lpszStoreProvider
0x1800738e1  call    cs:__imp_CertOpenStore
0x1800738e8  nop     dword ptr [rax+rax+00h]
0x1800738ed  mov     rbp, rax
0x1800738f0  test    rax, rax
0x1800738f3  jnz     short loc_180073938
0x1800738f5  xor     r15d, r15d
0x1800738f8  call    cs:__imp_GetLastError
0x1800738ff  nop     dword ptr [rax+rax+00h]
0x180073904  mov     edi, eax
0x180073906  mov     rcx, cs:WPP_GLOBAL_Control
0x18007390d  lea     rsi, WPP_GLOBAL_Control
0x180073914  cmp     rcx, rsi
0x180073917  jz      loc_180073B31
0x18007391d  mov     rcx, [rcx+10h]
0x180073921  lea     edx, [rbp+22h]
0x180073924  mov     r9d, eax
0x180073927  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18007392e  call    WPP_SF_d
0x180073933  jmp     loc_180073B31
0x180073938  mov     rbx, [rsp+78h+arg_20]
0x180073940  test    byte ptr [rbx], 4
0x180073943  jz      short loc_180073973
0x180073945  mov     rdi, [rbx+18h]
0x180073949  jmp     short loc_180073968
0x18007394b  mov     r8, [rdi+10h]; struct _EAPTLS_CERT_NODE *
0x18007394f  test    r8, r8
0x180073952  jz      short loc_180073965
0x180073954  cmp     r8, [rbx+10h]
0x180073958  jz      short loc_180073965
0x18007395a  mov     rdx, rbp; HCERTSTORE
0x18007395d  mov     rcx, r15; hCertStore
0x180073960  call    ?AddCertToStore@@YAXPEAX0PEAU_EAPTLS_CERT_NODE@@@Z; AddCertToStore(void *,void *,_EAPTLS_CERT_NODE *)
0x180073965  mov     rdi, [rdi]
0x180073968  test    rdi, rdi
0x18007396b  jnz     short loc_18007394B
0x18007396d  lea     r14, [rbx+8]
0x180073971  jmp     short loc_180073998
0x180073973  lea     r14, [rbx+8]
0x180073977  mov     rdi, [r14]
0x18007397a  jmp     short loc_180073993
0x18007397c  cmp     rdi, [rbx+10h]
0x180073980  jz      short loc_180073990
0x180073982  mov     r8, rdi; struct _EAPTLS_CERT_NODE *
0x180073985  mov     rdx, rbp; HCERTSTORE
0x180073988  mov     rcx, r15; hCertStore
0x18007398b  call    ?AddCertToStore@@YAXPEAX0PEAU_EAPTLS_CERT_NODE@@@Z; AddCertToStore(void *,void *,_EAPTLS_CERT_NODE *)
0x180073990  mov     rdi, [rdi]
0x180073993  test    rdi, rdi
0x180073996  jnz     short loc_18007397C
0x180073998  mov     r9, [rbx+10h]
0x18007399c  lea     rsi, WPP_GLOBAL_Control
0x1800739a3  test    r9, r9
0x1800739a6  jz      short loc_1800739DC
0x1800739a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800739af  cmp     rcx, rsi
0x1800739b2  jz      short loc_1800739CD
0x1800739b4  mov     r9, [r9+20h]
0x1800739b8  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x1800739bf  mov     rcx, [rcx+10h]
0x1800739c3  mov     edx, 23h ; '#'
0x1800739c8  call    WPP_SF_S
0x1800739cd  mov     r8, [rbx+10h]; struct _EAPTLS_CERT_NODE *
0x1800739d1  mov     rdx, rbp; HCERTSTORE
0x1800739d4  mov     rcx, r15; hCertStore
0x1800739d7  call    ?AddCertToStore@@YAXPEAX0PEAU_EAPTLS_CERT_NODE@@@Z; AddCertToStore(void *,void *,_EAPTLS_CERT_NODE *)
0x1800739dc  mov     [rsp+78h+pvReserved], 0; pvReserved
0x1800739e5  xor     r9d, r9d; pwszDisplayString
0x1800739e8  mov     [rsp+78h+dwFlags], 0; dwFlags
0x1800739f0  xor     r8d, r8d; pwszTitle
0x1800739f3  mov     rdx, r12; hwnd
0x1800739f6  mov     dword ptr [rsp+78h+pvPara], 0; dwDontUseColumn
0x1800739fe  mov     rcx, rbp; hCertStore
0x180073a01  call    cs:__imp_CryptUIDlgSelectCertificateFromStore
0x180073a08  nop     dword ptr [rax+rax+00h]
0x180073a0d  mov     r15, rax
0x180073a10  test    rax, rax
0x180073a13  jnz     short loc_180073A3E
0x180073a15  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a1c  cmp     rcx, rsi
0x180073a1f  jz      short loc_180073A34
0x180073a21  mov     rcx, [rcx+10h]
0x180073a25  lea     edx, [rax+24h]
0x180073a28  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180073a2f  call    WPP_SF_
0x180073a34  mov     edi, 4C7h
0x180073a39  jmp     loc_180073B20
0x180073a3e  mov     rax, [rbx+20h]
0x180073a42  mov     edx, 3; dwPropId
0x180073a47  mov     rcx, r15; pCertContext
0x180073a4a  mov     dword ptr [rax+10h], 14h
0x180073a51  mov     r9, [rbx+20h]
0x180073a55  add     r9, 10h; pcbData
0x180073a59  lea     r8, [r9+4]; pvData
0x180073a5d  call    cs:__imp_CertGetCertificateContextProperty
0x180073a64  nop     dword ptr [rax+rax+00h]
0x180073a69  test    eax, eax
0x180073a6b  jnz     short loc_180073AA5
0x180073a6d  call    cs:__imp_GetLastError
0x180073a74  nop     dword ptr [rax+rax+00h]
0x180073a79  mov     edi, eax
0x180073a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a82  cmp     rcx, rsi
0x180073a85  jz      loc_180073B20
0x180073a8b  mov     rcx, [rcx+10h]
0x180073a8f  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180073a96  mov     edx, 25h ; '%'
0x180073a9b  mov     r9d, eax
0x180073a9e  call    WPP_SF_d
0x180073aa3  jmp     short loc_180073B20
0x180073aa5  xor     edi, edi
0x180073aa7  test    byte ptr [rbx], 4
0x180073aaa  jz      short loc_180073AE9
0x180073aac  mov     r8, [rbx+18h]
0x180073ab0  test    r8, r8
0x180073ab3  jz      short loc_180073B20
0x180073ab5  mov     rdx, [r8+10h]
0x180073ab9  test    rdx, rdx
0x180073abc  jz      short loc_180073AE4
0x180073abe  mov     rax, [rbx+20h]
0x180073ac2  mov     rcx, [rdx+0Ch]
0x180073ac6  sub     rcx, [rax+14h]
0x180073aca  jnz     short loc_180073ADF
0x180073acc  mov     rcx, [rdx+14h]
0x180073ad0  sub     rcx, [rax+1Ch]
0x180073ad4  jnz     short loc_180073ADF
0x180073ad6  mov     ecx, [rdx+1Ch]
0x180073ad9  mov     eax, [rax+24h]
0x180073adc  sub     rcx, rax
0x180073adf  test    rcx, rcx
0x180073ae2  jz      short loc_180073B1C
0x180073ae4  mov     r8, [r8]
0x180073ae7  jmp     short loc_180073AB0
0x180073ae9  mov     rdx, [r14]
0x180073aec  test    rdx, rdx
0x180073aef  jz      short loc_180073B20
0x180073af1  mov     rax, [rbx+20h]
0x180073af5  mov     rcx, [rdx+0Ch]
0x180073af9  sub     rcx, [rax+14h]
0x180073afd  jnz     short loc_180073B12
0x180073aff  mov     rcx, [rdx+14h]
0x180073b03  sub     rcx, [rax+1Ch]
0x180073b07  jnz     short loc_180073B12
0x180073b09  mov     ecx, [rdx+1Ch]
0x180073b0c  mov     eax, [rax+24h]
0x180073b0f  sub     rcx, rax
0x180073b12  test    rcx, rcx
0x180073b15  jz      short loc_180073B1C
0x180073b17  mov     rdx, [rdx]
0x180073b1a  jmp     short loc_180073AEC
0x180073b1c  mov     [rbx+10h], rdx
0x180073b20  xor     edx, edx; dwFlags
0x180073b22  mov     rcx, rbp; hCertStore
0x180073b25  call    cs:__imp_CertCloseStore
0x180073b2c  nop     dword ptr [rax+rax+00h]
0x180073b31  mov     rcx, r15; pCertContext
0x180073b34  call    cs:__imp_CertFreeCertificateContext
0x180073b3b  nop     dword ptr [rax+rax+00h]
0x180073b40  mov     eax, edi
0x180073b42  add     rsp, 40h
0x180073b46  pop     r15
0x180073b48  pop     r14
0x180073b4a  pop     r12
0x180073b4c  pop     rdi
0x180073b4d  pop     rsi
0x180073b4e  pop     rbp
0x180073b4f  pop     rbx
0x180073b50  retn
```
