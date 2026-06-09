# CFmIfsEngine::_FmIfsCallbackHandler(_FMIFS_PACKET_TYPE,ulong,void *)

- ea: `0x180002648`
- end: `0x18000278e`
- name: `?_FmIfsCallbackHandler@CFmIfsEngine@@AEAAEW4_FMIFS_PACKET_TYPE@@KPEAX@Z`
- size: `326`
- prototype: `unsigned __int8 __high(enum _FMIFS_PACKET_TYPE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002600`

## callees

- `0x180002648`
- `0x180005ff6`
- `0x180007010`

## import_xrefs

- `msvcrt!malloc` at `0x1800026a0`
- `msvcrt!malloc` at `0x1800026a0`
- `msvcrt!free` at `0x180002707`
- `msvcrt!free` at `0x180002707`

## pseudocode

```c
char __fastcall CFmIfsEngine::_FmIfsCallbackHandler(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  __int64 v4; // rdi
  size_t v6; // r15
  _BYTE *v9; // r13
  int v10; // ebp
  __int64 v11; // rsi
  __int64 v12; // rax
  char *v13; // rax
  char *v14; // r12
  __int64 (__fastcall *v15)(__int64, __int64, _QWORD); // rax
  int v16; // eax
  bool v17; // al
  unsigned int v18; // [rsp+30h] [rbp-58h]
  char v19; // [rsp+90h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 64);
  v6 = a3;
  v19 = 1;
  if ( !v4 )
    return 1;
  if ( (_DWORD)a2 == 14 )
  {
    v9 = (_BYTE *)a4[1];
    v10 = 0;
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( v9[v12] );
    v18 = v12 + 17;
    v13 = (char *)malloc((unsigned int)(v12 + 17));
    v14 = v13;
    if ( v13 )
    {
      memcpy_0(v13, a4, v6);
      do
        ++v11;
      while ( v9[v11] );
      memcpy_0(&v14[v6], v9, v11 + 1);
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, char *, char *))(*(_QWORD *)v4 + 24LL))(
              v4,
              14,
              v18,
              v14,
              &v19);
      free(v14);
    }
    goto LABEL_16;
  }
  v15 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v4 + 24LL);
  if ( (_DWORD)a2 == 13 )
  {
    v16 = v15(v4, a2, a3);
    *(_BYTE *)a4 = v19;
  }
  else
  {
    if ( (_DWORD)a2 == 33 )
    {
      v10 = v15(v4, a2, a3);
      *(_BYTE *)a4 = v19;
      goto LABEL_16;
    }
    v16 = v15(v4, a2, a3);
  }
  v10 = v16;
LABEL_16:
  v17 = *(_BYTE *)(a1 + 72) || !v19 || v10 < 0;
  *(_BYTE *)(a1 + 72) = v17;
  return !v17;
}

```

## disassembly

```asm
0x180002648  mov     rax, rsp
0x18000264b  push    rbx
0x18000264c  push    rbp
0x18000264d  push    rsi
0x18000264e  push    rdi
0x18000264f  push    r12
0x180002651  push    r13
0x180002653  push    r14
0x180002655  push    r15
0x180002657  sub     rsp, 48h
0x18000265b  mov     rdi, [rcx+40h]
0x18000265f  mov     rbx, r9
0x180002662  mov     r15d, r8d
0x180002665  mov     r14, rcx
0x180002668  mov     byte ptr [rax+8], 1
0x18000266c  test    rdi, rdi
0x18000266f  jnz     short loc_180002678
0x180002671  mov     al, 1
0x180002673  jmp     loc_18000277D
0x180002678  cmp     edx, 0Eh
0x18000267b  jnz     loc_18000270F
0x180002681  mov     r13, [r9+8]
0x180002685  xor     ebp, ebp
0x180002687  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000268b  mov     rax, rsi
0x18000268e  inc     rax
0x180002691  cmp     [rax+r13], bpl
0x180002695  jnz     short loc_18000268E
0x180002697  add     eax, 11h
0x18000269a  mov     ecx, eax; Size
0x18000269c  mov     [rsp+88h+var_58], eax
0x1800026a0  call    cs:__imp_malloc
0x1800026a6  mov     r12, rax
0x1800026a9  test    rax, rax
0x1800026ac  jz      loc_18000275C
0x1800026b2  mov     r8, r15; Size
0x1800026b5  mov     rdx, rbx; Src
0x1800026b8  mov     rcx, rax; void *
0x1800026bb  call    memcpy_0
0x1800026c0  inc     rsi
0x1800026c3  cmp     [rsi+r13], bpl
0x1800026c7  jnz     short loc_1800026C0
0x1800026c9  lea     r8, [rsi+1]; Size
0x1800026cd  mov     rdx, r13; Src
0x1800026d0  lea     rcx, [r15+r12]; void *
0x1800026d4  call    memcpy_0
0x1800026d9  mov     rax, [rdi]
0x1800026dc  lea     rcx, [rsp+88h+arg_0]
0x1800026e4  mov     r8d, [rsp+88h+var_58]
0x1800026e9  mov     r9, r12
0x1800026ec  mov     [rsp+88h+var_68], rcx
0x1800026f1  mov     edx, 0Eh
0x1800026f6  mov     rcx, rdi
0x1800026f9  mov     rax, [rax+18h]
0x1800026fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002702  mov     rcx, r12; Block
0x180002705  mov     ebp, eax
0x180002707  call    cs:__imp_free
0x18000270d  jmp     short loc_18000275C
0x18000270f  mov     rax, [rdi]
0x180002712  lea     rcx, [rsp+88h+arg_0]
0x18000271a  mov     [rsp+88h+var_68], rcx
0x18000271f  mov     r8d, r15d
0x180002722  mov     rcx, rdi
0x180002725  mov     rax, [rax+18h]
0x180002729  cmp     edx, 0Dh
0x18000272c  jnz     short loc_18000273E
0x18000272e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002733  mov     cl, [rsp+88h+arg_0]
0x18000273a  mov     [rbx], cl
0x18000273c  jmp     short loc_18000275A
0x18000273e  cmp     edx, 21h ; '!'
0x180002741  jnz     short loc_180002755
0x180002743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002748  mov     ebp, eax
0x18000274a  mov     al, [rsp+88h+arg_0]
0x180002751  mov     [rbx], al
0x180002753  jmp     short loc_18000275C
0x180002755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000275a  mov     ebp, eax
0x18000275c  cmp     byte ptr [r14+48h], 0
0x180002761  jnz     short loc_180002775
0x180002763  cmp     [rsp+88h+arg_0], 0
0x18000276b  jz      short loc_180002775
0x18000276d  test    ebp, ebp
0x18000276f  js      short loc_180002775
0x180002771  xor     eax, eax
0x180002773  jmp     short loc_180002777
0x180002775  mov     al, 1
0x180002777  mov     [r14+48h], al
0x18000277b  xor     al, 1
0x18000277d  add     rsp, 48h
0x180002781  pop     r15
0x180002783  pop     r14
0x180002785  pop     r13
0x180002787  pop     r12
0x180002789  pop     rdi
0x18000278a  pop     rsi
0x18000278b  pop     rbp
0x18000278c  pop     rbx
0x18000278d  retn
```
