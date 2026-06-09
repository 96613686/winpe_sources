# MdmWinsOverGp_UnblockForGp(int)

- ea: `0x1800760a0`
- end: `0x1800761a7`
- name: `?MdmWinsOverGp_UnblockForGp@@YAJH@Z`
- size: `263`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180010fec`

## callees

- `0x1800071c0`
- `0x18000fdc0`
- `0x1800118f8`
- `0x180011938`
- `0x18003b0bc`
- `0x1800760a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800760dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800760dc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007616d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007616d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007610b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076199`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007610b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076199`

## string_xrefs

- `0x180076161`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MdmWinsOverGp_UnblockForGp()
{
  unsigned int v0; // eax
  __int64 v1; // rcx
  unsigned int v2; // ebx
  int v4; // eax
  __int64 v5; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  int phkResulta; // [rsp+20h] [rbp-28h]
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  int v9[4]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, c_szMDMWinsOverGpBlockRoot, 0, 0x2001Fu, &hKey);
  if ( v0 )
  {
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x436,
           (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
           (const char *)v0,
           phkResult);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  v9[0] = 0;
  v4 = MdmWinsOverGp_RecurseBlockRecord(v1, 1u, c_szMDMWinsOverGpBlockRoot, hKey, v9);
  v2 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x439,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
      (const char *)(unsigned int)v4,
      phkResulta);
    goto LABEL_3;
  }
  RegDeleteValueW(hKey, L"Delete");
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
    McTemplateU0d_EventWriteTransfer(v5, RecordsCleanupSuccessful, 1);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800760a0  push    rbx
0x1800760a2  sub     rsp, 40h
0x1800760a6  mov     [rsp+48h+hKey], 0
0x1800760af  xor     edx, edx
0x1800760b1  lea     rcx, [rsp+48h+hKey]
0x1800760b6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800760bb  lea     rax, [rsp+48h+hKey]
0x1800760c0  mov     qword ptr [rsp+48h+phkResult], rax; unsigned int
0x1800760c5  mov     r9d, 2001Fh; samDesired
0x1800760cb  xor     r8d, r8d; ulOptions
0x1800760ce  mov     rdx, cs:?c_szMDMWinsOverGpBlockRoot@@3PEBGEB; lpSubKey
0x1800760d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800760dc  call    cs:__imp_RegOpenKeyExW
0x1800760e2  test    eax, eax
0x1800760e4  jz      short loc_180076118
0x1800760e6  mov     rcx, [rsp+48h]; this
0x1800760eb  mov     r9d, eax; char *
0x1800760ee  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\dm\\dmcfgutils\\mdmw"...
0x1800760f5  mov     edx, 436h; void *
0x1800760fa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800760ff  mov     ebx, eax
0x180076101  mov     rcx, [rsp+48h+hKey]; hKey
0x180076106  test    rcx, rcx
0x180076109  jz      short loc_180076111
0x18007610b  call    cs:__imp_RegCloseKey
0x180076111  mov     eax, ebx
0x180076113  jmp     loc_1800761A1
0x180076118  mov     [rsp+48h+var_10], 0
0x180076120  lea     rax, [rsp+48h+var_10]
0x180076125  mov     qword ptr [rsp+48h+phkResult], rax; int
0x18007612a  mov     r9, [rsp+48h+hKey]; HKEY
0x18007612f  mov     r8, cs:?c_szMDMWinsOverGpBlockRoot@@3PEBGEB; unsigned __int16 *
0x180076136  mov     edx, 1; unsigned int
0x18007613b  call    ?MdmWinsOverGp_RecurseBlockRecord@@YAJHKPEBGPEAUHKEY__@@PEAH@Z; MdmWinsOverGp_RecurseBlockRecord(int,ulong,ushort const *,HKEY__ *,int *)
0x180076140  mov     ebx, eax
0x180076142  test    eax, eax
0x180076144  jns     short loc_180076161
0x180076146  mov     rcx, [rsp+48h]; this
0x18007614b  mov     r9d, eax; char *
0x18007614e  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\dm\\dmcfgutils\\mdmw"...
0x180076155  mov     edx, 439h; void *
0x18007615a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007615f  jmp     short loc_180076101
0x180076161  lea     rdx, aDelete; "Delete"
0x180076168  mov     rcx, [rsp+48h+hKey]; hKey
0x18007616d  call    cs:__imp_RegDeleteValueW
0x180076173  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x18007617a  jz      short loc_18007618F
0x18007617c  mov     r8d, 1
0x180076182  lea     rdx, RecordsCleanupSuccessful
0x180076189  call    McTemplateU0d_EventWriteTransfer
0x18007618e  nop
0x18007618f  mov     rcx, [rsp+48h+hKey]; hKey
0x180076194  test    rcx, rcx
0x180076197  jz      short loc_18007619F
0x180076199  call    cs:__imp_RegCloseKey
0x18007619f  xor     eax, eax
0x1800761a1  add     rsp, 40h
0x1800761a5  pop     rbx
0x1800761a6  retn
```
