# CMCreateMultiProfileTransformInternal

- ea: `0x1800067e4`
- end: `0x18000695c`
- name: `CMCreateMultiProfileTransformInternal`
- size: `376`
- prototype: `__int64 __fastcall(int, __int64, unsigned int, _DWORD *, int, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180006770`
- `0x18001d680`
- `0x18001d7a0`

## callees

- `0x1800042e0`
- `0x1800067e4`
- `0x180006964`
- `0x180018b28`
- `0x18001d15d`
- `0x18003d00e`

## pseudocode

```c
__int64 __fastcall CMCreateMultiProfileTransformInternal(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3,
        _DWORD *a4,
        int a5,
        int a6)
{
  size_t v7; // rbp
  _WORD *v11; // rbx
  unsigned int v12; // edi
  unsigned int v13; // edx
  __int64 v14; // rcx
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // ebp
  _DWORD *v19; // rax
  _DWORD *v20; // r14
  _DWORD *v21; // rdi
  __int64 i; // rcx
  __int16 v24; // [rsp+90h] [rbp+18h] BYREF

  v7 = (int)(8 * a3 + 16);
  v11 = malloc_0(v7);
  v12 = 8;
  v24 = v11 == 0 ? 8 : 0;
  if ( v11 )
  {
    memset_0(v11, 0, v7);
    *v11 = 0;
    v13 = 0;
    for ( v11[1] = a3; v13 < a3; *(_QWORD *)&v11[4 * v14 + 4] = *(_QWORD *)(a2 + 8 * v14) )
      v14 = v13++;
    if ( (unsigned __int16)a6 == 1 )
    {
      v15 = 1;
    }
    else if ( (unsigned __int16)a6 == 3 )
    {
      v15 = 2;
    }
    else
    {
      v15 = 0;
    }
    v16 = v15 | 0x80000;
    if ( (a6 & 0x10000) != 0 )
      v16 = v15;
    v17 = v16 | 0x100000;
    if ( (a6 & 0x20000) == 0 )
      v17 = v16;
    v18 = v17 | 0x40000;
    if ( (a6 & 0x40000) == 0 )
      v18 = v17;
    if ( a5 == 1 && a3 > 1 )
    {
      v19 = (_DWORD *)SmartNewPtrClear(4 * a3, &v24);
      v20 = v19;
      if ( !v24 )
      {
        *v19 = 0;
        v19[1] = *a4;
        if ( a3 > 2 )
        {
          v21 = v19 + 2;
          for ( i = a3 - 2; i; --i )
            *v21++ = 1;
        }
        v12 = CWConcatColorWorld4MS(a1, (__int64)v11, (__int64)v19, a3, v18);
        DisposeIfPtr(v20);
      }
    }
    else
    {
      v12 = CWConcatColorWorld4MS(a1, (__int64)v11, (__int64)a4, a5, v18);
    }
    DisposeIfPtr(v11);
  }
  return v12;
}

```

## disassembly

