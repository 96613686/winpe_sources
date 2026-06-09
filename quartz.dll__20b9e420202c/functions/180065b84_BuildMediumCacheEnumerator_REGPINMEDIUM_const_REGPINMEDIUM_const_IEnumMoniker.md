# BuildMediumCacheEnumerator(REGPINMEDIUM const *,REGPINMEDIUM const *,IEnumMoniker * *)

- ea: `0x180065b84`
- end: `0x180065f81`
- name: `?BuildMediumCacheEnumerator@@YAJPEBUREGPINMEDIUM@@0PEAPEAUIEnumMoniker@@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(const struct REGPINMEDIUM *, const struct REGPINMEDIUM *, struct IEnumMoniker **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800666e0`

## callees

- `0x180004924`
- `0x18002e928`
- `0x180038458`
- `0x1800388a0`
- `0x180039250`
- `0x180065550`
- `0x180065b84`
- `0x180066b20`
- `0x180067024`
- `0x18015e010`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180065d83`
- `ADVAPI32!RegEnumValueW` at `0x180065d83`
- `ADVAPI32!RegOpenKeyExW` at `0x180065c2e`
- `ADVAPI32!RegOpenKeyExW` at `0x180065d0d`
- `ADVAPI32!RegOpenKeyExW` at `0x180065c2e`
- `ADVAPI32!RegOpenKeyExW` at `0x180065d0d`
- `ADVAPI32!RegCloseKey` at `0x180065c46`
- `ADVAPI32!RegCloseKey` at `0x180065e77`
- `ADVAPI32!RegCloseKey` at `0x180065c46`
- `ADVAPI32!RegCloseKey` at `0x180065e77`
- `ole32!CoGetClassObject` at `0x180065be4`
- `ole32!CoGetClassObject` at `0x180065be4`

## string_xrefs

- `0x180065c20`: `System\CurrentControlSet\Control\MediumCache`
- `0x180065cb7`: `System\CurrentControlSet\Control\MediumCache\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}-%x-%x`

## pseudocode

```c
__int64 __fastcall BuildMediumCacheEnumerator(
        const struct REGPINMEDIUM *a1,
        const struct REGPINMEDIUM *a2,
        struct IEnumMoniker **a3)
{
  HRESULT ClassObject; // ebx
  const struct REGPINMEDIUM *v7; // r15
  unsigned int v8; // edi
  DWORD v9; // ebx
  LSTATUS v10; // r14d
  char v11; // si
  __int64 v12; // rcx
  void *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rbx
  int v16; // esi
  unsigned int i; // r14d
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[8]; // [rsp+88h] [rbp-78h] BYREF
  struct IClassFactory *v21; // [rsp+90h] [rbp-70h] BYREF
  struct IMoniker *v22; // [rsp+98h] [rbp-68h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp-60h] BYREF
  DWORD cchValueName; // [rsp+A4h] [rbp-5Ch] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-58h] BYREF
  struct IEnumMoniker **v26; // [rsp+B0h] [rbp-50h]
  _QWORD v27[200]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR SubKey[264]; // [rsp+700h] [rbp+600h] BYREF
  WCHAR ValueName[264]; // [rsp+910h] [rbp+810h] BYREF
  wchar_t Buffer[360]; // [rsp+B20h] [rbp+A20h] BYREF

