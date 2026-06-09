# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x1800066d4`
- end: `0x1800067d3`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800059e4`

## callees

- `0x1800066d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000674f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000674f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000679f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000679f`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // r8
  __int64 v5; // rcx
  _WORD *v6; // rax
  unsigned int v7; // ecx
  unsigned __int64 v8; // rcx
  LPVOID v9; // rax

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = -1;
  if ( v4 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v5;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v5) );
      }
      else
      {
        v5 = 0;
      }
      *(_QWORD *)(a1 + 8) = v5;
    }
    else
    {
      v5 = *(_QWORD *)(a1 + 8);
    }
    v4 = (v5 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v4;
  }
  if ( !v4 )
  {
    if ( is_mul_ok(v2, 2u) )
    {
      v6 = CoTaskMemAlloc(2 * v2);
      if ( v6 )
      {
        *(_QWORD *)(a1 + 16) = v2;
        *(_QWORD *)a1 = v6;
        *v6 = 0;
        return 0;
      }
      return (unsigned int)-2147024882;
    }
    return (unsigned int)-2147024362;
  }
  v7 = 0;
  if ( v2 > v4 )
  {
    if ( is_mul_ok(v4, 2u) )
    {
      v8 = v4 + 2048;
      if ( v4 <= 0x800 )
        v8 = 2 * v4;
      if ( v2 <= v8 )
        v2 = v8;
      v9 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v2);
      if ( v9 )
      {
        *(_QWORD *)(a1 + 16) = v2;
        *(_QWORD *)a1 = v9;
        return 0;
      }
      return (unsigned int)-2147024882;
    }
    return (unsigned int)-2147024362;
  }
  return v7;
}

```

## disassembly

```asm
0x1800066d4  mov     [rsp+arg_0], rbx
0x1800066d9  mov     [rsp+arg_10], rsi
0x1800066de  push    rdi
0x1800066df  sub     rsp, 20h
0x1800066e3  lea     rdi, [rdx+1]
0x1800066e7  mov     rbx, rcx
0x1800066ea  cmp     rdi, rdx
0x1800066ed  jb      loc_1800067BC
0x1800066f3  mov     r8, [rcx+10h]
0x1800066f7  xor     esi, esi
0x1800066f9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800066fd  cmp     r8, rcx
0x180006700  jnz     short loc_18000673B
0x180006702  cmp     [rbx+8], rcx
0x180006706  jnz     short loc_180006724
0x180006708  mov     rax, [rbx]
0x18000670b  test    rax, rax
0x18000670e  jz      short loc_18000671B
0x180006710  inc     rcx
0x180006713  cmp     [rax+rcx*2], si
0x180006717  jnz     short loc_180006710
0x180006719  jmp     short loc_18000671E
0x18000671b  mov     rcx, rsi
0x18000671e  mov     [rbx+8], rcx
0x180006722  jmp     short loc_180006728
0x180006724  mov     rcx, [rbx+8]
0x180006728  mov     rax, [rbx]
0x18000672b  inc     rcx
0x18000672e  neg     rax
0x180006731  sbb     r8, r8
0x180006734  and     r8, rcx
0x180006737  mov     [rbx+10h], r8
0x18000673b  test    r8, r8
0x18000673e  jnz     short loc_180006766
0x180006740  lea     eax, [r8+2]
0x180006744  mul     rdi
0x180006747  test    rdx, rdx
0x18000674a  jnz     short loc_1800067BC
0x18000674c  mov     rcx, rax; cb
0x18000674f  call    cs:__imp_CoTaskMemAlloc
0x180006755  test    rax, rax
0x180006758  jz      short loc_1800067B5
0x18000675a  mov     [rbx+10h], rdi
0x18000675e  mov     [rbx], rax
0x180006761  mov     [rax], si
0x180006764  jmp     short loc_1800067B1
0x180006766  mov     ecx, esi
0x180006768  cmp     rdi, r8
0x18000676b  jbe     short loc_1800067C1
0x18000676d  mov     eax, 2
0x180006772  mul     r8
0x180006775  mov     r9, rax
0x180006778  test    rdx, rdx
0x18000677b  jnz     short loc_1800067BC
0x18000677d  sub     rax, r8
0x180006780  lea     rcx, [r8+800h]
0x180006787  cmp     rax, 800h
0x18000678d  cmovbe  rcx, r9
0x180006791  cmp     rdi, rcx
0x180006794  cmovbe  rdi, rcx
0x180006798  mov     rcx, [rbx]; pv
0x18000679b  lea     rdx, [rdi+rdi]; cb
0x18000679f  call    cs:__imp_CoTaskMemRealloc
0x1800067a5  test    rax, rax
0x1800067a8  jz      short loc_1800067B5
0x1800067aa  mov     [rbx+10h], rdi
0x1800067ae  mov     [rbx], rax
0x1800067b1  mov     ecx, esi
0x1800067b3  jmp     short loc_1800067C1
0x1800067b5  mov     ecx, 8007000Eh
0x1800067ba  jmp     short loc_1800067C1
0x1800067bc  mov     ecx, 80070216h
0x1800067c1  mov     rbx, [rsp+28h+arg_0]
0x1800067c6  mov     eax, ecx
0x1800067c8  mov     rsi, [rsp+28h+arg_10]
0x1800067cd  add     rsp, 20h
0x1800067d1  pop     rdi
0x1800067d2  retn
```
