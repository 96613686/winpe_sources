# _LCIEBrokerRedirectUrlThreadProc

- ea: `0x1808cee80`
- end: `0x1808cf197`
- name: `_LCIEBrokerRedirectUrlThreadProc`
- size: `791`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180773a20`
- `0x1808ca524`
- `0x1808cee80`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1808cef6e`
- `KERNEL32!GetCurrentProcessId` at `0x1808cef6e`
- `USER32!AllowSetForegroundWindow` at `0x1808cef48`
- `USER32!AllowSetForegroundWindow` at `0x1808cf04f`
- `USER32!AllowSetForegroundWindow` at `0x1808cef48`
- `USER32!AllowSetForegroundWindow` at `0x1808cf04f`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1808cf011`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1808cf011`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808cefa0`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808cefa0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808ceeda`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808cefdf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808ceeda`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808cefdf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1808cf15a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1808cf15a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1808ceeaf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1808ceeaf`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808cefaf`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808cefaf`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808cef82`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808cef82`

## pseudocode

```c
__int64 __fastcall LCIEBrokerRedirectUrlThreadProc(_QWORD *Parameter)
{
  unsigned int v2; // edx
  IStream *v3; // rcx
  HRESULT InterfaceAndReleaseStream; // eax
  DWORD v5; // edi
  char Integrity; // al
  struct IE_GLOBAL_THREAD_STATE *v7; // rax
  IStream *v8; // rcx
  __int128 v9; // xmm0
  unsigned int v10; // ecx
  int v11; // edi
  DWORD dwProcessId; // [rsp+30h] [rbp-59h] BYREF
  struct IEUserBroker *v14; // [rsp+38h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-49h] BYREF
  __int64 v16; // [rsp+48h] [rbp-41h] BYREF
  __int64 v17; // [rsp+50h] [rbp-39h] BYREF
  LPVOID v18; // [rsp+58h] [rbp-31h] BYREF
  __int128 v19; // [rsp+60h] [rbp-29h] BYREF
  __int64 v20; // [rsp+70h] [rbp-19h]
  _DWORD v21[13]; // [rsp+80h] [rbp-9h] BYREF
  __int128 v22; // [rsp+B4h] [rbp+2Bh]

  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    v3 = (IStream *)Parameter[3];
    ppv = 0;
    InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v3, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
    Parameter[3] = 0;
    if ( InterfaceAndReleaseStream >= 0 )
    {
      v20 = 0;
      v19 = 0;
      LOWORD(v19) = 11;
      WORD4(v19) = -1;
      g_pfn_IUnknown_Exec((_DWORD)ppv, (unsigned int)&CGID_DocHostCmdPriv, 15, 0, (__int64)&v19, 0);
      v5 = -1;
      AllowSetForegroundWindow(0xFFFFFFFF);
      memset_0(v21, 0, 0x44u);
      v21[0] = *(_DWORD *)Parameter;
      v21[1] = *((_DWORD *)Parameter + 1);
      v21[6] = GetCurrentProcessId();
      Integrity = IsoGetIntegrity(1);
      v21[8] = 0;
      v21[7] = Integrity & 0x7F;
      v21[10] = IEConfiguration_GetDWORD(536870929);
      v7 = GlobalThreadState();
      v8 = (IStream *)Parameter[4];
      v9 = *(_OWORD *)v7;
      v18 = 0;
      v22 = v9;
      if ( v8 )
      {
        CoGetInterfaceAndReleaseStream(v8, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &v18);
        Parameter[4] = 0;
      }
      v10 = *((_DWORD *)Parameter + 4);
      v21[4] = 1;
      v17 = 0;
      v14 = 0;
      if ( (int)CoCreateUserBrokerForThread(v10, &v14) >= 0 )
      {
        dwProcessId = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v14 + 24LL))(
          v14,
          0,
          0,
          &dwProcessId);
        if ( dwProcessId )
          v5 = dwProcessId;
        AllowSetForegroundWindow(v5);
        v16 = 0;
        v11 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v14 + 48LL))(
                v14,
                &CLSID_CShdocvwBroker,
                &IID_IUnknown,
                &v16);
        if ( v11 >= 0 )
        {
          v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(v16, &IID_IShdocvwBroker, &v17);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v11 >= 0 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD *, LPVOID))(*(_QWORD *)v17 + 24LL))(
            v17,
            Parameter[1],
            *((unsigned int *)Parameter + 1),
            v21,
            v18);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
      WORD4(v19) = 0;
      g_pfn_IUnknown_Exec((_DWORD)ppv, (unsigned int)&CGID_DocHostCmdPriv, 15, 0, (__int64)&v19, 0);
      if ( v18 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
  if ( Parameter )
    LCIESRedirectUrlInfo::`scalar deleting destructor'((LCIESRedirectUrlInfo *)Parameter, v2);
  return 0;
}

