# CCompStrFactory::_CreateCompositionString(ulong)

- ea: `0x180072b18`
- end: `0x180072c11`
- name: `?_CreateCompositionString@CCompStrFactory@@AEAAJK@Z`
- size: `249`
- prototype: `__int64 __fastcall(CCompStrFactory *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003c2c0`
- `0x18003c4fc`
- `0x180044224`

## callees

- `0x180072b18`
- `0x18009eaea`
- `0x18010a010`

## import_xrefs

- `IMM32!ImmGetIMCCSize` at `0x180072b3c`
- `IMM32!ImmGetIMCCSize` at `0x180072b3c`
- `IMM32!ImmCreateIMCC` at `0x180072bc0`
- `IMM32!ImmCreateIMCC` at `0x180072bf8`
- `IMM32!ImmCreateIMCC` at `0x180072bc0`
- `IMM32!ImmCreateIMCC` at `0x180072bf8`
- `IMM32!ImmReSizeIMCC` at `0x180072b57`
- `IMM32!ImmReSizeIMCC` at `0x180072b57`
- `IMM32!ImmDestroyIMCC` at `0x180072bf0`
- `IMM32!ImmDestroyIMCC` at `0x180072bf0`

## pseudocode

```c
__int64 __fastcall CCompStrFactory::_CreateCompositionString(CCompStrFactory *this, int a2)
{
  DWORD v2; // edi
  HIMCC v4; // rcx
  BOOL v5; // ebp
  HIMCC v6; // rax
  HIMCC v7; // rdx
  __int64 result; // rax
  HIMCC IMCC; // rax

  v2 = a2 + 116;
  v4 = (HIMCC)*((_QWORD *)this + 2);
  v5 = a2 == 0;
  if ( v4 )
  {
    if ( ImmGetIMCCSize(v4) == v2 )
      goto LABEL_8;
    if ( *((_QWORD *)this + 1) )
      (*(void (__fastcall **)(CCompStrFactory *, _QWORD))(*(_QWORD *)this + 16LL))(this, *((_QWORD *)this + 2));
    v6 = ImmReSizeIMCC(*((HIMCC *)this + 2), v2);
    v7 = v6;
    if ( v6 )
    {
      *((_QWORD *)this + 2) = v6;
LABEL_7:
      *((_DWORD *)this + 6) = (*(__int64 (__fastcall **)(CCompStrFactory *, HIMCC, char *))(*(_QWORD *)this + 8LL))(
                                this,
                                v7,
                                (char *)this + 8);
      goto LABEL_8;
    }
    ImmDestroyIMCC(*((HIMCC *)this + 2));
    IMCC = ImmCreateIMCC(v2);
    v7 = IMCC;
    *((_QWORD *)this + 2) = IMCC;
  }
  else
  {
    IMCC = ImmCreateIMCC(v2);
    v7 = IMCC;
    *((_QWORD *)this + 2) = IMCC;
  }
  if ( IMCC )
    goto LABEL_7;
LABEL_8:
  result = *((unsigned int *)this + 6);
  if ( (int)result >= 0 )
  {
    if ( *((_QWORD *)this + 2) )
    {
      memset_0(*((void **)this + 1), 0, v2);
      result = v5;
      **((_DWORD **)this + 1) = v2;
      *((_QWORD *)this + 4) = *((_QWORD *)this + 1) + 100LL;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180072b18  push    rbx
0x180072b1a  push    rbp
0x180072b1b  push    rsi
0x180072b1c  push    rdi
0x180072b1d  sub     rsp, 28h
0x180072b21  xor     ebp, ebp
0x180072b23  lea     edi, [rdx+74h]
0x180072b26  test    edx, edx
0x180072b28  mov     rbx, rcx
0x180072b2b  mov     rcx, [rcx+10h]; HIMCC
0x180072b2f  setz    bpl
0x180072b33  test    rcx, rcx
0x180072b36  jz      loc_180072BBE
0x180072b3c  call    cs:__imp_ImmGetIMCCSize
0x180072b42  cmp     eax, edi
0x180072b44  jz      short loc_180072B83
0x180072b46  cmp     qword ptr [rbx+8], 0
0x180072b4b  jnz     loc_180072BD4
0x180072b51  mov     rcx, [rbx+10h]; HIMCC
0x180072b55  mov     edx, edi; DWORD
0x180072b57  call    cs:__imp_ImmReSizeIMCC
0x180072b5d  mov     rdx, rax
0x180072b60  test    rax, rax
0x180072b63  jz      loc_180072BEC
0x180072b69  mov     [rbx+10h], rax
0x180072b6d  mov     rax, [rbx]
0x180072b70  lea     r8, [rbx+8]
0x180072b74  mov     rcx, rbx
0x180072b77  mov     rax, [rax+8]
0x180072b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b80  mov     [rbx+18h], eax
0x180072b83  mov     eax, [rbx+18h]
0x180072b86  test    eax, eax
0x180072b88  jns     short loc_180072B93
0x180072b8a  add     rsp, 28h
0x180072b8e  pop     rdi
0x180072b8f  pop     rsi
0x180072b90  pop     rbp
0x180072b91  pop     rbx
0x180072b92  retn
0x180072b93  cmp     qword ptr [rbx+10h], 0
0x180072b98  jz      short loc_180072C07
0x180072b9a  mov     rcx, [rbx+8]; void *
0x180072b9e  xor     edx, edx; Val
0x180072ba0  mov     r8d, edi; Size
0x180072ba3  call    memset_0
0x180072ba8  mov     rcx, [rbx+8]
0x180072bac  mov     eax, ebp
0x180072bae  mov     [rcx], edi
0x180072bb0  mov     rcx, [rbx+8]
0x180072bb4  add     rcx, 64h ; 'd'
0x180072bb8  mov     [rbx+20h], rcx
0x180072bbc  jmp     short loc_180072B8A
0x180072bbe  mov     ecx, edi; DWORD
0x180072bc0  call    cs:__imp_ImmCreateIMCC
0x180072bc6  mov     rdx, rax
0x180072bc9  mov     [rbx+10h], rax
0x180072bcd  test    rax, rax
0x180072bd0  jnz     short loc_180072B6D
0x180072bd2  jmp     short loc_180072B83
0x180072bd4  mov     rax, [rbx]
0x180072bd7  mov     rcx, rbx
0x180072bda  mov     rdx, [rbx+10h]
0x180072bde  mov     rax, [rax+10h]
0x180072be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072be7  jmp     loc_180072B51
0x180072bec  mov     rcx, [rbx+10h]; HIMCC
0x180072bf0  call    cs:__imp_ImmDestroyIMCC
0x180072bf6  mov     ecx, edi; DWORD
0x180072bf8  call    cs:__imp_ImmCreateIMCC
0x180072bfe  mov     rdx, rax
0x180072c01  mov     [rbx+10h], rax
0x180072c05  jmp     short loc_180072BCD
0x180072c07  mov     eax, 8007000Eh
0x180072c0c  jmp     loc_180072B8A
```
