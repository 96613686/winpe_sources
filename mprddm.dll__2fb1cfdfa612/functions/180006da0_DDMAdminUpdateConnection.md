# DDMAdminUpdateConnection

- ea: `0x180006da0`
- end: `0x1800073d8`
- name: `DDMAdminUpdateConnection`
- size: `1592`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002e28`
- `0x180006da0`
- `0x180007b7c`
- `0x180007c50`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008c6f0`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180006f42`
- `msvcrt!_itow_s` at `0x180006fde`
- `msvcrt!_itow_s` at `0x180007065`
- `msvcrt!_itow_s` at `0x18000722c`
- `msvcrt!_itow_s` at `0x180007292`
- `msvcrt!_itow_s` at `0x1800072d6`
- `msvcrt!_itow_s` at `0x180006f42`
- `msvcrt!_itow_s` at `0x180006fde`
- `msvcrt!_itow_s` at `0x180007065`
- `msvcrt!_itow_s` at `0x18000722c`
- `msvcrt!_itow_s` at `0x180007292`
- `msvcrt!_itow_s` at `0x1800072d6`
- `msvcrt!wcsstr` at `0x180007133`
- `msvcrt!wcsstr` at `0x180007198`
- `msvcrt!wcsstr` at `0x180007133`
- `msvcrt!wcsstr` at `0x180007198`
- `KERNEL32!CloseHandle` at `0x180007337`
- `KERNEL32!CloseHandle` at `0x180007337`
- `KERNEL32!GetLastError` at `0x180007027`
- `KERNEL32!GetLastError` at `0x180007027`
- `KERNEL32!CreateEventW` at `0x180007015`
- `KERNEL32!CreateEventW` at `0x180007015`
- `KERNEL32!WaitForSingleObject` at `0x180007246`
- `KERNEL32!WaitForSingleObject` at `0x180007246`
- `KERNEL32!LeaveCriticalSection` at `0x180007346`
- `KERNEL32!LeaveCriticalSection` at `0x180007355`
- `KERNEL32!LeaveCriticalSection` at `0x180007346`
- `KERNEL32!LeaveCriticalSection` at `0x180007355`
- `KERNEL32!EnterCriticalSection` at `0x180006ef0`
- `KERNEL32!EnterCriticalSection` at `0x180006efa`
- `KERNEL32!EnterCriticalSection` at `0x180006ef0`
- `KERNEL32!EnterCriticalSection` at `0x180006efa`
- `ntdll!RtlIpv6StringToAddressW` at `0x180007174`
- `ntdll!RtlIpv6StringToAddressW` at `0x1800071d7`
- `ntdll!RtlIpv6StringToAddressW` at `0x180007174`
- `ntdll!RtlIpv6StringToAddressW` at `0x1800071d7`
- `ntdll!RtlIpv4StringToAddressW` at `0x18000715a`
- `ntdll!RtlIpv4StringToAddressW` at `0x1800071be`
- `ntdll!RtlIpv4StringToAddressW` at `0x18000715a`
- `ntdll!RtlIpv4StringToAddressW` at `0x1800071be`

## string_xrefs

- `0x180006e6b`: `DDMAdminUpdateConnection: Failed to get Connection and Device from bundle %d\n`
- `0x180006f69`: `DDMAdminUpdateConnection: Not supported for connections other than IKEv2`
- `0x180006ffd`: `DDMAdminUpdateConnection: Already one MOBIKE is in progress.`
- `0x18000706e`: `DDMAdminUpdateConnection: CreateEvent failed with error: %d`
- `0x180007232`: `DDMAdminUpdateConnection: fnSendMessageToProtocolEngine failed with error: %d`
- `0x180007298`: `DDMAdminUpdateConnection: MOBIKE status: %d`
- `0x1800072dc`: `DDMAdminUpdateConnection: WaitForSingleObject failed: %d`

## pseudocode

```c
__int64 __fastcall DDMAdminUpdateConnection(__int64 a1, __int64 a2)
{
  DWORD v4; // eax
  __int64 v5; // rbx
  DWORD LastError; // edi
  LPCWSTR v7; // r14
  __int64 v8; // r8
  __int64 v9; // rax
  char v10; // dl
  int v11; // ecx
  __int64 v12; // rax
  __int128 *v13; // r9
  const wchar_t *v14; // r8
  char v15; // dl
  int v16; // ecx
  HANDLE EventW; // r15
  int v18; // ecx
  __int64 v19; // rax
  wchar_t *v20; // rax
  const WCHAR *v21; // rcx
  wchar_t *v22; // rax
  const WCHAR *v23; // rcx
  int v24; // ecx
  DWORD v25; // eax
  int v26; // ecx
  int v27; // ecx
  LPCWSTR Terminator; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h]
  _BYTE v33[20]; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+64h] [rbp-9Ch]
  int v35; // [rsp+68h] [rbp-98h]
  struct in6_addr Addr; // [rsp+6Ch] [rbp-94h] BYREF
  int v37; // [rsp+7Ch] [rbp-84h]
  struct in6_addr v38[442]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v39; // [rsp+1C20h] [rbp+1B20h] BYREF
  _BYTE v40[16]; // [rsp+1C30h] [rbp+1B30h] BYREF
  int *v41; // [rsp+1C40h] [rbp+1B40h]
  int v42; // [rsp+1C48h] [rbp+1B48h]
  int v43; // [rsp+1C4Ch] [rbp+1B4Ch]
  wchar_t Buffer[2]; // [rsp+1C50h] [rbp+1B50h] BYREF
  __int128 v45; // [rsp+1C54h] [rbp+1B54h]
  __int128 v46; // [rsp+1C64h] [rbp+1B64h]
  int v47; // [rsp+1C74h] [rbp+1B74h]
  int v48; // [rsp+1C80h] [rbp+1B80h] BYREF
  _BYTE v49[2044]; // [rsp+1C84h] [rbp+1B84h] BYREF

  v30 = 0;
  Terminator = 0;
  v48 = 0;
  memset_0(v49, 0, sizeof(v49));
  *(_DWORD *)Buffer = 0;
  v47 = 0;
  v45 = 0;
  v46 = 0;
  v39 = 0;
  v4 = DDMGetConnectionAndDeviceFromBundle(a1, &Terminator, &v30);
  v5 = v30;
  LastError = v4;
  v7 = Terminator;
  if ( v4 )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v48) = 0;
      FormatRRASErrorString(&v48, L"DDMAdminUpdateConnection: Failed to get Connection and Device from bundle %d\n", a1);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)&v49[2 * v9 - 4] );
        v43 = 0;
        v42 = 2 * v9 + 2;
        v41 = &v48;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v8, 2, v40);
      }
    }
    goto LABEL_59;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(Terminator + 8));
  EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
  if ( v7[68] != 15 )
  {
    v10 = byte_1800C8404;
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_17;
    Buffer[0] = 0;
    if ( v5 )
    {
      v11 = *(_DWORD *)(v5 + 64);
      if ( v11 != -1 )
      {
        _itow_s(v11, Buffer, 0x14u, 10);
        v10 = byte_1800C8404;
      }
    }
    if ( (v10 & 0x10) == 0 )
      goto LABEL_17;
    v12 = v5 + 164;
    if ( v5 )
    {
      LODWORD(v13) = v5 + 1484;
    }
    else
    {
      v12 = 0;
      v13 = &v39;
    }
    v14 = L"DDMAdminUpdateConnection: Not supported for connections other than IKEv2";
LABEL_16:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceInfo,
      (_DWORD)v14,
      (_DWORD)v13,
      v12,
      (__int64)Buffer);
