# VBSAttestationNCrypt2BCryptPublicKey

- ea: `0x18004f354`
- end: `0x18004f5bd`
- name: `VBSAttestationNCrypt2BCryptPublicKey`
- size: `617`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, BCRYPT_KEY_HANDLE *phKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004f5c4`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x18004f354`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18004f54d`
- `bcrypt!BCryptImportKeyPair` at `0x18004f54d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004f595`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004f595`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004f511`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004f511`
- `ncrypt!NCryptGetProperty` at `0x18004f48c`
- `ncrypt!NCryptGetProperty` at `0x18004f4ea`
- `ncrypt!NCryptGetProperty` at `0x18004f48c`
- `ncrypt!NCryptGetProperty` at `0x18004f4ea`
- `ncrypt!NCryptExportKey` at `0x18004f3b6`
- `ncrypt!NCryptExportKey` at `0x18004f438`
- `ncrypt!NCryptExportKey` at `0x18004f3b6`
- `ncrypt!NCryptExportKey` at `0x18004f438`

## string_xrefs

- `0x18004f3d7`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`
- `0x18004f459`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`
- `0x18004f565`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`

## pseudocode

```c
__int64 __fastcall VBSAttestationNCrypt2BCryptPublicKey(NCRYPT_HANDLE hObject, BCRYPT_KEY_HANDLE *phKey)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rcx
  DWORD cbOutput; // r14d
  BYTE *pbOutput; // rsi
  unsigned int Property; // eax
  __int64 v11; // r9
  __int64 v12; // rcx
  BYTE *v13; // rdi
  unsigned int v14; // eax
  __int64 v15; // r9
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-10h] BYREF
  DWORD v18; // [rsp+90h] [rbp+40h] BYREF
  DWORD cbInput; // [rsp+98h] [rbp+48h] BYREF

  cbInput = 0;
  v18 = 0;
  phAlgorithm = 0;
  v4 = NCryptExportKey(hObject, 0, L"PUBLICBLOB", 0, 0, 0, &cbInput, 0);
  v5 = v4;
  if ( v4 )
  {
    v6 = 396;
    v7 = v4;
LABEL_3:
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v6);
    goto LABEL_23;
  }
  cbOutput = cbInput;
  pbOutput = (BYTE *)SafeAllocaAllocateFromHeap(cbInput);
  if ( !pbOutput )
  {
    v5 = -1073741801;
    v6 = 405;
    v7 = 3221225495LL;
    goto LABEL_3;
  }
  Property = NCryptExportKey(hObject, 0, L"PUBLICBLOB", 0, pbOutput, cbOutput, &cbInput, 0);
  v5 = Property;
  if ( !Property )
  {
    Property = NCryptGetProperty(hObject, L"Algorithm Name", 0, v18, &v18, 0);
    v5 = Property;
    if ( Property )
    {
      v11 = 435;
      goto LABEL_8;
    }
    v13 = (BYTE *)SafeAllocaAllocateFromHeap(v18);
    if ( !v13 )
    {
      v5 = -1073741801;
      v11 = 443;
      v12 = 3221225495LL;
      goto LABEL_9;
    }
    v14 = NCryptGetProperty(hObject, L"Algorithm Name", v13, v18, &v18, 0);
    v5 = v14;
    if ( v14 )
    {
      v15 = 457;
    }
    else
    {
      v14 = BCryptOpenAlgorithmProvider(&phAlgorithm, (LPCWSTR)v13, 0, 0);
      v5 = v14;
      if ( v14 )
      {
        v15 = 469;
      }
      else
      {
        v14 = BCryptImportKeyPair(phAlgorithm, 0, L"PUBLICBLOB", phKey, pbOutput, cbOutput, 0);
        v5 = v14;
        if ( !v14 )
        {
LABEL_21:
          MSCryptFree(v13);
          goto LABEL_22;
        }
        v15 = 484;
      }
    }
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v15);
    goto LABEL_21;
  }
  v11 = 421;
LABEL_8:
  v12 = Property;
LABEL_9:
  DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v11);
LABEL_22:
  MSCryptFree(pbOutput);
LABEL_23:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v5;
}

