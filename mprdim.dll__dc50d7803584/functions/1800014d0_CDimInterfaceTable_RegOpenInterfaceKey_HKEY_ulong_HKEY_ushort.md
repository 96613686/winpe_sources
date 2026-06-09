# CDimInterfaceTable::RegOpenInterfaceKey(HKEY__ *,ulong,HKEY__ * &,ushort *)

- ea: `0x1800014d0`
- end: `0x180001603`
- name: `?RegOpenInterfaceKey@CDimInterfaceTable@@AEAAKPEAUHKEY__@@KAEAPEAU2@PEAG@Z`
- size: `307`
- prototype: `unsigned int(CDimInterfaceTable *__hidden this, HKEY, unsigned int, HKEY *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800239f8`
- `0x180023e54`
- `0x180026e0c`

## callees

- `0x1800014d0`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180001577`
- `ADVAPI32!RegOpenKeyExW` at `0x180001577`
- `ADVAPI32!RegCloseKey` at `0x1800015f6`
- `ADVAPI32!RegCloseKey` at `0x1800015f6`
- `ADVAPI32!RegQueryValueExW` at `0x1800015a4`
- `ADVAPI32!RegQueryValueExW` at `0x1800015a4`
- `ADVAPI32!RegEnumKeyExW` at `0x180001551`
- `ADVAPI32!RegEnumKeyExW` at `0x180001551`

## pseudocode

```c
LSTATUS __fastcall CDimInterfaceTable::RegOpenInterfaceKey(
        CDimInterfaceTable *this,
        HKEY a2,
        DWORD a3,
        HKEY *a4,
        BYTE *lpData)
{
  LSTATUS v8; // ebx
  LSTATUS result; // eax
  DWORD Type; // [rsp+40h] [rbp-258h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-254h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-250h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-248h] BYREF

  memset_0(Name, 0, 0x202u);
  cchName = 257;
  Type = 0;
  cbData = 514;
  *a4 = 0;
  v8 = RegEnumKeyExW(a2, a3, Name, &cchName, 0, 0, 0, 0);
  if ( !v8 )
  {
    v8 = RegOpenKeyExW(a2, Name, 0, 0x20019u, a4);
    if ( !v8 )
    {
      result = RegQueryValueExW(*a4, L"InterfaceName", 0, &Type, lpData, &cbData);
      v8 = result;
      if ( result || Type == 1 )
      {
        *((_WORD *)lpData + 256) = 0;
        if ( !result )
          return result;
      }
      else
      {
        v8 = 1015;
        *((_WORD *)lpData + 256) = 0;
      }
    }
  }
  if ( *a4 )
  {
    RegCloseKey(*a4);
    *a4 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x1800014d0  push    rbx
0x1800014d2  push    rbp
0x1800014d3  push    rsi
0x1800014d4  push    rdi
0x1800014d5  push    r14
0x1800014d7  sub     rsp, 270h
0x1800014de  mov     rax, cs:__security_cookie
0x1800014e5  xor     rax, rsp
0x1800014e8  mov     [rsp+298h+var_38], rax
0x1800014f0  mov     rbp, [rsp+298h+lpData]
0x1800014f8  lea     rcx, [rsp+298h+Name]; void *
0x1800014fd  mov     ebx, r8d
0x180001500  mov     rsi, rdx
0x180001503  xor     edx, edx; Val
0x180001505  mov     r8d, 202h; Size
0x18000150b  mov     rdi, r9
0x18000150e  call    memset_0
0x180001513  xor     r14d, r14d
0x180001516  mov     [rsp+298h+cchName], 101h
0x18000151e  mov     [rsp+298h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180001523  lea     r9, [rsp+298h+cchName]; lpcchName
0x180001528  mov     [rsp+298h+lpcchClass], r14; lpcchClass
0x18000152d  lea     r8, [rsp+298h+Name]; lpName
0x180001532  mov     [rsp+298h+lpClass], r14; lpClass
0x180001537  mov     edx, ebx; dwIndex
0x180001539  mov     rcx, rsi; hKey
0x18000153c  mov     [rsp+298h+lpReserved], r14; lpReserved
0x180001541  mov     [rsp+298h+Type], r14d
0x180001546  mov     [rsp+298h+cbData], 202h
0x18000154e  mov     [rdi], r14
0x180001551  call    cs:__imp_RegEnumKeyExW
0x180001557  mov     ebx, eax
0x180001559  test    eax, eax
0x18000155b  jnz     loc_1800015EE
0x180001561  mov     r9d, 20019h; samDesired
0x180001567  mov     [rsp+298h+lpReserved], rdi; phkResult
0x18000156c  xor     r8d, r8d; ulOptions
0x18000156f  lea     rdx, [rsp+298h+Name]; lpSubKey
0x180001574  mov     rcx, rsi; hKey
0x180001577  call    cs:__imp_RegOpenKeyExW
0x18000157d  mov     ebx, eax
0x18000157f  test    eax, eax
0x180001581  jnz     short loc_1800015EE
0x180001583  mov     rcx, [rdi]; hKey
0x180001586  lea     rax, [rsp+298h+cbData]
0x18000158b  mov     [rsp+298h+lpClass], rax; lpcbData
0x180001590  lea     r9, [rsp+298h+Type]; lpType
0x180001595  xor     r8d, r8d; lpReserved
0x180001598  mov     [rsp+298h+lpReserved], rbp; lpData
0x18000159d  lea     rdx, ValueName; "InterfaceName"
0x1800015a4  call    cs:__imp_RegQueryValueExW
0x1800015aa  mov     ebx, eax
0x1800015ac  test    eax, eax
0x1800015ae  jz      short loc_1800015DA
0x1800015b0  mov     [rbp+200h], r14w
0x1800015b8  test    eax, eax
0x1800015ba  jnz     short loc_1800015EE
0x1800015bc  mov     rcx, [rsp+298h+var_38]
0x1800015c4  xor     rcx, rsp; StackCookie
0x1800015c7  call    __security_check_cookie
0x1800015cc  add     rsp, 270h
0x1800015d3  pop     r14
0x1800015d5  pop     rdi
0x1800015d6  pop     rsi
0x1800015d7  pop     rbp
0x1800015d8  pop     rbx
0x1800015d9  retn
0x1800015da  cmp     [rsp+298h+Type], 1
0x1800015df  jz      short loc_1800015B0
0x1800015e1  mov     ebx, 3F7h
0x1800015e6  mov     [rbp+200h], r14w
0x1800015ee  mov     rcx, [rdi]; hKey
0x1800015f1  test    rcx, rcx
0x1800015f4  jz      short loc_1800015FF
0x1800015f6  call    cs:__imp_RegCloseKey
0x1800015fc  mov     [rdi], r14
0x1800015ff  mov     eax, ebx
0x180001601  jmp     short loc_1800015BC
```
