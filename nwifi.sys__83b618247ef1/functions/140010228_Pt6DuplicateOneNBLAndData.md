# Pt6DuplicateOneNBLAndData

- ea: `0x140010228`
- end: `0x14001051a`
- name: `Pt6DuplicateOneNBLAndData`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000f440`

## callees

- `0x140010228`
- `0x140010520`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001037c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001037c`
- `ntoskrnl!MmSizeOfMdl` at `0x140010288`
- `ntoskrnl!MmSizeOfMdl` at `0x140010288`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400102ea`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400102ea`
- `ntoskrnl!ExAllocatePool2` at `0x140010305`
- `ntoskrnl!ExAllocatePool2` at `0x140010305`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010480`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400104c5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010480`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400104c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010491`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010491`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104d6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010400`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010400`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400103cb`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400103cb`
- `NDIS!NdisAllocateNetBuffer` at `0x140010394`
- `NDIS!NdisAllocateNetBuffer` at `0x140010394`
- `NDIS!NdisFreeNetBuffer` at `0x1400104e5`
- `NDIS!NdisFreeNetBuffer` at `0x1400104e5`

## pseudocode

```c
__int64 __fastcall Pt6DuplicateOneNBLAndData(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *v3; // r14
  struct _NET_BUFFER *Alignment; // rbx
  PNET_BUFFER *p_Next; // r15
  __int64 i; // rax
  __int64 v7; // rbp
  void *v8; // r13
  int v9; // esi
  __int64 v10; // r9
  unsigned int v11; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  char *Pool2; // rax
  struct _MDL *v14; // rdi
  PNET_BUFFER NetBuffer; // rax
  PNET_BUFFER v16; // rsi
  _MDL *MdlChain; // rcx
  PVOID MappedSystemVa; // rax
  unsigned int v19; // edx
  unsigned int v20; // edi
  struct _NET_BUFFER *v21; // rsi
  _MDL *v22; // rcx
  ULONG *p_StartVa; // rcx
  struct _MDL *v25; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v27; // [rsp+98h] [rbp+10h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+18h]
  unsigned int v29; // [rsp+A8h] [rbp+20h] BYREF

  v28 = a3;
  v3 = *(__int64 **)(a2 + 8);
  Alignment = 0;
  p_Next = 0;
  for ( i = a1; ; i = a1 )
  {
    if ( !v3 )
    {
      *(_QWORD *)(v28 + 8) = Alignment;
      return 0;
    }
    v7 = *((unsigned int *)v3 + 6);
    v27 = 0;
    v29 = 0;
    if ( (unsigned int)v7 > 0x1F3B )
      break;
    v8 = *(void **)(i + 72);
    v9 = (MmSizeOfMdl((PVOID)0xFFF, (unsigned int)v7) + 7) & 0xFFFFFFF8;
    v11 = v7 + v9 + 16;
    if ( v11 < 0x10 )
      break;
    if ( v11 <= 0x40 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_13:
      Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
      goto LABEL_15;
    }
    if ( v11 <= 0x100 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      goto LABEL_13;
    }
    if ( v11 <= 0x400 )
    {
      p_DeviceQueue = &Lookaside;
      goto LABEL_13;
    }
    if ( v11 <= 0x800 )
    {
      p_DeviceQueue = &stru_1400B0180;
      goto LABEL_13;
    }
    p_DeviceQueue = 0;
    Pool2 = (char *)ExAllocatePool2(64, v11, 1902736247, v10);
LABEL_15:
    if ( !Pool2 )
      break;
    *(_QWORD *)Pool2 = p_DeviceQueue;
    v14 = (struct _MDL *)(Pool2 + 16);
    *((_DWORD *)Pool2 + 2) = 1902736247;
    if ( Pool2 != (char *)-16LL )
    {
      v14->Next = 0;
      *((_DWORD *)Pool2 + 14) = v7;
      *((_WORD *)Pool2 + 13) = 0;
      *((_QWORD *)Pool2 + 6) = (unsigned __int64)&Pool2[v9 + 16] & 0xFFFFFFFFFFFFF000uLL;
      *((_DWORD *)Pool2 + 15) = ((_DWORD)Pool2 + 16 + v9) & 0xFFF;
      *((_WORD *)Pool2 + 12) = 8 * (((v7 + (((int)Pool2 + 16 + v9) & 0xFFFuLL) + 4095) >> 12) + 6);
      MmBuildMdlForNonPagedPool(v14);
    }
    NetBuffer = NdisAllocateNetBuffer(v8, v14, v7, 0);
    v16 = NetBuffer;
    if ( !NetBuffer )
    {
      if ( v14 )
      {
        if ( v14[-1].StartVa )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v14[-1].StartVa, &v14[-1].StartVa);
        else
          ExFreePoolWithTag(&v14[-1].StartVa, v14[-1].ByteCount);
      }
      break;
    }
    NetBuffer->Link.Alignment = 0;
    if ( Alignment )
      *p_Next = NetBuffer;
    else
      Alignment = NetBuffer;
    NdisRetreatNetBufferDataStart(NetBuffer, v7, 0, 0);
    MdlChain = v16->MdlChain;
    if ( (MdlChain->MdlFlags & 5) != 0 )
      MappedSystemVa = MdlChain->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlChain, 0, MmCached, 0, 0, 0x40000010u);
    if ( !MappedSystemVa )
      break;
    v19 = *((_DWORD *)v3 + 10);
    v25 = (struct _MDL *)v3[4];
    v20 = Dot11CopyMdlToBuffer(&v25, v19, MappedSystemVa, v7, &v29, &v27);
    if ( v20 )
      goto LABEL_38;
    v3 = (__int64 *)*v3;
    p_Next = &v16->Next;
  }
  v20 = -1073741670;
LABEL_38:
  while ( Alignment )
  {
    v21 = Alignment;
    Alignment = (struct _NET_BUFFER *)Alignment->Link.Alignment;
    v22 = v21->MdlChain;
    if ( v22 )
    {
      p_StartVa = (ULONG *)&v22[-1].StartVa;
      if ( *(_QWORD *)p_StartVa )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_StartVa, p_StartVa);
      else
        ExFreePoolWithTag(p_StartVa, p_StartVa[2]);
    }
    NdisFreeNetBuffer(v21);
  }
  return v20;
}

```

