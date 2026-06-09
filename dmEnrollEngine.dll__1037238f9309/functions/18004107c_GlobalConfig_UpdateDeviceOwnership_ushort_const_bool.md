# GlobalConfig::UpdateDeviceOwnership(ushort const *,bool)

- ea: `0x18004107c`
- end: `0x1800411c6`
- name: `?UpdateDeviceOwnership@GlobalConfig@@AEAAJPEBG_N@Z`
- size: `330`
- prototype: `int(GlobalConfig *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180019ad0`
- `0x18006b980`

## callees

- `0x1800071c0`
- `0x18004107c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800410f6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800410f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041171`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041171`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041125`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041125`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800411ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800411ae`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18004118a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18004118a`

## pseudocode

```c
__int64 __fastcall GlobalConfig::UpdateDeviceOwnership(GlobalConfig *this, const unsigned __int16 *a2, char a3)
{
  LSTATUS Key; // eax
  unsigned int v6; // ebx
  bool v7; // cc
  int v8; // eax
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  int Data; // [rsp+80h] [rbp+20h] BYREF
  int v12; // [rsp+84h] [rbp+24h]
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF

  v12 = HIDWORD(this);
  hKey[0] = 0;
  Data = 0;
  cbData = 4;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2011Fu, 0, hKey, 0);
  v6 = Key;
  v7 = Key <= 0;
  if ( Key )
    goto LABEL_14;
  Key = RegQueryValueExW(hKey[0], a2, 0, 0, (LPBYTE)&Data, &cbData);
  v6 = Key;
  if ( Key != 2 )
  {
    v7 = Key <= 0;
    if ( !Key )
    {
      if ( a3 )
        v8 = Data + 1;
      else
        v8 = Data - 1;
      goto LABEL_8;
    }
LABEL_14:
    if ( v7 )
      goto LABEL_16;
    goto LABEL_15;
  }
  v8 = 1;
LABEL_8:
  v6 = 0;
  Data = v8;
  if ( v8 )
    Key = RegSetValueExW(hKey[0], a2, 0, 4u, (const BYTE *)&Data, 4u);
  else
    Key = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, lpSubKey, a2);
  if ( !Key )
    goto LABEL_16;
  if ( Key <= 0 )
  {
    v6 = Key;
    goto LABEL_16;
  }
LABEL_15:
  v6 = (unsigned __int16)Key | 0x80070000;
LABEL_16:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v6;
}

```

## disassembly

```asm
0x18004107c  mov     [rsp-18h+arg_8], rbx
0x180041081  mov     qword ptr [rsp-18h+Data], rcx
0x180041086  push    rbp
0x180041087  push    rsi
0x180041088  push    rdi
0x180041089  mov     rbp, rsp
0x18004108c  sub     rsp, 60h
0x180041090  mov     rdi, rdx
0x180041093  mov     [rbp+hKey], 0
0x18004109b  xor     edx, edx
0x18004109d  mov     [rbp+Data], 0
0x1800410a4  lea     rcx, [rbp+hKey]
0x1800410a8  mov     [rbp+cbData], 4
0x1800410af  mov     sil, r8b
0x1800410b2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800410b7  mov     rdx, cs:lpSubKey; lpSubKey
0x1800410be  lea     rax, [rbp+hKey]
0x1800410c2  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800410cb  xor     r9d, r9d; lpClass
0x1800410ce  mov     [rsp+60h+phkResult], rax; phkResult
0x1800410d3  xor     r8d, r8d; Reserved
0x1800410d6  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800410df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800410e6  mov     [rsp+60h+samDesired], 2011Fh; samDesired
0x1800410ee  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1800410f6  call    cs:__imp_RegCreateKeyExW
0x1800410fc  mov     ebx, eax
0x1800410fe  test    eax, eax
0x180041100  jnz     loc_18004119A
0x180041106  mov     rcx, [rbp+hKey]; hKey
0x18004110a  lea     rax, [rbp+cbData]
0x18004110e  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180041113  xor     r9d, r9d; lpType
0x180041116  lea     rax, [rbp+Data]
0x18004111a  xor     r8d, r8d; lpReserved
0x18004111d  mov     rdx, rdi; lpValueName
0x180041120  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180041125  call    cs:__imp_RegQueryValueExW
0x18004112b  mov     ebx, eax
0x18004112d  cmp     eax, 2
0x180041130  jnz     short loc_180041137
0x180041132  lea     eax, [rbx-1]
0x180041135  jmp     short loc_180041149
0x180041137  test    eax, eax
0x180041139  jnz     short loc_18004119A
0x18004113b  mov     eax, [rbp+Data]
0x18004113e  test    sil, sil
0x180041141  jz      short loc_180041147
0x180041143  inc     eax
0x180041145  jmp     short loc_180041149
0x180041147  dec     eax
0x180041149  xor     ebx, ebx
0x18004114b  mov     [rbp+Data], eax
0x18004114e  test    eax, eax
0x180041150  jz      short loc_180041179
0x180041152  mov     rcx, [rbp+hKey]; hKey
0x180041156  lea     rax, [rbp+Data]
0x18004115a  mov     [rsp+60h+samDesired], 4; cbData
0x180041162  lea     r9d, [rbx+4]; dwType
0x180041166  xor     r8d, r8d; Reserved
0x180041169  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18004116e  mov     rdx, rdi; lpValueName
0x180041171  call    cs:__imp_RegSetValueExW
0x180041177  jmp     short loc_180041190
0x180041179  mov     rdx, cs:lpSubKey; lpSubKey
0x180041180  mov     r8, rdi; lpValueName
0x180041183  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004118a  call    cs:__imp_RegDeleteKeyValueW
0x180041190  test    eax, eax
0x180041192  jz      short loc_1800411A5
0x180041194  jg      short loc_18004119C
0x180041196  mov     ebx, eax
0x180041198  jmp     short loc_1800411A5
0x18004119a  jle     short loc_1800411A5
0x18004119c  movzx   ebx, ax
0x18004119f  or      ebx, 80070000h
0x1800411a5  mov     rcx, [rbp+hKey]; hKey
0x1800411a9  test    rcx, rcx
0x1800411ac  jz      short loc_1800411B4
0x1800411ae  call    cs:__imp_RegCloseKey
0x1800411b4  mov     eax, ebx
0x1800411b6  mov     rbx, [rsp+60h+arg_8]
0x1800411be  add     rsp, 60h
0x1800411c2  pop     rdi
0x1800411c3  pop     rsi
0x1800411c4  pop     rbp
0x1800411c5  retn
```
