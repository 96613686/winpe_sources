# SetRegistryValue(ushort *,ushort *)

- ea: `0x140035e8c`
- end: `0x140035fb2`
- name: `?SetRegistryValue@@YAJPEAG0@Z`
- size: `294`
- prototype: `int(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140025314`

## callees

- `0x140035e8c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140035f1b`
- `ADVAPI32!RegCloseKey` at `0x140035f1b`
- `ADVAPI32!RegOpenKeyExW` at `0x140035ee5`
- `ADVAPI32!RegOpenKeyExW` at `0x140035ee5`
- `ADVAPI32!RegSetValueExW` at `0x140035f91`
- `ADVAPI32!RegSetValueExW` at `0x140035f91`
- `OLEAUT32!__imp_SysAllocString` at `0x140035ea9`
- `OLEAUT32!__imp_SysAllocString` at `0x140035ea9`
- `OLEAUT32!__imp_SysFreeString` at `0x140035f05`
- `OLEAUT32!__imp_SysFreeString` at `0x140035f05`

## string_xrefs

- `0x140035f72`: `Wallpaper Path`

## pseudocode

```c
__int64 __fastcall SetRegistryValue(unsigned __int16 *a1, unsigned __int16 *a2)
{
  BYTE *v2; // rdi
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  __int64 v6; // rdx
  BYTE *v7; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v2 = (BYTE *)SysAllocString(a2);
  if ( !v2 )
  {
    v3 = -2147467259;
    goto LABEL_7;
  }
  v4 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Remote Assistance", 0, 2u, &hKey);
  v3 = v4;
  if ( !v4 )
  {
    v6 = 0x7FFFFFFF;
    v7 = v2;
    do
    {
      if ( !*(_WORD *)v7 )
        break;
      v7 += 2;
      --v6;
    }
    while ( v6 );
    if ( !v6 )
    {
      v3 = -2147467259;
      goto LABEL_6;
    }
    v3 = 0;
    v4 = RegSetValueExW(hKey, L"Wallpaper Path", 0, 1u, v2, v6 != 0 ? -2 - 2 * v6 + 2 : 2);
    if ( !v4 )
      goto LABEL_6;
    if ( v4 <= 0 )
    {
      v3 = v4;
      goto LABEL_6;
    }
    goto LABEL_5;
  }
  if ( v4 > 0 )
LABEL_5:
    v3 = (unsigned __int16)v4 | 0x80070000;
LABEL_6:
  SysFreeString((BSTR)v2);
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x140035e8c  mov     rax, rsp
0x140035e8f  mov     [rax+10h], rbx
0x140035e93  mov     [rax+18h], rsi
0x140035e97  mov     [rax+8], rcx
0x140035e9b  push    rdi
0x140035e9c  sub     rsp, 30h
0x140035ea0  xor     esi, esi
0x140035ea2  mov     rcx, rdx; psz
0x140035ea5  mov     [rax+8], rsi
0x140035ea9  call    cs:__imp_SysAllocString
0x140035eb0  nop     dword ptr [rax+rax+00h]
0x140035eb5  mov     rdi, rax
0x140035eb8  test    rax, rax
0x140035ebb  jnz     short loc_140035EC4
0x140035ebd  mov     ebx, 80004005h
0x140035ec2  jmp     short loc_140035F11
0x140035ec4  lea     rax, [rsp+38h+hKey]
0x140035ec9  mov     r9d, 2; samDesired
0x140035ecf  xor     r8d, r8d; ulOptions
0x140035ed2  mov     [rsp+38h+phkResult], rax; phkResult
0x140035ed7  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Remote Assistance"
0x140035ede  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140035ee5  call    cs:__imp_RegOpenKeyExW
0x140035eec  nop     dword ptr [rax+rax+00h]
0x140035ef1  mov     ebx, eax
0x140035ef3  test    eax, eax
0x140035ef5  jz      short loc_140035F3A
0x140035ef7  jle     short loc_140035F02
0x140035ef9  movzx   ebx, ax
0x140035efc  or      ebx, 80070000h
0x140035f02  mov     rcx, rdi; bstrString
0x140035f05  call    cs:__imp_SysFreeString
0x140035f0c  nop     dword ptr [rax+rax+00h]
0x140035f11  mov     rcx, [rsp+38h+hKey]; hKey
0x140035f16  test    rcx, rcx
0x140035f19  jz      short loc_140035F27
0x140035f1b  call    cs:__imp_RegCloseKey
0x140035f22  nop     dword ptr [rax+rax+00h]
0x140035f27  mov     rsi, [rsp+38h+arg_10]
0x140035f2c  mov     eax, ebx
0x140035f2e  mov     rbx, [rsp+38h+arg_8]
0x140035f33  add     rsp, 30h
0x140035f37  pop     rdi
0x140035f38  retn
0x140035f3a  mov     edx, 7FFFFFFFh
0x140035f3f  mov     rax, rdi
0x140035f42  cmp     [rax], si
0x140035f45  jz      short loc_140035F51
0x140035f47  add     rax, 2
0x140035f4b  sub     rdx, 1
0x140035f4f  jnz     short loc_140035F42
0x140035f51  test    rdx, rdx
0x140035f54  jnz     short loc_140035F5D
0x140035f56  mov     ebx, 80004005h
0x140035f5b  jmp     short loc_140035F02
0x140035f5d  lea     eax, [rdx+rdx]
0x140035f60  mov     ecx, 0FFFFFFFEh
0x140035f65  sub     ecx, eax
0x140035f67  mov     r9d, 1; dwType
0x140035f6d  neg     rdx
0x140035f70  mov     ebx, esi
0x140035f72  lea     rdx, aWallpaperPath; "Wallpaper Path"
0x140035f79  sbb     eax, eax
0x140035f7b  xor     r8d, r8d; Reserved
0x140035f7e  and     eax, ecx
0x140035f80  mov     rcx, [rsp+38h+hKey]; hKey
0x140035f85  add     eax, 2
0x140035f88  mov     [rsp+38h+cbData], eax; cbData
0x140035f8c  mov     [rsp+38h+phkResult], rdi; lpData
0x140035f91  call    cs:__imp_RegSetValueExW
0x140035f98  nop     dword ptr [rax+rax+00h]
0x140035f9d  test    eax, eax
0x140035f9f  jz      loc_140035F02
0x140035fa5  jg      loc_140035EF9
0x140035fab  mov     ebx, eax
0x140035fad  jmp     loc_140035F02
```
