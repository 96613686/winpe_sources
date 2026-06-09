# NameMapper::copyIdentity(ushort const *)

- ea: `0x180020f28`
- end: `0x180020fcd`
- name: `?copyIdentity@NameMapper@@IEAAPEAGPEBG@Z`
- size: `165`
- prototype: `unsigned __int16 *(NameMapper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800213d0`

## callees

- `0x180001f26`
- `0x18000c4a4`
- `0x18000c808`
- `0x180020f28`
- `0x1800254a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020f9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020f9a`

## string_xrefs

- `0x180020f53`: `NameMapper::copyIdentity`

## pseudocode

```c
unsigned __int16 *__fastcall NameMapper::copyIdentity(NameMapper *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  SIZE_T v4; // rdi
  void *v5; // rax
  void *v6; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("NameMapper::copyIdentity");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids, "NPSSVC");
  }
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  v4 = 2LL * (unsigned int)(v3 + 1);
  v5 = CoTaskMemAlloc(v4);
  v6 = v5;
  if ( !v5 )
    _com_issue_error(-2147024882);
  memcpy_0(v5, a2, v4);
  return (unsigned __int16 *)v6;
}

```

## disassembly

```asm
0x180020f28  push    rbx
0x180020f2a  push    rbp
0x180020f2b  push    rsi
0x180020f2c  push    rdi
0x180020f2d  sub     rsp, 28h
0x180020f31  mov     rsi, rdx
0x180020f34  mov     rax, cs:WPP_GLOBAL_Control
0x180020f3b  lea     rcx, WPP_GLOBAL_Control
0x180020f42  cmp     rax, rcx
0x180020f45  jz      short loc_180020F82
0x180020f47  cmp     byte ptr [rax+19h], 4
0x180020f4b  jb      short loc_180020F82
0x180020f4d  test    byte ptr [rax+1Ch], 4
0x180020f51  jz      short loc_180020F82
0x180020f53  lea     rcx, aNamemapperCopy; "NameMapper::copyIdentity"
0x180020f5a  call    WppDbgPrint
0x180020f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f66  lea     r9, aNpssvc; "NPSSVC"
0x180020f6d  mov     edx, 13h
0x180020f72  lea     r8, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids
0x180020f79  mov     rcx, [rcx+10h]
0x180020f7d  call    WPP_SF_s
0x180020f82  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020f86  xor     ebp, ebp
0x180020f88  inc     rax
0x180020f8b  cmp     [rsi+rax*2], bp
0x180020f8f  jnz     short loc_180020F88
0x180020f91  lea     edi, [rax+1]
0x180020f94  add     rdi, rdi
0x180020f97  mov     rcx, rdi; cb
0x180020f9a  call    cs:__imp_CoTaskMemAlloc
0x180020fa0  mov     rbx, rax
0x180020fa3  test    rax, rax
0x180020fa6  jnz     short loc_180020FB3
0x180020fa8  mov     ecx, 8007000Eh; int
0x180020fad  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180020fb3  mov     r8, rdi; Size
0x180020fb6  mov     rdx, rsi; Src
0x180020fb9  mov     rcx, rbx; void *
0x180020fbc  call    memcpy_0
0x180020fc1  mov     rax, rbx
0x180020fc4  add     rsp, 28h
0x180020fc8  pop     rdi
0x180020fc9  pop     rsi
0x180020fca  pop     rbp
0x180020fcb  pop     rbx
0x180020fcc  retn
```
