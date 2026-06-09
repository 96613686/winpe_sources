# IsAcceptCacheDisabled

- ea: `0x140009fd0`
- end: `0x14000a21e`
- name: `IsAcceptCacheDisabled`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140009e70`

## callees

- `0x140009520`
- `0x140009e00`
- `0x140009fd0`
- `0x14001cfe0`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a038`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a127`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a038`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a127`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009ffe`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009ffe`
- `NDIS!NdisAcquireRWLockRead` at `0x14000a01c`
- `NDIS!NdisAcquireRWLockRead` at `0x14000a01c`
- `NDIS!NdisReleaseRWLock` at `0x14000a158`
- `NDIS!NdisReleaseRWLock` at `0x14000a158`

## string_xrefs

- `0x14000a084`: `FeAcquireWriteEngineLock`
- `0x14000a0f9`: `GetLayerFromIdRead`
- `0x14000a1c5`: `GetLayerFromIdRead`
- `0x14000a20a`: `IsAcceptCacheDisabled`
- `0x14000a1fb`: `FeAcquireReadEngineLock`

## pseudocode

```c
__int64 __fastcall IsAcceptCacheDisabled(unsigned __int16 a1, _DWORD *a2)
{
  PNPAGED_LOOKASIDE_LIST v2; // rdi
  __int64 v4; // rsi
  KIRQL CurrentIrql; // bl
  __int64 v6; // rdx
  __int64 Flink_low; // rcx
  __int64 v8; // rbx
  PNPAGED_LOOKASIDE_LIST v9; // rdi
  _DWORD *v10; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

  v2 = gWfpGlobal;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *a2 = 0;
  v4 = a1;
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v2[1].L.ListHead.Alignment, &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v6 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v6 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v6 = 4;
  }
  Flink_low = LODWORD(gWfpGlobal[1].L.ListEntry.Flink);
  if ( (_DWORD)Flink_low == 2 )
  {
    v8 = WfpReportSysErrorAsNtStatus(Flink_low, "FeAcquireWriteEngineLock", 3221225473LL, 1);
    if ( v8 )
    {
      WfpReleaseFastWriteLock(&gWfpGlobal[1], &LockState);
      WfpReportError(v8, "FeAcquireReadEngineLock");
LABEL_23:
      WfpReportError(v8, "IsAcceptCacheDisabled");
      return v8;
    }
  }
  if ( (unsigned __int16)v4 < *((_WORD *)&gWfpGlobal[3].L.SingleListHead + 4) )
  {
    v8 = 0;
    if ( (*(_DWORD *)(136 * v4 + gWfpGlobal[3].L.ListHead.Alignment + 128) & 1) != 0 )
      *a2 = 1;
  }
  else
  {
    v8 = -1073741811;
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
  v9 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v10 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v10 == 4 )
      *v10 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v9[1].L.ListHead.Alignment, &LockState);
  if ( v8 )
    goto LABEL_23;
  return v8;
}

