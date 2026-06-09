# McGenEventWrite_EventWriteTransfer

- ea: `0x1800143bc`
- end: `0x180014409`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x180013dfc`
- `0x180014410`
- `0x180014a50`
- `0x180014c38`
- `0x180014f20`
- `0x180015308`
- `0x180015440`
- `0x180015a60`
- `0x180016254`
- `0x180016314`
- `0x1800163ec`
- `0x18002d2e0`
- `0x18002d378`
- `0x18002ddd4`
- `0x18002e130`
- `0x18002e300`
- `0x18002e940`
- `0x18002ec40`
- `0x18002f940`
- `0x180031488`
- `0x180031534`
- `0x1800315f4`
- `0x180031910`
- `0x180054ca8`

## callees

- `0x1800143bc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800143fe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800143fe`

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
0x1800143bc  sub     rsp, 38h
0x1800143c0  mov     r8, [rcx+8]
0x1800143c4  mov     rax, [rsp+38h+arg_20]
0x1800143c9  test    r8, r8
0x1800143cc  jnz     short loc_1800143D6
0x1800143ce  mov     [rax], r8
0x1800143d1  xor     r10d, r10d
0x1800143d4  jmp     short loc_1800143E3
0x1800143d6  mov     [rax], r8
0x1800143d9  mov     r10d, 2
0x1800143df  movzx   r8d, word ptr [r8]
0x1800143e3  mov     [rax+8], r8d
0x1800143e7  xor     r8d, r8d; ActivityId
0x1800143ea  mov     [rsp+38h+UserData], rax; UserData
0x1800143ef  mov     [rax+0Ch], r10d
0x1800143f3  mov     rcx, [rcx]; RegHandle
0x1800143f6  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800143fb  xor     r9d, r9d; RelatedActivityId
0x1800143fe  call    cs:__imp_EventWriteTransfer
0x180014404  add     rsp, 38h
0x180014408  retn
```
