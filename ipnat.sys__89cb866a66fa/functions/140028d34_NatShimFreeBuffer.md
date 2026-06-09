# NatShimFreeBuffer

- ea: `0x140028d34`
- end: `0x140028e9a`
- name: `NatShimFreeBuffer`
- size: `358`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140028af8`
- `0x140028c0c`
- `0x140028ea0`

## callees

- `0x140028d34`
- `0x14002c29c`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140028dd0`
- `ntoskrnl!KfRaiseIrql` at `0x140028dd0`
- `ntoskrnl!KeLowerIrql` at `0x140028e63`
- `ntoskrnl!KeLowerIrql` at `0x140028e63`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140028d9a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140028d9a`
- `ntoskrnl!ExQueryDepthSList` at `0x140028e06`
- `ntoskrnl!ExQueryDepthSList` at `0x140028e06`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140028dba`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140028de4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140028dba`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140028de4`

## pseudocode

```c
void __fastcall NatShimFreeBuffer(_QWORD *a1)
{
  unsigned __int64 v1; // r8
  unsigned __int64 v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // rbp
  __int16 v5; // r15
  __int64 v6; // r14
  unsigned __int64 v7; // rax
  int v8; // ebx
  KIRQL v9; // al
  int v10; // ebx
  KIRQL v11; // r12
  _QWORD *v12; // rdx
  __int64 v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  _QWORD *v16; // [rsp+70h] [rbp+8h]

  if ( a1 )
  {
    v1 = (unsigned __int64)a1;
    do
    {
      v2 = v1 & 0xFFFFFFFFFFFFF000uLL;
      v16 = *(_QWORD **)v1;
      v3 = *(_QWORD *)(v1 & 0xFFFFFFFFFFFFF000uLL);
      v4 = MEMORY[0xFFFFF78000000320];
      v5 = *(_WORD *)((v1 & 0xFFFFFFFFFFFFF000uLL) + 0x1A);
      v6 = *(_QWORD *)(v3 + 32);
      v7 = (unsigned __int64)*(unsigned int *)(v3 + 40) << 6;
      *(_QWORD *)((v1 & 0xFFFFFFFFFFFFF000uLL) + 0x30) = MEMORY[0xFFFFF78000000320];
      ExpInterlockedPushEntrySList(
        (PSLIST_HEADER)((v1 & 0xFFFFFFFFFFFFF000uLL) + 32),
        (PSLIST_ENTRY)(v1 + *(unsigned __int16 *)(v3 - v7 - 54)));
      if ( v5 || v4 > v6 )
      {
        v8 = *(_DWORD *)(v3 + 40);
        if ( KeGetCurrentProcessorNumberEx(0) == v8 )
        {
          v9 = KfRaiseIrql(2u);
          v10 = *(_DWORD *)(v3 + 40);
          v11 = v9;
          if ( KeGetCurrentProcessorNumberEx(0) == v10 )
          {
            if ( v5 && *(_WORD *)(v2 + 26) && ExQueryDepthSList((PSLIST_HEADER)(v2 + 32)) )
            {
              v12 = (_QWORD *)(v2 + 8);
              v13 = *(_QWORD *)(v2 + 8);
              if ( *(_QWORD *)(v13 + 8) != v2 + 8
                || (v14 = *(_QWORD **)(v2 + 16), (_QWORD *)*v14 != v12)
                || (*v14 = v13,
                    *(_QWORD *)(v13 + 8) = v14,
                    *(_WORD *)(v2 + 26) = 0,
                    v15 = *(_QWORD **)(v3 + 8),
                    *v15 != v3) )
              {
                __fastfail(3u);
              }
              *v12 = v3;
              *(_QWORD *)(v2 + 16) = v15;
              *v15 = v12;
              *(_QWORD *)(v3 + 8) = v12;
            }
            if ( v4 > v6 )
              FsbpScavengePool(v3);
          }
          KeLowerIrql(v11);
        }
      }
      v1 = (unsigned __int64)v16;
    }
    while ( v16 );
  }
}

```

## disassembly

