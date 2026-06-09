# WnsNotifications::UnInitialize(void)

- ea: `0x18001be34`
- end: `0x18001be58`
- name: `?UnInitialize@WnsNotifications@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(WnsNotifications *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026a08`
- `0x1800329e0`

## callees

- `0x18001be34`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001be45`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001be45`

## pseudocode

```c
void __fastcall WnsNotifications::UnInitialize(WnsNotifications *this)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(v2);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18001be34  push    rbx
0x18001be36  sub     rsp, 20h
0x18001be3a  mov     rbx, rcx
0x18001be3d  mov     rcx, [rcx]
0x18001be40  test    rcx, rcx
0x18001be43  jz      short loc_18001BE52
0x18001be45  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001be4b  mov     qword ptr [rbx], 0
0x18001be52  add     rsp, 20h
0x18001be56  pop     rbx
0x18001be57  retn
```
