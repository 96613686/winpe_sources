# GetRegSettingsInt(HKEY__ *,ushort const *,ulong *)

- ea: `0x140008ec4`
- end: `0x140009038`
- name: `?GetRegSettingsInt@@YAJPEAUHKEY__@@PEBGPEAK@Z`
- size: `372`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, LPBYTE lpData)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400051cc`
- `0x14000f7d8`

## callees

- `0x140008ec4`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x140008f59`
- `KERNEL32!WideCharToMultiByte` at `0x140008fce`
- `KERNEL32!WideCharToMultiByte` at `0x140008f59`
- `KERNEL32!WideCharToMultiByte` at `0x140008fce`
- `KERNEL32!GetLastError` at `0x140008f66`
- `KERNEL32!GetLastError` at `0x140008f66`
- `ADVAPI32!RegQueryValueExW` at `0x140008f17`
- `ADVAPI32!RegQueryValueExW` at `0x140008f17`
- `ADVAPI32!RegQueryValueExA` at `0x140008ff7`
- `ADVAPI32!RegQueryValueExA` at `0x140008ff7`

## pseudocode

```c
signed int __fastcall GetRegSettingsInt(HKEY hKey, LPCWCH lpWideCharStr, LPBYTE lpData)
{
  signed int result; // eax
  int v7; // eax
  bool v8; // cc
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  DWORD *p_Type; // rdi
  DWORD Type; // [rsp+40h] [rbp+0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp+4h] BYREF

  Type = 0;
  cbData = 4;
  if ( Global::g_fWindowsNT )
  {
    result = RegQueryValueExW(hKey, lpWideCharStr, 0, &Type, lpData, &cbData);
  }
  else
  {
    if ( lpWideCharStr )
    {
      v7 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
      if ( !v7 )
        goto LABEL_5;
      v9 = v7 + 15LL;
      if ( v9 < v7 )
        v9 = 0xFFFFFFFFFFFFFF0LL;
      v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
      v11 = alloca(v10);
      v12 = alloca(v10);
      p_Type = &Type;
      if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, (LPSTR)&Type, v7, 0, 0) )
      {
LABEL_5:
        result = GetLastError();
        v8 = result <= 0;
        goto LABEL_6;
      }
    }
    else
    {
      p_Type = 0;
    }
    result = RegQueryValueExA(hKey, (LPCSTR)p_Type, 0, &Type, lpData, &cbData);
  }
  v8 = result <= 0;
  if ( !result )
  {
    if ( Type == 4 )
      return cbData != 4 ? 0x80040153 : 0;
    else
      return -2147221165;
  }
LABEL_6:
  if ( !v8 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140008ec4  push    rbp
0x140008ec6  push    rbx
0x140008ec7  push    rsi
0x140008ec8  push    rdi
0x140008ec9  push    r14
0x140008ecb  sub     rsp, 50h
0x140008ecf  lea     rbp, [rsp+40h]
0x140008ed4  mov     rax, cs:__security_cookie
0x140008edb  xor     rax, rbp
0x140008ede  mov     [rbp+30h+var_28], rax
0x140008ee2  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140008ee9  mov     rsi, r8
0x140008eec  mov     rbx, rdx
0x140008eef  mov     [rbp+30h+Type], 0
0x140008ef6  mov     r14, rcx
0x140008ef9  mov     [rbp+30h+cbData], 4
0x140008f00  jz      short loc_140008F22
0x140008f02  lea     rax, [rbp+30h+cbData]
0x140008f06  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140008f0b  lea     r9, [rbp+30h+Type]; lpType
0x140008f0f  mov     [rsp+70h+lpData], r8; lpData
0x140008f14  xor     r8d, r8d; lpReserved
0x140008f17  call    cs:__imp_RegQueryValueExW
0x140008f1d  jmp     loc_140008FFD
0x140008f22  test    rbx, rbx
0x140008f25  jz      loc_140008FDA
0x140008f2b  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140008f34  or      r9d, 0FFFFFFFFh; cchWideChar
0x140008f38  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x140008f41  mov     r8, rbx; lpWideCharStr
0x140008f44  mov     dword ptr [rsp+70h+lpcbData], 0; cbMultiByte
0x140008f4c  xor     edx, edx; dwFlags
0x140008f4e  xor     ecx, ecx; CodePage
0x140008f50  mov     [rsp+70h+lpData], 0; lpMultiByteStr
0x140008f59  call    cs:__imp_WideCharToMultiByte
0x140008f5f  movsxd  rdx, eax
0x140008f62  test    eax, eax
0x140008f64  jnz     short loc_140008F81
0x140008f66  call    cs:__imp_GetLastError
0x140008f6c  test    eax, eax
0x140008f6e  jle     loc_140009021
0x140008f74  movzx   eax, ax
0x140008f77  or      eax, 80070000h
0x140008f7c  jmp     loc_140009021
0x140008f81  lea     rcx, [rdx+0Fh]
0x140008f85  cmp     rcx, rdx
0x140008f88  ja      short loc_140008F94
0x140008f8a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140008f94  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140008f98  mov     rax, rcx
0x140008f9b  call    _alloca_probe
0x140008fa0  sub     rsp, rcx
0x140008fa3  or      r9d, 0FFFFFFFFh; cchWideChar
0x140008fa7  mov     r8, rbx; lpWideCharStr
0x140008faa  xor     ecx, ecx; CodePage
0x140008fac  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140008fb5  lea     rdi, [rsp+70h+Type]
0x140008fba  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x140008fc3  mov     dword ptr [rsp+70h+lpcbData], edx; cbMultiByte
0x140008fc7  xor     edx, edx; dwFlags
0x140008fc9  mov     [rsp+70h+lpData], rdi; lpMultiByteStr
0x140008fce  call    cs:__imp_WideCharToMultiByte
0x140008fd4  test    eax, eax
0x140008fd6  jnz     short loc_140008FDC
0x140008fd8  jmp     short loc_140008F66
0x140008fda  xor     edi, edi
0x140008fdc  lea     rax, [rbp+30h+cbData]
0x140008fe0  xor     r8d, r8d; lpReserved
0x140008fe3  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140008fe8  lea     r9, [rbp+30h+Type]; lpType
0x140008fec  mov     rdx, rdi; lpValueName
0x140008fef  mov     [rsp+70h+lpData], rsi; lpData
0x140008ff4  mov     rcx, r14; hKey
0x140008ff7  call    cs:__imp_RegQueryValueExA
0x140008ffd  test    eax, eax
0x140008fff  jnz     loc_140008F6E
0x140009005  cmp     [rbp+30h+Type], 4
0x140009009  jnz     short loc_14000901C
0x14000900b  mov     eax, [rbp+30h+cbData]
0x14000900e  sub     eax, 4
0x140009011  neg     eax
0x140009013  sbb     eax, eax
0x140009015  and     eax, 80040153h
0x14000901a  jmp     short loc_140009021
0x14000901c  mov     eax, 80040153h
0x140009021  mov     rcx, [rbp+30h+var_28]
0x140009025  xor     rcx, rbp; StackCookie
0x140009028  call    __security_check_cookie
0x14000902d  lea     rsp, [rbp+10h]
0x140009031  pop     r14
0x140009033  pop     rdi
0x140009034  pop     rsi
0x140009035  pop     rbx
0x140009036  pop     rbp
0x140009037  retn
```
