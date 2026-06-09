# CDimInterfaceTable::RegGetInterfaceInfo(HKEY__ *,ushort *,_ROUTER_INTERFACE_TYPE &,bool &,ulong &,ulong &)

- ea: `0x1800268b8`
- end: `0x180026d4e`
- name: `?RegGetInterfaceInfo@CDimInterfaceTable@@CAKPEAUHKEY__@@PEAGAEAW4_ROUTER_INTERFACE_TYPE@@AEA_NAEAK4@Z`
- size: `1174`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, unsigned __int16 *@<rdx>, enum _ROUTER_INTERFACE_TYPE *@<r8>, bool *@<r9>, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800091dc`

## callees

- `0x18000df70`
- `0x1800268b8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `rtutils!RouterLogEventW` at `0x180026b58`
- `rtutils!RouterLogEventW` at `0x180026c3d`
- `rtutils!RouterLogEventW` at `0x180026d23`
- `rtutils!RouterLogEventW` at `0x180026b58`
- `rtutils!RouterLogEventW` at `0x180026c3d`
- `rtutils!RouterLogEventW` at `0x180026d23`
- `ADVAPI32!RegQueryValueExW` at `0x180026969`
- `ADVAPI32!RegQueryValueExW` at `0x1800269c0`
- `ADVAPI32!RegQueryValueExW` at `0x180026a62`
- `ADVAPI32!RegQueryValueExW` at `0x180026b8a`
- `ADVAPI32!RegQueryValueExW` at `0x180026969`
- `ADVAPI32!RegQueryValueExW` at `0x1800269c0`
- `ADVAPI32!RegQueryValueExW` at `0x180026a62`
- `ADVAPI32!RegQueryValueExW` at `0x180026b8a`

## string_xrefs

- `0x180026a03`: `Cannot access Registry value for %s.`
- `0x180026abd`: `Cannot access Registry value for %s.`
- `0x180026bcd`: `Cannot access Registry value for %s.`
- `0x180026cb0`: `Cannot access Registry value for %s.`

## pseudocode

