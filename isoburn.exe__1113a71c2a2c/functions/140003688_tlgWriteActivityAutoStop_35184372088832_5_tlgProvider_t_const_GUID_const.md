# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x140003688`
- end: `0x1400036fa`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140003798`

## callees

- `0x1400018dc`
- `0x140001fa0`
- `0x140003688`

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
        LODWORD(v2) = tlgWriteTransfer_EventWriteTransfer(a1, (unsigned __int8 *)byte_140013151, a2, 0, 2u, &v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140003688  sub     rsp, 68h
0x14000368c  mov     rax, cs:__security_cookie
0x140003693  xor     rax, rsp
0x140003696  mov     [rsp+68h+var_18], rax
0x14000369b  mov     eax, [rcx]
0x14000369d  mov     r8, rdx
0x1400036a0  cmp     eax, 5
0x1400036a3  jbe     short loc_1400036E8
0x1400036a5  mov     rdx, [rcx+18h]
0x1400036a9  mov     r9, 200000000000h
0x1400036b3  mov     rax, [rcx+10h]
0x1400036b7  test    r9, rax
0x1400036ba  jz      short loc_1400036E8
0x1400036bc  mov     rax, rdx
0x1400036bf  and     rax, r9
0x1400036c2  cmp     rax, rdx
0x1400036c5  jnz     short loc_1400036E8
0x1400036c7  lea     rax, [rsp+68h+var_38]
0x1400036cc  xor     r9d, r9d
0x1400036cf  mov     [rsp+68h+var_40], rax
0x1400036d4  lea     rdx, byte_140013151
0x1400036db  mov     [rsp+68h+var_48], 2
0x1400036e3  call    _tlgWriteTransfer_EventWriteTransfer
0x1400036e8  mov     rcx, [rsp+68h+var_18]
0x1400036ed  xor     rcx, rsp; StackCookie
0x1400036f0  call    __security_check_cookie
0x1400036f5  add     rsp, 68h
0x1400036f9  retn
```
