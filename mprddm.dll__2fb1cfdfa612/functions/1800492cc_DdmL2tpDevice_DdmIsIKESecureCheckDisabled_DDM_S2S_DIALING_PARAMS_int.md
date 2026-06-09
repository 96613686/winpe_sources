# DdmL2tpDevice::DdmIsIKESecureCheckDisabled(_DDM_S2S_DIALING_PARAMS &,int *)

- ea: `0x1800492cc`
- end: `0x18004979f`
- name: `?DdmIsIKESecureCheckDisabled@DdmL2tpDevice@@AEAAKAEAU_DDM_S2S_DIALING_PARAMS@@PEAH@Z`
- size: `1235`
- prototype: `unsigned int __fastcall(DdmL2tpDevice *__hidden this, struct _DDM_S2S_DIALING_PARAMS *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180048d88`

## callees

- `0x180007b7c`
- `0x1800492cc`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180049520`
- `ADVAPI32!RegOpenKeyExW` at `0x180049520`
- `ADVAPI32!RegQueryValueExW` at `0x18004956d`
- `ADVAPI32!RegQueryValueExW` at `0x18004956d`
- `ADVAPI32!RegCloseKey` at `0x1800496e8`
- `ADVAPI32!RegCloseKey` at `0x1800496e8`
- `ntdll!RtlIpv6StringToAddressW` at `0x18004942b`
- `ntdll!RtlIpv6StringToAddressW` at `0x18004942b`
- `ntdll!RtlIpv4StringToAddressW` at `0x1800493ad`
- `ntdll!RtlIpv4StringToAddressW` at `0x1800493ad`

## string_xrefs

- `0x180049512`: `System\CurrentControlSet\Services\rasman\parameters`
- `0x18004935f`: `DdmL2tpDevice::DdmIsIKESecureCheckDisabled: PSK connection - making the DisableIKESecurityCheck flag as TRUE`
- `0x1800494cc`: `DdmL2tpDevice::DdmIsIKESecureCheckDisabled: Destination address is an IPAddress, Disable the IKESecurity Check`
- `0x18004958c`: `DdmL2tpDevice::DdmIsIKESecureCheckDisabled: DisableIKESecurityCheck value as read from the registry is: %d`
- `0x180049680`: `DdmL2tpDevice::DdmIsIKESecureCheckDisabled: RegQueryValueEx for IKESecurityCheck failed with %d`
- `0x1800496f9`: `DdmL2tpDevice::DdmIsIKESecureCheckDisabled: RegOpenKeyEx for rasman\parameter failed with %d`

## pseudocode

```c
__int64 __fastcall DdmL2tpDevice::DdmIsIKESecureCheckDisabled(
        DdmL2tpDevice *this,
        struct _DDM_S2S_DIALING_PARAMS *a2,
        int *a3)
{
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // rbx
  __int64 v8; // rax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // r8
  int v16; // eax
  int *v17; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  LPCWSTR Terminator; // [rsp+38h] [rbp-C8h] BYREF
  struct in_addr Addr; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct in6_addr v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[16]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  int v29; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  hKey = 0;
  Terminator = 0;
  v25.u.Byte[0] = 0;
  *(_QWORD *)&v25.u.Byte[1] = 0;
  *(_DWORD *)((char *)&v25.u.Word[4] + 1) = 0;
  *(USHORT *)((char *)&v25.u.Word[6] + 1) = 0;
  v25.u.Byte[15] = 0;
  Addr = 0;
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  *a3 = 0;
  if ( (*((_BYTE *)a2 + 4068) & 0x10) != 0 )
  {
    *a3 = 1;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v28 = 218;
      v27 = L"DdmL2tpDevice::DdmIsIKESecureCheckDisabled: PSK connection - making the DisableIKESecurityCheck flag as TRUE";
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v5, 2, v26);
    }
    return 0;
  }
  v7 = -1;
  if ( RtlIpv4StringToAddressW((PCWSTR)a2 + 29, 1u, &Terminator, &Addr) || *Terminator )
  {
    Terminator = 0;
    if ( RtlIpv6StringToAddressW((PCWSTR)a2 + 29, &Terminator, &v25) || *Terminator )
    {
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v29) = 0;
        FormatRRASErrorString(&v29, L"DdmIsIKESecureCheckDisabled: %ws is a NOT a IPADDRESS String", (char *)a2 + 58);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&v30[2 * v13 - 4] );
          v28 = (unsigned int)(2 * v13 + 2);
          v27 = (const wchar_t *)&v29;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v12, 2, v26);
        }
      }
      goto LABEL_20;
    }
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, L"DdmIsIKESecureCheckDisabled: %ws is a valid IPV6 String", (char *)a2 + 58);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v8 = -1;
        do
          ++v8;
        while ( *(_WORD *)&v30[2 * v8 - 4] );
        goto LABEL_17;
      }
    }
  }
  else if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v29) = 0;
    FormatRRASErrorString(&v29, L"DdmIsIKESecureCheckDisabled: %ws is a valid IPV4 String", (char *)a2 + 58);
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&v30[2 * v8 - 4] );
LABEL_17:
      v28 = (unsigned int)(2 * v8 + 2);
      v27 = (const wchar_t *)&v29;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v6, 2, v26);
    }
  }
  *a3 = 1;
  LOBYTE(Type) = byte_1800C8404 & 0x10;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v28 = 222;
    v27 = L"DdmL2tpDevice::DdmIsIKESecureCheckDisabled: Destination address is an IPAddress, Disable the IKESecurity Check";
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v6, 2, v26);
  }
