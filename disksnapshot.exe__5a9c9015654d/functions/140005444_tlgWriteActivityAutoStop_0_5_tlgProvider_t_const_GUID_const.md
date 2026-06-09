# _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x140005444`
- end: `0x140005494`
- name: `??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400055a8`
- `0x140007c84`

## callees

- `0x1400011bc`
- `0x140001c50`
- `0x140005444`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<0,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  _BYTE v3[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
    return tlgWriteTransfer_EventWriteTransfer(a1, qword_140010750, a2, 0, 2, v3);
  return result;
}

```

## disassembly

```asm
0x140005444  sub     rsp, 68h
0x140005448  mov     rax, cs:__security_cookie
0x14000544f  xor     rax, rsp
0x140005452  mov     [rsp+68h+var_18], rax
0x140005457  mov     eax, [rcx]
0x140005459  cmp     eax, 5
0x14000545c  jbe     short loc_140005482
0x14000545e  lea     rax, [rsp+68h+var_38]
0x140005463  mov     r8, rdx
0x140005466  mov     [rsp+68h+var_40], rax
0x14000546b  lea     rdx, qword_140010750
0x140005472  xor     r9d, r9d
0x140005475  mov     [rsp+68h+var_48], 2
0x14000547d  call    _tlgWriteTransfer_EventWriteTransfer
0x140005482  mov     rcx, [rsp+68h+var_18]
0x140005487  xor     rcx, rsp; StackCookie
0x14000548a  call    __security_check_cookie
0x14000548f  add     rsp, 68h
0x140005493  retn
```
