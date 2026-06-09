# Copy<TaskAllocator>(_EAP_METHOD_INFO &,_EAP_METHOD_INFO const &)

- ea: `0x180003dc8`
- end: `0x180003e98`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_METHOD_INFO@@AEBU0@@Z`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003dc8`
- `0x180003ea0`

## callees

- `0x180003a30`
- `0x180003dc8`
- `0x1800041a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003e56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003e56`

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
0x180003dc8  push    rbx
0x180003dca  push    rbp
0x180003dcb  push    rsi
0x180003dcc  push    rdi
0x180003dcd  sub     rsp, 28h
0x180003dd1  mov     rdi, rdx
0x180003dd4  mov     rbx, rcx
0x180003dd7  xorps   xmm0, xmm0
0x180003dda  movups  xmmword ptr [rcx], xmm0
0x180003ddd  movups  xmmword ptr [rcx+10h], xmm0
0x180003de1  movups  xmmword ptr [rcx+20h], xmm0
0x180003de5  movups  xmm0, xmmword ptr [rdx]
0x180003de8  movdqu  xmmword ptr [rcx], xmm0
0x180003dec  mov     rcx, [rdx+10h]; Src
0x180003df0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003df4  xor     ebp, ebp
0x180003df6  test    rcx, rcx
0x180003df9  jz      short loc_180003E1D
0x180003dfb  mov     rdx, rsi
0x180003dfe  inc     rdx
0x180003e01  cmp     [rcx+rdx*2], bp
0x180003e05  jnz     short loc_180003DFE
0x180003e07  lea     rdx, ds:2[rdx*2]; Size
0x180003e0f  call    ??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z; Copy<TaskAllocator>(uchar const *,unsigned __int64)
0x180003e14  mov     [rbx+10h], rax
0x180003e18  test    rax, rax
0x180003e1b  jz      short loc_180003E7B
0x180003e1d  mov     rcx, [rdi+18h]; Src
0x180003e21  test    rcx, rcx
0x180003e24  jz      short loc_180003E45
0x180003e26  inc     rsi
0x180003e29  cmp     [rcx+rsi*2], bp
0x180003e2d  jnz     short loc_180003E26
0x180003e2f  lea     rdx, ds:2[rsi*2]; Size
0x180003e37  call    ??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z; Copy<TaskAllocator>(uchar const *,unsigned __int64)
0x180003e3c  mov     [rbx+18h], rax
0x180003e40  test    rax, rax
0x180003e43  jz      short loc_180003E7B
0x180003e45  mov     eax, [rdi+20h]
0x180003e48  mov     [rbx+20h], eax
0x180003e4b  cmp     [rdi+28h], rbp
0x180003e4f  jz      short loc_180003E88
0x180003e51  mov     ecx, 30h ; '0'; cb
0x180003e56  call    cs:__imp_CoTaskMemAlloc
0x180003e5d  nop     dword ptr [rax+rax+00h]
0x180003e62  mov     [rbx+28h], rax
0x180003e66  test    rax, rax
0x180003e69  jz      short loc_180003E7B
0x180003e6b  mov     rdx, [rdi+28h]
0x180003e6f  mov     rcx, rax
0x180003e72  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_METHOD_INFO@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_METHOD_INFO &,_EAP_METHOD_INFO const &)
0x180003e77  test    al, al
0x180003e79  jnz     short loc_180003E88
0x180003e7b  mov     dil, bpl
0x180003e7e  mov     rcx, rbx
0x180003e81  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<TaskAllocator>(_EAP_METHOD_INFO &)
0x180003e86  jmp     short loc_180003E8B
0x180003e88  mov     dil, 1
0x180003e8b  mov     al, dil
0x180003e8e  add     rsp, 28h
0x180003e92  pop     rdi
0x180003e93  pop     rsi
0x180003e94  pop     rbp
0x180003e95  pop     rbx
0x180003e96  retn
```
