# HsmCreateOrOpenNamedEvent

- ea: `0x140034e04`
- end: `0x1400350b7`
- name: `HsmCreateOrOpenNamedEvent`
- size: `691`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140038de0`

## callees

- `0x140003c50`
- `0x140010640`
- `0x1400150fc`
- `0x140034e04`
- `0x140082050`

## import_xrefs

- `ntoskrnl!ZwOpenEvent` at `0x140034f1a`
- `ntoskrnl!ZwOpenEvent` at `0x140034f1a`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x140034fea`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x140034fea`
- `ntoskrnl!ZwCreateEvent` at `0x140034ef0`
- `ntoskrnl!ZwCreateEvent` at `0x140034ef0`
- `ntoskrnl!ExEventObjectType` at `0x140034fbb`
- `ntoskrnl!KeClearEvent` at `0x140035031`
- `ntoskrnl!KeClearEvent` at `0x140035031`
- `ntoskrnl!ZwClose` at `0x140035064`
- `ntoskrnl!ZwClose` at `0x140035064`
- `ntoskrnl!ObfDereferenceObject` at `0x140035079`
- `ntoskrnl!ObfDereferenceObject` at `0x140035079`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035090`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035090`

## pseudocode

```c
__int64 __fastcall HsmCreateOrOpenNamedEvent(
        void **a1,
        struct _KEVENT **a2,
        __int64 a3,
        __int64 a4,
        struct _KEVENT *Object)
{
  NTSTATUS v7; // ebx
  int v8; // r8d
  int v9; // r9d
  int Timer_high; // edx
  PDEVICE_OBJECT v11; // rcx
  int v12; // edx
  PVOID P; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  void *EventHandle; // [rsp+B8h] [rbp+38h] BYREF

  P = 0;
  EventHandle = 0;
  Object = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v7 = SeSddlSecurityDescriptorFromSDDL(asc_140028220, a2, &P);
  HsmDbgBreakOnStatus((unsigned int)v7);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_ZZd(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v8, v9);
    }
    goto LABEL_24;
  }
  ObjectAttributes.ObjectName = (PUNICODE_STRING)aBd;
  ObjectAttributes.SecurityDescriptor = P;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityQualityOfService = 0;
  v7 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  HsmDbgBreakOnStatus((unsigned int)v7);
  if ( v7 == -1073741771 )
  {
    v7 = ZwOpenEvent(&EventHandle, 0x1F0003u, &ObjectAttributes);
    HsmDbgBreakOnStatus((unsigned int)v7);
    if ( v7 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_24;
      }
      v12 = 56;
      goto LABEL_12;
    }
  }
  else if ( v7 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_24;
    }
    v12 = 57;
LABEL_12:
    WPP_SF_Zd(
      v11->AttachedDevice,
      v12,
      (unsigned int)WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
      (unsigned int)aBd,
      v7);
    goto LABEL_24;
  }
  v7 = ObReferenceObjectByHandleWithTag(
         EventHandle,
         2u,
         (POBJECT_TYPE)ExEventObjectType,
         0,
         0x67706C43u,
         (PVOID *)&Object,
         0);
  HsmDbgBreakOnStatus((unsigned int)v7);
  if ( v7 >= 0 )
  {
    KeClearEvent(Object);
    *a1 = EventHandle;
    *a2 = Object;
    EventHandle = 0;
    Object = 0;
    goto LABEL_24;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v12 = 58;
    goto LABEL_12;
  }
