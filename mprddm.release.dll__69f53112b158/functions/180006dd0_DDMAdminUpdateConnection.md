# DDMAdminUpdateConnection

- ea: `0x180006dd0`
- end: `0x1800073eb`
- name: `DDMAdminUpdateConnection`
- size: `1563`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002e7c`
- `0x180006dd0`
- `0x180007c0c`
- `0x180007d00`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180092b90`
- `0x180095010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000713d`
- `msvcrt!wcsstr` at `0x1800071b3`
- `msvcrt!wcsstr` at `0x18000713d`
- `msvcrt!wcsstr` at `0x1800071b3`
- `KERNEL32!CloseHandle` at `0x180007334`
- `KERNEL32!CloseHandle` at `0x180007334`
- `KERNEL32!GetLastError` at `0x18000703e`
- `KERNEL32!GetLastError` at `0x18000703e`
- `KERNEL32!CreateEventW` at `0x180007026`
- `KERNEL32!CreateEventW` at `0x180007026`
- `KERNEL32!WaitForSingleObject` at `0x18000725d`
- `KERNEL32!WaitForSingleObject` at `0x18000725d`
- `KERNEL32!LeaveCriticalSection` at `0x180007349`
- `KERNEL32!LeaveCriticalSection` at `0x18000735e`
- `KERNEL32!LeaveCriticalSection` at `0x180007349`
- `KERNEL32!LeaveCriticalSection` at `0x18000735e`
- `KERNEL32!EnterCriticalSection` at `0x180006f20`
- `KERNEL32!EnterCriticalSection` at `0x180006f30`
- `KERNEL32!EnterCriticalSection` at `0x180006f20`
- `KERNEL32!EnterCriticalSection` at `0x180006f30`
- `ntdll!RtlIpv6StringToAddressW` at `0x18000718a`
- `ntdll!RtlIpv6StringToAddressW` at `0x1800071fc`
- `ntdll!RtlIpv6StringToAddressW` at `0x18000718a`
- `ntdll!RtlIpv6StringToAddressW` at `0x1800071fc`
- `ntdll!RtlIpv4StringToAddressW` at `0x18000716a`
- `ntdll!RtlIpv4StringToAddressW` at `0x1800071de`
- `ntdll!RtlIpv4StringToAddressW` at `0x18000716a`
- `ntdll!RtlIpv4StringToAddressW` at `0x1800071de`

## string_xrefs

- `0x180006e9b`: `DDMAdminUpdateConnection: Failed to get Connection and Device from bundle %d\n`
- `0x180006f93`: `DDMAdminUpdateConnection: Not supported for connections other than IKEv2`
- `0x180007011`: `DDMAdminUpdateConnection: Already one MOBIKE is in progress.`
- `0x18000707b`: `DDMAdminUpdateConnection: CreateEvent failed with error: %d`
- `0x18000724b`: `DDMAdminUpdateConnection: fnSendMessageToProtocolEngine failed with error: %d`
- `0x1800072a8`: `DDMAdminUpdateConnection: MOBIKE status: %d`
- `0x1800072d9`: `DDMAdminUpdateConnection: WaitForSingleObject failed: %d`

## pseudocode

