# MvSaveNodeForUndo(ProvStateContext const *,IConfigManager2URI *)

- ea: `0x18002fa98`
- end: `0x18002fcaf`
- name: `?MvSaveNodeForUndo@@YAJPEBVProvStateContext@@PEAUIConfigManager2URI@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(const struct ProvStateContext *, struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002fd10`

## callees

- `0x1800098dc`
- `0x180009900`
- `0x18002fa98`
- `0x180033784`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fc57`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fc57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fc22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fc72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fc22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fc72`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002fbed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002fbed`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb23`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb99`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fc83`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb23`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb99`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fc83`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MvSaveNodeForUndo(const struct ProvStateContext *a1, struct IConfigManager2URI *a2)
{
  int v3; // eax
  unsigned int v4; // edi
  const unsigned int *v6; // rdx
  __int64 v7; // rax
  int ContextSubKeyPath; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  REGSAM samDesired; // [rsp+28h] [rbp-D8h]
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !*(_QWORD *)a1 )
    return 0;
  bstrString = 0;
  v3 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, _QWORD, BSTR *))(*(_QWORD *)a2 + 64LL))(
         a2,
         2,
         0,
         &bstrString);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
      (const char *)(unsigned int)v3,
      dwOptions);
    if ( bstrString )
      SysFreeString(bstrString);
    return v4;
  }
  v6 = 0;
  v7 = *((_QWORD *)a1 + 4);
  if ( v7 && *(_DWORD *)(v7 + 96) )
    v6 = (const unsigned int *)(v7 + 92);
  ContextSubKeyPath = MvGetContextSubKeyPath(
                        *(struct IMVHandler **)a1,
                        v6,
                        gc_wszRegMultivariant,
                        L"Undo",
                        SubKey,
                        samDesired,
                        0);
  v9 = ContextSubKeyPath;
  if ( ContextSubKeyPath >= 0 )
  {
    hKey = 0;
    v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v10 )
    {
      v11 = 39;
      goto LABEL_16;
    }
    *(_DWORD *)Data = 0;
    v10 = RegSetValueExW(hKey, bstrString, 0, 4u, Data, 4u);
    if ( v10 )
    {
      v11 = 43;
LABEL_16:
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
             (const char *)v10,
             dwOptionsb);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_11;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( bstrString )
      SysFreeString(bstrString);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
    (const char *)(unsigned int)ContextSubKeyPath,
    dwOptionsa);
LABEL_11:
  if ( bstrString )
    SysFreeString(bstrString);
  return v9;
}

```

## disassembly

