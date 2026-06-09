# CValidatedData::Create(uint)

- ea: `0x180011800`
- end: `0x18001186a`
- name: `?Create@CValidatedData@@QEAAJI@Z`
- size: `106`
- prototype: `int(CValidatedData *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180014950`

## callees

- `0x180004d20`
- `0x180009658`
- `0x18000c2b4`
- `0x180011800`

## pseudocode

```c
__int64 __fastcall CValidatedData::Create(CValidatedData *this, const struct std::nothrow_t *a2)
{
  __int64 v3; // rdi
  void *v4; // rax
  void *v5; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *((_QWORD *)this + 2) = 0;
  v3 = (unsigned int)a2;
  v4 = operator new[]((unsigned int)a2, a2);
  v5 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = v4;
  if ( v5 )
    operator delete(v5);
  if ( *((_QWORD *)this + 1) )
  {
    *((_QWORD *)this + 2) = v3;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\restricted\\windows\\inc\\apiportclient.h",
      (const char *)0x8007000ELL,
      v7);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180011800  mov     [rsp+arg_0], rbx
0x180011805  push    rdi; int
0x180011806  sub     rsp, 20h
0x18001180a  mov     rbx, rcx
0x18001180d  mov     qword ptr [rcx+10h], 0
0x180011815  mov     ecx, edx; unsigned __int64
0x180011817  mov     edi, edx
0x180011819  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001181e  mov     rcx, [rbx+8]; void *
0x180011822  mov     [rbx+8], rax
0x180011826  test    rcx, rcx
0x180011829  jz      short loc_180011830
0x18001182b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011830  cmp     qword ptr [rbx+8], 0
0x180011835  jnz     short loc_180011859
0x180011837  mov     rcx, [rsp+28h]; this
0x18001183c  lea     r8, aOnecoreuapRest; "onecoreuap\\restricted\\windows\\inc\\a"...
0x180011843  mov     ebx, 8007000Eh
0x180011848  mov     edx, 53h ; 'S'; void *
0x18001184d  mov     r9d, ebx; char *
0x180011850  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011855  mov     eax, ebx
0x180011857  jmp     short loc_18001185F
0x180011859  mov     [rbx+10h], rdi
0x18001185d  xor     eax, eax
0x18001185f  mov     rbx, [rsp+28h+arg_0]
0x180011864  add     rsp, 20h
0x180011868  pop     rdi
0x180011869  retn
```
