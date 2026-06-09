# ReadRegistryFlowControlAndDVCSetting(IRDPENCPlatformContext *)

- ea: `0x180022488`
- end: `0x1800227be`
- name: `?ReadRegistryFlowControlAndDVCSetting@@YAXPEAUIRDPENCPlatformContext@@@Z`
- size: `822`
- prototype: `void __fastcall(struct IRDPENCPlatformContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004a390`

## callees

- `0x18000e458`
- `0x18000ee00`
- `0x180022488`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800225ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002266d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800226de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800225ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002266d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800226de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800227ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800227ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022584`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022584`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x180022500`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x180022500`

## string_xrefs

- `0x18002256b`: `SYSTEM\CurrentControlSet\Services\TermDD`
- `0x1800225a7`: `Failed to open key`
- `0x180022622`: `Failed to read FlowControlDisable value`
- `0x180022690`: `Failed to read FlowControlDisplayBandwidth value`
- `0x180022701`: `Failed to read FlowControlChannelBandwidth value`

## pseudocode

```c
void __fastcall ReadRegistryFlowControlAndDVCSetting(struct IRDPENCPlatformContext *a1)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  LSTATUS v5; // eax
  int v6; // r8d
  int v7; // r9d
  LSTATUS v8; // eax
  int v9; // r8d
  int v10; // r9d
  LSTATUS v11; // eax
  int v12; // r8d
  int v13; // r9d
  LSTATUS v14; // eax
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rax
  LSTATUS v18; // [rsp+40h] [rbp-39h] BYREF
  const char *v19; // [rsp+48h] [rbp-31h] BYREF
  const char *v20; // [rsp+50h] [rbp-29h] BYREF
  BYTE v21[8]; // [rsp+58h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-19h] BYREF
  DWORD cbData[2]; // [rsp+68h] [rbp-11h] BYREF
  __int128 v24; // [rsp+70h] [rbp-9h] BYREF
  __int64 v25; // [rsp+80h] [rbp+7h]
  __int128 v26; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+98h] [rbp+1Fh]
  __int128 v28; // [rsp+A0h] [rbp+27h] BYREF
  __int64 v29; // [rsp+B0h] [rbp+37h]
  LSTATUS v30; // [rsp+E0h] [rbp+67h] BYREF
  DWORD Type; // [rsp+E8h] [rbp+6Fh] BYREF
  int Data; // [rsp+F0h] [rbp+77h] BYREF
  int v33; // [rsp+F8h] [rbp+7Fh] BYREF

  hKey = 0;
  Type = 4;
  *(_QWORD *)cbData = 4;
  Data = 0;
  v25 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  v33 = 0;
  *(_DWORD *)v21 = 0;
  v24 = 0;
  v26 = 0;
  v28 = 0;
  RDPENCHLPREG_ReadValueDWORD(
    -2147483646,
    L"SOFTWARE\\Microsoft\\TClient\\TestDVCName",
    L"EnableDVCNameRemapTunnel",
    &v30);
  (*(void (__fastcall **)(struct IRDPENCPlatformContext *, const wchar_t *, bool))(*(_QWORD *)a1 + 64LL))(
    a1,
    L"DVCRemapChannelName",
    v30 != 0);
  if ( (unsigned int)dword_1801B76C8 > 5 )
  {
    v18 = v30;
    v19 = "The TestDVC name remapping feature status";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)&word_1801976E6,
      v3,
      v4,
      (__int64)&v19,
      (__int64)&v18);
  }
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\TermDD", 0, 0x20019u, &hKey);
  if ( v5 )
  {
    if ( (unsigned int)dword_1801B76C8 > 5 )
    {
      v18 = v5;
      v19 = (const char *)L"SYSTEM\\CurrentControlSet\\Services\\TermDD";
      v20 = "Failed to open key";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        dword_1801B76C8,
        (unsigned int)byte_1801976B1,
        v6,
        v7,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v18);
    }
  }
  else
  {
    v8 = RegQueryValueExW(hKey, L"FlowControlDisable", 0, &Type, (LPBYTE)&Data, cbData);
    if ( v8 )
    {
      if ( (unsigned int)dword_1801B76C8 > 5 )
      {
        v18 = v8;
        v20 = (const char *)L"SYSTEM\\CurrentControlSet\\Services\\TermDD";
        v19 = "Failed to read FlowControlDisable value";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          dword_1801B76C8,
          (unsigned int)&dword_18019767C,
          v9,
          v10,
          (__int64)&v19,
          (__int64)&v20,
          (__int64)&v18);
      }
    }
    else
    {
      v11 = RegQueryValueExW(hKey, L"FlowControlDisplayBandwidth", 0, &Type, (LPBYTE)&v33, cbData);
      if ( v11 )
      {
        if ( (unsigned int)dword_1801B76C8 > 5 )
        {
          v18 = v11;
          v20 = (const char *)L"SYSTEM\\CurrentControlSet\\Services\\TermDD";
          v19 = "Failed to read FlowControlDisplayBandwidth value";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            dword_1801B76C8,
            (unsigned int)&byte_180197647,
            v12,
            v13,
            (__int64)&v19,
            (__int64)&v20,
            (__int64)&v18);
        }
      }
      else
      {
        v14 = RegQueryValueExW(hKey, L"FlowControlChannelBandwidth", 0, &Type, v21, cbData);
        if ( v14 )
        {
          if ( (unsigned int)dword_1801B76C8 > 5 )
          {
            v18 = v14;
            v20 = (const char *)L"SYSTEM\\CurrentControlSet\\Services\\TermDD";
            v19 = "Failed to read FlowControlChannelBandwidth value";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              dword_1801B76C8,
              (unsigned int)word_180197612,
              v15,
              v16,
              (__int64)&v19,
              (__int64)&v20,
              (__int64)&v18);
          }
        }
        else
        {
          DWORD2(v24) = Data;
          DWORD2(v26) = v33;
          DWORD2(v28) = *(_DWORD *)v21;
          v17 = *(_QWORD *)a1;
          LOWORD(v24) = 23;
          LOWORD(v26) = 23;
          LOWORD(v28) = 23;
          if ( (*(int (__fastcall **)(struct IRDPENCPlatformContext *, const WCHAR *, __int128 *))(v17 + 56))(
                 a1,
                 L"FlowControlDisable",
                 &v24) >= 0
            && (*(int (__fastcall **)(struct IRDPENCPlatformContext *, const WCHAR *, __int128 *))(*(_QWORD *)a1 + 56LL))(
                 a1,
                 L"FlowControlDisplayBandwidth",
                 &v26) >= 0 )
          {
            (*(void (__fastcall **)(struct IRDPENCPlatformContext *, const WCHAR *, __int128 *))(*(_QWORD *)a1 + 56LL))(
              a1,
              L"FlowControlChannelBandwidth",
              &v28);
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180022488  push    rbp
0x18002248a  push    rbx
0x18002248b  push    rsi
0x18002248c  lea     rbp, [rsp-47h]
0x180022491  sub     rsp, 0C0h
0x180022498  mov     eax, 4
0x18002249d  mov     [rbp+57h+hKey], 0
0x1800224a5  xorps   xmm0, xmm0
0x1800224a8  mov     [rbp+57h+Type], eax
0x1800224ab  mov     qword ptr [rbp+57h+cbData], rax
0x1800224af  lea     r9, [rbp+57h+arg_0]
0x1800224b3  xor     eax, eax
0x1800224b5  mov     [rbp+57h+Data], 0
0x1800224bc  mov     rbx, rcx
0x1800224bf  mov     [rbp+57h+var_50], rax
0x1800224c3  xorps   xmm1, xmm1
0x1800224c6  mov     [rbp+57h+var_38], rax
0x1800224ca  lea     r8, aEnabledvcnamer; "EnableDVCNameRemapTunnel"
0x1800224d1  mov     [rbp+57h+var_20], rax
0x1800224d5  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\TClient\\TestDVCNa"...
0x1800224dc  mov     [rbp+57h+arg_0], eax
0x1800224df  mov     rcx, 0FFFFFFFF80000002h
0x1800224e6  mov     [rbp+57h+arg_18], 0
0x1800224ed  mov     dword ptr [rbp+57h+var_78], 0
0x1800224f4  movups  [rbp+57h+var_60], xmm0
0x1800224f8  movups  [rbp+57h+var_48], xmm1
0x1800224fc  movups  [rbp+57h+var_30], xmm0
0x180022500  call    cs:__imp_RDPENCHLPREG_ReadValueDWORD
0x180022506  mov     rax, [rbx]
0x180022509  lea     rdx, aDvcremapchanne; "DVCRemapChannelName"
0x180022510  xor     r8d, r8d
0x180022513  mov     rcx, rbx
0x180022516  cmp     [rbp+57h+arg_0], r8d
0x18002251a  mov     rax, [rax+40h]
0x18002251e  setnz   r8b
0x180022522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022527  mov     eax, cs:dword_1801B76C8
0x18002252d  cmp     eax, 5
0x180022530  jbe     short loc_180022561
0x180022532  mov     eax, [rbp+57h+arg_0]
0x180022535  lea     rdx, word_1801976E6
0x18002253c  mov     [rbp+57h+var_90], eax
0x18002253f  lea     rax, aTheTestdvcName_0; "The TestDVC name remapping feature stat"...
0x180022546  mov     [rbp+57h+var_88], rax
0x18002254a  lea     rax, [rbp+57h+var_90]
0x18002254e  mov     [rsp+0D0h+lpcbData], rax
0x180022553  lea     rax, [rbp+57h+var_88]
0x180022557  mov     [rsp+0D0h+phkResult], rax
0x18002255c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180022561  lea     rax, [rbp+57h+hKey]
0x180022565  mov     r9d, 20019h; samDesired
0x18002256b  lea     rsi, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x180022572  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180022577  mov     rdx, rsi; lpSubKey
0x18002257a  xor     r8d, r8d; ulOptions
0x18002257d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022584  call    cs:__imp_RegOpenKeyExW
0x18002258a  test    eax, eax
0x18002258c  jz      short loc_1800225DB
0x18002258e  mov     ecx, cs:dword_1801B76C8
0x180022594  cmp     ecx, 5
0x180022597  jbe     loc_1800227A4
0x18002259d  mov     [rbp+57h+var_90], eax
0x1800225a0  lea     rdx, byte_1801976B1
0x1800225a7  lea     rax, aFailedToOpenKe; "Failed to open key"
0x1800225ae  mov     [rbp+57h+var_88], rsi
0x1800225b2  mov     [rbp+57h+var_80], rax
0x1800225b6  lea     rax, [rbp+57h+var_90]
0x1800225ba  mov     [rsp+0D0h+var_A0], rax
0x1800225bf  lea     rax, [rbp+57h+var_88]
0x1800225c3  mov     [rsp+0D0h+lpcbData], rax
0x1800225c8  lea     rax, [rbp+57h+var_80]
0x1800225cc  mov     [rsp+0D0h+phkResult], rax
0x1800225d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800225d6  jmp     loc_1800227A4
0x1800225db  mov     rcx, [rbp+57h+hKey]; hKey
0x1800225df  lea     rax, [rbp+57h+cbData]
0x1800225e3  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800225e8  lea     r9, [rbp+57h+Type]; lpType
0x1800225ec  lea     rax, [rbp+57h+Data]
0x1800225f0  xor     r8d, r8d; lpReserved
0x1800225f3  lea     rdx, aFlowcontroldis; "FlowControlDisable"
0x1800225fa  mov     [rsp+0D0h+phkResult], rax; lpData
0x1800225ff  call    cs:__imp_RegQueryValueExW
0x180022605  test    eax, eax
0x180022607  jz      short loc_180022649
0x180022609  mov     ecx, cs:dword_1801B76C8
0x18002260f  cmp     ecx, 5
0x180022612  jbe     loc_1800227A4
0x180022618  mov     [rbp+57h+var_90], eax
0x18002261b  lea     rdx, dword_18019767C
0x180022622  lea     rax, aFailedToReadFl_1; "Failed to read FlowControlDisable value"
0x180022629  mov     [rbp+57h+var_80], rsi
0x18002262d  mov     [rbp+57h+var_88], rax
0x180022631  lea     rax, [rbp+57h+var_90]
0x180022635  mov     [rsp+0D0h+var_A0], rax
0x18002263a  lea     rax, [rbp+57h+var_80]
0x18002263e  mov     [rsp+0D0h+lpcbData], rax
0x180022643  lea     rax, [rbp+57h+var_88]
0x180022647  jmp     short loc_1800225CC
0x180022649  mov     rcx, [rbp+57h+hKey]; hKey
0x18002264d  lea     rax, [rbp+57h+cbData]
0x180022651  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180022656  lea     r9, [rbp+57h+Type]; lpType
0x18002265a  lea     rax, [rbp+57h+arg_18]
0x18002265e  xor     r8d, r8d; lpReserved
0x180022661  lea     rdx, aFlowcontroldis_0; "FlowControlDisplayBandwidth"
0x180022668  mov     [rsp+0D0h+phkResult], rax; lpData
0x18002266d  call    cs:__imp_RegQueryValueExW
0x180022673  test    eax, eax
0x180022675  jz      short loc_1800226BA
0x180022677  mov     ecx, cs:dword_1801B76C8
0x18002267d  cmp     ecx, 5
0x180022680  jbe     loc_1800227A4
0x180022686  mov     [rbp+57h+var_90], eax
0x180022689  lea     rdx, byte_180197647
0x180022690  lea     rax, aFailedToReadFl_0; "Failed to read FlowControlDisplayBandwi"...
0x180022697  mov     [rbp+57h+var_80], rsi
0x18002269b  mov     [rbp+57h+var_88], rax
0x18002269f  lea     rax, [rbp+57h+var_90]
0x1800226a3  mov     [rsp+0D0h+var_A0], rax
0x1800226a8  lea     rax, [rbp+57h+var_80]
0x1800226ac  mov     [rsp+0D0h+lpcbData], rax
0x1800226b1  lea     rax, [rbp+57h+var_88]
0x1800226b5  jmp     loc_1800225CC
0x1800226ba  mov     rcx, [rbp+57h+hKey]; hKey
0x1800226be  lea     rax, [rbp+57h+cbData]
0x1800226c2  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800226c7  lea     r9, [rbp+57h+Type]; lpType
0x1800226cb  lea     rax, [rbp+57h+var_78]
0x1800226cf  xor     r8d, r8d; lpReserved
0x1800226d2  lea     rdx, aFlowcontrolcha; "FlowControlChannelBandwidth"
0x1800226d9  mov     [rsp+0D0h+phkResult], rax; lpData
0x1800226de  call    cs:__imp_RegQueryValueExW
0x1800226e4  test    eax, eax
0x1800226e6  jz      short loc_18002272B
0x1800226e8  mov     ecx, cs:dword_1801B76C8
0x1800226ee  cmp     ecx, 5
0x1800226f1  jbe     loc_1800227A4
0x1800226f7  mov     [rbp+57h+var_90], eax
0x1800226fa  lea     rdx, word_180197612
0x180022701  lea     rax, aFailedToReadFl; "Failed to read FlowControlChannelBandwi"...
0x180022708  mov     [rbp+57h+var_80], rsi
0x18002270c  mov     [rbp+57h+var_88], rax
0x180022710  lea     rax, [rbp+57h+var_90]
0x180022714  mov     [rsp+0D0h+var_A0], rax
0x180022719  lea     rax, [rbp+57h+var_80]
0x18002271d  mov     [rsp+0D0h+lpcbData], rax
0x180022722  lea     rax, [rbp+57h+var_88]
0x180022726  jmp     loc_1800225CC
0x18002272b  mov     eax, [rbp+57h+Data]
0x18002272e  lea     r8, [rbp+57h+var_60]
0x180022732  mov     dword ptr [rbp+57h+var_60+8], eax
0x180022735  lea     rdx, aFlowcontroldis; "FlowControlDisable"
0x18002273c  mov     eax, [rbp+57h+arg_18]
0x18002273f  mov     ecx, 17h
0x180022744  mov     dword ptr [rbp+57h+var_48+8], eax
0x180022747  mov     eax, dword ptr [rbp+57h+var_78]
0x18002274a  mov     dword ptr [rbp+57h+var_30+8], eax
0x18002274d  mov     rax, [rbx]
0x180022750  mov     word ptr [rbp+57h+var_60], cx
0x180022754  mov     word ptr [rbp+57h+var_48], cx
0x180022758  mov     word ptr [rbp+57h+var_30], cx
0x18002275c  mov     rcx, rbx
0x18002275f  mov     rax, [rax+38h]
0x180022763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022768  test    eax, eax
0x18002276a  js      short loc_1800227A4
0x18002276c  mov     rax, [rbx]
0x18002276f  lea     r8, [rbp+57h+var_48]
0x180022773  lea     rdx, aFlowcontroldis_0; "FlowControlDisplayBandwidth"
0x18002277a  mov     rcx, rbx
0x18002277d  mov     rax, [rax+38h]
0x180022781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022786  test    eax, eax
0x180022788  js      short loc_1800227A4
0x18002278a  mov     rax, [rbx]
0x18002278d  lea     r8, [rbp+57h+var_30]
0x180022791  lea     rdx, aFlowcontrolcha; "FlowControlChannelBandwidth"
0x180022798  mov     rcx, rbx
0x18002279b  mov     rax, [rax+38h]
0x18002279f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227a4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800227a8  test    rcx, rcx
0x1800227ab  jz      short loc_1800227B3
0x1800227ad  call    cs:__imp_RegCloseKey
0x1800227b3  add     rsp, 0C0h
0x1800227ba  pop     rsi
0x1800227bb  pop     rbx
0x1800227bc  pop     rbp
0x1800227bd  retn
```