```

## disassembly

```asm
0x140009fd0  mov     [rsp+arg_0], rbx
0x140009fd5  mov     [rsp+arg_10], rbp
0x140009fda  push    rsi
0x140009fdb  push    rdi
0x140009fdc  push    r14
0x140009fde  sub     rsp, 30h
0x140009fe2  mov     rdi, cs:gWfpGlobal
0x140009fe9  xor     eax, eax
0x140009feb  xor     ebp, ebp
0x140009fed  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140009ff2  mov     [rsp+48h+LockState.Flags], al
0x140009ff6  mov     r14, rdx
0x140009ff9  mov     [rdx], ebp
0x140009ffb  movzx   esi, cx
0x140009ffe  call    cs:__imp_KeGetCurrentIrql
0x14000a005  nop     dword ptr [rax+rax+00h]
0x14000a00a  mov     rcx, [rdi+80h]; Lock
0x14000a011  lea     rdx, [rsp+48h+LockState]; LockState
0x14000a016  xor     r8d, r8d; Flags
0x14000a019  movzx   ebx, al
0x14000a01c  call    cs:__imp_NdisAcquireRWLockRead
0x14000a023  nop     dword ptr [rax+rax+00h]
0x14000a028  cmp     bl, 2
0x14000a02b  jz      short loc_14000A06C
0x14000a02d  cmp     cs:gWfpPerProContext, rbp
0x14000a034  jz      short loc_14000A06C
0x14000a036  xor     ecx, ecx; ProcNumber
0x14000a038  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000a03f  nop     dword ptr [rax+rax+00h]
0x14000a044  imul    eax, cs:gWfpPerProContextSize
0x14000a04b  mov     ecx, eax
0x14000a04d  mov     rax, cs:gWfpPerProContext
0x14000a054  mov     rdx, [rcx+rax]
0x14000a058  mov     rax, ds:0FFFFF78000000008h
0x14000a062  mov     [rdx+8], rax
0x14000a066  mov     dword ptr [rdx], 4
0x14000a06c  mov     rax, cs:gWfpGlobal
0x14000a073  mov     ecx, [rax+0C0h]
0x14000a079  cmp     ecx, 2
0x14000a07c  jnz     short loc_14000A0A2
0x14000a07e  mov     r9d, 1
0x14000a084  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x14000a08b  mov     r8d, 0C0000001h
0x14000a091  call    WfpReportSysErrorAsNtStatus
0x14000a096  mov     rbx, rax
0x14000a099  test    rax, rax
0x14000a09c  jnz     loc_14000A1E6
0x14000a0a2  mov     rdx, cs:gWfpGlobal
0x14000a0a9  cmp     si, [rdx+188h]
0x14000a0b0  jb      loc_14000A188
0x14000a0b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a0bd  lea     rdi, WPP_GLOBAL_Control
0x14000a0c4  mov     rbx, 0FFFFFFFFC000000Dh
0x14000a0cb  cmp     rcx, rdi
0x14000a0ce  jz      short loc_14000A0DA
0x14000a0d0  cmp     byte ptr [rcx+29h], 2
0x14000a0d4  jnb     loc_14000A1B4
0x14000a0da  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a0e1  cmp     rcx, rdi
0x14000a0e4  jz      short loc_14000A115
0x14000a0e6  cmp     byte ptr [rcx+29h], 2
0x14000a0ea  jb      short loc_14000A115
0x14000a0ec  test    dword ptr [rcx+2Ch], 1000h
0x14000a0f3  jz      short loc_14000A115
0x14000a0f5  mov     rcx, [rcx+18h]
0x14000a0f9  lea     r9, aGetlayerfromid_0; "GetLayerFromIdRead"
0x14000a100  mov     edx, 0Fh
0x14000a105  mov     [rsp+48h+var_28], ebx
0x14000a109  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000a110  call    WPP_SF_sd
0x14000a115  cmp     cs:gWfpPerProContext, rbp
0x14000a11c  mov     rdi, cs:gWfpGlobal
0x14000a123  jz      short loc_14000A14C
0x14000a125  xor     ecx, ecx; ProcNumber
0x14000a127  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000a12e  nop     dword ptr [rax+rax+00h]
0x14000a133  imul    eax, cs:gWfpPerProContextSize
0x14000a13a  mov     ecx, eax
0x14000a13c  mov     rax, cs:gWfpPerProContext
0x14000a143  mov     rdx, [rcx+rax]
0x14000a147  cmp     dword ptr [rdx], 4
0x14000a14a  jz      short loc_14000A184
0x14000a14c  mov     rcx, [rdi+80h]; Lock
0x14000a153  lea     rdx, [rsp+48h+LockState]; LockState
0x14000a158  call    cs:__imp_NdisReleaseRWLock
0x14000a15f  nop     dword ptr [rax+rax+00h]
0x14000a164  test    rbx, rbx
0x14000a167  jnz     loc_14000A20A
0x14000a16d  mov     rbp, [rsp+48h+arg_10]
0x14000a172  mov     rax, rbx
0x14000a175  mov     rbx, [rsp+48h+arg_0]
0x14000a17a  add     rsp, 30h
0x14000a17e  pop     r14
0x14000a180  pop     rdi
0x14000a181  pop     rsi
0x14000a182  retn
0x14000a184  mov     [rdx], ebp
0x14000a186  jmp     short loc_14000A14C
0x14000a188  mov     rax, [rdx+180h]
0x14000a18f  mov     rbx, rbp
0x14000a192  imul    rcx, rsi, 88h
0x14000a199  mov     eax, [rcx+rax+80h]
0x14000a1a0  test    al, 1
0x14000a1a2  jz      loc_14000A115
0x14000a1a8  mov     dword ptr [r14], 1
0x14000a1af  jmp     loc_14000A115
0x14000a1b4  test    dword ptr [rcx+2Ch], 1000h
0x14000a1bb  jz      loc_14000A0DA
0x14000a1c1  mov     rcx, [rcx+18h]
0x14000a1c5  lea     r9, aGetlayerfromid_0; "GetLayerFromIdRead"
0x14000a1cc  mov     edx, 0Ah
0x14000a1d1  mov     [rsp+48h+var_28], ebx
0x14000a1d5  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000a1dc  call    WPP_SF_sd
0x14000a1e1  jmp     loc_14000A0DA
0x14000a1e6  mov     rcx, cs:gWfpGlobal
0x14000a1ed  lea     rdx, [rsp+48h+LockState]
0x14000a1f2  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000a1f6  call    WfpReleaseFastWriteLock
0x14000a1fb  lea     rdx, aFeacquirereade; "FeAcquireReadEngineLock"
0x14000a202  mov     rcx, rbx
0x14000a205  call    WfpReportError
0x14000a20a  lea     rdx, aIsacceptcached; "IsAcceptCacheDisabled"
0x14000a211  mov     rcx, rbx
0x14000a214  call    WfpReportError
0x14000a219  jmp     loc_14000A16D
```