```asm
0x18002fa98  mov     [rsp-8+arg_10], rbx
0x18002fa9d  mov     [rsp-8+arg_18], rdi
0x18002faa2  push    rbp
0x18002faa3  lea     rbp, [rsp-190h]
0x18002faab  sub     rsp, 290h
0x18002fab2  mov     rax, cs:__security_cookie
0x18002fab9  xor     rax, rsp
0x18002fabc  mov     [rbp+190h+var_10], rax
0x18002fac3  mov     r10, rdx
0x18002fac6  mov     rbx, rcx
0x18002fac9  cmp     qword ptr [rcx], 0
0x18002facd  jz      loc_18002FC89
0x18002fad3  mov     [rsp+290h+bstrString], 0
0x18002fadc  mov     rax, [rdx]
0x18002fadf  lea     r9, [rsp+290h+bstrString]
0x18002fae4  xor     r8d, r8d
0x18002fae7  lea     edx, [r8+2]
0x18002faeb  mov     rcx, r10
0x18002faee  mov     rax, [rax+40h]
0x18002faf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002faf7  mov     edi, eax
0x18002faf9  test    eax, eax
0x18002fafb  jns     short loc_18002FB30
0x18002fafd  mov     rcx, [rbp+198h]; this
0x18002fb04  mov     r9d, eax; char *
0x18002fb07  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002fb0e  mov     edx, 17h; void *
0x18002fb13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fb18  nop
0x18002fb19  mov     rcx, [rsp+290h+bstrString]; bstrString
0x18002fb1e  test    rcx, rcx
0x18002fb21  jz      short loc_18002FB29
0x18002fb23  call    cs:__imp_SysFreeString
0x18002fb29  mov     eax, edi
0x18002fb2b  jmp     loc_18002FC8B
0x18002fb30  xor     edx, edx
0x18002fb32  mov     rax, [rbx+20h]
0x18002fb36  test    rax, rax
0x18002fb39  jz      short loc_18002FB44
0x18002fb3b  cmp     [rax+60h], edx
0x18002fb3e  jz      short loc_18002FB44
0x18002fb40  lea     rdx, [rax+5Ch]; unsigned int *
0x18002fb44  mov     [rsp+290h+lpSecurityAttributes], 0; pv
0x18002fb4d  lea     rax, [rsp+290h+SubKey]
0x18002fb52  mov     qword ptr [rsp+290h+dwOptions], rax; int
0x18002fb57  lea     r9, ?gc_wszUndo@@3QBGB; "Undo"
0x18002fb5e  mov     r8, cs:?gc_wszRegMultivariant@@3PEBGEB; unsigned __int16 *
0x18002fb65  mov     rcx, [rbx]; struct IMVHandler *
0x18002fb68  call    ?MvGetContextSubKeyPath@@YAJPEAUIMVHandler@@PEBKPEBG2PEAGKPEAU_MVProvisionData@@@Z; MvGetContextSubKeyPath(IMVHandler *,ulong const *,ushort const *,ushort const *,ushort *,ulong,_MVProvisionData *)
0x18002fb6d  mov     ebx, eax
0x18002fb6f  test    eax, eax
0x18002fb71  jns     short loc_18002FBA6
0x18002fb73  mov     rcx, [rbp+198h]; this
0x18002fb7a  mov     r9d, eax; char *
0x18002fb7d  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002fb84  mov     edx, 23h ; '#'; void *
0x18002fb89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fb8e  nop
0x18002fb8f  mov     rcx, [rsp+290h+bstrString]; bstrString
0x18002fb94  test    rcx, rcx
0x18002fb97  jz      short loc_18002FB9F
0x18002fb99  call    cs:__imp_SysFreeString
0x18002fb9f  mov     eax, ebx
0x18002fba1  jmp     loc_18002FC8B
0x18002fba6  mov     [rsp+290h+hKey], 0
0x18002fbaf  mov     [rsp+290h+lpdwDisposition], 0; lpdwDisposition
0x18002fbb8  lea     rax, [rsp+290h+hKey]
0x18002fbbd  mov     [rsp+290h+phkResult], rax; phkResult
0x18002fbc2  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002fbcb  mov     [rsp+290h+samDesired], 2; samDesired
0x18002fbd3  mov     [rsp+290h+dwOptions], 0; unsigned int
0x18002fbdb  xor     r9d, r9d; lpClass
0x18002fbde  xor     r8d, r8d; Reserved
0x18002fbe1  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18002fbe6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002fbed  call    cs:__imp_RegCreateKeyExW
0x18002fbf3  test    eax, eax
0x18002fbf5  jz      short loc_18002FC2D
0x18002fbf7  mov     edx, 27h ; '''; void *
0x18002fbfc  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002fc03  mov     r9d, eax; char *
0x18002fc06  mov     rcx, [rbp+198h]; this
0x18002fc0d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002fc12  mov     ebx, eax
0x18002fc14  mov     rcx, [rsp+290h+hKey]; hKey
0x18002fc19  test    rcx, rcx
0x18002fc1c  jz      loc_18002FB8F
0x18002fc22  call    cs:__imp_RegCloseKey
0x18002fc28  jmp     loc_18002FB8F
0x18002fc2d  mov     dword ptr [rsp+290h+Data], 0
0x18002fc35  mov     r9d, 4; dwType
0x18002fc3b  mov     [rsp+290h+samDesired], r9d; cbData
0x18002fc40  lea     rax, [rsp+290h+Data]
0x18002fc45  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18002fc4a  xor     r8d, r8d; Reserved
0x18002fc4d  mov     rdx, [rsp+290h+bstrString]; lpValueName
0x18002fc52  mov     rcx, [rsp+290h+hKey]; hKey
0x18002fc57  call    cs:__imp_RegSetValueExW
0x18002fc5d  test    eax, eax
0x18002fc5f  jz      short loc_18002FC68
0x18002fc61  mov     edx, 2Bh ; '+'
0x18002fc66  jmp     short loc_18002FBFC
0x18002fc68  mov     rcx, [rsp+290h+hKey]; hKey
0x18002fc6d  test    rcx, rcx
0x18002fc70  jz      short loc_18002FC79
0x18002fc72  call    cs:__imp_RegCloseKey
0x18002fc78  nop
0x18002fc79  mov     rcx, [rsp+290h+bstrString]; bstrString
0x18002fc7e  test    rcx, rcx
0x18002fc81  jz      short loc_18002FC89
0x18002fc83  call    cs:__imp_SysFreeString
0x18002fc89  xor     eax, eax
0x18002fc8b  mov     rcx, [rbp+190h+var_10]
0x18002fc92  xor     rcx, rsp; StackCookie
0x18002fc95  call    __security_check_cookie
0x18002fc9a  lea     r11, [rsp+290h+var_s0]
0x18002fca2  mov     rbx, [r11+20h]
0x18002fca6  mov     rdi, [r11+28h]
0x18002fcaa  mov     rsp, r11
0x18002fcad  pop     rbp
0x18002fcae  retn
```
