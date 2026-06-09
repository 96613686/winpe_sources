# PolicyManager::ReadDeviceLockPolicy

- ea: `0x180023714`
- end: `0x180023ca2`
- name: `PolicyManager::ReadDeviceLockPolicy`
- size: `1422`
- prototype: `__int64 __fastcall(NgcPolicy *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020320`

## callees

- `0x180001318`
- `0x1800158e0`
- `0x18001c218`
- `0x180023714`
- `0x18002541c`
- `0x18002f150`
- `0x180043f48`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_AllowSimpleDevicePassword` at `0x180023b1f`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_AllowSimpleDevicePassword` at `0x180023b1f`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordHistory` at `0x1800239ca`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordHistory` at `0x1800239ca`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters` at `0x180023937`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters` at `0x180023937`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordExpiration` at `0x180023a8e`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordExpiration` at `0x180023a8e`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled` at `0x1800237d4`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled` at `0x1800237d4`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MinDevicePasswordLength` at `0x180023836`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MinDevicePasswordLength` at `0x180023836`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequired` at `0x1800238d0`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequired` at `0x1800238d0`

## pseudocode

```c
__int64 __fastcall PolicyManager::ReadDeviceLockPolicy(NgcPolicy *this, _OWORD *a2)
{
  int v4; // r13d
  unsigned int v5; // r12d
  int DeviceLockPolicy_DevicePasswordEnabled; // eax
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // edi
  __int64 result; // rax
  int DeviceLockPolicy_MinDevicePasswordLength; // eax
  const unsigned __int16 *v11; // rdx
  int DeviceLockPolicy_AlphanumericDevicePasswordRequired; // eax
  int v13; // esi
  int v14; // r14d
  int DeviceLockPolicy_MinDevicePasswordComplexCharacters; // eax
  int v16; // edi
  int DeviceLockPolicy_DevicePasswordHistory; // eax
  __int64 v18; // rdx
  int DeviceLockPolicy_DevicePasswordExpiration; // eax
  __int64 v20; // rdx
  int DeviceLockPolicy_AllowSimpleDevicePassword; // eax
  unsigned __int8 *v22; // rdx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  int v26; // [rsp+50h] [rbp-69h] BYREF
  int v27; // [rsp+54h] [rbp-65h] BYREF
  unsigned int DefaultPinMinLength; // [rsp+58h] [rbp-61h] BYREF
  int v29; // [rsp+5Ch] [rbp-5Dh] BYREF
  int v30; // [rsp+60h] [rbp-59h] BYREF
  int v31; // [rsp+64h] [rbp-55h] BYREF
  __int128 v32; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v33[44]; // [rsp+78h] [rbp-41h]
  _BYTE v34[4]; // [rsp+A8h] [rbp-11h] BYREF
  int v35; // [rsp+ACh] [rbp-Dh]
  int v36; // [rsp+B0h] [rbp-9h]
  __int128 v37; // [rsp+B4h] [rbp-5h]
  int v38; // [rsp+C4h] [rbp+Bh]
  __int64 v39; // [rsp+C8h] [rbp+Fh]
  int v40; // [rsp+D0h] [rbp+17h]
  unsigned int v41; // [rsp+130h] [rbp+77h] BYREF
  unsigned int v42; // [rsp+138h] [rbp+7Fh] BYREF

  v4 = 0;
  if ( (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent() )
  {
    LOBYTE(v32) = 0;
    DWORD1(v32) = 1;
    v5 = 2;
    *((_QWORD *)&v32 + 1) = 1;
    *(_DWORD *)&v33[28] = 2;
    *(_OWORD *)&v33[12] = 0;
    *(_QWORD *)&v33[32] = 1;
    v29 = 1;
    v33[0] = 0;
    *(_QWORD *)&v33[4] = 0x7F00000008LL;
    *(_DWORD *)&v33[40] = 0;
    DeviceLockPolicy_DevicePasswordEnabled = PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled(&v29);
    v8 = DeviceLockPolicy_DevicePasswordEnabled;
    if ( DeviceLockPolicy_DevicePasswordEnabled < 0 )
    {
      if ( (unsigned int)dword_18006E000 > 4 )
      {
        v27 = DeviceLockPolicy_DevicePasswordEnabled;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18006E000,
          (unsigned __int8 *)&word_1800620AE,
          0,
          0,
          (__int64)&v27);
      }
      return v8;
    }
    if ( v29 )
      return 2148073489LL;
    DefaultPinMinLength = NgcPolicy::GetDefaultPinMinLength(this, v7);
    DeviceLockPolicy_MinDevicePasswordLength = PolicyManager_GetDeviceLockPolicy_MinDevicePasswordLength(&DefaultPinMinLength);
    v11 = (const unsigned __int16 *)(unsigned int)DeviceLockPolicy_MinDevicePasswordLength;
    if ( DeviceLockPolicy_MinDevicePasswordLength >= 0 )
    {
      if ( DefaultPinMinLength - 4 > 0x7B )
      {
        if ( (unsigned int)dword_18006E000 > 3 )
        {
          v27 = DefaultPinMinLength;
          v26 = DeviceLockPolicy_MinDevicePasswordLength;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18006E000,
            (unsigned int)word_180062022,
            0,
            0,
            (__int64)&v26,
            (__int64)&v27);
        }
        DefaultPinMinLength = NgcPolicy::GetDefaultPinMinLength(this, v11);
      }
    }
    else if ( (unsigned int)dword_18006E000 > 4 )
    {
      v27 = DeviceLockPolicy_MinDevicePasswordLength;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_18006206D,
        0,
        0,
        (__int64)&v27);
    }
    v30 = 2;
    DeviceLockPolicy_AlphanumericDevicePasswordRequired = PolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequired(
                                                            &v30,
                                                            v11);
    if ( DeviceLockPolicy_AlphanumericDevicePasswordRequired < 0 && (unsigned int)dword_18006E000 > 4 )
    {
      v26 = DeviceLockPolicy_AlphanumericDevicePasswordRequired;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)&word_180061FD6,
        0,
        0,
        (__int64)&v26);
    }
    if ( v30 == 1 )
    {
      v13 = 1;
      v14 = 2;
      v4 = 2;
    }
    else
    {
      v13 = 0;
      v14 = 0;
      v5 = 0;
      if ( !v30 )
      {
        v27 = 1;
        DeviceLockPolicy_MinDevicePasswordComplexCharacters = PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters(&v27);
        v16 = DeviceLockPolicy_MinDevicePasswordComplexCharacters;
        if ( DeviceLockPolicy_MinDevicePasswordComplexCharacters < 0 && (unsigned int)dword_18006E000 > 4 )
        {
          v26 = DeviceLockPolicy_MinDevicePasswordComplexCharacters;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_18006E000,
            (unsigned __int8 *)word_180061F8A,
            0,
            0,
            (__int64)&v26);
        }
        if ( v27 != 1 )
        {
          switch ( v27 )
          {
            case 2:
              v13 = 1;
              v14 = 1;
              break;
            case 3:
              v13 = 1;
              v14 = 1;
              v5 = 1;
              break;
            case 4:
              v13 = 1;
              v14 = 1;
              v5 = 1;
              v4 = 1;
              break;
            default:
              if ( (unsigned int)dword_18006E000 > 3 )
              {
                v26 = v16;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (__int64)&dword_18006E000,
                  (unsigned __int8 *)&dword_180061F44,
                  0,
                  0,
                  (__int64)&v26);
              }
              break;
          }
        }
      }
    }
    v42 = 0;
    DeviceLockPolicy_DevicePasswordHistory = PolicyManager_GetDeviceLockPolicy_DevicePasswordHistory(&v42);
    v18 = (unsigned int)DeviceLockPolicy_DevicePasswordHistory;
    if ( DeviceLockPolicy_DevicePasswordHistory >= 0 )
    {
      if ( v42 > 0x32 )
      {
        if ( (unsigned int)dword_18006E000 > 3 )
        {
          v26 = v42;
          v27 = DeviceLockPolicy_DevicePasswordHistory;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18006E000,
            (unsigned int)byte_180061ED1,
            0,
            0,
            (__int64)&v27,
            (__int64)&v26);
        }
        v42 = 0;
      }
    }
    else if ( (unsigned int)dword_18006E000 > 4 )
    {
      v26 = DeviceLockPolicy_DevicePasswordHistory;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_180061F05,
        0,
        0,
        (__int64)&v26);
    }
    v41 = 0;
    DeviceLockPolicy_DevicePasswordExpiration = PolicyManager_GetDeviceLockPolicy_DevicePasswordExpiration(&v41, v18);
    v20 = (unsigned int)DeviceLockPolicy_DevicePasswordExpiration;
    if ( DeviceLockPolicy_DevicePasswordExpiration >= 0 )
    {
      if ( v41 > 0x2DA )
      {
        if ( (unsigned int)dword_18006E000 > 3 )
        {
          v26 = v41;
          v27 = DeviceLockPolicy_DevicePasswordExpiration;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18006E000,
            (unsigned int)byte_180061E55,
            0,
            0,
            (__int64)&v27,
            (__int64)&v26);
        }
        v41 = 0;
      }
    }
    else if ( (unsigned int)dword_18006E000 > 4 )
    {
      v26 = DeviceLockPolicy_DevicePasswordExpiration;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_180061E8F,
        0,
        0,
        (__int64)&v26);
    }
    v31 = 1;
    DeviceLockPolicy_AllowSimpleDevicePassword = PolicyManager_GetDeviceLockPolicy_AllowSimpleDevicePassword(&v31, v20);
    if ( DeviceLockPolicy_AllowSimpleDevicePassword < 0 && (unsigned int)dword_18006E000 > 4 )
    {
      v26 = DeviceLockPolicy_AllowSimpleDevicePassword;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)word_180061E12,
        0,
        0,
        (__int64)&v26);
    }
    v34[0] = 0;
    v35 = 8;
    v36 = 127;
    v37 = 0;
    v38 = 2;
    v39 = 1;
    v40 = 0;
    v8 = NgcPolicy::NgcPinPolicy::Initialize(v34, DefaultPinMinLength, 127, v5, v14, v13, v4, v31, v42, v41);
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_18006E000 <= 2 )
        return v8;
      v22 = (unsigned __int8 *)byte_180061DE1;
LABEL_59:
      v26 = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        v22,
        0,
        0,
        (__int64)&v26);
      return v8;
    }
    result = NgcPolicy::NgcPolicy::Initialize(&v32, 1, 1, 0, v34);
    v8 = result;
    if ( (int)result < 0 )
    {
      if ( (unsigned int)dword_18006E000 <= 2 )
        return v8;
      v22 = (unsigned __int8 *)&unk_180061DB0;
      goto LABEL_59;
    }
    v23 = *(_OWORD *)v33;
    *a2 = v32;
    v24 = *(_OWORD *)&v33[16];
    a2[1] = v23;
    v25 = *(_OWORD *)&v33[28];
    a2[2] = v24;
    *(_OWORD *)((char *)a2 + 44) = v25;
  }
  else
  {
    if ( (unsigned int)dword_18006E000 > 4 )
    {
      v26 = -2146893783;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_1800620ED,
        0,
        0,
        (__int64)&v26);
    }
    return 2148073513LL;
  }
  return result;
}

```

