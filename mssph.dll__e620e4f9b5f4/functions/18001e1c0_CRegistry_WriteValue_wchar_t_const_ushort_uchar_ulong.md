# CRegistry::WriteValue(wchar_t const *,ushort,uchar *,ulong)

- ea: `0x18001e1c0`
- end: `0x18001e229`
- name: `?WriteValue@CRegistry@@UEAAHPEB_WGPEAEK@Z`
- size: `105`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, unsigned __int16, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18001d17c`
- `0x18001e1c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e1dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e218`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e1dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e218`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e208`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e208`

## pseudocode

```c
__int64 __fastcall CRegistry::WriteValue(
        CRegistry *this,
        const wchar_t *a2,
        unsigned __int16 a3,
        unsigned __int8 *a4,
        DWORD cbData)
{
  DWORD v6; // ecx
  DWORD v8; // eax
  HKEY v9; // r10
  const BYTE *lpData; // r11
  LSTATUS v11; // eax

  if ( !*((_QWORD *)this + 22) )
  {
    v6 = 6;
LABEL_3:
    SetLastError(v6);
    return 0;
  }
  v8 = ConvertDBTYPEToREGTYPE(a3);
  v11 = RegSetValueExW(v9, a2, 0, v8, lpData, cbData);
  if ( v11 )
  {
    v6 = v11;
    goto LABEL_3;
  }
  SetLastError(0);
  return 1;
}

```

## disassembly

```asm
0x18001e1c0  push    rbx
0x18001e1c2  sub     rsp, 30h
0x18001e1c6  mov     r10, [rcx+0B0h]
0x18001e1cd  mov     r11, r9
0x18001e1d0  mov     rbx, rdx
0x18001e1d3  test    r10, r10
0x18001e1d6  jnz     short loc_18001E1E6
0x18001e1d8  lea     ecx, [r10+6]; dwErrCode
0x18001e1dc  call    cs:__imp_SetLastError
0x18001e1e2  xor     eax, eax
0x18001e1e4  jmp     short loc_18001E223
0x18001e1e6  movzx   ecx, r8w; unsigned __int16
0x18001e1ea  call    ?ConvertDBTYPEToREGTYPE@@YAKG@Z; ConvertDBTYPEToREGTYPE(ushort)
0x18001e1ef  mov     r9d, eax; dwType
0x18001e1f2  xor     r8d, r8d; Reserved
0x18001e1f5  mov     eax, [rsp+38h+arg_20]
0x18001e1f9  mov     rdx, rbx; lpValueName
0x18001e1fc  mov     [rsp+38h+cbData], eax; cbData
0x18001e200  mov     rcx, r10; hKey
0x18001e203  mov     [rsp+38h+lpData], r11; lpData
0x18001e208  call    cs:__imp_RegSetValueExW
0x18001e20e  test    eax, eax
0x18001e210  jz      short loc_18001E216
0x18001e212  mov     ecx, eax
0x18001e214  jmp     short loc_18001E1DC
0x18001e216  xor     ecx, ecx; dwErrCode
0x18001e218  call    cs:__imp_SetLastError
0x18001e21e  mov     eax, 1
0x18001e223  add     rsp, 30h
0x18001e227  pop     rbx
0x18001e228  retn
```
