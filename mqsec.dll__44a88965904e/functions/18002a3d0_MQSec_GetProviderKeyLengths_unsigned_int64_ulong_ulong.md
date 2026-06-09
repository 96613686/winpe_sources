# MQSec_GetProviderKeyLengths(unsigned __int64,ulong *,ulong *)

- ea: `0x18002a3d0`
- end: `0x18002a558`
- name: `?MQSec_GetProviderKeyLengths@@YAX_KPEAK1@Z`
- size: `392`
- prototype: `void __fastcall(HCRYPTPROV hProv, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001cfc0`
- `0x18002aaa8`

## callees

- `0x18001786c`
- `0x18002a3d0`
- `0x18002f0ba`
- `0x18002f0e0`

## import_xrefs

- `ADVAPI32!CryptGetProvParam` at `0x18002a533`
- `ADVAPI32!CryptGetProvParam` at `0x18002a533`
- `KERNEL32!GetLastError` at `0x18002a4e4`
- `KERNEL32!GetLastError` at `0x18002a4e4`

## string_xrefs

- `0x18002a416`: `security\KeyExchangeKeySize`
- `0x18002a479`: `security\SignatureKeySize`

## pseudocode

```c
void __fastcall MQSec_GetProviderKeyLengths(HCRYPTPROV hProv, unsigned int *a2, unsigned int *a3)
{
  unsigned int v6; // eax
  bool v7; // zf
  unsigned int v8; // eax
  DWORD dwFlags; // [rsp+20h] [rbp-79h]
  DWORD pdwDataLen; // [rsp+34h] [rbp-65h] BYREF
  int v11; // [rsp+38h] [rbp-61h] BYREF
  __int64 v12; // [rsp+40h] [rbp-59h]
  const wchar_t *v13; // [rsp+48h] [rbp-51h]
  int v14; // [rsp+50h] [rbp-49h]
  __int64 v15; // [rsp+58h] [rbp-41h]
  BYTE pbData[12]; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v17; // [rsp+6Ch] [rbp-2Dh]

  if ( byte_1800431E8 )
  {
    v6 = dword_1800431E4;
  }
  else
  {
    v11 = 0;
    v12 = 0;
    v13 = L"security\\KeyExchangeKeySize";
    v14 = 2048;
    v15 = 0;
    QueryValueInternal((struct RegEntry *)&v11);
    v6 = 2048;
    dword_1800431E4 = 2048;
    byte_1800431E8 = 1;
  }
  v7 = byte_1800431E0 == 0;
  *a3 = v6;
  if ( v7 )
  {
    v11 = 0;
    v12 = 0;
    v13 = L"security\\SignatureKeySize";
    v14 = 2048;
    v15 = 0;
    QueryValueInternal((struct RegEntry *)&v11);
    v8 = 2048;
    dword_1800431DC = 2048;
    byte_1800431E0 = 1;
  }
  else
  {
    v8 = dword_1800431DC;
  }
  *a2 = v8;
  memset_0(pbData, 0, 0x58u);
  for ( dwFlags = 1; ; dwFlags = 0 )
  {
    pdwDataLen = 88;
    if ( !CryptGetProvParam(hProv, 0x16u, pbData, &pdwDataLen, dwFlags) || GetLastError() == 259 )
      break;
    if ( *(_DWORD *)pbData == 41984 )
    {
      if ( *a3 > v17 )
        *a3 = v17;
    }
    else if ( *(_DWORD *)pbData == 9216 && *a2 > v17 )
    {
      *a2 = v17;
    }
  }
}

```

## disassembly