```asm
0x140028d34  test    rcx, rcx
0x140028d37  jz      locret_140028E91
0x140028d3d  push    rbx
0x140028d3e  push    rbp
0x140028d3f  push    rsi
0x140028d40  push    rdi
0x140028d41  push    r12
0x140028d43  push    r13
0x140028d45  push    r14
0x140028d47  push    r15
0x140028d49  sub     rsp, 28h
0x140028d4d  mov     r8, rcx
0x140028d50  xor     ebx, ebx
0x140028d52  mov     rax, [r8]
0x140028d55  mov     rsi, r8
0x140028d58  and     rsi, 0FFFFFFFFFFFFF000h
0x140028d5f  mov     [rsp+68h+arg_0], rax
0x140028d64  mov     rbp, 0FFFFF78000000320h
0x140028d6e  mov     rdi, [rsi]
0x140028d71  mov     rbp, [rbp+0]
0x140028d75  mov     rcx, rdi
0x140028d78  movzx   r15d, word ptr [rsi+1Ah]
0x140028d7d  mov     eax, [rdi+28h]
0x140028d80  mov     r14, [rdi+20h]
0x140028d84  shl     rax, 6
0x140028d88  sub     rcx, rax
0x140028d8b  mov     [rsi+30h], rbp
0x140028d8f  movzx   edx, word ptr [rcx-36h]
0x140028d93  lea     rcx, [rsi+20h]; ListHead
0x140028d97  add     rdx, r8; ListEntry
0x140028d9a  call    cs:__imp_ExpInterlockedPushEntrySList
0x140028da1  nop     dword ptr [rax+rax+00h]
0x140028da6  test    r15w, r15w
0x140028daa  jnz     short loc_140028DB5
0x140028dac  cmp     rbp, r14
0x140028daf  jle     loc_140028E73
0x140028db5  mov     ebx, [rdi+28h]
0x140028db8  xor     ecx, ecx; ProcNumber
0x140028dba  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140028dc1  nop     dword ptr [rax+rax+00h]
0x140028dc6  cmp     eax, ebx
0x140028dc8  jnz     loc_140028E71
0x140028dce  mov     cl, 2; NewIrql
0x140028dd0  call    cs:__imp_KfRaiseIrql
0x140028dd7  nop     dword ptr [rax+rax+00h]
0x140028ddc  mov     ebx, [rdi+28h]
0x140028ddf  xor     ecx, ecx; ProcNumber
0x140028de1  mov     r12b, al
0x140028de4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140028deb  nop     dword ptr [rax+rax+00h]
0x140028df0  cmp     eax, ebx
0x140028df2  jnz     short loc_140028E5E
0x140028df4  xor     ebx, ebx
0x140028df6  test    r15w, r15w
0x140028dfa  jz      short loc_140028E4F
0x140028dfc  cmp     [rsi+1Ah], bx
0x140028e00  jz      short loc_140028E4F
0x140028e02  lea     rcx, [rsi+20h]; SListHead
0x140028e06  call    cs:__imp_ExQueryDepthSList
0x140028e0d  nop     dword ptr [rax+rax+00h]
0x140028e12  cmp     bx, ax
0x140028e15  jz      short loc_140028E4F
0x140028e17  lea     rdx, [rsi+8]
0x140028e1b  mov     rax, [rdx]
0x140028e1e  cmp     [rax+8], rdx
0x140028e22  jnz     short loc_140028E93
0x140028e24  mov     rcx, [rsi+10h]
0x140028e28  cmp     [rcx], rdx
0x140028e2b  jnz     short loc_140028E93
0x140028e2d  mov     [rcx], rax
0x140028e30  mov     [rax+8], rcx
0x140028e34  mov     [rsi+1Ah], bx
0x140028e38  mov     rax, [rdi+8]
0x140028e3c  cmp     [rax], rdi
0x140028e3f  jnz     short loc_140028E93
0x140028e41  mov     [rdx], rdi
0x140028e44  mov     [rdx+8], rax
0x140028e48  mov     [rax], rdx
0x140028e4b  mov     [rdi+8], rdx
0x140028e4f  cmp     rbp, r14
0x140028e52  jle     short loc_140028E60
0x140028e54  mov     rcx, rdi
0x140028e57  call    FsbpScavengePool
0x140028e5c  jmp     short loc_140028E60
0x140028e5e  xor     ebx, ebx
0x140028e60  mov     cl, r12b; NewIrql
0x140028e63  call    cs:__imp_KeLowerIrql
0x140028e6a  nop     dword ptr [rax+rax+00h]
0x140028e6f  jmp     short loc_140028E73
0x140028e71  xor     ebx, ebx
0x140028e73  mov     r8, [rsp+68h+arg_0]
0x140028e78  test    r8, r8
0x140028e7b  jnz     loc_140028D52
0x140028e81  add     rsp, 28h
0x140028e85  pop     r15
0x140028e87  pop     r14
0x140028e89  pop     r13
0x140028e8b  pop     r12
0x140028e8d  pop     rdi
0x140028e8e  pop     rsi
0x140028e8f  pop     rbp
0x140028e90  pop     rbx
0x140028e91  retn
0x140028e93  mov     ecx, 3
0x140028e98  int     29h; Win8: RtlFailFast(ecx)
```
