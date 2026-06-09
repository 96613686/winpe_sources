# EapHost::ECPDeviceManager::CreateECPBusEnumerator(ATL::CComPtr<IUMBusPDO> &)

- ea: `0x180011cb0`
- end: `0x1800122b2`
- name: `?CreateECPBusEnumerator@ECPDeviceManager@EapHost@@QEAAXAEAV?$CComPtr@UIUMBusPDO@@@ATL@@@Z`
- size: `1538`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f77c`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000ab70`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c1a8`
- `0x18000c39c`
- `0x18000c40c`
- `0x18000c7b8`
- `0x180011cb0`
- `0x1800142dc`
- `0x1800147b4`
- `0x1800148c4`
- `0x180017010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180011de9`
- `ntdll!EtwEventEnabled` at `0x180011eca`
- `ntdll!EtwEventEnabled` at `0x180011fcb`
- `ntdll!EtwEventEnabled` at `0x18001209b`
- `ntdll!EtwEventEnabled` at `0x18001211f`
- `ntdll!EtwEventEnabled` at `0x1800121b4`
- `ntdll!EtwEventEnabled` at `0x180012242`
- `ntdll!EtwEventEnabled` at `0x180011de9`
- `ntdll!EtwEventEnabled` at `0x180011eca`
- `ntdll!EtwEventEnabled` at `0x180011fcb`
- `ntdll!EtwEventEnabled` at `0x18001209b`
- `ntdll!EtwEventEnabled` at `0x18001211f`
- `ntdll!EtwEventEnabled` at `0x1800121b4`
- `ntdll!EtwEventEnabled` at `0x180012242`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011d17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011d17`

## string_xrefs

- `0x18001212c`: `Failed to create IPropertyStore for ECP bus enumerator, 0x%x`
- `0x180011ed7`: `The bus enumerator already exists when trying to create it`
- `0x18001224c`: `AddBusEnumerator for adding ECP bus device is considered failure`
- `0x180011fd5`: `ECP bus enumerator successfully created`

## pseudocode

