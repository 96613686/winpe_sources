# I8xKeyboardRemoveDevice

- ea: `0x1400197e8`
- end: `0x1400198da`
- name: `I8xKeyboardRemoveDevice`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14001fa30`

## callees

- `0x140004530`
- `0x14000b1a0`
- `0x1400197e8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140019879`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019879`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400198b4`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400198b4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400198c7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400198c7`
- `ntoskrnl!IoDisconnectInterrupt` at `0x140019857`
- `ntoskrnl!IoDisconnectInterrupt` at `0x140019857`

## pseudocode

```c
void __fastcall I8xKeyboardRemoveDevice(__int64 a1, int a2)
{
  __int64 v2; // rbx
  struct _KINTERRUPT *v3; // rcx
  void *v4; // rcx

  v2 = *(_QWORD *)(a1 + 64);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      16,
      21,
      (__int64)WPP_b71d3786c0783d031954a21c92de3f01_Traceguids);
  if ( WPP_MAIN_CB.Queue.Wcb.DeviceContext == (PVOID)v2 && v2 )
  {
    **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels &= 0xFFFFFEFE;
    WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
  }
  v3 = *(struct _KINTERRUPT **)(v2 + 8);
  if ( v3 )
  {
    IoDisconnectInterrupt(v3);
    *(_QWORD *)(v2 + 8) = 0;
  }
  v4 = *(void **)(v2 + 872);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    *(_QWORD *)(v2 + 872) = 0;
  }
  if ( *(_BYTE *)(v2 + 563) )
    I8xKeyboardRemoveDeviceInitialized(v2);
  if ( *(_QWORD *)(v2 + 680) )
  {
    IoSetDeviceInterfaceState((PUNICODE_STRING)(v2 + 672), 0);
    RtlFreeUnicodeString((PUNICODE_STRING)(v2 + 672));
  }
}

```

## disassembly

```asm
0x1400197e8  push    rbx
0x1400197ea  sub     rsp, 30h
0x1400197ee  mov     rbx, [rcx+40h]
0x1400197f2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400197f9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019800  jz      short loc_140019828
0x140019802  mov     rcx, cs:WPP_GLOBAL_Control
0x140019809  lea     rax, WPP_b71d3786c0783d031954a21c92de3f01_Traceguids
0x140019810  mov     r9d, 15h
0x140019816  mov     [rsp+38h+var_18], rax
0x14001981b  mov     rcx, [rcx+40h]
0x14001981f  lea     r8d, [r9-5]
0x140019823  call    WPP_RECORDER_SF_
0x140019828  cmp     qword ptr cs:WPP_MAIN_CB.Queue+20h, rbx
0x14001982f  jnz     short loc_14001984E
0x140019831  test    rbx, rbx
0x140019834  jz      short loc_14001984E
0x140019836  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001983d  and     dword ptr [rax], 0FFFFFEFEh
0x140019843  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14001984e  mov     rcx, [rbx+8]; InterruptObject
0x140019852  test    rcx, rcx
0x140019855  jz      short loc_14001986B
0x140019857  call    cs:__imp_IoDisconnectInterrupt
0x14001985e  nop     dword ptr [rax+rax+00h]
0x140019863  mov     qword ptr [rbx+8], 0
0x14001986b  mov     rcx, [rbx+368h]; P
0x140019872  test    rcx, rcx
0x140019875  jz      short loc_140019890
0x140019877  xor     edx, edx; Tag
0x140019879  call    cs:__imp_ExFreePoolWithTag
0x140019880  nop     dword ptr [rax+rax+00h]
0x140019885  mov     qword ptr [rbx+368h], 0
0x140019890  cmp     byte ptr [rbx+233h], 0
0x140019897  jz      short loc_1400198A1
0x140019899  mov     rcx, rbx
0x14001989c  call    I8xKeyboardRemoveDeviceInitialized
0x1400198a1  cmp     qword ptr [rbx+2A8h], 0
0x1400198a9  jz      short loc_1400198D3
0x1400198ab  xor     edx, edx; Enable
0x1400198ad  lea     rcx, [rbx+2A0h]; SymbolicLinkName
0x1400198b4  call    cs:__imp_IoSetDeviceInterfaceState
0x1400198bb  nop     dword ptr [rax+rax+00h]
0x1400198c0  lea     rcx, [rbx+2A0h]; UnicodeString
0x1400198c7  call    cs:__imp_RtlFreeUnicodeString
0x1400198ce  nop     dword ptr [rax+rax+00h]
0x1400198d3  add     rsp, 30h
0x1400198d7  pop     rbx
0x1400198d8  retn
```
