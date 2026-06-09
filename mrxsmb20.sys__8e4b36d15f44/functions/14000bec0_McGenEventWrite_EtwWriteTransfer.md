# McGenEventWrite_EtwWriteTransfer

- ea: `0x14000bec0`
- end: `0x14000bf16`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ad90`
- `0x14000b940`
- `0x14000b9c0`
- `0x14000ba80`
- `0x14000bb90`
- `0x14000bcc0`
- `0x14000bd50`
- `0x1400286c0`
- `0x140028730`
- `0x140028fa8`
- `0x140029084`
- `0x140029df0`
- `0x14002caf4`
- `0x14002cb78`
- `0x14002cc10`
- `0x14002e3ec`
- `0x14002e488`
- `0x14002e584`
- `0x14002e610`
- `0x14002f8c4`
- `0x1400330a4`

## callees

- `0x14000bec0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000bef6`
- `ntoskrnl!EtwWriteTransfer` at `0x14000bef6`

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

  v5 = (unsigned __int16 *)qword_140046008;
  if ( qword_140046008 )
  {
    UserData->Ptr = qword_140046008;
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
  return EtwWriteTransfer(REMOTEFS_SMB_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14000bec0  sub     rsp, 38h
0x14000bec4  mov     rcx, cs:qword_140046008
0x14000becb  mov     rax, [rsp+38h+arg_20]
0x14000bed0  test    rcx, rcx
0x14000bed3  jnz     short loc_14000BF08
0x14000bed5  mov     [rax], rcx
0x14000bed8  xor     r10d, r10d
0x14000bedb  mov     [rax+8], ecx
0x14000bede  mov     [rsp+38h+UserData], rax; UserData
0x14000bee3  mov     [rax+0Ch], r10d
0x14000bee7  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x14000beee  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000bef3  xor     r9d, r9d; RelatedActivityId
0x14000bef6  call    cs:__imp_EtwWriteTransfer
0x14000befd  nop     dword ptr [rax+rax+00h]
0x14000bf02  add     rsp, 38h
0x14000bf06  retn
0x14000bf08  mov     [rax], rcx
0x14000bf0b  mov     r10d, 2
0x14000bf11  movzx   ecx, word ptr [rcx]
0x14000bf14  jmp     short loc_14000BEDB
```
