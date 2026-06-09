# PutRegSettingsInt(HKEY__ *,ushort const *,ulong)

- ea: `0x140014e0c`
- end: `0x140014f48`
- name: `?PutRegSettingsInt@@YAJPEAUHKEY__@@PEBGK@Z`
- size: `316`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000d5d4`
- `0x14000f7d8`

## callees

- `0x140014e0c`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x140014e94`
- `KERNEL32!WideCharToMultiByte` at `0x140014ef6`
- `KERNEL32!WideCharToMultiByte` at `0x140014e94`
- `KERNEL32!WideCharToMultiByte` at `0x140014ef6`
- `KERNEL32!GetLastError` at `0x140014ea1`
- `KERNEL32!GetLastError` at `0x140014ea1`
- `ADVAPI32!RegSetValueExA` at `0x140014f21`
- `ADVAPI32!RegSetValueExA` at `0x140014f21`
- `ADVAPI32!RegSetValueExW` at `0x140014e52`
- `ADVAPI32!RegSetValueExW` at `0x140014e52`

## pseudocode

```c
signed int __fastcall PutRegSettingsInt(HKEY hKey, LPCWCH lpWideCharStr, int a3)
{
  signed int result; // eax
  int v6; // eax
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  CHAR *v11; // rdi
  CHAR MultiByteStr[48]; // [rsp+40h] [rbp+0h] BYREF
  int Data; // [rsp+90h] [rbp+50h] BYREF

  Data = a3;
  if ( Global::g_fWindowsNT )
  {
    result = RegSetValueExW(hKey, lpWideCharStr, 0, 4u, (const BYTE *)&Data, 4u);
    goto LABEL_12;
  }
  if ( lpWideCharStr )
  {
    v6 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( !v6 )
      goto LABEL_5;
    v7 = v6 + 15LL;
    if ( v7 < v6 )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
    v9 = alloca(v8);
    v10 = alloca(v8);
    v11 = MultiByteStr;
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, v6, 0, 0) )
    {
LABEL_5:
      result = GetLastError();
      goto LABEL_12;
    }
  }
  else
  {
    v11 = 0;
  }
  result = RegSetValueExA(hKey, v11, 0, 4u, (const BYTE *)&Data, 4u);
LABEL_12:
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140014e0c  mov     [rsp-8+Data], r8d
0x140014e11  push    rbp
0x140014e12  push    rbx
0x140014e13  push    rsi
0x140014e14  push    rdi
0x140014e15  sub     rsp, 58h
0x140014e19  lea     rbp, [rsp+40h]
0x140014e1e  mov     rax, cs:__security_cookie
0x140014e25  xor     rax, rbp
0x140014e28  mov     qword ptr [rbp+30h+MultiByteStr], rax
0x140014e2c  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140014e33  mov     rbx, rdx
0x140014e36  mov     rsi, rcx
0x140014e39  jz      short loc_140014E5D
0x140014e3b  mov     r9d, 4; dwType
0x140014e41  lea     rax, [rbp+30h+Data]
0x140014e45  mov     [rsp+70h+cbData], r9d; cbData
0x140014e4a  xor     r8d, r8d; Reserved
0x140014e4d  mov     [rsp+70h+lpData], rax; lpData
0x140014e52  call    cs:__imp_RegSetValueExW
0x140014e58  jmp     loc_140014F27
0x140014e5d  test    rbx, rbx
0x140014e60  jz      loc_140014F02
0x140014e66  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140014e6f  or      r9d, 0FFFFFFFFh; cchWideChar
0x140014e73  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x140014e7c  mov     r8, rbx; lpWideCharStr
0x140014e7f  mov     [rsp+70h+cbData], 0; cbMultiByte
0x140014e87  xor     edx, edx; dwFlags
0x140014e89  xor     ecx, ecx; CodePage
0x140014e8b  mov     [rsp+70h+lpData], 0; lpMultiByteStr
0x140014e94  call    cs:__imp_WideCharToMultiByte
0x140014e9a  movsxd  rdx, eax
0x140014e9d  test    eax, eax
0x140014e9f  jnz     short loc_140014EA9
0x140014ea1  call    cs:__imp_GetLastError
0x140014ea7  jmp     short loc_140014F27
0x140014ea9  lea     rcx, [rdx+0Fh]
0x140014ead  cmp     rcx, rdx
0x140014eb0  ja      short loc_140014EBC
0x140014eb2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140014ebc  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140014ec0  mov     rax, rcx
0x140014ec3  call    _alloca_probe
0x140014ec8  sub     rsp, rcx
0x140014ecb  or      r9d, 0FFFFFFFFh; cchWideChar
0x140014ecf  mov     r8, rbx; lpWideCharStr
0x140014ed2  xor     ecx, ecx; CodePage
0x140014ed4  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140014edd  lea     rdi, [rsp+70h+MultiByteStr]
0x140014ee2  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x140014eeb  mov     [rsp+70h+cbData], edx; cbMultiByte
0x140014eef  xor     edx, edx; dwFlags
0x140014ef1  mov     [rsp+70h+lpData], rdi; lpMultiByteStr
0x140014ef6  call    cs:__imp_WideCharToMultiByte
0x140014efc  test    eax, eax
0x140014efe  jnz     short loc_140014F04
0x140014f00  jmp     short loc_140014EA1
0x140014f02  xor     edi, edi
0x140014f04  mov     r9d, 4; dwType
0x140014f0a  lea     rax, [rbp+30h+Data]
0x140014f0e  mov     [rsp+70h+cbData], r9d; cbData
0x140014f13  xor     r8d, r8d; Reserved
0x140014f16  mov     rdx, rdi; lpValueName
0x140014f19  mov     [rsp+70h+lpData], rax; lpData
0x140014f1e  mov     rcx, rsi; hKey
0x140014f21  call    cs:__imp_RegSetValueExA
0x140014f27  test    eax, eax
0x140014f29  jle     short loc_140014F33
0x140014f2b  movzx   eax, ax
0x140014f2e  or      eax, 80070000h
0x140014f33  mov     rcx, qword ptr [rbp+30h+MultiByteStr]
0x140014f37  xor     rcx, rbp; StackCookie
0x140014f3a  call    __security_check_cookie
0x140014f3f  lea     rsp, [rbp+18h]
0x140014f43  pop     rdi
0x140014f44  pop     rsi
0x140014f45  pop     rbx
0x140014f46  pop     rbp
0x140014f47  retn
```
