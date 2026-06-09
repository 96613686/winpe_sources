# DRMDeconstructCertificateChain

- ea: `0x180038ff0`
- end: `0x180039148`
- name: `DRMDeconstructCertificateChain`
- size: `344`
- prototype: `HRESULT __stdcall(PWSTR wszChain, UINT iWhich, UINT *pcCert, PWSTR wszCert)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001fbdc`
- `0x1800325b0`
- `0x1800338a0`
- `0x180039a5c`

## callees

- `0x18000420c`
- `0x1800046c8`
- `0x180038ff0`
- `0x18004cdb4`

## import_xrefs

- `msvcrt!wcsstr` at `0x180039044`
- `msvcrt!wcsstr` at `0x180039059`
- `msvcrt!wcsstr` at `0x180039077`
- `msvcrt!wcsstr` at `0x18003909c`
- `msvcrt!wcsstr` at `0x1800390bc`
- `msvcrt!wcsstr` at `0x180039044`
- `msvcrt!wcsstr` at `0x180039059`
- `msvcrt!wcsstr` at `0x180039077`
- `msvcrt!wcsstr` at `0x18003909c`
- `msvcrt!wcsstr` at `0x1800390bc`

## string_xrefs

- `0x18003903a`: `<?xml version="1.0"`

## pseudocode

```c
HRESULT __stdcall DRMDeconstructCertificateChain(PWSTR wszChain, UINT iWhich, UINT *pcCert, PWSTR wszCert)
{
  __int64 v8; // r8
  __int64 v9; // r9
  wchar_t *v10; // rax
  const wchar_t *v11; // rbx
  UINT v12; // esi
  const wchar_t *i; // rcx
  const unsigned __int16 *v14; // rbp
  wchar_t *v15; // rax
  wchar_t *v16; // rax
  HRESULT v17; // ebx
  __int64 v19; // rdi
  __int64 v20; // rsi
  UINT v21; // r14d
  unsigned int v22[18]; // [rsp+20h] [rbp-48h] BYREF

  _RTLTRACE("[msdrm]:+DRMDeconstructCertificateChain iWhich = %d\n", iWhich);
  v22[0] = 0;
  if ( (unsigned __int8)DRMIsValidStringT<unsigned short>(wszChain, 0, v8, v9) )
  {
    if ( pcCert )
    {
      if ( wcsstr(wszChain, L"<?xml version=\"1.0\"") )
      {
        v10 = wcsstr(wszChain, L"<CERTIFICATECHAIN>");
        if ( v10 )
        {
          v11 = v10 + 18;
          if ( v10 != (wchar_t *)-36LL )
          {
            if ( wcsstr(v10 + 18, L"</CERTIFICATECHAIN>") )
            {
              v12 = 0;
              for ( i = v11; ; i = v15 + 14 )
              {
                v16 = wcsstr(i, L"<CERTIFICATE>");
                if ( !v16 )
                  break;
                v14 = v16 + 13;
                if ( v16 == (wchar_t *)-26LL )
                  break;
                v15 = wcsstr(v16 + 13, L"</CERTIFICATE>");
                if ( !v15 )
                  break;
                if ( v12 >= iWhich )
                {
                  v19 = v15 - v14;
                  v17 = UDBase64ToBinW(v19, v14, v22, 0);
                  if ( v17 < 0 )
                    goto LABEL_14;
                  v20 = v22[0] >> 1;
                  v21 = v20 + 1;
                  if ( wszCert )
                  {
                    if ( *pcCert >= v21 )
                    {
                      v17 = UDBase64ToBinW(v19, v14, v22, (unsigned __int8 *)wszCert);
                      if ( v17 < 0 )
                        goto LABEL_14;
                      wszCert[v20] = 0;
                    }
                    else
                    {
                      v17 = -2147024774;
                    }
                  }
                  *pcCert = v21;
                  goto LABEL_14;
                }
                ++v12;
              }
            }
          }
        }
      }
    }
  }
  v17 = -2147024809;
LABEL_14:
  _RTLTRACE("[msdrm]:-DRMDeconstructCertificateChain HR=%x\n", v17);
  return v17;
}

```

## disassembly

