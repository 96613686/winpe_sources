# ErrorPage::SetupErrorDetails(void)

- ea: `0x140018b5c`
- end: `0x140018f63`
- name: `?SetupErrorDetails@ErrorPage@@IEAAJXZ`
- size: `1031`
- prototype: `__int64 __fastcall(ErrorPage *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140017920`

## callees

- `0x1400070b0`
- `0x14000e300`
- `0x140010680`
- `0x140018b5c`
- `0x140020420`
- `0x140020d58`
- `0x140041c54`
- `0x140049770`
- `0x140049bc0`
- `0x14004a13c`
- `0x140050084`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140018c66`
- `KERNEL32!GetLastError` at `0x140018c66`
- `KERNEL32!HeapAlloc` at `0x140018b99`
- `KERNEL32!HeapAlloc` at `0x140018b99`
- `KERNEL32!HeapFree` at `0x140018f43`
- `KERNEL32!HeapFree` at `0x140018f43`
- `KERNEL32!GetProcessHeap` at `0x140018b82`
- `KERNEL32!GetProcessHeap` at `0x140018f2f`
- `KERNEL32!GetProcessHeap` at `0x140018b82`
- `KERNEL32!GetProcessHeap` at `0x140018f2f`
- `OLEAUT32!__imp_SysFreeString` at `0x140018f23`
- `OLEAUT32!__imp_SysFreeString` at `0x140018f23`
- `Secur32!GetUserNameExW` at `0x140018c56`
- `Secur32!GetUserNameExW` at `0x140018c56`

## string_xrefs

- `0x140018d62`: `txtPath`
- `0x140018d98`: `txtPath`
- `0x140018db8`: `txtPath`

## pseudocode

```c
__int64 __fastcall ErrorPage::SetupErrorDetails(ErrorPage *this)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // rax
  unsigned __int16 *v4; // rsi
  unsigned int v5; // ebx
  int LocalString; // eax
  int v7; // r9d
  signed int LastError; // eax
  int v9; // eax
  int v10; // r9d
  const unsigned __int16 *Path; // rax
  const unsigned __int16 *v12; // rax
  __int64 v13; // rcx
  unsigned __int16 *v14; // r14
  int v15; // eax
  int v16; // r9d
  int v17; // eax
  int v18; // r9d
  UINT v19; // ecx
  HANDLE v20; // rax
  const unsigned __int16 *v22; // [rsp+20h] [rbp-38h]
  unsigned int v23; // [rsp+20h] [rbp-38h]
  const unsigned __int16 *v24; // [rsp+20h] [rbp-38h]
  const unsigned __int16 *v25; // [rsp+20h] [rbp-38h]
  const unsigned __int16 *v26; // [rsp+20h] [rbp-38h]
  int v27; // [rsp+68h] [rbp+10h] BYREF
  ULONG nSize; // [rsp+70h] [rbp+18h] BYREF
  int v29; // [rsp+78h] [rbp+20h] BYREF

  v27 = 0;
  nSize = 256;
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x200u);
  v4 = v3;
  if ( v3 )
  {
    LocalString = StringCchPrintfW(v3, 0x100u, L"0x%08X", *((unsigned int *)this + 32));
    v5 = LocalString;
    if ( LocalString < 0 )
    {
      v7 = 2261;
LABEL_5:
      v23 = LocalString;
LABEL_6:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ErrorPage::SetupErrorDetails", v7, v23);
      goto LABEL_56;
    }
    LocalString = WizardPage::SetNamedValues(this, L"txtErrorCode", v4, 0, v22, 0);
    v5 = LocalString;
    if ( LocalString < 0 )
    {
      v7 = 2264;
      goto LABEL_5;
    }
    if ( !GetUserNameExW(NameSamCompatible, v4, &nSize) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
      {
        v23 = v5;
        v7 = 2270;
        goto LABEL_6;
      }
    }
    LocalString = WizardPage::SetNamedValues(this, L"txtUser", v4, 0, v24, 0);
    v5 = LocalString;
    if ( LocalString < 0 )
    {
      v7 = 2273;
      goto LABEL_5;
    }
    LocalString = DwzLoadLocalString(g_ErrorContext + 20, v4, 0x100u);
    v5 = LocalString;
    if ( LocalString < 0 )
    {
      v7 = 2283;
      goto LABEL_5;
    }
    LocalString = WizardPage::SetNamedValues(this, L"txtSource", v4, 0, v25, 0);
    v5 = LocalString;
    if ( LocalString < 0 )
    {
      v7 = 2286;
      goto LABEL_5;
    }
    if ( *((_DWORD *)Config + 66) == 9 )
    {
      v9 = DwzLoadLocalString(0x168u, v4, 0x100u);
      v5 = v9;
      if ( v9 < 0 )
      {
        v10 = 2299;
LABEL_24:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ErrorPage::SetupErrorDetails", v10, v9);
LABEL_56:
        v20 = GetProcessHeap();
        HeapFree(v20, 0, v4);
        return v5;
      }
      v9 = WizardPage::SetNamedValues(this, L"txtPath", v4, 0, v26, 0);
      v5 = v9;
      if ( v9 < 0 )
      {
        v10 = 2302;
        goto LABEL_24;
      }
    }
    else if ( Packages_GetNumber() )
    {
      Path = Packages_GetPath();
      v9 = WizardPage::SetNamedValues(this, L"txtPath", Path, 0, v26, Path);
      v5 = v9;
      if ( v9 < 0 )
      {
        v10 = 2307;
        goto LABEL_24;
      }
      v9 = WizardPage::EnableNamedTooltip(this, L"txtPath", 1);
      v5 = v9;
      if ( v9 < 0 )
      {
        v10 = 2310;
        goto LABEL_24;
      }
    }
    v12 = Packages_ID();
    v14 = (unsigned __int16 *)v12;
    if ( v12 )
    {
      v15 = DwzStrTruncate(v4, 0x24u, v12, &v29);
      v5 = v15;
      if ( v15 < 0 )
      {
        v16 = 2323;
LABEL_35:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ErrorPage::SetupErrorDetails", v16, v15);
        goto LABEL_55;
      }
      v15 = WizardPage::SetNamedValues(this, L"txtPackage", v4, v14, v26, v14);
      v5 = v15;
      if ( v15 < 0 )
      {
        v16 = 2326;
        goto LABEL_35;
      }
      v15 = WizardPage::EnableNamedTooltip(this, L"txtPackage", 1);
      v5 = v15;
      if ( v15 < 0 )
      {
        v16 = 2329;
        goto LABEL_35;
      }
    }
    if ( (unsigned int)LUAGetUserType(v13, &v27) )
    {
      v17 = -2147467259;
      v18 = 2337;
      v5 = -2147467259;
    }
    else
    {
      if ( v27 )
      {
        if ( v27 == 1 )
        {
          v19 = 362;
        }
        else
        {
          if ( v27 != 2 )
          {
            v17 = -2147467259;
            v18 = 2352;
            v5 = -2147467259;
            goto LABEL_53;
          }
          v19 = 363;
        }
      }
      else
      {
        v19 = 361;
      }
      v17 = DwzLoadLocalString(v19, v4, 0x100u);
      v5 = v17;
      if ( v17 >= 0 )
      {
        v17 = WizardPage::SetNamedValues(this, L"txtContext", v4, 0, v26, 0);
        v5 = v17;
        if ( v17 >= 0 )
          goto LABEL_54;
        v18 = 2359;
      }
      else
      {
        v18 = 2356;
      }
    }
LABEL_53:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ErrorPage::SetupErrorDetails", v18, v17);
LABEL_54:
    if ( !v14 )
      goto LABEL_56;
LABEL_55:
    SysFreeString(v14);
    goto LABEL_56;
  }
  v5 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ErrorPage::SetupErrorDetails", 2255, -2147024882);
  return v5;
}

