# SafeModeSplitAMSDUToNBList(_VELAN *,_NET_BUFFER *,_NET_BUFFER * *)

- ea: `0x14000e644`
- end: `0x14000eaba`
- name: `?SafeModeSplitAMSDUToNBList@@YAJPEAU_VELAN@@PEAU_NET_BUFFER@@PEAPEAU2@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(struct _VELAN *, struct _NET_BUFFER *, struct _NET_BUFFER **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140031f10`

## callees

- `0x14000e644`
- `0x140010510`
- `0x140011408`
- `0x140019394`
- `0x140019440`
- `0x1400323b8`
- `0x14009bbb0`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000e8d3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000e8d3`
- `ntoskrnl!MmSizeOfMdl` at `0x14000e7d4`
- `ntoskrnl!MmSizeOfMdl` at `0x14000e7d4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000e831`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000e831`
- `ntoskrnl!ExAllocatePool2` at `0x14000e84c`
- `ntoskrnl!ExAllocatePool2` at `0x14000e84c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e6d3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e6d3`
- `NDIS!NdisAllocateNetBuffer` at `0x14000e8f8`
- `NDIS!NdisAllocateNetBuffer` at `0x14000e8f8`

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
  unsigned int v22; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  int v25; // r13d
  struct _MDL *v26; // rsi
  size_t v27; // rbx
  char *v28; // rcx
  unsigned int v29; // eax
  struct _VELAN *v30; // rax
  PNET_BUFFER NetBuffer; // rax
  char *v32; // rdi
  char *v33; // r8
  unsigned int v34; // edi
  unsigned int v35; // ebx
  struct _MDL *v36; // rax
  __int16 v37; // dx
  __int16 v38; // r8
  int v39; // r9d
  __int16 v40; // cx
  struct _NET_BUFFER **p_Next; // rax
  unsigned int v43; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v44; // [rsp+34h] [rbp-45h] BYREF
  unsigned int v45; // [rsp+38h] [rbp-41h] BYREF
  unsigned int Size; // [rsp+3Ch] [rbp-3Dh]
  unsigned int Size_4; // [rsp+40h] [rbp-39h]
  int v48; // [rsp+44h] [rbp-35h]
  struct _MDL *v49; // [rsp+48h] [rbp-31h] BYREF
  struct _NET_BUFFER *v50; // [rsp+50h] [rbp-29h]
  struct _NET_BUFFER *v51; // [rsp+58h] [rbp-21h] BYREF
  _MDL *v52; // [rsp+60h] [rbp-19h]
  struct _NET_BUFFER *v53; // [rsp+68h] [rbp-11h] BYREF
  struct _VELAN *v54; // [rsp+70h] [rbp-9h]
  struct _NET_BUFFER **v55; // [rsp+78h] [rbp-1h]
  _BYTE v56[12]; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int16 v57; // [rsp+8Ch] [rbp+13h]
  char v58; // [rsp+90h] [rbp+17h] BYREF
  int v59; // [rsp+91h] [rbp+18h]
  _BYTE v60[3]; // [rsp+95h] [rbp+1Ch] BYREF

  CurrentMdl = a2->CurrentMdl;
  CurrentMdlOffset = a2->CurrentMdlOffset;
  v5 = 0;
  DataLength = a2->DataLength;
  v7 = 0;
  v55 = a3;
  v8 = (CurrentMdl->MdlFlags & 5) == 0;
  v54 = a1;
  v49 = CurrentMdl;
  memset(v56, 0, sizeof(v56));
  v57 = 0;
  v58 = 0;
  v59 = 0;
  memset(v60, 0, sizeof(v60));
  v53 = 0;
  v51 = 0;
  v44 = 0;
  if ( v8 )
    MappedSystemVa = MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000010u);
  else
    MappedSystemVa = CurrentMdl->MappedSystemVa;
  if ( !MappedSystemVa )
    return (unsigned int)-1073741670;
  v50 = 0;
  v11 = (__int16 *)((char *)CurrentMdl->MappedSystemVa + CurrentMdlOffset);
  v12 = Dot11DataFrameMacHeaderSize(v11);
  v13 = v12 + CurrentMdlOffset;
  Size = v12;
  v14 = DataLength - v12;
  v15 = v12;
  v48 = v14;
  while ( 1 )
  {
    if ( v14 <= 0 )
    {
      *v55 = v5;
      return 0;
    }
    v45 = 0;
    Dot11CopyMdlToBuffer(&v49, v13, v56, 0xEu, &v45, &v44);
    v16 = v13 + 14;
    v17 = __ROR2__(v57, 8);
    v57 = v17;
    v43 = v16;
    if ( (*v11 & 0x100) == 0 )
    {
      v18 = *((_DWORD *)v11 + 1) - *(_DWORD *)v56;
      if ( !v18 )
        v18 = (unsigned __int16)v11[4] - *(unsigned __int16 *)&v56[4];
      if ( v18 )
      {
        v10 = -1073741762;
        goto LABEL_52;
      }
    }
    Dot11CopyMdlToBuffer(&v49, v16, &v58, 8u, &v45, &v44);
    v19 = 8;
    if ( *(_WORD *)&v60[1] == 129 )
      v19 = 12;
    v20 = v19 + v15;
    Size_4 = v19;
    if ( v20 > 0x1F3B )
    {
      v10 = -1073741670;
      goto LABEL_52;
    }
    v52 = (_MDL *)v20;
    v21 = (MmSizeOfMdl((PVOID)0xFFF, v20) + 7) & 0xFFFFFFF8;
    v22 = v20 + v21 + 16;
    if ( v22 < 0x10 )
    {
LABEL_48:
      v10 = -1073741670;
      goto LABEL_49;
    }
    if ( v22 <= 0x40 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_24:
      Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
      goto LABEL_26;
    }
    if ( v22 <= 0x100 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      goto LABEL_24;
    }
    if ( v22 <= 0x400 )
    {
      p_DeviceQueue = &Lookaside;
      goto LABEL_24;
    }
    if ( v22 <= 0x800 )
    {
      p_DeviceQueue = &stru_1400B31C0;
      goto LABEL_24;
    }
    p_DeviceQueue = 0;
    Pool2 = (char *)ExAllocatePool2(64, v22, 828994423);
LABEL_26:
    if ( !Pool2 )
      goto LABEL_48;
    v25 = v17;
    v26 = (struct _MDL *)(Pool2 + 16);
    *(_QWORD *)Pool2 = p_DeviceQueue;
    v27 = Size;
    *((_DWORD *)Pool2 + 2) = 828994423;
    if ( Pool2 != (char *)-16LL )
    {
      v28 = (char *)&v52[85].Reserved + 1;
      v26->Next = 0;
      *((_QWORD *)Pool2 + 6) = ((unsigned __int64)v26 + v21) & 0xFFFFFFFFFFFFF000uLL;
      *((_DWORD *)Pool2 + 15) = ((_DWORD)v26 + v21) & 0xFFF;
      *((_WORD *)Pool2 + 13) = 0;
      v29 = v27 + Size_4;
      v26->Size = 8 * (((unsigned __int64)&v28[((unsigned int)v26 + v21) & 0xFFFLL] >> 12) + 6);
      v26->ByteCount = v29;
      MmBuildMdlForNonPagedPool(v26);
    }
    v30 = v54;
    v26->Next = 0;
    NetBuffer = NdisAllocateNetBuffer(v30->hSendNetBufferPool, v26, 0, (unsigned int)(v27 + v25));
    v51 = NetBuffer;
    v7 = NetBuffer;
    if ( !NetBuffer )
      break;
    NetBuffer->Link.Alignment = 0;
    v52 = NetBuffer->CurrentMdl;
    v32 = (char *)v52->MappedSystemVa;
    memmove(v32, v11, v27);
    v33 = &v32[v27];
    v34 = Size_4;
    Dot11CopyMdlToBuffer(&v49, v43, v33, Size_4, &v45, &v44);
    if ( v44 != v34 )
    {
      v10 = -1073741762;
      goto LABEL_46;
    }
    v43 += v34;
    v35 = (v25 + 17) & 0xFFFFFFFC;
    v36 = SafeModeCloneMdlChain(v25 - v34, &v49, &v43);
    v13 = v43 - 14 + v35 - v25;
    if ( !v36 )
    {
      v10 = -1073741762;
      goto LABEL_49;
    }
    v37 = *v11;
    v38 = *(_WORD *)&v56[10];
    v14 = v48 - v35;
    v39 = *(_DWORD *)&v56[6];
    v40 = (unsigned __int16)*v11 >> 9;
    v48 -= v35;
    if ( (v37 & 0x100) != 0 )
    {
      *((_DWORD *)v11 + 4) = *(_DWORD *)v56;
      v11[10] = *(_WORD *)&v56[4];
    }
    else if ( (v40 & 1) != 0 )
    {
      *((_DWORD *)v11 + 4) = *(_DWORD *)&v56[6];
      v11[10] = v38;
    }
    if ( (v40 & 1) != 0 && (v37 & 0x100) != 0 )
    {
      *((_DWORD *)v11 + 6) = v39;
      v11[14] = v38;
    }
    v52->Next = v36;
    p_Next = &v50->Next;
    v50 = v7;
    if ( p_Next )
    {
      *p_Next = v7;
    }
    else
    {
      v5 = v7;
      v53 = v7;
    }
    v15 = Size;
    v7 = 0;
    v51 = 0;
  }
  v10 = -1073741670;
