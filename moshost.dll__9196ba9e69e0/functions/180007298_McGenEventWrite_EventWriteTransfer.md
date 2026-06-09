# McGenEventWrite_EventWriteTransfer

- ea: `0x180007298`
- end: `0x1800072ea`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007550`
- `0x180007930`
- `0x1800079e0`
- `0x180008690`
- `0x18000af38`
- `0x18000b30c`
- `0x18000b38c`

## callees

- `0x180007298`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800072df`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800072df`

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

  v5 = (unsigned __int16 *)qword_180018048;
  if ( qword_180018048 )
  {
    UserData->Ptr = qword_180018048;
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
  return EventWriteTransfer(MICROSOFT_WINDOWS_MOSHOST_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180007298  sub     rsp, 38h
0x18000729c  mov     rcx, cs:qword_180018048
0x1800072a3  mov     rax, [rsp+38h+arg_20]
0x1800072a8  test    rcx, rcx
0x1800072ab  jnz     short loc_1800072B5
0x1800072ad  mov     [rax], rcx
0x1800072b0  xor     r8d, r8d
0x1800072b3  jmp     short loc_1800072C1
0x1800072b5  mov     [rax], rcx
0x1800072b8  mov     r8d, 2
0x1800072be  movzx   ecx, word ptr [rcx]
0x1800072c1  mov     [rax+8], ecx
0x1800072c4  mov     [rax+0Ch], r8d
0x1800072c8  xor     r8d, r8d; ActivityId
0x1800072cb  mov     rcx, cs:MICROSOFT_WINDOWS_MOSHOST_Context; RegHandle
0x1800072d2  mov     [rsp+38h+UserData], rax; UserData
0x1800072d7  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800072dc  xor     r9d, r9d; RelatedActivityId
0x1800072df  call    cs:__imp_EventWriteTransfer
0x1800072e5  add     rsp, 38h
0x1800072e9  retn
```
