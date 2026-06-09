# FeEnumLayer

- ea: `0x1400085f0`
- end: `0x1400088f2`
- name: `FeEnumLayer`
- size: `770`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14000bdd0`
- `0x14001a914`
- `0x140039800`
- `0x140061590`

## callees

- `0x140004bf0`
- `0x140008130`
- `0x1400085f0`
- `0x140009520`
- `0x140009e00`
- `0x14001cfe0`
- `0x14004efd4`
- `0x140078080`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400086f1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400087de`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400086f1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400087de`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400087a0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400087a0`
- `NDIS!NdisAcquireRWLockRead` at `0x1400087c1`
- `NDIS!NdisAcquireRWLockRead` at `0x1400087c1`
- `NDIS!NdisReleaseRWLock` at `0x140008729`
- `NDIS!NdisReleaseRWLock` at `0x140008729`

## string_xrefs

- `0x14000882e`: `FeAcquireWriteEngineLock`
- `0x14000867d`: `GetLayerFromIdRead`
- `0x1400088d1`: `GetLayerFromIdRead`
- `0x140008864`: `FeAcquireReadEngineLock`

## pseudocode

```c
__int64 __fastcall FeEnumLayer(unsigned __int16 a1, __int64 a2, int a3, PVOID *a4)
{
  __int64 v4; // rbp
  __int64 matched; // rsi
  unsigned int v9; // ebx
  ULONGLONG v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  PNPAGED_LOOKASIDE_LIST v13; // rbx
  _DWORD *v14; // rdx
  PNPAGED_LOOKASIDE_LIST v16; // rdi
  KIRQL CurrentIrql; // bl
  __int64 v18; // rdx
  __int64 Flink_low; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+90h] [rbp+18h] BYREF

  v4 = a1;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( !a3 )
  {
    v16 = gWfpGlobal;
    CurrentIrql = KeGetCurrentIrql();
    NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v16[1].L.ListHead.Alignment, &LockState, 0);
    if ( CurrentIrql != 2 && gWfpPerProContext )
    {
      v18 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v18 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v18 = 4;
    }
    Flink_low = LODWORD(gWfpGlobal[1].L.ListEntry.Flink);
    if ( (_DWORD)Flink_low == 2 )
    {
      matched = WfpReportSysErrorAsNtStatus(Flink_low, "FeAcquireWriteEngineLock", 3221225473LL, 1);
      if ( matched )
      {
        WfpReleaseFastWriteLock(&gWfpGlobal[1], &LockState);
        WfpReportError(matched, "FeAcquireReadEngineLock");
        FreeMatchBufListInternal(*a4);
LABEL_30:
        *a4 = 0;
        WfpReportError(matched, "FeEnumLayer");
        return matched;
      }
    }
  }
  if ( (unsigned __int16)v4 < *((_WORD *)&gWfpGlobal[3].L.SingleListHead + 4) )
  {
    v9 = 0;
    matched = 0;
    v10 = gWfpGlobal[3].L.ListHead.Alignment + 136 * v4;
    if ( *(_DWORD *)(v10 + 72) )
    {
      do
      {
        v11 = *(_QWORD *)(v10 + 104) + 16LL * v9;
        v12 = *(int *)(v11 + 8);
        if ( (_DWORD)v12 != 4 )
        {
          matched = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, PVOID *, _DWORD))&gWfpGlobal[1].L.Future[14 * v12 + 2])(
                      *(_QWORD *)v11,
                      a2,
                      0,
                      a4,
                      0);
          if ( matched )
            break;
        }
        ++v9;
      }
      while ( v9 < *(_DWORD *)(v10 + 72) );
    }
  }
  else
  {
    matched = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"GetLayerFromIdRead",
        13);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"GetLayerFromIdRead",
        13);
    }
  }
  if ( !a3 )
  {
    v13 = gWfpGlobal;
    if ( gWfpPerProContext )
    {
      v14 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v14 == 4 )
        *v14 = 0;
    }
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v13[1].L.ListHead.Alignment, &LockState);
  }
  if ( (*(_DWORD *)(a2 + 8) & 2) != 0 )
  {
    if ( matched )
      goto LABEL_29;
    matched = SortMatchList(*a4);
  }
  if ( matched )
  {
LABEL_29:
    FreeMatchBufListInternal(*a4);
    goto LABEL_30;
  }
  return matched;
}

```

## disassembly

