# McGenEventWrite_EventWriteTransfer

- ea: `0x180001a78`
- end: `0x180001aca`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c4c`
- `0x180001da8`

## callees

- `0x180001a78`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001abf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001abf`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180011008;
  if ( qword_180011008 )
  {
    UserData->Ptr = qword_180011008;
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
  return EventWriteTransfer(userpnp_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180001a78  sub     rsp, 38h
0x180001a7c  mov     rcx, cs:qword_180011008
0x180001a83  mov     rax, [rsp+38h+arg_20]
0x180001a88  test    rcx, rcx
0x180001a8b  jnz     short loc_180001A95
0x180001a8d  mov     [rax], rcx
0x180001a90  xor     r8d, r8d
0x180001a93  jmp     short loc_180001AA1
0x180001a95  mov     [rax], rcx
0x180001a98  mov     r8d, 2
0x180001a9e  movzx   ecx, word ptr [rcx]
0x180001aa1  mov     [rax+8], ecx
0x180001aa4  mov     [rax+0Ch], r8d
0x180001aa8  xor     r8d, r8d; ActivityId
0x180001aab  mov     rcx, cs:userpnp_Context; RegHandle
0x180001ab2  mov     [rsp+38h+UserData], rax; UserData
0x180001ab7  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180001abc  xor     r9d, r9d; RelatedActivityId
0x180001abf  call    cs:__imp_EventWriteTransfer
0x180001ac5  add     rsp, 38h
0x180001ac9  retn
```
