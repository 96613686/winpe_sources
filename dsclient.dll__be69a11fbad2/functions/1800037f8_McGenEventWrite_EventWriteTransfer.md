# McGenEventWrite_EventWriteTransfer

- ea: `0x1800037f8`
- end: `0x180003845`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000384c`
- `0x1800038d4`
- `0x1800097dc`

## callees

- `0x1800037f8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000383a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000383a`

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
0x1800037f8  sub     rsp, 38h
0x1800037fc  mov     r8, [rcx+8]
0x180003800  mov     rax, [rsp+38h+arg_20]
0x180003805  test    r8, r8
0x180003808  jnz     short loc_180003812
0x18000380a  mov     [rax], r8
0x18000380d  xor     r10d, r10d
0x180003810  jmp     short loc_18000381F
0x180003812  mov     [rax], r8
0x180003815  mov     r10d, 2
0x18000381b  movzx   r8d, word ptr [r8]
0x18000381f  mov     [rax+8], r8d
0x180003823  xor     r8d, r8d; ActivityId
0x180003826  mov     [rsp+38h+UserData], rax; UserData
0x18000382b  mov     [rax+0Ch], r10d
0x18000382f  mov     rcx, [rcx]; RegHandle
0x180003832  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180003837  xor     r9d, r9d; RelatedActivityId
0x18000383a  call    cs:__imp_EventWriteTransfer
0x180003840  add     rsp, 38h
0x180003844  retn
```
