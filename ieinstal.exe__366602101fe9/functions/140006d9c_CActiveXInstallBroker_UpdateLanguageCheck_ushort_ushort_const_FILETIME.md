# CActiveXInstallBroker::UpdateLanguageCheck(ushort *,ushort const *,_FILETIME)

- ea: `0x140006d9c`
- end: `0x140006f9d`
- name: `?UpdateLanguageCheck@CActiveXInstallBroker@@QEAAJPEAGPEBGU_FILETIME@@@Z`
- size: `513`
- prototype: `int(CActiveXInstallBroker *__hidden this, unsigned __int16 *, const unsigned __int16 *, struct _FILETIME)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140008580`

## callees

- `0x140006d9c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140006f07`
- `ADVAPI32!RegSetValueExW` at `0x140006f07`
- `ADVAPI32!RegCloseKey` at `0x140006f36`
- `ADVAPI32!RegCloseKey` at `0x140006f4b`
- `ADVAPI32!RegCloseKey` at `0x140006f60`
- `ADVAPI32!RegCloseKey` at `0x140006f36`
- `ADVAPI32!RegCloseKey` at `0x140006f4b`
- `ADVAPI32!RegCloseKey` at `0x140006f60`
- `ADVAPI32!RegCreateKeyW` at `0x140006ed5`
- `ADVAPI32!RegCreateKeyW` at `0x140006ed5`
- `ADVAPI32!RegOpenKeyExW` at `0x140006e5d`
- `ADVAPI32!RegOpenKeyExW` at `0x140006e8c`
- `ADVAPI32!RegOpenKeyExW` at `0x140006eb6`
- `ADVAPI32!RegOpenKeyExW` at `0x140006e5d`
- `ADVAPI32!RegOpenKeyExW` at `0x140006e8c`
- `ADVAPI32!RegOpenKeyExW` at `0x140006eb6`
- `KERNEL32!LeaveCriticalSection` at `0x140006f7b`
- `KERNEL32!LeaveCriticalSection` at `0x140006f7b`
- `KERNEL32!EnterCriticalSection` at `0x140006de7`
- `KERNEL32!EnterCriticalSection` at `0x140006de7`

## string_xrefs

- `0x140006e4f`: `CLSID`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::UpdateLanguageCheck(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _FILETIME a4)
{
  bool v4; // zf
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // eax
  LSTATUS v13; // eax
  bool v14; // cc
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  HKEY v18; // [rsp+60h] [rbp+20h] BYREF
  struct _FILETIME Data; // [rsp+78h] [rbp+38h] BYREF

  Data = a4;
  v4 = *(_DWORD *)this == 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  hKey = 0;
  phkResult = 0;
  v18 = 0;
  if ( v4 )
  {
    v9 = -2147024882;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( *((int *)this + 12) >= 7 )
    {
      if ( a2 && a3 )
      {
        v10 = *((_QWORD *)this + 8) - (_QWORD)a2;
        do
        {
          v11 = *(unsigned __int16 *)((char *)a2 + v10);
          v12 = *a2 - v11;
          if ( v12 )
            break;
          ++a2;
        }
        while ( v11 );
        if ( v12 )
        {
          v9 = -2147024891;
        }
        else
        {
          v13 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20019u, &hKey);
          v14 = v13 <= 0;
          if ( v13
            || (v13 = RegOpenKeyExW(hKey, a3, 0, 0x2001Fu, &phkResult), v14 = v13 <= 0, v13)
            || RegOpenKeyExW(phkResult, L"LanguageCheckPeriod", 0, 0x2001Fu, &v18)
            && (v13 = RegCreateKeyW(phkResult, L"LanguageCheckPeriod", &v18), v14 = v13 <= 0, v13)
            || (v9 = 0,
                v13 = RegSetValueExW(v18, L"LastCheckedHi", 0, 4u, (const BYTE *)&Data.dwHighDateTime, 4u),
                v14 = v13 <= 0,
                v13) )
          {
            if ( v14 )
              v9 = v13;
            else
              v9 = (unsigned __int16)v13 | 0x80070000;
          }
        }
      }
      else
      {
        v9 = -2147024809;
      }
    }
    else
    {
      v9 = -2147019873;
    }
    if ( v18 )
      RegCloseKey(v18);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( *(_DWORD *)this )
    LeaveCriticalSection(v5);
  return v9;
}

