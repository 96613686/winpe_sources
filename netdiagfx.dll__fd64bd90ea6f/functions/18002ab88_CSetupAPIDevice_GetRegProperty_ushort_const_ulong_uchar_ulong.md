# CSetupAPIDevice::GetRegProperty(ushort const *,ulong *,uchar *,ulong *)

- ea: `0x18002ab88`
- end: `0x18002ac32`
- name: `?GetRegProperty@CSetupAPIDevice@@QEAAJPEBGPEAKPEAE1@Z`
- size: `170`
- prototype: `int __fastcall(CSetupAPIDevice *this, const unsigned __int16 *, unsigned int *, unsigned __int8 *, unsigned int *lpcbData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18002ac38`

## callees

- `0x18002ab88`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002abec`
- `KERNEL32!GetLastError` at `0x18002abec`
- `ADVAPI32!RegQueryValueExW` at `0x18002ac10`
- `ADVAPI32!RegQueryValueExW` at `0x18002ac10`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x18002abd9`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x18002abd9`

## pseudocode

```c
int __fastcall CSetupAPIDevice::GetRegProperty(
        CSetupAPIDevice *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int8 *a4,
        unsigned int *lpcbData)
{
  __int64 v5; // rax
  int result; // eax
  HKEY v10; // rcx
  HKEY v11; // rax

  v5 = *((_QWORD *)this + 1);
  if ( !v5 )
    return -2147467259;
  v10 = (HKEY)*((_QWORD *)this + 6);
  if ( v10 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    && (v11 = SetupDiOpenDevRegKey(*(HDEVINFO *)(v5 + 8), (PSP_DEVINFO_DATA)((char *)this + 16), 1u, 0, 2u, 0x20019u),
        *((_QWORD *)this + 6) = v11,
        v10 = v11,
        v11 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL) )
  {
    result = GetLastError();
  }
  else
  {
    result = RegQueryValueExW(v10, L"NetCfgInstanceId", 0, a3, a4, lpcbData);
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002ab88  mov     [rsp+arg_0], rbx
0x18002ab8d  mov     [rsp+arg_8], rsi
0x18002ab92  push    rdi
0x18002ab93  sub     rsp, 30h
0x18002ab97  mov     rax, [rcx+8]
0x18002ab9b  mov     rdi, r9
0x18002ab9e  mov     rsi, r8
0x18002aba1  mov     rbx, rcx
0x18002aba4  test    rax, rax
0x18002aba7  jnz     short loc_18002ABB0
0x18002aba9  mov     eax, 80004005h
0x18002abae  jmp     short loc_18002AC22
0x18002abb0  mov     rcx, [rcx+30h]; hKey
0x18002abb4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002abb8  jnz     short loc_18002ABF4
0x18002abba  lea     r8d, [rcx+2]; Scope
0x18002abbe  mov     [rsp+38h+samDesired], 20019h; samDesired
0x18002abc6  mov     rcx, [rax+8]; DeviceInfoSet
0x18002abca  lea     rdx, [rbx+10h]; DeviceInfoData
0x18002abce  xor     r9d, r9d; HwProfile
0x18002abd1  mov     [rsp+38h+KeyType], 2; KeyType
0x18002abd9  call    cs:__imp_SetupDiOpenDevRegKey
0x18002abdf  mov     [rbx+30h], rax
0x18002abe3  mov     rcx, rax
0x18002abe6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002abea  jnz     short loc_18002ABF4
0x18002abec  call    cs:__imp_GetLastError
0x18002abf2  jmp     short loc_18002AC16
0x18002abf4  mov     rax, [rsp+38h+lpcbData]
0x18002abf9  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x18002ac00  mov     qword ptr [rsp+38h+samDesired], rax; lpcbData
0x18002ac05  mov     r9, rsi; lpType
0x18002ac08  xor     r8d, r8d; lpReserved
0x18002ac0b  mov     qword ptr [rsp+38h+KeyType], rdi; lpData
0x18002ac10  call    cs:__imp_RegQueryValueExW
0x18002ac16  test    eax, eax
0x18002ac18  jle     short loc_18002AC22
0x18002ac1a  movzx   eax, ax
0x18002ac1d  or      eax, 80070000h
0x18002ac22  mov     rbx, [rsp+38h+arg_0]
0x18002ac27  mov     rsi, [rsp+38h+arg_8]
0x18002ac2c  add     rsp, 30h
0x18002ac30  pop     rdi
0x18002ac31  retn
```
