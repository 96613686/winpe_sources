# SafeModeAllocateFragments(_VELAN *,_NET_BUFFER *,ulong,int,_NET_BUFFER * *)

- ea: `0x140010df8`
- end: `0x140011098`
- name: `?SafeModeAllocateFragments@@YAJPEAU_VELAN@@PEAU_NET_BUFFER@@KHPEAPEAU2@@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct _VELAN *, struct _NET_BUFFER *, unsigned int, int, struct _NET_BUFFER **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400324cc`

## callees

- `0x140010df8`
- `0x140011408`
- `0x140019394`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010f9a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010f9a`
- `ntoskrnl!MmSizeOfMdl` at `0x140010e97`
- `ntoskrnl!MmSizeOfMdl` at `0x140010e97`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010efd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010efd`
- `ntoskrnl!ExAllocatePool2` at `0x140010f18`
- `ntoskrnl!ExAllocatePool2` at `0x140010f18`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001103f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001103f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011050`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011050`
- `NDIS!NdisAllocateNetBuffer` at `0x140010fe0`
- `NDIS!NdisAllocateNetBuffer` at `0x140010fe0`

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
  unsigned int v17; // r15d
  unsigned int v18; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  struct _MDL *v21; // rdi
  unsigned int v22; // r9d
  int v23; // r8d
  PNET_BUFFER NetBuffer; // rax
  unsigned int v25; // eax
  struct _NET_BUFFER *v28; // [rsp+88h] [rbp+10h] BYREF
  int v29; // [rsp+90h] [rbp+18h]
  unsigned int v30; // [rsp+98h] [rbp+20h]

  v29 = a3;
  v5 = a1;
  v6 = 0;
  CurrentMdlOffset = a2->CurrentMdlOffset;
  v28 = 0;
  v10 = Dot11DataFrameMacHeaderSize((void *)(*(_QWORD *)(a2->Link.Region + 24) + CurrentMdlOffset));
  v11 = a2->DataLength - v10;
  v30 = v10;
  v12 = v11;
  v13 = a4 != 0 ? 2 : 0;
  v29 = v13;
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
    v17 = (MmSizeOfMdl((PVOID)0xFFF, v16) + 7) & 0xFFFFFFF8;
    v18 = v16 + v17 + 16;
    if ( v18 < 0x10 )
      break;
    if ( v18 <= 0x40 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_15:
      Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
      goto LABEL_17;
    }
    if ( v18 <= 0x100 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      goto LABEL_15;
    }
    if ( v18 <= 0x400 )
    {
      p_DeviceQueue = &Lookaside;
      goto LABEL_15;
    }
    if ( v18 <= 0x800 )
    {
      p_DeviceQueue = &stru_1400B31C0;
      goto LABEL_15;
    }
    p_DeviceQueue = 0;
    Pool2 = (char *)ExAllocatePool2(64, v18, 828994423);
LABEL_17:
    if ( !Pool2 )
      break;
    v21 = (struct _MDL *)(Pool2 + 16);
    *(_QWORD *)Pool2 = p_DeviceQueue;
    *((_DWORD *)Pool2 + 2) = 828994423;
    if ( Pool2 != (char *)-16LL )
    {
      v21->Next = 0;
      *((_DWORD *)Pool2 + 14) = v16;
      *((_QWORD *)Pool2 + 6) = ((unsigned __int64)v21 + v17) & 0xFFFFFFFFFFFFF000uLL;
      *((_WORD *)Pool2 + 13) = 0;
      *((_WORD *)Pool2 + 12) = 8
                             * ((((((_WORD)Pool2 + 16 + (_WORD)v17) & 0xFFF) + (unsigned __int64)v16 + 4095) >> 12) + 6);
      *((_DWORD *)Pool2 + 15) = ((_WORD)Pool2 + 16 + (_WORD)v17) & 0xFFF;
      MmBuildMdlForNonPagedPool(v21);
    }
    v5 = a1;
    v22 = v11;
    v23 = v29;
    v21->Next = 0;
    if ( v12 < v11 )
      v22 = v12;
    NetBuffer = NdisAllocateNetBuffer(a1->hSendNetBufferPool, v21, a1->uBackFillSize + v23 + 8, v30 + v22);
    if ( !NetBuffer )
    {
      if ( v21 )
      {
        if ( v21[-1].StartVa )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v21[-1].StartVa, &v21[-1].StartVa);
        else
          ExFreePoolWithTag(&v21[-1].StartVa, v21[-1].ByteCount);
      }
      break;
    }
    v13 = v29;
    v10 = v30;
    v6 = NetBuffer;
    NetBuffer->Link.Alignment = 0;
    v28 = NetBuffer;
    v25 = v11;
    if ( v12 < v11 )
      v25 = v12;
    v12 -= v25;
  }
  if ( v6 )
    SafeModeFreeNBChainAndMdls(&v28);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140010df8  mov     rax, rsp
