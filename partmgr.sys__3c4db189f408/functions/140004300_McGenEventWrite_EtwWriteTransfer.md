# McGenEventWrite_EtwWriteTransfer

- ea: `0x140004300`
- end: `0x140004356`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003674`
- `0x140003734`
- `0x1400037bc`
- `0x140004190`
- `0x140004260`
- `0x14000a3d0`
- `0x14000c14c`
- `0x14000c1b8`
- `0x14000c238`
- `0x14000c2a0`
- `0x14000df90`
- `0x14000e5b0`

## callees

- `0x140004300`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140004336`
- `ntoskrnl!EtwWriteTransfer` at `0x140004336`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r10d

  v5 = (unsigned __int16 *)qword_140017008;
  if ( qword_140017008 )
  {
    UserData->Ptr = qword_140017008;
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
  return EtwWriteTransfer(Microsoft_Windows_Partition_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140004300  sub     rsp, 38h
0x140004304  mov     rcx, cs:qword_140017008
0x14000430b  mov     rax, [rsp+38h+arg_20]
0x140004310  test    rcx, rcx
0x140004313  jnz     short loc_140004348
0x140004315  mov     [rax], rcx
0x140004318  xor     r10d, r10d
0x14000431b  mov     [rax+8], ecx
0x14000431e  mov     [rsp+38h+UserData], rax; UserData
0x140004323  mov     [rax+0Ch], r10d
0x140004327  mov     rcx, cs:Microsoft_Windows_Partition_Context; RegHandle
0x14000432e  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140004333  xor     r9d, r9d; RelatedActivityId
0x140004336  call    cs:__imp_EtwWriteTransfer
0x14000433d  nop     dword ptr [rax+rax+00h]
0x140004342  add     rsp, 38h
0x140004346  retn
0x140004348  mov     [rax], rcx
0x14000434b  mov     r10d, 2
0x140004351  movzx   ecx, word ptr [rcx]
0x140004354  jmp     short loc_14000431B
```
