# LoadUserConfiguration(void *,ATL::CComPtr<IFhConfigMgrPriv> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,int *)

- ea: `0x180008b30`
- end: `0x180008e55`
- name: `?LoadUserConfiguration@@YAJPEAXAEAV?$CComPtr@UIFhConfigMgrPriv@@@ATL@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEAH@Z`
- size: `805`
- prototype: `__int64 __fastcall(HANDLE Token, LPVOID *ppv, __int64, _DWORD *)`
- caller_count: `9`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800012d0`
- `0x180004e80`
- `0x1800079e0`
- `0x1800086e0`
- `0x18000df70`
- `0x18000e2f0`
- `0x18000e5d0`
- `0x18000e740`
- `0x18000e8b0`

## callees

- `0x180007644`
- `0x180007800`
- `0x180008b30`
- `0x18000ca14`
- `0x18000daf0`
- `0x180013010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180008bc4`
- `ADVAPI32!SetThreadToken` at `0x180008def`
- `ADVAPI32!SetThreadToken` at `0x180008bc4`
- `ADVAPI32!SetThreadToken` at `0x180008def`
- `ADVAPI32!RegGetValueW` at `0x180008dc9`
- `ADVAPI32!RegGetValueW` at `0x180008dc9`
- `KERNEL32!GetLastError` at `0x180008bce`
- `KERNEL32!GetLastError` at `0x180008e0b`
- `KERNEL32!GetLastError` at `0x180008bce`
- `KERNEL32!GetLastError` at `0x180008e0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d18`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d67`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d18`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d67`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008c3c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008c3c`

## string_xrefs

- `0x180008b77`: `ImpersonationToken`

## pseudocode

```c
__int64 __fastcall LoadUserConfiguration(HANDLE Token, LPVOID *ppv, __int64 a3, _DWORD *a4)
{
  LPVOID v9; // rcx
  int v10; // ebx
  signed int LastError; // eax
  unsigned int v12; // edi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  HRESULT Instance; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // r8
  signed int v20; // eax
  _DWORD pvData[10]; // [rsp+40h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+8h] BYREF
  _DWORD *v23; // [rsp+88h] [rbp+20h]

  v23 = a4;
  if ( !Token )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_efece49b8938379c060169b7945fb4b7_Traceguids,
        "ImpersonationToken");
    return 2147942487LL;
  }
  v9 = *ppv;
  v10 = 0;
  if ( *ppv )
  {
    *ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( a3 )
    ATL::CSimpleStringT<unsigned short,0>::Empty(a3);
  if ( !SetThreadToken(0, Token) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_41;
    v14 = 20;
    v15 = v12;
    goto LABEL_16;
  }
  Instance = CoCreateInstance(&CLSID_FhConfigMgr, 0, 0x17u, &GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4, ppv);
  v12 = Instance;
  if ( Instance < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_41;
    v14 = 21;
    v15 = (unsigned int)Instance;
    goto LABEL_16;
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 24LL))(*ppv);
  v12 = v17;
  if ( v17 >= 0 )
  {
    if ( a3 )
    {
      bstrString = 0;
      v18 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)*ppv + 136LL))(*ppv, &bstrString);
      v12 = v18;
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            &WPP_efece49b8938379c060169b7945fb4b7_Traceguids,
            (unsigned int)v18);
        SysFreeString(bstrString);
        goto LABEL_41;
      }
      ATL::CSimpleStringT<unsigned short,0>::Empty(a3);
      if ( bstrString )
      {
        v19 = -1;
        do
          ++v19;
        while ( bstrString[v19] );
      }
      else
      {
        v19 = 0;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(a3, bstrString, v19);
      SysFreeString(bstrString);
      bstrString = 0;
      SysFreeString(0);
    }
    if ( a4 )
    {
      pvData[0] = 0;
      LODWORD(bstrString) = 4;
      if ( !RegGetValueW(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
              L"ReassociationPerformed",
              0x10u,
              0,
              pvData,
              (LPDWORD)&bstrString)
        && (_DWORD)bstrString == 4 )
      {
        LOBYTE(v10) = pvData[0] != 0;
      }
      *a4 = v10;
    }
    goto LABEL_41;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 22;
    v15 = (unsigned int)v17;
LABEL_16:
    WPP_SF_d(v13[2], v14, &WPP_efece49b8938379c060169b7945fb4b7_Traceguids, v15);
  }
LABEL_41:
  if ( !SetThreadToken(0, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v20 = GetLastError();
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      &WPP_efece49b8938379c060169b7945fb4b7_Traceguids,
      (unsigned int)v20);
  }
  return v12;
}

