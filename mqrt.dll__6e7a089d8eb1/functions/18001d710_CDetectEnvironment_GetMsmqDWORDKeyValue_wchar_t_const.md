# CDetectEnvironment::GetMsmqDWORDKeyValue(wchar_t const *)

- ea: `0x18001d710`
- end: `0x18001d7a9`
- name: `?GetMsmqDWORDKeyValue@CDetectEnvironment@@AEAAKPEB_W@Z`
- size: `153`
- prototype: `unsigned int __fastcall(CDetectEnvironment *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d7b0`

## callees

- `0x1800113b8`
- `0x18001d710`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001d745`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d745`
- `ADVAPI32!RegQueryValueExW` at `0x18001d786`
- `ADVAPI32!RegQueryValueExW` at `0x18001d786`

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
0x18001d710  mov     r11, rsp
0x18001d713  mov     [r11+10h], rdx
0x18001d717  mov     [r11+8], rcx
0x18001d71b  push    rbx
0x18001d71c  sub     rsp, 30h
0x18001d720  xor     ebx, ebx
0x18001d722  mov     [r11+20h], rbx
0x18001d726  lea     rax, [r11+20h]
0x18001d72a  mov     [r11-18h], rax
0x18001d72e  mov     r9d, 20019h; samDesired
0x18001d734  xor     r8d, r8d; ulOptions
0x18001d737  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MSMQ\\Parameters"
0x18001d73e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d745  call    cs:__imp_RegOpenKeyExW
0x18001d74b  test    eax, eax
0x18001d74d  jnz     short loc_18001D797
0x18001d74f  mov     dword ptr [rsp+38h+Data], ebx
0x18001d753  lea     eax, [rbx+4]
0x18001d756  mov     [rsp+38h+Type], eax
0x18001d75a  mov     dword ptr [rsp+38h+cbData], eax
0x18001d75e  lea     rax, [rsp+38h+cbData]
0x18001d763  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001d768  lea     rax, [rsp+38h+Data]
0x18001d76d  mov     [rsp+38h+lpData], rax; lpData
0x18001d772  lea     r9, [rsp+38h+Type]; lpType
0x18001d777  xor     r8d, r8d; lpReserved
0x18001d77a  lea     rdx, aWorkgroup; "Workgroup"
0x18001d781  mov     rcx, [rsp+38h+hKey]; hKey
0x18001d786  call    cs:__imp_RegQueryValueExW
0x18001d78c  test    eax, 0FFFFFFFDh
0x18001d791  jnz     short loc_18001D797
0x18001d793  mov     ebx, dword ptr [rsp+38h+Data]
0x18001d797  lea     rcx, [rsp+38h+hKey]; this
0x18001d79c  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18001d7a1  mov     eax, ebx
0x18001d7a3  add     rsp, 30h
0x18001d7a7  pop     rbx
0x18001d7a8  retn
```
