# SslGeneratePreMasterKey

- ea: `0x18001b140`
- end: `0x18001b2ac`
- name: `SslGeneratePreMasterKey`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000e120`
- `0x18001b140`
- `0x180020010`

## string_xrefs

- `0x18001b178`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001b25c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslGeneratePreMasterKey(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7,
        int a8,
        __int64 a9,
        int a10)
{
  __int64 v13; // rsi
  unsigned int v14; // edi
  __int64 v15; // r9
  __int64 v16; // rcx
  NCRYPT_KEY_HANDLE *v17; // rdx
  NCryptKeyName **v18; // r8
  NCryptAlgorithmName **v19; // r9
  _OWORD *v20; // rax
  _OWORD *v21; // rbx
  int v22; // eax

  v13 = ValidateSslProvHandle(a1);
  if ( !v13 )
  {
    v14 = -2146893786;
    v15 = 3470;
    v16 = 2148073510LL;
LABEL_3:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v15);
    return NormalizeNteStatus(v14, v17, v18, v19, a5, a6, a7);
  }
  if ( !a3 )
  {
    v14 = -2146893785;
    v15 = 3477;
    v16 = 2148073511LL;
    goto LABEL_3;
  }
  if ( *(_WORD *)(v13 + 32) < 3u )
  {
    v14 = -2146893783;
    v15 = 3491;
    v16 = 2148073513LL;
    goto LABEL_3;
  }
  v20 = (_OWORD *)SafeAllocaAllocateFromHeap(32);
  v21 = v20;
  if ( !v20 )
  {
    v14 = -2146893810;
    v15 = 3503;
    v16 = 2148073486LL;
    goto LABEL_3;
  }
  *v20 = 0;
  v20[1] = 0;
  v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, _OWORD *, _QWORD, _DWORD, DWORD *, DWORD *, int, __int64, int))(v13 + 256))(
          *(_QWORD *)(v13 + 424),
          a2,
          v20 + 1,
          a4,
          (_DWORD)a5,
          a6,
          a7,
          a8,
          a9,
          a10);
  v14 = v22;
  if ( v22 >= 0 )
  {
    *(_DWORD *)v21 = 32;
    *(_QWORD *)((char *)v21 + 4) = 1145324610;
    *((_DWORD *)v21 + 3) = 1;
    *((_QWORD *)v21 + 3) = v13;
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 16));
    *a3 = v21;
  }
  else
  {
    DebugTraceError((unsigned int)v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3525);
    MSCryptFree(v21);
  }
  return NormalizeNteStatus(v14, v17, v18, v19, a5, a6, a7);
}

```

## disassembly

```asm
0x18001b140  push    rbx
0x18001b142  push    rbp
0x18001b143  push    rsi
0x18001b144  push    rdi
0x18001b145  push    r14
0x18001b147  sub     rsp, 60h
0x18001b14b  mov     edi, r9d
0x18001b14e  mov     r14, r8
0x18001b151  mov     rbp, rdx
0x18001b154  call    ValidateSslProvHandle
0x18001b159  mov     rsi, rax
0x18001b15c  test    rax, rax
0x18001b15f  jnz     short loc_18001B189
0x18001b161  mov     edi, 80090026h
0x18001b166  mov     r9d, 0D8Eh
0x18001b16c  mov     ecx, 80090026h
0x18001b171  lea     rdx, aStatus; "Status"
0x18001b178  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b17f  call    DebugTraceError
0x18001b184  jmp     loc_18001B29B
0x18001b189  test    r14, r14
0x18001b18c  jnz     short loc_18001B1A0
0x18001b18e  mov     edi, 80090027h
0x18001b193  mov     r9d, 0D95h
0x18001b199  mov     ecx, 80090027h
0x18001b19e  jmp     short loc_18001B171
0x18001b1a0  mov     eax, 3
0x18001b1a5  cmp     ax, [rsi+20h]
0x18001b1a9  jbe     short loc_18001B1BD
0x18001b1ab  mov     edi, 80090029h
0x18001b1b0  mov     r9d, 0DA3h
0x18001b1b6  mov     ecx, 80090029h
0x18001b1bb  jmp     short loc_18001B171
0x18001b1bd  mov     ecx, 20h ; ' '
0x18001b1c2  call    SafeAllocaAllocateFromHeap
0x18001b1c7  mov     rbx, rax
0x18001b1ca  test    rax, rax
0x18001b1cd  jnz     short loc_18001B1E1
0x18001b1cf  mov     edi, 8009000Eh
0x18001b1d4  mov     r9d, 0DAFh
0x18001b1da  mov     ecx, 8009000Eh
0x18001b1df  jmp     short loc_18001B171
0x18001b1e1  mov     ecx, [rsp+88h+arg_48]
0x18001b1e8  lea     r8, [rax+10h]
0x18001b1ec  mov     [rsp+88h+var_40], ecx
0x18001b1f0  xorps   xmm0, xmm0
0x18001b1f3  mov     rcx, [rsp+88h+arg_40]
0x18001b1fb  mov     r9d, edi
0x18001b1fe  mov     [rsp+88h+var_48], rcx
0x18001b203  mov     rdx, rbp
0x18001b206  mov     ecx, [rsp+88h+arg_38]
0x18001b20d  mov     [rsp+88h+var_50], ecx
0x18001b211  mov     rcx, [rsp+88h+arg_30]
0x18001b219  mov     [rsp+88h+var_58], rcx
0x18001b21e  mov     rcx, [rsp+88h+arg_28]
0x18001b226  mov     [rsp+88h+var_60], rcx
0x18001b22b  mov     ecx, dword ptr [rsp+88h+arg_20]
0x18001b232  movups  xmmword ptr [rax], xmm0
0x18001b235  mov     [rsp+88h+var_68], ecx
0x18001b239  movups  xmmword ptr [rax+10h], xmm0
0x18001b23d  mov     rcx, [rsi+1A8h]
0x18001b244  mov     rax, [rsi+100h]
0x18001b24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b250  mov     edi, eax
0x18001b252  test    eax, eax
0x18001b254  jns     short loc_18001B27B
0x18001b256  mov     r9d, 0DC5h
0x18001b25c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b263  lea     rdx, aStatus; "Status"
0x18001b26a  mov     ecx, eax
0x18001b26c  call    DebugTraceError
0x18001b271  mov     rcx, rbx
0x18001b274  call    MSCryptFree
0x18001b279  jmp     short loc_18001B29B
0x18001b27b  mov     dword ptr [rbx], 20h ; ' '
0x18001b281  mov     qword ptr [rbx+4], 44444442h
0x18001b289  mov     dword ptr [rbx+0Ch], 1
0x18001b290  mov     [rbx+18h], rsi
0x18001b294  lock inc dword ptr [rsi+10h]
0x18001b298  mov     [r14], rbx
0x18001b29b  mov     ecx, edi
0x18001b29d  add     rsp, 60h
0x18001b2a1  pop     r14
0x18001b2a3  pop     rdi
0x18001b2a4  pop     rsi
0x18001b2a5  pop     rbp
0x18001b2a6  pop     rbx
0x18001b2a7  jmp     NormalizeNteStatus
```
