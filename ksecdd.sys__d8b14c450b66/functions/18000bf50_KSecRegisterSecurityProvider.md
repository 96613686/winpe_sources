# KSecRegisterSecurityProvider

- ea: `0x18000bf50`
- end: `0x18000c159`
- name: `KSecRegisterSecurityProvider`
- size: `521`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001a98`
- `0x180001c00`
- `0x180001cf0`
- `0x180006bf4`
- `0x18000bf50`
- `0x180010920`
- `0x180010980`
- `0x180020b14`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18000bf7a`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18000bf7a`
- `ntoskrnl!ExAcquireFastMutex` at `0x18000bfb2`
- `ntoskrnl!ExAcquireFastMutex` at `0x18000bfb2`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000c0b7`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000c0f0`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000c12e`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000c0b7`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000c0f0`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000c12e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c03a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c03a`
- `ntoskrnl!ExAllocatePool2` at `0x18000bffc`
- `ntoskrnl!ExAllocatePool2` at `0x18000bffc`

## pseudocode

```c
__int64 __fastcall KSecRegisterSecurityProvider(
        unsigned __int16 *a1,
        void (__fastcall **a2)(__int64 (__fastcall **)(unsigned int)))
{
  int Package; // edi
  __int64 v5; // rbx
  __int64 v6; // rcx
  void *Pool2; // rax
  KDEFERRED_ROUTINE *v8; // rbx
  PKDEFERRED_ROUTINE DeferredRoutine; // rdi
  __int64 v10; // rcx
  unsigned int v11; // edx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  unsigned __int64 v16; // [rsp+60h] [rbp+18h] BYREF
  __int64 v17; // [rsp+68h] [rbp+20h] BYREF

  v16 = 0;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v17);
  if ( (unsigned __int8)PsIsCurrentThreadInServerSilo() )
  {
    Package = -2146893054;
  }
  else
  {
    v5 = v17;
    if ( v17 )
    {
      ExAcquireFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      if ( *(_QWORD *)(v5 + 456) )
      {
        if ( (LocateClient() & 0xC0000000) != 0xC0000000
          || (Package = CreateClient(0, 0, v12, v13), (Package & 0xC0000000) != 0xC0000000) )
        {
          if ( (unsigned __int64)*a1 + 2 > 0x120 )
          {
            ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
            Package = -2146893056;
            goto LABEL_24;
          }
          Package = SecpFindPackage(a1, &v16);
          if ( Package >= 0 )
          {
            if ( v16 >= *(unsigned int *)(v5 + 464) )
            {
              ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
              Package = -2146893051;
              goto LABEL_24;
            }
            v14 = *(_QWORD *)(v5 + 456);
            if ( *(_QWORD *)(v14 + 8 * v16) )
            {
              Package = -2146893051;
            }
            else
            {
              *(_QWORD *)(v14 + 8 * v16) = a2;
              (*a2)(&KspKernelFunctions);
            }
          }
        }
      }
      else
      {
        v6 = KsecDeferredPackageCount + 1;
        if ( (unsigned int)v6 >= KsecDeferredPackageCount
          && (unsigned int)v6 < 0x6666666
          && (Pool2 = (void *)ExAllocatePool2(256, 40 * v6, 1667593035), (v8 = (KDEFERRED_ROUTINE *)Pool2) != 0) )
        {
          DeferredRoutine = WPP_MAIN_CB.Dpc.DeferredRoutine;
          if ( WPP_MAIN_CB.Dpc.DeferredRoutine )
          {
            memmove(Pool2, WPP_MAIN_CB.Dpc.DeferredRoutine, 40LL * KsecDeferredPackageCount);
            ExFreePoolWithTag(DeferredRoutine, 0);
          }
          WPP_MAIN_CB.Dpc.DeferredRoutine = v8;
          v10 = 5LL * KsecDeferredPackageCount;
          v11 = KsecDeferredPackageCount + 1;
          *((_QWORD *)v8 + v10 + 1) = a1;
          Package = 0;
          *((_QWORD *)v8 + v10) = a2;
          KsecDeferredPackageCount = v11;
        }
        else
        {
          Package = -2146893056;
        }
      }
      ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      goto LABEL_24;
    }
    Package = -1073741058;
  }
LABEL_24:
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v17);
  return (unsigned int)Package;
}

