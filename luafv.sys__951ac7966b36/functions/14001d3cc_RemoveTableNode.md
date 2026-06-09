# RemoveTableNode

- ea: `0x14001d3cc`
- end: `0x14001d4ca`
- name: `RemoveTableNode`
- size: `254`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140016114`
- `0x140017e60`
- `0x14001d524`
- `0x14001efc0`
- `0x140022b50`

## callees

- `0x140001200`
- `0x14001d3cc`
- `0x14001d4d0`
- `0x14001dd00`
- `0x14001de14`

## import_xrefs

- `FLTMGR!FltReleasePushLockEx` at `0x14001d485`
- `FLTMGR!FltReleasePushLockEx` at `0x14001d49a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001d485`
- `FLTMGR!FltReleasePushLockEx` at `0x14001d49a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d3f2`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d407`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d3f2`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d407`

## pseudocode

```c
__int64 __fastcall RemoveTableNode(__int64 a1, char a2)
{
  PRTL_SPLAY_LINKS *v4; // rdi
  __int64 *v5; // rcx
  __int16 v6; // ax

  v4 = *(PRTL_SPLAY_LINKS **)(*(_QWORD *)(a1 + 32) + 40LL);
  FltAcquirePushLockExclusiveEx(&qword_14000F280, 0);
  FltAcquirePushLockExclusiveEx(&qword_14000F298, 0);
  v5 = *(__int64 **)(a1 + 232);
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
  FltReleasePushLockEx(&qword_14000F298, 0);
  return FltReleasePushLockEx(&qword_14000F280, 0);
}

```

## disassembly

```asm
0x14001d3cc  mov     [rsp+arg_0], rbx
0x14001d3d1  mov     [rsp+arg_8], rsi
0x14001d3d6  push    rdi
0x14001d3d7  sub     rsp, 20h
0x14001d3db  mov     rax, [rcx+20h]
0x14001d3df  mov     sil, dl
0x14001d3e2  mov     rbx, rcx
0x14001d3e5  xor     edx, edx
0x14001d3e7  lea     rcx, qword_14000F280
0x14001d3ee  mov     rdi, [rax+28h]
0x14001d3f2  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001d3f9  nop     dword ptr [rax+rax+00h]
0x14001d3fe  xor     edx, edx
0x14001d400  lea     rcx, qword_14000F298
0x14001d407  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001d40e  nop     dword ptr [rax+rax+00h]
0x14001d413  mov     rcx, [rbx+0E8h]
0x14001d41a  test    rcx, rcx
0x14001d41d  jz      short loc_14001D42F
0x14001d41f  call    LuafvDereferenceCachedSecurityDescriptor
0x14001d424  mov     qword ptr [rbx+0E8h], 0
0x14001d42f  test    byte ptr [rbx+1Eh], 10h
0x14001d433  jz      short loc_14001D43D
0x14001d435  mov     rcx, rbx
0x14001d438  call    RemoveFileIdTableNode
0x14001d43d  movzx   eax, word ptr [rbx+1Eh]
0x14001d441  test    al, 8
0x14001d443  jz      short loc_14001D45E
0x14001d445  lea     rdx, [rbx+60h]; Links
0x14001d449  mov     rcx, rdi; Root
0x14001d44c  call    LuafvDeleteElementTable
0x14001d451  mov     eax, 0FFF7h
0x14001d456  and     [rbx+1Eh], ax
0x14001d45a  movzx   eax, word ptr [rbx+1Eh]
0x14001d45e  test    sil, sil
0x14001d461  jnz     short loc_14001D4B7
0x14001d463  mov     rcx, rbx
0x14001d466  call    RemoveMruListNode
0x14001d46b  lea     rdx, [rbx+30h]; Links
0x14001d46f  mov     rcx, rdi; Root
0x14001d472  call    LuafvDeleteElementTable
0x14001d477  or      word ptr [rbx+1Eh], 4
0x14001d47c  xor     edx, edx
0x14001d47e  lea     rcx, qword_14000F298
0x14001d485  call    cs:__imp_FltReleasePushLockEx
0x14001d48c  nop     dword ptr [rax+rax+00h]
0x14001d491  xor     edx, edx
0x14001d493  lea     rcx, qword_14000F280
0x14001d49a  call    cs:__imp_FltReleasePushLockEx
0x14001d4a1  nop     dword ptr [rax+rax+00h]
0x14001d4a6  mov     rbx, [rsp+28h+arg_0]
0x14001d4ab  mov     rsi, [rsp+28h+arg_8]
0x14001d4b0  add     rsp, 20h
0x14001d4b4  pop     rdi
0x14001d4b5  retn
0x14001d4b7  cmp     dword ptr [rbx+100h], 2
0x14001d4be  jbe     short loc_14001D47C
0x14001d4c0  or      ax, 80h
0x14001d4c4  mov     [rbx+1Eh], ax
0x14001d4c8  jmp     short loc_14001D47C
```
