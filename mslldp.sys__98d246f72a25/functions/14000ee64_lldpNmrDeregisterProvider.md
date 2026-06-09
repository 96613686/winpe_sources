# lldpNmrDeregisterProvider

- ea: `0x14000ee64`
- end: `0x14000ef08`
- name: `lldpNmrDeregisterProvider`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e670`

## callees

- `0x140004b00`
- `0x14000ee64`

## import_xrefs

- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x14000ee92`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x14000ee92`
- `NETIO!NmrDeregisterProvider` at `0x14000ee78`
- `NETIO!NmrDeregisterProvider` at `0x14000ee78`

## pseudocode

```c
void lldpNmrDeregisterProvider()
{
  unsigned int v0; // eax
  PDEVICE_OBJECT v1; // rcx
  __int64 v2; // rdx

  if ( WPP_MAIN_CB.Queue.ListEntry.Blink )
  {
    v0 = NmrDeregisterProvider(WPP_MAIN_CB.Queue.ListEntry.Blink);
    if ( v0 == 259 )
    {
      v0 = NmrWaitForProviderDeregisterComplete(WPP_MAIN_CB.Queue.ListEntry.Blink);
      if ( !v0 )
        goto LABEL_12;
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        goto LABEL_12;
      v2 = 18;
    }
    else
    {
      if ( !v0 )
        goto LABEL_12;
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        goto LABEL_12;
      v2 = 19;
    }
    WPP_SF_d(v1->AttachedDevice, v2, WPP_7b2e41ea31413e6a6d3bdbc4c714aeb2_Traceguids, v0);
LABEL_12:
    WPP_MAIN_CB.Queue.ListEntry.Blink = 0;
  }
}

```

## disassembly

```asm
0x14000ee64  sub     rsp, 28h
0x14000ee68  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8; NmrProviderHandle
0x14000ee6f  test    rcx, rcx
0x14000ee72  jz      loc_14000EF02
0x14000ee78  call    cs:__imp_NmrDeregisterProvider
0x14000ee7f  nop     dword ptr [rax+rax+00h]
0x14000ee84  cmp     eax, 103h
0x14000ee89  jnz     short loc_14000EEC2
0x14000ee8b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8; NmrProviderHandle
0x14000ee92  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x14000ee99  nop     dword ptr [rax+rax+00h]
0x14000ee9e  test    eax, eax
0x14000eea0  jz      short loc_14000EEF7
0x14000eea2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eea9  lea     rdx, WPP_GLOBAL_Control
0x14000eeb0  cmp     rcx, rdx
0x14000eeb3  jz      short loc_14000EEF7
0x14000eeb5  cmp     byte ptr [rcx+29h], 3
0x14000eeb9  jb      short loc_14000EEF7
0x14000eebb  mov     edx, 12h
0x14000eec0  jmp     short loc_14000EEE4
0x14000eec2  test    eax, eax
0x14000eec4  jz      short loc_14000EEF7
0x14000eec6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eecd  lea     rdx, WPP_GLOBAL_Control
0x14000eed4  cmp     rcx, rdx
0x14000eed7  jz      short loc_14000EEF7
0x14000eed9  cmp     byte ptr [rcx+29h], 3
0x14000eedd  jb      short loc_14000EEF7
0x14000eedf  mov     edx, 13h
0x14000eee4  mov     rcx, [rcx+18h]
0x14000eee8  lea     r8, WPP_7b2e41ea31413e6a6d3bdbc4c714aeb2_Traceguids
0x14000eeef  mov     r9d, eax
0x14000eef2  call    WPP_SF_d
0x14000eef7  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, 0
0x14000ef02  add     rsp, 28h
0x14000ef06  retn
```
