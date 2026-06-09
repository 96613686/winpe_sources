# PcpTcIndicateInterfaceChange

- ea: `0x140002500`
- end: `0x14000258d`
- name: `PcpTcIndicateInterfaceChange`
- size: `141`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400020f0`
- `0x140002c1c`
- `0x14000bc08`
- `0x140010c70`

## callees

- `0x140002500`
- `0x140002594`
- `0x1400026c4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002577`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002577`
- `ntoskrnl!ExAllocatePool2` at `0x140002537`
- `ntoskrnl!ExAllocatePool2` at `0x140002537`

## pseudocode

```c
void __fastcall PcpTcIndicateInterfaceChange(__int64 a1, int a2)
{
  unsigned int v4; // esi
  _DWORD *Pool2; // rax
  void *v6; // rbx
  int v7; // [rsp+60h] [rbp+18h] BYREF

  v7 = 0;
  PcpCollectNetworkAddressList(a1, &v7, 0);
  v4 = v7 + 8;
  Pool2 = (_DWORD *)ExAllocatePool2(64, (unsigned int)(v7 + 8), 1768781648);
  v6 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = 0;
    PcpCollectNetworkAddressList(a1, &v7, Pool2 + 2);
    PcpTcNotify(a1, a2, v6, v4);
    ExFreePoolWithTag(v6, 0);
  }
}

```

## disassembly

```asm
0x140002500  push    rbx
0x140002502  push    rbp
0x140002503  push    rsi
0x140002504  push    rdi
0x140002505  sub     rsp, 28h
0x140002509  mov     ebp, edx
0x14000250b  mov     [rsp+48h+arg_10], 0
0x140002513  lea     rdx, [rsp+48h+arg_10]
0x140002518  xor     r8d, r8d
0x14000251b  mov     rdi, rcx
0x14000251e  call    PcpCollectNetworkAddressList
0x140002523  mov     esi, [rsp+48h+arg_10]
0x140002527  mov     ecx, 40h ; '@'
0x14000252c  add     esi, 8
0x14000252f  mov     r8d, 696D7750h
0x140002535  mov     edx, esi
0x140002537  call    cs:__imp_ExAllocatePool2
0x14000253e  nop     dword ptr [rax+rax+00h]
0x140002543  mov     rbx, rax
0x140002546  test    rax, rax
0x140002549  jz      short loc_140002583
0x14000254b  lea     r8, [rax+8]
0x14000254f  mov     dword ptr [rax], 0
0x140002555  lea     rdx, [rsp+48h+arg_10]
0x14000255a  mov     rcx, rdi
0x14000255d  call    PcpCollectNetworkAddressList
0x140002562  mov     r9d, esi
0x140002565  mov     r8, rbx
0x140002568  mov     edx, ebp
0x14000256a  mov     rcx, rdi
0x14000256d  call    PcpTcNotify
0x140002572  xor     edx, edx; Tag
0x140002574  mov     rcx, rbx; P
0x140002577  call    cs:__imp_ExFreePoolWithTag
0x14000257e  nop     dword ptr [rax+rax+00h]
0x140002583  add     rsp, 28h
0x140002587  pop     rdi
0x140002588  pop     rsi
0x140002589  pop     rbp
0x14000258a  pop     rbx
0x14000258b  retn
```
