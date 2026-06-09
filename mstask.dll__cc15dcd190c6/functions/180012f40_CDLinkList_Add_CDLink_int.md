# CDLinkList::Add(CDLink *,int)

- ea: `0x180012f40`
- end: `0x180012f86`
- name: `?Add@CDLinkList@@UEAAXPEAVCDLink@@H@Z`
- size: `70`
- prototype: `void(CDLinkList *__hidden this, struct CDLink *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180012f90`
- `0x1800144ac`
- `0x180014aa0`

## callees

- `0x180012f40`
- `0x1800198ac`
- `0x1800198e0`

## pseudocode

```c
void __fastcall CDLinkList::Add(CDLinkList *this, struct CDLink *a2, int a3)
{
  struct CDLink *v4; // rdx
  __int64 v5; // r9
  __int64 v6; // r10
  __int64 v7; // r9
  __int64 v8; // r10

  v4 = (struct CDLink *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    if ( a3 == 1 )
    {
      CDLink::LinkBefore(a2, v4);
      *(_QWORD *)(v6 + 8) = v5;
    }
    else
    {
      CDLink::LinkAfter(a2, *((struct CDLink **)this + 2));
      *(_QWORD *)(v8 + 16) = v7;
    }
  }
  else
  {
    *((_QWORD *)this + 1) = a2;
    *((_QWORD *)this + 2) = a2;
  }
}

```

## disassembly

```asm
0x180012f40  sub     rsp, 28h
0x180012f44  mov     r9, rdx
0x180012f47  mov     r10, rcx
0x180012f4a  mov     rdx, [rcx+8]; struct CDLink *
0x180012f4e  test    rdx, rdx
0x180012f51  jnz     short loc_180012F5D
0x180012f53  mov     [rcx+8], r9
0x180012f57  mov     [rcx+10h], r9
0x180012f5b  jmp     short loc_180012F81
0x180012f5d  cmp     r8d, 1
0x180012f61  jnz     short loc_180012F71
0x180012f63  mov     rcx, r9; this
0x180012f66  call    ?LinkBefore@CDLink@@QEAAXPEAV1@@Z; CDLink::LinkBefore(CDLink *)
0x180012f6b  mov     [r10+8], r9
0x180012f6f  jmp     short loc_180012F81
0x180012f71  mov     rdx, [rcx+10h]; struct CDLink *
0x180012f75  mov     rcx, r9; this
0x180012f78  call    ?LinkAfter@CDLink@@QEAAXPEAV1@@Z; CDLink::LinkAfter(CDLink *)
0x180012f7d  mov     [r10+10h], r9
0x180012f81  add     rsp, 28h
0x180012f85  retn
```
