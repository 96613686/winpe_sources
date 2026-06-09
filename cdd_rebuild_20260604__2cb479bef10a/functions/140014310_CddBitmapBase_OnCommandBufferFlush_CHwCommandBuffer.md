# CddBitmapBase::OnCommandBufferFlush(CHwCommandBuffer *)

- ea: `0x140014310`
- end: `0x140014330`
- name: `?OnCommandBufferFlush@CddBitmapBase@@UEAAXPEAVCHwCommandBuffer@@@Z`
- size: `32`
- prototype: `void __fastcall(CddBitmapBase *__hidden this, struct CHwCommandBuffer *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void __fastcall CddBitmapBase::OnCommandBufferFlush(CddBitmapBase *this, struct CHwCommandBuffer *a2)
{
  __int64 v2; // r8

  v2 = *((unsigned int *)a2 + 2);
  *((_BYTE *)this + v2 + 44) = 0;
  *((_QWORD *)this + 2 * v2 + 12) = 0;
  *((_QWORD *)this + 2 * v2 + 13) = 0;
}

```

## disassembly

```asm
0x140014310  mov     r8d, [rdx+8]
0x140014314  xor     edx, edx
0x140014316  mov     byte ptr [r8+rcx+2Ch], 0
0x14001431c  lea     rax, [r8+6]
0x140014320  add     rax, rax
0x140014323  add     r8, r8
0x140014326  mov     [rcx+rax*8], rdx
0x14001432a  mov     [rcx+r8*8+68h], rdx
0x14001432f  retn
```
