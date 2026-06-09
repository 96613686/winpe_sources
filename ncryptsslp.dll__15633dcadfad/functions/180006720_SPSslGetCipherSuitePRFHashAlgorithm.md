# SPSslGetCipherSuitePRFHashAlgorithm

- ea: `0x180006720`
- end: `0x1800068d9`
- name: `SPSslGetCipherSuitePRFHashAlgorithm`
- size: `441`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005e50`
- `0x180006720`
- `0x1800068e0`
- `0x18000b594`

## string_xrefs

- `0x1800067f4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006840`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800068c0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslGetCipherSuitePRFHashAlgorithm(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int64 a4,
        _WORD *a5,
        int a6)
{
  int v6; // edx
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  unsigned int v9; // ebx
  __int64 v10; // rax
  const wchar_t *v11; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  _WORD *v15; // rcx
  _QWORD *v17; // rcx
  char v18; // [rsp+30h] [rbp-18h]

  if ( a2 < 0x303 || a2 == 65279 )
  {
    v9 = -2146893783;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v9;
    v18 = 99;
    goto LABEL_23;
  }
  v9 = 0;
  if ( SslpValidateProvHandle(a1) )
  {
    if ( !a6 )
    {
      v10 = LookupCipherSuite(v8, v7);
      if ( v10 )
      {
        v11 = *(const wchar_t **)(v10 + 136);
        if ( !v11 || !*v11 )
          v11 = L"SHA256";
        v13 = 2147483646;
        v14 = 64;
        do
        {
          if ( !v13 )
            break;
          if ( !*v11 )
            break;
          *a5++ = *v11++;
          --v13;
          --v14;
        }
        while ( v14 );
        v15 = a5 - 1;
        if ( v14 )
          v15 = a5;
        *v15 = 0;
        return v9;
      }
      v9 = -2146893783;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v9;
      v18 = 124;
LABEL_23:
      WPP_SF_sDsd(
        v17[2],
        a2,
        a3,
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v18);
      return v9;
    }
    v9 = -2146893815;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v7,
        (unsigned int)"Status",
        9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        115);
  }
  else
  {
    v9 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v7,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        108);
  }
  return v9;
}

```

## disassembly

```asm
0x180006720  push    rbx
0x180006722  sub     rsp, 40h
0x180006726  mov     r9d, edx
0x180006729  cmp     edx, 303h
0x18000672f  jb      loc_180006856
0x180006735  cmp     edx, 0FEFFh
0x18000673b  jz      loc_180006856
0x180006741  call    SslpValidateProvHandle
0x180006746  xor     ebx, ebx
0x180006748  test    rax, rax
0x18000674b  jz      loc_180006892
0x180006751  cmp     [rsp+48h+arg_28], ebx
0x180006755  jnz     short loc_1800067CE
0x180006757  mov     edx, r8d
0x18000675a  mov     ecx, r9d
0x18000675d  call    LookupCipherSuite
0x180006762  test    rax, rax
0x180006765  jz      loc_18000681A
0x18000676b  mov     rax, [rax+88h]
0x180006772  test    rax, rax
0x180006775  jz      loc_180006886
0x18000677b  cmp     [rax], bx
0x18000677e  jz      loc_180006886
0x180006784  mov     rdx, [rsp+48h+arg_20]
0x180006789  mov     ecx, 7FFFFFFEh
0x18000678e  mov     r8d, 40h ; '@'
0x180006794  test    rcx, rcx
0x180006797  jz      short loc_1800067B8
0x180006799  movzx   r9d, word ptr [rax]
0x18000679d  test    r9w, r9w
0x1800067a1  jz      short loc_1800067B8
0x1800067a3  mov     [rdx], r9w
0x1800067a7  add     rax, 2
0x1800067ab  add     rdx, 2
0x1800067af  dec     rcx
0x1800067b2  sub     r8, 1
0x1800067b6  jnz     short loc_180006794
0x1800067b8  test    r8, r8
0x1800067bb  lea     rcx, [rdx-2]
0x1800067bf  cmovnz  rcx, rdx
0x1800067c3  mov     [rcx], bx
0x1800067c6  mov     eax, ebx
0x1800067c8  add     rsp, 40h
0x1800067cc  pop     rbx
0x1800067cd  retn
0x1800067ce  mov     ebx, 80090009h
0x1800067d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067da  lea     rax, WPP_GLOBAL_Control
0x1800067e1  cmp     rcx, rax
0x1800067e4  jz      short loc_1800067C6
0x1800067e6  test    byte ptr [rcx+1Ch], 1
0x1800067ea  jz      short loc_1800067C6
0x1800067ec  mov     dword ptr [rsp+48h+var_18], 673h
0x1800067f4  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800067fb  mov     [rsp+48h+var_20], rax
0x180006800  mov     [rsp+48h+var_28], 80090009h
0x180006808  mov     rcx, [rcx+10h]
0x18000680c  lea     r9, aStatus; "Status"
0x180006813  call    WPP_SF_sDsd
0x180006818  jmp     short loc_1800067C6
0x18000681a  mov     ebx, 80090029h
0x18000681f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006826  lea     rax, WPP_GLOBAL_Control
0x18000682d  cmp     rcx, rax
0x180006830  jz      short loc_1800067C6
0x180006832  test    byte ptr [rcx+1Ch], 1
0x180006836  jz      short loc_1800067C6
0x180006838  mov     dword ptr [rsp+48h+var_18], 67Ch
0x180006840  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006847  mov     [rsp+48h+var_20], rax
0x18000684c  mov     [rsp+48h+var_28], 80090029h
0x180006854  jmp     short loc_180006808
0x180006856  mov     ebx, 80090029h
0x18000685b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006862  lea     rax, WPP_GLOBAL_Control
0x180006869  cmp     rcx, rax
0x18000686c  jz      loc_1800067C6
0x180006872  test    byte ptr [rcx+1Ch], 1
0x180006876  jz      loc_1800067C6
0x18000687c  mov     dword ptr [rsp+48h+var_18], 663h
0x180006884  jmp     short loc_180006840
0x180006886  lea     rax, aSha256; "SHA256"
0x18000688d  jmp     loc_180006784
0x180006892  mov     ebx, 80090026h
0x180006897  mov     rcx, cs:WPP_GLOBAL_Control
0x18000689e  lea     rax, WPP_GLOBAL_Control
0x1800068a5  cmp     rcx, rax
0x1800068a8  jz      loc_1800067C6
0x1800068ae  test    byte ptr [rcx+1Ch], 1
0x1800068b2  jz      loc_1800067C6
0x1800068b8  mov     dword ptr [rsp+48h+var_18], 66Ch
0x1800068c0  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800068c7  mov     [rsp+48h+var_20], rax
0x1800068cc  mov     [rsp+48h+var_28], 80090026h
0x1800068d4  jmp     loc_180006808
```
