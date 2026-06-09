# KerbGetSharedECDHKeyNCrypt(unsigned __int64,unsigned __int64,_CRYPTOAPI_BLOB *,unsigned __int64 *)

- ea: `0x18007f60c`
- end: `0x18007f800`
- name: `?KerbGetSharedECDHKeyNCrypt@@YAH_K0PEAU_CRYPTOAPI_BLOB@@PEA_K@Z`
- size: `500`
- prototype: `__int64 __fastcall(NCRYPT_PROV_HANDLE hProvider, NCRYPT_KEY_HANDLE hPrivKey, struct _CRYPTOAPI_BLOB *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007f3f8`
- `0x18007f534`

## callees

- `0x180042410`
- `0x18004317c`
- `0x180066da8`
- `0x18007f60c`
- `0x18007f9fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007f7ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007f7ca`
- `ncrypt!NCryptExportKey` at `0x18007f6b5`
- `ncrypt!NCryptExportKey` at `0x18007f6b5`
- `ncrypt!NCryptSecretAgreement` at `0x18007f7b0`
- `ncrypt!NCryptSecretAgreement` at `0x18007f7b0`
- `ncrypt!NCryptDeleteKey` at `0x18007f7dc`
- `ncrypt!NCryptDeleteKey` at `0x18007f7dc`
- `ncrypt!NCryptImportKey` at `0x18007f794`
- `ncrypt!NCryptImportKey` at `0x18007f794`
- `ncrypt!NCryptGetProperty` at `0x18007f746`
- `ncrypt!NCryptGetProperty` at `0x18007f746`
- `ntdll!RtlNtStatusToDosError` at `0x18007f6c1`
- `ntdll!RtlNtStatusToDosError` at `0x18007f6c1`

## pseudocode

```c
__int64 __fastcall KerbGetSharedECDHKeyNCrypt(
        NCRYPT_PROV_HANDLE hProvider,
        NCRYPT_KEY_HANDLE hPrivKey,
        struct _CRYPTOAPI_BLOB *a3,
        unsigned __int64 *a4)
{
  unsigned int v7; // edi
  bool v9; // cc
  SECURITY_STATUS Property; // eax
  NTSTATUS v11; // ecx
  DWORD v12; // ecx
  size_t v13; // r8
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v16; // [rsp+44h] [rbp-BCh] BYREF
  BYTE v17[8]; // [rsp+48h] [rbp-B8h] BYREF
  NCRYPT_KEY_HANDLE phKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE pbData[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[136]; // [rsp+68h] [rbp-98h] BYREF

  v7 = 0;
  *(_DWORD *)v17 = 0;
  v16 = 0;
  memset_0(pbData, 0, 0x8Cu);
  v9 = a3->cbData <= 0x85;
  cbData = 140;
  phKey[0] = 0;
  if ( !v9 || a3->cbData <= 1 || *a3->pbData != 4 )
  {
    v12 = 87;
    goto LABEL_19;
  }
  Property = NCryptExportKey(hPrivKey, 0, L"ECCPUBLICBLOB", 0, pbData, 0x8Cu, &cbData, 0);
  if ( Property >= 0 )
  {
    v13 = a3->cbData - 1;
    if ( v13 != cbData - 8LL )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2));
      v11 = -1073741670;
      goto LABEL_6;
    }
    memcpy_0(v20, a3->pbData + 1, v13);
    Property = NCryptGetProperty(hPrivKey, L"Length", v17, 4u, &v16, 0);
    if ( Property >= 0 )
    {
      if ( v16 == 4 )
      {
        Property = NCryptImportKey(hProvider, 0, L"ECCPUBLICBLOB", 0, phKey, pbData, cbData, 0);
        if ( Property >= 0 )
        {
          Property = NCryptSecretAgreement(hPrivKey, phKey[0], a4, 0);
          if ( Property >= 0 )
          {
            v7 = 1;
            goto LABEL_20;
          }
        }
      }
      else
      {
        Property = -1073741595;
      }
    }
  }
  v11 = Property;
LABEL_6:
  v12 = RtlNtStatusToDosError(v11);
LABEL_19:
  SetLastError(v12);
LABEL_20:
  if ( phKey[0] )
    NCryptDeleteKey(phKey[0], 0);
  return v7;
}

```

## disassembly

