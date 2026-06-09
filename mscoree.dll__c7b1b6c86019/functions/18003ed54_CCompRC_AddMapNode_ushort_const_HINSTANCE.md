# CCompRC::AddMapNode(ushort const *,HINSTANCE__ *)

- ea: `0x18003ed54`
- end: `0x18003eea1`
- name: `?AddMapNode@CCompRC@@AEAAJPEBGPEAUHINSTANCE__@@@Z`
- size: `333`
- prototype: `int(CCompRC *__hidden this, const unsigned __int16 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003eff4`

## callees

- `0x180003740`
- `0x180003840`
- `0x1800060a0`
- `0x18003ed54`
- `0x18003fa88`
- `0x180041ec0`

## pseudocode

```c
__int64 __fastcall CCompRC::AddMapNode(CCompRC *this, const struct NoThrow *a2, HINSTANCE a3)
{
  char *v3; // rdi
  char *v7; // rax
  int v8; // r8d
  int i; // edx
  CCulturedHInstance *v10; // rcx
  unsigned __int64 v12; // r14
  unsigned __int128 v13; // rax
  char *v14; // rax
  char *v15; // rdi
  __int64 v16; // rax

  v3 = (char *)*((_QWORD *)this + 23);
  if ( !v3 )
  {
    v7 = (char *)operator new(0x508u, a2);
    v3 = v7;
    if ( !v7 )
    {
      *((_QWORD *)this + 23) = 0;
      return 2147942414LL;
    }
    `vector constructor iterator'(v7, 0xB8u, 7u, (void *(*)(void *))CCulturedHInstance::CCulturedHInstance);
    *((_QWORD *)this + 23) = v3;
    *((_DWORD *)this + 48) = 7;
  }
  v8 = *((_DWORD *)this + 48);
  for ( i = 0; i < v8; ++i )
  {
    v10 = (CCulturedHInstance *)&v3[184 * i];
    if ( !*((_QWORD *)v10 + 22) )
    {
      CCulturedHInstance::Set(v10, (const unsigned __int16 *)a2, a3);
      return 0;
    }
  }
  v12 = v8 + 5;
  v13 = v12 * (unsigned __int128)0xB8uLL;
  if ( !is_mul_ok(v12, 0xB8u) )
    *(_QWORD *)&v13 = -1;
  v14 = (char *)operator new(v13, *((const struct NoThrow **)&v13 + 1));
  v15 = v14;
  if ( v14 )
  {
    `vector constructor iterator'(v14, 0xB8u, v12, (void *(*)(void *))CCulturedHInstance::CCulturedHInstance);
    memmove(v15, *((const void **)this + 23), 184LL * *((int *)this + 48));
    operator delete(*((void **)this + 23));
    v16 = *((int *)this + 48);
    *((_QWORD *)this + 23) = v15;
    CCulturedHInstance::Set((CCulturedHInstance *)&v15[184 * v16], (const unsigned __int16 *)a2, a3);
    *((_DWORD *)this + 48) += 5;
    return 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18003ed54  push    rbx
0x18003ed56  push    rbp
0x18003ed57  push    rsi
0x18003ed58  push    rdi
0x18003ed59  push    r14
0x18003ed5b  push    r15
0x18003ed5d  sub     rsp, 28h
0x18003ed61  mov     rdi, [rcx+0B8h]
0x18003ed68  mov     rsi, r8
0x18003ed6b  mov     rbp, rdx
0x18003ed6e  mov     rbx, rcx
0x18003ed71  mov     r15d, 0B8h
0x18003ed77  test    rdi, rdi
0x18003ed7a  jnz     short loc_18003EDB7
0x18003ed7c  mov     ecx, 508h; unsigned __int64
0x18003ed81  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18003ed86  mov     rdi, rax
0x18003ed89  test    rax, rax
0x18003ed8c  jz      short loc_18003EDE0
0x18003ed8e  mov     r14d, 7
0x18003ed94  lea     r9, ??0CCulturedHInstance@@QEAA@XZ; void *(*)(void *)
0x18003ed9b  mov     r8d, r14d; unsigned __int64
0x18003ed9e  mov     edx, r15d; unsigned __int64
0x18003eda1  mov     rcx, rax; void *
0x18003eda4  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18003eda9  mov     [rbx+0B8h], rdi
0x18003edb0  mov     [rbx+0C0h], r14d
0x18003edb7  mov     r8d, [rbx+0C0h]
0x18003edbe  xor     edx, edx; struct NoThrow *
0x18003edc0  cmp     edx, r8d
0x18003edc3  jge     short loc_18003EE0C
0x18003edc5  movsxd  rax, edx
0x18003edc8  imul    rcx, rax, 0B8h
0x18003edcf  add     rcx, rdi; this
0x18003edd2  cmp     qword ptr [rcx+0B0h], 0
0x18003edda  jz      short loc_18003EDFD
0x18003eddc  inc     edx
0x18003edde  jmp     short loc_18003EDC0
0x18003ede0  mov     qword ptr [rbx+0B8h], 0
0x18003edeb  mov     eax, 8007000Eh
0x18003edf0  add     rsp, 28h
0x18003edf4  pop     r15
0x18003edf6  pop     r14
0x18003edf8  pop     rdi
0x18003edf9  pop     rsi
0x18003edfa  pop     rbp
0x18003edfb  pop     rbx
0x18003edfc  retn
0x18003edfd  mov     r8, rsi; HINSTANCE
0x18003ee00  mov     rdx, rbp; unsigned __int16 *
0x18003ee03  call    ?Set@CCulturedHInstance@@QEAAXPEBGPEAUHINSTANCE__@@@Z; CCulturedHInstance::Set(ushort const *,HINSTANCE__ *)
0x18003ee08  xor     eax, eax
0x18003ee0a  jmp     short loc_18003EDF0
0x18003ee0c  lea     eax, [r8+5]
0x18003ee10  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003ee17  movsxd  r14, eax
0x18003ee1a  mov     rax, r15
0x18003ee1d  mul     r14
0x18003ee20  cmovb   rax, rcx
0x18003ee24  mov     rcx, rax; unsigned __int64
0x18003ee27  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18003ee2c  mov     rdi, rax
0x18003ee2f  test    rax, rax
0x18003ee32  jz      short loc_18003EDEB
0x18003ee34  lea     r9, ??0CCulturedHInstance@@QEAA@XZ; void *(*)(void *)
0x18003ee3b  mov     r8, r14; unsigned __int64
0x18003ee3e  mov     rdx, r15; unsigned __int64
0x18003ee41  mov     rcx, rax; void *
0x18003ee44  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18003ee49  movsxd  rcx, dword ptr [rbx+0C0h]
0x18003ee50  mov     rdx, [rbx+0B8h]; Src
0x18003ee57  imul    r8, rcx, 0B8h; Size
0x18003ee5e  mov     rcx, rdi; void *
0x18003ee61  call    memmove
0x18003ee66  mov     rcx, [rbx+0B8h]; void *
0x18003ee6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ee72  movsxd  rax, dword ptr [rbx+0C0h]
0x18003ee79  mov     r8, rsi; HINSTANCE
0x18003ee7c  imul    rcx, rax, 0B8h
0x18003ee83  mov     rdx, rbp; unsigned __int16 *
0x18003ee86  mov     [rbx+0B8h], rdi
0x18003ee8d  add     rcx, rdi; this
0x18003ee90  call    ?Set@CCulturedHInstance@@QEAAXPEBGPEAUHINSTANCE__@@@Z; CCulturedHInstance::Set(ushort const *,HINSTANCE__ *)
0x18003ee95  add     dword ptr [rbx+0C0h], 5
0x18003ee9c  jmp     loc_18003EE08
```
