# CSimpleDataTableCache::ShrinkWriteCache(void)

- ea: `0x1800025f0`
- end: `0x18000273d`
- name: `?ShrinkWriteCache@CSimpleDataTableCache@@IEAAJXZ`
- size: `333`
- prototype: `__int64 __fastcall(CSimpleDataTableCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002590`

## callees

- `0x1800025f0`
- `0x18005550e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800026ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000270d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800026ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000270d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800026c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800026c8`

## pseudocode

```c
__int64 __fastcall CSimpleDataTableCache::ShrinkWriteCache(CSimpleDataTableCache *this)
{
  int v1; // edx
  int v3; // ebp
  int v4; // r14d
  int v5; // esi
  unsigned int v6; // edi
  int v7; // ecx
  void *v8; // r8
  SIZE_T v9; // rcx
  void *v10; // rax
  void *v11; // r15
  SIZE_T v12; // rax
  void *v13; // r8
  size_t v14; // rdi
  void *v15; // rax
  void *v16; // rsi
  LPVOID v18; // rax
  LPVOID v19; // rax

  v1 = *((_DWORD *)this + 10);
  v3 = *((_DWORD *)this + 3);
  v4 = *((_DWORD *)this + 4);
  v5 = *((_DWORD *)this + 2);
  v6 = *((_DWORD *)this + 20);
  v7 = v5 + v4 + v3;
  if ( (v1 & 2) == 0 )
    ++v7;
  if ( v6 < *((_DWORD *)this + 21) )
  {
    v8 = (void *)*((_QWORD *)this + 11);
    if ( *((void **)this + 7) == v8 )
      *((_QWORD *)this + 7) = 0;
    v9 = 4 * v6 * v7;
    if ( (v1 & 0x20000) != 0 && (*(_DWORD *)this & 0x40000) == 0 )
    {
      v10 = CoTaskMemAlloc(v9);
      v11 = v10;
      if ( !v10 )
        return 2147942414LL;
      memcpy_0(v10, *((const void **)this + 11), 4 * v6 * (v5 + v4 + v3 + 1));
      *((_QWORD *)this + 11) = v11;
      *((_DWORD *)this + 10) &= ~0x20000u;
    }
    else
    {
      v19 = CoTaskMemRealloc(v8, v9);
      if ( !v19 )
        return 2147942414LL;
      *((_QWORD *)this + 11) = v19;
    }
    *((_DWORD *)this + 21) = *((_DWORD *)this + 20);
  }
  v12 = *((unsigned int *)this + 24);
  if ( (unsigned int)v12 < *((_DWORD *)this + 25) )
  {
    v13 = (void *)*((_QWORD *)this + 13);
    if ( *((void **)this + 9) == v13 )
      *((_QWORD *)this + 9) = 0;
    v14 = v12;
    if ( (*(_DWORD *)this & 0x40000) == 0 && (*((_DWORD *)this + 10) & 0x200000) != 0 )
    {
      v15 = CoTaskMemAlloc(v12);
      v16 = v15;
      if ( !v15 )
        return 2147942414LL;
      memcpy_0(v15, *((const void **)this + 13), v14);
      *((_QWORD *)this + 13) = v16;
      *((_DWORD *)this + 10) &= ~0x200000u;
    }
    else
    {
      v18 = CoTaskMemRealloc(v13, v12);
      if ( !v18 )
        return 2147942414LL;
      *((_QWORD *)this + 13) = v18;
    }
    *((_DWORD *)this + 25) = *((_DWORD *)this + 24);
  }
  return 0;
}

```

## disassembly

