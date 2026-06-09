# StereoModuleData::DeInit(void)

- ea: `0x18001fe84`
- end: `0x18001fef4`
- name: `?DeInit@StereoModuleData@@QEAAXXZ`
- size: `112`
- prototype: `void __fastcall(StereoModuleData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f5f4`

## callees

- `0x18000c6b0`
- `0x18001fe84`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fea4`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fecc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fea4`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fecc`

## string_xrefs

- `0x18001feae`: `RtlUnsubscribeWnfNotificationWaitForCompletion`
- `0x18001fed6`: `RtlUnsubscribeWnfNotificationWaitForCompletion`

## pseudocode

```c
void __fastcall StereoModuleData::DeInit(StereoModuleData *this)
{
  signed int v2; // eax
  CModule *v3; // rcx
  bool v4; // r9
  signed int v5; // eax
  CModule *v6; // rcx
  bool v7; // r9

  if ( *(_QWORD *)this )
  {
    v2 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v2 < 0 )
      CModule::RecordJournalImpl(v3, v2, "RtlUnsubscribeWnfNotificationWaitForCompletion", v4);
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 4) = 0;
  }
  if ( *((_QWORD *)this + 1) )
  {
    v5 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v5 < 0 )
      CModule::RecordJournalImpl(v6, v5, "RtlUnsubscribeWnfNotificationWaitForCompletion", v7);
    *((_QWORD *)this + 1) = 0;
    *((_WORD *)this + 10) = 0;
  }
}

```

## disassembly

```asm
0x18001fe84  push    rbx
0x18001fe86  sub     rsp, 20h
0x18001fe8a  mov     rbx, rcx
0x18001fe8d  mov     rcx, [rcx]
0x18001fe90  test    rcx, rcx
0x18001fe93  jnz     short loc_18001FEA4
0x18001fe95  mov     rcx, [rbx+8]
0x18001fe99  test    rcx, rcx
0x18001fe9c  jnz     short loc_18001FECC
0x18001fe9e  add     rsp, 20h
0x18001fea2  pop     rbx
0x18001fea3  retn
0x18001fea4  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001feaa  test    eax, eax
0x18001feac  jns     short loc_18001FEBC
0x18001feae  lea     r8, aRtlunsubscribe_0; "RtlUnsubscribeWnfNotificationWaitForCom"...
0x18001feb5  mov     edx, eax; unsigned int
0x18001feb7  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001febc  mov     qword ptr [rbx], 0
0x18001fec3  mov     dword ptr [rbx+10h], 0
0x18001feca  jmp     short loc_18001FE95
0x18001fecc  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fed2  test    eax, eax
0x18001fed4  jns     short loc_18001FEE4
0x18001fed6  lea     r8, aRtlunsubscribe_0; "RtlUnsubscribeWnfNotificationWaitForCom"...
0x18001fedd  mov     edx, eax; unsigned int
0x18001fedf  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001fee4  mov     qword ptr [rbx+8], 0
0x18001feec  mov     word ptr [rbx+14h], 0
0x18001fef2  jmp     short loc_18001FE9E
```
