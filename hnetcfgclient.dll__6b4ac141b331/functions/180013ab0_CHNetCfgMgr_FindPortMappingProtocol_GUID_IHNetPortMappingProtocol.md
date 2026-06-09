# CHNetCfgMgr::FindPortMappingProtocol(_GUID *,IHNetPortMappingProtocol * *)

- ea: `0x180013ab0`
- end: `0x180013e94`
- name: `?FindPortMappingProtocol@CHNetCfgMgr@@UEAAJPEAU_GUID@@PEAPEAUIHNetPortMappingProtocol@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(CHNetCfgMgr *this, struct _GUID *, struct IHNetPortMappingProtocol **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800056dc`
- `0x18000a45c`
- `0x18000a484`
- `0x180010218`
- `0x180013ab0`
- `0x180023db8`
- `0x180029a3c`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180013c71`
- `OLEAUT32!__imp_SysAllocString` at `0x180013c71`
- `OLEAUT32!__imp_SysFreeString` at `0x180013ccd`
- `OLEAUT32!__imp_SysFreeString` at `0x180013ccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c66`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180013beb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180013beb`

## string_xrefs

- `0x180013c33`: `HNet_PortMappingProtocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHNetCfgMgr::FindPortMappingProtocol(
        CHNetCfgMgr *this,
        struct _GUID *a2,
        struct IHNetPortMappingProtocol **a3)
{
  PVOID *v6; // rcx
  bool v7; // zf
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  HRESULT v11; // eax
  __int64 v12; // r9
  unsigned __int16 *v13; // rax
  OLECHAR *v14; // rdi
  int WmiObjectFromPath; // eax
  int Instance; // eax
  CHNetPortMappingProtocol *v17; // rdi
  int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  LPOLESTR lpsz; // [rsp+30h] [rbp-D0h] BYREF
  struct IWbemClassObject *v23; // [rsp+38h] [rbp-C8h] BYREF
  CHNetPortMappingProtocol *v24; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR psz[264]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 302, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = *((_QWORD *)this + 8) == 0;
  lpsz = 0;
  v23 = 0;
  if ( v7 )
  {
    v8 = -2147467261;
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      {
        WPP_SF_d(v6[2], 303, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
      {
        v9 = 304;
LABEL_66:
        WPP_SF_d(v6[2], v9, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v8);
        return v8;
      }
    }
    return v8;
  }
  if ( !a3 )
  {
    v8 = -2147467261;
    if ( v6 == &WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)v6 + 28) & 8) == 0 || *((_BYTE *)v6 + 25) < 2u )
      goto LABEL_62;
    v10 = 306;
    goto LABEL_59;
  }
  *a3 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_62;
    v10 = 305;
LABEL_59:
    v12 = v8;
LABEL_60:
    WPP_SF_d(v6[2], v10, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v12);
    goto LABEL_61;
  }
  v11 = StringFromCLSID(a2, &lpsz);
  v8 = v11;
  if ( v11 < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_62;
    v10 = 307;
    v12 = (unsigned int)v11;
    goto LABEL_60;
  }
  if ( !v11 )
  {
    StringCchPrintfW(psz, 0x104u, L"%s.%s=\"%s\"", L"HNet_PortMappingProtocol", L"Id", lpsz);
    CoTaskMemFree(lpsz);
    v13 = SysAllocString(psz);
    v14 = v13;
    if ( !v13 )
    {
      v8 = -2147024882;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_62;
      v10 = 309;
      goto LABEL_59;
    }
    WmiObjectFromPath = GetWmiObjectFromPath(*((struct IWbemServices **)this + 8), v13, &v23);
    v8 = WmiObjectFromPath;
    if ( WmiObjectFromPath < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        308,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)WmiObjectFromPath);
    }
    SysFreeString(v14);
    if ( v8 )
      goto LABEL_61;
    v24 = 0;
    Instance = ATL::CComObject<CHNetPortMappingProtocol>::CreateInstance((volatile int **)&v24);
    v8 = Instance;
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          310,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)Instance);
      }
      goto LABEL_50;
    }
    v17 = v24;
    (*(void (__fastcall **)(CHNetPortMappingProtocol *))(*(_QWORD *)v24 + 8LL))(v24);
    v18 = CHNetPortMappingProtocol::Initialize(v17, *((struct IWbemServices **)this + 8), v23);
    v8 = v18;
    if ( v18 >= 0 )
    {
      v18 = (**(__int64 (__fastcall ***)(CHNetPortMappingProtocol *, GUID *, struct IHNetPortMappingProtocol **))v17)(
              v17,
              &GUID_85d18b7e_3032_11d4_9348_00c04f8eeb71,
              a3);
      v8 = v18;
      if ( v18 >= 0 )
        goto LABEL_49;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_49;
      }
      v20 = 312;
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_49;
      }
      v20 = 311;
    }
    WPP_SF_d(v19[2], v20, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v18);
LABEL_49:
    (*(void (__fastcall **)(CHNetPortMappingProtocol *))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_50:
    ((void (__fastcall *)(struct IWbemClassObject *))v23->lpVtbl->Release)(v23);
  }
LABEL_61:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_62:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
  {
    v9 = 313;
    goto LABEL_66;
  }
  return v8;
}

```

