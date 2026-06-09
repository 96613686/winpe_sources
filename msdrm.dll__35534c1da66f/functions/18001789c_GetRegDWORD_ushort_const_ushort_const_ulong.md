# GetRegDWORD(ushort const *,ushort const *,ulong *)

- ea: `0x18001789c`
- end: `0x18001795f`
- name: `?GetRegDWORD@@YAHPEBG0PEAK@Z`
- size: `195`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180017cf4`

## callees

- `0x18001789c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001794f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001794f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800178f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800178f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001792c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001792c`

## string_xrefs

- `0x180017925`: `updateFrequency`
- `0x1800178e9`: `SOFTWARE\Policies\Microsoft\MSDRM\TemplateManagement`

## pseudocode

```c
__int64 __fastcall GetRegDWORD(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  int v8; // [rsp+64h] [rbp+24h]
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  int v10; // [rsp+6Ch] [rbp+2Ch]
  unsigned int Data; // [rsp+78h] [rbp+38h] BYREF

  v10 = HIDWORD(a2);
  v8 = HIDWORD(a1);
  v3 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  if ( a3 )
  {
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Policies\\Microsoft\\MSDRM\\TemplateManagement",
            0,
            0x20019u,
            &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"updateFrequency", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      {
        v3 = 1;
        *a3 = Data;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18001789c  mov     qword ptr [rsp-18h+cbData], rdx
0x1800178a1  mov     qword ptr [rsp-18h+Type], rcx
0x1800178a6  push    rbp
0x1800178a7  push    rbx
0x1800178a8  push    rdi
0x1800178a9  mov     rbp, rsp
0x1800178ac  sub     rsp, 40h
0x1800178b0  xor     ebx, ebx
0x1800178b2  mov     [rbp+hKey], 0
0x1800178ba  mov     [rbp+Type], 0
0x1800178c1  mov     rdi, r8
0x1800178c4  mov     [rbp+Data], 0
0x1800178cb  mov     [rbp+cbData], 0
0x1800178d2  test    r8, r8
0x1800178d5  jz      short loc_180017955
0x1800178d7  lea     rax, [rbp+hKey]
0x1800178db  mov     r9d, 20019h; samDesired
0x1800178e1  xor     r8d, r8d; ulOptions
0x1800178e4  mov     [rsp+40h+phkResult], rax; phkResult
0x1800178e9  lea     rdx, ?g_wszTM_Policy_Key@@3QBGB; "SOFTWARE\\Policies\\Microsoft\\MSDRM\\T"...
0x1800178f0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800178f7  call    cs:__imp_RegOpenKeyExW
0x1800178fd  test    eax, eax
0x1800178ff  jnz     short loc_180017946
0x180017901  mov     rcx, [rbp+hKey]; hKey
0x180017905  lea     rax, [rbp+cbData]
0x180017909  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001790e  lea     r9, [rbp+Type]; lpType
0x180017912  lea     rax, [rbp+Data]
0x180017916  mov     [rbp+cbData], 4
0x18001791d  xor     r8d, r8d; lpReserved
0x180017920  mov     [rsp+40h+phkResult], rax; lpData
0x180017925  lea     rdx, ?g_wszTM_Value_updateFrequency@@3QBGB; "updateFrequency"
0x18001792c  call    cs:__imp_RegQueryValueExW
0x180017932  test    eax, eax
0x180017934  jnz     short loc_180017946
0x180017936  cmp     [rbp+Type], 4
0x18001793a  jnz     short loc_180017946
0x18001793c  mov     eax, [rbp+Data]
0x18001793f  mov     ebx, 1
0x180017944  mov     [rdi], eax
0x180017946  mov     rcx, [rbp+hKey]; hKey
0x18001794a  test    rcx, rcx
0x18001794d  jz      short loc_180017955
0x18001794f  call    cs:__imp_RegCloseKey
0x180017955  mov     eax, ebx
0x180017957  add     rsp, 40h
0x18001795b  pop     rdi
0x18001795c  pop     rbx
0x18001795d  pop     rbp
0x18001795e  retn
```
