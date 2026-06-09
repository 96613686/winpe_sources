# InvokeCreateSubscription

- ea: `0x180040ba0`
- end: `0x180040db3`
- name: `InvokeCreateSubscription`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x1800077a0`
- `0x180007800`
- `0x180007ad0`
- `0x180040b00`
- `0x180040ba0`
- `0x180040e2c`
- `0x180041220`
- `0x180044698`
- `0x1800446dc`
- `0x18004472c`
- `0x180044842`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!free` at `0x180040d8a`
- `msvcrt!free` at `0x180040d8a`

## pseudocode

```c
void __fastcall InvokeCreateSubscription(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // r14
  __int64 SubscriptionIdentifier; // rax
  void *v12; // rbx
  unsigned int v13; // eax
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v16[42]; // [rsp+40h] [rbp-C0h] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v8 = *(_QWORD *)(a3 + 48);
  v9 = *(_QWORD *)(a4 + 48);
  v10 = EnableErrorDetails();
  SubscriptionIdentifier = GetSubscriptionIdentifier(v8, v9);
  v12 = (void *)SubscriptionIdentifier;
  if ( !SubscriptionIdentifier )
  {
    RevertErrorDetails(v10);
    v13 = 27;
    goto LABEL_18;
  }
  if ( CimBaseCache_Find(a2, SubscriptionIdentifier) )
  {
    RevertErrorDetails(v10);
    v13 = 11;
    goto LABEL_18;
  }
  if ( !Subscription_New(a1, a2, a3, a4) )
  {
    CatchErrorDetails(v10, &v15);
    PostCimErrorOrAbortOnFailure(a1, v15);
    return;
  }
  RevertErrorDetails(v10);
  if ( !a1 || !*(_QWORD *)a1 )
    goto LABEL_17;
  v13 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD *))(*(_QWORD *)a1 + 24LL))(
          a1,
          &OMF_IndicationSubscription_rtti,
          v16);
  if ( v13
    || (v14 = a3 + 208,
        (v13 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 *, __int64, _DWORD))(v16[0] + 80LL))(
                 v16,
                 0,
                 &v14,
                 14,
                 0)) != 0)
    || (v14 = a4 + 168,
        (v13 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *, __int64, _DWORD))(v16[0] + 80LL))(
                 v16,
                 1,
                 &v14,
                 14,
                 0)) != 0) )
  {
LABEL_18:
    PostErrorOrAbortOnFailure(a1, v13);
    if ( !v12 )
      return;
    goto LABEL_19;
  }
  if ( !*(_QWORD *)a1 )
    goto LABEL_17;
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 8LL))(a1, v16);
  if ( v13 )
    goto LABEL_18;
  if ( !v16[0] )
  {
LABEL_17:
    v13 = 4;
    goto LABEL_18;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 8LL))(v16);
  if ( v13 )
    goto LABEL_18;
  PostResultOrAbortOnFailure(a1, 0);
LABEL_19:
  free(v12);
}

```

## disassembly

