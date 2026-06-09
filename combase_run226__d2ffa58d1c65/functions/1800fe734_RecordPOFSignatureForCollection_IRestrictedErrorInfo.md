# RecordPOFSignatureForCollection(IRestrictedErrorInfo *)

- ea: `0x1800fe734`
- end: `0x1800fe9fe`
- name: `?RecordPOFSignatureForCollection@@YAXPEAUIRestrictedErrorInfo@@@Z`
- size: `714`
- prototype: `void __fastcall(IRestrictedErrorInfo *pRestrictedErrorInfo)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18016a080`

## callees

- `0x18000b408`
- `0x1800fe734`
- `0x1800fef4c`
- `0x1800ff250`
- `0x1800ff384`
- `0x1800ff618`
- `0x1801999b0`
- `0x18019a654`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800fe8a6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800fe8a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800fe83c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800fe83c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fe961`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fe961`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe9a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe9b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe9a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe9b3`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800fe915`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800fe915`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fe99d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fe99d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe824`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe9be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe824`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe9be`

## pseudocode

```c
void __fastcall RecordPOFSignatureForCollection(IRestrictedErrorInfo *pRestrictedErrorInfo)
{
  IRestrictedErrorInfo_vtbl *v1; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  char v4; // r14
  HKEY__ *v5; // rsi
  unsigned int v6; // ecx
  unsigned int v7; // edi
  wchar_t *v8; // rdx
  int v9; // r8d
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // r8d
  int v13; // edx
  LSTATUS v14; // eax
  bool v15; // sf
  LSTATUS v16; // eax
  bool v17; // sf
  IRestrictedErrorInfoInternal *ptr; // rcx
  unsigned int disposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY__ *appKey; // [rsp+58h] [rbp-A8h] BYREF
  Microsoft::WRL::ComPtr<IRestrictedErrorInfoInternal> spRestrictedErrorInternal; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *bstrSignature; // [rsp+68h] [rbp-98h] BYREF
  unsigned int numSnapshots; // [rsp+70h] [rbp-90h] BYREF
  HKEY__ *signatureKey; // [rsp+78h] [rbp-88h] BYREF
  wchar_t folderPath[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t filePath[264]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t signatureKeyPath[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v1 = pRestrictedErrorInfo->__vftable;
  spRestrictedErrorInternal.ptr_ = 0;
  QueryInterface = v1->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&spRestrictedErrorInternal);
  if ( QueryInterface(pRestrictedErrorInfo, &IID_IRestrictedErrorInfoInternal, (void **)&spRestrictedErrorInternal.ptr_) >= 0 )
  {
    bstrSignature = 0;
    if ( spRestrictedErrorInternal.ptr_->GetSignature(spRestrictedErrorInternal.ptr_, &bstrSignature) >= 0 )
    {
      appKey = 0;
      disposition = 0;
      v4 = 0;
      GetSignatures(1, (wchar_t ***)&appKey, &disposition);
      v5 = appKey;
      v6 = 0;
      v7 = disposition;
      while ( v6 < disposition )
      {
        v8 = bstrSignature;
        do
        {
          v9 = *(wchar_t *)((char *)v8 + *((_QWORD *)appKey + v6) - (_QWORD)bstrSignature);
          v10 = *v8 - v9;
          if ( v10 )
            break;
          ++v8;
        }
        while ( v9 );
        if ( !v10 )
        {
          v4 = 1;
          break;
        }
        ++v6;
      }
      v11 = 0;
      if ( disposition )
      {
        do
          SysFreeString(*((BSTR *)v5 + v11++));
        while ( v11 < v7 );
      }
      HeapFree(g_hHeap, 0, v5);
      if ( !v4 )
      {
        memset_0(folderPath, 0, 0x208u);
        memset_0(signatureKeyPath, 0, 0x208u);
        if ( (int)GetGEHFile((wchar_t *)&pszValueToSet, folderPath, v12) >= 0
          && GetSignatureKeyPath(signatureKeyPath, v13, bstrSignature) >= 0 )
        {
          CreateDirectoryW(folderPath, 0);
          memset_0(filePath, 0, 0x208u);
          if ( StringCbPrintfW(filePath, 0x208u, L"%s%s", folderPath, L"POF.dat") >= 0 )
          {
            appKey = 0;
            signatureKey = 0;
            disposition = 0;
            v14 = RegLoadAppKeyW(filePath, &appKey, 0xF003Fu, 0, 0);
            v15 = v14 < 0;
            if ( v14 > 0 )
              v15 = 1;
            if ( !v15 )
            {
              v16 = RegCreateKeyExW(appKey, signatureKeyPath, 0, 0, 0, 0xF003Fu, 0, &signatureKey, &disposition);
              v17 = v16 < 0;
              if ( v16 > 0 )
                v17 = 1;
              if ( !v17 )
              {
                numSnapshots = 0;
                RegSetValueExW(signatureKey, L"SnapshotCaptured", 0, 4u, (const BYTE *)&numSnapshots, 4u);
              }
            }
            RegCloseKey(signatureKey);
            RegCloseKey(appKey);
          }
        }
      }
    }
    SysFreeString(bstrSignature);
  }
  ptr = spRestrictedErrorInternal.ptr_;
  if ( spRestrictedErrorInternal.ptr_ )
  {
    spRestrictedErrorInternal.ptr_ = 0;
    ptr->Release(ptr);
  }
}

```

