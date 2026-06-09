# CheckOffloadFastForLayer

- ea: `0x140005b60`
- end: `0x14000605a`
- name: `CheckOffloadFastForLayer`
- size: `1274`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140035990`

## callees

- `0x140004720`
- `0x140004970`
- `0x140004bf0`
- `0x140005b60`
- `0x140006c80`
- `0x140008130`
- `0x140009520`
- `0x140009e00`
- `0x14000c210`
- `0x14001cfe0`
- `0x140038dc8`
- `0x14004efd4`
- `0x140078080`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140005cc8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140005df2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140005cc8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140005df2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005faa`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005faa`
- `NDIS!NdisReleaseRWLock` at `0x140005cfc`
- `NDIS!NdisReleaseRWLock` at `0x140005e26`
- `NDIS!NdisReleaseRWLock` at `0x140005cfc`
- `NDIS!NdisReleaseRWLock` at `0x140005e26`

## string_xrefs

- `0x140005be8`: `FeAcquireWriteEngineLock`
- `0x140005c59`: `GetLayerFromIdRead`
- `0x140005ff4`: `GetLayerFromIdRead`
- `0x14000603a`: `FeAcquireReadEngineLock`

## pseudocode

```c
__int64 __fastcall CheckOffloadFastForLayer(unsigned __int16 a1, char *a2)
{
  __int64 v2; // rbx
  char v4; // r15
  __int64 Flink_low; // rcx
  __int64 matched; // rsi
  __int64 v7; // rdi
  unsigned int v8; // ebx
  ULONGLONG v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  PNPAGED_LOOKASIDE_LIST v12; // rbx
  _DWORD *v13; // rdx
  __int16 *v14; // rdx
  __int16 *v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rdi
  void *v20; // rdi
  PNPAGED_LOOKASIDE_LIST v21; // rsi
  _DWORD *v22; // rdx
  bool v23; // dl
  signed __int64 v24; // rcx
  __int16 *v25; // rcx
  __int64 result; // rax
  __int64 v27; // rbx
  __int128 v28; // [rsp+30h] [rbp-30h] BYREF
  __int128 v29; // [rsp+40h] [rbp-20h]
  struct _LOCK_STATE_EX LockState; // [rsp+90h] [rbp+30h] BYREF
  PVOID Entry; // [rsp+98h] [rbp+38h] BYREF

  v2 = a1;
  v28 = 0;
  Entry = 0;
  v29 = 0;
  LOWORD(v28) = a1;
  DWORD1(v28) = 1;
  DWORD2(v29) = -1;
  if ( !*a2 )
  {
    FreeMatchBufListInternal(0);
    result = 0;
    *a2 = 0;
    return result;
  }
  v4 = 1;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  WfpAcquireFastReadLock((PNDIS_RW_LOCK_EX *)&gWfpGlobal[1], &LockState);
  Flink_low = LODWORD(gWfpGlobal[1].L.ListEntry.Flink);
  if ( (_DWORD)Flink_low == 2 )
  {
    matched = WfpReportSysErrorAsNtStatus(Flink_low, "FeAcquireWriteEngineLock", 3221225473LL, 1);
    if ( matched )
    {
      WfpReleaseFastWriteLock(&gWfpGlobal[1], &LockState);
      WfpReportError(matched, "FeAcquireReadEngineLock");
      FreeMatchBufListInternal(Entry);
      v27 = matched;
      goto LABEL_51;
    }
  }
  if ( (unsigned __int16)v2 < *((_WORD *)&gWfpGlobal[3].L.SingleListHead + 4) )
  {
    v7 = 136 * v2;
    v8 = 0;
    matched = 0;
    v9 = gWfpGlobal[3].L.ListHead.Alignment + v7;
    if ( *(_DWORD *)(v9 + 72) )
    {
      do
      {
        v10 = *(_QWORD *)(v9 + 104) + 16LL * v8;
        v11 = *(int *)(v10 + 8);
        if ( (_DWORD)v11 != 4 )
        {
          matched = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, PVOID *, _DWORD))&gWfpGlobal[1].L.Future[14 * v11 + 2])(
                      *(_QWORD *)v10,
                      &v28,
                      0,
                      &Entry,
                      0);
          if ( matched )
            break;
        }
        ++v8;
      }
      while ( v8 < *(_DWORD *)(v9 + 72) );
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
  v12 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v13 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v13 == 4 )
      *v13 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v12[1].L.ListHead.Alignment, &LockState);
  if ( (BYTE8(v28) & 2) != 0 )
  {
    if ( matched )
      goto LABEL_50;
    matched = SortMatchList(Entry);
  }
  if ( matched )
  {
LABEL_50:
    v27 = matched;
    FreeMatchBufListInternal(Entry);
LABEL_51:
    Entry = 0;
    WfpReportError(matched, "FeEnumLayer");
    FreeMatchBufListInternal(Entry);
    *a2 = 1;
    WfpReportError(v27, "CheckOffloadFastForLayer");
    return v27;
  }
  while ( 1 )
  {
    v14 = (__int16 *)Entry;
    if ( !Entry )
      break;
    if ( *((__int16 *)Entry + 13) == *((unsigned __int16 *)Entry + 12) - 1 )
    {
      v15 = 0;
      if ( *((_QWORD *)Entry + 2) )
        v15 = (__int16 *)*((_QWORD *)Entry + 2);
      FreeMatchBufEntry(Entry);
      if ( !v15 )
        break;
      v14 = v15;
    }
    v16 = v14[13];
    v17 = *(_QWORD *)&v14[4 * v16 + 20];
    v14[13] = v16 + 1;
    _InterlockedIncrement64((volatile signed __int64 *)(v17 + 16));
    Entry = v14;
    if ( !v17 )
      goto LABEL_44;
    v18 = *(_QWORD *)(v17 + 24);
    if ( (*(_DWORD *)(v18 + 40) & 0x4000) != 0 )
    {
      v19 = *(unsigned int *)(v18 + 44);
      *(_WORD *)&LockState.OldIrql = 0;
      LockState.Flags = 0;
      WfpAcquireFastReadLock((PNDIS_RW_LOCK_EX *)&gWfpGlobal[1], &LockState);
      if ( (unsigned int)v19 >= gWfpGlobal[3].L.FreeMisses
        || (v20 = (void *)(*(_QWORD *)&gWfpGlobal[3].L.Tag + 144 * v19), !*((_DWORD *)v20 + 1)) )
      {
        v20 = gFeCallout;
      }
      _InterlockedIncrement((volatile signed __int32 *)v20 + 16);
      v21 = gWfpGlobal;
      if ( gWfpPerProContext )
      {
        v22 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        if ( *v22 == 4 )
          *v22 = 0;
      }
      NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v21[1].L.ListHead.Alignment, &LockState);
      if ( (*((_BYTE *)v20 + 56) & 2) == 0 )
        v4 = 0;
      _InterlockedDecrement((volatile signed __int32 *)v20 + 16);
    }
    v23 = 0;
    _InterlockedIncrement64((volatile signed __int64 *)(v17 + 16));
    v24 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v17 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
    if ( (_DWORD)v24 == HIDWORD(v24) )
    {
      _m_prefetchw((const void *)(v17 + 52));
      v23 = (_InterlockedOr((volatile signed __int32 *)(v17 + 52), 0x10u) & 0x10) == 0;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(v17 + 24) + 40LL) & 0x4000) == 0 || !v23 )
      goto LABEL_40;
    if ( !KeGetCurrentIrql() )
    {
      FeNotifyIntFilterDelete(v17);
LABEL_40:
      if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v17 + 16), 0xFFFFFFFFFFFFFFFFuLL) == 1 )
        FreeWFPFilter((PVOID)v17);
      goto LABEL_42;
    }
    NetioInsertWorkQueue(&gWfpGlobal[10].L.FreeEx);
