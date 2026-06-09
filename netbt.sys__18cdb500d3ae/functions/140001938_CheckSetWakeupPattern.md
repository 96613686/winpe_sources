# CheckSetWakeupPattern

- ea: `0x140001938`
- end: `0x140001b96`
- name: `CheckSetWakeupPattern`
- size: `606`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1400021d0`
- `0x1400031bc`
- `0x140003d04`

## callees

- `0x140001938`
- `0x140001b9c`
- `0x140001ca0`
- `0x140030f40`
- `0x140031020`
- `0x140031440`
- `0x1400428f4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000198d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a51`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000198d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a51`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400019da`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001a71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001af7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b80`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400019da`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001a71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001af7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b80`

## string_xrefs

- `0x140001b4d`: `Remove`

## pseudocode

```c
__int64 __fastcall CheckSetWakeupPattern(__int64 a1, char *a2, char a3, char a4)
{
  KSPIN_LOCK *v8; // rsi
  KIRQL v9; // bp
  int v10; // r15d
  __int128 v11; // xmm0
  __int64 v12; // r9
  __int64 v13; // r8
  int v14; // eax
  unsigned int v15; // r14d
  const char *v17; // r9
  _DWORD v18[20]; // [rsp+40h] [rbp-98h] BYREF

  if ( *(_DWORD *)(a1 + 340) )
    return 3221225473LL;
  v8 = (KSPIN_LOCK *)(a1 + 848);
  if ( a4 )
    v9 = -1;
  else
    v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 848));
  v10 = *(_DWORD *)(a1 + 596);
  if ( a3 )
  {
    if ( v10 )
    {
      v15 = -1073741823;
      if ( !memcmp((const void *)(a1 + 600), a2, 0xFu) )
      {
        v15 = 0;
        *(_DWORD *)(a1 + 596) = v10 + 1;
      }
      goto LABEL_15;
    }
    v11 = *(_OWORD *)a2;
    *(_DWORD *)(a1 + 596) = 1;
    *(_OWORD *)(a1 + 600) = v11;
LABEL_7:
    if ( !a4 )
      KeReleaseSpinLock(v8, v9);
    if ( (BYTE3(xmmword_140038420) & 1) != 0 )
    {
      v17 = "Add";
      if ( !a3 )
        v17 = "Remove";
      WPP_SF_ssDZ((unsigned __int8)a2[15], (unsigned int)"Remove", a3, (_DWORD)v17, (__int64)a2, a2[15], a1 + 456);
    }
    memset(v18, 0, 0x4Cu);
    ConvertToHalfAscii(&v18[10], a2, 0, 0);
    BYTE1(v18[2]) = 17;
    LOBYTE(v12) = a3;
    HIWORD(v18[7]) = 4096;
    v18[5] = -1996453632;
    v14 = NbtSetClearWakeUpPattern(a1, v18, v13, v12);
    v15 = v14;
    if ( !a3 || v14 >= 0 )
      return v15;
    if ( !a4 )
      v9 = KeAcquireSpinLockRaiseToDpc(v8);
    --*(_DWORD *)(a1 + 596);
LABEL_15:
    if ( !a4 )
      KeReleaseSpinLock(v8, v9);
    return v15;
  }
  if ( !v10 || memcmp((const void *)(a1 + 600), a2, 0xFu) )
  {
    if ( !a4 )
      KeReleaseSpinLock(v8, v9);
    return 3221225473LL;
  }
  *(_DWORD *)(a1 + 596) = v10 - 1;
  if ( v10 == 1 )
    goto LABEL_7;
  if ( !a4 )
    KeReleaseSpinLock(v8, v9);
  return 0;
}

```

## disassembly

