# UpdateBitLockerStatusReg(BITLOCKER_CSP_STATUS,ulong)

- ea: `0x1800d9af0`
- end: `0x1800d9dd9`
- name: `?UpdateBitLockerStatusReg@@YAJW4BITLOCKER_CSP_STATUS@@K@Z`
- size: `745`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b5aa0`

## callees

- `0x1800015b4`
- `0x180008d70`
- `0x1800090c0`
- `0x180037edc`
- `0x180045ff0`
- `0x1800485f0`
- `0x18004ad74`
- `0x1800d95f8`
- `0x1800d9af0`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x1800d9c9c`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x1800d9c9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d9ba7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d9ba7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9d15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9d15`

## pseudocode

```c
__int64 __fastcall UpdateBitLockerStatusReg(signed int a1, int a2)
{
  LSTATUS v2; // eax
  __int64 v3; // rcx
  signed int v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  int BitLockerCSPRegValueName; // eax
  LSTATUS v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  HKEY hKey; // [rsp+50h] [rbp+7h] BYREF
  __int64 v13; // [rsp+58h] [rbp+Fh] BYREF
  _BYTE v14[64]; // [rsp+60h] [rbp+17h] BYREF
  signed int v15; // [rsp+B0h] [rbp+67h] BYREF
  int Data; // [rsp+B8h] [rbp+6Fh] BYREF
  LPCWSTR lpValueName; // [rsp+C0h] [rbp+77h] BYREF
  int v18; // [rsp+C8h] [rbp+7Fh] BYREF

  Data = a2;
  v15 = a1;
  hKey = 0;
  lpValueName = 0;
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v14,
    &g_hBitLockerCSPStateUpdateProvider,
    &g_bitLockerCSPStateUpdateProviderInitLock,
    &g_bitLockerCSPStateUpdateProviderRefCount);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\BitLockerCsp\\EncryptionFailure",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  v4 = v2;
  if ( v2 > 0 )
    v4 = (unsigned __int16)v2 | 0x80070000;
  if ( v4 >= 0 )
  {
    BitLockerCSPRegValueName = GetBitLockerCSPRegValueName(v3, &lpValueName);
    v4 = BitLockerCSPRegValueName;
    if ( BitLockerCSPRegValueName >= 0 )
    {
      v8 = RegSetKeyValueW(hKey, 0, lpValueName, 4u, &Data, 4u);
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 < 0 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, 1, v4);
            v5 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 )
          {
            v6 = 87;
            goto LABEL_29;
          }
        }
      }
    }
    else
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            84,
            &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
            1,
            BitLockerCSPRegValueName);
          v5 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 )
        {
          v6 = 85;
          goto LABEL_29;
        }
      }
    }
  }
  else
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, 1, v4);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 )
      {
        v6 = 83;
LABEL_29:
        WPP_SF_d(v5[2], v6, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, (unsigned int)v4);
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (unsigned int)dword_180172518 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180172518, 0x400000000000LL) )
  {
    LODWORD(lpValueName) = Data;
    v13 = 0x1000000;
    v15 = v4;
    v18 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (int)&dword_180172518,
      (int)byte_18015FE31,
      v9,
      v10,
      (__int64)&v18,
      (__int64)&lpValueName,
      (__int64)&v15,
      (__int64)&v13);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800d9af0  mov     [rsp-8+Data], edx
