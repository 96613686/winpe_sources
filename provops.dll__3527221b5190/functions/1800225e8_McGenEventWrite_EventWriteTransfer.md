# McGenEventWrite_EventWriteTransfer

- ea: `0x1800225e8`
- end: `0x18002263a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d498`
- `0x18000d604`
- `0x18000f8d0`
- `0x180010b40`
- `0x180011b88`
- `0x180022640`
- `0x1800226dc`
- `0x180022784`
- `0x180034b86`
- `0x180034d20`

## callees

- `0x1800225e8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002262f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002262f`

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

  v5 = (unsigned __int16 *)qword_18004A048;
  if ( qword_18004A048 )
  {
    UserData->Ptr = qword_18004A048;
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
  return EventWriteTransfer(PROVISIONING_DIAGNOSTICS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800225e8  sub     rsp, 38h
0x1800225ec  mov     rcx, cs:qword_18004A048
0x1800225f3  mov     rax, [rsp+38h+arg_20]
0x1800225f8  test    rcx, rcx
0x1800225fb  jnz     short loc_180022605
0x1800225fd  mov     [rax], rcx
0x180022600  xor     r8d, r8d
0x180022603  jmp     short loc_180022611
0x180022605  mov     [rax], rcx
0x180022608  mov     r8d, 2
0x18002260e  movzx   ecx, word ptr [rcx]
0x180022611  mov     [rax+8], ecx
0x180022614  mov     [rax+0Ch], r8d
0x180022618  xor     r8d, r8d; ActivityId
0x18002261b  mov     rcx, cs:PROVISIONING_DIAGNOSTICS_Context; RegHandle
0x180022622  mov     [rsp+38h+UserData], rax; UserData
0x180022627  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18002262c  xor     r9d, r9d; RelatedActivityId
0x18002262f  call    cs:__imp_EventWriteTransfer
0x180022635  add     rsp, 38h
0x180022639  retn
```
