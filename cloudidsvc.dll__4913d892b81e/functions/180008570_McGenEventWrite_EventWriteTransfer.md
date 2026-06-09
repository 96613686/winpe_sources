# McGenEventWrite_EventWriteTransfer

- ea: `0x180008570`
- end: `0x1800085c2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006e94`
- `0x18000b1d0`
- `0x18000ba60`
- `0x18000ce9c`
- `0x18000ed90`
- `0x18000ff78`

## callees

- `0x180008570`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800085b7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800085b7`

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

  v5 = (unsigned __int16 *)qword_180019008;
  if ( qword_180019008 )
  {
    UserData->Ptr = qword_180019008;
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
  return EventWriteTransfer(Microsoft_Windows_TenantRestrictions_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180008570  sub     rsp, 38h
0x180008574  mov     rcx, cs:qword_180019008
0x18000857b  mov     rax, [rsp+38h+arg_20]
0x180008580  test    rcx, rcx
0x180008583  jnz     short loc_18000858D
0x180008585  mov     [rax], rcx
0x180008588  xor     r8d, r8d
0x18000858b  jmp     short loc_180008599
0x18000858d  mov     [rax], rcx
0x180008590  mov     r8d, 2
0x180008596  movzx   ecx, word ptr [rcx]
0x180008599  mov     [rax+8], ecx
0x18000859c  mov     [rax+0Ch], r8d
0x1800085a0  xor     r8d, r8d; ActivityId
0x1800085a3  mov     rcx, cs:Microsoft_Windows_TenantRestrictions_Context; RegHandle
0x1800085aa  mov     [rsp+38h+UserData], rax; UserData
0x1800085af  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800085b4  xor     r9d, r9d; RelatedActivityId
0x1800085b7  call    cs:__imp_EventWriteTransfer
0x1800085bd  add     rsp, 38h
0x1800085c1  retn
```