```

## disassembly

```asm
0x140018b5c  mov     [rsp+arg_0], rbx
0x140018b61  push    rbp
0x140018b62  push    rsi
0x140018b63  push    rdi
0x140018b64  push    r12
0x140018b66  push    r14
0x140018b68  sub     rsp, 30h
0x140018b6c  mov     r12d, 100h
0x140018b72  mov     [rsp+58h+arg_8], 0
0x140018b7a  mov     [rsp+58h+nSize], r12d
0x140018b7f  mov     rbp, rcx
0x140018b82  call    cs:__imp_GetProcessHeap
0x140018b89  nop     dword ptr [rax+rax+00h]
0x140018b8e  xor     edx, edx; dwFlags
0x140018b90  mov     r8d, 200h; dwBytes
0x140018b96  mov     rcx, rax; hHeap
0x140018b99  call    cs:__imp_HeapAlloc
0x140018ba0  nop     dword ptr [rax+rax+00h]
0x140018ba5  mov     rsi, rax
0x140018ba8  test    rax, rax
0x140018bab  jnz     short loc_140018BD7
0x140018bad  mov     ebx, 8007000Eh
0x140018bb2  lea     r8, aErrorpageSetup; "ErrorPage::SetupErrorDetails"
0x140018bb9  mov     r9d, 8CFh
0x140018bbf  mov     dword ptr [rsp+58h+var_38], ebx
0x140018bc3  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140018bca  lea     ecx, [rax+1]; Level
0x140018bcd  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140018bd2  jmp     loc_140018F4F
0x140018bd7  mov     r9d, [rbp+80h]
0x140018bde  lea     r8, a0x08x; "0x%08X"
0x140018be5  mov     rdx, r12; unsigned __int64
0x140018be8  mov     rcx, rsi; unsigned __int16 *
0x140018beb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140018bf0  mov     ebx, eax
0x140018bf2  test    eax, eax
0x140018bf4  jns     short loc_140018C1D
0x140018bf6  mov     r9d, 8D5h
0x140018bfc  mov     dword ptr [rsp+58h+var_38], eax
0x140018c00  mov     ecx, 1; Level
0x140018c05  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140018c0c  lea     r8, aErrorpageSetup; "ErrorPage::SetupErrorDetails"
0x140018c13  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140018c18  jmp     loc_140018F2F
0x140018c1d  xor     r9d, r9d; unsigned __int16 *
0x140018c20  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x140018c29  mov     r8, rsi; unsigned __int16 *
0x140018c2c  lea     rdx, aTxterrorcode; "txtErrorCode"
0x140018c33  mov     rcx, rbp; this
0x140018c36  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140018c3b  mov     ebx, eax
0x140018c3d  test    eax, eax
0x140018c3f  jns     short loc_140018C49
0x140018c41  mov     r9d, 8D8h
0x140018c47  jmp     short loc_140018BFC
0x140018c49  lea     r8, [rsp+58h+nSize]; nSize
0x140018c4e  mov     rdx, rsi; lpNameBuffer
0x140018c51  mov     ecx, 2; NameFormat
0x140018c56  call    cs:__imp_GetUserNameExW
0x140018c5d  nop     dword ptr [rax+rax+00h]
0x140018c62  test    al, al
0x140018c64  jnz     short loc_140018C94
0x140018c66  call    cs:__imp_GetLastError
0x140018c6d  nop     dword ptr [rax+rax+00h]
0x140018c72  mov     ebx, eax
0x140018c74  test    eax, eax
0x140018c76  jle     short loc_140018C81
0x140018c78  movzx   ebx, ax
0x140018c7b  or      ebx, 80070000h
0x140018c81  test    ebx, ebx
0x140018c83  jns     short loc_140018C94
0x140018c85  mov     dword ptr [rsp+58h+var_38], ebx
0x140018c89  mov     r9d, 8DEh
0x140018c8f  jmp     loc_140018C00
0x140018c94  xor     r9d, r9d; unsigned __int16 *
0x140018c97  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x140018ca0  mov     r8, rsi; unsigned __int16 *
0x140018ca3  lea     rdx, aTxtuser; "txtUser"
0x140018caa  mov     rcx, rbp; this
0x140018cad  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140018cb2  mov     ebx, eax
0x140018cb4  test    eax, eax
0x140018cb6  jns     short loc_140018CC3
0x140018cb8  mov     r9d, 8E1h
0x140018cbe  jmp     loc_140018BFC
0x140018cc3  mov     ecx, cs:?g_ErrorContext@@3IC; uint volatile g_ErrorContext
0x140018cc9  mov     r8, r12; cchBufferMax
0x140018ccc  add     ecx, 14h; uID
0x140018ccf  mov     rdx, rsi; lpBuffer
0x140018cd2  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x140018cd7  mov     ebx, eax
0x140018cd9  test    eax, eax
0x140018cdb  jns     short loc_140018CE8
0x140018cdd  mov     r9d, 8EBh
0x140018ce3  jmp     loc_140018BFC
0x140018ce8  xor     r9d, r9d; unsigned __int16 *
0x140018ceb  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x140018cf4  mov     r8, rsi; unsigned __int16 *
0x140018cf7  lea     rdx, aTxtsource; "txtSource"
0x140018cfe  mov     rcx, rbp; this
0x140018d01  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140018d06  mov     ebx, eax
0x140018d08  test    eax, eax
0x140018d0a  jns     short loc_140018D17
0x140018d0c  mov     r9d, 8EEh
0x140018d12  jmp     loc_140018BFC
0x140018d17  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140018d1e  mov     edi, 1
0x140018d23  cmp     dword ptr [rax+108h], 9
0x140018d2a  jnz     short loc_140018D7F
0x140018d2c  mov     r8, r12; cchBufferMax
0x140018d2f  mov     rdx, rsi; lpBuffer
0x140018d32  mov     ecx, 168h; uID
0x140018d37  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x140018d3c  mov     ebx, eax
0x140018d3e  test    eax, eax
0x140018d40  jns     short loc_140018D53
0x140018d42  mov     r9d, 8FBh
0x140018d48  mov     dword ptr [rsp+58h+var_38], eax
0x140018d4c  mov     ecx, edi
0x140018d4e  jmp     loc_140018C05
0x140018d53  xor     r9d, r9d; unsigned __int16 *
0x140018d56  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x140018d5f  mov     r8, rsi; unsigned __int16 *
0x140018d62  lea     rdx, aTxtpath; "txtPath"
0x140018d69  mov     rcx, rbp; this
0x140018d6c  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140018d71  mov     ebx, eax
0x140018d73  test    eax, eax
0x140018d75  jns     short loc_140018DD8
0x140018d77  mov     r9d, 8FEh
0x140018d7d  jmp     short loc_140018D48
0x140018d7f  call    ?Packages_GetNumber@@YAIXZ; Packages_GetNumber(void)
0x140018d84  test    eax, eax
0x140018d86  jz      short loc_140018DD8
0x140018d88  call    ?Packages_GetPath@@YAPEBGXZ; Packages_GetPath(void)
0x140018d8d  xor     r9d, r9d; unsigned __int16 *
0x140018d90  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x140018d95  mov     r8, rax; unsigned __int16 *
0x140018d98  lea     rdx, aTxtpath; "txtPath"
0x140018d9f  mov     rcx, rbp; this
0x140018da2  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140018da7  mov     ebx, eax
0x140018da9  test    eax, eax
0x140018dab  jns     short loc_140018DB5
0x140018dad  mov     r9d, 903h
0x140018db3  jmp     short loc_140018D48
0x140018db5  mov     r8d, edi; int
0x140018db8  lea     rdx, aTxtpath; "txtPath"
0x140018dbf  mov     rcx, rbp; this
0x140018dc2  call    ?EnableNamedTooltip@WizardPage@@IEAAJPEBGH@Z; WizardPage::EnableNamedTooltip(ushort const *,int)
0x140018dc7  mov     ebx, eax
0x140018dc9  test    eax, eax
0x140018dcb  jns     short loc_140018DD8
0x140018dcd  mov     r9d, 906h
0x140018dd3  jmp     loc_140018D48
0x140018dd8  call    ?Packages_ID@@YAPEAGXZ; Packages_ID(void)
0x140018ddd  mov     r14, rax
0x140018de0  test    rax, rax
0x140018de3  jz      loc_140018E70
0x140018de9  lea     r9, [rsp+58h+arg_18]; int *
0x140018dee  mov     r8, rax; unsigned __int16 *
0x140018df1  mov     edx, 24h ; '$'; unsigned __int64
0x140018df6  mov     rcx, rsi; unsigned __int16 *
0x140018df9  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x140018dfe  mov     ebx, eax
0x140018e00  test    eax, eax
0x140018e02  jns     short loc_140018E28
0x140018e04  mov     r9d, 913h
0x140018e0a  lea     r8, aErrorpageSetup; "ErrorPage::SetupErrorDetails"
0x140018e11  mov     dword ptr [rsp+58h+var_38], eax
0x140018e15  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140018e1c  mov     ecx, edi; Level
0x140018e1e  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140018e23  jmp     loc_140018F20
0x140018e28  mov     r9, r14; unsigned __int16 *
0x140018e2b  mov     [rsp+58h+var_30], r14; unsigned __int16 *
0x140018e30  mov     r8, rsi; unsigned __int16 *
0x140018e33  lea     rdx, aTxtpackage; "txtPackage"
0x140018e3a  mov     rcx, rbp; this
0x140018e3d  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140018e42  mov     ebx, eax
0x140018e44  test    eax, eax
0x140018e46  jns     short loc_140018E50
0x140018e48  mov     r9d, 916h
0x140018e4e  jmp     short loc_140018E0A
0x140018e50  mov     r8d, edi; int
0x140018e53  lea     rdx, aTxtpackage; "txtPackage"
0x140018e5a  mov     rcx, rbp; this
0x140018e5d  call    ?EnableNamedTooltip@WizardPage@@IEAAJPEBGH@Z; WizardPage::EnableNamedTooltip(ushort const *,int)
0x140018e62  mov     ebx, eax
0x140018e64  test    eax, eax
0x140018e66  jns     short loc_140018E70
0x140018e68  mov     r9d, 919h
0x140018e6e  jmp     short loc_140018E0A
0x140018e70  lea     rdx, [rsp+58h+arg_8]
0x140018e75  call    LUAGetUserType
0x140018e7a  test    eax, eax
0x140018e7c  jz      short loc_140018E8D
0x140018e7e  mov     eax, 80004005h
0x140018e83  mov     r9d, 921h
0x140018e89  mov     ebx, eax
0x140018e8b  jmp     short loc_140018F02
0x140018e8d  mov     ecx, [rsp+58h+arg_8]
0x140018e91  test    ecx, ecx
0x140018e93  jz      short loc_140018EBA
0x140018e95  sub     ecx, edi
0x140018e97  jz      short loc_140018EB3
0x140018e99  cmp     ecx, edi
0x140018e9b  jz      short loc_140018EAC
0x140018e9d  mov     eax, 80004005h
0x140018ea2  mov     r9d, 930h
0x140018ea8  mov     ebx, eax
0x140018eaa  jmp     short loc_140018F02
0x140018eac  mov     ecx, 16Bh
0x140018eb1  jmp     short loc_140018EBF
0x140018eb3  mov     ecx, 16Ah
0x140018eb8  jmp     short loc_140018EBF
0x140018eba  mov     ecx, 169h; uID
0x140018ebf  mov     r8, r12; cchBufferMax
0x140018ec2  mov     rdx, rsi; lpBuffer
0x140018ec5  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x140018eca  mov     ebx, eax
0x140018ecc  test    eax, eax
0x140018ece  jns     short loc_140018ED8
0x140018ed0  mov     r9d, 934h
0x140018ed6  jmp     short loc_140018F02
0x140018ed8  xor     r9d, r9d; unsigned __int16 *
0x140018edb  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x140018ee4  mov     r8, rsi; unsigned __int16 *
0x140018ee7  lea     rdx, aTxtcontext; "txtContext"
0x140018eee  mov     rcx, rbp; this
0x140018ef1  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140018ef6  mov     ebx, eax
0x140018ef8  test    eax, eax
0x140018efa  jns     short loc_140018F1B
0x140018efc  mov     r9d, 937h
0x140018f02  lea     r8, aErrorpageSetup; "ErrorPage::SetupErrorDetails"
0x140018f09  mov     dword ptr [rsp+58h+var_38], eax
0x140018f0d  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140018f14  mov     ecx, edi; Level
0x140018f16  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140018f1b  test    r14, r14
0x140018f1e  jz      short loc_140018F2F
0x140018f20  mov     rcx, r14; bstrString
0x140018f23  call    cs:__imp_SysFreeString
0x140018f2a  nop     dword ptr [rax+rax+00h]
0x140018f2f  call    cs:__imp_GetProcessHeap
0x140018f36  nop     dword ptr [rax+rax+00h]
0x140018f3b  mov     r8, rsi; lpMem
0x140018f3e  xor     edx, edx; dwFlags
0x140018f40  mov     rcx, rax; hHeap
0x140018f43  call    cs:__imp_HeapFree
0x140018f4a  nop     dword ptr [rax+rax+00h]
0x140018f4f  mov     eax, ebx
0x140018f51  mov     rbx, [rsp+58h+arg_0]
0x140018f56  add     rsp, 30h
0x140018f5a  pop     r14
0x140018f5c  pop     r12
0x140018f5e  pop     rdi
0x140018f5f  pop     rsi
0x140018f60  pop     rbp
0x140018f61  retn
```
