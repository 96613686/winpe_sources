# McGenEventWrite_EtwWriteTransfer

- ea: `0x140004100`
- end: `0x140004159`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004160`
- `0x140009a00`
- `0x140009a44`
- `0x140009aa4`

## callees

- `0x140004100`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140004147`
- `ntoskrnl!EtwWriteTransfer` at `0x140004147`

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

  v5 = (unsigned __int16 *)qword_14001A008;
  if ( qword_14001A008 )
  {
    UserData->Ptr = qword_14001A008;
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
  return EtwWriteTransfer(PROV_PROJFS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140004100  sub     rsp, 38h
0x140004104  mov     rcx, cs:qword_14001A008
0x14000410b  mov     rax, [rsp+38h+arg_20]
0x140004110  test    rcx, rcx
0x140004113  jnz     short loc_14000411D
0x140004115  mov     [rax], rcx
0x140004118  xor     r8d, r8d
0x14000411b  jmp     short loc_140004129
0x14000411d  mov     [rax], rcx
0x140004120  mov     r8d, 2
0x140004126  movzx   ecx, word ptr [rcx]
0x140004129  mov     [rax+8], ecx
0x14000412c  mov     [rax+0Ch], r8d
0x140004130  xor     r8d, r8d; ActivityId
0x140004133  mov     rcx, cs:PROV_PROJFS_Context; RegHandle
0x14000413a  mov     [rsp+38h+UserData], rax; UserData
0x14000413f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140004144  xor     r9d, r9d; RelatedActivityId
0x140004147  call    cs:__imp_EtwWriteTransfer
0x14000414e  nop     dword ptr [rax+rax+00h]
0x140004153  add     rsp, 38h
0x140004157  retn
```
