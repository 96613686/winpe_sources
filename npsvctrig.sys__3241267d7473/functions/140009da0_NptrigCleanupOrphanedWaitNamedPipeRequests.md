# NptrigCleanupOrphanedWaitNamedPipeRequests

- ea: `0x140009da0`
- end: `0x140009eb2`
- name: `NptrigCleanupOrphanedWaitNamedPipeRequests`
- size: `274`
- prototype: `PFLT_CALLBACK_DATA __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009b00`

## callees

- `0x140001500`
- `0x140001928`
- `0x140008330`
- `0x140009da0`

## import_xrefs

- `FLTMGR!FltFreeGenericWorkItem` at `0x140009e6b`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140009e6b`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x140009db2`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x140009e87`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x140009db2`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x140009e87`
- `FLTMGR!FltCompletePendedPostOperation` at `0x140009e58`
- `FLTMGR!FltCompletePendedPostOperation` at `0x140009e58`

## pseudocode

```c
PFLT_CALLBACK_DATA __fastcall NptrigCleanupOrphanedWaitNamedPipeRequests(__int64 a1)
{
  struct _FLT_CALLBACK_DATA_QUEUE *v1; // rbx
  PFLT_CALLBACK_DATA result; // rax
  __int64 v3; // r8
  _QWORD *v4; // rdi
  NTSTATUS v5; // edx
  __int64 v6; // r8

  v1 = (struct _FLT_CALLBACK_DATA_QUEUE *)(a1 + 24);
  for ( result = FltCbdqRemoveNextIo((PFLT_CALLBACK_DATA_QUEUE)(a1 + 24), (PVOID)1);
        result;
        result = FltCbdqRemoveNextIo(v1, (PVOID)1) )
  {
    v4 = result->QueueContext[0];
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 23, v3, v4, *v4);
    v5 = -1073741643;
    if ( *((_DWORD *)v4 + 46) )
      v5 = -1073741772;
    NptrigAlterIoStatus((PFLT_CALLBACK_DATA)*v4, v5, v3);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 24, v6, v4, *v4);
    FltCompletePendedPostOperation((PFLT_CALLBACK_DATA)*v4);
    FltFreeGenericWorkItem((PFLT_GENERIC_WORKITEM)v4[24]);
    NptrigReleaseRequestRef(v4);
  }
  return result;
}

```

## disassembly

```asm
0x140009da0  push    rbx
0x140009da2  sub     rsp, 30h
0x140009da6  lea     rbx, [rcx+18h]
0x140009daa  mov     edx, 1; PeekContext
0x140009daf  mov     rcx, rbx; Cbdq
0x140009db2  call    cs:__imp_FltCbdqRemoveNextIo
0x140009db9  nop     dword ptr [rax+rax+00h]
0x140009dbe  test    rax, rax
0x140009dc1  jz      loc_140009EAB
0x140009dc7  mov     [rsp+38h+arg_0], rbp
0x140009dcc  mov     ebp, 0C0000034h
0x140009dd1  mov     [rsp+38h+arg_8], rsi
0x140009dd6  lea     rsi, WPP_GLOBAL_Control
0x140009ddd  mov     [rsp+38h+arg_10], rdi
0x140009de2  mov     rdi, [rax+40h]
0x140009de6  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ded  cmp     rcx, rsi
0x140009df0  jz      short loc_140009E12
0x140009df2  mov     eax, [rcx+2Ch]
0x140009df5  test    al, 4
0x140009df7  jz      short loc_140009E12
0x140009df9  mov     rax, [rdi]
0x140009dfc  mov     edx, 17h
0x140009e01  mov     rcx, [rcx+18h]
0x140009e05  mov     r9, rdi
0x140009e08  mov     [rsp+38h+var_18], rax
0x140009e0d  call    WPP_SF_qq
0x140009e12  cmp     dword ptr [rdi+0B8h], 0
0x140009e19  mov     edx, 0C00000B5h
0x140009e1e  mov     rcx, [rdi]; Data
0x140009e21  cmovnz  edx, ebp
0x140009e24  call    NptrigAlterIoStatus
0x140009e29  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e30  cmp     rcx, rsi
0x140009e33  jz      short loc_140009E55
0x140009e35  mov     eax, [rcx+2Ch]
0x140009e38  test    al, 4
0x140009e3a  jz      short loc_140009E55
0x140009e3c  mov     rax, [rdi]
0x140009e3f  mov     edx, 18h
0x140009e44  mov     rcx, [rcx+18h]
0x140009e48  mov     r9, rdi
0x140009e4b  mov     [rsp+38h+var_18], rax
0x140009e50  call    WPP_SF_qq
0x140009e55  mov     rcx, [rdi]; CallbackData
0x140009e58  call    cs:__imp_FltCompletePendedPostOperation
0x140009e5f  nop     dword ptr [rax+rax+00h]
0x140009e64  mov     rcx, [rdi+0C0h]; FltWorkItem
0x140009e6b  call    cs:__imp_FltFreeGenericWorkItem
0x140009e72  nop     dword ptr [rax+rax+00h]
0x140009e77  mov     rcx, rdi; P
0x140009e7a  call    NptrigReleaseRequestRef
0x140009e7f  mov     edx, 1; PeekContext
0x140009e84  mov     rcx, rbx; Cbdq
0x140009e87  call    cs:__imp_FltCbdqRemoveNextIo
0x140009e8e  nop     dword ptr [rax+rax+00h]
0x140009e93  test    rax, rax
0x140009e96  jnz     loc_140009DE2
0x140009e9c  mov     rdi, [rsp+38h+arg_10]
0x140009ea1  mov     rsi, [rsp+38h+arg_8]
0x140009ea6  mov     rbp, [rsp+38h+arg_0]
0x140009eab  add     rsp, 30h
0x140009eaf  pop     rbx
0x140009eb0  retn
```
