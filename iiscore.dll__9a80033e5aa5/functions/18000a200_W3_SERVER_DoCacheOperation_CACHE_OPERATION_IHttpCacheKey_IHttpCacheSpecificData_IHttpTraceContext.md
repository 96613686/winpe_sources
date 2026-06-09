# W3_SERVER::DoCacheOperation(CACHE_OPERATION,IHttpCacheKey *,IHttpCacheSpecificData * *,IHttpTraceContext *)

- ea: `0x18000a200`
- end: `0x18000a32f`
- name: `?DoCacheOperation@W3_SERVER@@UEAAJW4CACHE_OPERATION@@PEAVIHttpCacheKey@@PEAPEAVIHttpCacheSpecificData@@PEAVIHttpTraceContext@@@Z`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000a200`
- `0x18000ad00`
- `0x180035010`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a280`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a296`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a280`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a296`

## pseudocode

```c
__int64 __fastcall W3_SERVER::DoCacheOperation(_DWORD *a1, int a2, __int64 a3, __int64 *a4, __int64 a5)
{
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD *Ptr; // rax
  __int64 v12; // rbx
  _QWORD *v13; // rdi
  unsigned int *v14; // rax
  __int64 v15; // rcx
  unsigned int *i; // rbx
  __int64 result; // rax
  void **v18; // [rsp+20h] [rbp-48h] BYREF
  int v19; // [rsp+28h] [rbp-40h]
  int v20; // [rsp+2Ch] [rbp-3Ch]
  __int64 v21; // [rsp+30h] [rbp-38h]
  __int64 v22; // [rsp+38h] [rbp-30h]
  __int64 v23; // [rsp+40h] [rbp-28h]

  if ( (int)a1[6] < 16 || a1[5] )
    return 2147942421LL;
  v9 = a5;
  if ( !a5 )
    v9 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 184LL))(a1);
  if ( a1[5] )
    return 2147500037LL;
  v19 = 0;
  v18 = &CACHE_DATA::`vftable';
  v23 = v9;
  if ( a2 == 1 )
    v10 = *a4;
  else
    v10 = 0;
  v20 = a2;
  v21 = a3;
  v22 = v10;
  Ptr = BUFFER::QueryPtr((BUFFER *)(a1 + 140));
  v12 = (unsigned int)a1[282];
  v13 = Ptr;
  v14 = (unsigned int *)BUFFER::QueryPtr((BUFFER *)(a1 + 264));
  v15 = v14[v12];
  for ( i = &v14[v12]; (_DWORD)v15 != -1; ++i )
  {
    if ( (unsigned int)VIRTUAL_MODULE::GlobalDoWork(v13[v15], 16, &v18) == 1 )
      break;
    v15 = i[1];
  }
  result = (unsigned int)v19;
  if ( v19 >= 0 )
  {
    if ( a4 )
      *a4 = v22;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a200  mov     [rsp+arg_8], rbx
0x18000a205  push    rsi
0x18000a206  push    rdi
0x18000a207  push    r14
0x18000a209  sub     rsp, 50h
0x18000a20d  cmp     dword ptr [rcx+18h], 10h
0x18000a211  mov     r14, r9
0x18000a214  mov     rdi, r8
0x18000a217  mov     ebx, edx
0x18000a219  mov     rsi, rcx
0x18000a21c  jl      loc_18000A301
0x18000a222  cmp     dword ptr [rcx+14h], 0
0x18000a226  jnz     loc_18000A301
0x18000a22c  mov     rax, [rsp+68h+arg_20]
0x18000a234  test    rax, rax
0x18000a237  jz      loc_18000A31B
0x18000a23d  cmp     dword ptr [rsi+14h], 0
0x18000a241  jnz     loc_18000A308
0x18000a247  mov     [rsp+68h+var_40], 0
0x18000a24f  lea     rcx, ??_7CACHE_DATA@@6B@; const CACHE_DATA::`vftable'
0x18000a256  mov     [rsp+68h+var_48], rcx
0x18000a25b  mov     [rsp+68h+var_28], rax
0x18000a260  cmp     ebx, 1
0x18000a263  jz      loc_18000A2F9
0x18000a269  xor     eax, eax
0x18000a26b  lea     rcx, [rsi+230h]
0x18000a272  mov     [rsp+68h+var_3C], ebx
0x18000a276  mov     [rsp+68h+var_38], rdi
0x18000a27b  mov     [rsp+68h+var_30], rax
0x18000a280  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a286  mov     ebx, [rsi+468h]
0x18000a28c  lea     rcx, [rsi+420h]
0x18000a293  mov     rdi, rax
0x18000a296  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a29c  mov     ecx, [rax+rbx*4]
0x18000a29f  lea     rbx, [rax+rbx*4]
0x18000a2a3  cmp     ecx, 0FFFFFFFFh
0x18000a2a6  jz      short loc_18000A2D4
0x18000a2a8  nop     dword ptr [rax+rax+00000000h]
0x18000a2b0  mov     rcx, [rdi+rcx*8]
0x18000a2b4  lea     r8, [rsp+68h+var_48]
0x18000a2b9  mov     edx, 10h
0x18000a2be  call    ?GlobalDoWork@VIRTUAL_MODULE@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; VIRTUAL_MODULE::GlobalDoWork(ulong,IHttpEventProvider *)
0x18000a2c3  cmp     eax, 1
0x18000a2c6  jz      short loc_18000A2D4
0x18000a2c8  mov     ecx, [rbx+4]
0x18000a2cb  add     rbx, 4
0x18000a2cf  cmp     ecx, 0FFFFFFFFh
0x18000a2d2  jnz     short loc_18000A2B0
0x18000a2d4  mov     eax, [rsp+68h+var_40]
0x18000a2d8  test    eax, eax
0x18000a2da  js      short loc_18000A2EB
0x18000a2dc  test    r14, r14
0x18000a2df  jz      short loc_18000A2E9
0x18000a2e1  mov     rax, [rsp+68h+var_30]
0x18000a2e6  mov     [r14], rax
0x18000a2e9  xor     eax, eax
0x18000a2eb  mov     rbx, [rsp+68h+arg_8]
0x18000a2f0  add     rsp, 50h
0x18000a2f4  pop     r14
0x18000a2f6  pop     rdi
0x18000a2f7  pop     rsi
0x18000a2f8  retn
0x18000a2f9  mov     rax, [r14]
0x18000a2fc  jmp     loc_18000A26B
0x18000a301  mov     eax, 80070015h
0x18000a306  jmp     short loc_18000A2EB
0x18000a308  mov     rbx, [rsp+68h+arg_8]
0x18000a30d  mov     eax, 80004005h
0x18000a312  add     rsp, 50h
0x18000a316  pop     r14
0x18000a318  pop     rdi
0x18000a319  pop     rsi
0x18000a31a  retn
0x18000a31b  mov     rax, [rcx]
0x18000a31e  mov     rax, [rax+0B8h]
0x18000a325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a32a  jmp     loc_18000A23D
```
