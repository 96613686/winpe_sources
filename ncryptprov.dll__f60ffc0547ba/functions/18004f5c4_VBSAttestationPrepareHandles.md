# VBSAttestationPrepareHandles

- ea: `0x18004f5c4`
- end: `0x18004f784`
- name: `VBSAttestationPrepareHandles`
- size: `448`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, NCRYPT_HANDLE, NCRYPT_HANDLE, BCRYPT_KEY_HANDLE *phKey, BCRYPT_KEY_HANDLE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004f87c`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x18004f354`
- `0x18004f5c4`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18004f75c`
- `bcrypt!BCryptImportKeyPair` at `0x18004f75c`
- `ncrypt!NCryptGetProperty` at `0x18004f698`
- `ncrypt!NCryptGetProperty` at `0x18004f6ff`
- `ncrypt!NCryptGetProperty` at `0x18004f698`
- `ncrypt!NCryptGetProperty` at `0x18004f6ff`

## string_xrefs

- `0x18004f5f7`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`
- `0x18004f62f`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`
- `0x18004f720`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`

## pseudocode

```c
__int64 __fastcall VBSAttestationPrepareHandles(
        NCRYPT_HANDLE hObject,
        NCRYPT_HANDLE a2,
        NCRYPT_HANDLE a3,
        BCRYPT_KEY_HANDLE *phKey,
        BCRYPT_KEY_HANDLE *phKeya)
{
  SECURITY_STATUS Property; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  BYTE *v11; // rdi
  SECURITY_STATUS v13; // eax
  __int64 v14; // r9
  __int64 v15; // rcx
  DWORD cbOutput[14]; // [rsp+40h] [rbp-38h] BYREF

  cbOutput[0] = 0;
  Property = VBSAttestationNCrypt2BCryptPublicKey(a2, phKey);
  v8 = Property;
  if ( Property < 0 )
  {
    v9 = 528;
LABEL_3:
    v10 = (unsigned int)Property;
LABEL_4:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v9);
    return v8;
  }
  if ( a3 )
  {
    v11 = 0;
    v8 = VBSAttestationNCrypt2BCryptPublicKey(a3, phKeya);
    goto LABEL_7;
  }
  if ( !hObject )
  {
    v8 = -1073741811;
    v9 = 541;
    v10 = 3221225485LL;
    goto LABEL_4;
  }
  Property = NCryptGetProperty(hObject, L"VBS_ROOT_PUB", 0, cbOutput[0], cbOutput, 0);
  v8 = Property;
  if ( Property < 0 )
  {
    v9 = 554;
    goto LABEL_3;
  }
  v11 = (BYTE *)SafeAllocaAllocateFromHeap(cbOutput[0]);
  if ( !v11 )
  {
    v8 = -1073741801;
    v9 = 562;
    v10 = 3221225495LL;
    goto LABEL_4;
  }
  v13 = NCryptGetProperty(hObject, L"VBS_ROOT_PUB", v11, cbOutput[0], cbOutput, 0);
  v8 = v13;
  if ( v13 < 0 )
  {
    v14 = 575;
    v15 = (unsigned int)v13;
LABEL_20:
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v14);
LABEL_10:
    MSCryptFree(v11);
    return v8;
  }
  v8 = BCryptImportKeyPair((BCRYPT_ALG_HANDLE)0xE1, 0, L"PUBLICBLOB", phKeya, v11, cbOutput[0], 0);
  if ( (v8 & 0x80000000) != 0 )
  {
    v8 = -1073741595;
    v14 = 591;
    v15 = 3221225701LL;
    goto LABEL_20;
  }
LABEL_7:
  if ( v8 )
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", 598);
  if ( v11 )
    goto LABEL_10;
  return v8;
}

```

## disassembly

