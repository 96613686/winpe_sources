# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000f838`
- end: `0x18000f8a1`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fa08`

## callees

- `0x180001f3c`
- `0x180001f68`
- `0x180002620`
- `0x18000f838`

## pseudocode

```c
ULONG __fastcall _tlgWriteActivityAutoStop<35184372088832,5>(ULONG *a1)
{
  ULONG result; // eax
  const GUID *v2; // r8
  __int64 v3; // r10
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( *a1 > 5 )
  {
    result = tlgKeywordOn(a1, 0x200000000000LL);
    if ( (_BYTE)result )
      return tlgWriteTransfer_EventWriteTransfer(v3, (unsigned __int8 *)&byte_1800160E9, v2, 0, 2u, &v4);
  }
  return result;
}

```

## disassembly

```asm
0x18000f838  sub     rsp, 68h
0x18000f83c  mov     rax, cs:__security_cookie
0x18000f843  xor     rax, rsp
0x18000f846  mov     [rsp+68h+var_18], rax
0x18000f84b  mov     eax, [rcx]
0x18000f84d  mov     r8, rdx
0x18000f850  mov     r10, rcx
0x18000f853  cmp     eax, 5
0x18000f856  jbe     short loc_18000F88F
0x18000f858  mov     rdx, 200000000000h
0x18000f862  call    _tlgKeywordOn
0x18000f867  test    al, al
0x18000f869  jz      short loc_18000F88F
0x18000f86b  lea     rax, [rsp+68h+var_38]
0x18000f870  xor     r9d, r9d; int
0x18000f873  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x18000f878  lea     rdx, byte_1800160E9; int
0x18000f87f  mov     rcx, r10; int
0x18000f882  mov     [rsp+68h+var_48], 2; ULONG
0x18000f88a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000f88f  mov     rcx, [rsp+68h+var_18]
0x18000f894  xor     rcx, rsp; StackCookie
0x18000f897  call    __security_check_cookie
0x18000f89c  add     rsp, 68h
0x18000f8a0  retn
```
