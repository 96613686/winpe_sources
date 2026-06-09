# FatCreateRootDcb

- ea: `0x140047e34`
- end: `0x1400480fe`
- name: `FatCreateRootDcb`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140040674`

## callees

- `0x1400062c8`
- `0x14000656c`
- `0x14000c680`
- `0x1400226b8`
- `0x14003eb84`
- `0x14004707c`
- `0x140047e34`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140047fa7`
- `ntoskrnl!KeInitializeEvent` at `0x140047fa7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047edd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047edd`
- `ntoskrnl!FsRtlInitializeOplock` at `0x1400480e2`
- `ntoskrnl!FsRtlInitializeOplock` at `0x1400480e2`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005fbd8`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005fbd8`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140048005`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140048005`
- `ntoskrnl!KeBugCheckEx` at `0x140047e82`
- `ntoskrnl!KeBugCheckEx` at `0x140047e82`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fc11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fc11`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400480ca`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400480ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140047ea0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140047ea0`

## pseudocode

```c
void __fastcall FatCreateRootDcb(__int64 a1, __int64 a2)
{
  char *PoolWithTag; // rax
  char *v5; // rbx
  PVOID v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rcx

  if ( *(_QWORD *)(a2 + 208) )
    KeBugCheckEx(0x23u, 0x1C03FFu, 0, 0, 0);
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1552, 0x278u, 0x46746146u);
  v5 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, 0x278u);
  *(_QWORD *)(a2 + 208) = v5;
  v6 = ExAllocateFromNPagedLookasideList(&FatNonPagedFcbLookasideList);
  *((_QWORD *)v5 + 15) = v6;
  memset(v6, 0, 0x78u);
  *(_DWORD *)v5 = 41420036;
  *((_DWORD *)v5 + 49) = 1;
  *((_QWORD *)v5 + 1) = FatAllocateResource(v8, v7, v9, v10);
  *((_QWORD *)v5 + 2) = FatAllocateResource(v12, v11, v13, v14);
  *((_QWORD *)v5 + 21) = v5 + 160;
  *((_QWORD *)v5 + 20) = v5 + 160;
  *((_QWORD *)v5 + 23) = a2;
  *((_QWORD *)v5 + 41) = v5 + 320;
  *((_QWORD *)v5 + 40) = v5 + 320;
  *((_QWORD *)v5 + 67) = L"\\";
  *((_DWORD *)v5 + 132) = 262146;
  *((_QWORD *)v5 + 61) = "\\";
  *((_DWORD *)v5 + 120) = 131073;
  v5[546] = 16;
  v15 = *((_QWORD *)v5 + 15);
  *(_DWORD *)(v15 + 40) = 1;
  *(_QWORD *)(v15 + 48) = 0;
  *(_DWORD *)(v15 + 56) = 0;
  KeInitializeEvent((PRKEVENT)(v15 + 64), SynchronizationEvent, 0);
  v16 = *((_QWORD *)v5 + 15);
  v5[4] |= 0x40u;
  v5[6] |= 2u;
  v5[7] = v5[7] & 0xF | 0x50;
  *((_QWORD *)v5 + 8) = v5 + 56;
  *((_QWORD *)v5 + 7) = v5 + 56;
  v17 = v16 + 40;
  if ( v17 )
    *((_QWORD *)v5 + 6) = v17;
  *((_QWORD *)v5 + 9) = 0;
  *((_QWORD *)v5 + 10) = 0;
  *((_QWORD *)v5 + 11) = 0;
  *((_QWORD *)v5 + 12) = 0;
  *((_DWORD *)v5 + 26) = 0;
  *((_QWORD *)v5 + 14) = 0;
  FsRtlInitializeLargeMcb((PLARGE_MCB)v5 + 9, (POOL_TYPE)512);
  if ( *(_BYTE *)(a2 + 376) == 32 )
  {
    *((_DWORD *)v5 + 32) = *(_DWORD *)(a2 + 328);
  }
  else
  {
    v18 = *(unsigned __int16 *)(a2 + 302);
    if ( !(_WORD)v18 )
      v18 = *(_DWORD *)(a2 + 316);
    FatAddMcbEntry(
      a2,
      v5 + 288,
      0,
      *(unsigned __int16 *)(a2 + 288)
    * (*(unsigned __int16 *)(a2 + 292) + v18 * (unsigned int)*(unsigned __int8 *)(a2 + 294)),
      32 * *(unsigned __int16 *)(a2 + 296));
  }
  if ( *(_BYTE *)(a2 + 376) == 32 )
  {
    *((_DWORD *)v5 + 6) = -1;
    FatLookupFileAllocationSize(a1, v5);
    v19 = *((_QWORD *)v5 + 3);
  }
  else
  {
    v19 = 32LL * *(unsigned __int16 *)(a2 + 296);
    *((_QWORD *)v5 + 3) = v19;
  }
  *((_QWORD *)v5 + 4) = v19;
  *((_QWORD *)v5 + 47) = -1;
  RtlInitializeBitMap((PRTL_BITMAP)v5 + 25, 0, 0);
  FatCheckFreeDirentBitmap(v20, v5);
  FsRtlInitializeOplock((POPLOCK)v5 + 11);
}

