# DdmL2tpDevice::DdmIsIKESecureCheckDisabled(_DDM_S2S_DIALING_PARAMS &,int *)

- ea: `0x18004a61c`
- end: `0x18004ab24`
- name: `?DdmIsIKESecureCheckDisabled@DdmL2tpDevice@@AEAAKAEAU_DDM_S2S_DIALING_PARAMS@@PEAH@Z`
- size: `1288`
- prototype: `unsigned int __fastcall(DdmL2tpDevice *__hidden this, struct _DDM_S2S_DIALING_PARAMS *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a090`

## callees

- `0x180007c0c`
- `0x18004a61c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18004a899`
- `ADVAPI32!RegOpenKeyExW` at `0x18004a899`
- `ADVAPI32!RegQueryValueExW` at `0x18004a8e9`
- `ADVAPI32!RegQueryValueExW` at `0x18004a8e9`
- `ADVAPI32!RegCloseKey` at `0x18004aa64`
- `ADVAPI32!RegCloseKey` at `0x18004aa64`
- `ntdll!RtlIpv6StringToAddressW` at `0x18004a793`
- `ntdll!RtlIpv6StringToAddressW` at `0x18004a793`
- `ntdll!RtlIpv4StringToAddressW` at `0x18004a711`
- `ntdll!RtlIpv4StringToAddressW` at `0x18004a711`

## string_xrefs

- `0x18004a88b`: `System\CurrentControlSet\Services\rasman\parameters`
- `0x18004a6b0`: `DdmL2tpDevice::DdmIsIKESecureCheckDisabled: PSK connection - making the DisableIKESecurityCheck flag as TRUE`
- `0x18004a835`: `DdmL2tpDevice::DdmIsIKESecureCheckDisabled: Destination address is an IPAddress, Disable the IKESecurity Check`
- `0x18004a90b`: `DdmL2tpDevice::DdmIsIKESecureCheckDisabled: DisableIKESecurityCheck value as read from the registry is: %d`
- `0x18004aa02`: `DdmL2tpDevice::DdmIsIKESecureCheckDisabled: RegQueryValueEx for IKESecurityCheck failed with %d`
- `0x18004aa82`: `DdmL2tpDevice::DdmIsIKESecureCheckDisabled: RegOpenKeyEx for rasman\parameter failed with %d`

## pseudocode

