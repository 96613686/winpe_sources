# AdapterEnumModuleData::DeInit(void)

- ea: `0x18001fd2c`
- end: `0x18001fe18`
- name: `?DeInit@AdapterEnumModuleData@@QEAAXXZ`
- size: `236`
- prototype: `void __fastcall(AdapterEnumModuleData *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f5f4`
- `0x18002eba8`

## callees

- `0x18000c6b0`
- `0x18001fd2c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fd7c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fd9a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fdb8`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fdd6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fdf7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fd7c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fd9a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fdb8`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fdd6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fdf7`

## string_xrefs

- `0x18001fd39`: `RtlUnsubscribeWnfNotificationWaitForCompletion for SubscriptionHandle from AdapterEnumModuleData`

## pseudocode

```c
void __fastcall AdapterEnumModuleData::DeInit(AdapterEnumModuleData *this)
{
  signed int v2; // eax
  CModule *v3; // rcx
  bool v4; // r9
  signed int v5; // eax
  CModule *v6; // rcx
  bool v7; // r9
  signed int v8; // eax
  CModule *v9; // rcx
  bool v10; // r9
  signed int v11; // eax
  CModule *v12; // rcx
  bool v13; // r9
  signed int v14; // eax
  CModule *v15; // rcx
  bool v16; // r9

  if ( *((_QWORD *)this + 1) )
  {
    v2 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v2 < 0 )
      CModule::RecordJournalImpl(
        v3,
        v2,
        "RtlUnsubscribeWnfNotificationWaitForCompletion for SubscriptionHandle from AdapterEnumModuleData",
        v4);
    *((_QWORD *)this + 1) = 0;
  }
  if ( *((_QWORD *)this + 2) )
  {
    v5 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v5 < 0 )
      CModule::RecordJournalImpl(
        v6,
        v5,
        "RtlUnsubscribeWnfNotificationWaitForCompletion for SubscriptionHandle from AdapterEnumModuleData",
        v7);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *((_QWORD *)this + 3) )
  {
    v8 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v8 < 0 )
      CModule::RecordJournalImpl(
        v9,
        v8,
        "RtlUnsubscribeWnfNotificationWaitForCompletion for SubscriptionHandle from AdapterEnumModuleData",
        v10);
    *((_QWORD *)this + 3) = 0;
  }
  if ( *((_QWORD *)this + 4) )
  {
    v11 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v11 < 0 )
      CModule::RecordJournalImpl(
        v12,
        v11,
        "RtlUnsubscribeWnfNotificationWaitForCompletion for SubscriptionHandle from AdapterEnumModuleData",
        v13);
    *((_QWORD *)this + 4) = 0;
  }
  if ( *((_QWORD *)this + 5) )
  {
    v14 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v14 < 0 )
      CModule::RecordJournalImpl(
        v15,
        v14,
        "RtlUnsubscribeWnfNotificationWaitForCompletion for SubscriptionHandle from AdapterEnumModuleData",
        v16);
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x18001fd2c  mov     [rsp+arg_0], rbx
0x18001fd31  push    rsi
0x18001fd32  sub     rsp, 20h
0x18001fd36  mov     rbx, rcx
0x18001fd39  lea     rsi, aRtlunsubscribe; "RtlUnsubscribeWnfNotificationWaitForCom"...
0x18001fd40  mov     rcx, [rcx+8]
0x18001fd44  test    rcx, rcx
0x18001fd47  jnz     short loc_18001FD7C
0x18001fd49  mov     rcx, [rbx+10h]
0x18001fd4d  test    rcx, rcx
0x18001fd50  jnz     short loc_18001FD9A
0x18001fd52  mov     rcx, [rbx+18h]
0x18001fd56  test    rcx, rcx
0x18001fd59  jnz     short loc_18001FDB8
0x18001fd5b  mov     rcx, [rbx+20h]
0x18001fd5f  test    rcx, rcx
0x18001fd62  jnz     short loc_18001FDD6
0x18001fd64  mov     rcx, [rbx+28h]
0x18001fd68  test    rcx, rcx
0x18001fd6b  jnz     loc_18001FDF7
0x18001fd71  mov     rbx, [rsp+28h+arg_0]
0x18001fd76  add     rsp, 20h
0x18001fd7a  pop     rsi
0x18001fd7b  retn
0x18001fd7c  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fd82  test    eax, eax
0x18001fd84  jns     short loc_18001FD90
0x18001fd86  mov     r8, rsi; char *
0x18001fd89  mov     edx, eax; unsigned int
0x18001fd8b  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001fd90  mov     qword ptr [rbx+8], 0
0x18001fd98  jmp     short loc_18001FD49
0x18001fd9a  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fda0  test    eax, eax
0x18001fda2  jns     short loc_18001FDAE
0x18001fda4  mov     r8, rsi; char *
0x18001fda7  mov     edx, eax; unsigned int
0x18001fda9  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001fdae  mov     qword ptr [rbx+10h], 0
0x18001fdb6  jmp     short loc_18001FD52
0x18001fdb8  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fdbe  test    eax, eax
0x18001fdc0  jns     short loc_18001FDCC
0x18001fdc2  mov     r8, rsi; char *
0x18001fdc5  mov     edx, eax; unsigned int
0x18001fdc7  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001fdcc  mov     qword ptr [rbx+18h], 0
0x18001fdd4  jmp     short loc_18001FD5B
0x18001fdd6  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fddc  test    eax, eax
0x18001fdde  jns     short loc_18001FDEA
0x18001fde0  mov     r8, rsi; char *
0x18001fde3  mov     edx, eax; unsigned int
0x18001fde5  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001fdea  mov     qword ptr [rbx+20h], 0
0x18001fdf2  jmp     loc_18001FD64
0x18001fdf7  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fdfd  test    eax, eax
0x18001fdff  jns     short loc_18001FE0B
0x18001fe01  mov     r8, rsi; char *
0x18001fe04  mov     edx, eax; unsigned int
0x18001fe06  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001fe0b  mov     qword ptr [rbx+28h], 0
0x18001fe13  jmp     loc_18001FD71
```
