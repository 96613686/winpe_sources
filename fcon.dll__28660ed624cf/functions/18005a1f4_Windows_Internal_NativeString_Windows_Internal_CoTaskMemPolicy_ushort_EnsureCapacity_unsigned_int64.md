# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18005a1f4`
- end: `0x18005a2e9`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180050908`
- `0x1800585d0`

## callees

- `0x18004aae8`
- `0x18005a1f4`
- `0x18005a2f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005a262`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005a262`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005a2c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005a2c5`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rbp
  int v4; // ebx
  unsigned __int64 v5; // r9
  _QWORD *v6; // rcx
  _WORD *v7; // rax
  __int64 v8; // r9
  SIZE_T v9; // rsi
  LPVOID v10; // rax
  SIZE_T cb; // [rsp+58h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount();
    if ( *v6 )
      v5 = v6[1] + 1LL;
    else
      v5 = 0;
    v6[2] = v5;
  }
  if ( !v5 )
  {
    cb = 0;
    v4 = ULongLongMult(v2, 2u, &cb);
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
    v4 = ULongLongMult(v5, 2u, &cb);
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
0x18005a1f4  push    rbx
0x18005a1f6  push    rbp
0x18005a1f7  push    rsi
0x18005a1f8  push    rdi
0x18005a1f9  sub     rsp, 28h
0x18005a1fd  lea     rbp, [rdx+1]
0x18005a201  mov     rdi, rcx
0x18005a204  cmp     rbp, rdx
0x18005a207  jnb     short loc_18005A213
0x18005a209  mov     ebx, 80070216h
0x18005a20e  jmp     loc_18005A2DE
0x18005a213  mov     r9, [rcx+10h]
0x18005a217  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18005a21b  jnz     short loc_18005A238
0x18005a21d  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18005a222  cmp     qword ptr [rcx], 0
0x18005a226  jz      short loc_18005A231
0x18005a228  mov     r9, [rcx+8]
0x18005a22c  inc     r9
0x18005a22f  jmp     short loc_18005A234
0x18005a231  xor     r9d, r9d
0x18005a234  mov     [rcx+10h], r9
0x18005a238  test    r9, r9
0x18005a23b  jnz     short loc_18005A27B
0x18005a23d  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18005a242  mov     [rsp+48h+cb], r9
0x18005a247  lea     edx, [r9+2]; unsigned __int64
0x18005a24b  mov     rcx, rbp; unsigned __int64
0x18005a24e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005a253  mov     ebx, eax
0x18005a255  test    eax, eax
0x18005a257  js      loc_18005A2DE
0x18005a25d  mov     rcx, [rsp+48h+cb]; cb
0x18005a262  call    cs:__imp_CoTaskMemAlloc
0x18005a268  test    rax, rax
0x18005a26b  jz      short loc_18005A2D9
0x18005a26d  xor     ecx, ecx
0x18005a26f  mov     [rdi+10h], rbp
0x18005a273  mov     [rdi], rax
0x18005a276  mov     [rax], cx
0x18005a279  jmp     short loc_18005A2DE
0x18005a27b  xor     ebx, ebx
0x18005a27d  cmp     rbp, r9
0x18005a280  jbe     short loc_18005A2DE
0x18005a282  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18005a287  mov     [rsp+48h+cb], rbx
0x18005a28c  lea     edx, [rbx+2]; unsigned __int64
0x18005a28f  mov     rcx, r9; unsigned __int64
0x18005a292  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005a297  mov     ebx, eax
0x18005a299  test    eax, eax
0x18005a29b  js      short loc_18005A2DE
0x18005a29d  mov     rsi, [rsp+48h+cb]
0x18005a2a2  mov     rax, rsi
0x18005a2a5  sub     rax, r9
0x18005a2a8  cmp     rax, 800h
0x18005a2ae  jbe     short loc_18005A2B7
0x18005a2b0  lea     rsi, [r9+800h]
0x18005a2b7  mov     rcx, [rdi]; pv
0x18005a2ba  cmp     rbp, rsi
0x18005a2bd  cmova   rsi, rbp
0x18005a2c1  lea     rdx, [rsi+rsi]; cb
0x18005a2c5  call    cs:__imp_CoTaskMemRealloc
0x18005a2cb  test    rax, rax
0x18005a2ce  jz      short loc_18005A2D9
0x18005a2d0  mov     [rdi+10h], rsi
0x18005a2d4  mov     [rdi], rax
0x18005a2d7  jmp     short loc_18005A2DE
0x18005a2d9  mov     ebx, 8007000Eh
0x18005a2de  mov     eax, ebx
0x18005a2e0  add     rsp, 28h
0x18005a2e4  pop     rdi
0x18005a2e5  pop     rsi
0x18005a2e6  pop     rbp
0x18005a2e7  pop     rbx
0x18005a2e8  retn
```
