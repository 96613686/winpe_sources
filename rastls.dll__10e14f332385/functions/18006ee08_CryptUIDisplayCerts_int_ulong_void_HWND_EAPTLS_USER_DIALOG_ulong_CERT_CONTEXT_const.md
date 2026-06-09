# CryptUIDisplayCerts(int,ulong,void *,HWND__ *,_EAPTLS_USER_DIALOG *,ulong *,_CERT_CONTEXT const * * *)

- ea: `0x18006ee08`
- end: `0x18006f07b`
- name: `?CryptUIDisplayCerts@@YAKHKPEAXPEAUHWND__@@PEAU_EAPTLS_USER_DIALOG@@PEAKPEAPEAPEBU_CERT_CONTEXT@@@Z`
- size: `627`
- prototype: `unsigned int(int, unsigned int, void *, HWND, struct _EAPTLS_USER_DIALOG *, unsigned int *, const struct _CERT_CONTEXT ***)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800136f0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f350`
- `0x18006e59c`
- `0x18006ee08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ee46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006efa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ee46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006efa9`
- `CRYPT32!CertCloseStore` at `0x18006f05b`
- `CRYPT32!CertCloseStore` at `0x18006f05b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18006ef9f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18006ef9f`
- `CRYPT32!CertFreeCertificateContext` at `0x18006f064`
- `CRYPT32!CertFreeCertificateContext` at `0x18006f064`
- `CRYPT32!CertOpenStore` at `0x18006ee35`
- `CRYPT32!CertOpenStore` at `0x18006ee35`
- `ext-ms-win-security-cryptui-l1-1-0!CryptUIDlgSelectCertificateFromStore` at `0x18006ef49`
- `ext-ms-win-security-cryptui-l1-1-0!CryptUIDlgSelectCertificateFromStore` at `0x18006ef49`

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
0x18006ee08  push    rbx
0x18006ee0a  push    rbp
0x18006ee0b  push    rsi
0x18006ee0c  push    rdi
0x18006ee0d  push    r12
0x18006ee0f  push    r14
0x18006ee11  push    r15
0x18006ee13  sub     rsp, 40h
0x18006ee17  mov     r12, r9
0x18006ee1a  mov     [rsp+78h+pvPara], 0; pvPara
0x18006ee23  xor     r9d, r9d; dwFlags
0x18006ee26  mov     r15, r8
0x18006ee29  xor     r8d, r8d; hCryptProv
0x18006ee2c  mov     edx, 10001h; dwEncodingType
0x18006ee31  lea     ecx, [r9+2]; lpszStoreProvider
0x18006ee35  call    cs:__imp_CertOpenStore
0x18006ee3b  mov     rbp, rax
0x18006ee3e  test    rax, rax
0x18006ee41  jnz     short loc_18006EE80
0x18006ee43  xor     r15d, r15d
0x18006ee46  call    cs:__imp_GetLastError
0x18006ee4c  mov     edi, eax
0x18006ee4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ee55  lea     rsi, WPP_GLOBAL_Control
0x18006ee5c  cmp     rcx, rsi
0x18006ee5f  jz      loc_18006F061
0x18006ee65  mov     rcx, [rcx+10h]
0x18006ee69  lea     edx, [rbp+22h]
0x18006ee6c  mov     r9d, eax
0x18006ee6f  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006ee76  call    WPP_SF_d
0x18006ee7b  jmp     loc_18006F061
0x18006ee80  mov     rbx, [rsp+78h+arg_20]
0x18006ee88  test    byte ptr [rbx], 4
0x18006ee8b  jz      short loc_18006EEBB
0x18006ee8d  mov     rdi, [rbx+18h]
0x18006ee91  jmp     short loc_18006EEB0
0x18006ee93  mov     r8, [rdi+10h]; struct _EAPTLS_CERT_NODE *
0x18006ee97  test    r8, r8
0x18006ee9a  jz      short loc_18006EEAD
0x18006ee9c  cmp     r8, [rbx+10h]
0x18006eea0  jz      short loc_18006EEAD
0x18006eea2  mov     rdx, rbp; HCERTSTORE
0x18006eea5  mov     rcx, r15; hCertStore
0x18006eea8  call    ?AddCertToStore@@YAXPEAX0PEAU_EAPTLS_CERT_NODE@@@Z; AddCertToStore(void *,void *,_EAPTLS_CERT_NODE *)
0x18006eead  mov     rdi, [rdi]
0x18006eeb0  test    rdi, rdi
0x18006eeb3  jnz     short loc_18006EE93
0x18006eeb5  lea     r14, [rbx+8]
0x18006eeb9  jmp     short loc_18006EEE0
0x18006eebb  lea     r14, [rbx+8]
0x18006eebf  mov     rdi, [r14]
0x18006eec2  jmp     short loc_18006EEDB
0x18006eec4  cmp     rdi, [rbx+10h]
0x18006eec8  jz      short loc_18006EED8
0x18006eeca  mov     r8, rdi; struct _EAPTLS_CERT_NODE *
0x18006eecd  mov     rdx, rbp; HCERTSTORE
0x18006eed0  mov     rcx, r15; hCertStore
0x18006eed3  call    ?AddCertToStore@@YAXPEAX0PEAU_EAPTLS_CERT_NODE@@@Z; AddCertToStore(void *,void *,_EAPTLS_CERT_NODE *)
0x18006eed8  mov     rdi, [rdi]
0x18006eedb  test    rdi, rdi
0x18006eede  jnz     short loc_18006EEC4
0x18006eee0  mov     r9, [rbx+10h]
0x18006eee4  lea     rsi, WPP_GLOBAL_Control
0x18006eeeb  test    r9, r9
0x18006eeee  jz      short loc_18006EF24
0x18006eef0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006eef7  cmp     rcx, rsi
0x18006eefa  jz      short loc_18006EF15
0x18006eefc  mov     r9, [r9+20h]
0x18006ef00  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006ef07  mov     rcx, [rcx+10h]
0x18006ef0b  mov     edx, 23h ; '#'
0x18006ef10  call    WPP_SF_S
0x18006ef15  mov     r8, [rbx+10h]; struct _EAPTLS_CERT_NODE *
0x18006ef19  mov     rdx, rbp; HCERTSTORE
0x18006ef1c  mov     rcx, r15; hCertStore
0x18006ef1f  call    ?AddCertToStore@@YAXPEAX0PEAU_EAPTLS_CERT_NODE@@@Z; AddCertToStore(void *,void *,_EAPTLS_CERT_NODE *)
0x18006ef24  mov     [rsp+78h+pvReserved], 0; pvReserved
0x18006ef2d  xor     r9d, r9d; pwszDisplayString
0x18006ef30  mov     [rsp+78h+dwFlags], 0; dwFlags
0x18006ef38  xor     r8d, r8d; pwszTitle
0x18006ef3b  mov     rdx, r12; hwnd
0x18006ef3e  mov     dword ptr [rsp+78h+pvPara], 0; dwDontUseColumn
0x18006ef46  mov     rcx, rbp; hCertStore
0x18006ef49  call    cs:__imp_CryptUIDlgSelectCertificateFromStore
0x18006ef4f  mov     r15, rax
0x18006ef52  test    rax, rax
0x18006ef55  jnz     short loc_18006EF80
0x18006ef57  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ef5e  cmp     rcx, rsi
0x18006ef61  jz      short loc_18006EF76
0x18006ef63  mov     rcx, [rcx+10h]
0x18006ef67  lea     edx, [rax+24h]
0x18006ef6a  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006ef71  call    WPP_SF_
0x18006ef76  mov     edi, 4C7h
0x18006ef7b  jmp     loc_18006F056
0x18006ef80  mov     rax, [rbx+20h]
0x18006ef84  mov     edx, 3; dwPropId
0x18006ef89  mov     rcx, r15; pCertContext
0x18006ef8c  mov     dword ptr [rax+10h], 14h
0x18006ef93  mov     r9, [rbx+20h]
0x18006ef97  add     r9, 10h; pcbData
0x18006ef9b  lea     r8, [r9+4]; pvData
0x18006ef9f  call    cs:__imp_CertGetCertificateContextProperty
0x18006efa5  test    eax, eax
0x18006efa7  jnz     short loc_18006EFDB
0x18006efa9  call    cs:__imp_GetLastError
0x18006efaf  mov     edi, eax
0x18006efb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006efb8  cmp     rcx, rsi
0x18006efbb  jz      loc_18006F056
0x18006efc1  mov     rcx, [rcx+10h]
0x18006efc5  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006efcc  mov     edx, 25h ; '%'
0x18006efd1  mov     r9d, eax
0x18006efd4  call    WPP_SF_d
0x18006efd9  jmp     short loc_18006F056
0x18006efdb  xor     edi, edi
0x18006efdd  test    byte ptr [rbx], 4
0x18006efe0  jz      short loc_18006F01F
0x18006efe2  mov     r8, [rbx+18h]
0x18006efe6  test    r8, r8
0x18006efe9  jz      short loc_18006F056
0x18006efeb  mov     rdx, [r8+10h]
0x18006efef  test    rdx, rdx
0x18006eff2  jz      short loc_18006F01A
0x18006eff4  mov     rax, [rbx+20h]
0x18006eff8  mov     rcx, [rdx+0Ch]
0x18006effc  sub     rcx, [rax+14h]
0x18006f000  jnz     short loc_18006F015
0x18006f002  mov     rcx, [rdx+14h]
0x18006f006  sub     rcx, [rax+1Ch]
0x18006f00a  jnz     short loc_18006F015
0x18006f00c  mov     ecx, [rdx+1Ch]
0x18006f00f  mov     eax, [rax+24h]
0x18006f012  sub     rcx, rax
0x18006f015  test    rcx, rcx
0x18006f018  jz      short loc_18006F052
0x18006f01a  mov     r8, [r8]
0x18006f01d  jmp     short loc_18006EFE6
0x18006f01f  mov     rdx, [r14]
0x18006f022  test    rdx, rdx
0x18006f025  jz      short loc_18006F056
0x18006f027  mov     rax, [rbx+20h]
0x18006f02b  mov     rcx, [rdx+0Ch]
0x18006f02f  sub     rcx, [rax+14h]
0x18006f033  jnz     short loc_18006F048
0x18006f035  mov     rcx, [rdx+14h]
0x18006f039  sub     rcx, [rax+1Ch]
0x18006f03d  jnz     short loc_18006F048
0x18006f03f  mov     ecx, [rdx+1Ch]
0x18006f042  mov     eax, [rax+24h]
0x18006f045  sub     rcx, rax
0x18006f048  test    rcx, rcx
0x18006f04b  jz      short loc_18006F052
0x18006f04d  mov     rdx, [rdx]
0x18006f050  jmp     short loc_18006F022
0x18006f052  mov     [rbx+10h], rdx
0x18006f056  xor     edx, edx; dwFlags
0x18006f058  mov     rcx, rbp; hCertStore
0x18006f05b  call    cs:__imp_CertCloseStore
0x18006f061  mov     rcx, r15; pCertContext
0x18006f064  call    cs:__imp_CertFreeCertificateContext
0x18006f06a  mov     eax, edi
0x18006f06c  add     rsp, 40h
0x18006f070  pop     r15
0x18006f072  pop     r14
0x18006f074  pop     r12
0x18006f076  pop     rdi
0x18006f077  pop     rsi
0x18006f078  pop     rbp
0x18006f079  pop     rbx
0x18006f07a  retn
```
