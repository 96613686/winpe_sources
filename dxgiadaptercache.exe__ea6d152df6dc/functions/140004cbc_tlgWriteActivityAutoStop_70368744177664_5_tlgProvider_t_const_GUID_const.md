# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x140004cbc`
- end: `0x140004d2e`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005fc4`

## callees

- `0x140001bac`
- `0x1400022a0`
- `0x140004cbc`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rdx
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    v4 = *((_QWORD *)a1 + 3);
    result = *((_QWORD *)a1 + 2);
    if ( (result & 0x400000000000LL) != 0 )
    {
      result = v4 & 0x400000000000LL;
      if ( (v4 & 0x400000000000LL) == v4 )
        return tlgWriteTransfer_EventWriteTransfer(a1, &dword_14001580C, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140004cbc  sub     rsp, 68h
0x140004cc0  mov     rax, cs:__security_cookie
0x140004cc7  xor     rax, rsp
0x140004cca  mov     [rsp+68h+var_18], rax
0x140004ccf  mov     eax, [rcx]
0x140004cd1  mov     r8, rdx
0x140004cd4  cmp     eax, 5
0x140004cd7  jbe     short loc_140004D1C
0x140004cd9  mov     rdx, [rcx+18h]
0x140004cdd  mov     r9, 400000000000h
0x140004ce7  mov     rax, [rcx+10h]
0x140004ceb  test    r9, rax
0x140004cee  jz      short loc_140004D1C
0x140004cf0  mov     rax, rdx
0x140004cf3  and     rax, r9
0x140004cf6  cmp     rax, rdx
0x140004cf9  jnz     short loc_140004D1C
0x140004cfb  lea     rax, [rsp+68h+var_38]
0x140004d00  xor     r9d, r9d
0x140004d03  mov     [rsp+68h+var_40], rax
0x140004d08  lea     rdx, dword_14001580C
0x140004d0f  mov     [rsp+68h+var_48], 2
0x140004d17  call    _tlgWriteTransfer_EventWriteTransfer
0x140004d1c  mov     rcx, [rsp+68h+var_18]
0x140004d21  xor     rcx, rsp; StackCookie
0x140004d24  call    __security_check_cookie
0x140004d29  add     rsp, 68h
0x140004d2d  retn
```