```asm
0x180038ff0  push    rbx
0x180038ff2  push    rbp
0x180038ff3  push    rsi
0x180038ff4  push    rdi
0x180038ff5  push    r12
0x180038ff7  push    r14
0x180038ff9  push    r15
0x180038ffb  sub     rsp, 30h
0x180038fff  mov     rbx, rcx
0x180039002  mov     r12, r9
0x180039005  lea     rcx, aMsdrmDrmdecons; "[msdrm]:+DRMDeconstructCertificateChain"...
0x18003900c  mov     r15, r8
0x18003900f  mov     r14d, edx
0x180039012  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180039017  xor     edx, edx
0x180039019  mov     [rsp+68h+var_48], 0
0x180039021  mov     rcx, rbx
0x180039024  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180039029  test    al, al
0x18003902b  jz      loc_1800390C7
0x180039031  test    r15, r15
0x180039034  jz      loc_1800390C7
0x18003903a  lea     rdx, ?g_wszXMLHEADERVersion@@3QBGB; "<?xml version=\"1.0\""
0x180039041  mov     rcx, rbx; Str
0x180039044  call    cs:__imp_wcsstr
0x18003904a  test    rax, rax
0x18003904d  jz      short loc_1800390C7
0x18003904f  lea     rdx, ?g_wszCertificateChainOpenNode@@3QBGB; "<CERTIFICATECHAIN>"
0x180039056  mov     rcx, rbx; Str
0x180039059  call    cs:__imp_wcsstr
0x18003905f  test    rax, rax
0x180039062  jz      short loc_1800390C7
0x180039064  lea     rbx, [rax+24h]
0x180039068  test    rbx, rbx
0x18003906b  jz      short loc_1800390C7
0x18003906d  lea     rdx, ?g_wszCertificateChainCloseNode@@3QBGB; "</CERTIFICATECHAIN>"
0x180039074  mov     rcx, rbx; Str
0x180039077  call    cs:__imp_wcsstr
0x18003907d  test    rax, rax
0x180039080  jz      short loc_1800390C7
0x180039082  xor     esi, esi
0x180039084  mov     rcx, rbx
0x180039087  jmp     short loc_1800390B5
0x180039089  lea     rbp, [rax+1Ah]
0x18003908d  test    rbp, rbp
0x180039090  jz      short loc_1800390C7
0x180039092  lea     rdx, ?g_wszCertificateCloseNode@@3QBGB; "</CERTIFICATE>"
0x180039099  mov     rcx, rbp; Str
0x18003909c  call    cs:__imp_wcsstr
0x1800390a2  mov     rdi, rax
0x1800390a5  test    rax, rax
0x1800390a8  jz      short loc_1800390C7
0x1800390aa  cmp     esi, r14d
0x1800390ad  jnb     short loc_1800390EB
0x1800390af  inc     esi
0x1800390b1  lea     rcx, [rax+1Ch]; Str
0x1800390b5  lea     rdx, ?g_wszCertificateOpenNode@@3QBGB; "<CERTIFICATE>"
0x1800390bc  call    cs:__imp_wcsstr
0x1800390c2  test    rax, rax
0x1800390c5  jnz     short loc_180039089
0x1800390c7  mov     ebx, 80070057h
0x1800390cc  mov     edx, ebx
0x1800390ce  lea     rcx, aMsdrmDrmdecons_0; "[msdrm]:-DRMDeconstructCertificateChain"...
0x1800390d5  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800390da  mov     eax, ebx
0x1800390dc  add     rsp, 30h
0x1800390e0  pop     r15
0x1800390e2  pop     r14
0x1800390e4  pop     r12
0x1800390e6  pop     rdi
0x1800390e7  pop     rsi
0x1800390e8  pop     rbp
0x1800390e9  pop     rbx
0x1800390ea  retn
0x1800390eb  sub     rdi, rbp
0x1800390ee  lea     r8, [rsp+68h+var_48]; unsigned int *
0x1800390f3  sar     rdi, 1
0x1800390f6  xor     r9d, r9d; unsigned __int8 *
0x1800390f9  mov     ecx, edi; unsigned int
0x1800390fb  mov     rdx, rbp; unsigned __int16 *
0x1800390fe  call    ?UDBase64ToBinW@@YAJIPEBGPEAIPEAE@Z; UDBase64ToBinW(uint,ushort const *,uint *,uchar *)
0x180039103  mov     ebx, eax
0x180039105  test    eax, eax
0x180039107  js      short loc_1800390CC
0x180039109  mov     esi, [rsp+68h+var_48]
0x18003910d  shr     esi, 1
0x18003910f  lea     r14d, [rsi+1]
0x180039113  test    r12, r12
0x180039116  jz      short loc_180039143
0x180039118  cmp     [r15], r14d
0x18003911b  jnb     short loc_180039124
0x18003911d  mov     ebx, 8007007Ah
0x180039122  jmp     short loc_180039143
0x180039124  mov     r9, r12; unsigned __int8 *
0x180039127  lea     r8, [rsp+68h+var_48]; unsigned int *
0x18003912c  mov     rdx, rbp; unsigned __int16 *
0x18003912f  mov     ecx, edi; unsigned int
0x180039131  call    ?UDBase64ToBinW@@YAJIPEBGPEAIPEAE@Z; UDBase64ToBinW(uint,ushort const *,uint *,uchar *)
0x180039136  mov     ebx, eax
0x180039138  test    eax, eax
0x18003913a  js      short loc_1800390CC
0x18003913c  xor     eax, eax
0x18003913e  mov     [r12+rsi*2], ax
0x180039143  mov     [r15], r14d
0x180039146  jmp     short loc_1800390CC
```
