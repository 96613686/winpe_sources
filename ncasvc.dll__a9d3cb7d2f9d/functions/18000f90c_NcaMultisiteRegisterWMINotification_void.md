# NcaMultisiteRegisterWMINotification(void)

- ea: `0x18000f90c`
- end: `0x18000fbb1`
- name: `?NcaMultisiteRegisterWMINotification@@YAJXZ`
- size: `677`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000fcf0`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x18000f8a8`
- `0x18000f90c`
- `0x18000fbb8`
- `0x18001abd4`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f94d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f94d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000fa86`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000fa86`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fb70`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fb70`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f9ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f9ac`

## pseudocode

```c
__int64 NcaMultisiteRegisterWMINotification(void)
{
  HRESULT Instance; // eax
  unsigned int v1; // ebx
  int v2; // edi
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  NcaMultisiteEventSink *v6; // rax
  NcaMultisiteEventSink *v7; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c712b148f8e73543b156b8659e2c9e82_Traceguids);
  Instance = CoInitializeEx(0, 0);
  v1 = Instance;
  if ( Instance >= 0 )
  {
    v2 = 1;
    Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &gNcaMultisiteTriggerComp);
    v1 = Instance;
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)gNcaMultisiteTriggerComp + 24LL))(
                   gNcaMultisiteTriggerComp,
                   L"root\\StandardCimv2",
                   0,
                   0,
                   0,
                   0,
                   0,
                   0,
                   &pProxy);
      v1 = Instance;
      if ( Instance >= 0 )
      {
        CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
        v6 = (NcaMultisiteEventSink *)NcaAlloc(16);
        if ( v6 )
        {
          v7 = NcaMultisiteEventSink::NcaMultisiteEventSink(v6);
          qword_180028F18 = (__int64)v7;
        }
        else
        {
          v7 = 0;
          qword_180028F18 = 0;
        }
        if ( v7 )
        {
          (*(void (__fastcall **)(NcaMultisiteEventSink *))(*(_QWORD *)v7 + 8LL))(v7);
          Instance = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, const wchar_t *, __int64, _QWORD, __int64))pProxy->lpVtbl[7].Release)(
                       pProxy,
                       L"WQL",
                       L"SELECT * FROM MSFT_DASettingsIndication",
                       128,
                       0,
                       qword_180028F18);
          v1 = Instance;
          if ( Instance >= 0 )
          {
            if ( !Instance )
            {
LABEL_31:
              CoUninitialize();
              goto LABEL_32;
            }
          }
          else
          {
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v4 = 15;
              goto LABEL_8;
            }
          }
        }
        else
        {
          v1 = -2147024882;
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v4 = 14;
            v5 = 2147942414LL;
            goto LABEL_24;
          }
        }
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v4 = 13;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 12;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v2 = 0;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 11;
LABEL_8:
      v5 = (unsigned int)Instance;
LABEL_24:
      WPP_SF_d(v3[2], v4, WPP_c712b148f8e73543b156b8659e2c9e82_Traceguids, v5);
    }
  }
  NcaMultisiteUnregisterWMINotification();
  if ( v2 == 1 )
    goto LABEL_31;
