# WanInitECP

- ea: `0x14003aad0`
- end: `0x14003abb5`
- name: `WanInitECP`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140039008`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ab0c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ab57`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003aba2`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ab0c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ab57`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003aba2`
- `NDIS!NdisGetVersion` at `0x14003aad6`
- `NDIS!NdisGetVersion` at `0x14003ab25`
- `NDIS!NdisGetVersion` at `0x14003ab70`
- `NDIS!NdisGetVersion` at `0x14003aad6`
- `NDIS!NdisGetVersion` at `0x14003ab25`
- `NDIS!NdisGetVersion` at `0x14003ab70`

## pseudocode

```c
void WanInitECP()
{
  SIZE_T Size; // rbx
  SIZE_T v1; // rbx

  NdisGetVersion();
  ExInitializeNPagedLookasideList(&EncryptCtxList, 0, 0, 0x200u, 0x18u, 0x566E6157u, 0);
  Size = 10LL * (unsigned int)glCachedKeyCount;
  NdisGetVersion();
  ExInitializeNPagedLookasideList(&CachedKeyList, 0, 0, 0x200u, Size, 0x414E6157u, 0);
  v1 = 18LL * (unsigned int)glCachedKeyCount;
  NdisGetVersion();
  ExInitializeNPagedLookasideList(&CachedKeyListLong, 0, 0, 0x200u, v1, 0x414E6157u, 0);
}

```

## disassembly

```asm
0x14003aad0  push    rbx
0x14003aad2  sub     rsp, 40h
0x14003aad6  call    cs:__imp_NdisGetVersion
0x14003aadd  nop     dword ptr [rax+rax+00h]
0x14003aae2  xor     eax, eax
0x14003aae4  lea     rcx, EncryptCtxList; Lookaside
0x14003aaeb  mov     [rsp+48h+Depth], ax; Depth
0x14003aaf0  mov     r9d, 200h; Flags
0x14003aaf6  mov     [rsp+48h+Tag], 566E6157h; Tag
0x14003aafe  xor     r8d, r8d; Free
0x14003ab01  xor     edx, edx; Allocate
0x14003ab03  mov     [rsp+48h+Size], 18h; Size
0x14003ab0c  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003ab13  nop     dword ptr [rax+rax+00h]
0x14003ab18  mov     eax, cs:glCachedKeyCount
0x14003ab1e  lea     rbx, [rax+rax*4]
0x14003ab22  add     rbx, rbx
0x14003ab25  call    cs:__imp_NdisGetVersion
0x14003ab2c  nop     dword ptr [rax+rax+00h]
0x14003ab31  xor     eax, eax
0x14003ab33  lea     rcx, CachedKeyList; Lookaside
0x14003ab3a  mov     [rsp+48h+Depth], ax; Depth
0x14003ab3f  mov     r9d, 200h; Flags
0x14003ab45  mov     [rsp+48h+Tag], 414E6157h; Tag
0x14003ab4d  xor     r8d, r8d; Free
0x14003ab50  xor     edx, edx; Allocate
0x14003ab52  mov     [rsp+48h+Size], rbx; Size
0x14003ab57  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003ab5e  nop     dword ptr [rax+rax+00h]
0x14003ab63  mov     eax, cs:glCachedKeyCount
0x14003ab69  lea     rbx, [rax+rax*8]
0x14003ab6d  add     rbx, rbx
0x14003ab70  call    cs:__imp_NdisGetVersion
0x14003ab77  nop     dword ptr [rax+rax+00h]
0x14003ab7c  xor     eax, eax
0x14003ab7e  lea     rcx, CachedKeyListLong; Lookaside
0x14003ab85  mov     [rsp+48h+Depth], ax; Depth
0x14003ab8a  mov     r9d, 200h; Flags
0x14003ab90  mov     [rsp+48h+Tag], 414E6157h; Tag
0x14003ab98  xor     r8d, r8d; Free
0x14003ab9b  xor     edx, edx; Allocate
0x14003ab9d  mov     [rsp+48h+Size], rbx; Size
0x14003aba2  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003aba9  nop     dword ptr [rax+rax+00h]
0x14003abae  add     rsp, 40h
0x14003abb2  pop     rbx
0x14003abb3  retn
```