## disassembly

```asm
0x180023714  mov     [rsp-8+arg_0], rbx
0x180023719  push    rbp
0x18002371a  push    rsi
0x18002371b  push    rdi
0x18002371c  push    r12
0x18002371e  push    r13
0x180023720  push    r14
0x180023722  push    r15
0x180023724  lea     rbp, [rsp-27h]
0x180023729  sub     rsp, 0E0h
0x180023730  mov     r15, rdx
0x180023733  mov     rsi, rcx
0x180023736  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x18002373b  xor     r13d, r13d
0x18002373e  test    al, al
0x180023740  jz      loc_180023C4E
0x180023746  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x18002374b  test    al, al
0x18002374d  jz      loc_180023C4E
0x180023753  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x180023758  test    al, al
0x18002375a  jz      loc_180023C4E
0x180023760  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x180023765  test    al, al
0x180023767  jz      loc_180023C4E
0x18002376d  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x180023772  test    al, al
0x180023774  jz      loc_180023C4E
0x18002377a  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x18002377f  test    al, al
0x180023781  jz      loc_180023C4E
0x180023787  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x18002378c  test    al, al
0x18002378e  jz      loc_180023C4E
0x180023794  lea     edx, [r13+1]
0x180023798  mov     byte ptr [rbp+57h+var_A8], r13b
0x18002379c  xorps   xmm0, xmm0
0x18002379f  mov     dword ptr [rbp+57h+var_A8+4], edx
0x1800237a2  lea     r12d, [r13+2]
0x1800237a6  mov     qword ptr [rbp+57h+var_A8+8], rdx
0x1800237aa  lea     rcx, [rbp+57h+var_B4]
0x1800237ae  mov     dword ptr [rbp+57h+var_7C], r12d
0x1800237b2  movdqu  [rbp+57h+var_98+0Ch], xmm0
0x1800237b7  mov     qword ptr [rbp+57h+var_7C+4], rdx
0x1800237bb  mov     [rbp+57h+var_B4], edx
0x1800237be  mov     byte ptr [rbp+57h+var_98], r13b
0x1800237c2  mov     dword ptr [rbp+57h+var_98+4], 8
0x1800237c9  mov     dword ptr [rbp+57h+var_98+8], 7Fh
0x1800237d0  mov     dword ptr [rbp+57h+var_7C+0Ch], r13d
0x1800237d4  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled
0x1800237da  mov     edi, eax
0x1800237dc  test    eax, eax
0x1800237de  jns     short loc_180023817
0x1800237e0  mov     ecx, cs:dword_18006E000
0x1800237e6  cmp     ecx, 4
0x1800237e9  jbe     short loc_180023810
0x1800237eb  mov     [rbp+57h+var_BC], eax
0x1800237ee  lea     rdx, word_1800620AE
0x1800237f5  lea     rax, [rbp+57h+var_BC]
0x1800237f9  xor     r9d, r9d
0x1800237fc  mov     [rsp+110h+var_F0], rax
0x180023801  lea     rcx, dword_18006E000
0x180023808  xor     r8d, r8d
0x18002380b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023810  mov     eax, edi
0x180023812  jmp     loc_180023C87
0x180023817  cmp     [rbp+57h+var_B4], r13d
0x18002381b  jz      short loc_180023827
0x18002381d  mov     eax, 80090011h
0x180023822  jmp     loc_180023C87
0x180023827  mov     rcx, rsi; this
0x18002382a  call    ?GetDefaultPinMinLength@NgcPolicy@@YAKPEBG@Z; NgcPolicy::GetDefaultPinMinLength(ushort const *)
0x18002382f  lea     rcx, [rbp+57h+var_B8]
0x180023833  mov     [rbp+57h+var_B8], eax
0x180023836  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_MinDevicePasswordLength
0x18002383c  lea     rbx, dword_18006E000
0x180023843  mov     edx, eax
0x180023845  test    eax, eax
0x180023847  jns     short loc_180023877
0x180023849  mov     ecx, cs:dword_18006E000
0x18002384f  cmp     ecx, 4
0x180023852  jbe     short loc_1800238C8
0x180023854  mov     [rbp+57h+var_BC], eax
0x180023857  lea     rdx, byte_18006206D
0x18002385e  lea     rax, [rbp+57h+var_BC]
0x180023862  xor     r9d, r9d
0x180023865  xor     r8d, r8d
0x180023868  mov     [rsp+110h+var_F0], rax
0x18002386d  mov     rcx, rbx
0x180023870  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023875  jmp     short loc_1800238C8
0x180023877  mov     eax, [rbp+57h+var_B8]
0x18002387a  add     eax, 0FFFFFFFCh
0x18002387d  cmp     eax, 7Bh ; '{'
0x180023880  jbe     short loc_1800238C8
0x180023882  mov     eax, cs:dword_18006E000
0x180023888  cmp     eax, 3
0x18002388b  jbe     short loc_1800238BD
0x18002388d  mov     eax, [rbp+57h+var_B8]
0x180023890  xor     r9d, r9d
0x180023893  mov     [rbp+57h+var_BC], eax
0x180023896  xor     r8d, r8d
0x180023899  lea     rax, [rbp+57h+var_BC]
0x18002389d  mov     [rbp+57h+var_C0], edx
0x1800238a0  mov     [rsp+110h+var_E8], rax
0x1800238a5  lea     rdx, word_180062022
0x1800238ac  lea     rax, [rbp+57h+var_C0]
0x1800238b0  mov     rcx, rbx
0x1800238b3  mov     [rsp+110h+var_F0], rax
0x1800238b8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800238bd  mov     rcx, rsi; this
0x1800238c0  call    ?GetDefaultPinMinLength@NgcPolicy@@YAKPEBG@Z; NgcPolicy::GetDefaultPinMinLength(ushort const *)
0x1800238c5  mov     [rbp+57h+var_B8], eax
0x1800238c8  lea     rcx, [rbp+57h+var_B0]
0x1800238cc  mov     [rbp+57h+var_B0], r12d
0x1800238d0  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequired
0x1800238d6  test    eax, eax
0x1800238d8  jns     short loc_180023906
0x1800238da  mov     ecx, cs:dword_18006E000
0x1800238e0  cmp     ecx, 4
0x1800238e3  jbe     short loc_180023906
0x1800238e5  mov     [rbp+57h+var_C0], eax
0x1800238e8  lea     rdx, word_180061FD6
0x1800238ef  lea     rax, [rbp+57h+var_C0]
0x1800238f3  xor     r9d, r9d
0x1800238f6  xor     r8d, r8d
0x1800238f9  mov     [rsp+110h+var_F0], rax
0x1800238fe  mov     rcx, rbx
0x180023901  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023906  mov     eax, [rbp+57h+var_B0]
0x180023909  mov     edi, 1
0x18002390e  cmp     eax, edi
0x180023910  jnz     short loc_18002391F
0x180023912  mov     esi, edi
0x180023914  mov     r14d, r12d
0x180023917  mov     r13d, r12d
0x18002391a  jmp     loc_1800239BF
0x18002391f  mov     esi, r13d
0x180023922  mov     r14d, r13d
0x180023925  mov     r12d, r13d
0x180023928  test    eax, eax
0x18002392a  jnz     loc_1800239BF
0x180023930  lea     rcx, [rbp+57h+var_BC]
0x180023934  mov     [rbp+57h+var_BC], edi
0x180023937  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters
0x18002393d  mov     edi, eax
0x18002393f  test    eax, eax
0x180023941  jns     short loc_18002396F
0x180023943  mov     ecx, cs:dword_18006E000
0x180023949  cmp     ecx, 4
0x18002394c  jbe     short loc_18002396F
0x18002394e  mov     [rbp+57h+var_C0], eax
0x180023951  lea     rdx, word_180061F8A
0x180023958  lea     rax, [rbp+57h+var_C0]
0x18002395c  xor     r9d, r9d
0x18002395f  xor     r8d, r8d
0x180023962  mov     [rsp+110h+var_F0], rax
0x180023967  mov     rcx, rbx
0x18002396a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002396f  mov     ecx, [rbp+57h+var_BC]
0x180023972  sub     ecx, 1
0x180023975  jz      short loc_1800239BA
0x180023977  sub     ecx, 1
0x18002397a  jz      loc_180023A29
0x180023980  sub     ecx, 1
0x180023983  jz      loc_180023A1A
0x180023989  cmp     ecx, 1
0x18002398c  jz      short loc_180023A08
0x18002398e  mov     eax, cs:dword_18006E000
0x180023994  cmp     eax, 3
0x180023997  jbe     short loc_1800239BA
0x180023999  lea     rax, [rbp+57h+var_C0]
0x18002399d  mov     [rbp+57h+var_C0], edi
0x1800239a0  xor     r9d, r9d
0x1800239a3  mov     [rsp+110h+var_F0], rax
0x1800239a8  xor     r8d, r8d
0x1800239ab  lea     rdx, dword_180061F44
0x1800239b2  mov     rcx, rbx
0x1800239b5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800239ba  mov     edi, 1
0x1800239bf  lea     rcx, [rbp+57h+arg_18]
0x1800239c3  mov     [rbp+57h+arg_18], 0
0x1800239ca  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_DevicePasswordHistory
0x1800239d0  mov     edx, eax
0x1800239d2  test    eax, eax
0x1800239d4  jns     short loc_180023A35
0x1800239d6  mov     ecx, cs:dword_18006E000
0x1800239dc  cmp     ecx, 4
0x1800239df  jbe     loc_180023A83
0x1800239e5  mov     [rbp+57h+var_C0], eax
0x1800239e8  lea     rdx, byte_180061F05
0x1800239ef  lea     rax, [rbp+57h+var_C0]
0x1800239f3  xor     r9d, r9d
0x1800239f6  xor     r8d, r8d
0x1800239f9  mov     [rsp+110h+var_F0], rax
0x1800239fe  mov     rcx, rbx
0x180023a01  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023a06  jmp     short loc_180023A83
0x180023a08  mov     edi, 1
0x180023a0d  mov     esi, edi
0x180023a0f  mov     r14d, edi
0x180023a12  mov     r12d, edi
0x180023a15  mov     r13d, edi
0x180023a18  jmp     short loc_1800239BF
0x180023a1a  mov     edi, 1
0x180023a1f  mov     esi, edi
0x180023a21  mov     r14d, edi
0x180023a24  mov     r12d, edi
0x180023a27  jmp     short loc_1800239BF
0x180023a29  mov     edi, 1
0x180023a2e  mov     esi, edi
0x180023a30  mov     r14d, edi
0x180023a33  jmp     short loc_1800239BF
0x180023a35  mov     eax, [rbp+57h+arg_18]
0x180023a38  test    eax, eax
0x180023a3a  js      short loc_180023A41
0x180023a3c  cmp     eax, 32h ; '2'
0x180023a3f  jbe     short loc_180023A83
0x180023a41  mov     eax, cs:dword_18006E000
0x180023a47  cmp     eax, 3
0x180023a4a  jbe     short loc_180023A7C
0x180023a4c  mov     eax, [rbp+57h+arg_18]
0x180023a4f  xor     r9d, r9d
0x180023a52  mov     [rbp+57h+var_C0], eax
0x180023a55  xor     r8d, r8d
0x180023a58  lea     rax, [rbp+57h+var_C0]
0x180023a5c  mov     [rbp+57h+var_BC], edx
0x180023a5f  mov     [rsp+110h+var_E8], rax
0x180023a64  lea     rdx, byte_180061ED1
0x180023a6b  lea     rax, [rbp+57h+var_BC]
0x180023a6f  mov     rcx, rbx
0x180023a72  mov     [rsp+110h+var_F0], rax
0x180023a77  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023a7c  mov     [rbp+57h+arg_18], 0
0x180023a83  lea     rcx, [rbp+57h+arg_10]
0x180023a87  mov     [rbp+57h+arg_10], 0
0x180023a8e  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_DevicePasswordExpiration
0x180023a94  mov     edx, eax
0x180023a96  test    eax, eax
0x180023a98  jns     short loc_180023AC8
0x180023a9a  mov     ecx, cs:dword_18006E000
0x180023aa0  cmp     ecx, 4
0x180023aa3  jbe     short loc_180023B18
0x180023aa5  mov     [rbp+57h+var_C0], eax
0x180023aa8  lea     rdx, byte_180061E8F
0x180023aaf  lea     rax, [rbp+57h+var_C0]
0x180023ab3  xor     r9d, r9d
0x180023ab6  xor     r8d, r8d
0x180023ab9  mov     [rsp+110h+var_F0], rax
0x180023abe  mov     rcx, rbx
0x180023ac1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023ac6  jmp     short loc_180023B18
0x180023ac8  mov     eax, [rbp+57h+arg_10]
0x180023acb  test    eax, eax
0x180023acd  js      short loc_180023AD6
0x180023acf  cmp     eax, 2DAh
0x180023ad4  jbe     short loc_180023B18
0x180023ad6  mov     eax, cs:dword_18006E000
0x180023adc  cmp     eax, 3
0x180023adf  jbe     short loc_180023B11
0x180023ae1  mov     eax, [rbp+57h+arg_10]
0x180023ae4  xor     r9d, r9d
0x180023ae7  mov     [rbp+57h+var_C0], eax
0x180023aea  xor     r8d, r8d
0x180023aed  lea     rax, [rbp+57h+var_C0]
0x180023af1  mov     [rbp+57h+var_BC], edx
0x180023af4  mov     [rsp+110h+var_E8], rax
0x180023af9  lea     rdx, byte_180061E55
0x180023b00  lea     rax, [rbp+57h+var_BC]
0x180023b04  mov     rcx, rbx
0x180023b07  mov     [rsp+110h+var_F0], rax
0x180023b0c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023b11  mov     [rbp+57h+arg_10], 0
0x180023b18  lea     rcx, [rbp+57h+var_AC]
0x180023b1c  mov     [rbp+57h+var_AC], edi
0x180023b1f  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_AllowSimpleDevicePassword
0x180023b25  test    eax, eax
0x180023b27  jns     short loc_180023B55
0x180023b29  mov     ecx, cs:dword_18006E000
0x180023b2f  cmp     ecx, 4
0x180023b32  jbe     short loc_180023B55
0x180023b34  mov     [rbp+57h+var_C0], eax
0x180023b37  lea     rdx, word_180061E12
0x180023b3e  lea     rax, [rbp+57h+var_C0]
0x180023b42  xor     r9d, r9d
0x180023b45  xor     r8d, r8d
0x180023b48  mov     [rsp+110h+var_F0], rax
0x180023b4d  mov     rcx, rbx
0x180023b50  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023b55  mov     eax, [rbp+57h+arg_10]
0x180023b58  lea     rcx, [rbp+57h+var_68]
0x180023b5c  mov     edx, [rbp+57h+var_B8]
0x180023b5f  mov     r8d, 7Fh
0x180023b65  mov     [rsp+110h+var_C8], eax
0x180023b69  xorps   xmm0, xmm0
0x180023b6c  mov     eax, [rbp+57h+arg_18]
0x180023b6f  mov     r9d, r12d
0x180023b72  mov     [rsp+110h+var_D0], eax
0x180023b76  mov     eax, [rbp+57h+var_AC]
0x180023b79  mov     [rsp+110h+var_D8], eax
  ... truncated ...
```