LABEL_32:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c712b148f8e73543b156b8659e2c9e82_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18000f90c  push    rbx
0x18000f90e  push    rbp
0x18000f90f  push    rdi
0x18000f910  push    r14
0x18000f912  push    r15
0x18000f914  sub     rsp, 50h
0x18000f918  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f91f  lea     r14, WPP_GLOBAL_Control
0x18000f926  lea     r15, WPP_c712b148f8e73543b156b8659e2c9e82_Traceguids
0x18000f92d  cmp     rcx, r14
0x18000f930  jz      short loc_18000F949
0x18000f932  test    byte ptr [rcx+1Ch], 8
0x18000f936  jz      short loc_18000F949
0x18000f938  mov     rcx, [rcx+10h]
0x18000f93c  mov     edx, 0Ah
0x18000f941  mov     r8, r15
0x18000f944  call    WPP_SF_
0x18000f949  xor     edx, edx; dwCoInit
0x18000f94b  xor     ecx, ecx; pvReserved
0x18000f94d  call    cs:__imp_CoInitializeEx
0x18000f954  nop     dword ptr [rax+rax+00h]
0x18000f959  mov     ebx, eax
0x18000f95b  mov     ebp, 1
0x18000f960  test    eax, eax
0x18000f962  jns     short loc_18000F98B
0x18000f964  xor     edi, edi
0x18000f966  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f96d  cmp     rcx, r14
0x18000f970  jz      loc_18000FB67
0x18000f976  test    [rcx+1Ch], bpl
0x18000f97a  jz      loc_18000FB67
0x18000f980  lea     edx, [rbp+0Ah]
0x18000f983  mov     r9d, eax
0x18000f986  jmp     loc_18000FAEA
0x18000f98b  lea     rax, ?gNcaMultisiteTriggerComp@@3UNCA_MULTISITE_TRIGGER_COMP_@@A; NCA_MULTISITE_TRIGGER_COMP_ gNcaMultisiteTriggerComp
0x18000f992  mov     r8d, ebp; dwClsContext
0x18000f995  lea     r9, IID_IWbemLocator; riid
0x18000f99c  mov     [rsp+78h+ppv], rax; ppv
0x18000f9a1  xor     edx, edx; pUnkOuter
0x18000f9a3  lea     rcx, CLSID_WbemLocator; rclsid
0x18000f9aa  mov     edi, ebp
0x18000f9ac  call    cs:__imp_CoCreateInstance
0x18000f9b3  nop     dword ptr [rax+rax+00h]
0x18000f9b8  mov     ebx, eax
0x18000f9ba  test    eax, eax
0x18000f9bc  jns     short loc_18000F9DF
0x18000f9be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9c5  cmp     rcx, r14
0x18000f9c8  jz      loc_18000FB67
0x18000f9ce  test    [rcx+1Ch], bpl
0x18000f9d2  jz      loc_18000FB67
0x18000f9d8  mov     edx, 0Ch
0x18000f9dd  jmp     short loc_18000F983
0x18000f9df  mov     rcx, cs:?gNcaMultisiteTriggerComp@@3UNCA_MULTISITE_TRIGGER_COMP_@@A; NCA_MULTISITE_TRIGGER_COMP_ gNcaMultisiteTriggerComp
0x18000f9e6  lea     rdx, pProxy
0x18000f9ed  mov     [rsp+78h+var_38], rdx
0x18000f9f2  xor     r9d, r9d
0x18000f9f5  mov     qword ptr [rsp+78h+dwCapabilities], 0
0x18000f9fe  lea     rdx, aRootStandardci; "root\\StandardCimv2"
0x18000fa05  mov     [rsp+78h+pAuthInfo], 0
0x18000fa0e  xor     r8d, r8d
0x18000fa11  mov     rax, [rcx]
0x18000fa14  mov     [rsp+78h+dwImpLevel], 0
0x18000fa1c  mov     [rsp+78h+ppv], 0
0x18000fa25  mov     rax, [rax+18h]
0x18000fa29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa2e  mov     ebx, eax
0x18000fa30  test    eax, eax
0x18000fa32  jns     short loc_18000FA58
0x18000fa34  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa3b  cmp     rcx, r14
0x18000fa3e  jz      loc_18000FB67
0x18000fa44  test    [rcx+1Ch], bpl
0x18000fa48  jz      loc_18000FB67
0x18000fa4e  mov     edx, 0Dh
0x18000fa53  jmp     loc_18000F983
0x18000fa58  mov     rcx, cs:pProxy; pProxy
0x18000fa5f  mov     eax, 3
0x18000fa64  mov     [rsp+78h+dwCapabilities], 0; dwCapabilities
0x18000fa6c  xor     r9d, r9d; pServerPrincName
0x18000fa6f  mov     [rsp+78h+pAuthInfo], 0; pAuthInfo
0x18000fa78  xor     r8d, r8d; dwAuthzSvc
0x18000fa7b  mov     [rsp+78h+dwImpLevel], eax; dwImpLevel
0x18000fa7f  lea     edx, [rax+7]; dwAuthnSvc
0x18000fa82  mov     dword ptr [rsp+78h+ppv], eax; dwAuthnLevel
0x18000fa86  call    cs:__imp_CoSetProxyBlanket
0x18000fa8d  nop     dword ptr [rax+rax+00h]
0x18000fa92  mov     ecx, 10h
0x18000fa97  call    NcaAlloc
0x18000fa9c  test    rax, rax
0x18000fa9f  jz      short loc_18000FAB5
0x18000faa1  mov     rcx, rax; this
0x18000faa4  call    ??0NcaMultisiteEventSink@@QEAA@XZ; NcaMultisiteEventSink::NcaMultisiteEventSink(void)
0x18000faa9  mov     rcx, rax
0x18000faac  mov     cs:qword_180028F18, rax
0x18000fab3  jmp     short loc_18000FABE
0x18000fab5  xor     ecx, ecx
0x18000fab7  mov     cs:qword_180028F18, rcx
0x18000fabe  test    rcx, rcx
0x18000fac1  jnz     short loc_18000FAF8
0x18000fac3  mov     ebx, 8007000Eh
0x18000fac8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000facf  cmp     rcx, r14
0x18000fad2  jz      loc_18000FB67
0x18000fad8  test    [rcx+1Ch], bpl
0x18000fadc  jz      loc_18000FB67
0x18000fae2  mov     edx, 0Eh
0x18000fae7  mov     r9d, ebx
0x18000faea  mov     rcx, [rcx+10h]
0x18000faee  mov     r8, r15
0x18000faf1  call    WPP_SF_d
0x18000faf6  jmp     short loc_18000FB67
0x18000faf8  mov     rax, [rcx]
0x18000fafb  mov     rax, [rax+8]
0x18000faff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb04  mov     rdx, cs:qword_180028F18
0x18000fb0b  lea     r8, aSelectFromMsft_0; "SELECT * FROM MSFT_DASettingsIndication"
0x18000fb12  mov     rcx, cs:pProxy
0x18000fb19  mov     r9d, 80h
0x18000fb1f  mov     qword ptr [rsp+78h+dwImpLevel], rdx
0x18000fb24  lea     rdx, aWql; "WQL"
0x18000fb2b  mov     [rsp+78h+ppv], 0
0x18000fb34  mov     rax, [rcx]
0x18000fb37  mov     rax, [rax+0B8h]
0x18000fb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb43  mov     ebx, eax
0x18000fb45  test    eax, eax
0x18000fb47  jns     short loc_18000FB65
0x18000fb49  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb50  cmp     rcx, r14
0x18000fb53  jz      short loc_18000FB67
0x18000fb55  test    [rcx+1Ch], bpl
0x18000fb59  jz      short loc_18000FB67
0x18000fb5b  mov     edx, 0Fh
0x18000fb60  jmp     loc_18000F983
0x18000fb65  jz      short loc_18000FB70
0x18000fb67  call    ?NcaMultisiteUnregisterWMINotification@@YAJXZ; NcaMultisiteUnregisterWMINotification(void)
0x18000fb6c  cmp     edi, ebp
0x18000fb6e  jnz     short loc_18000FB7C
0x18000fb70  call    cs:__imp_CoUninitialize
0x18000fb77  nop     dword ptr [rax+rax+00h]
0x18000fb7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb83  cmp     rcx, r14
0x18000fb86  jz      short loc_18000FBA2
0x18000fb88  test    byte ptr [rcx+1Ch], 8
0x18000fb8c  jz      short loc_18000FBA2
0x18000fb8e  mov     rcx, [rcx+10h]
0x18000fb92  mov     edx, 10h
0x18000fb97  mov     r9d, ebx
0x18000fb9a  mov     r8, r15
0x18000fb9d  call    WPP_SF_d
0x18000fba2  mov     eax, ebx
0x18000fba4  add     rsp, 50h
0x18000fba8  pop     r15
0x18000fbaa  pop     r14
0x18000fbac  pop     rdi
0x18000fbad  pop     rbp
0x18000fbae  pop     rbx
0x18000fbaf  retn
```
