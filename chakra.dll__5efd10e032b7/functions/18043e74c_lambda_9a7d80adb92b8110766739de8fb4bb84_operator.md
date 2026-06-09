# _lambda_9a7d80adb92b8110766739de8fb4bb84_::operator()

- ea: `0x18043e74c`
- end: `0x18043ea77`
- name: `_lambda_9a7d80adb92b8110766739de8fb4bb84_::operator()`
- size: `811`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18043e634`

## callees

- `0x180206e74`
- `0x180231404`
- `0x18043e74c`
- `0x18043eae0`
- `0x18043ed34`
- `0x1805a9e80`

## import_xrefs

- `msvcrt!_ltow_s` at `0x18043ea62`
- `msvcrt!_ltow_s` at `0x18043ea62`
- `msvcrt!_ultow_s` at `0x18043ea38`
- `msvcrt!_ultow_s` at `0x18043ea38`
- `OLEAUT32!__imp_SysAllocString` at `0x18043e87a`
- `OLEAUT32!__imp_SysAllocString` at `0x18043e87a`
- `OLEAUT32!__imp_VariantClear` at `0x18043e8a9`
- `OLEAUT32!__imp_VariantClear` at `0x18043e8a9`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18043e7e1`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18043e7e1`

## pseudocode

```c
HRESULT __fastcall lambda_9a7d80adb92b8110766739de8fb4bb84_::operator()(_QWORD **a1)
{
  _QWORD *v2; // rcx
  HRESULT result; // eax
  const VARIANTARG **v4; // rcx
  _DWORD *v5; // rax
  int v6; // ebx
  unsigned __int16 **v7; // rax
  _WORD *v8; // r8
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  wchar_t *v16; // rcx
  int StringLiteral; // eax
  const wchar_t *v18; // rcx
  double v19; // xmm1_8
  int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  VARIANT pvarDest; // [rsp+28h] [rbp-59h] BYREF
  wchar_t Buffer[64]; // [rsp+48h] [rbp-39h] BYREF

  v2 = (_QWORD *)**a1;
  if ( !v2 )
    return -2147467261;
  *v2 = 0;
  v4 = (const VARIANTARG **)a1[1];
  if ( !*v4 )
    return -2147024809;
  v5 = a1[2];
  if ( *v5 != 16 && *v5 != 10 )
    return -2147467263;
  v6 = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  if ( ((*v4)->vt & 0x4000) != 0 )
  {
    result = VariantCopyInd(&pvarDest, *v4);
    v6 = result;
    if ( result < 0 )
      return result;
    *a1[1] = &pvarDest;
  }
  v7 = (unsigned __int16 **)a1[1];
  v8 = *v7;
  v9 = **v7;
  if ( v9 <= 0xB )
  {
    if ( v9 == 11 )
    {
      v16 = (wchar_t *)L"false";
      if ( v8[4] )
        v16 = L"true";
      goto LABEL_23;
    }
    if ( !**v7 )
    {
      v16 = (wchar_t *)L"undefined";
      goto LABEL_23;
    }
    v10 = v9 - 1;
    if ( !v10 )
    {
      v16 = L"null";
      goto LABEL_23;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v20 = (__int16)v8[4];
      goto LABEL_65;
    }
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 3;
          if ( !v15 )
          {
            v18 = &String;
            if ( *((_QWORD *)v8 + 1) )
              v18 = (const wchar_t *)*((_QWORD *)v8 + 1);
            StringLiteral = GetStringLiteral(v18, **a1);
            goto LABEL_25;
          }
          if ( v15 == 1 )
            goto LABEL_21;
LABEL_56:
          *(_QWORD *)**a1 = 0;
          goto LABEL_26;
        }
        v19 = *((double *)v8 + 1);
      }
      else
      {
        v19 = *((float *)v8 + 2);
      }
      if ( (~*(_QWORD *)&v19 & 0x7FF0000000000000LL) == 0 )
      {
        if ( Js::NumberUtilities::IsNan(v19) )
        {
          v16 = (wchar_t *)L"NaN";
        }
        else
        {
          v16 = (wchar_t *)L"-Infinity";
          if ( v19 >= 0.0 )
            v16 = (wchar_t *)L"Infinity";
        }
        goto LABEL_23;
      }
      if ( !(unsigned int)Js::NumberUtilities::FDblToStr(v19, Buffer, 64) )
      {
        v6 = -2147024882;
        goto LABEL_26;
      }
      goto LABEL_67;
    }
    goto LABEL_58;
  }
  v21 = v9 - 13;
  if ( !v21 )
  {
LABEL_21:
    v16 = L"null";
    if ( *((_QWORD *)v8 + 1) )
      v16 = (wchar_t *)&String;
    goto LABEL_23;
  }
  v22 = v21 - 3;
  if ( !v22 )
  {
    v20 = *((char *)v8 + 8);
LABEL_65:
    if ( *(_DWORD *)a1[2] != 16 )
    {
      _ltow_s(v20, Buffer, 0x40u, 10);
      goto LABEL_67;
    }
    goto LABEL_62;
  }
  v23 = v22 - 1;
  if ( v23 )
  {
    v24 = v23 - 1;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 3;
        if ( !v26 )
        {
LABEL_58:
          v20 = *((_DWORD *)v8 + 2);
          goto LABEL_65;
        }
        if ( v26 != 1 )
          goto LABEL_56;
      }
      v27 = *((_DWORD *)v8 + 2);
    }
    else
    {
      v27 = (unsigned __int16)v8[4];
    }
  }
  else
  {
    v27 = *((unsigned __int8 *)v8 + 8);
  }
  if ( *(_DWORD *)a1[2] != 16 )
  {
    _ultow_s(v27, Buffer, 0x40u, 10);
LABEL_67:
    v16 = Buffer;
LABEL_23:
    *(_QWORD *)**a1 = SysAllocString(v16);
    StringLiteral = v6;
    if ( !*(_QWORD *)**a1 )
      StringLiteral = -2147024882;
    goto LABEL_25;
  }
