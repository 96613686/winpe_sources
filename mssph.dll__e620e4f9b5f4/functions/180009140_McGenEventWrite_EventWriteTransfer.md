# McGenEventWrite_EventWriteTransfer

- ea: `0x180009140`
- end: `0x18000918d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e30`
- `0x1800090b0`

## callees

- `0x180009140`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009173`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009173`

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
0x180009140  sub     rsp, 38h
0x180009144  mov     r8, [rcx+8]
0x180009148  mov     rax, [rsp+38h+arg_20]
0x18000914d  test    r8, r8
0x180009150  jnz     short loc_18000917E
0x180009152  mov     [rax], r8
0x180009155  xor     r10d, r10d
0x180009158  mov     [rax+8], r8d
0x18000915c  xor     r8d, r8d; ActivityId
0x18000915f  mov     [rsp+38h+UserData], rax; UserData
0x180009164  mov     [rax+0Ch], r10d
0x180009168  mov     rcx, [rcx]; RegHandle
0x18000916b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180009170  xor     r9d, r9d; RelatedActivityId
0x180009173  call    cs:__imp_EventWriteTransfer
0x180009179  add     rsp, 38h
0x18000917d  retn
0x18000917e  mov     [rax], r8
0x180009181  mov     r10d, 2
0x180009187  movzx   r8d, word ptr [r8]
0x18000918b  jmp     short loc_180009158
```
