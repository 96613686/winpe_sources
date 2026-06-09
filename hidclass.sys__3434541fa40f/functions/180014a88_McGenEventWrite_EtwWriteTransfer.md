# McGenEventWrite_EtwWriteTransfer

- ea: `0x180014a88`
- end: `0x180014ae1`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014980`
- `0x180014a44`

## callees

- `0x180014a88`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x180014abf`
- `ntoskrnl!EtwWriteTransfer` at `0x180014abf`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        ULONG a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r10
  unsigned int v7; // r9d
  int v8; // r11d

  v5 = (unsigned __int16 *)a1[1];
  v7 = 0;
  if ( v5 )
  {
    UserData->Ptr = (unsigned __int64)v5;
    v8 = 2;
    v7 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v8 = 0;
  }
  UserData->Size = v7;
  UserData->Reserved = v8;
  return EtwWriteTransfer(*a1, a2, a3, 0, a4, UserData);
}

```

## disassembly

```asm
0x180014a88  push    rbx
0x180014a8a  sub     rsp, 30h
0x180014a8e  mov     r10, [rcx+8]
0x180014a92  mov     ebx, r9d
0x180014a95  mov     rax, [rsp+38h+arg_20]
0x180014a9a  xor     r9d, r9d
0x180014a9d  test    r10, r10
0x180014aa0  jnz     short loc_180014AD2
0x180014aa2  mov     [rax], r9
0x180014aa5  mov     r11d, r9d
0x180014aa8  mov     [rax+8], r9d
0x180014aac  xor     r9d, r9d; RelatedActivityId
0x180014aaf  mov     [rax+0Ch], r11d
0x180014ab3  mov     rcx, [rcx]; RegHandle
0x180014ab6  mov     [rsp+38h+UserData], rax; UserData
0x180014abb  mov     [rsp+38h+UserDataCount], ebx; UserDataCount
0x180014abf  call    cs:__imp_EtwWriteTransfer
0x180014ac6  nop     dword ptr [rax+rax+00h]
0x180014acb  add     rsp, 30h
0x180014acf  pop     rbx
0x180014ad0  retn
0x180014ad2  mov     [rax], r10
0x180014ad5  mov     r11d, 2
0x180014adb  movzx   r9d, word ptr [r10]
0x180014adf  jmp     short loc_180014AA8
```
