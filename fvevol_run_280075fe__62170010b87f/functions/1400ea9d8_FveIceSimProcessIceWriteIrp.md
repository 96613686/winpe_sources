# FveIceSimProcessIceWriteIrp

- ea: `0x1400ea9d8`
- end: `0x1400eac60`
- name: `FveIceSimProcessIceWriteIrp`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400ea498`

## callees

- `0x140008288`
- `0x140008c10`
- `0x140021a00`
- `0x140021d00`
- `0x1400ea9d8`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400eaadb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400eaadb`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400eac02`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400eac02`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400eab48`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400eab48`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400eabe6`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400eabe6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400eab1f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400eab1f`
- `ntoskrnl!KeBugCheckEx` at `0x1400eabc1`
- `ntoskrnl!KeBugCheckEx` at `0x1400eac42`
- `ntoskrnl!KeBugCheckEx` at `0x1400eabc1`
- `ntoskrnl!KeBugCheckEx` at `0x1400eac42`

## pseudocode

```c
__int64 __fastcall FveIceSimProcessIceWriteIrp(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  size_t v5; // rbp
  __int64 v6; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r9
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  __int16 v14; // bx
  __int64 v15; // rcx
  PVOID v16; // rax
  char v17; // bl
  int v18; // eax
  __int64 v19; // rcx
  __int64 result; // rax
  int v21[64]; // [rsp+40h] [rbp-138h] BYREF

  v5 = a4;
  v6 = *(_QWORD *)(a1 + 4752);
  if ( *(_QWORD *)(v6 + 104) != a2 || *(_QWORD *)(v6 + 112) != *(_QWORD *)(a2 + 8) || a4 > 0x100000 )
    goto LABEL_18;
  memset(v21, 0, sizeof(v21));
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v9) )
    *(_QWORD *)&v21[16] = *(_QWORD *)(*(_QWORD *)(a1 + 4752) + 152LL);
  else
    *(_QWORD *)&v21[16] = *(_QWORD *)(a1 + 1008);
  v21[29] = *(_DWORD *)(a1 + 1308);
  v10 = *(_QWORD *)(a1 + 4752);
  v11 = *(_QWORD *)(v10 + 72);
  v12 = *(_QWORD *)(v10 + 80) & 0xFFFFFFFFFFFFF000uLL;
  v13 = *(_QWORD *)(v10 + 80) & 0xFFFLL;
  v14 = *(_WORD *)(v11 + 8);
  *(_QWORD *)v11 = 0;
  *(_WORD *)(v11 + 8) = 8 * (((v13 + v5 + 4095) >> 12) + 6);
  *(_WORD *)(v11 + 10) = 0;
  *(_QWORD *)(v11 + 32) = v12;
  *(_DWORD *)(v11 + 44) = v13;
  *(_DWORD *)(v11 + 40) = v5;
  MmBuildMdlForNonPagedPool(*(PMDL *)(*(_QWORD *)(a1 + 4752) + 72LL));
  *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 4752) + 72LL) + 8LL) = v14;
  v15 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v15 + 10) & 5) != 0 )
    v16 = *(PVOID *)(v15 + 24);
  else
    v16 = MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000010u);
  if ( v16 )
  {
    v17 = 0;
  }
  else
  {
    v16 = MmMapLockedPagesWithReservedMapping(
            *(PVOID *)(*(_QWORD *)(a1 + 4752) + 64LL),
            0x30455646u,
            *(PMDL *)(a2 + 8),
            MmCached);
    v17 = 1;
  }
  memmove(*(void **)(*(_QWORD *)(a1 + 4752) + 80LL), v16, v5);
  v18 = FveFilteredEncrypt(
          3,
          (int)v21,
          a3,
          -1,
          v5,
          *(PUCHAR *)(*(_QWORD *)(a1 + 4752) + 80LL),
          *(PUCHAR *)(*(_QWORD *)(a1 + 4752) + 80LL),
          0);
  if ( v18 < 0 )
    KeBugCheckEx(0x120u, 0xCu, 0, 0, v18);
  if ( v17 )
    MmUnmapReservedMapping(*(PVOID *)(*(_QWORD *)(a1 + 4752) + 64LL), 0x30455646u, *(PMDL *)(a2 + 8));
  MmMdlPageContentsState(*(_QWORD *)(*(_QWORD *)(a1 + 4752) + 72LL), 1);
  v19 = _InterlockedExchange64((volatile __int64 *)(a2 + 8), *(_QWORD *)(*(_QWORD *)(a1 + 4752) + 72LL));
  result = *(_QWORD *)(a1 + 4752);
  if ( *(_QWORD *)(result + 112) != v19 )
LABEL_18:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  return result;
}

```

