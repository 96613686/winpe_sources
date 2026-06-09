# EnumLockedDownComponents(void (*)(ushort const *,void *),void *)

- ea: `0x180007a4c`
- end: `0x180007b35`
- name: `?EnumLockedDownComponents@@YAXP6AXPEBGPEAX@Z1@Z`
- size: `233`
- prototype: `void(void (*)(const unsigned __int16 *, void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006ecc`

## callees

- `0x180001f90`
- `0x180006d30`
- `0x180007a4c`
- `0x180008560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007ae2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007ae2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b0e`

## pseudocode

```c
void __fastcall EnumLockedDownComponents(void (*a1)(const unsigned __int16 *, void *), void *a2)
{
  DWORD i; // ebx
  LSTATUS v4; // eax
  bool v5; // zf
  DWORD cchName; // [rsp+40h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-240h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-238h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-228h] BYREF

  hKey = 0;
  if ( !HrRegOpenKeyEx(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Network\\Lockdown", 0x20019u, &hKey) )
  {
    ftLastWriteTime = 0;
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      v4 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      v5 = v4 == 0;
      if ( v4 > 0 )
        v5 = 0;
      if ( !v5 )
        break;
      ExcludeLockedDownComponents(Name, a2);
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180007a4c  mov     [rsp+arg_0], rbx
0x180007a51  push    rdi
0x180007a52  sub     rsp, 280h
0x180007a59  mov     rax, cs:__security_cookie
0x180007a60  xor     rax, rsp
0x180007a63  mov     [rsp+288h+var_18], rax
0x180007a6b  mov     rdi, rdx
0x180007a6e  mov     [rsp+288h+hKey], 0
0x180007a77  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Net"...
0x180007a7e  mov     r8d, 20019h; unsigned int
0x180007a84  lea     r9, [rsp+288h+hKey]; HKEY *
0x180007a89  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180007a90  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180007a95  test    eax, eax
0x180007a97  jnz     short loc_180007B14
0x180007a99  mov     qword ptr [rsp+288h+ftLastWriteTime.dwLowDateTime], 0
0x180007aa2  xor     ebx, ebx
0x180007aa4  mov     rcx, [rsp+288h+hKey]; hKey
0x180007aa9  lea     rax, [rsp+288h+ftLastWriteTime]
0x180007aae  mov     [rsp+288h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007ab3  lea     r9, [rsp+288h+cchName]; lpcchName
0x180007ab8  mov     [rsp+288h+lpcchClass], 0; lpcchClass
0x180007ac1  lea     r8, [rsp+288h+Name]; lpName
0x180007ac6  mov     [rsp+288h+lpClass], 0; lpClass
0x180007acf  mov     edx, ebx; dwIndex
0x180007ad1  mov     [rsp+288h+lpReserved], 0; lpReserved
0x180007ada  mov     [rsp+288h+cchName], 104h
0x180007ae2  call    cs:__imp_RegEnumKeyExW
0x180007ae8  test    eax, eax
0x180007aea  jle     short loc_180007AF6
0x180007aec  movzx   eax, ax
0x180007aef  or      eax, 80070000h
0x180007af4  test    eax, eax
0x180007af6  jnz     short loc_180007B09
0x180007af8  mov     rdx, rdi; DeviceInfoSet
0x180007afb  lea     rcx, [rsp+288h+Name]; lpString2
0x180007b00  call    ?ExcludeLockedDownComponents@@YAXPEBGPEAX@Z; ExcludeLockedDownComponents(ushort const *,void *)
0x180007b05  inc     ebx
0x180007b07  jmp     short loc_180007AA4
0x180007b09  mov     rcx, [rsp+288h+hKey]; hKey
0x180007b0e  call    cs:__imp_RegCloseKey
0x180007b14  mov     rcx, [rsp+288h+var_18]
0x180007b1c  xor     rcx, rsp; StackCookie
0x180007b1f  call    __security_check_cookie
0x180007b24  mov     rbx, [rsp+288h+arg_0]
0x180007b2c  add     rsp, 280h
0x180007b33  pop     rdi
0x180007b34  retn
```