```asm
0x1400085f0  push    rbx
0x1400085f2  push    rbp
0x1400085f3  push    rsi
0x1400085f4  push    rdi
0x1400085f5  push    r12
0x1400085f7  push    r13
0x1400085f9  push    r14
0x1400085fb  push    r15
0x1400085fd  sub     rsp, 38h
0x140008601  xor     eax, eax
0x140008603  movzx   ebp, cx
0x140008606  mov     word ptr [rsp+78h+LockState.OldIrql], ax
0x14000860e  mov     r12, r9
0x140008611  mov     [rsp+78h+LockState.Flags], al
0x140008618  mov     r15d, r8d
0x14000861b  mov     r13, rdx
0x14000861e  test    r8d, r8d
0x140008621  jz      loc_140008799
0x140008627  mov     rdx, cs:gWfpGlobal
0x14000862e  xor     r14d, r14d
0x140008631  cmp     bp, [rdx+188h]
0x140008638  jb      short loc_14000869B
0x14000863a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008641  lea     rbx, WPP_GLOBAL_Control
0x140008648  mov     rsi, 0FFFFFFFFC000000Dh
0x14000864f  cmp     rcx, rbx
0x140008652  jz      short loc_14000865E
0x140008654  cmp     byte ptr [rcx+29h], 2
0x140008658  jnb     loc_1400088C0
0x14000865e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008665  cmp     rcx, rbx
0x140008668  jz      short loc_1400086DA
0x14000866a  cmp     byte ptr [rcx+29h], 2
0x14000866e  jb      short loc_1400086DA
0x140008670  test    dword ptr [rcx+2Ch], 1000h
0x140008677  jz      short loc_1400086DA
0x140008679  mov     rcx, [rcx+18h]
0x14000867d  lea     r9, aGetlayerfromid_0; "GetLayerFromIdRead"
0x140008684  mov     edx, 0Fh
0x140008689  mov     [rsp+78h+var_58], esi
0x14000868d  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140008694  call    WPP_SF_sd
0x140008699  jmp     short loc_1400086DA
0x14000869b  imul    rdi, rbp, 88h
0x1400086a2  mov     ebx, r14d
0x1400086a5  mov     rsi, r14
0x1400086a8  add     rdi, [rdx+180h]
0x1400086af  mov     eax, [rdi+48h]
0x1400086b2  test    eax, eax
0x1400086b4  jz      short loc_1400086DA
0x1400086b6  cmp     ebx, eax
0x1400086b8  jnb     short loc_1400086D1
0x1400086ba  mov     ecx, ebx
0x1400086bc  shl     rcx, 4
0x1400086c0  add     rcx, [rdi+68h]
0x1400086c4  movsxd  rax, dword ptr [rcx+8]
0x1400086c8  cmp     eax, 4
0x1400086cb  jnz     loc_14000875F
0x1400086d1  mov     eax, [rdi+48h]
0x1400086d4  inc     ebx
0x1400086d6  cmp     ebx, eax
0x1400086d8  jb      short loc_1400086BA
0x1400086da  test    r15d, r15d
0x1400086dd  jnz     short loc_140008735
0x1400086df  cmp     cs:gWfpPerProContext, r14
0x1400086e6  mov     rbx, cs:gWfpGlobal
0x1400086ed  jz      short loc_14000871A
0x1400086ef  xor     ecx, ecx; ProcNumber
0x1400086f1  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400086f8  nop     dword ptr [rax+rax+00h]
0x1400086fd  imul    eax, cs:gWfpPerProContextSize
0x140008704  mov     ecx, eax
0x140008706  mov     rax, cs:gWfpPerProContext
0x14000870d  mov     rdx, [rcx+rax]
0x140008711  cmp     dword ptr [rdx], 4
0x140008714  jz      loc_140008881
0x14000871a  mov     rcx, [rbx+80h]; Lock
0x140008721  lea     rdx, [rsp+78h+LockState]; LockState
0x140008729  call    cs:__imp_NdisReleaseRWLock
0x140008730  nop     dword ptr [rax+rax+00h]
0x140008735  mov     eax, [r13+8]
0x140008739  test    al, 2
0x14000873b  jnz     loc_140008889
0x140008741  test    rsi, rsi
0x140008744  jnz     loc_14000888E
0x14000874a  mov     rax, rsi
0x14000874d  add     rsp, 38h
0x140008751  pop     r15
0x140008753  pop     r14
0x140008755  pop     r13
0x140008757  pop     r12
0x140008759  pop     rdi
0x14000875a  pop     rsi
0x14000875b  pop     rbp
0x14000875c  pop     rbx
0x14000875d  retn
0x14000875f  mov     rcx, [rcx]
0x140008762  add     rax, 4
0x140008766  imul    rdx, rax, 38h ; '8'
0x14000876a  mov     rax, cs:gWfpGlobal
0x140008771  mov     r9, r12
0x140008774  xor     r8d, r8d
0x140008777  mov     [rsp+78h+var_58], r14d
0x14000877c  mov     rax, [rdx+rax]
0x140008780  mov     rdx, r13
0x140008783  call    _guard_dispatch_icall
0x140008788  mov     rsi, rax
0x14000878b  test    rax, rax
0x14000878e  jz      loc_1400086D1
0x140008794  jmp     loc_1400086DA
0x140008799  mov     rdi, cs:gWfpGlobal
0x1400087a0  call    cs:__imp_KeGetCurrentIrql
0x1400087a7  nop     dword ptr [rax+rax+00h]
0x1400087ac  mov     rcx, [rdi+80h]; Lock
0x1400087b3  lea     rdx, [rsp+78h+LockState]; LockState
0x1400087bb  xor     r8d, r8d; Flags
0x1400087be  movzx   ebx, al
0x1400087c1  call    cs:__imp_NdisAcquireRWLockRead
0x1400087c8  nop     dword ptr [rax+rax+00h]
0x1400087cd  cmp     bl, 2
0x1400087d0  jz      short loc_140008812
0x1400087d2  cmp     cs:gWfpPerProContext, 0
0x1400087da  jz      short loc_140008812
0x1400087dc  xor     ecx, ecx; ProcNumber
0x1400087de  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400087e5  nop     dword ptr [rax+rax+00h]
0x1400087ea  imul    eax, cs:gWfpPerProContextSize
0x1400087f1  mov     ecx, eax
0x1400087f3  mov     rax, cs:gWfpPerProContext
0x1400087fa  mov     rdx, [rcx+rax]
0x1400087fe  mov     rax, ds:0FFFFF78000000008h
0x140008808  mov     [rdx+8], rax
0x14000880c  mov     dword ptr [rdx], 4
0x140008812  mov     rax, cs:gWfpGlobal
0x140008819  mov     ecx, [rax+0C0h]
0x14000881f  cmp     ecx, 2
0x140008822  jnz     loc_140008627
0x140008828  mov     r9d, 1
0x14000882e  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x140008835  mov     r8d, 0C0000001h
0x14000883b  call    WfpReportSysErrorAsNtStatus
0x140008840  mov     rsi, rax
0x140008843  test    rax, rax
0x140008846  jz      loc_140008627
0x14000884c  mov     rcx, cs:gWfpGlobal
0x140008853  lea     rdx, [rsp+78h+LockState]
0x14000885b  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000885f  call    WfpReleaseFastWriteLock
0x140008864  lea     rdx, aFeacquirereade; "FeAcquireReadEngineLock"
0x14000886b  mov     rcx, rsi
0x14000886e  call    WfpReportError
0x140008873  mov     rcx, [r12]; Entry
0x140008877  call    FreeMatchBufListInternal
0x14000887c  xor     r14d, r14d
0x14000887f  jmp     short loc_140008897
0x140008881  mov     [rdx], r14d
0x140008884  jmp     loc_14000871A
0x140008889  test    rsi, rsi
0x14000888c  jz      short loc_1400088AF
0x14000888e  mov     rcx, [r12]; Entry
0x140008892  call    FreeMatchBufListInternal
0x140008897  lea     rdx, aFeenumlayer; "FeEnumLayer"
0x14000889e  mov     [r12], r14
0x1400088a2  mov     rcx, rsi
0x1400088a5  call    WfpReportError
0x1400088aa  jmp     loc_14000874A
0x1400088af  mov     rcx, [r12]
0x1400088b3  call    SortMatchList
0x1400088b8  mov     rsi, rax
0x1400088bb  jmp     loc_140008741
0x1400088c0  test    dword ptr [rcx+2Ch], 1000h
0x1400088c7  jz      loc_14000865E
0x1400088cd  mov     rcx, [rcx+18h]
0x1400088d1  lea     r9, aGetlayerfromid_0; "GetLayerFromIdRead"
0x1400088d8  mov     edx, 0Ah
0x1400088dd  mov     [rsp+78h+var_58], esi
0x1400088e1  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400088e8  call    WPP_SF_sd
0x1400088ed  jmp     loc_14000865E
```
