# EapHost::Peer::ConnectionSessionInfo::FreeBuffers(void)

- ea: `0x18000c160`
- end: `0x18000c1fb`
- name: `?FreeBuffers@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ`
- size: `155`
- prototype: `void __fastcall(EapHost::Peer::ConnectionSessionInfo *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000b6ac`
- `0x18000bef4`
- `0x18000c88c`

## callees

- `0x1800017a4`
- `0x18000c160`
- `0x18000f010`

## pseudocode

```c
void __fastcall EapHost::Peer::ConnectionSessionInfo::FreeBuffers(EapHost::Peer::ConnectionSessionInfo *this)
{
  _QWORD **v1; // rdx
  _QWORD *v3; // rbx
  __int64 v4; // rcx
  _QWORD *v5; // rsi

  v1 = (_QWORD **)*((_QWORD *)this + 19);
  *v1[1] = 0;
  v3 = *v1;
  if ( *v1 )
  {
    do
    {
      v4 = v3[2];
      v5 = (_QWORD *)*v3;
      if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 8), 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
      operator delete(v3);
      v3 = v5;
    }
    while ( v5 );
  }
  **((_QWORD **)this + 19) = *((_QWORD *)this + 19);
  *(_QWORD *)(*((_QWORD *)this + 19) + 8LL) = *((_QWORD *)this + 19);
  *((_QWORD *)this + 20) = 0;
}

```

## disassembly

```asm
0x18000c160  mov     [rsp+arg_8], rbx
0x18000c165  mov     [rsp+arg_10], rsi
0x18000c16a  push    rdi
0x18000c16b  sub     rsp, 20h
0x18000c16f  mov     rdx, [rcx+98h]
0x18000c176  mov     rdi, rcx
0x18000c179  mov     rax, [rdx+8]
0x18000c17d  mov     qword ptr [rax], 0
0x18000c184  mov     rbx, [rdx]
0x18000c187  test    rbx, rbx
0x18000c18a  jz      short loc_18000C1CA
0x18000c18c  mov     rcx, [rbx+10h]
0x18000c190  mov     rsi, [rbx]
0x18000c193  test    rcx, rcx
0x18000c196  jz      short loc_18000C1B5
0x18000c198  or      eax, 0FFFFFFFFh
0x18000c19b  lock xadd [rcx+8], eax
0x18000c1a0  cmp     eax, 1
0x18000c1a3  jnz     short loc_18000C1B5
0x18000c1a5  mov     rax, [rcx]
0x18000c1a8  mov     edx, 1
0x18000c1ad  mov     rax, [rax]
0x18000c1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1b5  mov     edx, 18h; unsigned __int64
0x18000c1ba  mov     rcx, rbx; void *
0x18000c1bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c1c2  mov     rbx, rsi
0x18000c1c5  test    rsi, rsi
0x18000c1c8  jnz     short loc_18000C18C
0x18000c1ca  mov     rax, [rdi+98h]
0x18000c1d1  mov     rbx, [rsp+28h+arg_8]
0x18000c1d6  mov     rsi, [rsp+28h+arg_10]
0x18000c1db  mov     [rax], rax
0x18000c1de  mov     rax, [rdi+98h]
0x18000c1e5  mov     [rax+8], rax
0x18000c1e9  mov     qword ptr [rdi+0A0h], 0
0x18000c1f4  add     rsp, 20h
0x18000c1f8  pop     rdi
0x18000c1f9  retn
```
