# CClfsRequest::FinalizeGlobals(void)

- ea: `0x140040da4`
- end: `0x140040f60`
- name: `?FinalizeGlobals@CClfsRequest@@SAXXZ`
- size: `444`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140035660`

## callees

- `0x140040da4`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140040dbb`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140040dbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ddb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040dfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040e1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040e3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040e5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040e80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ec2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ee3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ddb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040dfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040e1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040e3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040e5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040e80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ec2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ee3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f46`

## pseudocode

```c
void CClfsRequest::FinalizeGlobals(void)
{
  if ( CClfsRequest::m_fInitialize )
  {
    ExDeleteNPagedLookasideList(&CClfsRequest::m_laList);
    CClfsRequest::m_fInitialize = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_Initial )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_Initial, 0);
    CClfsRequest::m_pCClfsRequest_State_Initial = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_Done )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_Done, 0);
    CClfsRequest::m_pCClfsRequest_State_Done = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_FlushPending )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_FlushPending, 0);
    CClfsRequest::m_pCClfsRequest_State_FlushPending = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_AppendPendingFlush )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_AppendPendingFlush, 0);
    CClfsRequest::m_pCClfsRequest_State_AppendPendingFlush = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_ReadAwaitingCompletion )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_ReadAwaitingCompletion, 0);
    CClfsRequest::m_pCClfsRequest_State_ReadAwaitingCompletion = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_ReadPending )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_ReadPending, 0);
    CClfsRequest::m_pCClfsRequest_State_ReadPending = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_ReadPendingFailed )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_ReadPendingFailed, 0);
    CClfsRequest::m_pCClfsRequest_State_ReadPendingFailed = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_WriteRestartPending )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_WriteRestartPending, 0);
    CClfsRequest::m_pCClfsRequest_State_WriteRestartPending = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_WriteRestartInProgress )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_WriteRestartInProgress, 0);
    CClfsRequest::m_pCClfsRequest_State_WriteRestartInProgress = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_AdvanceLogBasePending )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_AdvanceLogBasePending, 0);
    CClfsRequest::m_pCClfsRequest_State_AdvanceLogBasePending = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart, 0);
    CClfsRequest::m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart = 0;
  }
  if ( CClfsRequest::m_pCClfsRequest_State_ReadMgmtNotificationPending )
  {
    ExFreePoolWithTag(CClfsRequest::m_pCClfsRequest_State_ReadMgmtNotificationPending, 0);
    CClfsRequest::m_pCClfsRequest_State_ReadMgmtNotificationPending = 0;
  }
}