```asm
0x18007f60c  push    rbp
0x18007f60e  push    rbx
0x18007f60f  push    rsi
0x18007f610  push    rdi
0x18007f611  push    r14
0x18007f613  push    r15
0x18007f615  lea     rbp, [rsp-8]
0x18007f61a  sub     rsp, 108h
0x18007f621  mov     rax, cs:__security_cookie
0x18007f628  xor     rax, rsp
0x18007f62b  mov     [rbp+30h+var_40], rax
0x18007f62f  mov     rbx, r8
0x18007f632  mov     rsi, rdx
0x18007f635  mov     r15, rcx
0x18007f638  xor     edi, edi
0x18007f63a  xor     edx, edx; Val
0x18007f63c  mov     dword ptr [rsp+130h+var_E8], edi
0x18007f640  mov     r8d, 8Ch; Size
0x18007f646  mov     [rsp+130h+var_EC], edi
0x18007f64a  lea     rcx, [rsp+130h+pbData]; void *
0x18007f64f  mov     r14, r9
0x18007f652  call    memset_0
0x18007f657  cmp     dword ptr [rbx], 85h
0x18007f65d  mov     [rsp+130h+cbData], 8Ch
0x18007f665  mov     [rsp+130h+phKey], rdi
0x18007f66a  ja      loc_18007F7C5
0x18007f670  cmp     dword ptr [rbx], 1
0x18007f673  jbe     loc_18007F7C5
0x18007f679  mov     rax, [rbx+8]
0x18007f67d  cmp     byte ptr [rax], 4
0x18007f680  jnz     loc_18007F7C5
0x18007f686  mov     [rsp+130h+dwFlags], edi; dwFlags
0x18007f68a  lea     rax, [rsp+130h+cbData]
0x18007f68f  mov     [rsp+130h+pcbResult], rax; pcbResult
0x18007f694  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x18007f69b  lea     rax, [rsp+130h+pbData]
0x18007f6a0  mov     [rsp+130h+cbOutput], 8Ch; cbOutput
0x18007f6a8  xor     r9d, r9d; pParameterList
0x18007f6ab  mov     [rsp+130h+pbOutput], rax; pbOutput
0x18007f6b0  xor     edx, edx; hExportKey
0x18007f6b2  mov     rcx, rsi; hKey
0x18007f6b5  call    cs:__imp_NCryptExportKey
0x18007f6bb  test    eax, eax
0x18007f6bd  jns     short loc_18007F6CE
0x18007f6bf  mov     ecx, eax; Status
0x18007f6c1  call    cs:__imp_RtlNtStatusToDosError
0x18007f6c7  mov     ecx, eax
0x18007f6c9  jmp     loc_18007F7CA
0x18007f6ce  mov     r9d, [rbx]
0x18007f6d1  mov     edx, [rsp+130h+cbData]
0x18007f6d5  lea     r8d, [r9-1]; Size
0x18007f6d9  lea     rax, [rdx-8]
0x18007f6dd  cmp     r8, rax
0x18007f6e0  jz      short loc_18007F712
0x18007f6e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f6e9  lea     rax, WPP_GLOBAL_Control
0x18007f6f0  cmp     rcx, rax
0x18007f6f3  jz      short loc_18007F70B
0x18007f6f5  test    byte ptr [rcx+1Ch], 1
0x18007f6f9  jz      short loc_18007F70B
0x18007f6fb  mov     rcx, [rcx+10h]
0x18007f6ff  lea     eax, [rdx-8]
0x18007f702  mov     dword ptr [rsp+130h+pbOutput], eax
0x18007f706  call    WPP_SF_dd
0x18007f70b  mov     ecx, 0C000009Ah
0x18007f710  jmp     short loc_18007F6C1
0x18007f712  mov     rdx, [rbx+8]
0x18007f716  lea     rcx, [rsp+130h+var_C8]; void *
0x18007f71b  inc     rdx; Src
0x18007f71e  call    memcpy_0
0x18007f723  lea     rax, [rsp+130h+var_EC]
0x18007f728  mov     [rsp+130h+cbOutput], edi; dwFlags
0x18007f72c  mov     r9d, 4; cbOutput
0x18007f732  mov     [rsp+130h+pbOutput], rax; pcbResult
0x18007f737  lea     r8, [rsp+130h+var_E8]; pbOutput
0x18007f73c  mov     rcx, rsi; hObject
0x18007f73f  lea     rdx, aLength; "Length"
0x18007f746  call    cs:__imp_NCryptGetProperty
0x18007f74c  test    eax, eax
0x18007f74e  js      loc_18007F6BF
0x18007f754  cmp     [rsp+130h+var_EC], 4
0x18007f759  jz      short loc_18007F765
0x18007f75b  mov     eax, 0C00000E5h
0x18007f760  jmp     loc_18007F6BF
0x18007f765  mov     eax, [rsp+130h+cbData]
0x18007f769  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x18007f770  mov     [rsp+130h+dwFlags], edi; dwFlags
0x18007f774  xor     r9d, r9d; pParameterList
0x18007f777  mov     dword ptr [rsp+130h+pcbResult], eax; cbData
0x18007f77b  xor     edx, edx; hImportKey
0x18007f77d  lea     rax, [rsp+130h+pbData]
0x18007f782  mov     rcx, r15; hProvider
0x18007f785  mov     qword ptr [rsp+130h+cbOutput], rax; pbData
0x18007f78a  lea     rax, [rsp+130h+phKey]
0x18007f78f  mov     [rsp+130h+pbOutput], rax; phKey
0x18007f794  call    cs:__imp_NCryptImportKey
0x18007f79a  test    eax, eax
0x18007f79c  js      loc_18007F6BF
0x18007f7a2  mov     rdx, [rsp+130h+phKey]; hPubKey
0x18007f7a7  xor     r9d, r9d; dwFlags
0x18007f7aa  mov     r8, r14; phAgreedSecret
0x18007f7ad  mov     rcx, rsi; hPrivKey
0x18007f7b0  call    cs:__imp_NCryptSecretAgreement
0x18007f7b6  test    eax, eax
0x18007f7b8  js      loc_18007F6BF
0x18007f7be  mov     edi, 1
0x18007f7c3  jmp     short loc_18007F7D0
0x18007f7c5  mov     ecx, 57h ; 'W'; dwErrCode
0x18007f7ca  call    cs:__imp_SetLastError
0x18007f7d0  mov     rcx, [rsp+130h+phKey]; hKey
0x18007f7d5  test    rcx, rcx
0x18007f7d8  jz      short loc_18007F7E2
0x18007f7da  xor     edx, edx; dwFlags
0x18007f7dc  call    cs:__imp_NCryptDeleteKey
0x18007f7e2  mov     eax, edi
0x18007f7e4  mov     rcx, [rbp+30h+var_40]
0x18007f7e8  xor     rcx, rsp; StackCookie
0x18007f7eb  call    __security_check_cookie
0x18007f7f0  add     rsp, 108h
0x18007f7f7  pop     r15
0x18007f7f9  pop     r14
0x18007f7fb  pop     rdi
0x18007f7fc  pop     rsi
0x18007f7fd  pop     rbx
0x18007f7fe  pop     rbp
0x18007f7ff  retn
```
