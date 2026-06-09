# I8xMouseRemoveDevice

- ea: `0x14001bf78`
- end: `0x14001c061`
- name: `I8xMouseRemoveDevice`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001fa30`

## callees

- `0x140004530`
- `0x14001bf78`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001c00f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c00f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001c02d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001c02d`
- `ntoskrnl!IoDisconnectInterrupt` at `0x14001bfed`
- `ntoskrnl!IoDisconnectInterrupt` at `0x14001bfed`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14001bfcd`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14001bfcd`

## pseudocode

```c
void __fastcall I8xMouseRemoveDevice(__int64 a1, int a2)
{
  __int64 v2; // rbx
  void *v3; // rcx
  struct _KINTERRUPT *v4; // rcx
  void *v5; // rcx

  v2 = *(_QWORD *)(a1 + 64);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      16,
      25,
      (__int64)WPP_16fba2f764b430b57540c812abbc2952_Traceguids);
  if ( *(_BYTE *)(v2 + 563) )
  {
    v3 = *(void **)(v2 + 1080);
    if ( v3 )
    {
      IoUnregisterPlugPlayNotification(v3);
      *(_QWORD *)(v2 + 1080) = 0;
    }
  }
  v4 = *(struct _KINTERRUPT **)(v2 + 8);
  if ( v4 )
  {
    IoDisconnectInterrupt(v4);
    *(_QWORD *)(v2 + 8) = 0;
  }
  v5 = *(void **)(v2 + 944);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0);
    *(_QWORD *)(v2 + 944) = 0;
  }
  RtlFreeUnicodeString((PUNICODE_STRING)(v2 + 1032));
  if ( WPP_MAIN_CB.Queue.Wcb.DeviceRoutine == (PDRIVER_CONTROL)v2 )
  {
    **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels &= 0xFFFFFDF5;
    WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = 0;
  }
}

```

## disassembly

```asm
0x14001bf78  push    rbx
0x14001bf7a  sub     rsp, 30h
0x14001bf7e  mov     rbx, [rcx+40h]
0x14001bf82  lea     rax, WPP_RECORDER_INITIALIZED
0x14001bf89  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001bf90  jz      short loc_14001BFB8
0x14001bf92  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf99  lea     rax, WPP_16fba2f764b430b57540c812abbc2952_Traceguids
0x14001bfa0  mov     r9d, 19h
0x14001bfa6  mov     [rsp+38h+var_18], rax
0x14001bfab  mov     rcx, [rcx+40h]
0x14001bfaf  lea     r8d, [r9-9]
0x14001bfb3  call    WPP_RECORDER_SF_
0x14001bfb8  cmp     byte ptr [rbx+233h], 0
0x14001bfbf  jz      short loc_14001BFE4
0x14001bfc1  mov     rcx, [rbx+438h]; NotificationEntry
0x14001bfc8  test    rcx, rcx
0x14001bfcb  jz      short loc_14001BFE4
0x14001bfcd  call    cs:__imp_IoUnregisterPlugPlayNotification
0x14001bfd4  nop     dword ptr [rax+rax+00h]
0x14001bfd9  mov     qword ptr [rbx+438h], 0
0x14001bfe4  mov     rcx, [rbx+8]; InterruptObject
0x14001bfe8  test    rcx, rcx
0x14001bfeb  jz      short loc_14001C001
0x14001bfed  call    cs:__imp_IoDisconnectInterrupt
0x14001bff4  nop     dword ptr [rax+rax+00h]
0x14001bff9  mov     qword ptr [rbx+8], 0
0x14001c001  mov     rcx, [rbx+3B0h]; P
0x14001c008  test    rcx, rcx
0x14001c00b  jz      short loc_14001C026
0x14001c00d  xor     edx, edx; Tag
0x14001c00f  call    cs:__imp_ExFreePoolWithTag
0x14001c016  nop     dword ptr [rax+rax+00h]
0x14001c01b  mov     qword ptr [rbx+3B0h], 0
0x14001c026  lea     rcx, [rbx+408h]; UnicodeString
0x14001c02d  call    cs:__imp_RtlFreeUnicodeString
0x14001c034  nop     dword ptr [rax+rax+00h]
0x14001c039  cmp     qword ptr cs:WPP_MAIN_CB.Queue+18h, rbx
0x14001c040  jnz     short loc_14001C05A
0x14001c042  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001c049  and     dword ptr [rax], 0FFFFFDF5h
0x14001c04f  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, 0
0x14001c05a  add     rsp, 30h
0x14001c05e  pop     rbx
0x14001c05f  retn
```