```c
__int64 __fastcall DDMAdminUpdateConnection(__int64 a1, __int64 a2)
{
  DWORD v4; // eax
  void (__fastcall ***v5)(_QWORD, __int64); // rbx
  DWORD LastError; // esi
  __int64 v7; // rdi
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int128 *v12; // r9
  const wchar_t *v13; // r8
  void (__fastcall **EventW)(_QWORD, __int64); // r15
  wchar_t *v15; // rax
  const WCHAR *v16; // rcx
  wchar_t *v17; // rax
  const WCHAR *v18; // rcx
  DWORD v19; // eax
  void (__fastcall ***v21)(_QWORD, __int64); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR Terminator; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v24; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v25[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h]
  char v27[20]; // [rsp+60h] [rbp-A0h] BYREF
  int v28; // [rsp+74h] [rbp-8Ch]
  int v29; // [rsp+78h] [rbp-88h]
  struct in6_addr Addr; // [rsp+7Ch] [rbp-84h] BYREF
  int v31; // [rsp+8Ch] [rbp-74h]
  struct in6_addr v32[442]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v33; // [rsp+1C30h] [rbp+1B30h] BYREF
  char v34[16]; // [rsp+1C40h] [rbp+1B40h] BYREF
  int *v35; // [rsp+1C50h] [rbp+1B50h]
  int v36; // [rsp+1C58h] [rbp+1B58h]
  int v37; // [rsp+1C5Ch] [rbp+1B5Ch]
  int v38; // [rsp+1C60h] [rbp+1B60h] BYREF
  __int128 v39; // [rsp+1C64h] [rbp+1B64h]
  __int128 v40; // [rsp+1C74h] [rbp+1B74h]
  int v41; // [rsp+1C84h] [rbp+1B84h]
  int v42; // [rsp+1C90h] [rbp+1B90h] BYREF
  char v43[2044]; // [rsp+1C94h] [rbp+1B94h] BYREF

  v21 = 0;
  v22 = 0;
  v42 = 0;
  memset_0(v43, 0, sizeof(v43));
  v38 = 0;
  v41 = 0;
  v39 = 0;
  v40 = 0;
  v33 = 0;
  v4 = DDMGetConnectionAndDeviceFromBundle(a1, &v22, &v21);
  v5 = v21;
  LastError = v4;
  v7 = v22;
  if ( v4 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"DDMAdminUpdateConnection: Failed to get Connection and Device from bundle %d\n", a1);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)&v43[2 * v9 - 4] );
        v37 = 0;
        v36 = 2 * v9 + 2;
        v35 = &v42;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v8, 2, v34);
      }
    }
    goto LABEL_49;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v22 + 16));
  EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 2));
  if ( *(_WORD *)(v7 + 136) != 15 )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_17;
    LOWORD(v38) = 0;
    v10 = v5 ? *((unsigned int *)v5 + 16) : 0xFFFFFFFFLL;
    ConvertPortNoToString(&v38, v10);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_17;
    v11 = (__int64)v5 + 164;
    if ( v5 )
    {
      LODWORD(v12) = (_DWORD)v5 + 1484;
    }
    else
    {
      v11 = 0;
      v12 = &v33;
    }
    v13 = L"DDMAdminUpdateConnection: Not supported for connections other than IKEv2";
    goto LABEL_16;
  }
  if ( v5[184] )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_17;
    LOWORD(v38) = 0;
    ConvertPortNoToString(&v38, *((unsigned int *)v5 + 16));
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_17;
    LODWORD(v12) = (_DWORD)v5 + 1484;
    v11 = (__int64)v5 + 164;
    v13 = L"DDMAdminUpdateConnection: Already one MOBIKE is in progress.";
LABEL_16:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceInfo,
      (_DWORD)v13,
      (_DWORD)v12,
      v11,
      (__int64)&v38);
LABEL_17:
    LastError = 50;
    goto LABEL_49;
  }
  EventW = (void (__fastcall **)(_QWORD, __int64))CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    if ( *(_BYTE *)a2 == 1 )
    {
      v25[1] = 0;
      memset_0(v27, 0, 0x1BD0u);
      v5[184] = EventW;
      v26 = *((_QWORD *)*v5[13] + 12);
      v28 = *(_DWORD *)(a2 + 8);
      v25[0] = 18;
      if ( *(_WORD *)(a2 + 12) )
      {
        v15 = wcsstr((const wchar_t *)(a2 + 12), L":");
        Terminator = 0;
        v16 = (const WCHAR *)(a2 + 12);
        if ( v15 )
        {
          v29 = 2;
          RtlIpv6StringToAddressW(v16, &Terminator, &Addr);
        }
        else
        {
          v29 = 1;
          RtlIpv4StringToAddressW(v16, 0, &Terminator, (struct in_addr *)&Addr);
        }
      }
      else
      {
        v29 = 0;
      }
      if ( *(_WORD *)(a2 + 142) )
      {
        v17 = wcsstr((const wchar_t *)(a2 + 142), L":");
        v24 = 0;
        v18 = (const WCHAR *)(a2 + 142);
        if ( v17 )
        {
          v31 = 2;
          RtlIpv6StringToAddressW(v18, &v24, v32);
        }
        else
        {
          v31 = 1;
          RtlIpv4StringToAddressW(v18, 0, &v24, (struct in_addr *)v32);
        }
      }
      else
      {
        v31 = 0;
      }
      LastError = ((__int64 (__fastcall *)(_DWORD *))qword_1800CE518)(v25);
      if ( !LastError )
      {
        v19 = WaitForSingleObject(EventW, 0xFFFFFFFF);
        v5[184] = 0;
        LastError = v19;
        if ( v19 )
        {
          if ( (byte_1800CF404 & 8) == 0 )
            goto LABEL_48;
          LOWORD(v42) = 0;
          LOWORD(v38) = 0;
          ConvertPortNoToString(&v38, *((unsigned int *)v5 + 16));
          FormatRRASErrorString(&v42, L"DDMAdminUpdateConnection: WaitForSingleObject failed: %d", LastError);
        }
        else
        {
          LastError = *((_DWORD *)v5 + 370);
          if ( (byte_1800CF404 & 8) == 0 )
            goto LABEL_48;
          LOWORD(v42) = 0;
          LOWORD(v38) = 0;
          ConvertPortNoToString(&v38, *((unsigned int *)v5 + 16));
          FormatRRASErrorString(&v42, L"DDMAdminUpdateConnection: MOBIKE status: %d", LastError);
        }
LABEL_46:
        if ( (byte_1800CF404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v42,
            (_DWORD)v5 + 1484,
            (__int64)v5 + 164,
            (__int64)&v38);
        goto LABEL_48;
      }
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v42) = 0;
        LOWORD(v38) = 0;
        ConvertPortNoToString(&v38, *((unsigned int *)v5 + 16));
        FormatRRASErrorString(
          &v42,
          L"DDMAdminUpdateConnection: fnSendMessageToProtocolEngine failed with error: %d",
          LastError);
        goto LABEL_46;
      }
    }
LABEL_48:
    CloseHandle(EventW);
    goto LABEL_49;
  }
  LastError = GetLastError();
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v42) = 0;
    LOWORD(v38) = 0;
    ConvertPortNoToString(&v38, *((unsigned int *)v5 + 16));
    FormatRRASErrorString(&v42, L"DDMAdminUpdateConnection: CreateEvent failed with error: %d", LastError);
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v42,
        (_DWORD)v5 + 1484,
        (__int64)v5 + 164,
        (__int64)&v38);
  }
LABEL_49:
  if ( v5 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 2));
  if ( v7 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v22)(v22, 1);
    v5 = v21;
  }
  if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 2, 0xFFFFFFFF) == 1 )
    (**v21)(v21, 1);
  return LastError;
}

```

