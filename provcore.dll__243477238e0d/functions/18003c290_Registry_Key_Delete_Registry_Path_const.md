# Registry::Key::Delete(Registry::Path const &)

- ea: `0x18003c290`
- end: `0x18003c2c8`
- name: `?Delete@Key@Registry@@SAJAEBVPath@2@@Z`
- size: `56`
- prototype: `__int64 __fastcall(const Registry::Path *path)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18002cf24`
- `0x18002cfb8`

## callees

- `0x180011844`
- `0x18003c290`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003c2a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003c2a6`

## pseudocode

```c
__int64 __fastcall Registry::Key::Delete(const Registry::Path *path)
{
  const WCHAR *v1; // rax
  HKEY *v2; // r8
  LSTATUS v3; // eax
  int v4; // ecx

  v1 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&path->m_path._Mypair._Myval2);
  v3 = RegDeleteTreeW(*v2, v1);
  v4 = 0;
  if ( v3 != 2 )
    v4 = v3;
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003c290  sub     rsp, 28h
0x18003c294  mov     r8, path
0x18003c297  add     path, 10h; this
0x18003c29b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c2a0  mov     path, [r8]; hKey
0x18003c2a3  mov     rdx, rax; lpSubKey
0x18003c2a6  call    cs:__imp_RegDeleteTreeW
0x18003c2ac  xor     ecx, ecx
0x18003c2ae  cmp     eax, 2
0x18003c2b1  cmovnz  ecx, eax
0x18003c2b4  test    ecx, ecx
0x18003c2b6  jle     short loc_18003C2C1
0x18003c2b8  movzx   ecx, cx
0x18003c2bb  or      ecx, 80070000h
0x18003c2c1  mov     eax, ecx
0x18003c2c3  add     rsp, 28h
0x18003c2c7  retn
```
