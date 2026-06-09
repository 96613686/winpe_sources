# RemoveTableNode

- ea: `0x14001d37c`
- end: `0x14001d47a`
- name: `RemoveTableNode`
- size: `254`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140016114`
- `0x140017e10`
- `0x14001d4d4`
- `0x14001ef70`
- `0x140022b00`

## callees

- `0x140001200`
- `0x14001d37c`
- `0x14001d480`
- `0x14001dcb0`
- `0x14001ddc4`

## import_xrefs

- `FLTMGR!FltReleasePushLockEx` at `0x14001d435`
- `FLTMGR!FltReleasePushLockEx` at `0x14001d44a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001d435`
- `FLTMGR!FltReleasePushLockEx` at `0x14001d44a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d3a2`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d3b7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d3a2`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d3b7`

## pseudocode

```c
__int64 __fastcall RemoveTableNode(__int64 a1, char a2)
{
  PRTL_SPLAY_LINKS *v4; // rdi
  __int64 v5; // rcx
  __int16 v6; // ax

  v4 = *(PRTL_SPLAY_LINKS **)(*(_QWORD *)(a1 + 32) + 40LL);
  FltAcquirePushLockExclusiveEx(&qword_14000EC40, 0);
  FltAcquirePushLockExclusiveEx(&qword_14000EC58, 0);
  v5 = *(_QWORD *)(a1 + 232);
  if ( v5 )
  {
    LuafvDereferenceCachedSecurityDescriptor(v5);
    *(_QWORD *)(a1 + 232) = 0;
  }
  if ( (*(_BYTE *)(a1 + 30) & 0x10) != 0 )
    RemoveFileIdTableNode(a1);
  v6 = *(_WORD *)(a1 + 30);
  if ( (v6 & 8) != 0 )
  {
    LuafvDeleteElementTable(v4, (PRTL_SPLAY_LINKS)(a1 + 96));
    *(_WORD *)(a1 + 30) &= ~8u;
    v6 = *(_WORD *)(a1 + 30);
  }
  if ( a2 )
  {
    if ( *(_DWORD *)(a1 + 256) > 2u )
      *(_WORD *)(a1 + 30) = v6 | 0x80;
  }
  else
  {
    RemoveMruListNode(a1);
    LuafvDeleteElementTable(v4, (PRTL_SPLAY_LINKS)(a1 + 48));
    *(_WORD *)(a1 + 30) |= 4u;
  }
  FltReleasePushLockEx(&qword_14000EC58, 0);
  return FltReleasePushLockEx(&qword_14000EC40, 0);
}

```

## disassembly

```asm
0x14001d37c  mov     [rsp+arg_0], rbx
0x14001d381  mov     [rsp+arg_8], rsi
0x14001d386  push    rdi
0x14001d387  sub     rsp, 20h
0x14001d38b  mov     rax, [rcx+20h]
0x14001d38f  mov     sil, dl
0x14001d392  mov     rbx, rcx
0x14001d395  xor     edx, edx
0x14001d397  lea     rcx, qword_14000EC40
0x14001d39e  mov     rdi, [rax+28h]
0x14001d3a2  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001d3a9  nop     dword ptr [rax+rax+00h]
0x14001d3ae  xor     edx, edx
0x14001d3b0  lea     rcx, qword_14000EC58
0x14001d3b7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001d3be  nop     dword ptr [rax+rax+00h]
0x14001d3c3  mov     rcx, [rbx+0E8h]
0x14001d3ca  test    rcx, rcx
0x14001d3cd  jz      short loc_14001D3DF
0x14001d3cf  call    LuafvDereferenceCachedSecurityDescriptor
0x14001d3d4  mov     qword ptr [rbx+0E8h], 0
0x14001d3df  test    byte ptr [rbx+1Eh], 10h
0x14001d3e3  jz      short loc_14001D3ED
0x14001d3e5  mov     rcx, rbx
0x14001d3e8  call    RemoveFileIdTableNode
0x14001d3ed  movzx   eax, word ptr [rbx+1Eh]
0x14001d3f1  test    al, 8
0x14001d3f3  jz      short loc_14001D40E
0x14001d3f5  lea     rdx, [rbx+60h]; Links
0x14001d3f9  mov     rcx, rdi; Root
0x14001d3fc  call    LuafvDeleteElementTable
0x14001d401  mov     eax, 0FFF7h
0x14001d406  and     [rbx+1Eh], ax
0x14001d40a  movzx   eax, word ptr [rbx+1Eh]
0x14001d40e  test    sil, sil
0x14001d411  jnz     short loc_14001D467
0x14001d413  mov     rcx, rbx
0x14001d416  call    RemoveMruListNode
0x14001d41b  lea     rdx, [rbx+30h]; Links
0x14001d41f  mov     rcx, rdi; Root
0x14001d422  call    LuafvDeleteElementTable
0x14001d427  or      word ptr [rbx+1Eh], 4
0x14001d42c  xor     edx, edx
0x14001d42e  lea     rcx, qword_14000EC58
0x14001d435  call    cs:__imp_FltReleasePushLockEx
0x14001d43c  nop     dword ptr [rax+rax+00h]
0x14001d441  xor     edx, edx
0x14001d443  lea     rcx, qword_14000EC40
0x14001d44a  call    cs:__imp_FltReleasePushLockEx
0x14001d451  nop     dword ptr [rax+rax+00h]
0x14001d456  mov     rbx, [rsp+28h+arg_0]
0x14001d45b  mov     rsi, [rsp+28h+arg_8]
0x14001d460  add     rsp, 20h
0x14001d464  pop     rdi
0x14001d465  retn
0x14001d467  cmp     dword ptr [rbx+100h], 2
0x14001d46e  jbe     short loc_14001D42C
0x14001d470  or      ax, 80h
0x14001d474  mov     [rbx+1Eh], ax
0x14001d478  jmp     short loc_14001D42C
```
