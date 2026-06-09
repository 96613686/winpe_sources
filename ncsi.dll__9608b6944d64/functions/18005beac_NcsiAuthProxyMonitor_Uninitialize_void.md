# NcsiAuthProxyMonitor::Uninitialize(void)

- ea: `0x18005beac`
- end: `0x18005bf05`
- name: `?Uninitialize@NcsiAuthProxyMonitor@@QEAAXXZ`
- size: `89`
- prototype: `void __fastcall(NcsiAuthProxyMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050300`
- `0x18007b960`

## callees

- `0x180010200`
- `0x18005beac`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005bef2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005bef2`

## pseudocode

```c
void __fastcall NcsiAuthProxyMonitor::Uninitialize(NcsiAuthProxyMonitor *this)
{
  if ( *(_QWORD *)this )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_9435711ae3a73e1799bc00f38a268496_Traceguids);
    }
    RtlUnsubscribeWnfNotificationWaitForCompletion(*(_QWORD *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18005beac  push    rbx
0x18005beae  sub     rsp, 20h
0x18005beb2  cmp     qword ptr [rcx], 0
0x18005beb6  mov     rbx, rcx
0x18005beb9  jz      short loc_18005BEFF
0x18005bebb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bec2  lea     rax, WPP_GLOBAL_Control
0x18005bec9  cmp     rcx, rax
0x18005becc  jz      short loc_18005BEEF
0x18005bece  test    byte ptr [rcx+1Ch], 10h
0x18005bed2  jz      short loc_18005BEEF
0x18005bed4  cmp     byte ptr [rcx+19h], 5
0x18005bed8  jb      short loc_18005BEEF
0x18005beda  mov     rcx, [rcx+10h]
0x18005bede  lea     r8, WPP_9435711ae3a73e1799bc00f38a268496_Traceguids
0x18005bee5  mov     edx, 0Dh
0x18005beea  call    WPP_SF_
0x18005beef  mov     rcx, [rbx]
0x18005bef2  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18005bef8  mov     qword ptr [rbx], 0
0x18005beff  add     rsp, 20h
0x18005bf03  pop     rbx
0x18005bf04  retn
```