```c
__int64 __fastcall EapHost::ECPDeviceManager::CreateECPBusEnumerator(_QWORD *a1, _QWORD *a2)
{
  unsigned int v4; // r15d
  unsigned int v5; // r15d
  EapHost::FDNotification *v6; // r13
  __int64 v7; // rdx
  unsigned int v8; // r15d
  __int64 v9; // r12
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rax
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rax
  unsigned int v16; // r15d
  __int64 result; // rax
  int v18; // r8d
  int v19; // r9d
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-C8h]
  _QWORD *v22; // [rsp+40h] [rbp-C0h]
  _QWORD v23[3]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v24[3]; // [rsp+60h] [rbp-A0h] BYREF
  LPCVOID lpMem[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v26; // [rsp+88h] [rbp-78h]
  char v27[2048]; // [rsp+A0h] [rbp-60h] BYREF

  v22 = a2;
  v21 = a1;
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_PropertyStore, 0, 1u, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( v4 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v27, 0x800u, "Failed to create IPropertyStore for ECP bus enumerator, 0x%x", v4) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v27);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v4);
    SystemError::Throw<long>((__int64)&byte_180018CBC, v4);
  }
  v23[2] = 0;
  v23[0] = 31;
  v23[1] = L"ECP_ROOT_BUS";
  v5 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, _QWORD *))(*(_QWORD *)ppv + 48LL))(ppv, qword_18001ABC8, v23);
  if ( v5 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v27,
                0x800u,
                "Failed to set PKEY_ECP_NOTIFY_ID for ECP bus enumerator while adding bus enumerator, 0x%x",
                v5) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v27);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v5);
    SystemError::Throw<long>((__int64)&byte_180018CBC, v5);
  }
  v6 = (EapHost::FDNotification *)(a1 + 2);
  *(_OWORD *)lpMem = 0;
  v26 = 0;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(
    lpMem,
    L"ECP_ROOT_BUS",
    0xCu);
  EapHost::FDNotification::SetUpWait(a1 + 2, v7, lpMem);
  if ( *((_QWORD *)&v26 + 1) > 7u )
    operator delete((void *)lpMem[0]);
  v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, LPVOID, _QWORD, _QWORD *))(*(_QWORD *)*a1 + 48LL))(
         *a1,
         L"ECP_ROOT_BUS",
         ppv,
         0,
         a2);
  v9 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v27, 0x800u, "AddBusEnumerator for ECP bus device returned 0x%x", v8) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v27[v12] );
    *(_QWORD *)&v26 = v27;
    *((_QWORD *)&v26 + 1) = (unsigned int)(v12 + 1);
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v10,
      v11,
      (__int64)lpMem);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v8);
  if ( !v8 || v8 == -2147483638 )
  {
    EapHost::FDNotification::WaitForNotification(v6, 1000 * *((_DWORD *)v21 + 24));
  }
  else
  {
    EapHost::FDNotification::StopWaiting(v6);
    if ( v8 != 1 )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
        && (int)StringCchPrintfA(v27, 0x800u, "AddBusEnumerator for adding ECP bus device is considered failure") >= 0
        && (byte_180020AC1 & 8) != 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v27);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids);
      SystemError::Throw<long>((__int64)&byte_180018CBC, v8);
    }
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v27, 0x800u, "The bus enumerator already exists when trying to create it") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v27[v15] );
      *(_QWORD *)&v26 = v27;
      *((_QWORD *)&v26 + 1) = (unsigned int)(v15 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v13,
        v14,
        (__int64)lpMem);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids);
  }
  v24[0] = 31;
  v24[2] = 0;
  v24[1] = L"ECPBus";
  v16 = (*(__int64 (__fastcall **)(_QWORD, const PROPERTYKEY *, _QWORD *))(*(_QWORD *)*v22 + 48LL))(
          *v22,
          &PKEY_Device_FriendlyName,
          v24);
  if ( v16 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v27,
                0x800u,
                "Failed to set PKEY_Device_FriendlyName while adding ECP bus enumerator, 0x%x",
                v16) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v27);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v16);
    SystemError::Throw<long>((__int64)&byte_180018CBC, v16);
  }
  result = EtwEventEnabled(eaphost_Context, DebugInfoEvent);
  if ( (_BYTE)result )
  {
    result = StringCchPrintfA(v27, 0x800u, "ECP bus enumerator successfully created");
    if ( (int)result >= 0 && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v9;
      while ( v27[v9] );
      *(_QWORD *)&v26 = v27;
      *((_QWORD *)&v26 + 1) = (unsigned int)(v9 + 1);
      result = McGenEventWrite_EtwEventWriteTransfer(
                 (unsigned int)&eaphost_Context,
                 (unsigned int)DebugInfoEvent,
                 v18,
                 v19,
                 (__int64)lpMem);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    result = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids);
  if ( ppv )
    return (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return result;
}

```

## disassembly

