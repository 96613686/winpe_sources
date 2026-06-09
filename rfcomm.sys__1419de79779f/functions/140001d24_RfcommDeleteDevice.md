# RfcommDeleteDevice

- ea: `0x140001d24`
- end: `0x140001eab`
- name: `RfcommDeleteDevice`
- size: `391`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001460`
- `0x140002ec8`

## callees

- `0x140001d24`
- `0x140004a68`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140001e87`
- `ntoskrnl!IoDeleteDevice` at `0x140001e87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001ddc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001ddc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e19`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001d70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001db6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001d70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001db6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140001d4b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140001d4b`
- `ntoskrnl!IoDetachDevice` at `0x140001dcd`
- `ntoskrnl!IoDetachDevice` at `0x140001dcd`

## string_xrefs

- `0x140001e29`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`

## pseudocode

```c
void __fastcall RfcommDeleteDevice(__int64 *a1)
{
  __int64 v2; // rsi
  void *v3; // rcx
  _QWORD **v4; // rdi
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  struct _DEVICE_OBJECT *v7; // rcx
  __int64 *v8; // rcx
  __int64 **v9; // rax
  int v10; // edx

  v2 = a1[12];
  if ( a1[44] )
  {
    RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 43));
    a1[44] = 0;
  }
  v3 = (void *)a1[45];
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    a1[45] = 0;
  }
  v4 = (_QWORD **)(a1 + 51);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( (_QWORD **)v5[1] != v4 )
      goto LABEL_17;
    v6 = (_QWORD *)*v5;
    if ( *(_QWORD **)(*v5 + 8LL) != v5 )
      goto LABEL_17;
    *v4 = v6;
    v6[1] = v4;
    ExFreePoolWithTag(v5, 0);
  }
  v7 = (struct _DEVICE_OBJECT *)a1[11];
  if ( v7 )
    IoDetachDevice(v7);
  *(_BYTE *)(v2 + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v2);
  v8 = (__int64 *)*a1;
  if ( *(__int64 **)(*a1 + 8) != a1 || (v9 = (__int64 **)a1[1], *v9 != a1) )
LABEL_17:
    __fastfail(3u);
  *v9 = v8;
  v8[1] = (__int64)v9;
  a1[1] = (__int64)a1;
  *a1 = (__int64)a1;
  KeReleaseSpinLock((PKSPIN_LOCK)v2, *(_BYTE *)(v2 + 8));
  RefObj_ReleaseEx(
    *(_QWORD *)(v2 + 16) + 24LL,
    542065734,
    2511,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      5,
      102,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      a1[10]);
  IoDeleteDevice((PDEVICE_OBJECT)a1[10]);
}

```

## disassembly

```asm
0x140001d24  mov     [rsp+arg_0], rbx
0x140001d29  mov     [rsp+arg_8], rsi
0x140001d2e  push    rdi
0x140001d2f  sub     rsp, 30h
0x140001d33  cmp     qword ptr [rcx+160h], 0
0x140001d3b  mov     rbx, rcx
0x140001d3e  mov     rsi, [rcx+60h]
0x140001d42  jz      short loc_140001D62
0x140001d44  add     rcx, 158h; UnicodeString
0x140001d4b  call    cs:__imp_RtlFreeUnicodeString
0x140001d52  nop     dword ptr [rax+rax+00h]
0x140001d57  mov     qword ptr [rbx+160h], 0
0x140001d62  mov     rcx, [rbx+168h]; P
0x140001d69  test    rcx, rcx
0x140001d6c  jz      short loc_140001D87
0x140001d6e  xor     edx, edx; Tag
0x140001d70  call    cs:__imp_ExFreePoolWithTag
0x140001d77  nop     dword ptr [rax+rax+00h]
0x140001d7c  mov     qword ptr [rbx+168h], 0
0x140001d87  lea     rdi, [rbx+198h]
0x140001d8e  mov     rcx, [rdi]; P
0x140001d91  cmp     rcx, rdi
0x140001d94  jz      short loc_140001DC4
0x140001d96  cmp     [rcx+8], rdi
0x140001d9a  jnz     loc_140001EA4
0x140001da0  mov     rax, [rcx]
0x140001da3  cmp     [rax+8], rcx
0x140001da7  jnz     loc_140001EA4
0x140001dad  mov     [rdi], rax
0x140001db0  xor     edx, edx; Tag
0x140001db2  mov     [rax+8], rdi
0x140001db6  call    cs:__imp_ExFreePoolWithTag
0x140001dbd  nop     dword ptr [rax+rax+00h]
0x140001dc2  jmp     short loc_140001D8E
0x140001dc4  mov     rcx, [rbx+58h]; TargetDevice
0x140001dc8  test    rcx, rcx
0x140001dcb  jz      short loc_140001DD9
0x140001dcd  call    cs:__imp_IoDetachDevice
0x140001dd4  nop     dword ptr [rax+rax+00h]
0x140001dd9  mov     rcx, rsi; SpinLock
0x140001ddc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001de3  nop     dword ptr [rax+rax+00h]
0x140001de8  mov     [rsi+8], al
0x140001deb  mov     rcx, [rbx]
0x140001dee  cmp     [rcx+8], rbx
0x140001df2  jnz     loc_140001EA4
0x140001df8  mov     rax, [rbx+8]
0x140001dfc  cmp     [rax], rbx
0x140001dff  jnz     loc_140001EA4
0x140001e05  mov     [rax], rcx
0x140001e08  mov     [rcx+8], rax
0x140001e0c  mov     rcx, rsi; SpinLock
0x140001e0f  mov     [rbx+8], rbx
0x140001e13  mov     [rbx], rbx
0x140001e16  mov     dl, [rsi+8]; NewIrql
0x140001e19  call    cs:__imp_KeReleaseSpinLock
0x140001e20  nop     dword ptr [rax+rax+00h]
0x140001e25  mov     rcx, [rsi+10h]
0x140001e29  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140001e30  add     rcx, 18h
0x140001e34  mov     edx, 204F4446h
0x140001e39  mov     r8d, 9CFh
0x140001e3f  call    RefObj_ReleaseEx
0x140001e44  lea     rax, WPP_RECORDER_INITIALIZED
0x140001e4b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001e52  jz      short loc_140001E83
0x140001e54  mov     rax, [rbx+50h]
0x140001e58  mov     r9d, 66h ; 'f'
0x140001e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e65  mov     [rsp+38h+var_10], rax
0x140001e6a  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140001e71  mov     [rsp+38h+var_18], rax
0x140001e76  lea     r8d, [r9-61h]
0x140001e7a  mov     rcx, [rcx+40h]
0x140001e7e  call    WPP_RECORDER_SF_q
0x140001e83  mov     rcx, [rbx+50h]; DeviceObject
0x140001e87  call    cs:__imp_IoDeleteDevice
0x140001e8e  nop     dword ptr [rax+rax+00h]
0x140001e93  mov     rbx, [rsp+38h+arg_0]
0x140001e98  mov     rsi, [rsp+38h+arg_8]
0x140001e9d  add     rsp, 30h
0x140001ea1  pop     rdi
0x140001ea2  retn
0x140001ea4  mov     ecx, 3
0x140001ea9  int     29h; Win8: RtlFailFast(ecx)
```