```asm
0x18002a3d0  push    rbp
0x18002a3d2  push    rbx
0x18002a3d3  push    rsi
0x18002a3d4  push    rdi
0x18002a3d5  push    r15
0x18002a3d7  lea     rbp, [rsp-37h]
0x18002a3dc  sub     rsp, 0D0h
0x18002a3e3  mov     rax, cs:__security_cookie
0x18002a3ea  xor     rax, rsp
0x18002a3ed  mov     [rbp+57h+var_30], rax
0x18002a3f1  cmp     cs:byte_1800431E8, 0
0x18002a3f8  mov     rbx, r8
0x18002a3fb  mov     rdi, rdx
0x18002a3fe  mov     rsi, rcx
0x18002a401  mov     r15d, 800h
0x18002a407  jnz     short loc_18002A45B
0x18002a409  mov     r9d, 4
0x18002a40f  mov     [rbp+57h+var_B8], 0
0x18002a416  lea     rax, aSecurityKeyexc; "security\\KeyExchangeKeySize"
0x18002a41d  mov     [rbp+57h+var_B0], 0
0x18002a425  mov     edx, r9d
0x18002a428  mov     [rbp+57h+var_A8], rax
0x18002a42c  lea     r8, [rbp+57h+var_C0]
0x18002a430  mov     [rbp+57h+var_A0], r15d
0x18002a434  lea     rcx, [rbp+57h+var_B8]; struct RegEntry *
0x18002a438  mov     [rbp+57h+var_98], 0
0x18002a440  mov     [rbp+57h+var_C0], r15d
0x18002a444  call    QueryValueInternal
0x18002a449  mov     eax, [rbp+57h+var_C0]
0x18002a44c  mov     cs:dword_1800431E4, eax
0x18002a452  mov     cs:byte_1800431E8, 1
0x18002a459  jmp     short loc_18002A461
0x18002a45b  mov     eax, cs:dword_1800431E4
0x18002a461  cmp     cs:byte_1800431E0, 0
0x18002a468  mov     [rbx], eax
0x18002a46a  jnz     short loc_18002A4BE
0x18002a46c  mov     r9d, 4
0x18002a472  mov     [rbp+57h+var_B8], 0
0x18002a479  lea     rax, aSecuritySignat; "security\\SignatureKeySize"
0x18002a480  mov     [rbp+57h+var_B0], 0
0x18002a488  mov     edx, r9d
0x18002a48b  mov     [rbp+57h+var_A8], rax
0x18002a48f  lea     r8, [rbp+57h+var_C0]
0x18002a493  mov     [rbp+57h+var_A0], r15d
0x18002a497  lea     rcx, [rbp+57h+var_B8]; struct RegEntry *
0x18002a49b  mov     [rbp+57h+var_98], 0
0x18002a4a3  mov     [rbp+57h+var_C0], r15d
0x18002a4a7  call    QueryValueInternal
0x18002a4ac  mov     eax, [rbp+57h+var_C0]
0x18002a4af  mov     cs:dword_1800431DC, eax
0x18002a4b5  mov     cs:byte_1800431E0, 1
0x18002a4bc  jmp     short loc_18002A4C4
0x18002a4be  mov     eax, cs:dword_1800431DC
0x18002a4c4  mov     r15d, 58h ; 'X'
0x18002a4ca  mov     [rdi], eax
0x18002a4cc  mov     r8d, r15d; Size
0x18002a4cf  lea     rcx, [rbp+57h+pbData]; void *
0x18002a4d3  xor     edx, edx; Val
0x18002a4d5  call    memset_0
0x18002a4da  mov     [rsp+0F0h+dwFlags], 1
0x18002a4e2  jmp     short loc_18002A51F
0x18002a4e4  call    cs:__imp_GetLastError
0x18002a4ea  cmp     eax, 103h
0x18002a4ef  jz      short loc_18002A53E
0x18002a4f1  cmp     dword ptr [rbp+57h+pbData], 0A400h
0x18002a4f8  jnz     short loc_18002A505
0x18002a4fa  mov     eax, [rbp+57h+var_84]
0x18002a4fd  cmp     [rbx], eax
0x18002a4ff  jbe     short loc_18002A517
0x18002a501  mov     [rbx], eax
0x18002a503  jmp     short loc_18002A517
0x18002a505  cmp     dword ptr [rbp+57h+pbData], 2400h
0x18002a50c  jnz     short loc_18002A517
0x18002a50e  mov     eax, [rbp+57h+var_84]
0x18002a511  cmp     [rdi], eax
0x18002a513  jbe     short loc_18002A517
0x18002a515  mov     [rdi], eax
0x18002a517  mov     [rsp+0F0h+dwFlags], 0; dwFlags
0x18002a51f  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18002a523  mov     [rbp+57h+pdwDataLen], r15d
0x18002a527  lea     r8, [rbp+57h+pbData]; pbData
0x18002a52b  mov     edx, 16h; dwParam
0x18002a530  mov     rcx, rsi; hProv
0x18002a533  call    cs:__imp_CryptGetProvParam
0x18002a539  cmp     eax, 1
0x18002a53c  jz      short loc_18002A4E4
0x18002a53e  mov     rcx, [rbp+57h+var_30]
0x18002a542  xor     rcx, rsp; StackCookie
0x18002a545  call    __security_check_cookie
0x18002a54a  add     rsp, 0D0h
0x18002a551  pop     r15
0x18002a553  pop     rdi
0x18002a554  pop     rsi
0x18002a555  pop     rbx
0x18002a556  pop     rbp
0x18002a557  retn
```