```c
__int64 __fastcall CDimInterfaceTable::RegGetInterfaceInfo(
        HKEY hKey,
        unsigned __int16 *a2,
        enum _ROUTER_INTERFACE_TYPE *a3,
        bool *a4,
        BYTE *a5,
        BYTE *a6)
{
  unsigned int v10; // edi
  DWORD v11; // ebx
  GUID *v12; // r9
  LSTATUS v13; // eax
  DWORD v14; // edi
  LSTATUS v15; // eax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  LPWSTR plpszSubStringArray; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE lpData[4]; // [rsp+44h] [rbp-BCh] BYREF
  GUID v22; // [rsp+48h] [rbp-B8h] BYREF
  GUID v23; // [rsp+58h] [rbp-A8h] BYREF
  GUID v24; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v25[2]; // [rsp+78h] [rbp-88h] BYREF
  int v26; // [rsp+98h] [rbp-68h] BYREF
  __int128 v27; // [rsp+9Ch] [rbp-64h]
  __int128 v28; // [rsp+ACh] [rbp-54h]
  int v29; // [rsp+BCh] [rbp-44h]
  int v30; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v31[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  *(_DWORD *)Data = 0;
  Type = 0;
  *(_DWORD *)lpData = 0;
  v30 = 0;
  cbData = 4;
  v25[1] = 0;
  memset_0(v31, 0, sizeof(v31));
  v26 = 0;
  v29 = 0;
  v27 = 0;
  v28 = 0;
  v10 = RegQueryValueExW(hKey, L"Type", 0, &Type, Data, &cbData);
  if ( v10 )
  {
LABEL_34:
    v25[0] = GUID_NULL;
    plpszSubStringArray = (LPWSTR)L"Type";
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
    {
      LOWORD(v30) = 0;
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v30, L"Cannot access Registry value for %s.");
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        v12 = (GUID *)v25;
        goto LABEL_37;
      }
    }
LABEL_38:
    if ( dword_180070F40 )
      RouterLogEventW(hLogHandle, 1u, 0x4E83u, 1u, &plpszSubStringArray, v10);
    return v10;
  }
  if ( Type != 4 || *(_DWORD *)Data >= 8u )
  {
    v10 = 1015;
    goto LABEL_34;
  }
  *a3 = *(enum _ROUTER_INTERFACE_TYPE *)Data;
  v11 = v10 + 4;
  cbData = v10 + 4;
  v10 = RegQueryValueExW(hKey, L"Enabled", 0, &Type, lpData, &cbData);
  if ( v10 )
  {
LABEL_7:
    v24 = GUID_NULL;
    plpszSubStringArray = (LPWSTR)L"Enabled";
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
    {
      LOWORD(v30) = 0;
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v30, L"Cannot access Registry value for %s.");
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        v12 = &v24;
LABEL_37:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceAdminError,
          (unsigned int)&v30,
          (_DWORD)v12,
          (__int64)a2,
          (__int64)&v26);
        goto LABEL_38;
      }
    }
    goto LABEL_38;
  }
  if ( Type != v11 )
  {
    v10 = 1015;
    goto LABEL_7;
  }
  cbData = v11;
  *a4 = *(_DWORD *)lpData != 0;
  v13 = RegQueryValueExW(hKey, L"MinUnreachabilityInterval", 0, &Type, a5, &cbData);
  v14 = v13;
  if ( v13 )
  {
    if ( v13 == 2 )
    {
      *(_DWORD *)a5 = 60;
    }
    else
    {
      plpszSubStringArray = (LPWSTR)L"MinUnreachabilityInterval";
      v22 = GUID_NULL;
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        LOWORD(v30) = 0;
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v30, L"Cannot access Registry value for %s.", L"MinUnreachabilityInterval");
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceAdminError,
            (unsigned int)&v30,
            (unsigned int)&v22,
            (__int64)a2,
            (__int64)&v26);
      }
      if ( dword_180070F40 )
        RouterLogEventW(hLogHandle, 1u, 0x4E83u, 1u, &plpszSubStringArray, v14);
    }
  }
  else if ( Type != 4 )
  {
    *(_DWORD *)a5 = 60;
    plpszSubStringArray = (LPWSTR)L"MinUnreachabilityInterval";
    if ( (unsigned int)dword_180070F40 > 1 )
      RouterLogEventW(hLogHandle, 2u, 0x4E85u, 1u, &plpszSubStringArray, 0);
  }
  cbData = 4;
  v15 = RegQueryValueExW(hKey, L"MaxUnreachabilityInterval", 0, &Type, a6, &cbData);
  v10 = v15;
  if ( v15 )
  {
    if ( v15 == 2 )
    {
      *(_DWORD *)a6 = 21600;
    }
    else
    {
      plpszSubStringArray = (LPWSTR)L"MaxUnreachabilityInterval";
      v23 = GUID_NULL;
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        LOWORD(v30) = 0;
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v30, L"Cannot access Registry value for %s.", L"MaxUnreachabilityInterval");
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceAdminError,
            (unsigned int)&v30,
            (unsigned int)&v23,
            (__int64)a2,
            (__int64)&v26);
      }
      if ( dword_180070F40 )
        RouterLogEventW(hLogHandle, 1u, 0x4E83u, 1u, &plpszSubStringArray, v10);
    }
    return 0;
  }
  else if ( Type != 4 )
  {
    *(_DWORD *)a6 = 21600;
    plpszSubStringArray = (LPWSTR)L"MaxUnreachabilityInterval";
    if ( (unsigned int)dword_180070F40 > 1 )
      RouterLogEventW(hLogHandle, 2u, 0x4E85u, 1u, &plpszSubStringArray, 0);
  }
  return v10;
}

```

## disassembly

