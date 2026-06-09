# Pt6DuplicateOneNBLAndData

- ea: `0x140010218`
- end: `0x14001050a`
- name: `Pt6DuplicateOneNBLAndData`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000f430`

## callees

- `0x140010218`
- `0x140010510`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001036c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001036c`
- `ntoskrnl!MmSizeOfMdl` at `0x140010278`
- `ntoskrnl!MmSizeOfMdl` at `0x140010278`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400102da`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400102da`
- `ntoskrnl!ExAllocatePool2` at `0x1400102f5`
- `ntoskrnl!ExAllocatePool2` at `0x1400102f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010470`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400104b5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010470`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400104b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010481`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010481`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104c6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400103f0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400103f0`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400103bb`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400103bb`
- `NDIS!NdisAllocateNetBuffer` at `0x140010384`
- `NDIS!NdisAllocateNetBuffer` at `0x140010384`
- `NDIS!NdisFreeNetBuffer` at `0x1400104d5`
- `NDIS!NdisFreeNetBuffer` at `0x1400104d5`

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
  unsigned int v10; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  char *Pool2; // rax
  struct _MDL *v13; // rdi
  PNET_BUFFER NetBuffer; // rax
  PNET_BUFFER v15; // rsi
  _MDL *MdlChain; // rcx
  PVOID MappedSystemVa; // rax
  unsigned int v18; // edx
  unsigned int v19; // edi
  struct _NET_BUFFER *v20; // rsi
  _MDL *v21; // rcx
  ULONG *p_StartVa; // rcx
  struct _MDL *v24; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v26; // [rsp+98h] [rbp+10h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+18h]
  unsigned int v28; // [rsp+A8h] [rbp+20h] BYREF

  v27 = a3;
  v3 = *(__int64 **)(a2 + 8);
  Alignment = 0;
  p_Next = 0;
  for ( i = a1; ; i = a1 )
  {
    if ( !v3 )
    {
      *(_QWORD *)(v27 + 8) = Alignment;
      return 0;
    }
    v7 = *((unsigned int *)v3 + 6);
    v26 = 0;
    v28 = 0;
    if ( (unsigned int)v7 > 0x1F3B )
      break;
    v8 = *(void **)(i + 72);
    v9 = (MmSizeOfMdl((PVOID)0xFFF, (unsigned int)v7) + 7) & 0xFFFFFFF8;
    v10 = v7 + v9 + 16;
    if ( v10 < 0x10 )
      break;
    if ( v10 <= 0x40 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_13:
      Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
      goto LABEL_15;
    }
    if ( v10 <= 0x100 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      goto LABEL_13;
    }
    if ( v10 <= 0x400 )
    {
      p_DeviceQueue = &Lookaside;
      goto LABEL_13;
    }
    if ( v10 <= 0x800 )
    {
      p_DeviceQueue = &stru_1400B31C0;
      goto LABEL_13;
    }
    p_DeviceQueue = 0;
    Pool2 = (char *)ExAllocatePool2(64, v10, 1902736247);
LABEL_15:
    if ( !Pool2 )
      break;
    *(_QWORD *)Pool2 = p_DeviceQueue;
    v13 = (struct _MDL *)(Pool2 + 16);
    *((_DWORD *)Pool2 + 2) = 1902736247;
    if ( Pool2 != (char *)-16LL )
    {
      v13->Next = 0;
      *((_DWORD *)Pool2 + 14) = v7;
      *((_WORD *)Pool2 + 13) = 0;
      *((_QWORD *)Pool2 + 6) = (unsigned __int64)&Pool2[v9 + 16] & 0xFFFFFFFFFFFFF000uLL;
      *((_DWORD *)Pool2 + 15) = ((_DWORD)Pool2 + 16 + v9) & 0xFFF;
      *((_WORD *)Pool2 + 12) = 8 * (((v7 + (((int)Pool2 + 16 + v9) & 0xFFFuLL) + 4095) >> 12) + 6);
      MmBuildMdlForNonPagedPool(v13);
    }
    NetBuffer = NdisAllocateNetBuffer(v8, v13, v7, 0);
    v15 = NetBuffer;
    if ( !NetBuffer )
    {
      if ( v13 )
      {
        if ( v13[-1].StartVa )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v13[-1].StartVa, &v13[-1].StartVa);
        else
          ExFreePoolWithTag(&v13[-1].StartVa, v13[-1].ByteCount);
      }
      break;
    }
    NetBuffer->Link.Alignment = 0;
    if ( Alignment )
      *p_Next = NetBuffer;
    else
      Alignment = NetBuffer;
    NdisRetreatNetBufferDataStart(NetBuffer, v7, 0, 0);
    MdlChain = v15->MdlChain;
    if ( (MdlChain->MdlFlags & 5) != 0 )
      MappedSystemVa = MdlChain->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlChain, 0, MmCached, 0, 0, 0x40000010u);
    if ( !MappedSystemVa )
      break;
    v18 = *((_DWORD *)v3 + 10);
    v24 = (struct _MDL *)v3[4];
    v19 = Dot11CopyMdlToBuffer(&v24, v18, MappedSystemVa, v7, &v28, &v26);
    if ( v19 )
      goto LABEL_38;
    v3 = (__int64 *)*v3;
    p_Next = &v15->Next;
  }
  v19 = -1073741670;
