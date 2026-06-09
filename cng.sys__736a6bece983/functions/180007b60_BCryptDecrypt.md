# BCryptDecrypt

- ea: `0x180007b60`
- end: `0x180007db2`
- name: `BCryptDecrypt`
- size: `594`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbInput, ULONG cbInput, void *pPaddingInfo, PUCHAR pbIV, ULONG cbIV, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180007760`
- `0x18003f080`
- `0x18003fb20`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180007b60`
- `0x1800082b0`
- `0x1800363a0`
- `0x180049978`
- `0x18004cc10`
- `0x18005adc0`
- `0x18005c4ec`
- `0x1800699a8`
- `0x18009f6d0`

## string_xrefs

- `0x180007cc4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a0ebe`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a0fbe`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDecrypt(
        BCRYPT_KEY_HANDLE hKey,
        PUCHAR pbInput,
        ULONG cbInput,
        void *pPaddingInfo,
        PUCHAR pbIV,
        ULONG cbIV,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  ULONG v10; // ebx
  __int64 v11; // rsi
  __int64 v15; // rax
  __int64 v16; // r10
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(_QWORD, PUCHAR, _QWORD, _QWORD, PUCHAR, ULONG, void *, _DWORD, int *, ULONG); // r11
  int v19; // eax
  NTSTATUS v20; // ebx
  void *v21; // rdi
  unsigned int v22; // r13d
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // r15d
  int v30; // r13d
  __int64 v31; // rax
  PUCHAR v32; // r14
  ULONG v33; // eax
  int v34; // eax
  ULONG v35; // [rsp+60h] [rbp-58h] BYREF
  int v36; // [rsp+64h] [rbp-54h] BYREF
  __int64 (__fastcall *v37)(_QWORD, PUCHAR, _QWORD, _QWORD, PUCHAR, ULONG, void *, _DWORD, int *, ULONG); // [rsp+68h] [rbp-50h]
  __int64 v38; // [rsp+70h] [rbp-48h]
  int v40; // [rsp+D8h] [rbp+20h]

  v40 = (int)pPaddingInfo;
  v10 = 0;
  v11 = cbInput;
  v35 = 0;
  v36 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqqdqdqD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      24,
      cbInput,
      hKey,
      pPaddingInfo,
      pbInput,
      cbInput,
      pbOutput,
      cbOutput,
      pcbResult,
      dwFlags);
  if ( !pcbResult )
  {
    v20 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)pbInput,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        20);
    return v20;
  }
  v15 = ValidateBaseKeyHandle(hKey);
  v38 = v15;
  v16 = v15;
  if ( !v15 )
  {
    v20 = -1073741816;
    v24 = 4124;
    v25 = 3221225480LL;
    goto LABEL_27;
  }
  v17 = *(_QWORD *)(v15 + 8);
  if ( *(_DWORD *)(v17 + 36) == 1 )
  {
    v18 = *(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD, PUCHAR, ULONG, void *, _DWORD, int *, ULONG))(v17 + 104);
  }
  else
  {
    if ( *(_DWORD *)(v17 + 36) != 3 )
    {
      v20 = -1073741637;
      v24 = 4161;
      v25 = 3221225659LL;
      goto LABEL_27;
    }
    v19 = ShouldRouterPadEncryption(*(unsigned int *)(v17 + 440), dwFlags, &v35);
    v20 = v19;
    if ( v19 < 0 )
    {
      v24 = 4154;
LABEL_20:
      v25 = (unsigned int)v19;
      goto LABEL_27;
    }
    v18 = *(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD, PUCHAR, ULONG, void *, _DWORD, int *, ULONG))(v17 + 112);
    v10 = v35;
  }
  v37 = v18;
  if ( v10 )
  {
    if ( 2 * (int)v11 >= (unsigned int)v11 )
    {
      v29 = SymCryptRoundUpPow2Sizet(v11);
      v30 = v11;
      if ( v29 < 0x20 )
        v29 = 32;
      if ( pbOutput )
        v30 = 0;
      v22 = v29 + v30;
      v31 = MSCryptAlloc(v22, v26, v27, v28);
      v21 = (void *)v31;
      if ( v31 )
      {
        if ( pbOutput )
          v32 = pbOutput;
        else
          v32 = (PUCHAR)(v31 + v29);
        v33 = v11;
        if ( pbOutput )
          v33 = cbOutput;
        v35 = v33;
        v34 = v37(*(_QWORD *)(v38 + 16), pbInput, (unsigned int)v11, 0, pbIV, cbIV, v21, v11, &v36, dwFlags);
        v20 = v34;
        if ( v34 < 0 )
        {
          DebugTraceError((unsigned int)v34, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 4234);
          goto LABEL_25;
        }
        CheckEncryptionPadding(dwFlags, v40, (_DWORD)v21, v36, v29, (__int64)v32, v35, (__int64)pcbResult);
LABEL_11:
        v20 = 0;
        if ( !v21 )
          return v20;
LABEL_25:
        SymCryptWipeAsm(v21, v22);
        MSCryptFree(v21);
        return v20;
      }
      v20 = -1073741801;
      v24 = 4203;
      v25 = 3221225495LL;
    }
    else
    {
      v20 = -1073741675;
      v24 = 4176;
      v25 = 3221225621LL;
    }
LABEL_27:
    DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v24);
    return v20;
  }
  v19 = v18(
          *(_QWORD *)(v16 + 16),
          pbInput,
          (unsigned int)v11,
          pPaddingInfo,
          pbIV,
          cbIV,
          pbOutput,
          cbOutput,
          (int *)pcbResult,
          dwFlags);
  v20 = v19;
  if ( *(_DWORD *)(v17 + 36) != 3 || (dwFlags & 2) == 0 )
  {
    v21 = 0;
    v22 = 0;
    if ( v19 >= 0 )
      goto LABEL_11;
    v24 = 4281;
    goto LABEL_20;
  }
  return v20;
}

```

