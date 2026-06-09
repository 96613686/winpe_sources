# CExtractIcon::GetIconLocation(uint,wchar_t *,uint,int *,uint *)

- ea: `0x18001b4d0`
- end: `0x18001b6f8`
- name: `?GetIconLocation@CExtractIcon@@UEAAJIPEA_WIPEAHPEAI@Z`
- size: `552`
- prototype: `int(CExtractIcon *__hidden this, unsigned int, wchar_t *, unsigned int, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006270`
- `0x180008a74`
- `0x18001b4d0`
- `0x18002fcdc`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001b572`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001b572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b6be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b6be`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001b64d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001b64d`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18001b6ad`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18001b6ad`

## string_xrefs

- `0x18001b65c`: `CLSID\%s\LocalServer32`

## pseudocode

```c
__int64 __fastcall CExtractIcon::GetIconLocation(
        CExtractIcon *this,
        __int64 a2,
        wchar_t *a3,
        DWORD a4,
        int *a5,
        unsigned int *a6)
{
  __int64 v9; // rcx
  int v10; // r14d
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-BCh] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-B8h] BYREF
  IID rclsid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszSubKey[256]; // [rsp+60h] [rbp-A0h] BYREF

  if ( a3 && a5 && a6 )
  {
    v9 = *((_QWORD *)this + 9);
    if ( v9 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
      if ( v10 >= 0 )
        *a6 &= ~2u;
      return (unsigned int)v10;
    }
    v10 = -2147467259;
    if ( !GetModuleFileNameW(off_180053498, a3, a4) )
      return (unsigned int)v10;
    if ( *((_DWORD *)this + 16) == 1 )
    {
      *a5 = -504;
      rclsid = GUID_NULL;
      if ( CMapiSupport::GetOutlookCLSID(&rclsid) >= 0 )
      {
        lpsz = 0;
        if ( StringFromCLSID(&rclsid, &lpsz) >= 0 )
        {
          if ( StringCchPrintfW(pszSubKey, 0x100u, L"CLSID\\%s\\LocalServer32", lpsz) >= 0 )
          {
            pdwType = 1;
            pcbData = 2 * a4;
            if ( !SHGetValueW(HKEY_CLASSES_ROOT, pszSubKey, &lParam, &pdwType, a3, &pcbData) )
              *a5 = 0;
          }
          CoTaskMemFree(lpsz);
        }
      }
      goto LABEL_31;
    }
    if ( *((_DWORD *)this + 16) == 2 )
    {
      *a5 = -502;
      goto LABEL_31;
    }
    if ( *((_DWORD *)this + 16) != 3 )
    {
      switch ( *((_DWORD *)this + 16) )
      {
        case 4:
          *a5 = -507;
          goto LABEL_31;
        case 5:
          *a5 = -508;
          goto LABEL_31;
        case 6:
          *a5 = -506;
          goto LABEL_31;
        case 7:
          *a5 = -509;
          goto LABEL_31;
        case 9:
          *a5 = -510;
          goto LABEL_31;
        case 0xA:
          *a5 = -511;
LABEL_31:
          *a6 = 0;
          return 0;
      }
    }
    *a5 = -(*((_DWORD *)this + 17) != 0) - 500;
    goto LABEL_31;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001b4d0  push    rbp
0x18001b4d2  push    rbx
0x18001b4d3  push    rsi
0x18001b4d4  push    rdi
0x18001b4d5  push    r12
0x18001b4d7  push    r14
0x18001b4d9  push    r15
0x18001b4db  lea     rbp, [rsp-170h]
0x18001b4e3  sub     rsp, 270h
0x18001b4ea  mov     rax, cs:__security_cookie
0x18001b4f1  xor     rax, rsp
0x18001b4f4  mov     [rbp+1A0h+var_40], rax
0x18001b4fb  mov     rbx, [rbp+1A0h+arg_20]
0x18001b502  mov     r12d, r9d
0x18001b505  mov     rdi, [rbp+1A0h+arg_28]
0x18001b50c  mov     r15, r8
0x18001b50f  mov     rsi, rcx
0x18001b512  test    r8, r8
0x18001b515  jz      loc_18001B6D2
0x18001b51b  test    rbx, rbx
0x18001b51e  jz      loc_18001B6D2
0x18001b524  test    rdi, rdi
0x18001b527  jz      loc_18001B6D2
0x18001b52d  mov     rcx, [rcx+48h]
0x18001b531  test    rcx, rcx
0x18001b534  jz      short loc_18001B55F
0x18001b536  mov     rax, [rcx]
0x18001b539  mov     [rsp+2A0h+pcbData], rdi
0x18001b53e  mov     [rsp+2A0h+pvData], rbx
0x18001b543  mov     rax, [rax+18h]
0x18001b547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b54c  mov     r14d, eax
0x18001b54f  test    eax, eax
0x18001b551  js      loc_18001B6CD
0x18001b557  and     dword ptr [rdi], 0FFFFFFFDh
0x18001b55a  jmp     loc_18001B6CD
0x18001b55f  mov     rcx, cs:off_180053498; hModule
0x18001b566  mov     r8d, r12d; nSize
0x18001b569  mov     rdx, r15; lpFilename
0x18001b56c  mov     r14d, 80004005h
0x18001b572  call    cs:__imp_GetModuleFileNameW
0x18001b578  test    eax, eax
0x18001b57a  jz      loc_18001B6CD
0x18001b580  mov     ecx, [rsi+40h]
0x18001b583  sub     ecx, 1
0x18001b586  jz      loc_18001B615
0x18001b58c  sub     ecx, 1
0x18001b58f  jz      short loc_18001B60A
0x18001b591  sub     ecx, 1
0x18001b594  jz      short loc_18001B5F6
0x18001b596  sub     ecx, 1
0x18001b599  jz      short loc_18001B5EB
0x18001b59b  sub     ecx, 1
0x18001b59e  jz      short loc_18001B5E0
0x18001b5a0  sub     ecx, 1
0x18001b5a3  jz      short loc_18001B5D5
0x18001b5a5  sub     ecx, 1
0x18001b5a8  jz      short loc_18001B5CA
0x18001b5aa  sub     ecx, 2
0x18001b5ad  jz      short loc_18001B5BF
0x18001b5af  cmp     ecx, 1
0x18001b5b2  jnz     short loc_18001B5F6
0x18001b5b4  mov     dword ptr [rbx], 0FFFFFE01h
0x18001b5ba  jmp     loc_18001B6C4
0x18001b5bf  mov     dword ptr [rbx], 0FFFFFE02h
0x18001b5c5  jmp     loc_18001B6C4
0x18001b5ca  mov     dword ptr [rbx], 0FFFFFE03h
0x18001b5d0  jmp     loc_18001B6C4
0x18001b5d5  mov     dword ptr [rbx], 0FFFFFE06h
0x18001b5db  jmp     loc_18001B6C4
0x18001b5e0  mov     dword ptr [rbx], 0FFFFFE04h
0x18001b5e6  jmp     loc_18001B6C4
0x18001b5eb  mov     dword ptr [rbx], 0FFFFFE05h
0x18001b5f1  jmp     loc_18001B6C4
0x18001b5f6  mov     eax, [rsi+44h]
0x18001b5f9  neg     eax
0x18001b5fb  sbb     ecx, ecx
0x18001b5fd  add     ecx, 0FFFFFE0Ch
0x18001b603  mov     [rbx], ecx
0x18001b605  jmp     loc_18001B6C4
0x18001b60a  mov     dword ptr [rbx], 0FFFFFE0Ah
0x18001b610  jmp     loc_18001B6C4
0x18001b615  mov     dword ptr [rbx], 0FFFFFE08h
0x18001b61b  lea     rcx, [rsp+2A0h+rclsid]; lpclsid
0x18001b620  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001b627  movdqu  xmmword ptr [rsp+2A0h+rclsid.Data1], xmm0
0x18001b62d  call    ?GetOutlookCLSID@CMapiSupport@@SAJPEAU_GUID@@@Z; CMapiSupport::GetOutlookCLSID(_GUID *)
0x18001b632  test    eax, eax
0x18001b634  js      loc_18001B6C4
0x18001b63a  lea     rdx, [rsp+2A0h+lpsz]; lplpsz
0x18001b63f  mov     [rsp+2A0h+lpsz], 0
0x18001b648  lea     rcx, [rsp+2A0h+rclsid]; rclsid
0x18001b64d  call    cs:__imp_StringFromCLSID
0x18001b653  test    eax, eax
0x18001b655  js      short loc_18001B6C4
0x18001b657  mov     r9, [rsp+2A0h+lpsz]
0x18001b65c  lea     r8, aClsidSLocalser; "CLSID\\%s\\LocalServer32"
0x18001b663  mov     edx, 100h; unsigned __int64
0x18001b668  lea     rcx, [rsp+2A0h+pszSubKey]; wchar_t *
0x18001b66d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001b672  test    eax, eax
0x18001b674  js      short loc_18001B6B9
0x18001b676  lea     eax, [r12+r12]
0x18001b67a  mov     [rsp+2A0h+pdwType], 1
0x18001b682  mov     [rsp+2A0h+var_260], eax
0x18001b686  lea     r9, [rsp+2A0h+pdwType]; pdwType
0x18001b68b  lea     rax, [rsp+2A0h+var_260]
0x18001b690  mov     rcx, 0FFFFFFFF80000000h; hkey
0x18001b697  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18001b69c  lea     r8, lParam; pszValue
0x18001b6a3  lea     rdx, [rsp+2A0h+pszSubKey]; pszSubKey
0x18001b6a8  mov     [rsp+2A0h+pvData], r15; pvData
0x18001b6ad  call    cs:__imp_SHGetValueW
0x18001b6b3  test    eax, eax
0x18001b6b5  jnz     short loc_18001B6B9
0x18001b6b7  mov     [rbx], eax
0x18001b6b9  mov     rcx, [rsp+2A0h+lpsz]; pv
0x18001b6be  call    cs:__imp_CoTaskMemFree
0x18001b6c4  mov     dword ptr [rdi], 0
0x18001b6ca  xor     r14d, r14d
0x18001b6cd  mov     eax, r14d
0x18001b6d0  jmp     short loc_18001B6D7
0x18001b6d2  mov     eax, 80004003h
0x18001b6d7  mov     rcx, [rbp+1A0h+var_40]
0x18001b6de  xor     rcx, rsp; StackCookie
0x18001b6e1  call    __security_check_cookie
0x18001b6e6  add     rsp, 270h
0x18001b6ed  pop     r15
0x18001b6ef  pop     r14
0x18001b6f1  pop     r12
0x18001b6f3  pop     rdi
0x18001b6f4  pop     rsi
0x18001b6f5  pop     rbx
0x18001b6f6  pop     rbp
0x18001b6f7  retn
```
