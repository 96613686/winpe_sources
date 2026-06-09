# SslGetProviderProperty

- ea: `0x18001b2c0`
- end: `0x18001b47d`
- name: `SslGetProviderProperty`
- size: `445`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000e120`
- `0x180011cd0`
- `0x18001b2c0`
- `0x180020010`

## string_xrefs

- `0x18001b3cc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001b455`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslGetProviderProperty(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7)
{
  __int64 v10; // rdx
  __int64 v11; // rbp
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  unsigned __int64 v15; // rax
  __int64 *v16; // rdi
  __int64 *v17; // rax
  int v18; // eax
  NCRYPT_KEY_HANDLE *v19; // rdx
  NCryptKeyName **v20; // r8
  NCryptAlgorithmName **v21; // r9
  __int64 v22; // rax
  __int64 v24[9]; // [rsp+40h] [rbp-48h] BYREF

  v24[0] = 0;
  v11 = ValidateSslProvHandle(a1);
  if ( !v11 )
  {
    v12 = -2146893786;
    v13 = 2358;
    v14 = 2148073510LL;
LABEL_29:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v13);
    return NormalizeNteStatus(v12, v19, v20, v21, a5, a6, a7);
  }
  if ( !a2 )
  {
    v13 = 2365;
LABEL_28:
    v12 = -2146893785;
    v14 = 2148073511LL;
    goto LABEL_29;
  }
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v10 + 2 * v15) );
  if ( v15 > 0x40 )
  {
    v13 = 2371;
    goto LABEL_28;
  }
  if ( !a3 || !a4 )
  {
    v13 = 2378;
    goto LABEL_28;
  }
  v16 = 0;
  if ( a5 )
  {
    v24[0] = *(_QWORD *)a5;
    if ( !v24[0] )
    {
      v17 = (__int64 *)SafeAllocaAllocateFromHeap(32);
      v16 = v17;
      if ( !v17 )
      {
        v12 = -2146893810;
        v13 = 2400;
        v14 = 2148073486LL;
        goto LABEL_29;
      }
      *(_OWORD *)v17 = 0;
      *((_OWORD *)v17 + 1) = 0;
    }
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, __int64 *, _DWORD))(v11 + 152))(
          *(_QWORD *)(v11 + 424),
          a2,
          a3,
          a4,
          v24,
          (_DWORD)a6);
  v12 = v18;
  if ( v18 >= 0 )
  {
    if ( a5 )
    {
      if ( v16 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 16));
        *v16 = v11;
        v16[1] = v24[0];
        MSCryptAddMemoryBuffer(&SslpProviderBufferList, v16);
        v22 = v24[0];
        v16 = 0;
      }
      else
      {
        v22 = v24[0];
        if ( v24[0] != *(_QWORD *)a5 )
        {
          v12 = -2146893792;
          v13 = 2438;
          v14 = 2148073504LL;
          goto LABEL_29;
        }
      }
      *(_QWORD *)a5 = v22;
    }
    v12 = 0;
  }
  else
  {
    DebugTraceError((unsigned int)v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 2421);
  }
  if ( v16 )
    MSCryptFree(v16);
  return NormalizeNteStatus(v12, v19, v20, v21, a5, a6, a7);
}

```

## disassembly

