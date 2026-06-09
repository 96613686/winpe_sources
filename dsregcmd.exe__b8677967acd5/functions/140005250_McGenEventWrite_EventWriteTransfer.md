# McGenEventWrite_EventWriteTransfer

- ea: `0x140005250`
- end: `0x14000529d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400052a4`
- `0x140005324`

## callees

- `0x140005250`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140005292`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140005292`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
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
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140005250  sub     rsp, 38h
0x140005254  mov     r8, [rcx+8]
0x140005258  mov     rax, [rsp+38h+arg_20]
0x14000525d  test    r8, r8
0x140005260  jnz     short loc_14000526A
0x140005262  mov     [rax], r8
0x140005265  xor     r10d, r10d
0x140005268  jmp     short loc_140005277
0x14000526a  mov     [rax], r8
0x14000526d  mov     r10d, 2
0x140005273  movzx   r8d, word ptr [r8]
0x140005277  mov     [rax+8], r8d
0x14000527b  xor     r8d, r8d; ActivityId
0x14000527e  mov     [rsp+38h+UserData], rax; UserData
0x140005283  mov     [rax+0Ch], r10d
0x140005287  mov     rcx, [rcx]; RegHandle
0x14000528a  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000528f  xor     r9d, r9d; RelatedActivityId
0x140005292  call    cs:__imp_EventWriteTransfer
0x140005298  add     rsp, 38h
0x14000529c  retn
```