```

## disassembly

```asm
0x140040da4  push    rbx
0x140040da6  sub     rsp, 20h
0x140040daa  xor     ebx, ebx
0x140040dac  cmp     cs:?m_fInitialize@CClfsRequest@@0_NA, bl; bool CClfsRequest::m_fInitialize
0x140040db2  jz      short loc_140040DCD
0x140040db4  lea     rcx, ?m_laList@CClfsRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140040dbb  call    cs:__imp_ExDeleteNPagedLookasideList
0x140040dc2  nop     dword ptr [rax+rax+00h]
0x140040dc7  mov     cs:?m_fInitialize@CClfsRequest@@0_NA, bl; bool CClfsRequest::m_fInitialize
0x140040dcd  mov     rcx, cs:?m_pCClfsRequest_State_Initial@CClfsRequest@@0PEAVCClfsRequest_State_Initial@@EA; P
0x140040dd4  test    rcx, rcx
0x140040dd7  jz      short loc_140040DEE
0x140040dd9  xor     edx, edx; Tag
0x140040ddb  call    cs:__imp_ExFreePoolWithTag
0x140040de2  nop     dword ptr [rax+rax+00h]
0x140040de7  mov     cs:?m_pCClfsRequest_State_Initial@CClfsRequest@@0PEAVCClfsRequest_State_Initial@@EA, rbx; CClfsRequest_State_Initial * CClfsRequest::m_pCClfsRequest_State_Initial
0x140040dee  mov     rcx, cs:?m_pCClfsRequest_State_Done@CClfsRequest@@0PEAVCClfsRequest_State_Done@@EA; P
0x140040df5  test    rcx, rcx
0x140040df8  jz      short loc_140040E0F
0x140040dfa  xor     edx, edx; Tag
0x140040dfc  call    cs:__imp_ExFreePoolWithTag
0x140040e03  nop     dword ptr [rax+rax+00h]
0x140040e08  mov     cs:?m_pCClfsRequest_State_Done@CClfsRequest@@0PEAVCClfsRequest_State_Done@@EA, rbx; CClfsRequest_State_Done * CClfsRequest::m_pCClfsRequest_State_Done
0x140040e0f  mov     rcx, cs:?m_pCClfsRequest_State_FlushPending@CClfsRequest@@0PEAVCClfsRequest_State_FlushPending@@EA; P
0x140040e16  test    rcx, rcx
0x140040e19  jz      short loc_140040E30
0x140040e1b  xor     edx, edx; Tag
0x140040e1d  call    cs:__imp_ExFreePoolWithTag
0x140040e24  nop     dword ptr [rax+rax+00h]
0x140040e29  mov     cs:?m_pCClfsRequest_State_FlushPending@CClfsRequest@@0PEAVCClfsRequest_State_FlushPending@@EA, rbx; CClfsRequest_State_FlushPending * CClfsRequest::m_pCClfsRequest_State_FlushPending
0x140040e30  mov     rcx, cs:?m_pCClfsRequest_State_AppendPendingFlush@CClfsRequest@@0PEAVCClfsRequest_State_AppendPendingFlush@@EA; P
0x140040e37  test    rcx, rcx
0x140040e3a  jz      short loc_140040E51
0x140040e3c  xor     edx, edx; Tag
0x140040e3e  call    cs:__imp_ExFreePoolWithTag
0x140040e45  nop     dword ptr [rax+rax+00h]
0x140040e4a  mov     cs:?m_pCClfsRequest_State_AppendPendingFlush@CClfsRequest@@0PEAVCClfsRequest_State_AppendPendingFlush@@EA, rbx; CClfsRequest_State_AppendPendingFlush * CClfsRequest::m_pCClfsRequest_State_AppendPendingFlush
0x140040e51  mov     rcx, cs:?m_pCClfsRequest_State_ReadAwaitingCompletion@CClfsRequest@@0PEAVCClfsRequest_State_ReadAwaitingCompletion@@EA; P
0x140040e58  test    rcx, rcx
0x140040e5b  jz      short loc_140040E72
0x140040e5d  xor     edx, edx; Tag
0x140040e5f  call    cs:__imp_ExFreePoolWithTag
0x140040e66  nop     dword ptr [rax+rax+00h]
0x140040e6b  mov     cs:?m_pCClfsRequest_State_ReadAwaitingCompletion@CClfsRequest@@0PEAVCClfsRequest_State_ReadAwaitingCompletion@@EA, rbx; CClfsRequest_State_ReadAwaitingCompletion * CClfsRequest::m_pCClfsRequest_State_ReadAwaitingCompletion
0x140040e72  mov     rcx, cs:?m_pCClfsRequest_State_ReadPending@CClfsRequest@@0PEAVCClfsRequest_State_ReadPending@@EA; P
0x140040e79  test    rcx, rcx
0x140040e7c  jz      short loc_140040E93
0x140040e7e  xor     edx, edx; Tag
0x140040e80  call    cs:__imp_ExFreePoolWithTag
0x140040e87  nop     dword ptr [rax+rax+00h]
0x140040e8c  mov     cs:?m_pCClfsRequest_State_ReadPending@CClfsRequest@@0PEAVCClfsRequest_State_ReadPending@@EA, rbx; CClfsRequest_State_ReadPending * CClfsRequest::m_pCClfsRequest_State_ReadPending
0x140040e93  mov     rcx, cs:?m_pCClfsRequest_State_ReadPendingFailed@CClfsRequest@@0PEAVCClfsRequest_State_ReadPendingFailed@@EA; P
0x140040e9a  test    rcx, rcx
0x140040e9d  jz      short loc_140040EB4
0x140040e9f  xor     edx, edx; Tag
0x140040ea1  call    cs:__imp_ExFreePoolWithTag
0x140040ea8  nop     dword ptr [rax+rax+00h]
0x140040ead  mov     cs:?m_pCClfsRequest_State_ReadPendingFailed@CClfsRequest@@0PEAVCClfsRequest_State_ReadPendingFailed@@EA, rbx; CClfsRequest_State_ReadPendingFailed * CClfsRequest::m_pCClfsRequest_State_ReadPendingFailed
0x140040eb4  mov     rcx, cs:?m_pCClfsRequest_State_WriteRestartPending@CClfsRequest@@0PEAVCClfsRequest_State_WriteRestartPending@@EA; P
0x140040ebb  test    rcx, rcx
0x140040ebe  jz      short loc_140040ED5
0x140040ec0  xor     edx, edx; Tag
0x140040ec2  call    cs:__imp_ExFreePoolWithTag
0x140040ec9  nop     dword ptr [rax+rax+00h]
0x140040ece  mov     cs:?m_pCClfsRequest_State_WriteRestartPending@CClfsRequest@@0PEAVCClfsRequest_State_WriteRestartPending@@EA, rbx; CClfsRequest_State_WriteRestartPending * CClfsRequest::m_pCClfsRequest_State_WriteRestartPending
0x140040ed5  mov     rcx, cs:?m_pCClfsRequest_State_WriteRestartInProgress@CClfsRequest@@0PEAVCClfsRequest_State_WriteRestartInProgress@@EA; P
0x140040edc  test    rcx, rcx
0x140040edf  jz      short loc_140040EF6
0x140040ee1  xor     edx, edx; Tag
0x140040ee3  call    cs:__imp_ExFreePoolWithTag
0x140040eea  nop     dword ptr [rax+rax+00h]
0x140040eef  mov     cs:?m_pCClfsRequest_State_WriteRestartInProgress@CClfsRequest@@0PEAVCClfsRequest_State_WriteRestartInProgress@@EA, rbx; CClfsRequest_State_WriteRestartInProgress * CClfsRequest::m_pCClfsRequest_State_WriteRestartInProgress
0x140040ef6  mov     rcx, cs:?m_pCClfsRequest_State_AdvanceLogBasePending@CClfsRequest@@0PEAVCClfsRequest_State_AdvanceLogBasePending@@EA; P
0x140040efd  test    rcx, rcx
0x140040f00  jz      short loc_140040F17
0x140040f02  xor     edx, edx; Tag
0x140040f04  call    cs:__imp_ExFreePoolWithTag
0x140040f0b  nop     dword ptr [rax+rax+00h]
0x140040f10  mov     cs:?m_pCClfsRequest_State_AdvanceLogBasePending@CClfsRequest@@0PEAVCClfsRequest_State_AdvanceLogBasePending@@EA, rbx; CClfsRequest_State_AdvanceLogBasePending * CClfsRequest::m_pCClfsRequest_State_AdvanceLogBasePending
0x140040f17  mov     rcx, cs:?m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart@CClfsRequest@@0PEAVCClfsRequest_State_AdvanceLogBaseAwaitingRestart@@EA; P
0x140040f1e  test    rcx, rcx
0x140040f21  jz      short loc_140040F38
0x140040f23  xor     edx, edx; Tag
0x140040f25  call    cs:__imp_ExFreePoolWithTag
0x140040f2c  nop     dword ptr [rax+rax+00h]
0x140040f31  mov     cs:?m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart@CClfsRequest@@0PEAVCClfsRequest_State_AdvanceLogBaseAwaitingRestart@@EA, rbx; CClfsRequest_State_AdvanceLogBaseAwaitingRestart * CClfsRequest::m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart
0x140040f38  mov     rcx, cs:?m_pCClfsRequest_State_ReadMgmtNotificationPending@CClfsRequest@@0PEAVCClfsRequest_State_ReadMgmtNotificationPending@@EA; P
0x140040f3f  test    rcx, rcx
0x140040f42  jz      short loc_140040F59
0x140040f44  xor     edx, edx; Tag
0x140040f46  call    cs:__imp_ExFreePoolWithTag
0x140040f4d  nop     dword ptr [rax+rax+00h]
0x140040f52  mov     cs:?m_pCClfsRequest_State_ReadMgmtNotificationPending@CClfsRequest@@0PEAVCClfsRequest_State_ReadMgmtNotificationPending@@EA, rbx; CClfsRequest_State_ReadMgmtNotificationPending * CClfsRequest::m_pCClfsRequest_State_ReadMgmtNotificationPending
0x140040f59  add     rsp, 20h
0x140040f5d  pop     rbx
0x140040f5e  retn
```
