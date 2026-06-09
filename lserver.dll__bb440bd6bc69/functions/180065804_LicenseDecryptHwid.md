# LicenseDecryptHwid

- ea: `0x180065804`
- end: `0x18006596d`
- name: `LicenseDecryptHwid`
- size: `361`
- prototype: `__int64 __fastcall(UCHAR *pbInput, unsigned int, __int64, int, PUCHAR pbIV)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180018510`
- `0x18001e6d4`
- `0x18002cba4`
- `0x18006421c`
- `0x180073490`

## callees

- `0x180065804`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800658ac`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800658ac`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180065941`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180065941`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180065872`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180065872`
- `bcrypt!BCryptDestroyKey` at `0x180065925`
- `bcrypt!BCryptDestroyKey` at `0x180065925`
- `bcrypt!BCryptEncrypt` at `0x1800658fc`
- `bcrypt!BCryptEncrypt` at `0x1800658fc`

## pseudocode

```c
__int64 __fastcall LicenseDecryptHwid(UCHAR *pbInput, unsigned int a2, __int64 a3, int a4, PUCHAR pbIV)
{
  UCHAR *pbSecret; // rbx
  unsigned int v8; // ebx
  BCRYPT_KEY_HANDLE v9; // rcx
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-10h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-8h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp+10h] BYREF

  phAlgorithm = 0;
  phKey = 0;
  pcbResult = 0;
  if ( !pbInput )
    return 3;
  if ( a2 < 0x14 )
    return 3;
  if ( !a3 )
    return 3;
  if ( a4 != 16 )
    return 3;
  pbSecret = pbIV;
  if ( !pbIV )
    return 3;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"RC4", 0, 0) < 0
    || BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, 0x10u, 0) < 0
    || (v9 = phKey,
        *(_OWORD *)pbInput = *(_OWORD *)a3,
        *((_DWORD *)pbInput + 4) = *(_DWORD *)(a3 + 16),
        BCryptEncrypt(v9, pbInput, 0x14u, 0, 0, 0, pbInput, 0x14u, &pcbResult, 0) < 0) )
  {
    v8 = 5;
  }
  else
  {
    v8 = 0;
    if ( pcbResult != 20 )
      v8 = 37;
  }
  if ( phKey )
  {
    BCryptDestroyKey(phKey);
    phKey = 0;
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v8;
}

```

## disassembly

```asm
0x180065804  mov     [rsp-8+arg_8], rbx
0x180065809  mov     [rsp-8+arg_10], rsi
0x18006580e  mov     [rsp-8+arg_18], rdi
0x180065813  push    rbp
0x180065814  mov     rbp, rsp
0x180065817  sub     rsp, 60h
0x18006581b  and     [rbp+phAlgorithm], 0
0x180065820  mov     rsi, r8
0x180065823  and     [rbp+phKey], 0
0x180065828  mov     rdi, rcx
0x18006582b  and     [rbp+arg_0], 0
0x18006582f  test    rcx, rcx
0x180065832  jz      loc_180065951
0x180065838  cmp     edx, 14h
0x18006583b  jb      loc_180065951
0x180065841  test    r8, r8
0x180065844  jz      loc_180065951
0x18006584a  cmp     r9d, 10h
0x18006584e  jnz     loc_180065951
0x180065854  mov     rbx, [rbp+pbIV]
0x180065858  test    rbx, rbx
0x18006585b  jz      loc_180065951
0x180065861  xor     r9d, r9d; dwFlags
0x180065864  lea     rdx, pszAlgId; "RC4"
0x18006586b  xor     r8d, r8d; pszImplementation
0x18006586e  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180065872  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180065879  nop     dword ptr [rax+rax+00h]
0x18006587e  test    eax, eax
0x180065880  jns     short loc_18006588C
0x180065882  mov     ebx, 5
0x180065887  jmp     loc_18006591C
0x18006588c  and     dword ptr [rsp+60h+pbOutput], 0
0x180065891  lea     rdx, [rbp+phKey]; phKey
0x180065895  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180065899  xor     r9d, r9d; cbKeyObject
0x18006589c  mov     [rsp+60h+cbSecret], 10h; cbIV
0x1800658a4  xor     r8d, r8d; pbKeyObject
0x1800658a7  mov     [rsp+60h+pbSecret], rbx; pbIV
0x1800658ac  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800658b3  nop     dword ptr [rax+rax+00h]
0x1800658b8  test    eax, eax
0x1800658ba  js      short loc_180065882
0x1800658bc  and     [rsp+60h+var_18], 0
0x1800658c1  xor     r9d, r9d; pPaddingInfo
0x1800658c4  movups  xmm0, xmmword ptr [rsi]
0x1800658c7  mov     rcx, [rbp+phKey]; hKey
0x1800658cb  mov     rdx, rdi; pbInput
0x1800658ce  movups  xmmword ptr [rdi], xmm0
0x1800658d1  mov     eax, [rsi+10h]
0x1800658d4  lea     r8d, [r9+14h]; cbInput
0x1800658d8  mov     [rdi+10h], eax
0x1800658db  lea     rax, [rbp+arg_0]
0x1800658df  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800658e4  mov     [rsp+60h+cbOutput], 14h; cbOutput
0x1800658ec  mov     [rsp+60h+pbOutput], rdi; pbOutput
0x1800658f1  and     [rsp+60h+cbSecret], 0
0x1800658f6  and     [rsp+60h+pbSecret], 0
0x1800658fc  call    cs:__imp_BCryptEncrypt
0x180065903  nop     dword ptr [rax+rax+00h]
0x180065908  test    eax, eax
0x18006590a  js      loc_180065882
0x180065910  xor     ebx, ebx
0x180065912  cmp     [rbp+arg_0], 14h
0x180065916  lea     eax, [rbx+25h]
0x180065919  cmovnz  ebx, eax
0x18006591c  mov     rcx, [rbp+phKey]; hKey
0x180065920  test    rcx, rcx
0x180065923  jz      short loc_180065936
0x180065925  call    cs:__imp_BCryptDestroyKey
0x18006592c  nop     dword ptr [rax+rax+00h]
0x180065931  and     [rbp+phKey], 0
0x180065936  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18006593a  test    rcx, rcx
0x18006593d  jz      short loc_18006594D
0x18006593f  xor     edx, edx; dwFlags
0x180065941  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180065948  nop     dword ptr [rax+rax+00h]
0x18006594d  mov     eax, ebx
0x18006594f  jmp     short loc_180065956
0x180065951  mov     eax, 3
0x180065956  lea     r11, [rsp+60h+var_s0]
0x18006595b  mov     rbx, [r11+18h]
0x18006595f  mov     rsi, [r11+20h]
0x180065963  mov     rdi, [r11+28h]
0x180065967  mov     rsp, r11
0x18006596a  pop     rbp
0x18006596b  retn
```
