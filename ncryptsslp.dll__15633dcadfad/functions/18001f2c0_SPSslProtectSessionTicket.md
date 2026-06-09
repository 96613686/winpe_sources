# SPSslProtectSessionTicket

- ea: `0x18001f2c0`
- end: `0x18001f3a2`
- name: `SPSslProtectSessionTicket`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x18000b654`
- `0x18001f2c0`
- `0x180021170`
- `0x180023a9c`

## string_xrefs

- `0x18001f387`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslProtectSessionTicket(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  __int64 v7; // r10
  __int64 v8; // r8
  int v9; // r9d
  __int64 v10; // r11
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // eax

  SslpValidateSessionTicketKeyHandle(a2);
  if ( !SslpValidateProvHandle(v7) || !v10 )
  {
    v11 = -2146893786;
    v12 = 7265;
    v13 = 2148073510LL;
    goto LABEL_11;
  }
  if ( !v9 || !a6 )
  {
    v11 = -2146893785;
    v12 = 7274;
    v13 = 2148073511LL;
    goto LABEL_11;
  }
  if ( a7 )
  {
    v11 = -2146893815;
    v12 = 7281;
    v13 = 2148073481LL;
LABEL_11:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v12);
    return v11;
  }
  v14 = ProtectSessionTicket(
          *(_QWORD *)(v10 + 64),
          *(unsigned int *)(v10 + 56),
          *(_QWORD *)(v10 + 16),
          *(_QWORD *)(v10 + 48),
          *(_DWORD *)(v10 + 40),
          v8,
          v9,
          a5,
          a6);
  v11 = v14;
  if ( v14 < 0 )
  {
    v12 = 7299;
    v13 = (unsigned int)v14;
    goto LABEL_11;
  }
  return v11;
}

```

## disassembly

```asm
0x18001f2c0  push    rbx
0x18001f2c2  sub     rsp, 50h
0x18001f2c6  mov     r10, rcx
0x18001f2c9  mov     rcx, rdx
0x18001f2cc  call    SslpValidateSessionTicketKeyHandle
0x18001f2d1  mov     rcx, r10
0x18001f2d4  mov     r11, rax
0x18001f2d7  call    SslpValidateProvHandle
0x18001f2dc  test    rax, rax
0x18001f2df  jz      loc_18001F377
0x18001f2e5  test    r11, r11
0x18001f2e8  jz      loc_18001F377
0x18001f2ee  test    r9d, r9d
0x18001f2f1  jz      short loc_18001F365
0x18001f2f3  mov     rax, [rsp+58h+arg_28]
0x18001f2fb  test    rax, rax
0x18001f2fe  jz      short loc_18001F365
0x18001f300  cmp     [rsp+58h+arg_30], 0
0x18001f308  jz      short loc_18001F31C
0x18001f30a  mov     ebx, 80090009h
0x18001f30f  mov     r9d, 1C71h
0x18001f315  mov     ecx, 80090009h
0x18001f31a  jmp     short loc_18001F387
0x18001f31c  mov     edx, [r11+38h]
0x18001f320  mov     rcx, [r11+40h]
0x18001f324  mov     [rsp+58h+var_18], rax
0x18001f329  mov     rax, [rsp+58h+arg_20]
0x18001f331  mov     [rsp+58h+var_20], rax
0x18001f336  mov     eax, [r11+28h]
0x18001f33a  mov     [rsp+58h+var_28], r9d
0x18001f33f  mov     r9, [r11+30h]
0x18001f343  mov     [rsp+58h+var_30], r8
0x18001f348  mov     r8, [r11+10h]
0x18001f34c  mov     [rsp+58h+var_38], eax
0x18001f350  call    ProtectSessionTicket
0x18001f355  mov     ebx, eax
0x18001f357  test    eax, eax
0x18001f359  jns     short loc_18001F39A
0x18001f35b  mov     r9d, 1C83h
0x18001f361  mov     ecx, eax
0x18001f363  jmp     short loc_18001F387
0x18001f365  mov     ebx, 80090027h
0x18001f36a  mov     r9d, 1C6Ah
0x18001f370  mov     ecx, 80090027h
0x18001f375  jmp     short loc_18001F387
0x18001f377  mov     ebx, 80090026h
0x18001f37c  mov     r9d, 1C61h
0x18001f382  mov     ecx, 80090026h
0x18001f387  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f38e  lea     rdx, aStatus; "Status"
0x18001f395  call    DebugTraceError
0x18001f39a  mov     eax, ebx
0x18001f39c  add     rsp, 50h
0x18001f3a0  pop     rbx
0x18001f3a1  retn
```
