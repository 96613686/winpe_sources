# SynchronousFsControl

- ea: `0x14001ea60`
- end: `0x14001ed7c`
- name: `SynchronousFsControl`
- size: `796`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400140b4`
- `0x140017afc`
- `0x140017c54`
- `0x14001e770`

## callees

- `0x140005f30`
- `0x140017a58`
- `0x14001ea60`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001ed3f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ed3f`
- `ntoskrnl!KeClearEvent` at `0x14001eaed`
- `ntoskrnl!KeClearEvent` at `0x14001ec6a`
- `ntoskrnl!KeClearEvent` at `0x14001eaed`
- `ntoskrnl!KeClearEvent` at `0x14001ec6a`
- `ntoskrnl!KeReadStateEvent` at `0x14001eaa4`
- `ntoskrnl!KeReadStateEvent` at `0x14001eaca`
- `ntoskrnl!KeReadStateEvent` at `0x14001eaa4`
- `ntoskrnl!KeReadStateEvent` at `0x14001eaca`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001ebfc`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001ebfc`
- `FLTMGR!FltCancelIo` at `0x14001ed1f`
- `FLTMGR!FltCancelIo` at `0x14001ed1f`
- `FLTMGR!FltPerformAsynchronousIo` at `0x14001ebad`
- `FLTMGR!FltPerformAsynchronousIo` at `0x14001ebad`
- `FLTMGR!FltFreeCallbackData` at `0x14001ec2a`
- `FLTMGR!FltFreeCallbackData` at `0x14001eca1`
- `FLTMGR!FltFreeCallbackData` at `0x14001ed68`
- `FLTMGR!FltFreeCallbackData` at `0x14001ec2a`
- `FLTMGR!FltFreeCallbackData` at `0x14001eca1`
- `FLTMGR!FltFreeCallbackData` at `0x14001ed68`
- `FLTMGR!FltAllocateCallbackData` at `0x14001eb05`
- `FLTMGR!FltAllocateCallbackData` at `0x14001eb05`

## pseudocode

