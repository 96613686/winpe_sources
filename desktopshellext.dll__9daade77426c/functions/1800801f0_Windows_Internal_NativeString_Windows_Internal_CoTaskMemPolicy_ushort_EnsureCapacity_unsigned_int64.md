# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x1800801f0`
- end: `0x180080312`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180081444`

## callees

- `0x1800801c0`
- `0x1800801f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800802e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800802e4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rbp
  int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rcx
  _WORD *v7; // rax
  __int64 v8; // r9
  SIZE_T v9; // rsi
  LPVOID v10; // rax
  SIZE_T cb; // [rsp+48h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = -1;
  if ( v5 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v6;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v6) );
      }
      else
      {
        v6 = 0;
      }
      *(_QWORD *)(a1 + 8) = v6;
    }
    else
    {
      v6 = *(_QWORD *)(a1 + 8);
    }
    v5 = (v6 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v5;
  }
  if ( !v5 )
  {
    cb = 0;
    v4 = ULongLongMult(a2 + 1, a2, &cb);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v7 = CoTaskMemAlloc(cb);
    if ( v7 )
    {
      *(_QWORD *)(a1 + 16) = v2;
      *(_QWORD *)a1 = v7;
      *v7 = 0;
      return (unsigned int)v4;
    }
    return (unsigned int)-2147024882;
  }
  v4 = 0;
  if ( v2 > v5 )
  {
    cb = 0;
    v4 = ULongLongMult(v5, a2, &cb);
    if ( v4 >= 0 )
    {
      v9 = cb;
      if ( cb - v8 > 0x800 )
        v9 = v8 + 2048;
      if ( v2 > v9 )
        v9 = v2;
      v10 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v9);
      if ( v10 )
      {
        *(_QWORD *)(a1 + 16) = v9;
        *(_QWORD *)a1 = v10;
        return (unsigned int)v4;
      }
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800801f0  mov     [rsp+arg_0], rbx
0x1800801f5  mov     [rsp+arg_10], rbp
0x1800801fa  push    rsi
0x1800801fb  push    rdi
0x1800801fc  push    r14
0x1800801fe  sub     rsp, 20h
0x180080202  lea     rbp, [rdx+1]
0x180080206  mov     rdi, rcx
0x180080209  cmp     rbp, rdx
0x18008020c  jnb     short loc_180080218
0x18008020e  mov     ebx, 80070216h
0x180080213  jmp     loc_1800802FD
0x180080218  mov     r9, [rcx+10h]
0x18008021c  xor     r14d, r14d
0x18008021f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180080223  cmp     r9, rcx
0x180080226  jnz     short loc_180080262
0x180080228  cmp     [rdi+8], rcx
0x18008022c  jnz     short loc_18008024B
0x18008022e  mov     rax, [rdi]
0x180080231  test    rax, rax
0x180080234  jz      short loc_180080242
0x180080236  inc     rcx
0x180080239  cmp     [rax+rcx*2], r14w
0x18008023e  jnz     short loc_180080236
0x180080240  jmp     short loc_180080245
0x180080242  mov     rcx, r14
0x180080245  mov     [rdi+8], rcx
0x180080249  jmp     short loc_18008024F
0x18008024b  mov     rcx, [rdi+8]
0x18008024f  mov     rax, [rdi]
0x180080252  inc     rcx
0x180080255  neg     rax
0x180080258  sbb     r9, r9
0x18008025b  and     r9, rcx
0x18008025e  mov     [rdi+10h], r9
0x180080262  test    r9, r9
0x180080265  jnz     short loc_18008029C
0x180080267  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18008026c  mov     [rsp+38h+cb], r14
0x180080271  mov     rcx, rbp; unsigned __int64
0x180080274  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180080279  mov     ebx, eax
0x18008027b  test    eax, eax
0x18008027d  js      short loc_1800802FD
0x18008027f  mov     rcx, [rsp+38h+cb]; cb
0x180080284  call    cs:__imp_CoTaskMemAlloc
0x18008028a  test    rax, rax
0x18008028d  jz      short loc_1800802F8
0x18008028f  mov     [rdi+10h], rbp
0x180080293  mov     [rdi], rax
0x180080296  mov     [rax], r14w
0x18008029a  jmp     short loc_1800802FD
0x18008029c  mov     ebx, r14d
0x18008029f  cmp     rbp, r9
0x1800802a2  jbe     short loc_1800802FD
0x1800802a4  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1800802a9  mov     [rsp+38h+cb], r14
0x1800802ae  mov     rcx, r9; unsigned __int64
0x1800802b1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800802b6  mov     ebx, eax
0x1800802b8  test    eax, eax
0x1800802ba  js      short loc_1800802FD
0x1800802bc  mov     rsi, [rsp+38h+cb]
0x1800802c1  mov     rax, rsi
0x1800802c4  sub     rax, r9
0x1800802c7  cmp     rax, 800h
0x1800802cd  jbe     short loc_1800802D6
0x1800802cf  lea     rsi, [r9+800h]
0x1800802d6  mov     rcx, [rdi]; pv
0x1800802d9  cmp     rbp, rsi
0x1800802dc  cmova   rsi, rbp
0x1800802e0  lea     rdx, [rsi+rsi]; cb
0x1800802e4  call    cs:__imp_CoTaskMemRealloc
0x1800802ea  test    rax, rax
0x1800802ed  jz      short loc_1800802F8
0x1800802ef  mov     [rdi+10h], rsi
0x1800802f3  mov     [rdi], rax
0x1800802f6  jmp     short loc_1800802FD
0x1800802f8  mov     ebx, 8007000Eh
0x1800802fd  mov     rbp, [rsp+38h+arg_10]
0x180080302  mov     eax, ebx
0x180080304  mov     rbx, [rsp+38h+arg_0]
0x180080309  add     rsp, 20h
0x18008030d  pop     r14
0x18008030f  pop     rdi
0x180080310  pop     rsi
0x180080311  retn
```
