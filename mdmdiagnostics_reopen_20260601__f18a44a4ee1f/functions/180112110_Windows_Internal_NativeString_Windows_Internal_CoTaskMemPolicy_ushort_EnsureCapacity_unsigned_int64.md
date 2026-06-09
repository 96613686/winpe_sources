# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180112110`
- end: `0x180112243`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801070c8`

## callees

- `0x1800f962c`
- `0x180112110`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801121a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801121a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18011220e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18011220e`

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
0x180112110  mov     [rsp+arg_0], rbx
0x180112115  mov     [rsp+arg_10], rbp
0x18011211a  push    rsi
0x18011211b  push    rdi
0x18011211c  push    r14
0x18011211e  sub     rsp, 20h
0x180112122  lea     rbp, [rdx+1]
0x180112126  mov     rdi, rcx
0x180112129  cmp     rbp, rdx
0x18011212c  jnb     short loc_180112138
0x18011212e  mov     ebx, 80070216h
0x180112133  jmp     loc_18011222D
0x180112138  mov     r9, [rcx+10h]
0x18011213c  xor     r14d, r14d
0x18011213f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180112143  cmp     r9, rcx
0x180112146  jnz     short loc_180112182
0x180112148  cmp     [rdi+8], rcx
0x18011214c  jnz     short loc_18011216B
0x18011214e  mov     rax, [rdi]
0x180112151  test    rax, rax
0x180112154  jz      short loc_180112162
0x180112156  inc     rcx
0x180112159  cmp     [rax+rcx*2], r14w
0x18011215e  jnz     short loc_180112156
0x180112160  jmp     short loc_180112165
0x180112162  mov     rcx, r14
0x180112165  mov     [rdi+8], rcx
0x180112169  jmp     short loc_18011216F
0x18011216b  mov     rcx, [rdi+8]
0x18011216f  mov     rax, [rdi]
0x180112172  inc     rcx
0x180112175  neg     rax
0x180112178  sbb     r9, r9
0x18011217b  and     r9, rcx
0x18011217e  mov     [rdi+10h], r9
0x180112182  test    r9, r9
0x180112185  jnz     short loc_1801121C6
0x180112187  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18011218c  mov     [rsp+38h+cb], r14
0x180112191  mov     rcx, rbp; unsigned __int64
0x180112194  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180112199  mov     ebx, eax
0x18011219b  test    eax, eax
0x18011219d  js      loc_18011222D
0x1801121a3  mov     rcx, [rsp+38h+cb]; cb
0x1801121a8  call    cs:__imp_CoTaskMemAlloc
0x1801121af  nop     dword ptr [rax+rax+00h]
0x1801121b4  test    rax, rax
0x1801121b7  jz      short loc_180112228
0x1801121b9  mov     [rdi+10h], rbp
0x1801121bd  mov     [rdi], rax
0x1801121c0  mov     [rax], r14w
0x1801121c4  jmp     short loc_18011222D
0x1801121c6  mov     ebx, r14d
0x1801121c9  cmp     rbp, r9
0x1801121cc  jbe     short loc_18011222D
0x1801121ce  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1801121d3  mov     [rsp+38h+cb], r14
0x1801121d8  mov     rcx, r9; unsigned __int64
0x1801121db  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1801121e0  mov     ebx, eax
0x1801121e2  test    eax, eax
0x1801121e4  js      short loc_18011222D
0x1801121e6  mov     rsi, [rsp+38h+cb]
0x1801121eb  mov     rax, rsi
0x1801121ee  sub     rax, r9
0x1801121f1  cmp     rax, 800h
0x1801121f7  jbe     short loc_180112200
0x1801121f9  lea     rsi, [r9+800h]
0x180112200  mov     rcx, [rdi]; pv
0x180112203  cmp     rbp, rsi
0x180112206  cmova   rsi, rbp
0x18011220a  lea     rdx, [rsi+rsi]; cb
0x18011220e  call    cs:__imp_CoTaskMemRealloc
0x180112215  nop     dword ptr [rax+rax+00h]
0x18011221a  test    rax, rax
0x18011221d  jz      short loc_180112228
0x18011221f  mov     [rdi+10h], rsi
0x180112223  mov     [rdi], rax
0x180112226  jmp     short loc_18011222D
0x180112228  mov     ebx, 8007000Eh
0x18011222d  mov     rbp, [rsp+38h+arg_10]
0x180112232  mov     eax, ebx
0x180112234  mov     rbx, [rsp+38h+arg_0]
0x180112239  add     rsp, 20h
0x18011223d  pop     r14
0x18011223f  pop     rdi
0x180112240  pop     rsi
0x180112241  retn
```
