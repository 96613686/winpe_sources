# CDirectMusicSynthPort::KsEvent(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x180011a20`
- end: `0x180011acd`
- name: `?KsEvent@CDirectMusicSynthPort@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `173`
- prototype: `__int64 __fastcall(CDirectMusicSynthPort *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180011a20`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusicSynthPort::KsEvent(
        CDirectMusicSynthPort *this,
        struct KSIDENTIFIER *a2,
        unsigned int a3,
        void *a4,
        unsigned int a5,
        unsigned int *a6)
{
  __int64 result; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx

  if ( a3 && !a2 || !a6 )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 2) )
    return 2289570100LL;
  v11 = *((_QWORD *)this + 4);
  result = 2289570082LL;
  if ( !v11
    || (result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 40LL))(v11), (_DWORD)result == -2005397214) )
  {
    v12 = *((_QWORD *)this + 5);
    if ( v12 )
      return (*(__int64 (__fastcall **)(__int64, struct KSIDENTIFIER *, _QWORD, void *, unsigned int, unsigned int *))(*(_QWORD *)v12 + 40LL))(
               v12,
               a2,
               a3,
               a4,
               a5,
               a6);
  }
  return result;
}

```

## disassembly

```asm
0x180011a20  push    rbx
0x180011a22  push    rbp
0x180011a23  push    rsi
0x180011a24  push    rdi
0x180011a25  push    r14
0x180011a27  push    r15
0x180011a29  sub     rsp, 48h
0x180011a2d  mov     r15, r9
0x180011a30  mov     ebp, r8d
0x180011a33  mov     rsi, rdx
0x180011a36  mov     rbx, rcx
0x180011a39  test    r8d, r8d
0x180011a3c  jz      short loc_180011A43
0x180011a3e  test    rdx, rdx
0x180011a41  jz      short loc_180011A50
0x180011a43  mov     rdi, [rsp+78h+arg_28]
0x180011a4b  test    rdi, rdi
0x180011a4e  jnz     short loc_180011A57
0x180011a50  mov     eax, 80004003h
0x180011a55  jmp     short loc_180011AC0
0x180011a57  cmp     qword ptr [rcx+10h], 0
0x180011a5c  jnz     short loc_180011A65
0x180011a5e  mov     eax, 88781134h
0x180011a63  jmp     short loc_180011AC0
0x180011a65  mov     rcx, [rcx+20h]
0x180011a69  mov     eax, 88781122h
0x180011a6e  mov     r14d, [rsp+78h+arg_20]
0x180011a76  test    rcx, rcx
0x180011a79  jz      short loc_180011A98
0x180011a7b  mov     rax, [rcx]
0x180011a7e  mov     [rsp+78h+var_50], rdi
0x180011a83  mov     [rsp+78h+var_58], r14d
0x180011a88  mov     rax, [rax+28h]
0x180011a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a91  cmp     eax, 88781122h
0x180011a96  jnz     short loc_180011AC0
0x180011a98  mov     rcx, [rbx+28h]
0x180011a9c  test    rcx, rcx
0x180011a9f  jz      short loc_180011AC0
0x180011aa1  mov     rax, [rcx]
0x180011aa4  mov     r9, r15
0x180011aa7  mov     [rsp+78h+var_50], rdi
0x180011aac  mov     r8d, ebp
0x180011aaf  mov     rdx, rsi
0x180011ab2  mov     [rsp+78h+var_58], r14d
0x180011ab7  mov     rax, [rax+28h]
0x180011abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ac0  add     rsp, 48h
0x180011ac4  pop     r15
0x180011ac6  pop     r14
0x180011ac8  pop     rdi
0x180011ac9  pop     rsi
0x180011aca  pop     rbp
0x180011acb  pop     rbx
0x180011acc  retn
```