```asm
0x180040ba0  push    rbp
0x180040ba2  push    rbx
0x180040ba3  push    rsi
0x180040ba4  push    rdi
0x180040ba5  push    r12
0x180040ba7  push    r13
0x180040ba9  push    r14
0x180040bab  push    r15
0x180040bad  lea     rbp, [rsp-0A8h]
0x180040bb5  sub     rsp, 1A8h
0x180040bbc  mov     rax, cs:__security_cookie
0x180040bc3  xor     rax, rsp
0x180040bc6  mov     [rbp+0E0h+var_50], rax
0x180040bcd  mov     r13, r8
0x180040bd0  mov     [rsp+1E0h+var_1A8], 0
0x180040bd9  mov     r15, rdx
0x180040bdc  mov     rsi, rcx
0x180040bdf  xor     edx, edx; Val
0x180040be1  lea     rcx, [rsp+1E0h+var_1A0]; void *
0x180040be6  mov     r8d, 150h; Size
0x180040bec  mov     r12, r9
0x180040bef  call    memset_0
0x180040bf4  mov     rdi, [r13+30h]
0x180040bf8  mov     rbx, [r12+30h]
0x180040bfd  call    EnableErrorDetails
0x180040c02  mov     rdx, rbx
0x180040c05  mov     rcx, rdi
0x180040c08  mov     r14, rax
0x180040c0b  call    GetSubscriptionIdentifier
0x180040c10  mov     rbx, rax
0x180040c13  test    rax, rax
0x180040c16  jnz     short loc_180040C28
0x180040c18  mov     rcx, r14
0x180040c1b  call    RevertErrorDetails
0x180040c20  lea     eax, [rbx+1Bh]
0x180040c23  jmp     loc_180040D78
0x180040c28  mov     rdx, rbx
0x180040c2b  mov     rcx, r15
0x180040c2e  call    CimBaseCache_Find
0x180040c33  test    rax, rax
0x180040c36  jz      short loc_180040C4A
0x180040c38  mov     rcx, r14
0x180040c3b  call    RevertErrorDetails
0x180040c40  mov     eax, 0Bh
0x180040c45  jmp     loc_180040D78
0x180040c4a  mov     r9, r12
0x180040c4d  mov     r8, r13
0x180040c50  mov     rdx, r15
0x180040c53  mov     rcx, rsi
0x180040c56  call    Subscription_New
0x180040c5b  mov     rcx, r14
0x180040c5e  test    rax, rax
0x180040c61  jnz     short loc_180040C7F
0x180040c63  lea     rdx, [rsp+1E0h+var_1A8]
0x180040c68  call    CatchErrorDetails
0x180040c6d  mov     rdx, [rsp+1E0h+var_1A8]
0x180040c72  mov     rcx, rsi
0x180040c75  call    PostCimErrorOrAbortOnFailure
0x180040c7a  jmp     loc_180040D90
0x180040c7f  call    RevertErrorDetails
0x180040c84  test    rsi, rsi
0x180040c87  jz      loc_180040D73
0x180040c8d  mov     rax, [rsi]
0x180040c90  test    rax, rax
0x180040c93  jz      loc_180040D73
0x180040c99  mov     rax, [rax+18h]
0x180040c9d  lea     r8, [rsp+1E0h+var_1A0]
0x180040ca2  lea     rdx, OMF_IndicationSubscription_rtti
0x180040ca9  mov     rcx, rsi
0x180040cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cb1  test    eax, eax
0x180040cb3  jnz     loc_180040D78
0x180040cb9  lea     rax, [r13+0D0h]
0x180040cc0  mov     [rsp+1E0h+var_1C0], 0
0x180040cc8  mov     [rsp+1E0h+var_1B0], rax
0x180040ccd  lea     r8, [rsp+1E0h+var_1B0]
0x180040cd2  mov     rax, [rsp+1E0h+var_1A0]
0x180040cd7  lea     rcx, [rsp+1E0h+var_1A0]
0x180040cdc  mov     edi, 0Eh
0x180040ce1  xor     edx, edx
0x180040ce3  mov     r9d, edi
0x180040ce6  mov     rax, [rax+50h]
0x180040cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cef  test    eax, eax
0x180040cf1  jnz     loc_180040D78
0x180040cf7  lea     rax, [r12+0A8h]
0x180040cff  mov     [rsp+1E0h+var_1C0], 0
0x180040d07  mov     [rsp+1E0h+var_1B0], rax
0x180040d0c  lea     r8, [rsp+1E0h+var_1B0]
0x180040d11  mov     rax, [rsp+1E0h+var_1A0]
0x180040d16  lea     edx, [rdi-0Dh]
0x180040d19  mov     r9d, edi
0x180040d1c  lea     rcx, [rsp+1E0h+var_1A0]
0x180040d21  mov     rax, [rax+50h]
0x180040d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d2a  test    eax, eax
0x180040d2c  jnz     short loc_180040D78
0x180040d2e  mov     rax, [rsi]
0x180040d31  test    rax, rax
0x180040d34  jz      short loc_180040D73
0x180040d36  mov     rax, [rax+8]
0x180040d3a  lea     rdx, [rsp+1E0h+var_1A0]
0x180040d3f  mov     rcx, rsi
0x180040d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d47  test    eax, eax
0x180040d49  jnz     short loc_180040D78
0x180040d4b  mov     rax, [rsp+1E0h+var_1A0]
0x180040d50  test    rax, rax
0x180040d53  jz      short loc_180040D73
0x180040d55  mov     rax, [rax+8]
0x180040d59  lea     rcx, [rsp+1E0h+var_1A0]
0x180040d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d63  test    eax, eax
0x180040d65  jnz     short loc_180040D78
0x180040d67  xor     edx, edx
0x180040d69  mov     rcx, rsi
0x180040d6c  call    PostResultOrAbortOnFailure
0x180040d71  jmp     short loc_180040D87
0x180040d73  mov     eax, 4
0x180040d78  mov     edx, eax
0x180040d7a  mov     rcx, rsi
0x180040d7d  call    PostErrorOrAbortOnFailure
0x180040d82  test    rbx, rbx
0x180040d85  jz      short loc_180040D90
0x180040d87  mov     rcx, rbx; Block
0x180040d8a  call    cs:__imp_free
0x180040d90  mov     rcx, [rbp+0E0h+var_50]
0x180040d97  xor     rcx, rsp; StackCookie
0x180040d9a  call    __security_check_cookie
0x180040d9f  add     rsp, 1A8h
0x180040da6  pop     r15
0x180040da8  pop     r14
0x180040daa  pop     r13
0x180040dac  pop     r12
0x180040dae  pop     rdi
0x180040daf  pop     rsi
0x180040db0  pop     rbx
0x180040db1  pop     rbp
0x180040db2  retn
```
