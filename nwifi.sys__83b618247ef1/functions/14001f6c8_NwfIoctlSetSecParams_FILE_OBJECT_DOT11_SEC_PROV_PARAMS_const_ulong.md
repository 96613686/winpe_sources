# NwfIoctlSetSecParams(_FILE_OBJECT *,DOT11_SEC_PROV_PARAMS const *,ulong)

- ea: `0x14001f6c8`
- end: `0x14001fb07`
- name: `?NwfIoctlSetSecParams@@YAJPEAU_FILE_OBJECT@@PEBUDOT11_SEC_PROV_PARAMS@@K@Z`
- size: `1087`
- prototype: `__int64 __fastcall(struct _FILE_OBJECT *, const struct DOT11_SEC_PROV_PARAMS *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140034050`

## callees

- `0x14001f6c8`
- `0x14002f6c0`
- `0x14002fa18`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001f8a8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001f8a8`
- `ntoskrnl!ExAllocatePool2` at `0x14001f8be`
- `ntoskrnl!ExAllocatePool2` at `0x14001f8be`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fa06`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fad4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fa06`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fad4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fa17`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fae5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fa17`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fae5`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001f95c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001f95c`
- `NDIS!NdisReleaseRWLock` at `0x14001fa88`
- `NDIS!NdisReleaseRWLock` at `0x14001faa5`
- `NDIS!NdisReleaseRWLock` at `0x14001fa88`
- `NDIS!NdisReleaseRWLock` at `0x14001faa5`

## pseudocode

```c
__int64 __fastcall NwfIoctlSetSecParams(
        struct _FILE_OBJECT *a1,
        const struct DOT11_SEC_PROV_PARAMS *a2,
        unsigned int a3)
{
  char *v5; // r9
  __int64 v7; // r14
  int inited; // ebx
  unsigned int v9; // eax
  unsigned int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // r10d
  int v13; // r11d
  int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // r15d
  unsigned int v17; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *v19; // rax
  char *v20; // r15
  struct _FILE_OBJECT *v21; // rcx
  _QWORD *v22; // r15
  struct _FILE_OBJECT *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  char *v26; // [rsp+20h] [rbp-98h]
  unsigned int Size; // [rsp+30h] [rbp-88h]
  unsigned int Size_4; // [rsp+34h] [rbp-84h]
  int v29; // [rsp+38h] [rbp-80h]
  char *FsContext; // [rsp+48h] [rbp-70h]
  _DWORD *v31; // [rsp+70h] [rbp-48h]
  _DWORD *v32; // [rsp+78h] [rbp-40h]
  char *v33; // [rsp+C0h] [rbp+8h]
  struct _LOCK_STATE_EX LockState; // [rsp+D8h] [rbp+20h] BYREF

  FsContext = (char *)a1->FsContext;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  v5 = 0;
  v26 = 0;
  if ( !FsContext )
    return 3221225488LL;
  v7 = *((_QWORD *)FsContext + 2);
  if ( !*(_DWORD *)(v7 + 5616) && *(struct _FILE_OBJECT **)(v7 + 5888) == a1 || a3 < 0x18 )
  {
    inited = -1073741436;
  }
  else
  {
    v32 = (_DWORD *)((char *)a2 + 8);
    v9 = *((_DWORD *)a2 + 2);
    if ( v9 > 0xFFFF )
      goto LABEL_56;
    v31 = (_DWORD *)((char *)a2 + 16);
    v10 = *((_DWORD *)a2 + 4);
    if ( v10 > 0xFFFF
      || (v11 = *((_DWORD *)a2 + 5), v12 = *((_DWORD *)a2 + 3), v12 > v11)
      || v11 > a3
      || (v13 = 6 * v9, Size_4 = 6 * v9, 6 * v9 > v11 - v12)
      || (v14 = 2 * v10, Size = 2 * v10, v15 = a3 - v11, 2 * v10 > (unsigned int)v15) )
    {
LABEL_56:
      inited = -1073741811;
    }
    else
    {
      v29 = v14 + 7;
      v16 = ((v14 + 7) & 0xFFFFFFF8) + ((v13 + 7) & 0xFFFFFFF8);
      if ( v16 )
      {
        inited = Dot11ValidateEtherTypeArray(a2, 4294967288LL, v15, 0);
        v5 = 0;
        if ( inited < 0 )
          goto LABEL_57;
        v17 = v16 + 16;
        if ( v16 < 0xFFFFFFF0 )
        {
          if ( v17 > 0x40 )
          {
            if ( v17 > 0x100 )
            {
              if ( v17 > 0x400 )
              {
                p_WaitListHead = &stru_1400B0180;
                if ( v17 > 0x800 )
                  p_WaitListHead = 0;
              }
              else
              {
                p_WaitListHead = &Lookaside;
              }
            }
            else
            {
              p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
            }
          }
          else
          {
            p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
          }
          v19 = p_WaitListHead
              ? ExAllocateFromNPagedLookasideList(p_WaitListHead)
              : (_DWORD *)ExAllocatePool2(64, v17, 1936290679, 0);
          if ( v19 )
          {
            *(_QWORD *)v19 = p_WaitListHead;
            v19[2] = 1936290679;
            v5 = (char *)(v19 + 4);
            v26 = (char *)(v19 + 4);
            inited = 0;
          }
          else
          {
            inited = -1073741670;
            v5 = 0;
          }
        }
        else
        {
          inited = -1073741670;
        }
        if ( inited < 0 )
          goto LABEL_57;
        v20 = &v5[v29 & 0xFFFFFFF8];
        v33 = v20;
        memmove(v5, (char *)a2 + *((unsigned int *)a2 + 5), Size);
        memmove(v20, (char *)a2 + *((unsigned int *)a2 + 3), Size_4);
      }
      else
      {
        inited = 0;
        v33 = 0;
      }
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v7 + 144), &LockState, 0);
      if ( (*(_DWORD *)a2 & 1) != 0 )
      {
        v21 = *(struct _FILE_OBJECT **)(v7 + 5880);
        if ( v21 && v21 != a1 )
          inited = -1073741757;
        v22 = (_QWORD *)(v7 + 5872);
      }
      else
      {
        v22 = (_QWORD *)(v7 + 5872);
        v23 = *(struct _FILE_OBJECT **)(v7 + 5872);
        if ( v23 && v23 != a1 )
          inited = -1073741757;
      }
      if ( inited >= 0 )
      {
        if ( *((_DWORD *)FsContext + 8) )
        {
LABEL_46:
          if ( (*(_DWORD *)a2 & 1) != 0 )
            *(_QWORD *)(v7 + 5880) = a1;
          else
            *v22 = a1;
          v24 = *((_QWORD *)FsContext + 22);
          if ( v24 )
          {
            v25 = v24 - 16;
            if ( *(_QWORD *)v25 )
              ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v25, (PVOID)v25);
            else
              ExFreePoolWithTag((PVOID)v25, *(_DWORD *)(v25 + 8));
            *((_QWORD *)FsContext + 22) = 0;
          }
          *((_DWORD *)FsContext + 40) = (*(_DWORD *)a2 >> 1) & 1;
          *((_DWORD *)FsContext + 41) = *((_DWORD *)a2 + 1);
          *((_QWORD *)FsContext + 22) = v26;
          *((_DWORD *)FsContext + 42) = *v31;
          *((_QWORD *)FsContext + 24) = v33;
          *((_DWORD *)FsContext + 46) = *v32;
          NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v7 + 144), &LockState);
          return (unsigned int)inited;
        }
        inited = NwfInitAuthUpcall((PIO_CSQ)(FsContext + 40), *(struct _ADAPT **)(v7 + 16));
        if ( inited >= 0 )
        {
          *((_DWORD *)FsContext + 8) = 1;
          goto LABEL_46;
        }
      }
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v7 + 144), &LockState);
      v5 = v26;
    }
  }
