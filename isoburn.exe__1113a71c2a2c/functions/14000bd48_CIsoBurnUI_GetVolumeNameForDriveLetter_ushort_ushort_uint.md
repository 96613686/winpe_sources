# CIsoBurnUI::_GetVolumeNameForDriveLetter(ushort,ushort *,uint)

- ea: `0x14000bd48`
- end: `0x14000be48`
- name: `?_GetVolumeNameForDriveLetter@CIsoBurnUI@@CAJGPEAGI@Z`
- size: `256`
- prototype: `static int(unsigned __int16, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000aac0`

## callees

- `0x140001fa0`
- `0x14000b8c0`
- `0x14000baa0`
- `0x14000bd48`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000be18`
- `ADVAPI32!RegCloseKey` at `0x14000be18`
- `ADVAPI32!RegOpenKeyExW` at `0x14000bdb0`
- `ADVAPI32!RegOpenKeyExW` at `0x14000bdb0`
- `ADVAPI32!RegEnumKeyW` at `0x14000be04`
- `ADVAPI32!RegEnumKeyW` at `0x14000be04`

## pseudocode

```c
__int64 __fastcall CIsoBurnUI::_GetVolumeNameForDriveLetter(__int16 a1, unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  DWORD v5; // ebp
  DWORD i; // edx
  unsigned int v7; // r8d
  unsigned __int16 v9; // [rsp+30h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF

  *a2 = 0;
  v4 = -2147467259;
  if ( a1 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\CD Burning\\Drives",
            0,
            0x20019u,
            &hKey) )
    {
      v5 = 0;
      for ( i = 0; !RegEnumKeyW(hKey, i, Name, 0x104u); i = v5 )
      {
        CIsoBurnUI::_ConstructVolumeNameFromKey(Name, a2, v7);
        v9 = 0;
        CIsoBurnUI::_GetDriveLetterForVolumeName(a2, &v9);
        if ( v9 && v9 == a1 )
        {
          v4 = 0;
          break;
        }
        ++v5;
      }
      RegCloseKey(hKey);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14000bd48  mov     [rsp+arg_0], rbx
0x14000bd4d  mov     [rsp+arg_10], rbp
0x14000bd52  push    rsi
0x14000bd53  push    rdi
0x14000bd54  push    r14
0x14000bd56  sub     rsp, 260h
0x14000bd5d  mov     rax, cs:__security_cookie
0x14000bd64  xor     rax, rsp
0x14000bd67  mov     [rsp+278h+var_28], rax
0x14000bd6f  xor     r14d, r14d
0x14000bd72  mov     rsi, rdx
0x14000bd75  mov     [rdx], r14w
0x14000bd79  movzx   edi, cx
0x14000bd7c  mov     ebx, 80004005h
0x14000bd81  test    cx, cx
0x14000bd84  jz      loc_14000BE1E
0x14000bd8a  lea     rax, [rsp+278h+hKey]
0x14000bd8f  mov     [rsp+278h+hKey], r14
0x14000bd94  mov     r9d, 20019h; samDesired
0x14000bd9a  mov     [rsp+278h+phkResult], rax; phkResult
0x14000bd9f  xor     r8d, r8d; ulOptions
0x14000bda2  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000bda9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000bdb0  call    cs:__imp_RegOpenKeyExW
0x14000bdb6  test    eax, eax
0x14000bdb8  jnz     short loc_14000BE1E
0x14000bdba  mov     ebp, r14d
0x14000bdbd  xor     edx, edx
0x14000bdbf  jmp     short loc_14000BDF4
0x14000bdc1  mov     rdx, rsi; unsigned __int16 *
0x14000bdc4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000bdc9  call    ?_ConstructVolumeNameFromKey@CIsoBurnUI@@CAJPEBGPEAGI@Z; CIsoBurnUI::_ConstructVolumeNameFromKey(ushort const *,ushort *,uint)
0x14000bdce  lea     rdx, [rsp+278h+var_248]; unsigned __int16 *
0x14000bdd3  mov     [rsp+278h+var_248], r14w
0x14000bdd9  mov     rcx, rsi; lpszVolumeName
0x14000bddc  call    ?_GetDriveLetterForVolumeName@CIsoBurnUI@@CAJPEBGPEAG@Z; CIsoBurnUI::_GetDriveLetterForVolumeName(ushort const *,ushort *)
0x14000bde1  movzx   eax, [rsp+278h+var_248]
0x14000bde6  test    ax, ax
0x14000bde9  jz      short loc_14000BDF0
0x14000bdeb  cmp     ax, di
0x14000bdee  jz      short loc_14000BE10
0x14000bdf0  inc     ebp
0x14000bdf2  mov     edx, ebp; dwIndex
0x14000bdf4  mov     rcx, [rsp+278h+hKey]; hKey
0x14000bdf9  lea     r8, [rsp+278h+Name]; lpName
0x14000bdfe  mov     r9d, 104h; cchName
0x14000be04  call    cs:__imp_RegEnumKeyW
0x14000be0a  test    eax, eax
0x14000be0c  jz      short loc_14000BDC1
0x14000be0e  jmp     short loc_14000BE13
0x14000be10  mov     ebx, r14d
0x14000be13  mov     rcx, [rsp+278h+hKey]; hKey
0x14000be18  call    cs:__imp_RegCloseKey
0x14000be1e  mov     eax, ebx
0x14000be20  mov     rcx, [rsp+278h+var_28]
0x14000be28  xor     rcx, rsp; StackCookie
0x14000be2b  call    __security_check_cookie
0x14000be30  lea     r11, [rsp+278h+var_18]
0x14000be38  mov     rbx, [r11+20h]
0x14000be3c  mov     rbp, [r11+30h]
0x14000be40  mov     rsp, r11
0x14000be43  pop     r14
0x14000be45  pop     rdi
0x14000be46  pop     rsi
0x14000be47  retn
```
