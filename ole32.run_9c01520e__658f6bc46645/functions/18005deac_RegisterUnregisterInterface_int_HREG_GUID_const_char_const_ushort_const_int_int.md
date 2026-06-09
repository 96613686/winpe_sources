# RegisterUnregisterInterface(int,HREG,_GUID const &,char const *,ushort const *,int,int)

- ea: `0x18005deac`
- end: `0x18005e0e9`
- name: `?RegisterUnregisterInterface@@YAJHUHREG@@AEBU_GUID@@PEBDPEBGHH@Z`
- size: `573`
- prototype: `HRESULT __fastcall(int fRegister, HREG hKeyInterface, const _GUID *riid, const char *szInterfaceName, const wchar_t *wszClassID, int fMarshal, int fCallFrame)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005e0f0`

## callees

- `0x180010efc`
- `0x180020a3c`
- `0x180020b10`
- `0x180046460`
- `0x18005deac`
- `0x18005e370`
- `0x1800c698c`
- `0x1800c6ae0`

## import_xrefs

- `ntdll!ZwClose` at `0x18005dfd1`
- `ntdll!ZwClose` at `0x18005e035`
- `ntdll!ZwClose` at `0x18005e0b2`
- `ntdll!ZwClose` at `0x18005dfd1`
- `ntdll!ZwClose` at `0x18005e035`
- `ntdll!ZwClose` at `0x18005e0b2`
- `ntdll!ZwDeleteKey` at `0x18005e020`
- `ntdll!ZwDeleteKey` at `0x18005e020`
- `ntdll!RtlInitUnicodeString` at `0x18005e086`
- `ntdll!RtlInitUnicodeString` at `0x18005e086`
- `ntdll!ZwDeleteValueKey` at `0x18005e099`
- `ntdll!ZwDeleteValueKey` at `0x18005e099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005df62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005df62`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall RegisterUnregisterInterface(
        int fRegister,
        HREG hKeyInterface,
        const _GUID *riid,
        const char *szInterfaceName,
        wchar_t *wszClassID,
        int fMarshal,
        int fCallFrame)
{
  HRESULT v10; // eax
  HRESULT v11; // ebx
  wchar_t *v12; // rax
  wchar_t *v13; // r14
  NTSTATUS v14; // eax
  void *h; // rbx
  NTSTATUS v16; // eax
  HREG hKeyIID; // [rsp+30h] [rbp-51h] BYREF
  _UNICODE_STRING hKeyClsid; // [rsp+38h] [rbp-49h] OVERLAPPED BYREF
  wchar_t wszIID[40]; // [rsp+50h] [rbp-31h] BYREF

  StringFromGuid(riid, wszIID);
  hKeyIID.h = 0;
  if ( fRegister )
    v10 = OpenRegistryKey(&hKeyIID, hKeyInterface, wszIID, 0x20006u, 1);
  else
    v10 = OpenRegistryKey(&hKeyIID, hKeyInterface, wszIID, 0xF003Fu, 0);
  v11 = v10;
  if ( !v10 )
  {
    if ( !fRegister || !szInterfaceName )
      goto LABEL_30;
    v12 = ToUnicode(szInterfaceName);
    v13 = v12;
    if ( !v12 )
    {
      v11 = -2147024882;
      goto LABEL_26;
    }
    v11 = SetRegistryValue(hKeyIID, &value, v12, 0);
    CoTaskMemFree(v13);
    if ( !v11 )
    {
LABEL_30:
      if ( !fMarshal )
        goto LABEL_20;
      *(_QWORD *)&hKeyClsid.Length = 0;
      if ( !fRegister )
      {
        if ( !OpenRegistryKey((HREG *)&hKeyClsid, hKeyIID, Com::Catalog::Constants::ProxyStubClsid32, 0xF003Fu, 0) )
        {
          if ( TestRegistryValue(*(HREG *)&hKeyClsid.Length, &value, wszClassID) )
          {
            ZwClose(*(HANDLE *)&hKeyClsid.Length);
          }
          else
          {
            v14 = ZwDeleteKey(*(HANDLE *)&hKeyClsid.Length);
            HrNt(v14);
          }
        }
        v11 = 0;
        goto LABEL_20;
      }
      v11 = OpenRegistryKey((HREG *)&hKeyClsid, hKeyIID, Com::Catalog::Constants::ProxyStubClsid32, 0x20006u, 1);
      if ( !v11 )
      {
        v11 = SetRegistryValue(*(HREG *)&hKeyClsid.Length, &value, wszClassID, 0);
        ZwClose(*(HANDLE *)&hKeyClsid.Length);
        if ( !v11 )
        {
LABEL_20:
          if ( fCallFrame )
          {
            if ( fRegister )
            {
              v11 = SetRegistryValue(hKeyIID, L"InterfaceHelperUser", wszClassID, 0);
            }
            else
            {
              if ( !TestRegistryValue(hKeyIID, L"InterfaceHelperUser", wszClassID) )
              {
                h = hKeyIID.h;
                hKeyClsid = 0;
                RtlInitUnicodeString(&hKeyClsid, L"InterfaceHelperUser");
                v16 = ZwDeleteValueKey(h, &hKeyClsid);
                HrNt(v16);
              }
              v11 = 0;
            }
          }
        }
      }
    }
LABEL_26:
    ZwClose(hKeyIID.h);
  }
  return v11 & (unsigned int)-(fRegister != 0);
}

