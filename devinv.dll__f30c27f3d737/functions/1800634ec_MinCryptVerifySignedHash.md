# MinCryptVerifySignedHash

- ea: `0x1800634ec`
- end: `0x1800636fb`
- name: `MinCryptVerifySignedHash`
- size: `527`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, PUCHAR pbHash@<rdx>, ULONG cbHash@<r8d>, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180063008`
- `0x180063a30`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x1800627c8`
- `0x180062bac`
- `0x1800632d4`
- `0x1800634ec`
- `0x18010cb94`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180063618`
- `ntdll!RtlNtStatusToDosError` at `0x180063618`
- `bcrypt!BCryptDestroyKey` at `0x1800636c2`
- `bcrypt!BCryptDestroyKey` at `0x1800636c2`
- `bcrypt!BCryptVerifySignature` at `0x1800636a4`
- `bcrypt!BCryptVerifySignature` at `0x1800636a4`
- `bcrypt!BCryptImportKeyPair` at `0x18006365b`
- `bcrypt!BCryptImportKeyPair` at `0x18006365b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800636d4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800636d4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006360c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006360c`

## pseudocode

```c
__int64 __fastcall MinCryptVerifySignedHash(unsigned int a1, PUCHAR pbHash, ULONG cbHash, __int64 a4, int *a5)
{
  int v9; // edx
  __int64 v10; // rcx
  ULONG v11; // ebx
  int v12; // eax
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-B8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *pPaddingInfo; // [rsp+58h] [rbp-A8h] BYREF
  UCHAR pbInput[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+6Ch] [rbp-94h]
  _BYTE v21[16]; // [rsp+280h] [rbp+180h] BYREF
  int v22; // [rsp+290h] [rbp+190h]
  _BYTE v23[16]; // [rsp+2B0h] [rbp+1B0h] BYREF
  struct _CRYPTOAPI_BLOB v24; // [rsp+2C0h] [rbp+1C0h] BYREF

  memset_0(v21, 0, 0x40u);
  memset_0(&v24, 0, 0x40u);
  memset_0(pbInput, 0, 0x21Cu);
  v9 = *a5;
  v10 = *((_QWORD *)a5 + 1);
  phAlgorithm = 0;
  phKey = 0;
  pPaddingInfo = 0;
  v14 = 3;
  if ( (int)MinAsn1ExtractValues(v10, v9, (unsigned int)&v14, (unsigned int)&qword_180118BC0, 4, (__int64)v21) <= 0
    || v22 <= 0
    || (int)MinAsn1ParseRSAPublicKey(v23, &v24) <= 0 )
  {
    v11 = -2146893803;
  }
  else
  {
    v11 = I_ConvertParsedRSAPubKeyToBCryptPubKey(&v24, (struct BCRYPT_PUB_KEY_CONTENT *)pbInput);
    if ( v11 )
      goto LABEL_13;
    v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", L"Microsoft Primitive Provider", 0);
    if ( v12 < 0 )
      goto LABEL_6;
    v12 = BCryptImportKeyPair(phAlgorithm, 0, L"RSAPUBLICBLOB", &phKey, pbInput, v20 + 24 + v19, 0);
    if ( v12 < 0 )
      goto LABEL_6;
    pPaddingInfo = CapiAlgIdToCngAlgId(a1);
    if ( !pPaddingInfo )
    {
      v11 = -2146893816;
      goto LABEL_13;
    }
    v12 = BCryptVerifySignature(phKey, &pPaddingInfo, pbHash, cbHash, *(PUCHAR *)(a4 + 8), *(_DWORD *)a4, 2u);
    if ( v12 < 0 )
LABEL_6:
      v11 = RtlNtStatusToDosError(v12);
  }
LABEL_13:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v11;
}