```

## disassembly

```asm
0x18004f354  mov     r11, rsp
0x18004f357  mov     [r11+8], rbx
0x18004f35b  mov     [r11+10h], rsi
0x18004f35f  push    rbp
0x18004f360  push    rdi
0x18004f361  push    r12
0x18004f363  push    r14
0x18004f365  push    r15
0x18004f367  mov     rbp, rsp
0x18004f36a  sub     rsp, 50h
0x18004f36e  mov     [rsp+50h+dwFlags], 0; dwFlags
0x18004f376  lea     rax, [rbp+cbInput]
0x18004f37a  mov     [r11-48h], rax
0x18004f37e  lea     r8, aPublicblob; "PUBLICBLOB"
0x18004f385  mov     r12, rdx
0x18004f388  mov     [rsp+50h+cbOutput], 0; cbOutput
0x18004f390  xor     r9d, r9d; pParameterList
0x18004f393  mov     qword ptr [r11-58h], 0
0x18004f39b  xor     edx, edx; hExportKey
0x18004f39d  mov     [rbp+cbInput], 0
0x18004f3a4  mov     r15, rcx
0x18004f3a7  mov     [rbp+arg_10], 0
0x18004f3ae  mov     [rbp+phAlgorithm], 0
0x18004f3b6  call    cs:__imp_NCryptExportKey
0x18004f3bd  nop     dword ptr [rax+rax+00h]
0x18004f3c2  mov     ebx, eax
0x18004f3c4  test    eax, eax
0x18004f3c6  jz      short loc_18004F3E8
0x18004f3c8  mov     r9d, 18Ch
0x18004f3ce  mov     ecx, eax
0x18004f3d0  lea     rdx, aStatus; "Status"
0x18004f3d7  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f3de  call    DebugTraceError
0x18004f3e3  jmp     loc_18004F58A
0x18004f3e8  mov     r14d, [rbp+cbInput]
0x18004f3ec  mov     ecx, r14d
0x18004f3ef  call    SafeAllocaAllocateFromHeap
0x18004f3f4  mov     rsi, rax
0x18004f3f7  test    rax, rax
0x18004f3fa  jnz     short loc_18004F40E
0x18004f3fc  mov     ebx, 0C0000017h
0x18004f401  mov     r9d, 195h
0x18004f407  mov     ecx, 0C0000017h
0x18004f40c  jmp     short loc_18004F3D0
0x18004f40e  mov     [rsp+50h+dwFlags], 0; dwFlags
0x18004f416  lea     rax, [rbp+cbInput]
0x18004f41a  mov     [rsp+50h+pcbResult], rax; pcbResult
0x18004f41f  lea     r8, aPublicblob; "PUBLICBLOB"
0x18004f426  mov     [rsp+50h+cbOutput], r14d; cbOutput
0x18004f42b  xor     r9d, r9d; pParameterList
0x18004f42e  xor     edx, edx; hExportKey
0x18004f430  mov     [rsp+50h+pbOutput], rsi; pbOutput
0x18004f435  mov     rcx, r15; hKey
0x18004f438  call    cs:__imp_NCryptExportKey
0x18004f43f  nop     dword ptr [rax+rax+00h]
0x18004f444  mov     ebx, eax
0x18004f446  test    eax, eax
0x18004f448  jz      short loc_18004F46A
0x18004f44a  mov     r9d, 1A5h
0x18004f450  mov     ecx, eax
0x18004f452  lea     rdx, aStatus; "Status"
0x18004f459  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f460  call    DebugTraceError
0x18004f465  jmp     loc_18004F582
0x18004f46a  mov     r9d, [rbp+arg_10]; cbOutput
0x18004f46e  lea     rax, [rbp+arg_10]
0x18004f472  mov     [rsp+50h+cbOutput], 0; dwFlags
0x18004f47a  lea     rdx, aAlgorithmName; "Algorithm Name"
0x18004f481  xor     r8d, r8d; pbOutput
0x18004f484  mov     [rsp+50h+pbOutput], rax; pcbResult
0x18004f489  mov     rcx, r15; hObject
0x18004f48c  call    cs:__imp_NCryptGetProperty
0x18004f493  nop     dword ptr [rax+rax+00h]
0x18004f498  mov     ebx, eax
0x18004f49a  test    eax, eax
0x18004f49c  jz      short loc_18004F4A6
0x18004f49e  mov     r9d, 1B3h
0x18004f4a4  jmp     short loc_18004F450
0x18004f4a6  mov     ecx, [rbp+arg_10]
0x18004f4a9  call    SafeAllocaAllocateFromHeap
0x18004f4ae  mov     rdi, rax
0x18004f4b1  test    rax, rax
0x18004f4b4  jnz     short loc_18004F4C8
0x18004f4b6  mov     ebx, 0C0000017h
0x18004f4bb  mov     r9d, 1BBh
0x18004f4c1  mov     ecx, 0C0000017h
0x18004f4c6  jmp     short loc_18004F452
0x18004f4c8  mov     r9d, [rbp+arg_10]; cbOutput
0x18004f4cc  lea     rax, [rbp+arg_10]
0x18004f4d0  mov     [rsp+50h+cbOutput], 0; dwFlags
0x18004f4d8  lea     rdx, aAlgorithmName; "Algorithm Name"
0x18004f4df  mov     r8, rdi; pbOutput
0x18004f4e2  mov     [rsp+50h+pbOutput], rax; pcbResult
0x18004f4e7  mov     rcx, r15; hObject
0x18004f4ea  call    cs:__imp_NCryptGetProperty
0x18004f4f1  nop     dword ptr [rax+rax+00h]
0x18004f4f6  mov     ebx, eax
0x18004f4f8  test    eax, eax
0x18004f4fa  jz      short loc_18004F504
0x18004f4fc  mov     r9d, 1C9h
0x18004f502  jmp     short loc_18004F565
0x18004f504  xor     r9d, r9d; dwFlags
0x18004f507  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18004f50b  xor     r8d, r8d; pszImplementation
0x18004f50e  mov     rdx, rdi; pszAlgId
0x18004f511  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004f518  nop     dword ptr [rax+rax+00h]
0x18004f51d  mov     ebx, eax
0x18004f51f  test    eax, eax
0x18004f521  jz      short loc_18004F52B
0x18004f523  mov     r9d, 1D5h
0x18004f529  jmp     short loc_18004F565
0x18004f52b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18004f52f  lea     r8, aPublicblob; "PUBLICBLOB"
0x18004f536  mov     dword ptr [rsp+50h+pcbResult], 0; dwFlags
0x18004f53e  mov     r9, r12; phKey
0x18004f541  mov     [rsp+50h+cbOutput], r14d; cbInput
0x18004f546  xor     edx, edx; hImportKey
0x18004f548  mov     [rsp+50h+pbOutput], rsi; pbInput
0x18004f54d  call    cs:__imp_BCryptImportKeyPair
0x18004f554  nop     dword ptr [rax+rax+00h]
0x18004f559  mov     ebx, eax
0x18004f55b  test    eax, eax
0x18004f55d  jz      short loc_18004F57A
0x18004f55f  mov     r9d, 1E4h
0x18004f565  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f56c  mov     ecx, eax
0x18004f56e  lea     rdx, aStatus; "Status"
0x18004f575  call    DebugTraceError
0x18004f57a  mov     rcx, rdi
0x18004f57d  call    MSCryptFree
0x18004f582  mov     rcx, rsi
0x18004f585  call    MSCryptFree
0x18004f58a  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18004f58e  test    rcx, rcx
0x18004f591  jz      short loc_18004F5A1
0x18004f593  xor     edx, edx; dwFlags
0x18004f595  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004f59c  nop     dword ptr [rax+rax+00h]
0x18004f5a1  lea     r11, [rsp+50h+var_s0]
0x18004f5a6  mov     eax, ebx
0x18004f5a8  mov     rbx, [r11+30h]
0x18004f5ac  mov     rsi, [r11+38h]
0x18004f5b0  mov     rsp, r11
0x18004f5b3  pop     r15
0x18004f5b5  pop     r14
0x18004f5b7  pop     r12
0x18004f5b9  pop     rdi
0x18004f5ba  pop     rbp
0x18004f5bb  retn
```