```

## disassembly

```asm
0x18005deac  mov     [rsp-8+arg_0], rbx
0x18005deb1  mov     [rsp-8+arg_8], rsi
0x18005deb6  push    rbp
0x18005deb7  push    rdi
0x18005deb8  push    r14
0x18005deba  lea     rbp, [rsp-2Fh]
0x18005debf  sub     rsp, 0B0h
0x18005dec6  mov     rax, cs:__security_cookie
0x18005decd  xor     rax, rsp
0x18005ded0  mov     [rbp+3Fh+var_20], rax
0x18005ded4  mov     rsi, [rbp+3Fh+wszTestValue]
0x18005ded8  mov     rbx, hKeyInterface
0x18005dedb  mov     edi, fRegister
0x18005dedd  lea     hKeyInterface, [rbp+3Fh+wszIID]; pwsz
0x18005dee1  mov     rcx, riid; guid
0x18005dee4  mov     r14, szInterfaceName
0x18005dee7  call    ?StringFromGuid@@YAXAEBU_GUID@@PEAG@Z; StringFromGuid(_GUID const &,ushort *)
0x18005deec  and     [rbp+3Fh+hKeyIID.h], 0
0x18005def1  lea     riid, [rbp+3Fh+wszIID]; wszKeyName
0x18005def5  lea     rcx, [rbp+3Fh+hKeyIID]; phkey
0x18005def9  mov     hKeyInterface, rbx; hKeyParent
0x18005defc  test    edi, edi
0x18005defe  jz      short loc_18005DF10
0x18005df00  mov     [rsp+0C0h+fCreate], 1
0x18005df08  mov     r9d, 20006h
0x18005df0e  jmp     short loc_18005DF1B
0x18005df10  and     [rsp+0C0h+fCreate], 0
0x18005df15  mov     r9d, 0F003Fh; dwDesiredAccess
0x18005df1b  call    OpenRegistryKey
0x18005df20  mov     ebx, eax
0x18005df22  test    eax, eax
0x18005df24  jnz     loc_18005E0BE
0x18005df2a  test    edi, edi
0x18005df2c  jz      short loc_18005DF76
0x18005df2e  test    r14, r14
0x18005df31  jz      short loc_18005DF76
0x18005df33  mov     rcx, r14; sz
0x18005df36  call    ?ToUnicode@@YAPEAGPEBD@Z; ToUnicode(char const *)
0x18005df3b  mov     r14, rax
0x18005df3e  test    rax, rax
0x18005df41  jz      loc_18005DFE7
0x18005df47  mov     rcx, [rbp+3Fh+hKeyIID.h]; hkey
0x18005df4b  lea     hKeyInterface, value; wszValueName
0x18005df52  xor     r9d, r9d
0x18005df55  mov     riid, rax
0x18005df58  call    ?SetRegistryValue@@YAJUHREG@@PEBGZZ; SetRegistryValue(HREG,ushort const *,...)
0x18005df5d  mov     rcx, r14; pv
0x18005df60  mov     ebx, eax
0x18005df62  call    cs:__imp_CoTaskMemFree
0x18005df69  nop     dword ptr [rax+rax+00h]
0x18005df6e  test    ebx, ebx
0x18005df70  jnz     loc_18005E0AE
0x18005df76  cmp     [rbp+3Fh+arg_28], 0
0x18005df7a  jz      loc_18005E043
0x18005df80  and     [rbp+3Fh+hKeyClsid.h], 0
0x18005df85  lea     riid, ?ProxyStubClsid32@Constants@Catalog@Com@@3QBGB; wszKeyName
0x18005df8c  mov     hKeyInterface, [rbp+3Fh+hKeyIID.h]; hKeyParent
0x18005df90  lea     rcx, [rbp+3Fh+hKeyClsid]; phkey
0x18005df94  test    edi, edi
0x18005df96  jz      short loc_18005DFF1
0x18005df98  mov     r9d, 20006h; dwDesiredAccess
0x18005df9e  mov     [rsp+0C0h+fCreate], 1; fCreate
0x18005dfa6  call    OpenRegistryKey
0x18005dfab  mov     ebx, eax
0x18005dfad  test    eax, eax
0x18005dfaf  jnz     loc_18005E0AE
0x18005dfb5  mov     rcx, [rbp+3Fh+hKeyClsid.h]; hkey
0x18005dfb9  lea     hKeyInterface, value; wszValueName
0x18005dfc0  xor     r9d, r9d
0x18005dfc3  mov     riid, rsi
0x18005dfc6  call    ?SetRegistryValue@@YAJUHREG@@PEBGZZ; SetRegistryValue(HREG,ushort const *,...)
0x18005dfcb  mov     rcx, [rbp+3Fh+hKeyClsid.h]; Handle
0x18005dfcf  mov     ebx, eax
0x18005dfd1  call    cs:__imp_ZwClose
0x18005dfd8  nop     dword ptr [rax+rax+00h]
0x18005dfdd  test    ebx, ebx
0x18005dfdf  jnz     loc_18005E0AE
0x18005dfe5  jmp     short loc_18005E043
0x18005dfe7  mov     ebx, 8007000Eh
0x18005dfec  jmp     loc_18005E0AE
0x18005dff1  and     [rsp+0C0h+fCreate], 0
0x18005dff6  mov     r9d, 0F003Fh; dwDesiredAccess
0x18005dffc  call    OpenRegistryKey
0x18005e001  test    eax, eax
0x18005e003  jnz     short loc_18005E041
0x18005e005  mov     rcx, [rbp+3Fh+hKeyClsid.h]; hreg
0x18005e009  lea     hKeyInterface, value; wszValueName
0x18005e010  mov     riid, rsi; wszTestValue
0x18005e013  call    ?TestRegistryValue@@YAJUHREG@@PEBG1@Z; TestRegistryValue(HREG,ushort const *,ushort const *)
0x18005e018  mov     rcx, [rbp+3Fh+hKeyClsid.h]; Handle
0x18005e01c  test    eax, eax
0x18005e01e  jnz     short loc_18005E035
0x18005e020  call    cs:__imp_ZwDeleteKey
0x18005e027  nop     dword ptr [rax+rax+00h]
0x18005e02c  mov     fRegister, eax; status
0x18005e02e  call    HrNt
0x18005e033  jmp     short loc_18005E041
0x18005e035  call    cs:__imp_ZwClose
0x18005e03c  nop     dword ptr [rax+rax+00h]
0x18005e041  xor     ebx, ebx
0x18005e043  cmp     [rbp+3Fh+arg_30], 0
0x18005e047  jz      short loc_18005E0AE
0x18005e049  mov     rcx, [rbp+3Fh+hKeyIID.h]; hreg
0x18005e04d  mov     riid, rsi; wszTestValue
0x18005e050  lea     hKeyInterface, aInterfacehelpe_2; "InterfaceHelperUser"
0x18005e057  test    edi, edi
0x18005e059  jz      short loc_18005E067
0x18005e05b  xor     r9d, r9d
0x18005e05e  call    ?SetRegistryValue@@YAJUHREG@@PEBGZZ; SetRegistryValue(HREG,ushort const *,...)
0x18005e063  mov     ebx, eax
0x18005e065  jmp     short loc_18005E0AE
0x18005e067  call    ?TestRegistryValue@@YAJUHREG@@PEBG1@Z; TestRegistryValue(HREG,ushort const *,ushort const *)
0x18005e06c  test    eax, eax
0x18005e06e  jnz     short loc_18005E0AC
0x18005e070  mov     rbx, [rbp+3Fh+hKeyIID.h]
0x18005e074  lea     hKeyInterface, aInterfacehelpe_2; "InterfaceHelperUser"
0x18005e07b  xorps   xmm0, xmm0
0x18005e07e  lea     rcx, [rbp+3Fh+hKeyClsid]; DestinationString
0x18005e082  movups  xmmword ptr [rbp+3Fh+hKeyClsid.h], xmm0
0x18005e086  call    cs:__imp_RtlInitUnicodeString
0x18005e08d  nop     dword ptr [rax+rax+00h]
0x18005e092  lea     hKeyInterface, [rbp+3Fh+hKeyClsid]; ValueName
0x18005e096  mov     rcx, rbx; KeyHandle
0x18005e099  call    cs:__imp_ZwDeleteValueKey
0x18005e0a0  nop     dword ptr [rax+rax+00h]
0x18005e0a5  mov     fRegister, eax; status
0x18005e0a7  call    HrNt
0x18005e0ac  xor     ebx, ebx
0x18005e0ae  mov     rcx, [rbp+3Fh+hKeyIID.h]; Handle
0x18005e0b2  call    cs:__imp_ZwClose
0x18005e0b9  nop     dword ptr [rax+rax+00h]
0x18005e0be  neg     edi
0x18005e0c0  sbb     eax, eax
0x18005e0c2  and     eax, ebx
0x18005e0c4  mov     rcx, [rbp+3Fh+var_20]
0x18005e0c8  xor     rcx, rsp; StackCookie
0x18005e0cb  call    __security_check_cookie
0x18005e0d0  lea     r11, [rsp+0C0h+var_10]
0x18005e0d8  mov     rbx, [r11+20h]
0x18005e0dc  mov     rsi, [r11+28h]
0x18005e0e0  mov     rsp, r11
0x18005e0e3  pop     r14
0x18005e0e5  pop     rdi
0x18005e0e6  pop     rbp
0x18005e0e7  retn
```
