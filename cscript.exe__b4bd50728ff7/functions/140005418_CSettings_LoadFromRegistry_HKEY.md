# CSettings::LoadFromRegistry(HKEY__ *)

- ea: `0x140005418`
- end: `0x140005609`
- name: `?LoadFromRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z`
- size: `497`
- prototype: `int(CSettings *__hidden this, HKEY)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003e2c`
- `0x14000a2f0`

## callees

- `0x140004b50`
- `0x140005418`
- `0x140005610`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1400054d1`
- `KERNEL32!WideCharToMultiByte` at `0x14000553f`
- `KERNEL32!WideCharToMultiByte` at `0x1400054d1`
- `KERNEL32!WideCharToMultiByte` at `0x14000553f`
- `KERNEL32!GetLastError` at `0x1400054de`
- `KERNEL32!GetLastError` at `0x1400054de`
- `ADVAPI32!RegQueryValueExW` at `0x1400054a3`
- `ADVAPI32!RegQueryValueExW` at `0x1400054a3`
- `ADVAPI32!RegQueryValueExA` at `0x140005568`
- `ADVAPI32!RegQueryValueExA` at `0x140005568`
- `ADVAPI32!RegCloseKey` at `0x1400055ea`
- `ADVAPI32!RegCloseKey` at `0x1400055ea`

## pseudocode

```c
int __fastcall CSettings::LoadFromRegistry(CSettings *this, HKEY a2)
{
  int result; // eax
  HKEY v4; // rbx
  LSTATUS v5; // eax
  int v6; // eax
  signed int LastError; // eax
  signed int v8; // ebx
  int v9; // ebx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  bool v14; // sf
  int v15; // ecx
  bool v16; // zf
  signed int RegSettingsBool; // eax
  DWORD Type; // [rsp+40h] [rbp+0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp+4h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+10h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  result = CreateRegSettings(a2, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &hKey);
  if ( result >= 0 )
  {
    v4 = hKey;
    Type = 0;
    cbData = 4;
    if ( Global::g_fWindowsNT )
    {
      v5 = RegQueryValueExW(hKey, L"Timeout", 0, &Type, Data, &cbData);
    }
    else
    {
      v6 = WideCharToMultiByte(0, 0, L"Timeout", -1, 0, 0, 0, 0);
      if ( !v6 )
        goto LABEL_5;
      v10 = v6 + 15LL;
      if ( v10 < v6 )
        v10 = 0xFFFFFFFFFFFFFF0LL;
      v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
      v12 = alloca(v11);
      v13 = alloca(v11);
      if ( !WideCharToMultiByte(0, 0, L"Timeout", -1, (LPSTR)&Type, v6, 0, 0) )
      {
LABEL_5:
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError <= 0 )
        {
LABEL_15:
          v14 = v8 < 0;
          goto LABEL_16;
        }
        v9 = (unsigned __int16)LastError;
LABEL_14:
        v8 = v9 | 0x80070000;
        goto LABEL_15;
      }
      v5 = RegQueryValueExA(v4, (LPCSTR)&Type, 0, &Type, Data, &cbData);
    }
    v8 = v5;
    v14 = v5 < 0;
    if ( !v5 )
    {
      if ( Type != 4 || cbData != 4 )
      {
        v8 = -2147221165;
        goto LABEL_28;
      }
LABEL_21:
      v15 = *(_DWORD *)Data;
      v16 = *(_DWORD *)Data == 0;
      *(_DWORD *)this = *(_DWORD *)Data;
      *((_BYTE *)this + 4) = !v16;
      if ( v15 )
        goto LABEL_23;
      goto LABEL_22;
    }
    if ( v5 <= 0 )
    {
LABEL_16:
      if ( v14 )
      {
        if ( v8 == -2147024894 )
        {
          *((_BYTE *)this + 4) = 0;
LABEL_22:
          *(_DWORD *)this = 0;
LABEL_23:
          RegSettingsBool = GetRegSettingsBool(hKey, L"DisplayLogo", (bool *)this + 6);
          v8 = RegSettingsBool;
          if ( RegSettingsBool >= 0 )
          {
            *((_BYTE *)this + 7) = 1;
          }
          else if ( RegSettingsBool == -2147024894 )
          {
            *((_BYTE *)this + 7) = 0;
            v8 = 0;
          }
        }
LABEL_28:
        RegCloseKey(hKey);
        return v8;
      }
      goto LABEL_21;
    }
    v9 = (unsigned __int16)v5;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x140005418  push    rbp
0x14000541a  push    rbx
0x14000541b  push    rsi
0x14000541c  push    rdi
0x14000541d  push    r14
0x14000541f  sub     rsp, 60h
0x140005423  lea     rbp, [rsp+40h]
0x140005428  mov     rax, cs:__security_cookie
0x14000542f  xor     rax, rbp
0x140005432  mov     [rbp+40h+var_28], rax
0x140005436  mov     rax, rdx
0x140005439  lea     r9, [rbp+40h+hKey]; phkResult
0x14000543d  mov     rdi, rcx
0x140005440  lea     rdx, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x140005447  xor     r14d, r14d
0x14000544a  mov     rcx, rax; hKey
0x14000544d  mov     r8d, 20019h; samDesired
0x140005453  mov     [rbp+40h+hKey], r14
0x140005457  mov     dword ptr [rbp+40h+Data], r14d
0x14000545b  call    ?CreateRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CreateRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x140005460  test    eax, eax
0x140005462  js      loc_1400055F2
0x140005468  cmp     cs:?g_fWindowsNT@Global@@2_NA, r14b; bool Global::g_fWindowsNT
0x14000546f  mov     rbx, [rbp+40h+hKey]
0x140005473  mov     [rbp+40h+Type], r14d
0x140005477  mov     [rbp+40h+cbData], 4
0x14000547e  jz      short loc_1400054AE
0x140005480  lea     rax, [rbp+40h+cbData]
0x140005484  xor     r8d, r8d; lpReserved
0x140005487  mov     [rsp+80h+lpcbData], rax; lpcbData
0x14000548c  lea     r9, [rbp+40h+Type]; lpType
0x140005490  lea     rax, [rbp+40h+Data]
0x140005494  mov     rcx, rbx; hKey
0x140005497  lea     rdx, ValueName; "Timeout"
0x14000549e  mov     [rsp+80h+lpData], rax; lpData
0x1400054a3  call    cs:__imp_RegQueryValueExW
0x1400054a9  jmp     loc_14000556E
0x1400054ae  mov     [rsp+80h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1400054b3  lea     r8, ValueName; "Timeout"
0x1400054ba  mov     [rsp+80h+lpDefaultChar], r14; lpDefaultChar
0x1400054bf  or      r9d, 0FFFFFFFFh; cchWideChar
0x1400054c3  mov     dword ptr [rsp+80h+lpcbData], r14d; cbMultiByte
0x1400054c8  xor     edx, edx; dwFlags
0x1400054ca  xor     ecx, ecx; CodePage
0x1400054cc  mov     [rsp+80h+lpData], r14; lpMultiByteStr
0x1400054d1  call    cs:__imp_WideCharToMultiByte
0x1400054d7  movsxd  rdx, eax
0x1400054da  test    eax, eax
0x1400054dc  jnz     short loc_1400054F6
0x1400054de  call    cs:__imp_GetLastError
0x1400054e4  mov     ebx, eax
0x1400054e6  test    eax, eax
0x1400054e8  jle     loc_14000557F
0x1400054ee  movzx   ebx, ax
0x1400054f1  jmp     loc_140005579
0x1400054f6  lea     rcx, [rdx+0Fh]
0x1400054fa  cmp     rcx, rdx
0x1400054fd  ja      short loc_140005509
0x1400054ff  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140005509  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000550d  mov     rax, rcx
0x140005510  call    _alloca_probe
0x140005515  sub     rsp, rcx
0x140005518  lea     r8, ValueName; "Timeout"
0x14000551f  or      r9d, 0FFFFFFFFh; cchWideChar
0x140005523  xor     ecx, ecx; CodePage
0x140005525  mov     [rsp+80h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x14000552a  lea     rsi, [rsp+80h+Type]
0x14000552f  mov     [rsp+80h+lpDefaultChar], r14; lpDefaultChar
0x140005534  mov     dword ptr [rsp+80h+lpcbData], edx; cbMultiByte
0x140005538  xor     edx, edx; dwFlags
0x14000553a  mov     [rsp+80h+lpData], rsi; lpMultiByteStr
0x14000553f  call    cs:__imp_WideCharToMultiByte
0x140005545  test    eax, eax
0x140005547  jz      short loc_1400054DE
0x140005549  lea     rax, [rbp+40h+cbData]
0x14000554d  xor     r8d, r8d; lpReserved
0x140005550  mov     [rsp+80h+lpcbData], rax; lpcbData
0x140005555  lea     r9, [rbp+40h+Type]; lpType
0x140005559  lea     rax, [rbp+40h+Data]
0x14000555d  mov     rdx, rsi; lpValueName
0x140005560  mov     rcx, rbx; hKey
0x140005563  mov     [rsp+80h+lpData], rax; lpData
0x140005568  call    cs:__imp_RegQueryValueExA
0x14000556e  mov     ebx, eax
0x140005570  test    eax, eax
0x140005572  jz      short loc_140005591
0x140005574  jle     short loc_140005581
0x140005576  movzx   ebx, bx
0x140005579  or      ebx, 80070000h
0x14000557f  test    ebx, ebx
0x140005581  jns     short loc_14000559D
0x140005583  cmp     ebx, 80070002h
0x140005589  jnz     short loc_1400055E6
0x14000558b  mov     [rdi+4], r14b
0x14000558f  jmp     short loc_1400055AE
0x140005591  cmp     [rbp+40h+Type], 4
0x140005595  jnz     short loc_1400055E1
0x140005597  cmp     [rbp+40h+cbData], 4
0x14000559b  jnz     short loc_1400055E1
0x14000559d  mov     ecx, dword ptr [rbp+40h+Data]
0x1400055a0  test    ecx, ecx
0x1400055a2  mov     [rdi], ecx
0x1400055a4  setnz   al
0x1400055a7  mov     [rdi+4], al
0x1400055aa  test    ecx, ecx
0x1400055ac  jnz     short loc_1400055B1
0x1400055ae  mov     [rdi], r14d
0x1400055b1  mov     rcx, [rbp+40h+hKey]; hKey
0x1400055b5  lea     r8, [rdi+6]; bool *
0x1400055b9  lea     rdx, aDisplaylogo; "DisplayLogo"
0x1400055c0  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x1400055c5  mov     ebx, eax
0x1400055c7  test    eax, eax
0x1400055c9  jns     short loc_1400055DB
0x1400055cb  cmp     eax, 80070002h
0x1400055d0  jnz     short loc_1400055E6
0x1400055d2  mov     [rdi+7], r14b
0x1400055d6  mov     ebx, r14d
0x1400055d9  jmp     short loc_1400055E6
0x1400055db  mov     byte ptr [rdi+7], 1
0x1400055df  jmp     short loc_1400055E6
0x1400055e1  mov     ebx, 80040153h
0x1400055e6  mov     rcx, [rbp+40h+hKey]; hKey
0x1400055ea  call    cs:__imp_RegCloseKey
0x1400055f0  mov     eax, ebx
0x1400055f2  mov     rcx, [rbp+40h+var_28]
0x1400055f6  xor     rcx, rbp; StackCookie
0x1400055f9  call    __security_check_cookie
0x1400055fe  lea     rsp, [rbp+20h]
0x140005602  pop     r14
0x140005604  pop     rdi
0x140005605  pop     rsi
0x140005606  pop     rbx
0x140005607  pop     rbp
0x140005608  retn
```
