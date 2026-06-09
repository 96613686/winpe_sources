# SafeModeAllocateFragments(_VELAN *,_NET_BUFFER *,ulong,int,_NET_BUFFER * *)

- ea: `0x140010e08`
- end: `0x1400110a8`
- name: `?SafeModeAllocateFragments@@YAJPEAU_VELAN@@PEAU_NET_BUFFER@@KHPEAPEAU2@@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct _VELAN *, struct _NET_BUFFER *, unsigned int, int, struct _NET_BUFFER **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400322ac`

## callees

- `0x140010e08`
- `0x140011418`
- `0x140019394`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010faa`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010faa`
- `ntoskrnl!MmSizeOfMdl` at `0x140010ea7`
- `ntoskrnl!MmSizeOfMdl` at `0x140010ea7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010f0d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010f0d`
- `ntoskrnl!ExAllocatePool2` at `0x140010f28`
- `ntoskrnl!ExAllocatePool2` at `0x140010f28`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001104f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001104f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011060`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011060`
- `NDIS!NdisAllocateNetBuffer` at `0x140010ff0`
- `NDIS!NdisAllocateNetBuffer` at `0x140010ff0`

## pseudocode

```c
__int64 __fastcall SafeModeAllocateFragments(
        struct _VELAN *a1,
        struct _NET_BUFFER *a2,
        int a3,
        int a4,
        struct _NET_BUFFER **a5)
{
  struct _VELAN *v5; // r15
  struct _NET_BUFFER *v6; // r14
  __int64 CurrentMdlOffset; // rcx
  unsigned int v10; // r8d
  unsigned int v11; // ebp
  unsigned int v12; // esi
  int v13; // edx
  int i; // r13d
  unsigned int v15; // ecx
  unsigned int v16; // r12d
  __int64 v17; // r9
  unsigned int v18; // r15d
  unsigned int v19; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  struct _MDL *v22; // rdi
  unsigned int v23; // r9d
  int v24; // r8d
  PNET_BUFFER NetBuffer; // rax
  unsigned int v26; // eax
  struct _NET_BUFFER *v29; // [rsp+88h] [rbp+10h] BYREF
  int v30; // [rsp+90h] [rbp+18h]
  unsigned int v31; // [rsp+98h] [rbp+20h]

  v30 = a3;
  v5 = a1;
  v6 = 0;
  CurrentMdlOffset = a2->CurrentMdlOffset;
  v29 = 0;
  v10 = Dot11DataFrameMacHeaderSize((void *)(*(_QWORD *)(a2->Link.Region + 24) + CurrentMdlOffset));
  v11 = a2->DataLength - v10;
  v31 = v10;
  v12 = v11;
  v13 = a4 != 0 ? 2 : 0;
  v30 = v13;
  for ( i = 0; ; i = 1 )
  {
    if ( i )
    {
      *a5 = v6;
      return 0;
    }
    v15 = v11;
    if ( v12 < v11 )
      v15 = v12;
    v16 = v10 + v15 + v13 + v5->uBackFillSize + 16;
    if ( v16 > 0x1F3B )
      break;
    v18 = (MmSizeOfMdl((PVOID)0xFFF, v16) + 7) & 0xFFFFFFF8;
    v19 = v16 + v18 + 16;
    if ( v19 < 0x10 )
      break;
    if ( v19 <= 0x40 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_15:
      Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
      goto LABEL_17;
    }
    if ( v19 <= 0x100 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      goto LABEL_15;
    }
    if ( v19 <= 0x400 )
    {
      p_DeviceQueue = &Lookaside;
      goto LABEL_15;
    }
    if ( v19 <= 0x800 )
    {
      p_DeviceQueue = &stru_1400B0180;
      goto LABEL_15;
    }
    p_DeviceQueue = 0;
    Pool2 = (char *)ExAllocatePool2(64, v19, 828994423, v17);
LABEL_17:
    if ( !Pool2 )
      break;
    v22 = (struct _MDL *)(Pool2 + 16);
    *(_QWORD *)Pool2 = p_DeviceQueue;
    *((_DWORD *)Pool2 + 2) = 828994423;
    if ( Pool2 != (char *)-16LL )
    {
      v22->Next = 0;
      *((_DWORD *)Pool2 + 14) = v16;
      *((_QWORD *)Pool2 + 6) = ((unsigned __int64)v22 + v18) & 0xFFFFFFFFFFFFF000uLL;
      *((_WORD *)Pool2 + 13) = 0;
      *((_WORD *)Pool2 + 12) = 8
                             * ((((((_WORD)Pool2 + 16 + (_WORD)v18) & 0xFFF) + (unsigned __int64)v16 + 4095) >> 12) + 6);
      *((_DWORD *)Pool2 + 15) = ((_WORD)Pool2 + 16 + (_WORD)v18) & 0xFFF;
      MmBuildMdlForNonPagedPool(v22);
    }
    v5 = a1;
    v23 = v11;
    v24 = v30;
    v22->Next = 0;
    if ( v12 < v11 )
      v23 = v12;
    NetBuffer = NdisAllocateNetBuffer(a1->hSendNetBufferPool, v22, a1->uBackFillSize + v24 + 8, v31 + v23);
    if ( !NetBuffer )
    {
      if ( v22 )
      {
        if ( v22[-1].StartVa )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v22[-1].StartVa, &v22[-1].StartVa);
        else
          ExFreePoolWithTag(&v22[-1].StartVa, v22[-1].ByteCount);
      }
      break;
    }
    v13 = v30;
    v10 = v31;
    v6 = NetBuffer;
    NetBuffer->Link.Alignment = 0;
    v29 = NetBuffer;
    v26 = v11;
    if ( v12 < v11 )
      v26 = v12;
    v12 -= v26;
  }
  if ( v6 )
    SafeModeFreeNBChainAndMdls(&v29);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140010e08  mov     rax, rsp
0x140010e0b  mov     [rax+18h], r8d
0x140010e0f  mov     [rax+8], rcx
0x140010e13  push    rbx
0x140010e14  push    rbp
0x140010e15  push    rsi
0x140010e16  push    rdi
0x140010e17  push    r12
0x140010e19  push    r13
0x140010e1b  push    r14
0x140010e1d  push    r15
0x140010e1f  sub     rsp, 38h
0x140010e23  mov     r15, rcx
0x140010e26  xor     r14d, r14d
0x140010e29  mov     ecx, [rdx+10h]
0x140010e2c  mov     edi, r9d
0x140010e2f  mov     [rax+10h], r14
0x140010e33  mov     rbx, rdx
0x140010e36  mov     rax, [rdx+8]
0x140010e3a  add     rcx, [rax+18h]; void *
0x140010e3e  call    ?Dot11DataFrameMacHeaderSize@@YAKPEAX@Z; Dot11DataFrameMacHeaderSize(void *)
0x140010e43  mov     ebp, [rbx+18h]
0x140010e46  mov     r8d, eax
0x140010e49  sub     ebp, eax
0x140010e4b  mov     [rsp+78h+arg_18], eax
0x140010e52  neg     edi
0x140010e54  mov     esi, ebp
0x140010e56  sbb     edx, edx
0x140010e58  and     edx, 2
0x140010e5b  mov     [rsp+78h+arg_10], edx
0x140010e62  xor     r13d, r13d
0x140010e65  cmp     r13d, 1
0x140010e69  jnb     loc_140011089
0x140010e6f  mov     r12d, [r15+84h]
0x140010e76  cmp     esi, ebp
0x140010e78  mov     ecx, ebp
0x140010e7a  cmovb   ecx, esi
0x140010e7d  add     r12d, 10h
0x140010e81  add     r12d, edx
0x140010e84  add     r12d, ecx
0x140010e87  add     r12d, r8d
0x140010e8a  cmp     r12d, 1F3Bh
0x140010e91  ja      loc_14001106E
0x140010e97  mov     eax, r12d
0x140010e9a  mov     ecx, 0FFFh; Base
0x140010e9f  mov     edx, r12d; Length
0x140010ea2  mov     [rsp+78h+var_58], rax
0x140010ea7  call    cs:__imp_MmSizeOfMdl
0x140010eae  nop     dword ptr [rax+rax+00h]
0x140010eb3  lea     r15d, [rax+7]
0x140010eb7  and     r15d, 0FFFFFFF8h
0x140010ebb  lea     ecx, [r15+10h]
0x140010ebf  add     ecx, r12d
0x140010ec2  cmp     ecx, 10h
0x140010ec5  jb      loc_14001106E
0x140010ecb  cmp     ecx, 40h ; '@'
0x140010ece  ja      short loc_140010ED9
0x140010ed0  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140010ed7  jmp     short loc_140010F0A
0x140010ed9  cmp     ecx, 100h
0x140010edf  ja      short loc_140010EEA
0x140010ee1  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140010ee8  jmp     short loc_140010F0A
0x140010eea  cmp     ecx, 400h
0x140010ef0  ja      short loc_140010EFB
0x140010ef2  lea     rbx, Lookaside
0x140010ef9  jmp     short loc_140010F0A
0x140010efb  cmp     ecx, 800h
0x140010f01  ja      short loc_140010F1B
0x140010f03  lea     rbx, stru_1400B0180
0x140010f0a  mov     rcx, rbx; Lookaside
0x140010f0d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140010f14  nop     dword ptr [rax+rax+00h]
0x140010f19  jmp     short loc_140010F34
0x140010f1b  xor     ebx, ebx
0x140010f1d  mov     edx, ecx
0x140010f1f  mov     r8d, 31697377h
0x140010f25  lea     ecx, [rbx+40h]
0x140010f28  call    cs:__imp_ExAllocatePool2
0x140010f2f  nop     dword ptr [rax+rax+00h]
0x140010f34  test    rax, rax
0x140010f37  jz      loc_14001106E
0x140010f3d  lea     rdi, [rax+10h]
0x140010f41  mov     [rax], rbx
0x140010f44  mov     dword ptr [rax+8], 31697377h
0x140010f4b  test    rdi, rdi
0x140010f4e  jz      short loc_140010FB6
0x140010f50  mov     rcx, [rsp+78h+var_58]
0x140010f55  add     rcx, 0FFFh
0x140010f5c  mov     edx, r15d
0x140010f5f  add     rdx, rdi
0x140010f62  mov     qword ptr [rdi], 0
0x140010f69  mov     r8d, edx
0x140010f6c  mov     [rdi+28h], r12d
0x140010f70  mov     eax, r8d
0x140010f73  and     rdx, 0FFFFFFFFFFFFF000h
0x140010f7a  and     eax, 0FFFh
0x140010f7f  mov     [rdi+20h], rdx
0x140010f83  add     rcx, rax
0x140010f86  and     r8d, 0FFFh
0x140010f8d  shr     rcx, 0Ch
0x140010f91  xor     eax, eax
0x140010f93  add     cx, 6
0x140010f97  mov     [rdi+0Ah], ax
0x140010f9b  shl     cx, 3
0x140010f9f  mov     [rdi+8], cx
0x140010fa3  mov     rcx, rdi; MemoryDescriptorList
0x140010fa6  mov     [rdi+2Ch], r8d
0x140010faa  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140010fb1  nop     dword ptr [rax+rax+00h]
0x140010fb6  mov     r15, [rsp+78h+arg_0]
0x140010fbe  mov     r9d, ebp
0x140010fc1  mov     r8d, [rsp+78h+arg_10]
0x140010fc9  cmp     esi, ebp
0x140010fcb  mov     qword ptr [rdi], 0
0x140010fd2  mov     rdx, rdi; MdlChain
0x140010fd5  cmovb   r9d, esi
0x140010fd9  add     r8d, 8
0x140010fdd  add     r8d, [r15+84h]; DataOffset
0x140010fe4  add     r9d, [rsp+78h+arg_18]; DataLength
0x140010fec  mov     rcx, [r15+38h]; PoolHandle
0x140010ff0  call    cs:__imp_NdisAllocateNetBuffer
0x140010ff7  nop     dword ptr [rax+rax+00h]
0x140010ffc  test    rax, rax
0x140010fff  jz      short loc_140011033
0x140011001  mov     edx, [rsp+78h+arg_10]
0x140011008  cmp     esi, ebp
0x14001100a  mov     r8d, [rsp+78h+arg_18]
0x140011012  mov     r14, rax
0x140011015  mov     qword ptr [rax], 0
0x14001101c  mov     [rsp+78h+arg_8], rax
0x140011024  mov     eax, ebp
0x140011026  cmovb   eax, esi
0x140011029  sub     esi, eax
0x14001102b  inc     r13d
0x14001102e  jmp     loc_140010E65
0x140011033  mov     ebx, 0C000009Ah
0x140011038  test    rdi, rdi
0x14001103b  jz      short loc_140011073
0x14001103d  lea     rcx, [rdi-10h]; P
0x140011041  mov     rax, [rcx]
0x140011044  test    rax, rax
0x140011047  jz      short loc_14001105D
0x140011049  mov     rdx, rcx; Entry
0x14001104c  mov     rcx, rax; Lookaside
0x14001104f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140011056  nop     dword ptr [rax+rax+00h]
0x14001105b  jmp     short loc_140011073
0x14001105d  mov     edx, [rcx+8]; Tag
0x140011060  call    cs:__imp_ExFreePoolWithTag
0x140011067  nop     dword ptr [rax+rax+00h]
0x14001106c  jmp     short loc_140011073
0x14001106e  mov     ebx, 0C000009Ah
0x140011073  test    r14, r14
0x140011076  jz      short loc_140011085
0x140011078  lea     rcx, [rsp+78h+arg_8]; struct _NET_BUFFER **
0x140011080  call    ?SafeModeFreeNBChainAndMdls@@YAXPEAPEAU_NET_BUFFER@@@Z; SafeModeFreeNBChainAndMdls(_NET_BUFFER * *)
0x140011085  mov     eax, ebx
0x140011087  jmp     short loc_140011096
0x140011089  mov     rax, [rsp+78h+arg_20]
0x140011091  mov     [rax], r14
0x140011094  xor     eax, eax
0x140011096  add     rsp, 38h
0x14001109a  pop     r15
0x14001109c  pop     r14
0x14001109e  pop     r13
0x1400110a0  pop     r12
0x1400110a2  pop     rdi
0x1400110a3  pop     rsi
0x1400110a4  pop     rbp
0x1400110a5  pop     rbx
0x1400110a6  retn
```