LABEL_38:
  while ( Alignment )
  {
    v20 = Alignment;
    Alignment = (struct _NET_BUFFER *)Alignment->Link.Alignment;
    v21 = v20->MdlChain;
    if ( v21 )
    {
      p_StartVa = (ULONG *)&v21[-1].StartVa;
      if ( *(_QWORD *)p_StartVa )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_StartVa, p_StartVa);
      else
        ExFreePoolWithTag(p_StartVa, p_StartVa[2]);
    }
    NdisFreeNetBuffer(v20);
  }
  return v19;
}

```

## disassembly

```asm
0x140010218  mov     [rsp+arg_10], r8
0x14001021d  mov     [rsp+arg_0], rcx
0x140010222  push    rbx
0x140010223  push    rbp
0x140010224  push    rsi
0x140010225  push    rdi
0x140010226  push    r12
0x140010228  push    r13
0x14001022a  push    r14
0x14001022c  push    r15
0x14001022e  sub     rsp, 48h
0x140010232  mov     r14, [rdx+8]
0x140010236  xor     ebx, ebx
0x140010238  xor     r15d, r15d
0x14001023b  mov     rax, rcx
0x14001023e  test    r14, r14
0x140010241  jz      loc_1400104EA
0x140010247  mov     ebp, [r14+18h]
0x14001024b  mov     [rsp+88h+arg_8], 0
0x140010256  mov     [rsp+88h+arg_18], 0
0x140010261  cmp     ebp, 1F3Bh
0x140010267  ja      loc_14001048D
0x14001026d  mov     r13, [rax+48h]
0x140010271  mov     edx, ebp; Length
0x140010273  mov     ecx, 0FFFh; Base
0x140010278  call    cs:__imp_MmSizeOfMdl
0x14001027f  nop     dword ptr [rax+rax+00h]
0x140010284  lea     esi, [rax+7]
0x140010287  and     esi, 0FFFFFFF8h
0x14001028a  lea     ecx, [rsi+10h]
0x14001028d  add     ecx, ebp
0x14001028f  cmp     ecx, 10h
0x140010292  jb      loc_14001048D
0x140010298  cmp     ecx, 40h ; '@'
0x14001029b  ja      short loc_1400102A6
0x14001029d  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x1400102a4  jmp     short loc_1400102D7
0x1400102a6  cmp     ecx, 100h
0x1400102ac  ja      short loc_1400102B7
0x1400102ae  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400102b5  jmp     short loc_1400102D7
0x1400102b7  cmp     ecx, 400h
0x1400102bd  ja      short loc_1400102C8
0x1400102bf  lea     rdi, Lookaside
0x1400102c6  jmp     short loc_1400102D7
0x1400102c8  cmp     ecx, 800h
0x1400102ce  ja      short loc_1400102E8
0x1400102d0  lea     rdi, stru_1400B31C0
0x1400102d7  mov     rcx, rdi; Lookaside
0x1400102da  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400102e1  nop     dword ptr [rax+rax+00h]
0x1400102e6  jmp     short loc_140010301
0x1400102e8  xor     edi, edi
0x1400102ea  mov     edx, ecx
0x1400102ec  mov     r8d, 71697377h
0x1400102f2  lea     ecx, [rdi+40h]
0x1400102f5  call    cs:__imp_ExAllocatePool2
0x1400102fc  nop     dword ptr [rax+rax+00h]
0x140010301  test    rax, rax
0x140010304  jz      loc_14001048D
0x14001030a  mov     [rax], rdi
0x14001030d  lea     rdi, [rax+10h]
0x140010311  mov     dword ptr [rax+8], 71697377h
0x140010318  test    rdi, rdi
0x14001031b  jz      short loc_140010378
0x14001031d  mov     r9d, 0FFFh
0x140010323  mov     edx, esi
0x140010325  add     rdx, rdi
0x140010328  mov     qword ptr [rdi], 0
0x14001032f  mov     r8d, edx
0x140010332  mov     [rdi+28h], ebp
0x140010335  mov     ecx, r8d
0x140010338  xor     eax, eax
0x14001033a  and     rcx, r9
0x14001033d  mov     [rdi+0Ah], ax
0x140010341  add     rcx, r9
0x140010344  and     rdx, 0FFFFFFFFFFFFF000h
0x14001034b  add     rcx, rbp
0x14001034e  mov     [rdi+20h], rdx
0x140010352  shr     rcx, 0Ch
0x140010356  and     r8d, r9d
0x140010359  add     cx, 6
0x14001035d  mov     [rdi+2Ch], r8d
0x140010361  shl     cx, 3
0x140010365  mov     [rdi+8], cx
0x140010369  mov     rcx, rdi; MemoryDescriptorList
0x14001036c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140010373  nop     dword ptr [rax+rax+00h]
0x140010378  xor     r9d, r9d; DataLength
0x14001037b  mov     r8d, ebp; DataOffset
0x14001037e  mov     rdx, rdi; MdlChain
0x140010381  mov     rcx, r13; PoolHandle
0x140010384  call    cs:__imp_NdisAllocateNetBuffer
0x14001038b  nop     dword ptr [rax+rax+00h]
0x140010390  mov     rsi, rax
0x140010393  test    rax, rax
0x140010396  jz      loc_140010459
0x14001039c  mov     qword ptr [rax], 0
0x1400103a3  test    rbx, rbx
0x1400103a6  jnz     short loc_1400103AD
0x1400103a8  mov     rbx, rax
0x1400103ab  jmp     short loc_1400103B0
0x1400103ad  mov     [r15], rsi
0x1400103b0  xor     r9d, r9d; AllocateMdlHandler
0x1400103b3  xor     r8d, r8d; DataBackFill
0x1400103b6  mov     edx, ebp; DataOffsetDelta
0x1400103b8  mov     rcx, rsi; NetBuffer
0x1400103bb  call    cs:__imp_NdisRetreatNetBufferDataStart
0x1400103c2  nop     dword ptr [rax+rax+00h]
0x1400103c7  mov     rcx, [rsi+20h]; MemoryDescriptorList
0x1400103cb  test    byte ptr [rcx+0Ah], 5
0x1400103cf  jz      short loc_1400103D7
0x1400103d1  mov     rax, [rcx+18h]
0x1400103d5  jmp     short loc_1400103FC
0x1400103d7  xor     r9d, r9d; RequestedAddress
0x1400103da  mov     [rsp+88h+Priority], 40000010h; Priority
0x1400103e2  xor     edx, edx; AccessMode
0x1400103e4  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400103ec  lea     r8d, [r9+1]; CacheType
0x1400103f0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400103f7  nop     dword ptr [rax+rax+00h]
0x1400103fc  test    rax, rax
0x1400103ff  jz      loc_14001048D
0x140010405  mov     rcx, [r14+20h]
0x140010409  mov     r9d, ebp; unsigned int
0x14001040c  mov     edx, [r14+28h]; unsigned int
0x140010410  mov     r8, rax; void *
0x140010413  mov     [rsp+88h+var_58], rcx
0x140010418  lea     rcx, [rsp+88h+arg_8]
0x140010420  mov     qword ptr [rsp+88h+Priority], rcx; unsigned int *
0x140010425  lea     rcx, [rsp+88h+arg_18]
0x14001042d  mov     qword ptr [rsp+88h+BugCheckOnFailure], rcx; unsigned int *
0x140010432  lea     rcx, [rsp+88h+var_58]; struct _MDL **
0x140010437  call    ?Dot11CopyMdlToBuffer@@YAHPEAPEAU_MDL@@KPEAXKPEAK2@Z; Dot11CopyMdlToBuffer(_MDL * *,ulong,void *,ulong,ulong *,ulong *)
0x14001043c  mov     edi, eax
0x14001043e  test    eax, eax
0x140010440  jnz     loc_1400104E1
0x140010446  mov     r14, [r14]
0x140010449  mov     r15, rsi
0x14001044c  mov     rax, [rsp+88h+arg_0]
0x140010454  jmp     loc_14001023E
0x140010459  test    rdi, rdi
0x14001045c  jz      short loc_14001048D
0x14001045e  lea     rcx, [rdi-10h]; P
0x140010462  mov     rax, [rcx]
0x140010465  test    rax, rax
0x140010468  jz      short loc_14001047E
0x14001046a  mov     rdx, rcx; Entry
0x14001046d  mov     rcx, rax; Lookaside
0x140010470  call    cs:__imp_ExFreeToNPagedLookasideList
0x140010477  nop     dword ptr [rax+rax+00h]
0x14001047c  jmp     short loc_14001048D
0x14001047e  mov     edx, [rcx+8]; Tag
0x140010481  call    cs:__imp_ExFreePoolWithTag
0x140010488  nop     dword ptr [rax+rax+00h]
0x14001048d  mov     edi, 0C000009Ah
0x140010492  jmp     short loc_1400104E1
0x140010494  mov     rsi, rbx
0x140010497  mov     rbx, [rbx]
0x14001049a  mov     rcx, [rsi+20h]
0x14001049e  test    rcx, rcx
0x1400104a1  jz      short loc_1400104D2
0x1400104a3  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400104a7  mov     rax, [rcx]
0x1400104aa  test    rax, rax
0x1400104ad  jz      short loc_1400104C3
0x1400104af  mov     rdx, rcx; Entry
0x1400104b2  mov     rcx, rax; Lookaside
0x1400104b5  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400104bc  nop     dword ptr [rax+rax+00h]
0x1400104c1  jmp     short loc_1400104D2
0x1400104c3  mov     edx, [rcx+8]; Tag
0x1400104c6  call    cs:__imp_ExFreePoolWithTag
0x1400104cd  nop     dword ptr [rax+rax+00h]
0x1400104d2  mov     rcx, rsi; NetBuffer
0x1400104d5  call    cs:__imp_NdisFreeNetBuffer
0x1400104dc  nop     dword ptr [rax+rax+00h]
0x1400104e1  test    rbx, rbx
0x1400104e4  jnz     short loc_140010494
0x1400104e6  mov     eax, edi
0x1400104e8  jmp     short loc_1400104F8
0x1400104ea  mov     rax, [rsp+88h+arg_10]
0x1400104f2  mov     [rax+8], rbx
0x1400104f6  xor     eax, eax
0x1400104f8  add     rsp, 48h
0x1400104fc  pop     r15
0x1400104fe  pop     r14
0x140010500  pop     r13
0x140010502  pop     r12
0x140010504  pop     rdi
0x140010505  pop     rsi
0x140010506  pop     rbp
0x140010507  pop     rbx
0x140010508  retn
```