## disassembly

```asm
0x180007b60  mov     rax, rsp
0x180007b63  mov     [rax+8], rbx
0x180007b67  mov     [rax+20h], r9
0x180007b6b  mov     [rax+10h], rdx
0x180007b6f  push    rbp
0x180007b70  push    rsi
0x180007b71  push    rdi
0x180007b72  push    r12
0x180007b74  push    r13
0x180007b76  push    r14
0x180007b78  push    r15
0x180007b7a  sub     rsp, 80h
0x180007b81  xor     ebx, ebx
0x180007b83  mov     esi, r8d
0x180007b86  mov     [rax-58h], ebx
0x180007b89  mov     r15, r9
0x180007b8c  mov     r13, rdx
0x180007b8f  mov     dword ptr [rax-54h], 0
0x180007b96  mov     r14, rcx
0x180007b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ba0  lea     rax, WPP_GLOBAL_Control
0x180007ba7  mov     ebp, [rsp+0B8h+dwFlags]
0x180007bae  mov     r12, [rsp+0B8h+pbOutput]
0x180007bb6  mov     rdi, [rsp+0B8h+pcbResult]
0x180007bbe  cmp     rcx, rax
0x180007bc1  jz      short loc_180007BD5
0x180007bc3  mov     eax, [rcx+2Ch]
0x180007bc6  test    al, 4
0x180007bc8  jnz     loc_180007CEE
0x180007bce  lea     rax, WPP_GLOBAL_Control
0x180007bd5  test    rdi, rdi
0x180007bd8  jz      loc_180007CA8
0x180007bde  mov     rcx, r14
0x180007be1  call    ValidateBaseKeyHandle
0x180007be6  mov     [rsp+0B8h+var_48], rax
0x180007beb  mov     r10, rax
0x180007bee  test    rax, rax
0x180007bf1  jz      loc_180007D2B
0x180007bf7  mov     rdi, [rax+8]
0x180007bfb  mov     ecx, [rdi+24h]
0x180007bfe  sub     ecx, 1
0x180007c01  jnz     loc_180007D40
0x180007c07  mov     r11, [rdi+68h]
0x180007c0b  mov     [rsp+0B8h+var_50], r11
0x180007c10  test    ebx, ebx
0x180007c12  jnz     loc_180007D6B
0x180007c18  mov     rax, [rsp+0B8h+pcbResult]
0x180007c20  mov     r9, r15
0x180007c23  mov     rcx, [r10+10h]
0x180007c27  mov     r8d, esi
0x180007c2a  mov     dword ptr [rsp+0B8h+var_70], ebp
0x180007c2e  mov     rdx, r13
0x180007c31  mov     [rsp+0B8h+var_78], rax
0x180007c36  mov     eax, [rsp+0B8h+cbOutput]
0x180007c3d  mov     dword ptr [rsp+0B8h+var_80], eax
0x180007c41  mov     eax, [rsp+0B8h+cbIV]
0x180007c48  mov     [rsp+0B8h+var_88], r12
0x180007c4d  mov     dword ptr [rsp+0B8h+var_90], eax
0x180007c51  mov     rax, [rsp+0B8h+pbIV]
0x180007c59  mov     [rsp+0B8h+var_98], rax
0x180007c5e  mov     rax, r11
0x180007c61  call    _guard_dispatch_icall
0x180007c66  cmp     dword ptr [rdi+24h], 3
0x180007c6a  mov     ebx, eax
0x180007c6c  jz      loc_180007D8B
0x180007c72  xor     edi, edi
0x180007c74  xor     r13d, r13d
0x180007c77  test    eax, eax
0x180007c79  js      loc_180007D5E
0x180007c7f  xor     ebx, ebx
0x180007c81  test    rdi, rdi
0x180007c84  jnz     loc_180007D9A
0x180007c8a  mov     eax, ebx
0x180007c8c  mov     rbx, [rsp+0B8h+arg_0]
0x180007c94  add     rsp, 80h
0x180007c9b  pop     r15
0x180007c9d  pop     r14
0x180007c9f  pop     r13
0x180007ca1  pop     r12
0x180007ca3  pop     rdi
0x180007ca4  pop     rsi
0x180007ca5  pop     rbp
0x180007ca6  retn
0x180007ca8  mov     ebx, 0C000000Dh
0x180007cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cb4  cmp     rcx, rax
0x180007cb7  jz      short loc_180007C8A
0x180007cb9  mov     eax, [rcx+2Ch]
0x180007cbc  test    al, 1
0x180007cbe  jz      short loc_180007C8A
0x180007cc0  mov     rcx, [rcx+18h]
0x180007cc4  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007ccb  mov     dword ptr [rsp+0B8h+var_88], 1014h
0x180007cd3  lea     r9, aStatus; "Status"
0x180007cda  mov     [rsp+0B8h+var_90], r8
0x180007cdf  mov     dword ptr [rsp+0B8h+var_98], 0C000000Dh
0x180007ce7  call    WPP_SF_sDsd
0x180007cec  jmp     short loc_180007C8A
0x180007cee  mov     eax, [rsp+0B8h+cbOutput]
0x180007cf5  mov     edx, 18h
0x180007cfa  mov     rcx, [rcx+18h]
0x180007cfe  mov     r9, r14
0x180007d01  mov     [rsp+0B8h+var_68], ebp
0x180007d05  mov     [rsp+0B8h+var_70], rdi
0x180007d0a  mov     dword ptr [rsp+0B8h+var_78], eax
0x180007d0e  mov     [rsp+0B8h+var_80], r12
0x180007d13  mov     dword ptr [rsp+0B8h+var_88], esi
0x180007d17  mov     [rsp+0B8h+var_90], r13
0x180007d1c  mov     [rsp+0B8h+var_98], r15
0x180007d21  call    WPP_SF_qqqdqdqD
0x180007d26  jmp     loc_180007BCE
0x180007d2b  mov     ebx, 0C0000008h
0x180007d30  mov     r9d, 101Ch
0x180007d36  mov     ecx, 0C0000008h
0x180007d3b  jmp     loc_1800A0EBE
0x180007d40  cmp     ecx, 2
0x180007d43  jz      loc_1800A0ED7
0x180007d49  mov     ebx, 0C00000BBh
0x180007d4e  mov     r9d, 1041h
0x180007d54  mov     ecx, 0C00000BBh
0x180007d59  jmp     loc_1800A0EBE
0x180007d5e  mov     r9d, 10B9h
0x180007d64  mov     ecx, eax
0x180007d66  jmp     loc_1800A0EBE
0x180007d6b  lea     eax, [rsi+rsi]
0x180007d6e  cmp     eax, esi
0x180007d70  jnb     loc_1800A0F07
0x180007d76  mov     ebx, 0C0000095h
0x180007d7b  mov     r9d, 1050h
0x180007d81  mov     ecx, 0C0000095h
0x180007d86  jmp     loc_1800A0EBE
0x180007d8b  test    bpl, 2
0x180007d8f  jnz     loc_180007C8A
0x180007d95  jmp     loc_180007C72
0x180007d9a  mov     edx, r13d
0x180007d9d  mov     rcx, rdi
0x180007da0  call    SymCryptWipeAsm
0x180007da5  mov     rcx, rdi; P
0x180007da8  call    MSCryptFree
0x180007dad  jmp     loc_180007C8A
0x1800a0eae  mov     ebx, 0C0000017h
0x1800a0eb3  mov     r9d, 106Bh
0x1800a0eb9  mov     ecx, 0C0000017h
0x1800a0ebe  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a0ec5  lea     rdx, aStatus; "Status"
0x1800a0ecc  call    DebugTraceError
0x1800a0ed1  nop
0x1800a0ed2  jmp     loc_180007C8A
0x1800a0ed7  mov     ecx, [rdi+1B8h]
0x1800a0edd  lea     r8, [rsp+0B8h+var_58]
0x1800a0ee2  mov     edx, ebp
0x1800a0ee4  call    ShouldRouterPadEncryption
0x1800a0ee9  mov     ebx, eax
0x1800a0eeb  test    eax, eax
0x1800a0eed  jns     short loc_1800A0EFA
0x1800a0eef  mov     r9d, 103Ah
0x1800a0ef5  jmp     loc_180007D64
0x1800a0efa  mov     r11, [rdi+70h]
0x1800a0efe  mov     ebx, [rsp+0B8h+var_58]
0x1800a0f02  jmp     loc_180007C0B
0x1800a0f07  mov     rcx, rsi
0x1800a0f0a  call    SymCryptRoundUpPow2Sizet
0x1800a0f0f  mov     r15, rax
0x1800a0f12  mov     r13d, esi
0x1800a0f15  mov     eax, 20h ; ' '
0x1800a0f1a  cmp     r15d, eax
0x1800a0f1d  cmovb   r15d, eax
0x1800a0f21  xor     ecx, ecx
0x1800a0f23  test    r12, r12
0x1800a0f26  cmovnz  r13d, ecx
0x1800a0f2a  add     r13d, r15d
0x1800a0f2d  mov     ecx, r13d
0x1800a0f30  call    MSCryptAlloc
0x1800a0f35  mov     rdi, rax
0x1800a0f38  test    rax, rax
0x1800a0f3b  jz      loc_1800A0EAE
0x1800a0f41  test    r12, r12
0x1800a0f44  jnz     short loc_1800A0F4E
0x1800a0f46  mov     r14d, r15d
0x1800a0f49  add     r14, rax
0x1800a0f4c  jmp     short loc_1800A0F51
0x1800a0f4e  mov     r14, r12
0x1800a0f51  mov     ecx, [rsp+0B8h+cbIV]
0x1800a0f58  mov     eax, esi
0x1800a0f5a  mov     rdx, [rsp+0B8h+arg_8]
0x1800a0f62  test    r12, r12
0x1800a0f65  mov     dword ptr [rsp+0B8h+var_70], ebp
0x1800a0f69  mov     r8d, esi
0x1800a0f6c  cmovnz  eax, [rsp+0B8h+cbOutput]
0x1800a0f74  xor     r9d, r9d
0x1800a0f77  mov     [rsp+0B8h+var_58], eax
0x1800a0f7b  lea     rax, [rsp+0B8h+var_54]
0x1800a0f80  mov     [rsp+0B8h+var_78], rax
0x1800a0f85  mov     rax, [rsp+0B8h+var_50]
0x1800a0f8a  mov     dword ptr [rsp+0B8h+var_80], esi
0x1800a0f8e  mov     [rsp+0B8h+var_88], rdi
0x1800a0f93  mov     dword ptr [rsp+0B8h+var_90], ecx
0x1800a0f97  mov     rcx, [rsp+0B8h+pbIV]
0x1800a0f9f  mov     [rsp+0B8h+var_98], rcx
0x1800a0fa4  mov     rcx, [rsp+0B8h+var_48]
0x1800a0fa9  mov     rcx, [rcx+10h]
0x1800a0fad  call    _guard_dispatch_icall
0x1800a0fb2  mov     ebx, eax
0x1800a0fb4  test    eax, eax
0x1800a0fb6  jns     short loc_1800A0FD9
0x1800a0fb8  mov     r9d, 108Ah
0x1800a0fbe  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a0fc5  lea     rdx, aStatus; "Status"
0x1800a0fcc  mov     ecx, eax
0x1800a0fce  call    DebugTraceError
0x1800a0fd3  nop
0x1800a0fd4  jmp     loc_180007D9A
0x1800a0fd9  mov     rax, [rsp+0B8h+pcbResult]
0x1800a0fe1  mov     r8, rdi
0x1800a0fe4  mov     r9d, [rsp+0B8h+var_54]
0x1800a0fe9  mov     ecx, ebp
0x1800a0feb  mov     rdx, [rsp+0B8h+arg_18]
0x1800a0ff3  mov     [rsp+0B8h+var_80], rax
0x1800a0ff8  mov     eax, [rsp+0B8h+var_58]
0x1800a0ffc  mov     dword ptr [rsp+0B8h+var_88], eax
0x1800a1000  mov     [rsp+0B8h+var_90], r14
0x1800a1005  mov     dword ptr [rsp+0B8h+var_98], r15d
0x1800a100a  call    CheckEncryptionPadding
0x1800a100f  nop
0x1800a1010  jmp     loc_180007C7F
```
