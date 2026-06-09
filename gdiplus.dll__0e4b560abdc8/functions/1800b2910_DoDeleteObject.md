# DoDeleteObject

- ea: `0x1800b2910`
- end: `0x1800b2a90`
- name: `DoDeleteObject`
- size: `384`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1800b0428`
- `0x1800e0810`
- `0x18013e8d0`

## callees

- `0x1800b2190`
- `0x1800b224c`
- `0x1800b2910`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2a01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2a01`
- `GDI32!DeleteObject` at `0x1800b2975`
- `GDI32!DeleteObject` at `0x1800b29cb`
- `GDI32!DeleteObject` at `0x1800b2975`
- `GDI32!DeleteObject` at `0x1800b29cb`

## pseudocode

```c
__int64 __fastcall DoDeleteObject(__int64 a1, unsigned int a2)
{
  unsigned int v3; // edi
  signed int v4; // eax
  __int64 v5; // r8
  __int64 result; // rax
  __int64 v7; // rcx
  void *v8; // rcx
  __int64 v9; // rsi
  __int64 v10; // r14
  __int64 v11; // rbp
  __int64 v12; // rsi
  void *v13; // rcx
  _QWORD *v14; // rax

  v3 = 0;
  v4 = iNormalizeHandle(a1, a2);
  if ( v4 != -1 )
  {
    if ( (unsigned int)v4 <= 0x13 )
      return 1;
    v7 = *(_QWORD *)(a1 + 552);
    if ( v7 )
    {
      if ( (int)v5 < 0 || (unsigned int)v5 >= *(_DWORD *)(a1 + 520) )
        return 0;
      v8 = *(void **)(v7 + 8 * v5);
      v9 = v5;
      if ( v8 )
      {
        LODWORD(result) = DeleteObject(v8);
        *(_QWORD *)(*(_QWORD *)(a1 + 552) + 8 * v9) = 0;
        return (unsigned int)result;
      }
    }
    v10 = v4;
    v11 = *(int *)(*(_QWORD *)(a1 + 400) + 4LL * v4);
    if ( (_DWORD)v11 != -1 )
    {
      v12 = 32 * v11;
      v13 = *(void **)(*(_QWORD *)(a1 + 416) + 32 * v11 + 8);
      if ( v13 )
      {
        DeleteObject(v13);
        *(_QWORD *)(*(_QWORD *)(a1 + 416) + v12 + 8) = 0;
      }
      if ( *(_DWORD *)(a1 + 484) != 1 || *(_DWORD *)(*(_QWORD *)(a1 + 416) + v12 + 16) == 1 )
        goto LABEL_17;
      v14 = LocalAlloc(0, 0x18u);
      if ( v14 )
      {
        *(_DWORD *)v14 = v11;
        v14[1] = *(_QWORD *)(*(_QWORD *)(a1 + 416) + v12 + 24);
        v14[2] = *(_QWORD *)(a1 + 560);
        *(_QWORD *)(a1 + 560) = v14;
LABEL_17:
        *(_DWORD *)(v12 + *(_QWORD *)(a1 + 416)) = 1;
        *(_QWORD *)(*(_QWORD *)(a1 + 416) + v12 + 24) = 0;
        *(_DWORD *)(*(_QWORD *)(a1 + 400) + 4 * v10) = -1;
        return (unsigned int)bW16Emit1(a1, 496, (unsigned __int16)v11);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800b2910  mov     rax, rsp
0x1800b2913  mov     [rax+8], rbx
0x1800b2917  mov     [rax+10h], rbp
0x1800b291b  mov     [rax+18h], rsi
0x1800b291f  mov     [rax+20h], rdi
0x1800b2923  push    r14
0x1800b2925  sub     rsp, 20h
0x1800b2929  movsxd  r8, edx
0x1800b292c  mov     rbx, rcx
0x1800b292f  mov     edx, r8d
0x1800b2932  xor     edi, edi
0x1800b2934  call    iNormalizeHandle
0x1800b2939  cmp     eax, 0FFFFFFFFh
0x1800b293c  jz      loc_1800B2A72
0x1800b2942  cmp     eax, 13h
0x1800b2945  ja      short loc_1800B294F
0x1800b2947  lea     eax, [rdi+1]
0x1800b294a  jmp     loc_1800B2A74
0x1800b294f  mov     rcx, [rbx+228h]
0x1800b2956  test    rcx, rcx
0x1800b2959  jz      short loc_1800B299C
0x1800b295b  test    r8d, r8d
0x1800b295e  js      short loc_1800B2995
0x1800b2960  cmp     r8d, [rbx+208h]
0x1800b2967  jnb     short loc_1800B2995
0x1800b2969  mov     rcx, [rcx+r8*8]; ho
0x1800b296d  mov     rsi, r8
0x1800b2970  test    rcx, rcx
0x1800b2973  jz      short loc_1800B299C
0x1800b2975  call    cs:__imp_DeleteObject
0x1800b297c  nop     dword ptr [rax+rax+00h]
0x1800b2981  mov     ecx, eax
0x1800b2983  mov     rax, [rbx+228h]
0x1800b298a  mov     [rax+rsi*8], rdi
0x1800b298e  mov     eax, ecx
0x1800b2990  jmp     loc_1800B2A74
0x1800b2995  xor     eax, eax
0x1800b2997  jmp     loc_1800B2A74
0x1800b299c  movsxd  r14, eax
0x1800b299f  mov     rax, [rbx+190h]
0x1800b29a6  movsxd  rbp, dword ptr [rax+r14*4]
0x1800b29aa  cmp     ebp, 0FFFFFFFFh
0x1800b29ad  jz      loc_1800B2A72
0x1800b29b3  mov     rax, [rbx+1A0h]
0x1800b29ba  mov     rsi, rbp
0x1800b29bd  shl     rsi, 5
0x1800b29c1  mov     rcx, [rax+rsi+8]; ho
0x1800b29c6  test    rcx, rcx
0x1800b29c9  jz      short loc_1800B29E3
0x1800b29cb  call    cs:__imp_DeleteObject
0x1800b29d2  nop     dword ptr [rax+rax+00h]
0x1800b29d7  mov     rax, [rbx+1A0h]
0x1800b29de  mov     [rax+rsi+8], rdi
0x1800b29e3  cmp     dword ptr [rbx+1E4h], 1
0x1800b29ea  jnz     short loc_1800B2A39
0x1800b29ec  mov     rax, [rbx+1A0h]
0x1800b29f3  cmp     dword ptr [rax+rsi+10h], 1
0x1800b29f8  jz      short loc_1800B2A39
0x1800b29fa  mov     edx, 18h; uBytes
0x1800b29ff  xor     ecx, ecx; uFlags
0x1800b2a01  call    cs:__imp_LocalAlloc
0x1800b2a08  nop     dword ptr [rax+rax+00h]
0x1800b2a0d  mov     rdx, rax
0x1800b2a10  test    rax, rax
0x1800b2a13  jz      short loc_1800B2A72
0x1800b2a15  mov     [rax], ebp
0x1800b2a17  mov     rax, [rbx+1A0h]
0x1800b2a1e  mov     rcx, [rax+rsi+18h]
0x1800b2a23  mov     [rdx+8], rcx
0x1800b2a27  mov     rax, [rbx+230h]
0x1800b2a2e  mov     [rdx+10h], rax
0x1800b2a32  mov     [rbx+230h], rdx
0x1800b2a39  mov     rax, [rbx+1A0h]
0x1800b2a40  mov     edx, 1F0h
0x1800b2a45  movzx   r8d, bp
0x1800b2a49  mov     rcx, rbx
0x1800b2a4c  mov     dword ptr [rsi+rax], 1
0x1800b2a53  mov     rax, [rbx+1A0h]
0x1800b2a5a  mov     [rax+rsi+18h], rdi
0x1800b2a5f  mov     rax, [rbx+190h]
0x1800b2a66  or      dword ptr [rax+r14*4], 0FFFFFFFFh
0x1800b2a6b  call    bW16Emit1
0x1800b2a70  mov     edi, eax
0x1800b2a72  mov     eax, edi
0x1800b2a74  mov     rbx, [rsp+28h+arg_0]
0x1800b2a79  mov     rbp, [rsp+28h+arg_8]
0x1800b2a7e  mov     rsi, [rsp+28h+arg_10]
0x1800b2a83  mov     rdi, [rsp+28h+arg_18]
0x1800b2a88  add     rsp, 20h
0x1800b2a8c  pop     r14
0x1800b2a8e  retn
```
