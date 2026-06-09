# CHidPairingPlugin::_OnHidPairingMessage(HID_NOTIFICATION_TYPE,__int64)

- ea: `0x18002638c`
- end: `0x18002666a`
- name: `?_OnHidPairingMessage@CHidPairingPlugin@@AEAAJW4HID_NOTIFICATION_TYPE@@_J@Z`
- size: `734`
- prototype: `int __high(enum HID_NOTIFICATION_TYPE, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180026a60`

## callees

- `0x180003470`
- `0x180018920`
- `0x18001aa9c`
- `0x18002638c`
- `0x180026a28`
- `0x180026b68`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x180026574`
- `ntdll!WinSqmIncrementDWORD` at `0x180026574`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026622`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026622`

## string_xrefs

- `0x18002664a`: `HidPairing Notification %d ignored by plugin.`

## pseudocode

```c
__int64 __fastcall CHidPairingPlugin::_OnHidPairingMessage(__int64 a1, unsigned int a2, _QWORD *a3)
{
  unsigned int v3; // ebp
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // eax
  void *v11; // rcx
  void *v12; // rdi
  unsigned int v13; // eax
  unsigned int PairingCompleteSqmId; // eax
  __int64 (*v15)(void); // rax
  _BYTE v17[16]; // [rsp+30h] [rbp-38h] BYREF

  v3 = 0;
  if ( !*(_BYTE *)(a1 + 69) || !*(_QWORD *)(a1 + 48) )
  {
    UnattendLogW(0, L"HidPairing Notification %d ignored by plugin.", a2);
    goto LABEL_42;
  }
  UnattendLogW(0, L"Processing HidPairing notification [%d]", a2);
  switch ( a2 )
  {
    case 0u:
      if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          Microsoft_Windows_OOBE_Machine_Plugins_Context,
          HidPairingNotification_DeviceSelected,
          v7,
          1,
          v17);
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 48) + 24LL))(*(_QWORD *)(a1 + 48), *a3);
      goto LABEL_39;
    case 1u:
      if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          Microsoft_Windows_OOBE_Machine_Plugins_Context,
          HidPairingNotification_DiscoveryTimeout,
          v7,
          1,
          v17);
      v15 = *(__int64 (**)(void))(**(_QWORD **)(a1 + 48) + 32LL);
      break;
    case 2u:
      if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          Microsoft_Windows_OOBE_Machine_Plugins_Context,
          HidPairingNotification_PassKeyGenerated,
          v7,
          1,
          v17);
      if ( *(_QWORD *)&g_hSQMSession.Data1 )
        WinSqmIncrementDWORD(*(_QWORD *)&g_hSQMSession.Data1, 9090, 1);
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(a1 + 48) + 40LL))(*(_QWORD *)(a1 + 48), a3);
      v12 = 0;
      goto LABEL_44;
    case 3u:
      if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(a2 - 3, HidPairingNotification_KeyPressed, (unsigned int)a3);
      v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 48) + 48LL))(
              *(_QWORD *)(a1 + 48),
              (unsigned int)a3);
      goto LABEL_14;
    case 4u:
      if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          Microsoft_Windows_OOBE_Machine_Plugins_Context,
          HidPairingNotification_PairingSuccess,
          v7,
          1,
          v17);
      PairingCompleteSqmId = _s_GetPairingCompleteSqmId(*(unsigned int *)(a1 + 72));
      OOBESQMAddHRESULTToStream(PairingCompleteSqmId, 0);
      v15 = *(__int64 (**)(void))(**(_QWORD **)(a1 + 48) + 56LL);
      break;
    case 5u:
      if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(a2 - 5, HidPairingNotification_PairingFailed, (unsigned int)a3);
      v13 = _s_GetPairingCompleteSqmId(*(unsigned int *)(a1 + 72));
      OOBESQMAddHRESULTToStream(v13, (int)a3);
      v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 48) + 64LL))(
              *(_QWORD *)(a1 + 48),
              (unsigned int)a3);
      goto LABEL_14;
    default:
      v8 = a2 - 6;
      if ( a2 == 6 )
      {
        if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v8, HidPairingNotification_HidArrival, (unsigned int)a3);
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 48) + 72LL))(
                *(_QWORD *)(a1 + 48),
                (unsigned int)a3);
        goto LABEL_14;
      }
      if ( a2 == 7 )
      {
        if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v8, HidPairingNotification_UnexpectedError, (unsigned int)a3);
        v9 = _s_GetPairingCompleteSqmId(*(unsigned int *)(a1 + 72));
        OOBESQMAddHRESULTToStream(v9, (int)a3);
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 48) + 80LL))(
                *(_QWORD *)(a1 + 48),
                (unsigned int)a3);
        goto LABEL_14;
      }
LABEL_42:
      if ( a2 )
      {
        v11 = 0;
        v12 = 0;
        if ( a2 != 2 )
          goto LABEL_40;
LABEL_44:
        v11 = a3;
        goto LABEL_40;
      }
