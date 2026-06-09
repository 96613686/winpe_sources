# BCryptDecrypt

- ea: `0x180011c80`
- end: `0x180011ed2`
- name: `BCryptDecrypt`
- size: `594`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbInput, ULONG cbInput, void *pPaddingInfo, PUCHAR pbIV, ULONG cbIV, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180011880`
- `0x1800484b0`
- `0x180048f50`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x180011c80`
- `0x1800123d0`
- `0x18003f910`
- `0x180052fe8`
- `0x1800564d0`
- `0x1800646a0`
- `0x180065dcc`
- `0x180073148`
- `0x1800a4300`

## string_xrefs

- `0x180011de4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a5e2c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a5f2c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
  unsigned int v27; // r15d
  int v28; // r13d
  __int64 v29; // rax
  PUCHAR v30; // r14
  ULONG v31; // eax
  int v32; // eax
  ULONG v33; // [rsp+60h] [rbp-58h] BYREF
  int v34; // [rsp+64h] [rbp-54h] BYREF
  __int64 (__fastcall *v35)(_QWORD, PUCHAR, _QWORD, _QWORD, PUCHAR, ULONG, void *, _DWORD, int *, ULONG); // [rsp+68h] [rbp-50h]
  __int64 v36; // [rsp+70h] [rbp-48h]
  int v38; // [rsp+D8h] [rbp+20h]

  v38 = (int)pPaddingInfo;
  v10 = 0;
  v11 = cbInput;
  v33 = 0;
  v34 = 0;
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
  v36 = v15;
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
    v19 = ShouldRouterPadEncryption(*(unsigned int *)(v17 + 440), dwFlags, &v33);
    v20 = v19;
    if ( v19 < 0 )
    {
      v24 = 4154;
LABEL_20:
      v25 = (unsigned int)v19;
      goto LABEL_27;
    }
    v18 = *(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD, PUCHAR, ULONG, void *, _DWORD, int *, ULONG))(v17 + 112);
    v10 = v33;
  }
  v35 = v18;
  if ( v10 )
  {
    if ( 2 * (int)v11 >= (unsigned int)v11 )
    {
      v27 = SymCryptRoundUpPow2Sizet(v11);
      v28 = v11;
      if ( v27 < 0x20 )
        v27 = 32;
      if ( pbOutput )
        v28 = 0;
      v22 = v27 + v28;
      v29 = MSCryptAlloc(v22, v26);
      v21 = (void *)v29;
      if ( v29 )
      {
        if ( pbOutput )
          v30 = pbOutput;
        else
          v30 = (PUCHAR)(v29 + v27);
        v31 = v11;
        if ( pbOutput )
          v31 = cbOutput;
        v33 = v31;
        v32 = v35(*(_QWORD *)(v36 + 16), pbInput, (unsigned int)v11, 0, pbIV, cbIV, v21, v11, &v34, dwFlags);
        v20 = v32;
        if ( v32 < 0 )
        {
          DebugTraceError((unsigned int)v32, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 4234);
          goto LABEL_25;
        }
        CheckEncryptionPadding(dwFlags, v38, (_DWORD)v21, v34, v27, (__int64)v30, v33, (__int64)pcbResult);
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
0x180011c80  mov     rax, rsp
0x180011c83  mov     [rax+8], rbx
0x180011c87  mov     [rax+20h], r9
0x180011c8b  mov     [rax+10h], rdx
0x180011c8f  push    rbp
0x180011c90  push    rsi
0x180011c91  push    rdi
0x180011c92  push    r12
0x180011c94  push    r13
0x180011c96  push    r14
0x180011c98  push    r15
0x180011c9a  sub     rsp, 80h
0x180011ca1  xor     ebx, ebx
0x180011ca3  mov     esi, r8d
0x180011ca6  mov     [rax-58h], ebx
0x180011ca9  mov     r15, r9
0x180011cac  mov     r13, rdx
0x180011caf  mov     dword ptr [rax-54h], 0
0x180011cb6  mov     r14, rcx
0x180011cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cc0  lea     rax, WPP_GLOBAL_Control
0x180011cc7  mov     ebp, [rsp+0B8h+dwFlags]
0x180011cce  mov     r12, [rsp+0B8h+pbOutput]
0x180011cd6  mov     rdi, [rsp+0B8h+pcbResult]
0x180011cde  cmp     rcx, rax
0x180011ce1  jz      short loc_180011CF5
0x180011ce3  mov     eax, [rcx+2Ch]
0x180011ce6  test    al, 4
0x180011ce8  jnz     loc_180011E0E
0x180011cee  lea     rax, WPP_GLOBAL_Control
0x180011cf5  test    rdi, rdi
0x180011cf8  jz      loc_180011DC8
0x180011cfe  mov     rcx, r14
0x180011d01  call    ValidateBaseKeyHandle
0x180011d06  mov     [rsp+0B8h+var_48], rax
0x180011d0b  mov     r10, rax
0x180011d0e  test    rax, rax
0x180011d11  jz      loc_180011E4B
0x180011d17  mov     rdi, [rax+8]
0x180011d1b  mov     ecx, [rdi+24h]
0x180011d1e  sub     ecx, 1
0x180011d21  jnz     loc_180011E60
0x180011d27  mov     r11, [rdi+68h]
0x180011d2b  mov     [rsp+0B8h+var_50], r11
0x180011d30  test    ebx, ebx
0x180011d32  jnz     loc_180011E8B
0x180011d38  mov     rax, [rsp+0B8h+pcbResult]
0x180011d40  mov     r9, r15
0x180011d43  mov     rcx, [r10+10h]
0x180011d47  mov     r8d, esi
0x180011d4a  mov     dword ptr [rsp+0B8h+var_70], ebp
0x180011d4e  mov     rdx, r13
0x180011d51  mov     [rsp+0B8h+var_78], rax
0x180011d56  mov     eax, [rsp+0B8h+cbOutput]
0x180011d5d  mov     dword ptr [rsp+0B8h+var_80], eax
0x180011d61  mov     eax, [rsp+0B8h+cbIV]
0x180011d68  mov     [rsp+0B8h+var_88], r12
0x180011d6d  mov     dword ptr [rsp+0B8h+var_90], eax
0x180011d71  mov     rax, [rsp+0B8h+pbIV]
0x180011d79  mov     [rsp+0B8h+var_98], rax
0x180011d7e  mov     rax, r11
0x180011d81  call    _guard_dispatch_icall
0x180011d86  cmp     dword ptr [rdi+24h], 3
0x180011d8a  mov     ebx, eax
0x180011d8c  jz      loc_180011EAB
0x180011d92  xor     edi, edi
0x180011d94  xor     r13d, r13d
0x180011d97  test    eax, eax
0x180011d99  js      loc_180011E7E
0x180011d9f  xor     ebx, ebx
0x180011da1  test    rdi, rdi
0x180011da4  jnz     loc_180011EBA
0x180011daa  mov     eax, ebx
0x180011dac  mov     rbx, [rsp+0B8h+arg_0]
0x180011db4  add     rsp, 80h
0x180011dbb  pop     r15
0x180011dbd  pop     r14
0x180011dbf  pop     r13
0x180011dc1  pop     r12
0x180011dc3  pop     rdi
0x180011dc4  pop     rsi
0x180011dc5  pop     rbp
0x180011dc6  retn
0x180011dc8  mov     ebx, 0C000000Dh
0x180011dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dd4  cmp     rcx, rax
0x180011dd7  jz      short loc_180011DAA
0x180011dd9  mov     eax, [rcx+2Ch]
0x180011ddc  test    al, 1
0x180011dde  jz      short loc_180011DAA
0x180011de0  mov     rcx, [rcx+18h]
0x180011de4  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011deb  mov     dword ptr [rsp+0B8h+var_88], 1014h
0x180011df3  lea     r9, aStatus; "Status"
0x180011dfa  mov     [rsp+0B8h+var_90], r8
0x180011dff  mov     dword ptr [rsp+0B8h+var_98], 0C000000Dh
0x180011e07  call    WPP_SF_sDsd
0x180011e0c  jmp     short loc_180011DAA
0x180011e0e  mov     eax, [rsp+0B8h+cbOutput]
0x180011e15  mov     edx, 18h
0x180011e1a  mov     rcx, [rcx+18h]
0x180011e1e  mov     r9, r14
0x180011e21  mov     [rsp+0B8h+var_68], ebp
0x180011e25  mov     [rsp+0B8h+var_70], rdi
0x180011e2a  mov     dword ptr [rsp+0B8h+var_78], eax
0x180011e2e  mov     [rsp+0B8h+var_80], r12
0x180011e33  mov     dword ptr [rsp+0B8h+var_88], esi
0x180011e37  mov     [rsp+0B8h+var_90], r13
0x180011e3c  mov     [rsp+0B8h+var_98], r15
0x180011e41  call    WPP_SF_qqqdqdqD
0x180011e46  jmp     loc_180011CEE
0x180011e4b  mov     ebx, 0C0000008h
0x180011e50  mov     r9d, 101Ch
0x180011e56  mov     ecx, 0C0000008h
0x180011e5b  jmp     loc_1800A5E2C
0x180011e60  cmp     ecx, 2
0x180011e63  jz      loc_1800A5E45
0x180011e69  mov     ebx, 0C00000BBh
0x180011e6e  mov     r9d, 1041h
0x180011e74  mov     ecx, 0C00000BBh
0x180011e79  jmp     loc_1800A5E2C
0x180011e7e  mov     r9d, 10B9h
0x180011e84  mov     ecx, eax
0x180011e86  jmp     loc_1800A5E2C
0x180011e8b  lea     eax, [rsi+rsi]
0x180011e8e  cmp     eax, esi
0x180011e90  jnb     loc_1800A5E75
0x180011e96  mov     ebx, 0C0000095h
0x180011e9b  mov     r9d, 1050h
0x180011ea1  mov     ecx, 0C0000095h
0x180011ea6  jmp     loc_1800A5E2C
0x180011eab  test    bpl, 2
0x180011eaf  jnz     loc_180011DAA
0x180011eb5  jmp     loc_180011D92
0x180011eba  mov     edx, r13d
0x180011ebd  mov     rcx, rdi
0x180011ec0  call    SymCryptWipeAsm
0x180011ec5  mov     rcx, rdi; P
0x180011ec8  call    MSCryptFree
0x180011ecd  jmp     loc_180011DAA
0x1800a5e1c  mov     ebx, 0C0000017h
0x1800a5e21  mov     r9d, 106Bh
0x1800a5e27  mov     ecx, 0C0000017h
0x1800a5e2c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a5e33  lea     rdx, aStatus; "Status"
0x1800a5e3a  call    DebugTraceError
0x1800a5e3f  nop
0x1800a5e40  jmp     loc_180011DAA
0x1800a5e45  mov     ecx, [rdi+1B8h]
0x1800a5e4b  lea     r8, [rsp+0B8h+var_58]
0x1800a5e50  mov     edx, ebp
0x1800a5e52  call    ShouldRouterPadEncryption
0x1800a5e57  mov     ebx, eax
0x1800a5e59  test    eax, eax
0x1800a5e5b  jns     short loc_1800A5E68
0x1800a5e5d  mov     r9d, 103Ah
0x1800a5e63  jmp     loc_180011E84
0x1800a5e68  mov     r11, [rdi+70h]
0x1800a5e6c  mov     ebx, [rsp+0B8h+var_58]
0x1800a5e70  jmp     loc_180011D2B
0x1800a5e75  mov     rcx, rsi
0x1800a5e78  call    SymCryptRoundUpPow2Sizet
0x1800a5e7d  mov     r15, rax
0x1800a5e80  mov     r13d, esi
0x1800a5e83  mov     eax, 20h ; ' '
0x1800a5e88  cmp     r15d, eax
0x1800a5e8b  cmovb   r15d, eax
0x1800a5e8f  xor     ecx, ecx
0x1800a5e91  test    r12, r12
0x1800a5e94  cmovnz  r13d, ecx
0x1800a5e98  add     r13d, r15d
0x1800a5e9b  mov     ecx, r13d
0x1800a5e9e  call    MSCryptAlloc
0x1800a5ea3  mov     rdi, rax
0x1800a5ea6  test    rax, rax
0x1800a5ea9  jz      loc_1800A5E1C
0x1800a5eaf  test    r12, r12
0x1800a5eb2  jnz     short loc_1800A5EBC
0x1800a5eb4  mov     r14d, r15d
0x1800a5eb7  add     r14, rax
0x1800a5eba  jmp     short loc_1800A5EBF
0x1800a5ebc  mov     r14, r12
0x1800a5ebf  mov     ecx, [rsp+0B8h+cbIV]
0x1800a5ec6  mov     eax, esi
0x1800a5ec8  mov     rdx, [rsp+0B8h+arg_8]
0x1800a5ed0  test    r12, r12
0x1800a5ed3  mov     dword ptr [rsp+0B8h+var_70], ebp
0x1800a5ed7  mov     r8d, esi
0x1800a5eda  cmovnz  eax, [rsp+0B8h+cbOutput]
0x1800a5ee2  xor     r9d, r9d
0x1800a5ee5  mov     [rsp+0B8h+var_58], eax
0x1800a5ee9  lea     rax, [rsp+0B8h+var_54]
0x1800a5eee  mov     [rsp+0B8h+var_78], rax
0x1800a5ef3  mov     rax, [rsp+0B8h+var_50]
0x1800a5ef8  mov     dword ptr [rsp+0B8h+var_80], esi
0x1800a5efc  mov     [rsp+0B8h+var_88], rdi
0x1800a5f01  mov     dword ptr [rsp+0B8h+var_90], ecx
0x1800a5f05  mov     rcx, [rsp+0B8h+pbIV]
0x1800a5f0d  mov     [rsp+0B8h+var_98], rcx
0x1800a5f12  mov     rcx, [rsp+0B8h+var_48]
0x1800a5f17  mov     rcx, [rcx+10h]
0x1800a5f1b  call    _guard_dispatch_icall
0x1800a5f20  mov     ebx, eax
0x1800a5f22  test    eax, eax
0x1800a5f24  jns     short loc_1800A5F47
0x1800a5f26  mov     r9d, 108Ah
0x1800a5f2c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a5f33  lea     rdx, aStatus; "Status"
0x1800a5f3a  mov     ecx, eax
0x1800a5f3c  call    DebugTraceError
0x1800a5f41  nop
0x1800a5f42  jmp     loc_180011EBA
0x1800a5f47  mov     rax, [rsp+0B8h+pcbResult]
0x1800a5f4f  mov     r8, rdi
0x1800a5f52  mov     r9d, [rsp+0B8h+var_54]
0x1800a5f57  mov     ecx, ebp
0x1800a5f59  mov     rdx, [rsp+0B8h+arg_18]
0x1800a5f61  mov     [rsp+0B8h+var_80], rax
0x1800a5f66  mov     eax, [rsp+0B8h+var_58]
0x1800a5f6a  mov     dword ptr [rsp+0B8h+var_88], eax
0x1800a5f6e  mov     [rsp+0B8h+var_90], r14
0x1800a5f73  mov     dword ptr [rsp+0B8h+var_98], r15d
0x1800a5f78  call    CheckEncryptionPadding
0x1800a5f7d  nop
0x1800a5f7e  jmp     loc_180011D9F
```
