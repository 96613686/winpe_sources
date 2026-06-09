# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180009b24`
- end: `0x180009c15`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800066dc`

## callees

- `0x1800092b8`
- `0x180009b24`
- `0x180009c1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180009bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180009bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009b8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009b8d`

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
  SIZE_T cb[5]; // [rsp+20h] [rbp-28h] BYREF

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
    cb[0] = 0;
    v4 = ULongLongMult(v2, a2, cb);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v7 = CoTaskMemAlloc(cb[0]);
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
    cb[0] = 0;
    v4 = ULongLongMult(v5, a2, cb);
    if ( v4 >= 0 )
    {
      v9 = cb[0];
      if ( cb[0] - v8 > 0x800 )
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
0x180009b24  mov     [rsp+arg_10], rbx
0x180009b29  push    rbp
0x180009b2a  push    rsi
0x180009b2b  push    rdi
0x180009b2c  sub     rsp, 30h
0x180009b30  lea     rbp, [rdx+1]
0x180009b34  mov     rdi, rcx
0x180009b37  cmp     rbp, rdx
0x180009b3a  jnb     short loc_180009B46
0x180009b3c  mov     ebx, 80070216h
0x180009b41  jmp     loc_180009C06
0x180009b46  mov     r9, [rcx+10h]
0x180009b4a  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180009b4e  jnz     short loc_180009B6B
0x180009b50  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180009b55  cmp     qword ptr [rcx], 0
0x180009b59  jz      short loc_180009B64
0x180009b5b  mov     r9, [rcx+8]
0x180009b5f  inc     r9
0x180009b62  jmp     short loc_180009B67
0x180009b64  xor     r9d, r9d
0x180009b67  mov     [rcx+10h], r9
0x180009b6b  test    r9, r9
0x180009b6e  jnz     short loc_180009BA6
0x180009b70  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180009b75  mov     [rsp+48h+cb], r9
0x180009b7a  mov     rcx, rbp; unsigned __int64
0x180009b7d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180009b82  mov     ebx, eax
0x180009b84  test    eax, eax
0x180009b86  js      short loc_180009C06
0x180009b88  mov     rcx, [rsp+48h+cb]; cb
0x180009b8d  call    cs:__imp_CoTaskMemAlloc
0x180009b93  test    rax, rax
0x180009b96  jz      short loc_180009C01
0x180009b98  xor     ecx, ecx
0x180009b9a  mov     [rdi+10h], rbp
0x180009b9e  mov     [rdi], rax
0x180009ba1  mov     [rax], cx
0x180009ba4  jmp     short loc_180009C06
0x180009ba6  xor     ebx, ebx
0x180009ba8  cmp     rbp, r9
0x180009bab  jbe     short loc_180009C06
0x180009bad  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180009bb2  mov     [rsp+48h+cb], rbx
0x180009bb7  mov     rcx, r9; unsigned __int64
0x180009bba  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180009bbf  mov     ebx, eax
0x180009bc1  test    eax, eax
0x180009bc3  js      short loc_180009C06
0x180009bc5  mov     rsi, [rsp+48h+cb]
0x180009bca  mov     rax, rsi
0x180009bcd  sub     rax, r9
0x180009bd0  cmp     rax, 800h
0x180009bd6  jbe     short loc_180009BDF
0x180009bd8  lea     rsi, [r9+800h]
0x180009bdf  mov     rcx, [rdi]; pv
0x180009be2  cmp     rbp, rsi
0x180009be5  cmova   rsi, rbp
0x180009be9  lea     rdx, [rsi+rsi]; cb
0x180009bed  call    cs:__imp_CoTaskMemRealloc
0x180009bf3  test    rax, rax
0x180009bf6  jz      short loc_180009C01
0x180009bf8  mov     [rdi+10h], rsi
0x180009bfc  mov     [rdi], rax
0x180009bff  jmp     short loc_180009C06
0x180009c01  mov     ebx, 8007000Eh
0x180009c06  mov     eax, ebx
0x180009c08  mov     rbx, [rsp+48h+arg_10]
0x180009c0d  add     rsp, 30h
0x180009c11  pop     rdi
0x180009c12  pop     rsi
0x180009c13  pop     rbp
0x180009c14  retn
```
