# SetDefaultRenderingIntent(WCS_PROFILE_MANAGEMENT_SCOPE,ulong)

- ea: `0x1800431a4`
- end: `0x18004331b`
- name: `?SetDefaultRenderingIntent@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@K@Z`
- size: `375`
- prototype: `unsigned int __fastcall(enum WCS_PROFILE_MANAGEMENT_SCOPE, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800455a0`

## callees

- `0x1800089d8`
- `0x18002e5f0`
- `0x1800431a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800432d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800432d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800432cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800432cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004326d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004326d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800432ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800432ef`

## pseudocode

```c
__int64 __fastcall SetDefaultRenderingIntent(enum WCS_PROFILE_MANAGEMENT_SCOPE a1, int a2)
{
  __int64 v2; // rdi
  int v3; // eax
  unsigned int v4; // ebx
  signed int i; // edx
  __int64 v6; // rcx
  char *v7; // rax
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  int v12; // [rsp+68h] [rbp-98h] BYREF
  WCHAR ValueName[8]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  *(_DWORD *)Data = a2;
  dwDisposition = 0;
  hKey = 0;
  v2 = -(__int64)(a1 != WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE);
  v3 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", gszICMRegPath, gszRegisteredProfiles);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v4 = RegCreateKeyExW((HKEY)(v2 - 2147483646), SubKey, 0, 0, 0, 0x102u, 0, &hKey, &dwDisposition);
    if ( !v4 )
    {
      v12 = 1919483904;
      for ( i = 0; (unsigned int)i < 4; ++i )
      {
        v6 = i;
        v7 = (char *)&v12 - i + 3;
        ValueName[v6] = *v7;
      }
      ValueName[4] = 0;
      if ( *(_DWORD *)Data == -1 )
      {
        v4 = RegDeleteValueW(hKey, ValueName);
        if ( v4 == 2 )
          v4 = 0;
      }
      else
      {
        v4 = RegSetValueExW(hKey, ValueName, 0, 4u, Data, 4u);
      }
    }
  }
  else if ( (v3 & 0x1FFF0000) == 0x70000 )
  {
    v4 = (unsigned __int16)v3;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1800431a4  mov     [rsp-8+arg_0], rbx
0x1800431a9  mov     [rsp-8+arg_10], rdi
0x1800431ae  push    rbp
0x1800431af  lea     rbp, [rsp-1A0h]
0x1800431b7  sub     rsp, 2A0h
0x1800431be  mov     rax, cs:__security_cookie
0x1800431c5  xor     rax, rsp
0x1800431c8  mov     [rbp+1A0h+var_10], rax
0x1800431cf  neg     ecx
0x1800431d1  mov     dword ptr [rsp+2A0h+Data], edx
0x1800431d5  lea     rax, gszRegisteredProfiles; "RegisteredProfiles"
0x1800431dc  mov     [rsp+2A0h+dwDisposition], 0
0x1800431e4  lea     rcx, [rbp+1A0h+SubKey]; unsigned __int16 *
0x1800431e8  mov     [rsp+2A0h+hKey], 0
0x1800431f1  lea     r9, gszICMRegPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800431f8  mov     qword ptr [rsp+2A0h+dwOptions], rax
0x1800431fd  lea     r8, aSS; "%s\\%s"
0x180043204  mov     edx, 104h; unsigned __int64
0x180043209  sbb     rdi, rdi
0x18004320c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043211  mov     ebx, eax
0x180043213  test    eax, eax
0x180043215  jns     short loc_18004322F
0x180043217  and     eax, 1FFF0000h
0x18004321c  cmp     eax, 70000h
0x180043221  jnz     loc_1800432E5
0x180043227  movzx   ebx, bx
0x18004322a  jmp     loc_1800432E5
0x18004322f  lea     rax, [rsp+2A0h+dwDisposition]
0x180043234  xor     r9d, r9d; lpClass
0x180043237  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x18004323c  lea     rdx, [rbp+1A0h+SubKey]; lpSubKey
0x180043240  lea     rax, [rsp+2A0h+hKey]
0x180043245  xor     r8d, r8d; Reserved
0x180043248  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18004324d  lea     rcx, [rdi-7FFFFFFEh]; hKey
0x180043254  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004325d  mov     [rsp+2A0h+samDesired], 102h; samDesired
0x180043265  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x18004326d  call    cs:__imp_RegCreateKeyExW
0x180043273  mov     ebx, eax
0x180043275  test    eax, eax
0x180043277  jnz     short loc_1800432E5
0x180043279  mov     [rsp+2A0h+var_238], 72690000h
0x180043281  lea     r9d, [rax+4]; dwType
0x180043285  xor     edx, edx
0x180043287  movsxd  rcx, edx
0x18004328a  lea     rax, [rsp+2A0h+var_238+3]
0x18004328f  sub     rax, rcx
0x180043292  inc     edx
0x180043294  movsx   eax, byte ptr [rax]
0x180043297  mov     [rsp+rcx*2+2A0h+ValueName], ax
0x18004329c  cmp     edx, r9d
0x18004329f  jb      short loc_180043287
0x1800432a1  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800432a6  lea     rdx, [rsp+2A0h+ValueName]; lpValueName
0x1800432ab  xor     eax, eax
0x1800432ad  cmp     dword ptr [rsp+2A0h+Data], 0FFFFFFFFh
0x1800432b2  mov     [rsp+2A0h+var_228], ax
0x1800432b7  jz      short loc_1800432D5
0x1800432b9  lea     rax, [rsp+2A0h+Data]
0x1800432be  mov     [rsp+2A0h+samDesired], r9d; cbData
0x1800432c3  xor     r8d, r8d; Reserved
0x1800432c6  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x1800432cb  call    cs:__imp_RegSetValueExW
0x1800432d1  mov     ebx, eax
0x1800432d3  jmp     short loc_1800432E5
0x1800432d5  call    cs:__imp_RegDeleteValueW
0x1800432db  mov     ebx, eax
0x1800432dd  xor     eax, eax
0x1800432df  cmp     ebx, 2
0x1800432e2  cmovz   ebx, eax
0x1800432e5  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800432ea  test    rcx, rcx
0x1800432ed  jz      short loc_1800432F5
0x1800432ef  call    cs:__imp_RegCloseKey
0x1800432f5  mov     eax, ebx
0x1800432f7  mov     rcx, [rbp+1A0h+var_10]
0x1800432fe  xor     rcx, rsp; StackCookie
0x180043301  call    __security_check_cookie
0x180043306  lea     r11, [rsp+2A0h+var_s0]
0x18004330e  mov     rbx, [r11+10h]
0x180043312  mov     rdi, [r11+20h]
0x180043316  mov     rsp, r11
0x180043319  pop     rbp
0x18004331a  retn
```