LABEL_17:
    LastError = 50;
    goto LABEL_59;
  }
  if ( *(_QWORD *)(v5 + 1472) )
  {
    v15 = byte_1800C8404;
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_17;
    Buffer[0] = 0;
    v16 = *(_DWORD *)(v5 + 64);
    if ( v16 != -1 )
    {
      _itow_s(v16, Buffer, 0x14u, 10);
      v15 = byte_1800C8404;
    }
    if ( (v15 & 0x10) == 0 )
      goto LABEL_17;
    v12 = v5 + 164;
    LODWORD(v13) = v5 + 1484;
    v14 = L"DDMAdminUpdateConnection: Already one MOBIKE is in progress.";
    goto LABEL_16;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    if ( *(_BYTE *)a2 == 1 )
    {
      v32 = 0;
      v31 = 18;
      memset_0(v33, 0, 0x1BD0u);
      *(_QWORD *)(v5 + 1472) = EventW;
      v19 = *(_QWORD *)(**(_QWORD **)(v5 + 104) + 96LL);
      LODWORD(v31) = 18;
      v32 = v19;
      v34 = *(_DWORD *)(a2 + 8);
      if ( *(_WORD *)(a2 + 12) )
      {
        v20 = wcsstr((const wchar_t *)(a2 + 12), L":");
        Terminator = 0;
        v21 = (const WCHAR *)(a2 + 12);
        if ( v20 )
        {
          v35 = 2;
          RtlIpv6StringToAddressW(v21, &Terminator, &Addr);
        }
        else
        {
          v35 = 1;
          RtlIpv4StringToAddressW(v21, 0, &Terminator, (struct in_addr *)&Addr);
        }
      }
      else
      {
        v35 = 0;
      }
      if ( *(_WORD *)(a2 + 142) )
      {
        v22 = wcsstr((const wchar_t *)(a2 + 142), L":");
        Terminator = 0;
        v23 = (const WCHAR *)(a2 + 142);
        if ( v22 )
        {
          v37 = 2;
          RtlIpv6StringToAddressW(v23, &Terminator, v38);
        }
        else
        {
          v37 = 1;
          RtlIpv4StringToAddressW(v23, 0, &Terminator, (struct in_addr *)v38);
        }
      }
      else
      {
        v37 = 0;
      }
      LastError = ((__int64 (__fastcall *)(__int64 *))qword_1800C7518)(&v31);
      if ( LastError )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v48) = 0;
          Buffer[0] = 0;
          v24 = *(_DWORD *)(v5 + 64);
          if ( v24 != -1 )
            _itow_s(v24, Buffer, 0x14u, 10);
          FormatRRASErrorString(
            &v48,
            L"DDMAdminUpdateConnection: fnSendMessageToProtocolEngine failed with error: %d",
            LastError);
LABEL_56:
          if ( (byte_1800C8404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v48,
              v5 + 1484,
              v5 + 164,
              (__int64)Buffer);
        }
      }
      else
      {
        v25 = WaitForSingleObject(EventW, 0xFFFFFFFF);
        *(_QWORD *)(v5 + 1472) = 0;
        LastError = v25;
        if ( v25 )
        {
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v48) = 0;
            Buffer[0] = 0;
            v27 = *(_DWORD *)(v5 + 64);
            if ( v27 != -1 )
              _itow_s(v27, Buffer, 0x14u, 10);
            FormatRRASErrorString(&v48, L"DDMAdminUpdateConnection: WaitForSingleObject failed: %d", LastError);
            goto LABEL_56;
          }
        }
        else
        {
          LastError = *(_DWORD *)(v5 + 1480);
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v48) = 0;
            Buffer[0] = 0;
            v26 = *(_DWORD *)(v5 + 64);
            if ( v26 != -1 )
              _itow_s(v26, Buffer, 0x14u, 10);
            FormatRRASErrorString(&v48, L"DDMAdminUpdateConnection: MOBIKE status: %d", LastError);
            goto LABEL_56;
          }
        }
      }
    }
    CloseHandle(EventW);
    goto LABEL_59;
  }
  LastError = GetLastError();
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v48) = 0;
    Buffer[0] = 0;
    v18 = *(_DWORD *)(v5 + 64);
    if ( v18 != -1 )
      _itow_s(v18, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v48, L"DDMAdminUpdateConnection: CreateEvent failed with error: %d", LastError);
    if ( (byte_1800C8404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v48,
        v5 + 1484,
        v5 + 164,
        (__int64)Buffer);
  }
