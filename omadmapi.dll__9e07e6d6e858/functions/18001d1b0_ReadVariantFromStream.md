# ReadVariantFromStream

- ea: `0x18001d1b0`
- end: `0x18001d3b7`
- name: `ReadVariantFromStream`
- size: `519`
- prototype: `__int64 __fastcall(VARIANTARG *pvargDest, struct ISequentialStream *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001cb1c`
- `0x18001cf70`
- `0x18001d1b0`
- `0x180024010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001d1e8`
- `OLEAUT32!__imp_VariantInit` at `0x18001d1e8`
- `OLEAUT32!__imp_VariantClear` at `0x18001d20b`
- `OLEAUT32!__imp_VariantClear` at `0x18001d28f`
- `OLEAUT32!__imp_VariantClear` at `0x18001d20b`
- `OLEAUT32!__imp_VariantClear` at `0x18001d28f`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001d368`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001d368`

## pseudocode

```c
__int64 __fastcall ReadVariantFromStream(VARIANTARG *pvargDest, struct ISequentialStream *a2)
{
  int SafeArrayFromStream; // ebx
  unsigned int v5; // edi
  int v6; // ecx
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  VARTYPE v9; // [rsp+80h] [rbp+30h] BYREF
  int v10; // [rsp+90h] [rbp+40h] BYREF

  v10 = 0;
  v9 = 1;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !pvargDest || !a2 )
  {
    SafeArrayFromStream = -2147467261;
    goto LABEL_17;
  }
  VariantClear(pvargDest);
  v5 = 2;
  SafeArrayFromStream = ((__int64 (__fastcall *)(struct ISequentialStream *, VARTYPE *, __int64, int *))a2->lpVtbl->Read)(
                          a2,
                          &v9,
                          2,
                          &v10);
  if ( SafeArrayFromStream < 0 )
    goto LABEL_17;
  if ( v10 != 2 )
  {
LABEL_6:
    SafeArrayFromStream = -2147467259;
    goto LABEL_17;
  }
  if ( v9 > 0xBu )
  {
    if ( v9 == 13 )
      goto LABEL_16;
    if ( v9 != 16 && v9 != 17 )
    {
      if ( v9 == 18 )
        goto LABEL_34;
      if ( v9 == 19 )
        goto LABEL_32;
      v6 = v9 - 22;
      if ( v9 == 22 )
        goto LABEL_32;
      goto LABEL_25;
    }
    v5 = 1;
LABEL_34:
    SafeArrayFromStream = ((__int64 (__fastcall *)(struct ISequentialStream *, ULONG *, _QWORD, int *))a2->lpVtbl->Read)(
                            a2,
                            &pvargDest->decVal.Lo32,
                            v5,
                            &v10);
    if ( SafeArrayFromStream < 0 )
      goto LABEL_17;
    if ( v5 != v10 )
      goto LABEL_6;
LABEL_28:
    pvargDest->vt = v9;
    goto LABEL_17;
  }
  switch ( v9 )
  {
    case 0xBu:
    case 2u:
      goto LABEL_34;
    case 3u:
    case 4u:
      goto LABEL_32;
    case 5u:
    case 6u:
    case 7u:
      v5 = 8;
      goto LABEL_34;
  }
  v6 = v9 - 9;
  if ( v9 == 9 )
  {
LABEL_16:
    SafeArrayFromStream = -2147418113;
    goto LABEL_17;
  }
LABEL_25:
  if ( v6 == 1 )
  {
LABEL_32:
    v5 = 4;
    goto LABEL_34;
  }
  if ( (v9 & 0x2000) != 0 )
  {
    SafeArrayFromStream = ReadSafeArrayFromStream(&pvargDest->parray, v9 & 0xDFFF, a2);
    if ( SafeArrayFromStream < 0 )
      goto LABEL_17;
    goto LABEL_28;
  }
  if ( v9 != 1 )
  {
    pvarg.llVal = 0;
    pvarg.vt = 8;
    SafeArrayFromStream = ReadBSTRFromStream(&pvarg.decVal.Lo32, a2);
    if ( SafeArrayFromStream >= 0 )
      SafeArrayFromStream = VariantChangeType(pvargDest, &pvarg, 1u, v9);
  }
LABEL_17:
  VariantClear(&pvarg);
  return (unsigned int)SafeArrayFromStream;
}

```

