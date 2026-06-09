# CMvExtensionKey::ReadProvisionStates(HKEY__ *)

- ea: `0x18001576c`
- end: `0x18001592c`
- name: `?ReadProvisionStates@CMvExtensionKey@@AEAAJPEAUHKEY__@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(CMvExtensionKey *this, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001504c`

## callees

- `0x18001576c`
- `0x1800366b8`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800157ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800157ca`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001581a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800158c8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001581a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800158c8`

## pseudocode

```c
__int64 __fastcall CMvExtensionKey::ReadProvisionStates(CMvExtensionKey *this, HKEY a2)
{
  LSTATUS v3; // eax
  LSTATUS ProvisionStateFromString; // ebx
  DWORD v5; // esi
  bool v6; // zf
  __int64 v7; // rdx
  unsigned int v8; // ecx
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  cchValueName = 0;
  v3 = RegOpenKeyExW(a2, L"ProvisionState", 0, 0x20019u, &hKey);
  ProvisionStateFromString = v3;
  if ( v3 )
  {
    if ( v3 <= 0 )
      goto LABEL_20;
    ProvisionStateFromString = (unsigned __int16)v3;
    goto LABEL_4;
  }
  v5 = 0;
  cchValueName = 260;
  ProvisionStateFromString = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, 0, 0, 0);
  if ( ProvisionStateFromString != 259 )
  {
    while ( !ProvisionStateFromString )
    {
      if ( cchValueName )
      {
        v6 = *((_DWORD *)this + 150) == 18;
        v11 = 0;
        if ( v6 )
          goto LABEL_19;
        ProvisionStateFromString = GetProvisionStateFromString(
                                     ValueName,
                                     (enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *)&v11);
        if ( ProvisionStateFromString < 0 )
          goto LABEL_20;
        v7 = *((unsigned int *)this + 150);
        v8 = 0;
        if ( (_DWORD)v7 )
        {
          while ( *((_DWORD *)this + v8 + 132) != v11 )
          {
            if ( ++v8 >= (unsigned int)v7 )
              goto LABEL_13;
          }
          goto LABEL_19;
        }
LABEL_13:
        *((_DWORD *)this + v7 + 132) = v11;
        ++*((_DWORD *)this + 150);
      }
      ++v5;
      cchValueName = 260;
      ProvisionStateFromString = RegEnumValueW(hKey, v5, ValueName, &cchValueName, 0, 0, 0, 0);
      if ( ProvisionStateFromString == 259 )
      {
        if ( !v5 )
          goto LABEL_19;
        ProvisionStateFromString = 0;
        goto LABEL_20;
      }
    }
    if ( ProvisionStateFromString <= 0 )
      goto LABEL_20;
    ProvisionStateFromString = (unsigned __int16)ProvisionStateFromString;
LABEL_4:
    ProvisionStateFromString |= 0x80070000;
    goto LABEL_20;
  }
LABEL_19:
  ProvisionStateFromString = -2147024809;
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)ProvisionStateFromString;
}

```

## disassembly