```asm
0x180011cb0  mov     [rsp-8+arg_10], rbx
0x180011cb5  push    rbp
0x180011cb6  push    rsi
0x180011cb7  push    rdi
0x180011cb8  push    r12
0x180011cba  push    r13
0x180011cbc  push    r14
0x180011cbe  push    r15
0x180011cc0  lea     rbp, [rsp-7B0h]
0x180011cc8  sub     rsp, 8B0h
0x180011ccf  mov     rax, cs:__security_cookie
0x180011cd6  xor     rax, rsp
0x180011cd9  mov     [rbp+7E0h+var_40], rax
0x180011ce0  mov     rdi, rdx
0x180011ce3  mov     [rsp+8E0h+var_8A0], rdx
0x180011ce8  mov     rbx, rcx
0x180011ceb  mov     [rsp+8E0h+var_8A8], rcx
0x180011cf0  mov     [rsp+8E0h+var_8B0], 0
0x180011cf9  lea     rax, [rsp+8E0h+var_8B0]
0x180011cfe  mov     [rsp+8E0h+ppv], rax; ppv
0x180011d03  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180011d0a  xor     edx, edx; pUnkOuter
0x180011d0c  lea     r8d, [rdx+1]; dwClsContext
0x180011d10  lea     rcx, CLSID_PropertyStore; rclsid
0x180011d17  call    cs:__imp_CoCreateInstance
0x180011d1d  mov     r15d, eax
0x180011d20  test    eax, eax
0x180011d22  jnz     loc_180012111
0x180011d28  xorps   xmm0, xmm0
0x180011d2b  xor     eax, eax
0x180011d2d  movups  [rsp+8E0h+var_898], xmm0
0x180011d32  mov     [rsp+8E0h+var_888], rax
0x180011d37  lea     eax, [r15+1Fh]
0x180011d3b  mov     word ptr [rsp+8E0h+var_898], ax
0x180011d40  lea     rsi, aEcpRootBus; "ECP_ROOT_BUS"
0x180011d47  mov     qword ptr [rsp+8E0h+var_898+8], rsi
0x180011d4c  mov     rcx, [rsp+8E0h+var_8B0]
0x180011d51  mov     rax, [rcx]
0x180011d54  lea     r8, [rsp+8E0h+var_898]
0x180011d59  lea     rdx, qword_18001ABC8
0x180011d60  mov     rax, [rax+30h]
0x180011d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d69  mov     r15d, eax
0x180011d6c  test    eax, eax
0x180011d6e  jnz     loc_1800121A6
0x180011d74  lea     r13, [rbx+10h]
0x180011d78  xorps   xmm0, xmm0
0x180011d7b  movups  xmmword ptr [rsp+8E0h+lpMem], xmm0
0x180011d80  xorps   xmm1, xmm1
0x180011d83  movdqu  [rbp+7E0h+var_858], xmm1
0x180011d88  lea     r8d, [rax+0Ch]
0x180011d8c  mov     rdx, rsi
0x180011d8f  lea     rcx, [rsp+8E0h+lpMem]
0x180011d94  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXQEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180011d99  nop
0x180011d9a  lea     r8, [rsp+8E0h+lpMem]
0x180011d9f  mov     rcx, r13
0x180011da2  call    ?SetUpWait@FDNotification@EapHost@@QEAAXW4tagQueryUpdateAction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapHost::FDNotification::SetUpWait(tagQueryUpdateAction,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180011da7  nop
0x180011da8  cmp     qword ptr [rbp+7E0h+var_858+8], 7
0x180011dad  jbe     short loc_180011DB9
0x180011daf  mov     rcx, [rsp+8E0h+lpMem]; lpMem
0x180011db4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011db9  mov     rcx, [rbx]
0x180011dbc  mov     rax, [rcx]
0x180011dbf  mov     [rsp+8E0h+ppv], rdi
0x180011dc4  xor     r9d, r9d
0x180011dc7  mov     r8, [rsp+8E0h+var_8B0]
0x180011dcc  mov     rdx, rsi
0x180011dcf  mov     rax, [rax+30h]
0x180011dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dd8  mov     r15d, eax
0x180011ddb  lea     rdx, DebugInfoEvent
0x180011de2  mov     rcx, cs:eaphost_Context
0x180011de9  call    cs:__imp_EtwEventEnabled
0x180011def  lea     rsi, eaphost_Context
0x180011df6  or      r12, 0FFFFFFFFFFFFFFFFh
0x180011dfa  xor     ebx, ebx
0x180011dfc  mov     r14d, 800h
0x180011e02  test    al, al
0x180011e04  jz      short loc_180011E60
0x180011e06  mov     r9d, r15d
0x180011e09  lea     r8, aAddbusenumerat_0; "AddBusEnumerator for ECP bus device ret"...
0x180011e10  mov     edx, r14d; unsigned __int64
0x180011e13  lea     rcx, [rbp+7E0h+var_840]; char *
0x180011e17  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011e1c  test    eax, eax
0x180011e1e  js      short loc_180011E60
0x180011e20  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x180011e26  jge     short loc_180011E60
0x180011e28  lea     rcx, [rbp+7E0h+var_840]
0x180011e2c  mov     rax, r12
0x180011e2f  inc     rax
0x180011e32  cmp     [rcx+rax], bl
0x180011e35  jnz     short loc_180011E2F
0x180011e37  inc     eax
0x180011e39  lea     rcx, [rbp+7E0h+var_840]
0x180011e3d  mov     qword ptr [rbp+7E0h+var_858], rcx
0x180011e41  mov     dword ptr [rbp+7E0h+var_858+8], eax
0x180011e44  mov     dword ptr [rbp+7E0h+var_858+0Ch], ebx
0x180011e47  lea     rax, [rsp+8E0h+lpMem]
0x180011e4c  mov     [rsp+8E0h+ppv], rax
0x180011e51  lea     rdx, DebugInfoEvent
0x180011e58  mov     rcx, rsi
0x180011e5b  call    McGenEventWrite_EtwEventWriteTransfer
0x180011e60  lea     rbx, WPP_GLOBAL_Control
0x180011e67  lea     rdi, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180011e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e75  cmp     rcx, rbx
0x180011e78  jz      short loc_180011E94
0x180011e7a  test    byte ptr [rcx+1Ch], 4
0x180011e7e  jz      short loc_180011E94
0x180011e80  mov     edx, 10h
0x180011e85  mov     r9d, r15d
0x180011e88  mov     r8, rdi
0x180011e8b  mov     rcx, [rcx+10h]
0x180011e8f  call    WPP_SF_d
0x180011e94  test    r15d, r15d
0x180011e97  jz      loc_180011F56
0x180011e9d  cmp     r15d, 8000000Ah
0x180011ea4  jz      loc_180011F56
0x180011eaa  mov     rcx, r13; this
0x180011ead  call    ?StopWaiting@FDNotification@EapHost@@QEAAXXZ; EapHost::FDNotification::StopWaiting(void)
0x180011eb2  mov     rcx, cs:eaphost_Context
0x180011eb9  cmp     r15d, 1
0x180011ebd  jnz     loc_18001223B
0x180011ec3  lea     rdx, DebugInfoEvent
0x180011eca  call    cs:__imp_EtwEventEnabled
0x180011ed0  xor     r13d, r13d
0x180011ed3  test    al, al
0x180011ed5  jz      short loc_180011F31
0x180011ed7  lea     r8, aTheBusEnumerat; "The bus enumerator already exists when "...
0x180011ede  mov     rdx, r14; unsigned __int64
0x180011ee1  lea     rcx, [rbp+7E0h+var_840]; char *
0x180011ee5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011eea  test    eax, eax
0x180011eec  js      short loc_180011F31
0x180011eee  cmp     cs:Microsoft_Windows_EapHostEnableBits, r13b
0x180011ef5  jge     short loc_180011F31
0x180011ef7  lea     rcx, [rbp+7E0h+var_840]
0x180011efb  mov     rax, r12
0x180011efe  inc     rax
0x180011f01  cmp     [rcx+rax], r13b
0x180011f05  jnz     short loc_180011EFE
0x180011f07  inc     eax
0x180011f09  lea     rcx, [rbp+7E0h+var_840]
0x180011f0d  mov     qword ptr [rbp+7E0h+var_858], rcx
0x180011f11  mov     dword ptr [rbp+7E0h+var_858+8], eax
0x180011f14  mov     dword ptr [rbp+7E0h+var_858+0Ch], r13d
0x180011f18  lea     rax, [rsp+8E0h+lpMem]
0x180011f1d  mov     [rsp+8E0h+ppv], rax
0x180011f22  lea     rdx, DebugInfoEvent
0x180011f29  mov     rcx, rsi
0x180011f2c  call    McGenEventWrite_EtwEventWriteTransfer
0x180011f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f38  cmp     rcx, rbx
0x180011f3b  jz      short loc_180011F6D
0x180011f3d  test    byte ptr [rcx+1Ch], 4
0x180011f41  jz      short loc_180011F6D
0x180011f43  mov     edx, 11h
0x180011f48  mov     r8, rdi
0x180011f4b  mov     rcx, [rcx+10h]
0x180011f4f  call    WPP_SF_
0x180011f54  jmp     short loc_180011F6D
0x180011f56  mov     rax, [rsp+8E0h+var_8A8]
0x180011f5b  imul    edx, [rax+60h], 3E8h; dwMilliseconds
0x180011f62  mov     rcx, r13; this
0x180011f65  call    ?WaitForNotification@FDNotification@EapHost@@QEAAXI@Z; EapHost::FDNotification::WaitForNotification(uint)
0x180011f6a  xor     r13d, r13d
0x180011f6d  xorps   xmm0, xmm0
0x180011f70  xor     eax, eax
0x180011f72  movups  [rsp+8E0h+var_880], xmm0
0x180011f77  mov     [rsp+8E0h+var_870], rax
0x180011f7c  mov     eax, 1Fh
0x180011f81  mov     word ptr [rsp+8E0h+var_880], ax
0x180011f86  lea     rax, aEcpbus; "ECPBus"
0x180011f8d  mov     qword ptr [rsp+8E0h+var_880+8], rax
0x180011f92  mov     rcx, [rsp+8E0h+var_8A0]
0x180011f97  mov     rcx, [rcx]
0x180011f9a  mov     rax, [rcx]
0x180011f9d  lea     r8, [rsp+8E0h+var_880]
0x180011fa2  lea     rdx, PKEY_Device_FriendlyName
0x180011fa9  mov     rax, [rax+30h]
0x180011fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fb2  mov     r15d, eax
0x180011fb5  mov     rcx, cs:eaphost_Context
0x180011fbc  test    eax, eax
0x180011fbe  jnz     loc_180012094
0x180011fc4  lea     rdx, DebugInfoEvent
0x180011fcb  call    cs:__imp_EtwEventEnabled
0x180011fd1  test    al, al
0x180011fd3  jz      short loc_18001202F
0x180011fd5  lea     r8, aEcpBusEnumerat_1; "ECP bus enumerator successfully created"
0x180011fdc  mov     rdx, r14; unsigned __int64
0x180011fdf  lea     rcx, [rbp+7E0h+var_840]; char *
0x180011fe3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011fe8  test    eax, eax
0x180011fea  js      short loc_18001202F
0x180011fec  cmp     cs:Microsoft_Windows_EapHostEnableBits, r13b
0x180011ff3  jge     short loc_18001202F
0x180011ff5  lea     rax, [rbp+7E0h+var_840]
0x180011ff9  inc     r12
0x180011ffc  cmp     [rax+r12], r13b
0x180012000  jnz     short loc_180011FF9
0x180012002  lea     eax, [r12+1]
0x180012007  lea     rcx, [rbp+7E0h+var_840]
0x18001200b  mov     qword ptr [rbp+7E0h+var_858], rcx
0x18001200f  mov     dword ptr [rbp+7E0h+var_858+8], eax
0x180012012  mov     dword ptr [rbp+7E0h+var_858+0Ch], r13d
0x180012016  lea     rax, [rsp+8E0h+lpMem]
0x18001201b  mov     [rsp+8E0h+ppv], rax
0x180012020  lea     rdx, DebugInfoEvent
0x180012027  mov     rcx, rsi
0x18001202a  call    McGenEventWrite_EtwEventWriteTransfer
0x18001202f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012036  cmp     rcx, rbx
0x180012039  jz      short loc_180012053
0x18001203b  test    byte ptr [rcx+1Ch], 4
0x18001203f  jz      short loc_180012053
0x180012041  mov     edx, 14h
0x180012046  mov     r8, rdi
0x180012049  mov     rcx, [rcx+10h]
0x18001204d  call    WPP_SF_
0x180012052  nop
0x180012053  mov     rcx, [rsp+8E0h+var_8B0]
0x180012058  test    rcx, rcx
0x18001205b  jz      short loc_18001206A
0x18001205d  mov     rax, [rcx]
0x180012060  mov     rax, [rax+10h]
0x180012064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012069  nop
0x18001206a  mov     rcx, [rbp+7E0h+var_40]
0x180012071  xor     rcx, rsp; StackCookie
0x180012074  call    __security_check_cookie
0x180012079  mov     rbx, [rsp+8E0h+arg_10]
0x180012081  add     rsp, 8B0h
0x180012088  pop     r15
0x18001208a  pop     r14
0x18001208c  pop     r13
0x18001208e  pop     r12
0x180012090  pop     rdi
0x180012091  pop     rsi
0x180012092  pop     rbp
0x180012093  retn
0x180012094  lea     rdx, DebugErrorEvent
0x18001209b  call    cs:__imp_EtwEventEnabled
0x1800120a1  test    al, al
0x1800120a3  jz      short loc_1800120DB
0x1800120a5  mov     r9d, r15d
0x1800120a8  lea     r8, aFailedToSetPke; "Failed to set PKEY_Device_FriendlyName "...
0x1800120af  mov     rdx, r14; unsigned __int64
0x1800120b2  lea     rcx, [rbp+7E0h+var_840]; char *
0x1800120b6  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800120bb  test    eax, eax
0x1800120bd  js      short loc_1800120DB
0x1800120bf  test    cs:byte_180020AC1, 8
0x1800120c6  jz      short loc_1800120DB
0x1800120c8  lea     r8, [rbp+7E0h+var_840]
0x1800120cc  lea     rdx, DebugErrorEvent
0x1800120d3  mov     rcx, rsi
0x1800120d6  call    McTemplateU0s_EtwEventWriteTransfer
0x1800120db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120e2  cmp     rcx, rbx
0x1800120e5  jz      short loc_180012101
0x1800120e7  test    byte ptr [rcx+1Ch], 1
0x1800120eb  jz      short loc_180012101
0x1800120ed  mov     edx, 13h
0x1800120f2  mov     r9d, r15d
0x1800120f5  mov     r8, rdi
0x1800120f8  mov     rcx, [rcx+10h]
0x1800120fc  call    WPP_SF_d
0x180012101  mov     edx, r15d
0x180012104  lea     rcx, byte_180018CBC
0x18001210b  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
0x180012111  lea     rdx, DebugErrorEvent
0x180012118  mov     rcx, cs:eaphost_Context
0x18001211f  call    cs:__imp_EtwEventEnabled
0x180012125  test    al, al
0x180012127  jz      short loc_180012165
0x180012129  mov     r9d, r15d
0x18001212c  lea     r8, aFailedToCreate; "Failed to create IPropertyStore for ECP"...
0x180012133  mov     edx, 800h; unsigned __int64
0x180012138  lea     rcx, [rbp+7E0h+var_840]; char *
0x18001213c  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180012141  test    eax, eax
0x180012143  js      short loc_180012165
0x180012145  test    cs:byte_180020AC1, 8
0x18001214c  jz      short loc_180012165
0x18001214e  lea     r8, [rbp+7E0h+var_840]
0x180012152  lea     rdx, DebugErrorEvent
0x180012159  lea     rcx, eaphost_Context
0x180012160  call    McTemplateU0s_EtwEventWriteTransfer
0x180012165  lea     rbx, WPP_GLOBAL_Control
0x18001216c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012173  cmp     rcx, rbx
0x180012176  jz      short loc_180012196
0x180012178  test    byte ptr [rcx+1Ch], 1
0x18001217c  jz      short loc_180012196
0x18001217e  mov     edx, 0Eh
0x180012183  mov     r9d, r15d
  ... truncated ...
```
