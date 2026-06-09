# ClassMpdevInternalDeviceControl

- ea: `0x14003a700`
- end: `0x14003a77c`
- name: `ClassMpdevInternalDeviceControl`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14001fc38`
- `0x14003a700`
- `0x14003ae28`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003a75d`
- `ntoskrnl!IofCompleteRequest` at `0x14003a75d`

## pseudocode

```c
__int64 __fastcall ClassMpdevInternalDeviceControl(__int64 a1, IRP *a2)
{
  if ( !*(_BYTE *)(*(_QWORD *)(a1 + 64) + 582LL) )
    return ClasspMpdevDefaultDispatch(a1, a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids, a1);
  }
  a2->IoStatus.Status = -1073741632;
  IofCompleteRequest(a2, 0);
  return 3221225664LL;
}

```

## disassembly

```asm
0x14003a700  push    rbx
0x14003a702  sub     rsp, 20h
0x14003a706  mov     rax, [rcx+40h]
0x14003a70a  mov     rbx, rdx
0x14003a70d  mov     r8, rcx
0x14003a710  cmp     byte ptr [rax+246h], 0
0x14003a717  jz      short loc_14003A770
0x14003a719  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a720  lea     rax, WPP_GLOBAL_Control
0x14003a727  cmp     rcx, rax
0x14003a72a  jz      short loc_14003A751
0x14003a72c  mov     eax, [rcx+2Ch]
0x14003a72f  test    al, 10h
0x14003a731  jz      short loc_14003A751
0x14003a733  cmp     byte ptr [rcx+29h], 3
0x14003a737  jb      short loc_14003A751
0x14003a739  mov     rcx, [rcx+18h]
0x14003a73d  mov     r9, r8
0x14003a740  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a747  mov     edx, 0Ah
0x14003a74c  call    WPP_SF_q
0x14003a751  xor     edx, edx; PriorityBoost
0x14003a753  mov     dword ptr [rbx+30h], 0C00000C0h
0x14003a75a  mov     rcx, rbx; Irp
0x14003a75d  call    cs:__imp_IofCompleteRequest
0x14003a764  nop     dword ptr [rax+rax+00h]
0x14003a769  mov     eax, 0C00000C0h
0x14003a76e  jmp     short loc_14003A775
0x14003a770  call    ClasspMpdevDefaultDispatch
0x14003a775  add     rsp, 20h
0x14003a779  pop     rbx
0x14003a77a  retn
```
