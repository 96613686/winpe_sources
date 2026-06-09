# SettingStore::CRegistryKey::SetValue(ushort const *,SettingStore::TYPE,ulong,uchar const *,ulong)

- ea: `0x180025500`
- end: `0x180025684`
- name: `?SetValue@CRegistryKey@SettingStore@@UEAAJPEBGW4TYPE@2@KPEBEK@Z`
- size: `388`
- prototype: `int __high(const unsigned __int16 *, enum SettingStore::TYPE, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180055f10`

## callees

- `0x18001d514`
- `0x180025500`
- `0x180025a80`
- `0x180031670`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180025615`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180025615`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025560`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025679`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025560`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025679`

## pseudocode

```c
__int64 __fastcall SettingStore::CRegistryKey::SetValue(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int16 a4,
        _BYTE *a5,
        DWORD cbData)
{
  DWORD RegType; // r9d
  const BYTE *lpData; // r11
  LSTATUS v11; // eax
  signed int v12; // ebx
  _FILETIME *p_SystemTimeAsFileTime; // r8
  DWORD v15; // eax
  const BYTE *v16; // r8
  DWORD v17; // r10d
  unsigned int v18; // r11d
  _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ValueName[264]; // [rsp+40h] [rbp-C0h] BYREF

  if ( (_DWORD)a3 || (a4 & 0x4000) == 0 )
  {
    RegType = SettingStore::GetRegType((unsigned int)a3, a2, a3);
    v11 = RegSetValueExW(*(HKEY *)(a1 + 16), a2, 0, RegType, lpData, cbData);
  }
  else
  {
    p_SystemTimeAsFileTime = (_FILETIME *)&v20;
    v20 = *(_QWORD *)L"yes";
    SystemTimeAsFileTime.dwLowDateTime = *(_DWORD *)L"no";
    LOWORD(SystemTimeAsFileTime.dwHighDateTime) = aNo_2[2];
    if ( !*a5 )
      p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
    v15 = SettingStore::GetRegType(2, a2, p_SystemTimeAsFileTime);
    v11 = RegSetValueExW(*(HKEY *)(a1 + 16), a2, 0, v15, v16, v17);
  }
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 >= 0 && (a4 & 0x1000) != 0 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( (int)StringCchCopyW(ValueName, 0x104u, a2) >= 0 && (int)StringCchCatW(ValueName, v18, L"_TIMESTAMP") >= 0 )
      RegSetValueExW(*(HKEY *)(a1 + 16), ValueName, 0, 3u, (const BYTE *)&SystemTimeAsFileTime, 8u);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180025500  push    rbp
0x180025502  push    rbx
0x180025503  push    rsi
0x180025504  push    rdi
0x180025505  push    r14
0x180025507  lea     rbp, [rsp-160h]
0x18002550f  sub     rsp, 260h
0x180025516  mov     rax, cs:__security_cookie
0x18002551d  xor     rax, rsp
0x180025520  mov     [rbp+180h+var_30], rax
0x180025527  mov     r11, [rbp+180h+arg_20]
0x18002552e  mov     edi, r9d
0x180025531  mov     r14, rdx
0x180025534  mov     rsi, rcx
0x180025537  test    r8d, r8d
0x18002553a  jz      short loc_1800255A2
0x18002553c  mov     ecx, r8d
0x18002553f  call    ?GetRegType@SettingStore@@YAKW4TYPE@1@@Z; SettingStore::GetRegType(SettingStore::TYPE)
0x180025544  mov     r9d, eax; dwType
0x180025547  mov     eax, [rbp+180h+arg_28]
0x18002554d  mov     [rsp+280h+cbData], eax; cbData
0x180025551  mov     [rsp+280h+lpData], r11; lpData
0x180025556  mov     rcx, [rsi+10h]; hKey
0x18002555a  xor     r8d, r8d; Reserved
0x18002555d  mov     rdx, r14; lpValueName
0x180025560  call    cs:__imp_RegSetValueExW
0x180025566  mov     ebx, eax
0x180025568  test    eax, eax
0x18002556a  jle     short loc_180025575
0x18002556c  movzx   ebx, ax
0x18002556f  or      ebx, 80070000h
0x180025575  test    ebx, ebx
0x180025577  js      short loc_180025583
0x180025579  bt      edi, 0Ch
0x18002557d  jb      loc_180025607
0x180025583  mov     eax, ebx
0x180025585  mov     rcx, [rbp+180h+var_30]
0x18002558c  xor     rcx, rsp; StackCookie
0x18002558f  call    __security_check_cookie
0x180025594  add     rsp, 260h
0x18002559b  pop     r14
0x18002559d  pop     rdi
0x18002559e  pop     rsi
0x18002559f  pop     rbx
0x1800255a0  pop     rbp
0x1800255a1  retn
0x1800255a2  bt      edi, 0Eh
0x1800255a6  jnb     short loc_18002553C
0x1800255a8  mov     rax, qword ptr cs:aYes; "yes"
0x1800255af  lea     r8, [rsp+280h+var_248]
0x1800255b4  mov     [rsp+280h+var_248], rax
0x1800255b9  mov     ecx, 2
0x1800255be  mov     eax, dword ptr cs:aNo_2; "no"
0x1800255c4  mov     [rsp+280h+SystemTimeAsFileTime.dwLowDateTime], eax
0x1800255c8  movzx   eax, word ptr cs:aNo_2+4; ""
0x1800255cf  mov     word ptr [rsp+280h+SystemTimeAsFileTime.dwHighDateTime], ax
0x1800255d4  mov     al, [r11]
0x1800255d7  neg     al
0x1800255d9  lea     rax, [rsp+280h+SystemTimeAsFileTime]
0x1800255de  sbb     r10d, r10d
0x1800255e1  and     r10d, ecx
0x1800255e4  add     r10d, 6
0x1800255e8  cmp     byte ptr [r11], 0
0x1800255ec  cmovz   r8, rax
0x1800255f0  call    ?GetRegType@SettingStore@@YAKW4TYPE@1@@Z; SettingStore::GetRegType(SettingStore::TYPE)
0x1800255f5  mov     [rsp+280h+cbData], r10d
0x1800255fa  mov     r9d, eax
0x1800255fd  mov     [rsp+280h+lpData], r8
0x180025602  jmp     loc_180025556
0x180025607  lea     rcx, [rsp+280h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002560c  mov     qword ptr [rsp+280h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180025615  call    cs:__imp_GetSystemTimeAsFileTime
0x18002561b  mov     r11d, 104h
0x180025621  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180025626  mov     edx, r11d; unsigned __int64
0x180025629  mov     r8, r14; unsigned __int16 *
0x18002562c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025631  test    eax, eax
0x180025633  js      loc_180025583
0x180025639  lea     r8, aTimestamp_0; "_TIMESTAMP"
0x180025640  mov     edx, r11d; unsigned __int64
0x180025643  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180025648  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002564d  test    eax, eax
0x18002564f  js      loc_180025583
0x180025655  mov     rcx, [rsi+10h]; hKey
0x180025659  lea     rax, [rsp+280h+SystemTimeAsFileTime]
0x18002565e  mov     [rsp+280h+cbData], 8; cbData
0x180025666  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18002566b  mov     r9d, 3; dwType
0x180025671  mov     [rsp+280h+lpData], rax; lpData
0x180025676  xor     r8d, r8d; Reserved
0x180025679  call    cs:__imp_RegSetValueExW
0x18002567f  jmp     loc_180025583
```