  v26 = a3;
  v21 = 0;
  ClassObject = CoGetClassObject(
                  &CLSID_CDeviceMoniker,
                  3u,
                  0,
                  &GUID_00000001_0000_0000_c000_000000000046,
                  (LPVOID *)&v21);
  if ( ClassObject < 0 )
  {
    ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v21);
    return (unsigned int)ClassObject;
  }
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\MediumCache", 0, 0x20019u, &phkResult) )
  {
    RegCloseKey(phkResult);
    v7 = a1;
    if ( !a1 )
      v7 = a2;
    LODWORD(ppv) = v7->clsMedium.Data2;
    StringCchPrintfW(
      SubKey,
      0x104u,
      L"System\\CurrentControlSet\\Control\\MediumCache\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}-%x-%x",
      v7->clsMedium.Data1,
      ppv,
      v7->clsMedium.Data3,
      v7->clsMedium.Data4[0],
      v7->clsMedium.Data4[1],
      v7->clsMedium.Data4[2],
      v7->clsMedium.Data4[3],
      v7->clsMedium.Data4[4],
      v7->clsMedium.Data4[5],
      v7->clsMedium.Data4[6],
      v7->clsMedium.Data4[7],
      v7->dw1,
      v7->dw2);
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
    {
      v16 = -2147220970;
LABEL_32:
      ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v21);
      return (unsigned int)v16;
    }
    memset_0(v27, 0, sizeof(v27));
    v8 = 0;
    v9 = 0;
    while ( v8 < 0xC8 )
    {
      cchValueName = 260;
      *(_DWORD *)Data = 0;
      cbData = 4;
      v10 = RegEnumValueW(hKey, v9, ValueName, &cchValueName, 0, 0, Data, &cbData);
      if ( v10 || (*(_DWORD *)Data != 1 || !a2) && (*(_DWORD *)Data || !a1) )
        goto LABEL_20;
      StringCchPrintfW(Buffer, 0x168u, L"@device:pnp:%s", ValueName);
      v22 = 0;
      if ( (int)ParseDisplayNameHelper(Buffer, v21, &v22) < 0 )
        goto LABEL_20;
      phkResult = 0;
      if ( ((__int64 (__fastcall *)(struct IMoniker *, __int64 *, HKEY *))v22->lpVtbl->QueryInterface)(
             v22,
             qword_18019DB38,
             &phkResult) )
      {
        goto LABEL_19;
      }
      v11 = 1;
      if ( (*(unsigned __int8 (__fastcall **)(HKEY))(*(_QWORD *)phkResult + 24LL))(phkResult) )
      {
        v11 = 0;
        v12 = v8++;
        v27[v12] = v22;
      }
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult + 16LL))(phkResult);
      if ( v11 )
      {
LABEL_19:
        ((void (__fastcall *)(struct IMoniker *))v22->lpVtbl->Release)(v22);
        ++v9;
      }
      else
      {
LABEL_20:
        ++v9;
        if ( v10 )
          break;
      }
    }
    RegCloseKey(hKey);
    v13 = operator new(0x88u);
    if ( v13 )
    {
      v14 = ATL::CComObject<ATL::CComEnum<IEnumMoniker,&_GUID const IID_IEnumMoniker,IMoniker *,ATL::_CopyInterface<IMoniker>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumMoniker,&_GUID const IID_IEnumMoniker,IMoniker *,ATL::_CopyInterface<IMoniker>,ATL::CComMultiThreadModel>>(v13);
      v15 = v14;
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
        v16 = ATL::CComEnumImpl<IEnumMoniker,&_GUID const IID_IEnumMoniker,IMoniker *,ATL::_CopyInterface<IMoniker>>::Init(
                v15,
                (unsigned int)v27,
                (unsigned int)&v27[v8],
                0,
                3);
        if ( v16 >= 0 )
          v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IEnumMoniker **))v15)(v15, &IID_IEnumMoniker, v26);
        goto LABEL_27;
      }
    }
    else
    {
      v15 = 0;
    }
    v16 = -2147024882;
LABEL_27:
    for ( i = 0; i < v8; ++i )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v27[i] + 16LL))(v27[i]);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_32;
  }
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v21);
  return 1;
}

