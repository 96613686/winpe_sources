# AccountLockoutOpenAndQuery

- ea: `0x180011664`
- end: `0x1800116ff`
- name: `AccountLockoutOpenAndQuery`
- size: `155`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f040`
- `0x180018f04`

## callees

- `0x180011664`
- `0x18001195c`
- `0x180011b3c`

## import_xrefs

- `msvcrt!malloc` at `0x1800116b8`
- `msvcrt!malloc` at `0x1800116b8`

## pseudocode

```c
__int64 __fastcall AccountLockoutOpenAndQuery(unsigned __int16 *a1, unsigned __int16 *a2, AccountInfo **a3)
{
  __int64 v7; // rax
  __int64 v8; // rcx
  AccountInfo *v9; // rax
  AccountInfo *v10; // rax

  if ( !a3 )
    return 87;
  if ( AccountInfo::root && a2 && a1 )
  {
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    do
      ++v7;
    while ( a1[v7] );
    v9 = (AccountInfo *)malloc(2 * (v7 + v8) + 34);
    if ( v9 )
      v10 = AccountInfo::AccountInfo(v9, a2, a1);
    else
      v10 = 0;
    *a3 = v10;
    if ( v10 && AccountInfo::isLockedOut(v10) )
      return 1;
  }
  else
  {
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180011664  push    rbx
0x180011666  push    rbp
0x180011667  push    rsi
0x180011668  push    rdi
0x180011669  sub     rsp, 28h
0x18001166d  xor     ebp, ebp
0x18001166f  mov     rbx, r8
0x180011672  mov     rdi, rdx
0x180011675  mov     rsi, rcx
0x180011678  test    r8, r8
0x18001167b  jnz     short loc_180011682
0x18001167d  lea     eax, [rbp+57h]
0x180011680  jmp     short loc_1800116F6
0x180011682  cmp     cs:?root@AccountInfo@@0VLockoutKey@@A, ebp; LockoutKey AccountInfo::root
0x180011688  jz      short loc_1800116F1
0x18001168a  test    rdi, rdi
0x18001168d  jz      short loc_1800116F1
0x18001168f  test    rsi, rsi
0x180011692  jz      short loc_1800116F1
0x180011694  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011698  mov     rcx, rax
0x18001169b  inc     rcx
0x18001169e  cmp     [rdx+rcx*2], bp
0x1800116a2  jnz     short loc_18001169B
0x1800116a4  inc     rax
0x1800116a7  cmp     [rsi+rax*2], bp
0x1800116ab  jnz     short loc_1800116A4
0x1800116ad  add     rcx, rax
0x1800116b0  lea     rcx, ds:22h[rcx*2]; Size
0x1800116b8  call    cs:__imp_malloc
0x1800116be  test    rax, rax
0x1800116c1  jz      short loc_1800116D3
0x1800116c3  mov     r8, rsi; unsigned __int16 *
0x1800116c6  mov     rdx, rdi; unsigned __int16 *
0x1800116c9  mov     rcx, rax; this
0x1800116cc  call    ??0AccountInfo@@IEAA@PEBG0@Z; AccountInfo::AccountInfo(ushort const *,ushort const *)
0x1800116d1  jmp     short loc_1800116D6
0x1800116d3  mov     rax, rbp
0x1800116d6  mov     [rbx], rax
0x1800116d9  test    rax, rax
0x1800116dc  jz      short loc_1800116F4
0x1800116de  mov     rcx, rax; this
0x1800116e1  call    ?isLockedOut@AccountInfo@@QEBA_NXZ; AccountInfo::isLockedOut(void)
0x1800116e6  test    al, al
0x1800116e8  jz      short loc_1800116F4
0x1800116ea  mov     eax, 1
0x1800116ef  jmp     short loc_1800116F6
0x1800116f1  mov     [r8], rbp
0x1800116f4  mov     eax, ebp
0x1800116f6  add     rsp, 28h
0x1800116fa  pop     rdi
0x1800116fb  pop     rsi
0x1800116fc  pop     rbp
0x1800116fd  pop     rbx
0x1800116fe  retn
```
