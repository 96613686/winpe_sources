# SafeModeSplitAMSDUToNBList(_VELAN *,_NET_BUFFER *,_NET_BUFFER * *)

- ea: `0x14000e654`
- end: `0x14000eaca`
- name: `?SafeModeSplitAMSDUToNBList@@YAJPEAU_VELAN@@PEAU_NET_BUFFER@@PEAPEAU2@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(struct _VELAN *, struct _NET_BUFFER *, struct _NET_BUFFER **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140031ce8`

## callees

- `0x14000e654`
- `0x140010520`
- `0x140011418`
- `0x140019394`
- `0x140019440`
- `0x140032198`
- `0x14009a3d0`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000e8e3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000e8e3`
- `ntoskrnl!MmSizeOfMdl` at `0x14000e7e4`
- `ntoskrnl!MmSizeOfMdl` at `0x14000e7e4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000e841`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000e841`
- `ntoskrnl!ExAllocatePool2` at `0x14000e85c`
- `ntoskrnl!ExAllocatePool2` at `0x14000e85c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e6e3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e6e3`
- `NDIS!NdisAllocateNetBuffer` at `0x14000e908`
- `NDIS!NdisAllocateNetBuffer` at `0x14000e908`

## pseudocode

```c
__int64 __fastcall SafeModeSplitAMSDUToNBList(struct _VELAN *a1, struct _NET_BUFFER *a2, struct _NET_BUFFER **a3)
{
  _MDL *CurrentMdl; // rbx
  __int64 CurrentMdlOffset; // rdi
  struct _NET_BUFFER *v5; // r12
  unsigned int DataLength; // esi
  struct _NET_BUFFER *v7; // r14
  bool v8; // zf
  PVOID MappedSystemVa; // rax
  unsigned int v10; // ebx
  __int16 *v11; // r15
  unsigned int v12; // eax
  unsigned int v13; // edi
  int v14; // esi
  unsigned int v15; // ebx
  unsigned int v16; // edi
  unsigned __int16 v17; // si
  int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  unsigned int v21; // edi
  __int64 v22; // r9
  unsigned int v23; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  int v26; // r13d
  struct _MDL *v27; // rsi
  size_t v28; // rbx
  char *v29; // rcx
  unsigned int v30; // eax
  struct _VELAN *v31; // rax
  PNET_BUFFER NetBuffer; // rax
  char *v33; // rdi
  char *v34; // r8
  unsigned int v35; // edi
  unsigned int v36; // ebx
  struct _MDL *v37; // rax
  __int16 v38; // dx
  __int16 v39; // r8
  int v40; // r9d
  __int16 v41; // cx
  struct _NET_BUFFER **p_Next; // rax
  unsigned int v44; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v45; // [rsp+34h] [rbp-45h] BYREF
  unsigned int v46; // [rsp+38h] [rbp-41h] BYREF
  unsigned int Size; // [rsp+3Ch] [rbp-3Dh]
  unsigned int Size_4; // [rsp+40h] [rbp-39h]
  int v49; // [rsp+44h] [rbp-35h]
  struct _MDL *v50; // [rsp+48h] [rbp-31h] BYREF
  struct _NET_BUFFER *v51; // [rsp+50h] [rbp-29h]
  struct _NET_BUFFER *v52; // [rsp+58h] [rbp-21h] BYREF
  _MDL *v53; // [rsp+60h] [rbp-19h]
  struct _NET_BUFFER *v54; // [rsp+68h] [rbp-11h] BYREF
  struct _VELAN *v55; // [rsp+70h] [rbp-9h]
  struct _NET_BUFFER **v56; // [rsp+78h] [rbp-1h]
  _BYTE v57[12]; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int16 v58; // [rsp+8Ch] [rbp+13h]
  char v59; // [rsp+90h] [rbp+17h] BYREF
  int v60; // [rsp+91h] [rbp+18h]
  _BYTE v61[3]; // [rsp+95h] [rbp+1Ch] BYREF

  CurrentMdl = a2->CurrentMdl;
  CurrentMdlOffset = a2->CurrentMdlOffset;
  v5 = 0;
  DataLength = a2->DataLength;
  v7 = 0;
  v56 = a3;
  v8 = (CurrentMdl->MdlFlags & 5) == 0;
  v55 = a1;
  v50 = CurrentMdl;
  memset(v57, 0, sizeof(v57));
  v58 = 0;
  v59 = 0;
  v60 = 0;
  memset(v61, 0, sizeof(v61));
  v54 = 0;
  v52 = 0;
  v45 = 0;
  if ( v8 )
    MappedSystemVa = MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000010u);
  else
    MappedSystemVa = CurrentMdl->MappedSystemVa;
  if ( !MappedSystemVa )
    return (unsigned int)-1073741670;
  v51 = 0;
  v11 = (__int16 *)((char *)CurrentMdl->MappedSystemVa + CurrentMdlOffset);
  v12 = Dot11DataFrameMacHeaderSize(v11);
  v13 = v12 + CurrentMdlOffset;
  Size = v12;
  v14 = DataLength - v12;
  v15 = v12;
  v49 = v14;
  while ( 1 )
  {
    if ( v14 <= 0 )
    {
      *v56 = v5;
      return 0;
    }
    v46 = 0;
    Dot11CopyMdlToBuffer(&v50, v13, v57, 0xEu, &v46, &v45);
    v16 = v13 + 14;
    v17 = __ROR2__(v58, 8);
    v58 = v17;
    v44 = v16;
    if ( (*v11 & 0x100) == 0 )
    {
      v18 = *((_DWORD *)v11 + 1) - *(_DWORD *)v57;
      if ( !v18 )
        v18 = (unsigned __int16)v11[4] - *(unsigned __int16 *)&v57[4];
      if ( v18 )
      {
        v10 = -1073741762;
        goto LABEL_52;
      }
    }
    Dot11CopyMdlToBuffer(&v50, v16, &v59, 8u, &v46, &v45);
    v19 = 8;
    if ( *(_WORD *)&v61[1] == 129 )
      v19 = 12;
    v20 = v19 + v15;
    Size_4 = v19;
    if ( v20 > 0x1F3B )
    {
      v10 = -1073741670;
      goto LABEL_52;
    }
    v53 = (_MDL *)v20;
    v21 = (MmSizeOfMdl((PVOID)0xFFF, v20) + 7) & 0xFFFFFFF8;
    v23 = v20 + v21 + 16;
    if ( v23 < 0x10 )
    {
LABEL_48:
      v10 = -1073741670;
      goto LABEL_49;
    }
    if ( v23 <= 0x40 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_24:
      Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
      goto LABEL_26;
    }
    if ( v23 <= 0x100 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      goto LABEL_24;
    }
    if ( v23 <= 0x400 )
    {
      p_DeviceQueue = &Lookaside;
      goto LABEL_24;
    }
    if ( v23 <= 0x800 )
    {
      p_DeviceQueue = &stru_1400B0180;
      goto LABEL_24;
    }
    p_DeviceQueue = 0;
    Pool2 = (char *)ExAllocatePool2(64, v23, 828994423, v22);
LABEL_26:
    if ( !Pool2 )
      goto LABEL_48;
    v26 = v17;
    v27 = (struct _MDL *)(Pool2 + 16);
    *(_QWORD *)Pool2 = p_DeviceQueue;
    v28 = Size;
    *((_DWORD *)Pool2 + 2) = 828994423;
    if ( Pool2 != (char *)-16LL )
    {
      v29 = (char *)&v53[85].Reserved + 1;
      v27->Next = 0;
      *((_QWORD *)Pool2 + 6) = ((unsigned __int64)v27 + v21) & 0xFFFFFFFFFFFFF000uLL;
      *((_DWORD *)Pool2 + 15) = ((_DWORD)v27 + v21) & 0xFFF;
      *((_WORD *)Pool2 + 13) = 0;
      v30 = v28 + Size_4;
      v27->Size = 8 * (((unsigned __int64)&v29[((unsigned int)v27 + v21) & 0xFFFLL] >> 12) + 6);
      v27->ByteCount = v30;
      MmBuildMdlForNonPagedPool(v27);
    }
    v31 = v55;
    v27->Next = 0;
    NetBuffer = NdisAllocateNetBuffer(v31->hSendNetBufferPool, v27, 0, (unsigned int)(v28 + v26));
    v52 = NetBuffer;
    v7 = NetBuffer;
    if ( !NetBuffer )
      break;
    NetBuffer->Link.Alignment = 0;
    v53 = NetBuffer->CurrentMdl;
    v33 = (char *)v53->MappedSystemVa;
    memmove(v33, v11, v28);
    v34 = &v33[v28];
    v35 = Size_4;
    Dot11CopyMdlToBuffer(&v50, v44, v34, Size_4, &v46, &v45);
    if ( v45 != v35 )
    {
      v10 = -1073741762;
      goto LABEL_46;
    }
    v44 += v35;
    v36 = (v26 + 17) & 0xFFFFFFFC;
    v37 = SafeModeCloneMdlChain(v26 - v35, &v50, &v44);
    v13 = v44 - 14 + v36 - v26;
    if ( !v37 )
    {
      v10 = -1073741762;
      goto LABEL_49;
    }
    v38 = *v11;
    v39 = *(_WORD *)&v57[10];
    v14 = v49 - v36;
    v40 = *(_DWORD *)&v57[6];
    v41 = (unsigned __int16)*v11 >> 9;
    v49 -= v36;
    if ( (v38 & 0x100) != 0 )
    {
      *((_DWORD *)v11 + 4) = *(_DWORD *)v57;
      v11[10] = *(_WORD *)&v57[4];
    }
    else if ( (v41 & 1) != 0 )
    {
      *((_DWORD *)v11 + 4) = *(_DWORD *)&v57[6];
      v11[10] = v39;
    }
    if ( (v41 & 1) != 0 && (v38 & 0x100) != 0 )
    {
      *((_DWORD *)v11 + 6) = v40;
      v11[14] = v39;
    }
    v53->Next = v37;
    p_Next = &v51->Next;
    v51 = v7;
    if ( p_Next )
    {
      *p_Next = v7;
    }
    else
    {
      v5 = v7;
      v54 = v7;
    }
    v15 = Size;
    v7 = 0;
    v52 = 0;
  }
  v10 = -1073741670;
LABEL_46:
  if ( v27 )
    SafeModeFreeMdlChain(v27);
LABEL_49:
  if ( v7 )
    SafeModeFreeNBChainAndMdls(&v52);
LABEL_52:
  if ( v5 )
    SafeModeFreeNBChainAndMdls(&v54);
  return v10;
}

```

