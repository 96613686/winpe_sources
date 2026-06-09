# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x140011758`
- end: `0x1400117ca`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001191c`

## callees

- `0x1400016dc`
- `0x140002600`
- `0x140011758`

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
        LODWORD(v2) = tlgWriteTransfer_EventWriteTransfer(a1, (unsigned __int8 *)word_1400183D2, a2, 0, 2u, &v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140011758  sub     rsp, 68h
0x14001175c  mov     rax, cs:__security_cookie
0x140011763  xor     rax, rsp
0x140011766  mov     [rsp+68h+var_18], rax
0x14001176b  mov     eax, [rcx]
0x14001176d  mov     r8, rdx
0x140011770  cmp     eax, 5
0x140011773  jbe     short loc_1400117B8
0x140011775  mov     rdx, [rcx+18h]
0x140011779  mov     r9, 400000000000h
0x140011783  mov     rax, [rcx+10h]
0x140011787  test    r9, rax
0x14001178a  jz      short loc_1400117B8
0x14001178c  mov     rax, rdx
0x14001178f  and     rax, r9
0x140011792  cmp     rax, rdx
0x140011795  jnz     short loc_1400117B8
0x140011797  lea     rax, [rsp+68h+var_38]
0x14001179c  xor     r9d, r9d
0x14001179f  mov     [rsp+68h+var_40], rax
0x1400117a4  lea     rdx, word_1400183D2
0x1400117ab  mov     [rsp+68h+var_48], 2
0x1400117b3  call    _tlgWriteTransfer_EventWriteTransfer
0x1400117b8  mov     rcx, [rsp+68h+var_18]
0x1400117bd  xor     rcx, rsp; StackCookie
0x1400117c0  call    __security_check_cookie
0x1400117c5  add     rsp, 68h
0x1400117c9  retn
```
