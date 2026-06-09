# SslGenerateSessionKeys

- ea: `0x180009aa0`
- end: `0x180009cc7`
- name: `SslGenerateSessionKeys`
- size: `551`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009a70`
- `0x180009aa0`
- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## string_xrefs

- `0x180009bd2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180009c1e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180009c34`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180009c94`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslGenerateSessionKeys(__int64 a1, __int64 a2, __int64 *a3, __int64 *a4, __int64 a5, int a6)
{
  NCRYPT_KEY_HANDLE *v8; // rdx
  __int64 v9; // rbp
  NCryptKeyName **v10; // r8
  PVOID *v11; // r9
  __int64 v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rdi
  int v16; // eax
  unsigned int v17; // ebx
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r9

  v9 = ValidateSslProvHandle(a1);
  if ( !v9 )
  {
    v17 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (_DWORD)v10,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        98);
    return NormalizeNteStatus(v17, v8, v10, v11, a5);
  }
  v12 = ValidateSslKeyHandle(v8);
  if ( !v12 )
  {
    v17 = -2146893786;
    v19 = 2154;
    v20 = 2148073510LL;
LABEL_21:
    DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v19);
    return NormalizeNteStatus(v17, v8, v10, v11, a5);
  }
  if ( !v10 || !v11 )
  {
    v17 = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (_DWORD)v10,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        113);
    return NormalizeNteStatus(v17, v8, v10, v11, a5);
  }
  v13 = SafeAllocaAllocateFromHeap(32);
  if ( !v13 )
  {
    v17 = -2146893810;
    v19 = 2177;
    v20 = 2148073486LL;
    goto LABEL_21;
  }
  v14 = SafeAllocaAllocateFromHeap(32);
  v15 = v14;
  if ( v14 )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, __int64, int))(v9 + 136))(
            *(_QWORD *)(v9 + 424),
            *(_QWORD *)(v12 + 16),
            v13 + 16,
            v14 + 16,
            a5,
            a6);
    v17 = v16;
    if ( v16 >= 0 )
    {
      *(_DWORD *)v13 = 32;
      *(_QWORD *)(v13 + 4) = 1145324610;
      *(_DWORD *)(v13 + 12) = 1;
      *(_QWORD *)(v13 + 24) = v9;
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 16));
      *a3 = v13;
      *(_DWORD *)v15 = 32;
      *(_QWORD *)(v15 + 4) = 1145324610;
      *(_DWORD *)(v15 + 12) = 1;
      *(_QWORD *)(v15 + 24) = v9;
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 16));
      *a4 = v15;
      v17 = 0;
      return NormalizeNteStatus(v17, v8, v10, v11, a5);
    }
    v21 = (unsigned int)v16;
    v22 = 2204;
  }
  else
  {
    v17 = -2146893810;
    v21 = 2148073486LL;
    v22 = 2186;
  }
  DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v22);
  MSCryptFree(v13);
  if ( v15 )
    MSCryptFree(v15);
  return NormalizeNteStatus(v17, v8, v10, v11, a5);
}

