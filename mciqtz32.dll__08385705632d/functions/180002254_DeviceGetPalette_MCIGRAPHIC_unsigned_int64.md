# DeviceGetPalette(_MCIGRAPHIC *,unsigned __int64 *)

- ea: `0x180002254`
- end: `0x180002383`
- name: `?DeviceGetPalette@@YAKPEAU_MCIGRAPHIC@@PEA_K@Z`
- size: `303`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003604`
- `0x180005934`

## callees

- `0x180001008`
- `0x180001014`
- `0x180001e7c`
- `0x180002254`
- `0x180007010`

## import_xrefs

- `GDI32!CreatePalette` at `0x18000233b`
- `GDI32!CreatePalette` at `0x18000233b`

## pseudocode

```c
unsigned int __fastcall DeviceGetPalette(struct _MCIGRAPHIC *a1, unsigned __int64 *a2)
{
  int v4; // ebx
  __int64 v5; // rcx
  LOGPALETTE *v7; // rax
  LOGPALETTE *v8; // rdi
  HPALETTE Palette; // rax
  int v10; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_QWORD *)a1 + 40) )
  {
    v4 = 0;
  }
  else
  {
    v5 = *((_QWORD *)a1 + 21);
    v4 = -2147467259;
    if ( v5 )
    {
      v10 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, int *, _QWORD))(*(_QWORD *)v5 + 280LL))(
             v5,
             0,
             0,
             &v10,
             0);
      if ( !v4 )
      {
        if ( v10 > 256 )
          return -2147418113;
        v7 = (LOGPALETTE *)operator new[](4LL * v10 + 8);
        v8 = v7;
        if ( v7 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *, LOGPALETTE *))(**((_QWORD **)a1 + 21) + 280LL))(
                 *((_QWORD *)a1 + 21),
                 0,
                 (unsigned int)v10,
                 &v10,
                 v7 + 1);
          if ( !v4 )
          {
            v8->palNumEntries = v10;
            v8->palVersion = 768;
            Palette = CreatePalette(v8);
            *((_QWORD *)a1 + 40) = Palette;
            if ( !Palette )
              v4 = -2147467259;
          }
          operator delete[](v8);
        }
        else
        {
          v4 = -2147024882;
        }
      }
    }
  }
  *a2 = *((_QWORD *)a1 + 40);
  return CheckResult(v4);
}

```

## disassembly

```asm
0x180002254  mov     [rsp+arg_8], rbx
0x180002259  mov     [rsp+arg_10], rsi
0x18000225e  push    rdi
0x18000225f  push    r14
0x180002261  push    r15
0x180002263  sub     rsp, 30h
0x180002267  cmp     qword ptr [rcx+140h], 0
0x18000226f  mov     r14, rdx
0x180002272  mov     rsi, rcx
0x180002275  jz      short loc_18000227E
0x180002277  xor     ebx, ebx
0x180002279  jmp     loc_18000235E
0x18000227e  mov     rcx, [rcx+0A8h]
0x180002285  mov     r15d, 80004005h
0x18000228b  mov     ebx, r15d
0x18000228e  test    rcx, rcx
0x180002291  jz      loc_18000235E
0x180002297  mov     [rsp+48h+arg_0], 0
0x18000229f  lea     r9, [rsp+48h+arg_0]
0x1800022a4  mov     rax, [rcx]
0x1800022a7  xor     r8d, r8d
0x1800022aa  xor     edx, edx
0x1800022ac  mov     [rsp+48h+var_28], 0
0x1800022b5  mov     rax, [rax+118h]
0x1800022bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c1  mov     ebx, eax
0x1800022c3  test    eax, eax
0x1800022c5  jnz     loc_18000235E
0x1800022cb  cmp     [rsp+48h+arg_0], 100h
0x1800022d3  jle     short loc_1800022DF
0x1800022d5  mov     eax, 8000FFFFh
0x1800022da  jmp     loc_18000236F
0x1800022df  movsxd  rcx, [rsp+48h+arg_0]
0x1800022e4  lea     rcx, ds:8[rcx*4]; unsigned __int64
0x1800022ec  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800022f1  mov     rdi, rax
0x1800022f4  test    rax, rax
0x1800022f7  jz      short loc_180002359
0x1800022f9  mov     rcx, [rsi+0A8h]
0x180002300  lea     r8, [rax+8]
0x180002304  mov     [rsp+48h+var_28], r8
0x180002309  lea     r9, [rsp+48h+arg_0]
0x18000230e  mov     r8d, [rsp+48h+arg_0]
0x180002313  mov     rdx, [rcx]
0x180002316  mov     rax, [rdx+118h]
0x18000231d  xor     edx, edx
0x18000231f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002324  mov     ebx, eax
0x180002326  test    eax, eax
0x180002328  jnz     short loc_18000234F
0x18000232a  movzx   eax, word ptr [rsp+48h+arg_0]
0x18000232f  mov     rcx, rdi; plpal
0x180002332  mov     [rdi+2], ax
0x180002336  mov     word ptr [rdi], 300h
0x18000233b  call    cs:__imp_CreatePalette
0x180002341  test    rax, rax
0x180002344  mov     [rsi+140h], rax
0x18000234b  cmovz   ebx, r15d
0x18000234f  mov     rcx, rdi; void *
0x180002352  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180002357  jmp     short loc_18000235E
0x180002359  mov     ebx, 8007000Eh
0x18000235e  mov     rax, [rsi+140h]
0x180002365  mov     ecx, ebx; int
0x180002367  mov     [r14], rax
0x18000236a  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x18000236f  mov     rbx, [rsp+48h+arg_8]
0x180002374  mov     rsi, [rsp+48h+arg_10]
0x180002379  add     rsp, 30h
0x18000237d  pop     r15
0x18000237f  pop     r14
0x180002381  pop     rdi
0x180002382  retn
```
