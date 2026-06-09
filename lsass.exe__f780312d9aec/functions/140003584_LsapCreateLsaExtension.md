# LsapCreateLsaExtension

- ea: `0x140003584`
- end: `0x140003626`
- name: `LsapCreateLsaExtension`
- size: `162`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140003654`

## callees

- `0x1400016c0`
- `0x140001a80`
- `0x140003584`
- `0x140005295`

## pseudocode

```c
__int64 __fastcall LsapCreateLsaExtension(_WORD *Src, __int64 *a2, __int64 a3)
{
  __int64 LsaHeap; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // rax
  unsigned __int16 v11; // ax
  void *v12; // rax

  LsaHeap = LsapAllocateLsaHeap(88, a2, a3);
  v8 = LsaHeap;
  if ( LsaHeap )
  {
    *(_QWORD *)(LsaHeap + 8) = LsaHeap;
    *(_QWORD *)LsaHeap = LsaHeap;
    *(_QWORD *)(LsaHeap + 60) = 0;
    *(_DWORD *)(LsaHeap + 56) = 0;
    v10 = -1;
    do
      ++v10;
    while ( Src[v10] );
    v11 = 2 * v10;
    *(_WORD *)(v8 + 32) = v11;
    v11 += 2;
    *(_WORD *)(v8 + 34) = v11;
    v12 = (void *)LsapAllocateLsaHeap(v11, v6, v7);
    *(_QWORD *)(v8 + 40) = v12;
    if ( v12 )
    {
      v9 = 0;
      memcpy_0(v12, Src, *(unsigned __int16 *)(v8 + 34));
      *(_QWORD *)(v8 + 24) = v8 + 16;
      *(_QWORD *)(v8 + 16) = v8 + 16;
    }
    else
    {
      v9 = 8;
      LsapFreeLsaHeap(v8);
      v8 = 0;
    }
  }
  else
  {
    v9 = 8;
  }
  *a2 = v8;
  return v9;
}

```

## disassembly

```asm
0x140003584  push    rbx
0x140003586  push    rbp
0x140003587  push    rsi
0x140003588  push    rdi
0x140003589  push    r14
0x14000358b  sub     rsp, 20h
0x14000358f  mov     rsi, rcx
0x140003592  mov     r14, rdx
0x140003595  mov     ecx, 58h ; 'X'
0x14000359a  call    LsapAllocateLsaHeap
0x14000359f  xor     ebp, ebp
0x1400035a1  mov     rbx, rax
0x1400035a4  test    rax, rax
0x1400035a7  jnz     short loc_1400035AE
0x1400035a9  lea     edi, [rax+8]
0x1400035ac  jmp     short loc_140003616
0x1400035ae  mov     [rax+8], rbx
0x1400035b2  mov     [rax], rbx
0x1400035b5  mov     [rax+3Ch], rbp
0x1400035b9  mov     [rax+38h], ebp
0x1400035bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400035c0  inc     rax
0x1400035c3  cmp     [rsi+rax*2], bp
0x1400035c7  jnz     short loc_1400035C0
0x1400035c9  add     ax, ax
0x1400035cc  mov     [rbx+20h], ax
0x1400035d0  add     ax, 2
0x1400035d4  movzx   ecx, ax
0x1400035d7  mov     [rbx+22h], cx
0x1400035db  call    LsapAllocateLsaHeap
0x1400035e0  mov     [rbx+28h], rax
0x1400035e4  test    rax, rax
0x1400035e7  jnz     short loc_1400035F9
0x1400035e9  mov     rcx, rbx
0x1400035ec  lea     edi, [rax+8]
0x1400035ef  call    LsapFreeLsaHeap
0x1400035f4  mov     rbx, rbp
0x1400035f7  jmp     short loc_140003616
0x1400035f9  movzx   r8d, word ptr [rbx+22h]; Size
0x1400035fe  mov     rdx, rsi; Src
0x140003601  mov     rcx, rax; void *
0x140003604  mov     edi, ebp
0x140003606  call    memcpy_0
0x14000360b  lea     rcx, [rbx+10h]
0x14000360f  mov     [rcx+8], rcx
0x140003613  mov     [rcx], rcx
0x140003616  mov     [r14], rbx
0x140003619  mov     eax, edi
0x14000361b  add     rsp, 20h
0x14000361f  pop     r14
0x140003621  pop     rdi
0x140003622  pop     rsi
0x140003623  pop     rbp
0x140003624  pop     rbx
0x140003625  retn
```
