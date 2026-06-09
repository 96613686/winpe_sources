# McGenEventWrite_EventWriteTransfer

- ea: `0x140016058`
- end: `0x1400160aa`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400160b0`
- `0x14001614c`
- `0x140016418`
- `0x1400166a4`
- `0x140016778`
- `0x1400168a4`
- `0x1400169d0`
- `0x140016b80`
- `0x140016c54`

## callees

- `0x140016058`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14001609f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14001609f`

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

  v5 = (unsigned __int16 *)qword_140021008;
  if ( qword_140021008 )
  {
    UserData->Ptr = qword_140021008;
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
  return EventWriteTransfer(Microsoft_Windows_Cleanmgr_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140016058  sub     rsp, 38h
0x14001605c  mov     rcx, cs:qword_140021008
0x140016063  mov     rax, [rsp+38h+arg_20]
0x140016068  test    rcx, rcx
0x14001606b  jnz     short loc_140016075
0x14001606d  mov     [rax], rcx
0x140016070  xor     r8d, r8d
0x140016073  jmp     short loc_140016081
0x140016075  mov     [rax], rcx
0x140016078  mov     r8d, 2
0x14001607e  movzx   ecx, word ptr [rcx]
0x140016081  mov     [rax+8], ecx
0x140016084  mov     [rax+0Ch], r8d
0x140016088  xor     r8d, r8d; ActivityId
0x14001608b  mov     rcx, cs:Microsoft_Windows_Cleanmgr_Context; RegHandle
0x140016092  mov     [rsp+38h+UserData], rax; UserData
0x140016097  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14001609c  xor     r9d, r9d; RelatedActivityId
0x14001609f  call    cs:__imp_EventWriteTransfer
0x1400160a5  add     rsp, 38h
0x1400160a9  retn
```
