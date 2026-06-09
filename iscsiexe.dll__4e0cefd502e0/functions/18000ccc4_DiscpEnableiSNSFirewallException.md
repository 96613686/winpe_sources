# DiscpEnableiSNSFirewallException

- ea: `0x18000ccc4`
- end: `0x18000cd74`
- name: `DiscpEnableiSNSFirewallException`
- size: `176`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004380`
- `0x180009408`

## callees

- `0x18000ccc4`
- `0x180016c48`

## import_xrefs

- `ISCSIUM!DiscpGetRegistryValue` at `0x18000ccfe`
- `ISCSIUM!DiscpGetRegistryValue` at `0x18000ccfe`
- `ISCSIUM!DiscpReportEventlog` at `0x18000cd49`
- `ISCSIUM!DiscpReportEventlog` at `0x18000cd49`
- `ISCSIUM!DiscpFreeMemory` at `0x18000cd59`
- `ISCSIUM!DiscpFreeMemory` at `0x18000cd59`

## pseudocode

```c
__int64 DiscpEnableiSNSFirewallException()
{
  unsigned int v0; // ebx
  int v1; // eax
  char v3; // [rsp+20h] [rbp-28h]
  int v4; // [rsp+28h] [rbp-20h]
  int v5; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+58h] [rbp+10h] BYREF
  _DWORD *v7; // [rsp+60h] [rbp+18h] BYREF

  v0 = 0;
  v7 = 0;
  v3 = 0;
  v6 = 0;
  if ( (unsigned int)DiscpGetRegistryValue(
                       0,
                       L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery",
                       L"AllowiSNSFirewallException",
                       4,
                       v3,
                       &v7,
                       &v6) )
  {
    v0 = -268500890;
    goto LABEL_9;
  }
  if ( *v7 )
  {
    v5 = 0;
    v1 = WindowsFirewall_EnableiSCSI(1);
    v5 = v1;
    if ( v1 >= 0 && v1 != 1 )
      goto LABEL_7;
    LOWORD(v4) = 0;
    DiscpReportEventlog(122, 2, 0, 4, &v5, v4);
  }
  v0 = -268500890;
LABEL_7:
  DiscpFreeMemory(v7);
LABEL_9:
  iSNSFirewallEnabled = v0;
  return v0;
}

```

## disassembly

```asm
0x18000ccc4  mov     r11, rsp
0x18000ccc7  push    rbx
0x18000ccc8  sub     rsp, 40h
0x18000cccc  xor     ebx, ebx
0x18000ccce  lea     rax, [r11+10h]
0x18000ccd2  mov     [r11-18h], rax
0x18000ccd6  lea     r8, aAllowisnsfirew; "AllowiSNSFirewallException"
0x18000ccdd  lea     rax, [r11+18h]
0x18000cce1  mov     [r11+18h], rbx
0x18000cce5  mov     [r11-20h], rax
0x18000cce9  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000ccf0  lea     r9d, [rbx+4]
0x18000ccf4  mov     byte ptr [rsp+48h+var_28], bl
0x18000ccf8  xor     ecx, ecx
0x18000ccfa  mov     [rsp+48h+arg_8], ebx
0x18000ccfe  call    cs:__imp_DiscpGetRegistryValue
0x18000cd04  test    eax, eax
0x18000cd06  jnz     short loc_18000CD61
0x18000cd08  mov     rax, [rsp+48h+arg_10]
0x18000cd0d  cmp     [rax], ebx
0x18000cd0f  jz      short loc_18000CD4F
0x18000cd11  lea     ecx, [rbx+1]
0x18000cd14  mov     [rsp+48h+arg_0], ebx
0x18000cd18  call    WindowsFirewall_EnableiSCSI
0x18000cd1d  mov     [rsp+48h+arg_0], eax
0x18000cd21  test    eax, eax
0x18000cd23  js      short loc_18000CD2A
0x18000cd25  cmp     eax, 1
0x18000cd28  jnz     short loc_18000CD54
0x18000cd2a  mov     edx, 2
0x18000cd2f  mov     word ptr [rsp+48h+var_20], bx
0x18000cd34  lea     rax, [rsp+48h+arg_0]
0x18000cd39  movzx   r8d, bx
0x18000cd3d  mov     [rsp+48h+var_28], rax
0x18000cd42  lea     r9d, [rdx+2]
0x18000cd46  lea     ecx, [rdx+78h]
0x18000cd49  call    cs:__imp_DiscpReportEventlog
0x18000cd4f  mov     ebx, 0EFFF0066h
0x18000cd54  mov     rcx, [rsp+48h+arg_10]
0x18000cd59  call    cs:__imp_DiscpFreeMemory
0x18000cd5f  jmp     short loc_18000CD66
0x18000cd61  mov     ebx, 0EFFF0066h
0x18000cd66  mov     cs:iSNSFirewallEnabled, ebx
0x18000cd6c  mov     eax, ebx
0x18000cd6e  add     rsp, 40h
0x18000cd72  pop     rbx
0x18000cd73  retn
```
