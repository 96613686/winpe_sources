# CParamProps::IsValidValue(ulong,tagDBPROP *)

- ea: `0x1800dfff0`
- end: `0x1800e01e3`
- name: `?IsValidValue@CParamProps@@EEAAJKPEAUtagDBPROP@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(CParamProps *__hidden this, unsigned int, struct tagDBPROP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180003d80`
- `0x1800dfff0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800e00bf`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e00bf`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800e00e7`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800e00e7`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1800e00f5`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1800e00f5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800e012f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800e012f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800e0111`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800e0111`

## pseudocode

```c
_BOOL8 __fastcall CParamProps::IsValidValue(CParamProps *this, int a2, struct tagDBPROP *a3)
{
  int v4; // eax
  bool v5; // zf
  unsigned int v6; // eax
  int v7; // ecx
  SAFEARRAY *parray; // rdi
  unsigned int v10; // eax
  unsigned int v11; // eax
  LONG plUbound; // [rsp+20h] [rbp-18h] BYREF
  LONG plLbound; // [rsp+24h] [rbp-14h] BYREF

  plLbound = 0;
  plUbound = 0;
  if ( !a2 )
  {
    switch ( a3->dwPropertyID )
    {
      case 0x18u:
      case 0x19u:
      case 0x1Au:
        v4 = *((_DWORD *)this + 144);
        if ( v4 == 141 )
          goto LABEL_11;
        v5 = v4 == 130;
        goto LABEL_10;
      case 0x1Bu:
      case 0x1Cu:
      case 0x1Du:
      case 0x26u:
        v5 = ((*((_DWORD *)this + 144) - 128) & 0xFFFFFFFB) == 0;
        goto LABEL_10;
      case 0x27u:
      case 0x28u:
        v6 = *((_DWORD *)this + 144) - 128;
        if ( v6 > 0xF )
          return 1;
        v7 = 32785;
        if ( !_bittest(&v7, v6) )
          return 1;
        goto LABEL_11;
      case 0x29u:
      case 0x2Au:
        v5 = *((_DWORD *)this + 144) == 143;
LABEL_10:
        if ( v5 )
        {
LABEL_11:
          switch ( a3->dwPropertyID )
          {
            case 0x18u:
            case 0x19u:
            case 0x1Au:
            case 0x1Bu:
            case 0x1Cu:
            case 0x1Du:
            case 0x26u:
            case 0x27u:
            case 0x28u:
              return a3->vValue.vt != 8 || SysStringLen(a3->vValue.bstrVal) - 1 > 0x7F;
            case 0x29u:
            case 0x2Au:
              if ( a3->vValue.vt != 8210 )
                return 1;
              parray = a3->vValue.parray;
              if ( !parray )
                return 1;
              if ( SafeArrayGetDim(a3->vValue.parray) != 1 )
                return 1;
              if ( SafeArrayGetElemsize(parray) != 2 )
                return 1;
              if ( SafeArrayGetLBound(parray, 1u, &plLbound) < 0 )
                return 1;
              _mm_lfence();
              if ( SafeArrayGetUBound(parray, 1u, &plUbound) < 0 )
                return 1;
              v10 = plUbound - plLbound;
              if ( a3->dwPropertyID == 41 )
                return v10 >= 0x400;
              v11 = v10 + 1;
              if ( v11 <= 0x800 && (v11 & 1) == 0 )
                return 0;
              break;
            default:
              return 1;
          }
        }
        break;
      default:
        return 1;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800dfff0  mov     [rsp+arg_0], rbx
0x1800dfff5  push    rdi
0x1800dfff6  sub     rsp, 30h
0x1800dfffa  mov     rax, cs:__security_cookie
0x1800e0001  xor     rax, rsp
0x1800e0004  mov     [rsp+38h+var_10], rax
0x1800e0009  xor     eax, eax
0x1800e000b  mov     rbx, r8
0x1800e000e  mov     [rsp+38h+plLbound], eax
0x1800e0012  mov     [rsp+38h+plUbound], eax
0x1800e0016  test    edx, edx
0x1800e0018  jnz     short def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e001a  mov     edx, [r8]
0x1800e001d  add     edx, 0FFFFFFE8h; switch 19 cases
0x1800e0020  cmp     edx, 12h
0x1800e0023  ja      short def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e0025  lea     r8, cs:180000000h
0x1800e002c  mov     eax, ds:(jpt_1800E0037 - 180000000h)[r8+rdx*4]
0x1800e0034  add     rax, r8
0x1800e0037  jmp     rax; switch jump
0x1800e0039  mov     eax, [rcx+240h]; jumptable 00000001800E0037 cases 24-26
0x1800e003f  cmp     eax, 8Dh
0x1800e0044  jz      short loc_1800E009E
0x1800e0046  cmp     eax, 82h
0x1800e004b  jmp     short loc_1800E009C
0x1800e004d  mov     eax, [rcx+240h]; jumptable 00000001800E0037 cases 27-29,38
0x1800e0053  add     eax, 0FFFFFF80h
0x1800e0056  test    eax, 0FFFFFFFBh
0x1800e005b  jmp     short loc_1800E009C
0x1800e005d  mov     eax, [rcx+240h]; jumptable 00000001800E0037 cases 39,40
0x1800e0063  add     eax, 0FFFFFF80h
0x1800e0066  cmp     eax, 0Fh
0x1800e0069  ja      short def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e006b  mov     ecx, 8011h
0x1800e0070  bt      ecx, eax
0x1800e0073  jb      short loc_1800E009E
0x1800e0075  mov     eax, 1; jumptable 00000001800E0037 default case, cases 30-37
0x1800e007a  mov     rcx, [rsp+38h+var_10]
0x1800e007f  xor     rcx, rsp; StackCookie
0x1800e0082  call    __security_check_cookie
0x1800e0087  mov     rbx, [rsp+38h+arg_0]
0x1800e008c  add     rsp, 30h
0x1800e0090  pop     rdi
0x1800e0091  retn
0x1800e0092  cmp     dword ptr [rcx+240h], 8Fh; jumptable 00000001800E0037 cases 41,42
0x1800e009c  jnz     short def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e009e  movzx   eax, ds:(byte_1800E01D0 - 180000000h)[r8+rdx]
0x1800e00a7  mov     ecx, ds:(jpt_1800E00B2 - 180000000h)[r8+rax*4]
0x1800e00af  add     rcx, r8
0x1800e00b2  jmp     rcx; switch jump
0x1800e00b4  cmp     word ptr [rbx+30h], 8; jumptable 00000001800E00B2 cases 24-29,38-40
0x1800e00b9  jnz     short def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e00bb  mov     rcx, [rbx+38h]; pbstr
0x1800e00bf  call    cs:__imp_SysStringLen
0x1800e00c5  dec     eax
0x1800e00c7  cmp     eax, 7Fh
0x1800e00ca  ja      short def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e00cc  xor     eax, eax
0x1800e00ce  jmp     short loc_1800E007A
0x1800e00d0  mov     eax, 2012h; jumptable 00000001800E00B2 cases 41,42
0x1800e00d5  cmp     [rbx+30h], ax
0x1800e00d9  jnz     short def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e00db  mov     rdi, [rbx+38h]
0x1800e00df  test    rdi, rdi
0x1800e00e2  jz      short def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e00e4  mov     rcx, rdi; psa
0x1800e00e7  call    cs:__imp_SafeArrayGetDim
0x1800e00ed  cmp     eax, 1
0x1800e00f0  jnz     short def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e00f2  mov     rcx, rdi; psa
0x1800e00f5  call    cs:__imp_SafeArrayGetElemsize
0x1800e00fb  cmp     eax, 2
0x1800e00fe  jnz     def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e0104  lea     r8, [rsp+38h+plLbound]; plLbound
0x1800e0109  mov     edx, 1; nDim
0x1800e010e  mov     rcx, rdi; psa
0x1800e0111  call    cs:__imp_SafeArrayGetLBound
0x1800e0117  test    eax, eax
0x1800e0119  js      def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e011f  lfence
0x1800e0122  lea     r8, [rsp+38h+plUbound]; plUbound
0x1800e0127  mov     edx, 1; nDim
0x1800e012c  mov     rcx, rdi; psa
0x1800e012f  call    cs:__imp_SafeArrayGetUBound
0x1800e0135  test    eax, eax
0x1800e0137  js      def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e013d  mov     eax, [rsp+38h+plUbound]
0x1800e0141  sub     eax, [rsp+38h+plLbound]
0x1800e0145  cmp     dword ptr [rbx], 29h ; ')'
0x1800e0148  jnz     short loc_1800E015C
0x1800e014a  cmp     eax, 400h
0x1800e014f  jnb     def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e0155  xor     eax, eax
0x1800e0157  jmp     loc_1800E007A
0x1800e015c  inc     eax
0x1800e015e  cmp     eax, 800h
0x1800e0163  ja      def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e0169  test    al, 1
0x1800e016b  jnz     def_1800E0037; jumptable 00000001800E0037 default case, cases 30-37
0x1800e0171  xor     eax, eax
0x1800e0173  jmp     loc_1800E007A
```