```

## disassembly

```asm
0x1800634ec  push    rbp
0x1800634ee  push    rbx
0x1800634ef  push    rsi
0x1800634f0  push    rdi
0x1800634f1  push    r14
0x1800634f3  push    r15
0x1800634f5  lea     rbp, [rsp-218h]
0x1800634fd  sub     rsp, 318h
0x180063504  mov     rax, cs:__security_cookie
0x18006350b  xor     rax, rsp
0x18006350e  mov     [rbp+240h+var_40], rax
0x180063515  mov     rbx, [rbp+240h+arg_20]
0x18006351c  mov     r14, rdx
0x18006351f  xor     edx, edx; Val
0x180063521  mov     r15d, r8d
0x180063524  mov     esi, ecx
0x180063526  mov     rdi, r9
0x180063529  lea     rcx, [rbp+240h+var_C0]; void *
0x180063530  lea     r8d, [rdx+40h]; Size
0x180063534  call    memset_0
0x180063539  xor     edx, edx; Val
0x18006353b  lea     rcx, [rbp+240h+var_80]; void *
0x180063542  lea     r8d, [rdx+40h]; Size
0x180063546  call    memset_0
0x18006354b  xor     edx, edx; Val
0x18006354d  lea     rcx, [rsp+340h+var_2E0]; void *
0x180063552  mov     r8d, 21Ch; Size
0x180063558  call    memset_0
0x18006355d  mov     edx, [rbx]
0x18006355f  lea     rax, [rbp+240h+var_C0]
0x180063566  mov     rcx, [rbx+8]
0x18006356a  lea     r9, qword_180118BC0
0x180063571  mov     qword ptr [rsp+340h+cbInput], rax
0x180063576  lea     r8, [rsp+340h+var_300]
0x18006357b  mov     dword ptr [rsp+340h+pbInput], 4
0x180063583  mov     [rsp+340h+phAlgorithm], 0
0x18006358c  mov     [rsp+340h+phKey], 0
0x180063595  mov     [rsp+340h+pPaddingInfo], 0
0x18006359e  mov     [rsp+340h+var_300], 3
0x1800635a6  call    MinAsn1ExtractValues
0x1800635ab  test    eax, eax
0x1800635ad  jle     loc_1800636B3
0x1800635b3  cmp     [rbp+240h+var_B0], 0
0x1800635ba  jle     loc_1800636B3
0x1800635c0  lea     rdx, [rbp+240h+var_80]
0x1800635c7  lea     rcx, [rbp+240h+var_90]
0x1800635ce  call    MinAsn1ParseRSAPublicKey
0x1800635d3  test    eax, eax
0x1800635d5  jle     loc_1800636B3
0x1800635db  lea     rdx, [rsp+340h+var_2E0]; struct BCRYPT_PUB_KEY_CONTENT *
0x1800635e0  lea     rcx, [rbp+240h+var_80]; struct _CRYPTOAPI_BLOB *
0x1800635e7  call    ?I_ConvertParsedRSAPubKeyToBCryptPubKey@@YAJQEAU_CRYPTOAPI_BLOB@@PEAUBCRYPT_PUB_KEY_CONTENT@@@Z; I_ConvertParsedRSAPubKeyToBCryptPubKey(_CRYPTOAPI_BLOB * const,BCRYPT_PUB_KEY_CONTENT *)
0x1800635ec  mov     ebx, eax
0x1800635ee  test    eax, eax
0x1800635f0  jnz     loc_1800636B8
0x1800635f6  xor     r9d, r9d; dwFlags
0x1800635f9  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180063600  lea     rdx, pszAlgId; "RSA"
0x180063607  lea     rcx, [rsp+340h+phAlgorithm]; phAlgorithm
0x18006360c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180063612  test    eax, eax
0x180063614  jns     short loc_180063625
0x180063616  mov     ecx, eax; Status
0x180063618  call    cs:__imp_RtlNtStatusToDosError
0x18006361e  mov     ebx, eax
0x180063620  jmp     loc_1800636B8
0x180063625  mov     eax, [rsp+340h+var_2D4]
0x180063629  lea     r9, [rsp+340h+phKey]; phKey
0x18006362e  mov     edx, [rsp+340h+var_2D8]
0x180063632  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x180063639  mov     rcx, [rsp+340h+phAlgorithm]; hAlgorithm
0x18006363e  add     eax, 18h
0x180063641  add     edx, eax
0x180063643  mov     [rsp+340h+dwFlags], 0; dwFlags
0x18006364b  mov     [rsp+340h+cbInput], edx; cbInput
0x18006364f  lea     rax, [rsp+340h+var_2E0]
0x180063654  xor     edx, edx; hImportKey
0x180063656  mov     [rsp+340h+pbInput], rax; pbInput
0x18006365b  call    cs:__imp_BCryptImportKeyPair
0x180063661  test    eax, eax
0x180063663  js      short loc_180063616
0x180063665  mov     ecx, esi; unsigned int
0x180063667  call    ?CapiAlgIdToCngAlgId@@YAPEBGI@Z; CapiAlgIdToCngAlgId(uint)
0x18006366c  mov     [rsp+340h+pPaddingInfo], rax
0x180063671  test    rax, rax
0x180063674  jnz     short loc_18006367D
0x180063676  mov     ebx, 80090008h
0x18006367b  jmp     short loc_1800636B8
0x18006367d  mov     eax, [rdi]
0x18006367f  lea     rdx, [rsp+340h+pPaddingInfo]; pPaddingInfo
0x180063684  mov     rcx, [rsp+340h+phKey]; hKey
0x180063689  mov     r9d, r15d; cbHash
0x18006368c  mov     [rsp+340h+dwFlags], 2; dwFlags
0x180063694  mov     r8, r14; pbHash
0x180063697  mov     [rsp+340h+cbInput], eax; cbSignature
0x18006369b  mov     rax, [rdi+8]
0x18006369f  mov     [rsp+340h+pbInput], rax; pbSignature
0x1800636a4  call    cs:__imp_BCryptVerifySignature
0x1800636aa  test    eax, eax
0x1800636ac  jns     short loc_1800636B8
0x1800636ae  jmp     loc_180063616
0x1800636b3  mov     ebx, 80090015h
0x1800636b8  mov     rcx, [rsp+340h+phKey]; hKey
0x1800636bd  test    rcx, rcx
0x1800636c0  jz      short loc_1800636C8
0x1800636c2  call    cs:__imp_BCryptDestroyKey
0x1800636c8  mov     rcx, [rsp+340h+phAlgorithm]; hAlgorithm
0x1800636cd  test    rcx, rcx
0x1800636d0  jz      short loc_1800636DA
0x1800636d2  xor     edx, edx; dwFlags
0x1800636d4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800636da  mov     eax, ebx
0x1800636dc  mov     rcx, [rbp+240h+var_40]
0x1800636e3  xor     rcx, rsp; StackCookie
0x1800636e6  call    __security_check_cookie
0x1800636eb  add     rsp, 318h
0x1800636f2  pop     r15
0x1800636f4  pop     r14
0x1800636f6  pop     rdi
0x1800636f7  pop     rsi
0x1800636f8  pop     rbx
0x1800636f9  pop     rbp
0x1800636fa  retn
```
