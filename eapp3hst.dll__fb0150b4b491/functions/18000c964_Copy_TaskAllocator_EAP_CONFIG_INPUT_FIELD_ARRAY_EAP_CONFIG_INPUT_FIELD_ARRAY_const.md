# Copy<TaskAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &,_EAP_CONFIG_INPUT_FIELD_ARRAY const &)

- ea: `0x18000c964`
- end: `0x18000cae5`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@AEBU0@@Z`
- size: `385`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000caec`
- `0x18000e450`

## callees

- `0x18000c964`
- `0x18000ce64`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c9ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c9ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Copy<TaskAllocator>(__int64 a1, __int64 a2)
{
  int v4; // eax
  char v5; // di
  void *v6; // rax
  unsigned int i; // r14d
  __int64 v8; // rdx
  __int64 v9; // rcx
  void *v10; // rcx
  __int64 v11; // r8
  _WORD *v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  void *v15; // rcx
  __int64 v16; // r8
  _WORD *v17; // rdx

  *(_OWORD *)a1 = 0;
  *(_DWORD *)a1 = *(_DWORD *)a2;
  v4 = *(_DWORD *)(a2 + 4);
  v5 = 1;
  if ( v4 && *(_QWORD *)(a2 + 8) )
  {
    *(_DWORD *)(a1 + 4) = v4;
    v6 = CoTaskMemAlloc(40LL * *(unsigned int *)(a2 + 4));
    *(_QWORD *)(a1 + 8) = v6;
    if ( v6 )
    {
      memcpy_0(v6, *(const void **)(a2 + 8), 40LL * *(unsigned int *)(a2 + 4));
      for ( i = 0; i < *(_DWORD *)(a1 + 4); ++i )
      {
        v8 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 40LL * i + 16);
        if ( v8 )
        {
          v9 = -1;
          do
            ++v9;
          while ( *(_WORD *)(v8 + 2 * v9) );
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 40LL * i + 16) = CoTaskMemAlloc(2 * v9 + 2);
          v10 = *(void **)(*(_QWORD *)(a1 + 8) + 40LL * i + 16);
          if ( !v10 )
            goto LABEL_21;
          v11 = -1;
          v12 = *(_WORD **)(*(_QWORD *)(a2 + 8) + 40LL * i + 16);
          do
            ++v11;
          while ( v12[v11] );
          memcpy_0(v10, v12, 2 * v11 + 2);
        }
        v13 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 40LL * i + 24);
        if ( v13 )
        {
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)(v13 + 2 * v14) );
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 40LL * i + 24) = CoTaskMemAlloc(2 * v14 + 2);
          v15 = *(void **)(*(_QWORD *)(a1 + 8) + 40LL * i + 24);
          if ( !v15 )
            goto LABEL_21;
          v16 = -1;
          v17 = *(_WORD **)(*(_QWORD *)(a2 + 8) + 40LL * i + 24);
          do
            ++v16;
          while ( v17[v16] );
          memcpy_0(v15, v17, 2 * v16 + 2);
        }
      }
    }
    else
    {
LABEL_21:
      v5 = 0;
      Free<TaskAllocator>(a1);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000c964  push    rbx
0x18000c966  push    rbp
0x18000c967  push    rsi
0x18000c968  push    rdi
0x18000c969  push    r12
0x18000c96b  push    r14
0x18000c96d  push    r15
0x18000c96f  sub     rsp, 20h
0x18000c973  xorps   xmm0, xmm0
0x18000c976  xor     r15d, r15d
0x18000c979  movups  xmmword ptr [rcx], xmm0
0x18000c97c  mov     eax, [rdx]
0x18000c97e  mov     rbx, rdx
0x18000c981  mov     [rcx], eax
0x18000c983  mov     rsi, rcx
0x18000c986  mov     eax, [rdx+4]
0x18000c989  mov     edi, 1
0x18000c98e  test    eax, eax
0x18000c990  jz      loc_18000CAD3
0x18000c996  cmp     [rdx+8], r15
0x18000c99a  jz      loc_18000CAD3
0x18000c9a0  mov     [rcx+4], eax
0x18000c9a3  mov     eax, [rdx+4]
0x18000c9a6  lea     rcx, [rax+rax*4]
0x18000c9aa  shl     rcx, 3; cb
0x18000c9ae  call    cs:__imp_CoTaskMemAlloc
0x18000c9b4  mov     [rsi+8], rax
0x18000c9b8  mov     rcx, rax; void *
0x18000c9bb  test    rax, rax
0x18000c9be  jz      loc_18000CAC8
0x18000c9c4  mov     eax, [rbx+4]
0x18000c9c7  mov     rdx, [rbx+8]; Src
0x18000c9cb  lea     r8, [rax+rax*4]
0x18000c9cf  shl     r8, 3; Size
0x18000c9d3  call    memcpy_0
0x18000c9d8  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000c9dc  mov     r14d, r15d
0x18000c9df  cmp     r14d, [rsi+4]
0x18000c9e3  jnb     loc_18000CAD3
0x18000c9e9  mov     eax, r14d
0x18000c9ec  lea     rbp, [rax+rax*4]
0x18000c9f0  mov     rax, [rbx+8]
0x18000c9f4  mov     rdx, [rax+rbp*8+10h]
0x18000c9f9  test    rdx, rdx
0x18000c9fc  jz      short loc_18000CA5A
0x18000c9fe  mov     rcx, r12
0x18000ca01  inc     rcx
0x18000ca04  cmp     [rdx+rcx*2], r15w
0x18000ca09  jnz     short loc_18000CA01
0x18000ca0b  lea     rcx, ds:2[rcx*2]; cb
0x18000ca13  call    cs:__imp_CoTaskMemAlloc
0x18000ca19  mov     rcx, rax
0x18000ca1c  mov     rax, [rsi+8]
0x18000ca20  mov     [rax+rbp*8+10h], rcx
0x18000ca25  mov     rax, [rsi+8]
0x18000ca29  mov     rcx, [rax+rbp*8+10h]; void *
0x18000ca2e  test    rcx, rcx
0x18000ca31  jz      loc_18000CAC8
0x18000ca37  mov     rax, [rbx+8]
0x18000ca3b  mov     r8, r12
0x18000ca3e  mov     rdx, [rax+rbp*8+10h]; Src
0x18000ca43  inc     r8
0x18000ca46  cmp     [rdx+r8*2], r15w
0x18000ca4b  jnz     short loc_18000CA43
0x18000ca4d  lea     r8, ds:2[r8*2]; Size
0x18000ca55  call    memcpy_0
0x18000ca5a  mov     rax, [rbx+8]
0x18000ca5e  mov     rdx, [rax+rbp*8+18h]
0x18000ca63  test    rdx, rdx
0x18000ca66  jz      short loc_18000CAC0
0x18000ca68  mov     rcx, r12
0x18000ca6b  inc     rcx
0x18000ca6e  cmp     [rdx+rcx*2], r15w
0x18000ca73  jnz     short loc_18000CA6B
0x18000ca75  lea     rcx, ds:2[rcx*2]; cb
0x18000ca7d  call    cs:__imp_CoTaskMemAlloc
0x18000ca83  mov     rcx, rax
0x18000ca86  mov     rax, [rsi+8]
0x18000ca8a  mov     [rax+rbp*8+18h], rcx
0x18000ca8f  mov     rax, [rsi+8]
0x18000ca93  mov     rcx, [rax+rbp*8+18h]; void *
0x18000ca98  test    rcx, rcx
0x18000ca9b  jz      short loc_18000CAC8
0x18000ca9d  mov     rax, [rbx+8]
0x18000caa1  mov     r8, r12
0x18000caa4  mov     rdx, [rax+rbp*8+18h]; Src
0x18000caa9  inc     r8
0x18000caac  cmp     [rdx+r8*2], r15w
0x18000cab1  jnz     short loc_18000CAA9
0x18000cab3  lea     r8, ds:2[r8*2]; Size
0x18000cabb  call    memcpy_0
0x18000cac0  add     r14d, edi
0x18000cac3  jmp     loc_18000C9DF
0x18000cac8  mov     dil, r15b
0x18000cacb  mov     rcx, rsi
0x18000cace  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; Free<TaskAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)
0x18000cad3  mov     al, dil
0x18000cad6  add     rsp, 20h
0x18000cada  pop     r15
0x18000cadc  pop     r14
0x18000cade  pop     r12
0x18000cae0  pop     rdi
0x18000cae1  pop     rsi
0x18000cae2  pop     rbp
0x18000cae3  pop     rbx
0x18000cae4  retn
```