```

## disassembly

```asm
0x140006d9c  mov     [rsp-18h+arg_8], rbx
0x140006da1  mov     [rsp-18h+arg_10], rsi
0x140006da6  mov     [rsp-18h+Data], r9
0x140006dab  push    rbp
0x140006dac  push    rdi
0x140006dad  push    r14
0x140006daf  mov     rbp, rsp
0x140006db2  sub     rsp, 40h
0x140006db6  cmp     dword ptr [rcx], 0
0x140006db9  lea     rsi, [rcx+8]
0x140006dbd  mov     r14, r8
0x140006dc0  mov     [rbp+hKey], 0
0x140006dc8  mov     rbx, rdx
0x140006dcb  mov     [rbp+var_10], 0
0x140006dd3  mov     rdi, rcx
0x140006dd6  mov     [rbp+arg_0], 0
0x140006dde  jz      loc_140006F6E
0x140006de4  mov     rcx, rsi; lpCriticalSection
0x140006de7  call    cs:__imp_EnterCriticalSection
0x140006dee  nop     dword ptr [rax+rax+00h]
0x140006df3  cmp     dword ptr [rdi+30h], 7
0x140006df7  jge     short loc_140006E03
0x140006df9  mov     ebx, 8007139Fh
0x140006dfe  jmp     loc_140006F2D
0x140006e03  test    rbx, rbx
0x140006e06  jz      loc_140006F28
0x140006e0c  test    r14, r14
0x140006e0f  jz      loc_140006F28
0x140006e15  mov     rdx, [rdi+40h]
0x140006e19  sub     rdx, rbx
0x140006e1c  movzx   eax, word ptr [rbx]
0x140006e1f  movzx   ecx, word ptr [rbx+rdx]
0x140006e23  sub     eax, ecx
0x140006e25  jnz     short loc_140006E2F
0x140006e27  add     rbx, 2
0x140006e2b  test    ecx, ecx
0x140006e2d  jnz     short loc_140006E1C
0x140006e2f  test    eax, eax
0x140006e31  jz      short loc_140006E3D
0x140006e33  mov     ebx, 80070005h
0x140006e38  jmp     loc_140006F2D
0x140006e3d  lea     rax, [rbp+hKey]
0x140006e41  mov     r9d, 20019h; samDesired
0x140006e47  xor     r8d, r8d; ulOptions
0x140006e4a  mov     [rsp+40h+phkResult], rax; phkResult
0x140006e4f  lea     rdx, aClsid_0; "CLSID"
0x140006e56  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140006e5d  call    cs:__imp_RegOpenKeyExW
0x140006e64  nop     dword ptr [rax+rax+00h]
0x140006e69  test    eax, eax
0x140006e6b  jnz     loc_140006F17
0x140006e71  mov     rcx, [rbp+hKey]; hKey
0x140006e75  lea     rax, [rbp+var_10]
0x140006e79  mov     ebx, 2001Fh
0x140006e7e  mov     [rsp+40h+phkResult], rax; phkResult
0x140006e83  mov     r9d, ebx; samDesired
0x140006e86  xor     r8d, r8d; ulOptions
0x140006e89  mov     rdx, r14; lpSubKey
0x140006e8c  call    cs:__imp_RegOpenKeyExW
0x140006e93  nop     dword ptr [rax+rax+00h]
0x140006e98  test    eax, eax
0x140006e9a  jnz     short loc_140006F17
0x140006e9c  mov     rcx, [rbp+var_10]; hKey
0x140006ea0  lea     rax, [rbp+arg_0]
0x140006ea4  mov     r9d, ebx; samDesired
0x140006ea7  mov     [rsp+40h+phkResult], rax; phkResult
0x140006eac  xor     r8d, r8d; ulOptions
0x140006eaf  lea     rdx, aLanguagecheckp; "LanguageCheckPeriod"
0x140006eb6  call    cs:__imp_RegOpenKeyExW
0x140006ebd  nop     dword ptr [rax+rax+00h]
0x140006ec2  test    eax, eax
0x140006ec4  jz      short loc_140006EE5
0x140006ec6  mov     rcx, [rbp+var_10]; hKey
0x140006eca  lea     r8, [rbp+arg_0]; phkResult
0x140006ece  lea     rdx, aLanguagecheckp; "LanguageCheckPeriod"
0x140006ed5  call    cs:__imp_RegCreateKeyW
0x140006edc  nop     dword ptr [rax+rax+00h]
0x140006ee1  test    eax, eax
0x140006ee3  jnz     short loc_140006F17
0x140006ee5  mov     rcx, [rbp+arg_0]; hKey
0x140006ee9  lea     rax, [rbp+Data+4]
0x140006eed  xor     ebx, ebx
0x140006eef  lea     rdx, aLastcheckedhi; "LastCheckedHi"
0x140006ef6  xor     r8d, r8d; Reserved
0x140006ef9  lea     r9d, [rbx+4]; dwType
0x140006efd  mov     [rsp+40h+cbData], r9d; cbData
0x140006f02  mov     [rsp+40h+phkResult], rax; lpData
0x140006f07  call    cs:__imp_RegSetValueExW
0x140006f0e  nop     dword ptr [rax+rax+00h]
0x140006f13  test    eax, eax
0x140006f15  jz      short loc_140006F2D
0x140006f17  jg      short loc_140006F1D
0x140006f19  mov     ebx, eax
0x140006f1b  jmp     short loc_140006F2D
0x140006f1d  movzx   ebx, ax
0x140006f20  or      ebx, 80070000h
0x140006f26  jmp     short loc_140006F2D
0x140006f28  mov     ebx, 80070057h
0x140006f2d  mov     rcx, [rbp+arg_0]; hKey
0x140006f31  test    rcx, rcx
0x140006f34  jz      short loc_140006F42
0x140006f36  call    cs:__imp_RegCloseKey
0x140006f3d  nop     dword ptr [rax+rax+00h]
0x140006f42  mov     rcx, [rbp+var_10]; hKey
0x140006f46  test    rcx, rcx
0x140006f49  jz      short loc_140006F57
0x140006f4b  call    cs:__imp_RegCloseKey
0x140006f52  nop     dword ptr [rax+rax+00h]
0x140006f57  mov     rcx, [rbp+hKey]; hKey
0x140006f5b  test    rcx, rcx
0x140006f5e  jz      short loc_140006F73
0x140006f60  call    cs:__imp_RegCloseKey
0x140006f67  nop     dword ptr [rax+rax+00h]
0x140006f6c  jmp     short loc_140006F73
0x140006f6e  mov     ebx, 8007000Eh
0x140006f73  cmp     dword ptr [rdi], 0
0x140006f76  jz      short loc_140006F87
0x140006f78  mov     rcx, rsi; lpCriticalSection
0x140006f7b  call    cs:__imp_LeaveCriticalSection
0x140006f82  nop     dword ptr [rax+rax+00h]
0x140006f87  mov     rsi, [rsp+40h+arg_10]
0x140006f8c  mov     eax, ebx
0x140006f8e  mov     rbx, [rsp+40h+arg_8]
0x140006f93  add     rsp, 40h
0x140006f97  pop     r14
0x140006f99  pop     rdi
0x140006f9a  pop     rbp
0x140006f9b  retn
```
