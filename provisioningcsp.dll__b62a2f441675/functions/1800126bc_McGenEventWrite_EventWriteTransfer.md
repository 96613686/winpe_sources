# McGenEventWrite_EventWriteTransfer

- ea: `0x1800126bc`
- end: `0x180012715`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800118a0`
- `0x180031afc`

## callees

- `0x1800126bc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012703`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012703`

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

  v5 = (unsigned __int16 *)qword_180049628;
  if ( qword_180049628 )
  {
    UserData->Ptr = qword_180049628;
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
0x1800126bc  sub     rsp, 38h
0x1800126c0  mov     rcx, cs:qword_180049628
0x1800126c7  mov     rax, [rsp+38h+arg_20]
0x1800126cc  test    rcx, rcx
0x1800126cf  jnz     short loc_1800126D9
0x1800126d1  mov     [rax], rcx
0x1800126d4  xor     r8d, r8d
0x1800126d7  jmp     short loc_1800126E5
0x1800126d9  mov     [rax], rcx
0x1800126dc  mov     r8d, 2
0x1800126e2  movzx   ecx, word ptr [rcx]
0x1800126e5  mov     [rax+8], ecx
0x1800126e8  mov     [rax+0Ch], r8d
0x1800126ec  xor     r8d, r8d; ActivityId
0x1800126ef  mov     rcx, cs:PROVISIONING_DIAGNOSTICS_Context; RegHandle
0x1800126f6  mov     [rsp+38h+UserData], rax; UserData
0x1800126fb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180012700  xor     r9d, r9d; RelatedActivityId
0x180012703  call    cs:__imp_EventWriteTransfer
0x18001270a  nop     dword ptr [rax+rax+00h]
0x18001270f  add     rsp, 38h
0x180012713  retn
```