## disassembly

```asm
0x1400ea9d8  push    rbx
0x1400ea9da  push    rbp
0x1400ea9db  push    rsi
0x1400ea9dc  push    rdi
0x1400ea9dd  push    r14
0x1400ea9df  push    r15
0x1400ea9e1  sub     rsp, 148h
0x1400ea9e8  mov     rdi, rcx
0x1400ea9eb  mov     ebp, r9d
0x1400ea9ee  mov     rcx, [rcx+1290h]
0x1400ea9f5  mov     r14, r8
0x1400ea9f8  mov     rsi, rdx
0x1400ea9fb  cmp     [rcx+68h], rdx
0x1400ea9ff  jnz     loc_1400EAC2A
0x1400eaa05  mov     rax, [rdx+8]
0x1400eaa09  cmp     [rcx+70h], rax
0x1400eaa0d  jnz     loc_1400EAC2A
0x1400eaa13  cmp     ebp, 100000h
0x1400eaa19  ja      loc_1400EAC2A
0x1400eaa1f  xor     edx, edx; Val
0x1400eaa21  lea     rcx, [rsp+178h+var_138]; void *
0x1400eaa26  mov     r8d, 100h; Size
0x1400eaa2c  call    memset
0x1400eaa31  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400eaa36  test    eax, eax
0x1400eaa38  jz      short loc_1400EAA52
0x1400eaa3a  mov     rax, [rdi+1290h]
0x1400eaa41  mov     rcx, [rax+98h]
0x1400eaa48  mov     [rsp+178h+var_F8], rcx
0x1400eaa50  jmp     short loc_1400EAA61
0x1400eaa52  mov     rax, [rdi+3F0h]
0x1400eaa59  mov     [rsp+178h+var_F8], rax
0x1400eaa61  mov     eax, [rdi+51Ch]
0x1400eaa67  lea     rcx, [rbp+0FFFh]
0x1400eaa6e  mov     [rsp+178h+var_C4], eax
0x1400eaa75  mov     r10d, 0FFFh
0x1400eaa7b  mov     rax, [rdi+1290h]
0x1400eaa82  mov     rdx, [rax+50h]
0x1400eaa86  mov     r9, [rax+48h]
0x1400eaa8a  mov     r8d, edx
0x1400eaa8d  mov     eax, r8d
0x1400eaa90  and     rdx, 0FFFFFFFFFFFFF000h
0x1400eaa97  and     rax, r10
0x1400eaa9a  and     r8d, r10d
0x1400eaa9d  add     rcx, rax
0x1400eaaa0  xor     eax, eax
0x1400eaaa2  movzx   ebx, word ptr [r9+8]
0x1400eaaa7  shr     rcx, 0Ch
0x1400eaaab  add     cx, 6
0x1400eaaaf  mov     qword ptr [r9], 0
0x1400eaab6  shl     cx, 3
0x1400eaaba  mov     [r9+8], cx
0x1400eaabf  mov     [r9+0Ah], ax
0x1400eaac4  mov     [r9+20h], rdx
0x1400eaac8  mov     [r9+2Ch], r8d
0x1400eaacc  mov     [r9+28h], ebp
0x1400eaad0  mov     rcx, [rdi+1290h]
0x1400eaad7  mov     rcx, [rcx+48h]; MemoryDescriptorList
0x1400eaadb  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400eaae2  nop     dword ptr [rax+rax+00h]
0x1400eaae7  mov     rax, [rdi+1290h]
0x1400eaaee  mov     rcx, [rax+48h]
0x1400eaaf2  mov     [rcx+8], bx
0x1400eaaf6  mov     rcx, [rsi+8]; MemoryDescriptorList
0x1400eaafa  test    byte ptr [rcx+0Ah], 5
0x1400eaafe  jz      short loc_1400EAB06
0x1400eab00  mov     rax, [rcx+18h]
0x1400eab04  jmp     short loc_1400EAB2B
0x1400eab06  xor     r9d, r9d; RequestedAddress
0x1400eab09  mov     [rsp+178h+Priority], 40000010h; Priority
0x1400eab11  xor     edx, edx; AccessMode
0x1400eab13  mov     [rsp+178h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400eab1b  lea     r8d, [r9+1]; CacheType
0x1400eab1f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400eab26  nop     dword ptr [rax+rax+00h]
0x1400eab2b  test    rax, rax
0x1400eab2e  jnz     short loc_1400EAB58
0x1400eab30  mov     rcx, [rdi+1290h]
0x1400eab37  lea     r9d, [rax+1]; CacheType
0x1400eab3b  mov     r8, [rsi+8]; MemoryDescriptorList
0x1400eab3f  mov     edx, 30455646h; PoolTag
0x1400eab44  mov     rcx, [rcx+40h]; MappingAddress
0x1400eab48  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400eab4f  nop     dword ptr [rax+rax+00h]
0x1400eab54  mov     bl, 1
0x1400eab56  jmp     short loc_1400EAB5A
0x1400eab58  xor     bl, bl
0x1400eab5a  mov     rcx, [rdi+1290h]
0x1400eab61  mov     r8, rbp; Size
0x1400eab64  mov     rdx, rax; Src
0x1400eab67  mov     rcx, [rcx+50h]; void *
0x1400eab6b  call    memmove
0x1400eab70  mov     rax, [rdi+1290h]
0x1400eab77  lea     rdx, [rsp+178h+var_138]; int
0x1400eab7c  mov     [rsp+178h+var_140], 0; __int64
0x1400eab85  or      r9, 0FFFFFFFFFFFFFFFFh; int
0x1400eab89  mov     r8, r14; int
0x1400eab8c  mov     rcx, [rax+50h]
0x1400eab90  mov     [rsp+178h+var_148], rcx; PUCHAR
0x1400eab95  mov     qword ptr [rsp+178h+Priority], rcx; PUCHAR
0x1400eab9a  lea     ecx, [r9+4]; int
0x1400eab9e  mov     [rsp+178h+BugCheckOnFailure], ebp; int
0x1400eaba2  call    FveFilteredEncrypt
0x1400eaba7  test    eax, eax
0x1400eaba9  jns     short loc_1400EABCE
0x1400eabab  xor     r9d, r9d; BugCheckParameter3
0x1400eabae  cdqe
0x1400eabb0  xor     r8d, r8d; BugCheckParameter2
0x1400eabb3  mov     qword ptr [rsp+178h+BugCheckOnFailure], rax; BugCheckParameter4
0x1400eabb8  mov     ecx, 120h; BugCheckCode
0x1400eabbd  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400eabc1  call    cs:__imp_KeBugCheckEx
0x1400eabce  test    bl, bl
0x1400eabd0  jz      short loc_1400EABF2
0x1400eabd2  mov     rcx, [rdi+1290h]
0x1400eabd9  mov     edx, 30455646h; PoolTag
0x1400eabde  mov     r8, [rsi+8]; MemoryDescriptorList
0x1400eabe2  mov     rcx, [rcx+40h]; BaseAddress
0x1400eabe6  call    cs:__imp_MmUnmapReservedMapping
0x1400eabed  nop     dword ptr [rax+rax+00h]
0x1400eabf2  mov     rcx, [rdi+1290h]
0x1400eabf9  mov     edx, 1
0x1400eabfe  mov     rcx, [rcx+48h]
0x1400eac02  call    cs:__imp_MmMdlPageContentsState
0x1400eac09  nop     dword ptr [rax+rax+00h]
0x1400eac0e  mov     rax, [rdi+1290h]
0x1400eac15  mov     rcx, [rax+48h]
0x1400eac19  xchg    rcx, [rsi+8]
0x1400eac1d  mov     rax, [rdi+1290h]
0x1400eac24  cmp     [rax+70h], rcx
0x1400eac28  jz      short loc_1400EAC4F
0x1400eac2a  xor     r9d, r9d; BugCheckParameter3
0x1400eac2d  mov     qword ptr [rsp+178h+BugCheckOnFailure], 0; BugCheckParameter4
0x1400eac36  xor     r8d, r8d; BugCheckParameter2
0x1400eac39  mov     ecx, 120h; BugCheckCode
0x1400eac3e  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400eac42  call    cs:__imp_KeBugCheckEx
0x1400eac4f  add     rsp, 148h
0x1400eac56  pop     r15
0x1400eac58  pop     r14
0x1400eac5a  pop     rdi
0x1400eac5b  pop     rsi
0x1400eac5c  pop     rbp
0x1400eac5d  pop     rbx
0x1400eac5e  retn
```