```c
__int64 __fastcall DdmL2tpDevice::DdmIsIKESecureCheckDisabled(
        DdmL2tpDevice *this,
        struct _DDM_S2S_DIALING_PARAMS *a2,
        int *a3)
{
  __int64 v5; // r8
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // r8
  int v18; // eax
  int v19; // ecx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR Terminator; // [rsp+38h] [rbp-C8h] BYREF
  struct in_addr Addr; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct in6_addr v27; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v28[16]; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+84h] [rbp-7Ch]
  int v32; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  hKey = 0;
  Terminator = 0;
  v27.u.Byte[0] = 0;
  *(_QWORD *)&v27.u.Byte[1] = 0;
  *(_DWORD *)((char *)&v27.u.Word[4] + 1) = 0;
  *(USHORT *)((char *)&v27.u.Word[6] + 1) = 0;
  v27.u.Byte[15] = 0;
  Addr = 0;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  *a3 = 0;
  if ( (*((_BYTE *)a2 + 4068) & 0x10) != 0 )
  {
    *a3 = 1;
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v6 = -1;
      do
        ++v6;
      while ( aDdml2tpdeviceD[v6] );
      v29 = L"DdmL2tpDevice::DdmIsIKESecureCheckDisabled: PSK connection - making the DisableIKESecurityCheck flag as TRUE";
      v30 = 2 * v6 + 2;
      v31 = 0;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v5, 2, v28);
    }
    return 0;
  }
  v8 = -1;
  if ( RtlIpv4StringToAddressW((PCWSTR)a2 + 29, 1u, &Terminator, &Addr) || *Terminator )
  {
    Terminator = 0;
    if ( RtlIpv6StringToAddressW((PCWSTR)a2 + 29, &Terminator, &v27) || *Terminator )
    {
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        LOWORD(v32) = 0;
        FormatRRASErrorString(&v32, L"DdmIsIKESecureCheckDisabled: %ws is a NOT a IPADDRESS String", (char *)a2 + 58);
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)&v33[2 * v15 - 4] );
          v31 = 0;
          v30 = 2 * v15 + 2;
          v29 = (const wchar_t *)&v32;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v14, 2, v28);
        }
      }
      goto LABEL_24;
    }
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v32) = 0;
      FormatRRASErrorString(&v32, L"DdmIsIKESecureCheckDisabled: %ws is a valid IPV6 String", (char *)a2 + 58);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)&v33[2 * v9 - 4] );
        goto LABEL_19;
      }
    }
  }
  else if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v32, L"DdmIsIKESecureCheckDisabled: %ws is a valid IPV4 String", (char *)a2 + 58);
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)&v33[2 * v9 - 4] );
LABEL_19:
      v31 = 0;
      v30 = 2 * v9 + 2;
      v29 = (const wchar_t *)&v32;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v7, 2, v28);
    }
  }
  *a3 = 1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v10 = -1;
    do
      ++v10;
    while ( aDdml2tpdeviceD_0[v10] );
    v29 = L"DdmL2tpDevice::DdmIsIKESecureCheckDisabled: Destination address is an IPAddress, Disable the IKESecurity Check";
    v30 = 2 * v10 + 2;
    v31 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v7, 2, v28);
  }
LABEL_24:
  v11 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\rasman\\parameters",
          0,
          0x20019u,
          &hKey);
  if ( v11 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v32) = 0;
      FormatRRASErrorString(
        &v32,
        L"DdmL2tpDevice::DdmIsIKESecureCheckDisabled: RegOpenKeyEx for rasman\\parameter failed with %d",
        v11);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        do
          ++v8;
        while ( *(_WORD *)&v33[2 * v8 - 4] );
        v31 = 0;
        v30 = 2 * v8 + 2;
        v29 = (const wchar_t *)&v32;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v17, 2, v28);
      }
    }
  }
  else
  {
    Type = 0;
    *(_DWORD *)Data = 1;
    cbData = 4;
    v12 = RegQueryValueExW(hKey, L"DisableIKENameEkuCheck", 0, &Type, Data, &cbData);
    if ( v12 )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v32) = 0;
        FormatRRASErrorString(
          &v32,
          L"DdmL2tpDevice::DdmIsIKESecureCheckDisabled: RegQueryValueEx for IKESecurityCheck failed with %d",
          v12);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          do
            ++v8;
          while ( *(_WORD *)&v33[2 * v8 - 4] );
          v31 = 0;
          v30 = 2 * v8 + 2;
          v29 = (const wchar_t *)&v32;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v16, 2, v28);
        }
      }
    }
    else
    {
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        LOWORD(v32) = 0;
        FormatRRASErrorString(
          &v32,
          L"DdmL2tpDevice::DdmIsIKESecureCheckDisabled: DisableIKESecurityCheck value as read from the registry is: %d",
          *(unsigned int *)Data);
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          do
            ++v8;
          while ( *(_WORD *)&v33[2 * v8 - 4] );
          v31 = 0;
          v30 = 2 * v8 + 2;
          v29 = (const wchar_t *)&v32;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v13, 2, v28);
        }
      }
      *a3 = *(_DWORD *)Data == 1;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  v18 = *a3;
  if ( !*a3 )
  {
    v19 = *((_DWORD *)a2 + 2246);
    if ( v19 )
    {
      *a3 = v19;
      v18 = v19;
    }
  }
  *((_DWORD *)a2 + 2246) = v18;
  return 0;
}

```

## disassembly

