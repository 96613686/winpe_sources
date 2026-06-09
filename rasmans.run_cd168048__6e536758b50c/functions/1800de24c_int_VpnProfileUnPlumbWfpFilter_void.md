# int_VpnProfileUnPlumbWfpFilter(void)

- ea: `0x1800de24c`
- end: `0x1800de316`
- name: `?int_VpnProfileUnPlumbWfpFilter@@YAXXZ`
- size: `202`
- prototype: `void(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d1ecc`
- `0x1800db738`
- `0x1800ddb70`
- `0x1800de7e0`
- `0x1800e0a90`

## callees

- `0x180005bcc`
- `0x1800de24c`

## import_xrefs

- `fwpuclnt!FwpmCalloutDeleteByKey0` at `0x1800de2c2`
- `fwpuclnt!FwpmCalloutDeleteByKey0` at `0x1800de2dc`
- `fwpuclnt!FwpmCalloutDeleteByKey0` at `0x1800de2c2`
- `fwpuclnt!FwpmCalloutDeleteByKey0` at `0x1800de2dc`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800de28e`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800de2a8`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800de28e`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800de2a8`

## pseudocode

```c
void int_VpnProfileUnPlumbWfpFilter(void)
{
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 549, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  FwpmFilterDeleteByKey0(g_FwpEngineHandle, &key);
  FwpmFilterDeleteByKey0(g_FwpEngineHandle, &stru_1800FDFA8);
  FwpmCalloutDeleteByKey0(g_FwpEngineHandle, &stru_18010B540);
  FwpmCalloutDeleteByKey0(g_FwpEngineHandle, &stru_18010B560);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 550, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
}

```

## disassembly

```asm
0x1800de24c  push    rbx
0x1800de24e  sub     rsp, 20h
0x1800de252  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de259  lea     rbx, WPP_GLOBAL_Control
0x1800de260  cmp     rcx, rbx
0x1800de263  jz      short loc_1800DE280
0x1800de265  test    byte ptr [rcx+1Ch], 8
0x1800de269  jz      short loc_1800DE280
0x1800de26b  mov     rcx, [rcx+10h]
0x1800de26f  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800de276  mov     edx, 225h
0x1800de27b  call    WPP_SF_
0x1800de280  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; engineHandle
0x1800de287  lea     rdx, key; key
0x1800de28e  call    cs:__imp_FwpmFilterDeleteByKey0
0x1800de295  nop     dword ptr [rax+rax+00h]
0x1800de29a  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; engineHandle
0x1800de2a1  lea     rdx, stru_1800FDFA8; key
0x1800de2a8  call    cs:__imp_FwpmFilterDeleteByKey0
0x1800de2af  nop     dword ptr [rax+rax+00h]
0x1800de2b4  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; engineHandle
0x1800de2bb  lea     rdx, stru_18010B540; key
0x1800de2c2  call    cs:__imp_FwpmCalloutDeleteByKey0
0x1800de2c9  nop     dword ptr [rax+rax+00h]
0x1800de2ce  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; engineHandle
0x1800de2d5  lea     rdx, stru_18010B560; key
0x1800de2dc  call    cs:__imp_FwpmCalloutDeleteByKey0
0x1800de2e3  nop     dword ptr [rax+rax+00h]
0x1800de2e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de2ef  cmp     rcx, rbx
0x1800de2f2  jz      short loc_1800DE30F
0x1800de2f4  test    byte ptr [rcx+1Ch], 8
0x1800de2f8  jz      short loc_1800DE30F
0x1800de2fa  mov     rcx, [rcx+10h]
0x1800de2fe  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800de305  mov     edx, 226h
0x1800de30a  call    WPP_SF_
0x1800de30f  add     rsp, 20h
0x1800de313  pop     rbx
0x1800de314  retn
```
