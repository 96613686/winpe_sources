# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x140003210`
- end: `0x140003282`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003900`
- `0x1400059ac`

## callees

- `0x140001130`
- `0x140003210`
- `0x14000ded0`

## pseudocode

```c
int __fastcall _tlgWriteActivityAutoStop<35184372088832,5>(__int64 a1, const GUID *a2)
{
  __int64 v2; // rax
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF

  LODWORD(v2) = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 > 5u )
  {
    v2 = *(_QWORD *)(a1 + 16);
    if ( (v2 & 0x200000000000LL) != 0 )
    {
      LODWORD(v2) = 0;
      if ( (*(_QWORD *)(a1 + 24) & 0x200000000000LL) == *(_QWORD *)(a1 + 24) )
        LODWORD(v2) = tlgWriteTransfer_EventWriteTransfer(a1, (unsigned __int8 *)&word_1400133E6, a2, 0, 2u, &v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140003210  sub     rsp, 68h
0x140003214  mov     rax, cs:__security_cookie
0x14000321b  xor     rax, rsp
0x14000321e  mov     [rsp+68h+var_18], rax
0x140003223  mov     eax, [rcx]
0x140003225  mov     r8, rdx
0x140003228  cmp     eax, 5
0x14000322b  jbe     short loc_140003270
0x14000322d  mov     rdx, [rcx+18h]
0x140003231  mov     r9, 200000000000h
0x14000323b  mov     rax, [rcx+10h]
0x14000323f  test    r9, rax
0x140003242  jz      short loc_140003270
0x140003244  mov     rax, rdx
0x140003247  and     rax, r9
0x14000324a  cmp     rax, rdx
0x14000324d  jnz     short loc_140003270
0x14000324f  lea     rax, [rsp+68h+var_38]
0x140003254  xor     r9d, r9d
0x140003257  mov     [rsp+68h+var_40], rax
0x14000325c  lea     rdx, word_1400133E6
0x140003263  mov     [rsp+68h+var_48], 2
0x14000326b  call    _tlgWriteTransfer_EventWriteTransfer
0x140003270  mov     rcx, [rsp+68h+var_18]
0x140003275  xor     rcx, rsp; StackCookie
0x140003278  call    __security_check_cookie
0x14000327d  add     rsp, 68h
0x140003281  retn
```
