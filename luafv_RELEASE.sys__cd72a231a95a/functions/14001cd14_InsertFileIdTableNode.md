# InsertFileIdTableNode

- ea: `0x14001cd14`
- end: `0x14001ce3e`
- name: `InsertFileIdTableNode`
- size: `298`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001af3c`
- `0x14001c3d0`
- `0x140024b70`

## callees

- `0x14001cd14`
- `0x14001cea0`

## import_xrefs

- `ntoskrnl!RtlSplay` at `0x14001cd9c`
- `ntoskrnl!RtlSplay` at `0x14001cd9c`
- `FLTMGR!FltReleasePushLockEx` at `0x14001cddd`
- `FLTMGR!FltReleasePushLockEx` at `0x14001cddd`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001cd2f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001cd2f`

## pseudocode

```c
__int64 __fastcall InsertFileIdTableNode(__int64 a1)
{
  struct _RTL_SPLAY_LINKS *v2; // rbx
  int NodeOrParent; // eax
  struct _RTL_SPLAY_LINKS *v4; // rcx
  int v5; // esi
  struct _RTL_SPLAY_LINKS *v6; // rax
  __int16 v7; // cx
  struct _RTL_SPLAY_LINKS *v9; // rbx
  struct _RTL_SPLAY_LINKS *LeftChild; // rcx
  struct _RTL_SPLAY_LINKS *v11; // [rsp+30h] [rbp+8h] BYREF

  FltAcquirePushLockExclusiveEx(&qword_14000EC40, 0);
  v2 = (struct _RTL_SPLAY_LINKS *)(a1 + 144);
  v11 = 0;
  NodeOrParent = FindNodeOrParent(&Root, a1 + 168, &v11);
  v4 = v11;
  v5 = NodeOrParent;
  if ( NodeOrParent == 1 )
  {
    v2 = v11;
  }
  else
  {
    v2->Parent = v2;
    *(_QWORD *)(a1 + 152) = 0;
    *(_QWORD *)(a1 + 160) = 0;
    ++dword_14000EC38;
    if ( NodeOrParent )
    {
      if ( NodeOrParent == 2 )
        v4->LeftChild = v2;
      else
        v4->RightChild = v2;
      v2->Parent = v4;
    }
    else
    {
      Root = (PRTL_SPLAY_LINKS)(a1 + 144);
    }
  }
  Root = RtlSplay(v2);
  v6 = (struct _RTL_SPLAY_LINKS *)(a1 + 192);
  v7 = *(_WORD *)(a1 + 30);
  if ( v5 == 1 )
  {
    v9 = v2 + 2;
    *(_WORD *)(a1 + 30) = v7 & 0xFDFF;
    LeftChild = v9->LeftChild;
    if ( LeftChild->Parent != v9 )
      __fastfail(3u);
    v6->Parent = v9;
    *(_QWORD *)(a1 + 200) = LeftChild;
    LeftChild->Parent = v6;
    v9->LeftChild = v6;
  }
  else
  {
    *(_WORD *)(a1 + 30) = v7 | 0x200;
    *(_QWORD *)(a1 + 200) = a1 + 192;
    v6->Parent = v6;
  }
  *(_WORD *)(a1 + 30) |= 0x10u;
  return FltReleasePushLockEx(&qword_14000EC40, 0);
}

```

## disassembly

```asm
0x14001cd14  mov     [rsp+arg_8], rbx
0x14001cd19  mov     [rsp+arg_10], rsi
0x14001cd1e  push    rdi
0x14001cd1f  sub     rsp, 20h
0x14001cd23  mov     rdi, rcx
0x14001cd26  xor     edx, edx
0x14001cd28  lea     rcx, qword_14000EC40
0x14001cd2f  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001cd36  nop     dword ptr [rax+rax+00h]
0x14001cd3b  lea     rbx, [rdi+90h]
0x14001cd42  mov     [rsp+28h+arg_0], 0
0x14001cd4b  lea     rdx, [rbx+18h]
0x14001cd4f  lea     r8, [rsp+28h+arg_0]
0x14001cd54  lea     rcx, Root
0x14001cd5b  call    FindNodeOrParent
0x14001cd60  mov     rcx, [rsp+28h+arg_0]
0x14001cd65  mov     esi, eax
0x14001cd67  cmp     eax, 1
0x14001cd6a  jz      loc_14001CE00
0x14001cd70  mov     [rbx], rbx
0x14001cd73  mov     qword ptr [rbx+8], 0
0x14001cd7b  mov     qword ptr [rbx+10h], 0
0x14001cd83  inc     cs:dword_14000EC38
0x14001cd89  test    eax, eax
0x14001cd8b  jz      short loc_14001CE05
0x14001cd8d  cmp     eax, 2
0x14001cd90  jnz     short loc_14001CDFA
0x14001cd92  mov     [rcx+8], rbx
0x14001cd96  mov     [rbx], rcx
0x14001cd99  mov     rcx, rbx; Links
0x14001cd9c  call    cs:__imp_RtlSplay
0x14001cda3  nop     dword ptr [rax+rax+00h]
0x14001cda8  mov     cs:Root, rax
0x14001cdaf  lea     rax, [rdi+0C0h]
0x14001cdb6  movzx   ecx, word ptr [rdi+1Eh]
0x14001cdba  cmp     esi, 1
0x14001cdbd  jz      short loc_14001CE0E
0x14001cdbf  or      cx, 200h
0x14001cdc4  mov     [rdi+1Eh], cx
0x14001cdc8  mov     [rax+8], rax
0x14001cdcc  mov     [rax], rax
0x14001cdcf  or      word ptr [rdi+1Eh], 10h
0x14001cdd4  lea     rcx, qword_14000EC40
0x14001cddb  xor     edx, edx
0x14001cddd  call    cs:__imp_FltReleasePushLockEx
0x14001cde4  nop     dword ptr [rax+rax+00h]
0x14001cde9  mov     rbx, [rsp+28h+arg_8]
0x14001cdee  mov     rsi, [rsp+28h+arg_10]
0x14001cdf3  add     rsp, 20h
0x14001cdf7  pop     rdi
0x14001cdf8  retn
0x14001cdfa  mov     [rcx+10h], rbx
0x14001cdfe  jmp     short loc_14001CD96
0x14001ce00  mov     rbx, rcx
0x14001ce03  jmp     short loc_14001CD99
0x14001ce05  mov     cs:Root, rbx
0x14001ce0c  jmp     short loc_14001CD99
0x14001ce0e  add     rbx, 30h ; '0'
0x14001ce12  mov     edx, 0FDFFh
0x14001ce17  and     cx, dx
0x14001ce1a  mov     [rdi+1Eh], cx
0x14001ce1e  mov     rcx, [rbx+8]
0x14001ce22  cmp     [rcx], rbx
0x14001ce25  jnz     short loc_14001CE37
0x14001ce27  mov     [rax], rbx
0x14001ce2a  mov     [rax+8], rcx
0x14001ce2e  mov     [rcx], rax
0x14001ce31  mov     [rbx+8], rax
0x14001ce35  jmp     short loc_14001CDCF
0x14001ce37  mov     ecx, 3
0x14001ce3c  int     29h; Win8: RtlFailFast(ecx)
```