```asm
0x1800025f0  push    rbx
0x1800025f2  push    rbp
0x1800025f3  push    rsi
0x1800025f4  push    rdi
0x1800025f5  push    r14
0x1800025f7  push    r15
0x1800025f9  sub     rsp, 28h
0x1800025fd  mov     edx, [rcx+28h]
0x180002600  mov     rbx, rcx
0x180002603  mov     ebp, [rcx+0Ch]
0x180002606  mov     r14d, [rcx+10h]
0x18000260a  mov     esi, [rcx+8]
0x18000260d  mov     edi, [rbx+50h]
0x180002610  lea     ecx, [r14+rbp]
0x180002614  add     ecx, esi
0x180002616  test    dl, 2
0x180002619  lea     eax, [rcx+1]
0x18000261c  cmovz   ecx, eax
0x18000261f  cmp     edi, [rbx+54h]
0x180002622  jnb     short loc_180002691
0x180002624  mov     r8, [rbx+58h]
0x180002628  cmp     [rbx+38h], r8
0x18000262c  jnz     short loc_180002636
0x18000262e  mov     qword ptr [rbx+38h], 0
0x180002636  imul    ecx, edi
0x180002639  shl     ecx, 2; cb
0x18000263c  bt      edx, 11h
0x180002640  setb    dl
0x180002643  test    dword ptr [rbx], 40000h
0x180002649  setz    al
0x18000264c  test    al, dl
0x18000264e  jz      loc_180002707
0x180002654  call    cs:__imp_CoTaskMemAlloc
0x18000265a  mov     r15, rax
0x18000265d  test    rax, rax
0x180002660  jz      short loc_1800026D6
0x180002662  mov     rdx, [rbx+58h]; Src
0x180002666  lea     r8d, [rbp+1]
0x18000266a  add     r8d, r14d
0x18000266d  mov     rcx, rax; void *
0x180002670  add     r8d, esi
0x180002673  imul    r8d, edi
0x180002677  shl     r8d, 2; Size
0x18000267b  call    memcpy_0
0x180002680  mov     [rbx+58h], r15
0x180002684  and     dword ptr [rbx+28h], 0FFFDFFFFh
0x18000268b  mov     eax, [rbx+50h]
0x18000268e  mov     [rbx+54h], eax
0x180002691  mov     eax, [rbx+60h]
0x180002694  cmp     eax, [rbx+64h]
0x180002697  jnb     short loc_180002703
0x180002699  mov     r8, [rbx+68h]
0x18000269d  cmp     [rbx+48h], r8
0x1800026a1  jnz     short loc_1800026AB
0x1800026a3  mov     qword ptr [rbx+48h], 0
0x1800026ab  test    dword ptr [rbx], 40000h
0x1800026b1  mov     rdi, rax
0x1800026b4  setz    cl
0x1800026b7  test    dword ptr [rbx+28h], 200000h
0x1800026be  setnz   al
0x1800026c1  test    al, cl
0x1800026c3  jz      short loc_1800026E8
0x1800026c5  mov     rcx, rdi; cb
0x1800026c8  call    cs:__imp_CoTaskMemAlloc
0x1800026ce  mov     rsi, rax
0x1800026d1  test    rax, rax
0x1800026d4  jnz     short loc_180002721
0x1800026d6  mov     eax, 8007000Eh
0x1800026db  add     rsp, 28h
0x1800026df  pop     r15
0x1800026e1  pop     r14
0x1800026e3  pop     rdi
0x1800026e4  pop     rsi
0x1800026e5  pop     rbp
0x1800026e6  pop     rbx
0x1800026e7  retn
0x1800026e8  mov     rdx, rdi; cb
0x1800026eb  mov     rcx, r8; pv
0x1800026ee  call    cs:__imp_CoTaskMemRealloc
0x1800026f4  test    rax, rax
0x1800026f7  jz      short loc_1800026D6
0x1800026f9  mov     [rbx+68h], rax
0x1800026fd  mov     eax, [rbx+60h]
0x180002700  mov     [rbx+64h], eax
0x180002703  xor     eax, eax
0x180002705  jmp     short loc_1800026DB
0x180002707  mov     rdx, rcx; cb
0x18000270a  mov     rcx, r8; pv
0x18000270d  call    cs:__imp_CoTaskMemRealloc
0x180002713  test    rax, rax
0x180002716  jz      short loc_1800026D6
0x180002718  mov     [rbx+58h], rax
0x18000271c  jmp     loc_18000268B
0x180002721  mov     rdx, [rbx+68h]; Src
0x180002725  mov     r8, rdi; Size
0x180002728  mov     rcx, rsi; void *
0x18000272b  call    memcpy_0
0x180002730  mov     [rbx+68h], rsi
0x180002734  and     dword ptr [rbx+28h], 0FFDFFFFFh
0x18000273b  jmp     short loc_1800026FD
```