## disassembly

```asm
0x180013ab0  push    rbp
0x180013ab2  push    rbx
0x180013ab3  push    rsi
0x180013ab4  push    rdi
0x180013ab5  push    r12
0x180013ab7  push    r13
0x180013ab9  push    r14
0x180013abb  lea     rbp, [rsp-170h]
0x180013ac3  sub     rsp, 270h
0x180013aca  mov     rax, cs:__security_cookie
0x180013ad1  xor     rax, rsp
0x180013ad4  mov     [rbp+1A0h+var_40], rax
0x180013adb  mov     rsi, r8
0x180013ade  mov     rbx, rdx
0x180013ae1  mov     r14, rcx
0x180013ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x180013aeb  lea     r13, WPP_GLOBAL_Control
0x180013af2  mov     r12b, 8
0x180013af5  cmp     rcx, r13
0x180013af8  jz      short loc_180013B22
0x180013afa  test    [rcx+1Ch], r12b
0x180013afe  jz      short loc_180013B22
0x180013b00  cmp     byte ptr [rcx+19h], 6
0x180013b04  jb      short loc_180013B22
0x180013b06  mov     rcx, [rcx+10h]
0x180013b0a  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180013b11  mov     edx, 12Eh
0x180013b16  call    WPP_SF_
0x180013b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b22  cmp     qword ptr [r14+40h], 0
0x180013b27  mov     [rsp+2A0h+lpsz], 0
0x180013b30  mov     [rsp+2A0h+var_268], 0
0x180013b39  jnz     short loc_180013B9B
0x180013b3b  mov     ebx, 80004003h
0x180013b40  cmp     rcx, r13
0x180013b43  jz      loc_180013E71
0x180013b49  test    [rcx+1Ch], r12b
0x180013b4d  jz      short loc_180013B74
0x180013b4f  cmp     byte ptr [rcx+19h], 2
0x180013b53  jb      short loc_180013B74
0x180013b55  mov     rcx, [rcx+10h]
0x180013b59  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180013b60  mov     edx, 12Fh
0x180013b65  mov     r9d, ebx
0x180013b68  call    WPP_SF_d
0x180013b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b74  cmp     rcx, r13
0x180013b77  jz      loc_180013E71
0x180013b7d  test    [rcx+1Ch], r12b
0x180013b81  jz      loc_180013E71
0x180013b87  cmp     byte ptr [rcx+19h], 6
0x180013b8b  jb      loc_180013E71
0x180013b91  mov     edx, 130h
0x180013b96  jmp     loc_180013E5E
0x180013b9b  test    rsi, rsi
0x180013b9e  jz      loc_180013E13
0x180013ba4  mov     qword ptr [rsi], 0
0x180013bab  test    rbx, rbx
0x180013bae  jnz     short loc_180013BE3
0x180013bb0  mov     ebx, 80070057h
0x180013bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bbc  cmp     rcx, r13
0x180013bbf  jz      loc_180013E71
0x180013bc5  test    [rcx+1Ch], r12b
0x180013bc9  jz      loc_180013E48
0x180013bcf  cmp     byte ptr [rcx+19h], 2
0x180013bd3  jb      loc_180013E48
0x180013bd9  mov     edx, 131h
0x180013bde  jmp     loc_180013E2E
0x180013be3  lea     rdx, [rsp+2A0h+lpsz]; lplpsz
0x180013be8  mov     rcx, rbx; rclsid
0x180013beb  call    cs:__imp_StringFromCLSID
0x180013bf1  mov     ebx, eax
0x180013bf3  test    eax, eax
0x180013bf5  jns     short loc_180013C28
0x180013bf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bfe  cmp     rcx, r13
0x180013c01  jz      loc_180013E71
0x180013c07  test    [rcx+1Ch], r12b
0x180013c0b  jz      loc_180013E48
0x180013c11  cmp     byte ptr [rcx+19h], 2
0x180013c15  jb      loc_180013E48
0x180013c1b  mov     edx, 133h
0x180013c20  mov     r9d, eax
0x180013c23  jmp     loc_180013E31
0x180013c28  jnz     loc_180013E41
0x180013c2e  mov     rax, [rsp+2A0h+lpsz]
0x180013c33  lea     r9, ?c_wszHnetPortMappingProtocol@@3QBGB; "HNet_PortMappingProtocol"
0x180013c3a  mov     [rsp+2A0h+var_278], rax
0x180013c3f  lea     r8, aSSS; "%s.%s=\"%s\""
0x180013c46  lea     rax, ?c_wszId@@3QBGB; "Id"
0x180013c4d  mov     edx, 104h; unsigned __int64
0x180013c52  lea     rcx, [rsp+2A0h+psz]; unsigned __int16 *
0x180013c57  mov     [rsp+2A0h+var_280], rax
0x180013c5c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013c61  mov     rcx, [rsp+2A0h+lpsz]; pv
0x180013c66  call    cs:__imp_CoTaskMemFree
0x180013c6c  lea     rcx, [rsp+2A0h+psz]; psz
0x180013c71  call    cs:__imp_SysAllocString
0x180013c77  mov     rdi, rax
0x180013c7a  test    rax, rax
0x180013c7d  jz      loc_180013DEF
0x180013c83  mov     rcx, [r14+40h]; struct IWbemServices *
0x180013c87  lea     r8, [rsp+2A0h+var_268]; struct IWbemClassObject **
0x180013c8c  mov     rdx, rax; unsigned __int16 *
0x180013c8f  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180013c94  mov     ebx, eax
0x180013c96  test    eax, eax
0x180013c98  jns     short loc_180013CCA
0x180013c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ca1  cmp     rcx, r13
0x180013ca4  jz      short loc_180013CCA
0x180013ca6  test    [rcx+1Ch], r12b
0x180013caa  jz      short loc_180013CCA
0x180013cac  cmp     byte ptr [rcx+19h], 2
0x180013cb0  jb      short loc_180013CCA
0x180013cb2  mov     rcx, [rcx+10h]
0x180013cb6  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180013cbd  mov     edx, 134h
0x180013cc2  mov     r9d, eax
0x180013cc5  call    WPP_SF_d
0x180013cca  mov     rcx, rdi; bstrString
0x180013ccd  call    cs:__imp_SysFreeString
0x180013cd3  test    ebx, ebx
0x180013cd5  jnz     loc_180013E41
0x180013cdb  lea     rcx, [rsp+2A0h+var_260]
0x180013ce0  mov     [rsp+2A0h+var_260], 0
0x180013ce9  call    ?CreateInstance@?$CComObject@VCHNetPortMappingProtocol@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNetPortMappingProtocol>::CreateInstance(ATL::CComObject<CHNetPortMappingProtocol> * *)
0x180013cee  mov     ebx, eax
0x180013cf0  test    eax, eax
0x180013cf2  jns     short loc_180013D35
0x180013cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cfb  cmp     rcx, r13
0x180013cfe  jz      loc_180013DDC
0x180013d04  test    [rcx+1Ch], r12b
0x180013d08  jz      loc_180013DDC
0x180013d0e  cmp     byte ptr [rcx+19h], 2
0x180013d12  jb      loc_180013DDC
0x180013d18  mov     rcx, [rcx+10h]
0x180013d1c  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180013d23  mov     edx, 136h
0x180013d28  mov     r9d, eax
0x180013d2b  call    WPP_SF_d
0x180013d30  jmp     loc_180013DDC
0x180013d35  mov     rdi, [rsp+2A0h+var_260]
0x180013d3a  mov     rcx, rdi
0x180013d3d  mov     rax, [rdi]
0x180013d40  mov     rax, [rax+8]
0x180013d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d49  mov     r8, [rsp+2A0h+var_268]; struct IWbemClassObject *
0x180013d4e  mov     rcx, rdi; this
0x180013d51  mov     rdx, [r14+40h]; struct IWbemServices *
0x180013d55  call    ?Initialize@CHNetPortMappingProtocol@@QEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; CHNetPortMappingProtocol::Initialize(IWbemServices *,IWbemClassObject *)
0x180013d5a  mov     ebx, eax
0x180013d5c  test    eax, eax
0x180013d5e  jns     short loc_180013D7F
0x180013d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d67  cmp     rcx, r13
0x180013d6a  jz      short loc_180013DCD
0x180013d6c  test    [rcx+1Ch], r12b
0x180013d70  jz      short loc_180013DCD
0x180013d72  cmp     byte ptr [rcx+19h], 2
0x180013d76  jb      short loc_180013DCD
0x180013d78  mov     edx, 137h
0x180013d7d  jmp     short loc_180013DBA
0x180013d7f  mov     rax, [rdi]
0x180013d82  lea     rdx, _GUID_85d18b7e_3032_11d4_9348_00c04f8eeb71
0x180013d89  mov     r8, rsi
0x180013d8c  mov     rcx, rdi
0x180013d8f  mov     rax, [rax]
0x180013d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d97  mov     ebx, eax
0x180013d99  test    eax, eax
0x180013d9b  jns     short loc_180013DCD
0x180013d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013da4  cmp     rcx, r13
0x180013da7  jz      short loc_180013DCD
0x180013da9  test    [rcx+1Ch], r12b
0x180013dad  jz      short loc_180013DCD
0x180013daf  cmp     byte ptr [rcx+19h], 2
0x180013db3  jb      short loc_180013DCD
0x180013db5  mov     edx, 138h
0x180013dba  mov     rcx, [rcx+10h]
0x180013dbe  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180013dc5  mov     r9d, eax
0x180013dc8  call    WPP_SF_d
0x180013dcd  mov     rax, [rdi]
0x180013dd0  mov     rcx, rdi
0x180013dd3  mov     rax, [rax+10h]
0x180013dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ddc  mov     rcx, [rsp+2A0h+var_268]
0x180013de1  mov     rax, [rcx]
0x180013de4  mov     rax, [rax+10h]
0x180013de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ded  jmp     short loc_180013E41
0x180013def  mov     ebx, 8007000Eh
0x180013df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180013dfb  cmp     rcx, r13
0x180013dfe  jz      short loc_180013E71
0x180013e00  test    [rcx+1Ch], r12b
0x180013e04  jz      short loc_180013E48
0x180013e06  cmp     byte ptr [rcx+19h], 2
0x180013e0a  jb      short loc_180013E48
0x180013e0c  mov     edx, 135h
0x180013e11  jmp     short loc_180013E2E
0x180013e13  mov     ebx, 80004003h
0x180013e18  cmp     rcx, r13
0x180013e1b  jz      short loc_180013E71
0x180013e1d  test    [rcx+1Ch], r12b
0x180013e21  jz      short loc_180013E48
0x180013e23  cmp     byte ptr [rcx+19h], 2
0x180013e27  jb      short loc_180013E48
0x180013e29  mov     edx, 132h
0x180013e2e  mov     r9d, ebx
0x180013e31  mov     rcx, [rcx+10h]
0x180013e35  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180013e3c  call    WPP_SF_d
0x180013e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e48  cmp     rcx, r13
0x180013e4b  jz      short loc_180013E71
0x180013e4d  test    [rcx+1Ch], r12b
0x180013e51  jz      short loc_180013E71
0x180013e53  cmp     byte ptr [rcx+19h], 6
0x180013e57  jb      short loc_180013E71
0x180013e59  mov     edx, 139h
0x180013e5e  mov     rcx, [rcx+10h]
0x180013e62  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180013e69  mov     r9d, ebx
0x180013e6c  call    WPP_SF_d
0x180013e71  mov     eax, ebx
0x180013e73  mov     rcx, [rbp+1A0h+var_40]
0x180013e7a  xor     rcx, rsp; StackCookie
0x180013e7d  call    __security_check_cookie
0x180013e82  add     rsp, 270h
0x180013e89  pop     r14
0x180013e8b  pop     r13
0x180013e8d  pop     r12
0x180013e8f  pop     rdi
0x180013e90  pop     rsi
0x180013e91  pop     rbx
0x180013e92  pop     rbp
0x180013e93  retn
```