LABEL_20:
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\rasman\\parameters", 0, 0x20019u, &hKey);
  if ( v9 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v29) = 0;
      FormatRRASErrorString(
        &v29,
        L"DdmL2tpDevice::DdmIsIKESecureCheckDisabled: RegOpenKeyEx for rasman\\parameter failed with %d",
        v9);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        do
          ++v7;
        while ( *(_WORD *)&v30[2 * v7 - 4] );
        v28 = (unsigned int)(2 * v7 + 2);
        v27 = (const wchar_t *)&v29;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v15, 2, v26);
      }
    }
  }
  else
  {
    Type = 0;
    *(_DWORD *)Data = 1;
    cbData = 4;
    v10 = RegQueryValueExW(hKey, L"DisableIKENameEkuCheck", 0, &Type, Data, &cbData);
    if ( v10 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v29) = 0;
        FormatRRASErrorString(
          &v29,
          L"DdmL2tpDevice::DdmIsIKESecureCheckDisabled: RegQueryValueEx for IKESecurityCheck failed with %d",
          v10);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          do
            ++v7;
          while ( *(_WORD *)&v30[2 * v7 - 4] );
          v28 = (unsigned int)(2 * v7 + 2);
          v27 = (const wchar_t *)&v29;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v14, 2, v26);
        }
      }
    }
    else
    {
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v29) = 0;
        FormatRRASErrorString(
          &v29,
          L"DdmL2tpDevice::DdmIsIKESecureCheckDisabled: DisableIKESecurityCheck value as read from the registry is: %d",
          *(unsigned int *)Data);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          do
            ++v7;
          while ( *(_WORD *)&v30[2 * v7 - 4] );
          v28 = (unsigned int)(2 * v7 + 2);
          v27 = (const wchar_t *)&v29;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v11, 2, v26);
        }
      }
      *a3 = *(_DWORD *)Data == 1;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  v16 = *a3;
  v17 = (int *)((char *)a2 + 8984);
  if ( !*a3 )
  {
    v16 = *v17;
    if ( *v17 )
      *a3 = v16;
    else
      v16 = 0;
  }
  *v17 = v16;
  return 0;
}

