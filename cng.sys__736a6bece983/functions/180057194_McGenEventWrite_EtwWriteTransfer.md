# McGenEventWrite_EtwWriteTransfer

- ea: `0x180057194`
- end: `0x1800571e8`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800571f0`
- `0x180057278`
- `0x180057334`
- `0x1800573e4`
- `0x18005b0a8`
- `0x18005e644`

## callees

- `0x180057194`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1800571d6`
- `ntoskrnl!EtwWriteTransfer` at `0x1800571d6`

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
0x180057194  sub     rsp, 38h
0x180057198  mov     r8, [rcx+8]
0x18005719c  mov     rax, [rsp+38h+arg_20]
0x1800571a1  test    r8, r8
0x1800571a4  jnz     short loc_1800571AE
0x1800571a6  mov     [rax], r8
0x1800571a9  xor     r10d, r10d
0x1800571ac  jmp     short loc_1800571BB
0x1800571ae  mov     [rax], r8
0x1800571b1  mov     r10d, 2
0x1800571b7  movzx   r8d, word ptr [r8]
0x1800571bb  mov     [rax+8], r8d
0x1800571bf  xor     r8d, r8d; ActivityId
0x1800571c2  mov     [rsp+38h+UserData], rax; UserData
0x1800571c7  mov     [rax+0Ch], r10d
0x1800571cb  mov     rcx, [rcx]; RegHandle
0x1800571ce  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800571d3  xor     r9d, r9d; RelatedActivityId
0x1800571d6  call    cs:__imp_EtwWriteTransfer
0x1800571dd  nop     dword ptr [rax+rax+00h]
0x1800571e2  add     rsp, 38h
0x1800571e6  retn
```
