# SetProfileForProfileID(WCS_PROFILE_MANAGEMENT_SCOPE,ulong,ushort const *,int)

- ea: `0x18004387c`
- end: `0x180043a81`
- name: `?SetProfileForProfileID@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@KPEBGH@Z`
- size: `517`
- prototype: `unsigned int(enum WCS_PROFILE_MANAGEMENT_SCOPE, unsigned int, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180042bfc`
- `0x180043094`
- `0x180043324`

## callees

- `0x1800089d8`
- `0x180008a64`
- `0x1800097bc`
- `0x180020750`
- `0x18002e5f0`
- `0x18004387c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043a31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043a31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043a1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043a1f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180043994`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180043994`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043a4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043a4e`

## pseudocode

```c
__int64 __fastcall SetProfileForProfileID(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 v5; // r14
  DWORD v8; // ebx
  int v9; // eax
  signed int i; // edx
  __int64 v11; // rcx
  char *v12; // rax
  LSTATUS v13; // eax
  unsigned __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[4]; // [rsp+68h] [rbp-98h] BYREF
  __int16 v19; // [rsp+70h] [rbp-90h]
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  *(_QWORD *)ValueName = 0;
  v19 = 0;
  v5 = -(__int64)(a1 != WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE);
  dwDisposition = 0;
  hKey = 0;
  if ( a3 && *a3 && !(unsigned int)IsCustomWorkingSpaceProfile(a2) )
  {
    LODWORD(v15) = 0;
    v8 = IsInstalledProfile(0, a3, (int *)&v15);
    if ( v8 )
      goto LABEL_21;
    if ( !(_DWORD)v15 )
    {
      v8 = 2;
      goto LABEL_21;
    }
  }
  v9 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", gszICMRegPath, gszRegisteredProfiles);
  v8 = v9;
  if ( v9 < 0 )
    goto LABEL_8;
  v8 = RegCreateKeyExW((HKEY)(v5 - 2147483646), SubKey, 0, 0, 0, 0x102u, 0, &hKey, &dwDisposition);
  if ( v8 )
    goto LABEL_21;
  LODWORD(v15) = a2;
  for ( i = 0; (unsigned int)i < 4; ++i )
  {
    v11 = i;
    v12 = (char *)&v15 - i + 3;
    ValueName[v11] = *v12;
  }
  v19 = 0;
  if ( !a3 || !*a3 && !a4 )
  {
    v13 = RegDeleteValueW(hKey, ValueName);
    if ( v13 == 2 )
      v13 = 0;
    goto LABEL_20;
  }
  v15 = 0;
  v9 = StringCbLengthW(a3, 0x208u, &v15);
  v8 = v9;
  if ( v9 >= 0 )
  {
    v13 = RegSetValueExW(hKey, ValueName, 0, 1u, (const BYTE *)a3, v15 + 2);
LABEL_20:
    v8 = v13;
    goto LABEL_21;
  }
LABEL_8:
  if ( (v9 & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)v8;
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x18004387c  mov     [rsp-8+arg_0], rbx
0x180043881  mov     [rsp-8+arg_8], rsi
0x180043886  push    rbp
0x180043887  push    rdi
0x180043888  push    r12
0x18004388a  push    r14
0x18004388c  push    r15
0x18004388e  lea     rbp, [rsp-1A0h]
0x180043896  sub     rsp, 2A0h
0x18004389d  mov     rax, cs:__security_cookie
0x1800438a4  xor     rax, rsp
0x1800438a7  mov     [rbp+1C0h+var_30], rax
0x1800438ae  xor     eax, eax
0x1800438b0  xor     r12d, r12d
0x1800438b3  neg     ecx
0x1800438b5  mov     qword ptr [rsp+2C0h+ValueName], rax
0x1800438ba  mov     r15d, r9d
0x1800438bd  mov     [rsp+2C0h+var_250], ax
0x1800438c2  sbb     r14, r14
0x1800438c5  mov     [rsp+2C0h+dwDisposition], r12d
0x1800438ca  mov     [rsp+2C0h+hKey], r12
0x1800438cf  mov     rdi, r8
0x1800438d2  mov     esi, edx
0x1800438d4  test    r8, r8
0x1800438d7  jz      short loc_180043917
0x1800438d9  cmp     [r8], r12w
0x1800438dd  jz      short loc_180043917
0x1800438df  mov     ecx, edx; unsigned int
0x1800438e1  call    ?IsCustomWorkingSpaceProfile@@YAHK@Z; IsCustomWorkingSpaceProfile(ulong)
0x1800438e6  test    eax, eax
0x1800438e8  jnz     short loc_180043917
0x1800438ea  lea     r8, [rsp+2C0h+var_270]; int *
0x1800438ef  mov     dword ptr [rsp+2C0h+var_270], r12d
0x1800438f4  mov     rdx, rdi; unsigned __int16 *
0x1800438f7  xor     ecx, ecx; unsigned int *
0x1800438f9  call    ?IsInstalledProfile@@YAKPEBKPEBGPEAH@Z; IsInstalledProfile(ulong const *,ushort const *,int *)
0x1800438fe  mov     ebx, eax
0x180043900  test    eax, eax
0x180043902  jnz     loc_180043A44
0x180043908  cmp     dword ptr [rsp+2C0h+var_270], r12d
0x18004390d  jnz     short loc_180043917
0x18004390f  lea     ebx, [rax+2]
0x180043912  jmp     loc_180043A44
0x180043917  lea     rax, gszRegisteredProfiles; "RegisteredProfiles"
0x18004391e  mov     edx, 104h; unsigned __int64
0x180043923  lea     r9, gszICMRegPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004392a  mov     qword ptr [rsp+2C0h+dwOptions], rax
0x18004392f  lea     r8, aSS; "%s\\%s"
0x180043936  lea     rcx, [rbp+1C0h+SubKey]; unsigned __int16 *
0x18004393a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004393f  mov     ebx, eax
0x180043941  test    eax, eax
0x180043943  jns     short loc_18004395D
0x180043945  and     eax, 1FFF0000h
0x18004394a  cmp     eax, 70000h
0x18004394f  jnz     loc_180043A44
0x180043955  movzx   ebx, bx
0x180043958  jmp     loc_180043A44
0x18004395d  lea     rax, [rsp+2C0h+dwDisposition]
0x180043962  xor     r9d, r9d; lpClass
0x180043965  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x18004396a  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x18004396e  lea     rax, [rsp+2C0h+hKey]
0x180043973  xor     r8d, r8d; Reserved
0x180043976  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18004397b  lea     rcx, [r14-7FFFFFFEh]; hKey
0x180043982  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180043987  mov     [rsp+2C0h+samDesired], 102h; samDesired
0x18004398f  mov     [rsp+2C0h+dwOptions], r12d; dwOptions
0x180043994  call    cs:__imp_RegCreateKeyExW
0x18004399a  mov     ebx, eax
0x18004399c  test    eax, eax
0x18004399e  jnz     loc_180043A44
0x1800439a4  mov     dword ptr [rsp+2C0h+var_270], esi
0x1800439a8  mov     edx, r12d
0x1800439ab  movsxd  rcx, edx
0x1800439ae  lea     rax, [rsp+2C0h+var_270+3]
0x1800439b3  sub     rax, rcx
0x1800439b6  inc     edx
0x1800439b8  movsx   eax, byte ptr [rax]
0x1800439bb  mov     [rsp+rcx*2+2C0h+ValueName], ax
0x1800439c0  cmp     edx, 4
0x1800439c3  jb      short loc_1800439AB
0x1800439c5  mov     [rsp+2C0h+var_250], r12w
0x1800439cb  test    rdi, rdi
0x1800439ce  jz      short loc_180043A27
0x1800439d0  cmp     [rdi], r12w
0x1800439d4  jnz     short loc_1800439DB
0x1800439d6  test    r15d, r15d
0x1800439d9  jz      short loc_180043A27
0x1800439db  lea     r8, [rsp+2C0h+var_270]; unsigned __int64 *
0x1800439e0  mov     [rsp+2C0h+var_270], r12
0x1800439e5  mov     edx, 208h; unsigned __int64
0x1800439ea  mov     rcx, rdi; unsigned __int16 *
0x1800439ed  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800439f2  mov     ebx, eax
0x1800439f4  test    eax, eax
0x1800439f6  js      loc_180043945
0x1800439fc  mov     eax, dword ptr [rsp+2C0h+var_270]
0x180043a00  lea     rdx, [rsp+2C0h+ValueName]; lpValueName
0x180043a05  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180043a0a  add     eax, 2
0x180043a0d  mov     [rsp+2C0h+samDesired], eax; cbData
0x180043a11  mov     r9d, 1; dwType
0x180043a17  xor     r8d, r8d; Reserved
0x180043a1a  mov     qword ptr [rsp+2C0h+dwOptions], rdi; lpData
0x180043a1f  call    cs:__imp_RegSetValueExW
0x180043a25  jmp     short loc_180043A42
0x180043a27  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180043a2c  lea     rdx, [rsp+2C0h+ValueName]; lpValueName
0x180043a31  call    cs:__imp_RegDeleteValueW
0x180043a37  mov     ebx, 2
0x180043a3c  cmp     eax, ebx
0x180043a3e  cmovz   eax, r12d
0x180043a42  mov     ebx, eax
0x180043a44  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180043a49  test    rcx, rcx
0x180043a4c  jz      short loc_180043A54
0x180043a4e  call    cs:__imp_RegCloseKey
0x180043a54  mov     eax, ebx
0x180043a56  mov     rcx, [rbp+1C0h+var_30]
0x180043a5d  xor     rcx, rsp; StackCookie
0x180043a60  call    __security_check_cookie
0x180043a65  lea     r11, [rsp+2C0h+var_20]
0x180043a6d  mov     rbx, [r11+30h]
0x180043a71  mov     rsi, [r11+38h]
0x180043a75  mov     rsp, r11
0x180043a78  pop     r15
0x180043a7a  pop     r14
0x180043a7c  pop     r12
0x180043a7e  pop     rdi
0x180043a7f  pop     rbp
0x180043a80  retn
```