```c
NTSTATUS __fastcall SynchronousFsControl(__int64 a1, _OWORD *a2, DWORD a3, void *a4, ULONG a5, void *a6, ULONG a7)
{
  void *v7; // r13
  NTSTATUS result; // eax
  NTSTATUS Status; // ebx
  struct _FLT_CALLBACK_DATA *v13; // rcx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  struct _FLT_CALLBACK_DATA *v15; // rcx
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+40h] [rbp-38h] BYREF
  void *v17; // [rsp+48h] [rbp-30h]
  PVOID Object[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v19; // [rsp+60h] [rbp-18h]

  v17 = a4;
  v7 = (void *)(a1 + 112);
  v19 = 0;
  RetNewCallbackData = 0;
  *(_OWORD *)Object = 0;
  if ( KeReadStateEvent((PRKEVENT)(a1 + 112)) )
    return 1;
  if ( KeReadStateEvent((PRKEVENT)(a1 + 136)) )
  {
    KeClearEvent((PRKEVENT)(a1 + 136));
    AcknowledgePauseRequest(a1);
    return 2;
  }
  KeClearEvent((PRKEVENT)(a1 + 208));
  result = FltAllocateCallbackData(*(PFLT_INSTANCE *)(a1 + 16), *(PFILE_OBJECT *)(a1 + 64), &RetNewCallbackData);
  if ( result >= 0 )
  {
    RetNewCallbackData->Iopb->MajorFunction = 13;
    RetNewCallbackData->Iopb->MinorFunction = 0;
    if ( a3 == 590055 || a3 == 590011 )
    {
      RetNewCallbackData->Iopb->IrpFlags = 0;
      RetNewCallbackData->Iopb->Parameters.Read.ByteOffset.LowPart = a3;
      RetNewCallbackData->Iopb->Parameters.Create.Options = a5;
      RetNewCallbackData->Iopb->Parameters.Read.Length = a7;
      RetNewCallbackData->Iopb->Parameters.CreatePipe.Parameters = v17;
      RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = a6;
      RetNewCallbackData->Iopb->Parameters.Create.AllocationSize.QuadPart = 0;
    }
    else
    {
      if ( a3 != 590068 && a3 != 590072 )
      {
        FltFreeCallbackData(RetNewCallbackData);
        return -1073741811;
      }
      RetNewCallbackData->Iopb->IrpFlags = 16;
      RetNewCallbackData->Iopb->Parameters.Read.ByteOffset.LowPart = a3;
      RetNewCallbackData->Iopb->Parameters.Create.Options = a5;
      RetNewCallbackData->Iopb->Parameters.Read.Length = a7;
      Iopb = RetNewCallbackData->Iopb;
      if ( a7 )
      {
        Iopb->Parameters.CreatePipe.Parameters = a6;
        RetNewCallbackData->Iopb->IrpFlags |= 0x40u;
      }
      else
      {
        Iopb->Parameters.CreatePipe.Parameters = v17;
      }
    }
    Status = FltPerformAsynchronousIo(RetNewCallbackData, AsyncIoCompletion, (PVOID)(a1 + 56));
    if ( Status == 259
      && (Object[0] = v7,
          Object[1] = (PVOID)(a1 + 136),
          v19 = a1 + 208,
          Status = KeWaitForMultipleObjects(3u, Object, WaitAny, Executive, 0, 0, 0, 0),
          Status != 2) )
    {
      FltCancelIo(RetNewCallbackData);
      KeWaitForSingleObject((PVOID)(a1 + 208), Executive, 0, 0, 0);
      if ( Status == 1 )
        AcknowledgePauseRequest(a1);
      v15 = RetNewCallbackData;
      if ( a2 )
        *a2 = *(_OWORD *)&RetNewCallbackData->IoStatus.Status;
      FltFreeCallbackData(v15);
      return Status + 1;
    }
    else
    {
      v13 = RetNewCallbackData;
      if ( Status >= 0 )
        Status = RetNewCallbackData->IoStatus.Status;
      if ( a2 )
        *a2 = *(_OWORD *)&RetNewCallbackData->IoStatus.Status;
      FltFreeCallbackData(v13);
      return Status;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001ea60  push    rbp
0x14001ea62  push    rbx
0x14001ea63  push    rdi
0x14001ea64  push    r13
0x14001ea66  push    r14
0x14001ea68  push    r15
0x14001ea6a  mov     rbp, rsp
0x14001ea6d  sub     rsp, 78h
0x14001ea71  mov     rax, cs:__security_cookie
0x14001ea78  xor     rax, rsp
0x14001ea7b  mov     [rbp+var_10], rax
0x14001ea7f  xor     eax, eax
0x14001ea81  mov     [rbp+var_30], r9
0x14001ea85  lea     r13, [rcx+70h]
0x14001ea89  mov     [rbp+var_18], rax
0x14001ea8d  mov     r14, rcx
0x14001ea90  mov     [rbp+RetNewCallbackData], rax
0x14001ea94  xorps   xmm0, xmm0
0x14001ea97  mov     rcx, r13; Event
0x14001ea9a  mov     r15d, r8d
0x14001ea9d  mov     rdi, rdx
0x14001eaa0  movups  xmmword ptr [rbp+Object], xmm0
0x14001eaa4  call    cs:__imp_KeReadStateEvent
0x14001eaab  nop     dword ptr [rax+rax+00h]
0x14001eab0  test    eax, eax
0x14001eab2  jnz     loc_14001EC60
0x14001eab8  mov     [rsp+78h+arg_10], rsi
0x14001eac0  lea     rsi, [r14+88h]
0x14001eac7  mov     rcx, rsi; Event
0x14001eaca  call    cs:__imp_KeReadStateEvent
0x14001ead1  nop     dword ptr [rax+rax+00h]
0x14001ead6  test    eax, eax
0x14001ead8  jnz     loc_14001EC67
0x14001eade  mov     [rsp+78h+var_8], r12
0x14001eae3  lea     r12, [r14+0D0h]
0x14001eaea  mov     rcx, r12; Event
0x14001eaed  call    cs:__imp_KeClearEvent
0x14001eaf4  nop     dword ptr [rax+rax+00h]
0x14001eaf9  mov     rdx, [r14+40h]; FileObject
0x14001eafd  lea     r8, [rbp+RetNewCallbackData]; RetNewCallbackData
0x14001eb01  mov     rcx, [r14+10h]; Instance
0x14001eb05  call    cs:__imp_FltAllocateCallbackData
0x14001eb0c  nop     dword ptr [rax+rax+00h]
0x14001eb11  test    eax, eax
0x14001eb13  js      loc_14001EC38
0x14001eb19  mov     rax, [rbp+RetNewCallbackData]
0x14001eb1d  mov     rcx, [rax+10h]
0x14001eb21  mov     byte ptr [rcx+4], 0Dh
0x14001eb25  mov     rax, [rbp+RetNewCallbackData]
0x14001eb29  mov     rcx, [rax+10h]
0x14001eb2d  mov     byte ptr [rcx+5], 0
0x14001eb31  cmp     r15d, 900E7h
0x14001eb38  jnz     loc_14001EC85
0x14001eb3e  mov     rax, [rbp+RetNewCallbackData]
0x14001eb42  xor     edx, edx
0x14001eb44  mov     rcx, [rax+10h]
0x14001eb48  mov     [rcx], edx
0x14001eb4a  mov     rax, [rbp+RetNewCallbackData]
0x14001eb4e  mov     rcx, [rax+10h]
0x14001eb52  mov     [rcx+28h], r15d
0x14001eb56  mov     rax, [rbp+RetNewCallbackData]
0x14001eb5a  mov     rcx, [rax+10h]
0x14001eb5e  mov     eax, [rbp+arg_20]
0x14001eb61  mov     [rcx+20h], eax
0x14001eb64  mov     rax, [rbp+RetNewCallbackData]
0x14001eb68  mov     rcx, [rax+10h]
0x14001eb6c  mov     eax, [rbp+arg_30]
0x14001eb6f  mov     [rcx+18h], eax
0x14001eb72  mov     rax, [rbp+RetNewCallbackData]
0x14001eb76  mov     rcx, [rax+10h]
0x14001eb7a  mov     rax, [rbp+var_30]
0x14001eb7e  mov     [rcx+30h], rax
0x14001eb82  mov     rax, [rbp+RetNewCallbackData]
0x14001eb86  mov     rcx, [rax+10h]
0x14001eb8a  mov     rax, [rbp+arg_28]
0x14001eb8e  mov     [rcx+38h], rax
0x14001eb92  mov     rax, [rbp+RetNewCallbackData]
0x14001eb96  mov     rcx, [rax+10h]
0x14001eb9a  mov     [rcx+40h], rdx
0x14001eb9e  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14001eba2  lea     r8, [r14+38h]; CallbackContext
0x14001eba6  lea     rdx, AsyncIoCompletion; CallbackRoutine
0x14001ebad  call    cs:__imp_FltPerformAsynchronousIo
0x14001ebb4  nop     dword ptr [rax+rax+00h]
0x14001ebb9  mov     ebx, eax
0x14001ebbb  cmp     eax, 103h
0x14001ebc0  jnz     short loc_14001EC13
0x14001ebc2  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x14001ebcb  lea     rdx, [rbp+Object]; Object
0x14001ebcf  mov     [rsp+78h+Timeout], 0; Timeout
0x14001ebd8  xor     r9d, r9d; WaitReason
0x14001ebdb  mov     [rsp+78h+Alertable], 0; Alertable
0x14001ebe0  mov     r8d, 1; WaitType
0x14001ebe6  mov     ecx, 3; Count
0x14001ebeb  mov     [rsp+78h+WaitMode], 0; WaitMode
0x14001ebf0  mov     [rbp+Object], r13
0x14001ebf4  mov     [rbp+Object+8], rsi
0x14001ebf8  mov     [rbp+var_18], r12
0x14001ebfc  call    cs:__imp_KeWaitForMultipleObjects
0x14001ec03  nop     dword ptr [rax+rax+00h]
0x14001ec08  mov     ebx, eax
0x14001ec0a  cmp     eax, 2
0x14001ec0d  jnz     loc_14001ED1B
0x14001ec13  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14001ec17  test    ebx, ebx
0x14001ec19  js      short loc_14001EC1E
0x14001ec1b  mov     ebx, [rcx+18h]
0x14001ec1e  test    rdi, rdi
0x14001ec21  jz      short loc_14001EC2A
0x14001ec23  movups  xmm0, xmmword ptr [rcx+18h]
0x14001ec27  movups  xmmword ptr [rdi], xmm0
0x14001ec2a  call    cs:__imp_FltFreeCallbackData
0x14001ec31  nop     dword ptr [rax+rax+00h]
0x14001ec36  mov     eax, ebx
0x14001ec38  mov     r12, [rsp+78h+var_8]
0x14001ec3d  mov     rsi, [rsp+78h+arg_10]
0x14001ec45  mov     rcx, [rbp+var_10]
0x14001ec49  xor     rcx, rsp; StackCookie
0x14001ec4c  call    __security_check_cookie
0x14001ec51  add     rsp, 78h
0x14001ec55  pop     r15
0x14001ec57  pop     r14
0x14001ec59  pop     r13
0x14001ec5b  pop     rdi
0x14001ec5c  pop     rbx
0x14001ec5d  pop     rbp
0x14001ec5e  retn
0x14001ec60  mov     eax, 1
0x14001ec65  jmp     short loc_14001EC45
0x14001ec67  mov     rcx, rsi; Event
0x14001ec6a  call    cs:__imp_KeClearEvent
0x14001ec71  nop     dword ptr [rax+rax+00h]
0x14001ec76  mov     rcx, r14
0x14001ec79  call    AcknowledgePauseRequest
0x14001ec7e  mov     eax, 2
0x14001ec83  jmp     short loc_14001EC3D
0x14001ec85  mov     eax, r15d
0x14001ec88  sub     eax, 900BBh
0x14001ec8d  jz      loc_14001EB3E
0x14001ec93  sub     eax, 39h ; '9'
0x14001ec96  jz      short loc_14001ECB4
0x14001ec98  cmp     eax, 4
0x14001ec9b  jz      short loc_14001ECB4
0x14001ec9d  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14001eca1  call    cs:__imp_FltFreeCallbackData
0x14001eca8  nop     dword ptr [rax+rax+00h]
0x14001ecad  mov     eax, 0C000000Dh
0x14001ecb2  jmp     short loc_14001EC38
0x14001ecb4  mov     rax, [rbp+RetNewCallbackData]
0x14001ecb8  mov     rcx, [rax+10h]
0x14001ecbc  mov     dword ptr [rcx], 10h
0x14001ecc2  mov     rax, [rbp+RetNewCallbackData]
0x14001ecc6  mov     rcx, [rax+10h]
0x14001ecca  mov     [rcx+28h], r15d
0x14001ecce  mov     rax, [rbp+RetNewCallbackData]
0x14001ecd2  mov     rcx, [rax+10h]
0x14001ecd6  mov     eax, [rbp+arg_20]
0x14001ecd9  mov     [rcx+20h], eax
0x14001ecdc  mov     rax, [rbp+RetNewCallbackData]
0x14001ece0  mov     rcx, [rax+10h]
0x14001ece4  mov     eax, [rbp+arg_30]
0x14001ece7  test    eax, eax
0x14001ece9  mov     [rcx+18h], eax
0x14001ecec  mov     rax, [rbp+RetNewCallbackData]
0x14001ecf0  mov     rcx, [rax+10h]
0x14001ecf4  jz      short loc_14001ED0E
0x14001ecf6  mov     rax, [rbp+arg_28]
0x14001ecfa  mov     [rcx+30h], rax
0x14001ecfe  mov     rax, [rbp+RetNewCallbackData]
0x14001ed02  mov     rcx, [rax+10h]
0x14001ed06  or      dword ptr [rcx], 40h
0x14001ed09  jmp     loc_14001EB9E
0x14001ed0e  mov     rax, [rbp+var_30]
0x14001ed12  mov     [rcx+30h], rax
0x14001ed16  jmp     loc_14001EB9E
0x14001ed1b  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14001ed1f  call    cs:__imp_FltCancelIo
0x14001ed26  nop     dword ptr [rax+rax+00h]
0x14001ed2b  xor     r9d, r9d; Alertable
0x14001ed2e  mov     qword ptr [rsp+78h+WaitMode], 0; Timeout
0x14001ed37  xor     r8d, r8d; WaitMode
0x14001ed3a  xor     edx, edx; WaitReason
0x14001ed3c  mov     rcx, r12; Object
0x14001ed3f  call    cs:__imp_KeWaitForSingleObject
0x14001ed46  nop     dword ptr [rax+rax+00h]
0x14001ed4b  cmp     ebx, 1
0x14001ed4e  jnz     short loc_14001ED58
0x14001ed50  mov     rcx, r14
0x14001ed53  call    AcknowledgePauseRequest
0x14001ed58  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14001ed5c  test    rdi, rdi
0x14001ed5f  jz      short loc_14001ED68
0x14001ed61  movups  xmm0, xmmword ptr [rcx+18h]
0x14001ed65  movups  xmmword ptr [rdi], xmm0
0x14001ed68  call    cs:__imp_FltFreeCallbackData
0x14001ed6f  nop     dword ptr [rax+rax+00h]
0x14001ed74  lea     eax, [rbx+1]
0x14001ed77  jmp     loc_14001EC38
```
