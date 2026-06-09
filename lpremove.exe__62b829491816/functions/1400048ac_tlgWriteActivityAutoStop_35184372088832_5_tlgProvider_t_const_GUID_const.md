# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1400048ac`
- end: `0x14000491e`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004e04`

## callees

- `0x140001b9c`
- `0x140002190`
- `0x1400048ac`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<35184372088832,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rdx
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    v4 = *((_QWORD *)a1 + 3);
    result = *((_QWORD *)a1 + 2);
    if ( (result & 0x200000000000LL) != 0 )
    {
      result = v4 & 0x200000000000LL;
      if ( (v4 & 0x200000000000LL) == v4 )
        return tlgWriteTransfer_EventWriteTransfer(a1, byte_1400140A1, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400048ac  sub     rsp, 68h
0x1400048b0  mov     rax, cs:__security_cookie
0x1400048b7  xor     rax, rsp
0x1400048ba  mov     [rsp+68h+var_18], rax
0x1400048bf  mov     eax, [rcx]
0x1400048c1  mov     r8, rdx
0x1400048c4  cmp     eax, 5
0x1400048c7  jbe     short loc_14000490C
0x1400048c9  mov     rdx, [rcx+18h]
0x1400048cd  mov     r9, 200000000000h
0x1400048d7  mov     rax, [rcx+10h]
0x1400048db  test    r9, rax
0x1400048de  jz      short loc_14000490C
0x1400048e0  mov     rax, rdx
0x1400048e3  and     rax, r9
0x1400048e6  cmp     rax, rdx
0x1400048e9  jnz     short loc_14000490C
0x1400048eb  lea     rax, [rsp+68h+var_38]
0x1400048f0  xor     r9d, r9d
0x1400048f3  mov     [rsp+68h+var_40], rax
0x1400048f8  lea     rdx, byte_1400140A1
0x1400048ff  mov     [rsp+68h+var_48], 2
0x140004907  call    _tlgWriteTransfer_EventWriteTransfer
0x14000490c  mov     rcx, [rsp+68h+var_18]
0x140004911  xor     rcx, rsp; StackCookie
0x140004914  call    __security_check_cookie
0x140004919  add     rsp, 68h
0x14000491d  retn
```
