# get_namespace_uri

- ea: `0x18001f068`
- end: `0x18001f0c3`
- name: `get_namespace_uri`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fb5c`

## callees

- `0x18001f068`
- `0x18001fe28`
- `0x1800203e4`

## pseudocode

```c
_DWORD *__fastcall get_namespace_uri(_DWORD *a1, __int64 *a2, const void **a3)
{
  CNameSpaceInfo::GetNs(a2, (__int64)a1, a3);
  if ( !*a1
    && *(_DWORD *)a3
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF__xwcs_t_(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  return a1;
}

```

## disassembly

```asm
0x18001f068  mov     [rsp+arg_0], rbx
0x18001f06d  push    rdi
0x18001f06e  sub     rsp, 20h
0x18001f072  mov     rax, rdx
0x18001f075  mov     rdi, rcx
0x18001f078  mov     rdx, rcx
0x18001f07b  mov     rbx, r8
0x18001f07e  mov     rcx, rax
0x18001f081  call    ?GetNs@CNameSpaceInfo@@QEBA?BUCNsUri@@AEBV?$basic_xstr_t@_W@@@Z; CNameSpaceInfo::GetNs(basic_xstr_t<wchar_t> const &)
0x18001f086  cmp     dword ptr [rdi], 0
0x18001f089  jnz     short loc_18001F0B5
0x18001f08b  cmp     dword ptr [rbx], 0
0x18001f08e  jz      short loc_18001F0B5
0x18001f090  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f097  lea     rax, WPP_GLOBAL_Control
0x18001f09e  cmp     rcx, rax
0x18001f0a1  jz      short loc_18001F0B5
0x18001f0a3  test    byte ptr [rcx+1Ch], 1
0x18001f0a7  jz      short loc_18001F0B5
0x18001f0a9  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f0ad  mov     r9, rbx
0x18001f0b0  call    WPP_SF__xwcs_t_
0x18001f0b5  mov     rbx, [rsp+28h+arg_0]
0x18001f0ba  mov     rax, rdi
0x18001f0bd  add     rsp, 20h
0x18001f0c1  pop     rdi
0x18001f0c2  retn
```
