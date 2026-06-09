# McGenEventWrite_EventWriteTransfer

- ea: `0x1800097fc`
- end: `0x180009849`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180007890`
- `0x1800083ec`
- `0x180008940`
- `0x18000c740`
- `0x18000ca90`
- `0x18000cb50`
- `0x180011ccc`
- `0x180011d5c`
- `0x18001a5c8`
- `0x18001c054`
- `0x18001c61c`
- `0x18001d2a4`
- `0x18001de38`
- `0x18001dfa0`
- `0x18001e08c`
- `0x18001e178`

## callees

- `0x1800097fc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000983e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000983e`

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
0x1800097fc  sub     rsp, 38h
0x180009800  mov     r8, [rcx+8]
0x180009804  mov     rax, [rsp+38h+arg_20]
0x180009809  test    r8, r8
0x18000980c  jnz     short loc_180009816
0x18000980e  mov     [rax], r8
0x180009811  xor     r10d, r10d
0x180009814  jmp     short loc_180009823
0x180009816  mov     [rax], r8
0x180009819  mov     r10d, 2
0x18000981f  movzx   r8d, word ptr [r8]
0x180009823  mov     [rax+8], r8d
0x180009827  xor     r8d, r8d; ActivityId
0x18000982a  mov     [rsp+38h+UserData], rax; UserData
0x18000982f  mov     [rax+0Ch], r10d
0x180009833  mov     rcx, [rcx]; RegHandle
0x180009836  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000983b  xor     r9d, r9d; RelatedActivityId
0x18000983e  call    cs:__imp_EventWriteTransfer
0x180009844  add     rsp, 38h
0x180009848  retn
```
