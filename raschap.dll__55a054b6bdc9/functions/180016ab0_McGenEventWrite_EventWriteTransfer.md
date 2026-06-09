# McGenEventWrite_EventWriteTransfer

- ea: `0x180016ab0`
- end: `0x180016afd`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180016b04`
- `0x18001b878`
- `0x180025514`
- `0x1800255ec`
- `0x18002566c`

## callees

- `0x180016ab0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016af2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016af2`

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
0x180016ab0  sub     rsp, 38h
0x180016ab4  mov     r8, [rcx+8]
0x180016ab8  mov     rax, [rsp+38h+arg_20]
0x180016abd  test    r8, r8
0x180016ac0  jnz     short loc_180016ACA
0x180016ac2  mov     [rax], r8
0x180016ac5  xor     r10d, r10d
0x180016ac8  jmp     short loc_180016AD7
0x180016aca  mov     [rax], r8
0x180016acd  mov     r10d, 2
0x180016ad3  movzx   r8d, word ptr [r8]
0x180016ad7  mov     [rax+8], r8d
0x180016adb  xor     r8d, r8d; ActivityId
0x180016ade  mov     [rsp+38h+UserData], rax; UserData
0x180016ae3  mov     [rax+0Ch], r10d
0x180016ae7  mov     rcx, [rcx]; RegHandle
0x180016aea  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180016aef  xor     r9d, r9d; RelatedActivityId
0x180016af2  call    cs:__imp_EventWriteTransfer
0x180016af8  add     rsp, 38h
0x180016afc  retn
```
