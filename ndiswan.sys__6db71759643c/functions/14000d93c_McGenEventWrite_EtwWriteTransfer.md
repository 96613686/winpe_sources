# McGenEventWrite_EtwWriteTransfer

- ea: `0x14000d93c`
- end: `0x14000d995`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d99c`

## callees

- `0x14000d93c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000d983`
- `ntoskrnl!EtwWriteTransfer` at `0x14000d983`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // r9d

  v5 = (unsigned __int16 *)qword_14001D098;
  if ( qword_14001D098 )
  {
    UserData->Ptr = qword_14001D098;
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
  return EtwWriteTransfer(MICROSOFT_RAS_NDISWAN_PACKETCAPTURE_PROVIDER_Context, a2, a3, 0, 5u, UserData);
}

```

## disassembly

```asm
0x14000d93c  sub     rsp, 38h
0x14000d940  mov     rcx, cs:qword_14001D098
0x14000d947  mov     rax, [rsp+38h+arg_20]
0x14000d94c  test    rcx, rcx
0x14000d94f  jnz     short loc_14000D959
0x14000d951  mov     [rax], rcx
0x14000d954  xor     r9d, r9d
0x14000d957  jmp     short loc_14000D965
0x14000d959  mov     [rax], rcx
0x14000d95c  mov     r9d, 2
0x14000d962  movzx   ecx, word ptr [rcx]
0x14000d965  mov     [rax+8], ecx
0x14000d968  mov     [rax+0Ch], r9d
0x14000d96c  xor     r9d, r9d; RelatedActivityId
0x14000d96f  mov     rcx, cs:MICROSOFT_RAS_NDISWAN_PACKETCAPTURE_PROVIDER_Context; RegHandle
0x14000d976  mov     [rsp+38h+UserData], rax; UserData
0x14000d97b  mov     [rsp+38h+UserDataCount], 5; UserDataCount
0x14000d983  call    cs:__imp_EtwWriteTransfer
0x14000d98a  nop     dword ptr [rax+rax+00h]
0x14000d98f  add     rsp, 38h
0x14000d993  retn
```
