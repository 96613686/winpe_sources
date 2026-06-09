# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180004f6c`
- end: `0x180004fde`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800052b8`

## callees

- `0x1800018dc`
- `0x180001ef0`
- `0x180004f6c`

## pseudocode

```c
int __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(__int64 a1, const GUID *a2)
{
  __int64 v2; // rax
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF

  LODWORD(v2) = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 > 5u )
  {
    v2 = *(_QWORD *)(a1 + 16);
    if ( (v2 & 0x400000000000LL) != 0 )
    {
      LODWORD(v2) = 0;
      if ( (*(_QWORD *)(a1 + 24) & 0x400000000000LL) == *(_QWORD *)(a1 + 24) )
        LODWORD(v2) = tlgWriteTransfer_EventWriteTransfer(a1, (unsigned __int8 *)&dword_18000E06C, a2, 0, 2u, &v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180004f6c  sub     rsp, 68h
0x180004f70  mov     rax, cs:__security_cookie
0x180004f77  xor     rax, rsp
0x180004f7a  mov     [rsp+68h+var_18], rax
0x180004f7f  mov     eax, [rcx]
0x180004f81  mov     r8, rdx
0x180004f84  cmp     eax, 5
0x180004f87  jbe     short loc_180004FCC
0x180004f89  mov     rdx, [rcx+18h]
0x180004f8d  mov     r9, 400000000000h
0x180004f97  mov     rax, [rcx+10h]
0x180004f9b  test    r9, rax
0x180004f9e  jz      short loc_180004FCC
0x180004fa0  mov     rax, rdx
0x180004fa3  and     rax, r9
0x180004fa6  cmp     rax, rdx
0x180004fa9  jnz     short loc_180004FCC
0x180004fab  lea     rax, [rsp+68h+var_38]
0x180004fb0  xor     r9d, r9d
0x180004fb3  mov     [rsp+68h+var_40], rax
0x180004fb8  lea     rdx, dword_18000E06C
0x180004fbf  mov     [rsp+68h+var_48], 2
0x180004fc7  call    _tlgWriteTransfer_EventWriteTransfer
0x180004fcc  mov     rcx, [rsp+68h+var_18]
0x180004fd1  xor     rcx, rsp; StackCookie
0x180004fd4  call    __security_check_cookie
0x180004fd9  add     rsp, 68h
0x180004fdd  retn
```