```

## disassembly

```asm
0x180008b30  mov     [rsp+arg_8], rbx
0x180008b35  mov     [rsp+arg_10], rsi
0x180008b3a  mov     [rsp+arg_18], r9
0x180008b3f  push    rdi
0x180008b40  push    r14
0x180008b42  push    r15
0x180008b44  sub     rsp, 50h
0x180008b48  mov     r14, r9
0x180008b4b  mov     rsi, r8
0x180008b4e  mov     r15, rdx
0x180008b51  mov     rdi, rcx
0x180008b54  test    rcx, rcx
0x180008b57  jnz     short loc_180008B98
0x180008b59  lea     rbx, WPP_GLOBAL_Control
0x180008b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b67  cmp     rcx, rbx
0x180008b6a  jz      short loc_180008B8E
0x180008b6c  test    byte ptr [rcx+1Ch], 1
0x180008b70  jz      short loc_180008B8E
0x180008b72  mov     edx, 13h
0x180008b77  lea     r9, aImpersonationt; "ImpersonationToken"
0x180008b7e  lea     r8, WPP_efece49b8938379c060169b7945fb4b7_Traceguids
0x180008b85  mov     rcx, [rcx+10h]
0x180008b89  call    WPP_SF_s
0x180008b8e  mov     eax, 80070057h
0x180008b93  jmp     loc_180008E3E
0x180008b98  mov     rcx, [rdx]
0x180008b9b  xor     ebx, ebx
0x180008b9d  test    rcx, rcx
0x180008ba0  jz      short loc_180008BB2
0x180008ba2  mov     [rdx], rbx
0x180008ba5  mov     rax, [rcx]
0x180008ba8  mov     rax, [rax+10h]
0x180008bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bb1  nop
0x180008bb2  test    rsi, rsi
0x180008bb5  jz      short loc_180008BBF
0x180008bb7  mov     rcx, rsi
0x180008bba  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180008bbf  mov     rdx, rdi; Token
0x180008bc2  xor     ecx, ecx; Thread
0x180008bc4  call    cs:__imp_SetThreadToken
0x180008bca  test    eax, eax
0x180008bcc  jnz     short loc_180008C21
0x180008bce  call    cs:__imp_GetLastError
0x180008bd4  mov     edi, eax
0x180008bd6  test    eax, eax
0x180008bd8  jle     short loc_180008BE3
0x180008bda  movzx   edi, ax
0x180008bdd  or      edi, 80070000h
0x180008be3  lea     rbx, WPP_GLOBAL_Control
0x180008bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bf1  cmp     rcx, rbx
0x180008bf4  jz      loc_180008DEB
0x180008bfa  test    byte ptr [rcx+1Ch], 1
0x180008bfe  jz      loc_180008DEB
0x180008c04  mov     edx, 14h
0x180008c09  mov     r9d, edi
0x180008c0c  lea     r8, WPP_efece49b8938379c060169b7945fb4b7_Traceguids
0x180008c13  mov     rcx, [rcx+10h]
0x180008c17  call    WPP_SF_d
0x180008c1c  jmp     loc_180008DEB
0x180008c21  mov     [rsp+68h+ppv], r15; ppv
0x180008c26  lea     r9, _GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4; riid
0x180008c2d  xor     edx, edx; pUnkOuter
0x180008c2f  mov     r8d, 17h; dwClsContext
0x180008c35  lea     rcx, CLSID_FhConfigMgr; rclsid
0x180008c3c  call    cs:__imp_CoCreateInstance
0x180008c42  mov     edi, eax
0x180008c44  test    eax, eax
0x180008c46  jns     short loc_180008C73
0x180008c48  lea     rbx, WPP_GLOBAL_Control
0x180008c4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c56  cmp     rcx, rbx
0x180008c59  jz      loc_180008DEB
0x180008c5f  test    byte ptr [rcx+1Ch], 1
0x180008c63  jz      loc_180008DEB
0x180008c69  mov     edx, 15h
0x180008c6e  mov     r9d, eax
0x180008c71  jmp     short loc_180008C0C
0x180008c73  mov     rcx, [r15]
0x180008c76  mov     rax, [rcx]
0x180008c79  mov     rax, [rax+18h]
0x180008c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c82  mov     edi, eax
0x180008c84  test    eax, eax
0x180008c86  jns     short loc_180008CB6
0x180008c88  lea     rbx, WPP_GLOBAL_Control
0x180008c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c96  cmp     rcx, rbx
0x180008c99  jz      loc_180008DEB
0x180008c9f  test    byte ptr [rcx+1Ch], 1
0x180008ca3  jz      loc_180008DEB
0x180008ca9  mov     edx, 16h
0x180008cae  mov     r9d, eax
0x180008cb1  jmp     loc_180008C0C
0x180008cb6  test    rsi, rsi
0x180008cb9  jz      loc_180008D84
0x180008cbf  mov     [rsp+68h+bstrString], rbx
0x180008cc4  mov     rcx, [r15]
0x180008cc7  mov     rax, [rcx]
0x180008cca  lea     rdx, [rsp+68h+bstrString]
0x180008ccf  mov     rax, [rax+88h]
0x180008cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdb  mov     edi, eax
0x180008cdd  test    eax, eax
0x180008cdf  jns     short loc_180008D24
0x180008ce1  lea     rbx, WPP_GLOBAL_Control
0x180008ce8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cef  cmp     rcx, rbx
0x180008cf2  jz      short loc_180008D13
0x180008cf4  test    byte ptr [rcx+1Ch], 1
0x180008cf8  jz      short loc_180008D13
0x180008cfa  mov     edx, 17h
0x180008cff  mov     r9d, eax
0x180008d02  lea     r8, WPP_efece49b8938379c060169b7945fb4b7_Traceguids
0x180008d09  mov     rcx, [rcx+10h]
0x180008d0d  call    WPP_SF_d
0x180008d12  nop
0x180008d13  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180008d18  call    cs:__imp_SysFreeString
0x180008d1e  nop
0x180008d1f  jmp     loc_180008DEB
0x180008d24  mov     rcx, rsi
0x180008d27  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180008d2c  mov     rdx, [rsp+68h+bstrString]
0x180008d31  test    rdx, rdx
0x180008d34  jnz     short loc_180008D3B
0x180008d36  mov     r8d, ebx
0x180008d39  jmp     short loc_180008D4D
0x180008d3b  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180008d42  inc     r8
0x180008d45  cmp     word ptr [rdx+r8*2], 0
0x180008d4b  jnz     short loc_180008D42
0x180008d4d  mov     rcx, rsi
0x180008d50  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180008d55  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180008d5a  call    cs:__imp_SysFreeString
0x180008d60  mov     [rsp+68h+bstrString], rbx
0x180008d65  xor     ecx, ecx; bstrString
0x180008d67  call    cs:__imp_SysFreeString
0x180008d6d  nop
0x180008d6e  jmp     short loc_180008D84
0x180008d70  mov     edi, dword ptr [rsp+68h+bstrString]
0x180008d74  jmp     short loc_180008DE4
0x180008d76  xor     ebx, ebx
0x180008d78  mov     r14, [rsp+68h+arg_18]
0x180008d80  mov     edi, dword ptr [rsp+68h+bstrString]
0x180008d84  test    r14, r14
0x180008d87  jz      short loc_180008DE4
0x180008d89  mov     [rsp+68h+var_28], ebx
0x180008d8d  mov     dword ptr [rsp+68h+bstrString], 4
0x180008d95  lea     rax, [rsp+68h+bstrString]
0x180008d9a  mov     [rsp+68h+pcbData], rax; pcbData
0x180008d9f  lea     rax, [rsp+68h+var_28]
0x180008da4  mov     [rsp+68h+pvData], rax; pvData
0x180008da9  mov     [rsp+68h+ppv], rbx; pdwType
0x180008dae  mov     r9d, 10h; dwFlags
0x180008db4  lea     r8, aReassociationp; "ReassociationPerformed"
0x180008dbb  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180008dc2  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180008dc9  call    cs:__imp_RegGetValueW
0x180008dcf  test    eax, eax
0x180008dd1  jnz     short loc_180008DE1
0x180008dd3  cmp     dword ptr [rsp+68h+bstrString], 4
0x180008dd8  jnz     short loc_180008DE1
0x180008dda  cmp     [rsp+68h+var_28], eax
0x180008dde  setnz   bl
0x180008de1  mov     [r14], ebx
0x180008de4  lea     rbx, WPP_GLOBAL_Control
0x180008deb  xor     edx, edx; Token
0x180008ded  xor     ecx, ecx; Thread
0x180008def  call    cs:__imp_SetThreadToken
0x180008df5  test    eax, eax
0x180008df7  jnz     short loc_180008E3C
0x180008df9  mov     rax, cs:WPP_GLOBAL_Control
0x180008e00  cmp     rax, rbx
0x180008e03  jz      short loc_180008E3C
0x180008e05  test    byte ptr [rax+1Ch], 1
0x180008e09  jz      short loc_180008E3C
0x180008e0b  call    cs:__imp_GetLastError
0x180008e11  test    eax, eax
0x180008e13  jle     short loc_180008E1D
0x180008e15  movzx   eax, ax
0x180008e18  or      eax, 80070000h
0x180008e1d  mov     edx, 19h
0x180008e22  mov     r9d, eax
0x180008e25  lea     r8, WPP_efece49b8938379c060169b7945fb4b7_Traceguids
0x180008e2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e33  mov     rcx, [rcx+10h]
0x180008e37  call    WPP_SF_d
0x180008e3c  mov     eax, edi
0x180008e3e  mov     rbx, [rsp+68h+arg_8]
0x180008e43  mov     rsi, [rsp+68h+arg_10]
0x180008e4b  add     rsp, 50h
0x180008e4f  pop     r15
0x180008e51  pop     r14
0x180008e53  pop     rdi
0x180008e54  retn
```