```

## disassembly

```asm
0x180065b84  mov     [rsp-8+arg_18], rbx
0x180065b89  push    rbp
0x180065b8a  push    rsi
0x180065b8b  push    rdi
0x180065b8c  push    r12
0x180065b8e  push    r13
0x180065b90  push    r14
0x180065b92  push    r15
0x180065b94  lea     rbp, [rsp-0D00h]
0x180065b9c  sub     rsp, 0E00h
0x180065ba3  mov     rax, cs:__security_cookie
0x180065baa  xor     rax, rsp
0x180065bad  mov     [rbp+0D30h+var_40], rax
0x180065bb4  mov     [rbp+0D30h+var_D80], r8
0x180065bb8  lea     rax, [rbp+0D30h+var_DA0]
0x180065bbc  xor     r8d, r8d; pvReserved
0x180065bbf  mov     [rbp+0D30h+var_DA0], 0
0x180065bc7  mov     r13, rdx
0x180065bca  mov     [rsp+0E30h+ppv], rax; ppv
0x180065bcf  mov     r12, rcx
0x180065bd2  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180065bd9  lea     rcx, CLSID_CDeviceMoniker; rclsid
0x180065be0  lea     edx, [r8+3]; dwClsContext
0x180065be4  call    cs:__imp_CoGetClassObject
0x180065beb  nop     dword ptr [rax+rax+00h]
0x180065bf0  mov     ebx, eax
0x180065bf2  test    eax, eax
0x180065bf4  jns     short loc_180065C06
0x180065bf6  lea     rcx, [rbp+0D30h+var_DA0]
0x180065bfa  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180065bff  mov     eax, ebx
0x180065c01  jmp     loc_180065F56
0x180065c06  lea     rax, [rbp+0D30h+phkResult]
0x180065c0a  mov     [rbp+0D30h+phkResult], 0
0x180065c12  mov     r9d, 20019h; samDesired
0x180065c18  mov     [rsp+0E30h+ppv], rax; phkResult
0x180065c1d  xor     r8d, r8d; ulOptions
0x180065c20  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Med"...
0x180065c27  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180065c2e  call    cs:__imp_RegOpenKeyExW
0x180065c35  nop     dword ptr [rax+rax+00h]
0x180065c3a  test    eax, eax
0x180065c3c  jnz     loc_180065F48
0x180065c42  mov     rcx, [rbp+0D30h+phkResult]; hKey
0x180065c46  call    cs:__imp_RegCloseKey
0x180065c4d  nop     dword ptr [rax+rax+00h]
0x180065c52  test    r12, r12
0x180065c55  mov     r15, r12
0x180065c58  cmovz   r15, r13
0x180065c5c  mov     eax, [r15+14h]
0x180065c60  movzx   ecx, byte ptr [r15+0Fh]
0x180065c65  movzx   edx, byte ptr [r15+0Eh]
0x180065c6a  movzx   r8d, byte ptr [r15+0Dh]
0x180065c6f  movzx   r9d, byte ptr [r15+0Ch]
0x180065c74  movzx   r10d, byte ptr [r15+0Bh]
0x180065c79  movzx   r11d, byte ptr [r15+0Ah]
0x180065c7e  movzx   ebx, byte ptr [r15+9]
0x180065c83  movzx   edi, byte ptr [r15+8]
0x180065c88  movzx   esi, word ptr [r15+6]
0x180065c8d  movzx   r14d, word ptr [r15+4]
0x180065c92  mov     [rsp+0E30h+var_DB8], eax
0x180065c96  mov     eax, [r15+10h]
0x180065c9a  mov     [rsp+0E30h+var_DC0], eax
0x180065c9e  mov     [rsp+0E30h+var_DC8], ecx
0x180065ca2  lea     rcx, [rbp+0D30h+SubKey]; Buffer
0x180065ca9  mov     [rsp+0E30h+var_DD0], edx
0x180065cad  mov     edx, 104h; unsigned __int64
0x180065cb2  mov     [rsp+0E30h+var_DD8], r8d
0x180065cb7  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Med"...
0x180065cbe  mov     [rsp+0E30h+var_DE0], r9d
0x180065cc3  mov     r9d, [r15]
0x180065cc6  mov     [rsp+0E30h+var_DE8], r10d
0x180065ccb  mov     [rsp+0E30h+var_DF0], r11d
0x180065cd0  mov     dword ptr [rsp+0E30h+lpcbData], ebx
0x180065cd4  mov     dword ptr [rsp+0E30h+lpData], edi
0x180065cd8  mov     dword ptr [rsp+0E30h+lpType], esi
0x180065cdc  mov     dword ptr [rsp+0E30h+ppv], r14d
0x180065ce1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180065ce6  lea     rax, [rbp+0D30h+hKey]
0x180065cea  xor     r15d, r15d
0x180065ced  mov     r9d, 20019h; samDesired
0x180065cf3  mov     [rsp+0E30h+ppv], rax; phkResult
0x180065cf8  xor     r8d, r8d; ulOptions
0x180065cfb  mov     [rbp+0D30h+hKey], r15
0x180065cff  lea     rdx, [rbp+0D30h+SubKey]; lpSubKey
0x180065d06  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180065d0d  call    cs:__imp_RegOpenKeyExW
0x180065d14  nop     dword ptr [rax+rax+00h]
0x180065d19  test    eax, eax
0x180065d1b  jnz     loc_180065F36
0x180065d21  xor     edx, edx; Val
0x180065d23  lea     rcx, [rbp+0D30h+var_D70]; void *
0x180065d27  mov     r8d, 640h; Size
0x180065d2d  call    memset_0
0x180065d32  mov     edi, r15d
0x180065d35  mov     ebx, r15d
0x180065d38  cmp     edi, 0C8h
0x180065d3e  jnb     loc_180065E73
0x180065d44  mov     rcx, [rbp+0D30h+hKey]; hKey
0x180065d48  lea     rax, [rbp+0D30h+cbData]
0x180065d4c  mov     [rsp+0E30h+lpcbData], rax; lpcbData
0x180065d51  lea     r9, [rbp+0D30h+cchValueName]; lpcchValueName
0x180065d55  lea     rax, [rbp+0D30h+Data]
0x180065d59  mov     [rbp+0D30h+cchValueName], 104h
0x180065d60  mov     [rsp+0E30h+lpData], rax; lpData
0x180065d65  lea     r8, [rbp+0D30h+ValueName]; lpValueName
0x180065d6c  mov     [rsp+0E30h+lpType], r15; lpType
0x180065d71  mov     edx, ebx; dwIndex
0x180065d73  mov     [rsp+0E30h+ppv], r15; lpReserved
0x180065d78  mov     dword ptr [rbp+0D30h+Data], r15d
0x180065d7c  mov     [rbp+0D30h+cbData], 4
0x180065d83  call    cs:__imp_RegEnumValueW
0x180065d8a  nop     dword ptr [rax+rax+00h]
0x180065d8f  mov     r14d, eax
0x180065d92  test    eax, eax
0x180065d94  jnz     loc_180065E68
0x180065d9a  mov     ecx, dword ptr [rbp+0D30h+Data]
0x180065d9d  cmp     ecx, 1
0x180065da0  jnz     short loc_180065DA7
0x180065da2  test    r13, r13
0x180065da5  jnz     short loc_180065DB8
0x180065da7  test    ecx, ecx
0x180065da9  jnz     loc_180065E68
0x180065daf  test    r12, r12
0x180065db2  jz      loc_180065E68
0x180065db8  lea     r9, [rbp+0D30h+ValueName]
0x180065dbf  mov     edx, 168h; unsigned __int64
0x180065dc4  lea     r8, aDevicePnpS; "@device:pnp:%s"
0x180065dcb  lea     rcx, [rbp+0D30h+Buffer]; Buffer
0x180065dd2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180065dd7  mov     rdx, [rbp+0D30h+var_DA0]; struct IClassFactory *
0x180065ddb  lea     r8, [rbp+0D30h+var_D98]; struct IMoniker **
0x180065ddf  lea     rcx, [rbp+0D30h+Buffer]; szUserName
0x180065de6  mov     [rbp+0D30h+var_D98], r15
0x180065dea  call    ?ParseDisplayNameHelper@@YAJPEAGPEAUIClassFactory@@PEAPEAUIMoniker@@@Z; ParseDisplayNameHelper(ushort *,IClassFactory *,IMoniker * *)
0x180065def  test    eax, eax
0x180065df1  js      short loc_180065E68
0x180065df3  mov     rcx, [rbp+0D30h+var_D98]
0x180065df7  lea     r8, [rbp+0D30h+phkResult]
0x180065dfb  mov     [rbp+0D30h+phkResult], r15
0x180065dff  lea     rdx, qword_18019DB38
0x180065e06  mov     rax, [rcx]
0x180065e09  mov     rax, [rax]
0x180065e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e11  test    eax, eax
0x180065e13  jnz     short loc_180065E51
0x180065e15  mov     rcx, [rbp+0D30h+phkResult]
0x180065e19  mov     sil, 1
0x180065e1c  mov     rax, [rcx]
0x180065e1f  mov     rax, [rax+18h]
0x180065e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e28  test    al, al
0x180065e2a  jz      short loc_180065E3C
0x180065e2c  mov     rax, [rbp+0D30h+var_D98]
0x180065e30  mov     sil, r15b
0x180065e33  mov     ecx, edi
0x180065e35  inc     edi
0x180065e37  mov     [rbp+rcx*8+0D30h+var_D70], rax
0x180065e3c  mov     rcx, [rbp+0D30h+phkResult]
0x180065e40  mov     rax, [rcx]
0x180065e43  mov     rax, [rax+10h]
0x180065e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e4c  test    sil, sil
0x180065e4f  jz      short loc_180065E68
0x180065e51  mov     rcx, [rbp+0D30h+var_D98]
0x180065e55  mov     rax, [rcx]
0x180065e58  mov     rax, [rax+10h]
0x180065e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e61  inc     ebx
0x180065e63  jmp     loc_180065D38
0x180065e68  inc     ebx
0x180065e6a  test    r14d, r14d
0x180065e6d  jz      loc_180065D38
0x180065e73  mov     rcx, [rbp+0D30h+hKey]; hKey
0x180065e77  call    cs:__imp_RegCloseKey
0x180065e7e  nop     dword ptr [rax+rax+00h]
0x180065e83  mov     ecx, 88h; Size
0x180065e88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065e8d  test    rax, rax
0x180065e90  jz      short loc_180065EF5
0x180065e92  mov     rcx, rax
0x180065e95  call    ??0?$CComObject@V?$CComEnum@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@BPEAUIMoniker@@V?$_CopyInterface@UIMoniker@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumMoniker,&_GUID const IID_IEnumMoniker,IMoniker *,ATL::_CopyInterface<IMoniker>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumMoniker,&_GUID const IID_IEnumMoniker,IMoniker *,ATL::_CopyInterface<IMoniker>,ATL::CComMultiThreadModel>>(void *)
0x180065e9a  mov     rbx, rax
0x180065e9d  test    rax, rax
0x180065ea0  jz      short loc_180065EF8
0x180065ea2  mov     rax, [rax]
0x180065ea5  mov     rcx, rbx
0x180065ea8  mov     rax, [rax+8]
0x180065eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065eb1  mov     eax, edi
0x180065eb3  lea     r8, [rbp+0D30h+var_D70]
0x180065eb7  xor     r9d, r9d
0x180065eba  mov     dword ptr [rsp+0E30h+ppv], 3
0x180065ec2  lea     rdx, [rbp+0D30h+var_D70]
0x180065ec6  mov     rcx, rbx
0x180065ec9  lea     r8, [r8+rax*8]
0x180065ecd  call    ?Init@?$CComEnumImpl@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@BPEAUIMoniker@@V?$_CopyInterface@UIMoniker@@@ATL@@@ATL@@QEAAJPEAPEAUIMoniker@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumMoniker,&_GUID const IID_IEnumMoniker,IMoniker *,ATL::_CopyInterface<IMoniker>>::Init(IMoniker * *,IMoniker * *,IUnknown *,ATL::CComEnumFlags)
0x180065ed2  mov     esi, eax
0x180065ed4  test    eax, eax
0x180065ed6  js      short loc_180065EFD
0x180065ed8  mov     rax, [rbx]
0x180065edb  lea     rdx, IID_IEnumMoniker
0x180065ee2  mov     r8, [rbp+0D30h+var_D80]
0x180065ee6  mov     rcx, rbx
0x180065ee9  mov     rax, [rax]
0x180065eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ef1  mov     esi, eax
0x180065ef3  jmp     short loc_180065EFD
0x180065ef5  mov     rbx, r15
0x180065ef8  mov     esi, 8007000Eh
0x180065efd  mov     r14d, r15d
0x180065f00  test    edi, edi
0x180065f02  jz      short loc_180065F20
0x180065f04  mov     eax, r14d
0x180065f07  mov     rcx, [rbp+rax*8+0D30h+var_D70]
0x180065f0c  mov     rax, [rcx]
0x180065f0f  mov     rax, [rax+10h]
0x180065f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f18  inc     r14d
0x180065f1b  cmp     r14d, edi
0x180065f1e  jb      short loc_180065F04
0x180065f20  test    rbx, rbx
0x180065f23  jz      short loc_180065F3B
0x180065f25  mov     rax, [rbx]
0x180065f28  mov     rcx, rbx
0x180065f2b  mov     rax, [rax+10h]
0x180065f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f34  jmp     short loc_180065F3B
0x180065f36  mov     esi, 80040216h
0x180065f3b  lea     rcx, [rbp+0D30h+var_DA0]
0x180065f3f  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180065f44  mov     eax, esi
0x180065f46  jmp     short loc_180065F56
0x180065f48  lea     rcx, [rbp+0D30h+var_DA0]
0x180065f4c  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180065f51  mov     eax, 1
0x180065f56  mov     rcx, [rbp+0D30h+var_40]
0x180065f5d  xor     rcx, rsp; StackCookie
0x180065f60  call    __security_check_cookie
0x180065f65  mov     rbx, [rsp+0E30h+arg_18]
0x180065f6d  add     rsp, 0E00h
0x180065f74  pop     r15
0x180065f76  pop     r14
0x180065f78  pop     r13
0x180065f7a  pop     r12
0x180065f7c  pop     rdi
0x180065f7d  pop     rsi
0x180065f7e  pop     rbp
0x180065f7f  retn
```