```

## disassembly

```asm
0x1800492cc  mov     [rsp-8+arg_0], rbx
0x1800492d1  mov     [rsp-8+arg_18], rsi
0x1800492d6  push    rbp
0x1800492d7  push    rdi
0x1800492d8  push    r13
0x1800492da  push    r14
0x1800492dc  push    r15
0x1800492de  lea     rbp, [rsp-790h]
0x1800492e6  sub     rsp, 890h
0x1800492ed  mov     rax, cs:__security_cookie
0x1800492f4  xor     rax, rsp
0x1800492f7  mov     [rbp+7B0h+var_30], rax
0x1800492fe  xor     ebx, ebx
0x180049300  lea     rcx, [rbp+7B0h+var_82C]; void *
0x180049304  xor     eax, eax
0x180049306  mov     [rsp+8B0h+hKey], rbx
0x18004930b  mov     rsi, r8
0x18004930e  mov     [rsp+8B0h+Terminator], rbx
0x180049313  mov     r13, rdx
0x180049316  mov     byte ptr [rsp+8B0h+var_860.u], bl
0x18004931a  xor     edx, edx; Val
0x18004931c  mov     qword ptr [rsp+8B0h+var_860.u+1], rax
0x180049321  mov     r8d, 7FCh; Size
0x180049327  mov     dword ptr [rsp+8B0h+var_860.u+9], eax
0x18004932b  mov     word ptr [rsp+8B0h+var_860.u+0Dh], ax
0x180049330  mov     byte ptr [rsp+8B0h+var_860.u+0Fh], al
0x180049334  mov     dword ptr [rsp+8B0h+Addr.S_un], ebx
0x180049338  mov     [rbp+7B0h+var_830], ebx
0x18004933b  call    memset_0
0x180049340  mov     [rsi], ebx
0x180049342  test    byte ptr [r13+0FE4h], 10h
0x18004934a  jz      short loc_18004939A
0x18004934c  mov     dword ptr [rsi], 1
0x180049352  test    cs:byte_1800C8404, 10h
0x180049359  jz      loc_180049772
0x18004935f  lea     rax, aDdml2tpdeviceD; "DdmL2tpDevice::DdmIsIKESecureCheckDisab"...
0x180049366  mov     [rsp+8B0h+var_838], 0DAh
0x18004936f  mov     [rsp+8B0h+var_840], rax
0x180049374  lea     r9d, [rbx+2]
0x180049378  lea     rax, [rsp+8B0h+var_850]
0x18004937d  lea     rdx, RasDdmTraceInfo
0x180049384  mov     [rsp+8B0h+phkResult], rax
0x180049389  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049390  call    McGenEventWrite_EventWriteTransfer
0x180049395  jmp     loc_180049772
0x18004939a  lea     rdi, [r13+3Ah]
0x18004939e  mov     dl, 1; Strict
0x1800493a0  mov     rcx, rdi; S
0x1800493a3  lea     r9, [rsp+8B0h+Addr]; Addr
0x1800493a8  lea     r8, [rsp+8B0h+Terminator]; Terminator
0x1800493ad  call    cs:__imp_RtlIpv4StringToAddressW
0x1800493b3  xor     ecx, ecx
0x1800493b5  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800493bc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800493c0  mov     r14d, 2
0x1800493c6  test    eax, eax
0x1800493c8  jnz     short loc_180049419
0x1800493ca  mov     rax, [rsp+8B0h+Terminator]
0x1800493cf  cmp     [rax], cx
0x1800493d2  jnz     short loc_180049419
0x1800493d4  test    cs:byte_1800C8404, 10h
0x1800493db  jz      loc_1800494B8
0x1800493e1  mov     word ptr [rbp+7B0h+var_830], cx
0x1800493e5  lea     rdx, aDdmisikesecure_0; "DdmIsIKESecureCheckDisabled: %ws is a v"...
0x1800493ec  lea     rcx, [rbp+7B0h+var_830]
0x1800493f0  mov     r8, rdi
0x1800493f3  call    FormatRRASErrorString
0x1800493f8  test    cs:byte_1800C8404, 10h
0x1800493ff  jz      loc_1800494B8
0x180049405  lea     rcx, [rbp+7B0h+var_830]
0x180049409  mov     rax, rbx
0x18004940c  xor     edx, edx
0x18004940e  inc     rax
0x180049411  cmp     [rcx+rax*2], dx
0x180049415  jnz     short loc_18004940E
0x180049417  jmp     short loc_180049484
0x180049419  mov     [rsp+8B0h+Terminator], rcx
0x18004941e  lea     r8, [rsp+8B0h+var_860]; Addr
0x180049423  mov     rcx, rdi; S
0x180049426  lea     rdx, [rsp+8B0h+Terminator]; Terminator
0x18004942b  call    cs:__imp_RtlIpv6StringToAddressW
0x180049431  xor     ecx, ecx
0x180049433  test    eax, eax
0x180049435  jnz     loc_1800495FB
0x18004943b  mov     rax, [rsp+8B0h+Terminator]
0x180049440  cmp     [rax], cx
0x180049443  jnz     loc_1800495FB
0x180049449  test    cs:byte_1800C8404, 10h
0x180049450  jz      short loc_1800494B8
0x180049452  mov     word ptr [rbp+7B0h+var_830], cx
0x180049456  lea     rdx, aDdmisikesecure_1; "DdmIsIKESecureCheckDisabled: %ws is a v"...
0x18004945d  lea     rcx, [rbp+7B0h+var_830]
0x180049461  mov     r8, rdi
0x180049464  call    FormatRRASErrorString
0x180049469  test    cs:byte_1800C8404, 10h
0x180049470  jz      short loc_1800494B8
0x180049472  lea     rcx, [rbp+7B0h+var_830]
0x180049476  mov     rax, rbx
0x180049479  xor     edx, edx
0x18004947b  inc     rax
0x18004947e  cmp     [rcx+rax*2], dx
0x180049482  jnz     short loc_18004947B
0x180049484  lea     eax, ds:2[rax*2]
0x18004948b  mov     dword ptr [rsp+8B0h+var_838+4], edx
0x18004948f  lea     rcx, [rbp+7B0h+var_830]
0x180049493  mov     dword ptr [rsp+8B0h+var_838], eax
0x180049497  lea     rax, [rsp+8B0h+var_850]
0x18004949c  mov     [rsp+8B0h+var_840], rcx
0x1800494a1  mov     r9d, r14d
0x1800494a4  mov     [rsp+8B0h+phkResult], rax
0x1800494a9  lea     rdx, RasDdmTraceInfo
0x1800494b0  mov     rcx, r15
0x1800494b3  call    McGenEventWrite_EventWriteTransfer
0x1800494b8  mov     dword ptr [rsi], 1
0x1800494be  mov     al, cs:byte_1800C8404
0x1800494c4  and     al, 10h
0x1800494c6  mov     byte ptr [rsp+8B0h+Type], al
0x1800494ca  jz      short loc_1800494FD
0x1800494cc  lea     rax, aDdml2tpdeviceD_0; "DdmL2tpDevice::DdmIsIKESecureCheckDisab"...
0x1800494d3  mov     [rsp+8B0h+var_838], 0DEh
0x1800494dc  mov     [rsp+8B0h+var_840], rax
0x1800494e1  lea     rdx, RasDdmTraceInfo
0x1800494e8  lea     rax, [rsp+8B0h+var_850]
0x1800494ed  mov     r9d, r14d
0x1800494f0  mov     rcx, r15
0x1800494f3  mov     [rsp+8B0h+phkResult], rax
0x1800494f8  call    McGenEventWrite_EventWriteTransfer
0x1800494fd  xor     edi, edi
0x1800494ff  lea     rax, [rsp+8B0h+hKey]
0x180049504  mov     r9d, 20019h; samDesired
0x18004950a  xor     r8d, r8d; ulOptions
0x18004950d  mov     [rsp+8B0h+phkResult], rax; phkResult
0x180049512  lea     rdx, aSystemCurrentc_27; "System\\CurrentControlSet\\Services\\ra"...
0x180049519  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049520  call    cs:__imp_RegOpenKeyExW
0x180049526  mov     r8d, eax
0x180049529  test    eax, eax
0x18004952b  jnz     loc_1800496F0
0x180049531  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180049536  lea     rax, [rsp+8B0h+cbData]
0x18004953b  mov     [rsp+8B0h+lpcbData], rax; lpcbData
0x180049540  lea     r9, [rsp+8B0h+Type]; lpType
0x180049545  lea     rax, [rsp+8B0h+Data]
0x18004954a  mov     [rsp+8B0h+Type], edi
0x18004954e  xor     r8d, r8d; lpReserved
0x180049551  mov     [rsp+8B0h+phkResult], rax; lpData
0x180049556  lea     rdx, aDisableikename; "DisableIKENameEkuCheck"
0x18004955d  mov     dword ptr [rsp+8B0h+Data], 1
0x180049565  mov     [rsp+8B0h+cbData], 4
0x18004956d  call    cs:__imp_RegQueryValueExW
0x180049573  mov     r8d, eax
0x180049576  test    eax, eax
0x180049578  jnz     loc_180049677
0x18004957e  test    cs:byte_1800C8404, 10h
0x180049585  jz      short loc_1800495EA
0x180049587  mov     r8d, dword ptr [rsp+8B0h+Data]
0x18004958c  lea     rdx, aDdml2tpdeviceD_6; "DdmL2tpDevice::DdmIsIKESecureCheckDisab"...
0x180049593  lea     rcx, [rbp+7B0h+var_830]
0x180049597  mov     word ptr [rbp+7B0h+var_830], di
0x18004959b  call    FormatRRASErrorString
0x1800495a0  test    cs:byte_1800C8404, 10h
0x1800495a7  jz      short loc_1800495EA
0x1800495a9  lea     rax, [rbp+7B0h+var_830]
0x1800495ad  inc     rbx
0x1800495b0  cmp     [rax+rbx*2], di
0x1800495b4  jnz     short loc_1800495AD
0x1800495b6  lea     eax, ds:2[rbx*2]
0x1800495bd  mov     dword ptr [rsp+8B0h+var_838+4], edi
0x1800495c1  lea     rcx, [rbp+7B0h+var_830]
0x1800495c5  mov     dword ptr [rsp+8B0h+var_838], eax
0x1800495c9  lea     rax, [rsp+8B0h+var_850]
0x1800495ce  mov     [rsp+8B0h+var_840], rcx
0x1800495d3  mov     r9d, r14d
0x1800495d6  mov     [rsp+8B0h+phkResult], rax
0x1800495db  lea     rdx, RasDdmTraceInfo
0x1800495e2  mov     rcx, r15
0x1800495e5  call    McGenEventWrite_EventWriteTransfer
0x1800495ea  cmp     dword ptr [rsp+8B0h+Data], 1
0x1800495ef  mov     eax, edi
0x1800495f1  setz    al
0x1800495f4  mov     [rsi], eax
0x1800495f6  jmp     loc_1800496DE
0x1800495fb  test    cs:byte_1800C8404, 10h
0x180049602  jz      loc_1800494FD
0x180049608  mov     word ptr [rbp+7B0h+var_830], cx
0x18004960c  lea     rdx, aDdmisikesecure; "DdmIsIKESecureCheckDisabled: %ws is a N"...
0x180049613  lea     rcx, [rbp+7B0h+var_830]
0x180049617  mov     r8, rdi
0x18004961a  call    FormatRRASErrorString
0x18004961f  xor     edi, edi
0x180049621  test    cs:byte_1800C8404, 10h
0x180049628  jz      loc_1800494FF
0x18004962e  lea     rcx, [rbp+7B0h+var_830]
0x180049632  mov     rax, rbx
0x180049635  inc     rax
0x180049638  cmp     [rcx+rax*2], di
0x18004963c  jnz     short loc_180049635
0x18004963e  lea     eax, ds:2[rax*2]
0x180049645  mov     dword ptr [rsp+8B0h+var_838+4], edi
0x180049649  lea     rcx, [rbp+7B0h+var_830]
0x18004964d  mov     dword ptr [rsp+8B0h+var_838], eax
0x180049651  lea     rax, [rsp+8B0h+var_850]
0x180049656  mov     [rsp+8B0h+var_840], rcx
0x18004965b  mov     r9d, r14d
0x18004965e  mov     [rsp+8B0h+phkResult], rax
0x180049663  lea     rdx, RasDdmTraceInfo
0x18004966a  mov     rcx, r15
0x18004966d  call    McGenEventWrite_EventWriteTransfer
0x180049672  jmp     loc_1800494FF
0x180049677  test    cs:byte_1800C8404, 8
0x18004967e  jz      short loc_1800496DE
0x180049680  lea     rdx, aDdml2tpdeviceD_5; "DdmL2tpDevice::DdmIsIKESecureCheckDisab"...
0x180049687  mov     word ptr [rbp+7B0h+var_830], di
0x18004968b  lea     rcx, [rbp+7B0h+var_830]
0x18004968f  call    FormatRRASErrorString
0x180049694  test    cs:byte_1800C8404, 8
0x18004969b  jz      short loc_1800496DE
0x18004969d  lea     rax, [rbp+7B0h+var_830]
0x1800496a1  inc     rbx
0x1800496a4  cmp     [rax+rbx*2], di
0x1800496a8  jnz     short loc_1800496A1
0x1800496aa  lea     eax, ds:2[rbx*2]
0x1800496b1  mov     dword ptr [rsp+8B0h+var_838+4], edi
0x1800496b5  lea     rcx, [rbp+7B0h+var_830]
0x1800496b9  mov     dword ptr [rsp+8B0h+var_838], eax
0x1800496bd  lea     rax, [rsp+8B0h+var_850]
0x1800496c2  mov     [rsp+8B0h+var_840], rcx
0x1800496c7  mov     r9d, r14d
0x1800496ca  mov     [rsp+8B0h+phkResult], rax
0x1800496cf  lea     rdx, RasDdmTraceError
0x1800496d6  mov     rcx, r15
0x1800496d9  call    McGenEventWrite_EventWriteTransfer
0x1800496de  mov     rcx, [rsp+8B0h+hKey]; hKey
0x1800496e3  test    rcx, rcx
0x1800496e6  jz      short loc_180049757
0x1800496e8  call    cs:__imp_RegCloseKey
0x1800496ee  jmp     short loc_180049757
0x1800496f0  test    cs:byte_1800C8404, 8
0x1800496f7  jz      short loc_180049757
0x1800496f9  lea     rdx, aDdml2tpdeviceD_3; "DdmL2tpDevice::DdmIsIKESecureCheckDisab"...
0x180049700  mov     word ptr [rbp+7B0h+var_830], di
0x180049704  lea     rcx, [rbp+7B0h+var_830]
0x180049708  call    FormatRRASErrorString
0x18004970d  test    cs:byte_1800C8404, 8
0x180049714  jz      short loc_180049757
0x180049716  lea     rax, [rbp+7B0h+var_830]
0x18004971a  inc     rbx
0x18004971d  cmp     [rax+rbx*2], di
0x180049721  jnz     short loc_18004971A
0x180049723  lea     eax, ds:2[rbx*2]
0x18004972a  mov     dword ptr [rsp+8B0h+var_838+4], edi
0x18004972e  lea     rcx, [rbp+7B0h+var_830]
0x180049732  mov     dword ptr [rsp+8B0h+var_838], eax
0x180049736  lea     rax, [rsp+8B0h+var_850]
0x18004973b  mov     [rsp+8B0h+var_840], rcx
0x180049740  mov     r9d, r14d
0x180049743  mov     [rsp+8B0h+phkResult], rax
0x180049748  lea     rdx, RasDdmTraceError
0x18004974f  mov     rcx, r15
0x180049752  call    McGenEventWrite_EventWriteTransfer
0x180049757  mov     eax, [rsi]
0x180049759  lea     rcx, [r13+2318h]
0x180049760  test    eax, eax
0x180049762  jnz     short loc_180049770
0x180049764  mov     eax, [rcx]
0x180049766  test    eax, eax
0x180049768  jz      short loc_18004976E
0x18004976a  mov     [rsi], eax
0x18004976c  jmp     short loc_180049770
0x18004976e  mov     eax, edi
0x180049770  mov     [rcx], eax
0x180049772  xor     eax, eax
0x180049774  mov     rcx, [rbp+7B0h+var_30]
0x18004977b  xor     rcx, rsp; StackCookie
0x18004977e  call    __security_check_cookie
0x180049783  lea     r11, [rsp+8B0h+var_20]
0x18004978b  mov     rbx, [r11+30h]
0x18004978f  mov     rsi, [r11+48h]
0x180049793  mov     rsp, r11
0x180049796  pop     r15
0x180049798  pop     r14
0x18004979a  pop     r13
0x18004979c  pop     rdi
0x18004979d  pop     rbp
0x18004979e  retn
```