LABEL_46:
  if ( v26 )
    SafeModeFreeMdlChain(v26);
LABEL_49:
  if ( v7 )
    SafeModeFreeNBChainAndMdls(&v51);
LABEL_52:
  if ( v5 )
    SafeModeFreeNBChainAndMdls(&v53);
  return v10;
}

```

## disassembly

```asm
0x14000e644  mov     [rsp-8+arg_18], rbx
0x14000e649  push    rbp
0x14000e64a  push    rsi
0x14000e64b  push    rdi
0x14000e64c  push    r12
0x14000e64e  push    r13
0x14000e650  push    r14
0x14000e652  push    r15
0x14000e654  lea     rbp, [rsp-27h]
0x14000e659  sub     rsp, 0A0h
0x14000e660  mov     rax, cs:__security_cookie
0x14000e667  xor     rax, rsp
0x14000e66a  mov     [rbp+57h+var_38], rax
0x14000e66e  mov     rbx, [rdx+8]
0x14000e672  xor     eax, eax
0x14000e674  mov     edi, [rdx+10h]
0x14000e677  xor     r12d, r12d
0x14000e67a  mov     esi, [rdx+18h]
0x14000e67d  xor     r14d, r14d
0x14000e680  mov     [rbp+57h+var_58], r8
0x14000e684  test    byte ptr [rbx+0Ah], 5
0x14000e688  mov     [rbp+57h+var_60], rcx
0x14000e68c  mov     [rbp+57h+var_88], rbx
0x14000e690  mov     [rbp+57h+var_50], rax
0x14000e694  mov     [rbp+57h+var_48], eax
0x14000e697  mov     [rbp+57h+var_44], ax
0x14000e69b  mov     [rbp+57h+var_40], al
0x14000e69e  mov     [rbp+57h+var_3F], eax
0x14000e6a1  mov     [rbp+57h+var_3B], ax
0x14000e6a5  mov     [rbp+57h+var_39], al
0x14000e6a8  mov     [rbp+57h+var_68], r12
0x14000e6ac  mov     [rbp+57h+var_78], r14
0x14000e6b0  mov     [rbp+57h+var_9C], eax
0x14000e6b3  jz      short loc_14000E6BB
0x14000e6b5  mov     rax, [rbx+18h]
0x14000e6b9  jmp     short loc_14000E6DF
0x14000e6bb  xor     r9d, r9d; RequestedAddress
0x14000e6be  mov     [rsp+0D0h+Priority], 40000010h; Priority
0x14000e6c6  xor     edx, edx; AccessMode
0x14000e6c8  mov     [rsp+0D0h+BugCheckOnFailure], eax; BugCheckOnFailure
0x14000e6cc  mov     rcx, rbx; MemoryDescriptorList
0x14000e6cf  lea     r8d, [r9+1]; CacheType
0x14000e6d3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000e6da  nop     dword ptr [rax+rax+00h]
0x14000e6df  test    rax, rax
0x14000e6e2  jnz     short loc_14000E6EE
0x14000e6e4  mov     ebx, 0C000009Ah
0x14000e6e9  jmp     loc_14000EA85
0x14000e6ee  mov     r15, rdi
0x14000e6f1  mov     [rbp+57h+var_80], r12
0x14000e6f5  add     r15, [rbx+18h]
0x14000e6f9  mov     rcx, r15; void *
0x14000e6fc  call    ?Dot11DataFrameMacHeaderSize@@YAKPEAX@Z; Dot11DataFrameMacHeaderSize(void *)
0x14000e701  add     edi, eax
0x14000e703  mov     dword ptr [rbp+57h+Size], eax
0x14000e706  sub     esi, eax
0x14000e708  mov     ebx, eax
0x14000e70a  mov     [rbp+57h+var_8C], esi
0x14000e70d  mov     r13d, 100h
0x14000e713  test    esi, esi
0x14000e715  jle     loc_14000EA89
0x14000e71b  lea     rax, [rbp+57h+var_9C]
0x14000e71f  mov     [rbp+57h+var_98], 0
0x14000e726  mov     qword ptr [rsp+0D0h+Priority], rax; unsigned int *
0x14000e72b  lea     r8, [rbp+57h+var_50]; void *
0x14000e72f  lea     rax, [rbp+57h+var_98]
0x14000e733  mov     r9d, 0Eh; unsigned int
0x14000e739  mov     edx, edi; unsigned int
0x14000e73b  mov     qword ptr [rsp+0D0h+BugCheckOnFailure], rax; unsigned int *
0x14000e740  lea     rcx, [rbp+57h+var_88]; struct _MDL **
0x14000e744  call    ?Dot11CopyMdlToBuffer@@YAHPEAPEAU_MDL@@KPEAXKPEAK2@Z; Dot11CopyMdlToBuffer(_MDL * *,ulong,void *,ulong,ulong *,ulong *)
0x14000e749  movzx   esi, [rbp+57h+var_44]
0x14000e74d  add     edi, 0Eh
0x14000e750  ror     si, 8
0x14000e754  mov     [rbp+57h+var_44], si
0x14000e758  mov     [rbp+57h+var_A0], edi
0x14000e75b  test    [r15], r13w
0x14000e75f  jnz     short loc_14000E77D
0x14000e761  mov     ecx, [r15+4]
0x14000e765  sub     ecx, dword ptr [rbp+57h+var_50]
0x14000e768  jnz     short loc_14000E775
0x14000e76a  movzx   ecx, word ptr [r15+8]
0x14000e76f  movzx   eax, word ptr [rbp+57h+var_50+4]
0x14000e773  sub     ecx, eax
0x14000e775  test    ecx, ecx
0x14000e777  jnz     loc_14000EA34
0x14000e77d  lea     rax, [rbp+57h+var_9C]
0x14000e781  mov     r9d, 8; unsigned int
0x14000e787  mov     qword ptr [rsp+0D0h+Priority], rax; unsigned int *
0x14000e78c  lea     r8, [rbp+57h+var_40]; void *
0x14000e790  lea     rax, [rbp+57h+var_98]
0x14000e794  mov     edx, edi; unsigned int
0x14000e796  lea     rcx, [rbp+57h+var_88]; struct _MDL **
0x14000e79a  mov     qword ptr [rsp+0D0h+BugCheckOnFailure], rax; unsigned int *
0x14000e79f  call    ?Dot11CopyMdlToBuffer@@YAHPEAPEAU_MDL@@KPEAXKPEAK2@Z; Dot11CopyMdlToBuffer(_MDL * *,ulong,void *,ulong,ulong *,ulong *)
0x14000e7a4  mov     eax, 8
0x14000e7a9  lea     ecx, [rax+79h]
0x14000e7ac  cmp     [rbp+57h+var_3B+1], cx
0x14000e7b0  lea     edx, [rax+4]
0x14000e7b3  cmovz   eax, edx
0x14000e7b6  add     ebx, eax
0x14000e7b8  mov     dword ptr [rbp+57h+Size+4], eax
0x14000e7bb  cmp     ebx, 1F3Bh
0x14000e7c1  ja      loc_14000EA72
0x14000e7c7  mov     eax, ebx
0x14000e7c9  mov     ecx, 0FFFh; Base
0x14000e7ce  mov     edx, ebx; Length
0x14000e7d0  mov     [rbp+57h+var_70], rax
0x14000e7d4  call    cs:__imp_MmSizeOfMdl
0x14000e7db  nop     dword ptr [rax+rax+00h]
0x14000e7e0  lea     edi, [rax+7]
0x14000e7e3  and     edi, 0FFFFFFF8h
0x14000e7e6  lea     eax, [rdi+10h]
0x14000e7e9  add     eax, ebx
0x14000e7eb  cmp     eax, 10h
0x14000e7ee  jb      loc_14000EA5D
0x14000e7f4  cmp     eax, 40h ; '@'
0x14000e7f7  ja      short loc_14000E802
0x14000e7f9  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14000e800  jmp     short loc_14000E82E
0x14000e802  cmp     eax, r13d
0x14000e805  ja      short loc_14000E810
0x14000e807  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14000e80e  jmp     short loc_14000E82E
0x14000e810  cmp     eax, 400h
0x14000e815  ja      short loc_14000E820
0x14000e817  lea     rbx, Lookaside
0x14000e81e  jmp     short loc_14000E82E
0x14000e820  cmp     eax, 800h
0x14000e825  ja      short loc_14000E83F
0x14000e827  lea     rbx, stru_1400B31C0
0x14000e82e  mov     rcx, rbx; Lookaside
0x14000e831  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000e838  nop     dword ptr [rax+rax+00h]
0x14000e83d  jmp     short loc_14000E858
0x14000e83f  xor     ebx, ebx
0x14000e841  mov     edx, eax
0x14000e843  mov     r8d, 31697377h
0x14000e849  lea     ecx, [rbx+40h]
0x14000e84c  call    cs:__imp_ExAllocatePool2
0x14000e853  nop     dword ptr [rax+rax+00h]
0x14000e858  test    rax, rax
0x14000e85b  jz      loc_14000EA5D
0x14000e861  movzx   r13d, si
0x14000e865  lea     rsi, [rax+10h]
0x14000e869  mov     [rax], rbx
0x14000e86c  mov     ebx, dword ptr [rbp+57h+Size]
0x14000e86f  mov     dword ptr [rax+8], 31697377h
0x14000e876  test    rsi, rsi
0x14000e879  jz      short loc_14000E8DF
0x14000e87b  mov     rcx, [rbp+57h+var_70]
0x14000e87f  mov     r9d, 0FFFh
0x14000e885  add     rcx, r9
0x14000e888  mov     edx, edi
0x14000e88a  add     rdx, rsi
0x14000e88d  mov     qword ptr [rsi], 0
0x14000e894  mov     r8d, edx
0x14000e897  and     rdx, 0FFFFFFFFFFFFF000h
0x14000e89e  mov     eax, r8d
0x14000e8a1  mov     [rsi+20h], rdx
0x14000e8a5  and     rax, r9
0x14000e8a8  and     r8d, r9d
0x14000e8ab  add     rcx, rax
0x14000e8ae  mov     [rsi+2Ch], r8d
0x14000e8b2  shr     rcx, 0Ch
0x14000e8b6  xor     eax, eax
0x14000e8b8  add     cx, 6
0x14000e8bc  mov     [rsi+0Ah], ax
0x14000e8c0  mov     eax, dword ptr [rbp+57h+Size+4]
0x14000e8c3  shl     cx, 3
0x14000e8c7  add     eax, ebx
0x14000e8c9  mov     [rsi+8], cx
0x14000e8cd  mov     rcx, rsi; MemoryDescriptorList
0x14000e8d0  mov     [rsi+28h], eax
0x14000e8d3  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000e8da  nop     dword ptr [rax+rax+00h]
0x14000e8df  mov     rax, [rbp+57h+var_60]
0x14000e8e3  lea     r9d, [rbx+r13]; DataLength
0x14000e8e7  mov     qword ptr [rsi], 0
0x14000e8ee  xor     r8d, r8d; DataOffset
0x14000e8f1  mov     rdx, rsi; MdlChain
0x14000e8f4  mov     rcx, [rax+38h]; PoolHandle
0x14000e8f8  call    cs:__imp_NdisAllocateNetBuffer
0x14000e8ff  nop     dword ptr [rax+rax+00h]
0x14000e904  mov     [rbp+57h+var_78], rax
0x14000e908  mov     r14, rax
0x14000e90b  test    rax, rax
0x14000e90e  jz      loc_14000EA49
0x14000e914  mov     qword ptr [rax], 0
0x14000e91b  mov     r8, rbx; Size
0x14000e91e  mov     rax, [rax+8]
0x14000e922  mov     rdx, r15; Src
0x14000e925  mov     [rbp+57h+var_70], rax
0x14000e929  mov     rdi, [rax+18h]
0x14000e92d  mov     rcx, rdi; void *
0x14000e930  call    memmove
0x14000e935  mov     edx, [rbp+57h+var_A0]; unsigned int
0x14000e938  lea     rax, [rbp+57h+var_9C]
0x14000e93c  mov     qword ptr [rsp+0D0h+Priority], rax; unsigned int *
0x14000e941  lea     r8, [rbx+rdi]; void *
0x14000e945  mov     edi, dword ptr [rbp+57h+Size+4]
0x14000e948  lea     rax, [rbp+57h+var_98]
0x14000e94c  mov     r9d, edi; unsigned int
0x14000e94f  mov     qword ptr [rsp+0D0h+BugCheckOnFailure], rax; unsigned int *
0x14000e954  lea     rcx, [rbp+57h+var_88]; struct _MDL **
0x14000e958  call    ?Dot11CopyMdlToBuffer@@YAHPEAPEAU_MDL@@KPEAXKPEAK2@Z; Dot11CopyMdlToBuffer(_MDL * *,ulong,void *,ulong,ulong *,ulong *)
0x14000e95d  cmp     [rbp+57h+var_9C], edi
0x14000e960  jnz     loc_14000EA42
0x14000e966  add     [rbp+57h+var_A0], edi
0x14000e969  lea     ebx, [r13+11h]
0x14000e96d  mov     ecx, r13d
0x14000e970  lea     r8, [rbp+57h+var_A0]; unsigned int *
0x14000e974  sub     ecx, edi; unsigned int
0x14000e976  lea     rdx, [rbp+57h+var_88]; struct _MDL **
0x14000e97a  and     ebx, 0FFFFFFFCh
0x14000e97d  call    ?SafeModeCloneMdlChain@@YAPEAU_MDL@@KPEAPEAU1@PEAK@Z; SafeModeCloneMdlChain(ulong,_MDL * *,ulong *)
0x14000e982  mov     ecx, [rbp+57h+var_A0]
0x14000e985  mov     edi, ebx
0x14000e987  add     ecx, 0FFFFFFF2h
0x14000e98a  sub     edi, r13d
0x14000e98d  add     edi, ecx
0x14000e98f  mov     r10, rax
0x14000e992  test    rax, rax
0x14000e995  jz      loc_14000EA3B
0x14000e99b  movzx   edx, word ptr [r15]
0x14000e99f  mov     r13d, 100h
0x14000e9a5  mov     esi, [rbp+57h+var_8C]
0x14000e9a8  movzx   ecx, dx
0x14000e9ab  movzx   r8d, word ptr [rbp+57h+var_48+2]
0x14000e9b0  sub     esi, ebx
0x14000e9b2  mov     r9d, dword ptr [rbp+57h+var_50+6]
0x14000e9b6  shr     cx, 9
0x14000e9ba  mov     [rbp+57h+var_8C], esi
0x14000e9bd  test    r13w, dx
0x14000e9c1  jz      short loc_14000E9D5
0x14000e9c3  mov     eax, dword ptr [rbp+57h+var_50]
0x14000e9c6  mov     [r15+10h], eax
0x14000e9ca  movzx   eax, word ptr [rbp+57h+var_50+4]
0x14000e9ce  mov     [r15+14h], ax
0x14000e9d3  jmp     short loc_14000E9E3
0x14000e9d5  test    cl, 1
0x14000e9d8  jz      short loc_14000E9E3
0x14000e9da  mov     [r15+10h], r9d
0x14000e9de  mov     [r15+14h], r8w
0x14000e9e3  xor     eax, eax
0x14000e9e5  bt      cx, ax
0x14000e9e9  mov     eax, 8
0x14000e9ee  setb    cl
0x14000e9f1  bt      dx, ax
0x14000e9f5  setb    al
0x14000e9f8  test    al, cl
0x14000e9fa  jz      short loc_14000EA05
0x14000e9fc  mov     [r15+18h], r9d
0x14000ea00  mov     [r15+1Ch], r8w
0x14000ea05  mov     rax, [rbp+57h+var_70]
0x14000ea09  mov     [rax], r10
0x14000ea0c  mov     rax, [rbp+57h+var_80]
0x14000ea10  mov     [rbp+57h+var_80], r14
0x14000ea14  test    rax, rax
0x14000ea17  jnz     short loc_14000EA22
0x14000ea19  mov     r12, r14
0x14000ea1c  mov     [rbp+57h+var_68], r14
0x14000ea20  jmp     short loc_14000EA25
0x14000ea22  mov     [rax], r14
0x14000ea25  mov     ebx, dword ptr [rbp+57h+Size]
0x14000ea28  xor     r14d, r14d
0x14000ea2b  mov     [rbp+57h+var_78], r14
0x14000ea2f  jmp     loc_14000E713
0x14000ea34  mov     ebx, 0C000003Eh
0x14000ea39  jmp     short loc_14000EA77
0x14000ea3b  mov     ebx, 0C000003Eh
0x14000ea40  jmp     short loc_14000EA62
0x14000ea42  mov     ebx, 0C000003Eh
0x14000ea47  jmp     short loc_14000EA4E
0x14000ea49  mov     ebx, 0C000009Ah
0x14000ea4e  test    rsi, rsi
0x14000ea51  jz      short loc_14000EA62
0x14000ea53  mov     rcx, rsi; struct _MDL *
0x14000ea56  call    ?SafeModeFreeMdlChain@@YAXPEAU_MDL@@@Z; SafeModeFreeMdlChain(_MDL *)
0x14000ea5b  jmp     short loc_14000EA62
0x14000ea5d  mov     ebx, 0C000009Ah
0x14000ea62  test    r14, r14
0x14000ea65  jz      short loc_14000EA77
0x14000ea67  lea     rcx, [rbp+57h+var_78]; struct _NET_BUFFER **
0x14000ea6b  call    ?SafeModeFreeNBChainAndMdls@@YAXPEAPEAU_NET_BUFFER@@@Z; SafeModeFreeNBChainAndMdls(_NET_BUFFER * *)
0x14000ea70  jmp     short loc_14000EA77
0x14000ea72  mov     ebx, 0C000009Ah
0x14000ea77  test    r12, r12
0x14000ea7a  jz      short loc_14000EA85
0x14000ea7c  lea     rcx, [rbp+57h+var_68]; struct _NET_BUFFER **
0x14000ea80  call    ?SafeModeFreeNBChainAndMdls@@YAXPEAPEAU_NET_BUFFER@@@Z; SafeModeFreeNBChainAndMdls(_NET_BUFFER * *)
0x14000ea85  mov     eax, ebx
0x14000ea87  jmp     short loc_14000EA92
0x14000ea89  mov     rax, [rbp+57h+var_58]
0x14000ea8d  mov     [rax], r12
0x14000ea90  xor     eax, eax
0x14000ea92  mov     rcx, [rbp+57h+var_38]
0x14000ea96  xor     rcx, rsp; StackCookie
0x14000ea99  call    __security_check_cookie
0x14000ea9e  mov     rbx, [rsp+0D0h+arg_18]
  ... truncated ...
```
