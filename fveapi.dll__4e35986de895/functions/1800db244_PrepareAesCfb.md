# PrepareAesCfb

- ea: `0x1800db244`
- end: `0x1800db392`
- name: `PrepareAesCfb`
- size: `334`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800db3a0`
- `0x1800db5a0`

## callees

- `0x1800db244`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x1800db2f2`
- `bcrypt!BCryptSetProperty` at `0x1800db321`
- `bcrypt!BCryptSetProperty` at `0x1800db2f2`
- `bcrypt!BCryptSetProperty` at `0x1800db321`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800db28b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800db28b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800db376`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800db376`
- `bcrypt!BCryptDestroyKey` at `0x1800db35f`
- `bcrypt!BCryptDestroyKey` at `0x1800db35f`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800db2c0`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800db2c0`

## pseudocode

```c
__int64 __fastcall PrepareAesCfb(PUCHAR pbSecret, ULONG cbSecret, BCRYPT_ALG_HANDLE *a3, BCRYPT_KEY_HANDLE *a4)
{
  NTSTATUS v8; // ebx
  BCRYPT_ALG_HANDLE v9; // rcx
  BCRYPT_KEY_HANDLE v10; // rax
  UCHAR pbInput[8]; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF

  phAlgorithm = 0;
  phKey = 0;
  *(_DWORD *)pbInput = 16;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", L"Microsoft Primitive Provider", 0);
  if ( v8 < 0
    || (v8 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, cbSecret, 0), v8 < 0)
    || (v8 = BCryptSetProperty(phKey, L"ChainingMode", (PUCHAR)L"ChainingModeCFB", 0x20u, 0), v8 < 0)
    || (v8 = BCryptSetProperty(phKey, L"MessageBlockLength", pbInput, 4u, 0), v8 < 0) )
  {
    v9 = phAlgorithm;
    v10 = phKey;
  }
  else
  {
    v9 = 0;
    *a3 = phAlgorithm;
    *a4 = phKey;
    v10 = 0;
    phKey = 0;
    phAlgorithm = 0;
  }
  if ( v10 )
  {
    BCryptDestroyKey(v10);
    v9 = phAlgorithm;
  }
  if ( v9 )
    BCryptCloseAlgorithmProvider(v9, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800db244  push    rbp
0x1800db246  push    rbx
0x1800db247  push    rsi
0x1800db248  push    rdi
0x1800db249  push    r14
0x1800db24b  push    r15
0x1800db24d  mov     rbp, rsp
0x1800db250  sub     rsp, 68h
0x1800db254  mov     r14, r9
0x1800db257  mov     [rbp+phAlgorithm], 0
0x1800db25f  mov     r15, r8
0x1800db262  mov     [rbp+phKey], 0
0x1800db26a  mov     edi, edx
0x1800db26c  mov     dword ptr [rbp+pbInput], 10h
0x1800db273  mov     rsi, rcx
0x1800db276  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800db27d  xor     r9d, r9d; dwFlags
0x1800db280  lea     rdx, aAes; "AES"
0x1800db287  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800db28b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800db292  nop     dword ptr [rax+rax+00h]
0x1800db297  mov     ebx, eax
0x1800db299  test    eax, eax
0x1800db29b  js      loc_1800DB34F
0x1800db2a1  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800db2a5  lea     rdx, [rbp+phKey]; phKey
0x1800db2a9  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800db2b1  xor     r9d, r9d; cbKeyObject
0x1800db2b4  mov     [rsp+68h+cbSecret], edi; cbSecret
0x1800db2b8  xor     r8d, r8d; pbKeyObject
0x1800db2bb  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x1800db2c0  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800db2c7  nop     dword ptr [rax+rax+00h]
0x1800db2cc  mov     ebx, eax
0x1800db2ce  test    eax, eax
0x1800db2d0  js      short loc_1800DB34F
0x1800db2d2  mov     rcx, [rbp+phKey]; hObject
0x1800db2d6  lea     r8, aChainingmodecf; "ChainingModeCFB"
0x1800db2dd  mov     r9d, 20h ; ' '; cbInput
0x1800db2e3  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x1800db2eb  lea     rdx, aChainingmode; "ChainingMode"
0x1800db2f2  call    cs:__imp_BCryptSetProperty
0x1800db2f9  nop     dword ptr [rax+rax+00h]
0x1800db2fe  mov     ebx, eax
0x1800db300  test    eax, eax
0x1800db302  js      short loc_1800DB34F
0x1800db304  mov     rcx, [rbp+phKey]; hObject
0x1800db308  lea     r8, [rbp+pbInput]; pbInput
0x1800db30c  mov     r9d, 4; cbInput
0x1800db312  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x1800db31a  lea     rdx, aMessageblockle; "MessageBlockLength"
0x1800db321  call    cs:__imp_BCryptSetProperty
0x1800db328  nop     dword ptr [rax+rax+00h]
0x1800db32d  mov     ebx, eax
0x1800db32f  test    eax, eax
0x1800db331  js      short loc_1800DB34F
0x1800db333  mov     rax, [rbp+phAlgorithm]
0x1800db337  xor     ecx, ecx
0x1800db339  mov     [r15], rax
0x1800db33c  mov     rax, [rbp+phKey]
0x1800db340  mov     [r14], rax
0x1800db343  xor     eax, eax
0x1800db345  mov     [rbp+phKey], rax
0x1800db349  mov     [rbp+phAlgorithm], rcx
0x1800db34d  jmp     short loc_1800DB357
0x1800db34f  mov     rcx, [rbp+phAlgorithm]
0x1800db353  mov     rax, [rbp+phKey]
0x1800db357  test    rax, rax
0x1800db35a  jz      short loc_1800DB36F
0x1800db35c  mov     rcx, rax; hKey
0x1800db35f  call    cs:__imp_BCryptDestroyKey
0x1800db366  nop     dword ptr [rax+rax+00h]
0x1800db36b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800db36f  test    rcx, rcx
0x1800db372  jz      short loc_1800DB382
0x1800db374  xor     edx, edx; dwFlags
0x1800db376  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800db37d  nop     dword ptr [rax+rax+00h]
0x1800db382  mov     eax, ebx
0x1800db384  add     rsp, 68h
0x1800db388  pop     r15
0x1800db38a  pop     r14
0x1800db38c  pop     rdi
0x1800db38d  pop     rsi
0x1800db38e  pop     rbx
0x1800db38f  pop     rbp
0x1800db390  retn
```
