# McGenEventWrite_EventWriteTransfer

- ea: `0x180014514`
- end: `0x180014568`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fc34`
- `0x180014570`
- `0x1800145f4`
- `0x180014698`
- `0x18001473c`
- `0x1800148f0`
- `0x180015bb0`
- `0x180016c50`
- `0x1800174d0`
- `0x180018480`
- `0x180018cf0`
- `0x180018ea0`
- `0x180019060`
- `0x180019250`
- `0x180019410`
- `0x18001a3f0`
- `0x18001a6a0`
- `0x18001a7d0`
- `0x18001a940`
- `0x180021cb8`
- `0x18002206c`

## callees

- `0x180014514`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014556`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014556`

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
0x180014514  sub     rsp, 38h
0x180014518  mov     r8, [rcx+8]
0x18001451c  mov     rax, [rsp+38h+arg_20]
0x180014521  test    r8, r8
0x180014524  jnz     short loc_18001452E
0x180014526  mov     [rax], r8
0x180014529  xor     r10d, r10d
0x18001452c  jmp     short loc_18001453B
0x18001452e  mov     [rax], r8
0x180014531  mov     r10d, 2
0x180014537  movzx   r8d, word ptr [r8]
0x18001453b  mov     [rax+8], r8d
0x18001453f  xor     r8d, r8d; ActivityId
0x180014542  mov     [rsp+38h+UserData], rax; UserData
0x180014547  mov     [rax+0Ch], r10d
0x18001454b  mov     rcx, [rcx]; RegHandle
0x18001454e  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180014553  xor     r9d, r9d; RelatedActivityId
0x180014556  call    cs:__imp_EventWriteTransfer
0x18001455d  nop     dword ptr [rax+rax+00h]
0x180014562  add     rsp, 38h
0x180014566  retn
```