LABEL_39:
      v11 = (void *)*a3;
      v12 = a3;
      goto LABEL_40;
  }
  v10 = v15();
LABEL_14:
  v11 = 0;
  v3 = v10;
  v12 = 0;
LABEL_40:
  CoTaskMemFree(v11);
  CoTaskMemFree(v12);
  return v3;
}

```

## disassembly

```asm
0x18002638c  mov     [rsp+arg_18], rbx
0x180026391  push    rbp
0x180026392  push    rsi
0x180026393  push    rdi
0x180026394  sub     rsp, 50h
0x180026398  mov     rax, cs:__security_cookie
0x18002639f  xor     rax, rsp
0x1800263a2  mov     [rsp+68h+var_28], rax
0x1800263a7  xor     ebp, ebp
0x1800263a9  mov     rbx, r8
0x1800263ac  mov     esi, edx
0x1800263ae  mov     rdi, rcx
0x1800263b1  cmp     [rcx+45h], bpl
0x1800263b5  jz      loc_180026647
0x1800263bb  cmp     [rcx+30h], rbp
0x1800263bf  jz      loc_180026647
0x1800263c5  mov     r8d, edx
0x1800263c8  xor     ecx, ecx
0x1800263ca  lea     rdx, aProcessingHidp; "Processing HidPairing notification [%d]"
0x1800263d1  call    UnattendLogW
0x1800263d6  mov     ecx, esi
0x1800263d8  test    esi, esi
0x1800263da  jz      loc_1800265D2
0x1800263e0  sub     ecx, 1
0x1800263e3  jz      loc_180026596
0x1800263e9  sub     ecx, 1
0x1800263ec  jz      loc_180026531
0x1800263f2  sub     ecx, 1
0x1800263f5  jz      loc_180026509
0x1800263fb  sub     ecx, 1
0x1800263fe  jz      loc_1800264B7
0x180026404  sub     ecx, 1
0x180026407  jz      short loc_180026481
0x180026409  sub     ecx, 1
0x18002640c  jz      short loc_18002645C
0x18002640e  cmp     ecx, 1
0x180026411  jnz     loc_180026658
0x180026417  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, cl
0x18002641d  jz      short loc_18002642E
0x18002641f  mov     r8d, ebx
0x180026422  lea     rdx, HidPairingNotification_UnexpectedError
0x180026429  call    McTemplateU0q_EventWriteTransfer
0x18002642e  mov     ecx, [rdi+48h]
0x180026431  call    ?_s_GetPairingCompleteSqmId@@YAKW4HID_TYPE@@@Z; _s_GetPairingCompleteSqmId(HID_TYPE)
0x180026436  mov     ecx, eax; unsigned int
0x180026438  mov     edx, ebx; int
0x18002643a  call    ?OOBESQMAddHRESULTToStream@@YAJKJ@Z; OOBESQMAddHRESULTToStream(ulong,long)
0x18002643f  mov     rcx, [rdi+30h]
0x180026443  mov     rax, [rcx]
0x180026446  mov     rax, [rax+50h]
0x18002644a  mov     edx, ebx
0x18002644c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026451  xor     ecx, ecx
0x180026453  mov     ebp, eax
0x180026455  xor     edi, edi
0x180026457  jmp     loc_180026619
0x18002645c  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x180026463  jz      short loc_180026474
0x180026465  mov     r8d, ebx
0x180026468  lea     rdx, HidPairingNotification_HidArrival
0x18002646f  call    McTemplateU0q_EventWriteTransfer
0x180026474  mov     rcx, [rdi+30h]
0x180026478  mov     rax, [rcx]
0x18002647b  mov     rax, [rax+48h]
0x18002647f  jmp     short loc_18002644A
0x180026481  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x180026488  jz      short loc_180026499
0x18002648a  mov     r8d, ebx
0x18002648d  lea     rdx, HidPairingNotification_PairingFailed
0x180026494  call    McTemplateU0q_EventWriteTransfer
0x180026499  mov     ecx, [rdi+48h]
0x18002649c  call    ?_s_GetPairingCompleteSqmId@@YAKW4HID_TYPE@@@Z; _s_GetPairingCompleteSqmId(HID_TYPE)
0x1800264a1  mov     ecx, eax; unsigned int
0x1800264a3  mov     edx, ebx; int
0x1800264a5  call    ?OOBESQMAddHRESULTToStream@@YAJKJ@Z; OOBESQMAddHRESULTToStream(ulong,long)
0x1800264aa  mov     rcx, [rdi+30h]
0x1800264ae  mov     rax, [rcx]
0x1800264b1  mov     rax, [rax+40h]
0x1800264b5  jmp     short loc_18002644A
0x1800264b7  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x1800264be  jz      short loc_1800264E3
0x1800264c0  lea     rax, [rsp+68h+var_38]
0x1800264c5  mov     r9d, 1
0x1800264cb  lea     rdx, HidPairingNotification_PairingSuccess
0x1800264d2  mov     [rsp+68h+var_48], rax
0x1800264d7  lea     rcx, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x1800264de  call    McGenEventWrite_EventWriteTransfer
0x1800264e3  mov     ecx, [rdi+48h]
0x1800264e6  call    ?_s_GetPairingCompleteSqmId@@YAKW4HID_TYPE@@@Z; _s_GetPairingCompleteSqmId(HID_TYPE)
0x1800264eb  mov     ecx, eax; unsigned int
0x1800264ed  xor     edx, edx; int
0x1800264ef  call    ?OOBESQMAddHRESULTToStream@@YAJKJ@Z; OOBESQMAddHRESULTToStream(ulong,long)
0x1800264f4  mov     rcx, [rdi+30h]
0x1800264f8  mov     rax, [rcx]
0x1800264fb  mov     rax, [rax+38h]
0x1800264ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026504  jmp     loc_180026451
0x180026509  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x180026510  jz      short loc_180026521
0x180026512  mov     r8d, ebx
0x180026515  lea     rdx, HidPairingNotification_KeyPressed
0x18002651c  call    McTemplateU0q_EventWriteTransfer
0x180026521  mov     rcx, [rdi+30h]
0x180026525  mov     rax, [rcx]
0x180026528  mov     rax, [rax+30h]
0x18002652c  jmp     loc_18002644A
0x180026531  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x180026538  jz      short loc_18002655D
0x18002653a  lea     rax, [rsp+68h+var_38]
0x18002653f  mov     r9d, 1
0x180026545  lea     rdx, HidPairingNotification_PassKeyGenerated
0x18002654c  mov     [rsp+68h+var_48], rax
0x180026551  lea     rcx, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x180026558  call    McGenEventWrite_EventWriteTransfer
0x18002655d  mov     rcx, qword ptr cs:?g_hSQMSession@@3PEAU_GUID@@EA.Data1; _GUID * g_hSQMSession ...
0x180026564  test    rcx, rcx
0x180026567  jz      short loc_18002657A
0x180026569  mov     edx, 2382h
0x18002656e  mov     r8d, 1
0x180026574  call    cs:__imp_WinSqmIncrementDWORD
0x18002657a  mov     rcx, [rdi+30h]
0x18002657e  mov     rdx, rbx
0x180026581  mov     rax, [rcx]
0x180026584  mov     rax, [rax+28h]
0x180026588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002658d  mov     ebp, eax
0x18002658f  xor     edi, edi
0x180026591  jmp     loc_180026665
0x180026596  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x18002659d  jz      short loc_1800265C2
0x18002659f  lea     rax, [rsp+68h+var_38]
0x1800265a4  mov     r9d, 1
0x1800265aa  lea     rdx, HidPairingNotification_DiscoveryTimeout
0x1800265b1  mov     [rsp+68h+var_48], rax
0x1800265b6  lea     rcx, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x1800265bd  call    McGenEventWrite_EventWriteTransfer
0x1800265c2  mov     rcx, [rdi+30h]
0x1800265c6  mov     rax, [rcx]
0x1800265c9  mov     rax, [rax+20h]
0x1800265cd  jmp     loc_1800264FF
0x1800265d2  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x1800265d9  jz      short loc_1800265FE
0x1800265db  lea     rax, [rsp+68h+var_38]
0x1800265e0  mov     r9d, 1
0x1800265e6  lea     rdx, HidPairingNotification_DeviceSelected
0x1800265ed  mov     [rsp+68h+var_48], rax
0x1800265f2  lea     rcx, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x1800265f9  call    McGenEventWrite_EventWriteTransfer
0x1800265fe  mov     rcx, [rdi+30h]
0x180026602  mov     rdx, [rbx]
0x180026605  mov     rax, [rcx]
0x180026608  mov     rax, [rax+18h]
0x18002660c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026611  mov     ebp, eax
0x180026613  mov     rcx, [rbx]; pv
0x180026616  mov     rdi, rbx
0x180026619  call    cs:__imp_CoTaskMemFree
0x18002661f  mov     rcx, rdi; pv
0x180026622  call    cs:__imp_CoTaskMemFree
0x180026628  mov     eax, ebp
0x18002662a  mov     rcx, [rsp+68h+var_28]
0x18002662f  xor     rcx, rsp; StackCookie
0x180026632  call    __security_check_cookie
0x180026637  mov     rbx, [rsp+68h+arg_18]
0x18002663f  add     rsp, 50h
0x180026643  pop     rdi
0x180026644  pop     rsi
0x180026645  pop     rbp
0x180026646  retn
0x180026647  mov     r8d, esi
0x18002664a  lea     rdx, aHidpairingNoti; "HidPairing Notification %d ignored by p"...
0x180026651  xor     ecx, ecx
0x180026653  call    UnattendLogW
0x180026658  test    esi, esi
0x18002665a  jz      short loc_180026613
0x18002665c  xor     ecx, ecx
0x18002665e  xor     edi, edi
0x180026660  cmp     esi, 2
0x180026663  jnz     short loc_180026619
0x180026665  mov     rcx, rbx
0x180026668  jmp     short loc_180026619
```