```asm
0x18004a61c  mov     [rsp-8+arg_0], rbx
0x18004a621  mov     [rsp-8+arg_18], rsi
0x18004a626  push    rbp
0x18004a627  push    rdi
0x18004a628  push    r13
0x18004a62a  push    r14
0x18004a62c  push    r15
0x18004a62e  lea     rbp, [rsp-7A0h]
0x18004a636  sub     rsp, 8A0h
0x18004a63d  mov     rax, cs:__security_cookie
0x18004a644  xor     rax, rsp
0x18004a647  mov     [rbp+7C0h+var_30], rax
0x18004a64e  xor     edi, edi
0x18004a650  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18004a654  xor     eax, eax
0x18004a656  mov     [rsp+8C0h+hKey], rdi
0x18004a65b  mov     rsi, r8
0x18004a65e  mov     [rsp+8C0h+Terminator], rdi
0x18004a663  mov     r13, rdx
0x18004a666  mov     byte ptr [rsp+8C0h+var_868.u], dil
0x18004a66b  xor     edx, edx; Val
0x18004a66d  mov     qword ptr [rsp+8C0h+var_868.u+1], rax
0x18004a672  mov     r8d, 7FCh; Size
0x18004a678  mov     dword ptr [rsp+8C0h+var_868.u+9], eax
0x18004a67c  mov     word ptr [rsp+8C0h+var_868.u+0Dh], ax
0x18004a681  mov     byte ptr [rsp+8C0h+var_868.u+0Fh], al
0x18004a685  mov     dword ptr [rsp+8C0h+Addr.S_un], edi
0x18004a689  mov     [rbp+7C0h+var_830], edi
0x18004a68c  call    memset_0
0x18004a691  mov     [rsi], edi
0x18004a693  test    byte ptr [r13+0FE4h], 10h
0x18004a69b  jz      short loc_18004A6FE
0x18004a69d  mov     dword ptr [rsi], 1
0x18004a6a3  test    cs:byte_1800CF404, 10h
0x18004a6aa  jz      loc_18004AAF6
0x18004a6b0  lea     rcx, aDdml2tpdeviceD; "DdmL2tpDevice::DdmIsIKESecureCheckDisab"...
0x18004a6b7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004a6bb  inc     rbx
0x18004a6be  cmp     [rcx+rbx*2], di
0x18004a6c2  jnz     short loc_18004A6BB
0x18004a6c4  lea     eax, ds:2[rbx*2]
0x18004a6cb  mov     [rsp+8C0h+var_848], rcx
0x18004a6d0  mov     [rbp+7C0h+var_840], eax
0x18004a6d3  lea     rdx, RasDdmTraceInfo
0x18004a6da  lea     rax, [rsp+8C0h+var_858]
0x18004a6df  mov     [rbp+7C0h+var_83C], edi
0x18004a6e2  mov     r9d, 2
0x18004a6e8  mov     [rsp+8C0h+phkResult], rax
0x18004a6ed  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004a6f4  call    McGenEventWrite_EventWriteTransfer
0x18004a6f9  jmp     loc_18004AAF6
0x18004a6fe  lea     rdi, [r13+3Ah]
0x18004a702  mov     dl, 1; Strict
0x18004a704  mov     rcx, rdi; S
0x18004a707  lea     r9, [rsp+8C0h+Addr]; Addr
0x18004a70c  lea     r8, [rsp+8C0h+Terminator]; Terminator
0x18004a711  call    cs:__imp_RtlIpv4StringToAddressW
0x18004a718  nop     dword ptr [rax+rax+00h]
0x18004a71d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004a721  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004a728  xor     ecx, ecx
0x18004a72a  lea     r14d, [rbx+3]
0x18004a72e  test    eax, eax
0x18004a730  jnz     short loc_18004A781
0x18004a732  mov     rax, [rsp+8C0h+Terminator]
0x18004a737  cmp     [rax], cx
0x18004a73a  jnz     short loc_18004A781
0x18004a73c  test    cs:byte_1800CF404, 10h
0x18004a743  jz      loc_18004A826
0x18004a749  mov     word ptr [rbp+7C0h+var_830], cx
0x18004a74d  lea     rdx, aDdmisikesecure_0; "DdmIsIKESecureCheckDisabled: %ws is a v"...
0x18004a754  lea     rcx, [rbp+7C0h+var_830]
0x18004a758  mov     r8, rdi
0x18004a75b  call    FormatRRASErrorString
0x18004a760  test    cs:byte_1800CF404, 10h
0x18004a767  jz      loc_18004A824
0x18004a76d  lea     rcx, [rbp+7C0h+var_830]
0x18004a771  mov     rax, rbx
0x18004a774  xor     edx, edx
0x18004a776  inc     rax
0x18004a779  cmp     [rcx+rax*2], dx
0x18004a77d  jnz     short loc_18004A776
0x18004a77f  jmp     short loc_18004A7F2
0x18004a781  mov     [rsp+8C0h+Terminator], rcx
0x18004a786  lea     r8, [rsp+8C0h+var_868]; Addr
0x18004a78b  mov     rcx, rdi; S
0x18004a78e  lea     rdx, [rsp+8C0h+Terminator]; Terminator
0x18004a793  call    cs:__imp_RtlIpv6StringToAddressW
0x18004a79a  nop     dword ptr [rax+rax+00h]
0x18004a79f  xor     ecx, ecx
0x18004a7a1  test    eax, eax
0x18004a7a3  jnz     loc_18004A978
0x18004a7a9  mov     rax, [rsp+8C0h+Terminator]
0x18004a7ae  cmp     [rax], cx
0x18004a7b1  jnz     loc_18004A978
0x18004a7b7  test    cs:byte_1800CF404, 10h
0x18004a7be  jz      short loc_18004A826
0x18004a7c0  mov     word ptr [rbp+7C0h+var_830], cx
0x18004a7c4  lea     rdx, aDdmisikesecure_1; "DdmIsIKESecureCheckDisabled: %ws is a v"...
0x18004a7cb  lea     rcx, [rbp+7C0h+var_830]
0x18004a7cf  mov     r8, rdi
0x18004a7d2  call    FormatRRASErrorString
0x18004a7d7  test    cs:byte_1800CF404, 10h
0x18004a7de  jz      short loc_18004A824
0x18004a7e0  lea     rcx, [rbp+7C0h+var_830]
0x18004a7e4  mov     rax, rbx
0x18004a7e7  xor     edx, edx
0x18004a7e9  inc     rax
0x18004a7ec  cmp     [rcx+rax*2], dx
0x18004a7f0  jnz     short loc_18004A7E9
0x18004a7f2  lea     eax, ds:2[rax*2]
0x18004a7f9  mov     [rbp+7C0h+var_83C], edx
0x18004a7fc  lea     rcx, [rbp+7C0h+var_830]
0x18004a800  mov     [rbp+7C0h+var_840], eax
0x18004a803  lea     rax, [rsp+8C0h+var_858]
0x18004a808  mov     [rsp+8C0h+var_848], rcx
0x18004a80d  mov     r9d, r14d
0x18004a810  mov     [rsp+8C0h+phkResult], rax
0x18004a815  lea     rdx, RasDdmTraceInfo
0x18004a81c  mov     rcx, r15
0x18004a81f  call    McGenEventWrite_EventWriteTransfer
0x18004a824  xor     ecx, ecx
0x18004a826  mov     dword ptr [rsi], 1
0x18004a82c  test    cs:byte_1800CF404, 10h
0x18004a833  jz      short loc_18004A876
0x18004a835  lea     rdx, aDdml2tpdeviceD_0; "DdmL2tpDevice::DdmIsIKESecureCheckDisab"...
0x18004a83c  mov     rax, rbx
0x18004a83f  inc     rax
0x18004a842  cmp     [rdx+rax*2], cx
0x18004a846  jnz     short loc_18004A83F
0x18004a848  lea     eax, ds:2[rax*2]
0x18004a84f  mov     [rsp+8C0h+var_848], rdx
0x18004a854  mov     [rbp+7C0h+var_840], eax
0x18004a857  lea     rdx, RasDdmTraceInfo
0x18004a85e  lea     rax, [rsp+8C0h+var_858]
0x18004a863  mov     [rbp+7C0h+var_83C], ecx
0x18004a866  mov     r9d, r14d
0x18004a869  mov     [rsp+8C0h+phkResult], rax
0x18004a86e  mov     rcx, r15
0x18004a871  call    McGenEventWrite_EventWriteTransfer
0x18004a876  xor     edi, edi
0x18004a878  lea     rax, [rsp+8C0h+hKey]
0x18004a87d  mov     r9d, 20019h; samDesired
0x18004a883  xor     r8d, r8d; ulOptions
0x18004a886  mov     [rsp+8C0h+phkResult], rax; phkResult
0x18004a88b  lea     rdx, aSystemCurrentc_27; "System\\CurrentControlSet\\Services\\ra"...
0x18004a892  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a899  call    cs:__imp_RegOpenKeyExW
0x18004a8a0  nop     dword ptr [rax+rax+00h]
0x18004a8a5  test    eax, eax
0x18004a8a7  jnz     loc_18004AA72
0x18004a8ad  mov     rcx, [rsp+8C0h+hKey]; hKey
0x18004a8b2  lea     rax, [rsp+8C0h+cbData]
0x18004a8b7  mov     [rsp+8C0h+lpcbData], rax; lpcbData
0x18004a8bc  lea     r9, [rsp+8C0h+Type]; lpType
0x18004a8c1  lea     rax, [rsp+8C0h+Data]
0x18004a8c6  mov     [rsp+8C0h+Type], edi
0x18004a8ca  xor     r8d, r8d; lpReserved
0x18004a8cd  mov     [rsp+8C0h+phkResult], rax; lpData
0x18004a8d2  lea     rdx, aDisableikename; "DisableIKENameEkuCheck"
0x18004a8d9  mov     dword ptr [rsp+8C0h+Data], 1
0x18004a8e1  mov     [rsp+8C0h+cbData], 4
0x18004a8e9  call    cs:__imp_RegQueryValueExW
0x18004a8f0  nop     dword ptr [rax+rax+00h]
0x18004a8f5  test    eax, eax
0x18004a8f7  jnz     loc_18004A9F2
0x18004a8fd  test    cs:byte_1800CF404, 10h
0x18004a904  jz      short loc_18004A967
0x18004a906  mov     r8d, dword ptr [rsp+8C0h+Data]
0x18004a90b  lea     rdx, aDdml2tpdeviceD_6; "DdmL2tpDevice::DdmIsIKESecureCheckDisab"...
0x18004a912  lea     rcx, [rbp+7C0h+var_830]
0x18004a916  mov     word ptr [rbp+7C0h+var_830], di
0x18004a91a  call    FormatRRASErrorString
0x18004a91f  test    cs:byte_1800CF404, 10h
0x18004a926  jz      short loc_18004A967
0x18004a928  lea     rax, [rbp+7C0h+var_830]
0x18004a92c  inc     rbx
0x18004a92f  cmp     [rax+rbx*2], di
0x18004a933  jnz     short loc_18004A92C
0x18004a935  lea     eax, ds:2[rbx*2]
0x18004a93c  mov     [rbp+7C0h+var_83C], edi
0x18004a93f  lea     rcx, [rbp+7C0h+var_830]
0x18004a943  mov     [rbp+7C0h+var_840], eax
0x18004a946  lea     rax, [rsp+8C0h+var_858]
0x18004a94b  mov     [rsp+8C0h+var_848], rcx
0x18004a950  mov     r9d, r14d
0x18004a953  mov     [rsp+8C0h+phkResult], rax
0x18004a958  lea     rdx, RasDdmTraceInfo
0x18004a95f  mov     rcx, r15
0x18004a962  call    McGenEventWrite_EventWriteTransfer
0x18004a967  cmp     dword ptr [rsp+8C0h+Data], 1
0x18004a96c  mov     eax, edi
0x18004a96e  setz    al
0x18004a971  mov     [rsi], eax
0x18004a973  jmp     loc_18004AA5A
0x18004a978  test    cs:byte_1800CF404, 10h
0x18004a97f  jz      loc_18004A876
0x18004a985  mov     word ptr [rbp+7C0h+var_830], cx
0x18004a989  lea     rdx, aDdmisikesecure; "DdmIsIKESecureCheckDisabled: %ws is a N"...
0x18004a990  lea     rcx, [rbp+7C0h+var_830]
0x18004a994  mov     r8, rdi
0x18004a997  call    FormatRRASErrorString
0x18004a99c  xor     edi, edi
0x18004a99e  test    cs:byte_1800CF404, 10h
0x18004a9a5  jz      loc_18004A878
0x18004a9ab  lea     rcx, [rbp+7C0h+var_830]
0x18004a9af  mov     rax, rbx
0x18004a9b2  inc     rax
0x18004a9b5  cmp     [rcx+rax*2], di
0x18004a9b9  jnz     short loc_18004A9B2
0x18004a9bb  lea     eax, ds:2[rax*2]
0x18004a9c2  mov     [rbp+7C0h+var_83C], edi
0x18004a9c5  lea     rcx, [rbp+7C0h+var_830]
0x18004a9c9  mov     [rbp+7C0h+var_840], eax
0x18004a9cc  lea     rax, [rsp+8C0h+var_858]
0x18004a9d1  mov     [rsp+8C0h+var_848], rcx
0x18004a9d6  mov     r9d, r14d
0x18004a9d9  mov     [rsp+8C0h+phkResult], rax
0x18004a9de  lea     rdx, RasDdmTraceInfo
0x18004a9e5  mov     rcx, r15
0x18004a9e8  call    McGenEventWrite_EventWriteTransfer
0x18004a9ed  jmp     loc_18004A878
0x18004a9f2  test    cs:byte_1800CF404, 8
0x18004a9f9  jz      short loc_18004AA5A
0x18004a9fb  mov     r8d, eax
0x18004a9fe  mov     word ptr [rbp+7C0h+var_830], di
0x18004aa02  lea     rdx, aDdml2tpdeviceD_5; "DdmL2tpDevice::DdmIsIKESecureCheckDisab"...
0x18004aa09  lea     rcx, [rbp+7C0h+var_830]
0x18004aa0d  call    FormatRRASErrorString
0x18004aa12  test    cs:byte_1800CF404, 8
0x18004aa19  jz      short loc_18004AA5A
0x18004aa1b  lea     rax, [rbp+7C0h+var_830]
0x18004aa1f  inc     rbx
0x18004aa22  cmp     [rax+rbx*2], di
0x18004aa26  jnz     short loc_18004AA1F
0x18004aa28  lea     eax, ds:2[rbx*2]
0x18004aa2f  mov     [rbp+7C0h+var_83C], edi
0x18004aa32  lea     rcx, [rbp+7C0h+var_830]
0x18004aa36  mov     [rbp+7C0h+var_840], eax
0x18004aa39  lea     rax, [rsp+8C0h+var_858]
0x18004aa3e  mov     [rsp+8C0h+var_848], rcx
0x18004aa43  mov     r9d, r14d
0x18004aa46  mov     [rsp+8C0h+phkResult], rax
0x18004aa4b  lea     rdx, RasDdmTraceError
0x18004aa52  mov     rcx, r15
0x18004aa55  call    McGenEventWrite_EventWriteTransfer
0x18004aa5a  mov     rcx, [rsp+8C0h+hKey]; hKey
0x18004aa5f  test    rcx, rcx
0x18004aa62  jz      short loc_18004AADA
0x18004aa64  call    cs:__imp_RegCloseKey
0x18004aa6b  nop     dword ptr [rax+rax+00h]
0x18004aa70  jmp     short loc_18004AADA
0x18004aa72  test    cs:byte_1800CF404, 8
0x18004aa79  jz      short loc_18004AADA
0x18004aa7b  mov     r8d, eax
0x18004aa7e  mov     word ptr [rbp+7C0h+var_830], di
0x18004aa82  lea     rdx, aDdml2tpdeviceD_3; "DdmL2tpDevice::DdmIsIKESecureCheckDisab"...
0x18004aa89  lea     rcx, [rbp+7C0h+var_830]
0x18004aa8d  call    FormatRRASErrorString
0x18004aa92  test    cs:byte_1800CF404, 8
0x18004aa99  jz      short loc_18004AADA
0x18004aa9b  lea     rax, [rbp+7C0h+var_830]
0x18004aa9f  inc     rbx
0x18004aaa2  cmp     [rax+rbx*2], di
0x18004aaa6  jnz     short loc_18004AA9F
0x18004aaa8  lea     eax, ds:2[rbx*2]
0x18004aaaf  mov     [rbp+7C0h+var_83C], edi
0x18004aab2  lea     rcx, [rbp+7C0h+var_830]
0x18004aab6  mov     [rbp+7C0h+var_840], eax
0x18004aab9  lea     rax, [rsp+8C0h+var_858]
0x18004aabe  mov     [rsp+8C0h+var_848], rcx
0x18004aac3  mov     r9d, r14d
0x18004aac6  mov     [rsp+8C0h+phkResult], rax
0x18004aacb  lea     rdx, RasDdmTraceError
0x18004aad2  mov     rcx, r15
0x18004aad5  call    McGenEventWrite_EventWriteTransfer
0x18004aada  mov     eax, [rsi]
0x18004aadc  test    eax, eax
0x18004aade  jnz     short loc_18004AAEF
0x18004aae0  mov     ecx, [r13+2318h]
0x18004aae7  test    ecx, ecx
0x18004aae9  jz      short loc_18004AAEF
0x18004aaeb  mov     [rsi], ecx
0x18004aaed  mov     eax, ecx
0x18004aaef  mov     [r13+2318h], eax
0x18004aaf6  xor     eax, eax
0x18004aaf8  mov     rcx, [rbp+7C0h+var_30]
0x18004aaff  xor     rcx, rsp; StackCookie
0x18004ab02  call    __security_check_cookie
0x18004ab07  lea     r11, [rsp+8C0h+var_20]
0x18004ab0f  mov     rbx, [r11+30h]
0x18004ab13  mov     rsi, [r11+48h]
0x18004ab17  mov     rsp, r11
0x18004ab1a  pop     r15
0x18004ab1c  pop     r14
0x18004ab1e  pop     r13
0x18004ab20  pop     rdi
0x18004ab21  pop     rbp
0x18004ab22  retn
```
