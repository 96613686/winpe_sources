# InsertFileIdTableNode

- ea: `0x14001cd64`
- end: `0x14001ce8e`
- name: `InsertFileIdTableNode`
- size: `298`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001af8c`
- `0x14001c420`
- `0x140024bc0`

## callees

- `0x14001cd64`
- `0x14001cef0`

## import_xrefs

- `ntoskrnl!RtlSplay` at `0x14001cdec`
- `ntoskrnl!RtlSplay` at `0x14001cdec`
- `FLTMGR!FltReleasePushLockEx` at `0x14001ce2d`
- `FLTMGR!FltReleasePushLockEx` at `0x14001ce2d`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001cd7f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001cd7f`

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

  FltAcquirePushLockExclusiveEx(&qword_14000F280, 0);
  v2 = (struct _RTL_SPLAY_LINKS *)(a1 + 144);
  v11 = 0;
  NodeOrParent = FindNodeOrParent((__int64 *)&Root, a1 + 168, &v11);
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
    ++dword_14000F278;
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
  return FltReleasePushLockEx(&qword_14000F280, 0);
}

```

## disassembly

```asm
0x14001cd64  mov     [rsp+arg_8], rbx
0x14001cd69  mov     [rsp+arg_10], rsi
0x14001cd6e  push    rdi
0x14001cd6f  sub     rsp, 20h
0x14001cd73  mov     rdi, rcx
0x14001cd76  xor     edx, edx
0x14001cd78  lea     rcx, qword_14000F280
0x14001cd7f  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001cd86  nop     dword ptr [rax+rax+00h]
0x14001cd8b  lea     rbx, [rdi+90h]
0x14001cd92  mov     [rsp+28h+arg_0], 0
0x14001cd9b  lea     rdx, [rbx+18h]
0x14001cd9f  lea     r8, [rsp+28h+arg_0]
0x14001cda4  lea     rcx, Root
0x14001cdab  call    FindNodeOrParent
0x14001cdb0  mov     rcx, [rsp+28h+arg_0]
0x14001cdb5  mov     esi, eax
0x14001cdb7  cmp     eax, 1
0x14001cdba  jz      loc_14001CE50
0x14001cdc0  mov     [rbx], rbx
0x14001cdc3  mov     qword ptr [rbx+8], 0
0x14001cdcb  mov     qword ptr [rbx+10h], 0
0x14001cdd3  inc     cs:dword_14000F278
0x14001cdd9  test    eax, eax
0x14001cddb  jz      short loc_14001CE55
0x14001cddd  cmp     eax, 2
0x14001cde0  jnz     short loc_14001CE4A
0x14001cde2  mov     [rcx+8], rbx
0x14001cde6  mov     [rbx], rcx
0x14001cde9  mov     rcx, rbx; Links
0x14001cdec  call    cs:__imp_RtlSplay
0x14001cdf3  nop     dword ptr [rax+rax+00h]
0x14001cdf8  mov     cs:Root, rax
0x14001cdff  lea     rax, [rdi+0C0h]
0x14001ce06  movzx   ecx, word ptr [rdi+1Eh]
0x14001ce0a  cmp     esi, 1
0x14001ce0d  jz      short loc_14001CE5E
0x14001ce0f  or      cx, 200h
0x14001ce14  mov     [rdi+1Eh], cx
0x14001ce18  mov     [rax+8], rax
0x14001ce1c  mov     [rax], rax
0x14001ce1f  or      word ptr [rdi+1Eh], 10h
0x14001ce24  lea     rcx, qword_14000F280
0x14001ce2b  xor     edx, edx
0x14001ce2d  call    cs:__imp_FltReleasePushLockEx
0x14001ce34  nop     dword ptr [rax+rax+00h]
0x14001ce39  mov     rbx, [rsp+28h+arg_8]
0x14001ce3e  mov     rsi, [rsp+28h+arg_10]
0x14001ce43  add     rsp, 20h
0x14001ce47  pop     rdi
0x14001ce48  retn
0x14001ce4a  mov     [rcx+10h], rbx
0x14001ce4e  jmp     short loc_14001CDE6
0x14001ce50  mov     rbx, rcx
0x14001ce53  jmp     short loc_14001CDE9
0x14001ce55  mov     cs:Root, rbx
0x14001ce5c  jmp     short loc_14001CDE9
0x14001ce5e  add     rbx, 30h ; '0'
0x14001ce62  mov     edx, 0FDFFh
0x14001ce67  and     cx, dx
0x14001ce6a  mov     [rdi+1Eh], cx
0x14001ce6e  mov     rcx, [rbx+8]
0x14001ce72  cmp     [rcx], rbx
0x14001ce75  jnz     short loc_14001CE87
0x14001ce77  mov     [rax], rbx
0x14001ce7a  mov     [rax+8], rcx
0x14001ce7e  mov     [rcx], rax
0x14001ce81  mov     [rbx+8], rax
0x14001ce85  jmp     short loc_14001CE1F
0x14001ce87  mov     ecx, 3
0x14001ce8c  int     29h; Win8: RtlFailFast(ecx)
```
