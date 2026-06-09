# CMemoryTable::ResizeCache(ulong,ulong)

- ea: `0x1800101f8`
- end: `0x18001032b`
- name: `?ResizeCache@CMemoryTable@@AEAAJKK@Z`
- size: `307`
- prototype: `int(CMemoryTable *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e378`
- `0x18000e5c4`
- `0x18000e67c`

## callees

- `0x1800101f8`
- `0x18002e0b2`
- `0x18002e0be`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x1800102b0`
- `ole32!CoTaskMemRealloc` at `0x1800102d5`
- `ole32!CoTaskMemRealloc` at `0x1800102b0`
- `ole32!CoTaskMemRealloc` at `0x1800102d5`

## pseudocode

```c
__int64 __fastcall CMemoryTable::ResizeCache(CMemoryTable *this, int a2, unsigned int a3)
{
  unsigned int v3; // edi
  _QWORD *v7; // r12
  unsigned int v8; // r15d
  __int64 v9; // r14
  unsigned int v10; // esi
  unsigned int v11; // eax
  const void *v12; // r13
  void *v13; // rax
  LPVOID v14; // rax
  char *v15; // rcx

  v3 = a3;
  if ( a2 == 0x20000 )
  {
    v10 = *((_DWORD *)this + 41);
    if ( a3 <= 0x4000000 )
    {
      if ( v10 || a3 >= *((_DWORD *)this + 22) )
      {
        v11 = *((_DWORD *)this + 41);
        if ( v10 < a3 )
          v11 = a3;
        v3 = v10 + 0x4000000;
        if ( 2 * v11 - v10 <= 0x4000000 )
          v3 = 2 * v11;
      }
      else
      {
        v3 = *((_DWORD *)this + 22);
      }
    }
    else
    {
      v3 = v10 + a3;
    }
    v8 = *((_DWORD *)this + 35);
    v7 = (_QWORD *)((char *)this + 144);
    v9 = 152;
  }
  else
  {
    if ( a2 != 0x40000 )
      return 2147549183LL;
    v7 = 0;
    v8 = 0;
    v9 = 176;
    v10 = 12 * *((_DWORD *)this + 42);
  }
  if ( (*((_DWORD *)this + 8) & 0x1000000) != 0 || (a2 & *((_DWORD *)this + 23)) == 0 )
  {
    v14 = CoTaskMemRealloc(*(LPVOID *)((char *)this + v9), v3);
    if ( v14 )
    {
      *(_QWORD *)((char *)this + v9) = v14;
      goto LABEL_22;
    }
    return 2147942414LL;
  }
  *((_DWORD *)this + 23) &= ~a2;
  v12 = *(const void **)((char *)this + v9);
  v13 = CoTaskMemRealloc(0, v3);
  if ( !v13 )
    return 2147942414LL;
  *(_QWORD *)((char *)this + v9) = v13;
  memcpy_0(v13, v12, v10);
LABEL_22:
  if ( (a2 & 0x20000) != 0 )
  {
    v15 = (char *)(*(_QWORD *)((char *)this + v9) + v3 - v8);
    *v7 = v15;
    memmove_0(v15, &v15[-(v3 - v10)], v8);
    *((_DWORD *)this + 41) = v3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800101f8  push    rbx
0x1800101fa  push    rbp
0x1800101fb  push    rsi
0x1800101fc  push    rdi
0x1800101fd  push    r12
0x1800101ff  push    r13
0x180010201  push    r14
0x180010203  push    r15
0x180010205  sub     rsp, 28h
0x180010209  mov     edi, r8d
0x18001020c  mov     ebp, edx
0x18001020e  mov     rbx, rcx
0x180010211  cmp     edx, 20000h
0x180010217  jz      short loc_180010245
0x180010219  cmp     edx, 40000h
0x18001021f  jz      short loc_18001022B
0x180010221  mov     eax, 8000FFFFh
0x180010226  jmp     loc_18001031A
0x18001022b  mov     eax, [rcx+0A8h]
0x180010231  xor     r12d, r12d
0x180010234  xor     r15d, r15d
0x180010237  mov     r14d, 0B0h
0x18001023d  lea     esi, [rax+rax*2]
0x180010240  shl     esi, 2
0x180010243  jmp     short loc_180010293
0x180010245  mov     esi, [rcx+0A4h]
0x18001024b  mov     edx, 4000000h
0x180010250  cmp     edi, edx
0x180010252  jbe     short loc_180010258
0x180010254  add     edi, esi
0x180010256  jmp     short loc_18001027F
0x180010258  test    esi, esi
0x18001025a  jnz     short loc_180010266
0x18001025c  cmp     edi, [rcx+58h]
0x18001025f  jnb     short loc_180010266
0x180010261  mov     edi, [rcx+58h]
0x180010264  jmp     short loc_18001027F
0x180010266  cmp     esi, edi
0x180010268  mov     eax, esi
0x18001026a  cmovb   eax, edi
0x18001026d  lea     edi, [rsi+4000000h]
0x180010273  lea     ecx, [rax+rax]
0x180010276  mov     eax, ecx
0x180010278  sub     eax, esi
0x18001027a  cmp     eax, edx
0x18001027c  cmovbe  edi, ecx
0x18001027f  mov     r15d, [rbx+8Ch]
0x180010286  lea     r12, [rbx+90h]
0x18001028d  mov     r14d, 98h
0x180010293  test    dword ptr [rbx+20h], 1000000h
0x18001029a  jnz     short loc_1800102CF
0x18001029c  test    [rbx+5Ch], ebp
0x18001029f  jz      short loc_1800102CF
0x1800102a1  mov     eax, ebp
0x1800102a3  mov     edx, edi; cb
0x1800102a5  not     eax
0x1800102a7  xor     ecx, ecx; pv
0x1800102a9  and     [rbx+5Ch], eax
0x1800102ac  mov     r13, [r14+rbx]
0x1800102b0  call    cs:__imp_CoTaskMemRealloc
0x1800102b6  test    rax, rax
0x1800102b9  jz      short loc_1800102E0
0x1800102bb  mov     r8d, esi; Size
0x1800102be  mov     rdx, r13; Src
0x1800102c1  mov     rcx, rax; void *
0x1800102c4  mov     [r14+rbx], rax
0x1800102c8  call    memcpy_0
0x1800102cd  jmp     short loc_1800102EB
0x1800102cf  mov     rcx, [r14+rbx]; pv
0x1800102d3  mov     edx, edi; cb
0x1800102d5  call    cs:__imp_CoTaskMemRealloc
0x1800102db  test    rax, rax
0x1800102de  jnz     short loc_1800102E7
0x1800102e0  mov     eax, 8007000Eh
0x1800102e5  jmp     short loc_18001031A
0x1800102e7  mov     [r14+rbx], rax
0x1800102eb  bt      ebp, 11h
0x1800102ef  jnb     short loc_180010318
0x1800102f1  mov     r9d, edi
0x1800102f4  mov     r8d, r15d; Size
0x1800102f7  mov     ecx, edi
0x1800102f9  sub     r9d, esi
0x1800102fc  sub     ecx, r15d
0x1800102ff  add     rcx, [r14+rbx]; void *
0x180010303  mov     rdx, rcx
0x180010306  mov     [r12], rcx
0x18001030a  sub     rdx, r9; Src
0x18001030d  call    memmove_0
0x180010312  mov     [rbx+0A4h], edi
0x180010318  xor     eax, eax
0x18001031a  add     rsp, 28h
0x18001031e  pop     r15
0x180010320  pop     r14
0x180010322  pop     r13
0x180010324  pop     r12
0x180010326  pop     rdi
0x180010327  pop     rsi
0x180010328  pop     rbp
0x180010329  pop     rbx
0x18001032a  retn
```
