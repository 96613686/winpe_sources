# McGenEventWrite_EtwWriteTransfer

- ea: `0x140003c54`
- end: `0x140003caa`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003cb0`
- `0x140003d30`
- `0x140003dd8`
- `0x140003ecc`
- `0x140003f78`

## callees

- `0x140003c54`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140003c98`
- `ntoskrnl!EtwWriteTransfer` at `0x140003c98`

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

  v5 = (unsigned __int16 *)qword_14000A008;
  if ( qword_14000A008 )
  {
    UserData->Ptr = qword_14000A008;
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
  return EtwWriteTransfer(DiskEventProvider_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140003c54  sub     rsp, 38h
0x140003c58  mov     rcx, cs:qword_14000A008
0x140003c5f  mov     rax, [rsp+38h+arg_20]
0x140003c64  test    rcx, rcx
0x140003c67  jnz     short loc_140003C71
0x140003c69  mov     [rax], rcx
0x140003c6c  xor     r10d, r10d
0x140003c6f  jmp     short loc_140003C7D
0x140003c71  mov     [rax], rcx
0x140003c74  mov     r10d, 2
0x140003c7a  movzx   ecx, word ptr [rcx]
0x140003c7d  mov     [rax+8], ecx
0x140003c80  mov     [rsp+38h+UserData], rax; UserData
0x140003c85  mov     [rax+0Ch], r10d
0x140003c89  mov     rcx, cs:DiskEventProvider_Context; RegHandle
0x140003c90  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140003c95  xor     r9d, r9d; RelatedActivityId
0x140003c98  call    cs:__imp_EtwWriteTransfer
0x140003c9f  nop     dword ptr [rax+rax+00h]
0x140003ca4  add     rsp, 38h
0x140003ca8  retn
```
