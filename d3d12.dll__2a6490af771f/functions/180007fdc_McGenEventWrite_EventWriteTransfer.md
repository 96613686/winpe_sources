# McGenEventWrite_EventWriteTransfer

- ea: `0x180007fdc`
- end: `0x180008029`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007f78`
- `0x180011ba0`
- `0x180011c48`
- `0x180013908`

## callees

- `0x180007fdc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000801e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000801e`

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
0x180007fdc  sub     rsp, 38h
0x180007fe0  mov     r8, [rcx+8]
0x180007fe4  mov     rax, [rsp+38h+arg_20]
0x180007fe9  test    r8, r8
0x180007fec  jnz     short loc_180007FF6
0x180007fee  mov     [rax], r8
0x180007ff1  xor     r10d, r10d
0x180007ff4  jmp     short loc_180008003
0x180007ff6  mov     [rax], r8
0x180007ff9  mov     r10d, 2
0x180007fff  movzx   r8d, word ptr [r8]
0x180008003  mov     [rax+8], r8d
0x180008007  xor     r8d, r8d; ActivityId
0x18000800a  mov     [rsp+38h+UserData], rax; UserData
0x18000800f  mov     [rax+0Ch], r10d
0x180008013  mov     rcx, [rcx]; RegHandle
0x180008016  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000801b  xor     r9d, r9d; RelatedActivityId
0x18000801e  call    cs:__imp_EventWriteTransfer
0x180008024  add     rsp, 38h
0x180008028  retn
```