LABEL_57:
  if ( v5 )
  {
    if ( *((_QWORD *)v5 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v5 - 2), v5 - 16);
    else
      ExFreePoolWithTag(v5 - 16, *((_DWORD *)v5 - 2));
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14001f6c8  mov     r11, rsp
0x14001f6cb  mov     [r11+10h], rdx
0x14001f6cf  mov     [r11+8], rcx
0x14001f6d3  push    rbx
0x14001f6d4  push    rsi
0x14001f6d5  push    rdi
0x14001f6d6  push    r12
0x14001f6d8  push    r13
0x14001f6da  push    r14
0x14001f6dc  push    r15
0x14001f6de  sub     rsp, 80h
0x14001f6e5  mov     r12, rdx
0x14001f6e8  mov     r13, rcx
0x14001f6eb  mov     rsi, [rcx+18h]
0x14001f6ef  mov     [rsp+0B8h+var_70], rsi
0x14001f6f4  xor     edi, edi
0x14001f6f6  mov     [r11+20h], dil
0x14001f6fa  xor     eax, eax
0x14001f6fc  mov     [r11+21h], ax
0x14001f701  mov     r9d, edi
0x14001f704  mov     [rsp+0B8h+var_98], rdi
0x14001f709  mov     [r11-78h], rdi
0x14001f70d  test    rsi, rsi
0x14001f710  jnz     short loc_14001F71C
0x14001f712  mov     eax, 0C0000010h
0x14001f717  jmp     loc_14001FAF3
0x14001f71c  mov     r14, [rsi+10h]
0x14001f720  mov     [rsp+0B8h+var_68], r14
0x14001f725  cmp     [r14+15F0h], edi
0x14001f72c  jnz     short loc_14001F741
0x14001f72e  cmp     [r14+1700h], rcx
0x14001f735  jnz     short loc_14001F741
0x14001f737  mov     ebx, 0C0000184h
0x14001f73c  jmp     loc_14001FABD
0x14001f741  cmp     r8d, 18h
0x14001f745  jb      short loc_14001F737
0x14001f747  lea     rax, [rdx+8]
0x14001f74b  mov     [rsp+0B8h+var_40], rax
0x14001f750  mov     eax, [rax]
0x14001f752  mov     r10d, 0FFFFh
0x14001f758  cmp     eax, r10d
0x14001f75b  ja      loc_14001FAB8
0x14001f761  lea     rcx, [rdx+10h]
0x14001f765  mov     [rsp+0B8h+var_48], rcx
0x14001f76a  mov     edx, [rcx]
0x14001f76c  cmp     edx, r10d
0x14001f76f  ja      loc_14001FAB8
0x14001f775  lea     rcx, [r12+14h]
0x14001f77a  mov     [rsp+0B8h+var_58], rcx
0x14001f77f  mov     ecx, [rcx]
0x14001f781  lea     r10, [r12+0Ch]
0x14001f786  mov     [rsp+0B8h+var_50], r10
0x14001f78b  mov     r10d, [r10]
0x14001f78e  cmp     r10d, ecx
0x14001f791  ja      loc_14001FAB8
0x14001f797  cmp     ecx, r8d
0x14001f79a  ja      loc_14001FAB8
0x14001f7a0  lea     eax, [rax+rax*2]
0x14001f7a3  lea     r11d, [rax+rax]
0x14001f7a7  mov     dword ptr [rsp+0B8h+Size+4], r11d
0x14001f7ac  mov     eax, ecx
0x14001f7ae  sub     eax, r10d
0x14001f7b1  cmp     r11d, eax
0x14001f7b4  ja      loc_14001FAB8
0x14001f7ba  lea     eax, [rdx+rdx]
0x14001f7bd  mov     dword ptr [rsp+0B8h+Size], eax
0x14001f7c1  sub     r8d, ecx
0x14001f7c4  cmp     eax, r8d
0x14001f7c7  ja      loc_14001FAB8
0x14001f7cd  add     eax, 7
0x14001f7d0  mov     [rsp+0B8h+var_80], rax
0x14001f7d5  mov     dword ptr [rsp+0B8h+var_60], eax
0x14001f7d9  lea     r15d, [r11+7]
0x14001f7dd  mov     edx, 0FFFFFFF8h
0x14001f7e2  and     r15d, edx
0x14001f7e5  and     eax, edx
0x14001f7e7  add     r15d, eax
0x14001f7ea  mov     [rsp+0B8h+var_8C], r15d
0x14001f7ef  jz      loc_14001F940
0x14001f7f5  mov     rcx, r12
0x14001f7f8  call    Dot11ValidateEtherTypeArray
0x14001f7fd  mov     ebx, eax
0x14001f7ff  mov     [rsp+0B8h+var_90], eax
0x14001f803  mov     r9, rdi
0x14001f806  jmp     short loc_14001F843
0x14001f808  mov     ebx, eax
0x14001f80a  mov     [rsp+0B8h+var_90], eax
0x14001f80e  xor     edi, edi
0x14001f810  mov     r12, [rsp+0B8h+arg_8]
0x14001f818  mov     r13, [rsp+0B8h+arg_0]
0x14001f820  mov     r9, [rsp+0B8h+var_78]
0x14001f825  mov     [rsp+0B8h+var_98], r9
0x14001f82a  mov     rsi, [rsp+0B8h+var_70]
0x14001f82f  mov     r14, [rsp+0B8h+var_68]
0x14001f834  mov     r15d, [rsp+0B8h+var_8C]
0x14001f839  mov     rax, [rsp+0B8h+var_60]
0x14001f83e  mov     [rsp+0B8h+var_80], rax
0x14001f843  test    ebx, ebx
0x14001f845  js      loc_14001FABD
0x14001f84b  lea     eax, [r15+10h]
0x14001f84f  cmp     eax, 10h
0x14001f852  jnb     short loc_14001F85E
0x14001f854  mov     ebx, 0C000009Ah
0x14001f859  jmp     loc_14001F8F0
0x14001f85e  mov     ecx, 40h ; '@'
0x14001f863  cmp     eax, ecx
0x14001f865  ja      short loc_14001F870
0x14001f867  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14001f86e  jmp     short loc_14001F8A0
0x14001f870  cmp     eax, 100h
0x14001f875  ja      short loc_14001F880
0x14001f877  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14001f87e  jmp     short loc_14001F8A0
0x14001f880  cmp     eax, 400h
0x14001f885  ja      short loc_14001F890
0x14001f887  lea     rbx, Lookaside
0x14001f88e  jmp     short loc_14001F8A0
0x14001f890  lea     rbx, stru_1400B0180
0x14001f897  cmp     eax, 800h
0x14001f89c  cmova   rbx, rdi
0x14001f8a0  test    rbx, rbx
0x14001f8a3  jz      short loc_14001F8B6
0x14001f8a5  mov     rcx, rbx; Lookaside
0x14001f8a8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001f8af  nop     dword ptr [rax+rax+00h]
0x14001f8b4  jmp     short loc_14001F8CA
0x14001f8b6  mov     edx, eax
0x14001f8b8  mov     r8d, 73697377h
0x14001f8be  call    cs:__imp_ExAllocatePool2
0x14001f8c5  nop     dword ptr [rax+rax+00h]
0x14001f8ca  test    rax, rax
0x14001f8cd  jnz     short loc_14001F8DB
0x14001f8cf  mov     ebx, 0C000009Ah
0x14001f8d4  mov     r9, [rsp+0B8h+var_98]
0x14001f8d9  jmp     short loc_14001F8F0
0x14001f8db  mov     [rax], rbx
0x14001f8de  mov     dword ptr [rax+8], 73697377h
0x14001f8e5  lea     r9, [rax+10h]
0x14001f8e9  mov     [rsp+0B8h+var_98], r9
0x14001f8ee  mov     ebx, edi
0x14001f8f0  test    ebx, ebx
0x14001f8f2  js      loc_14001FABD
0x14001f8f8  mov     r15, [rsp+0B8h+var_80]
0x14001f8fd  mov     ecx, 0FFFFFFF8h
0x14001f902  and     r15, rcx
0x14001f905  add     r15, r9
0x14001f908  mov     [rsp+0B8h+arg_0], r15
0x14001f910  mov     r8d, dword ptr [rsp+0B8h+Size]; Size
0x14001f915  mov     rax, [rsp+0B8h+var_58]
0x14001f91a  mov     edx, [rax]
0x14001f91c  add     rdx, r12; Src
0x14001f91f  mov     rcx, r9; void *
0x14001f922  call    memmove
0x14001f927  mov     r8d, dword ptr [rsp+0B8h+Size+4]; Size
0x14001f92c  mov     rax, [rsp+0B8h+var_50]
0x14001f931  mov     edx, [rax]
0x14001f933  add     rdx, r12; Src
0x14001f936  mov     rcx, r15; void *
0x14001f939  call    memmove
0x14001f93e  jmp     short loc_14001F94A
0x14001f940  mov     ebx, edi
0x14001f942  mov     [rsp+0B8h+arg_0], rdi
0x14001f94a  xor     r8d, r8d; Flags
0x14001f94d  lea     rdx, [rsp+0B8h+LockState]; LockState
0x14001f955  mov     rcx, [r14+90h]; Lock
0x14001f95c  call    cs:__imp_NdisAcquireRWLockWrite
0x14001f963  nop     dword ptr [rax+rax+00h]
0x14001f968  mov     eax, [r12]
0x14001f96c  test    al, 1
0x14001f96e  jz      short loc_14001F990
0x14001f970  mov     rcx, [r14+16F8h]
0x14001f977  test    rcx, rcx
0x14001f97a  jz      short loc_14001F987
0x14001f97c  mov     eax, 0C0000043h
0x14001f981  cmp     rcx, r13
0x14001f984  cmovnz  ebx, eax
0x14001f987  lea     r15, [r14+16F0h]
0x14001f98e  jmp     short loc_14001F9A9
0x14001f990  lea     r15, [r14+16F0h]
0x14001f997  mov     rax, [r15]
0x14001f99a  test    rax, rax
0x14001f99d  jz      short loc_14001F9A9
0x14001f99f  cmp     rax, r13
0x14001f9a2  jz      short loc_14001F9A9
0x14001f9a4  mov     ebx, 0C0000043h
0x14001f9a9  test    ebx, ebx
0x14001f9ab  js      loc_14001FA96
0x14001f9b1  cmp     [rsi+20h], edi
0x14001f9b4  jnz     short loc_14001F9D4
0x14001f9b6  lea     rcx, [rsi+28h]; Csq
0x14001f9ba  mov     rdx, [r14+10h]; struct _ADAPT *
0x14001f9be  call    ?NwfInitAuthUpcall@@YAJPEAUNWF_AUTH_UPCALL@@PEAU_ADAPT@@@Z; NwfInitAuthUpcall(NWF_AUTH_UPCALL *,_ADAPT *)
0x14001f9c3  mov     ebx, eax
0x14001f9c5  test    eax, eax
0x14001f9c7  js      loc_14001FA96
0x14001f9cd  mov     dword ptr [rsi+20h], 1
0x14001f9d4  mov     eax, [r12]
0x14001f9d8  test    al, 1
0x14001f9da  jz      short loc_14001F9E5
0x14001f9dc  mov     [r14+16F8h], r13
0x14001f9e3  jmp     short loc_14001F9E8
0x14001f9e5  mov     [r15], r13
0x14001f9e8  mov     rcx, [rsi+0B0h]
0x14001f9ef  test    rcx, rcx
0x14001f9f2  jz      short loc_14001FA2A
0x14001f9f4  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14001f9f8  mov     rax, [rcx]
0x14001f9fb  test    rax, rax
0x14001f9fe  jz      short loc_14001FA14
0x14001fa00  mov     rdx, rcx; Entry
0x14001fa03  mov     rcx, rax; Lookaside
0x14001fa06  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001fa0d  nop     dword ptr [rax+rax+00h]
0x14001fa12  jmp     short loc_14001FA23
0x14001fa14  mov     edx, [rcx+8]; Tag
0x14001fa17  call    cs:__imp_ExFreePoolWithTag
0x14001fa1e  nop     dword ptr [rax+rax+00h]
0x14001fa23  mov     [rsi+0B0h], rdi
0x14001fa2a  mov     eax, [r12]
0x14001fa2e  shr     eax, 1
0x14001fa30  and     eax, 1
0x14001fa33  mov     [rsi+0A0h], eax
0x14001fa39  mov     eax, [r12+4]
0x14001fa3e  mov     [rsi+0A4h], eax
0x14001fa44  mov     rax, [rsp+0B8h+var_98]
0x14001fa49  mov     [rsi+0B0h], rax
0x14001fa50  mov     rax, [rsp+0B8h+var_48]
0x14001fa55  mov     eax, [rax]
0x14001fa57  mov     [rsi+0A8h], eax
0x14001fa5d  mov     rax, [rsp+0B8h+arg_0]
0x14001fa65  mov     [rsi+0C0h], rax
0x14001fa6c  mov     rax, [rsp+0B8h+var_40]
0x14001fa71  mov     eax, [rax]
0x14001fa73  mov     [rsi+0B8h], eax
0x14001fa79  lea     rdx, [rsp+0B8h+LockState]; LockState
0x14001fa81  mov     rcx, [r14+90h]; Lock
0x14001fa88  call    cs:__imp_NdisReleaseRWLock
0x14001fa8f  nop     dword ptr [rax+rax+00h]
0x14001fa94  jmp     short loc_14001FAF1
0x14001fa96  lea     rdx, [rsp+0B8h+LockState]; LockState
0x14001fa9e  mov     rcx, [r14+90h]; Lock
0x14001faa5  call    cs:__imp_NdisReleaseRWLock
0x14001faac  nop     dword ptr [rax+rax+00h]
0x14001fab1  mov     r9, [rsp+0B8h+var_98]
0x14001fab6  jmp     short loc_14001FABD
0x14001fab8  mov     ebx, 0C000000Dh
0x14001fabd  test    r9, r9
0x14001fac0  jz      short loc_14001FAF1
0x14001fac2  lea     rcx, [r9-10h]; P
0x14001fac6  mov     rax, [rcx]
0x14001fac9  test    rax, rax
0x14001facc  jz      short loc_14001FAE2
0x14001face  mov     rdx, rcx; Entry
0x14001fad1  mov     rcx, rax; Lookaside
0x14001fad4  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001fadb  nop     dword ptr [rax+rax+00h]
0x14001fae0  jmp     short loc_14001FAF1
0x14001fae2  mov     edx, [rcx+8]; Tag
0x14001fae5  call    cs:__imp_ExFreePoolWithTag
0x14001faec  nop     dword ptr [rax+rax+00h]
0x14001faf1  mov     eax, ebx
0x14001faf3  add     rsp, 80h
0x14001fafa  pop     r15
0x14001fafc  pop     r14
0x14001fafe  pop     r13
0x14001fb00  pop     r12
0x14001fb02  pop     rdi
0x14001fb03  pop     rsi
0x14001fb04  pop     rbx
0x14001fb05  retn
```
