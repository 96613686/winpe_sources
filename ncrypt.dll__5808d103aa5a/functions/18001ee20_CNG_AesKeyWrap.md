# CNG_AesKeyWrap

- ea: `0x18001ee20`
- end: `0x18001effc`
- name: `CNG_AesKeyWrap`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001550`

## callees

- `0x180005fa0`
- `0x18000e120`
- `0x18001ee20`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18001efc5`
- `bcrypt!BCryptDestroyKey` at `0x18001efd4`
- `bcrypt!BCryptDestroyKey` at `0x18001efc5`
- `bcrypt!BCryptDestroyKey` at `0x18001efd4`
- `bcrypt!BCryptExportKey` at `0x18001ef17`
- `bcrypt!BCryptExportKey` at `0x18001ef91`
- `bcrypt!BCryptExportKey` at `0x18001ef17`
- `bcrypt!BCryptExportKey` at `0x18001ef91`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001eeb1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001eee0`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001eeb1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001eee0`

## string_xrefs

- `0x18001ee75`: `onecore\ds\security\cryptoapi\ncrypt\protect\common\keywrap.c`
- `0x18001ef48`: `onecore\ds\security\cryptoapi\ncrypt\protect\common\keywrap.c`

## pseudocode

```c
__int64 __fastcall CNG_AesKeyWrap(__int64 a1, UCHAR *a2, ULONG a3, UCHAR *a4, ULONG cbSecret, UCHAR **a6, ULONG *a7)
{
  UCHAR *v9; // rdi
  int BCryptHandle; // ebx
  __int64 v13; // r9
  unsigned int v14; // ebx
  UCHAR *v15; // rax
  ULONG pcbResult; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp-10h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+58h] [rbp-8h] BYREF

  hAlgorithm = 0;
  phKey = 0;
  v9 = 0;
  hKey = 0;
  pcbResult = 0;
  BCryptHandle = CNG_GetBCryptHandle((char *)L"AES", &hAlgorithm);
  if ( BCryptHandle < 0 )
  {
    v13 = 75;
LABEL_3:
    DebugTraceError(
      (unsigned int)BCryptHandle,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\common\\keywrap.c",
      v13);
    v14 = BCryptHandle | 0x10000000;
    goto LABEL_15;
  }
  BCryptHandle = BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, a4, cbSecret, 0);
  if ( BCryptHandle < 0 )
  {
    v13 = 90;
    goto LABEL_3;
  }
  BCryptHandle = BCryptGenerateSymmetricKey(hAlgorithm, &hKey, 0, 0, a2, a3, 0);
  if ( BCryptHandle < 0 )
  {
    v13 = 108;
    goto LABEL_3;
  }
  BCryptHandle = BCryptExportKey(hKey, phKey, L"Rfc3565KeyWrapBlob", 0, 0, &pcbResult, 0);
  if ( BCryptHandle < 0 )
  {
    v13 = 124;
    goto LABEL_3;
  }
  v15 = (UCHAR *)(*(__int64 (__fastcall **)(_QWORD))(a1 + 8))(pcbResult);
  v9 = v15;
  if ( v15 )
  {
    BCryptHandle = BCryptExportKey(hKey, phKey, L"Rfc3565KeyWrapBlob", v15, pcbResult, &pcbResult, 0);
    if ( BCryptHandle < 0 )
    {
      v13 = 148;
      goto LABEL_3;
    }
    v14 = 0;
    *a6 = v9;
    v9 = 0;
    *a7 = pcbResult;
  }
  else
  {
    v14 = -2146893810;
    DebugTraceError(2148073486LL, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\common\\keywrap.c", 133);
  }
LABEL_15:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v9 )
    (*(void (__fastcall **)(UCHAR *))(a1 + 16))(v9);
  return v14;
}

```

## disassembly