## disassembly

```asm
0x1800fe734  push    rbp
0x1800fe736  push    rbx
0x1800fe737  push    rsi
0x1800fe738  push    rdi
0x1800fe739  push    r14
0x1800fe73b  push    r15
0x1800fe73d  lea     rbp, [rsp-5C8h]
0x1800fe745  sub     rsp, 6C8h
0x1800fe74c  mov     rax, cs:__security_cookie
0x1800fe753  xor     rax, rsp
0x1800fe756  mov     [rbp+5F0h+var_40], rax
0x1800fe75d  mov     rax, [pRestrictedErrorInfo]
0x1800fe760  mov     rdi, pRestrictedErrorInfo
0x1800fe763  xor     r15d, r15d
0x1800fe766  lea     pRestrictedErrorInfo, [rsp+6F0h+spRestrictedErrorInternal]; this
0x1800fe76b  mov     [rsp+6F0h+spRestrictedErrorInternal.ptr_], r15
0x1800fe770  mov     rbx, [rax]
0x1800fe773  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fe778  lea     r8, [rsp+6F0h+spRestrictedErrorInternal]
0x1800fe77d  mov     pRestrictedErrorInfo, rdi
0x1800fe780  lea     rdx, IID_IRestrictedErrorInfoInternal
0x1800fe787  mov     rax, rbx
0x1800fe78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe78f  test    eax, eax
0x1800fe791  js      loc_1800FE9C4
0x1800fe797  mov     pRestrictedErrorInfo, [rsp+6F0h+spRestrictedErrorInternal.ptr_]
0x1800fe79c  lea     rdx, [rsp+6F0h+bstrSignature]
0x1800fe7a1  mov     [rsp+6F0h+bstrSignature], r15
0x1800fe7a6  mov     rax, [pRestrictedErrorInfo]
0x1800fe7a9  mov     rax, [rax+28h]
0x1800fe7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe7b2  test    eax, eax
0x1800fe7b4  js      loc_1800FE9B9
0x1800fe7ba  lea     r8, [rsp+6F0h+disposition]; numSignaturesReturned
0x1800fe7bf  mov     [rsp+6F0h+appKey], r15
0x1800fe7c4  lea     rdx, [rsp+6F0h+appKey]; signatures
0x1800fe7c9  mov     [rsp+6F0h+disposition], r15d
0x1800fe7ce  mov     cl, 1; includeSignaturesWithMaximumSnapshotsCaptured
0x1800fe7d0  mov     r14b, r15b
0x1800fe7d3  call    ?GetSignatures@@YAX_NPEAPEAPEAGPEAK@Z; GetSignatures(bool,ushort * * *,ulong *)
0x1800fe7d8  mov     rsi, [rsp+6F0h+appKey]
0x1800fe7dd  mov     ecx, r15d
0x1800fe7e0  mov     edi, [rsp+6F0h+disposition]
0x1800fe7e4  cmp     ecx, edi
0x1800fe7e6  jnb     short loc_1800FE817
0x1800fe7e8  mov     rdx, [rsp+6F0h+bstrSignature]
0x1800fe7ed  mov     eax, ecx
0x1800fe7ef  mov     r9, [rsi+rax*8]
0x1800fe7f3  sub     r9, rdx
0x1800fe7f6  movzx   eax, word ptr [rdx]
0x1800fe7f9  movzx   r8d, word ptr [rdx+r9]
0x1800fe7fe  sub     eax, r8d
0x1800fe801  jnz     short loc_1800FE80C
0x1800fe803  add     rdx, 2
0x1800fe807  test    r8d, r8d
0x1800fe80a  jnz     short loc_1800FE7F6
0x1800fe80c  test    eax, eax
0x1800fe80e  jz      short loc_1800FE814
0x1800fe810  inc     ecx
0x1800fe812  jmp     short loc_1800FE7E4
0x1800fe814  mov     r14b, 1
0x1800fe817  mov     ebx, r15d
0x1800fe81a  test    edi, edi
0x1800fe81c  jz      short loc_1800FE830
0x1800fe81e  mov     ecx, ebx
0x1800fe820  mov     pRestrictedErrorInfo, [rsi+pRestrictedErrorInfo*8]; bstrString
0x1800fe824  call    cs:__imp_SysFreeString
0x1800fe82a  inc     ebx
0x1800fe82c  cmp     ebx, edi
0x1800fe82e  jb      short loc_1800FE81E
0x1800fe830  mov     pRestrictedErrorInfo, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800fe837  mov     r8, rsi; lpMem
0x1800fe83a  xor     edx, edx; dwFlags
0x1800fe83c  call    cs:__imp_HeapFree
0x1800fe842  test    r14b, r14b
0x1800fe845  jnz     loc_1800FE9B9
0x1800fe84b  mov     ebx, 208h
0x1800fe850  lea     pRestrictedErrorInfo, [rbp+5F0h+folderPath]; void *
0x1800fe854  mov     r8d, ebx; Size
0x1800fe857  xor     edx, edx; Val
0x1800fe859  call    memset_0
0x1800fe85e  mov     r8d, ebx; Size
0x1800fe861  lea     pRestrictedErrorInfo, [rbp+5F0h+signatureKeyPath]; void *
0x1800fe868  xor     edx, edx; Val
0x1800fe86a  call    memset_0
0x1800fe86f  lea     rdx, [rbp+5F0h+folderPath]; filePath
0x1800fe873  lea     pRestrictedErrorInfo, pszValueToSet; fileName
0x1800fe87a  call    ?GetGEHFile@@YAJPEAG0H@Z; GetGEHFile(ushort *,ushort *,int)
0x1800fe87f  test    eax, eax
0x1800fe881  js      loc_1800FE9B9
0x1800fe887  mov     r8, [rsp+6F0h+bstrSignature]; key
0x1800fe88c  lea     pRestrictedErrorInfo, [rbp+5F0h+signatureKeyPath]; key
0x1800fe893  call    ?GetSignatureKeyPath@@YAJPEAGH0@Z; GetSignatureKeyPath(ushort *,int,ushort *)
0x1800fe898  test    eax, eax
0x1800fe89a  js      loc_1800FE9B9
0x1800fe8a0  xor     edx, edx; lpSecurityAttributes
0x1800fe8a2  lea     pRestrictedErrorInfo, [rbp+5F0h+folderPath]; lpPathName
0x1800fe8a6  call    cs:__imp_CreateDirectoryW
0x1800fe8ac  mov     r8d, ebx; Size
0x1800fe8af  lea     pRestrictedErrorInfo, [rbp+5F0h+filePath]; void *
0x1800fe8b6  xor     edx, edx; Val
0x1800fe8b8  call    memset_0
0x1800fe8bd  lea     rax, aPofDat; "POF.dat"
0x1800fe8c4  mov     edx, ebx; cbDest
0x1800fe8c6  lea     r9, [rbp+5F0h+folderPath]
0x1800fe8ca  mov     qword ptr [rsp+6F0h+Reserved], rax
0x1800fe8cf  lea     r8, aSS_0; "%s%s"
0x1800fe8d6  lea     pRestrictedErrorInfo, [rbp+5F0h+filePath]; pszDest
0x1800fe8dd  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fe8e2  test    eax, eax
0x1800fe8e4  js      loc_1800FE9B9
0x1800fe8ea  mov     edi, 0F003Fh
0x1800fe8ef  mov     [rsp+6F0h+appKey], r15
0x1800fe8f4  mov     r8d, edi; samDesired
0x1800fe8f7  mov     [rsp+6F0h+signatureKey], r15
0x1800fe8fc  xor     r9d, r9d; dwOptions
0x1800fe8ff  mov     [rsp+6F0h+disposition], r15d
0x1800fe904  lea     rdx, [rsp+6F0h+appKey]; phkResult
0x1800fe909  mov     [rsp+6F0h+Reserved], r15d; Reserved
0x1800fe90e  lea     pRestrictedErrorInfo, [rbp+5F0h+filePath]; lpFile
0x1800fe915  call    cs:__imp_RegLoadAppKeyW
0x1800fe91b  mov     ebx, 80070000h
0x1800fe920  test    eax, eax
0x1800fe922  jle     short loc_1800FE92B
0x1800fe924  movzx   eax, ax
0x1800fe927  or      eax, ebx
0x1800fe929  test    eax, eax
0x1800fe92b  js      short loc_1800FE9A3
0x1800fe92d  mov     pRestrictedErrorInfo, [rsp+6F0h+appKey]; hKey
0x1800fe932  lea     rax, [rsp+6F0h+disposition]
0x1800fe937  mov     [rsp+6F0h+lpdwDisposition], rax; lpdwDisposition
0x1800fe93c  lea     rdx, [rbp+5F0h+signatureKeyPath]; lpSubKey
0x1800fe943  lea     rax, [rsp+6F0h+signatureKey]
0x1800fe948  xor     r9d, r9d; lpClass
0x1800fe94b  mov     [rsp+6F0h+phkResult], rax; phkResult
0x1800fe950  xor     r8d, r8d; Reserved
0x1800fe953  mov     [rsp+6F0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800fe958  mov     [rsp+6F0h+samDesired], edi; samDesired
0x1800fe95c  mov     [rsp+6F0h+Reserved], r15d; dwOptions
0x1800fe961  call    cs:__imp_RegCreateKeyExW
0x1800fe967  test    eax, eax
0x1800fe969  jle     short loc_1800FE972
0x1800fe96b  movzx   eax, ax
0x1800fe96e  or      eax, ebx
0x1800fe970  test    eax, eax
0x1800fe972  js      short loc_1800FE9A3
0x1800fe974  mov     pRestrictedErrorInfo, [rsp+6F0h+signatureKey]; hKey
0x1800fe979  lea     rax, [rsp+6F0h+numSnapshots]
0x1800fe97e  mov     r9d, 4; dwType
0x1800fe984  mov     [rsp+6F0h+numSnapshots], r15d
0x1800fe989  mov     [rsp+6F0h+samDesired], r9d; cbData
0x1800fe98e  lea     rdx, aSnapshotcaptur; "SnapshotCaptured"
0x1800fe995  xor     r8d, r8d; Reserved
0x1800fe998  mov     qword ptr [rsp+6F0h+Reserved], rax; lpData
0x1800fe99d  call    cs:__imp_RegSetValueExW
0x1800fe9a3  mov     pRestrictedErrorInfo, [rsp+6F0h+signatureKey]; hKey
0x1800fe9a8  call    cs:__imp_RegCloseKey
0x1800fe9ae  mov     pRestrictedErrorInfo, [rsp+6F0h+appKey]; hKey
0x1800fe9b3  call    cs:__imp_RegCloseKey
0x1800fe9b9  mov     pRestrictedErrorInfo, [rsp+6F0h+bstrSignature]; bstrString
0x1800fe9be  call    cs:__imp_SysFreeString
0x1800fe9c4  mov     pRestrictedErrorInfo, [rsp+6F0h+spRestrictedErrorInternal.ptr_]
0x1800fe9c9  test    pRestrictedErrorInfo, pRestrictedErrorInfo
0x1800fe9cc  jz      short loc_1800FE9DF
0x1800fe9ce  mov     [rsp+6F0h+spRestrictedErrorInternal.ptr_], r15
0x1800fe9d3  mov     rax, [pRestrictedErrorInfo]
0x1800fe9d6  mov     rax, [rax+10h]
0x1800fe9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe9df  mov     pRestrictedErrorInfo, [rbp+5F0h+var_40]
0x1800fe9e6  xor     pRestrictedErrorInfo, rsp; StackCookie
0x1800fe9e9  call    __security_check_cookie
0x1800fe9ee  add     rsp, 6C8h
0x1800fe9f5  pop     r15
0x1800fe9f7  pop     r14
0x1800fe9f9  pop     rdi
0x1800fe9fa  pop     rsi
0x1800fe9fb  pop     rbx
0x1800fe9fc  pop     rbp
0x1800fe9fd  retn
```
