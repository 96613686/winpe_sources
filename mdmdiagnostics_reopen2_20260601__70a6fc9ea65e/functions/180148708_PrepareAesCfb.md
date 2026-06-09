# PrepareAesCfb

- ea: `0x180148708`
- end: `0x180148856`
- name: `PrepareAesCfb`
- size: `334`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180148860`
- `0x180148a30`

## callees

- `0x180148708`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x1801487b6`
- `bcrypt!BCryptSetProperty` at `0x1801487e5`
- `bcrypt!BCryptSetProperty` at `0x1801487b6`
- `bcrypt!BCryptSetProperty` at `0x1801487e5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18014874f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18014874f`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180148784`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180148784`
- `bcrypt!BCryptDestroyKey` at `0x180148823`
- `bcrypt!BCryptDestroyKey` at `0x180148823`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18014883a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18014883a`

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
0x180148708  push    rbp
0x18014870a  push    rbx
0x18014870b  push    rsi
0x18014870c  push    rdi
0x18014870d  push    r14
0x18014870f  push    r15
0x180148711  mov     rbp, rsp
0x180148714  sub     rsp, 68h
0x180148718  mov     r14, r9
0x18014871b  mov     [rbp+phAlgorithm], 0
0x180148723  mov     r15, r8
0x180148726  mov     [rbp+phKey], 0
0x18014872e  mov     edi, edx
0x180148730  mov     dword ptr [rbp+pbInput], 10h
0x180148737  mov     rsi, rcx
0x18014873a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180148741  xor     r9d, r9d; dwFlags
0x180148744  lea     rdx, aAes; "AES"
0x18014874b  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18014874f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180148756  nop     dword ptr [rax+rax+00h]
0x18014875b  mov     ebx, eax
0x18014875d  test    eax, eax
0x18014875f  js      loc_180148813
0x180148765  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180148769  lea     rdx, [rbp+phKey]; phKey
0x18014876d  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180148775  xor     r9d, r9d; cbKeyObject
0x180148778  mov     [rsp+68h+cbSecret], edi; cbSecret
0x18014877c  xor     r8d, r8d; pbKeyObject
0x18014877f  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x180148784  call    cs:__imp_BCryptGenerateSymmetricKey
0x18014878b  nop     dword ptr [rax+rax+00h]
0x180148790  mov     ebx, eax
0x180148792  test    eax, eax
0x180148794  js      short loc_180148813
0x180148796  mov     rcx, [rbp+phKey]; hObject
0x18014879a  lea     r8, pbInput; "ChainingModeCFB"
0x1801487a1  mov     r9d, 20h ; ' '; cbInput
0x1801487a7  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x1801487af  lea     rdx, aChainingmode; "ChainingMode"
0x1801487b6  call    cs:__imp_BCryptSetProperty
0x1801487bd  nop     dword ptr [rax+rax+00h]
0x1801487c2  mov     ebx, eax
0x1801487c4  test    eax, eax
0x1801487c6  js      short loc_180148813
0x1801487c8  mov     rcx, [rbp+phKey]; hObject
0x1801487cc  lea     r8, [rbp+pbInput]; pbInput
0x1801487d0  mov     r9d, 4; cbInput
0x1801487d6  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x1801487de  lea     rdx, aMessageblockle; "MessageBlockLength"
0x1801487e5  call    cs:__imp_BCryptSetProperty
0x1801487ec  nop     dword ptr [rax+rax+00h]
0x1801487f1  mov     ebx, eax
0x1801487f3  test    eax, eax
0x1801487f5  js      short loc_180148813
0x1801487f7  mov     rax, [rbp+phAlgorithm]
0x1801487fb  xor     ecx, ecx
0x1801487fd  mov     [r15], rax
0x180148800  mov     rax, [rbp+phKey]
0x180148804  mov     [r14], rax
0x180148807  xor     eax, eax
0x180148809  mov     [rbp+phKey], rax
0x18014880d  mov     [rbp+phAlgorithm], rcx
0x180148811  jmp     short loc_18014881B
0x180148813  mov     rcx, [rbp+phAlgorithm]
0x180148817  mov     rax, [rbp+phKey]
0x18014881b  test    rax, rax
0x18014881e  jz      short loc_180148833
0x180148820  mov     rcx, rax; hKey
0x180148823  call    cs:__imp_BCryptDestroyKey
0x18014882a  nop     dword ptr [rax+rax+00h]
0x18014882f  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180148833  test    rcx, rcx
0x180148836  jz      short loc_180148846
0x180148838  xor     edx, edx; dwFlags
0x18014883a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180148841  nop     dword ptr [rax+rax+00h]
0x180148846  mov     eax, ebx
0x180148848  add     rsp, 68h
0x18014884c  pop     r15
0x18014884e  pop     r14
0x180148850  pop     rdi
0x180148851  pop     rsi
0x180148852  pop     rbx
0x180148853  pop     rbp
0x180148854  retn
```
