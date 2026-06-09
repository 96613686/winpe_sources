# TlsHkdfExtract

- ea: `0x18000cfb0`
- end: `0x18000d29d`
- name: `TlsHkdfExtract`
- size: `749`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbSecret@<rcx>, ULONG cbSecret@<edx>, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800058e0`
- `0x18000dea0`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x18000cfb0`
- `0x1800183d0`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x18000d10b`
- `bcrypt!BCryptSetProperty` at `0x18000d131`
- `bcrypt!BCryptSetProperty` at `0x18000d10b`
- `bcrypt!BCryptSetProperty` at `0x18000d131`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000d0c2`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000d0c2`
- `bcrypt!BCryptDestroyKey` at `0x18000d292`
- `bcrypt!BCryptDestroyKey` at `0x18000d292`

## string_xrefs

- `0x18000d170`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000d251`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000d270`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsHkdfExtract(PUCHAR pbSecret, ULONG cbSecret, UCHAR *a3, ULONG a4, __int64 a5)
{
  __int64 v7; // r14
  __int64 v8; // rax
  const wchar_t *v9; // rbp
  int v10; // r15d
  UCHAR *v11; // rbx
  __int64 i; // rdi
  const wchar_t **v13; // rax
  __int64 *v14; // rsi
  UCHAR *v15; // rbp
  ULONG v16; // esi
  int v17; // edx
  unsigned int v18; // edi
  int v19; // r8d
  __int64 v20; // r9
  _QWORD *v22; // rcx
  char dwFlags; // [rsp+30h] [rbp-48h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+80h] [rbp+8h] BYREF
  PUCHAR pbInput; // [rsp+90h] [rbp+18h]
  ULONG cbInput; // [rsp+98h] [rbp+20h]

  cbInput = a4;
  pbInput = a3;
  phKey = 0;
  if ( pbSecret && cbSecret && (v7 = a5) != 0 && (v8 = *(_QWORD *)(a5 + 16)) != 0 )
  {
    v9 = *(const wchar_t **)(v8 + 136);
    v10 = 0;
    v11 = 0;
    if ( !v9 || !*v9 )
      v9 = L"SHA256";
    for ( i = 0; (unsigned int)i < g_dwHashInfoTotalCount; i = (unsigned int)(i + 1) )
    {
      v13 = (const wchar_t **)g_pHashInfo[i];
      v14 = &g_pHashInfo[i];
      if ( v13 && *v13 && !wcsnicmp(v9, *v13, 0x40u) )
      {
        _mm_lfence();
        if ( *v14 )
        {
          v10 = *(_DWORD *)(*v14 + 8);
          v11 = (UCHAR *)v9;
        }
        break;
      }
    }
    v15 = pbInput;
    if ( pbInput && (v16 = cbInput, cbInput == v10) )
    {
      v18 = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x391, &phKey, 0, 0, pbSecret, cbSecret, 0);
      if ( v18 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          dwFlags = -19;
          goto LABEL_26;
        }
      }
      else
      {
        v20 = -1;
        while ( *(_WORD *)&v11[2 * v20++ + 2] != 0 )
          ;
        v18 = BCryptSetProperty(phKey, L"HkdfHashAlgorithm", v11, 2 * v20 + 2, 0);
        if ( !v18 )
        {
          v18 = BCryptSetProperty(phKey, L"HkdfSaltAndFinalize", v15, v16, 0);
          if ( !v18 )
          {
            *(_QWORD *)(v7 + 32) = phKey;
            return v18;
          }
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_27;
          dwFlags = 7;
          goto LABEL_26;
        }
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          dwFlags = -6;
LABEL_26:
          WPP_SF_sDsd(
            v22[2],
            v17,
            v19,
            (unsigned int)"Status",
            v18,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            dwFlags);
        }
      }
    }
    else
    {
      v18 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 3807);
    }
  }
  else
  {
    v18 = -1073741811;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v18;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      cbSecret,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      210);
  }
LABEL_27:
  if ( phKey )
    BCryptDestroyKey(phKey);
  return v18;
}

```

## disassembly

