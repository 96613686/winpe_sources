# Ssl3ComputeMasterKey

- ea: `0x180020248`
- end: `0x180020326`
- name: `Ssl3ComputeMasterKey`
- size: `222`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007990`
- `0x180007de4`
- `0x18001355c`

## callees

- `0x18000b654`
- `0x180020248`
- `0x18002032c`
- `0x180024ef0`

## string_xrefs

- `0x1800202d5`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`
- `0x1800202f8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`

## pseudocode

```c
__int64 __fastcall Ssl3ComputeMasterKey(
        __int64 a1,
        UCHAR *a2,
        ULONG a3,
        __int64 a4,
        int a5,
        _OWORD *a6,
        int a7,
        _OWORD *a8,
        int a9)
{
  __int128 v9; // xmm1
  __int128 v10; // xmm1
  int KeyMaterial; // eax
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v16; // [rsp+20h] [rbp-78h]
  _OWORD v17[4]; // [rsp+40h] [rbp-58h] BYREF

  if ( a7 != 32 || a9 != 32 )
  {
    v12 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\ssl3key.c", 75);
    v13 = 138;
    v14 = 3221225485LL;
    goto LABEL_6;
  }
  v9 = a6[1];
  v17[0] = *a6;
  v17[1] = v9;
  v10 = a8[1];
  v17[2] = *a8;
  v17[3] = v10;
  KeyMaterial = Ssl3GenerateKeyMaterial(a1, a2, a3, (UCHAR *)v17, v16, a4, 0x30u);
  v12 = KeyMaterial;
  if ( KeyMaterial < 0 )
  {
    v13 = 156;
    v14 = (unsigned int)KeyMaterial;
LABEL_6:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\ssl3key.c", v13);
  }
  return v12;
}

```

## disassembly

```asm
0x180020248  push    rbx
0x18002024a  sub     rsp, 90h
0x180020251  mov     rax, cs:__security_cookie
0x180020258  xor     rax, rsp
0x18002025b  mov     [rsp+98h+var_18], rax
0x180020263  cmp     [rsp+98h+arg_30], 20h ; ' '
0x18002026b  mov     rax, [rsp+98h+arg_28]
0x180020273  jnz     short loc_1800202D0
0x180020275  cmp     [rsp+98h+arg_40], 20h ; ' '
0x18002027d  jnz     short loc_1800202D0
0x18002027f  movups  xmm0, xmmword ptr [rax]
0x180020282  mov     [rsp+98h+var_68], 30h ; '0'
0x18002028a  movups  xmm1, xmmword ptr [rax+10h]
0x18002028e  mov     rax, [rsp+98h+arg_38]
0x180020296  movaps  [rsp+98h+var_58], xmm0
0x18002029b  movaps  [rsp+98h+var_48], xmm1
0x1800202a0  mov     [rsp+98h+var_70], r9
0x1800202a5  lea     r9, [rsp+98h+var_58]
0x1800202aa  movups  xmm0, xmmword ptr [rax]
0x1800202ad  movups  xmm1, xmmword ptr [rax+10h]
0x1800202b1  movaps  [rsp+98h+var_38], xmm0
0x1800202b6  movaps  [rsp+98h+var_28], xmm1
0x1800202bb  call    Ssl3GenerateKeyMaterial
0x1800202c0  mov     ebx, eax
0x1800202c2  test    eax, eax
0x1800202c4  jns     short loc_18002030B
0x1800202c6  mov     r9d, 9Ch
0x1800202cc  mov     ecx, eax
0x1800202ce  jmp     short loc_1800202F8
0x1800202d0  mov     ebx, 0C000000Dh
0x1800202d5  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800202dc  mov     ecx, ebx
0x1800202de  lea     rdx, aStatus; "Status"
0x1800202e5  mov     r9d, 4Bh ; 'K'
0x1800202eb  call    DebugTraceError
0x1800202f0  mov     r9d, 8Ah
0x1800202f6  mov     ecx, ebx
0x1800202f8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800202ff  lea     rdx, aStatus; "Status"
0x180020306  call    DebugTraceError
0x18002030b  mov     eax, ebx
0x18002030d  mov     rcx, [rsp+98h+var_18]
0x180020315  xor     rcx, rsp; StackCookie
0x180020318  call    __security_check_cookie
0x18002031d  add     rsp, 90h
0x180020324  pop     rbx
0x180020325  retn
```
