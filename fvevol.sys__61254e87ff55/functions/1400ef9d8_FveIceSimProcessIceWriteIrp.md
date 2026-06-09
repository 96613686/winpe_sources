# FveIceSimProcessIceWriteIrp

- ea: `0x1400ef9d8`
- end: `0x1400efc60`
- name: `FveIceSimProcessIceWriteIrp`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400ef498`

## callees

- `0x140008348`
- `0x140008cd0`
- `0x140022d40`
- `0x140023040`
- `0x1400ef9d8`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400efadb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400efadb`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400efc02`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400efc02`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400efb48`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400efb48`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400efbe6`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400efbe6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400efb1f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400efb1f`
- `ntoskrnl!KeBugCheckEx` at `0x1400efbc1`
- `ntoskrnl!KeBugCheckEx` at `0x1400efc42`
- `ntoskrnl!KeBugCheckEx` at `0x1400efbc1`
- `ntoskrnl!KeBugCheckEx` at `0x1400efc42`

## pseudocode

```c
__int64 __fastcall FveIceSimProcessIceWriteIrp(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  size_t v5; // rbp
  __int64 v6; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r9
  unsigned __int64 v13; // rdx
  __int64 v14; // r8
  __int16 v15; // bx
  __int64 v16; // rcx
  PVOID v17; // rax
  char v18; // bl
  int v19; // eax
  __int64 v20; // rcx
  __int64 result; // rax
  int v22[64]; // [rsp+40h] [rbp-138h] BYREF

  v5 = a4;
  v6 = *(_QWORD *)(a1 + 4768);
  if ( *(_QWORD *)(v6 + 104) != a2 || *(_QWORD *)(v6 + 112) != *(_QWORD *)(a2 + 8) || a4 > 0x100000 )
    goto LABEL_18;
  memset(v22, 0, sizeof(v22));
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v10, v9) )
    *(_QWORD *)&v22[16] = *(_QWORD *)(*(_QWORD *)(a1 + 4768) + 152LL);
  else
    *(_QWORD *)&v22[16] = *(_QWORD *)(a1 + 1008);
  v22[29] = *(_DWORD *)(a1 + 1308);
  v11 = *(_QWORD *)(a1 + 4768);
  v12 = *(_QWORD *)(v11 + 72);
  v13 = *(_QWORD *)(v11 + 80) & 0xFFFFFFFFFFFFF000uLL;
  v14 = *(_QWORD *)(v11 + 80) & 0xFFFLL;
  v15 = *(_WORD *)(v12 + 8);
  *(_QWORD *)v12 = 0;
  *(_WORD *)(v12 + 8) = 8 * (((v14 + v5 + 4095) >> 12) + 6);
  *(_WORD *)(v12 + 10) = 0;
  *(_QWORD *)(v12 + 32) = v13;
  *(_DWORD *)(v12 + 44) = v14;
  *(_DWORD *)(v12 + 40) = v5;
  MmBuildMdlForNonPagedPool(*(PMDL *)(*(_QWORD *)(a1 + 4768) + 72LL));
  *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 4768) + 72LL) + 8LL) = v15;
  v16 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v16 + 10) & 5) != 0 )
    v17 = *(PVOID *)(v16 + 24);
  else
    v17 = MmMapLockedPagesSpecifyCache((PMDL)v16, 0, MmCached, 0, 0, 0x40000010u);
  if ( v17 )
  {
    v18 = 0;
  }
  else
  {
    v17 = MmMapLockedPagesWithReservedMapping(
            *(PVOID *)(*(_QWORD *)(a1 + 4768) + 64LL),
            0x30455646u,
            *(PMDL *)(a2 + 8),
            MmCached);
    v18 = 1;
  }
  memmove(*(void **)(*(_QWORD *)(a1 + 4768) + 80LL), v17, v5);
  v19 = FveFilteredEncrypt(
          3,
          (int)v22,
          a3,
          -1,
          v5,
          *(PUCHAR *)(*(_QWORD *)(a1 + 4768) + 80LL),
          *(PUCHAR *)(*(_QWORD *)(a1 + 4768) + 80LL),
          0);
  if ( v19 < 0 )
    KeBugCheckEx(0x120u, 0xCu, 0, 0, v19);
  if ( v18 )
    MmUnmapReservedMapping(*(PVOID *)(*(_QWORD *)(a1 + 4768) + 64LL), 0x30455646u, *(PMDL *)(a2 + 8));
  MmMdlPageContentsState(*(_QWORD *)(*(_QWORD *)(a1 + 4768) + 72LL), 1);
  v20 = _InterlockedExchange64((volatile __int64 *)(a2 + 8), *(_QWORD *)(*(_QWORD *)(a1 + 4768) + 72LL));
  result = *(_QWORD *)(a1 + 4768);
  if ( *(_QWORD *)(result + 112) != v20 )
LABEL_18:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  return result;
}

```