```asm
0x18000cfb0  mov     rax, rsp
0x18000cfb3  mov     [rax+10h], rbx
0x18000cfb7  mov     [rax+20h], r9d
0x18000cfbb  mov     [rax+18h], r8
0x18000cfbf  push    rbp
0x18000cfc0  push    rsi
0x18000cfc1  push    rdi
0x18000cfc2  push    r12
0x18000cfc4  push    r13
0x18000cfc6  push    r14
0x18000cfc8  push    r15
0x18000cfca  sub     rsp, 40h
0x18000cfce  mov     qword ptr [rax+8], 0
0x18000cfd6  mov     r12d, edx
0x18000cfd9  mov     r13, rcx
0x18000cfdc  test    rcx, rcx
0x18000cfdf  jz      loc_18000D223
0x18000cfe5  test    edx, edx
0x18000cfe7  jz      loc_18000D223
0x18000cfed  mov     r14, [rsp+78h+arg_20]
0x18000cff5  test    r14, r14
0x18000cff8  jz      loc_18000D223
0x18000cffe  mov     rax, [r14+10h]
0x18000d002  test    rax, rax
0x18000d005  jz      loc_18000D223
0x18000d00b  mov     rbp, [rax+88h]
0x18000d012  xor     r15d, r15d
0x18000d015  xor     ebx, ebx
0x18000d017  test    rbp, rbp
0x18000d01a  jz      loc_18000D1C7
0x18000d020  cmp     [rbp+0], bx
0x18000d024  jz      loc_18000D1C7
0x18000d02a  xor     edi, edi
0x18000d02c  lea     rcx, g_pHashInfo
0x18000d033  cmp     edi, cs:g_dwHashInfoTotalCount
0x18000d039  jnb     short loc_18000D07C
0x18000d03b  mov     rax, [rcx+rdi*8]
0x18000d03f  lea     rsi, [rcx+rdi*8]
0x18000d043  test    rax, rax
0x18000d046  jz      short loc_18000D069
0x18000d048  mov     rdx, [rax]; String2
0x18000d04b  test    rdx, rdx
0x18000d04e  jz      short loc_18000D069
0x18000d050  mov     r8d, 40h ; '@'; MaxCount
0x18000d056  mov     rcx, rbp; String1
0x18000d059  call    _wcsnicmp
0x18000d05e  test    eax, eax
0x18000d060  jz      short loc_18000D06D
0x18000d062  lea     rcx, g_pHashInfo
0x18000d069  inc     edi
0x18000d06b  jmp     short loc_18000D033
0x18000d06d  lfence
0x18000d070  mov     rax, [rsi]
0x18000d073  test    rax, rax
0x18000d076  jnz     loc_18000D1BB
0x18000d07c  mov     rbp, [rsp+78h+pbInput]
0x18000d084  test    rbp, rbp
0x18000d087  jz      loc_18000D26A
0x18000d08d  mov     esi, [rsp+78h+cbInput]
0x18000d094  cmp     esi, r15d
0x18000d097  jnz     loc_18000D26A
0x18000d09d  xor     r15d, r15d
0x18000d0a0  lea     rdx, [rsp+78h+phKey]; phKey
0x18000d0a8  mov     dword ptr [rsp+78h+dwFlags], r15d; dwFlags
0x18000d0ad  xor     r9d, r9d; cbKeyObject
0x18000d0b0  mov     [rsp+78h+cbSecret], r12d; cbSecret
0x18000d0b5  xor     r8d, r8d; pbKeyObject
0x18000d0b8  mov     ecx, 391h; hAlgorithm
0x18000d0bd  mov     [rsp+78h+pbSecret], r13; pbSecret
0x18000d0c2  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000d0c8  mov     edi, eax
0x18000d0ca  test    eax, eax
0x18000d0cc  jnz     loc_18000D1D3
0x18000d0d2  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18000d0d9  nop     dword ptr [rax+00000000h]
0x18000d0e0  cmp     [rbx+r9*2+2], r15w
0x18000d0e6  lea     r9, [r9+1]
0x18000d0ea  jnz     short loc_18000D0E0
0x18000d0ec  mov     rcx, [rsp+78h+phKey]; hObject
0x18000d0f4  lea     r9d, ds:2[r9*2]; cbInput
0x18000d0fc  mov     r8, rbx; pbInput
0x18000d0ff  mov     dword ptr [rsp+78h+pbSecret], r15d; dwFlags
0x18000d104  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x18000d10b  call    cs:__imp_BCryptSetProperty
0x18000d111  mov     edi, eax
0x18000d113  test    eax, eax
0x18000d115  jnz     short loc_18000D14F
0x18000d117  mov     rcx, [rsp+78h+phKey]; hObject
0x18000d11f  lea     rdx, aHkdfsaltandfin; "HkdfSaltAndFinalize"
0x18000d126  mov     r9d, esi; cbInput
0x18000d129  mov     dword ptr [rsp+78h+pbSecret], r15d; dwFlags
0x18000d12e  mov     r8, rbp; pbInput
0x18000d131  call    cs:__imp_BCryptSetProperty
0x18000d137  mov     edi, eax
0x18000d139  test    eax, eax
0x18000d13b  jnz     loc_18000D1F9
0x18000d141  mov     rax, [rsp+78h+phKey]
0x18000d149  mov     [r14+20h], rax
0x18000d14d  jmp     short loc_18000D1A1
0x18000d14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d156  lea     rax, WPP_GLOBAL_Control
0x18000d15d  cmp     rcx, rax
0x18000d160  jz      short loc_18000D190
0x18000d162  test    byte ptr [rcx+1Ch], 1
0x18000d166  jz      short loc_18000D190
0x18000d168  mov     dword ptr [rsp+78h+dwFlags], 0EFAh
0x18000d170  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d177  mov     qword ptr [rsp+78h+cbSecret], rax
0x18000d17c  mov     dword ptr [rsp+78h+pbSecret], edi
0x18000d180  mov     rcx, [rcx+10h]
0x18000d184  lea     r9, aStatus; "Status"
0x18000d18b  call    WPP_SF_sDsd
0x18000d190  mov     rcx, [rsp+78h+phKey]; hKey
0x18000d198  test    rcx, rcx
0x18000d19b  jnz     loc_18000D292
0x18000d1a1  mov     rbx, [rsp+78h+arg_8]
0x18000d1a9  mov     eax, edi
0x18000d1ab  add     rsp, 40h
0x18000d1af  pop     r15
0x18000d1b1  pop     r14
0x18000d1b3  pop     r13
0x18000d1b5  pop     r12
0x18000d1b7  pop     rdi
0x18000d1b8  pop     rsi
0x18000d1b9  pop     rbp
0x18000d1ba  retn
0x18000d1bb  mov     r15d, [rax+8]
0x18000d1bf  mov     rbx, rbp
0x18000d1c2  jmp     loc_18000D07C
0x18000d1c7  lea     rbp, aSha256; "SHA256"
0x18000d1ce  jmp     loc_18000D02A
0x18000d1d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1da  lea     rax, WPP_GLOBAL_Control
0x18000d1e1  cmp     rcx, rax
0x18000d1e4  jz      short loc_18000D190
0x18000d1e6  test    byte ptr [rcx+1Ch], 1
0x18000d1ea  jz      short loc_18000D190
0x18000d1ec  mov     dword ptr [rsp+78h+dwFlags], 0EEDh
0x18000d1f4  jmp     loc_18000D170
0x18000d1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d200  lea     rax, WPP_GLOBAL_Control
0x18000d207  cmp     rcx, rax
0x18000d20a  jz      short loc_18000D190
0x18000d20c  test    byte ptr [rcx+1Ch], 1
0x18000d210  jz      loc_18000D190
0x18000d216  mov     dword ptr [rsp+78h+dwFlags], 0F07h
0x18000d21e  jmp     loc_18000D170
0x18000d223  mov     edi, 0C000000Dh
0x18000d228  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d22f  lea     rax, WPP_GLOBAL_Control
0x18000d236  cmp     rcx, rax
0x18000d239  jz      loc_18000D1A1
0x18000d23f  test    byte ptr [rcx+1Ch], 1
0x18000d243  jz      loc_18000D1A1
0x18000d249  mov     dword ptr [rsp+78h+dwFlags], 0ED2h
0x18000d251  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d258  mov     qword ptr [rsp+78h+cbSecret], rax
0x18000d25d  mov     dword ptr [rsp+78h+pbSecret], 0C000000Dh
0x18000d265  jmp     loc_18000D180
0x18000d26a  mov     r9d, 0EDFh
0x18000d270  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d277  lea     rdx, aStatus; "Status"
0x18000d27e  mov     ecx, 0C000000Dh
0x18000d283  mov     edi, 0C000000Dh
0x18000d288  call    DebugTraceError
0x18000d28d  jmp     loc_18000D190
0x18000d292  call    cs:__imp_BCryptDestroyKey
0x18000d298  jmp     loc_18000D1A1
```