LABEL_59:
  if ( v5 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
  if ( v7 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(LPCWSTR, __int64))v7)(v7, 1);
  }
  if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  return LastError;
}

```

## disassembly

```asm
0x180006da0  mov     [rsp-8+arg_10], rbx
0x180006da5  mov     [rsp-8+arg_18], rsi
0x180006daa  push    rbp
0x180006dab  push    rdi
0x180006dac  push    r12
0x180006dae  push    r14
0x180006db0  push    r15
0x180006db2  lea     rbp, [rsp-2390h]
0x180006dba  mov     eax, 2490h
0x180006dbf  call    _alloca_probe
0x180006dc4  sub     rsp, rax
0x180006dc7  mov     rax, cs:__security_cookie
0x180006dce  xor     rax, rsp
0x180006dd1  mov     [rbp+23B0h+var_30], rax
0x180006dd8  xor     r12d, r12d
0x180006ddb  mov     rsi, rdx
0x180006dde  mov     r15, rcx
0x180006de1  mov     [rsp+24B0h+var_2478], r12
0x180006de6  xor     edx, edx; Val
0x180006de8  mov     [rsp+24B0h+Terminator], r12
0x180006ded  lea     rcx, [rbp+23B0h+var_82C]; void *
0x180006df4  mov     [rbp+23B0h+var_830], r12d
0x180006dfb  mov     r8d, 7FCh; Size
0x180006e01  call    memset_0
0x180006e06  xorps   xmm0, xmm0
0x180006e09  mov     dword ptr [rbp+23B0h+Buffer], r12d
0x180006e10  xor     eax, eax
0x180006e12  lea     r8, [rsp+24B0h+var_2478]
0x180006e17  lea     rdx, [rsp+24B0h+Terminator]
0x180006e1c  mov     [rbp+23B0h+var_83C], eax
0x180006e22  mov     rcx, r15
0x180006e25  movups  [rbp+23B0h+var_85C], xmm0
0x180006e2c  movups  [rbp+23B0h+var_84C], xmm0
0x180006e33  movups  [rbp+23B0h+var_890], xmm0
0x180006e3a  call    ?DDMGetConnectionAndDeviceFromBundle@@YAKPEAXAEAV?$RasObjPtr@VDdmDevice@@@@AEAV?$RasObjPtr@VDdmConnection@@@@@Z; DDMGetConnectionAndDeviceFromBundle(void *,RasObjPtr<DdmDevice> &,RasObjPtr<DdmConnection> &)
0x180006e3f  mov     rbx, [rsp+24B0h+var_2478]
0x180006e44  mov     edi, eax
0x180006e46  mov     r14, [rsp+24B0h+Terminator]
0x180006e4b  test    eax, eax
0x180006e4d  jz      loc_180006EEC
0x180006e53  test    cs:byte_1800C8404, 10h
0x180006e5a  jz      loc_18000733D
0x180006e60  mov     r8, r15
0x180006e63  mov     word ptr [rbp+23B0h+var_830], r12w
0x180006e6b  lea     rdx, aDdmadminupdate_4; "DDMAdminUpdateConnection: Failed to get"...
0x180006e72  lea     rcx, [rbp+23B0h+var_830]
0x180006e79  call    FormatRRASErrorString
0x180006e7e  test    cs:byte_1800C8404, 10h
0x180006e85  jz      loc_18000733D
0x180006e8b  lea     rcx, [rbp+23B0h+var_830]
0x180006e92  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006e96  inc     rax
0x180006e99  cmp     [rcx+rax*2], r12w
0x180006e9e  jnz     short loc_180006E96
0x180006ea0  lea     eax, ds:2[rax*2]
0x180006ea7  mov     [rbp+23B0h+var_864], r12d
0x180006eae  lea     rcx, [rbp+23B0h+var_830]
0x180006eb5  mov     [rbp+23B0h+var_868], eax
0x180006ebb  lea     rax, [rbp+23B0h+var_880]
0x180006ec2  mov     [rbp+23B0h+var_870], rcx
0x180006ec9  mov     r9d, 2
0x180006ecf  mov     [rsp+24B0h+var_2490], rax
0x180006ed4  lea     rdx, RasDdmTraceInfo
0x180006edb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006ee2  call    McGenEventWrite_EventWriteTransfer
0x180006ee7  jmp     loc_18000733D
0x180006eec  lea     rcx, [r14+10h]; lpCriticalSection
0x180006ef0  call    cs:__imp_EnterCriticalSection
0x180006ef6  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006efa  call    cs:__imp_EnterCriticalSection
0x180006f00  cmp     word ptr [r14+88h], 0Fh
0x180006f09  jz      loc_180006FA7
0x180006f0f  mov     dl, cs:byte_1800C8404
0x180006f15  test    dl, 10h
0x180006f18  jz      short loc_180006F94
0x180006f1a  mov     [rbp+23B0h+Buffer], r12w
0x180006f22  test    rbx, rbx
0x180006f25  jz      short loc_180006F4E
0x180006f27  mov     ecx, [rbx+40h]; Value
0x180006f2a  or      esi, 0FFFFFFFFh
0x180006f2d  cmp     ecx, esi
0x180006f2f  jz      short loc_180006F4E
0x180006f31  mov     r9d, 0Ah; Radix
0x180006f37  lea     rdx, [rbp+23B0h+Buffer]; Buffer
0x180006f3e  lea     r8d, [r9+0Ah]; BufferCount
0x180006f42  call    cs:__imp__itow_s
0x180006f48  mov     dl, cs:byte_1800C8404
0x180006f4e  test    dl, 10h
0x180006f51  jz      short loc_180006F94
0x180006f53  lea     rax, [rbx+0A4h]
0x180006f5a  test    rbx, rbx
0x180006f5d  jnz     short loc_180006F9E
0x180006f5f  mov     rax, r12
0x180006f62  lea     r9, [rbp+23B0h+var_890]
0x180006f69  lea     r8, aDdmadminupdate_3; "DDMAdminUpdateConnection: Not supported"...
0x180006f70  lea     rcx, [rbp+23B0h+Buffer]
0x180006f77  mov     [rsp+24B0h+var_2488], rcx
0x180006f7c  lea     rdx, RasDdmParamTraceInfo
0x180006f83  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006f8a  mov     [rsp+24B0h+var_2490], rax
0x180006f8f  call    McTemplateU0zjzz_EventWriteTransfer
0x180006f94  mov     edi, 32h ; '2'
0x180006f99  jmp     loc_18000733D
0x180006f9e  lea     r9, [rbx+5CCh]
0x180006fa5  jmp     short loc_180006F69
0x180006fa7  cmp     [rbx+5C0h], r12
0x180006fae  jz      short loc_180007009
0x180006fb0  mov     dl, cs:byte_1800C8404
0x180006fb6  test    dl, 10h
0x180006fb9  jz      short loc_180006F94
0x180006fbb  mov     [rbp+23B0h+Buffer], r12w
0x180006fc3  or      esi, 0FFFFFFFFh
0x180006fc6  mov     ecx, [rbx+40h]; Value
0x180006fc9  cmp     ecx, esi
0x180006fcb  jz      short loc_180006FEA
0x180006fcd  mov     r9d, 0Ah; Radix
0x180006fd3  lea     rdx, [rbp+23B0h+Buffer]; Buffer
0x180006fda  lea     r8d, [r9+0Ah]; BufferCount
0x180006fde  call    cs:__imp__itow_s
0x180006fe4  mov     dl, cs:byte_1800C8404
0x180006fea  test    dl, 10h
0x180006fed  jz      short loc_180006F94
0x180006fef  lea     rax, [rbx+0A4h]
0x180006ff6  lea     r9, [rbx+5CCh]
0x180006ffd  lea     r8, aDdmadminupdate_5; "DDMAdminUpdateConnection: Already one M"...
0x180007004  jmp     loc_180006F70
0x180007009  xor     r9d, r9d; lpName
0x18000700c  xor     r8d, r8d; bInitialState
0x18000700f  xor     ecx, ecx; lpEventAttributes
0x180007011  lea     edx, [r9+1]; bManualReset
0x180007015  call    cs:__imp_CreateEventW
0x18000701b  mov     r15, rax
0x18000701e  test    rax, rax
0x180007021  jnz     loc_1800070CC
0x180007027  call    cs:__imp_GetLastError
0x18000702d  test    cs:byte_1800C8404, 8
0x180007034  mov     edi, eax
0x180007036  jz      loc_18000733D
0x18000703c  mov     word ptr [rbp+23B0h+var_830], r12w
0x180007044  or      esi, 0FFFFFFFFh
0x180007047  mov     [rbp+23B0h+Buffer], r12w
0x18000704f  mov     ecx, [rbx+40h]; Value
0x180007052  cmp     ecx, esi
0x180007054  jz      short loc_18000706B
0x180007056  lea     r9d, [r15+0Ah]; Radix
0x18000705a  lea     r8d, [r15+14h]; BufferCount
0x18000705e  lea     rdx, [rbp+23B0h+Buffer]; Buffer
0x180007065  call    cs:__imp__itow_s
0x18000706b  mov     r8d, edi
0x18000706e  lea     rdx, aDdmadminupdate_2; "DDMAdminUpdateConnection: CreateEvent f"...
0x180007075  lea     rcx, [rbp+23B0h+var_830]
0x18000707c  call    FormatRRASErrorString
0x180007081  test    cs:byte_1800C8404, 8
0x180007088  jz      loc_18000733D
0x18000708e  lea     rcx, [rbp+23B0h+Buffer]
0x180007095  mov     [rsp+24B0h+var_2488], rcx
0x18000709a  lea     rax, [rbx+0A4h]
0x1800070a1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800070a8  mov     [rsp+24B0h+var_2490], rax
0x1800070ad  lea     r9, [rbx+5CCh]
0x1800070b4  lea     r8, [rbp+23B0h+var_830]
0x1800070bb  lea     rdx, RasDdmParamTraceError
0x1800070c2  call    McTemplateU0zjzz_EventWriteTransfer
0x1800070c7  jmp     loc_18000733D
0x1800070cc  cmp     byte ptr [rsi], 1
0x1800070cf  jnz     loc_180007334
0x1800070d5  mov     edi, 12h
0x1800070da  mov     [rsp+24B0h+var_2468], r12
0x1800070df  xor     edx, edx; Val
0x1800070e1  mov     [rsp+24B0h+var_2470], rdi
0x1800070e6  mov     r8d, 1BD0h; Size
0x1800070ec  lea     rcx, [rsp+24B0h+var_2460]; void *
0x1800070f1  call    memset_0
0x1800070f6  mov     [rbx+5C0h], r15
0x1800070fd  mov     rax, [rbx+68h]
0x180007101  mov     rcx, [rax]
0x180007104  mov     rax, [rcx+60h]
0x180007108  mov     dword ptr [rsp+24B0h+var_2470], edi
0x18000710c  lea     rdi, [rsi+0Ch]
0x180007110  mov     [rsp+24B0h+var_2468], rax
0x180007115  mov     eax, [rsi+8]
0x180007118  mov     [rsp+24B0h+var_244C], eax
0x18000711c  cmp     [rdi], r12w
0x180007120  jnz     short loc_180007129
0x180007122  mov     [rsp+24B0h+var_2448], r12d
0x180007127  jmp     short loc_18000717A
0x180007129  lea     rdx, SubStr; ":"
0x180007130  mov     rcx, rdi; Str
0x180007133  call    cs:__imp_wcsstr
0x180007139  mov     [rsp+24B0h+Terminator], r12
0x18000713e  mov     rcx, rdi; S
0x180007141  test    rax, rax
0x180007144  jnz     short loc_180007162
0x180007146  lea     r9, [rsp+24B0h+Addr]; Addr
0x18000714b  mov     [rsp+24B0h+var_2448], 1
0x180007153  lea     r8, [rsp+24B0h+Terminator]; Terminator
0x180007158  xor     edx, edx; Strict
0x18000715a  call    cs:__imp_RtlIpv4StringToAddressW
0x180007160  jmp     short loc_18000717A
0x180007162  lea     r8, [rsp+24B0h+Addr]; Addr
0x180007167  mov     [rsp+24B0h+var_2448], 2
0x18000716f  lea     rdx, [rsp+24B0h+Terminator]; Terminator
0x180007174  call    cs:__imp_RtlIpv6StringToAddressW
0x18000717a  lea     rdi, [rsi+8Eh]
0x180007181  cmp     [rdi], r12w
0x180007185  jnz     short loc_18000718E
0x180007187  mov     [rsp+24B0h+var_2434], r12d
0x18000718c  jmp     short loc_1800071DD
0x18000718e  lea     rdx, SubStr; ":"
0x180007195  mov     rcx, rdi; Str
0x180007198  call    cs:__imp_wcsstr
0x18000719e  mov     [rsp+24B0h+Terminator], r12
0x1800071a3  mov     rcx, rdi; S
0x1800071a6  test    rax, rax
0x1800071a9  jnz     short loc_1800071C6
0x1800071ab  lea     r9, [rbp+23B0h+var_2430]; Addr
0x1800071af  mov     [rsp+24B0h+var_2434], 1
0x1800071b7  lea     r8, [rsp+24B0h+Terminator]; Terminator
0x1800071bc  xor     edx, edx; Strict
0x1800071be  call    cs:__imp_RtlIpv4StringToAddressW
0x1800071c4  jmp     short loc_1800071DD
0x1800071c6  lea     r8, [rbp+23B0h+var_2430]; Addr
0x1800071ca  mov     [rsp+24B0h+var_2434], 2
0x1800071d2  lea     rdx, [rsp+24B0h+Terminator]; Terminator
0x1800071d7  call    cs:__imp_RtlIpv6StringToAddressW
0x1800071dd  mov     rax, cs:qword_1800C7518
0x1800071e4  lea     rcx, [rsp+24B0h+var_2470]
0x1800071e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ee  mov     edi, eax
0x1800071f0  test    eax, eax
0x1800071f2  jz      short loc_18000723E
0x1800071f4  test    cs:byte_1800C8404, 8
0x1800071fb  jz      loc_180007334
0x180007201  mov     word ptr [rbp+23B0h+var_830], r12w
0x180007209  or      esi, 0FFFFFFFFh
0x18000720c  mov     [rbp+23B0h+Buffer], r12w
0x180007214  mov     ecx, [rbx+40h]; Value
0x180007217  cmp     ecx, esi
0x180007219  jz      short loc_180007232
0x18000721b  mov     r9d, 0Ah; Radix
0x180007221  lea     rdx, [rbp+23B0h+Buffer]; Buffer
0x180007228  lea     r8d, [r9+0Ah]; BufferCount
0x18000722c  call    cs:__imp__itow_s
0x180007232  lea     rdx, aDdmadminupdate_6; "DDMAdminUpdateConnection: fnSendMessage"...
0x180007239  jmp     loc_1800072E3
0x18000723e  or      esi, 0FFFFFFFFh
0x180007241  mov     rcx, r15; hHandle
0x180007244  mov     edx, esi; dwMilliseconds
0x180007246  call    cs:__imp_WaitForSingleObject
0x18000724c  mov     [rbx+5C0h], r12
0x180007253  mov     edi, eax
0x180007255  test    eax, eax
0x180007257  jnz     short loc_1800072A1
0x180007259  test    cs:byte_1800C8404, 8
0x180007260  mov     edi, [rbx+5C8h]
0x180007266  jz      loc_180007334
0x18000726c  mov     word ptr [rbp+23B0h+var_830], r12w
0x180007274  mov     [rbp+23B0h+Buffer], r12w
0x18000727c  mov     ecx, [rbx+40h]; Value
0x18000727f  cmp     ecx, esi
0x180007281  jz      short loc_180007298
0x180007283  lea     r9d, [rax+0Ah]; Radix
0x180007287  lea     r8d, [rax+14h]; BufferCount
0x18000728b  lea     rdx, [rbp+23B0h+Buffer]; Buffer
0x180007292  call    cs:__imp__itow_s
0x180007298  lea     rdx, aDdmadminupdate_7; "DDMAdminUpdateConnection: MOBIKE status"...
0x18000729f  jmp     short loc_1800072E3
0x1800072a1  test    cs:byte_1800C8404, 8
0x1800072a8  jz      loc_180007334
0x1800072ae  mov     word ptr [rbp+23B0h+var_830], r12w
0x1800072b6  mov     [rbp+23B0h+Buffer], r12w
0x1800072be  mov     ecx, [rbx+40h]; Value
0x1800072c1  cmp     ecx, esi
0x1800072c3  jz      short loc_1800072DC
0x1800072c5  mov     r9d, 0Ah; Radix
0x1800072cb  lea     rdx, [rbp+23B0h+Buffer]; Buffer
0x1800072d2  lea     r8d, [r9+0Ah]; BufferCount
0x1800072d6  call    cs:__imp__itow_s
0x1800072dc  lea     rdx, aDdmadminupdate_8; "DDMAdminUpdateConnection: WaitForSingle"...
0x1800072e3  mov     r8d, edi
0x1800072e6  lea     rcx, [rbp+23B0h+var_830]
0x1800072ed  call    FormatRRASErrorString
0x1800072f2  test    cs:byte_1800C8404, 8
0x1800072f9  jz      short loc_180007334
0x1800072fb  lea     rcx, [rbp+23B0h+Buffer]
0x180007302  mov     [rsp+24B0h+var_2488], rcx
0x180007307  lea     rax, [rbx+0A4h]
0x18000730e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007315  mov     [rsp+24B0h+var_2490], rax
0x18000731a  lea     r9, [rbx+5CCh]
0x180007321  lea     r8, [rbp+23B0h+var_830]
0x180007328  lea     rdx, RasDdmParamTraceError
0x18000732f  call    McTemplateU0zjzz_EventWriteTransfer
0x180007334  mov     rcx, r15; hObject
0x180007337  call    cs:__imp_CloseHandle
0x18000733d  test    rbx, rbx
0x180007340  jz      short loc_18000734C
0x180007342  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007346  call    cs:__imp_LeaveCriticalSection
0x18000734c  test    r14, r14
  ... truncated ...
```
