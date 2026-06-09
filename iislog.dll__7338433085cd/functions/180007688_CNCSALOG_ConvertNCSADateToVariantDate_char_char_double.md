# CNCSALOG::ConvertNCSADateToVariantDate(char *,char *,double *)

- ea: `0x180007688`
- end: `0x18000789b`
- name: `?ConvertNCSADateToVariantDate@CNCSALOG@@AEAAHPEAD0PEAN@Z`
- size: `531`
- prototype: `int(CNCSALOG *__hidden this, char *, char *, double *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007d20`

## callees

- `0x180007688`
- `0x18000ec6e`
- `0x18000eca0`

## import_xrefs

- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18000787b`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18000787b`

## pseudocode

```c
INT __fastcall CNCSALOG::ConvertNCSADateToVariantDate(CNCSALOG *this, char *a2, char *a3, double *a4)
{
  char *v4; // rbx
  WORD v7; // ax
  bool v8; // zf
  WORD v9; // cx
  WORD v10; // ax
  WORD v11; // di
  char *v12; // r8
  WORD v13; // ax
  WORD v14; // cx
  char *v15; // rdx
  WORD v16; // ax
  WORD v17; // cx
  WORD v18; // ax
  WORD v19; // cx
  char *Str2[12]; // [rsp+20h] [rbp-49h]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp+17h] BYREF

  Str2[0] = "Jan";
  v4 = a2 + 1;
  Str2[1] = "Feb";
  Str2[2] = "Mar";
  Str2[3] = "Apr";
  Str2[4] = "May";
  Str2[5] = "Jun";
  Str2[6] = "Jul";
  Str2[7] = "Aug";
  Str2[8] = "Sep";
  Str2[9] = "Oct";
  Str2[10] = "Nov";
  Str2[11] = "Dec";
  v7 = *a2 - 48;
  v8 = a2[1] == 47;
  v9 = v7;
  SystemTime = 0;
  if ( v8 )
    v4 = a2;
  else
    v9 = *v4 - 48 + 10 * v7;
  SystemTime.wDay = v9;
  v10 = 0;
  while ( 1 )
  {
    v11 = v10 + 1;
    if ( !strncmp_0(v4 + 2, Str2[v10], 3u) )
      break;
    v10 = v11;
    if ( v11 >= 0xCu )
      goto LABEL_9;
  }
  SystemTime.wMonth = v11;
LABEL_9:
  v12 = a3 + 1;
  v13 = *a3 - 48;
  SystemTime.wYear = v4[9] + 10 * (v4[8] + 10 * (v4[7] + 10 * v4[6])) + 12208;
  v14 = v13;
  if ( a3[1] == 58 )
    v12 = a3;
  else
    v14 = *v12 - 48 + 10 * v13;
  v15 = v12 + 3;
  v16 = v12[2] - 48;
  SystemTime.wHour = v14;
  v17 = v16;
  if ( v12[3] == 58 )
    v15 = v12 + 2;
  else
    v17 = *v15 + 10 * v16 - 48;
  v18 = v15[2] - 48;
  SystemTime.wMinute = v17;
  v19 = v18;
  if ( v15[3] )
    v19 = v15[3] + 10 * v18 - 48;
  SystemTime.wSecond = v19;
  return SystemTimeToVariantTime(&SystemTime, a4);
}

```

## disassembly

