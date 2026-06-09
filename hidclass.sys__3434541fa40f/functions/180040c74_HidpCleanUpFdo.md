# HidpCleanUpFdo

- ea: `0x180040c74`
- end: `0x180040d9c`
- name: `HidpCleanUpFdo`
- size: `296`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000621c`
- `0x18003b444`

## callees

- `0x18001775c`
- `0x180040c74`
- `0x180040da4`
- `0x180040f24`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x180040d81`
- `ntoskrnl!IoWMIRegistrationControl` at `0x180040d81`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180040d4a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180040d4a`
- `ntoskrnl!IoFreeWorkItem` at `0x180040d62`
- `ntoskrnl!IoFreeWorkItem` at `0x180040d62`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x180040ca1`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x180040ccf`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x180040cfd`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x180040ca1`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x180040ccf`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x180040cfd`

## pseudocode

```c
__int64 __fastcall HidpCleanUpFdo(__int64 a1)
{
  __int64 v2; // rax
  struct _IO_WORKITEM *v3; // rcx

  DequeueFdoExt(a1);
  HidpFdoFreeDeviceResources(a1);
  if ( *(_QWORD *)(a1 + 680) != *(_QWORD *)(a1 + 672) )
  {
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
    *(_QWORD *)(a1 + 680) = 0;
  }
  if ( *(_QWORD *)(a1 + 688) != *(_QWORD *)(a1 + 672) )
  {
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
    *(_QWORD *)(a1 + 688) = 0;
  }
  if ( g_RecorderLog != *(_QWORD *)(a1 + 672) )
  {
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
    v2 = *(_QWORD *)(a1 + 672);
    if ( *(_QWORD *)(a1 + 680) == v2 )
      *(_QWORD *)(a1 + 680) = 0;
    if ( *(_QWORD *)(a1 + 688) == v2 )
      *(_QWORD *)(a1 + 688) = 0;
    *(_QWORD *)(a1 + 672) = 0;
  }
  RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 256));
  v3 = *(struct _IO_WORKITEM **)(a1 + 1688);
  if ( v3 )
  {
    IoFreeWorkItem(v3);
    *(_QWORD *)(a1 + 1688) = 0;
  }
  IoWMIRegistrationControl(*(PDEVICE_OBJECT *)a1, 2u);
  return HidpDeleteDeviceObjects(a1);
}

```

## disassembly

```asm
0x180040c74  push    rbx
0x180040c76  sub     rsp, 20h
0x180040c7a  mov     rbx, rcx
0x180040c7d  call    DequeueFdoExt
0x180040c82  mov     rcx, rbx
0x180040c85  call    HidpFdoFreeDeviceResources
0x180040c8a  mov     rdx, [rbx+2A8h]
0x180040c91  cmp     rdx, [rbx+2A0h]
0x180040c98  jz      short loc_180040CB8
0x180040c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ca1  call    cs:__imp_imp_WppRecorderLogDelete
0x180040ca8  nop     dword ptr [rax+rax+00h]
0x180040cad  mov     qword ptr [rbx+2A8h], 0
0x180040cb8  mov     rdx, [rbx+2B0h]
0x180040cbf  cmp     rdx, [rbx+2A0h]
0x180040cc6  jz      short loc_180040CE6
0x180040cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ccf  call    cs:__imp_imp_WppRecorderLogDelete
0x180040cd6  nop     dword ptr [rax+rax+00h]
0x180040cdb  mov     qword ptr [rbx+2B0h], 0
0x180040ce6  mov     rdx, [rbx+2A0h]
0x180040ced  cmp     cs:g_RecorderLog, rdx
0x180040cf4  jz      short loc_180040D43
0x180040cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180040cfd  call    cs:__imp_imp_WppRecorderLogDelete
0x180040d04  nop     dword ptr [rax+rax+00h]
0x180040d09  mov     rax, [rbx+2A0h]
0x180040d10  cmp     [rbx+2A8h], rax
0x180040d17  jnz     short loc_180040D24
0x180040d19  mov     qword ptr [rbx+2A8h], 0
0x180040d24  cmp     [rbx+2B0h], rax
0x180040d2b  jnz     short loc_180040D38
0x180040d2d  mov     qword ptr [rbx+2B0h], 0
0x180040d38  mov     qword ptr [rbx+2A0h], 0
0x180040d43  lea     rcx, [rbx+100h]; UnicodeString
0x180040d4a  call    cs:__imp_RtlFreeUnicodeString
0x180040d51  nop     dword ptr [rax+rax+00h]
0x180040d56  mov     rcx, [rbx+698h]; IoWorkItem
0x180040d5d  test    rcx, rcx
0x180040d60  jz      short loc_180040D79
0x180040d62  call    cs:__imp_IoFreeWorkItem
0x180040d69  nop     dword ptr [rax+rax+00h]
0x180040d6e  mov     qword ptr [rbx+698h], 0
0x180040d79  mov     rcx, [rbx]; DeviceObject
0x180040d7c  mov     edx, 2; Action
0x180040d81  call    cs:__imp_IoWMIRegistrationControl
0x180040d88  nop     dword ptr [rax+rax+00h]
0x180040d8d  mov     rcx, rbx
0x180040d90  call    HidpDeleteDeviceObjects
0x180040d95  add     rsp, 20h
0x180040d99  pop     rbx
0x180040d9a  retn
```