0x140010dfb  mov     [rax+18h], r8d
0x140010dff  mov     [rax+8], rcx
0x140010e03  push    rbx
0x140010e04  push    rbp
0x140010e05  push    rsi
0x140010e06  push    rdi
0x140010e07  push    r12
0x140010e09  push    r13
0x140010e0b  push    r14
0x140010e0d  push    r15
0x140010e0f  sub     rsp, 38h
0x140010e13  mov     r15, rcx
0x140010e16  xor     r14d, r14d
0x140010e19  mov     ecx, [rdx+10h]
0x140010e1c  mov     edi, r9d
0x140010e1f  mov     [rax+10h], r14
0x140010e23  mov     rbx, rdx
0x140010e26  mov     rax, [rdx+8]
0x140010e2a  add     rcx, [rax+18h]; void *
0x140010e2e  call    ?Dot11DataFrameMacHeaderSize@@YAKPEAX@Z; Dot11DataFrameMacHeaderSize(void *)
0x140010e33  mov     ebp, [rbx+18h]
0x140010e36  mov     r8d, eax
0x140010e39  sub     ebp, eax
0x140010e3b  mov     [rsp+78h+arg_18], eax
0x140010e42  neg     edi
0x140010e44  mov     esi, ebp
0x140010e46  sbb     edx, edx
0x140010e48  and     edx, 2
0x140010e4b  mov     [rsp+78h+arg_10], edx
0x140010e52  xor     r13d, r13d
0x140010e55  cmp     r13d, 1
0x140010e59  jnb     loc_140011079
0x140010e5f  mov     r12d, [r15+84h]
0x140010e66  cmp     esi, ebp
0x140010e68  mov     ecx, ebp
0x140010e6a  cmovb   ecx, esi
0x140010e6d  add     r12d, 10h
0x140010e71  add     r12d, edx
0x140010e74  add     r12d, ecx
0x140010e77  add     r12d, r8d
0x140010e7a  cmp     r12d, 1F3Bh
0x140010e81  ja      loc_14001105E
0x140010e87  mov     eax, r12d
0x140010e8a  mov     ecx, 0FFFh; Base
0x140010e8f  mov     edx, r12d; Length
0x140010e92  mov     [rsp+78h+var_58], rax
0x140010e97  call    cs:__imp_MmSizeOfMdl
0x140010e9e  nop     dword ptr [rax+rax+00h]
0x140010ea3  lea     r15d, [rax+7]
0x140010ea7  and     r15d, 0FFFFFFF8h
0x140010eab  lea     ecx, [r15+10h]
0x140010eaf  add     ecx, r12d
0x140010eb2  cmp     ecx, 10h
0x140010eb5  jb      loc_14001105E
0x140010ebb  cmp     ecx, 40h ; '@'
0x140010ebe  ja      short loc_140010EC9
0x140010ec0  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140010ec7  jmp     short loc_140010EFA
0x140010ec9  cmp     ecx, 100h
0x140010ecf  ja      short loc_140010EDA
0x140010ed1  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140010ed8  jmp     short loc_140010EFA
0x140010eda  cmp     ecx, 400h
0x140010ee0  ja      short loc_140010EEB
0x140010ee2  lea     rbx, Lookaside
0x140010ee9  jmp     short loc_140010EFA
0x140010eeb  cmp     ecx, 800h
0x140010ef1  ja      short loc_140010F0B
0x140010ef3  lea     rbx, stru_1400B31C0
0x140010efa  mov     rcx, rbx; Lookaside
0x140010efd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140010f04  nop     dword ptr [rax+rax+00h]
0x140010f09  jmp     short loc_140010F24
0x140010f0b  xor     ebx, ebx
0x140010f0d  mov     edx, ecx
0x140010f0f  mov     r8d, 31697377h
0x140010f15  lea     ecx, [rbx+40h]
0x140010f18  call    cs:__imp_ExAllocatePool2
0x140010f1f  nop     dword ptr [rax+rax+00h]
0x140010f24  test    rax, rax
0x140010f27  jz      loc_14001105E
0x140010f2d  lea     rdi, [rax+10h]
0x140010f31  mov     [rax], rbx
0x140010f34  mov     dword ptr [rax+8], 31697377h
0x140010f3b  test    rdi, rdi
0x140010f3e  jz      short loc_140010FA6
0x140010f40  mov     rcx, [rsp+78h+var_58]
0x140010f45  add     rcx, 0FFFh
0x140010f4c  mov     edx, r15d
0x140010f4f  add     rdx, rdi
0x140010f52  mov     qword ptr [rdi], 0
0x140010f59  mov     r8d, edx
0x140010f5c  mov     [rdi+28h], r12d
0x140010f60  mov     eax, r8d
0x140010f63  and     rdx, 0FFFFFFFFFFFFF000h
0x140010f6a  and     eax, 0FFFh
0x140010f6f  mov     [rdi+20h], rdx
0x140010f73  add     rcx, rax
0x140010f76  and     r8d, 0FFFh
0x140010f7d  shr     rcx, 0Ch
0x140010f81  xor     eax, eax
0x140010f83  add     cx, 6
0x140010f87  mov     [rdi+0Ah], ax
0x140010f8b  shl     cx, 3
0x140010f8f  mov     [rdi+8], cx
0x140010f93  mov     rcx, rdi; MemoryDescriptorList
0x140010f96  mov     [rdi+2Ch], r8d
0x140010f9a  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140010fa1  nop     dword ptr [rax+rax+00h]
0x140010fa6  mov     r15, [rsp+78h+arg_0]
0x140010fae  mov     r9d, ebp
0x140010fb1  mov     r8d, [rsp+78h+arg_10]
0x140010fb9  cmp     esi, ebp
0x140010fbb  mov     qword ptr [rdi], 0
0x140010fc2  mov     rdx, rdi; MdlChain
0x140010fc5  cmovb   r9d, esi
0x140010fc9  add     r8d, 8
0x140010fcd  add     r8d, [r15+84h]; DataOffset
0x140010fd4  add     r9d, [rsp+78h+arg_18]; DataLength
0x140010fdc  mov     rcx, [r15+38h]; PoolHandle
0x140010fe0  call    cs:__imp_NdisAllocateNetBuffer
0x140010fe7  nop     dword ptr [rax+rax+00h]
0x140010fec  test    rax, rax
0x140010fef  jz      short loc_140011023
0x140010ff1  mov     edx, [rsp+78h+arg_10]
0x140010ff8  cmp     esi, ebp
0x140010ffa  mov     r8d, [rsp+78h+arg_18]
0x140011002  mov     r14, rax
0x140011005  mov     qword ptr [rax], 0
0x14001100c  mov     [rsp+78h+arg_8], rax
0x140011014  mov     eax, ebp
0x140011016  cmovb   eax, esi
0x140011019  sub     esi, eax
0x14001101b  inc     r13d
0x14001101e  jmp     loc_140010E55
0x140011023  mov     ebx, 0C000009Ah
0x140011028  test    rdi, rdi
0x14001102b  jz      short loc_140011063
0x14001102d  lea     rcx, [rdi-10h]; P
0x140011031  mov     rax, [rcx]
0x140011034  test    rax, rax
0x140011037  jz      short loc_14001104D
0x140011039  mov     rdx, rcx; Entry
0x14001103c  mov     rcx, rax; Lookaside
0x14001103f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140011046  nop     dword ptr [rax+rax+00h]
0x14001104b  jmp     short loc_140011063
0x14001104d  mov     edx, [rcx+8]; Tag
0x140011050  call    cs:__imp_ExFreePoolWithTag
0x140011057  nop     dword ptr [rax+rax+00h]
0x14001105c  jmp     short loc_140011063
0x14001105e  mov     ebx, 0C000009Ah
0x140011063  test    r14, r14
0x140011066  jz      short loc_140011075
0x140011068  lea     rcx, [rsp+78h+arg_8]; struct _NET_BUFFER **
0x140011070  call    ?SafeModeFreeNBChainAndMdls@@YAXPEAPEAU_NET_BUFFER@@@Z; SafeModeFreeNBChainAndMdls(_NET_BUFFER * *)
0x140011075  mov     eax, ebx
0x140011077  jmp     short loc_140011086
0x140011079  mov     rax, [rsp+78h+arg_20]
0x140011081  mov     [rax], r14
0x140011084  xor     eax, eax
0x140011086  add     rsp, 38h
0x14001108a  pop     r15
0x14001108c  pop     r14
0x14001108e  pop     r13
0x140011090  pop     r12
0x140011092  pop     rdi
0x140011093  pop     rsi
0x140011094  pop     rbp
0x140011095  pop     rbx
0x140011096  retn
```
