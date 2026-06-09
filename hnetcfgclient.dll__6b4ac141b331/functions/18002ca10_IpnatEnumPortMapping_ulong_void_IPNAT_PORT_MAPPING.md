# IpnatEnumPortMapping(ulong,void * *,_IPNAT_PORT_MAPPING *)

- ea: `0x18002ca10`
- end: `0x18002cbec`
- name: `?IpnatEnumPortMapping@@YAJKPEAPEAXPEAU_IPNAT_PORT_MAPPING@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(DWORD dwIndex, void **, struct _IPNAT_PORT_MAPPING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180021fa0`

## callees

- `0x180005698`
- `0x18002ca10`
- `0x18002d200`

## import_xrefs

- `msvcrt!wcstok_s` at `0x18002cbb4`
- `msvcrt!wcstok_s` at `0x18002cbb4`
- `msvcrt!_wtoi` at `0x18002cb78`
- `msvcrt!_wtoi` at `0x18002cb87`
- `msvcrt!_wtoi` at `0x18002cb78`
- `msvcrt!_wtoi` at `0x18002cb87`
- `msvcrt!_wcsicmp` at `0x18002cb4b`
- `msvcrt!_wcsicmp` at `0x18002cb65`
- `msvcrt!_wcsicmp` at `0x18002cb4b`
- `msvcrt!_wcsicmp` at `0x18002cb65`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002cafa`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002cafa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ca8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ca8f`

## string_xrefs

- `0x18002ca73`: `SYSTEM\CurrentControlSet\services\SharedAccess\Setup\StaticPortMapping`

## pseudocode

