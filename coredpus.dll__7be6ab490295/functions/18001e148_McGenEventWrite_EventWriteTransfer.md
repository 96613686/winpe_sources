# McGenEventWrite_EventWriteTransfer

- ea: `0x18001e148`
- end: `0x18001e19f`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `87`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e1a8`
- `0x18002b33c`

## callees

- `0x18001e148`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e18d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e18d`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
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
  return EventWriteTransfer(*a1, a2, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x18001e148  sub     rsp, 38h
0x18001e14c  mov     r8, [rcx+8]
0x18001e150  mov     r10d, 2
0x18001e156  mov     rax, [rsp+38h+arg_20]
0x18001e15b  test    r8, r8
0x18001e15e  jnz     short loc_18001E168
0x18001e160  mov     [rax], r8
0x18001e163  xor     r9d, r9d
0x18001e166  jmp     short loc_18001E172
0x18001e168  mov     [rax], r8
0x18001e16b  mov     r9d, r10d
0x18001e16e  movzx   r8d, word ptr [r8]
0x18001e172  mov     [rax+8], r8d
0x18001e176  xor     r8d, r8d; ActivityId
0x18001e179  mov     [rax+0Ch], r9d
0x18001e17d  xor     r9d, r9d; RelatedActivityId
0x18001e180  mov     rcx, [rcx]; RegHandle
0x18001e183  mov     [rsp+38h+UserData], rax; UserData
0x18001e188  mov     [rsp+38h+UserDataCount], r10d; UserDataCount
0x18001e18d  call    cs:__imp_EventWriteTransfer
0x18001e194  nop     dword ptr [rax+rax+00h]
0x18001e199  add     rsp, 38h
0x18001e19d  retn
```
