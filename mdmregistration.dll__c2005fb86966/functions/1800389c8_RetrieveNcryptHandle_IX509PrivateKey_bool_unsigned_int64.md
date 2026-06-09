# RetrieveNcryptHandle(IX509PrivateKey *,bool,unsigned __int64 *)

- ea: `0x1800389c8`
- end: `0x180038c63`
- name: `?RetrieveNcryptHandle@@YAJPEAUIX509PrivateKey@@_NPEA_K@Z`
- size: `667`
- prototype: `__int64 __fastcall(struct IX509PrivateKey *, bool, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x18000b0f4`
- `0x1800389c8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038aa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038aa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038ac7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038b30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038b98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038ac7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038b30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038b98`
- `OLEAUT32!__imp_SysFreeString` at `0x180038a46`
- `OLEAUT32!__imp_SysFreeString` at `0x180038a5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180038b22`
- `OLEAUT32!__imp_SysFreeString` at `0x180038bf4`
- `OLEAUT32!__imp_SysFreeString` at `0x180038c10`
- `OLEAUT32!__imp_SysFreeString` at `0x180038a46`
- `OLEAUT32!__imp_SysFreeString` at `0x180038a5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180038b22`
- `OLEAUT32!__imp_SysFreeString` at `0x180038bf4`
- `OLEAUT32!__imp_SysFreeString` at `0x180038c10`
- `ncrypt!NCryptFreeObject` at `0x180038a72`
- `ncrypt!NCryptFreeObject` at `0x180038a88`
- `ncrypt!NCryptFreeObject` at `0x180038ab9`
- `ncrypt!NCryptFreeObject` at `0x180038b8a`
- `ncrypt!NCryptFreeObject` at `0x180038c25`
- `ncrypt!NCryptFreeObject` at `0x180038c3b`
- `ncrypt!NCryptFreeObject` at `0x180038a72`
- `ncrypt!NCryptFreeObject` at `0x180038a88`
- `ncrypt!NCryptFreeObject` at `0x180038ab9`
- `ncrypt!NCryptFreeObject` at `0x180038b8a`
- `ncrypt!NCryptFreeObject` at `0x180038c25`
- `ncrypt!NCryptFreeObject` at `0x180038c3b`
- `ncrypt!NCryptOpenKey` at `0x180038bbe`
- `ncrypt!NCryptOpenKey` at `0x180038bbe`
- `ncrypt!NCryptOpenStorageProvider` at `0x180038ae5`
- `ncrypt!NCryptOpenStorageProvider` at `0x180038ae5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RetrieveNcryptHandle(struct IX509PrivateKey *a1, unsigned __int8 a2, unsigned __int64 *a3)
{
  int v4; // r15d
  SECURITY_STATUS v6; // ebx
  __int64 v7; // rdx
  HRESULT (__stdcall *get_ContainerName)(IX509PrivateKey *, BSTR *); // r14
  OLECHAR *v10; // rdi
  DWORD LastError; // ebx
  const WCHAR *v12; // r14
  NCRYPT_HANDLE v13; // rsi
  DWORD v14; // ebx
  NCRYPT_HANDLE v15; // rax
  NCRYPT_HANDLE v16; // rcx
  DWORD dwFlags; // [rsp+20h] [rbp-20h]
  NCRYPT_HANDLE phProvider; // [rsp+30h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  NCRYPT_HANDLE hObject; // [rsp+70h] [rbp+30h] BYREF
  BSTR v22; // [rsp+88h] [rbp+48h] BYREF

  v4 = a2;
  phProvider = 0;
  hObject = 0;
  v22 = 0;
  bstrString = 0;
  v6 = ((__int64 (__fastcall *)(struct IX509PrivateKey *, BSTR *))a1->lpVtbl->get_ProviderName)(a1, &bstrString);
  if ( v6 < 0 )
  {
    v7 = 2257;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)v6,
      dwFlags);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v22 )
      SysFreeString(v22);
    if ( hObject )
      NCryptFreeObject(hObject);
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return (unsigned int)v6;
  }
  phProvider = 0;
  v6 = NCryptOpenStorageProvider(&phProvider, bstrString, 0);
  if ( v6 < 0 )
  {
    v7 = 2259;
    goto LABEL_3;
  }
  get_ContainerName = a1->lpVtbl->get_ContainerName;
  v10 = v22;
  if ( v22 )
  {
    LastError = GetLastError();
    SysFreeString(v10);
    SetLastError(LastError);
  }
  v22 = 0;
  v6 = ((__int64 (__fastcall *)(struct IX509PrivateKey *, BSTR *))get_ContainerName)(a1, &v22);
  if ( v6 < 0 )
  {
    v7 = 2261;
    goto LABEL_3;
  }
  v12 = v22;
  v13 = hObject;
  if ( hObject )
  {
    v14 = GetLastError();
    NCryptFreeObject(v13);
    SetLastError(v14);
  }
  hObject = 0;
  v6 = NCryptOpenKey(phProvider, &hObject, v12, 0, (32 * v4) | 0x40);
  if ( v6 < 0 )
  {
    v7 = 2263;
    goto LABEL_3;
  }
  v15 = hObject;
  v16 = 0;
  hObject = 0;
  *a3 = v15;
  if ( bstrString )
  {
    SysFreeString(bstrString);
    v16 = hObject;
  }
  if ( v22 )
  {
    SysFreeString(v22);
    v16 = hObject;
  }
  if ( v16 )
    NCryptFreeObject(v16);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return 0;
}

```