```c
__int64 __fastcall IpnatEnumPortMapping(DWORD dwIndex, HKEY *a2, struct _IPNAT_PORT_MAPPING *a3)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  bool v8; // cc
  HKEY v9; // rcx
  WCHAR *v10; // rcx
  int i; // r14d
  wchar_t *v12; // rax
  const wchar_t *v13; // rdi
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Delimiter[2]; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *Context; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF

  cchValueName = 0;
  phkResult = 0;
  if ( a3 && a2 )
  {
    if ( dwIndex )
    {
      v9 = *a2;
      phkResult = *a2;
    }
    else
    {
      *a2 = 0;
      v6 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\services\\SharedAccess\\Setup\\StaticPortMapping",
             0,
             0x20019u,
             &phkResult);
      v7 = v6;
      v8 = v6 <= 0;
      if ( v6 )
        goto LABEL_5;
      v9 = phkResult;
      *a2 = phkResult;
    }
    cchValueName = 260;
    v6 = RegEnumValueW(v9, dwIndex, ValueName, &cchValueName, 0, 0, 0, 0);
    v7 = v6;
    v8 = v6 <= 0;
    if ( !v6 )
    {
      Context = 0;
      v10 = ValueName;
      wcscpy(Delimiter, L";");
      for ( i = 0; ; ++i )
      {
        v12 = wcstok_s(v10, Delimiter, &Context);
        v13 = v12;
        if ( !v12 || i >= 4 )
          break;
        if ( i )
        {
          switch ( i )
          {
            case 1:
              *((_WORD *)a3 + 46) = _wtoi(v12);
              break;
            case 2:
              *((_WORD *)a3 + 47) = _wtoi(v12);
              break;
            case 3:
              if ( _wcsicmp(L"tcp", v12) )
              {
                if ( !_wcsicmp(L"udp", v13) )
                  *((_BYTE *)a3 + 96) = 17;
              }
              else
              {
                *((_BYTE *)a3 + 96) = 6;
              }
              break;
          }
        }
        else
        {
          v7 = StringCchCopyW((unsigned __int16 *)a3, 0x2Eu, v12);
        }
        v10 = 0;
      }
      return v7;
    }
LABEL_5:
    if ( !v8 )
      return (unsigned __int16)v6 | 0x80070000;
    return v7;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002ca10  push    rbp
0x18002ca12  push    rbx
0x18002ca13  push    rsi
0x18002ca14  push    rdi
0x18002ca15  push    r14
0x18002ca17  lea     rbp, [rsp-180h]
0x18002ca1f  sub     rsp, 280h
0x18002ca26  mov     rax, cs:__security_cookie
0x18002ca2d  xor     rax, rsp
0x18002ca30  mov     [rbp+1A0h+var_30], rax
0x18002ca37  mov     [rsp+2A0h+cchValueName], 0
0x18002ca3f  mov     rsi, r8
0x18002ca42  mov     [rsp+2A0h+var_258], 0
0x18002ca4b  mov     rdi, rdx
0x18002ca4e  mov     r14d, ecx
0x18002ca51  test    r8, r8
0x18002ca54  jz      loc_18002CBCA
0x18002ca5a  test    rdx, rdx
0x18002ca5d  jz      loc_18002CBCA
0x18002ca63  test    ecx, ecx
0x18002ca65  jnz     short loc_18002CAB9
0x18002ca67  mov     qword ptr [rdx], 0
0x18002ca6e  lea     rax, [rsp+2A0h+var_258]
0x18002ca73  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\services\\Sh"...
0x18002ca7a  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18002ca7f  mov     r9d, 20019h; samDesired
0x18002ca85  xor     r8d, r8d; ulOptions
0x18002ca88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ca8f  call    cs:__imp_RegOpenKeyExW
0x18002ca95  mov     ebx, eax
0x18002ca97  test    eax, eax
0x18002ca99  jz      short loc_18002CAAF
0x18002ca9b  jle     loc_18002CBC6
0x18002caa1  movzx   ebx, ax
0x18002caa4  or      ebx, 80070000h
0x18002caaa  jmp     loc_18002CBC6
0x18002caaf  mov     rcx, [rsp+2A0h+var_258]
0x18002cab4  mov     [rdi], rcx
0x18002cab7  jmp     short loc_18002CAC1
0x18002cab9  mov     rcx, [rdx]; hKey
0x18002cabc  mov     [rsp+2A0h+var_258], rcx
0x18002cac1  mov     [rsp+2A0h+lpcbData], 0; lpcbData
0x18002caca  lea     r9, [rsp+2A0h+cchValueName]; lpcchValueName
0x18002cacf  mov     [rsp+2A0h+lpData], 0; lpData
0x18002cad8  lea     r8, [rsp+2A0h+ValueName]; lpValueName
0x18002cadd  mov     [rsp+2A0h+lpType], 0; lpType
0x18002cae6  mov     edx, r14d; dwIndex
0x18002cae9  mov     [rsp+2A0h+phkResult], 0; lpReserved
0x18002caf2  mov     [rsp+2A0h+cchValueName], 104h
0x18002cafa  call    cs:__imp_RegEnumValueW
0x18002cb00  mov     ebx, eax
0x18002cb02  test    eax, eax
0x18002cb04  jnz     short loc_18002CA9B
0x18002cb06  mov     [rsp+2A0h+Context], rbx
0x18002cb0b  lea     rcx, [rsp+2A0h+ValueName]
0x18002cb10  mov     dword ptr [rsp+2A0h+Delimiter], 3Bh ; ';'
0x18002cb18  xor     r14d, r14d
0x18002cb1b  jmp     loc_18002CBAA
0x18002cb20  cmp     r14d, 4
0x18002cb24  jge     loc_18002CBC6
0x18002cb2a  mov     ecx, r14d
0x18002cb2d  test    r14d, r14d
0x18002cb30  jz      short loc_18002CB93
0x18002cb32  sub     ecx, 1
0x18002cb35  jz      short loc_18002CB84
0x18002cb37  sub     ecx, 1
0x18002cb3a  jz      short loc_18002CB75
0x18002cb3c  cmp     ecx, 1
0x18002cb3f  jnz     short loc_18002CBA5
0x18002cb41  mov     rdx, rdi; String2
0x18002cb44  lea     rcx, aTcp; "tcp"
0x18002cb4b  call    cs:__imp__wcsicmp
0x18002cb51  test    eax, eax
0x18002cb53  jnz     short loc_18002CB5B
0x18002cb55  mov     byte ptr [rsi+60h], 6
0x18002cb59  jmp     short loc_18002CBA5
0x18002cb5b  mov     rdx, rdi; String2
0x18002cb5e  lea     rcx, aUdp; "udp"
0x18002cb65  call    cs:__imp__wcsicmp
0x18002cb6b  test    eax, eax
0x18002cb6d  jnz     short loc_18002CBA5
0x18002cb6f  mov     byte ptr [rsi+60h], 11h
0x18002cb73  jmp     short loc_18002CBA5
0x18002cb75  mov     rcx, rdi; String
0x18002cb78  call    cs:__imp__wtoi
0x18002cb7e  mov     [rsi+5Eh], ax
0x18002cb82  jmp     short loc_18002CBA5
0x18002cb84  mov     rcx, rdi; String
0x18002cb87  call    cs:__imp__wtoi
0x18002cb8d  mov     [rsi+5Ch], ax
0x18002cb91  jmp     short loc_18002CBA5
0x18002cb93  mov     r8, rdi; unsigned __int16 *
0x18002cb96  mov     edx, 2Eh ; '.'; unsigned __int64
0x18002cb9b  mov     rcx, rsi; unsigned __int16 *
0x18002cb9e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cba3  mov     ebx, eax
0x18002cba5  inc     r14d
0x18002cba8  xor     ecx, ecx; String
0x18002cbaa  lea     r8, [rsp+2A0h+Context]; Context
0x18002cbaf  lea     rdx, [rsp+2A0h+Delimiter]; Delimiter
0x18002cbb4  call    cs:__imp_wcstok_s
0x18002cbba  mov     rdi, rax
0x18002cbbd  test    rax, rax
0x18002cbc0  jnz     loc_18002CB20
0x18002cbc6  mov     eax, ebx
0x18002cbc8  jmp     short loc_18002CBCF
0x18002cbca  mov     eax, 80070057h
0x18002cbcf  mov     rcx, [rbp+1A0h+var_30]
0x18002cbd6  xor     rcx, rsp; StackCookie
0x18002cbd9  call    __security_check_cookie
0x18002cbde  add     rsp, 280h
0x18002cbe5  pop     r14
0x18002cbe7  pop     rdi
0x18002cbe8  pop     rsi
0x18002cbe9  pop     rbx
0x18002cbea  pop     rbp
0x18002cbeb  retn
```
