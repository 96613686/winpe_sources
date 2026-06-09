# ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x180002310`
- end: `0x180002476`
- name: `?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z`
- size: `358`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_HASH_HANDLE hHash, unsigned int, PUCHAR pbSecret, ULONG cbSecret, PUCHAR pbInput, ULONG cbInput, PUCHAR pbHashObject, ULONG cbHashObject, PUCHAR pbOutput, ULONG)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18001199c`
- `0x180029818`
- `0x180029adc`
- `0x18002fab8`
- `0x18002ffac`
- `0x18003048c`
- `0x18003442c`
- `0x1800349e4`

## callees

- `0x180002310`
- `0x1800029d0`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800023bf`
- `bcrypt!BCryptFinishHash` at `0x1800023bf`
- `bcrypt!BCryptDestroyHash` at `0x180002402`
- `bcrypt!BCryptDestroyHash` at `0x180002402`
- `bcrypt!BCryptHashData` at `0x18000239c`
- `bcrypt!BCryptHashData` at `0x18000239c`
- `bcrypt!BCryptCreateHash` at `0x180002458`
- `bcrypt!BCryptCreateHash` at `0x180002458`

## pseudocode

```c
__int64 __fastcall ReusableHMAC(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_HASH_HANDLE hHash,
        unsigned int a3,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbHashObject,
        ULONG cbHashObject,
        PUCHAR pbOutput,
        ULONG a11)
{
  unsigned int v12; // ecx
  unsigned int v15; // esi
  unsigned int v16; // eax
  ULONG v17; // edi
  BCRYPT_HASH_HANDLE v18; // rcx
  BCRYPT_HASH_HANDLE hHasha; // [rsp+40h] [rbp-38h] BYREF

  hHasha = 0;
  v12 = 32772;
  if ( a3 != 32777 )
    v12 = a3;
  v15 = 0;
  if ( v12 == 32772 )
  {
    v16 = 20;
  }
  else
  {
    if ( v12 != 32782 )
      return v15;
    v16 = 64;
  }
  v17 = a11;
  if ( a11 > v16 )
    v17 = v16;
  if ( hAlgorithm || (hAlgorithm = (BCRYPT_ALG_HANDLE)GetBCryptProviderHandle(v12)) != 0 )
  {
    if ( hHash )
    {
      v18 = hHash;
      hHasha = hHash;
    }
    else
    {
      if ( BCryptCreateHash(hAlgorithm, &hHasha, pbHashObject, cbHashObject, pbSecret, cbSecret, 0) < 0 )
        goto LABEL_14;
      v18 = hHasha;
    }
    if ( BCryptHashData(v18, pbInput, cbInput, 0) >= 0 && BCryptFinishHash(hHasha, pbOutput, v17, 0) >= 0 )
      v15 = 1;
  }
LABEL_14:
  if ( hHasha && hHash != hHasha )
    BCryptDestroyHash(hHasha);
  return v15;
}

```

## disassembly

```asm
0x180002310  push    rbx
0x180002312  push    rbp
0x180002313  push    rsi
0x180002314  push    r14
0x180002316  sub     rsp, 58h
0x18000231a  xor     r14d, r14d
0x18000231d  mov     r10, rcx
0x180002320  cmp     r8d, 8009h
0x180002327  mov     [rsp+78h+hHash], r14
0x18000232c  mov     ecx, 8004h
0x180002331  mov     rbp, r9
0x180002334  cmovnz  ecx, r8d; unsigned int
0x180002338  mov     rbx, rdx
0x18000233b  mov     esi, r14d
0x18000233e  cmp     ecx, 8004h
0x180002344  jz      loc_1800023F8
0x18000234a  cmp     ecx, 800Eh
0x180002350  jnz     loc_1800023EB
0x180002356  mov     eax, 40h ; '@'
0x18000235b  mov     [rsp+78h+arg_0], rdi
0x180002363  mov     edi, [rsp+78h+arg_50]
0x18000236a  cmp     edi, eax
0x18000236c  cmova   edi, eax
0x18000236f  test    r10, r10
0x180002372  jz      loc_180002410
0x180002378  test    rbx, rbx
0x18000237b  jz      loc_18000242B
0x180002381  mov     rcx, rbx; hHash
0x180002384  mov     [rsp+78h+hHash], rbx
0x180002389  mov     r8d, [rsp+78h+cbInput]; cbInput
0x180002391  xor     r9d, r9d; dwFlags
0x180002394  mov     rdx, [rsp+78h+pbInput]; pbInput
0x18000239c  call    cs:__imp_BCryptHashData
0x1800023a3  nop     dword ptr [rax+rax+00h]
0x1800023a8  test    eax, eax
0x1800023aa  js      short loc_1800023D4
0x1800023ac  mov     rdx, [rsp+78h+pbOutput]; pbOutput
0x1800023b4  xor     r9d, r9d; dwFlags
0x1800023b7  mov     rcx, [rsp+78h+hHash]; hHash
0x1800023bc  mov     r8d, edi; cbOutput
0x1800023bf  call    cs:__imp_BCryptFinishHash
0x1800023c6  nop     dword ptr [rax+rax+00h]
0x1800023cb  test    eax, eax
0x1800023cd  js      short loc_1800023D4
0x1800023cf  mov     esi, 1
0x1800023d4  mov     rcx, [rsp+78h+hHash]; hHash
0x1800023d9  mov     rdi, [rsp+78h+arg_0]
0x1800023e1  test    rcx, rcx
0x1800023e4  jz      short loc_1800023EB
0x1800023e6  cmp     rbx, rcx
0x1800023e9  jnz     short loc_180002402
0x1800023eb  mov     eax, esi
0x1800023ed  add     rsp, 58h
0x1800023f1  pop     r14
0x1800023f3  pop     rsi
0x1800023f4  pop     rbp
0x1800023f5  pop     rbx
0x1800023f6  retn
0x1800023f8  mov     eax, 14h
0x1800023fd  jmp     loc_18000235B
0x180002402  call    cs:__imp_BCryptDestroyHash
0x180002409  nop     dword ptr [rax+rax+00h]
0x18000240e  jmp     short loc_1800023EB
0x180002410  xor     edx, edx
0x180002412  mov     r8d, 28h ; '('
0x180002418  call    GetBCryptProviderHandle
0x18000241d  mov     r10, rax
0x180002420  test    rax, rax
0x180002423  jnz     loc_180002378
0x180002429  jmp     short loc_1800023D4
0x18000242b  mov     eax, [rsp+78h+arg_20]
0x180002432  lea     rdx, [rsp+78h+hHash]; phHash
0x180002437  mov     r9d, [rsp+78h+cbHashObject]; cbHashObject
0x18000243f  mov     rcx, r10; hAlgorithm
0x180002442  mov     r8, [rsp+78h+pbHashObject]; pbHashObject
0x18000244a  mov     [rsp+78h+dwFlags], r14d; dwFlags
0x18000244f  mov     [rsp+78h+cbSecret], eax; cbSecret
0x180002453  mov     [rsp+78h+pbSecret], rbp; pbSecret
0x180002458  call    cs:__imp_BCryptCreateHash
0x18000245f  nop     dword ptr [rax+rax+00h]
0x180002464  test    eax, eax
0x180002466  js      loc_1800023D4
0x18000246c  mov     rcx, [rsp+78h+hHash]
0x180002471  jmp     loc_180002389
```
