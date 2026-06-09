# NcaEvCollIPHTTPsCertInitialize(void)

- ea: `0x180014b80`
- end: `0x180014d16`
- name: `?NcaEvCollIPHTTPsCertInitialize@@YAJXZ`
- size: `406`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002d50`
- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x180014b80`
- `0x180014d20`
- `0x180014ea0`
- `0x180016678`
- `0x180018ffc`
- `0x18001a38c`
- `0x18001cc3e`

## string_xrefs

- `0x180014c34`: `SYSTEM\CurrentControlSet\Services\iphlpsvc\Parameters\IPHTTPS\IPHTTPSInterface`

## pseudocode

```c
__int64 NcaEvCollIPHTTPsCertInitialize(void)
{
  PVOID v0; // rcx
  int v1; // eax
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int IsCertError; // eax
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v12; // [rsp+20h] [rbp-48h]

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_8db24c4892c836aea10a5a876d8eb362_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v0, ModuleInitializeStart, L"EvCollIPHTTPsCert");
  memset_0(&gNcaEvCollIphttpsCert, 0, 0x50u);
  v1 = NcaCriticalSectionCreate(&stru_180029228);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v4 = 12;
LABEL_19:
    WPP_SF_d(v3[2], v4, WPP_8db24c4892c836aea10a5a876d8eb362_Traceguids, (unsigned int)v1);
LABEL_20:
    NcaEvCollIPHTTPsCertShutdown();
    goto LABEL_21;
  }
  v1 = NcaRegOpenKey(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\iphlpsvc\\Parameters\\IPHTTPS\\IPHTTPSInterface",
         9u,
         (__int64)&gNcaEvCollIphttpsCert);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v4 = 13;
    goto LABEL_19;
  }
  if ( (_DWORD)gNcaEvCollIphttpsCert )
  {
    IsCertError = NcaEvCollIphttpsIsCertError();
    NcaDAPEvidenceSnapshotSetGlobalState(14, IsCertError);
    v1 = NcaRegNotifyCreate(v8, v7, v9, v10, v12);
    v2 = v1;
    if ( v1 < 0 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v4 = 14;
      goto LABEL_19;
    }
  }
LABEL_21:
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(v5, ModuleInitializeEnd, L"EvCollIPHTTPsCert", (int)v2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_8db24c4892c836aea10a5a876d8eb362_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180014b80  push    rbx
0x180014b82  push    rbp
0x180014b83  push    rsi
0x180014b84  push    r14
0x180014b86  sub     rsp, 48h
0x180014b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b91  lea     rsi, WPP_GLOBAL_Control
0x180014b98  lea     rbp, WPP_8db24c4892c836aea10a5a876d8eb362_Traceguids
0x180014b9f  cmp     rcx, rsi
0x180014ba2  jz      short loc_180014BBB
0x180014ba4  test    byte ptr [rcx+1Ch], 8
0x180014ba8  jz      short loc_180014BBB
0x180014baa  mov     rcx, [rcx+10h]
0x180014bae  mov     edx, 0Bh
0x180014bb3  mov     r8, rbp
0x180014bb6  call    WPP_SF_
0x180014bbb  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180014bc2  jz      short loc_180014BD7
0x180014bc4  lea     r8, aEvcolliphttpsc; "EvCollIPHTTPsCert"
0x180014bcb  lea     rdx, ModuleInitializeStart
0x180014bd2  call    McTemplateU0z_EventWriteTransfer
0x180014bd7  xor     edx, edx; Val
0x180014bd9  lea     r14, ?gNcaEvCollIphttpsCert@@3UNCA_EVCOLL_IPHTTPS_CERT_COMPONENT_@@A; NCA_EVCOLL_IPHTTPS_CERT_COMPONENT_ gNcaEvCollIphttpsCert
0x180014be0  mov     rcx, r14; void *
0x180014be3  lea     r8d, [rdx+50h]; Size
0x180014be7  call    memset_0
0x180014bec  lea     rcx, stru_180029228; lpCriticalSection
0x180014bf3  call    NcaCriticalSectionCreate
0x180014bf8  mov     ebx, eax
0x180014bfa  test    eax, eax
0x180014bfc  jns     short loc_180014C22
0x180014bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c05  cmp     rcx, rsi
0x180014c08  jz      loc_180014CBF
0x180014c0e  test    byte ptr [rcx+1Ch], 1
0x180014c12  jz      loc_180014CBF
0x180014c18  mov     edx, 0Ch
0x180014c1d  jmp     loc_180014CB0
0x180014c22  lea     r9, qword_180029218
0x180014c29  mov     qword ptr [rsp+68h+var_48], r14; __int64
0x180014c2e  mov     r8d, 9; samDesired
0x180014c34  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\ip"...
0x180014c3b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014c42  call    NcaRegOpenKey
0x180014c47  mov     ebx, eax
0x180014c49  test    eax, eax
0x180014c4b  jns     short loc_180014C66
0x180014c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c54  cmp     rcx, rsi
0x180014c57  jz      short loc_180014CBF
0x180014c59  test    byte ptr [rcx+1Ch], 1
0x180014c5d  jz      short loc_180014CBF
0x180014c5f  mov     edx, 0Dh
0x180014c64  jmp     short loc_180014CB0
0x180014c66  cmp     cs:?gNcaEvCollIphttpsCert@@3UNCA_EVCOLL_IPHTTPS_CERT_COMPONENT_@@A, 0; NCA_EVCOLL_IPHTTPS_CERT_COMPONENT_ gNcaEvCollIphttpsCert
0x180014c6d  jz      short loc_180014CC4
0x180014c6f  call    ?NcaEvCollIphttpsIsCertError@@YAHXZ; NcaEvCollIphttpsIsCertError(void)
0x180014c74  mov     r14d, 0Eh
0x180014c7a  mov     edx, eax
0x180014c7c  mov     ecx, r14d
0x180014c7f  call    NcaDAPEvidenceSnapshotSetGlobalState
0x180014c84  lea     rax, qword_180029220
0x180014c8b  mov     [rsp+68h+var_30], rax
0x180014c90  call    NcaRegNotifyCreate
0x180014c95  mov     ebx, eax
0x180014c97  test    eax, eax
0x180014c99  jns     short loc_180014CC4
0x180014c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ca2  cmp     rcx, rsi
0x180014ca5  jz      short loc_180014CBF
0x180014ca7  test    byte ptr [rcx+1Ch], 1
0x180014cab  jz      short loc_180014CBF
0x180014cad  mov     edx, r14d
0x180014cb0  mov     rcx, [rcx+10h]
0x180014cb4  mov     r9d, eax
0x180014cb7  mov     r8, rbp
0x180014cba  call    WPP_SF_d
0x180014cbf  call    ?NcaEvCollIPHTTPsCertShutdown@@YAXXZ; NcaEvCollIPHTTPsCertShutdown(void)
0x180014cc4  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180014ccb  jz      short loc_180014CE3
0x180014ccd  movsxd  r9, ebx
0x180014cd0  lea     r8, aEvcolliphttpsc; "EvCollIPHTTPsCert"
0x180014cd7  lea     rdx, ModuleInitializeEnd
0x180014cde  call    McTemplateU0zx_EventWriteTransfer
0x180014ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cea  cmp     rcx, rsi
0x180014ced  jz      short loc_180014D09
0x180014cef  test    byte ptr [rcx+1Ch], 8
0x180014cf3  jz      short loc_180014D09
0x180014cf5  mov     rcx, [rcx+10h]
0x180014cf9  mov     edx, 0Fh
0x180014cfe  mov     r9d, ebx
0x180014d01  mov     r8, rbp
0x180014d04  call    WPP_SF_d
0x180014d09  mov     eax, ebx
0x180014d0b  add     rsp, 48h
0x180014d0f  pop     r14
0x180014d11  pop     rsi
0x180014d12  pop     rbp
0x180014d13  pop     rbx
0x180014d14  retn
```