LABEL_24:
  if ( EventHandle )
    ZwClose(EventHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140034e04  mov     [rsp-18h+arg_0], rbx
0x140034e09  mov     [rsp-18h+arg_8], rsi
0x140034e0e  mov     [rsp-18h+EventHandle], r9
0x140034e13  push    rbp
0x140034e14  push    rdi
0x140034e15  push    r15
0x140034e17  mov     rbp, rsp
0x140034e1a  sub     rsp, 80h
0x140034e21  xorps   xmm0, xmm0
0x140034e24  mov     [rbp+P], 0
0x140034e2c  mov     rsi, rcx
0x140034e2f  mov     [rbp+EventHandle], 0
0x140034e37  lea     rcx, asc_140028220; ":<"
0x140034e3e  mov     [rbp+arg_20], 0
0x140034e46  lea     r8, [rbp+P]
0x140034e4a  mov     rdi, rdx
0x140034e4d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140034e51  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140034e55  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140034e59  call    SeSddlSecurityDescriptorFromSDDL
0x140034e5e  mov     ecx, eax
0x140034e60  mov     ebx, eax
0x140034e62  call    HsmDbgBreakOnStatus
0x140034e67  test    ebx, ebx
0x140034e69  jns     short loc_140034EAA
0x140034e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140034e72  lea     rax, WPP_GLOBAL_Control
0x140034e79  cmp     rcx, rax
0x140034e7c  jz      loc_14003505B
0x140034e82  mov     edx, [rcx+2Ch]
0x140034e85  test    dl, 8
0x140034e88  jz      loc_14003505B
0x140034e8e  cmp     byte ptr [rcx+29h], 2
0x140034e92  jb      loc_14003505B
0x140034e98  mov     rcx, [rcx+18h]
0x140034e9c  mov     dword ptr [rsp+80h+Object], ebx
0x140034ea0  call    WPP_SF_ZZd
0x140034ea5  jmp     loc_14003505B
0x140034eaa  mov     rax, [rbp+P]
0x140034eae  lea     r15, aBd; "BD"
0x140034eb5  xor     r9d, r9d; EventType
0x140034eb8  mov     [rbp+ObjectAttributes.ObjectName], r15
0x140034ebc  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140034ec0  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x140034ec4  mov     edx, 1F0003h; DesiredAccess
0x140034ec9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140034ed0  lea     rcx, [rbp+EventHandle]; EventHandle
0x140034ed4  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140034edc  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140034ee3  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140034eeb  mov     [rsp+80h+InitialState], 0; InitialState
0x140034ef0  call    cs:__imp_ZwCreateEvent
0x140034ef7  nop     dword ptr [rax+rax+00h]
0x140034efc  mov     ecx, eax
0x140034efe  mov     ebx, eax
0x140034f00  call    HsmDbgBreakOnStatus
0x140034f05  cmp     ebx, 0C0000035h
0x140034f0b  jnz     short loc_140034F84
0x140034f0d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140034f11  mov     edx, 1F0003h; DesiredAccess
0x140034f16  lea     rcx, [rbp+EventHandle]; EventHandle
0x140034f1a  call    cs:__imp_ZwOpenEvent
0x140034f21  nop     dword ptr [rax+rax+00h]
0x140034f26  mov     ecx, eax
0x140034f28  mov     ebx, eax
0x140034f2a  call    HsmDbgBreakOnStatus
0x140034f2f  test    ebx, ebx
0x140034f31  jns     loc_140034FBB
0x140034f37  mov     rcx, cs:WPP_GLOBAL_Control
0x140034f3e  lea     rax, WPP_GLOBAL_Control
0x140034f45  cmp     rcx, rax
0x140034f48  jz      loc_14003505B
0x140034f4e  mov     eax, [rcx+2Ch]
0x140034f51  test    al, 8
0x140034f53  jz      loc_14003505B
0x140034f59  cmp     byte ptr [rcx+29h], 2
0x140034f5d  jb      loc_14003505B
0x140034f63  mov     edx, 38h ; '8'
0x140034f68  mov     rcx, [rcx+18h]
0x140034f6c  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x140034f73  mov     r9, r15
0x140034f76  mov     dword ptr [rsp+80h+InitialState], ebx
0x140034f7a  call    WPP_SF_Zd
0x140034f7f  jmp     loc_14003505B
0x140034f84  test    ebx, ebx
0x140034f86  jns     short loc_140034FBB
0x140034f88  mov     rcx, cs:WPP_GLOBAL_Control
0x140034f8f  lea     rax, WPP_GLOBAL_Control
0x140034f96  cmp     rcx, rax
0x140034f99  jz      loc_14003505B
0x140034f9f  mov     eax, [rcx+2Ch]
0x140034fa2  test    al, 8
0x140034fa4  jz      loc_14003505B
0x140034faa  cmp     byte ptr [rcx+29h], 2
0x140034fae  jb      loc_14003505B
0x140034fb4  mov     edx, 39h ; '9'
0x140034fb9  jmp     short loc_140034F68
0x140034fbb  mov     r8, cs:ExEventObjectType
0x140034fc2  lea     rax, [rbp+arg_20]
0x140034fc6  mov     rcx, [rbp+EventHandle]; Handle
0x140034fca  xor     r9d, r9d; AccessMode
0x140034fcd  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x140034fd6  mov     [rsp+80h+Object], rax; Object
0x140034fdb  mov     r8, [r8]; ObjectType
0x140034fde  lea     edx, [r9+2]; DesiredAccess
0x140034fe2  mov     dword ptr [rsp+80h+InitialState], 67706C43h; Tag
0x140034fea  call    cs:__imp_ObReferenceObjectByHandleWithTag
0x140034ff1  nop     dword ptr [rax+rax+00h]
0x140034ff6  mov     ecx, eax
0x140034ff8  mov     ebx, eax
0x140034ffa  call    HsmDbgBreakOnStatus
0x140034fff  test    ebx, ebx
0x140035001  jns     short loc_14003502D
0x140035003  mov     rcx, cs:WPP_GLOBAL_Control
0x14003500a  lea     rax, WPP_GLOBAL_Control
0x140035011  cmp     rcx, rax
0x140035014  jz      short loc_14003505B
0x140035016  mov     eax, [rcx+2Ch]
0x140035019  test    al, 8
0x14003501b  jz      short loc_14003505B
0x14003501d  cmp     byte ptr [rcx+29h], 2
0x140035021  jb      short loc_14003505B
0x140035023  mov     edx, 3Ah ; ':'
0x140035028  jmp     loc_140034F68
0x14003502d  mov     rcx, [rbp+arg_20]; Event
0x140035031  call    cs:__imp_KeClearEvent
0x140035038  nop     dword ptr [rax+rax+00h]
0x14003503d  mov     rax, [rbp+EventHandle]
0x140035041  mov     [rsi], rax
0x140035044  mov     rax, [rbp+arg_20]
0x140035048  mov     [rdi], rax
0x14003504b  mov     [rbp+EventHandle], 0
0x140035053  mov     [rbp+arg_20], 0
0x14003505b  mov     rcx, [rbp+EventHandle]; Handle
0x14003505f  test    rcx, rcx
0x140035062  jz      short loc_140035070
0x140035064  call    cs:__imp_ZwClose
0x14003506b  nop     dword ptr [rax+rax+00h]
0x140035070  mov     rcx, [rbp+arg_20]; Object
0x140035074  test    rcx, rcx
0x140035077  jz      short loc_140035085
0x140035079  call    cs:__imp_ObfDereferenceObject
0x140035080  nop     dword ptr [rax+rax+00h]
0x140035085  mov     rcx, [rbp+P]; P
0x140035089  test    rcx, rcx
0x14003508c  jz      short loc_14003509C
0x14003508e  xor     edx, edx; Tag
0x140035090  call    cs:__imp_ExFreePoolWithTag
0x140035097  nop     dword ptr [rax+rax+00h]
0x14003509c  lea     r11, [rsp+80h+var_s0]
0x1400350a4  mov     eax, ebx
0x1400350a6  mov     rbx, [r11+20h]
0x1400350aa  mov     rsi, [r11+28h]
0x1400350ae  mov     rsp, r11
0x1400350b1  pop     r15
0x1400350b3  pop     rdi
0x1400350b4  pop     rbp
0x1400350b5  retn
```
