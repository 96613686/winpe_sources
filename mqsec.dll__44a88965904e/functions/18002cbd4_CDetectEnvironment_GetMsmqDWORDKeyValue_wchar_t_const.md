# CDetectEnvironment::GetMsmqDWORDKeyValue(wchar_t const *)

- ea: `0x18002cbd4`
- end: `0x18002cc6d`
- name: `?GetMsmqDWORDKeyValue@CDetectEnvironment@@AEAAKPEB_W@Z`
- size: `153`
- prototype: `unsigned int __fastcall(CDetectEnvironment *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cc74`

## callees

- `0x180005d48`
- `0x18002cbd4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18002cc4a`
- `ADVAPI32!RegQueryValueExW` at `0x18002cc4a`
- `ADVAPI32!RegOpenKeyExW` at `0x18002cc09`
- `ADVAPI32!RegOpenKeyExW` at `0x18002cc09`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDetectEnvironment::GetMsmqDWORDKeyValue(CDetectEnvironment *this, const wchar_t *a2)
{
  unsigned int v2; // ebx
  CDetectEnvironment *cbData; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *Data; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = a2;
  cbData = this;
  v2 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSMQ\\Parameters", 0, 0x20019u, &hKey) )
  {
    LODWORD(Data) = 0;
    Type = 4;
    LODWORD(cbData) = 4;
    if ( (RegQueryValueExW(hKey, L"Workgroup", 0, &Type, (LPBYTE)&Data, (LPDWORD)&cbData) & 0xFFFFFFFD) == 0 )
      v2 = (unsigned int)Data;
  }
  CRegHandle::~CRegHandle((CRegHandle *)&hKey);
  return v2;
}

```

## disassembly

```asm
0x18002cbd4  mov     r11, rsp
0x18002cbd7  mov     [r11+10h], rdx
0x18002cbdb  mov     [r11+8], rcx
0x18002cbdf  push    rbx
0x18002cbe0  sub     rsp, 30h
0x18002cbe4  xor     ebx, ebx
0x18002cbe6  mov     [r11+20h], rbx
0x18002cbea  lea     rax, [r11+20h]
0x18002cbee  mov     [r11-18h], rax
0x18002cbf2  mov     r9d, 20019h; samDesired
0x18002cbf8  xor     r8d, r8d; ulOptions
0x18002cbfb  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MSMQ\\Parameters"
0x18002cc02  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002cc09  call    cs:__imp_RegOpenKeyExW
0x18002cc0f  test    eax, eax
0x18002cc11  jnz     short loc_18002CC5B
0x18002cc13  mov     dword ptr [rsp+38h+Data], ebx
0x18002cc17  lea     eax, [rbx+4]
0x18002cc1a  mov     [rsp+38h+Type], eax
0x18002cc1e  mov     dword ptr [rsp+38h+cbData], eax
0x18002cc22  lea     rax, [rsp+38h+cbData]
0x18002cc27  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002cc2c  lea     rax, [rsp+38h+Data]
0x18002cc31  mov     [rsp+38h+lpData], rax; lpData
0x18002cc36  lea     r9, [rsp+38h+Type]; lpType
0x18002cc3b  xor     r8d, r8d; lpReserved
0x18002cc3e  lea     rdx, aWorkgroup; "Workgroup"
0x18002cc45  mov     rcx, [rsp+38h+hKey]; hKey
0x18002cc4a  call    cs:__imp_RegQueryValueExW
0x18002cc50  test    eax, 0FFFFFFFDh
0x18002cc55  jnz     short loc_18002CC5B
0x18002cc57  mov     ebx, dword ptr [rsp+38h+Data]
0x18002cc5b  lea     rcx, [rsp+38h+hKey]; this
0x18002cc60  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18002cc65  mov     eax, ebx
0x18002cc67  add     rsp, 30h
0x18002cc6b  pop     rbx
0x18002cc6c  retn
```
