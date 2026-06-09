# CreateSysClock

- ea: `0x180012370`
- end: `0x18001245d`
- name: `CreateSysClock`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180012370`
- `0x180012590`
- `0x1800217b0`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800123a6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800123a6`

## pseudocode

```c
__int64 __fastcall CreateSysClock(CReferenceClockWinmm **a1)
{
  unsigned int v2; // ebx
  CReferenceClockWinmm *v3; // rax
  CReferenceClockWinmm *v4; // rdi

  if ( !dword_18002A894 )
    return 2147500037LL;
  if ( dword_18002A894 != 1 )
    return (unsigned int)-2147467259;
  v3 = (CReferenceClockWinmm *)malloc(0x10u);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 2) = 1;
    *(_QWORD *)v3 = &CReferenceClockWinmm::`vftable';
    if ( a1 )
    {
      *a1 = 0;
      if ( !memcmp_0(&IID_IReferenceClock, &IID_IUnknown, 0x10u)
        || !memcmp_0(&IID_IReferenceClock, &IID_IReferenceClock, 0x10u) )
      {
        *a1 = v4;
        (*(void (__fastcall **)(CReferenceClockWinmm *))(*(_QWORD *)v4 + 8LL))(v4);
        v2 = 0;
      }
      else
      {
        v2 = -2147467262;
      }
    }
    else
    {
      v2 = -2147467261;
    }
    CReferenceClockWinmm::Release(v4);
    return v2;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180012370  mov     [rsp+arg_0], rbx
0x180012375  mov     [rsp+arg_8], rsi
0x18001237a  push    rdi
0x18001237b  sub     rsp, 20h
0x18001237f  mov     edx, cs:dword_18002A894
0x180012385  mov     rbx, rcx
0x180012388  test    edx, edx
0x18001238a  jz      loc_180012448
0x180012390  cmp     edx, 1
0x180012393  jz      short loc_18001239F
0x180012395  mov     ebx, 80004005h
0x18001239a  jmp     loc_18001243D
0x18001239f  mov     esi, 10h
0x1800123a4  mov     ecx, esi; Size
0x1800123a6  call    cs:__imp_malloc
0x1800123ac  mov     [rsp+28h+arg_10], rax
0x1800123b1  mov     rdi, rax
0x1800123b4  test    rax, rax
0x1800123b7  jz      loc_180012441
0x1800123bd  mov     dword ptr [rdi+8], 1
0x1800123c4  lea     rax, ??_7CReferenceClockWinmm@@6B@; const CReferenceClockWinmm::`vftable'
0x1800123cb  mov     [rdi], rax
0x1800123ce  test    rdi, rdi
0x1800123d1  jz      short loc_180012441
0x1800123d3  test    rbx, rbx
0x1800123d6  jnz     short loc_1800123DF
0x1800123d8  mov     ebx, 80004003h
0x1800123dd  jmp     short loc_180012435
0x1800123df  mov     r8, rsi; Size
0x1800123e2  mov     qword ptr [rbx], 0
0x1800123e9  lea     rdx, IID_IUnknown; Buf2
0x1800123f0  lea     rcx, IID_IReferenceClock; Buf1
0x1800123f7  call    memcmp_0
0x1800123fc  test    eax, eax
0x1800123fe  jz      short loc_180012421
0x180012400  mov     r8, rsi; Size
0x180012403  lea     rdx, IID_IReferenceClock; Buf2
0x18001240a  lea     rcx, IID_IReferenceClock; Buf1
0x180012411  call    memcmp_0
0x180012416  test    eax, eax
0x180012418  jz      short loc_180012421
0x18001241a  mov     ebx, 80004002h
0x18001241f  jmp     short loc_180012435
0x180012421  mov     [rbx], rdi
0x180012424  mov     rcx, rdi
0x180012427  mov     rax, [rdi]
0x18001242a  mov     rax, [rax+8]
0x18001242e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012433  xor     ebx, ebx
0x180012435  mov     rcx, rdi; this
0x180012438  call    ?Release@CReferenceClockWinmm@@UEAAKXZ; CReferenceClockWinmm::Release(void)
0x18001243d  mov     eax, ebx
0x18001243f  jmp     short loc_18001244D
0x180012441  mov     eax, 8007000Eh
0x180012446  jmp     short loc_18001244D
0x180012448  mov     eax, 80004005h
0x18001244d  mov     rbx, [rsp+28h+arg_0]
0x180012452  mov     rsi, [rsp+28h+arg_8]
0x180012457  add     rsp, 20h
0x18001245b  pop     rdi
0x18001245c  retn
```