## disassembly

```asm
0x140010228  mov     [rsp+arg_10], r8
0x14001022d  mov     [rsp+arg_0], rcx
0x140010232  push    rbx
0x140010233  push    rbp
0x140010234  push    rsi
0x140010235  push    rdi
0x140010236  push    r12
0x140010238  push    r13
0x14001023a  push    r14
0x14001023c  push    r15
0x14001023e  sub     rsp, 48h
0x140010242  mov     r14, [rdx+8]
0x140010246  xor     ebx, ebx
0x140010248  xor     r15d, r15d
0x14001024b  mov     rax, rcx
0x14001024e  test    r14, r14
0x140010251  jz      loc_1400104FA
0x140010257  mov     ebp, [r14+18h]
0x14001025b  mov     [rsp+88h+arg_8], 0
0x140010266  mov     [rsp+88h+arg_18], 0
0x140010271  cmp     ebp, 1F3Bh
0x140010277  ja      loc_14001049D
0x14001027d  mov     r13, [rax+48h]
0x140010281  mov     edx, ebp; Length
0x140010283  mov     ecx, 0FFFh; Base
0x140010288  call    cs:__imp_MmSizeOfMdl
0x14001028f  nop     dword ptr [rax+rax+00h]
0x140010294  lea     esi, [rax+7]
0x140010297  and     esi, 0FFFFFFF8h
0x14001029a  lea     ecx, [rsi+10h]
0x14001029d  add     ecx, ebp
0x14001029f  cmp     ecx, 10h
0x1400102a2  jb      loc_14001049D
0x1400102a8  cmp     ecx, 40h ; '@'
0x1400102ab  ja      short loc_1400102B6
0x1400102ad  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x1400102b4  jmp     short loc_1400102E7
0x1400102b6  cmp     ecx, 100h
0x1400102bc  ja      short loc_1400102C7
0x1400102be  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400102c5  jmp     short loc_1400102E7
0x1400102c7  cmp     ecx, 400h
0x1400102cd  ja      short loc_1400102D8
0x1400102cf  lea     rdi, Lookaside
0x1400102d6  jmp     short loc_1400102E7
0x1400102d8  cmp     ecx, 800h
0x1400102de  ja      short loc_1400102F8
0x1400102e0  lea     rdi, stru_1400B0180
0x1400102e7  mov     rcx, rdi; Lookaside
0x1400102ea  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400102f1  nop     dword ptr [rax+rax+00h]
0x1400102f6  jmp     short loc_140010311
0x1400102f8  xor     edi, edi
0x1400102fa  mov     edx, ecx
0x1400102fc  mov     r8d, 71697377h
0x140010302  lea     ecx, [rdi+40h]
0x140010305  call    cs:__imp_ExAllocatePool2
0x14001030c  nop     dword ptr [rax+rax+00h]
0x140010311  test    rax, rax
0x140010314  jz      loc_14001049D
0x14001031a  mov     [rax], rdi
0x14001031d  lea     rdi, [rax+10h]
0x140010321  mov     dword ptr [rax+8], 71697377h
0x140010328  test    rdi, rdi
0x14001032b  jz      short loc_140010388
0x14001032d  mov     r9d, 0FFFh
0x140010333  mov     edx, esi
0x140010335  add     rdx, rdi
0x140010338  mov     qword ptr [rdi], 0
0x14001033f  mov     r8d, edx
0x140010342  mov     [rdi+28h], ebp
0x140010345  mov     ecx, r8d
0x140010348  xor     eax, eax
0x14001034a  and     rcx, r9
0x14001034d  mov     [rdi+0Ah], ax
0x140010351  add     rcx, r9
0x140010354  and     rdx, 0FFFFFFFFFFFFF000h
0x14001035b  add     rcx, rbp
0x14001035e  mov     [rdi+20h], rdx
0x140010362  shr     rcx, 0Ch
0x140010366  and     r8d, r9d
0x140010369  add     cx, 6
0x14001036d  mov     [rdi+2Ch], r8d
0x140010371  shl     cx, 3
0x140010375  mov     [rdi+8], cx
0x140010379  mov     rcx, rdi; MemoryDescriptorList
0x14001037c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140010383  nop     dword ptr [rax+rax+00h]
0x140010388  xor     r9d, r9d; DataLength
0x14001038b  mov     r8d, ebp; DataOffset
0x14001038e  mov     rdx, rdi; MdlChain
0x140010391  mov     rcx, r13; PoolHandle
0x140010394  call    cs:__imp_NdisAllocateNetBuffer
0x14001039b  nop     dword ptr [rax+rax+00h]
0x1400103a0  mov     rsi, rax
0x1400103a3  test    rax, rax
0x1400103a6  jz      loc_140010469
0x1400103ac  mov     qword ptr [rax], 0
0x1400103b3  test    rbx, rbx
0x1400103b6  jnz     short loc_1400103BD
0x1400103b8  mov     rbx, rax
0x1400103bb  jmp     short loc_1400103C0
0x1400103bd  mov     [r15], rsi
0x1400103c0  xor     r9d, r9d; AllocateMdlHandler
0x1400103c3  xor     r8d, r8d; DataBackFill
0x1400103c6  mov     edx, ebp; DataOffsetDelta
0x1400103c8  mov     rcx, rsi; NetBuffer
0x1400103cb  call    cs:__imp_NdisRetreatNetBufferDataStart
0x1400103d2  nop     dword ptr [rax+rax+00h]
0x1400103d7  mov     rcx, [rsi+20h]; MemoryDescriptorList
0x1400103db  test    byte ptr [rcx+0Ah], 5
0x1400103df  jz      short loc_1400103E7
0x1400103e1  mov     rax, [rcx+18h]
0x1400103e5  jmp     short loc_14001040C
0x1400103e7  xor     r9d, r9d; RequestedAddress
0x1400103ea  mov     [rsp+88h+Priority], 40000010h; Priority
0x1400103f2  xor     edx, edx; AccessMode
0x1400103f4  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400103fc  lea     r8d, [r9+1]; CacheType
0x140010400  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140010407  nop     dword ptr [rax+rax+00h]
0x14001040c  test    rax, rax
0x14001040f  jz      loc_14001049D
0x140010415  mov     rcx, [r14+20h]
0x140010419  mov     r9d, ebp; unsigned int
0x14001041c  mov     edx, [r14+28h]; unsigned int
0x140010420  mov     r8, rax; void *
0x140010423  mov     [rsp+88h+var_58], rcx
0x140010428  lea     rcx, [rsp+88h+arg_8]
0x140010430  mov     qword ptr [rsp+88h+Priority], rcx; unsigned int *
0x140010435  lea     rcx, [rsp+88h+arg_18]
0x14001043d  mov     qword ptr [rsp+88h+BugCheckOnFailure], rcx; unsigned int *
0x140010442  lea     rcx, [rsp+88h+var_58]; struct _MDL **
0x140010447  call    ?Dot11CopyMdlToBuffer@@YAHPEAPEAU_MDL@@KPEAXKPEAK2@Z; Dot11CopyMdlToBuffer(_MDL * *,ulong,void *,ulong,ulong *,ulong *)
0x14001044c  mov     edi, eax
0x14001044e  test    eax, eax
0x140010450  jnz     loc_1400104F1
0x140010456  mov     r14, [r14]
0x140010459  mov     r15, rsi
0x14001045c  mov     rax, [rsp+88h+arg_0]
0x140010464  jmp     loc_14001024E
0x140010469  test    rdi, rdi
0x14001046c  jz      short loc_14001049D
0x14001046e  lea     rcx, [rdi-10h]; P
0x140010472  mov     rax, [rcx]
0x140010475  test    rax, rax
0x140010478  jz      short loc_14001048E
0x14001047a  mov     rdx, rcx; Entry
0x14001047d  mov     rcx, rax; Lookaside
0x140010480  call    cs:__imp_ExFreeToNPagedLookasideList
0x140010487  nop     dword ptr [rax+rax+00h]
0x14001048c  jmp     short loc_14001049D
0x14001048e  mov     edx, [rcx+8]; Tag
0x140010491  call    cs:__imp_ExFreePoolWithTag
0x140010498  nop     dword ptr [rax+rax+00h]
0x14001049d  mov     edi, 0C000009Ah
0x1400104a2  jmp     short loc_1400104F1
0x1400104a4  mov     rsi, rbx
0x1400104a7  mov     rbx, [rbx]
0x1400104aa  mov     rcx, [rsi+20h]
0x1400104ae  test    rcx, rcx
0x1400104b1  jz      short loc_1400104E2
0x1400104b3  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400104b7  mov     rax, [rcx]
0x1400104ba  test    rax, rax
0x1400104bd  jz      short loc_1400104D3
0x1400104bf  mov     rdx, rcx; Entry
0x1400104c2  mov     rcx, rax; Lookaside
0x1400104c5  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400104cc  nop     dword ptr [rax+rax+00h]
0x1400104d1  jmp     short loc_1400104E2
0x1400104d3  mov     edx, [rcx+8]; Tag
0x1400104d6  call    cs:__imp_ExFreePoolWithTag
0x1400104dd  nop     dword ptr [rax+rax+00h]
0x1400104e2  mov     rcx, rsi; NetBuffer
0x1400104e5  call    cs:__imp_NdisFreeNetBuffer
0x1400104ec  nop     dword ptr [rax+rax+00h]
0x1400104f1  test    rbx, rbx
0x1400104f4  jnz     short loc_1400104A4
0x1400104f6  mov     eax, edi
0x1400104f8  jmp     short loc_140010508
0x1400104fa  mov     rax, [rsp+88h+arg_10]
0x140010502  mov     [rax+8], rbx
0x140010506  xor     eax, eax
0x140010508  add     rsp, 48h
0x14001050c  pop     r15
0x14001050e  pop     r14
0x140010510  pop     r13
0x140010512  pop     r12
0x140010514  pop     rdi
0x140010515  pop     rsi
0x140010516  pop     rbp
0x140010517  pop     rbx
0x140010518  retn
```
