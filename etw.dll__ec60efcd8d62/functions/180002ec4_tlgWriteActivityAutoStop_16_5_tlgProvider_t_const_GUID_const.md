# _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180002ec4`
- end: `0x180002f2b`
- name: `??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `103`
- prototype: ``
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x18000390c`
- `0x180006520`
- `0x180006740`
- `0x180006970`
- `0x180006c60`
- `0x180007060`
- `0x180007cc0`
- `0x1800080f0`
- `0x180008330`
- `0x1800099c0`
- `0x18000a300`
- `0x18000ad70`
- `0x18000b5f0`
- `0x18000b970`
- `0x18000bbe0`
- `0x18000bf60`
- `0x18000c4a0`
- `0x18000cca0`

## callees

- `0x180001008`
- `0x180001560`
- `0x180002ec4`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<16,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  _BYTE v3[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    result = *((_QWORD *)a1 + 2);
    if ( (result & 0x10) != 0 )
    {
      result = *((_QWORD *)a1 + 3) & 0x10LL;
      if ( result == *((_QWORD *)a1 + 3) )
        return tlgWriteTransfer_EtwEventWriteTransfer(
                 (__int64)a1,
                 (unsigned __int8 *)byte_1800187E1,
                 a2,
                 0,
                 2,
                 (__int64)v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002ec4  sub     rsp, 68h
0x180002ec8  mov     rax, cs:__security_cookie
0x180002ecf  xor     rax, rsp
0x180002ed2  mov     [rsp+68h+var_18], rax
0x180002ed7  mov     eax, [rcx]
0x180002ed9  mov     r8, rdx
0x180002edc  cmp     eax, 5
0x180002edf  jbe     short loc_180002F19
0x180002ee1  mov     rdx, [rcx+18h]
0x180002ee5  mov     rax, [rcx+10h]
0x180002ee9  test    al, 10h
0x180002eeb  jz      short loc_180002F19
0x180002eed  mov     rax, rdx
0x180002ef0  and     eax, 10h
0x180002ef3  cmp     rax, rdx
0x180002ef6  jnz     short loc_180002F19
0x180002ef8  lea     rax, [rsp+68h+var_38]
0x180002efd  xor     r9d, r9d
0x180002f00  mov     [rsp+68h+var_40], rax
0x180002f05  lea     rdx, byte_1800187E1
0x180002f0c  mov     [rsp+68h+var_48], 2
0x180002f14  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180002f19  mov     rcx, [rsp+68h+var_18]
0x180002f1e  xor     rcx, rsp; StackCookie
0x180002f21  call    __security_check_cookie
0x180002f26  add     rsp, 68h
0x180002f2a  retn
```
