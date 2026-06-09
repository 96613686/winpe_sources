# CuiGetBinarySignature(ushort const *,void *,uchar,uchar,SIGNATURE_INFO_FLAGS,_CONTEXT_SIGNATURE *,uchar *,ushort * *,ushort * *,_CERT_CONTEXT const * *,void * *)

- ea: `0x140003e40`
- end: `0x1400042d4`
- name: `?CuiGetBinarySignature@@YAJPEBGPEAXEEW4SIGNATURE_INFO_FLAGS@@PEAW4_CONTEXT_SIGNATURE@@PEAEPEAPEAG5PEAPEBU_CERT_CONTEXT@@PEAPEAX@Z`
- size: `1172`
- prototype: `__int64 __fastcall(__int64, __int64, char, char, int, int *, _BYTE *, LPWSTR *, LPWSTR *ppwsz, PCCERT_CONTEXT *, void **)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x140003040`
- `0x140003820`
- `0x140003b00`
- `0x140003c90`

## callees

- `0x140003e40`
- `0x1400098a0`
- `0x14000fbec`
- `0x140010ad3`
- `0x1400195d4`
- `0x1400196b4`
- `0x140019920`
- `0x1400199a0`
- `0x14001e050`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x14000414c`
- `CRYPT32!CertFreeCertificateContext` at `0x14000414c`
- `SHLWAPI!SHStrDupW` at `0x140004014`
- `SHLWAPI!SHStrDupW` at `0x140004250`
- `SHLWAPI!SHStrDupW` at `0x140004014`
- `SHLWAPI!SHStrDupW` at `0x140004250`
- `WINTRUST!WTGetSignatureInfo` at `0x140003f9f`
- `WINTRUST!WTGetSignatureInfo` at `0x140003f9f`

## pseudocode

```c
__int64 __fastcall CuiGetBinarySignature(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        int a5,
        int *a6,
        _BYTE *a7,
        LPWSTR *a8,
        LPWSTR *ppwsz,
        PCCERT_CONTEXT *a10,
        void **a11)
{
  int v14; // r8d
  __int64 v15; // r8
  __int64 v16; // rdx
  int v17; // eax
  unsigned int v18; // ebx
  const wchar_t *v19; // r15
  bool v20; // zf
  _BYTE *v21; // r14
  int v22; // eax
  int *v23; // rdi
  const wchar_t *v25; // rcx
  const wchar_t *v26; // rax
  const wchar_t *v27; // r9
  void *v28; // rcx
  const wchar_t *v29; // rdx
  const wchar_t *v30; // rax
  LPWSTR *v31; // rsi
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR *v34; // [rsp+60h] [rbp-A0h]
  __int128 v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h]
  WCHAR *v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+90h] [rbp-70h]
  WCHAR *v39; // [rsp+98h] [rbp-68h]
  __int128 v40; // [rsp+A0h] [rbp-60h]
  __int128 v41; // [rsp+B0h] [rbp-50h]
  __int64 v42; // [rsp+C0h] [rbp-40h]
  WCHAR v43[128]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR psz[264]; // [rsp+1D0h] [rbp+D0h] BYREF

  *a8 = 0;
  *ppwsz = 0;
  *a6 = 1;
  *a7 = 0;
  v34 = a8;
  *a10 = 0;
  *a11 = 0;
  memset_0(v43, 0, sizeof(v43));
  memset_0(psz, 0, 0x208u);
  pCertContext = 0;
  v42 = 0;
  v38 = 260;
  v36 = 0;
  v37 = psz;
  v35 = 0;
  v39 = v43;
  v40 = 0;
  LODWORD(v35) = 88;
  v41 = 0;
  LODWORD(v40) = 128;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    v25 = L"TRUE";
    v26 = L"TRUE";
    if ( !a4 )
      v25 = L"FALSE";
    LODWORD(v27) = a1;
    if ( !a3 )
      v26 = L"FALSE";
    if ( !a1 )
      v27 = L"NULL";
    WPP_SF_SDSSD(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      WPP_GLOBAL_Control,
      (unsigned int)L"NULL",
      (_DWORD)v27,
      a2,
      (__int64)v26,
      (__int64)v25,
      a5);
  }
  if ( !a3 || (v14 = 10255, a4) )
    v14 = 2063;
  v15 = a5 | (unsigned int)v14;
  v16 = -1;
  if ( a2 )
    v16 = a2;
  v17 = WTGetSignatureInfo(a1, v16, v15, &v35, &pCertContext, a11);
  v18 = v17;
  if ( v17 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_D(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        27,
        WPP_bed9811735e730a365d52877ff824444_Traceguids,
        (unsigned int)v17);
    v23 = a6;
    v19 = L"TRUE";
    v21 = a7;
  }
  else
  {
    v19 = L"TRUE";
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v29 = L"TRUE";
      v30 = L"TRUE";
      if ( !a3 )
        v29 = L"FALSE";
      if ( !HIDWORD(v42) )
        v30 = L"FALSE";
      WPP_SF_dSS(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (_DWORD)v29,
        (unsigned int)L"FALSE",
        DWORD1(v35),
        (__int64)v30,
        (__int64)v29);
    }
    if ( DWORD1(v35) != 5 )
    {
      switch ( DWORD1(v35) )
      {
        case 6:
          break;
        case 7:
          v23 = a6;
          v21 = a7;
          *a6 = 0;
          goto LABEL_33;
        default:
          v21 = a7;
          goto LABEL_48;
      }
    }
    v20 = HIDWORD(v42) == 0;
    v21 = a7;
    *a7 = 1;
    if ( v20 )
    {
      v22 = 2;
      goto LABEL_11;
    }
    if ( a3 )
    {
      v22 = 3;
LABEL_11:
      v23 = a6;
      *a6 = v22;
      if ( (v36 & 2) != 0 )
      {
        v31 = v34;
        SHStrDupW(v43, v34);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 29, WPP_bed9811735e730a365d52877ff824444_Traceguids, *v31);
      }
      if ( (v36 & 1) != 0 )
      {
        SHStrDupW(psz, ppwsz);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 30, WPP_bed9811735e730a365d52877ff824444_Traceguids, *ppwsz);
      }
      *a10 = pCertContext;
      pCertContext = 0;
      goto LABEL_17;
    }
