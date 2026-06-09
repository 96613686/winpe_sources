# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000c018`
- end: `0x18000c08a`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c27c`

## callees

- `0x1800018dc`
- `0x180001f90`
- `0x18000c018`

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
        LODWORD(v2) = tlgWriteTransfer_EventWriteTransfer(a1, (unsigned __int8 *)byte_180015E99, a2, 0, 2u, &v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000c018  sub     rsp, 68h
0x18000c01c  mov     rax, cs:__security_cookie
0x18000c023  xor     rax, rsp
0x18000c026  mov     [rsp+68h+var_18], rax
0x18000c02b  mov     eax, [rcx]
0x18000c02d  mov     r8, rdx
0x18000c030  cmp     eax, 5
0x18000c033  jbe     short loc_18000C078
0x18000c035  mov     rdx, [rcx+18h]
0x18000c039  mov     r9, 400000000000h
0x18000c043  mov     rax, [rcx+10h]
0x18000c047  test    r9, rax
0x18000c04a  jz      short loc_18000C078
0x18000c04c  mov     rax, rdx
0x18000c04f  and     rax, r9
0x18000c052  cmp     rax, rdx
0x18000c055  jnz     short loc_18000C078
0x18000c057  lea     rax, [rsp+68h+var_38]
0x18000c05c  xor     r9d, r9d
0x18000c05f  mov     [rsp+68h+var_40], rax
0x18000c064  lea     rdx, byte_180015E99
0x18000c06b  mov     [rsp+68h+var_48], 2
0x18000c073  call    _tlgWriteTransfer_EventWriteTransfer
0x18000c078  mov     rcx, [rsp+68h+var_18]
0x18000c07d  xor     rcx, rsp; StackCookie
0x18000c080  call    __security_check_cookie
0x18000c085  add     rsp, 68h
0x18000c089  retn
```