```asm
0x1800067e4  push    rbx
0x1800067e6  push    rbp
0x1800067e7  push    rsi
0x1800067e8  push    rdi
0x1800067e9  push    r12
0x1800067eb  push    r13
0x1800067ed  push    r14
0x1800067ef  push    r15
0x1800067f1  sub     rsp, 38h
0x1800067f5  lea     eax, ds:10h[r8*8]
0x1800067fd  mov     r12, rcx
0x180006800  movsxd  rbp, eax
0x180006803  mov     r15, r9
0x180006806  mov     rcx, rbp; Size
0x180006809  mov     esi, r8d
0x18000680c  mov     r14, rdx
0x18000680f  call    malloc_0
0x180006814  mov     rbx, rax
0x180006817  mov     edi, 8
0x18000681c  neg     rax
0x18000681f  sbb     ax, ax
0x180006822  xor     r13d, r13d
0x180006825  not     ax
0x180006828  and     ax, di
0x18000682b  mov     [rsp+78h+arg_10], ax
0x180006833  test    rbx, rbx
0x180006836  jz      loc_180006949
0x18000683c  mov     r8, rbp; Size
0x18000683f  xor     edx, edx; Val
0x180006841  mov     rcx, rbx; void *
0x180006844  call    memset_0
0x180006849  mov     [rbx], r13w
0x18000684d  mov     edx, r13d
0x180006850  mov     [rbx+2], si
0x180006854  test    esi, esi
0x180006856  jz      short loc_180006869
0x180006858  mov     ecx, edx
0x18000685a  inc     edx
0x18000685c  mov     rax, [r14+rcx*8]
0x180006860  mov     [rbx+rcx*8+8], rax
0x180006865  cmp     edx, esi
0x180006867  jb      short loc_180006858
0x180006869  mov     r8d, [rsp+78h+arg_28]
0x180006871  movzx   eax, r8w
0x180006875  sub     eax, 1
0x180006878  jz      short loc_18000688B
0x18000687a  cmp     eax, 2
0x18000687d  jz      short loc_180006884
0x18000687f  mov     edx, r13d
0x180006882  jmp     short loc_180006890
0x180006884  mov     edx, 2
0x180006889  jmp     short loc_180006890
0x18000688b  mov     edx, 1
0x180006890  mov     r9d, [rsp+78h+arg_20]
0x180006898  mov     ecx, edx
0x18000689a  bts     ecx, 13h
0x18000689e  mov     eax, 40000h
0x1800068a3  bt      r8d, 10h
0x1800068a8  cmovb   ecx, edx
0x1800068ab  mov     edx, ecx
0x1800068ad  bts     edx, 14h
0x1800068b1  bt      r8d, 11h
0x1800068b6  cmovnb  edx, ecx
0x1800068b9  mov     ebp, edx
0x1800068bb  or      ebp, eax
0x1800068bd  test    eax, r8d
0x1800068c0  cmovz   ebp, edx
0x1800068c3  cmp     r9d, 1
0x1800068c7  jnz     short loc_18000692D
0x1800068c9  cmp     esi, r9d
0x1800068cc  jbe     short loc_18000692D
0x1800068ce  lea     ecx, ds:0[rsi*4]
0x1800068d5  lea     rdx, [rsp+78h+arg_10]
0x1800068dd  call    SmartNewPtrClear
0x1800068e2  mov     r14, rax
0x1800068e5  cmp     [rsp+78h+arg_10], r13w
0x1800068ee  jnz     short loc_180006941
0x1800068f0  mov     [rax], r13d
0x1800068f3  mov     ecx, [r15]
0x1800068f6  mov     [rax+4], ecx
0x1800068f9  cmp     esi, 2
0x1800068fc  jbe     short loc_18000690C
0x1800068fe  lea     rdi, [rax+8]
0x180006902  mov     eax, 1
0x180006907  lea     ecx, [rsi-2]
0x18000690a  rep stosd
0x18000690c  mov     r9d, esi
0x18000690f  mov     [rsp+78h+var_58], ebp
0x180006913  mov     r8, r14
0x180006916  mov     rdx, rbx
0x180006919  mov     rcx, r12
0x18000691c  call    CWConcatColorWorld4MS
0x180006921  mov     rcx, r14
0x180006924  mov     edi, eax
0x180006926  call    DisposeIfPtr
0x18000692b  jmp     short loc_180006941
0x18000692d  mov     r8, r15
0x180006930  mov     [rsp+78h+var_58], ebp
0x180006934  mov     rdx, rbx
0x180006937  mov     rcx, r12
0x18000693a  call    CWConcatColorWorld4MS
0x18000693f  mov     edi, eax
0x180006941  mov     rcx, rbx
0x180006944  call    DisposeIfPtr
0x180006949  mov     eax, edi
0x18000694b  add     rsp, 38h
0x18000694f  pop     r15
0x180006951  pop     r14
0x180006953  pop     r13
0x180006955  pop     r12
0x180006957  pop     rdi
0x180006958  pop     rsi
0x180006959  pop     rbp
0x18000695a  pop     rbx
0x18000695b  retn
```