## disassembly

```asm
0x1800389c8  mov     [rsp-28h+arg_8], rbx
0x1800389cd  mov     [rsp-28h+arg_10], rsi
0x1800389d2  push    rbp
0x1800389d3  push    rdi
0x1800389d4  push    r12
0x1800389d6  push    r14
0x1800389d8  push    r15
0x1800389da  mov     rbp, rsp
0x1800389dd  sub     rsp, 40h
0x1800389e1  mov     r12, r8
0x1800389e4  movzx   r15d, dl
0x1800389e8  mov     rsi, rcx
0x1800389eb  mov     [rbp+phProvider], 0
0x1800389f3  mov     [rbp+hObject], 0
0x1800389fb  mov     [rbp+arg_18], 0
0x180038a03  mov     [rbp+bstrString], 0
0x180038a0b  mov     rax, [rcx]
0x180038a0e  lea     rdx, [rbp+bstrString]
0x180038a12  mov     rax, [rax+0C8h]
0x180038a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a1e  mov     ebx, eax
0x180038a20  test    eax, eax
0x180038a22  jns     short loc_180038A9B
0x180038a24  mov     edx, 8D1h; void *
0x180038a29  mov     r9d, ebx; char *
0x180038a2c  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038a33  mov     rcx, [rbp+28h]; this
0x180038a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038a3c  nop
0x180038a3d  mov     rcx, [rbp+bstrString]; bstrString
0x180038a41  test    rcx, rcx
0x180038a44  jz      short loc_180038A53
0x180038a46  call    cs:__imp_SysFreeString
0x180038a4d  nop     dword ptr [rax+rax+00h]
0x180038a52  nop
0x180038a53  mov     rcx, [rbp+arg_18]; bstrString
0x180038a57  test    rcx, rcx
0x180038a5a  jz      short loc_180038A69
0x180038a5c  call    cs:__imp_SysFreeString
0x180038a63  nop     dword ptr [rax+rax+00h]
0x180038a68  nop
0x180038a69  mov     rcx, [rbp+hObject]; hObject
0x180038a6d  test    rcx, rcx
0x180038a70  jz      short loc_180038A7F
0x180038a72  call    cs:__imp_NCryptFreeObject
0x180038a79  nop     dword ptr [rax+rax+00h]
0x180038a7e  nop
0x180038a7f  mov     rcx, [rbp+phProvider]; hObject
0x180038a83  test    rcx, rcx
0x180038a86  jz      short loc_180038A94
0x180038a88  call    cs:__imp_NCryptFreeObject
0x180038a8f  nop     dword ptr [rax+rax+00h]
0x180038a94  mov     eax, ebx
0x180038a96  jmp     loc_180038C49
0x180038a9b  mov     r14, [rbp+bstrString]
0x180038a9f  mov     rdi, [rbp+phProvider]
0x180038aa3  test    rdi, rdi
0x180038aa6  jz      short loc_180038AD3
0x180038aa8  call    cs:__imp_GetLastError
0x180038aaf  nop     dword ptr [rax+rax+00h]
0x180038ab4  mov     ebx, eax
0x180038ab6  mov     rcx, rdi; hObject
0x180038ab9  call    cs:__imp_NCryptFreeObject
0x180038ac0  nop     dword ptr [rax+rax+00h]
0x180038ac5  mov     ecx, ebx; dwErrCode
0x180038ac7  call    cs:__imp_SetLastError
0x180038ace  nop     dword ptr [rax+rax+00h]
0x180038ad3  mov     [rbp+phProvider], 0
0x180038adb  xor     r8d, r8d; dwFlags
0x180038ade  mov     rdx, r14; pszProviderName
0x180038ae1  lea     rcx, [rbp+phProvider]; phProvider
0x180038ae5  call    cs:__imp_NCryptOpenStorageProvider
0x180038aec  nop     dword ptr [rax+rax+00h]
0x180038af1  mov     ebx, eax
0x180038af3  test    eax, eax
0x180038af5  jns     short loc_180038B01
0x180038af7  mov     edx, 8D3h
0x180038afc  jmp     loc_180038A29
0x180038b01  mov     rax, [rsi]
0x180038b04  mov     r14, [rax+78h]
0x180038b08  mov     rdi, [rbp+arg_18]
0x180038b0c  test    rdi, rdi
0x180038b0f  jz      short loc_180038B3C
0x180038b11  call    cs:__imp_GetLastError
0x180038b18  nop     dword ptr [rax+rax+00h]
0x180038b1d  mov     ebx, eax
0x180038b1f  mov     rcx, rdi; bstrString
0x180038b22  call    cs:__imp_SysFreeString
0x180038b29  nop     dword ptr [rax+rax+00h]
0x180038b2e  mov     ecx, ebx; dwErrCode
0x180038b30  call    cs:__imp_SetLastError
0x180038b37  nop     dword ptr [rax+rax+00h]
0x180038b3c  mov     [rbp+arg_18], 0
0x180038b44  lea     rdx, [rbp+arg_18]
0x180038b48  mov     rcx, rsi
0x180038b4b  mov     rax, r14
0x180038b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b53  mov     ebx, eax
0x180038b55  test    eax, eax
0x180038b57  jns     short loc_180038B63
0x180038b59  mov     edx, 8D5h
0x180038b5e  jmp     loc_180038A29
0x180038b63  mov     edi, r15d
0x180038b66  shl     edi, 5
0x180038b69  or      edi, 40h
0x180038b6c  mov     r14, [rbp+arg_18]
0x180038b70  mov     rsi, [rbp+hObject]
0x180038b74  test    rsi, rsi
0x180038b77  jz      short loc_180038BA4
0x180038b79  call    cs:__imp_GetLastError
0x180038b80  nop     dword ptr [rax+rax+00h]
0x180038b85  mov     ebx, eax
0x180038b87  mov     rcx, rsi; hObject
0x180038b8a  call    cs:__imp_NCryptFreeObject
0x180038b91  nop     dword ptr [rax+rax+00h]
0x180038b96  mov     ecx, ebx; dwErrCode
0x180038b98  call    cs:__imp_SetLastError
0x180038b9f  nop     dword ptr [rax+rax+00h]
0x180038ba4  mov     [rbp+hObject], 0
0x180038bac  mov     [rsp+40h+dwFlags], edi; dwFlags
0x180038bb0  xor     r9d, r9d; dwLegacyKeySpec
0x180038bb3  mov     r8, r14; pszKeyName
0x180038bb6  lea     rdx, [rbp+hObject]; phKey
0x180038bba  mov     rcx, [rbp+phProvider]; hProvider
0x180038bbe  call    cs:__imp_NCryptOpenKey
0x180038bc5  nop     dword ptr [rax+rax+00h]
0x180038bca  mov     ebx, eax
0x180038bcc  test    eax, eax
0x180038bce  jns     short loc_180038BDA
0x180038bd0  mov     edx, 8D7h
0x180038bd5  jmp     loc_180038A29
0x180038bda  mov     rax, [rbp+hObject]
0x180038bde  xor     ecx, ecx
0x180038be0  mov     [rbp+hObject], rcx
0x180038be4  mov     [r12], rax
0x180038be8  mov     rax, [rbp+bstrString]
0x180038bec  test    rax, rax
0x180038bef  jz      short loc_180038C04
0x180038bf1  mov     rcx, rax; bstrString
0x180038bf4  call    cs:__imp_SysFreeString
0x180038bfb  nop     dword ptr [rax+rax+00h]
0x180038c00  mov     rcx, [rbp+hObject]
0x180038c04  mov     rax, [rbp+arg_18]
0x180038c08  test    rax, rax
0x180038c0b  jz      short loc_180038C20
0x180038c0d  mov     rcx, rax; bstrString
0x180038c10  call    cs:__imp_SysFreeString
0x180038c17  nop     dword ptr [rax+rax+00h]
0x180038c1c  mov     rcx, [rbp+hObject]; hObject
0x180038c20  test    rcx, rcx
0x180038c23  jz      short loc_180038C32
0x180038c25  call    cs:__imp_NCryptFreeObject
0x180038c2c  nop     dword ptr [rax+rax+00h]
0x180038c31  nop
0x180038c32  mov     rcx, [rbp+phProvider]; hObject
0x180038c36  test    rcx, rcx
0x180038c39  jz      short loc_180038C47
0x180038c3b  call    cs:__imp_NCryptFreeObject
0x180038c42  nop     dword ptr [rax+rax+00h]
0x180038c47  xor     eax, eax
0x180038c49  lea     r11, [rsp+40h+var_s0]
0x180038c4e  mov     rbx, [r11+38h]
0x180038c52  mov     rsi, [r11+40h]
0x180038c56  mov     rsp, r11
0x180038c59  pop     r15
0x180038c5b  pop     r14
0x180038c5d  pop     r12
0x180038c5f  pop     rdi
0x180038c60  pop     rbp
0x180038c61  retn
```
