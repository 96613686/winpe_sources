# _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180003698`
- end: `0x1800036e8`
- name: `??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800039fc`

## callees

- `0x180001f18`
- `0x180003698`
- `0x18001ac90`

## pseudocode

```c
ULONG __fastcall _tlgWriteActivityAutoStop<0,5>(ULONG *a1, const GUID *a2)
{
  ULONG result; // eax
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( *a1 > 5 )
    return tlgWriteTransfer_EventWriteTransfer((__int64)a1, (unsigned __int8 *)&byte_18001E347, a2, 0, 2u, &v3);
  return result;
}

```

## disassembly

```asm
0x180003698  sub     rsp, 68h
0x18000369c  mov     rax, cs:__security_cookie
0x1800036a3  xor     rax, rsp
0x1800036a6  mov     [rsp+68h+var_18], rax
0x1800036ab  mov     eax, [rcx]
0x1800036ad  cmp     eax, 5
0x1800036b0  jbe     short loc_1800036D6
0x1800036b2  lea     rax, [rsp+68h+var_38]
0x1800036b7  mov     r8, rdx
0x1800036ba  mov     [rsp+68h+var_40], rax
0x1800036bf  lea     rdx, byte_18001E347
0x1800036c6  xor     r9d, r9d
0x1800036c9  mov     [rsp+68h+var_48], 2
0x1800036d1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800036d6  mov     rcx, [rsp+68h+var_18]
0x1800036db  xor     rcx, rsp; StackCookie
0x1800036de  call    __security_check_cookie
0x1800036e3  add     rsp, 68h
0x1800036e7  retn
```