LABEL_42:
    if ( !v4 )
    {
      v14 = (__int16 *)Entry;
LABEL_44:
      v25 = v14;
      goto LABEL_45;
    }
  }
  v25 = 0;
  Entry = 0;
LABEL_45:
  FreeMatchBufListInternal(v25);
  result = 0;
  *a2 = v4;
  return result;
}

```

## disassembly

```asm
0x140005b60  push    rbp
0x140005b62  push    rbx
0x140005b63  push    rdi
0x140005b64  push    r12
0x140005b66  push    r13
0x140005b68  mov     rbp, rsp
0x140005b6b  sub     rsp, 60h
0x140005b6f  xor     r13d, r13d
0x140005b72  movzx   ebx, cx
0x140005b75  mov     ecx, r13d; Entry
0x140005b78  xorps   xmm0, xmm0
0x140005b7b  mov     edi, 1
0x140005b80  mov     r12, rdx
0x140005b83  movups  [rbp+var_30], xmm0
0x140005b87  mov     [rbp+Entry], rcx
0x140005b8b  movups  [rbp+var_20], xmm0
0x140005b8f  mov     word ptr [rbp+var_30], bx
0x140005b93  mov     dword ptr [rbp+var_30+4], edi
0x140005b96  mov     dword ptr [rbp+var_20+8], 0FFFFFFFFh
0x140005b9d  cmp     [rdx], cl
0x140005b9f  jz      loc_140006015
0x140005ba5  mov     rcx, cs:gWfpGlobal
0x140005bac  lea     rdx, [rbp+LockState]
0x140005bb0  xor     eax, eax
0x140005bb2  mov     [rsp+60h+arg_10], rsi
0x140005bba  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140005bbe  mov     [rsp+60h+var_10], r15
0x140005bc3  movzx   r15d, dil
0x140005bc7  mov     word ptr [rbp+LockState.OldIrql], ax
0x140005bcb  mov     [rbp+LockState.Flags], al
0x140005bce  call    WfpAcquireFastReadLock
0x140005bd3  mov     rax, cs:gWfpGlobal
0x140005bda  mov     ecx, [rax+0C0h]
0x140005be0  cmp     ecx, 2
0x140005be3  jnz     short loc_140005C06
0x140005be5  mov     r9d, edi
0x140005be8  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x140005bef  mov     r8d, 0C0000001h
0x140005bf5  call    WfpReportSysErrorAsNtStatus
0x140005bfa  mov     rsi, rax
0x140005bfd  test    rax, rax
0x140005c00  jnz     loc_140006026
0x140005c06  mov     rdx, cs:gWfpGlobal
0x140005c0d  cmp     bx, [rdx+188h]
0x140005c14  jb      short loc_140005C77
0x140005c16  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c1d  lea     rbx, WPP_GLOBAL_Control
0x140005c24  mov     rsi, 0FFFFFFFFC000000Dh
0x140005c2b  cmp     rcx, rbx
0x140005c2e  jz      short loc_140005C3A
0x140005c30  cmp     byte ptr [rcx+29h], 2
0x140005c34  jnb     loc_140005FE3
0x140005c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c41  cmp     rcx, rbx
0x140005c44  jz      short loc_140005CB6
0x140005c46  cmp     byte ptr [rcx+29h], 2
0x140005c4a  jb      short loc_140005CB6
0x140005c4c  test    dword ptr [rcx+2Ch], 1000h
0x140005c53  jz      short loc_140005CB6
0x140005c55  mov     rcx, [rcx+18h]
0x140005c59  lea     r9, aGetlayerfromid_0; "GetLayerFromIdRead"
0x140005c60  mov     edx, 0Fh
0x140005c65  mov     [rsp+60h+var_40], esi
0x140005c69  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140005c70  call    WPP_SF_sd
0x140005c75  jmp     short loc_140005CB6
0x140005c77  imul    rdi, rbx, 88h
0x140005c7e  mov     ebx, r13d
0x140005c81  mov     rsi, r13
0x140005c84  add     rdi, [rdx+180h]
0x140005c8b  mov     eax, [rdi+48h]
0x140005c8e  test    eax, eax
0x140005c90  jz      short loc_140005CB6
0x140005c92  cmp     ebx, eax
0x140005c94  jnb     short loc_140005CAD
0x140005c96  mov     ecx, ebx
0x140005c98  shl     rcx, 4
0x140005c9c  add     rcx, [rdi+68h]
0x140005ca0  movsxd  rax, dword ptr [rcx+8]
0x140005ca4  cmp     eax, 4
0x140005ca7  jnz     loc_140005ED4
0x140005cad  mov     eax, [rdi+48h]
0x140005cb0  inc     ebx
0x140005cb2  cmp     ebx, eax
0x140005cb4  jb      short loc_140005C96
0x140005cb6  cmp     cs:gWfpPerProContext, r13
0x140005cbd  mov     rbx, cs:gWfpGlobal
0x140005cc4  jz      short loc_140005CF1
0x140005cc6  xor     ecx, ecx; ProcNumber
0x140005cc8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140005ccf  nop     dword ptr [rax+rax+00h]
0x140005cd4  imul    eax, cs:gWfpPerProContextSize
0x140005cdb  mov     ecx, eax
0x140005cdd  mov     rax, cs:gWfpPerProContext
0x140005ce4  mov     rdx, [rcx+rax]
0x140005ce8  cmp     dword ptr [rdx], 4
0x140005ceb  jz      loc_140005F10
0x140005cf1  mov     rcx, [rbx+80h]; Lock
0x140005cf8  lea     rdx, [rbp+LockState]; LockState
0x140005cfc  call    cs:__imp_NdisReleaseRWLock
0x140005d03  nop     dword ptr [rax+rax+00h]
0x140005d08  test    byte ptr [rbp+var_30+8], 2
0x140005d0c  jnz     loc_140005F21
0x140005d12  test    rsi, rsi
0x140005d15  jnz     loc_140005F26
0x140005d1b  mov     [rsp+60h+var_8], r14
0x140005d20  mov     rdx, [rbp+Entry]
0x140005d24  test    rdx, rdx
0x140005d27  jz      loc_140005F18
0x140005d2d  movzx   ecx, word ptr [rdx+18h]
0x140005d31  movsx   eax, word ptr [rdx+1Ah]
0x140005d35  dec     ecx
0x140005d37  cmp     eax, ecx
0x140005d39  jnz     short loc_140005D5D
0x140005d3b  mov     rax, [rdx+10h]
0x140005d3f  mov     rbx, r13
0x140005d42  test    rax, rax
0x140005d45  mov     rcx, rdx; Entry
0x140005d48  cmovnz  rbx, rax
0x140005d4c  call    FreeMatchBufEntry
0x140005d51  test    rbx, rbx
0x140005d54  jz      loc_140005F18
0x140005d5a  mov     rdx, rbx
0x140005d5d  movsx   rcx, word ptr [rdx+1Ah]
0x140005d62  mov     rbx, [rdx+rcx*8+28h]
0x140005d67  inc     cx
0x140005d6a  mov     [rdx+1Ah], cx
0x140005d6e  lock inc qword ptr [rbx+10h]
0x140005d73  mov     [rbp+Entry], rdx
0x140005d77  test    rbx, rbx
0x140005d7a  jz      loc_140005EA6
0x140005d80  mov     rcx, [rbx+18h]
0x140005d84  test    dword ptr [rcx+28h], 4000h
0x140005d8b  jz      loc_140005E42
0x140005d91  mov     edi, [rcx+2Ch]
0x140005d94  lea     rdx, [rbp+LockState]
0x140005d98  mov     rcx, cs:gWfpGlobal
0x140005d9f  xor     eax, eax
0x140005da1  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140005da5  mov     word ptr [rbp+LockState.OldIrql], ax
0x140005da9  mov     [rbp+LockState.Flags], al
0x140005dac  call    WfpAcquireFastReadLock
0x140005db1  mov     rdx, cs:gWfpGlobal
0x140005db8  cmp     edi, [rdx+1A0h]
0x140005dbe  jnb     short loc_140005DD5
0x140005dc0  lea     rdi, [rdi+rdi*8]
0x140005dc4  shl     rdi, 4
0x140005dc8  add     rdi, [rdx+1A8h]
0x140005dcf  cmp     [rdi+4], r13d
0x140005dd3  jnz     short loc_140005DDC
0x140005dd5  mov     rdi, cs:gFeCallout
0x140005ddc  lock inc dword ptr [rdi+40h]
0x140005de0  cmp     cs:gWfpPerProContext, r13
0x140005de7  mov     rsi, cs:gWfpGlobal
0x140005dee  jz      short loc_140005E1B
0x140005df0  xor     ecx, ecx; ProcNumber
0x140005df2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140005df9  nop     dword ptr [rax+rax+00h]
0x140005dfe  imul    eax, cs:gWfpPerProContextSize
0x140005e05  mov     ecx, eax
0x140005e07  mov     rax, cs:gWfpPerProContext
0x140005e0e  mov     rdx, [rcx+rax]
0x140005e12  cmp     dword ptr [rdx], 4
0x140005e15  jz      loc_140005F6C
0x140005e1b  mov     rcx, [rsi+80h]; Lock
0x140005e22  lea     rdx, [rbp+LockState]; LockState
0x140005e26  call    cs:__imp_NdisReleaseRWLock
0x140005e2d  nop     dword ptr [rax+rax+00h]
0x140005e32  test    byte ptr [rdi+38h], 2
0x140005e36  movzx   r15d, r15b
0x140005e3a  cmovz   r15d, r13d
0x140005e3e  lock dec dword ptr [rdi+40h]
0x140005e42  xor     dl, dl
0x140005e44  lock inc qword ptr [rbx+10h]
0x140005e49  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140005e50  lock xadd [rbx+10h], rcx
0x140005e56  sub     rcx, 2
0x140005e5a  mov     rax, rcx
0x140005e5d  shr     rax, 20h
0x140005e61  cmp     ecx, eax
0x140005e63  jz      loc_140005F85
0x140005e69  mov     rax, [rbx+18h]
0x140005e6d  test    dword ptr [rax+28h], 4000h
0x140005e74  jz      short loc_140005E7E
0x140005e76  test    dl, dl
0x140005e78  jnz     loc_140005FAA
0x140005e7e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140005e85  lock xadd [rbx+10h], rax
0x140005e8b  cmp     rax, 1
0x140005e8f  jnz     short loc_140005E99
0x140005e91  mov     rcx, rbx; P
0x140005e94  call    FreeWFPFilter
0x140005e99  test    r15b, r15b
0x140005e9c  jnz     loc_140005D20
0x140005ea2  mov     rdx, [rbp+Entry]
0x140005ea6  mov     rcx, rdx; Entry
0x140005ea9  call    FreeMatchBufListInternal
0x140005eae  mov     r14, [rsp+60h+var_8]
0x140005eb3  mov     rax, r13
0x140005eb6  mov     [r12], r15b
0x140005eba  mov     rsi, [rsp+60h+arg_10]
0x140005ec2  mov     r15, [rsp+60h+var_10]
0x140005ec7  add     rsp, 60h
0x140005ecb  pop     r13
0x140005ecd  pop     r12
0x140005ecf  pop     rdi
0x140005ed0  pop     rbx
0x140005ed1  pop     rbp
0x140005ed2  retn
0x140005ed4  mov     rcx, [rcx]
0x140005ed7  lea     r9, [rbp+Entry]
0x140005edb  add     rax, 4
0x140005edf  mov     [rsp+60h+var_40], r13d
0x140005ee4  imul    rdx, rax, 38h ; '8'
0x140005ee8  mov     rax, cs:gWfpGlobal
0x140005eef  xor     r8d, r8d
0x140005ef2  mov     rax, [rdx+rax]
0x140005ef6  lea     rdx, [rbp+var_30]
0x140005efa  call    _guard_dispatch_icall
0x140005eff  mov     rsi, rax
0x140005f02  test    rax, rax
0x140005f05  jz      loc_140005CAD
0x140005f0b  jmp     loc_140005CB6
0x140005f10  mov     [rdx], r13d
0x140005f13  jmp     loc_140005CF1
0x140005f18  mov     rcx, r13
0x140005f1b  mov     [rbp+Entry], rcx
0x140005f1f  jmp     short loc_140005EA9
0x140005f21  test    rsi, rsi
0x140005f24  jz      short loc_140005F74
0x140005f26  mov     rcx, [rbp+Entry]; Entry
0x140005f2a  mov     rbx, rsi
0x140005f2d  call    FreeMatchBufListInternal
0x140005f32  mov     rax, r13
0x140005f35  lea     rdx, aFeenumlayer; "FeEnumLayer"
0x140005f3c  mov     rcx, rsi
0x140005f3f  mov     [rbp+Entry], rax
0x140005f43  call    WfpReportError
0x140005f48  mov     rcx, [rbp+Entry]; Entry
0x140005f4c  call    FreeMatchBufListInternal
0x140005f51  lea     rdx, aCheckoffloadfa; "CheckOffloadFastForLayer"
0x140005f58  mov     [r12], r15b
0x140005f5c  mov     rcx, rbx
0x140005f5f  call    WfpReportError
0x140005f64  mov     rax, rbx
0x140005f67  jmp     loc_140005EBA
0x140005f6c  mov     [rdx], r13d
0x140005f6f  jmp     loc_140005E1B
0x140005f74  mov     rcx, [rbp+Entry]
0x140005f78  call    SortMatchList
0x140005f7d  mov     rsi, rax
0x140005f80  jmp     loc_140005D12
0x140005f85  prefetchw byte ptr [rbx+34h]
0x140005f89  mov     eax, [rbx+34h]
0x140005f8c  mov     ecx, eax
0x140005f8e  or      ecx, 10h
0x140005f91  lock cmpxchg [rbx+34h], ecx
0x140005f96  jnz     short loc_140005F8C
0x140005f98  test    al, 10h
0x140005f9a  movzx   edx, dl
0x140005f9d  mov     eax, 1
0x140005fa2  cmovz   edx, eax
0x140005fa5  jmp     loc_140005E69
0x140005faa  call    cs:__imp_KeGetCurrentIrql
0x140005fb1  nop     dword ptr [rax+rax+00h]
0x140005fb6  test    al, al
0x140005fb8  jnz     short loc_140005FC7
0x140005fba  mov     rcx, rbx
0x140005fbd  call    FeNotifyIntFilterDelete
0x140005fc2  jmp     loc_140005E7E
0x140005fc7  mov     rcx, cs:gWfpGlobal
0x140005fce  lea     rdx, [rbx+28h]
0x140005fd2  add     rcx, 538h; Context
0x140005fd9  call    NetioInsertWorkQueue
0x140005fde  jmp     loc_140005E99
0x140005fe3  test    dword ptr [rcx+2Ch], 1000h
0x140005fea  jz      loc_140005C3A
0x140005ff0  mov     rcx, [rcx+18h]
0x140005ff4  lea     r9, aGetlayerfromid_0; "GetLayerFromIdRead"
0x140005ffb  mov     edx, 0Ah
0x140006000  mov     [rsp+60h+var_40], esi
0x140006004  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000600b  call    WPP_SF_sd
0x140006010  jmp     loc_140005C3A
0x140006015  call    FreeMatchBufListInternal
0x14000601a  mov     rax, r13
0x14000601d  mov     [r12], r13b
0x140006021  jmp     loc_140005EC7
0x140006026  mov     rcx, cs:gWfpGlobal
0x14000602d  lea     rdx, [rbp+LockState]
0x140006031  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140006035  call    WfpReleaseFastWriteLock
0x14000603a  lea     rdx, aFeacquirereade; "FeAcquireReadEngineLock"
0x140006041  mov     rcx, rsi
0x140006044  call    WfpReportError
0x140006049  mov     rcx, [rbp+Entry]; Entry
0x14000604d  call    FreeMatchBufListInternal
0x140006052  mov     rbx, rsi
0x140006055  jmp     loc_140005F32
```
