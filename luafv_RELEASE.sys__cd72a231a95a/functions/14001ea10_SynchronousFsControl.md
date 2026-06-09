# SynchronousFsControl

- ea: `0x14001ea10`
- end: `0x14001ed2c`
- name: `SynchronousFsControl`
- size: `796`
- prototype: `NTSTATUS __fastcall(__int64, _OWORD *, DWORD, void *, ULONG, void *, ULONG)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400140b4`
- `0x140017aac`
- `0x140017c04`
- `0x14001e720`

## callees

- `0x140005bb0`
- `0x140017a08`
- `0x14001ea10`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001ecef`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ecef`
- `ntoskrnl!KeClearEvent` at `0x14001ea9d`
- `ntoskrnl!KeClearEvent` at `0x14001ec1a`
- `ntoskrnl!KeClearEvent` at `0x14001ea9d`
- `ntoskrnl!KeClearEvent` at `0x14001ec1a`
- `ntoskrnl!KeReadStateEvent` at `0x14001ea54`
- `ntoskrnl!KeReadStateEvent` at `0x14001ea7a`
- `ntoskrnl!KeReadStateEvent` at `0x14001ea54`
- `ntoskrnl!KeReadStateEvent` at `0x14001ea7a`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001ebac`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001ebac`
- `FLTMGR!FltCancelIo` at `0x14001eccf`
- `FLTMGR!FltCancelIo` at `0x14001eccf`
- `FLTMGR!FltPerformAsynchronousIo` at `0x14001eb5d`
- `FLTMGR!FltPerformAsynchronousIo` at `0x14001eb5d`
- `FLTMGR!FltFreeCallbackData` at `0x14001ebda`
- `FLTMGR!FltFreeCallbackData` at `0x14001ec51`
- `FLTMGR!FltFreeCallbackData` at `0x14001ed18`
- `FLTMGR!FltFreeCallbackData` at `0x14001ebda`
- `FLTMGR!FltFreeCallbackData` at `0x14001ec51`
- `FLTMGR!FltFreeCallbackData` at `0x14001ed18`
- `FLTMGR!FltAllocateCallbackData` at `0x14001eab5`
- `FLTMGR!FltAllocateCallbackData` at `0x14001eab5`

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
    Status = FltPerformAsynchronousIo(
               RetNewCallbackData,
               (PFLT_COMPLETED_ASYNC_IO_CALLBACK)AsyncIoCompletion,
               (PVOID)(a1 + 56));
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
0x14001ea10  push    rbp
0x14001ea12  push    rbx
0x14001ea13  push    rdi
0x14001ea14  push    r13
0x14001ea16  push    r14
0x14001ea18  push    r15
0x14001ea1a  mov     rbp, rsp
0x14001ea1d  sub     rsp, 78h
0x14001ea21  mov     rax, cs:__security_cookie
0x14001ea28  xor     rax, rsp
0x14001ea2b  mov     [rbp+var_10], rax
0x14001ea2f  xor     eax, eax
0x14001ea31  mov     [rbp+var_30], r9
0x14001ea35  lea     r13, [rcx+70h]
0x14001ea39  mov     [rbp+var_18], rax
0x14001ea3d  mov     r14, rcx
0x14001ea40  mov     [rbp+RetNewCallbackData], rax
0x14001ea44  xorps   xmm0, xmm0
0x14001ea47  mov     rcx, r13; Event
0x14001ea4a  mov     r15d, r8d
0x14001ea4d  mov     rdi, rdx
0x14001ea50  movups  xmmword ptr [rbp+Object], xmm0
0x14001ea54  call    cs:__imp_KeReadStateEvent
0x14001ea5b  nop     dword ptr [rax+rax+00h]
0x14001ea60  test    eax, eax
0x14001ea62  jnz     loc_14001EC10
0x14001ea68  mov     [rsp+78h+arg_10], rsi
0x14001ea70  lea     rsi, [r14+88h]
0x14001ea77  mov     rcx, rsi; Event
0x14001ea7a  call    cs:__imp_KeReadStateEvent
0x14001ea81  nop     dword ptr [rax+rax+00h]
0x14001ea86  test    eax, eax
0x14001ea88  jnz     loc_14001EC17
0x14001ea8e  mov     [rsp+78h+var_8], r12
0x14001ea93  lea     r12, [r14+0D0h]
0x14001ea9a  mov     rcx, r12; Event
0x14001ea9d  call    cs:__imp_KeClearEvent
0x14001eaa4  nop     dword ptr [rax+rax+00h]
0x14001eaa9  mov     rdx, [r14+40h]; FileObject
0x14001eaad  lea     r8, [rbp+RetNewCallbackData]; RetNewCallbackData
0x14001eab1  mov     rcx, [r14+10h]; Instance
0x14001eab5  call    cs:__imp_FltAllocateCallbackData
0x14001eabc  nop     dword ptr [rax+rax+00h]
0x14001eac1  test    eax, eax
0x14001eac3  js      loc_14001EBE8
0x14001eac9  mov     rax, [rbp+RetNewCallbackData]
0x14001eacd  mov     rcx, [rax+10h]
0x14001ead1  mov     byte ptr [rcx+4], 0Dh
0x14001ead5  mov     rax, [rbp+RetNewCallbackData]
0x14001ead9  mov     rcx, [rax+10h]
0x14001eadd  mov     byte ptr [rcx+5], 0
0x14001eae1  cmp     r15d, 900E7h
0x14001eae8  jnz     loc_14001EC35
0x14001eaee  mov     rax, [rbp+RetNewCallbackData]
0x14001eaf2  xor     edx, edx
0x14001eaf4  mov     rcx, [rax+10h]
0x14001eaf8  mov     [rcx], edx
0x14001eafa  mov     rax, [rbp+RetNewCallbackData]
0x14001eafe  mov     rcx, [rax+10h]
0x14001eb02  mov     [rcx+28h], r15d
0x14001eb06  mov     rax, [rbp+RetNewCallbackData]
0x14001eb0a  mov     rcx, [rax+10h]
0x14001eb0e  mov     eax, [rbp+arg_20]
0x14001eb11  mov     [rcx+20h], eax
0x14001eb14  mov     rax, [rbp+RetNewCallbackData]
0x14001eb18  mov     rcx, [rax+10h]
0x14001eb1c  mov     eax, [rbp+arg_30]
0x14001eb1f  mov     [rcx+18h], eax
0x14001eb22  mov     rax, [rbp+RetNewCallbackData]
0x14001eb26  mov     rcx, [rax+10h]
0x14001eb2a  mov     rax, [rbp+var_30]
0x14001eb2e  mov     [rcx+30h], rax
0x14001eb32  mov     rax, [rbp+RetNewCallbackData]
0x14001eb36  mov     rcx, [rax+10h]
0x14001eb3a  mov     rax, [rbp+arg_28]
0x14001eb3e  mov     [rcx+38h], rax
0x14001eb42  mov     rax, [rbp+RetNewCallbackData]
0x14001eb46  mov     rcx, [rax+10h]
0x14001eb4a  mov     [rcx+40h], rdx
0x14001eb4e  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14001eb52  lea     r8, [r14+38h]; CallbackContext
0x14001eb56  lea     rdx, AsyncIoCompletion; CallbackRoutine
0x14001eb5d  call    cs:__imp_FltPerformAsynchronousIo
0x14001eb64  nop     dword ptr [rax+rax+00h]
0x14001eb69  mov     ebx, eax
0x14001eb6b  cmp     eax, 103h
0x14001eb70  jnz     short loc_14001EBC3
0x14001eb72  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x14001eb7b  lea     rdx, [rbp+Object]; Object
0x14001eb7f  mov     [rsp+78h+Timeout], 0; Timeout
0x14001eb88  xor     r9d, r9d; WaitReason
0x14001eb8b  mov     [rsp+78h+Alertable], 0; Alertable
0x14001eb90  mov     r8d, 1; WaitType
0x14001eb96  mov     ecx, 3; Count
0x14001eb9b  mov     [rsp+78h+WaitMode], 0; WaitMode
0x14001eba0  mov     [rbp+Object], r13
0x14001eba4  mov     [rbp+Object+8], rsi
0x14001eba8  mov     [rbp+var_18], r12
0x14001ebac  call    cs:__imp_KeWaitForMultipleObjects
0x14001ebb3  nop     dword ptr [rax+rax+00h]
0x14001ebb8  mov     ebx, eax
0x14001ebba  cmp     eax, 2
0x14001ebbd  jnz     loc_14001ECCB
0x14001ebc3  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14001ebc7  test    ebx, ebx
0x14001ebc9  js      short loc_14001EBCE
0x14001ebcb  mov     ebx, [rcx+18h]
0x14001ebce  test    rdi, rdi
0x14001ebd1  jz      short loc_14001EBDA
0x14001ebd3  movups  xmm0, xmmword ptr [rcx+18h]
0x14001ebd7  movups  xmmword ptr [rdi], xmm0
0x14001ebda  call    cs:__imp_FltFreeCallbackData
0x14001ebe1  nop     dword ptr [rax+rax+00h]
0x14001ebe6  mov     eax, ebx
0x14001ebe8  mov     r12, [rsp+78h+var_8]
0x14001ebed  mov     rsi, [rsp+78h+arg_10]
0x14001ebf5  mov     rcx, [rbp+var_10]
0x14001ebf9  xor     rcx, rsp; StackCookie
0x14001ebfc  call    __security_check_cookie
0x14001ec01  add     rsp, 78h
0x14001ec05  pop     r15
0x14001ec07  pop     r14
0x14001ec09  pop     r13
0x14001ec0b  pop     rdi
0x14001ec0c  pop     rbx
0x14001ec0d  pop     rbp
0x14001ec0e  retn
0x14001ec10  mov     eax, 1
0x14001ec15  jmp     short loc_14001EBF5
0x14001ec17  mov     rcx, rsi; Event
0x14001ec1a  call    cs:__imp_KeClearEvent
0x14001ec21  nop     dword ptr [rax+rax+00h]
0x14001ec26  mov     rcx, r14
0x14001ec29  call    AcknowledgePauseRequest
0x14001ec2e  mov     eax, 2
0x14001ec33  jmp     short loc_14001EBED
0x14001ec35  mov     eax, r15d
0x14001ec38  sub     eax, 900BBh
0x14001ec3d  jz      loc_14001EAEE
0x14001ec43  sub     eax, 39h ; '9'
0x14001ec46  jz      short loc_14001EC64
0x14001ec48  cmp     eax, 4
0x14001ec4b  jz      short loc_14001EC64
0x14001ec4d  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14001ec51  call    cs:__imp_FltFreeCallbackData
0x14001ec58  nop     dword ptr [rax+rax+00h]
0x14001ec5d  mov     eax, 0C000000Dh
0x14001ec62  jmp     short loc_14001EBE8
0x14001ec64  mov     rax, [rbp+RetNewCallbackData]
0x14001ec68  mov     rcx, [rax+10h]
0x14001ec6c  mov     dword ptr [rcx], 10h
0x14001ec72  mov     rax, [rbp+RetNewCallbackData]
0x14001ec76  mov     rcx, [rax+10h]
0x14001ec7a  mov     [rcx+28h], r15d
0x14001ec7e  mov     rax, [rbp+RetNewCallbackData]
0x14001ec82  mov     rcx, [rax+10h]
0x14001ec86  mov     eax, [rbp+arg_20]
0x14001ec89  mov     [rcx+20h], eax
0x14001ec8c  mov     rax, [rbp+RetNewCallbackData]
0x14001ec90  mov     rcx, [rax+10h]
0x14001ec94  mov     eax, [rbp+arg_30]
0x14001ec97  test    eax, eax
0x14001ec99  mov     [rcx+18h], eax
0x14001ec9c  mov     rax, [rbp+RetNewCallbackData]
0x14001eca0  mov     rcx, [rax+10h]
0x14001eca4  jz      short loc_14001ECBE
0x14001eca6  mov     rax, [rbp+arg_28]
0x14001ecaa  mov     [rcx+30h], rax
0x14001ecae  mov     rax, [rbp+RetNewCallbackData]
0x14001ecb2  mov     rcx, [rax+10h]
0x14001ecb6  or      dword ptr [rcx], 40h
0x14001ecb9  jmp     loc_14001EB4E
0x14001ecbe  mov     rax, [rbp+var_30]
0x14001ecc2  mov     [rcx+30h], rax
0x14001ecc6  jmp     loc_14001EB4E
0x14001eccb  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14001eccf  call    cs:__imp_FltCancelIo
0x14001ecd6  nop     dword ptr [rax+rax+00h]
0x14001ecdb  xor     r9d, r9d; Alertable
0x14001ecde  mov     qword ptr [rsp+78h+WaitMode], 0; Timeout
0x14001ece7  xor     r8d, r8d; WaitMode
0x14001ecea  xor     edx, edx; WaitReason
0x14001ecec  mov     rcx, r12; Object
0x14001ecef  call    cs:__imp_KeWaitForSingleObject
0x14001ecf6  nop     dword ptr [rax+rax+00h]
0x14001ecfb  cmp     ebx, 1
0x14001ecfe  jnz     short loc_14001ED08
0x14001ed00  mov     rcx, r14
0x14001ed03  call    AcknowledgePauseRequest
0x14001ed08  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14001ed0c  test    rdi, rdi
0x14001ed0f  jz      short loc_14001ED18
0x14001ed11  movups  xmm0, xmmword ptr [rcx+18h]
0x14001ed15  movups  xmmword ptr [rdi], xmm0
0x14001ed18  call    cs:__imp_FltFreeCallbackData
0x14001ed1f  nop     dword ptr [rax+rax+00h]
0x14001ed24  lea     eax, [rbx+1]
0x14001ed27  jmp     loc_14001EBE8
```
