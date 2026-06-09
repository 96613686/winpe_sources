# GetRegSettingsString(HKEY__ *,ushort const *,ushort *,ulong)

- ea: `0x1400098d4`
- end: `0x140009a2b`
- name: `?GetRegSettingsString@@YAJPEAUHKEY__@@PEBGPEAGK@Z`
- size: `343`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140001950`

## callees

- `0x1400098d4`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x140009a0d`
- `KERNEL32!MultiByteToWideChar` at `0x140009a0d`
- `KERNEL32!GetLastError` at `0x140009a17`
- `KERNEL32!GetLastError` at `0x140009a17`
- `ADVAPI32!RegQueryValueExW` at `0x140009939`
- `ADVAPI32!RegQueryValueExW` at `0x140009939`
- `ADVAPI32!RegQueryValueExA` at `0x1400099d2`
- `ADVAPI32!RegQueryValueExA` at `0x1400099d2`

## pseudocode

```c
signed int __fastcall GetRegSettingsString(HKEY hKey, const unsigned __int16 *a2, BYTE *lpData, unsigned int a4)
{
  signed int result; // eax
  bool v8; // cc
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  DWORD cbData; // [rsp+30h] [rbp+0h] BYREF
  DWORD Type; // [rsp+34h] [rbp+4h] BYREF

  Type = 0;
  if ( Global::g_fWindowsNT )
  {
    if ( 2 * (unsigned __int64)a4 > 0xFFFFFFFF )
      return -2147221165;
    cbData = 2 * a4;
    result = RegQueryValueExW(hKey, 0, 0, &Type, lpData, &cbData);
    v8 = result <= 0;
    if ( result )
      goto LABEL_4;
    if ( Type - 1 > 1 || *(_WORD *)&lpData[2 * ((unsigned __int64)cbData >> 1) - 2] )
      return -2147221165;
    return 0;
  }
  v9 = a4 + 1;
  v10 = v9 + 15;
  if ( v9 + 15 <= v9 )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
  v12 = alloca(v11);
  v13 = alloca(v11);
  cbData = v9;
  result = RegQueryValueExA(hKey, 0, 0, &Type, (LPBYTE)&cbData, &cbData);
  v8 = result <= 0;
  if ( result )
    goto LABEL_4;
  if ( Type - 1 > 1 || *((_BYTE *)&cbData + cbData - 1) )
    return -2147221165;
  if ( MultiByteToWideChar(0, 0, (LPCCH)&cbData, -1, (LPWSTR)lpData, a4) )
    return 0;
  result = GetLastError();
  v8 = result <= 0;
LABEL_4:
  if ( !v8 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400098d4  push    rbp
0x1400098d6  push    rbx
0x1400098d7  push    rsi
0x1400098d8  push    rdi
0x1400098d9  push    r14
0x1400098db  push    r15
0x1400098dd  sub     rsp, 48h
0x1400098e1  lea     rbp, [rsp+30h]
0x1400098e6  mov     rax, cs:__security_cookie
0x1400098ed  xor     rax, rbp
0x1400098f0  mov     [rbp+40h+var_38], rax
0x1400098f4  xor     r15d, r15d
0x1400098f7  mov     ebx, r9d
0x1400098fa  cmp     cs:?g_fWindowsNT@Global@@2_NA, r15b; bool Global::g_fWindowsNT
0x140009901  mov     rdi, r8
0x140009904  mov     r14, rcx
0x140009907  mov     [rbp+40h+Type], r15d
0x14000990b  jz      short loc_140009989
0x14000990d  mov     eax, ebx
0x14000990f  mov     ecx, 0FFFFFFFFh
0x140009914  add     rax, rax
0x140009917  cmp     rax, rcx
0x14000991a  ja      short loc_14000996B
0x14000991c  mov     [rbp+40h+cbData], eax
0x14000991f  lea     r9, [rbp+40h+Type]; lpType
0x140009923  lea     rax, [rbp+40h+cbData]
0x140009927  xor     edx, edx; lpValueName
0x140009929  mov     [rsp+70h+lpcbData], rax; lpcbData
0x14000992e  mov     rcx, r14; hKey
0x140009931  mov     [rsp+70h+lpData], r8; lpData
0x140009936  xor     r8d, r8d; lpReserved
0x140009939  call    cs:__imp_RegQueryValueExW
0x14000993f  test    eax, eax
0x140009941  jz      short loc_14000994F
0x140009943  jle     short loc_140009970
0x140009945  movzx   eax, ax
0x140009948  or      eax, 80070000h
0x14000994d  jmp     short loc_140009970
0x14000994f  mov     eax, [rbp+40h+Type]
0x140009952  dec     eax
0x140009954  cmp     eax, 1
0x140009957  ja      short loc_14000996B
0x140009959  mov     eax, [rbp+40h+cbData]
0x14000995c  shr     rax, 1
0x14000995f  cmp     [rdi+rax*2-2], r15w
0x140009965  jz      loc_140009A24
0x14000996b  mov     eax, 80040153h
0x140009970  mov     rcx, [rbp+40h+var_38]
0x140009974  xor     rcx, rbp; StackCookie
0x140009977  call    __security_check_cookie
0x14000997c  lea     rsp, [rbp+18h]
0x140009980  pop     r15
0x140009982  pop     r14
0x140009984  pop     rdi
0x140009985  pop     rsi
0x140009986  pop     rbx
0x140009987  pop     rbp
0x140009988  retn
0x140009989  lea     edx, [rbx+1]
0x14000998c  mov     eax, edx
0x14000998e  lea     rcx, [rdx+0Fh]
0x140009992  cmp     rcx, rax
0x140009995  ja      short loc_1400099A1
0x140009997  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1400099a1  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400099a5  mov     rax, rcx
0x1400099a8  call    _alloca_probe
0x1400099ad  sub     rsp, rcx
0x1400099b0  mov     [rbp+40h+cbData], edx
0x1400099b3  lea     rax, [rbp+40h+cbData]
0x1400099b7  xor     r8d, r8d; lpReserved
0x1400099ba  lea     r9, [rbp+40h+Type]; lpType
0x1400099be  xor     edx, edx; lpValueName
0x1400099c0  mov     rcx, r14; hKey
0x1400099c3  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1400099c8  lea     rsi, [rsp+70h+cbData]
0x1400099cd  mov     [rsp+70h+lpData], rsi; lpData
0x1400099d2  call    cs:__imp_RegQueryValueExA
0x1400099d8  test    eax, eax
0x1400099da  jnz     loc_140009943
0x1400099e0  mov     eax, [rbp+40h+Type]
0x1400099e3  dec     eax
0x1400099e5  cmp     eax, 1
0x1400099e8  ja      short loc_14000996B
0x1400099ea  mov     eax, [rbp+40h+cbData]
0x1400099ed  dec     eax
0x1400099ef  cmp     [rax+rsi], r15b
0x1400099f3  jnz     loc_14000996B
0x1400099f9  mov     dword ptr [rsp+70h+lpcbData], ebx; cchWideChar
0x1400099fd  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140009a01  mov     r8, rsi; lpMultiByteStr
0x140009a04  mov     [rsp+70h+lpData], rdi; lpWideCharStr
0x140009a09  xor     edx, edx; dwFlags
0x140009a0b  xor     ecx, ecx; CodePage
0x140009a0d  call    cs:__imp_MultiByteToWideChar
0x140009a13  test    eax, eax
0x140009a15  jnz     short loc_140009A24
0x140009a17  call    cs:__imp_GetLastError
0x140009a1d  test    eax, eax
0x140009a1f  jmp     loc_140009943
0x140009a24  xor     eax, eax
0x140009a26  jmp     loc_140009970
```
