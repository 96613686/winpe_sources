# WfpAssociateContextToFlow

- ea: `0x14000a900`
- end: `0x14000ab1f`
- name: `WfpAssociateContextToFlow`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14000a900`
- `0x14000ab30`
- `0x14001cfe0`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a966`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000aa37`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a966`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000aa37`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a92b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a92b`
- `NDIS!NdisAcquireRWLockRead` at `0x14000a949`
- `NDIS!NdisAcquireRWLockRead` at `0x14000a949`
- `NDIS!NdisReleaseRWLock` at `0x14000aa68`
- `NDIS!NdisReleaseRWLock` at `0x14000aa68`

## string_xrefs

- `0x14000a9b2`: `FeAcquireWriteEngineLock`
- `0x14000aaee`: `FeAcquireReadEngineLock`

## pseudocode

```c
__int64 __fastcall WfpAssociateContextToFlow(int a1, unsigned __int16 a2, int a3, __int64 a4)
{
  PNPAGED_LOOKASIDE_LIST v4; // rdi
  __int64 v7; // rbp
  KIRQL CurrentIrql; // bl
  __int64 v10; // rdx
  __int64 Flink_low; // rcx
  __int64 v12; // rbx
  PNPAGED_LOOKASIDE_LIST v13; // rdi
  _DWORD *v14; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-48h] BYREF

  v4 = gWfpGlobal;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v7 = a2;
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v4[1].L.ListHead.Alignment, &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v10 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v10 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v10 = 4;
  }
  Flink_low = LODWORD(gWfpGlobal[1].L.ListEntry.Flink);
  if ( (_DWORD)Flink_low == 2 )
  {
    v12 = WfpReportSysErrorAsNtStatus(Flink_low, "FeAcquireWriteEngineLock", 3221225473LL, 1);
    if ( v12 )
    {
      WfpReleaseFastWriteLock(&gWfpGlobal[1], &LockState);
      WfpReportError(v12, "FeAcquireReadEngineLock");
LABEL_14:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpAssociateContextToFlow",
          v12);
      }
      return v12;
    }
  }
  if ( a4 )
  {
    v12 = WfpAssociateContextToFlowInternal(a1, (unsigned __int16)v7, a3, a4, 0);
    if ( !v12 && (unsigned __int16)v7 < *((_WORD *)&gWfpGlobal[3].L.SingleListHead + 4) )
      _InterlockedIncrement((volatile signed __int32 *)(136 * v7 + gWfpGlobal[3].L.ListHead.Alignment + 68));
  }
  else
  {
    v12 = WfpReportSysErrorAsNtStatus(Flink_low, "WfpAssociateContextToFlow", 3221225485LL, 1);
  }
  v13 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v14 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v14 == 4 )
      *v14 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v13[1].L.ListHead.Alignment, &LockState);
  if ( v12 )
    goto LABEL_14;
  return v12;
}

```

## disassembly

