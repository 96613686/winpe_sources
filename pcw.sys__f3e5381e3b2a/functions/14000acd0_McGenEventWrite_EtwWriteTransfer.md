# McGenEventWrite_EtwWriteTransfer

- ea: `0x14000acd0`
- end: `0x14000ad29`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ad30`
- `0x14000d8fc`
- `0x14000d98c`

## callees

- `0x14000acd0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000ad17`
- `ntoskrnl!EtwWriteTransfer` at `0x14000ad17`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_140011118;
  if ( qword_140011118 )
  {
    UserData->Ptr = qword_140011118;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EtwWriteTransfer(PCW_EVENT_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14000acd0  sub     rsp, 38h
0x14000acd4  mov     rcx, cs:qword_140011118
0x14000acdb  mov     rax, [rsp+38h+arg_20]
0x14000ace0  test    rcx, rcx
0x14000ace3  jnz     short loc_14000ACED
0x14000ace5  mov     [rax], rcx
0x14000ace8  xor     r8d, r8d
0x14000aceb  jmp     short loc_14000ACF9
0x14000aced  mov     [rax], rcx
0x14000acf0  mov     r8d, 2
0x14000acf6  movzx   ecx, word ptr [rcx]
0x14000acf9  mov     [rax+8], ecx
0x14000acfc  mov     [rax+0Ch], r8d
0x14000ad00  xor     r8d, r8d; ActivityId
0x14000ad03  mov     rcx, cs:PCW_EVENT_PROVIDER_Context; RegHandle
0x14000ad0a  mov     [rsp+38h+UserData], rax; UserData
0x14000ad0f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000ad14  xor     r9d, r9d; RelatedActivityId
0x14000ad17  call    cs:__imp_EtwWriteTransfer
0x14000ad1e  nop     dword ptr [rax+rax+00h]
0x14000ad23  add     rsp, 38h
0x14000ad27  retn
```
