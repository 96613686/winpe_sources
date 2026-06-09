# CCMLuaUtil::DeleteRegistryStringValue(int,ushort const *,ushort const *)

- ea: `0x180003390`
- end: `0x18000340e`
- name: `?DeleteRegistryStringValue@CCMLuaUtil@@UEAAJHPEBG0@Z`
- size: `126`
- prototype: `__int64 __fastcall(CCMLuaUtil *this, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003390`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800033ee`
- `ADVAPI32!RegCloseKey` at `0x1800033ee`
- `ADVAPI32!RegOpenKeyExW` at `0x1800033cd`
- `ADVAPI32!RegOpenKeyExW` at `0x1800033cd`
- `ADVAPI32!RegDeleteValueW` at `0x1800033e1`
- `ADVAPI32!RegDeleteValueW` at `0x1800033e1`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::DeleteRegistryStringValue(
        CCMLuaUtil *this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  LSTATUS v5; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExW((HKEY)((a2 != 0) - 0x7FFFFFFFLL), a3, 0, 0xF003Fu, &hKey);
  if ( !v5 )
  {
    v5 = RegDeleteValueW(hKey, a4);
    RegCloseKey(hKey);
  }
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003390  mov     r11, rsp
0x180003393  mov     [r11+8], rbx
0x180003397  push    rdi
0x180003398  sub     rsp, 30h
0x18000339c  neg     edx
0x18000339e  mov     qword ptr [r11+18h], 0
0x1800033a6  lea     rdx, [r11+18h]
0x1800033aa  mov     rax, r8
0x1800033ad  sbb     rcx, rcx
0x1800033b0  mov     [r11-18h], rdx
0x1800033b4  neg     rcx
0x1800033b7  mov     rdi, r9
0x1800033ba  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800033c1  mov     r9d, 0F003Fh; samDesired
0x1800033c7  xor     r8d, r8d; ulOptions
0x1800033ca  mov     rdx, rax; lpSubKey
0x1800033cd  call    cs:__imp_RegOpenKeyExW
0x1800033d3  mov     ebx, eax
0x1800033d5  test    eax, eax
0x1800033d7  jnz     short loc_1800033F4
0x1800033d9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800033de  mov     rdx, rdi; lpValueName
0x1800033e1  call    cs:__imp_RegDeleteValueW
0x1800033e7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800033ec  mov     ebx, eax
0x1800033ee  call    cs:__imp_RegCloseKey
0x1800033f4  test    ebx, ebx
0x1800033f6  jle     short loc_180003401
0x1800033f8  movzx   ebx, bx
0x1800033fb  or      ebx, 80070000h
0x180003401  mov     eax, ebx
0x180003403  mov     rbx, [rsp+38h+arg_0]
0x180003408  add     rsp, 30h
0x18000340c  pop     rdi
0x18000340d  retn
```