```asm
0x18001ee20  push    rbp
0x18001ee22  push    rbx
0x18001ee23  push    rsi
0x18001ee24  push    rdi
0x18001ee25  push    r13
0x18001ee27  push    r14
0x18001ee29  push    r15
0x18001ee2b  mov     rbp, rsp
0x18001ee2e  sub     rsp, 60h
0x18001ee32  mov     r14, rdx
0x18001ee35  mov     [rbp+hAlgorithm], 0
0x18001ee3d  mov     r13, rcx
0x18001ee40  mov     [rbp+phKey], 0
0x18001ee48  xor     edi, edi
0x18001ee4a  mov     [rbp+hKey], 0
0x18001ee52  lea     rdx, [rbp+hAlgorithm]
0x18001ee56  mov     [rbp+pcbResult], edi
0x18001ee59  lea     rcx, aAes; "AES"
0x18001ee60  mov     r15, r9
0x18001ee63  mov     esi, r8d
0x18001ee66  call    CNG_GetBCryptHandle
0x18001ee6b  mov     ebx, eax
0x18001ee6d  test    eax, eax
0x18001ee6f  jns     short loc_18001EE93
0x18001ee71  lea     r9d, [rdi+4Bh]
0x18001ee75  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ee7c  mov     ecx, ebx
0x18001ee7e  lea     rdx, aStatus_0; "status"
0x18001ee85  call    DebugTraceError
0x18001ee8a  bts     ebx, 1Ch
0x18001ee8e  jmp     loc_18001EFBC
0x18001ee93  mov     eax, [rbp+arg_20]
0x18001ee96  lea     rdx, [rbp+phKey]; phKey
0x18001ee9a  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18001ee9e  xor     r9d, r9d; cbKeyObject
0x18001eea1  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18001eea5  xor     r8d, r8d; pbKeyObject
0x18001eea8  mov     [rsp+60h+cbSecret], eax; cbSecret
0x18001eeac  mov     [rsp+60h+pbSecret], r15; pbSecret
0x18001eeb1  call    cs:__imp_BCryptGenerateSymmetricKey
0x18001eeb7  mov     ebx, eax
0x18001eeb9  test    eax, eax
0x18001eebb  jns     short loc_18001EEC5
0x18001eebd  mov     r9d, 5Ah ; 'Z'
0x18001eec3  jmp     short loc_18001EE75
0x18001eec5  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18001eec9  lea     rdx, [rbp+hKey]; phKey
0x18001eecd  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18001eed1  xor     r9d, r9d; cbKeyObject
0x18001eed4  mov     [rsp+60h+cbSecret], esi; cbSecret
0x18001eed8  xor     r8d, r8d; pbKeyObject
0x18001eedb  mov     [rsp+60h+pbSecret], r14; pbSecret
0x18001eee0  call    cs:__imp_BCryptGenerateSymmetricKey
0x18001eee6  mov     ebx, eax
0x18001eee8  test    eax, eax
0x18001eeea  jns     short loc_18001EEF4
0x18001eeec  mov     r9d, 6Ch ; 'l'
0x18001eef2  jmp     short loc_18001EE75
0x18001eef4  mov     rdx, [rbp+phKey]; hExportKey
0x18001eef8  lea     rax, [rbp+pcbResult]
0x18001eefc  mov     rcx, [rbp+hKey]; hKey
0x18001ef00  lea     r8, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x18001ef07  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18001ef0b  xor     r9d, r9d; pbOutput
0x18001ef0e  mov     qword ptr [rsp+60h+cbSecret], rax; pcbResult
0x18001ef13  mov     dword ptr [rsp+60h+pbSecret], edi; cbOutput
0x18001ef17  call    cs:__imp_BCryptExportKey
0x18001ef1d  mov     ebx, eax
0x18001ef1f  test    eax, eax
0x18001ef21  jns     short loc_18001EF2E
0x18001ef23  mov     r9d, 7Ch ; '|'
0x18001ef29  jmp     loc_18001EE75
0x18001ef2e  mov     ecx, [rbp+pcbResult]
0x18001ef31  mov     rax, [r13+8]
0x18001ef35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef3a  mov     rdi, rax
0x18001ef3d  test    rax, rax
0x18001ef40  jnz     short loc_18001EF67
0x18001ef42  mov     r9d, 85h
0x18001ef48  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ef4f  lea     rdx, aHr; "hr"
0x18001ef56  mov     ecx, 8009000Eh
0x18001ef5b  mov     ebx, 8009000Eh
0x18001ef60  call    DebugTraceError
0x18001ef65  jmp     short loc_18001EFBC
0x18001ef67  mov     rdx, [rbp+phKey]; hExportKey
0x18001ef6b  lea     rax, [rbp+pcbResult]
0x18001ef6f  mov     rcx, [rbp+hKey]; hKey
0x18001ef73  lea     r8, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x18001ef7a  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18001ef82  mov     r9, rdi; pbOutput
0x18001ef85  mov     qword ptr [rsp+60h+cbSecret], rax; pcbResult
0x18001ef8a  mov     eax, [rbp+pcbResult]
0x18001ef8d  mov     dword ptr [rsp+60h+pbSecret], eax; cbOutput
0x18001ef91  call    cs:__imp_BCryptExportKey
0x18001ef97  mov     ebx, eax
0x18001ef99  test    eax, eax
0x18001ef9b  jns     short loc_18001EFA8
0x18001ef9d  mov     r9d, 94h
0x18001efa3  jmp     loc_18001EE75
0x18001efa8  mov     rax, [rbp+arg_28]
0x18001efac  xor     ebx, ebx
0x18001efae  mov     rcx, [rbp+arg_30]
0x18001efb2  mov     [rax], rdi
0x18001efb5  xor     edi, edi
0x18001efb7  mov     eax, [rbp+pcbResult]
0x18001efba  mov     [rcx], eax
0x18001efbc  mov     rcx, [rbp+phKey]; hKey
0x18001efc0  test    rcx, rcx
0x18001efc3  jz      short loc_18001EFCB
0x18001efc5  call    cs:__imp_BCryptDestroyKey
0x18001efcb  mov     rcx, [rbp+hKey]; hKey
0x18001efcf  test    rcx, rcx
0x18001efd2  jz      short loc_18001EFDA
0x18001efd4  call    cs:__imp_BCryptDestroyKey
0x18001efda  test    rdi, rdi
0x18001efdd  jz      short loc_18001EFEB
0x18001efdf  mov     rax, [r13+10h]
0x18001efe3  mov     rcx, rdi
0x18001efe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efeb  mov     eax, ebx
0x18001efed  add     rsp, 60h
0x18001eff1  pop     r15
0x18001eff3  pop     r14
0x18001eff5  pop     r13
0x18001eff7  pop     rdi
0x18001eff8  pop     rsi
0x18001eff9  pop     rbx
0x18001effa  pop     rbp
0x18001effb  retn
```
