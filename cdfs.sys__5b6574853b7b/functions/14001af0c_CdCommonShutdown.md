# CdCommonShutdown

- ea: `0x14001af0c`
- end: `0x14001b0d1`
- name: `CdCommonShutdown`
- size: `453`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001240`

## callees

- `0x140001160`
- `0x1400024e0`
- `0x14000bcf8`
- `0x1400181a4`
- `0x14001af0c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14001b065`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b081`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b065`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b081`
- `ntoskrnl!IoDeleteDevice` at `0x14001b0a7`
- `ntoskrnl!IoDeleteDevice` at `0x14001b0a7`
- `ntoskrnl!KeInitializeEvent` at `0x14001af42`
- `ntoskrnl!KeInitializeEvent` at `0x14001af42`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001af5f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001af5f`
- `ntoskrnl!IofCallDriver` at `0x14001b005`
- `ntoskrnl!IofCallDriver` at `0x14001b005`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x14001afed`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x14001afed`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b02e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b02e`
- `ntoskrnl!KeClearEvent` at `0x14001b03f`
- `ntoskrnl!KeClearEvent` at `0x14001b03f`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14001b094`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14001b094`

## pseudocode

```c
__int64 __fastcall CdCommonShutdown(_DWORD *a1, IRP *a2)
{
  __int64 *v4; // rdi
  __int64 v5; // rbx
  IRP *v6; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-68h] BYREF
  struct _KEVENT Event; // [rsp+50h] [rbp-58h] BYREF

  a1[8] |= 0x200u;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  word_14000732E |= 1u;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v4 = (__int64 *)qword_1400072F0;
  while ( v4 != &qword_1400072F0 )
  {
    v5 = (__int64)(v4 - 4);
    v4 = (__int64 *)*v4;
    if ( (*(_DWORD *)(v5 + 48) & 0x400) == 0 && *(_DWORD *)(v5 + 52) == 2 )
    {
      CdAcquireResource(a1, v5 + 128, 0, 0);
      CdPurgeVolume((__int64)a1, v5, 0);
      v6 = IoBuildSynchronousFsdRequest(0x10u, *(PDEVICE_OBJECT *)(v5 + 16), 0, 0, 0, &Event, &IoStatusBlock);
      if ( v6 )
      {
        if ( IofCallDriver(*(PDEVICE_OBJECT *)(v5 + 16), v6) == 259 )
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        KeClearEvent(&Event);
      }
      *(_DWORD *)(v5 + 48) |= 0x400u;
      if ( (unsigned __int8)CdCheckForDismount(a1, v5, 0) )
        ExReleaseResourceLite((PERESOURCE)(v5 + 128));
    }
  }
  ExReleaseResourceLite(&Resource);
  IoUnregisterFileSystem(DeviceObject);
  IoDeleteDevice(DeviceObject);
  CdCompleteRequest(a1, a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14001af0c  push    rbx
0x14001af0e  push    rbp
0x14001af0f  push    rsi
0x14001af10  push    rdi
0x14001af11  push    r12
0x14001af13  push    r14
0x14001af15  sub     rsp, 78h
0x14001af19  bts     dword ptr [rcx+20h], 9
0x14001af1e  xorps   xmm0, xmm0
0x14001af21  mov     r14, rdx
0x14001af24  mov     rsi, rcx
0x14001af27  xor     eax, eax
0x14001af29  lea     rcx, [rsp+0A8h+Event]; Event
0x14001af2e  xor     edx, edx; Type
0x14001af30  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14001af35  xor     r8d, r8d; State
0x14001af38  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x14001af3d  movups  xmmword ptr [rsp+0A8h+var_68], xmm0
0x14001af42  call    cs:__imp_KeInitializeEvent
0x14001af49  nop     dword ptr [rax+rax+00h]
0x14001af4e  or      cs:word_14000732E, 1
0x14001af56  lea     rcx, Resource; Resource
0x14001af5d  mov     dl, 1; Wait
0x14001af5f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001af66  nop     dword ptr [rax+rax+00h]
0x14001af6b  mov     rdi, cs:qword_1400072F0
0x14001af72  lea     r12, qword_1400072F0
0x14001af79  jmp     loc_14001B071
0x14001af7e  lea     rbx, [rdi-20h]
0x14001af82  mov     rdi, [rdi]
0x14001af85  test    dword ptr [rbx+30h], 400h
0x14001af8c  jnz     loc_14001B071
0x14001af92  cmp     dword ptr [rbx+34h], 2
0x14001af96  jnz     loc_14001B071
0x14001af9c  lea     rbp, [rbx+80h]
0x14001afa3  xor     r9d, r9d
0x14001afa6  mov     rdx, rbp
0x14001afa9  xor     r8d, r8d
0x14001afac  mov     rcx, rsi
0x14001afaf  call    CdAcquireResource
0x14001afb4  xor     r8d, r8d
0x14001afb7  mov     rdx, rbx
0x14001afba  mov     rcx, rsi
0x14001afbd  call    CdPurgeVolume
0x14001afc2  mov     rdx, [rbx+10h]; DeviceObject
0x14001afc6  lea     rax, [rsp+0A8h+var_68]
0x14001afcb  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x14001afd0  xor     r9d, r9d; Length
0x14001afd3  lea     rax, [rsp+0A8h+Event]
0x14001afd8  xor     r8d, r8d; Buffer
0x14001afdb  mov     [rsp+0A8h+var_80], rax; Event
0x14001afe0  mov     [rsp+0A8h+StartingOffset], 0; StartingOffset
0x14001afe9  lea     ecx, [r9+10h]; MajorFunction
0x14001afed  call    cs:__imp_IoBuildSynchronousFsdRequest
0x14001aff4  nop     dword ptr [rax+rax+00h]
0x14001aff9  test    rax, rax
0x14001affc  jz      short loc_14001B04B
0x14001affe  mov     rcx, [rbx+10h]; DeviceObject
0x14001b002  mov     rdx, rax; Irp
0x14001b005  call    cs:__imp_IofCallDriver
0x14001b00c  nop     dword ptr [rax+rax+00h]
0x14001b011  cmp     eax, 103h
0x14001b016  jnz     short loc_14001B03A
0x14001b018  xor     r9d, r9d; Alertable
0x14001b01b  mov     [rsp+0A8h+StartingOffset], 0; Timeout
0x14001b024  xor     r8d, r8d; WaitMode
0x14001b027  lea     rcx, [rsp+0A8h+Event]; Object
0x14001b02c  xor     edx, edx; WaitReason
0x14001b02e  call    cs:__imp_KeWaitForSingleObject
0x14001b035  nop     dword ptr [rax+rax+00h]
0x14001b03a  lea     rcx, [rsp+0A8h+Event]; Event
0x14001b03f  call    cs:__imp_KeClearEvent
0x14001b046  nop     dword ptr [rax+rax+00h]
0x14001b04b  bts     dword ptr [rbx+30h], 0Ah
0x14001b050  xor     r8d, r8d
0x14001b053  mov     rdx, rbx
0x14001b056  mov     rcx, rsi
0x14001b059  call    CdCheckForDismount
0x14001b05e  test    al, al
0x14001b060  jz      short loc_14001B071
0x14001b062  mov     rcx, rbp; Resource
0x14001b065  call    cs:__imp_ExReleaseResourceLite
0x14001b06c  nop     dword ptr [rax+rax+00h]
0x14001b071  cmp     rdi, r12
0x14001b074  jnz     loc_14001AF7E
0x14001b07a  lea     rcx, Resource; Resource
0x14001b081  call    cs:__imp_ExReleaseResourceLite
0x14001b088  nop     dword ptr [rax+rax+00h]
0x14001b08d  mov     rcx, cs:DeviceObject; DeviceObject
0x14001b094  call    cs:__imp_IoUnregisterFileSystem
0x14001b09b  nop     dword ptr [rax+rax+00h]
0x14001b0a0  mov     rcx, cs:DeviceObject; DeviceObject
0x14001b0a7  call    cs:__imp_IoDeleteDevice
0x14001b0ae  nop     dword ptr [rax+rax+00h]
0x14001b0b3  xor     r8d, r8d
0x14001b0b6  mov     rdx, r14
0x14001b0b9  mov     rcx, rsi
0x14001b0bc  call    CdCompleteRequest
0x14001b0c1  xor     eax, eax
0x14001b0c3  add     rsp, 78h
0x14001b0c7  pop     r14
0x14001b0c9  pop     r12
0x14001b0cb  pop     rdi
0x14001b0cc  pop     rsi
0x14001b0cd  pop     rbp
0x14001b0ce  pop     rbx
0x14001b0cf  retn
```
