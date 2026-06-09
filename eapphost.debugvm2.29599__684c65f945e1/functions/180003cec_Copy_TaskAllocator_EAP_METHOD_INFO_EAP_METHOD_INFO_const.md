# Copy<TaskAllocator>(_EAP_METHOD_INFO &,_EAP_METHOD_INFO const &)

- ea: `0x180003cec`
- end: `0x180003db5`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_METHOD_INFO@@AEBU0@@Z`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003cec`
- `0x180003dbc`

## callees

- `0x180003990`
- `0x180003cec`
- `0x180004084`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003d7a`

## pseudocode

```c
char __fastcall Copy<TaskAllocator>(__int64 a1, __int64 a2)
{
  _WORD *v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rax
  _WORD *v8; // rcx
  __int64 v9; // rax
  LPVOID v10; // rax
  char v11; // di

  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_OWORD *)a1 = *(_OWORD *)a2;
  v4 = *(_WORD **)(a2 + 16);
  v5 = -1;
  if ( v4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v4[v6] );
    v7 = Copy<TaskAllocator>(v4, 2 * v6 + 2);
    *(_QWORD *)(a1 + 16) = v7;
    if ( !v7 )
      goto LABEL_11;
  }
  v8 = *(_WORD **)(a2 + 24);
  if ( v8 )
  {
    do
      ++v5;
    while ( v8[v5] );
    v9 = Copy<TaskAllocator>(v8, 2 * v5 + 2);
    *(_QWORD *)(a1 + 24) = v9;
    if ( !v9 )
      goto LABEL_11;
  }
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(a2 + 32);
  if ( !*(_QWORD *)(a2 + 40) )
    return 1;
  v10 = CoTaskMemAlloc(0x30u);
  *(_QWORD *)(a1 + 40) = v10;
  if ( v10 )
  {
    if ( (unsigned __int8)Copy<TaskAllocator>(v10, *(_QWORD *)(a2 + 40)) )
      return 1;
  }
LABEL_11:
  v11 = 0;
  Free<TaskAllocator>(a1);
  return v11;
}

```

## disassembly

```asm
0x180003cec  push    rbx
0x180003cee  push    rbp
0x180003cef  push    rsi
0x180003cf0  push    rdi
0x180003cf1  sub     rsp, 28h
0x180003cf5  mov     rdi, rdx
0x180003cf8  mov     rbx, rcx
0x180003cfb  xorps   xmm0, xmm0
0x180003cfe  movups  xmmword ptr [rcx], xmm0
0x180003d01  movups  xmmword ptr [rcx+10h], xmm0
0x180003d05  movups  xmmword ptr [rcx+20h], xmm0
0x180003d09  movups  xmm0, xmmword ptr [rdx]
0x180003d0c  movdqu  xmmword ptr [rcx], xmm0
0x180003d10  mov     rcx, [rdx+10h]; Src
0x180003d14  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003d18  xor     ebp, ebp
0x180003d1a  test    rcx, rcx
0x180003d1d  jz      short loc_180003D41
0x180003d1f  mov     rdx, rsi
0x180003d22  inc     rdx
0x180003d25  cmp     [rcx+rdx*2], bp
0x180003d29  jnz     short loc_180003D22
0x180003d2b  lea     rdx, ds:2[rdx*2]; Size
0x180003d33  call    ??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z; Copy<TaskAllocator>(uchar const *,unsigned __int64)
0x180003d38  mov     [rbx+10h], rax
0x180003d3c  test    rax, rax
0x180003d3f  jz      short loc_180003D99
0x180003d41  mov     rcx, [rdi+18h]; Src
0x180003d45  test    rcx, rcx
0x180003d48  jz      short loc_180003D69
0x180003d4a  inc     rsi
0x180003d4d  cmp     [rcx+rsi*2], bp
0x180003d51  jnz     short loc_180003D4A
0x180003d53  lea     rdx, ds:2[rsi*2]; Size
0x180003d5b  call    ??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z; Copy<TaskAllocator>(uchar const *,unsigned __int64)
0x180003d60  mov     [rbx+18h], rax
0x180003d64  test    rax, rax
0x180003d67  jz      short loc_180003D99
0x180003d69  mov     eax, [rdi+20h]
0x180003d6c  mov     [rbx+20h], eax
0x180003d6f  cmp     [rdi+28h], rbp
0x180003d73  jz      short loc_180003DA6
0x180003d75  mov     ecx, 30h ; '0'; cb
0x180003d7a  call    cs:__imp_CoTaskMemAlloc
0x180003d80  mov     [rbx+28h], rax
0x180003d84  test    rax, rax
0x180003d87  jz      short loc_180003D99
0x180003d89  mov     rdx, [rdi+28h]
0x180003d8d  mov     rcx, rax
0x180003d90  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_METHOD_INFO@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_METHOD_INFO &,_EAP_METHOD_INFO const &)
0x180003d95  test    al, al
0x180003d97  jnz     short loc_180003DA6
0x180003d99  mov     dil, bpl
0x180003d9c  mov     rcx, rbx
0x180003d9f  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<TaskAllocator>(_EAP_METHOD_INFO &)
0x180003da4  jmp     short loc_180003DA9
0x180003da6  mov     dil, 1
0x180003da9  mov     al, dil
0x180003dac  add     rsp, 28h
0x180003db0  pop     rdi
0x180003db1  pop     rsi
0x180003db2  pop     rbp
0x180003db3  pop     rbx
0x180003db4  retn
```
