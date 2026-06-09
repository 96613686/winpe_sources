# _EncryptAndWriteOEMData(ushort const *,uchar const *,uint)

- ea: `0x1800445fc`
- end: `0x1800448a3`
- name: `?_EncryptAndWriteOEMData@@YAJPEBGPEBEI@Z`
- size: `679`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int8 *Src, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800441c0`

## callees

- `0x18000ac48`
- `0x1800445fc`
- `0x18004493c`
- `0x180044e54`
- `0x180044f64`
- `0x18004504c`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180044822`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180044822`
- `CRYPTSP!CryptReleaseContext` at `0x18004488e`
- `CRYPTSP!CryptReleaseContext` at `0x18004488e`
- `CRYPTSP!CryptImportKey` at `0x1800446e5`
- `CRYPTSP!CryptImportKey` at `0x1800446e5`
- `CRYPTSP!CryptDestroyKey` at `0x180044862`
- `CRYPTSP!CryptDestroyKey` at `0x18004486c`
- `CRYPTSP!CryptDestroyKey` at `0x180044862`
- `CRYPTSP!CryptDestroyKey` at `0x18004486c`
- `CRYPTSP!CryptAcquireContextW` at `0x18004463f`
- `CRYPTSP!CryptAcquireContextW` at `0x180044674`
- `CRYPTSP!CryptAcquireContextW` at `0x18004463f`
- `CRYPTSP!CryptAcquireContextW` at `0x180044674`
- `CRYPTSP!CryptGenKey` at `0x180044719`
- `CRYPTSP!CryptGenKey` at `0x180044719`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800447fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044842`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800447fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044842`

## string_xrefs

- `0x1800447e6`: `OEM registration: Failed to write session key to file with hr=0x%08X`
- `0x18004482d`: `OEM registration: Failed to write data to file with hr=0x%08X`

## pseudocode

```c
__int64 __fastcall _EncryptAndWriteOEMData(const unsigned __int16 *a1, const unsigned __int8 *Src, unsigned int a3)
{
  int Error; // ebx
  HCRYPTPROV v7; // rdi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // eax
  HCRYPTPROV phProv; // [rsp+30h] [rbp-38h] BYREF
  HCRYPTKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  BYTE *pbData; // [rsp+48h] [rbp-20h] BYREF
  HCRYPTKEY hExpKey[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD dwDataLen; // [rsp+B8h] [rbp+50h] BYREF

  phProv = 0;
  if ( CryptAcquireContextW(&phProv, L"OOBEOEMReg", L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 8u) )
    goto LABEL_4;
  Error = ResultFromKnownLastError();
  if ( Error != -2146893809 )
    goto LABEL_6;
  if ( CryptAcquireContextW(&phProv, L"OOBEOEMReg", L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0) )
LABEL_4:
    Error = 0;
  else
    Error = ResultFromKnownLastError();
LABEL_6:
  if ( Error >= 0 )
  {
    v7 = phProv;
    hExpKey[0] = 0;
    pbData = 0;
    dwDataLen = 0;
    Error = ReadFileToByteArray(a1, &pbData, &dwDataLen);
    if ( Error < 0
      || !CryptImportKey(v7, pbData, dwDataLen, 0, 0, hExpKey) && (Error = ResultFromKnownLastError(), Error < 0) )
    {
      UnattendLogW(1, L"OEM registration: Could not import OEM key with hr=0x%08X", (unsigned int)Error);
      goto LABEL_28;
    }
    hKey = 0;
    if ( !CryptGenKey(phProv, 0x660Eu, 0x800001u, &hKey) )
    {
      v8 = ResultFromKnownLastError();
      Error = v8;
      if ( v8 < 0 )
      {
        UnattendLogW(1, L"OEM registration: Failed to generate session key with hr=0x%08X", (unsigned int)v8);
LABEL_26:
        CryptDestroyKey(hExpKey[0]);
LABEL_28:
        CryptReleaseContext(phProv, 0);
        return (unsigned int)Error;
      }
    }
    pbData = 0;
    dwDataLen = 0;
    v9 = CryptEncryptHelper(hKey, Src, a3, &pbData, &dwDataLen);
    Error = v9;
    if ( v9 < 0 )
    {
      UnattendLogW(1, L"OEM registration: Failed to encrypt data with hr=0x%08X", (unsigned int)v9);
      goto LABEL_25;
    }
    v10 = _WriteByteArrayToOobeInfoFolder(L"userdata.blob", pbData, dwDataLen);
    Error = v10;
    if ( v10 < 0 )
    {
      UnattendLogW(1, L"OEM registration: Failed to write data to file with hr=0x%08X", (unsigned int)v10);
    }
    else
    {
      pv = 0;
      dwDataLen = 0;
      v12 = CryptExportKeyHelper(hKey, hExpKey[0], v11, (unsigned __int8 **)&pv, &dwDataLen);
      Error = v12;
      if ( v12 < 0 )
      {
        UnattendLogW(1, L"OEM registration: Failed to export session key with hr=0x%08X", (unsigned int)v12);
      }
      else
      {
        v13 = _WriteByteArrayToOobeInfoFolder(L"sessionkey.blob", (const unsigned __int8 *)pv, dwDataLen);
        Error = v13;
        if ( v13 < 0 )
          UnattendLogW(1, L"OEM registration: Failed to write session key to file with hr=0x%08X", (unsigned int)v13);
        CoTaskMemFree(pv);
        if ( Error >= 0 )
          goto LABEL_23;
      }
      DeleteFileW(L"outfile.blob");
    }
LABEL_23:
    CoTaskMemFree(pbData);
LABEL_25:
    CryptDestroyKey(hKey);
    goto LABEL_26;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800445fc  push    rbp
0x1800445fe  push    rbx
0x1800445ff  push    rsi
0x180044600  push    rdi
0x180044601  push    r14
0x180044603  push    r15
0x180044605  mov     rbp, rsp
0x180044608  sub     rsp, 68h
0x18004460c  mov     r14d, r8d
0x18004460f  mov     [rbp+phProv], 0
0x180044617  mov     r15, rdx
0x18004461a  mov     [rsp+68h+dwFlags], 8; dwFlags
0x180044622  mov     rsi, rcx
0x180044625  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18004462c  mov     edi, 18h
0x180044631  lea     rdx, szContainer; "OOBEOEMReg"
0x180044638  mov     r9d, edi; dwProvType
0x18004463b  lea     rcx, [rbp+phProv]; phProv
0x18004463f  call    cs:__imp_CryptAcquireContextW
0x180044645  test    eax, eax
0x180044647  jnz     short loc_18004467E
0x180044649  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004464e  mov     ebx, eax
0x180044650  cmp     eax, 8009000Fh
0x180044655  jnz     short loc_180044689
0x180044657  mov     r9d, edi; dwProvType
0x18004465a  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180044662  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180044669  lea     rdx, szContainer; "OOBEOEMReg"
0x180044670  lea     rcx, [rbp+phProv]; phProv
0x180044674  call    cs:__imp_CryptAcquireContextW
0x18004467a  test    eax, eax
0x18004467c  jz      short loc_180044682
0x18004467e  xor     ebx, ebx
0x180044680  jmp     short loc_180044689
0x180044682  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180044687  mov     ebx, eax
0x180044689  test    ebx, ebx
0x18004468b  js      loc_180044894
0x180044691  mov     rdi, [rbp+phProv]
0x180044695  lea     r8, [rbp+dwDataLen]; unsigned int *
0x180044699  lea     rdx, [rbp+pbData]; unsigned __int8 **
0x18004469d  mov     [rbp+hExpKey], 0
0x1800446a5  mov     rcx, rsi; unsigned __int16 *
0x1800446a8  mov     [rbp+pbData], 0
0x1800446b0  mov     [rbp+dwDataLen], 0
0x1800446b7  call    ?ReadFileToByteArray@@YAJPEBGPEAPEAEPEAK@Z; ReadFileToByteArray(ushort const *,uchar * *,ulong *)
0x1800446bc  mov     ebx, eax
0x1800446be  test    eax, eax
0x1800446c0  js      loc_180044874
0x1800446c6  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x1800446ca  lea     rax, [rbp+hExpKey]
0x1800446ce  mov     rdx, [rbp+pbData]; pbData
0x1800446d2  xor     r9d, r9d; hPubKey
0x1800446d5  mov     [rsp+68h+phKey], rax; phKey
0x1800446da  mov     rcx, rdi; hProv
0x1800446dd  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800446e5  call    cs:__imp_CryptImportKey
0x1800446eb  test    eax, eax
0x1800446ed  jnz     short loc_1800446FE
0x1800446ef  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800446f4  mov     ebx, eax
0x1800446f6  test    eax, eax
0x1800446f8  js      loc_180044874
0x1800446fe  mov     rcx, [rbp+phProv]; hProv
0x180044702  lea     r9, [rbp+hKey]; phKey
0x180044706  mov     edx, 660Eh; Algid
0x18004470b  mov     [rbp+hKey], 0
0x180044713  mov     r8d, 800001h; dwFlags
0x180044719  call    cs:__imp_CryptGenKey
0x18004471f  test    eax, eax
0x180044721  jnz     short loc_180044747
0x180044723  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180044728  mov     ebx, eax
0x18004472a  test    eax, eax
0x18004472c  jns     short loc_180044747
0x18004472e  mov     r8d, eax
0x180044731  lea     rdx, aOemRegistratio_17; "OEM registration: Failed to generate se"...
0x180044738  mov     ecx, 1
0x18004473d  call    UnattendLogW
0x180044742  jmp     loc_180044868
0x180044747  mov     rcx, [rbp+hKey]; hKey
0x18004474b  lea     rax, [rbp+dwDataLen]
0x18004474f  lea     r9, [rbp+pbData]; unsigned __int8 **
0x180044753  mov     qword ptr [rsp+68h+dwFlags], rax; unsigned int *
0x180044758  mov     r8d, r14d; unsigned int
0x18004475b  mov     [rbp+pbData], 0
0x180044763  mov     rdx, r15; Src
0x180044766  mov     [rbp+dwDataLen], 0
0x18004476d  call    ?CryptEncryptHelper@@YAJ_KPEBEKPEAPEAEPEAK@Z; CryptEncryptHelper(unsigned __int64,uchar const *,ulong,uchar * *,ulong *)
0x180044772  mov     ebx, eax
0x180044774  test    eax, eax
0x180044776  js      loc_18004484A
0x18004477c  mov     r8d, [rbp+dwDataLen]; unsigned int
0x180044780  lea     rcx, aUserdataBlob; "userdata.blob"
0x180044787  mov     rdx, [rbp+pbData]; unsigned __int8 *
0x18004478b  call    ?_WriteByteArrayToOobeInfoFolder@@YAJPEBGPEBEK@Z; _WriteByteArrayToOobeInfoFolder(ushort const *,uchar const *,ulong)
0x180044790  mov     ebx, eax
0x180044792  test    eax, eax
0x180044794  js      loc_18004482A
0x18004479a  mov     rdx, [rbp+hExpKey]; hExpKey
0x18004479e  lea     rax, [rbp+dwDataLen]
0x1800447a2  mov     rcx, [rbp+hKey]; hKey
0x1800447a6  lea     r9, [rbp+pv]; unsigned __int8 **
0x1800447aa  mov     qword ptr [rsp+68h+dwFlags], rax; unsigned int *
0x1800447af  mov     [rbp+pv], 0
0x1800447b7  mov     [rbp+dwDataLen], 0
0x1800447be  call    ?CryptExportKeyHelper@@YAJ_K0KPEAPEAEPEAK@Z; CryptExportKeyHelper(unsigned __int64,unsigned __int64,ulong,uchar * *,ulong *)
0x1800447c3  mov     ebx, eax
0x1800447c5  test    eax, eax
0x1800447c7  js      short loc_180044807
0x1800447c9  mov     r8d, [rbp+dwDataLen]; unsigned int
0x1800447cd  lea     rcx, aSessionkeyBlob; "sessionkey.blob"
0x1800447d4  mov     rdx, [rbp+pv]; unsigned __int8 *
0x1800447d8  call    ?_WriteByteArrayToOobeInfoFolder@@YAJPEBGPEBEK@Z; _WriteByteArrayToOobeInfoFolder(ushort const *,uchar const *,ulong)
0x1800447dd  mov     ebx, eax
0x1800447df  test    eax, eax
0x1800447e1  jns     short loc_1800447F7
0x1800447e3  mov     r8d, eax
0x1800447e6  lea     rdx, aOemRegistratio_11; "OEM registration: Failed to write sessi"...
0x1800447ed  mov     ecx, 1
0x1800447f2  call    UnattendLogW
0x1800447f7  mov     rcx, [rbp+pv]; pv
0x1800447fb  call    cs:__imp_CoTaskMemFree
0x180044801  test    ebx, ebx
0x180044803  jns     short loc_18004483E
0x180044805  jmp     short loc_18004481B
0x180044807  mov     r8d, eax
0x18004480a  lea     rdx, aOemRegistratio_3; "OEM registration: Failed to export sess"...
0x180044811  mov     ecx, 1
0x180044816  call    UnattendLogW
0x18004481b  lea     rcx, FileName; "outfile.blob"
0x180044822  call    cs:__imp_DeleteFileW
0x180044828  jmp     short loc_18004483E
0x18004482a  mov     r8d, eax
0x18004482d  lea     rdx, aOemRegistratio_26; "OEM registration: Failed to write data "...
0x180044834  mov     ecx, 1
0x180044839  call    UnattendLogW
0x18004483e  mov     rcx, [rbp+pbData]; pv
0x180044842  call    cs:__imp_CoTaskMemFree
0x180044848  jmp     short loc_18004485E
0x18004484a  mov     r8d, eax
0x18004484d  lea     rdx, aOemRegistratio_2; "OEM registration: Failed to encrypt dat"...
0x180044854  mov     ecx, 1
0x180044859  call    UnattendLogW
0x18004485e  mov     rcx, [rbp+hKey]; hKey
0x180044862  call    cs:__imp_CryptDestroyKey
0x180044868  mov     rcx, [rbp+hExpKey]; hKey
0x18004486c  call    cs:__imp_CryptDestroyKey
0x180044872  jmp     short loc_180044888
0x180044874  mov     r8d, ebx
0x180044877  lea     rdx, aOemRegistratio_5; "OEM registration: Could not import OEM "...
0x18004487e  mov     ecx, 1
0x180044883  call    UnattendLogW
0x180044888  mov     rcx, [rbp+phProv]; hProv
0x18004488c  xor     edx, edx; dwFlags
0x18004488e  call    cs:__imp_CryptReleaseContext
0x180044894  mov     eax, ebx
0x180044896  add     rsp, 68h
0x18004489a  pop     r15
0x18004489c  pop     r14
0x18004489e  pop     rdi
0x18004489f  pop     rsi
0x1800448a0  pop     rbx
0x1800448a1  pop     rbp
0x1800448a2  retn
```