```

## disassembly

```asm
0x140047e34  mov     rax, rsp
0x140047e37  mov     [rax+10h], rdx
0x140047e3b  push    rbx
0x140047e3c  push    rsi
0x140047e3d  push    rdi
0x140047e3e  push    r12
0x140047e40  push    r14
0x140047e42  push    r15
0x140047e44  sub     rsp, 68h
0x140047e48  mov     rdi, rdx
0x140047e4b  mov     r15, rcx
0x140047e4e  xorps   xmm0, xmm0
0x140047e51  movdqu  xmmword ptr [rax-50h], xmm0
0x140047e56  xor     r12d, r12d
0x140047e59  mov     [rax-60h], r12
0x140047e5d  mov     [rax-58h], r12
0x140047e61  mov     [rax-68h], r12
0x140047e65  cmp     [rdx+0D0h], r12
0x140047e6c  jz      short loc_140047E8E
0x140047e6e  mov     [rax-78h], r12
0x140047e72  xor     r9d, r9d; BugCheckParameter3
0x140047e75  xor     r8d, r8d; BugCheckParameter2
0x140047e78  mov     edx, 1C03FFh; BugCheckParameter1
0x140047e7d  lea     ecx, [r12+23h]; BugCheckCode
0x140047e82  call    cs:__imp_KeBugCheckEx
0x140047e8e  mov     esi, 278h
0x140047e93  mov     r8d, 46746146h; Tag
0x140047e99  mov     edx, esi; NumberOfBytes
0x140047e9b  mov     ecx, 610h; PoolType
0x140047ea0  call    cs:__imp_ExAllocatePoolWithTag
0x140047ea7  nop     dword ptr [rax+rax+00h]
0x140047eac  mov     rbx, rax
0x140047eaf  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x140047eb6  jnz     short loc_140047ECA
0x140047eb8  test    rax, rax
0x140047ebb  jz      short loc_140047ECA
0x140047ebd  mov     r8d, esi; Size
0x140047ec0  xor     edx, edx; Val
0x140047ec2  mov     rcx, rax; void *
0x140047ec5  call    memset
0x140047eca  mov     [rdi+0D0h], rbx
0x140047ed1  mov     [rsp+98h+var_50], rbx
0x140047ed6  lea     rcx, FatNonPagedFcbLookasideList; Lookaside
0x140047edd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140047ee4  nop     dword ptr [rax+rax+00h]
0x140047ee9  mov     [rbx+78h], rax
0x140047eed  mov     [rsp+98h+var_48], rax
0x140047ef2  xor     edx, edx; Val
0x140047ef4  lea     r8d, [rdx+78h]; Size
0x140047ef8  mov     rcx, rax; void *
0x140047efb  call    memset
0x140047f00  mov     dword ptr [rbx], 2780504h
0x140047f06  mov     r14d, 1
0x140047f0c  mov     [rbx+0C4h], r14d
0x140047f13  call    FatAllocateResource
0x140047f18  mov     [rbx+8], rax
0x140047f1c  mov     [rsp+98h+var_60], rax
0x140047f21  call    FatAllocateResource
0x140047f26  mov     [rbx+10h], rax
0x140047f2a  mov     [rsp+98h+var_58], rax
0x140047f2f  lea     rax, [rbx+0A0h]
0x140047f36  mov     [rax+8], rax
0x140047f3a  mov     [rax], rax
0x140047f3d  mov     [rbx+0B8h], rdi
0x140047f44  lea     rax, [rbx+140h]
0x140047f4b  mov     [rax+8], rax
0x140047f4f  mov     [rax], rax
0x140047f52  lea     rax, asc_14000FC20; "\\"
0x140047f59  mov     [rbx+218h], rax
0x140047f60  lea     esi, [r14+1]
0x140047f64  mov     dword ptr [rbx+210h], 40002h
0x140047f6e  lea     rax, asc_14000FC1C; "\\"
0x140047f75  mov     [rbx+1E8h], rax
0x140047f7c  mov     dword ptr [rbx+1E0h], 20001h
0x140047f86  mov     byte ptr [rbx+222h], 10h
0x140047f8d  mov     rcx, [rbx+78h]
0x140047f91  mov     [rcx+28h], r14d
0x140047f95  mov     [rcx+30h], r12
0x140047f99  mov     [rcx+38h], r12d
0x140047f9d  add     rcx, 40h ; '@'; Event
0x140047fa1  xor     r8d, r8d; State
0x140047fa4  mov     edx, r14d; Type
0x140047fa7  call    cs:__imp_KeInitializeEvent
0x140047fae  nop     dword ptr [rax+rax+00h]
0x140047fb3  mov     rcx, [rbx+78h]
0x140047fb7  or      byte ptr [rbx+4], 40h
0x140047fbb  or      [rbx+6], sil
0x140047fbf  mov     al, [rbx+7]
0x140047fc2  and     al, 0Fh
0x140047fc4  or      al, 50h
0x140047fc6  mov     [rbx+7], al
0x140047fc9  lea     rax, [rbx+38h]
0x140047fcd  mov     [rax+8], rax
0x140047fd1  mov     [rax], rax
0x140047fd4  add     rcx, 28h ; '('
0x140047fd8  jz      short loc_140047FDE
0x140047fda  mov     [rbx+30h], rcx
0x140047fde  mov     [rbx+48h], r12
0x140047fe2  mov     [rbx+50h], r12
0x140047fe6  mov     [rbx+58h], r12
0x140047fea  mov     [rbx+60h], r12
0x140047fee  mov     [rbx+68h], r12d
0x140047ff2  mov     [rbx+70h], r12
0x140047ff6  lea     rsi, [rbx+120h]
0x140047ffd  mov     edx, 200h; PoolType
0x140048002  mov     rcx, rsi; Mcb
0x140048005  call    cs:__imp_FsRtlInitializeLargeMcb
0x14004800c  nop     dword ptr [rax+rax+00h]
0x140048011  mov     [rsp+98h+var_68], rsi
0x140048016  cmp     byte ptr [rdi+178h], 20h ; ' '
0x14004801d  jnz     short loc_14004802D
0x14004801f  mov     eax, [rdi+148h]
0x140048025  mov     [rbx+80h], eax
0x14004802b  jmp     short loc_14004807F
0x14004802d  movzx   eax, word ptr [rdi+12Eh]
0x140048034  movzx   edx, word ptr [rdi+120h]
0x14004803b  test    ax, ax
0x14004803e  jnz     short loc_140048046
0x140048040  mov     eax, [rdi+13Ch]
0x140048046  movzx   r8d, word ptr [rdi+128h]
0x14004804e  shl     r8d, 5
0x140048052  movzx   r9d, byte ptr [rdi+126h]
0x14004805a  imul    r9d, eax
0x14004805e  movzx   eax, word ptr [rdi+124h]
0x140048065  add     r9d, eax
0x140048068  imul    r9d, edx
0x14004806c  mov     [rsp+98h+var_78], r8d
0x140048071  xor     r8d, r8d
0x140048074  mov     rdx, rsi
0x140048077  mov     rcx, rdi
0x14004807a  call    FatAddMcbEntry
0x14004807f  cmp     byte ptr [rdi+178h], 20h ; ' '
0x140048086  jnz     short loc_1400480A0
0x140048088  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x14004808f  mov     rdx, rbx
0x140048092  mov     rcx, r15
0x140048095  call    FatLookupFileAllocationSize
0x14004809a  mov     rax, [rbx+18h]
0x14004809e  jmp     short loc_1400480AF
0x1400480a0  movzx   eax, word ptr [rdi+128h]
0x1400480a7  shl     rax, 5
0x1400480ab  mov     [rbx+18h], rax
0x1400480af  mov     [rbx+20h], rax
0x1400480b3  mov     qword ptr [rbx+178h], 0FFFFFFFFFFFFFFFFh
0x1400480be  lea     rcx, [rbx+190h]; BitMapHeader
0x1400480c5  xor     r8d, r8d; SizeOfBitMap
0x1400480c8  xor     edx, edx; BitMapBuffer
0x1400480ca  call    cs:__imp_RtlInitializeBitMap
0x1400480d1  nop     dword ptr [rax+rax+00h]
0x1400480d6  mov     rdx, rbx
0x1400480d9  call    FatCheckFreeDirentBitmap
0x1400480de  lea     rcx, [rbx+58h]; Oplock
0x1400480e2  call    cs:__imp_FsRtlInitializeOplock
0x1400480e9  nop     dword ptr [rax+rax+00h]
0x1400480ee  nop
0x1400480ef  add     rsp, 68h
0x1400480f3  pop     r15
0x1400480f5  pop     r14
0x1400480f7  pop     r12
0x1400480f9  pop     rdi
0x1400480fa  pop     rsi
0x1400480fb  pop     rbx
0x1400480fc  retn
0x14005fbc1  push    rbx
0x14005fbc3  push    rbp
0x14005fbc4  sub     rsp, 38h
0x14005fbc8  mov     rbp, rdx
0x14005fbcb  test    cl, cl
0x14005fbcd  jz      short loc_14005FC37
0x14005fbcf  mov     rcx, [rbp+30h]; Mcb
0x14005fbd3  test    rcx, rcx
0x14005fbd6  jz      short loc_14005FBE5
0x14005fbd8  call    cs:__imp_FsRtlUninitializeLargeMcb
0x14005fbdf  nop     dword ptr [rax+rax+00h]
0x14005fbe4  nop
0x14005fbe5  mov     rcx, [rbp+38h]; Entry
0x14005fbe9  test    rcx, rcx
0x14005fbec  jz      short loc_14005FBF4
0x14005fbee  call    FatFreeResource
0x14005fbf3  nop
0x14005fbf4  mov     rcx, [rbp+40h]; Entry
0x14005fbf8  test    rcx, rcx
0x14005fbfb  jz      short loc_14005FC03
0x14005fbfd  call    FatFreeResource
0x14005fc02  nop
0x14005fc03  xor     ebx, ebx
0x14005fc05  mov     rcx, [rbp+rbx*8+48h]; P
0x14005fc0a  test    rcx, rcx
0x14005fc0d  jz      short loc_14005FC1E
0x14005fc0f  xor     edx, edx; Tag
0x14005fc11  call    cs:__imp_ExFreePoolWithTag
0x14005fc18  nop     dword ptr [rax+rax+00h]
0x14005fc1d  nop
0x14005fc1e  inc     ebx
0x14005fc20  cmp     ebx, 2
0x14005fc23  jb      short loc_14005FC05
0x14005fc25  mov     rax, [rbp+0A8h]
0x14005fc2c  mov     qword ptr [rax+0D0h], 0
0x14005fc37  add     rsp, 38h
0x14005fc3b  pop     rbp
0x14005fc3c  pop     rbx
0x14005fc3d  retn
```
