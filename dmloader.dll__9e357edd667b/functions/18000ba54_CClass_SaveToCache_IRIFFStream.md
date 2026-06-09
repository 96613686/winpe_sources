# CClass::SaveToCache(IRIFFStream *)

- ea: `0x18000ba54`
- end: `0x18000bbbb`
- name: `?SaveToCache@CClass@@QEAAJPEAUIRIFFStream@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(CClass *__hidden this, struct IRIFFStream *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009844`

## callees

- `0x1800015d0`
- `0x18000ba54`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CClass::SaveToCache(CClass *this, struct IRIFFStream *a2)
{
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  int v8; // ebx
  __int16 v9[2]; // [rsp+30h] [rbp-40h] BYREF
  int v10; // [rsp+34h] [rbp-3Ch] BYREF
  __int128 v11; // [rsp+38h] [rbp-38h] BYREF
  int v12; // [rsp+48h] [rbp-28h]
  __int128 v13; // [rsp+50h] [rbp-20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v9[0] = 0;
  v10 = 0;
  v12 = 0;
  v5 = *(_QWORD *)a2;
  v13 = 0;
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IRIFFStream *))(v5 + 56))(a2);
  if ( !v6 )
    return 2289570182LL;
  v7 = *(_QWORD *)a2;
  LODWORD(v11) = 1752394851;
  if ( (*(unsigned int (__fastcall **)(struct IRIFFStream *, __int128 *, _QWORD))(v7 + 40))(a2, &v11, 0) )
    goto LABEL_11;
  v9[0] = 16;
  if ( (*(int (__fastcall **)(__int64, __int16 *, __int64, int *))(*(_QWORD *)v6 + 32LL))(v6, v9, 2, &v10) >= 0
    && v10 == 2 )
  {
    v13 = *(_OWORD *)((char *)this + 36);
    v8 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, int *))(*(_QWORD *)v6 + 32LL))(v6, &v13, 16, &v10);
    if ( v8 < 0 || v10 != 16 )
    {
      v8 = -2005397226;
      goto LABEL_12;
    }
    if ( !(*(unsigned int (__fastcall **)(struct IRIFFStream *, __int128 *, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, &v11, 0) )
    {
LABEL_12:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      return (unsigned int)v8;
    }
LABEL_11:
    v8 = -2005397227;
    goto LABEL_12;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return 2289570070LL;
}

```

## disassembly

```asm
0x18000ba54  mov     [rsp-18h+arg_10], rbx
0x18000ba59  mov     [rsp-18h+arg_18], rsi
0x18000ba5e  push    rbp
0x18000ba5f  push    rdi
0x18000ba60  push    r14
0x18000ba62  mov     rbp, rsp
0x18000ba65  sub     rsp, 70h
0x18000ba69  mov     rax, cs:__security_cookie
0x18000ba70  xor     rax, rsp
0x18000ba73  mov     [rbp+var_10], rax
0x18000ba77  mov     rsi, rdx
0x18000ba7a  mov     rbx, rcx
0x18000ba7d  test    rdx, rdx
0x18000ba80  jnz     short loc_18000BA8C
0x18000ba82  mov     eax, 80004003h
0x18000ba87  jmp     loc_18000BB7D
0x18000ba8c  xor     eax, eax
0x18000ba8e  xorps   xmm0, xmm0
0x18000ba91  mov     [rbp+var_40], ax
0x18000ba95  xorps   xmm1, xmm1
0x18000ba98  mov     [rbp+var_3C], eax
0x18000ba9b  mov     rcx, rsi
0x18000ba9e  mov     [rbp+var_28], eax
0x18000baa1  mov     rax, [rdx]
0x18000baa4  movups  [rbp+var_20], xmm0
0x18000baa8  movups  [rbp+var_38], xmm1
0x18000baac  mov     rax, [rax+38h]
0x18000bab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bab5  mov     rdi, rax
0x18000bab8  test    rax, rax
0x18000babb  jnz     short loc_18000BAC7
0x18000babd  mov     eax, 88781186h
0x18000bac2  jmp     loc_18000BB7D
0x18000bac7  mov     rax, [rsi]
0x18000baca  lea     rdx, [rbp+var_38]
0x18000bace  xor     r8d, r8d
0x18000bad1  mov     dword ptr [rbp+var_38], 68736C63h
0x18000bad8  mov     rcx, rsi
0x18000badb  mov     rax, [rax+28h]
0x18000badf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bae4  test    eax, eax
0x18000bae6  jnz     short loc_18000BB67
0x18000bae8  lea     r14d, [rax+10h]
0x18000baec  mov     rcx, rdi
0x18000baef  mov     [rbp+var_40], r14w
0x18000baf4  lea     r9, [rbp+var_3C]
0x18000baf8  mov     rax, [rdi]
0x18000bafb  lea     r8d, [r14-0Eh]
0x18000baff  lea     rdx, [rbp+var_40]
0x18000bb03  mov     rax, [rax+20h]
0x18000bb07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb0c  test    eax, eax
0x18000bb0e  js      loc_18000BBA5
0x18000bb14  cmp     [rbp+var_3C], 2
0x18000bb18  jnz     loc_18000BBA5
0x18000bb1e  movups  xmm0, xmmword ptr [rbx+24h]
0x18000bb22  lea     r9, [rbp+var_3C]
0x18000bb26  mov     r8d, r14d
0x18000bb29  lea     rdx, [rbp+var_20]
0x18000bb2d  mov     rcx, rdi
0x18000bb30  movdqu  [rbp+var_20], xmm0
0x18000bb35  mov     rax, [rdi]
0x18000bb38  mov     rax, [rax+20h]
0x18000bb3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb41  mov     ebx, eax
0x18000bb43  test    eax, eax
0x18000bb45  js      short loc_18000BB9E
0x18000bb47  cmp     [rbp+var_3C], r14d
0x18000bb4b  jnz     short loc_18000BB9E
0x18000bb4d  mov     rdx, [rsi]
0x18000bb50  xor     r8d, r8d
0x18000bb53  mov     rcx, rsi
0x18000bb56  mov     rax, [rdx+20h]
0x18000bb5a  lea     rdx, [rbp+var_38]
0x18000bb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb63  test    eax, eax
0x18000bb65  jz      short loc_18000BB6C
0x18000bb67  mov     ebx, 88781115h
0x18000bb6c  mov     rax, [rdi]
0x18000bb6f  mov     rcx, rdi
0x18000bb72  mov     rax, [rax+10h]
0x18000bb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb7b  mov     eax, ebx
0x18000bb7d  mov     rcx, [rbp+var_10]
0x18000bb81  xor     rcx, rsp; StackCookie
0x18000bb84  call    __security_check_cookie
0x18000bb89  lea     r11, [rsp+70h+var_s0]
0x18000bb8e  mov     rbx, [r11+30h]
0x18000bb92  mov     rsi, [r11+38h]
0x18000bb96  mov     rsp, r11
0x18000bb99  pop     r14
0x18000bb9b  pop     rdi
0x18000bb9c  pop     rbp
0x18000bb9d  retn
0x18000bb9e  mov     ebx, 88781116h
0x18000bba3  jmp     short loc_18000BB6C
0x18000bba5  mov     rax, [rdi]
0x18000bba8  mov     rcx, rdi
0x18000bbab  mov     rax, [rax+10h]
0x18000bbaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbb4  mov     eax, 88781116h
0x18000bbb9  jmp     short loc_18000BB7D
```