```

## disassembly

```asm
0x18000bf50  mov     [rsp+arg_0], rbx
0x18000bf55  push    rsi
0x18000bf56  push    rdi
0x18000bf57  push    r12
0x18000bf59  push    r14
0x18000bf5b  push    r15
0x18000bf5d  sub     rsp, 20h
0x18000bf61  mov     rsi, rcx
0x18000bf64  mov     [rsp+48h+arg_10], 0
0x18000bf6d  lea     rcx, [rsp+48h+arg_18]; this
0x18000bf72  mov     r14, rdx
0x18000bf75  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x18000bf7a  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x18000bf81  nop     dword ptr [rax+rax+00h]
0x18000bf86  test    al, al
0x18000bf88  jz      short loc_18000BF94
0x18000bf8a  mov     edi, 80090302h
0x18000bf8f  jmp     loc_18000C13A
0x18000bf94  mov     rbx, [rsp+48h+arg_18]
0x18000bf99  test    rbx, rbx
0x18000bf9c  jnz     short loc_18000BFA8
0x18000bf9e  mov     edi, 0C00002FEh
0x18000bfa3  jmp     loc_18000C13A
0x18000bfa8  lea     r15, WPP_MAIN_CB.Queue+18h
0x18000bfaf  mov     rcx, r15; FastMutex
0x18000bfb2  call    cs:__imp_ExAcquireFastMutex
0x18000bfb9  nop     dword ptr [rax+rax+00h]
0x18000bfbe  cmp     qword ptr [rbx+1C8h], 0
0x18000bfc6  jnz     loc_18000C079
0x18000bfcc  mov     eax, cs:?KsecDeferredPackageCount@@3KA; ulong KsecDeferredPackageCount
0x18000bfd2  lea     ecx, [rax+1]
0x18000bfd5  cmp     ecx, eax
0x18000bfd7  jb      loc_18000C06F
0x18000bfdd  cmp     ecx, 6666666h
0x18000bfe3  jnb     loc_18000C06F
0x18000bfe9  lea     rdx, [rcx+rcx*4]
0x18000bfed  mov     r8d, 6365734Bh
0x18000bff3  shl     rdx, 3
0x18000bff7  mov     ecx, 100h
0x18000bffc  call    cs:__imp_ExAllocatePool2
0x18000c003  nop     dword ptr [rax+rax+00h]
0x18000c008  mov     rbx, rax
0x18000c00b  test    rax, rax
0x18000c00e  jz      short loc_18000C06F
0x18000c010  mov     rdi, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x18000c017  test    rdi, rdi
0x18000c01a  jz      short loc_18000C046
0x18000c01c  mov     edx, cs:?KsecDeferredPackageCount@@3KA; ulong KsecDeferredPackageCount
0x18000c022  mov     rcx, rax; void *
0x18000c025  lea     r8, [rdx+rdx*4]
0x18000c029  mov     rdx, rdi; Src
0x18000c02c  shl     r8, 3; Size
0x18000c030  call    memmove
0x18000c035  xor     edx, edx; Tag
0x18000c037  mov     rcx, rdi; P
0x18000c03a  call    cs:__imp_ExFreePoolWithTag
0x18000c041  nop     dword ptr [rax+rax+00h]
0x18000c046  mov     edx, cs:?KsecDeferredPackageCount@@3KA; ulong KsecDeferredPackageCount
0x18000c04c  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rbx
0x18000c053  lea     rcx, [rdx+rdx*4]
0x18000c057  inc     edx
0x18000c059  mov     [rbx+rcx*8+8], rsi
0x18000c05e  xor     edi, edi
0x18000c060  mov     [rbx+rcx*8], r14
0x18000c064  mov     cs:?KsecDeferredPackageCount@@3KA, edx; ulong KsecDeferredPackageCount
0x18000c06a  jmp     loc_18000C12B
0x18000c06f  mov     edi, 80090300h
0x18000c074  jmp     loc_18000C12B
0x18000c079  call    LocateClient
0x18000c07e  mov     r12d, 0C0000000h
0x18000c084  and     eax, r12d
0x18000c087  cmp     eax, r12d
0x18000c08a  jnz     short loc_18000C0A5
0x18000c08c  xor     edx, edx
0x18000c08e  xor     ecx, ecx
0x18000c090  call    CreateClient
0x18000c095  mov     edx, eax
0x18000c097  mov     edi, eax
0x18000c099  and     edx, r12d
0x18000c09c  cmp     edx, r12d
0x18000c09f  jz      loc_18000C12B
0x18000c0a5  movzx   eax, word ptr [rsi]
0x18000c0a8  add     rax, 2
0x18000c0ac  cmp     rax, 120h
0x18000c0b2  jbe     short loc_18000C0CA
0x18000c0b4  mov     rcx, r15; FastMutex
0x18000c0b7  call    cs:__imp_ExReleaseFastMutex
0x18000c0be  nop     dword ptr [rax+rax+00h]
0x18000c0c3  mov     edi, 80090300h
0x18000c0c8  jmp     short loc_18000C13A
0x18000c0ca  lea     rdx, [rsp+48h+arg_10]
0x18000c0cf  mov     rcx, rsi
0x18000c0d2  call    SecpFindPackage
0x18000c0d7  mov     edi, eax
0x18000c0d9  test    eax, eax
0x18000c0db  js      short loc_18000C12B
0x18000c0dd  mov     eax, [rbx+1D0h]
0x18000c0e3  mov     rcx, [rsp+48h+arg_10]
0x18000c0e8  cmp     rcx, rax
0x18000c0eb  jb      short loc_18000C103
0x18000c0ed  mov     rcx, r15; FastMutex
0x18000c0f0  call    cs:__imp_ExReleaseFastMutex
0x18000c0f7  nop     dword ptr [rax+rax+00h]
0x18000c0fc  mov     edi, 80090305h
0x18000c101  jmp     short loc_18000C13A
0x18000c103  mov     rax, [rbx+1C8h]
0x18000c10a  cmp     qword ptr [rax+rcx*8], 0
0x18000c10f  jnz     short loc_18000C126
0x18000c111  mov     [rax+rcx*8], r14
0x18000c115  lea     rcx, KspKernelFunctions
0x18000c11c  mov     rax, [r14]
0x18000c11f  call    _guard_dispatch_icall
0x18000c124  jmp     short loc_18000C12B
0x18000c126  mov     edi, 80090305h
0x18000c12b  mov     rcx, r15; FastMutex
0x18000c12e  call    cs:__imp_ExReleaseFastMutex
0x18000c135  nop     dword ptr [rax+rax+00h]
0x18000c13a  lea     rcx, [rsp+48h+arg_18]; this
0x18000c13f  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000c144  mov     rbx, [rsp+48h+arg_0]
0x18000c149  mov     eax, edi
0x18000c14b  add     rsp, 20h
0x18000c14f  pop     r15
0x18000c151  pop     r14
0x18000c153  pop     r12
0x18000c155  pop     rdi
0x18000c156  pop     rsi
0x18000c157  retn
```
