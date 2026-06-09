# GetRegistryValue

- ea: `0x18002091c`
- end: `0x180020a34`
- name: `GetRegistryValue`
- size: `280`
- prototype: `HRESULT __fastcall(HREG hkey, const wchar_t *wszValue, _KEY_VALUE_FULL_INFORMATION **ppinfo, unsigned int hkey)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800126bc`
- `0x180013f54`
- `0x180020874`
- `0x180043ba8`
- `0x18005e370`

## callees

- `0x18002091c`
- `0x180020b10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180020945`
- `ntdll!RtlInitUnicodeString` at `0x180020945`
- `ntdll!ZwQueryValueKey` at `0x18002096f`
- `ntdll!ZwQueryValueKey` at `0x1800209e3`
- `ntdll!ZwQueryValueKey` at `0x18002096f`
- `ntdll!ZwQueryValueKey` at `0x1800209e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800209a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800209a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800209fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020a21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800209fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020a21`

## pseudocode

```c
HRESULT __fastcall GetRegistryValue(
        HREG hkey,
        const wchar_t *wszValue,
        _KEY_VALUE_FULL_INFORMATION **ppinfo,
        unsigned int a4)
{
  NTSTATUS v6; // eax
  int v7; // ecx
  _KEY_VALUE_FULL_INFORMATION *v9; // rax
  _KEY_VALUE_FULL_INFORMATION *v10; // rdi
  NTSTATUS v11; // ebx
  _UNICODE_STRING unicodeString; // [rsp+30h] [rbp-18h] BYREF
  unsigned int keyValueLength; // [rsp+68h] [rbp+20h] BYREF

  keyValueLength = 0;
  unicodeString = 0;
  RtlInitUnicodeString(&unicodeString, wszValue);
  v6 = ZwQueryValueKey(hkey.h, &unicodeString, KeyValueFullInformation, 0, 0, &keyValueLength);
  if ( v6 != -2147483643 && v6 != -1073741789 )
  {
    v7 = v6;
    return HrNt(v7);
  }
  v9 = (_KEY_VALUE_FULL_INFORMATION *)CoTaskMemAlloc(keyValueLength);
  v10 = v9;
  if ( !v9 )
  {
    v7 = -1073741670;
    return HrNt(v7);
  }
  v11 = ZwQueryValueKey(hkey.h, &unicodeString, KeyValueFullInformation, v9, keyValueLength, &keyValueLength);
  if ( v11 < 0 )
  {
    CoTaskMemFree(v10);
    v7 = v11;
    return HrNt(v7);
  }
  if ( v10->Type == 1 )
  {
    *ppinfo = v10;
    return 0;
  }
  else
  {
    CoTaskMemFree(v10);
    return -2147221165;
  }
}

```

## disassembly

```asm
0x18002091c  mov     rax, rsp
0x18002091f  mov     [rax+8], rbx
0x180020923  mov     [rax+10h], rsi
0x180020927  mov     [rax+20h], r9d
0x18002092b  push    rdi
0x18002092c  sub     rsp, 40h
0x180020930  and     dword ptr [rax+20h], 0
0x180020934  mov     rbx, hkey
0x180020937  xorps   xmm0, xmm0
0x18002093a  lea     hkey, [rax-18h]; DestinationString
0x18002093e  movups  xmmword ptr [rax-18h], xmm0
0x180020942  mov     rsi, ppinfo
0x180020945  call    cs:__imp_RtlInitUnicodeString
0x18002094c  nop     dword ptr [rax+rax+00h]
0x180020951  xor     r9d, r9d; KeyValueInformation
0x180020954  lea     rax, [rsp+48h+keyValueLength]
0x180020959  mov     [rsp+48h+ResultLength], rax; ResultLength
0x18002095e  lea     wszValue, [rsp+48h+unicodeString]; ValueName
0x180020963  and     [rsp+48h+Length], 0
0x180020968  mov     hkey, rbx; KeyHandle
0x18002096b  lea     r8d, [r9+1]; KeyValueInformationClass
0x18002096f  call    cs:__imp_ZwQueryValueKey
0x180020976  nop     dword ptr [rax+rax+00h]
0x18002097b  cmp     eax, 80000005h
0x180020980  jz      short loc_1800209A1
0x180020982  cmp     eax, 0C0000023h
0x180020987  jz      short loc_1800209A1
0x180020989  mov     ecx, eax; status
0x18002098b  call    HrNt
0x180020990  mov     rbx, [rsp+48h+arg_0]
0x180020995  mov     rsi, [rsp+48h+arg_8]
0x18002099a  add     rsp, 40h
0x18002099e  pop     rdi
0x18002099f  retn
0x1800209a1  mov     ecx, [rsp+48h+keyValueLength]; cb
0x1800209a5  call    cs:__imp_CoTaskMemAlloc
0x1800209ac  nop     dword ptr [rax+rax+00h]
0x1800209b1  mov     rdi, rax
0x1800209b4  test    rax, rax
0x1800209b7  jnz     short loc_1800209C0
0x1800209b9  mov     ecx, 0C000009Ah
0x1800209be  jmp     short loc_18002098B
0x1800209c0  lea     rax, [rsp+48h+keyValueLength]
0x1800209c5  mov     r9, rdi; KeyValueInformation
0x1800209c8  mov     [rsp+48h+ResultLength], rax; ResultLength
0x1800209cd  lea     wszValue, [rsp+48h+unicodeString]; ValueName
0x1800209d2  mov     eax, [rsp+48h+keyValueLength]
0x1800209d6  mov     r8d, 1; KeyValueInformationClass
0x1800209dc  mov     hkey, rbx; KeyHandle
0x1800209df  mov     [rsp+48h+Length], eax; Length
0x1800209e3  call    cs:__imp_ZwQueryValueKey
0x1800209ea  nop     dword ptr [rax+rax+00h]
0x1800209ef  mov     ebx, eax
0x1800209f1  test    eax, eax
0x1800209f3  js      short loc_180020A1E
0x1800209f5  cmp     dword ptr [rdi+4], 1
0x1800209f9  jz      short loc_180020A14
0x1800209fb  mov     hkey, rdi; pv
0x1800209fe  call    cs:__imp_CoTaskMemFree
0x180020a05  nop     dword ptr [rax+rax+00h]
0x180020a0a  mov     eax, 80040153h
0x180020a0f  jmp     loc_180020990
0x180020a14  mov     [rsi], rdi
0x180020a17  xor     eax, eax
0x180020a19  jmp     loc_180020990
0x180020a1e  mov     hkey, rdi; pv
0x180020a21  call    cs:__imp_CoTaskMemFree
0x180020a28  nop     dword ptr [rax+rax+00h]
0x180020a2d  mov     ecx, ebx
0x180020a2f  jmp     loc_18002098B
```