0x1800d9af4  mov     [rsp-8+arg_0], ecx
0x1800d9af8  push    rbp
0x1800d9af9  push    rbx
0x1800d9afa  push    rsi
0x1800d9afb  push    r14
0x1800d9afd  lea     rbp, [rsp-3Fh]
0x1800d9b02  sub     rsp, 88h
0x1800d9b09  lea     r9, ?g_bitLockerCSPStateUpdateProviderRefCount@@3JC; volatile int *
0x1800d9b10  mov     [rbp+57h+hKey], 0
0x1800d9b18  lea     r8, ?g_bitLockerCSPStateUpdateProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x1800d9b1f  mov     [rbp+57h+lpValueName], 0
0x1800d9b27  lea     rdx, g_hBitLockerCSPStateUpdateProvider; struct _tlgProvider_t **
0x1800d9b2e  lea     rcx, [rbp+57h+var_40]; this
0x1800d9b32  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z; TelemetryProviderRegistrar::TelemetryProviderRegistrar(_tlgProvider_t const * const *,_RTL_SRWLOCK *,long volatile *)
0x1800d9b37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9b3e  lea     rsi, WPP_GLOBAL_Control
0x1800d9b45  lea     r14, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d9b4c  cmp     rcx, rsi
0x1800d9b4f  jz      short loc_1800D9B68
0x1800d9b51  test    byte ptr [rcx+1Ch], 20h
0x1800d9b55  jz      short loc_1800D9B68
0x1800d9b57  mov     rcx, [rcx+10h]
0x1800d9b5b  mov     edx, 51h ; 'Q'
0x1800d9b60  mov     r8, r14
0x1800d9b63  call    WPP_SF_
0x1800d9b68  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x1800d9b71  lea     rax, [rbp+57h+hKey]
0x1800d9b75  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800d9b7a  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\BitLockerCsp\\Encr"...
0x1800d9b81  mov     [rsp+0A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800d9b8a  xor     r9d, r9d; lpClass
0x1800d9b8d  mov     [rsp+0A0h+samDesired], 0F003Fh; samDesired
0x1800d9b95  xor     r8d, r8d; Reserved
0x1800d9b98  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d9b9f  mov     [rsp+0A0h+dwOptions], 0; dwOptions
0x1800d9ba7  call    cs:__imp_RegCreateKeyExW
0x1800d9bae  nop     dword ptr [rax+rax+00h]
0x1800d9bb3  mov     ebx, eax
0x1800d9bb5  test    eax, eax
0x1800d9bb7  jle     short loc_1800D9BC2
0x1800d9bb9  movzx   ebx, ax
0x1800d9bbc  or      ebx, 80070000h
0x1800d9bc2  test    ebx, ebx
0x1800d9bc4  jns     short loc_1800D9C19
0x1800d9bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9bcd  cmp     rcx, rsi
0x1800d9bd0  jz      loc_1800D9D0C
0x1800d9bd6  test    byte ptr [rcx+1Ch], 2
0x1800d9bda  jz      short loc_1800D9BFC
0x1800d9bdc  mov     rcx, [rcx+10h]
0x1800d9be0  mov     edx, 52h ; 'R'
0x1800d9be5  mov     r8, r14
0x1800d9be8  mov     [rsp+0A0h+dwOptions], ebx
0x1800d9bec  lea     r9d, [rdx-51h]
0x1800d9bf0  call    WPP_SF_Dd
0x1800d9bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9bfc  cmp     rcx, rsi
0x1800d9bff  jz      loc_1800D9D0C
0x1800d9c05  test    byte ptr [rcx+1Ch], 40h
0x1800d9c09  jz      loc_1800D9D0C
0x1800d9c0f  mov     edx, 53h ; 'S'
0x1800d9c14  jmp     loc_1800D9CFD
0x1800d9c19  lea     rdx, [rbp+57h+lpValueName]
0x1800d9c1d  call    ?GetBitLockerCSPRegValueName@@YAJW4BITLOCKER_CSP_STATUS@@PEAPEBG@Z; GetBitLockerCSPRegValueName(BITLOCKER_CSP_STATUS,ushort const * *)
0x1800d9c22  mov     ebx, eax
0x1800d9c24  test    eax, eax
0x1800d9c26  jns     short loc_1800D9C7B
0x1800d9c28  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9c2f  cmp     rcx, rsi
0x1800d9c32  jz      loc_1800D9D0C
0x1800d9c38  test    byte ptr [rcx+1Ch], 2
0x1800d9c3c  jz      short loc_1800D9C5E
0x1800d9c3e  mov     rcx, [rcx+10h]
0x1800d9c42  mov     edx, 54h ; 'T'
0x1800d9c47  mov     r8, r14
0x1800d9c4a  mov     [rsp+0A0h+dwOptions], eax
0x1800d9c4e  lea     r9d, [rdx-53h]
0x1800d9c52  call    WPP_SF_Dd
0x1800d9c57  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9c5e  cmp     rcx, rsi
0x1800d9c61  jz      loc_1800D9D0C
0x1800d9c67  test    byte ptr [rcx+1Ch], 40h
0x1800d9c6b  jz      loc_1800D9D0C
0x1800d9c71  mov     edx, 55h ; 'U'
0x1800d9c76  jmp     loc_1800D9CFD
0x1800d9c7b  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x1800d9c7f  lea     rax, [rbp+57h+Data]
0x1800d9c83  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d9c87  mov     r9d, 4; dwType
0x1800d9c8d  mov     [rsp+0A0h+samDesired], 4; cbData
0x1800d9c95  xor     edx, edx; lpSubKey
0x1800d9c97  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x1800d9c9c  call    cs:__imp_RegSetKeyValueW
0x1800d9ca3  nop     dword ptr [rax+rax+00h]
0x1800d9ca8  mov     ebx, eax
0x1800d9caa  test    eax, eax
0x1800d9cac  jle     short loc_1800D9CB7
0x1800d9cae  movzx   ebx, ax
0x1800d9cb1  or      ebx, 80070000h
0x1800d9cb7  test    ebx, ebx
0x1800d9cb9  jns     short loc_1800D9D0C
0x1800d9cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9cc2  cmp     rcx, rsi
0x1800d9cc5  jz      short loc_1800D9D0C
0x1800d9cc7  test    byte ptr [rcx+1Ch], 2
0x1800d9ccb  jz      short loc_1800D9CED
0x1800d9ccd  mov     rcx, [rcx+10h]
0x1800d9cd1  mov     edx, 56h ; 'V'
0x1800d9cd6  mov     r8, r14
0x1800d9cd9  mov     [rsp+0A0h+dwOptions], ebx
0x1800d9cdd  lea     r9d, [rdx-55h]
0x1800d9ce1  call    WPP_SF_Dd
0x1800d9ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9ced  cmp     rcx, rsi
0x1800d9cf0  jz      short loc_1800D9D0C
0x1800d9cf2  test    byte ptr [rcx+1Ch], 40h
0x1800d9cf6  jz      short loc_1800D9D0C
0x1800d9cf8  mov     edx, 57h ; 'W'
0x1800d9cfd  mov     rcx, [rcx+10h]
0x1800d9d01  mov     r9d, ebx
0x1800d9d04  mov     r8, r14
0x1800d9d07  call    WPP_SF_d
0x1800d9d0c  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d9d10  test    rcx, rcx
0x1800d9d13  jz      short loc_1800D9D29
0x1800d9d15  call    cs:__imp_RegCloseKey
0x1800d9d1c  nop     dword ptr [rax+rax+00h]
0x1800d9d21  mov     [rbp+57h+hKey], 0
0x1800d9d29  mov     eax, cs:dword_180172518
0x1800d9d2f  cmp     eax, 4
0x1800d9d32  jbe     short loc_1800D9D9D
0x1800d9d34  mov     rdx, 400000000000h
0x1800d9d3e  lea     rcx, dword_180172518
0x1800d9d45  call    _tlgKeywordOn
0x1800d9d4a  test    al, al
0x1800d9d4c  jz      short loc_1800D9D9D
0x1800d9d4e  mov     eax, [rbp+57h+Data]
0x1800d9d51  lea     rdx, byte_18015FE31
0x1800d9d58  mov     dword ptr [rbp+57h+lpValueName], eax
0x1800d9d5b  lea     rcx, dword_180172518
0x1800d9d62  lea     rax, [rbp+57h+var_48]
0x1800d9d66  mov     [rbp+57h+var_48], 1000000h
0x1800d9d6e  mov     [rsp+0A0h+phkResult], rax
0x1800d9d73  lea     rax, [rbp+57h+arg_0]
0x1800d9d77  mov     [rsp+0A0h+lpSecurityAttributes], rax
0x1800d9d7c  lea     rax, [rbp+57h+lpValueName]
0x1800d9d80  mov     qword ptr [rsp+0A0h+samDesired], rax
0x1800d9d85  lea     rax, [rbp+57h+arg_18]
0x1800d9d89  mov     qword ptr [rsp+0A0h+dwOptions], rax
0x1800d9d8e  mov     [rbp+57h+arg_0], ebx
0x1800d9d91  mov     [rbp+57h+arg_18], 1
0x1800d9d98  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800d9d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9da4  cmp     rcx, rsi
0x1800d9da7  jz      short loc_1800D9DC0
0x1800d9da9  test    byte ptr [rcx+1Ch], 20h
0x1800d9dad  jz      short loc_1800D9DC0
0x1800d9daf  mov     rcx, [rcx+10h]
0x1800d9db3  mov     edx, 58h ; 'X'
0x1800d9db8  mov     r8, r14
0x1800d9dbb  call    WPP_SF_
0x1800d9dc0  lea     rcx, [rbp+57h+var_40]; this
0x1800d9dc4  call    ??1TelemetryProviderRegistrar@@QEAA@XZ; TelemetryProviderRegistrar::~TelemetryProviderRegistrar(void)
0x1800d9dc9  mov     eax, ebx
0x1800d9dcb  add     rsp, 88h
0x1800d9dd2  pop     r14
0x1800d9dd4  pop     rsi
0x1800d9dd5  pop     rbx
0x1800d9dd6  pop     rbp
0x1800d9dd7  retn
```
