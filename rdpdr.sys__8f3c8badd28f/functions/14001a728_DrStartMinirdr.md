# DrStartMinirdr

- ea: `0x14001a728`
- end: `0x14001a93c`
- name: `DrStartMinirdr`
- size: `532`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002acc0`
- `0x14002aebc`

## callees

- `0x14000324c`
- `0x14000327c`
- `0x14001a728`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001a7ea`
- `ntoskrnl!ZwClose` at `0x14001a7ea`
- `ntoskrnl!PsCreateSystemThread` at `0x14001a7a9`
- `ntoskrnl!PsCreateSystemThread` at `0x14001a7a9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001a7d8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001a7d8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a80c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a894`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a80c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a894`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a81c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a81c`

## pseudocode

```c
__int64 __fastcall DrStartMinirdr(PVOID StartContext)
{
  NTSTATUS v1; // ebx
  __int64 Blink_high; // r9
  PDEVICE_OBJECT v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+98h] [rbp+28h] BYREF
  PVOID Object; // [rsp+A0h] [rbp+30h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+A8h] [rbp+38h] BYREF

  v1 = 0;
  ThreadHandle = 0;
  Object = 0;
  Timeout.QuadPart = 0;
  if ( HIDWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink) != 2 )
  {
    if ( _InterlockedCompareExchange((_DWORD *)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink + 1, 1, 0) )
    {
      Timeout.QuadPart = -600000000;
      v5 = KeWaitForSingleObject(&WPP_MAIN_CB.DeviceExtension, Executive, 0, 0, &Timeout);
      v1 = v5;
      if ( v5 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids, v5);
        return (unsigned int)-1073741823;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids);
      Blink_high = HIDWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
      if ( HIDWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink) != 2 )
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return (unsigned int)-1073741823;
        v4 = 27;
        goto LABEL_10;
      }
    }
    else
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 512;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v1 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, &ObjectAttributes, 0, 0, DrStartMinirdrWorker, StartContext);
      if ( v1 >= 0 )
      {
        v1 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
        ZwClose(ThreadHandle);
        if ( v1 >= 0 )
        {
          KeWaitForSingleObject(Object, UserRequest, 0, 0, 0);
          ObfDereferenceObject(Object);
        }
      }
      Blink_high = HIDWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
      if ( HIDWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink) != 2 )
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return (unsigned int)-1073741823;
        v4 = 25;
LABEL_10:
        WPP_SF_d(v3->AttachedDevice, v4, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids, Blink_high);
        return (unsigned int)-1073741823;
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14001a728  push    rbp
0x14001a72a  push    rbx
0x14001a72b  push    rdi
0x14001a72c  mov     rbp, rsp
0x14001a72f  sub     rsp, 70h
0x14001a733  xor     edi, edi
0x14001a735  cmp     dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink+4, 2
0x14001a73c  mov     ebx, edi
0x14001a73e  mov     [rbp+ThreadHandle], rdi
0x14001a742  mov     [rbp+Object], rdi
0x14001a746  mov     qword ptr [rbp+Timeout], rdi
0x14001a74a  jz      loc_14001A931
0x14001a750  lea     edx, [rdi+1]
0x14001a753  xor     eax, eax
0x14001a755  lock cmpxchg dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink+4, edx
0x14001a75d  jnz     loc_14001A874
0x14001a763  mov     [rsp+70h+StartContext], rcx; StartContext
0x14001a768  lea     rax, DrStartMinirdrWorker
0x14001a76f  xorps   xmm0, xmm0
0x14001a772  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x14001a777  xor     r9d, r9d; ProcessHandle
0x14001a77a  mov     [rsp+70h+ClientId], rdi; ClientId
0x14001a77f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001a783  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001a78b  mov     edx, 1FFFFFh; DesiredAccess
0x14001a790  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x14001a798  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14001a79c  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x14001a7a0  mov     [rbp+ObjectAttributes.ObjectName], rdi
0x14001a7a4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001a7a9  call    cs:__imp_PsCreateSystemThread
0x14001a7b0  nop     dword ptr [rax+rax+00h]
0x14001a7b5  mov     ebx, eax
0x14001a7b7  test    eax, eax
0x14001a7b9  js      short loc_14001A828
0x14001a7bb  mov     rcx, [rbp+ThreadHandle]; Handle
0x14001a7bf  lea     rax, [rbp+Object]
0x14001a7c3  mov     [rsp+70h+StartRoutine], rdi; HandleInformation
0x14001a7c8  xor     r9d, r9d; AccessMode
0x14001a7cb  xor     r8d, r8d; ObjectType
0x14001a7ce  mov     [rsp+70h+ClientId], rax; Object
0x14001a7d3  mov     edx, 1FFFFFh; DesiredAccess
0x14001a7d8  call    cs:__imp_ObReferenceObjectByHandle
0x14001a7df  nop     dword ptr [rax+rax+00h]
0x14001a7e4  mov     rcx, [rbp+ThreadHandle]; Handle
0x14001a7e8  mov     ebx, eax
0x14001a7ea  call    cs:__imp_ZwClose
0x14001a7f1  nop     dword ptr [rax+rax+00h]
0x14001a7f6  test    ebx, ebx
0x14001a7f8  js      short loc_14001A828
0x14001a7fa  mov     rcx, [rbp+Object]; Object
0x14001a7fe  lea     edx, [rdi+6]; WaitReason
0x14001a801  xor     r9d, r9d; Alertable
0x14001a804  mov     [rsp+70h+ClientId], rdi; Timeout
0x14001a809  xor     r8d, r8d; WaitMode
0x14001a80c  call    cs:__imp_KeWaitForSingleObject
0x14001a813  nop     dword ptr [rax+rax+00h]
0x14001a818  mov     rcx, [rbp+Object]; Object
0x14001a81c  call    cs:__imp_ObfDereferenceObject
0x14001a823  nop     dword ptr [rax+rax+00h]
0x14001a828  mov     r9d, dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink+4
0x14001a82f  cmp     r9d, 2
0x14001a833  jz      loc_14001A931
0x14001a839  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a840  lea     rdi, WPP_GLOBAL_Control
0x14001a847  cmp     rcx, rdi
0x14001a84a  jz      loc_14001A92C
0x14001a850  cmp     byte ptr [rcx+29h], 2
0x14001a854  jb      loc_14001A92C
0x14001a85a  mov     edx, 19h
0x14001a85f  mov     rcx, [rcx+18h]
0x14001a863  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a86a  call    WPP_SF_d
0x14001a86f  jmp     loc_14001A92C
0x14001a874  lea     rax, [rbp+Timeout]
0x14001a878  mov     qword ptr [rbp+Timeout], 0FFFFFFFFDC3CBA00h
0x14001a880  xor     r9d, r9d; Alertable
0x14001a883  mov     [rsp+70h+ClientId], rax; Timeout
0x14001a888  xor     r8d, r8d; WaitMode
0x14001a88b  lea     rcx, WPP_MAIN_CB.DeviceExtension; Object
0x14001a892  xor     edx, edx; WaitReason
0x14001a894  call    cs:__imp_KeWaitForSingleObject
0x14001a89b  nop     dword ptr [rax+rax+00h]
0x14001a8a0  mov     ebx, eax
0x14001a8a2  test    eax, eax
0x14001a8a4  jnz     short loc_14001A8FB
0x14001a8a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8ad  lea     rdi, WPP_GLOBAL_Control
0x14001a8b4  cmp     rcx, rdi
0x14001a8b7  jz      short loc_14001A8D2
0x14001a8b9  cmp     byte ptr [rcx+29h], 4
0x14001a8bd  jb      short loc_14001A8D2
0x14001a8bf  mov     rcx, [rcx+18h]
0x14001a8c3  lea     edx, [rax+1Ah]
0x14001a8c6  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a8cd  call    WPP_SF_
0x14001a8d2  mov     r9d, dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink+4
0x14001a8d9  cmp     r9d, 2
0x14001a8dd  jz      short loc_14001A931
0x14001a8df  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8e6  cmp     rcx, rdi
0x14001a8e9  jz      short loc_14001A92C
0x14001a8eb  cmp     byte ptr [rcx+29h], 2
0x14001a8ef  jb      short loc_14001A92C
0x14001a8f1  mov     edx, 1Bh
0x14001a8f6  jmp     loc_14001A85F
0x14001a8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a902  lea     rdi, WPP_GLOBAL_Control
0x14001a909  cmp     rcx, rdi
0x14001a90c  jz      short loc_14001A92C
0x14001a90e  cmp     byte ptr [rcx+29h], 2
0x14001a912  jb      short loc_14001A92C
0x14001a914  mov     rcx, [rcx+18h]
0x14001a918  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a91f  mov     edx, 1Ch
0x14001a924  mov     r9d, eax
0x14001a927  call    WPP_SF_d
0x14001a92c  mov     ebx, 0C0000001h
0x14001a931  mov     eax, ebx
0x14001a933  add     rsp, 70h
0x14001a937  pop     rdi
0x14001a938  pop     rbx
0x14001a939  pop     rbp
0x14001a93a  retn
```