```asm
0x18001576c  mov     [rsp-8+arg_10], rbx
0x180015771  mov     [rsp-8+arg_18], rsi
0x180015776  push    rbp
0x180015777  push    rdi
0x180015778  push    r14
0x18001577a  lea     rbp, [rsp-170h]
0x180015782  sub     rsp, 270h
0x180015789  mov     rax, cs:__security_cookie
0x180015790  xor     rax, rsp
0x180015793  mov     [rbp+180h+var_20], rax
0x18001579a  mov     rdi, rcx
0x18001579d  mov     rax, rdx
0x1800157a0  lea     rcx, [rsp+280h+hKey]
0x1800157a5  xor     r14d, r14d
0x1800157a8  mov     [rsp+280h+phkResult], rcx; phkResult
0x1800157ad  lea     rdx, aProvisionstate; "ProvisionState"
0x1800157b4  mov     rcx, rax; hKey
0x1800157b7  mov     [rsp+280h+hKey], r14
0x1800157bc  mov     r9d, 20019h; samDesired
0x1800157c2  mov     [rsp+280h+cchValueName], r14d
0x1800157c7  xor     r8d, r8d; ulOptions
0x1800157ca  call    cs:__imp_RegOpenKeyExW
0x1800157d0  mov     ebx, eax
0x1800157d2  test    eax, eax
0x1800157d4  jz      short loc_1800157EA
0x1800157d6  jle     loc_1800158F3
0x1800157dc  movzx   ebx, ax
0x1800157df  or      ebx, 80070000h
0x1800157e5  jmp     loc_1800158F3
0x1800157ea  mov     rcx, [rsp+280h+hKey]; hKey
0x1800157ef  lea     r9, [rsp+280h+cchValueName]; lpcchValueName
0x1800157f4  mov     [rsp+280h+lpcbData], r14; lpcbData
0x1800157f9  lea     r8, [rsp+280h+ValueName]; lpValueName
0x1800157fe  mov     [rsp+280h+lpData], r14; lpData
0x180015803  xor     edx, edx; dwIndex
0x180015805  mov     [rsp+280h+lpType], r14; lpType
0x18001580a  mov     esi, r14d
0x18001580d  mov     [rsp+280h+phkResult], r14; lpReserved
0x180015812  mov     [rsp+280h+cchValueName], 104h
0x18001581a  call    cs:__imp_RegEnumValueW
0x180015820  mov     ebx, eax
0x180015822  cmp     eax, 103h
0x180015827  jz      loc_1800158EE
0x18001582d  test    ebx, ebx
0x18001582f  jnz     loc_1800158E4
0x180015835  cmp     [rsp+280h+cchValueName], r14d
0x18001583a  jbe     short loc_180015899
0x18001583c  cmp     dword ptr [rdi+258h], 12h
0x180015843  mov     [rsp+280h+var_23C], r14d
0x180015848  jz      loc_1800158EE
0x18001584e  lea     rdx, [rsp+280h+var_23C]; enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *
0x180015853  lea     rcx, [rsp+280h+ValueName]; String1
0x180015858  call    ?GetProvisionStateFromString@@YAJPEBGPEAW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@@Z; GetProvisionStateFromString(ushort const *,__MIDL___MIDL_itf_mvengine_0000_0000_0001 *)
0x18001585d  mov     ebx, eax
0x18001585f  test    eax, eax
0x180015861  js      loc_1800158F3
0x180015867  mov     edx, [rdi+258h]
0x18001586d  mov     ecx, r14d
0x180015870  mov     r8d, [rsp+280h+var_23C]
0x180015875  test    edx, edx
0x180015877  jz      short loc_18001588B
0x180015879  mov     eax, ecx
0x18001587b  cmp     [rdi+rax*4+210h], r8d
0x180015883  jz      short loc_1800158EE
0x180015885  inc     ecx
0x180015887  cmp     ecx, edx
0x180015889  jb      short loc_180015879
0x18001588b  mov     [rdi+rdx*4+210h], r8d
0x180015893  inc     dword ptr [rdi+258h]
0x180015899  mov     rcx, [rsp+280h+hKey]; hKey
0x18001589e  lea     r9, [rsp+280h+cchValueName]; lpcchValueName
0x1800158a3  mov     [rsp+280h+lpcbData], r14; lpcbData
0x1800158a8  lea     r8, [rsp+280h+ValueName]; lpValueName
0x1800158ad  mov     [rsp+280h+lpData], r14; lpData
0x1800158b2  inc     esi
0x1800158b4  mov     [rsp+280h+lpType], r14; lpType
0x1800158b9  mov     edx, esi; dwIndex
0x1800158bb  mov     [rsp+280h+phkResult], r14; lpReserved
0x1800158c0  mov     [rsp+280h+cchValueName], 104h
0x1800158c8  call    cs:__imp_RegEnumValueW
0x1800158ce  mov     ebx, eax
0x1800158d0  cmp     eax, 103h
0x1800158d5  jnz     loc_18001582D
0x1800158db  test    esi, esi
0x1800158dd  jz      short loc_1800158EE
0x1800158df  mov     ebx, r14d
0x1800158e2  jmp     short loc_1800158F3
0x1800158e4  jle     short loc_1800158F3
0x1800158e6  movzx   ebx, bx
0x1800158e9  jmp     loc_1800157DF
0x1800158ee  mov     ebx, 80070057h
0x1800158f3  mov     rcx, [rsp+280h+hKey]; hKey
0x1800158f8  test    rcx, rcx
0x1800158fb  jz      short loc_180015903
0x1800158fd  call    cs:__imp_RegCloseKey
0x180015903  mov     eax, ebx
0x180015905  mov     rcx, [rbp+180h+var_20]
0x18001590c  xor     rcx, rsp; StackCookie
0x18001590f  call    __security_check_cookie
0x180015914  lea     r11, [rsp+280h+var_10]
0x18001591c  mov     rbx, [r11+30h]
0x180015920  mov     rsi, [r11+38h]
0x180015924  mov     rsp, r11
0x180015927  pop     r14
0x180015929  pop     rdi
0x18001592a  pop     rbp
0x18001592b  retn
```
