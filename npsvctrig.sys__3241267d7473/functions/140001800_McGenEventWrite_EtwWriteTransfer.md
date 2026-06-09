# McGenEventWrite_EtwWriteTransfer

- ea: `0x140001800`
- end: `0x140001857`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `87`
- prototype: `NTSTATUS __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400015f0`

## callees

- `0x140001800`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001845`
- `ntoskrnl!EtwWriteTransfer` at `0x140001845`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  ULONG v6; // r9d

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
  return EtwWriteTransfer(*a1, a2, 0, 0, 3u, UserData);
}

```

## disassembly

```asm
0x140001800  sub     rsp, 38h
0x140001804  mov     r8, [rcx+8]
0x140001808  mov     rax, [rsp+38h+arg_20]
0x14000180d  test    r8, r8
0x140001810  jnz     short loc_14000181A
0x140001812  mov     [rax], r8
0x140001815  xor     r9d, r9d
0x140001818  jmp     short loc_140001827
0x14000181a  mov     [rax], r8
0x14000181d  mov     r9d, 2
0x140001823  movzx   r8d, word ptr [r8]
0x140001827  mov     [rax+8], r8d
0x14000182b  xor     r8d, r8d; ActivityId
0x14000182e  mov     [rax+0Ch], r9d
0x140001832  xor     r9d, r9d; RelatedActivityId
0x140001835  mov     rcx, [rcx]; RegHandle
0x140001838  mov     [rsp+38h+UserData], rax; UserData
0x14000183d  mov     [rsp+38h+UserDataCount], 3; UserDataCount
0x140001845  call    cs:__imp_EtwWriteTransfer
0x14000184c  nop     dword ptr [rax+rax+00h]
0x140001851  add     rsp, 38h
0x140001855  retn
```
