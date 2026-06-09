# EnableWMFiltersAppCompatibilityOption(ulong)

- ea: `0x18000222c`
- end: `0x180002447`
- name: `?EnableWMFiltersAppCompatibilityOption@@YAHK@Z`
- size: `539`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800100f4`

## callees

- `0x180001460`
- `0x18000222c`
- `0x1800026d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002349`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002349`
- `KERNEL32!FindAtomW` at `0x1800022fc`
- `KERNEL32!FindAtomW` at `0x1800022fc`
- `KERNEL32!GetModuleFileNameW` at `0x180002321`
- `KERNEL32!GetModuleFileNameW` at `0x180002321`
- `ADVAPI32!RegCloseKey` at `0x180002407`
- `ADVAPI32!RegCloseKey` at `0x180002407`
- `ADVAPI32!RegQueryValueExW` at `0x1800023ea`
- `ADVAPI32!RegQueryValueExW` at `0x1800023ea`
- `ADVAPI32!RegOpenKeyExW` at `0x1800023ba`
- `ADVAPI32!RegOpenKeyExW` at `0x1800023ba`

## string_xrefs

- `0x180002253`: `SOFTWARE\Microsoft\DirectShow\WMFilters\AppCompatibility`

## pseudocode

```c
__int64 __fastcall EnableWMFiltersAppCompatibilityOption()
{
  unsigned int v0; // ebx
  wchar_t v1; // ax
  WCHAR *v2; // rsi
  WCHAR *v3; // rdi
  wchar_t *v4; // rax
  WCHAR *v5; // rcx
  WCHAR *v6; // rdi
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t ValueName[20]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v13[7]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v14; // [rsp+E0h] [rbp-20h]
  WCHAR Filename[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR SubKey[320]; // [rsp+300h] [rbp+200h] BYREF

  v13[0] = *(_OWORD *)L"SOFTWARE\\Microsoft\\DirectShow\\WMFilters\\AppCompatibility";
  v13[2] = *(_OWORD *)L"ft\\DirectShow\\WMFilters\\AppCompatibility";
  v13[1] = *(_OWORD *)L"\\Microsoft\\DirectShow\\WMFilters\\AppCompatibility";
  v13[4] = *(_OWORD *)L"Filters\\AppCompatibility";
  v13[3] = *(_OWORD *)L"tShow\\WMFilters\\AppCompatibility";
  v13[6] = *(_OWORD *)L"tibility";
  v14 = aSoftwareMicros[56];
  v13[5] = *(_OWORD *)L"AppCompatibility";
  hKey = 0;
  wcscpy(ValueName, L"OpnFlags1");
  cbData = 4;
  Type = 0;
  *(_DWORD *)Data = 0;
  if ( (dword_180026200 & 1) != 0 )
  {
    v0 = dword_1800261FC & 1;
  }
  else if ( FindAtomW(L"ExcludeScriptStreamDeliverySynchronization") )
  {
    v0 = 1;
  }
  else
  {
    v0 = 0;
    if ( GetModuleFileNameW(0, Filename, 0x105u) )
    {
      v1 = Filename[0];
      if ( !Filename[0] )
        goto LABEL_13;
      v2 = Filename;
      v3 = 0;
      do
      {
        v4 = wcschr(L"/\\", v1);
        v5 = v2;
        if ( !v4 )
          v5 = v3;
        ++v2;
        v3 = v5;
        v1 = *v2;
      }
      while ( *v2 );
      if ( v5 )
        v6 = v5 + 1;
      else
LABEL_13:
        v6 = Filename;
      StringCchPrintfW(SubKey, 0x13Eu, L"%s\\%s", v13, v6);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
      {
        if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) && Type == 4 )
          v0 = Data[0] & 1;
        RegCloseKey(hKey);
      }
    }
  }
  if ( (dword_180026200 & 1) == 0 )
  {
    dword_180026200 |= 1u;
    if ( v0 )
      dword_1800261FC |= 1u;
  }
  return v0;
}

```

## disassembly