```asm
0x140001938  mov     [rsp+arg_18], rbx
0x14000193d  push    rbp
0x14000193e  push    rsi
0x14000193f  push    rdi
0x140001940  push    r12
0x140001942  push    r13
0x140001944  push    r14
0x140001946  push    r15
0x140001948  sub     rsp, 0A0h
0x14000194f  mov     rax, cs:__security_cookie
0x140001956  xor     rax, rsp
0x140001959  mov     [rsp+0D8h+var_48], rax
0x140001961  cmp     dword ptr [rcx+154h], 0
0x140001968  mov     dil, r9b
0x14000196b  mov     r13b, r8b
0x14000196e  mov     r12, rdx
0x140001971  mov     rbx, rcx
0x140001974  jnz     loc_140001B8C
0x14000197a  lea     rsi, [rcx+350h]
0x140001981  test    r9b, r9b
0x140001984  jnz     loc_140001AAC
0x14000198a  mov     rcx, rsi; SpinLock
0x14000198d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001994  nop     dword ptr [rax+rax+00h]
0x140001999  mov     bpl, al
0x14000199c  mov     r15d, [rbx+254h]
0x1400019a3  test    r13b, r13b
0x1400019a6  jz      loc_140001AB4
0x1400019ac  lea     rax, [rbx+258h]
0x1400019b3  test    r15d, r15d
0x1400019b6  jnz     loc_140001B0A
0x1400019bc  movups  xmm0, xmmword ptr [r12]
0x1400019c1  mov     dword ptr [rbx+254h], 1
0x1400019cb  movdqu  xmmword ptr [rax], xmm0
0x1400019cf  test    dil, dil
0x1400019d2  jnz     short loc_1400019E6
0x1400019d4  mov     dl, bpl; NewIrql
0x1400019d7  mov     rcx, rsi; SpinLock
0x1400019da  call    cs:__imp_KeReleaseSpinLock
0x1400019e1  nop     dword ptr [rax+rax+00h]
0x1400019e6  test    byte ptr cs:xmmword_140038420+3, 1
0x1400019ed  jnz     loc_140001B3B
0x1400019f3  xor     edx, edx; Val
0x1400019f5  lea     rcx, [rsp+0D8h+var_98]; void *
0x1400019fa  lea     r8d, [rdx+4Ch]; Size
0x1400019fe  call    memset
0x140001a03  xor     r9d, r9d
0x140001a06  lea     rcx, [rsp+0D8h+var_70]
0x140001a0b  xor     r8d, r8d
0x140001a0e  mov     rdx, r12
0x140001a11  call    ConvertToHalfAscii
0x140001a16  mov     eax, 1000h
0x140001a1b  mov     [rsp+0D8h+var_8F], 11h
0x140001a20  mov     r9b, r13b
0x140001a23  mov     [rsp+0D8h+var_7A], ax
0x140001a28  lea     rdx, [rsp+0D8h+var_98]
0x140001a2d  mov     [rsp+0D8h+var_84], 89008900h
0x140001a35  mov     rcx, rbx
0x140001a38  call    NbtSetClearWakeUpPattern
0x140001a3d  mov     r14d, eax
0x140001a40  test    r13b, r13b
0x140001a43  jz      short loc_140001A7D
0x140001a45  test    eax, eax
0x140001a47  jns     short loc_140001A7D
0x140001a49  test    dil, dil
0x140001a4c  jnz     short loc_140001A60
0x140001a4e  mov     rcx, rsi; SpinLock
0x140001a51  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001a58  nop     dword ptr [rax+rax+00h]
0x140001a5d  mov     bpl, al
0x140001a60  dec     dword ptr [rbx+254h]
0x140001a66  test    dil, dil
0x140001a69  jnz     short loc_140001A7D
0x140001a6b  mov     dl, bpl; NewIrql
0x140001a6e  mov     rcx, rsi; SpinLock
0x140001a71  call    cs:__imp_KeReleaseSpinLock
0x140001a78  nop     dword ptr [rax+rax+00h]
0x140001a7d  mov     eax, r14d
0x140001a80  mov     rcx, [rsp+0D8h+var_48]
0x140001a88  xor     rcx, rsp; StackCookie
0x140001a8b  call    __security_check_cookie
0x140001a90  mov     rbx, [rsp+0D8h+arg_18]
0x140001a98  add     rsp, 0A0h
0x140001a9f  pop     r15
0x140001aa1  pop     r14
0x140001aa3  pop     r13
0x140001aa5  pop     r12
0x140001aa7  pop     rdi
0x140001aa8  pop     rsi
0x140001aa9  pop     rbp
0x140001aaa  retn
0x140001aac  mov     bpl, 0FFh
0x140001aaf  jmp     loc_14000199C
0x140001ab4  test    r15d, r15d
0x140001ab7  jz      loc_140001B75
0x140001abd  lea     rcx, [rbx+258h]; Buf1
0x140001ac4  mov     r8d, 0Fh; Size
0x140001aca  mov     rdx, r12; Buf2
0x140001acd  call    memcmp
0x140001ad2  test    eax, eax
0x140001ad4  jnz     loc_140001B75
0x140001ada  lea     eax, [r15-1]
0x140001ade  mov     [rbx+254h], eax
0x140001ae4  test    eax, eax
0x140001ae6  jz      loc_1400019CF
0x140001aec  test    dil, dil
0x140001aef  jnz     short loc_140001B03
0x140001af1  mov     dl, bpl; NewIrql
0x140001af4  mov     rcx, rsi; SpinLock
0x140001af7  call    cs:__imp_KeReleaseSpinLock
0x140001afe  nop     dword ptr [rax+rax+00h]
0x140001b03  xor     eax, eax
0x140001b05  jmp     loc_140001A80
0x140001b0a  mov     r8d, 0Fh; Size
0x140001b10  mov     rdx, r12; Buf2
0x140001b13  mov     rcx, rax; Buf1
0x140001b16  mov     r14d, 0C0000001h
0x140001b1c  call    memcmp
0x140001b21  test    eax, eax
0x140001b23  jnz     loc_140001A66
0x140001b29  lea     eax, [r15+1]
0x140001b2d  xor     r14d, r14d
0x140001b30  mov     [rbx+254h], eax
0x140001b36  jmp     loc_140001A66
0x140001b3b  movzx   ecx, byte ptr [r12+0Fh]
0x140001b41  lea     rax, [rbx+1C8h]
0x140001b48  mov     [rsp+0D8h+var_A8], rax
0x140001b4d  lea     rdx, aRemove; "Remove"
0x140001b54  test    r13b, r13b
0x140001b57  mov     [rsp+0D8h+var_B0], ecx
0x140001b5b  lea     r9, aAdd; "Add"
0x140001b62  mov     [rsp+0D8h+var_B8], r12
0x140001b67  cmovz   r9, rdx
0x140001b6b  call    WPP_SF_ssDZ
0x140001b70  jmp     loc_1400019F3
0x140001b75  test    dil, dil
0x140001b78  jnz     short loc_140001B8C
0x140001b7a  mov     dl, bpl; NewIrql
0x140001b7d  mov     rcx, rsi; SpinLock
0x140001b80  call    cs:__imp_KeReleaseSpinLock
0x140001b87  nop     dword ptr [rax+rax+00h]
0x140001b8c  mov     eax, 0C0000001h
0x140001b91  jmp     loc_140001A80
```