```

## disassembly

```asm
0x1808cee80  mov     [rsp-8+arg_8], rbx
0x1808cee85  mov     [rsp-8+arg_10], rdi
0x1808cee8a  push    rbp
0x1808cee8b  lea     rbp, [rsp-57h]
0x1808cee90  sub     rsp, 0E0h
0x1808cee97  mov     rax, cs:__security_cookie
0x1808cee9e  xor     rax, rsp
0x1808ceea1  mov     [rbp+57h+var_10], rax
0x1808ceea5  mov     rbx, rcx
0x1808ceea8  mov     edx, 2; dwCoInit
0x1808ceead  xor     ecx, ecx; pvReserved
0x1808ceeaf  call    cs:__imp_CoInitializeEx
0x1808ceeb6  nop     dword ptr [rax+rax+00h]
0x1808ceebb  test    eax, eax
0x1808ceebd  js      loc_1808CF166
0x1808ceec3  mov     rcx, [rbx+18h]; pStm
0x1808ceec7  lea     r8, [rbp+57h+ppv]; ppv
0x1808ceecb  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x1808ceed2  mov     [rbp+57h+ppv], 0
0x1808ceeda  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1808ceee1  nop     dword ptr [rax+rax+00h]
0x1808ceee6  mov     qword ptr [rbx+18h], 0
0x1808ceeee  test    eax, eax
0x1808ceef0  js      loc_1808CF15A
0x1808ceef6  mov     rcx, [rbp+57h+ppv]
0x1808ceefa  lea     rdx, CGID_DocHostCmdPriv
0x1808cef01  xor     eax, eax
0x1808cef03  mov     [rsp+0E0h+var_B8], 0
0x1808cef0c  mov     [rbp+57h+var_70], rax
0x1808cef10  xorps   xmm0, xmm0
0x1808cef13  mov     eax, 0Bh
0x1808cef18  xor     r9d, r9d
0x1808cef1b  movups  [rbp+57h+var_80], xmm0
0x1808cef1f  mov     word ptr [rbp+57h+var_80], ax
0x1808cef23  or      eax, 0FFFFFFFFh
0x1808cef26  mov     word ptr [rbp+57h+var_80+8], ax
0x1808cef2a  lea     rax, [rbp+57h+var_80]
0x1808cef2e  lea     r8d, [r9+0Fh]
0x1808cef32  mov     [rsp+0E0h+var_C0], rax
0x1808cef37  call    cs:g_pfn_IUnknown_Exec
0x1808cef3e  nop     dword ptr [rax+rax+00h]
0x1808cef43  or      edi, 0FFFFFFFFh
0x1808cef46  mov     ecx, edi; dwProcessId
0x1808cef48  call    cs:__imp_AllowSetForegroundWindow
0x1808cef4f  nop     dword ptr [rax+rax+00h]
0x1808cef54  xor     edx, edx; Val
0x1808cef56  lea     rcx, [rbp+57h+var_60]; void *
0x1808cef5a  lea     r8d, [rdx+44h]; Size
0x1808cef5e  call    memset_0
0x1808cef63  mov     eax, [rbx]
0x1808cef65  mov     [rbp+57h+var_60], eax
0x1808cef68  mov     eax, [rbx+4]
0x1808cef6b  mov     [rbp+57h+var_5C], eax
0x1808cef6e  call    cs:__imp_GetCurrentProcessId
0x1808cef75  nop     dword ptr [rax+rax+00h]
0x1808cef7a  mov     ecx, 1
0x1808cef7f  mov     [rbp+57h+var_48], eax
0x1808cef82  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1808cef89  nop     dword ptr [rax+rax+00h]
0x1808cef8e  mov     ecx, 20000011h
0x1808cef93  mov     [rbp+57h+var_40], 0
0x1808cef9a  and     eax, 7Fh
0x1808cef9d  mov     [rbp+57h+var_44], eax
0x1808cefa0  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1808cefa7  nop     dword ptr [rax+rax+00h]
0x1808cefac  mov     [rbp+57h+var_38], eax
0x1808cefaf  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808cefb6  nop     dword ptr [rax+rax+00h]
0x1808cefbb  mov     rcx, [rbx+20h]; pStm
0x1808cefbf  movups  xmm0, xmmword ptr [rax]
0x1808cefc2  mov     [rbp+57h+var_88], 0
0x1808cefca  movdqu  [rbp+57h+var_2C], xmm0
0x1808cefcf  test    rcx, rcx
0x1808cefd2  jz      short loc_1808CEFF3
0x1808cefd4  lea     r8, [rbp+57h+var_88]; ppv
0x1808cefd8  lea     rdx, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; iid
0x1808cefdf  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1808cefe6  nop     dword ptr [rax+rax+00h]
0x1808cefeb  mov     qword ptr [rbx+20h], 0
0x1808ceff3  mov     ecx, [rbx+10h]
0x1808ceff6  lea     rdx, [rbp+57h+var_A8]
0x1808ceffa  mov     [rbp+57h+var_50], 1
0x1808cf001  mov     [rbp+57h+var_90], 0
0x1808cf009  mov     [rbp+57h+var_A8], 0
0x1808cf011  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1808cf018  nop     dword ptr [rax+rax+00h]
0x1808cf01d  test    eax, eax
0x1808cf01f  js      loc_1808CF103
0x1808cf025  mov     rcx, [rbp+57h+var_A8]
0x1808cf029  lea     r9, [rbp+57h+dwProcessId]
0x1808cf02d  mov     [rbp+57h+dwProcessId], 0
0x1808cf034  xor     r8d, r8d
0x1808cf037  xor     edx, edx
0x1808cf039  mov     rax, [rcx]
0x1808cf03c  mov     rax, [rax+18h]
0x1808cf040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cf045  mov     eax, [rbp+57h+dwProcessId]
0x1808cf048  test    eax, eax
0x1808cf04a  cmovnz  edi, eax
0x1808cf04d  mov     ecx, edi; dwProcessId
0x1808cf04f  call    cs:__imp_AllowSetForegroundWindow
0x1808cf056  nop     dword ptr [rax+rax+00h]
0x1808cf05b  mov     rcx, [rbp+57h+var_A8]
0x1808cf05f  lea     r9, [rbp+57h+var_98]
0x1808cf063  mov     [rbp+57h+var_98], 0
0x1808cf06b  lea     r8, IID_IUnknown
0x1808cf072  lea     rdx, CLSID_CShdocvwBroker
0x1808cf079  mov     rax, [rcx]
0x1808cf07c  mov     rax, [rax+30h]
0x1808cf080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cf085  mov     edi, eax
0x1808cf087  test    eax, eax
0x1808cf089  js      short loc_1808CF0B7
0x1808cf08b  mov     rcx, [rbp+57h+var_98]
0x1808cf08f  lea     r8, [rbp+57h+var_90]
0x1808cf093  lea     rdx, IID_IShdocvwBroker
0x1808cf09a  mov     rax, [rcx]
0x1808cf09d  mov     rax, [rax]
0x1808cf0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cf0a5  mov     rcx, [rbp+57h+var_98]
0x1808cf0a9  mov     edi, eax
0x1808cf0ab  mov     rax, [rcx]
0x1808cf0ae  mov     rax, [rax+10h]
0x1808cf0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cf0b7  mov     rcx, [rbp+57h+var_A8]
0x1808cf0bb  mov     rax, [rcx]
0x1808cf0be  mov     rax, [rax+10h]
0x1808cf0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cf0c7  test    edi, edi
0x1808cf0c9  js      short loc_1808CF103
0x1808cf0cb  mov     r10, [rbp+57h+var_90]
0x1808cf0cf  lea     r9, [rbp+57h+var_60]
0x1808cf0d3  mov     rcx, [rbp+57h+var_88]
0x1808cf0d7  mov     r8d, [rbx+4]
0x1808cf0db  mov     rdx, [rbx+8]
0x1808cf0df  mov     rax, [r10]
0x1808cf0e2  mov     [rsp+0E0h+var_C0], rcx
0x1808cf0e7  mov     rcx, r10
0x1808cf0ea  mov     rax, [rax+18h]
0x1808cf0ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cf0f3  mov     rcx, [rbp+57h+var_90]
0x1808cf0f7  mov     rax, [rcx]
0x1808cf0fa  mov     rax, [rax+10h]
0x1808cf0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cf103  mov     rcx, [rbp+57h+ppv]
0x1808cf107  lea     rdx, CGID_DocHostCmdPriv
0x1808cf10e  xor     eax, eax
0x1808cf110  xor     r9d, r9d
0x1808cf113  mov     [rsp+0E0h+var_B8], rax
0x1808cf118  mov     word ptr [rbp+57h+var_80+8], ax
0x1808cf11c  lea     rax, [rbp+57h+var_80]
0x1808cf120  mov     [rsp+0E0h+var_C0], rax
0x1808cf125  lea     r8d, [r9+0Fh]
0x1808cf129  call    cs:g_pfn_IUnknown_Exec
0x1808cf130  nop     dword ptr [rax+rax+00h]
0x1808cf135  mov     rcx, [rbp+57h+var_88]
0x1808cf139  test    rcx, rcx
0x1808cf13c  jz      short loc_1808CF14A
0x1808cf13e  mov     rax, [rcx]
0x1808cf141  mov     rax, [rax+10h]
0x1808cf145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cf14a  mov     rcx, [rbp+57h+ppv]
0x1808cf14e  mov     rax, [rcx]
0x1808cf151  mov     rax, [rax+10h]
0x1808cf155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cf15a  call    cs:__imp_CoUninitialize
0x1808cf161  nop     dword ptr [rax+rax+00h]
0x1808cf166  test    rbx, rbx
0x1808cf169  jz      short loc_1808CF173
0x1808cf16b  mov     rcx, rbx; this
0x1808cf16e  call    ??_GLCIESRedirectUrlInfo@@QEAAPEAXI@Z; LCIESRedirectUrlInfo::`scalar deleting destructor'(uint)
0x1808cf173  xor     eax, eax
0x1808cf175  mov     rcx, [rbp+57h+var_10]
0x1808cf179  xor     rcx, rsp; StackCookie
0x1808cf17c  call    __security_check_cookie
0x1808cf181  lea     r11, [rsp+0E0h+var_s0]
0x1808cf189  mov     rbx, [r11+18h]
0x1808cf18d  mov     rdi, [r11+20h]
0x1808cf191  mov     rsp, r11
0x1808cf194  pop     rbp
0x1808cf195  retn
```
