# RxSystemControl

- ea: `0x140014ca0`
- end: `0x140014cfe`
- name: `RxSystemControl`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140069190`

## callees

- `0x140014ca0`
- `0x14001c4b4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140014ce6`
- `ntoskrnl!IofCompleteRequest` at `0x140014ce6`

## pseudocode

```c
__int64 __fastcall RxSystemControl(__int64 a1, IRP *a2, __int64 a3)
{
  a2->IoStatus.Status = -1073741808;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqhD(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, a2);
  }
  IofCompleteRequest(a2, 0);
  return 3221225488LL;
}

```

## disassembly

```asm
0x140014ca0  push    rbx
0x140014ca2  sub     rsp, 40h
0x140014ca6  mov     rbx, rdx
0x140014ca9  mov     dword ptr [rdx+30h], 0C0000010h
0x140014cb0  mov     r9, rcx
0x140014cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140014cba  lea     rax, WPP_GLOBAL_Control
0x140014cc1  cmp     rcx, rax
0x140014cc4  jz      short loc_140014CE1
0x140014cc6  mov     eax, [rcx+2Ch]
0x140014cc9  test    al, 4
0x140014ccb  jz      short loc_140014CE1
0x140014ccd  cmp     byte ptr [rcx+29h], 2
0x140014cd1  jb      short loc_140014CE1
0x140014cd3  mov     rcx, [rcx+18h]
0x140014cd7  mov     [rsp+48h+var_28], rdx
0x140014cdc  call    WPP_SF_qqhD
0x140014ce1  xor     edx, edx; PriorityBoost
0x140014ce3  mov     rcx, rbx; Irp
0x140014ce6  call    cs:__imp_IofCompleteRequest
0x140014ced  nop     dword ptr [rax+rax+00h]
0x140014cf2  mov     eax, 0C0000010h
0x140014cf7  add     rsp, 40h
0x140014cfb  pop     rbx
0x140014cfc  retn
```
