# ReadCFFIndex

- ea: `0x14005a21c`
- end: `0x14005a3be`
- name: `ReadCFFIndex`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140059d9c`

## callees

- `0x14005a21c`
- `0x14005a3c4`
- `0x140075de0`
- `0x140098010`

## pseudocode

```c
__int64 __fastcall ReadCFFIndex(_QWORD *a1, __int64 a2, unsigned __int16 *a3)
{
  int v6; // eax
  unsigned __int16 v8; // cx
  char v9; // al
  __int64 v10; // rax
  __int64 v11; // rbp
  __int64 i; // rdi
  __int64 v13; // rax
  int *v14; // rcx
  int v15; // edx
  int v16; // ecx
  unsigned int v17; // edi
  __int64 v18; // rax
  unsigned __int16 v19; // [rsp+30h] [rbp-B8h] BYREF
  char v20; // [rsp+32h] [rbp-B6h]

  v6 = ((__int64 (__fastcall *)(_QWORD))a1[4])(*a1);
  *((_DWORD *)a3 + 6) = v6;
  if ( v6 == -1
    || ((__int64 (__fastcall *)(_QWORD, unsigned __int16 *, __int64, __int64, __int64))a1[1])(*a1, &v19, 3, 1, a2) != 1 )
  {
    return 0xFFFFFFFFLL;
  }
  v8 = _byteswap_ushort(v19);
  v9 = v20;
  *a3 = v8;
  *((_BYTE *)a3 + 2) = v9;
  v10 = ((__int64 (__fastcall *)(_QWORD, __int64))a1[5])(*a1, 4LL * v8 + 4);
  *((_QWORD *)a3 + 1) = v10;
  if ( v10 )
  {
    v11 = *((unsigned __int8 *)a3 + 2);
    if ( (unsigned int)v11 > 0x80 )
      return 4294967290LL;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v13 = *a3;
      if ( (unsigned int)i > (unsigned int)v13 )
        break;
      if ( ((__int64 (__fastcall *)(_QWORD, unsigned __int16 *, __int64, __int64, __int64))a1[1])(*a1, &v19, v11, 1, a2) != 1 )
        return 0xFFFFFFFFLL;
      *(_DWORD *)(*((_QWORD *)a3 + 1) + 4 * i) = getnum(&v19, (unsigned int)v11);
      if ( (_DWORD)i
        && *(_DWORD *)(*((_QWORD *)a3 + 1) + 4 * i) < *(_DWORD *)(*((_QWORD *)a3 + 1) + 4LL * (unsigned int)(i - 1)) )
      {
        return 4294967290LL;
      }
    }
    v14 = (int *)*((_QWORD *)a3 + 1);
    v15 = *v14;
    v16 = v14[v13];
    if ( v15 > 1 )
      v15 = 1;
    v17 = v16 - v15;
    v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD))a1[5])(*a1, (unsigned int)(v16 - v15));
    *((_QWORD *)a3 + 2) = v18;
    if ( v18 )
      return (unsigned int)-(((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, __int64, __int64))a1[1])(
                               *a1,
                               v18,
                               v17,
                               1,
                               a2) != 1);
  }
  return 4294967293LL;
}