```asm
0x18004f5c4  push    rbx
0x18004f5c6  push    rbp
0x18004f5c7  push    rsi
0x18004f5c8  push    rdi
0x18004f5c9  sub     rsp, 58h
0x18004f5cd  mov     rax, rdx
0x18004f5d0  mov     [rsp+78h+cbOutput], 0
0x18004f5d8  mov     rsi, rcx
0x18004f5db  mov     rdx, r9; phKey
0x18004f5de  mov     rcx, rax; hObject
0x18004f5e1  mov     rbp, r8
0x18004f5e4  call    VBSAttestationNCrypt2BCryptPublicKey
0x18004f5e9  mov     ebx, eax
0x18004f5eb  test    eax, eax
0x18004f5ed  jns     short loc_18004F60C
0x18004f5ef  mov     r9d, 210h
0x18004f5f5  mov     ecx, eax
0x18004f5f7  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f5fe  lea     rdx, aStatus; "Status"
0x18004f605  call    DebugTraceError
0x18004f60a  jmp     short loc_18004F651
0x18004f60c  test    rbp, rbp
0x18004f60f  jz      short loc_18004F65D
0x18004f611  mov     rdx, [rsp+78h+phKey]; phKey
0x18004f619  xor     edi, edi
0x18004f61b  mov     rcx, rbp; hObject
0x18004f61e  call    VBSAttestationNCrypt2BCryptPublicKey
0x18004f623  mov     ebx, eax
0x18004f625  test    ebx, ebx
0x18004f627  jz      short loc_18004F644
0x18004f629  mov     r9d, 256h
0x18004f62f  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f636  lea     rdx, aStatus; "Status"
0x18004f63d  mov     ecx, ebx
0x18004f63f  call    DebugTraceError
0x18004f644  test    rdi, rdi
0x18004f647  jz      short loc_18004F651
0x18004f649  mov     rcx, rdi
0x18004f64c  call    MSCryptFree
0x18004f651  mov     eax, ebx
0x18004f653  add     rsp, 58h
0x18004f657  pop     rdi
0x18004f658  pop     rsi
0x18004f659  pop     rbp
0x18004f65a  pop     rbx
0x18004f65b  retn
0x18004f65d  test    rsi, rsi
0x18004f660  jnz     short loc_18004F674
0x18004f662  mov     ebx, 0C000000Dh
0x18004f667  mov     r9d, 21Dh
0x18004f66d  mov     ecx, 0C000000Dh
0x18004f672  jmp     short loc_18004F5F7
0x18004f674  mov     r9d, [rsp+78h+cbOutput]; cbOutput
0x18004f679  lea     rax, [rsp+78h+cbOutput]
0x18004f67e  mov     [rsp+78h+dwFlags], 0; dwFlags
0x18004f686  lea     rdx, aVbsRootPub; "VBS_ROOT_PUB"
0x18004f68d  xor     r8d, r8d; pbOutput
0x18004f690  mov     [rsp+78h+pcbResult], rax; pcbResult
0x18004f695  mov     rcx, rsi; hObject
0x18004f698  call    cs:__imp_NCryptGetProperty
0x18004f69f  nop     dword ptr [rax+rax+00h]
0x18004f6a4  mov     ebx, eax
0x18004f6a6  test    eax, eax
0x18004f6a8  jns     short loc_18004F6B5
0x18004f6aa  mov     r9d, 22Ah
0x18004f6b0  jmp     loc_18004F5F5
0x18004f6b5  mov     ecx, [rsp+78h+cbOutput]
0x18004f6b9  call    SafeAllocaAllocateFromHeap
0x18004f6be  mov     rdi, rax
0x18004f6c1  test    rax, rax
0x18004f6c4  jnz     short loc_18004F6DB
0x18004f6c6  mov     ebx, 0C0000017h
0x18004f6cb  mov     r9d, 232h
0x18004f6d1  mov     ecx, 0C0000017h
0x18004f6d6  jmp     loc_18004F5F7
0x18004f6db  mov     r9d, [rsp+78h+cbOutput]; cbOutput
0x18004f6e0  lea     rax, [rsp+78h+cbOutput]
0x18004f6e5  mov     [rsp+78h+dwFlags], 0; dwFlags
0x18004f6ed  lea     rdx, aVbsRootPub; "VBS_ROOT_PUB"
0x18004f6f4  mov     r8, rdi; pbOutput
0x18004f6f7  mov     [rsp+78h+pcbResult], rax; pcbResult
0x18004f6fc  mov     rcx, rsi; hObject
0x18004f6ff  call    cs:__imp_NCryptGetProperty
0x18004f706  nop     dword ptr [rax+rax+00h]
0x18004f70b  mov     ebx, eax
0x18004f70d  test    eax, eax
0x18004f70f  jns     short loc_18004F731
0x18004f711  mov     r9d, 23Fh
0x18004f717  mov     ecx, eax
0x18004f719  lea     rdx, aStatus; "Status"
0x18004f720  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f727  call    DebugTraceError
0x18004f72c  jmp     loc_18004F649
0x18004f731  mov     eax, [rsp+78h+cbOutput]
0x18004f735  lea     r8, aPublicblob; "PUBLICBLOB"
0x18004f73c  mov     r9, [rsp+78h+phKey]; phKey
0x18004f744  xor     edx, edx; hImportKey
0x18004f746  mov     [rsp+78h+var_48], 0; dwFlags
0x18004f74e  mov     ecx, 0E1h; hAlgorithm
0x18004f753  mov     [rsp+78h+dwFlags], eax; cbInput
0x18004f757  mov     [rsp+78h+pcbResult], rdi; pbInput
0x18004f75c  call    cs:__imp_BCryptImportKeyPair
0x18004f763  nop     dword ptr [rax+rax+00h]
0x18004f768  mov     ebx, eax
0x18004f76a  test    eax, eax
0x18004f76c  jns     loc_18004F625
0x18004f772  mov     ebx, 0C00000E5h
0x18004f777  mov     r9d, 24Fh
0x18004f77d  mov     ecx, 0C00000E5h
0x18004f782  jmp     short loc_18004F719
```
