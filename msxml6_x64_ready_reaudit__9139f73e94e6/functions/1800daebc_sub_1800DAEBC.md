# sub_1800DAEBC

- ea: `0x1800daebc`
- end: `0x1800db233`
- name: `sub_1800DAEBC`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800878e4`

## callees

- `0x180015a80`
- `0x180019cd0`
- `0x180019e20`
- `0x180054310`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800d82c0`
- `0x1800da96c`
- `0x1800dab10`
- `0x1800dad54`
- `0x1800daebc`
- `0x1800db2d0`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!VariantClear` at `0x1800db1d0`
- `OLEAUT32!VariantClear` at `0x1800db1d0`
- `OLEAUT32!SafeArrayGetUBound` at `0x1800dafdb`
- `OLEAUT32!SafeArrayGetUBound` at `0x1800dafdb`
- `OLEAUT32!SafeArrayGetLBound` at `0x1800dafb5`
- `OLEAUT32!SafeArrayGetLBound` at `0x1800dafb5`
- `OLEAUT32!SafeArrayAccessData` at `0x1800daffe`
- `OLEAUT32!SafeArrayAccessData` at `0x1800daffe`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1800db05f`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1800db05f`
- `OLEAUT32!VariantChangeTypeEx` at `0x1800db0ce`
- `OLEAUT32!VariantChangeTypeEx` at `0x1800db142`
- `OLEAUT32!VariantChangeTypeEx` at `0x1800db0ce`
- `OLEAUT32!VariantChangeTypeEx` at `0x1800db142`

## pseudocode

```c
__int64 __fastcall sub_1800DAEBC(__int64 *a1, const VARIANTARG *a2, int a3)
{
  HRESULT LBound; // edi
  __int64 *pllVal; // r14
  void *bstrVal; // rcx
  HRESULT v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v14; // [rsp+38h] [rbp-70h] BYREF
  LONG plUbound; // [rsp+40h] [rbp-68h] BYREF
  LONG plLbound; // [rsp+44h] [rbp-64h] BYREF
  LONGLONG llVal; // [rsp+48h] [rbp-60h]
  VARIANTARG pvargDest; // [rsp+50h] [rbp-58h] BYREF
  void *ppvData[2]; // [rsp+68h] [rbp-40h] BYREF
  int v20; // [rsp+C8h] [rbp+20h] BYREF

  LBound = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  pllVal = 0;
  llVal = 0;
  v20 = 0;
  pvargDest.vt = 1;
  v14 = 0;
  if ( a3 > 17 )
  {
    if ( a3 != 18 && a3 != 31 && a3 != 32 )
    {
      if ( a3 == 38 )
      {
        *(_OWORD *)ppvData = 0;
        LBound = VariantChangeTypeEx(&pvargDest, a2, 0x409u, 1u, 8u);
        if ( LBound < 0 )
          goto LABEL_37;
        v10 = sub_180054310(pvargDest.llVal, 0x7FFFFFFF);
        LBound = sub_1800DA96C(pvargDest.llVal, v10, ppvData);
        if ( LBound < 0 )
          goto LABEL_37;
        pllVal = pvargDest.pllVal;
        llVal = pvargDest.llVal;
      }
      else if ( a3 == 39 )
      {
        LBound = -2147467259;
        goto LABEL_37;
      }
      goto LABEL_9;
    }
    goto LABEL_8;
  }
  switch ( a3 )
  {
    case 17:
LABEL_8:
      LBound = sub_1800DB2D0(&v14, (unsigned int)a3, &a2->decVal.Lo32);
      if ( LBound < 0 )
        goto LABEL_37;
      break;
    case 12:
    case 13:
      plLbound = 0;
      plUbound = 0;
      ppvData[0] = 0;
      LBound = SafeArrayGetLBound(a2->parray, 1u, &plLbound);
      if ( LBound < 0 )
        goto LABEL_37;
      LBound = SafeArrayGetUBound(a2->parray, 1u, &plUbound);
      if ( LBound < 0 )
        goto LABEL_37;
      LBound = SafeArrayAccessData(a2->parray, ppvData);
      if ( LBound < 0 )
        goto LABEL_37;
      v9 = a3 == 13
         ? sub_1800DAD54(&v14, ppvData[0], (unsigned int)(plUbound - plLbound + 1))
         : sub_1800DAB10(ppvData[0], (unsigned int)(plUbound - plLbound + 1), &v14);
      LBound = v9;
      SafeArrayUnaccessData(a2->parray);
      if ( LBound < 0 )
        goto LABEL_37;
      break;
    case 14:
      pllVal = &qword_1801C7250;
      if ( a2->iVal != -1 )
        pllVal = (__int64 *)L"0";
      goto LABEL_12;
    case 15:
      LOWORD(v20) = a2->iVal;
      pllVal = (__int64 *)&v20;
LABEL_12:
      llVal = (LONGLONG)pllVal;
      break;
    case 16:
      goto LABEL_8;
  }
LABEL_9:
  if ( pllVal )
  {
    bstrVal = pllVal;
LABEL_36:
    v11 = sub_180019CD0(bstrVal);
    sub_180019E20(&v14);
    v14 = v11;
    goto LABEL_37;
  }
  if ( !v14 )
  {
    LBound = VariantChangeTypeEx(&pvargDest, a2, 0x409u, 1u, 8u);
    if ( LBound >= 0 )
    {
      bstrVal = pvargDest.bstrVal;
      goto LABEL_36;
    }
  }
LABEL_37:
  VariantClear(&pvargDest);
  v12 = v14;
  v14 = 0;
  *a1 = v12;
  sub_180019E20(&v14);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x1800daebc  mov     r11, rsp
0x1800daebf  mov     [r11+10h], rbx
0x1800daec3  mov     [r11+18h], rsi
0x1800daec7  mov     [r11+8], rcx
0x1800daecb  push    rdi
0x1800daecc  push    r12
0x1800daece  push    r13
0x1800daed0  push    r14
0x1800daed2  push    r15
0x1800daed4  sub     rsp, 80h
0x1800daedb  mov     ebx, r8d
0x1800daede  mov     r15, rdx
0x1800daee1  mov     r12, rcx
0x1800daee4  xor     esi, esi
0x1800daee6  mov     edi, esi
0x1800daee8  xorps   xmm0, xmm0
0x1800daeeb  xor     eax, eax
0x1800daeed  movups  xmmword ptr [rsp+0A8h+pvargDest], xmm0
0x1800daef2  mov     [r11-48h], rax
0x1800daef6  mov     r14d, esi
0x1800daef9  mov     [r11-60h], rsi
0x1800daefd  mov     [r11+20h], esi
0x1800daf01  lea     r13d, [rsi+1]
0x1800daf05  mov     [r11-58h], r13w
0x1800daf0a  mov     [r11-70h], rsi
0x1800daf0e  cmp     ebx, 11h
0x1800daf11  jg      loc_1800DB078
0x1800daf17  jz      short loc_1800DAF34
0x1800daf19  mov     ecx, ebx
0x1800daf1b  sub     ecx, 0Ch
0x1800daf1e  jz      short loc_1800DAF9C
0x1800daf20  sub     ecx, r13d
0x1800daf23  jz      short loc_1800DAF9C
0x1800daf25  sub     ecx, r13d
0x1800daf28  jz      short loc_1800DAF83
0x1800daf2a  sub     ecx, r13d
0x1800daf2d  jz      short loc_1800DAF68
0x1800daf2f  cmp     ecx, r13d
0x1800daf32  jnz     short loc_1800DAF52
0x1800daf34  lea     r8, [rdx+8]
0x1800daf38  mov     edx, ebx
0x1800daf3a  lea     rcx, [rsp+0A8h+var_70]
0x1800daf3f  call    sub_1800DB2D0
0x1800daf44  mov     edi, eax
0x1800daf46  mov     [rsp+0A8h+var_78], eax
0x1800daf4a  test    eax, eax
0x1800daf4c  js      loc_1800DB1CB
0x1800daf52  mov     ebx, 8
0x1800daf57  test    r14, r14
0x1800daf5a  jz      loc_1800DB125
0x1800daf60  mov     rcx, r14
0x1800daf63  jmp     loc_1800DB15D
0x1800daf68  movzx   eax, word ptr [rdx+8]
0x1800daf6c  mov     word ptr [rsp+0A8h+arg_18], ax
0x1800daf74  lea     r14, [rsp+0A8h+arg_18]
0x1800daf7c  mov     [rsp+0A8h+var_60], r14
0x1800daf81  jmp     short loc_1800DAF52
0x1800daf83  lea     r14, qword_1801C7250
0x1800daf8a  lea     rax, a0_0; "0"
0x1800daf91  cmp     word ptr [rdx+8], 0FFFFh
0x1800daf96  cmovnz  r14, rax
0x1800daf9a  jmp     short loc_1800DAF7C
0x1800daf9c  mov     [rsp+0A8h+plLbound], esi
0x1800dafa0  mov     [rsp+0A8h+plUbound], esi
0x1800dafa4  mov     [rsp+0A8h+ppvData], rsi
0x1800dafa9  lea     r8, [rsp+0A8h+plLbound]; plLbound
0x1800dafae  mov     edx, r13d; nDim
0x1800dafb1  mov     rcx, [r15+8]; psa
0x1800dafb5  call    cs:SafeArrayGetLBound
0x1800dafbc  nop     dword ptr [rax+rax+00h]
0x1800dafc1  mov     edi, eax
0x1800dafc3  mov     [rsp+0A8h+var_78], eax
0x1800dafc7  test    eax, eax
0x1800dafc9  js      loc_1800DB1CB
0x1800dafcf  lea     r8, [rsp+0A8h+plUbound]; plUbound
0x1800dafd4  mov     edx, r13d; nDim
0x1800dafd7  mov     rcx, [r15+8]; psa
0x1800dafdb  call    cs:SafeArrayGetUBound
0x1800dafe2  nop     dword ptr [rax+rax+00h]
0x1800dafe7  mov     edi, eax
0x1800dafe9  mov     [rsp+0A8h+var_78], eax
0x1800dafed  test    eax, eax
0x1800dafef  js      loc_1800DB1CB
0x1800daff5  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x1800daffa  mov     rcx, [r15+8]; psa
0x1800daffe  call    cs:SafeArrayAccessData
0x1800db005  nop     dword ptr [rax+rax+00h]
0x1800db00a  mov     edi, eax
0x1800db00c  mov     [rsp+0A8h+var_78], eax
0x1800db010  test    eax, eax
0x1800db012  js      loc_1800DB1CB
0x1800db018  cmp     ebx, 0Dh
0x1800db01b  jnz     short loc_1800DB03B
0x1800db01d  mov     r8d, [rsp+0A8h+plUbound]
0x1800db022  sub     r8d, [rsp+0A8h+plLbound]
0x1800db027  add     r8d, r13d
0x1800db02a  mov     rdx, [rsp+0A8h+ppvData]
0x1800db02f  lea     rcx, [rsp+0A8h+var_70]
0x1800db034  call    sub_1800DAD54
0x1800db039  jmp     short loc_1800DB055
0x1800db03b  mov     edx, [rsp+0A8h+plUbound]
0x1800db03f  sub     edx, [rsp+0A8h+plLbound]
0x1800db043  add     edx, r13d
0x1800db046  lea     r8, [rsp+0A8h+var_70]
0x1800db04b  mov     rcx, [rsp+0A8h+ppvData]
0x1800db050  call    sub_1800DAB10
0x1800db055  mov     [rsp+0A8h+var_78], eax
0x1800db059  mov     edi, eax
0x1800db05b  mov     rcx, [r15+8]; psa
0x1800db05f  call    cs:SafeArrayUnaccessData
0x1800db066  nop     dword ptr [rax+rax+00h]
0x1800db06b  test    edi, edi
0x1800db06d  jns     loc_1800DAF52
0x1800db073  jmp     loc_1800DB1CB
0x1800db078  mov     ecx, ebx
0x1800db07a  sub     ecx, 12h
0x1800db07d  jz      loc_1800DAF34
0x1800db083  sub     ecx, 0Dh
0x1800db086  jz      loc_1800DAF34
0x1800db08c  sub     ecx, 1
0x1800db08f  jz      loc_1800DAF34
0x1800db095  sub     ecx, 6
0x1800db098  jz      short loc_1800DB0B1
0x1800db09a  cmp     ecx, 1
0x1800db09d  jnz     loc_1800DAF52
0x1800db0a3  mov     edi, 80004005h
0x1800db0a8  mov     [rsp+0A8h+var_78], edi
0x1800db0ac  jmp     loc_1800DB1CB
0x1800db0b1  movups  xmmword ptr [rsp+0A8h+ppvData], xmm0
0x1800db0b6  mov     ebx, 8
0x1800db0bb  mov     r9d, r13d; wFlags
0x1800db0be  mov     [rsp+0A8h+vt], bx; vt
0x1800db0c3  mov     r8d, 409h; lcid
0x1800db0c9  lea     rcx, [rsp+0A8h+pvargDest]; pvargDest
0x1800db0ce  call    cs:VariantChangeTypeEx
0x1800db0d5  nop     dword ptr [rax+rax+00h]
0x1800db0da  mov     edi, eax
0x1800db0dc  mov     [rsp+0A8h+var_78], eax
0x1800db0e0  test    eax, eax
0x1800db0e2  js      loc_1800DB1CB
0x1800db0e8  mov     edx, 7FFFFFFFh
0x1800db0ed  mov     rcx, qword ptr [rsp+0A8h+pvargDest+8]
0x1800db0f2  call    sub_180054310
0x1800db0f7  mov     edx, eax
0x1800db0f9  lea     r8, [rsp+0A8h+ppvData]
0x1800db0fe  mov     rcx, qword ptr [rsp+0A8h+pvargDest+8]
0x1800db103  call    sub_1800DA96C
0x1800db108  mov     edi, eax
0x1800db10a  mov     [rsp+0A8h+var_78], eax
0x1800db10e  test    eax, eax
0x1800db110  js      loc_1800DB1CB
0x1800db116  mov     r14, qword ptr [rsp+0A8h+pvargDest+8]
0x1800db11b  mov     [rsp+0A8h+var_60], r14
0x1800db120  jmp     loc_1800DAF57
0x1800db125  cmp     [rsp+0A8h+var_70], rsi
0x1800db12a  jnz     short loc_1800DB174
0x1800db12c  mov     r9d, r13d; wFlags
0x1800db12f  mov     [rsp+0A8h+vt], bx; vt
0x1800db134  mov     r8d, 409h; lcid
0x1800db13a  mov     rdx, r15; pvarSrc
0x1800db13d  lea     rcx, [rsp+0A8h+pvargDest]; pvargDest
0x1800db142  call    cs:VariantChangeTypeEx
0x1800db149  nop     dword ptr [rax+rax+00h]
0x1800db14e  mov     edi, eax
0x1800db150  mov     [rsp+0A8h+var_78], eax
0x1800db154  test    eax, eax
0x1800db156  js      short loc_1800DB1CB
0x1800db158  mov     rcx, qword ptr [rsp+0A8h+pvargDest+8]; Src
0x1800db15d  call    sub_180019CD0
0x1800db162  mov     rbx, rax
0x1800db165  lea     rcx, [rsp+0A8h+var_70]
0x1800db16a  call    sub_180019E20
0x1800db16f  mov     [rsp+0A8h+var_70], rbx
0x1800db174  jmp     short loc_1800DB1CB
0x1800db176  call    sub_1800A3C08
0x1800db17b  cmp     [rsp+0A8h+var_70], 0
0x1800db181  jz      short loc_1800DB18F
0x1800db183  xor     edx, edx
0x1800db185  lea     rcx, [rsp+0A8h+var_70]
0x1800db18a  call    sub_180015A80
0x1800db18f  mov     ecx, cs:TlsIndex
0x1800db195  mov     rax, gs:58h
0x1800db19e  mov     edx, 8
0x1800db1a3  mov     rax, [rax+rcx*8]
0x1800db1a7  mov     rcx, [rax+rdx]
0x1800db1ab  mov     rcx, [rcx+8]
0x1800db1af  mov     rax, [rcx]
0x1800db1b2  mov     rax, [rax+68h]
0x1800db1b6  call    sub_18018C010
0x1800db1bb  mov     edi, eax
0x1800db1bd  mov     [rsp+0A8h+var_78], eax
0x1800db1c1  xor     esi, esi
0x1800db1c3  mov     r12, [rsp+0A8h+arg_0]
0x1800db1cb  lea     rcx, [rsp+0A8h+pvargDest]; pvarg
0x1800db1d0  call    cs:VariantClear
0x1800db1d7  nop     dword ptr [rax+rax+00h]
0x1800db1dc  mov     rax, [rsp+0A8h+var_70]
0x1800db1e1  mov     [rsp+0A8h+var_70], rsi
0x1800db1e6  mov     [r12], rax
0x1800db1ea  lea     rcx, [rsp+0A8h+var_70]
0x1800db1ef  call    sub_180019E20
0x1800db1f4  mov     eax, edi
0x1800db1f6  lea     r11, [rsp+0A8h+var_28]
0x1800db1fe  mov     rbx, [r11+38h]
0x1800db202  mov     rsi, [r11+40h]
0x1800db206  mov     rsp, r11
0x1800db209  pop     r15
0x1800db20b  pop     r14
0x1800db20d  pop     r13
0x1800db20f  pop     r12
0x1800db211  pop     rdi
0x1800db212  retn
0x1800db214  call    sub_1800A3C08
0x1800db219  cmp     [rsp+0A8h+var_70], 0
0x1800db21f  jz      short loc_1800DB22D
0x1800db221  xor     edx, edx
0x1800db223  lea     rcx, [rsp+0A8h+var_70]
0x1800db228  call    sub_180015A80
0x1800db22d  call    sub_1800D82C0
0x180182ae3  push    rbp
0x180182ae5  sub     rsp, 30h
0x180182ae9  mov     rbp, rdx
0x180182aec  call    sub_18009FEFC
0x180182af1  nop
0x180182af2  add     rsp, 30h
0x180182af6  pop     rbp
0x180182af7  retn
0x180182af9  push    rbp
0x180182afb  sub     rsp, 30h
0x180182aff  mov     rbp, rdx
0x180182b02  call    sub_18009FEFC
0x180182b07  nop
0x180182b08  add     rsp, 30h
0x180182b0c  pop     rbp
0x180182b0d  retn
```
