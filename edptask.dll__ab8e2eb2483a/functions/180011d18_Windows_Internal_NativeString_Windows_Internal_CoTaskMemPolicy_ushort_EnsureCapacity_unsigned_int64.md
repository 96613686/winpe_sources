# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180011d18`
- end: `0x180011e17`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011e48`

## callees

- `0x180011d18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180011de3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180011de3`

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
0x180011d18  mov     [rsp+arg_0], rbx
0x180011d1d  mov     [rsp+arg_10], rsi
0x180011d22  push    rdi
0x180011d23  sub     rsp, 20h
0x180011d27  lea     rdi, [rdx+1]
0x180011d2b  mov     rbx, rcx
0x180011d2e  cmp     rdi, rdx
0x180011d31  jb      loc_180011E00
0x180011d37  mov     r8, [rcx+10h]
0x180011d3b  xor     esi, esi
0x180011d3d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180011d41  cmp     r8, rcx
0x180011d44  jnz     short loc_180011D7F
0x180011d46  cmp     [rbx+8], rcx
0x180011d4a  jnz     short loc_180011D68
0x180011d4c  mov     rax, [rbx]
0x180011d4f  test    rax, rax
0x180011d52  jz      short loc_180011D5F
0x180011d54  inc     rcx
0x180011d57  cmp     [rax+rcx*2], si
0x180011d5b  jnz     short loc_180011D54
0x180011d5d  jmp     short loc_180011D62
0x180011d5f  mov     rcx, rsi
0x180011d62  mov     [rbx+8], rcx
0x180011d66  jmp     short loc_180011D6C
0x180011d68  mov     rcx, [rbx+8]
0x180011d6c  mov     rax, [rbx]
0x180011d6f  inc     rcx
0x180011d72  neg     rax
0x180011d75  sbb     r8, r8
0x180011d78  and     r8, rcx
0x180011d7b  mov     [rbx+10h], r8
0x180011d7f  test    r8, r8
0x180011d82  jnz     short loc_180011DAA
0x180011d84  lea     eax, [r8+2]
0x180011d88  mul     rdi
0x180011d8b  test    rdx, rdx
0x180011d8e  jnz     short loc_180011E00
0x180011d90  mov     rcx, rax; cb
0x180011d93  call    cs:__imp_CoTaskMemAlloc
0x180011d99  test    rax, rax
0x180011d9c  jz      short loc_180011DF9
0x180011d9e  mov     [rbx+10h], rdi
0x180011da2  mov     [rbx], rax
0x180011da5  mov     [rax], si
0x180011da8  jmp     short loc_180011DF5
0x180011daa  mov     ecx, esi
0x180011dac  cmp     rdi, r8
0x180011daf  jbe     short loc_180011E05
0x180011db1  mov     eax, 2
0x180011db6  mul     r8
0x180011db9  mov     r9, rax
0x180011dbc  test    rdx, rdx
0x180011dbf  jnz     short loc_180011E00
0x180011dc1  sub     rax, r8
0x180011dc4  lea     rcx, [r8+800h]
0x180011dcb  cmp     rax, 800h
0x180011dd1  cmovbe  rcx, r9
0x180011dd5  cmp     rdi, rcx
0x180011dd8  cmovbe  rdi, rcx
0x180011ddc  mov     rcx, [rbx]; pv
0x180011ddf  lea     rdx, [rdi+rdi]; cb
0x180011de3  call    cs:__imp_CoTaskMemRealloc
0x180011de9  test    rax, rax
0x180011dec  jz      short loc_180011DF9
0x180011dee  mov     [rbx+10h], rdi
0x180011df2  mov     [rbx], rax
0x180011df5  mov     ecx, esi
0x180011df7  jmp     short loc_180011E05
0x180011df9  mov     ecx, 8007000Eh
0x180011dfe  jmp     short loc_180011E05
0x180011e00  mov     ecx, 80070216h
0x180011e05  mov     rbx, [rsp+28h+arg_0]
0x180011e0a  mov     eax, ecx
0x180011e0c  mov     rsi, [rsp+28h+arg_10]
0x180011e11  add     rsp, 20h
0x180011e15  pop     rdi
0x180011e16  retn
```