```asm
0x180007688  push    rbp
0x18000768a  push    rbx
0x18000768b  push    rsi
0x18000768c  push    rdi
0x18000768d  push    r14
0x18000768f  lea     rbp, [rsp-37h]
0x180007694  sub     rsp, 0A0h
0x18000769b  mov     rax, cs:__security_cookie
0x1800076a2  xor     rax, rsp
0x1800076a5  mov     [rbp+57h+var_30], rax
0x1800076a9  lea     rax, aJan; "Jan"
0x1800076b0  xorps   xmm0, xmm0
0x1800076b3  mov     [rbp+57h+Str2], rax
0x1800076b7  lea     rbx, [rdx+1]
0x1800076bb  lea     rax, aFeb; "Feb"
0x1800076c2  mov     r14, r9
0x1800076c5  mov     [rbp+57h+var_98], rax
0x1800076c9  mov     rsi, r8
0x1800076cc  lea     rax, aMar; "Mar"
0x1800076d3  mov     [rbp+57h+var_90], rax
0x1800076d7  lea     rax, aApr; "Apr"
0x1800076de  mov     [rbp+57h+var_88], rax
0x1800076e2  lea     rax, aMay; "May"
0x1800076e9  mov     [rbp+57h+var_80], rax
0x1800076ed  lea     rax, aJun; "Jun"
0x1800076f4  mov     [rbp+57h+var_78], rax
0x1800076f8  lea     rax, aJul; "Jul"
0x1800076ff  mov     [rbp+57h+var_70], rax
0x180007703  lea     rax, aAug; "Aug"
0x18000770a  mov     [rbp+57h+var_68], rax
0x18000770e  lea     rax, aSep; "Sep"
0x180007715  mov     [rbp+57h+var_60], rax
0x180007719  lea     rax, aOct; "Oct"
0x180007720  mov     [rbp+57h+var_58], rax
0x180007724  lea     rax, aNov; "Nov"
0x18000772b  mov     [rbp+57h+var_50], rax
0x18000772f  lea     rax, aDec; "Dec"
0x180007736  mov     [rbp+57h+var_48], rax
0x18000773a  movsx   eax, byte ptr [rdx]
0x18000773d  sub     ax, 30h ; '0'
0x180007741  cmp     byte ptr [rbx], 2Fh ; '/'
0x180007744  movzx   ecx, ax
0x180007747  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18000774b  jz      short loc_180007763
0x18000774d  shl     ax, 2
0x180007751  add     cx, ax
0x180007754  movsx   eax, byte ptr [rbx]
0x180007757  sub     ax, 30h ; '0'
0x18000775b  add     cx, cx
0x18000775e  add     cx, ax
0x180007761  jmp     short loc_180007766
0x180007763  mov     rbx, rdx
0x180007766  mov     [rbp+57h+SystemTime.wDay], cx
0x18000776a  xor     eax, eax
0x18000776c  movzx   edx, ax
0x18000776f  lea     rcx, [rbx+2]; Str1
0x180007773  mov     r8d, 3; MaxCount
0x180007779  lea     edi, [rax+1]
0x18000777c  mov     rdx, [rbp+rdx*8+57h+Str2]; Str2
0x180007781  call    strncmp_0
0x180007786  test    eax, eax
0x180007788  jz      short loc_180007795
0x18000778a  movzx   eax, di
0x18000778d  cmp     di, 0Ch
0x180007791  jb      short loc_18000776C
0x180007793  jmp     short loc_180007799
0x180007795  mov     [rbp+57h+SystemTime.wMonth], di
0x180007799  movsx   ecx, byte ptr [rbx+6]
0x18000779d  lea     r8, [rsi+1]
0x1800077a1  movzx   eax, cx
0x1800077a4  shl     ax, 2
0x1800077a8  add     cx, ax
0x1800077ab  movsx   eax, byte ptr [rbx+7]
0x1800077af  add     cx, cx
0x1800077b2  add     cx, ax
0x1800077b5  movzx   eax, cx
0x1800077b8  shl     ax, 2
0x1800077bc  add     cx, ax
0x1800077bf  movsx   eax, byte ptr [rbx+8]
0x1800077c3  add     cx, cx
0x1800077c6  add     cx, ax
0x1800077c9  movzx   eax, cx
0x1800077cc  shl     ax, 2
0x1800077d0  add     cx, ax
0x1800077d3  movsx   eax, byte ptr [rbx+9]
0x1800077d7  add     cx, cx
0x1800077da  add     cx, ax
0x1800077dd  mov     eax, 2FB0h
0x1800077e2  add     cx, ax
0x1800077e5  movsx   eax, byte ptr [rsi]
0x1800077e8  sub     ax, 30h ; '0'
0x1800077ec  mov     [rbp+57h+SystemTime.wYear], cx
0x1800077f0  cmp     byte ptr [r8], 3Ah ; ':'
0x1800077f4  movzx   ecx, ax
0x1800077f7  jz      short loc_180007810
0x1800077f9  shl     ax, 2
0x1800077fd  add     cx, ax
0x180007800  movsx   eax, byte ptr [r8]
0x180007804  sub     ax, 30h ; '0'
0x180007808  add     cx, cx
0x18000780b  add     cx, ax
0x18000780e  jmp     short loc_180007813
0x180007810  mov     r8, rsi
0x180007813  movsx   eax, byte ptr [r8+2]
0x180007818  lea     rdx, [r8+3]
0x18000781c  sub     ax, 30h ; '0'
0x180007820  mov     [rbp+57h+SystemTime.wHour], cx
0x180007824  cmp     byte ptr [rdx], 3Ah ; ':'
0x180007827  movzx   ecx, ax
0x18000782a  jz      short loc_180007842
0x18000782c  shl     ax, 2
0x180007830  add     cx, ax
0x180007833  movsx   eax, byte ptr [rdx]
0x180007836  add     cx, cx
0x180007839  sub     cx, 30h ; '0'
0x18000783d  add     cx, ax
0x180007840  jmp     short loc_180007846
0x180007842  lea     rdx, [r8+2]
0x180007846  movsx   eax, byte ptr [rdx+2]
0x18000784a  sub     ax, 30h ; '0'
0x18000784e  mov     [rbp+57h+SystemTime.wMinute], cx
0x180007852  cmp     byte ptr [rdx+3], 0
0x180007856  movzx   ecx, ax
0x180007859  jz      short loc_180007870
0x18000785b  shl     ax, 2
0x18000785f  add     cx, ax
0x180007862  movsx   eax, byte ptr [rdx+3]
0x180007866  add     cx, cx
0x180007869  sub     cx, 30h ; '0'
0x18000786d  add     cx, ax
0x180007870  mov     [rbp+57h+SystemTime.wSecond], cx
0x180007874  mov     rdx, r14; pvtime
0x180007877  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18000787b  call    cs:__imp_SystemTimeToVariantTime
0x180007881  mov     rcx, [rbp+57h+var_30]
0x180007885  xor     rcx, rsp; StackCookie
0x180007888  call    __security_check_cookie
0x18000788d  add     rsp, 0A0h
0x180007894  pop     r14
0x180007896  pop     rdi
0x180007897  pop     rsi
0x180007898  pop     rbx
0x180007899  pop     rbp
0x18000789a  retn
```
