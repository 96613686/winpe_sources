# McGenEventWrite_EventWriteTransfer

- ea: `0x18001a62c`
- end: `0x18001a67e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001964c`
- `0x180019b50`
- `0x18001a684`
- `0x18001a6dc`
- `0x18001a75c`
- `0x18001a7fc`
- `0x18001a8b4`

## callees

- `0x18001a62c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a673`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a673`

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

  v5 = (unsigned __int16 *)qword_180033888;
  if ( qword_180033888 )
  {
    UserData->Ptr = qword_180033888;
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
  return EventWriteTransfer(Microsoft_Windows_XPerfCore_ETWProvider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18001a62c  sub     rsp, 38h
0x18001a630  mov     rcx, cs:qword_180033888
0x18001a637  mov     rax, [rsp+38h+arg_20]
0x18001a63c  test    rcx, rcx
0x18001a63f  jnz     short loc_18001A649
0x18001a641  mov     [rax], rcx
0x18001a644  xor     r8d, r8d
0x18001a647  jmp     short loc_18001A655
0x18001a649  mov     [rax], rcx
0x18001a64c  mov     r8d, 2
0x18001a652  movzx   ecx, word ptr [rcx]
0x18001a655  mov     [rax+8], ecx
0x18001a658  mov     [rax+0Ch], r8d
0x18001a65c  xor     r8d, r8d; ActivityId
0x18001a65f  mov     rcx, cs:Microsoft_Windows_XPerfCore_ETWProvider_Context; RegHandle
0x18001a666  mov     [rsp+38h+UserData], rax; UserData
0x18001a66b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001a670  xor     r9d, r9d; RelatedActivityId
0x18001a673  call    cs:__imp_EventWriteTransfer
0x18001a679  add     rsp, 38h
0x18001a67d  retn
```
