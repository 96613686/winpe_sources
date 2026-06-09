# PcpStartRegistryNotification

- ea: `0x14001fd60`
- end: `0x14001feba`
- name: `PcpStartRegistryNotification`
- size: `346`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x14000b5e0`
- `0x14000eb54`
- `0x14001fa50`
- `0x14001fae4`
- `0x14001fd60`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001fd90`
- `ntoskrnl!KeInitializeEvent` at `0x14001fda8`
- `ntoskrnl!KeInitializeEvent` at `0x14001fd90`
- `ntoskrnl!KeInitializeEvent` at `0x14001fda8`
- `ntoskrnl!KeSetEvent` at `0x14001fe8c`
- `ntoskrnl!KeSetEvent` at `0x14001fe8c`
- `ntoskrnl!ZwOpenKey` at `0x14001fe11`
- `ntoskrnl!ZwOpenKey` at `0x14001fe11`

## pseudocode

```c
__int64 PcpStartRegistryNotification()
{
  char v0; // di
  NTSTATUS v1; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  char v4; // [rsp+60h] [rbp+10h] BYREF

  v4 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  v0 = 1;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  KeInitializeEvent(&PcgRegistryStateLock, SynchronizationEvent, 1u);
  KeInitializeEvent(&PcgRegistryCompletionEvent, NotificationEvent, 0);
  qword_1400185B8 = 0;
  qword_1400185B0 = (__int64)PcpRegistryNotificationCallback;
  *(_QWORD *)PcgPolicyNotifyCallbackWorkItem = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)L"vx";
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  v1 = ZwOpenKey(&PcgPolicyKeyHandle, 0x20019u, &ObjectAttributes);
  if ( v1 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_67a0081011b8336ab20862c5401e156e_Traceguids,
        (unsigned int)v1);
    }
    goto LABEL_11;
  }
  if ( (unsigned __int8)PcpQueryIfRegistryHiveExists(&v4) )
  {
    PcpProcessSettingsChange();
    goto LABEL_10;
  }
  if ( v4 )
  {
    v0 = 0;
LABEL_10:
    if ( v4 )
      goto LABEL_12;
  }
LABEL_11:
  KeSetEvent(&PcgRegistryCompletionEvent, 0, 0);
LABEL_12:
  if ( v0 )
    PcpDisableRegistryNotification();
  else
    *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1 |= 0x40uLL;
  return 0;
}

```

## disassembly

```asm
0x14001fd60  mov     [rsp-8+arg_8], rdi
0x14001fd65  push    rbp
0x14001fd66  mov     rbp, rsp
0x14001fd69  sub     rsp, 50h
0x14001fd6d  xorps   xmm0, xmm0
0x14001fd70  lea     rcx, PcgRegistryStateLock; Event
0x14001fd77  xor     eax, eax
0x14001fd79  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001fd7d  mov     [rbp+arg_0], al
0x14001fd80  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001fd84  lea     edi, [rax+1]
0x14001fd87  mov     r8b, dil; State
0x14001fd8a  mov     edx, edi; Type
0x14001fd8c  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14001fd90  call    cs:__imp_KeInitializeEvent
0x14001fd97  nop     dword ptr [rax+rax+00h]
0x14001fd9c  xor     r8d, r8d; State
0x14001fd9f  lea     rcx, PcgRegistryCompletionEvent; Event
0x14001fda6  xor     edx, edx; Type
0x14001fda8  call    cs:__imp_KeInitializeEvent
0x14001fdaf  nop     dword ptr [rax+rax+00h]
0x14001fdb4  lea     rax, PcpRegistryNotificationCallback
0x14001fdbb  mov     cs:qword_1400185B8, 0
0x14001fdc6  mov     cs:qword_1400185B0, rax
0x14001fdcd  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001fdd1  lea     rax, PcgRegistryKeyHiveList; "vx"
0x14001fdd8  mov     cs:PcgPolicyNotifyCallbackWorkItem, 0
0x14001fde3  xorps   xmm0, xmm0
0x14001fde6  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001fdea  mov     edx, 20019h; DesiredAccess
0x14001fdef  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001fdf6  lea     rcx, PcgPolicyKeyHandle; KeyHandle
0x14001fdfd  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14001fe05  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14001fe0c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001fe11  call    cs:__imp_ZwOpenKey
0x14001fe18  nop     dword ptr [rax+rax+00h]
0x14001fe1d  test    eax, eax
0x14001fe1f  jns     short loc_14001FE5D
0x14001fe21  mov     r10, cs:WPP_GLOBAL_Control
0x14001fe28  lea     rcx, WPP_GLOBAL_Control
0x14001fe2f  cmp     r10, rcx
0x14001fe32  jz      short loc_14001FE80
0x14001fe34  cmp     byte ptr [r10+29h], 2
0x14001fe39  jb      short loc_14001FE80
0x14001fe3b  test    dword ptr [r10+2Ch], 800h
0x14001fe43  jz      short loc_14001FE80
0x14001fe45  mov     rcx, [r10+18h]
0x14001fe49  lea     edx, [rdi+9]
0x14001fe4c  mov     r9d, eax
0x14001fe4f  lea     r8, WPP_67a0081011b8336ab20862c5401e156e_Traceguids
0x14001fe56  call    WPP_SF_D
0x14001fe5b  jmp     short loc_14001FE80
0x14001fe5d  lea     rcx, [rbp+arg_0]
0x14001fe61  call    PcpQueryIfRegistryHiveExists
0x14001fe66  test    al, al
0x14001fe68  jz      short loc_14001FE71
0x14001fe6a  call    PcpProcessSettingsChange
0x14001fe6f  jmp     short loc_14001FE7A
0x14001fe71  cmp     [rbp+arg_0], 0
0x14001fe75  jz      short loc_14001FE80
0x14001fe77  xor     dil, dil
0x14001fe7a  cmp     [rbp+arg_0], 0
0x14001fe7e  jnz     short loc_14001FE98
0x14001fe80  xor     r8d, r8d; Wait
0x14001fe83  lea     rcx, PcgRegistryCompletionEvent; Event
0x14001fe8a  xor     edx, edx; Increment
0x14001fe8c  call    cs:__imp_KeSetEvent
0x14001fe93  nop     dword ptr [rax+rax+00h]
0x14001fe98  test    dil, dil
0x14001fe9b  jz      short loc_14001FEA4
0x14001fe9d  call    PcpDisableRegistryNotification
0x14001fea2  jmp     short loc_14001FEAC
0x14001fea4  or      qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, 40h
0x14001feac  mov     rdi, [rsp+50h+arg_8]
0x14001feb1  xor     eax, eax
0x14001feb3  add     rsp, 50h
0x14001feb7  pop     rbp
0x14001feb8  retn
```
