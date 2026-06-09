# CheckAndDisableOOBETrigger(void)

- ea: `0x1400025c0`
- end: `0x140002700`
- name: `?CheckAndDisableOOBETrigger@@YAJXZ`
- size: `320`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003610`

## callees

- `0x14000233f`
- `0x1400025c0`
- `0x1400115f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400026df`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400026df`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400025df`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400025df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000268c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000268c`
- `dcntel!SetCustomTriggerEx` at `0x14000260e`
- `dcntel!SetCustomTriggerEx` at `0x1400026b4`
- `dcntel!SetCustomTriggerEx` at `0x1400026d7`
- `dcntel!SetCustomTriggerEx` at `0x14000260e`
- `dcntel!SetCustomTriggerEx` at `0x1400026b4`
- `dcntel!SetCustomTriggerEx` at `0x1400026d7`
- `dcntel!SetCustomTrigger` at `0x1400025f1`
- `dcntel!SetCustomTrigger` at `0x1400025f1`
- `dcntel!GetCensusRegistryLocation` at `0x140002640`
- `dcntel!GetCensusRegistryLocation` at `0x140002640`

## string_xrefs

- `0x1400025f7`: `WNF_CSHL_PRODUCT_READY`
- `0x14000269d`: `WNF_SHEL_OOBE_USER_LOGON_COMPLETE`
- `0x1400026c0`: `WNF_SHEL_OOBE_USER_LOGON_COMPLETE`

## pseudocode

```c
__int64 CheckAndDisableOOBETrigger(void)
{
  HRESULT v0; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-238h] BYREF
  unsigned int pvData[3]; // [rsp+44h] [rbp-234h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF

  v0 = CoInitializeEx(0, 0);
  if ( v0 >= 0 )
  {
    SetCustomTrigger(0);
    SetCustomTriggerEx(
      0,
      L"\\Microsoft\\Windows\\Application Experience",
      L"Device Census Gather",
      L"WNF_CSHL_PRODUCT_READY");
    pvData[0] = 0;
    pcbData = 0;
    memset_0(SubKey, 0, 0x20Au);
    if ( (int)GetCensusRegistryLocation(SubKey, 0x105u) >= 0 )
    {
      pcbData = 4;
      if ( !RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"RunCounter", 0x10u, 0, pvData, &pcbData) && pvData[0] >= 2 )
      {
        v0 = SetCustomTriggerEx(
               0,
               L"\\Microsoft\\Windows\\Device Information",
               L"Device",
               L"WNF_SHEL_OOBE_USER_LOGON_COMPLETE");
        if ( v0 < 0 )
          v0 = SetCustomTriggerEx(
                 0,
                 L"\\Microsoft\\Windows\\Application Experience",
                 L"Device Census Gather",
                 L"WNF_SHEL_OOBE_USER_LOGON_COMPLETE");
      }
    }
    CoUninitialize();
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400025c0  push    rbx
0x1400025c2  sub     rsp, 270h
0x1400025c9  mov     rax, cs:__security_cookie
0x1400025d0  xor     rax, rsp
0x1400025d3  mov     [rsp+278h+var_18], rax
0x1400025db  xor     edx, edx; dwCoInit
0x1400025dd  xor     ecx, ecx; pvReserved
0x1400025df  call    cs:__imp_CoInitializeEx
0x1400025e5  mov     ebx, eax
0x1400025e7  test    eax, eax
0x1400025e9  js      loc_1400026E5
0x1400025ef  xor     ecx, ecx
0x1400025f1  call    cs:__imp_?SetCustomTrigger@@YAJH@Z; SetCustomTrigger(int)
0x1400025f7  lea     r9, aWnfCshlProduct; "WNF_CSHL_PRODUCT_READY"
0x1400025fe  xor     ecx, ecx
0x140002600  lea     r8, aDeviceCensusGa; "Device Census Gather"
0x140002607  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Application Exper"...
0x14000260e  call    cs:__imp_?SetCustomTriggerEx@@YAJHPEBG00@Z; SetCustomTriggerEx(int,ushort const *,ushort const *,ushort const *)
0x140002614  xor     edx, edx; Val
0x140002616  mov     [rsp+278h+var_234], 0
0x14000261e  mov     r8d, 20Ah; Size
0x140002624  mov     [rsp+278h+var_238], 0
0x14000262c  lea     rcx, [rsp+278h+SubKey]; void *
0x140002631  call    memset_0
0x140002636  mov     edx, 105h
0x14000263b  lea     rcx, [rsp+278h+SubKey]
0x140002640  call    cs:__imp_?GetCensusRegistryLocation@@YAJPEAGK@Z; GetCensusRegistryLocation(ushort *,ulong)
0x140002646  test    eax, eax
0x140002648  js      loc_1400026DF
0x14000264e  lea     rax, [rsp+278h+var_238]
0x140002653  mov     [rsp+278h+var_238], 4
0x14000265b  mov     [rsp+278h+pcbData], rax; pcbData
0x140002660  lea     r8, Value; "RunCounter"
0x140002667  lea     rax, [rsp+278h+var_234]
0x14000266c  mov     r9d, 10h; dwFlags
0x140002672  mov     [rsp+278h+pvData], rax; pvData
0x140002677  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x14000267c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140002683  mov     [rsp+278h+pdwType], 0; pdwType
0x14000268c  call    cs:__imp_RegGetValueW
0x140002692  test    eax, eax
0x140002694  jnz     short loc_1400026DF
0x140002696  cmp     [rsp+278h+var_234], 2
0x14000269b  jb      short loc_1400026DF
0x14000269d  lea     r9, aWnfShelOobeUse; "WNF_SHEL_OOBE_USER_LOGON_COMPLETE"
0x1400026a4  xor     ecx, ecx
0x1400026a6  lea     r8, aDevice; "Device"
0x1400026ad  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\Device Informatio"...
0x1400026b4  call    cs:__imp_?SetCustomTriggerEx@@YAJHPEBG00@Z; SetCustomTriggerEx(int,ushort const *,ushort const *,ushort const *)
0x1400026ba  mov     ebx, eax
0x1400026bc  test    eax, eax
0x1400026be  jns     short loc_1400026DF
0x1400026c0  lea     r9, aWnfShelOobeUse; "WNF_SHEL_OOBE_USER_LOGON_COMPLETE"
0x1400026c7  xor     ecx, ecx
0x1400026c9  lea     r8, aDeviceCensusGa; "Device Census Gather"
0x1400026d0  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Application Exper"...
0x1400026d7  call    cs:__imp_?SetCustomTriggerEx@@YAJHPEBG00@Z; SetCustomTriggerEx(int,ushort const *,ushort const *,ushort const *)
0x1400026dd  mov     ebx, eax
0x1400026df  call    cs:__imp_CoUninitialize
0x1400026e5  mov     eax, ebx
0x1400026e7  mov     rcx, [rsp+278h+var_18]
0x1400026ef  xor     rcx, rsp; StackCookie
0x1400026f2  call    __security_check_cookie
0x1400026f7  add     rsp, 270h
0x1400026fe  pop     rbx
0x1400026ff  retn
```