LABEL_62:
  StringLiteral = GetHexLiteral(v8, **a1);
LABEL_25:
  v6 = StringLiteral;
LABEL_26:
  VariantClear(&pvarDest);
  if ( v6 >= 0 )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x18043e74c  mov     rax, rsp
0x18043e74f  mov     [rax+10h], rbx
0x18043e753  mov     [rax+18h], rdi
0x18043e757  mov     [rax+8], rcx
0x18043e75b  push    rbp
0x18043e75c  lea     rbp, [rax-5Fh]
0x18043e760  sub     rsp, 0D0h
0x18043e767  mov     rax, cs:__security_cookie
0x18043e76e  xor     rax, rsp
0x18043e771  mov     [rbp+57h+var_10], rax
0x18043e775  mov     rdi, [rbp+57h+arg_0]
0x18043e779  mov     rax, [rdi]
0x18043e77c  mov     rcx, [rax]
0x18043e77f  test    rcx, rcx
0x18043e782  jnz     short loc_18043E78E
0x18043e784  mov     eax, 80004003h
0x18043e789  jmp     loc_18043E8BE
0x18043e78e  mov     qword ptr [rcx], 0
0x18043e795  mov     rcx, [rdi+8]
0x18043e799  cmp     qword ptr [rcx], 0
0x18043e79d  jnz     short loc_18043E7A9
0x18043e79f  mov     eax, 80070057h
0x18043e7a4  jmp     loc_18043E8BE
0x18043e7a9  mov     rax, [rdi+10h]
0x18043e7ad  cmp     dword ptr [rax], 10h
0x18043e7b0  jz      short loc_18043E7C1
0x18043e7b2  cmp     dword ptr [rax], 0Ah
0x18043e7b5  jz      short loc_18043E7C1
0x18043e7b7  mov     eax, 80004001h
0x18043e7bc  jmp     loc_18043E8BE
0x18043e7c1  xor     eax, eax
0x18043e7c3  xorps   xmm0, xmm0
0x18043e7c6  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x18043e7ca  xor     ebx, ebx
0x18043e7cc  movups  xmmword ptr [rbp+57h+pvarDest], xmm0
0x18043e7d0  mov     rdx, [rcx]; pvargSrc
0x18043e7d3  mov     eax, 4000h
0x18043e7d8  test    [rdx], ax
0x18043e7db  jz      short loc_18043E802
0x18043e7dd  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x18043e7e1  call    cs:__imp_VariantCopyInd
0x18043e7e8  nop     dword ptr [rax+rax+00h]
0x18043e7ed  mov     ebx, eax
0x18043e7ef  test    eax, eax
0x18043e7f1  js      loc_18043E8BE
0x18043e7f7  mov     rax, [rdi+8]
0x18043e7fb  lea     rcx, [rbp+57h+pvarDest]
0x18043e7ff  mov     [rax], rcx
0x18043e802  mov     rax, [rdi+8]
0x18043e806  mov     r8, [rax]
0x18043e809  movzx   ecx, word ptr [r8]
0x18043e80d  cmp     ecx, 0Bh
0x18043e810  ja      loc_18043E9BD
0x18043e816  jz      loc_18043E99F
0x18043e81c  test    ecx, ecx
0x18043e81e  jz      loc_18043E993
0x18043e824  sub     ecx, 1
0x18043e827  jz      loc_18043E987
0x18043e82d  sub     ecx, 1
0x18043e830  jz      loc_18043E97D
0x18043e836  sub     ecx, 1
0x18043e839  jz      loc_18043E9FC
0x18043e83f  sub     ecx, 1
0x18043e842  jz      loc_18043E906
0x18043e848  sub     ecx, 1
0x18043e84b  jz      loc_18043E8FE
0x18043e851  sub     ecx, 3
0x18043e854  jz      loc_18043E8E0
0x18043e85a  cmp     ecx, 1
0x18043e85d  jnz     loc_18043E9E4
0x18043e863  cmp     qword ptr [r8+8], 0
0x18043e868  lea     rcx, aNull; "null"
0x18043e86f  lea     rax, String
0x18043e876  cmovnz  rcx, rax; psz
0x18043e87a  call    cs:__imp_SysAllocString
0x18043e881  nop     dword ptr [rax+rax+00h]
0x18043e886  mov     rcx, [rdi]
0x18043e889  mov     rdx, [rcx]
0x18043e88c  mov     [rdx], rax
0x18043e88f  mov     rax, [rdi]
0x18043e892  mov     rcx, [rax]
0x18043e895  mov     eax, ebx
0x18043e897  mov     ebx, 8007000Eh
0x18043e89c  cmp     qword ptr [rcx], 0
0x18043e8a0  cmovz   eax, ebx
0x18043e8a3  mov     ebx, eax
0x18043e8a5  lea     rcx, [rbp+57h+pvarDest]; pvarg
0x18043e8a9  call    cs:__imp_VariantClear
0x18043e8b0  nop     dword ptr [rax+rax+00h]
0x18043e8b5  xor     eax, eax
0x18043e8b7  test    ebx, ebx
0x18043e8b9  cmovns  ebx, eax
0x18043e8bc  mov     eax, ebx
0x18043e8be  mov     rcx, [rbp+57h+var_10]
0x18043e8c2  xor     rcx, rsp; StackCookie
0x18043e8c5  call    __security_check_cookie
0x18043e8ca  lea     r11, [rsp+0D0h+var_s0]
0x18043e8d2  mov     rbx, [r11+18h]
0x18043e8d6  mov     rdi, [r11+20h]
0x18043e8da  mov     rsp, r11
0x18043e8dd  pop     rbp
0x18043e8de  retn
0x18043e8e0  mov     rdx, [rdi]
0x18043e8e3  lea     rcx, String
0x18043e8ea  cmp     qword ptr [r8+8], 0
0x18043e8ef  cmovnz  rcx, [r8+8]
0x18043e8f4  mov     rdx, [rdx]
0x18043e8f7  call    GetStringLiteral
0x18043e8fc  jmp     short loc_18043E8A3
0x18043e8fe  movsd   xmm1, qword ptr [r8+8]
0x18043e904  jmp     short loc_18043E90F
0x18043e906  movss   xmm1, dword ptr [r8+8]
0x18043e90c  cvtps2pd xmm1, xmm1
0x18043e90f  movq    rax, xmm1
0x18043e914  mov     rcx, 7FF0000000000000h
0x18043e91e  not     rax
0x18043e921  movaps  xmm0, xmm1; double
0x18043e924  test    rcx, rax
0x18043e927  jz      short loc_18043E94A
0x18043e929  mov     r8d, 40h ; '@'; int
0x18043e92f  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x18043e933  call    ?FDblToStr@NumberUtilities@Js@@SAHNPEAGH@Z; Js::NumberUtilities::FDblToStr(double,ushort *,int)
0x18043e938  test    eax, eax
0x18043e93a  jnz     loc_18043EA6E
0x18043e940  mov     ebx, 8007000Eh
0x18043e945  jmp     loc_18043E8A5
0x18043e94a  call    ?IsNan@NumberUtilities@Js@@SA_NN@Z; Js::NumberUtilities::IsNan(double)
0x18043e94f  test    al, al
0x18043e951  jz      short loc_18043E95F
0x18043e953  lea     rcx, String1; "NaN"
0x18043e95a  jmp     loc_18043E87A
0x18043e95f  xorps   xmm0, xmm0
0x18043e962  lea     rcx, aInfinity_1; "-Infinity"
0x18043e969  comisd  xmm0, xmm1
0x18043e96d  lea     rax, Source; "Infinity"
0x18043e974  cmovbe  rcx, rax
0x18043e978  jmp     loc_18043E87A
0x18043e97d  movsx   ecx, word ptr [r8+8]
0x18043e982  jmp     loc_18043EA4B
0x18043e987  lea     rcx, aNull; "null"
0x18043e98e  jmp     loc_18043E87A
0x18043e993  lea     rcx, aUndefined; "undefined"
0x18043e99a  jmp     loc_18043E87A
0x18043e99f  xor     eax, eax
0x18043e9a1  lea     rdx, aTrue; "true"
0x18043e9a8  cmp     ax, [r8+8]
0x18043e9ad  lea     rcx, aFalse; "false"
0x18043e9b4  cmovnz  rcx, rdx
0x18043e9b8  jmp     loc_18043E87A
0x18043e9bd  sub     ecx, 0Dh
0x18043e9c0  jz      loc_18043E863
0x18043e9c6  sub     ecx, 3
0x18043e9c9  jz      short loc_18043EA46
0x18043e9cb  sub     ecx, 1
0x18043e9ce  jz      short loc_18043EA09
0x18043e9d0  sub     ecx, 1
0x18043e9d3  jz      short loc_18043EA02
0x18043e9d5  sub     ecx, 1
0x18043e9d8  jz      short loc_18043E9F6
0x18043e9da  sub     ecx, 3
0x18043e9dd  jz      short loc_18043E9FC
0x18043e9df  cmp     ecx, 1
0x18043e9e2  jz      short loc_18043E9F6
0x18043e9e4  mov     rax, [rdi]
0x18043e9e7  mov     rcx, [rax]
0x18043e9ea  mov     qword ptr [rcx], 0
0x18043e9f1  jmp     loc_18043E8A5
0x18043e9f6  mov     ecx, [r8+8]
0x18043e9fa  jmp     short loc_18043EA0E
0x18043e9fc  mov     ecx, [r8+8]
0x18043ea00  jmp     short loc_18043EA4B
0x18043ea02  movzx   ecx, word ptr [r8+8]
0x18043ea07  jmp     short loc_18043EA0E
0x18043ea09  movzx   ecx, byte ptr [r8+8]; Value
0x18043ea0e  mov     rax, [rdi+10h]
0x18043ea12  cmp     dword ptr [rax], 10h
0x18043ea15  jnz     short loc_18043EA2A
0x18043ea17  mov     rdx, [rdi]
0x18043ea1a  mov     rcx, r8
0x18043ea1d  mov     rdx, [rdx]
0x18043ea20  call    GetHexLiteral
0x18043ea25  jmp     loc_18043E8A3
0x18043ea2a  mov     r9d, 0Ah; Radix
0x18043ea30  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18043ea34  lea     r8d, [r9+36h]; BufferCount
0x18043ea38  call    cs:__imp__ultow_s
0x18043ea3f  nop     dword ptr [rax+rax+00h]
0x18043ea44  jmp     short loc_18043EA6E
0x18043ea46  movsx   ecx, byte ptr [r8+8]; Value
0x18043ea4b  mov     rax, [rdi+10h]
0x18043ea4f  cmp     dword ptr [rax], 10h
0x18043ea52  jz      short loc_18043EA17
0x18043ea54  mov     r9d, 0Ah; Radix
0x18043ea5a  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18043ea5e  lea     r8d, [r9+36h]; BufferCount
0x18043ea62  call    cs:__imp__ltow_s
0x18043ea69  nop     dword ptr [rax+rax+00h]
0x18043ea6e  lea     rcx, [rbp+57h+Buffer]
0x18043ea72  jmp     loc_18043E87A
```