## disassembly

```asm
0x18001d1b0  mov     [rsp-28h+arg_8], rbx
0x18001d1b5  push    rbp
0x18001d1b6  push    rsi
0x18001d1b7  push    rdi
0x18001d1b8  push    r14
0x18001d1ba  push    r15
0x18001d1bc  mov     rbp, rsp
0x18001d1bf  sub     rsp, 50h
0x18001d1c3  xor     eax, eax
0x18001d1c5  mov     rsi, rcx
0x18001d1c8  xorps   xmm0, xmm0
0x18001d1cb  mov     qword ptr [rbp+pvarg+10h], rax
0x18001d1cf  mov     r15d, 1
0x18001d1d5  mov     [rbp+arg_10], eax
0x18001d1d8  lea     rcx, [rbp+pvarg]; pvarg
0x18001d1dc  mov     [rbp+arg_0], r15w
0x18001d1e1  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001d1e5  mov     r14, rdx
0x18001d1e8  call    cs:__imp_VariantInit
0x18001d1ef  nop     dword ptr [rax+rax+00h]
0x18001d1f4  test    rsi, rsi
0x18001d1f7  jnz     short loc_18001D203
0x18001d1f9  mov     ebx, 80004003h
0x18001d1fe  jmp     loc_18001D28B
0x18001d203  test    r14, r14
0x18001d206  jz      short loc_18001D1F9
0x18001d208  mov     rcx, rsi; pvarg
0x18001d20b  call    cs:__imp_VariantClear
0x18001d212  nop     dword ptr [rax+rax+00h]
0x18001d217  mov     rax, [r14]
0x18001d21a  lea     r9, [rbp+arg_10]
0x18001d21e  mov     edi, 2
0x18001d223  lea     rdx, [rbp+arg_0]
0x18001d227  mov     r8d, edi
0x18001d22a  mov     rcx, r14
0x18001d22d  mov     rax, [rax+18h]
0x18001d231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d236  mov     ebx, eax
0x18001d238  test    eax, eax
0x18001d23a  js      short loc_18001D28B
0x18001d23c  cmp     [rbp+arg_10], edi
0x18001d23f  jz      short loc_18001D248
0x18001d241  mov     ebx, 80004005h
0x18001d246  jmp     short loc_18001D28B
0x18001d248  movzx   edx, [rbp+arg_0]
0x18001d24c  mov     ecx, edx
0x18001d24e  cmp     edx, 0Bh
0x18001d251  ja      short loc_18001D2BC
0x18001d253  jz      loc_18001D385
0x18001d259  sub     ecx, edi
0x18001d25b  jz      loc_18001D385
0x18001d261  sub     ecx, r15d
0x18001d264  jz      loc_18001D37B
0x18001d26a  sub     ecx, r15d
0x18001d26d  jz      loc_18001D37B
0x18001d273  sub     ecx, r15d
0x18001d276  jz      short loc_18001D2B2
0x18001d278  sub     ecx, r15d
0x18001d27b  jz      short loc_18001D2B2
0x18001d27d  sub     ecx, r15d
0x18001d280  jz      short loc_18001D2B2
0x18001d282  sub     ecx, edi
0x18001d284  jnz     short loc_18001D2EE
0x18001d286  mov     ebx, 8000FFFFh
0x18001d28b  lea     rcx, [rbp+pvarg]; pvarg
0x18001d28f  call    cs:__imp_VariantClear
0x18001d296  nop     dword ptr [rax+rax+00h]
0x18001d29b  mov     eax, ebx
0x18001d29d  mov     rbx, [rsp+50h+arg_8]
0x18001d2a5  add     rsp, 50h
0x18001d2a9  pop     r15
0x18001d2ab  pop     r14
0x18001d2ad  pop     rdi
0x18001d2ae  pop     rsi
0x18001d2af  pop     rbp
0x18001d2b0  retn
0x18001d2b2  mov     edi, 8
0x18001d2b7  jmp     loc_18001D385
0x18001d2bc  sub     ecx, 0Dh
0x18001d2bf  jz      short loc_18001D286
0x18001d2c1  sub     ecx, 3
0x18001d2c4  jz      loc_18001D382
0x18001d2ca  sub     ecx, r15d
0x18001d2cd  jz      loc_18001D382
0x18001d2d3  sub     ecx, r15d
0x18001d2d6  jz      loc_18001D385
0x18001d2dc  sub     ecx, r15d
0x18001d2df  jz      loc_18001D37B
0x18001d2e5  sub     ecx, 3
0x18001d2e8  jz      loc_18001D37B
0x18001d2ee  cmp     ecx, r15d
0x18001d2f1  jz      loc_18001D37B
0x18001d2f7  bt      dx, 0Dh
0x18001d2fc  jnb     short loc_18001D328
0x18001d2fe  mov     eax, 0DFFFh
0x18001d303  lea     rcx, [rsi+8]; struct tagSAFEARRAY **
0x18001d307  and     dx, ax; unsigned __int16
0x18001d30a  mov     r8, r14; struct ISequentialStream *
0x18001d30d  call    ?ReadSafeArrayFromStream@@YAJPEAPEAUtagSAFEARRAY@@GPEAUISequentialStream@@@Z; ReadSafeArrayFromStream(tagSAFEARRAY * *,ushort,ISequentialStream *)
0x18001d312  mov     ebx, eax
0x18001d314  test    eax, eax
0x18001d316  js      loc_18001D28B
0x18001d31c  movzx   eax, [rbp+arg_0]
0x18001d320  mov     [rsi], ax
0x18001d323  jmp     loc_18001D28B
0x18001d328  cmp     dx, r15w
0x18001d32c  jz      loc_18001D28B
0x18001d332  mov     edi, 8
0x18001d337  mov     qword ptr [rbp+pvarg+8], 0
0x18001d33f  mov     rdx, r14
0x18001d342  mov     word ptr [rbp+pvarg], di
0x18001d346  lea     rcx, [rbp+pvarg+8]
0x18001d34a  call    ReadBSTRFromStream
0x18001d34f  mov     ebx, eax
0x18001d351  test    eax, eax
0x18001d353  js      loc_18001D28B
0x18001d359  movzx   r9d, [rbp+arg_0]; vt
0x18001d35e  lea     rdx, [rbp+pvarg]; pvarSrc
0x18001d362  mov     r8d, r15d; wFlags
0x18001d365  mov     rcx, rsi; pvargDest
0x18001d368  call    cs:__imp_VariantChangeType
0x18001d36f  nop     dword ptr [rax+rax+00h]
0x18001d374  mov     ebx, eax
0x18001d376  jmp     loc_18001D28B
0x18001d37b  mov     edi, 4
0x18001d380  jmp     short loc_18001D385
0x18001d382  mov     edi, r15d
0x18001d385  mov     rax, [r14]
0x18001d388  lea     rdx, [rsi+8]
0x18001d38c  lea     r9, [rbp+arg_10]
0x18001d390  mov     r8d, edi
0x18001d393  mov     rcx, r14
0x18001d396  mov     rax, [rax+18h]
0x18001d39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d39f  mov     ebx, eax
0x18001d3a1  test    eax, eax
0x18001d3a3  js      loc_18001D28B
0x18001d3a9  cmp     edi, [rbp+arg_10]
0x18001d3ac  jz      loc_18001D31C
0x18001d3b2  jmp     loc_18001D241
```
