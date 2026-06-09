# UserSecurityContext::UserSecurityContext(void)

- ea: `0x180016178`
- end: `0x1800161df`
- name: `??0UserSecurityContext@@QEAA@XZ`
- size: `103`
- prototype: `UserSecurityContext *__fastcall(UserSecurityContext *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017728`
- `0x18001b088`

## callees

- `0x18001305c`
- `0x180023c5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
UserSecurityContext *__fastcall UserSecurityContext::UserSecurityContext(UserSecurityContext *this)
{
  memset_0((char *)this + 8, 0, 0x40u);
  *((_DWORD *)this + 8) = 1;
  *((_DWORD *)this + 15) = 1;
  *((_DWORD *)this + 16) = 2;
  *(_QWORD *)this = &UserSecurityContext::`vftable';
  *((_QWORD *)this + 11) = 0;
  CCriticalSection::CCriticalSection((UserSecurityContext *)((char *)this + 160));
  *((_BYTE *)this + 80) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 9) = 0;
  return this;
}

```

## disassembly

```asm
0x180016178  mov     [rsp+arg_8], rbx
0x18001617d  mov     [rsp+arg_0], rcx
0x180016182  push    rdi
0x180016183  sub     rsp, 20h
0x180016187  mov     rdi, rcx
0x18001618a  xor     edx, edx; Val
0x18001618c  lea     r8d, [rdx+40h]; Size
0x180016190  add     rcx, 8; void *
0x180016194  call    memset_0
0x180016199  mov     eax, 1
0x18001619e  mov     [rdi+20h], eax
0x1800161a1  mov     [rdi+3Ch], eax
0x1800161a4  mov     dword ptr [rdi+40h], 2
0x1800161ab  lea     rax, ??_7UserSecurityContext@@6B@; const UserSecurityContext::`vftable'
0x1800161b2  mov     [rdi], rax
0x1800161b5  xor     ebx, ebx
0x1800161b7  mov     [rdi+58h], rbx
0x1800161bb  lea     rcx, [rdi+0A0h]; this
0x1800161c2  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x1800161c7  mov     [rdi+50h], bl
0x1800161ca  mov     [rdi+60h], ebx
0x1800161cd  mov     [rdi+48h], rbx
0x1800161d1  mov     rax, rdi
0x1800161d4  mov     rbx, [rsp+28h+arg_8]
0x1800161d9  add     rsp, 20h
0x1800161dd  pop     rdi
0x1800161de  retn
```
