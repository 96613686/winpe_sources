# RegisterUnregisterInterface(int,HREG,_GUID const &,char const *,ushort const *,int,int)

- ea: `0x1800686a0`
- end: `0x1800688be`
- name: `?RegisterUnregisterInterface@@YAJHUHREG@@AEBU_GUID@@PEBDPEBGHH@Z`
- size: `542`
- prototype: `HRESULT __fastcall(int fRegister, HREG hKeyInterface, const _GUID *riid, const char *szInterfaceName, const wchar_t *wszClassID, int fMarshal, int fCallFrame)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800688c4`

## callees

- `0x1800177e4`
- `0x180017894`
- `0x180018b30`
- `0x180052390`
- `0x1800686a0`
- `0x180068b44`
- `0x1800bd7d8`
- `0x1800bd91c`

## import_xrefs

- `ntdll!ZwClose` at `0x1800687c8`
- `ntdll!ZwClose` at `0x180068823`
- `ntdll!ZwClose` at `0x18006888e`
- `ntdll!ZwClose` at `0x1800687c8`
- `ntdll!ZwClose` at `0x180068823`
- `ntdll!ZwClose` at `0x18006888e`
- `ntdll!ZwDeleteKey` at `0x180068814`
- `ntdll!ZwDeleteKey` at `0x180068814`
- `ntdll!RtlInitUnicodeString` at `0x18006886e`
- `ntdll!RtlInitUnicodeString` at `0x18006886e`
- `ntdll!ZwDeleteValueKey` at `0x18006887b`
- `ntdll!ZwDeleteValueKey` at `0x18006887b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006875c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006875c`

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
0x1800686a0  mov     [rsp-8+arg_0], rbx
0x1800686a5  mov     [rsp-8+arg_8], rsi
0x1800686aa  push    rbp
0x1800686ab  push    rdi
0x1800686ac  push    r14
0x1800686ae  lea     rbp, [rsp-2Fh]
0x1800686b3  sub     rsp, 0B0h
0x1800686ba  mov     rax, cs:__security_cookie
0x1800686c1  xor     rax, rsp
0x1800686c4  mov     [rbp+3Fh+var_20], rax
0x1800686c8  mov     rsi, [rbp+3Fh+wszTestValue]
0x1800686cc  mov     rbx, hKeyInterface
0x1800686cf  mov     edi, fRegister
0x1800686d1  lea     hKeyInterface, [rbp+3Fh+wszIID]; pwsz
0x1800686d5  mov     rcx, riid; guid
0x1800686d8  mov     r14, szInterfaceName
0x1800686db  call    ?StringFromGuid@@YAXAEBU_GUID@@PEAG@Z; StringFromGuid(_GUID const &,ushort *)
0x1800686e0  mov     [rbp+3Fh+hKeyIID.h], 0
0x1800686e8  lea     riid, [rbp+3Fh+wszIID]; wszKeyName
0x1800686ec  lea     rcx, [rbp+3Fh+hKeyIID]; phkey
0x1800686f0  mov     hKeyInterface, rbx; hKeyParent
0x1800686f3  test    edi, edi
0x1800686f5  jz      short loc_180068707
0x1800686f7  mov     [rsp+0C0h+fCreate], 1
0x1800686ff  mov     r9d, 20006h
0x180068705  jmp     short loc_180068715
0x180068707  mov     [rsp+0C0h+fCreate], 0; fCreate
0x18006870f  mov     r9d, 0F003Fh; dwDesiredAccess
0x180068715  call    OpenRegistryKey
0x18006871a  mov     ebx, eax
0x18006871c  test    eax, eax
0x18006871e  jnz     loc_180068894
0x180068724  test    edi, edi
0x180068726  jz      short loc_18006876A
0x180068728  test    r14, r14
0x18006872b  jz      short loc_18006876A
0x18006872d  mov     rcx, r14; sz
0x180068730  call    ?ToUnicode@@YAPEAGPEBD@Z; ToUnicode(char const *)
0x180068735  mov     r14, rax
0x180068738  test    rax, rax
0x18006873b  jz      loc_1800687D8
0x180068741  mov     rcx, [rbp+3Fh+hKeyIID.h]; hkey
0x180068745  lea     hKeyInterface, value; wszValueName
0x18006874c  xor     r9d, r9d
0x18006874f  mov     riid, rax
0x180068752  call    ?SetRegistryValue@@YAJUHREG@@PEBGZZ; SetRegistryValue(HREG,ushort const *,...)
0x180068757  mov     rcx, r14; pv
0x18006875a  mov     ebx, eax
0x18006875c  call    cs:__imp_CoTaskMemFree
0x180068762  test    ebx, ebx
0x180068764  jnz     loc_18006888A
0x18006876a  cmp     [rbp+3Fh+arg_28], 0
0x18006876e  jz      loc_18006882B
0x180068774  mov     hKeyInterface, [rbp+3Fh+hKeyIID.h]; hKeyParent
0x180068778  lea     riid, ?ProxyStubClsid32@Constants@Catalog@Com@@3QBGB; wszKeyName
0x18006877f  mov     [rbp+3Fh+hKeyClsid.h], 0
0x180068787  lea     rcx, [rbp+3Fh+hKeyClsid]; phkey
0x18006878b  test    edi, edi
0x18006878d  jz      short loc_1800687E2
0x18006878f  mov     r9d, 20006h; dwDesiredAccess
0x180068795  mov     [rsp+0C0h+fCreate], 1; fCreate
0x18006879d  call    OpenRegistryKey
0x1800687a2  mov     ebx, eax
0x1800687a4  test    eax, eax
0x1800687a6  jnz     loc_18006888A
0x1800687ac  mov     rcx, [rbp+3Fh+hKeyClsid.h]; hkey
0x1800687b0  lea     hKeyInterface, value; wszValueName
0x1800687b7  xor     r9d, r9d
0x1800687ba  mov     riid, rsi
0x1800687bd  call    ?SetRegistryValue@@YAJUHREG@@PEBGZZ; SetRegistryValue(HREG,ushort const *,...)
0x1800687c2  mov     rcx, [rbp+3Fh+hKeyClsid.h]; Handle
0x1800687c6  mov     ebx, eax
0x1800687c8  call    cs:__imp_ZwClose
0x1800687ce  test    ebx, ebx
0x1800687d0  jnz     loc_18006888A
0x1800687d6  jmp     short loc_18006882B
0x1800687d8  mov     ebx, 8007000Eh
0x1800687dd  jmp     loc_18006888A
0x1800687e2  mov     r9d, 0F003Fh; dwDesiredAccess
0x1800687e8  mov     [rsp+0C0h+fCreate], 0; fCreate
0x1800687f0  call    OpenRegistryKey
0x1800687f5  test    eax, eax
0x1800687f7  jnz     short loc_180068829
0x1800687f9  mov     rcx, [rbp+3Fh+hKeyClsid.h]; hreg
0x1800687fd  lea     hKeyInterface, value; wszValueName
0x180068804  mov     riid, rsi; wszTestValue
0x180068807  call    ?TestRegistryValue@@YAJUHREG@@PEBG1@Z; TestRegistryValue(HREG,ushort const *,ushort const *)
0x18006880c  mov     rcx, [rbp+3Fh+hKeyClsid.h]; Handle
0x180068810  test    eax, eax
0x180068812  jnz     short loc_180068823
0x180068814  call    cs:__imp_ZwDeleteKey
0x18006881a  mov     fRegister, eax; status
0x18006881c  call    HrNt
0x180068821  jmp     short loc_180068829
0x180068823  call    cs:__imp_ZwClose
0x180068829  xor     ebx, ebx
0x18006882b  cmp     [rbp+3Fh+arg_30], 0
0x18006882f  jz      short loc_18006888A
0x180068831  mov     rcx, [rbp+3Fh+hKeyIID.h]; hreg
0x180068835  mov     riid, rsi; wszTestValue
0x180068838  lea     hKeyInterface, aInterfacehelpe_2; "InterfaceHelperUser"
0x18006883f  test    edi, edi
0x180068841  jz      short loc_18006884F
0x180068843  xor     r9d, r9d
0x180068846  call    ?SetRegistryValue@@YAJUHREG@@PEBGZZ; SetRegistryValue(HREG,ushort const *,...)
0x18006884b  mov     ebx, eax
0x18006884d  jmp     short loc_18006888A
0x18006884f  call    ?TestRegistryValue@@YAJUHREG@@PEBG1@Z; TestRegistryValue(HREG,ushort const *,ushort const *)
0x180068854  test    eax, eax
0x180068856  jnz     short loc_180068888
0x180068858  mov     rbx, [rbp+3Fh+hKeyIID.h]
0x18006885c  lea     hKeyInterface, aInterfacehelpe_2; "InterfaceHelperUser"
0x180068863  xorps   xmm0, xmm0
0x180068866  lea     rcx, [rbp+3Fh+hKeyClsid]; DestinationString
0x18006886a  movups  xmmword ptr [rbp+3Fh+hKeyClsid.h], xmm0
0x18006886e  call    cs:__imp_RtlInitUnicodeString
0x180068874  lea     hKeyInterface, [rbp+3Fh+hKeyClsid]; ValueName
0x180068878  mov     rcx, rbx; KeyHandle
0x18006887b  call    cs:__imp_ZwDeleteValueKey
0x180068881  mov     fRegister, eax; status
0x180068883  call    HrNt
0x180068888  xor     ebx, ebx
0x18006888a  mov     rcx, [rbp+3Fh+hKeyIID.h]; Handle
0x18006888e  call    cs:__imp_ZwClose
0x180068894  neg     edi
0x180068896  sbb     eax, eax
0x180068898  and     eax, ebx
0x18006889a  mov     rcx, [rbp+3Fh+var_20]
0x18006889e  xor     rcx, rsp; StackCookie
0x1800688a1  call    __security_check_cookie
0x1800688a6  lea     r11, [rsp+0C0h+var_10]
0x1800688ae  mov     rbx, [r11+20h]
0x1800688b2  mov     rsi, [r11+28h]
0x1800688b6  mov     rsp, r11
0x1800688b9  pop     r14
0x1800688bb  pop     rdi
0x1800688bc  pop     rbp
0x1800688bd  retn
```