```asm
0x14000a900  push    rbx
0x14000a902  push    rbp
0x14000a903  push    rsi
0x14000a904  push    rdi
0x14000a905  push    r14
0x14000a907  push    r15
0x14000a909  sub     rsp, 48h
0x14000a90d  mov     rdi, cs:gWfpGlobal
0x14000a914  xor     eax, eax
0x14000a916  mov     word ptr [rsp+78h+LockState.OldIrql], ax
0x14000a91b  mov     rsi, r9
0x14000a91e  mov     [rsp+78h+LockState.Flags], al
0x14000a922  mov     r14d, r8d
0x14000a925  movzx   ebp, dx
0x14000a928  mov     r15, rcx
0x14000a92b  call    cs:__imp_KeGetCurrentIrql
0x14000a932  nop     dword ptr [rax+rax+00h]
0x14000a937  mov     rcx, [rdi+80h]; Lock
0x14000a93e  lea     rdx, [rsp+78h+LockState]; LockState
0x14000a943  xor     r8d, r8d; Flags
0x14000a946  movzx   ebx, al
0x14000a949  call    cs:__imp_NdisAcquireRWLockRead
0x14000a950  nop     dword ptr [rax+rax+00h]
0x14000a955  cmp     bl, 2
0x14000a958  jz      short loc_14000A99A
0x14000a95a  cmp     cs:gWfpPerProContext, 0
0x14000a962  jz      short loc_14000A99A
0x14000a964  xor     ecx, ecx; ProcNumber
0x14000a966  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000a96d  nop     dword ptr [rax+rax+00h]
0x14000a972  imul    eax, cs:gWfpPerProContextSize
0x14000a979  mov     ecx, eax
0x14000a97b  mov     rax, cs:gWfpPerProContext
0x14000a982  mov     rdx, [rcx+rax]
0x14000a986  mov     rax, ds:0FFFFF78000000008h
0x14000a990  mov     [rdx+8], rax
0x14000a994  mov     dword ptr [rdx], 4
0x14000a99a  mov     rax, cs:gWfpGlobal
0x14000a9a1  mov     ecx, [rax+0C0h]
0x14000a9a7  cmp     ecx, 2
0x14000a9aa  jnz     short loc_14000A9D0
0x14000a9ac  mov     r9d, 1
0x14000a9b2  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x14000a9b9  mov     r8d, 0C0000001h
0x14000a9bf  call    WfpReportSysErrorAsNtStatus
0x14000a9c4  mov     rbx, rax
0x14000a9c7  test    rax, rax
0x14000a9ca  jnz     loc_14000AAD9
0x14000a9d0  mov     [rsp+78h+arg_0], r12
0x14000a9d8  xor     r12d, r12d
0x14000a9db  test    rsi, rsi
0x14000a9de  jz      loc_14000AAFF
0x14000a9e4  mov     r9, rsi
0x14000a9e7  mov     [rsp+78h+var_58], r12
0x14000a9ec  mov     r8d, r14d
0x14000a9ef  movzx   edx, bp
0x14000a9f2  mov     rcx, r15
0x14000a9f5  call    WfpAssociateContextToFlowInternal
0x14000a9fa  mov     rbx, rax
0x14000a9fd  test    rax, rax
0x14000aa00  jnz     short loc_14000AA25
0x14000aa02  mov     rdx, cs:gWfpGlobal
0x14000aa09  cmp     bp, [rdx+188h]
0x14000aa10  jnb     short loc_14000AA25
0x14000aa12  mov     rax, [rdx+180h]
0x14000aa19  imul    rcx, rbp, 88h
0x14000aa20  lock inc dword ptr [rcx+rax+44h]
0x14000aa25  cmp     cs:gWfpPerProContext, r12
0x14000aa2c  mov     rdi, cs:gWfpGlobal
0x14000aa33  jz      short loc_14000AA5C
0x14000aa35  xor     ecx, ecx; ProcNumber
0x14000aa37  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000aa3e  nop     dword ptr [rax+rax+00h]
0x14000aa43  imul    eax, cs:gWfpPerProContextSize
0x14000aa4a  mov     ecx, eax
0x14000aa4c  mov     rax, cs:gWfpPerProContext
0x14000aa53  mov     rdx, [rcx+rax]
0x14000aa57  cmp     dword ptr [rdx], 4
0x14000aa5a  jz      short loc_14000AAD4
0x14000aa5c  mov     rcx, [rdi+80h]; Lock
0x14000aa63  lea     rdx, [rsp+78h+LockState]; LockState
0x14000aa68  call    cs:__imp_NdisReleaseRWLock
0x14000aa6f  nop     dword ptr [rax+rax+00h]
0x14000aa74  mov     r12, [rsp+78h+arg_0]
0x14000aa7c  test    rbx, rbx
0x14000aa7f  jz      short loc_14000AAC3
0x14000aa81  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa88  lea     rax, WPP_GLOBAL_Control
0x14000aa8f  cmp     rcx, rax
0x14000aa92  jz      short loc_14000AAC3
0x14000aa94  cmp     byte ptr [rcx+29h], 2
0x14000aa98  jb      short loc_14000AAC3
0x14000aa9a  test    dword ptr [rcx+2Ch], 1000h
0x14000aaa1  jz      short loc_14000AAC3
0x14000aaa3  mov     rcx, [rcx+18h]
0x14000aaa7  lea     r9, aWfpassociateco_1; "WfpAssociateContextToFlow"
0x14000aaae  mov     edx, 0Fh
0x14000aab3  mov     dword ptr [rsp+78h+var_58], ebx
0x14000aab7  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000aabe  call    WPP_SF_sd
0x14000aac3  mov     rax, rbx
0x14000aac6  add     rsp, 48h
0x14000aaca  pop     r15
0x14000aacc  pop     r14
0x14000aace  pop     rdi
0x14000aacf  pop     rsi
0x14000aad0  pop     rbp
0x14000aad1  pop     rbx
0x14000aad2  retn
0x14000aad4  mov     [rdx], r12d
0x14000aad7  jmp     short loc_14000AA5C
0x14000aad9  mov     rcx, cs:gWfpGlobal
0x14000aae0  lea     rdx, [rsp+78h+LockState]
0x14000aae5  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000aae9  call    WfpReleaseFastWriteLock
0x14000aaee  lea     rdx, aFeacquirereade; "FeAcquireReadEngineLock"
0x14000aaf5  mov     rcx, rbx
0x14000aaf8  call    WfpReportError
0x14000aafd  jmp     short loc_14000AA81
0x14000aaff  mov     r9d, 1
0x14000ab05  lea     rdx, aWfpassociateco_1; "WfpAssociateContextToFlow"
0x14000ab0c  mov     r8d, 0C000000Dh
0x14000ab12  call    WfpReportSysErrorAsNtStatus
0x14000ab17  mov     rbx, rax
0x14000ab1a  jmp     loc_14000AA25
```