```asm
0x18000222c  push    rbp
0x18000222e  push    rbx
0x18000222f  push    rsi
0x180002230  push    rdi
0x180002231  push    r14
0x180002233  lea     rbp, [rsp-490h]
0x18000223b  sub     rsp, 590h
0x180002242  mov     rax, cs:__security_cookie
0x180002249  xor     rax, rsp
0x18000224c  mov     [rbp+4B0h+var_30], rax
0x180002253  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "SOFTWARE\\Microsoft\\DirectShow\\WMFilt"...
0x18000225a  xor     r14d, r14d
0x18000225d  test    byte ptr cs:dword_180026200, 1
0x180002264  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\DirectShow\\WMFilters\\App"...
0x18000226b  movzx   eax, word ptr cs:aSoftwareMicros+70h; ""
0x180002272  movaps  [rsp+5B0h+var_540], xmm0
0x180002277  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\DirectShow\\WMFilters\\AppCompatibi"...
0x18000227e  movaps  [rbp+4B0h+var_520], xmm0
0x180002282  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+40h; "Filters\\AppCompatibility"
0x180002289  movaps  [rbp+4B0h+var_530], xmm1
0x18000228d  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "tShow\\WMFilters\\AppCompatibility"
0x180002294  movaps  [rbp+4B0h+var_500], xmm0
0x180002298  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+60h; "tibility"
0x18000229f  movaps  [rbp+4B0h+var_510], xmm1
0x1800022a3  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+50h; "AppCompatibility"
0x1800022aa  movaps  [rbp+4B0h+var_4E0], xmm0
0x1800022ae  movups  xmm0, xmmword ptr cs:aOptionflags1; "OptionFlags1"
0x1800022b5  mov     [rbp+4B0h+var_4D0], ax
0x1800022b9  movaps  [rbp+4B0h+var_4F0], xmm1
0x1800022bd  movups  xmm1, xmmword ptr cs:aOptionflags1+0Ah; "nFlags1"
0x1800022c4  mov     [rsp+5B0h+hKey], r14
0x1800022c9  movups  xmmword ptr [rsp+5B0h+ValueName], xmm0
0x1800022ce  mov     [rsp+5B0h+cbData], 4
0x1800022d6  movups  xmmword ptr [rsp+5B0h+ValueName+0Ah], xmm1
0x1800022db  mov     [rsp+5B0h+Type], r14d
0x1800022e0  mov     dword ptr [rsp+5B0h+Data], r14d
0x1800022e5  jz      short loc_1800022F5
0x1800022e7  mov     ebx, cs:dword_1800261FC
0x1800022ed  and     ebx, 1
0x1800022f0  jmp     loc_18000240D
0x1800022f5  lea     rcx, String; "ExcludeScriptStreamDeliverySynchronizat"...
0x1800022fc  call    cs:__imp_FindAtomW
0x180002302  cmp     r14w, ax
0x180002306  jz      short loc_180002312
0x180002308  mov     ebx, 1
0x18000230d  jmp     loc_18000240D
0x180002312  mov     r8d, 105h; nSize
0x180002318  lea     rdx, [rbp+4B0h+Filename]; lpFilename
0x18000231c  xor     ecx, ecx; hModule
0x18000231e  mov     ebx, r14d
0x180002321  call    cs:__imp_GetModuleFileNameW
0x180002327  test    eax, eax
0x180002329  jz      loc_18000240D
0x18000232f  movzx   eax, [rbp+4B0h+Filename]
0x180002333  test    ax, ax
0x180002336  jz      short loc_180002373
0x180002338  lea     rsi, [rbp+4B0h+Filename]
0x18000233c  mov     rdi, r14
0x18000233f  movzx   edx, ax; Ch
0x180002342  lea     rcx, Str; "/\\"
0x180002349  call    cs:__imp_wcschr
0x18000234f  test    rax, rax
0x180002352  mov     rcx, rsi
0x180002355  cmovz   rcx, rdi
0x180002359  add     rsi, 2
0x18000235d  mov     rdi, rcx
0x180002360  movzx   eax, word ptr [rsi]
0x180002363  test    ax, ax
0x180002366  jnz     short loc_18000233F
0x180002368  test    rcx, rcx
0x18000236b  jz      short loc_180002373
0x18000236d  add     rdi, 2
0x180002371  jmp     short loc_180002377
0x180002373  lea     rdi, [rbp+4B0h+Filename]
0x180002377  lea     r9, [rsp+5B0h+var_540]
0x18000237c  mov     [rsp+5B0h+phkResult], rdi
0x180002381  lea     r8, aSS; "%s\\%s"
0x180002388  mov     edx, 13Eh; unsigned __int64
0x18000238d  lea     rcx, [rbp+4B0h+SubKey]; unsigned __int16 *
0x180002394  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002399  lea     rax, [rsp+5B0h+hKey]
0x18000239e  mov     r9d, 20019h; samDesired
0x1800023a4  xor     r8d, r8d; ulOptions
0x1800023a7  mov     [rsp+5B0h+phkResult], rax; phkResult
0x1800023ac  lea     rdx, [rbp+4B0h+SubKey]; lpSubKey
0x1800023b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800023ba  call    cs:__imp_RegOpenKeyExW
0x1800023c0  test    eax, eax
0x1800023c2  jnz     short loc_18000240D
0x1800023c4  mov     rcx, [rsp+5B0h+hKey]; hKey
0x1800023c9  lea     rax, [rsp+5B0h+cbData]
0x1800023ce  mov     [rsp+5B0h+lpcbData], rax; lpcbData
0x1800023d3  lea     r9, [rsp+5B0h+Type]; lpType
0x1800023d8  lea     rax, [rsp+5B0h+Data]
0x1800023dd  xor     r8d, r8d; lpReserved
0x1800023e0  lea     rdx, [rsp+5B0h+ValueName]; lpValueName
0x1800023e5  mov     [rsp+5B0h+phkResult], rax; lpData
0x1800023ea  call    cs:__imp_RegQueryValueExW
0x1800023f0  test    eax, eax
0x1800023f2  jnz     short loc_180002402
0x1800023f4  cmp     [rsp+5B0h+Type], 4
0x1800023f9  jnz     short loc_180002402
0x1800023fb  mov     ebx, dword ptr [rsp+5B0h+Data]
0x1800023ff  and     ebx, 1
0x180002402  mov     rcx, [rsp+5B0h+hKey]; hKey
0x180002407  call    cs:__imp_RegCloseKey
0x18000240d  test    byte ptr cs:dword_180026200, 1
0x180002414  jnz     short loc_180002428
0x180002416  or      cs:dword_180026200, 1
0x18000241d  test    ebx, ebx
0x18000241f  jz      short loc_180002428
0x180002421  or      cs:dword_1800261FC, 1
0x180002428  mov     eax, ebx
0x18000242a  mov     rcx, [rbp+4B0h+var_30]
0x180002431  xor     rcx, rsp; StackCookie
0x180002434  call    __security_check_cookie
0x180002439  add     rsp, 590h
0x180002440  pop     r14
0x180002442  pop     rdi
0x180002443  pop     rsi
0x180002444  pop     rbx
0x180002445  pop     rbp
0x180002446  retn
```
