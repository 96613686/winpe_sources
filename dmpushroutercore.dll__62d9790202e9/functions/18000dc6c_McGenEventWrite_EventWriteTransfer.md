# McGenEventWrite_EventWriteTransfer

- ea: `0x18000dc6c`
- end: `0x18000dcb9`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `39`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a400`
- `0x18000dcc0`
- `0x18000e0a0`
- `0x18000e620`
- `0x18000e710`
- `0x18000e860`
- `0x18000f694`
- `0x18000fac0`
- `0x180010290`
- `0x180010320`
- `0x1800103f8`
- `0x1800105a0`
- `0x1800107b0`
- `0x180011690`
- `0x180013f64`
- `0x180015500`
- `0x180016110`
- `0x180016c04`
- `0x180017700`
- `0x180017788`
- `0x180017838`
- `0x180017928`
- `0x180018d14`
- `0x18001946c`
- `0x1800195c8`
- `0x18001b0f8`
- `0x18001ba3c`
- `0x18001cdb8`
- `0x1800229f0`
- `0x180023ce0`
- `0x180023d64`
- `0x180024754`
- `0x1800248c4`
- `0x1800249b4`
- `0x180024aa4`
- `0x180024cbc`
- `0x180024dac`
- `0x180024e9c`
- `0x180024f8c`

## callees

- `0x18000dc6c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000dcae`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000dcae`

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
0x18000dc6c  sub     rsp, 38h
0x18000dc70  mov     r8, [rcx+8]
0x18000dc74  mov     rax, [rsp+38h+arg_20]
0x18000dc79  test    r8, r8
0x18000dc7c  jnz     short loc_18000DC86
0x18000dc7e  mov     [rax], r8
0x18000dc81  xor     r10d, r10d
0x18000dc84  jmp     short loc_18000DC93
0x18000dc86  mov     [rax], r8
0x18000dc89  mov     r10d, 2
0x18000dc8f  movzx   r8d, word ptr [r8]
0x18000dc93  mov     [rax+8], r8d
0x18000dc97  xor     r8d, r8d; ActivityId
0x18000dc9a  mov     [rsp+38h+UserData], rax; UserData
0x18000dc9f  mov     [rax+0Ch], r10d
0x18000dca3  mov     rcx, [rcx]; RegHandle
0x18000dca6  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000dcab  xor     r9d, r9d; RelatedActivityId
0x18000dcae  call    cs:__imp_EventWriteTransfer
0x18000dcb4  add     rsp, 38h
0x18000dcb8  retn
```