## disassembly

```asm
0x1400ef9d8  push    rbx
0x1400ef9da  push    rbp
0x1400ef9db  push    rsi
0x1400ef9dc  push    rdi
0x1400ef9dd  push    r14
0x1400ef9df  push    r15
0x1400ef9e1  sub     rsp, 148h
0x1400ef9e8  mov     rdi, rcx
0x1400ef9eb  mov     ebp, r9d
0x1400ef9ee  mov     rcx, [rcx+12A0h]
0x1400ef9f5  mov     r14, r8
0x1400ef9f8  mov     rsi, rdx
0x1400ef9fb  cmp     [rcx+68h], rdx
0x1400ef9ff  jnz     loc_1400EFC2A
0x1400efa05  mov     rax, [rdx+8]
0x1400efa09  cmp     [rcx+70h], rax
0x1400efa0d  jnz     loc_1400EFC2A
0x1400efa13  cmp     ebp, 100000h
0x1400efa19  ja      loc_1400EFC2A
0x1400efa1f  xor     edx, edx; Val
0x1400efa21  lea     rcx, [rsp+178h+var_138]; void *
0x1400efa26  mov     r8d, 100h; Size
0x1400efa2c  call    memset
0x1400efa31  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400efa36  test    eax, eax
0x1400efa38  jz      short loc_1400EFA52
0x1400efa3a  mov     rax, [rdi+12A0h]
0x1400efa41  mov     rcx, [rax+98h]
0x1400efa48  mov     [rsp+178h+var_F8], rcx
0x1400efa50  jmp     short loc_1400EFA61
0x1400efa52  mov     rax, [rdi+3F0h]
0x1400efa59  mov     [rsp+178h+var_F8], rax
0x1400efa61  mov     eax, [rdi+51Ch]
0x1400efa67  lea     rcx, [rbp+0FFFh]
0x1400efa6e  mov     [rsp+178h+var_C4], eax
0x1400efa75  mov     r10d, 0FFFh
0x1400efa7b  mov     rax, [rdi+12A0h]
0x1400efa82  mov     rdx, [rax+50h]
0x1400efa86  mov     r9, [rax+48h]
0x1400efa8a  mov     r8d, edx
0x1400efa8d  mov     eax, r8d
0x1400efa90  and     rdx, 0FFFFFFFFFFFFF000h
0x1400efa97  and     rax, r10
0x1400efa9a  and     r8d, r10d
0x1400efa9d  add     rcx, rax
0x1400efaa0  xor     eax, eax
0x1400efaa2  movzx   ebx, word ptr [r9+8]
0x1400efaa7  shr     rcx, 0Ch
0x1400efaab  add     cx, 6
0x1400efaaf  mov     qword ptr [r9], 0
0x1400efab6  shl     cx, 3
0x1400efaba  mov     [r9+8], cx
0x1400efabf  mov     [r9+0Ah], ax
0x1400efac4  mov     [r9+20h], rdx
0x1400efac8  mov     [r9+2Ch], r8d
0x1400efacc  mov     [r9+28h], ebp
0x1400efad0  mov     rcx, [rdi+12A0h]
0x1400efad7  mov     rcx, [rcx+48h]; MemoryDescriptorList
0x1400efadb  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400efae2  nop     dword ptr [rax+rax+00h]
0x1400efae7  mov     rax, [rdi+12A0h]
0x1400efaee  mov     rcx, [rax+48h]
0x1400efaf2  mov     [rcx+8], bx
0x1400efaf6  mov     rcx, [rsi+8]; MemoryDescriptorList
0x1400efafa  test    byte ptr [rcx+0Ah], 5
0x1400efafe  jz      short loc_1400EFB06
0x1400efb00  mov     rax, [rcx+18h]
0x1400efb04  jmp     short loc_1400EFB2B
0x1400efb06  xor     r9d, r9d; RequestedAddress
0x1400efb09  mov     [rsp+178h+Priority], 40000010h; Priority
0x1400efb11  xor     edx, edx; AccessMode
0x1400efb13  mov     [rsp+178h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400efb1b  lea     r8d, [r9+1]; CacheType
0x1400efb1f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400efb26  nop     dword ptr [rax+rax+00h]
0x1400efb2b  test    rax, rax
0x1400efb2e  jnz     short loc_1400EFB58
0x1400efb30  mov     rcx, [rdi+12A0h]
0x1400efb37  lea     r9d, [rax+1]; CacheType
0x1400efb3b  mov     r8, [rsi+8]; MemoryDescriptorList
0x1400efb3f  mov     edx, 30455646h; PoolTag
0x1400efb44  mov     rcx, [rcx+40h]; MappingAddress
0x1400efb48  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400efb4f  nop     dword ptr [rax+rax+00h]
0x1400efb54  mov     bl, 1
0x1400efb56  jmp     short loc_1400EFB5A
0x1400efb58  xor     bl, bl
0x1400efb5a  mov     rcx, [rdi+12A0h]
0x1400efb61  mov     r8, rbp; Size
0x1400efb64  mov     rdx, rax; Src
0x1400efb67  mov     rcx, [rcx+50h]; void *
0x1400efb6b  call    memmove
0x1400efb70  mov     rax, [rdi+12A0h]
0x1400efb77  lea     rdx, [rsp+178h+var_138]; int
0x1400efb7c  mov     [rsp+178h+var_140], 0; __int64
0x1400efb85  or      r9, 0FFFFFFFFFFFFFFFFh; int
0x1400efb89  mov     r8, r14; int
0x1400efb8c  mov     rcx, [rax+50h]
0x1400efb90  mov     [rsp+178h+var_148], rcx; PUCHAR
0x1400efb95  mov     qword ptr [rsp+178h+Priority], rcx; PUCHAR
0x1400efb9a  lea     ecx, [r9+4]; int
0x1400efb9e  mov     [rsp+178h+BugCheckOnFailure], ebp; int
0x1400efba2  call    FveFilteredEncrypt
0x1400efba7  test    eax, eax
0x1400efba9  jns     short loc_1400EFBCE
0x1400efbab  xor     r9d, r9d; BugCheckParameter3
0x1400efbae  cdqe
0x1400efbb0  xor     r8d, r8d; BugCheckParameter2
0x1400efbb3  mov     qword ptr [rsp+178h+BugCheckOnFailure], rax; BugCheckParameter4
0x1400efbb8  mov     ecx, 120h; BugCheckCode
0x1400efbbd  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400efbc1  call    cs:__imp_KeBugCheckEx
0x1400efbce  test    bl, bl
0x1400efbd0  jz      short loc_1400EFBF2
0x1400efbd2  mov     rcx, [rdi+12A0h]
0x1400efbd9  mov     edx, 30455646h; PoolTag
0x1400efbde  mov     r8, [rsi+8]; MemoryDescriptorList
0x1400efbe2  mov     rcx, [rcx+40h]; BaseAddress
0x1400efbe6  call    cs:__imp_MmUnmapReservedMapping
0x1400efbed  nop     dword ptr [rax+rax+00h]
0x1400efbf2  mov     rcx, [rdi+12A0h]
0x1400efbf9  mov     edx, 1
0x1400efbfe  mov     rcx, [rcx+48h]
0x1400efc02  call    cs:__imp_MmMdlPageContentsState
0x1400efc09  nop     dword ptr [rax+rax+00h]
0x1400efc0e  mov     rax, [rdi+12A0h]
0x1400efc15  mov     rcx, [rax+48h]
0x1400efc19  xchg    rcx, [rsi+8]
0x1400efc1d  mov     rax, [rdi+12A0h]
0x1400efc24  cmp     [rax+70h], rcx
0x1400efc28  jz      short loc_1400EFC4F
0x1400efc2a  xor     r9d, r9d; BugCheckParameter3
0x1400efc2d  mov     qword ptr [rsp+178h+BugCheckOnFailure], 0; BugCheckParameter4
0x1400efc36  xor     r8d, r8d; BugCheckParameter2
0x1400efc39  mov     ecx, 120h; BugCheckCode
0x1400efc3e  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400efc42  call    cs:__imp_KeBugCheckEx
0x1400efc4f  add     rsp, 148h
0x1400efc56  pop     r15
0x1400efc58  pop     r14
0x1400efc5a  pop     rdi
0x1400efc5b  pop     rsi
0x1400efc5c  pop     rbp
0x1400efc5d  pop     rbx
0x1400efc5e  retn
```
