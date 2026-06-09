# DataConvertForSafeArrays(ushort,ushort,void *,void *,ulong,ulong *,unsigned __int64 *)

- ea: `0x18003ecf0`
- end: `0x18003ef15`
- name: `?DataConvertForSafeArrays@@YAJGGPEAX0KPEAKPEA_K@Z`
- size: `549`
- prototype: `int(unsigned __int16, unsigned __int16, void *, void *, unsigned int, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003320`

## callees

- `0x180013870`
- `0x180025108`
- `0x180029560`
- `0x18003ecf0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003edc3`
- `OLEAUT32!__imp_VariantInit` at `0x18003edc3`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18003edae`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18003edae`

## pseudocode

```c
__int64 __fastcall DataConvertForSafeArrays(
        VARTYPE a1,
        __int16 a2,
        SAFEARRAY **a3,
        VARIANTARG *a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned __int64 *a7)
{
  unsigned __int64 v11; // rcx
  SAFEARRAY *v12; // rcx
  HRESULT v13; // eax
  unsigned int v14; // ebx
  __int64 v16; // rdx
  SAFEARRAY *ppsaOut; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 v18; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int16 v19; // [rsp+58h] [rbp+10h] BYREF

  v18 = 0;
  v19 = 0;
  if ( a1 != a2 && a2 != 12 || (int)GetSafeArraySizeAndFeatures(a1 & 0xDFFF, &v18, &v19) < 0 )
  {
    v14 = -2147217891;
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    OLEDBTraceErr(-2147217891, L"<DataConvertForSafeArrays|OLEDB|ERR> ", 0x36Du);
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    v16 = 899081;
    return (unsigned int)bidTraceHR(off_1800C8390[0], v16, L"<DataConvertForSafeArrays|Trace|HR> ", v14);
  }
  if ( !a4 )
  {
    *a7 = 8;
    return 0;
  }
  v11 = 24;
  if ( a2 != 12 )
    v11 = 8;
  *a7 = v11;
  if ( !a3 || (v12 = *a3) == 0 )
  {
    if ( !a5 )
      *a6 = 8;
    v14 = -2147467259;
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    OLEDBTraceErr(-2147467259, L"<DataConvertForSafeArrays|OLEDB|ERR> ", 0x35Bu);
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    v16 = 880649;
    return (unsigned int)bidTraceHR(off_1800C8390[0], v16, L"<DataConvertForSafeArrays|Trace|HR> ", v14);
  }
  ppsaOut = 0;
  if ( v12->cbElements != v18 || v19 && (v19 & v12->fFeatures) == 0 )
  {
    v14 = -2147217887;
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    OLEDBTraceErr(-2147217887, L"<DataConvertForSafeArrays|OLEDB|ERR> ", 0x351u);
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    v16 = 870409;
    return (unsigned int)bidTraceHR(off_1800C8390[0], v16, L"<DataConvertForSafeArrays|Trace|HR> ", v14);
  }
  v13 = SafeArrayCopy(v12, &ppsaOut);
  v14 = v13;
  if ( v13 >= 0 )
  {
    if ( a2 == 12 )
    {
      VariantInit(a4);
      a4->llVal = (LONGLONG)ppsaOut;
      a4->vt = a1;
    }
    else
    {
      *(_QWORD *)&a4->vt = ppsaOut;
    }
    return 0;
  }
  if ( v13 == -2147024809 )
  {
    v14 = -2147217887;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147217887, L"<DataConvertForSafeArrays|OLEDB|ERR> ", 0x347u);
      if ( (bidGblFlags & 2) != 0 )
      {
        v16 = 862217;
        return (unsigned int)bidTraceHR(off_1800C8390[0], v16, L"<DataConvertForSafeArrays|Trace|HR> ", v14);
      }
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18003ecf0  mov     rax, rsp
0x18003ecf3  mov     [rax+18h], rbx
0x18003ecf7  mov     [rax+20h], rbp
0x18003ecfb  push    rsi
0x18003ecfc  push    rdi
0x18003ecfd  push    r14
0x18003ecff  sub     rsp, 30h
0x18003ed03  xor     r14d, r14d
0x18003ed06  mov     rdi, r9
0x18003ed09  mov     [rax+8], r14w
0x18003ed0e  mov     rbx, r8
0x18003ed11  mov     [rax+10h], r14w
0x18003ed16  movzx   esi, dx
0x18003ed19  movzx   ebp, cx
0x18003ed1c  cmp     cx, dx
0x18003ed1f  jz      short loc_18003ED2B
0x18003ed21  cmp     dx, 0Ch
0x18003ed25  jnz     loc_18003EEB6
0x18003ed2b  mov     eax, 0DFFFh
0x18003ed30  lea     r8, [rsp+48h+arg_8]; unsigned __int16 *
0x18003ed35  and     cx, ax; unsigned __int16
0x18003ed38  lea     rdx, [rsp+48h+arg_0]; unsigned __int16 *
0x18003ed3d  call    ?GetSafeArraySizeAndFeatures@@YAJGPEAG0@Z; GetSafeArraySizeAndFeatures(ushort,ushort *,ushort *)
0x18003ed42  test    eax, eax
0x18003ed44  js      loc_18003EEB6
0x18003ed4a  mov     rax, [rsp+48h+arg_30]
0x18003ed52  mov     edx, 8
0x18003ed57  test    rdi, rdi
0x18003ed5a  jz      loc_18003EEAE
0x18003ed60  cmp     si, 0Ch
0x18003ed64  lea     ecx, [rdx+10h]
0x18003ed67  cmovnz  ecx, edx
0x18003ed6a  mov     [rax], rcx
0x18003ed6d  test    rbx, rbx
0x18003ed70  jz      loc_18003EE6C
0x18003ed76  mov     rcx, [rbx]; psa
0x18003ed79  test    rcx, rcx
0x18003ed7c  jz      loc_18003EE6C
0x18003ed82  movzx   eax, [rsp+48h+arg_0]
0x18003ed87  mov     [rsp+48h+ppsaOut], r14
0x18003ed8c  cmp     [rcx+4], eax
0x18003ed8f  jnz     loc_18003EE30
0x18003ed95  movzx   eax, [rsp+48h+arg_8]
0x18003ed9a  test    ax, ax
0x18003ed9d  jz      short loc_18003EDA9
0x18003ed9f  test    [rcx+2], ax
0x18003eda3  jz      loc_18003EE30
0x18003eda9  lea     rdx, [rsp+48h+ppsaOut]; ppsaOut
0x18003edae  call    cs:__imp_SafeArrayCopy
0x18003edb4  mov     ebx, eax
0x18003edb6  test    eax, eax
0x18003edb8  js      short loc_18003EDE6
0x18003edba  cmp     si, 0Ch
0x18003edbe  jnz     short loc_18003EDD7
0x18003edc0  mov     rcx, rdi; pvarg
0x18003edc3  call    cs:__imp_VariantInit
0x18003edc9  mov     rax, [rsp+48h+ppsaOut]
0x18003edce  mov     [rdi+8], rax
0x18003edd2  mov     [rdi], bp
0x18003edd5  jmp     short loc_18003EDDF
0x18003edd7  mov     rax, [rsp+48h+ppsaOut]
0x18003eddc  mov     [rdi], rax
0x18003eddf  xor     eax, eax
0x18003ede1  jmp     loc_18003EF02
0x18003ede6  cmp     eax, 80070057h
0x18003edeb  jnz     loc_18003EF00
0x18003edf1  mov     eax, cs:_bidGblFlags
0x18003edf7  mov     ebx, 80040E21h
0x18003edfc  test    al, 2
0x18003edfe  jz      loc_18003EF00
0x18003ee04  mov     r8d, 347h; unsigned int
0x18003ee0a  lea     rdx, aDataconvertfor_0; "<DataConvertForSafeArrays|OLEDB|ERR> "
0x18003ee11  mov     ecx, ebx; int
0x18003ee13  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003ee18  mov     eax, cs:_bidGblFlags
0x18003ee1e  test    al, 2
0x18003ee20  jz      loc_18003EF00
0x18003ee26  mov     edx, 0D2809h
0x18003ee2b  jmp     loc_18003EEE8
0x18003ee30  mov     eax, cs:_bidGblFlags
0x18003ee36  mov     ebx, 80040E21h
0x18003ee3b  test    al, 2
0x18003ee3d  jz      loc_18003EF00
0x18003ee43  mov     r8d, 351h; unsigned int
0x18003ee49  lea     rdx, aDataconvertfor_0; "<DataConvertForSafeArrays|OLEDB|ERR> "
0x18003ee50  mov     ecx, ebx; int
0x18003ee52  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003ee57  mov     eax, cs:_bidGblFlags
0x18003ee5d  test    al, 2
0x18003ee5f  jz      loc_18003EF00
0x18003ee65  mov     edx, 0D4809h
0x18003ee6a  jmp     short loc_18003EEE8
0x18003ee6c  cmp     [rsp+48h+arg_20], r14d
0x18003ee71  jnz     short loc_18003EE7A
0x18003ee73  mov     rax, [rsp+48h+arg_28]
0x18003ee78  mov     [rax], edx
0x18003ee7a  mov     eax, cs:_bidGblFlags
0x18003ee80  mov     ebx, 80004005h
0x18003ee85  test    al, 2
0x18003ee87  jz      short loc_18003EF00
0x18003ee89  mov     r8d, 35Bh; unsigned int
0x18003ee8f  lea     rdx, aDataconvertfor_0; "<DataConvertForSafeArrays|OLEDB|ERR> "
0x18003ee96  mov     ecx, ebx; int
0x18003ee98  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003ee9d  mov     eax, cs:_bidGblFlags
0x18003eea3  test    al, 2
0x18003eea5  jz      short loc_18003EF00
0x18003eea7  mov     edx, 0D7009h
0x18003eeac  jmp     short loc_18003EEE8
0x18003eeae  mov     [rax], rdx
0x18003eeb1  jmp     loc_18003EDDF
0x18003eeb6  mov     eax, cs:_bidGblFlags
0x18003eebc  mov     ebx, 80040E1Dh
0x18003eec1  test    al, 2
0x18003eec3  jz      short loc_18003EF00
0x18003eec5  mov     r8d, 36Dh; unsigned int
0x18003eecb  lea     rdx, aDataconvertfor_0; "<DataConvertForSafeArrays|OLEDB|ERR> "
0x18003eed2  mov     ecx, ebx; int
0x18003eed4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003eed9  mov     eax, cs:_bidGblFlags
0x18003eedf  test    al, 2
0x18003eee1  jz      short loc_18003EF00
0x18003eee3  mov     edx, 0DB809h
0x18003eee8  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18003eeef  lea     r8, aDataconvertfor; "<DataConvertForSafeArrays|Trace|HR> "
0x18003eef6  mov     r9d, ebx
0x18003eef9  call    _bidTraceHR
0x18003eefe  mov     ebx, eax
0x18003ef00  mov     eax, ebx
0x18003ef02  mov     rbx, [rsp+48h+arg_10]
0x18003ef07  mov     rbp, [rsp+48h+arg_18]
0x18003ef0c  add     rsp, 30h
0x18003ef10  pop     r14
0x18003ef12  pop     rdi
0x18003ef13  pop     rsi
0x18003ef14  retn
```