## disassembly

```asm
0x180006dd0  mov     [rsp-8+arg_10], rbx
0x180006dd5  mov     [rsp-8+arg_18], rsi
0x180006dda  push    rbp
0x180006ddb  push    rdi
0x180006ddc  push    r12
0x180006dde  push    r14
0x180006de0  push    r15
0x180006de2  lea     rbp, [rsp-23A0h]
0x180006dea  mov     eax, 24A0h
0x180006def  call    _alloca_probe
0x180006df4  sub     rsp, rax
0x180006df7  mov     rax, cs:__security_cookie
0x180006dfe  xor     rax, rsp
0x180006e01  mov     [rbp+23C0h+var_30], rax
0x180006e08  xor     r12d, r12d
0x180006e0b  mov     r14, rdx
0x180006e0e  mov     r15, rcx
0x180006e11  mov     [rsp+24C0h+var_2490], r12
0x180006e16  xor     edx, edx; Val
0x180006e18  mov     [rsp+24C0h+var_2488], r12
0x180006e1d  lea     rcx, [rbp+23C0h+var_82C]; void *
0x180006e24  mov     [rbp+23C0h+var_830], r12d
0x180006e2b  mov     r8d, 7FCh; Size
0x180006e31  call    memset_0
0x180006e36  xorps   xmm0, xmm0
0x180006e39  mov     [rbp+23C0h+var_860], r12d
0x180006e40  xor     eax, eax
0x180006e42  lea     r8, [rsp+24C0h+var_2490]
0x180006e47  lea     rdx, [rsp+24C0h+var_2488]
0x180006e4c  mov     [rbp+23C0h+var_83C], eax
0x180006e52  mov     rcx, r15
0x180006e55  movups  [rbp+23C0h+var_85C], xmm0
0x180006e5c  movups  [rbp+23C0h+var_84C], xmm0
0x180006e63  movups  [rbp+23C0h+var_890], xmm0
0x180006e6a  call    ?DDMGetConnectionAndDeviceFromBundle@@YAKPEAXAEAV?$RasObjPtr@VDdmDevice@@@@AEAV?$RasObjPtr@VDdmConnection@@@@@Z; DDMGetConnectionAndDeviceFromBundle(void *,RasObjPtr<DdmDevice> &,RasObjPtr<DdmConnection> &)
0x180006e6f  mov     rbx, [rsp+24C0h+var_2490]
0x180006e74  mov     esi, eax
0x180006e76  mov     rdi, [rsp+24C0h+var_2488]
0x180006e7b  test    eax, eax
0x180006e7d  jz      loc_180006F1C
0x180006e83  test    cs:byte_1800CF404, 10h
0x180006e8a  jz      loc_180007340
0x180006e90  mov     r8, r15
0x180006e93  mov     word ptr [rbp+23C0h+var_830], r12w
0x180006e9b  lea     rdx, aDdmadminupdate_4; "DDMAdminUpdateConnection: Failed to get"...
0x180006ea2  lea     rcx, [rbp+23C0h+var_830]
0x180006ea9  call    FormatRRASErrorString
0x180006eae  test    cs:byte_1800CF404, 10h
0x180006eb5  jz      loc_180007340
0x180006ebb  lea     rcx, [rbp+23C0h+var_830]
0x180006ec2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006ec6  inc     rax
0x180006ec9  cmp     [rcx+rax*2], r12w
0x180006ece  jnz     short loc_180006EC6
0x180006ed0  lea     eax, ds:2[rax*2]
0x180006ed7  mov     [rbp+23C0h+var_864], r12d
0x180006ede  lea     rcx, [rbp+23C0h+var_830]
0x180006ee5  mov     [rbp+23C0h+var_868], eax
0x180006eeb  lea     rax, [rbp+23C0h+var_880]
0x180006ef2  mov     [rbp+23C0h+var_870], rcx
0x180006ef9  mov     r9d, 2
0x180006eff  mov     [rsp+24C0h+var_24A0], rax
0x180006f04  lea     rdx, RasDdmTraceInfo
0x180006f0b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006f12  call    McGenEventWrite_EventWriteTransfer
0x180006f17  jmp     loc_180007340
0x180006f1c  lea     rcx, [rdi+10h]; lpCriticalSection
0x180006f20  call    cs:__imp_EnterCriticalSection
0x180006f27  nop     dword ptr [rax+rax+00h]
0x180006f2c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006f30  call    cs:__imp_EnterCriticalSection
0x180006f37  nop     dword ptr [rax+rax+00h]
0x180006f3c  cmp     word ptr [rdi+88h], 0Fh
0x180006f44  jz      loc_180006FD1
0x180006f4a  test    cs:byte_1800CF404, 10h
0x180006f51  jz      short loc_180006FBE
0x180006f53  mov     word ptr [rbp+23C0h+var_860], r12w
0x180006f5b  test    rbx, rbx
0x180006f5e  jz      short loc_180006F65
0x180006f60  mov     edx, [rbx+40h]
0x180006f63  jmp     short loc_180006F68
0x180006f65  or      edx, 0FFFFFFFFh
0x180006f68  lea     rcx, [rbp+23C0h+var_860]
0x180006f6f  call    ConvertPortNoToString
0x180006f74  test    cs:byte_1800CF404, 10h
0x180006f7b  jz      short loc_180006FBE
0x180006f7d  lea     rax, [rbx+0A4h]
0x180006f84  test    rbx, rbx
0x180006f87  jnz     short loc_180006FC8
0x180006f89  mov     rax, r12
0x180006f8c  lea     r9, [rbp+23C0h+var_890]
0x180006f93  lea     r8, aDdmadminupdate_3; "DDMAdminUpdateConnection: Not supported"...
0x180006f9a  lea     rcx, [rbp+23C0h+var_860]
0x180006fa1  mov     [rsp+24C0h+var_2498], rcx
0x180006fa6  lea     rdx, RasDdmParamTraceInfo
0x180006fad  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006fb4  mov     [rsp+24C0h+var_24A0], rax
0x180006fb9  call    McTemplateU0zjzz_EventWriteTransfer
0x180006fbe  mov     esi, 32h ; '2'
0x180006fc3  jmp     loc_180007340
0x180006fc8  lea     r9, [rbx+5CCh]
0x180006fcf  jmp     short loc_180006F93
0x180006fd1  cmp     [rbx+5C0h], r12
0x180006fd8  jz      short loc_18000701A
0x180006fda  test    cs:byte_1800CF404, 10h
0x180006fe1  jz      short loc_180006FBE
0x180006fe3  mov     word ptr [rbp+23C0h+var_860], r12w
0x180006feb  lea     rcx, [rbp+23C0h+var_860]
0x180006ff2  mov     edx, [rbx+40h]
0x180006ff5  call    ConvertPortNoToString
0x180006ffa  test    cs:byte_1800CF404, 10h
0x180007001  jz      short loc_180006FBE
0x180007003  lea     r9, [rbx+5CCh]
0x18000700a  lea     rax, [rbx+0A4h]
0x180007011  lea     r8, aDdmadminupdate_5; "DDMAdminUpdateConnection: Already one M"...
0x180007018  jmp     short loc_180006F9A
0x18000701a  xor     r9d, r9d; lpName
0x18000701d  xor     r8d, r8d; bInitialState
0x180007020  xor     ecx, ecx; lpEventAttributes
0x180007022  lea     edx, [r9+1]; bManualReset
0x180007026  call    cs:__imp_CreateEventW
0x18000702d  nop     dword ptr [rax+rax+00h]
0x180007032  mov     r15, rax
0x180007035  test    rax, rax
0x180007038  jnz     loc_1800070D9
0x18000703e  call    cs:__imp_GetLastError
0x180007045  nop     dword ptr [rax+rax+00h]
0x18000704a  test    cs:byte_1800CF404, 8
0x180007051  mov     esi, eax
0x180007053  jz      loc_180007340
0x180007059  mov     word ptr [rbp+23C0h+var_830], r12w
0x180007061  lea     rcx, [rbp+23C0h+var_860]
0x180007068  mov     word ptr [rbp+23C0h+var_860], r12w
0x180007070  mov     edx, [rbx+40h]
0x180007073  call    ConvertPortNoToString
0x180007078  mov     r8d, esi
0x18000707b  lea     rdx, aDdmadminupdate_2; "DDMAdminUpdateConnection: CreateEvent f"...
0x180007082  lea     rcx, [rbp+23C0h+var_830]
0x180007089  call    FormatRRASErrorString
0x18000708e  test    cs:byte_1800CF404, 8
0x180007095  jz      loc_180007340
0x18000709b  lea     rcx, [rbp+23C0h+var_860]
0x1800070a2  mov     [rsp+24C0h+var_2498], rcx
0x1800070a7  lea     rax, [rbx+0A4h]
0x1800070ae  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800070b5  mov     [rsp+24C0h+var_24A0], rax
0x1800070ba  lea     r9, [rbx+5CCh]
0x1800070c1  lea     r8, [rbp+23C0h+var_830]
0x1800070c8  lea     rdx, RasDdmParamTraceError
0x1800070cf  call    McTemplateU0zjzz_EventWriteTransfer
0x1800070d4  jmp     loc_180007340
0x1800070d9  cmp     byte ptr [r14], 1
0x1800070dd  jnz     loc_180007331
0x1800070e3  xor     eax, eax
0x1800070e5  lea     rcx, [rsp+24C0h+var_2460]; void *
0x1800070ea  xor     edx, edx; Val
0x1800070ec  mov     [rsp+24C0h+var_246C], eax
0x1800070f0  mov     r8d, 1BD0h; Size
0x1800070f6  call    memset_0
0x1800070fb  mov     [rbx+5C0h], r15
0x180007102  lea     rsi, [r14+0Ch]
0x180007106  mov     rax, [rbx+68h]
0x18000710a  mov     rcx, [rax]
0x18000710d  mov     rax, [rcx+60h]
0x180007111  mov     [rsp+24C0h+var_2468], rax
0x180007116  mov     eax, [r14+8]
0x18000711a  mov     [rsp+24C0h+var_244C], eax
0x18000711e  mov     [rsp+24C0h+var_2470], 12h
0x180007126  cmp     [rsi], r12w
0x18000712a  jnz     short loc_180007133
0x18000712c  mov     [rsp+24C0h+var_2448], r12d
0x180007131  jmp     short loc_180007196
0x180007133  lea     rdx, SubStr; ":"
0x18000713a  mov     rcx, rsi; Str
0x18000713d  call    cs:__imp_wcsstr
0x180007144  nop     dword ptr [rax+rax+00h]
0x180007149  mov     [rsp+24C0h+Terminator], r12
0x18000714e  mov     rcx, rsi; S
0x180007151  test    rax, rax
0x180007154  jnz     short loc_180007178
0x180007156  lea     r9, [rsp+24C0h+Addr]; Addr
0x18000715b  mov     [rsp+24C0h+var_2448], 1
0x180007163  lea     r8, [rsp+24C0h+Terminator]; Terminator
0x180007168  xor     edx, edx; Strict
0x18000716a  call    cs:__imp_RtlIpv4StringToAddressW
0x180007171  nop     dword ptr [rax+rax+00h]
0x180007176  jmp     short loc_180007196
0x180007178  lea     r8, [rsp+24C0h+Addr]; Addr
0x18000717d  mov     [rsp+24C0h+var_2448], 2
0x180007185  lea     rdx, [rsp+24C0h+Terminator]; Terminator
0x18000718a  call    cs:__imp_RtlIpv6StringToAddressW
0x180007191  nop     dword ptr [rax+rax+00h]
0x180007196  lea     rsi, [r14+8Eh]
0x18000719d  cmp     [rsi], r12w
0x1800071a1  jnz     short loc_1800071A9
0x1800071a3  mov     [rbp+23C0h+var_2434], r12d
0x1800071a7  jmp     short loc_180007208
0x1800071a9  lea     rdx, SubStr; ":"
0x1800071b0  mov     rcx, rsi; Str
0x1800071b3  call    cs:__imp_wcsstr
0x1800071ba  nop     dword ptr [rax+rax+00h]
0x1800071bf  mov     [rsp+24C0h+var_2478], r12
0x1800071c4  mov     rcx, rsi; S
0x1800071c7  test    rax, rax
0x1800071ca  jnz     short loc_1800071EC
0x1800071cc  lea     r9, [rbp+23C0h+var_2430]; Addr
0x1800071d0  mov     [rbp+23C0h+var_2434], 1
0x1800071d7  lea     r8, [rsp+24C0h+var_2478]; Terminator
0x1800071dc  xor     edx, edx; Strict
0x1800071de  call    cs:__imp_RtlIpv4StringToAddressW
0x1800071e5  nop     dword ptr [rax+rax+00h]
0x1800071ea  jmp     short loc_180007208
0x1800071ec  lea     r8, [rbp+23C0h+var_2430]; Addr
0x1800071f0  mov     [rbp+23C0h+var_2434], 2
0x1800071f7  lea     rdx, [rsp+24C0h+var_2478]; Terminator
0x1800071fc  call    cs:__imp_RtlIpv6StringToAddressW
0x180007203  nop     dword ptr [rax+rax+00h]
0x180007208  mov     rax, cs:qword_1800CE518
0x18000720f  lea     rcx, [rsp+24C0h+var_2470]
0x180007214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007219  mov     esi, eax
0x18000721b  test    eax, eax
0x18000721d  jz      short loc_180007257
0x18000721f  test    cs:byte_1800CF404, 8
0x180007226  jz      loc_180007331
0x18000722c  mov     word ptr [rbp+23C0h+var_830], r12w
0x180007234  lea     rcx, [rbp+23C0h+var_860]
0x18000723b  mov     word ptr [rbp+23C0h+var_860], r12w
0x180007243  mov     edx, [rbx+40h]
0x180007246  call    ConvertPortNoToString
0x18000724b  lea     rdx, aDdmadminupdate_6; "DDMAdminUpdateConnection: fnSendMessage"...
0x180007252  jmp     loc_1800072E0
0x180007257  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000725a  mov     rcx, r15; hHandle
0x18000725d  call    cs:__imp_WaitForSingleObject
0x180007264  nop     dword ptr [rax+rax+00h]
0x180007269  mov     [rbx+5C0h], r12
0x180007270  mov     esi, eax
0x180007272  test    eax, eax
0x180007274  jnz     short loc_1800072B1
0x180007276  test    cs:byte_1800CF404, 8
0x18000727d  mov     esi, [rbx+5C8h]
0x180007283  jz      loc_180007331
0x180007289  mov     word ptr [rbp+23C0h+var_830], r12w
0x180007291  lea     rcx, [rbp+23C0h+var_860]
0x180007298  mov     word ptr [rbp+23C0h+var_860], r12w
0x1800072a0  mov     edx, [rbx+40h]
0x1800072a3  call    ConvertPortNoToString
0x1800072a8  lea     rdx, aDdmadminupdate_7; "DDMAdminUpdateConnection: MOBIKE status"...
0x1800072af  jmp     short loc_1800072E0
0x1800072b1  test    cs:byte_1800CF404, 8
0x1800072b8  jz      short loc_180007331
0x1800072ba  mov     word ptr [rbp+23C0h+var_830], r12w
0x1800072c2  lea     rcx, [rbp+23C0h+var_860]
0x1800072c9  mov     word ptr [rbp+23C0h+var_860], r12w
0x1800072d1  mov     edx, [rbx+40h]
0x1800072d4  call    ConvertPortNoToString
0x1800072d9  lea     rdx, aDdmadminupdate_8; "DDMAdminUpdateConnection: WaitForSingle"...
0x1800072e0  mov     r8d, esi
0x1800072e3  lea     rcx, [rbp+23C0h+var_830]
0x1800072ea  call    FormatRRASErrorString
0x1800072ef  test    cs:byte_1800CF404, 8
0x1800072f6  jz      short loc_180007331
0x1800072f8  lea     rcx, [rbp+23C0h+var_860]
0x1800072ff  mov     [rsp+24C0h+var_2498], rcx
0x180007304  lea     rax, [rbx+0A4h]
0x18000730b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007312  mov     [rsp+24C0h+var_24A0], rax
0x180007317  lea     r9, [rbx+5CCh]
0x18000731e  lea     r8, [rbp+23C0h+var_830]
0x180007325  lea     rdx, RasDdmParamTraceError
0x18000732c  call    McTemplateU0zjzz_EventWriteTransfer
0x180007331  mov     rcx, r15; hObject
0x180007334  call    cs:__imp_CloseHandle
0x18000733b  nop     dword ptr [rax+rax+00h]
0x180007340  test    rbx, rbx
0x180007343  jz      short loc_180007355
0x180007345  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007349  call    cs:__imp_LeaveCriticalSection
0x180007350  nop     dword ptr [rax+rax+00h]
0x180007355  test    rdi, rdi
0x180007358  jz      short loc_180007396
0x18000735a  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000735e  call    cs:__imp_LeaveCriticalSection
0x180007365  nop     dword ptr [rax+rax+00h]
0x18000736a  test    rdi, rdi
0x18000736d  jz      short loc_180007396
0x18000736f  or      eax, 0FFFFFFFFh
0x180007372  lock xadd [rdi+8], eax
0x180007377  cmp     eax, 1
0x18000737a  jnz     short loc_180007391
0x18000737c  mov     rcx, [rsp+24C0h+var_2488]
0x180007381  mov     edx, 1
0x180007386  mov     rax, [rcx]
0x180007389  mov     rax, [rax]
0x18000738c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007391  mov     rbx, [rsp+24C0h+var_2490]
0x180007396  test    rbx, rbx
0x180007399  jz      short loc_1800073BD
0x18000739b  or      eax, 0FFFFFFFFh
  ... truncated ...
```
