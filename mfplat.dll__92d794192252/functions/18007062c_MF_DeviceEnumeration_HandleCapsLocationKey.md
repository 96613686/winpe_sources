# MF::DeviceEnumeration::HandleCapsLocationKey

- ea: `0x18007062c`
- end: `0x18007082d`
- name: `MF::DeviceEnumeration::HandleCapsLocationKey`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800705a0`

## callees

- `0x18007062c`
- `0x18007aa0c`
- `0x180120030`
- `0x18012003c`
- `0x1801200d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180070748`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180070766`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180070784`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180070748`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180070766`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180070784`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800707a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800707f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800707a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800707f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800706ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007070f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800706ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007070f`

## pseudocode

```c
LSTATUS __fastcall MF::DeviceEnumeration::HandleCapsLocationKey(HKEY *a1, HKEY *a2)
{
  HKEY v4; // rcx
  WCHAR *lpData; // rbx
  DWORD v6; // esi
  unsigned __int64 v7; // rcx
  LSTATUS v8; // edi
  LSTATUS result; // eax
  DWORD cbData; // [rsp+30h] [rbp-50h] BYREF
  DWORD Type; // [rsp+34h] [rbp-4Ch] BYREF
  unsigned __int64 v12; // [rsp+38h] [rbp-48h] BYREF
  WCHAR ValueName[24]; // [rsp+40h] [rbp-40h] BYREF

  v4 = *a1;
  wcscpy(ValueName, L"Capabilitiocation");
  Type = 0;
  cbData = 0;
  v12 = 0;
  if ( !RegQueryValueExW(v4, ValueName, 0, &Type, 0, &cbData) && Type == 1 )
  {
    lpData = (WCHAR *)operator new[](saturated_mul(cbData, 2u));
    if ( !lpData )
      return -2147024882;
    v6 = cbData;
    if ( !RegQueryValueExW(*a1, ValueName, 0, &Type, (LPBYTE)lpData, &cbData)
      && (int)StringCchLengthW(lpData, v6, &v12) >= 0
      && v12 > 5 )
    {
      if ( wcsstr(lpData, L"HKLM\\") )
      {
        v7 = -2147483646;
LABEL_13:
        v8 = RegOpenKeyExW((HKEY)v7, lpData + 5, 0, 0x20019u, a2);
        operator delete(lpData);
        if ( v8 > 0 )
          return (unsigned __int16)v8 | 0x80070000;
        return v8;
      }
      if ( wcsstr(lpData, L"HKCR\\") )
      {
        v7 = 0xFFFFFFFF80000000uLL;
        goto LABEL_13;
      }
      if ( wcsstr(lpData, L"HKCU\\") )
      {
        v7 = -2147483647;
        goto LABEL_13;
      }
    }
    operator delete(lpData);
    return -2147024809;
  }
  result = RegOpenKeyExW(*a1, L"Capabilities", 0, 0x20019u, a2);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18007062c  mov     r11, rsp
0x18007062f  mov     [r11+18h], rbx
0x180070633  mov     [r11+20h], rsi
0x180070637  push    rbp
0x180070638  push    rdi
0x180070639  push    r14
0x18007063b  mov     rbp, rsp
0x18007063e  sub     rsp, 80h
0x180070645  mov     rax, cs:__security_cookie
0x18007064c  xor     rax, rsp
0x18007064f  mov     [rbp+var_10], rax
0x180070653  movups  xmm0, xmmword ptr cs:aCapabilitieslo; "CapabilitiesLocation"
0x18007065a  lea     rax, [rbp+cbData]
0x18007065e  mov     r14, rdx
0x180070661  movups  xmm1, xmmword ptr cs:aCapabilitieslo+10h; "tiesLocation"
0x180070668  mov     rdi, rcx
0x18007066b  mov     rcx, [rcx]; hKey
0x18007066e  movups  xmmword ptr [rbp+ValueName], xmm0
0x180070672  mov     [r11-70h], rax
0x180070676  lea     r9, [rbp+Type]; lpType
0x18007067a  movups  xmm0, xmmword ptr cs:aCapabilitieslo+1Ah; "ocation"
0x180070681  xor     r8d, r8d; lpReserved
0x180070684  lea     rdx, [rbp+ValueName]; lpValueName
0x180070688  movups  [rbp+var_30], xmm1
0x18007068c  mov     [rbp+Type], 0
0x180070693  movups  [rbp+var_30+0Ah], xmm0
0x180070697  mov     [rbp+cbData], 0
0x18007069e  mov     [rbp+var_48], 0
0x1800706a6  mov     qword ptr [r11-78h], 0
0x1800706ae  call    cs:__imp_RegQueryValueExW
0x1800706b4  test    eax, eax
0x1800706b6  jnz     loc_1800707DF
0x1800706bc  cmp     [rbp+Type], 1
0x1800706c0  jnz     loc_1800707DF
0x1800706c6  mov     ecx, [rbp+cbData]
0x1800706c9  mov     eax, 2
0x1800706ce  mul     rcx
0x1800706d1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800706d8  cmovb   rax, rcx
0x1800706dc  mov     rcx, rax; unsigned __int64
0x1800706df  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800706e4  mov     rbx, rax
0x1800706e7  test    rax, rax
0x1800706ea  jz      loc_1800707D8
0x1800706f0  mov     rcx, [rdi]; hKey
0x1800706f3  lea     rax, [rbp+cbData]
0x1800706f7  mov     esi, [rbp+cbData]
0x1800706fa  lea     r9, [rbp+Type]; lpType
0x1800706fe  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180070703  lea     rdx, [rbp+ValueName]; lpValueName
0x180070707  xor     r8d, r8d; lpReserved
0x18007070a  mov     [rsp+80h+lpData], rbx; lpData
0x18007070f  call    cs:__imp_RegQueryValueExW
0x180070715  test    eax, eax
0x180070717  jnz     loc_1800707C9
0x18007071d  lea     r8, [rbp+var_48]; unsigned __int64 *
0x180070721  mov     edx, esi; unsigned __int64
0x180070723  mov     rcx, rbx; unsigned __int16 *
0x180070726  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18007072b  test    eax, eax
0x18007072d  js      loc_1800707C9
0x180070733  cmp     [rbp+var_48], 5
0x180070738  jbe     loc_1800707C9
0x18007073e  lea     rdx, aHklm; "HKLM\\"
0x180070745  mov     rcx, rbx; Str
0x180070748  call    cs:__imp_wcsstr
0x18007074e  test    rax, rax
0x180070751  jz      short loc_18007075C
0x180070753  mov     rcx, 0FFFFFFFF80000002h
0x18007075a  jmp     short loc_180070796
0x18007075c  lea     rdx, aHkcr; "HKCR\\"
0x180070763  mov     rcx, rbx; Str
0x180070766  call    cs:__imp_wcsstr
0x18007076c  test    rax, rax
0x18007076f  jz      short loc_18007077A
0x180070771  mov     rcx, 0FFFFFFFF80000000h
0x180070778  jmp     short loc_180070796
0x18007077a  lea     rdx, aHkcu; "HKCU\\"
0x180070781  mov     rcx, rbx; Str
0x180070784  call    cs:__imp_wcsstr
0x18007078a  test    rax, rax
0x18007078d  jz      short loc_1800707C9
0x18007078f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180070796  lea     rdx, [rbx+0Ah]; lpSubKey
0x18007079a  mov     [rsp+80h+lpData], r14; phkResult
0x18007079f  mov     r9d, 20019h; samDesired
0x1800707a5  xor     r8d, r8d; ulOptions
0x1800707a8  call    cs:__imp_RegOpenKeyExW
0x1800707ae  mov     rcx, rbx; void *
0x1800707b1  mov     edi, eax
0x1800707b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800707b8  test    edi, edi
0x1800707ba  jle     short loc_1800707C5
0x1800707bc  movzx   edi, di
0x1800707bf  or      edi, 80070000h
0x1800707c5  mov     eax, edi
0x1800707c7  jmp     short loc_180070809
0x1800707c9  mov     rcx, rbx; void *
0x1800707cc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800707d1  mov     eax, 80070057h
0x1800707d6  jmp     short loc_180070809
0x1800707d8  mov     eax, 8007000Eh
0x1800707dd  jmp     short loc_180070809
0x1800707df  mov     rcx, [rdi]; hKey
0x1800707e2  lea     rdx, aCapabilities; "Capabilities"
0x1800707e9  mov     r9d, 20019h; samDesired
0x1800707ef  mov     [rsp+80h+lpData], r14; phkResult
0x1800707f4  xor     r8d, r8d; ulOptions
0x1800707f7  call    cs:__imp_RegOpenKeyExW
0x1800707fd  test    eax, eax
0x1800707ff  jle     short loc_180070809
0x180070801  movzx   eax, ax
0x180070804  or      eax, 80070000h
0x180070809  mov     rcx, [rbp+var_10]
0x18007080d  xor     rcx, rsp; StackCookie
0x180070810  call    __security_check_cookie
0x180070815  lea     r11, [rsp+80h+var_s0]
0x18007081d  mov     rbx, [r11+30h]
0x180070821  mov     rsi, [r11+38h]
0x180070825  mov     rsp, r11
0x180070828  pop     r14
0x18007082a  pop     rdi
0x18007082b  pop     rbp
0x18007082c  retn
```
