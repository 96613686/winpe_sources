# CNG_DecryptAndAllocate

- ea: `0x180006c9c`
- end: `0x180006f37`
- name: `CNG_DecryptAndAllocate`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007024`

## callees

- `0x180006c9c`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptDecrypt` at `0x180006d51`
- `bcrypt!BCryptDecrypt` at `0x180006dc3`
- `bcrypt!BCryptDecrypt` at `0x180006d51`
- `bcrypt!BCryptDecrypt` at `0x180006dc3`

## string_xrefs

- `0x180006e1c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180006e64`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180006ea8`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180006eef`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180006f0e`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`

## pseudocode

```c
__int64 __fastcall CNG_DecryptAndAllocate(__int64 a1, UCHAR *a2, ULONG a3, UCHAR **a4, ULONG *a5)
{
  ULONG *v5; // r15
  ULONG v7; // esi
  __int64 v10; // rcx
  int v11; // edx
  unsigned int cbIV; // ebx
  int v13; // edx
  UCHAR *pbOutput; // rbp
  unsigned int v15; // eax
  ULONG v16; // eax
  ULONG pcbResult; // [rsp+80h] [rbp+8h] BYREF

  v5 = a5;
  *a4 = 0;
  v7 = a3;
  pcbResult = 0;
  *v5 = 0;
  if ( (*(_DWORD *)(a1 + 112) & 0x10000000) == 0 )
  {
LABEL_5:
    cbIV = BCryptDecrypt(
             *(BCRYPT_KEY_HANDLE *)(a1 + 16),
             a2,
             v7,
             *(void **)(a1 + 72),
             0,
             0,
             0,
             0,
             &pcbResult,
             *(_DWORD *)(*(_QWORD *)(a1 + 24) + 72LL));
    if ( cbIV )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
          (unsigned int)"Status",
          cbIV,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
          72);
    }
    else
    {
      pbOutput = (UCHAR *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1 + 8LL))(pcbResult);
      if ( pbOutput )
      {
        v15 = BCryptDecrypt(
                *(BCRYPT_KEY_HANDLE *)(a1 + 16),
                a2,
                v7,
                *(void **)(a1 + 72),
                0,
                cbIV,
                pbOutput,
                pcbResult,
                &pcbResult,
                *(_DWORD *)(*(_QWORD *)(a1 + 24) + 72LL));
        cbIV = v15;
        if ( v15 )
        {
          DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c", 1378);
          (*(void (__fastcall **)(UCHAR *))(*(_QWORD *)a1 + 16LL))(pbOutput);
        }
        else
        {
          v16 = pcbResult;
          *a4 = pbOutput;
          *v5 = v16;
        }
      }
      else
      {
        cbIV = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v13,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
            80);
      }
    }
    return cbIV;
  }
  if ( *(_DWORD *)(a1 + 64) < 0x98u )
  {
    cbIV = -2146893779;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
        (unsigned int)"Status",
        45,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
        39);
  }
  else
  {
    v10 = *(_QWORD *)(a1 + 72);
    if ( a3 >= *(_DWORD *)(v10 + 48) )
    {
      v7 = a3 - *(_DWORD *)(v10 + 48);
      *(_QWORD *)(v10 + 40) = &a2[v7];
      goto LABEL_5;
    }
    cbIV = -2146893819;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
        (unsigned int)"Status",
        5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
        46);
  }
  return cbIV;
}

```

## disassembly