## disassembly

```asm
0x14000e654  mov     [rsp-8+arg_18], rbx
0x14000e659  push    rbp
0x14000e65a  push    rsi
0x14000e65b  push    rdi
0x14000e65c  push    r12
0x14000e65e  push    r13
0x14000e660  push    r14
0x14000e662  push    r15
0x14000e664  lea     rbp, [rsp-27h]
0x14000e669  sub     rsp, 0A0h
0x14000e670  mov     rax, cs:__security_cookie
0x14000e677  xor     rax, rsp
0x14000e67a  mov     [rbp+57h+var_38], rax
0x14000e67e  mov     rbx, [rdx+8]
0x14000e682  xor     eax, eax
0x14000e684  mov     edi, [rdx+10h]
0x14000e687  xor     r12d, r12d
0x14000e68a  mov     esi, [rdx+18h]
0x14000e68d  xor     r14d, r14d
0x14000e690  mov     [rbp+57h+var_58], r8
0x14000e694  test    byte ptr [rbx+0Ah], 5
0x14000e698  mov     [rbp+57h+var_60], rcx
0x14000e69c  mov     [rbp+57h+var_88], rbx
0x14000e6a0  mov     [rbp+57h+var_50], rax
0x14000e6a4  mov     [rbp+57h+var_48], eax
0x14000e6a7  mov     [rbp+57h+var_44], ax
0x14000e6ab  mov     [rbp+57h+var_40], al
0x14000e6ae  mov     [rbp+57h+var_3F], eax
0x14000e6b1  mov     [rbp+57h+var_3B], ax
0x14000e6b5  mov     [rbp+57h+var_39], al
0x14000e6b8  mov     [rbp+57h+var_68], r12
0x14000e6bc  mov     [rbp+57h+var_78], r14
0x14000e6c0  mov     [rbp+57h+var_9C], eax
0x14000e6c3  jz      short loc_14000E6CB
0x14000e6c5  mov     rax, [rbx+18h]
0x14000e6c9  jmp     short loc_14000E6EF
0x14000e6cb  xor     r9d, r9d; RequestedAddress
0x14000e6ce  mov     [rsp+0D0h+Priority], 40000010h; Priority
0x14000e6d6  xor     edx, edx; AccessMode
0x14000e6d8  mov     [rsp+0D0h+BugCheckOnFailure], eax; BugCheckOnFailure
0x14000e6dc  mov     rcx, rbx; MemoryDescriptorList
0x14000e6df  lea     r8d, [r9+1]; CacheType
0x14000e6e3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000e6ea  nop     dword ptr [rax+rax+00h]
0x14000e6ef  test    rax, rax
0x14000e6f2  jnz     short loc_14000E6FE
0x14000e6f4  mov     ebx, 0C000009Ah
0x14000e6f9  jmp     loc_14000EA95
0x14000e6fe  mov     r15, rdi
0x14000e701  mov     [rbp+57h+var_80], r12
0x14000e705  add     r15, [rbx+18h]
0x14000e709  mov     rcx, r15; void *
0x14000e70c  call    ?Dot11DataFrameMacHeaderSize@@YAKPEAX@Z; Dot11DataFrameMacHeaderSize(void *)
0x14000e711  add     edi, eax
0x14000e713  mov     dword ptr [rbp+57h+Size], eax
0x14000e716  sub     esi, eax
0x14000e718  mov     ebx, eax
0x14000e71a  mov     [rbp+57h+var_8C], esi
0x14000e71d  mov     r13d, 100h
0x14000e723  test    esi, esi
0x14000e725  jle     loc_14000EA99
0x14000e72b  lea     rax, [rbp+57h+var_9C]
0x14000e72f  mov     [rbp+57h+var_98], 0
0x14000e736  mov     qword ptr [rsp+0D0h+Priority], rax; unsigned int *
0x14000e73b  lea     r8, [rbp+57h+var_50]; void *
0x14000e73f  lea     rax, [rbp+57h+var_98]
0x14000e743  mov     r9d, 0Eh; unsigned int
0x14000e749  mov     edx, edi; unsigned int
0x14000e74b  mov     qword ptr [rsp+0D0h+BugCheckOnFailure], rax; unsigned int *
0x14000e750  lea     rcx, [rbp+57h+var_88]; struct _MDL **
0x14000e754  call    ?Dot11CopyMdlToBuffer@@YAHPEAPEAU_MDL@@KPEAXKPEAK2@Z; Dot11CopyMdlToBuffer(_MDL * *,ulong,void *,ulong,ulong *,ulong *)
0x14000e759  movzx   esi, [rbp+57h+var_44]
0x14000e75d  add     edi, 0Eh
0x14000e760  ror     si, 8
0x14000e764  mov     [rbp+57h+var_44], si
0x14000e768  mov     [rbp+57h+var_A0], edi
0x14000e76b  test    [r15], r13w
0x14000e76f  jnz     short loc_14000E78D
0x14000e771  mov     ecx, [r15+4]
0x14000e775  sub     ecx, dword ptr [rbp+57h+var_50]
0x14000e778  jnz     short loc_14000E785
0x14000e77a  movzx   ecx, word ptr [r15+8]
0x14000e77f  movzx   eax, word ptr [rbp+57h+var_50+4]
0x14000e783  sub     ecx, eax
0x14000e785  test    ecx, ecx
0x14000e787  jnz     loc_14000EA44
0x14000e78d  lea     rax, [rbp+57h+var_9C]
0x14000e791  mov     r9d, 8; unsigned int
0x14000e797  mov     qword ptr [rsp+0D0h+Priority], rax; unsigned int *
0x14000e79c  lea     r8, [rbp+57h+var_40]; void *
0x14000e7a0  lea     rax, [rbp+57h+var_98]
0x14000e7a4  mov     edx, edi; unsigned int
0x14000e7a6  lea     rcx, [rbp+57h+var_88]; struct _MDL **
0x14000e7aa  mov     qword ptr [rsp+0D0h+BugCheckOnFailure], rax; unsigned int *
0x14000e7af  call    ?Dot11CopyMdlToBuffer@@YAHPEAPEAU_MDL@@KPEAXKPEAK2@Z; Dot11CopyMdlToBuffer(_MDL * *,ulong,void *,ulong,ulong *,ulong *)
0x14000e7b4  mov     eax, 8
0x14000e7b9  lea     ecx, [rax+79h]
0x14000e7bc  cmp     [rbp+57h+var_3B+1], cx
0x14000e7c0  lea     edx, [rax+4]
0x14000e7c3  cmovz   eax, edx
0x14000e7c6  add     ebx, eax
0x14000e7c8  mov     dword ptr [rbp+57h+Size+4], eax
0x14000e7cb  cmp     ebx, 1F3Bh
0x14000e7d1  ja      loc_14000EA82
0x14000e7d7  mov     eax, ebx
0x14000e7d9  mov     ecx, 0FFFh; Base
0x14000e7de  mov     edx, ebx; Length
0x14000e7e0  mov     [rbp+57h+var_70], rax
0x14000e7e4  call    cs:__imp_MmSizeOfMdl
0x14000e7eb  nop     dword ptr [rax+rax+00h]
0x14000e7f0  lea     edi, [rax+7]
0x14000e7f3  and     edi, 0FFFFFFF8h
0x14000e7f6  lea     eax, [rdi+10h]
0x14000e7f9  add     eax, ebx
0x14000e7fb  cmp     eax, 10h
0x14000e7fe  jb      loc_14000EA6D
0x14000e804  cmp     eax, 40h ; '@'
0x14000e807  ja      short loc_14000E812
0x14000e809  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14000e810  jmp     short loc_14000E83E
0x14000e812  cmp     eax, r13d
0x14000e815  ja      short loc_14000E820
0x14000e817  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14000e81e  jmp     short loc_14000E83E
0x14000e820  cmp     eax, 400h
0x14000e825  ja      short loc_14000E830
0x14000e827  lea     rbx, Lookaside
0x14000e82e  jmp     short loc_14000E83E
0x14000e830  cmp     eax, 800h
0x14000e835  ja      short loc_14000E84F
0x14000e837  lea     rbx, stru_1400B0180
0x14000e83e  mov     rcx, rbx; Lookaside
0x14000e841  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000e848  nop     dword ptr [rax+rax+00h]
0x14000e84d  jmp     short loc_14000E868
0x14000e84f  xor     ebx, ebx
0x14000e851  mov     edx, eax
0x14000e853  mov     r8d, 31697377h
0x14000e859  lea     ecx, [rbx+40h]
0x14000e85c  call    cs:__imp_ExAllocatePool2
0x14000e863  nop     dword ptr [rax+rax+00h]
0x14000e868  test    rax, rax
0x14000e86b  jz      loc_14000EA6D
0x14000e871  movzx   r13d, si
0x14000e875  lea     rsi, [rax+10h]
0x14000e879  mov     [rax], rbx
0x14000e87c  mov     ebx, dword ptr [rbp+57h+Size]
0x14000e87f  mov     dword ptr [rax+8], 31697377h
0x14000e886  test    rsi, rsi
0x14000e889  jz      short loc_14000E8EF
0x14000e88b  mov     rcx, [rbp+57h+var_70]
0x14000e88f  mov     r9d, 0FFFh
0x14000e895  add     rcx, r9
0x14000e898  mov     edx, edi
0x14000e89a  add     rdx, rsi
0x14000e89d  mov     qword ptr [rsi], 0
0x14000e8a4  mov     r8d, edx
0x14000e8a7  and     rdx, 0FFFFFFFFFFFFF000h
0x14000e8ae  mov     eax, r8d
0x14000e8b1  mov     [rsi+20h], rdx
0x14000e8b5  and     rax, r9
0x14000e8b8  and     r8d, r9d
0x14000e8bb  add     rcx, rax
0x14000e8be  mov     [rsi+2Ch], r8d
0x14000e8c2  shr     rcx, 0Ch
0x14000e8c6  xor     eax, eax
0x14000e8c8  add     cx, 6
0x14000e8cc  mov     [rsi+0Ah], ax
0x14000e8d0  mov     eax, dword ptr [rbp+57h+Size+4]
0x14000e8d3  shl     cx, 3
0x14000e8d7  add     eax, ebx
0x14000e8d9  mov     [rsi+8], cx
0x14000e8dd  mov     rcx, rsi; MemoryDescriptorList
0x14000e8e0  mov     [rsi+28h], eax
0x14000e8e3  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000e8ea  nop     dword ptr [rax+rax+00h]
0x14000e8ef  mov     rax, [rbp+57h+var_60]
0x14000e8f3  lea     r9d, [rbx+r13]; DataLength
0x14000e8f7  mov     qword ptr [rsi], 0
0x14000e8fe  xor     r8d, r8d; DataOffset
0x14000e901  mov     rdx, rsi; MdlChain
0x14000e904  mov     rcx, [rax+38h]; PoolHandle
0x14000e908  call    cs:__imp_NdisAllocateNetBuffer
0x14000e90f  nop     dword ptr [rax+rax+00h]
0x14000e914  mov     [rbp+57h+var_78], rax
0x14000e918  mov     r14, rax
0x14000e91b  test    rax, rax
0x14000e91e  jz      loc_14000EA59
0x14000e924  mov     qword ptr [rax], 0
0x14000e92b  mov     r8, rbx; Size
0x14000e92e  mov     rax, [rax+8]
0x14000e932  mov     rdx, r15; Src
0x14000e935  mov     [rbp+57h+var_70], rax
0x14000e939  mov     rdi, [rax+18h]
0x14000e93d  mov     rcx, rdi; void *
0x14000e940  call    memmove
0x14000e945  mov     edx, [rbp+57h+var_A0]; unsigned int
0x14000e948  lea     rax, [rbp+57h+var_9C]
0x14000e94c  mov     qword ptr [rsp+0D0h+Priority], rax; unsigned int *
0x14000e951  lea     r8, [rbx+rdi]; void *
0x14000e955  mov     edi, dword ptr [rbp+57h+Size+4]
0x14000e958  lea     rax, [rbp+57h+var_98]
0x14000e95c  mov     r9d, edi; unsigned int
0x14000e95f  mov     qword ptr [rsp+0D0h+BugCheckOnFailure], rax; unsigned int *
0x14000e964  lea     rcx, [rbp+57h+var_88]; struct _MDL **
0x14000e968  call    ?Dot11CopyMdlToBuffer@@YAHPEAPEAU_MDL@@KPEAXKPEAK2@Z; Dot11CopyMdlToBuffer(_MDL * *,ulong,void *,ulong,ulong *,ulong *)
0x14000e96d  cmp     [rbp+57h+var_9C], edi
0x14000e970  jnz     loc_14000EA52
0x14000e976  add     [rbp+57h+var_A0], edi
0x14000e979  lea     ebx, [r13+11h]
0x14000e97d  mov     ecx, r13d
0x14000e980  lea     r8, [rbp+57h+var_A0]; unsigned int *
0x14000e984  sub     ecx, edi; unsigned int
0x14000e986  lea     rdx, [rbp+57h+var_88]; struct _MDL **
0x14000e98a  and     ebx, 0FFFFFFFCh
0x14000e98d  call    ?SafeModeCloneMdlChain@@YAPEAU_MDL@@KPEAPEAU1@PEAK@Z; SafeModeCloneMdlChain(ulong,_MDL * *,ulong *)
0x14000e992  mov     ecx, [rbp+57h+var_A0]
0x14000e995  mov     edi, ebx
0x14000e997  add     ecx, 0FFFFFFF2h
0x14000e99a  sub     edi, r13d
0x14000e99d  add     edi, ecx
0x14000e99f  mov     r10, rax
0x14000e9a2  test    rax, rax
0x14000e9a5  jz      loc_14000EA4B
0x14000e9ab  movzx   edx, word ptr [r15]
0x14000e9af  mov     r13d, 100h
0x14000e9b5  mov     esi, [rbp+57h+var_8C]
0x14000e9b8  movzx   ecx, dx
0x14000e9bb  movzx   r8d, word ptr [rbp+57h+var_48+2]
0x14000e9c0  sub     esi, ebx
0x14000e9c2  mov     r9d, dword ptr [rbp+57h+var_50+6]
0x14000e9c6  shr     cx, 9
0x14000e9ca  mov     [rbp+57h+var_8C], esi
0x14000e9cd  test    r13w, dx
0x14000e9d1  jz      short loc_14000E9E5
0x14000e9d3  mov     eax, dword ptr [rbp+57h+var_50]
0x14000e9d6  mov     [r15+10h], eax
0x14000e9da  movzx   eax, word ptr [rbp+57h+var_50+4]
0x14000e9de  mov     [r15+14h], ax
0x14000e9e3  jmp     short loc_14000E9F3
0x14000e9e5  test    cl, 1
0x14000e9e8  jz      short loc_14000E9F3
0x14000e9ea  mov     [r15+10h], r9d
0x14000e9ee  mov     [r15+14h], r8w
0x14000e9f3  xor     eax, eax
0x14000e9f5  bt      cx, ax
0x14000e9f9  mov     eax, 8
0x14000e9fe  setb    cl
0x14000ea01  bt      dx, ax
0x14000ea05  setb    al
0x14000ea08  test    al, cl
0x14000ea0a  jz      short loc_14000EA15
0x14000ea0c  mov     [r15+18h], r9d
0x14000ea10  mov     [r15+1Ch], r8w
0x14000ea15  mov     rax, [rbp+57h+var_70]
0x14000ea19  mov     [rax], r10
0x14000ea1c  mov     rax, [rbp+57h+var_80]
0x14000ea20  mov     [rbp+57h+var_80], r14
0x14000ea24  test    rax, rax
0x14000ea27  jnz     short loc_14000EA32
0x14000ea29  mov     r12, r14
0x14000ea2c  mov     [rbp+57h+var_68], r14
0x14000ea30  jmp     short loc_14000EA35
0x14000ea32  mov     [rax], r14
0x14000ea35  mov     ebx, dword ptr [rbp+57h+Size]
0x14000ea38  xor     r14d, r14d
0x14000ea3b  mov     [rbp+57h+var_78], r14
0x14000ea3f  jmp     loc_14000E723
0x14000ea44  mov     ebx, 0C000003Eh
0x14000ea49  jmp     short loc_14000EA87
0x14000ea4b  mov     ebx, 0C000003Eh
0x14000ea50  jmp     short loc_14000EA72
0x14000ea52  mov     ebx, 0C000003Eh
0x14000ea57  jmp     short loc_14000EA5E
0x14000ea59  mov     ebx, 0C000009Ah
0x14000ea5e  test    rsi, rsi
0x14000ea61  jz      short loc_14000EA72
0x14000ea63  mov     rcx, rsi; struct _MDL *
0x14000ea66  call    ?SafeModeFreeMdlChain@@YAXPEAU_MDL@@@Z; SafeModeFreeMdlChain(_MDL *)
0x14000ea6b  jmp     short loc_14000EA72
0x14000ea6d  mov     ebx, 0C000009Ah
0x14000ea72  test    r14, r14
0x14000ea75  jz      short loc_14000EA87
0x14000ea77  lea     rcx, [rbp+57h+var_78]; struct _NET_BUFFER **
0x14000ea7b  call    ?SafeModeFreeNBChainAndMdls@@YAXPEAPEAU_NET_BUFFER@@@Z; SafeModeFreeNBChainAndMdls(_NET_BUFFER * *)
0x14000ea80  jmp     short loc_14000EA87
0x14000ea82  mov     ebx, 0C000009Ah
0x14000ea87  test    r12, r12
0x14000ea8a  jz      short loc_14000EA95
0x14000ea8c  lea     rcx, [rbp+57h+var_68]; struct _NET_BUFFER **
0x14000ea90  call    ?SafeModeFreeNBChainAndMdls@@YAXPEAPEAU_NET_BUFFER@@@Z; SafeModeFreeNBChainAndMdls(_NET_BUFFER * *)
0x14000ea95  mov     eax, ebx
0x14000ea97  jmp     short loc_14000EAA2
0x14000ea99  mov     rax, [rbp+57h+var_58]
0x14000ea9d  mov     [rax], r12
0x14000eaa0  xor     eax, eax
0x14000eaa2  mov     rcx, [rbp+57h+var_38]
0x14000eaa6  xor     rcx, rsp; StackCookie
0x14000eaa9  call    __security_check_cookie
0x14000eaae  mov     rbx, [rsp+0D0h+arg_18]
  ... truncated ...
```