```asm
0x1800268b8  push    rbp
0x1800268ba  push    rbx
0x1800268bb  push    rsi
0x1800268bc  push    rdi
0x1800268bd  push    r12
0x1800268bf  push    r13
0x1800268c1  push    r14
0x1800268c3  push    r15
0x1800268c5  lea     rbp, [rsp-7D8h]
0x1800268cd  sub     rsp, 8D8h
0x1800268d4  mov     rax, cs:__security_cookie
0x1800268db  xor     rax, rsp
0x1800268de  mov     [rbp+810h+var_50], rax
0x1800268e5  mov     r14, [rbp+810h+arg_20]
0x1800268ec  xor     edi, edi
0x1800268ee  mov     r15, [rbp+810h+arg_28]
0x1800268f5  mov     rbx, r8
0x1800268f8  mov     rsi, rdx
0x1800268fb  mov     dword ptr [rsp+910h+Data], edi
0x1800268ff  mov     r12, rcx
0x180026902  mov     [rsp+910h+Type], edi
0x180026906  xorps   xmm0, xmm0
0x180026909  mov     dword ptr [rsp+910h+var_8CC], edi
0x18002690d  xor     edx, edx; Val
0x18002690f  mov     [rbp+810h+var_850], edi
0x180026912  mov     r8d, 7FCh; Size
0x180026918  mov     [rsp+910h+cbData], 4
0x180026920  lea     rcx, [rbp+810h+var_84C]; void *
0x180026924  mov     r13, r9
0x180026927  movups  [rbp+810h+var_888], xmm0
0x18002692b  call    memset_0
0x180026930  xor     eax, eax
0x180026932  mov     [rbp+810h+var_878], edi
0x180026935  mov     [rbp+810h+var_854], eax
0x180026938  lea     r9, [rsp+910h+Type]; lpType
0x18002693d  xorps   xmm0, xmm0
0x180026940  lea     rax, [rsp+910h+cbData]
0x180026945  mov     [rsp+910h+lpcbData], rax; lpcbData
0x18002694a  lea     rdx, aType; "Type"
0x180026951  lea     rax, [rsp+910h+Data]
0x180026956  xor     r8d, r8d; lpReserved
0x180026959  mov     rcx, r12; hKey
0x18002695c  mov     [rsp+910h+lpData], rax; lpData
0x180026961  movups  [rbp+810h+var_874], xmm0
0x180026965  movups  [rbp+810h+var_864], xmm0
0x180026969  call    cs:__imp_RegQueryValueExW
0x18002696f  mov     edi, eax
0x180026971  test    eax, eax
0x180026973  jnz     loc_180026C88
0x180026979  cmp     [rsp+910h+Type], 4
0x18002697e  jnz     loc_180026C83
0x180026984  mov     eax, dword ptr [rsp+910h+Data]
0x180026988  cmp     eax, 8
0x18002698b  jnb     loc_180026C83
0x180026991  mov     [rbx], eax
0x180026993  lea     r9, [rsp+910h+Type]; lpType
0x180026998  lea     rax, [rsp+910h+cbData]
0x18002699d  xor     r8d, r8d; lpReserved
0x1800269a0  mov     [rsp+910h+lpcbData], rax; lpcbData
0x1800269a5  lea     ebx, [rdi+4]
0x1800269a8  lea     rax, [rsp+910h+var_8CC]
0x1800269ad  mov     [rsp+910h+cbData], ebx
0x1800269b1  lea     rdx, aEnabled; "Enabled"
0x1800269b8  mov     [rsp+910h+lpData], rax; lpData
0x1800269bd  mov     rcx, r12; hKey
0x1800269c0  call    cs:__imp_RegQueryValueExW
0x1800269c6  mov     edi, eax
0x1800269c8  test    eax, eax
0x1800269ca  jnz     short loc_1800269D7
0x1800269cc  cmp     [rsp+910h+Type], ebx
0x1800269d0  jz      short loc_180026A31
0x1800269d2  mov     edi, 3F7h
0x1800269d7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800269de  mov     ebx, 1
0x1800269e3  lea     r8, aEnabled; "Enabled"
0x1800269ea  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800269f0  movdqu  [rsp+910h+var_8A8], xmm0
0x1800269f6  mov     [rsp+910h+plpszSubStringArray], r8
0x1800269fb  jz      loc_180026CFA
0x180026a01  xor     eax, eax
0x180026a03  lea     rdx, aCannotAccessRe; "Cannot access Registry value for %s."
0x180026a0a  lea     rcx, [rbp+810h+var_850]
0x180026a0e  mov     word ptr [rbp+810h+var_850], ax
0x180026a12  mov     word ptr [rbp+810h+var_878], ax
0x180026a16  call    FormatRRASErrorString
0x180026a1b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026a21  jz      loc_180026CFA
0x180026a27  lea     r9, [rsp+910h+var_8A8]
0x180026a2c  jmp     loc_180026CD5
0x180026a31  cmp     dword ptr [rsp+910h+var_8CC], 0
0x180026a36  lea     r9, [rsp+910h+Type]; lpType
0x180026a3b  lea     rdx, aMinunreachabil; "MinUnreachabilityInterval"
0x180026a42  mov     [rsp+910h+cbData], ebx
0x180026a46  setnz   al
0x180026a49  mov     rcx, r12; hKey
0x180026a4c  mov     [r13+0], al
0x180026a50  xor     r8d, r8d; lpReserved
0x180026a53  lea     rax, [rsp+910h+cbData]
0x180026a58  mov     [rsp+910h+lpcbData], rax; lpcbData
0x180026a5d  mov     [rsp+910h+lpData], r14; lpData
0x180026a62  call    cs:__imp_RegQueryValueExW
0x180026a68  xor     r13d, r13d
0x180026a6b  mov     ebx, 1
0x180026a70  mov     edi, eax
0x180026a72  test    eax, eax
0x180026a74  jz      loc_180026B12
0x180026a7a  cmp     eax, 2
0x180026a7d  jnz     short loc_180026A8B
0x180026a7f  mov     dword ptr [r14], 3Ch ; '<'
0x180026a86  jmp     loc_180026B5E
0x180026a8b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026a91  lea     rcx, aMinunreachabil; "MinUnreachabilityInterval"
0x180026a98  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180026a9f  mov     [rsp+910h+plpszSubStringArray], rcx
0x180026aa4  movdqu  [rsp+910h+var_8C8], xmm0
0x180026aaa  jz      short loc_180026AFB
0x180026aac  mov     r8, rcx
0x180026aaf  mov     word ptr [rbp+810h+var_850], r13w
0x180026ab4  lea     rcx, [rbp+810h+var_850]
0x180026ab8  mov     word ptr [rbp+810h+var_878], r13w
0x180026abd  lea     rdx, aCannotAccessRe; "Cannot access Registry value for %s."
0x180026ac4  call    FormatRRASErrorString
0x180026ac9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026acf  jz      short loc_180026AFB
0x180026ad1  lea     rax, [rbp+810h+var_878]
0x180026ad5  mov     [rsp+910h+lpcbData], rax
0x180026ada  lea     r9, [rsp+910h+var_8C8]
0x180026adf  lea     r8, [rbp+810h+var_850]
0x180026ae3  mov     [rsp+910h+lpData], rsi
0x180026ae8  lea     rdx, RasDimParamTraceAdminError
0x180026aef  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026af6  call    McTemplateU0zjzz_EventWriteTransfer
0x180026afb  cmp     cs:dword_180070F40, r13d
0x180026b02  jbe     short loc_180026B5E
0x180026b04  mov     dword ptr [rsp+910h+lpcbData], edi
0x180026b08  mov     r8d, 4E83h
0x180026b0e  mov     edx, ebx
0x180026b10  jmp     short loc_180026B44
0x180026b12  cmp     [rsp+910h+Type], 4
0x180026b17  jz      short loc_180026B5E
0x180026b19  mov     dword ptr [r14], 3Ch ; '<'
0x180026b20  lea     rcx, aMinunreachabil; "MinUnreachabilityInterval"
0x180026b27  cmp     cs:dword_180070F40, ebx
0x180026b2d  mov     [rsp+910h+plpszSubStringArray], rcx
0x180026b32  jbe     short loc_180026B5E
0x180026b34  mov     dword ptr [rsp+910h+lpcbData], r13d; dwErrorCode
0x180026b39  mov     edx, 2; dwEventType
0x180026b3e  mov     r8d, 4E85h; dwMessageId
0x180026b44  mov     rcx, cs:hLogHandle; hLogHandle
0x180026b4b  lea     rax, [rsp+910h+plpszSubStringArray]
0x180026b50  mov     r9d, ebx; dwSubStringCount
0x180026b53  mov     [rsp+910h+lpData], rax; plpszSubStringArray
0x180026b58  call    cs:__imp_RouterLogEventW
0x180026b5e  lea     rax, [rsp+910h+cbData]
0x180026b63  mov     [rsp+910h+cbData], 4
0x180026b6b  mov     [rsp+910h+lpcbData], rax; lpcbData
0x180026b70  lea     r14, aMaxunreachabil; "MaxUnreachabilityInterval"
0x180026b77  mov     rdx, r14; lpValueName
0x180026b7a  mov     [rsp+910h+lpData], r15; lpData
0x180026b7f  lea     r9, [rsp+910h+Type]; lpType
0x180026b84  xor     r8d, r8d; lpReserved
0x180026b87  mov     rcx, r12; hKey
0x180026b8a  call    cs:__imp_RegQueryValueExW
0x180026b90  mov     edi, eax
0x180026b92  test    eax, eax
0x180026b94  jz      loc_180026C4B
0x180026b9a  cmp     eax, 2
0x180026b9d  jnz     short loc_180026BAB
0x180026b9f  mov     dword ptr [r15], 5460h
0x180026ba6  jmp     loc_180026C43
0x180026bab  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026bb1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180026bb8  mov     [rsp+910h+plpszSubStringArray], r14
0x180026bbd  movdqu  [rsp+910h+var_8B8], xmm0
0x180026bc3  jz      short loc_180026C14
0x180026bc5  mov     r8, r14
0x180026bc8  mov     word ptr [rbp+810h+var_850], r13w
0x180026bcd  lea     rdx, aCannotAccessRe; "Cannot access Registry value for %s."
0x180026bd4  mov     word ptr [rbp+810h+var_878], r13w
0x180026bd9  lea     rcx, [rbp+810h+var_850]
0x180026bdd  call    FormatRRASErrorString
0x180026be2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026be8  jz      short loc_180026C14
0x180026bea  lea     rax, [rbp+810h+var_878]
0x180026bee  mov     [rsp+910h+lpcbData], rax
0x180026bf3  lea     r9, [rsp+910h+var_8B8]
0x180026bf8  lea     r8, [rbp+810h+var_850]
0x180026bfc  mov     [rsp+910h+lpData], rsi
0x180026c01  lea     rdx, RasDimParamTraceAdminError
0x180026c08  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026c0f  call    McTemplateU0zjzz_EventWriteTransfer
0x180026c14  cmp     cs:dword_180070F40, r13d
0x180026c1b  jbe     short loc_180026C43
0x180026c1d  mov     rcx, cs:hLogHandle; hLogHandle
0x180026c24  lea     rax, [rsp+910h+plpszSubStringArray]
0x180026c29  mov     dword ptr [rsp+910h+lpcbData], edi; dwErrorCode
0x180026c2d  mov     r9d, ebx; dwSubStringCount
0x180026c30  mov     r8d, 4E83h; dwMessageId
0x180026c36  mov     [rsp+910h+lpData], rax; plpszSubStringArray
0x180026c3b  mov     edx, ebx; dwEventType
0x180026c3d  call    cs:__imp_RouterLogEventW
0x180026c43  mov     edi, r13d
0x180026c46  jmp     loc_180026D29
0x180026c4b  cmp     [rsp+910h+Type], 4
0x180026c50  jz      loc_180026D29
0x180026c56  mov     dword ptr [r15], 5460h
0x180026c5d  cmp     cs:dword_180070F40, ebx
0x180026c63  mov     [rsp+910h+plpszSubStringArray], r14
0x180026c68  jbe     loc_180026D29
0x180026c6e  mov     dword ptr [rsp+910h+lpcbData], r13d
0x180026c73  mov     edx, 2
0x180026c78  mov     r8d, 4E85h
0x180026c7e  jmp     loc_180026D0F
0x180026c83  mov     edi, 3F7h
0x180026c88  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180026c8f  mov     ebx, 1
0x180026c94  lea     r8, aType; "Type"
0x180026c9b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026ca1  movdqu  [rsp+910h+var_898], xmm0
0x180026ca7  mov     [rsp+910h+plpszSubStringArray], r8
0x180026cac  jz      short loc_180026CFA
0x180026cae  xor     eax, eax
0x180026cb0  lea     rdx, aCannotAccessRe; "Cannot access Registry value for %s."
0x180026cb7  lea     rcx, [rbp+810h+var_850]
0x180026cbb  mov     word ptr [rbp+810h+var_850], ax
0x180026cbf  mov     word ptr [rbp+810h+var_878], ax
0x180026cc3  call    FormatRRASErrorString
0x180026cc8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026cce  jz      short loc_180026CFA
0x180026cd0  lea     r9, [rsp+910h+var_898]
0x180026cd5  lea     rax, [rbp+810h+var_878]
0x180026cd9  mov     [rsp+910h+lpcbData], rax
0x180026cde  lea     r8, [rbp+810h+var_850]
0x180026ce2  lea     rdx, RasDimParamTraceAdminError
0x180026ce9  mov     [rsp+910h+lpData], rsi
0x180026cee  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026cf5  call    McTemplateU0zjzz_EventWriteTransfer
0x180026cfa  cmp     cs:dword_180070F40, 0
0x180026d01  jbe     short loc_180026D29
0x180026d03  mov     edx, ebx; dwEventType
0x180026d05  mov     dword ptr [rsp+910h+lpcbData], edi; dwErrorCode
0x180026d09  mov     r8d, 4E83h; dwMessageId
0x180026d0f  mov     rcx, cs:hLogHandle; hLogHandle
0x180026d16  lea     rax, [rsp+910h+plpszSubStringArray]
0x180026d1b  mov     r9d, ebx; dwSubStringCount
0x180026d1e  mov     [rsp+910h+lpData], rax; plpszSubStringArray
0x180026d23  call    cs:__imp_RouterLogEventW
0x180026d29  mov     eax, edi
0x180026d2b  mov     rcx, [rbp+810h+var_50]
0x180026d32  xor     rcx, rsp; StackCookie
0x180026d35  call    __security_check_cookie
0x180026d3a  add     rsp, 8D8h
0x180026d41  pop     r15
0x180026d43  pop     r14
0x180026d45  pop     r13
0x180026d47  pop     r12
0x180026d49  pop     rdi
0x180026d4a  pop     rsi
0x180026d4b  pop     rbx
0x180026d4c  pop     rbp
0x180026d4d  retn
```