```

## disassembly

```asm
0x180009aa0  push    rbx
0x180009aa2  push    rbp
0x180009aa3  push    rsi
0x180009aa4  push    rdi
0x180009aa5  push    r12
0x180009aa7  push    r14
0x180009aa9  push    r15
0x180009aab  sub     rsp, 40h
0x180009aaf  mov     r14, r9
0x180009ab2  mov     r15, r8
0x180009ab5  call    ValidateSslProvHandle
0x180009aba  mov     rbp, rax
0x180009abd  test    rax, rax
0x180009ac0  jz      loc_180009BAC
0x180009ac6  mov     rcx, rdx
0x180009ac9  call    ValidateSslKeyHandle
0x180009ace  mov     rbx, rax
0x180009ad1  test    rax, rax
0x180009ad4  jz      loc_180009C6B
0x180009ada  test    r8, r8
0x180009add  jz      loc_180009BF8
0x180009ae3  test    r9, r9
0x180009ae6  jz      loc_180009BF8
0x180009aec  mov     r12d, 20h ; ' '
0x180009af2  mov     ecx, r12d
0x180009af5  call    SafeAllocaAllocateFromHeap
0x180009afa  mov     rsi, rax
0x180009afd  test    rax, rax
0x180009b00  jz      loc_180009C7D
0x180009b06  mov     ecx, r12d
0x180009b09  call    SafeAllocaAllocateFromHeap
0x180009b0e  mov     rdi, rax
0x180009b11  test    rax, rax
0x180009b14  jz      loc_180009CA5
0x180009b1a  mov     ecx, [rsp+78h+arg_28]
0x180009b21  lea     r9, [rax+10h]
0x180009b25  mov     rdx, [rbx+10h]
0x180009b29  lea     r8, [rsi+10h]
0x180009b2d  mov     rax, [rbp+88h]
0x180009b34  mov     dword ptr [rsp+78h+var_50], ecx
0x180009b38  mov     rcx, [rsp+78h+arg_20]
0x180009b40  mov     [rsp+78h+var_58], rcx
0x180009b45  mov     rcx, [rbp+1A8h]
0x180009b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b51  mov     ebx, eax
0x180009b53  test    eax, eax
0x180009b55  js      loc_180009CBA
0x180009b5b  mov     [rsi], r12d
0x180009b5e  mov     qword ptr [rsi+4], 44444442h
0x180009b66  mov     dword ptr [rsi+0Ch], 1
0x180009b6d  mov     [rsi+18h], rbp
0x180009b71  lock inc dword ptr [rbp+10h]
0x180009b75  mov     [r15], rsi
0x180009b78  mov     [rdi], r12d
0x180009b7b  mov     qword ptr [rdi+4], 44444442h
0x180009b83  mov     dword ptr [rdi+0Ch], 1
0x180009b8a  mov     [rdi+18h], rbp
0x180009b8e  lock inc dword ptr [rbp+10h]
0x180009b92  mov     [r14], rdi
0x180009b95  xor     ebx, ebx
0x180009b97  mov     ecx, ebx
0x180009b99  add     rsp, 40h
0x180009b9d  pop     r15
0x180009b9f  pop     r14
0x180009ba1  pop     r12
0x180009ba3  pop     rdi
0x180009ba4  pop     rsi
0x180009ba5  pop     rbp
0x180009ba6  pop     rbx
0x180009ba7  jmp     NormalizeNteStatus
0x180009bac  mov     ebx, 80090026h
0x180009bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bb8  lea     rax, WPP_GLOBAL_Control
0x180009bbf  cmp     rcx, rax
0x180009bc2  jz      short loc_180009B97
0x180009bc4  test    byte ptr [rcx+1Ch], 1
0x180009bc8  jz      short loc_180009B97
0x180009bca  mov     [rsp+78h+var_48], 862h
0x180009bd2  lea     rdx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009bd9  mov     [rsp+78h+var_50], rdx
0x180009bde  mov     dword ptr [rsp+78h+var_58], 80090026h
0x180009be6  mov     rcx, [rcx+10h]
0x180009bea  lea     r9, aStatus; "Status"
0x180009bf1  call    WPP_SF_sDsd
0x180009bf6  jmp     short loc_180009B97
0x180009bf8  mov     ebx, 80090027h
0x180009bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c04  lea     rax, WPP_GLOBAL_Control
0x180009c0b  cmp     rcx, rax
0x180009c0e  jz      short loc_180009B97
0x180009c10  test    byte ptr [rcx+1Ch], 1
0x180009c14  jz      short loc_180009B97
0x180009c16  mov     [rsp+78h+var_48], 871h
0x180009c1e  lea     rdx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009c25  mov     [rsp+78h+var_50], rdx
0x180009c2a  mov     dword ptr [rsp+78h+var_58], 80090027h
0x180009c32  jmp     short loc_180009BE6
0x180009c34  lea     rdx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009c3b  lea     rax, aStatus; "Status"
0x180009c42  mov     r8, rdx
0x180009c45  mov     rdx, rax
0x180009c48  call    DebugTraceError
0x180009c4d  mov     rcx, rsi
0x180009c50  call    MSCryptFree
0x180009c55  test    rdi, rdi
0x180009c58  jz      loc_180009B97
0x180009c5e  mov     rcx, rdi
0x180009c61  call    MSCryptFree
0x180009c66  jmp     loc_180009B97
0x180009c6b  mov     ebx, 80090026h
0x180009c70  mov     r9d, 86Ah
0x180009c76  mov     ecx, 80090026h
0x180009c7b  jmp     short loc_180009C8D
0x180009c7d  mov     ebx, 8009000Eh
0x180009c82  mov     r9d, 881h
0x180009c88  mov     ecx, 8009000Eh
0x180009c8d  lea     rdx, aStatus; "Status"
0x180009c94  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009c9b  call    DebugTraceError
0x180009ca0  jmp     loc_180009B97
0x180009ca5  mov     ebx, 8009000Eh
0x180009caa  mov     ecx, 8009000Eh
0x180009caf  mov     r9d, 88Ah
0x180009cb5  jmp     loc_180009C34
0x180009cba  mov     ecx, eax
0x180009cbc  mov     r9d, 89Ch
0x180009cc2  jmp     loc_180009C34
```