```asm
0x18001b2c0  push    rbx
0x18001b2c2  push    rbp
0x18001b2c3  push    rsi
0x18001b2c4  push    rdi
0x18001b2c5  push    r12
0x18001b2c7  push    r14
0x18001b2c9  push    r15
0x18001b2cb  sub     rsp, 50h
0x18001b2cf  xor     r12d, r12d
0x18001b2d2  mov     r14, r9
0x18001b2d5  mov     [rsp+88h+var_48], r12
0x18001b2da  mov     r15, r8
0x18001b2dd  mov     rbx, rdx
0x18001b2e0  call    ValidateSslProvHandle
0x18001b2e5  mov     rbp, rax
0x18001b2e8  test    rax, rax
0x18001b2eb  jnz     short loc_18001B302
0x18001b2ed  mov     ebx, 80090026h
0x18001b2f2  mov     r9d, 936h
0x18001b2f8  mov     ecx, 80090026h
0x18001b2fd  jmp     loc_18001B455
0x18001b302  test    rbx, rbx
0x18001b305  jnz     short loc_18001B312
0x18001b307  mov     r9d, 93Dh
0x18001b30d  jmp     loc_18001B44B
0x18001b312  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b316  inc     rax
0x18001b319  cmp     [rdx+rax*2], r12w
0x18001b31e  jnz     short loc_18001B316
0x18001b320  cmp     rax, 40h ; '@'
0x18001b324  jbe     short loc_18001B331
0x18001b326  mov     r9d, 943h
0x18001b32c  jmp     loc_18001B44B
0x18001b331  test    r15, r15
0x18001b334  jz      loc_18001B445
0x18001b33a  test    r14, r14
0x18001b33d  jz      loc_18001B445
0x18001b343  mov     rsi, [rsp+88h+arg_20]
0x18001b34b  mov     rdi, r12
0x18001b34e  test    rsi, rsi
0x18001b351  jz      short loc_18001B38F
0x18001b353  mov     rax, [rsi]
0x18001b356  mov     [rsp+88h+var_48], rax
0x18001b35b  test    rax, rax
0x18001b35e  jnz     short loc_18001B38F
0x18001b360  lea     ecx, [rax+20h]
0x18001b363  call    SafeAllocaAllocateFromHeap
0x18001b368  mov     rdi, rax
0x18001b36b  test    rax, rax
0x18001b36e  jnz     short loc_18001B385
0x18001b370  mov     ebx, 8009000Eh
0x18001b375  mov     r9d, 960h
0x18001b37b  mov     ecx, 8009000Eh
0x18001b380  jmp     loc_18001B455
0x18001b385  xorps   xmm0, xmm0
0x18001b388  movups  xmmword ptr [rax], xmm0
0x18001b38b  movups  xmmword ptr [rax+10h], xmm0
0x18001b38f  mov     ecx, [rsp+88h+arg_28]
0x18001b396  lea     rax, [rsp+88h+var_48]
0x18001b39b  mov     [rsp+88h+var_60], ecx
0x18001b39f  mov     r9, r14
0x18001b3a2  mov     rcx, [rbp+1A8h]
0x18001b3a9  mov     r8, r15
0x18001b3ac  mov     [rsp+88h+var_68], rax
0x18001b3b1  mov     rdx, rbx
0x18001b3b4  mov     rax, [rbp+98h]
0x18001b3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3c0  mov     ebx, eax
0x18001b3c2  test    eax, eax
0x18001b3c4  jns     short loc_18001B3E3
0x18001b3c6  mov     r9d, 975h
0x18001b3cc  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b3d3  lea     rdx, aStatus; "Status"
0x18001b3da  mov     ecx, eax
0x18001b3dc  call    DebugTraceError
0x18001b3e1  jmp     short loc_18001B436
0x18001b3e3  test    rsi, rsi
0x18001b3e6  jz      short loc_18001B433
0x18001b3e8  test    rdi, rdi
0x18001b3eb  jnz     short loc_18001B409
0x18001b3ed  mov     rax, [rsp+88h+var_48]
0x18001b3f2  cmp     rax, [rsi]
0x18001b3f5  jz      short loc_18001B430
0x18001b3f7  mov     ebx, 80090020h
0x18001b3fc  mov     r9d, 986h
0x18001b402  mov     ecx, 80090020h
0x18001b407  jmp     short loc_18001B455
0x18001b409  lock inc dword ptr [rbp+10h]
0x18001b40d  mov     [rdi], rbp
0x18001b410  lea     rcx, SslpProviderBufferList
0x18001b417  mov     rax, [rsp+88h+var_48]
0x18001b41c  mov     rdx, rdi
0x18001b41f  mov     [rdi+8], rax
0x18001b423  call    MSCryptAddMemoryBuffer
0x18001b428  mov     rax, [rsp+88h+var_48]
0x18001b42d  mov     rdi, r12
0x18001b430  mov     [rsi], rax
0x18001b433  mov     ebx, r12d
0x18001b436  test    rdi, rdi
0x18001b439  jz      short loc_18001B468
0x18001b43b  mov     rcx, rdi
0x18001b43e  call    MSCryptFree
0x18001b443  jmp     short loc_18001B468
0x18001b445  mov     r9d, 94Ah
0x18001b44b  mov     ebx, 80090027h
0x18001b450  mov     ecx, 80090027h
0x18001b455  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b45c  lea     rdx, aStatus; "Status"
0x18001b463  call    DebugTraceError
0x18001b468  mov     ecx, ebx
0x18001b46a  add     rsp, 50h
0x18001b46e  pop     r15
0x18001b470  pop     r14
0x18001b472  pop     r12
0x18001b474  pop     rdi
0x18001b475  pop     rsi
0x18001b476  pop     rbp
0x18001b477  pop     rbx
0x18001b478  jmp     NormalizeNteStatus
```
