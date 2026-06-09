# CRegistry::WriteValue(wchar_t const *,ushort,uchar *,ulong)

- ea: `0x180036b70`
- end: `0x180036bd9`
- name: `?WriteValue@CRegistry@@UEAAHPEB_WGPEAEK@Z`
- size: `105`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, unsigned __int16, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180036060`
- `0x180036b70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036b8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036bc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036b8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036bc8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036bb8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036bb8`

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
0x180036b70  push    rbx
0x180036b72  sub     rsp, 30h
0x180036b76  mov     r10, [rcx+0B0h]
0x180036b7d  mov     r11, r9
0x180036b80  mov     rbx, rdx
0x180036b83  test    r10, r10
0x180036b86  jnz     short loc_180036B96
0x180036b88  lea     ecx, [r10+6]; dwErrCode
0x180036b8c  call    cs:__imp_SetLastError
0x180036b92  xor     eax, eax
0x180036b94  jmp     short loc_180036BD3
0x180036b96  movzx   ecx, r8w; unsigned __int16
0x180036b9a  call    ?ConvertDBTYPEToREGTYPE@@YAKG@Z; ConvertDBTYPEToREGTYPE(ushort)
0x180036b9f  mov     r9d, eax; dwType
0x180036ba2  xor     r8d, r8d; Reserved
0x180036ba5  mov     eax, [rsp+38h+arg_20]
0x180036ba9  mov     rdx, rbx; lpValueName
0x180036bac  mov     [rsp+38h+cbData], eax; cbData
0x180036bb0  mov     rcx, r10; hKey
0x180036bb3  mov     [rsp+38h+lpData], r11; lpData
0x180036bb8  call    cs:__imp_RegSetValueExW
0x180036bbe  test    eax, eax
0x180036bc0  jz      short loc_180036BC6
0x180036bc2  mov     ecx, eax
0x180036bc4  jmp     short loc_180036B8C
0x180036bc6  xor     ecx, ecx; dwErrCode
0x180036bc8  call    cs:__imp_SetLastError
0x180036bce  mov     eax, 1
0x180036bd3  add     rsp, 30h
0x180036bd7  pop     rbx
0x180036bd8  retn
```