```

## disassembly

```asm
0x14005a21c  mov     [rsp+arg_18], rbx
0x14005a221  push    rbp
0x14005a222  push    rsi
0x14005a223  push    rdi
0x14005a224  push    r14
0x14005a226  push    r15
0x14005a228  sub     rsp, 0C0h
0x14005a22f  mov     rax, cs:__security_cookie
0x14005a236  xor     rax, rsp
0x14005a239  mov     [rsp+0E8h+var_38], rax
0x14005a241  mov     rbx, rcx
0x14005a244  mov     rsi, r8
0x14005a247  mov     rcx, [rcx]
0x14005a24a  mov     r14, rdx
0x14005a24d  mov     rax, [rbx+20h]
0x14005a251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a256  mov     [rsi+18h], eax
0x14005a259  cmp     eax, 0FFFFFFFFh
0x14005a25c  jz      short loc_14005A286
0x14005a25e  mov     rcx, [rbx]
0x14005a261  lea     rdx, [rsp+0E8h+var_B8]
0x14005a266  mov     rax, [rbx+8]
0x14005a26a  mov     r15d, 1
0x14005a270  mov     r9d, r15d
0x14005a273  mov     [rsp+0E8h+var_C8], r14
0x14005a278  lea     r8d, [r15+2]
0x14005a27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a281  cmp     rax, r15
0x14005a284  jz      short loc_14005A2B0
0x14005a286  or      eax, 0FFFFFFFFh
0x14005a289  mov     rcx, [rsp+0E8h+var_38]
0x14005a291  xor     rcx, rsp; StackCookie
0x14005a294  call    __security_check_cookie
0x14005a299  mov     rbx, [rsp+0E8h+arg_18]
0x14005a2a1  add     rsp, 0C0h
0x14005a2a8  pop     r15
0x14005a2aa  pop     r14
0x14005a2ac  pop     rdi
0x14005a2ad  pop     rsi
0x14005a2ae  pop     rbp
0x14005a2af  retn
0x14005a2b0  movzx   eax, byte ptr [rsp+0E8h+var_B8+1]
0x14005a2b5  movzx   ecx, byte ptr [rsp+0E8h+var_B8]
0x14005a2ba  shl     cx, 8
0x14005a2be  or      cx, ax
0x14005a2c1  mov     al, [rsp+0E8h+var_B6]
0x14005a2c5  movzx   edx, cx
0x14005a2c8  mov     [rsi], dx
0x14005a2cb  mov     [rsi+2], al
0x14005a2ce  mov     rcx, [rbx]
0x14005a2d1  mov     rax, [rbx+28h]
0x14005a2d5  lea     rdx, ds:4[rdx*4]
0x14005a2dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a2e2  mov     [rsi+8], rax
0x14005a2e6  test    rax, rax
0x14005a2e9  jz      loc_14005A3B4
0x14005a2ef  movzx   ebp, byte ptr [rsi+2]
0x14005a2f3  cmp     ebp, 80h
0x14005a2f9  ja      loc_14005A3AA
0x14005a2ff  xor     edi, edi
0x14005a301  movzx   eax, word ptr [rsi]
0x14005a304  cmp     edi, eax
0x14005a306  ja      short loc_14005A349
0x14005a308  mov     rcx, [rbx]
0x14005a30b  lea     rdx, [rsp+0E8h+var_B8]
0x14005a310  mov     rax, [rbx+8]
0x14005a314  mov     r8, rbp
0x14005a317  mov     r9, r15
0x14005a31a  mov     [rsp+0E8h+var_C8], r14
0x14005a31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a324  cmp     rax, r15
0x14005a327  jnz     loc_14005A286
0x14005a32d  mov     edx, ebp
0x14005a32f  lea     rcx, [rsp+0E8h+var_B8]
0x14005a334  call    getnum
0x14005a339  mov     rcx, [rsi+8]
0x14005a33d  mov     [rcx+rdi*4], eax
0x14005a340  test    edi, edi
0x14005a342  jnz     short loc_14005A39B
0x14005a344  add     edi, r15d
0x14005a347  jmp     short loc_14005A301
0x14005a349  mov     rcx, [rsi+8]
0x14005a34d  mov     edx, [rcx]
0x14005a34f  cmp     edx, r15d
0x14005a352  mov     ecx, [rcx+rax*4]
0x14005a355  mov     rax, [rbx+28h]
0x14005a359  cmovg   edx, r15d
0x14005a35d  sub     ecx, edx
0x14005a35f  mov     edi, ecx
0x14005a361  mov     edx, ecx
0x14005a363  mov     rcx, [rbx]
0x14005a366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a36b  mov     [rsi+10h], rax
0x14005a36f  test    rax, rax
0x14005a372  jz      short loc_14005A3B4
0x14005a374  mov     rcx, [rbx]
0x14005a377  mov     rdx, rax
0x14005a37a  mov     rax, [rbx+8]
0x14005a37e  mov     r9, r15
0x14005a381  mov     r8d, edi
0x14005a384  mov     [rsp+0E8h+var_C8], r14
0x14005a389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a38e  sub     rax, r15
0x14005a391  neg     rax
0x14005a394  sbb     eax, eax
0x14005a396  jmp     loc_14005A289
0x14005a39b  mov     rdx, [rsi+8]
0x14005a39f  lea     eax, [rdi-1]
0x14005a3a2  mov     eax, [rdx+rax*4]
0x14005a3a5  cmp     [rdx+rdi*4], eax
0x14005a3a8  jge     short loc_14005A344
0x14005a3aa  mov     eax, 0FFFFFFFAh
0x14005a3af  jmp     loc_14005A289
0x14005a3b4  mov     eax, 0FFFFFFFDh
0x14005a3b9  jmp     loc_14005A289
```