LABEL_48:
    v23 = a6;
    *a6 = 1;
  }
LABEL_33:
  if ( pCertContext )
  {
    CertFreeCertificateContext(pCertContext);
    v28 = *a11;
    pCertContext = 0;
    CuiFreeWVTStateData(v28);
    *a11 = 0;
  }
LABEL_17:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    if ( !*v21 )
      v19 = L"FALSE";
    WPP_SF_dS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      31,
      (unsigned int)WPP_bed9811735e730a365d52877ff824444_Traceguids,
      *v23,
      (__int64)v19);
  }
  return v18;
}

```

## disassembly

```asm
0x140003e40  mov     [rsp-8+arg_10], rbx
0x140003e45  push    rbp
0x140003e46  push    rsi
0x140003e47  push    rdi
0x140003e48  push    r12
0x140003e4a  push    r13
0x140003e4c  push    r14
0x140003e4e  push    r15
0x140003e50  lea     rbp, [rsp-2F0h]
0x140003e58  sub     rsp, 3F0h
0x140003e5f  mov     rax, cs:__security_cookie
0x140003e66  xor     rax, rsp
0x140003e69  mov     [rbp+320h+var_40], rax
0x140003e70  mov     rax, [rbp+320h+arg_28]
0x140003e77  xor     r15d, r15d
0x140003e7a  mov     r13, [rbp+320h+ppwsz]
0x140003e81  mov     rbx, rdx
0x140003e84  mov     rdx, [rbp+320h+arg_38]
0x140003e8b  mov     r14, rcx
0x140003e8e  mov     rcx, [rbp+320h+arg_30]
0x140003e95  movzx   edi, r8b
0x140003e99  mov     r12, [rbp+320h+arg_48]
0x140003ea0  mov     r8d, 100h; Size
0x140003ea6  mov     rsi, [rbp+320h+arg_50]
0x140003ead  mov     [rdx], r15
0x140003eb0  mov     [r13+0], r15
0x140003eb4  mov     dword ptr [rax], 1
0x140003eba  mov     [rcx], r15b
0x140003ebd  mov     [rsp+420h+var_3D0], rcx
0x140003ec2  lea     rcx, [rbp+320h+var_350]; void *
0x140003ec6  mov     [rsp+420h+var_3C0], rdx
0x140003ecb  xor     edx, edx; Val
0x140003ecd  mov     [r12], r15
0x140003ed1  mov     [rsi], r15
0x140003ed4  mov     [rsp+420h+var_3E0], r9b
0x140003ed9  mov     [rsp+420h+var_3D8], rax
0x140003ede  call    memset_0
0x140003ee3  xor     edx, edx; Val
0x140003ee5  lea     rcx, [rbp+320h+psz]; void *
0x140003eec  mov     r8d, 208h; Size
0x140003ef2  call    memset_0
0x140003ef7  xorps   xmm0, xmm0
0x140003efa  mov     [rsp+420h+pCertContext], r15
0x140003eff  xor     eax, eax
0x140003f01  mov     [rbp+320h+var_360], rax
0x140003f05  lea     rax, [rbp+320h+psz]
0x140003f0c  movups  [rbp+320h+var_390], xmm0
0x140003f10  mov     dword ptr [rbp+320h+var_390], 104h
0x140003f17  movups  [rbp+320h+var_3A0], xmm0
0x140003f1b  mov     qword ptr [rbp+320h+var_3A0+8], rax
0x140003f1f  lea     rax, [rbp+320h+var_350]
0x140003f23  movups  [rsp+420h+var_3B0], xmm0
0x140003f28  mov     qword ptr [rbp+320h+var_390+8], rax
0x140003f2c  movups  [rbp+320h+var_380], xmm0
0x140003f30  mov     dword ptr [rsp+420h+var_3B0], 58h ; 'X'
0x140003f38  movups  [rbp+320h+var_370], xmm0
0x140003f3c  mov     dword ptr [rbp+320h+var_380], 80h
0x140003f43  mov     rdx, cs:WPP_GLOBAL_Control
0x140003f4a  lea     rax, WPP_GLOBAL_Control
0x140003f51  mov     r15d, [rbp+320h+arg_20]
0x140003f58  lea     r8, aFalse; "FALSE"
0x140003f5f  cmp     rdx, rax
0x140003f62  jnz     loc_1400040BC
0x140003f68  test    dil, dil
0x140003f6b  jnz     loc_1400041E6
0x140003f71  mov     r8d, 80Fh
0x140003f77  or      r8d, r15d
0x140003f7a  mov     [rsp+420h+var_3F8], rsi
0x140003f7f  lea     rax, [rsp+420h+pCertContext]
0x140003f84  test    rbx, rbx
0x140003f87  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140003f8e  mov     [rsp+420h+var_400], rax
0x140003f93  cmovnz  rdx, rbx
0x140003f97  lea     r9, [rsp+420h+var_3B0]
0x140003f9c  mov     rcx, r14
0x140003f9f  call    cs:__imp_WTGetSignatureInfo
0x140003fa5  mov     ebx, eax
0x140003fa7  test    eax, eax
0x140003fa9  js      loc_140004116
0x140003faf  mov     rcx, cs:WPP_GLOBAL_Control
0x140003fb6  lea     rax, WPP_GLOBAL_Control
0x140003fbd  lea     r15, aTrue; "TRUE"
0x140003fc4  cmp     rcx, rax
0x140003fc7  jnz     loc_14000416F
0x140003fcd  movsxd  rax, dword ptr [rsp+420h+var_3B0+4]
0x140003fd2  cmp     eax, 5
0x140003fd5  jnz     loc_1400041B2
0x140003fdb  cmp     dword ptr [rbp+320h+var_360+4], 0; jumptable 00000001400041C8 case 6
0x140003fdf  mov     r14, [rsp+420h+var_3D0]
0x140003fe4  mov     byte ptr [r14], 1
0x140003fe8  jnz     loc_140004235
0x140003fee  mov     eax, 2
0x140003ff3  mov     rdi, [rsp+420h+var_3D8]
0x140003ff8  mov     [rdi], eax
0x140003ffa  test    byte ptr [rbp+320h+var_3A0], 2
0x140003ffe  jnz     loc_140004244
0x140004004  test    byte ptr [rbp+320h+var_3A0], 1
0x140004008  jz      short loc_140004037
0x14000400a  mov     rdx, r13; ppwsz
0x14000400d  lea     rcx, [rbp+320h+psz]; psz
0x140004014  call    cs:__imp_SHStrDupW
0x14000401a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004021  lea     rax, WPP_GLOBAL_Control
0x140004028  cmp     rcx, rax
0x14000402b  jz      short loc_140004037
0x14000402d  test    byte ptr [rcx+1Ch], 2
0x140004031  jnz     loc_140004294
0x140004037  mov     rax, [rsp+420h+pCertContext]
0x14000403c  mov     [r12], rax
0x140004040  lea     r12, WPP_GLOBAL_Control
0x140004047  mov     [rsp+420h+pCertContext], 0
0x140004050  mov     rcx, cs:WPP_GLOBAL_Control
0x140004057  cmp     rcx, r12
0x14000405a  jnz     short loc_140004088
0x14000405c  mov     eax, ebx
0x14000405e  mov     rcx, [rbp+320h+var_40]
0x140004065  xor     rcx, rsp; StackCookie
0x140004068  call    __security_check_cookie
0x14000406d  mov     rbx, [rsp+420h+arg_10]
0x140004075  add     rsp, 3F0h
0x14000407c  pop     r15
0x14000407e  pop     r14
0x140004080  pop     r13
0x140004082  pop     r12
0x140004084  pop     rdi
0x140004085  pop     rsi
0x140004086  pop     rbp
0x140004087  retn
0x140004088  test    byte ptr [rcx+1Ch], 2
0x14000408c  jz      short loc_14000405C
0x14000408e  cmp     byte ptr [r14], 0
0x140004092  lea     rax, aFalse; "FALSE"
0x140004099  mov     r9d, [rdi]
0x14000409c  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x1400040a3  mov     rcx, [rcx+10h]
0x1400040a7  cmovz   r15, rax
0x1400040ab  mov     edx, 1Fh
0x1400040b0  mov     [rsp+420h+var_400], r15
0x1400040b5  call    WPP_SF_dS
0x1400040ba  jmp     short loc_14000405C
0x1400040bc  test    byte ptr [rdx+1Ch], 2
0x1400040c0  jz      loc_140003F68
0x1400040c6  cmp     [rsp+420h+var_3E0], 0
0x1400040cb  lea     rcx, aTrue; "TRUE"
0x1400040d2  mov     [rsp+420h+var_3E8], r15d
0x1400040d7  lea     rax, aTrue; "TRUE"
0x1400040de  cmovz   rcx, r8
0x1400040e2  mov     r9, r14
0x1400040e5  mov     [rsp+420h+var_3F0], rcx
0x1400040ea  test    dil, dil
0x1400040ed  mov     rcx, [rdx+10h]
0x1400040f1  cmovz   rax, r8
0x1400040f5  test    r14, r14
0x1400040f8  lea     r8, aNull; "NULL"
0x1400040ff  mov     [rsp+420h+var_3F8], rax
0x140004104  cmovz   r9, r8
0x140004108  mov     dword ptr [rsp+420h+var_400], ebx
0x14000410c  call    WPP_SF_SDSSD
0x140004111  jmp     loc_140003F68
0x140004116  mov     rcx, cs:WPP_GLOBAL_Control
0x14000411d  lea     r12, WPP_GLOBAL_Control
0x140004124  cmp     rcx, r12
0x140004127  jnz     loc_1400041FC
0x14000412d  mov     rdi, [rsp+420h+var_3D8]
0x140004132  lea     r15, aTrue; "TRUE"
0x140004139  mov     r14, [rsp+420h+var_3D0]
0x14000413e  mov     rcx, [rsp+420h+pCertContext]; pCertContext
0x140004143  test    rcx, rcx
0x140004146  jz      loc_140004050
0x14000414c  call    cs:__imp_CertFreeCertificateContext
0x140004152  mov     rcx, [rsi]; void *
0x140004155  mov     [rsp+420h+pCertContext], 0
0x14000415e  call    ?CuiFreeWVTStateData@@YAXPEAX@Z; CuiFreeWVTStateData(void *)
0x140004163  mov     qword ptr [rsi], 0
0x14000416a  jmp     loc_140004050
0x14000416f  test    byte ptr [rcx+1Ch], 4
0x140004173  jz      loc_140003FCD
0x140004179  mov     r9d, dword ptr [rsp+420h+var_3B0+4]
0x14000417e  lea     r8, aFalse; "FALSE"
0x140004185  mov     rcx, [rcx+10h]
0x140004189  test    dil, dil
0x14000418c  mov     rdx, r15
0x14000418f  mov     rax, r15
0x140004192  cmovz   rdx, r8
0x140004196  cmp     dword ptr [rbp+320h+var_360+4], 0
0x14000419a  mov     [rsp+420h+var_3F8], rdx
0x14000419f  cmovz   rax, r8
0x1400041a3  mov     [rsp+420h+var_400], rax
0x1400041a8  call    WPP_SF_dSS
0x1400041ad  jmp     loc_140003FCD
0x1400041b2  cmp     eax, 7; switch 8 cases
0x1400041b5  ja      short def_1400041C8; jumptable 00000001400041C8 default case, cases 0-5
0x1400041b7  lea     rdx, __ImageBase
0x1400041be  mov     ecx, ds:(jpt_1400041C8 - 140000000h)[rdx+rax*4]
0x1400041c5  add     rcx, rdx
0x1400041c8  jmp     rcx; switch jump
0x1400041ca  mov     rdi, [rsp+420h+var_3D8]; jumptable 00000001400041C8 case 7
0x1400041cf  mov     r14, [rsp+420h+var_3D0]
0x1400041d4  mov     dword ptr [rdi], 0
0x1400041da  lea     r12, WPP_GLOBAL_Control
0x1400041e1  jmp     loc_14000413E
0x1400041e6  cmp     [rsp+420h+var_3E0], 0
0x1400041eb  mov     r8d, 280Fh
0x1400041f1  jz      loc_140003F77
0x1400041f7  jmp     loc_140003F71
0x1400041fc  test    byte ptr [rcx+1Ch], 4
0x140004200  jz      loc_14000412D
0x140004206  mov     rcx, [rcx+10h]
0x14000420a  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x140004211  mov     edx, 1Bh
0x140004216  mov     r9d, ebx
0x140004219  call    WPP_SF_D
0x14000421e  jmp     loc_14000412D
0x140004223  mov     r14, [rsp+420h+var_3D0]; jumptable 00000001400041C8 default case, cases 0-5
0x140004228  mov     rdi, [rsp+420h+var_3D8]
0x14000422d  mov     dword ptr [rdi], 1
0x140004233  jmp     short loc_1400041DA
0x140004235  test    dil, dil
0x140004238  jz      short loc_140004228
0x14000423a  mov     eax, 3
0x14000423f  jmp     loc_140003FF3
0x140004244  mov     rsi, [rsp+420h+var_3C0]
0x140004249  lea     rcx, [rbp+320h+var_350]; psz
0x14000424d  mov     rdx, rsi; ppwsz
0x140004250  call    cs:__imp_SHStrDupW
0x140004256  mov     rcx, cs:WPP_GLOBAL_Control
0x14000425d  lea     rax, WPP_GLOBAL_Control
0x140004264  cmp     rcx, rax
0x140004267  jz      loc_140004004
0x14000426d  test    byte ptr [rcx+1Ch], 2
0x140004271  jz      loc_140004004
0x140004277  mov     r9, [rsi]
0x14000427a  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x140004281  mov     rcx, [rcx+10h]
0x140004285  mov     edx, 1Dh
0x14000428a  call    WPP_SF_S
0x14000428f  jmp     loc_140004004
0x140004294  mov     r9, [r13+0]
0x140004298  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x14000429f  mov     rcx, [rcx+10h]
0x1400042a3  mov     edx, 1Eh
0x1400042a8  call    WPP_SF_S
0x1400042ad  jmp     loc_140004037
```
