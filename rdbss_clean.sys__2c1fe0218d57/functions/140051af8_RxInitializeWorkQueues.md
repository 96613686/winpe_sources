# RxInitializeWorkQueues

- ea: `0x140051af8`
- end: `0x140051c1d`
- name: `RxInitializeWorkQueues`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14008321c`

## callees

- `0x1400240e8`
- `0x140051af8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140051b3e`
- `ntoskrnl!ExAllocatePool2` at `0x140051b3e`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140051b02`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140051b02`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140051b94`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140051b94`

## pseudocode

```c
void RxInitializeWorkQueues()
{
  USHORT HighestNodeNumber; // ax
  __int64 v1; // rax
  unsigned int i; // ebx

  HighestNodeNumber = KeQueryHighestNodeNumber();
  P = 0;
  v1 = (unsigned int)HighestNodeNumber + 1;
  RxGlobalDispatcher = v1;
  if ( (unsigned int)v1 <= 1 || (P = (PVOID)ExAllocatePool2(74, 384 * v1, 1901557842)) == 0 )
  {
    RxGlobalDispatcher = 1;
    P = &RxpNodes;
  }
  ExInitializeNPagedLookasideList(&RxWorkItemLookasideList, 0, 0, 0x200u, 0x40u, 0x71577852u, 0);
  for ( i = 0; i < RxGlobalDispatcher; ++i )
  {
    RxpInitializeWorkQueue(i, 0, 8);
    RxpInitializeWorkQueue(i, 1, 8);
    RxpInitializeWorkQueue(i, 2, 8);
    RxpInitializeWorkQueue(i, 3, 512);
    RxpInitializeWorkQueue(i, 4, 8);
    RxpInitializeWorkQueue(i, 5, 8);
  }
}

```

## disassembly

```asm
0x140051af8  mov     [rsp+arg_0], rbx
0x140051afd  push    rsi
0x140051afe  sub     rsp, 40h
0x140051b02  call    cs:__imp_KeQueryHighestNodeNumber
0x140051b09  nop     dword ptr [rax+rax+00h]
0x140051b0e  mov     cs:P, 0
0x140051b19  mov     ebx, 71577852h
0x140051b1e  movzx   eax, ax
0x140051b21  inc     eax
0x140051b23  mov     cs:RxGlobalDispatcher, eax
0x140051b29  cmp     eax, 1
0x140051b2c  jbe     short loc_140051B56
0x140051b2e  lea     rdx, [rax+rax*2]
0x140051b32  mov     r8d, ebx
0x140051b35  shl     rdx, 7
0x140051b39  mov     ecx, 4Ah ; 'J'
0x140051b3e  call    cs:__imp_ExAllocatePool2
0x140051b45  nop     dword ptr [rax+rax+00h]
0x140051b4a  mov     cs:P, rax
0x140051b51  test    rax, rax
0x140051b54  jnz     short loc_140051B6E
0x140051b56  lea     rax, RxpNodes
0x140051b5d  mov     cs:RxGlobalDispatcher, 1
0x140051b67  mov     cs:P, rax
0x140051b6e  xor     eax, eax
0x140051b70  lea     rcx, RxWorkItemLookasideList; Lookaside
0x140051b77  mov     [rsp+48h+Depth], ax; Depth
0x140051b7c  mov     r9d, 200h; Flags
0x140051b82  mov     [rsp+48h+Tag], ebx; Tag
0x140051b86  xor     r8d, r8d; Free
0x140051b89  xor     edx, edx; Allocate
0x140051b8b  mov     [rsp+48h+Size], 40h ; '@'; Size
0x140051b94  call    cs:__imp_ExInitializeNPagedLookasideList
0x140051b9b  nop     dword ptr [rax+rax+00h]
0x140051ba0  xor     ebx, ebx
0x140051ba2  cmp     cs:RxGlobalDispatcher, ebx
0x140051ba8  jbe     short loc_140051C11
0x140051baa  lea     esi, [rbx+8]
0x140051bad  mov     r8d, esi
0x140051bb0  xor     edx, edx
0x140051bb2  mov     ecx, ebx
0x140051bb4  call    RxpInitializeWorkQueue
0x140051bb9  mov     r8d, esi
0x140051bbc  mov     edx, 1
0x140051bc1  mov     ecx, ebx
0x140051bc3  call    RxpInitializeWorkQueue
0x140051bc8  mov     r8d, esi
0x140051bcb  mov     edx, 2
0x140051bd0  mov     ecx, ebx
0x140051bd2  call    RxpInitializeWorkQueue
0x140051bd7  mov     edx, 3
0x140051bdc  mov     r8d, 200h
0x140051be2  mov     ecx, ebx
0x140051be4  call    RxpInitializeWorkQueue
0x140051be9  mov     r8d, esi
0x140051bec  mov     edx, 4
0x140051bf1  mov     ecx, ebx
0x140051bf3  call    RxpInitializeWorkQueue
0x140051bf8  mov     r8d, esi
0x140051bfb  mov     edx, 5
0x140051c00  mov     ecx, ebx
0x140051c02  call    RxpInitializeWorkQueue
0x140051c07  inc     ebx
0x140051c09  cmp     ebx, cs:RxGlobalDispatcher
0x140051c0f  jb      short loc_140051BAD
0x140051c11  mov     rbx, [rsp+48h+arg_0]
0x140051c16  add     rsp, 40h
0x140051c1a  pop     rsi
0x140051c1b  retn
```
