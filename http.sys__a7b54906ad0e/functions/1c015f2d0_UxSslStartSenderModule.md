# UxSslStartSenderModule

- ea: `0x1c015f2d0`
- end: `0x1c015f449`
- name: `UxSslStartSenderModule`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1c015f2d0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1c015f2f9`
- `ntoskrnl!MmSizeOfMdl` at `0x1c015f38e`
- `ntoskrnl!MmSizeOfMdl` at `0x1c015f2f9`
- `ntoskrnl!MmSizeOfMdl` at `0x1c015f38e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c015f37c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c015f411`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c015f37c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c015f411`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c015f31c`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c015f3b1`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c015f31c`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c015f3b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c015fc56`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c015fc56`

## pseudocode

```c
__int64 UxSslStartSenderModule()
{
  unsigned int v0; // edi
  struct _MDL *PoolWithTagPriority; // rax
  unsigned int v2; // ebx
  struct _MDL *v3; // rsi
  unsigned __int64 v4; // rcx
  unsigned int v5; // ebp
  struct _MDL *v6; // rax
  struct _MDL *v7; // rdi
  unsigned __int64 v8; // rdx

  v0 = (MmSizeOfMdl((PVOID)0xFFF, 2u) + 7) & 0xFFFFFFF8;
  PoolWithTagPriority = (struct _MDL *)ExAllocatePoolWithTagPriority(
                                         (POOL_TYPE)512,
                                         v0 + 2,
                                         0x43537855u,
                                         LowPoolPriority);
  v2 = 0;
  v3 = PoolWithTagPriority;
  if ( PoolWithTagPriority )
  {
    v4 = (unsigned __int64)PoolWithTagPriority + v0;
    *(_WORD *)v4 = 1;
    PoolWithTagPriority->Next = 0;
    PoolWithTagPriority->MdlFlags = 0;
    PoolWithTagPriority->ByteCount = 2;
    PoolWithTagPriority->Size = 8 * ((((v4 & 0xFFF) + 4097) >> 12) + 6);
    PoolWithTagPriority->ByteOffset = v4 & 0xFFF;
    PoolWithTagPriority->StartVa = (PVOID)(v4 & 0xFFFFFFFFFFFFF000uLL);
    MmBuildMdlForNonPagedPool(PoolWithTagPriority);
    v5 = (MmSizeOfMdl((PVOID)0xFFF, 4u) + 7) & 0xFFFFFFF8;
    v6 = (struct _MDL *)ExAllocatePoolWithTagPriority((POOL_TYPE)512, v5 + 4, 0x48537855u, LowPoolPriority);
    v7 = v6;
    if ( v6 )
    {
      v8 = (unsigned __int64)v6 + v5;
      *(_DWORD *)v8 = 0;
      v6->Next = 0;
      v6->StartVa = (PVOID)(v8 & 0xFFFFFFFFFFFFF000uLL);
      v6->MdlFlags = 0;
      v6->ByteOffset = v8 & 0xFFF;
      v6->Size = 8 * ((((v8 & 0xFFF) + 4099) >> 12) + 6);
      v6->ByteCount = 4;
      MmBuildMdlForNonPagedPool(v6);
      UxSslCloseNotifyMdl = v3;
      UxSslHelloRequestMdl = v7;
    }
    else
    {
      v2 = -1073741670;
      ExFreePoolWithTag(v3, 0);
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v2;
}

```

## disassembly

```asm
0x1c015f2d0  mov     rax, rsp
0x1c015f2d3  mov     [rax+8], rbx
0x1c015f2d7  mov     [rax+10h], rbp
0x1c015f2db  mov     [rax+18h], rsi
0x1c015f2df  mov     [rax+20h], rdi
0x1c015f2e3  push    r14
0x1c015f2e5  sub     rsp, 20h
0x1c015f2e9  mov     ebp, 2
0x1c015f2ee  mov     r14d, 0FFFh
0x1c015f2f4  mov     edx, ebp; Length
0x1c015f2f6  mov     ecx, r14d; Base
0x1c015f2f9  call    cs:__imp_MmSizeOfMdl
0x1c015f300  nop     dword ptr [rax+rax+00h]
0x1c015f305  xor     r9d, r9d; Priority
0x1c015f308  mov     ecx, 200h; PoolType
0x1c015f30d  mov     r8d, 43537855h; Tag
0x1c015f313  lea     edi, [rax+7]
0x1c015f316  and     edi, 0FFFFFFF8h
0x1c015f319  lea     edx, [rdi+2]; NumberOfBytes
0x1c015f31c  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c015f323  nop     dword ptr [rax+rax+00h]
0x1c015f328  xor     ebx, ebx
0x1c015f32a  mov     rsi, rax
0x1c015f32d  test    rax, rax
0x1c015f330  jz      loc_1C015FC42
0x1c015f336  mov     ecx, edi
0x1c015f338  add     rcx, rax
0x1c015f33b  mov     word ptr [rcx], 1
0x1c015f340  mov     [rax], rbx
0x1c015f343  mov     rax, rcx
0x1c015f346  and     rax, r14
0x1c015f349  mov     [rsi+0Ah], bx
0x1c015f34d  add     rax, 1001h
0x1c015f353  mov     [rsi+28h], ebp
0x1c015f356  shr     rax, 0Ch
0x1c015f35a  add     ax, 6
0x1c015f35e  shl     ax, 3
0x1c015f362  mov     [rsi+8], ax
0x1c015f366  mov     rax, rcx
0x1c015f369  and     ecx, r14d
0x1c015f36c  and     rax, 0FFFFFFFFFFFFF000h
0x1c015f372  mov     [rsi+2Ch], ecx
0x1c015f375  mov     rcx, rsi; MemoryDescriptorList
0x1c015f378  mov     [rsi+20h], rax
0x1c015f37c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1c015f383  nop     dword ptr [rax+rax+00h]
0x1c015f388  lea     edx, [rbp+2]; Length
0x1c015f38b  mov     ecx, r14d; Base
0x1c015f38e  call    cs:__imp_MmSizeOfMdl
0x1c015f395  nop     dword ptr [rax+rax+00h]
0x1c015f39a  xor     r9d, r9d; Priority
0x1c015f39d  mov     ecx, 200h; PoolType
0x1c015f3a2  mov     r8d, 48537855h; Tag
0x1c015f3a8  lea     ebp, [rax+7]
0x1c015f3ab  and     ebp, 0FFFFFFF8h
0x1c015f3ae  lea     edx, [rbp+4]; NumberOfBytes
0x1c015f3b1  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c015f3b8  nop     dword ptr [rax+rax+00h]
0x1c015f3bd  mov     rdi, rax
0x1c015f3c0  test    rax, rax
0x1c015f3c3  jz      loc_1C015FC4C
0x1c015f3c9  mov     edx, ebp
0x1c015f3cb  add     rdx, rax
0x1c015f3ce  mov     rcx, rdx
0x1c015f3d1  and     rcx, 0FFFFFFFFFFFFF000h
0x1c015f3d8  mov     [rdx], ebx
0x1c015f3da  mov     [rax], rbx
0x1c015f3dd  mov     rax, rdx
0x1c015f3e0  and     rax, r14
0x1c015f3e3  mov     [rdi+20h], rcx
0x1c015f3e7  add     rax, 1003h
0x1c015f3ed  mov     [rdi+0Ah], bx
0x1c015f3f1  shr     rax, 0Ch
0x1c015f3f5  and     edx, r14d
0x1c015f3f8  add     ax, 6
0x1c015f3fc  mov     [rdi+2Ch], edx
0x1c015f3ff  shl     ax, 3
0x1c015f403  mov     rcx, rdi; MemoryDescriptorList
0x1c015f406  mov     [rdi+8], ax
0x1c015f40a  mov     dword ptr [rdi+28h], 4
0x1c015f411  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1c015f418  nop     dword ptr [rax+rax+00h]
0x1c015f41d  mov     cs:UxSslCloseNotifyMdl, rsi
0x1c015f424  mov     cs:UxSslHelloRequestMdl, rdi
0x1c015f42b  mov     rbp, [rsp+28h+arg_8]
0x1c015f430  mov     eax, ebx
0x1c015f432  mov     rbx, [rsp+28h+arg_0]
0x1c015f437  mov     rsi, [rsp+28h+arg_10]
0x1c015f43c  mov     rdi, [rsp+28h+arg_18]
0x1c015f441  add     rsp, 20h
0x1c015f445  pop     r14
0x1c015f447  retn
0x1c015fc42  mov     ebx, 0C000009Ah
0x1c015fc47  jmp     loc_1C015F42B
0x1c015fc4c  xor     edx, edx; Tag
0x1c015fc4e  mov     rcx, rsi; P
0x1c015fc51  mov     ebx, 0C000009Ah
0x1c015fc56  call    cs:__imp_ExFreePoolWithTag
0x1c015fc5d  nop     dword ptr [rax+rax+00h]
0x1c015fc62  nop
0x1c015fc63  jmp     loc_1C015F42B
```
