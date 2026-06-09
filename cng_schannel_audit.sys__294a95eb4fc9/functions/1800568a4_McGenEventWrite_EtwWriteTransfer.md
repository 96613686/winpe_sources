# McGenEventWrite_EtwWriteTransfer

- ea: `0x1800568a4`
- end: `0x1800568f8`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180056900`
- `0x180056988`
- `0x180056a44`
- `0x180056af4`
- `0x18005a7b8`
- `0x18005dd54`

## callees

- `0x1800568a4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1800568e6`
- `ntoskrnl!EtwWriteTransfer` at `0x1800568e6`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
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
  return EtwWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800568a4  sub     rsp, 38h
0x1800568a8  mov     r8, [rcx+8]
0x1800568ac  mov     rax, [rsp+38h+arg_20]
0x1800568b1  test    r8, r8
0x1800568b4  jnz     short loc_1800568BE
0x1800568b6  mov     [rax], r8
0x1800568b9  xor     r10d, r10d
0x1800568bc  jmp     short loc_1800568CB
0x1800568be  mov     [rax], r8
0x1800568c1  mov     r10d, 2
0x1800568c7  movzx   r8d, word ptr [r8]
0x1800568cb  mov     [rax+8], r8d
0x1800568cf  xor     r8d, r8d; ActivityId
0x1800568d2  mov     [rsp+38h+UserData], rax; UserData
0x1800568d7  mov     [rax+0Ch], r10d
0x1800568db  mov     rcx, [rcx]; RegHandle
0x1800568de  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800568e3  xor     r9d, r9d; RelatedActivityId
0x1800568e6  call    cs:__imp_EtwWriteTransfer
0x1800568ed  nop     dword ptr [rax+rax+00h]
0x1800568f2  add     rsp, 38h
0x1800568f6  retn
```