```asm
0x180006c9c  mov     rax, rsp
0x180006c9f  mov     [rax+10h], rbx
0x180006ca3  mov     [rax+18h], rbp
0x180006ca7  push    rsi
0x180006ca8  push    rdi
0x180006ca9  push    r12
0x180006cab  push    r14
0x180006cad  push    r15
0x180006caf  sub     rsp, 50h
0x180006cb3  mov     r15, [rsp+78h+arg_20]
0x180006cbb  mov     r14, r9
0x180006cbe  mov     qword ptr [r9], 0
0x180006cc5  mov     esi, r8d
0x180006cc8  mov     r12, rdx
0x180006ccb  mov     dword ptr [rax+8], 0
0x180006cd2  mov     rdi, rcx
0x180006cd5  mov     dword ptr [r15], 0
0x180006cdc  test    dword ptr [rcx+70h], 10000000h
0x180006ce3  jz      short loc_180006D0C
0x180006ce5  cmp     dword ptr [rcx+40h], 98h
0x180006cec  jb      loc_180006E3E
0x180006cf2  mov     rcx, [rcx+48h]
0x180006cf6  cmp     r8d, [rcx+30h]
0x180006cfa  jb      loc_180006E7A
0x180006d00  sub     esi, [rcx+30h]
0x180006d03  mov     eax, esi
0x180006d05  add     rax, rdx
0x180006d08  mov     [rcx+28h], rax
0x180006d0c  mov     rax, [rdi+18h]
0x180006d10  mov     r8d, esi; cbInput
0x180006d13  mov     r9, [rdi+48h]; pPaddingInfo
0x180006d17  mov     ecx, [rax+48h]
0x180006d1a  lea     rax, [rsp+78h+arg_0]
0x180006d22  mov     [rsp+78h+dwFlags], ecx; dwFlags
0x180006d26  mov     rcx, [rdi+10h]; hKey
0x180006d2a  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180006d2f  mov     [rsp+78h+cbOutput], 0; cbOutput
0x180006d37  mov     [rsp+78h+pbOutput], 0; pbOutput
0x180006d40  mov     [rsp+78h+cbIV], 0; cbIV
0x180006d48  mov     [rsp+78h+pbIV], 0; pbIV
0x180006d51  call    cs:__imp_BCryptDecrypt
0x180006d57  mov     ebx, eax
0x180006d59  test    eax, eax
0x180006d5b  jnz     loc_180006DFB
0x180006d61  mov     rax, [rdi]
0x180006d64  mov     ecx, [rsp+78h+arg_0]
0x180006d6b  mov     rax, [rax+8]
0x180006d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d74  mov     rbp, rax
0x180006d77  test    rax, rax
0x180006d7a  jz      loc_180006EC1
0x180006d80  mov     rax, [rdi+18h]
0x180006d84  mov     r8d, esi; cbInput
0x180006d87  mov     r9, [rdi+48h]; pPaddingInfo
0x180006d8b  mov     rdx, r12; pbInput
0x180006d8e  mov     ecx, [rax+48h]
0x180006d91  lea     rax, [rsp+78h+arg_0]
0x180006d99  mov     [rsp+78h+dwFlags], ecx; dwFlags
0x180006d9d  mov     rcx, [rdi+10h]; hKey
0x180006da1  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180006da6  mov     eax, [rsp+78h+arg_0]
0x180006dad  mov     [rsp+78h+cbOutput], eax; cbOutput
0x180006db1  mov     [rsp+78h+pbOutput], rbp; pbOutput
0x180006db6  mov     [rsp+78h+cbIV], ebx; cbIV
0x180006dba  mov     [rsp+78h+pbIV], 0; pbIV
0x180006dc3  call    cs:__imp_BCryptDecrypt
0x180006dc9  mov     ebx, eax
0x180006dcb  test    eax, eax
0x180006dcd  jnz     loc_180006F08
0x180006dd3  mov     eax, [rsp+78h+arg_0]
0x180006dda  mov     [r14], rbp
0x180006ddd  mov     [r15], eax
0x180006de0  lea     r11, [rsp+78h+var_28]
0x180006de5  mov     eax, ebx
0x180006de7  mov     rbx, [r11+38h]
0x180006deb  mov     rbp, [r11+40h]
0x180006def  mov     rsp, r11
0x180006df2  pop     r15
0x180006df4  pop     r14
0x180006df6  pop     r12
0x180006df8  pop     rdi
0x180006df9  pop     rsi
0x180006dfa  retn
0x180006dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e02  lea     rax, WPP_GLOBAL_Control
0x180006e09  cmp     rcx, rax
0x180006e0c  jz      short loc_180006DE0
0x180006e0e  test    byte ptr [rcx+1Ch], 1
0x180006e12  jz      short loc_180006DE0
0x180006e14  mov     dword ptr [rsp+78h+pbOutput], 548h
0x180006e1c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006e23  mov     qword ptr [rsp+78h+cbIV], r8
0x180006e28  mov     dword ptr [rsp+78h+pbIV], ebx
0x180006e2c  mov     rcx, [rcx+10h]
0x180006e30  lea     r9, aStatus; "Status"
0x180006e37  call    WPP_SF_sDsd
0x180006e3c  jmp     short loc_180006DE0
0x180006e3e  mov     ebx, 8009002Dh
0x180006e43  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e4a  lea     rax, WPP_GLOBAL_Control
0x180006e51  cmp     rcx, rax
0x180006e54  jz      short loc_180006DE0
0x180006e56  test    byte ptr [rcx+1Ch], 1
0x180006e5a  jz      short loc_180006DE0
0x180006e5c  mov     dword ptr [rsp+78h+pbOutput], 527h
0x180006e64  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006e6b  mov     qword ptr [rsp+78h+cbIV], r8
0x180006e70  mov     dword ptr [rsp+78h+pbIV], 8009002Dh
0x180006e78  jmp     short loc_180006E2C
0x180006e7a  mov     ebx, 80090005h
0x180006e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e86  lea     rax, WPP_GLOBAL_Control
0x180006e8d  cmp     rcx, rax
0x180006e90  jz      loc_180006DE0
0x180006e96  test    byte ptr [rcx+1Ch], 1
0x180006e9a  jz      loc_180006DE0
0x180006ea0  mov     dword ptr [rsp+78h+pbOutput], 52Eh
0x180006ea8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006eaf  mov     qword ptr [rsp+78h+cbIV], r8
0x180006eb4  mov     dword ptr [rsp+78h+pbIV], 80090005h
0x180006ebc  jmp     loc_180006E2C
0x180006ec1  mov     ebx, 8009000Eh
0x180006ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ecd  lea     rax, WPP_GLOBAL_Control
0x180006ed4  cmp     rcx, rax
0x180006ed7  jz      loc_180006DE0
0x180006edd  test    byte ptr [rcx+1Ch], 1
0x180006ee1  jz      loc_180006DE0
0x180006ee7  mov     dword ptr [rsp+78h+pbOutput], 550h
0x180006eef  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006ef6  mov     qword ptr [rsp+78h+cbIV], r8
0x180006efb  mov     dword ptr [rsp+78h+pbIV], 8009000Eh
0x180006f03  jmp     loc_180006E2C
0x180006f08  mov     r9d, 562h
0x180006f0e  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006f15  lea     rdx, aStatus; "Status"
0x180006f1c  mov     ecx, eax
0x180006f1e  call    DebugTraceError
0x180006f23  mov     rax, [rdi]
0x180006f26  mov     rcx, rbp
0x180006f29  mov     rax, [rax+10h]
0x180006f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f32  jmp     loc_180006DE0
```
