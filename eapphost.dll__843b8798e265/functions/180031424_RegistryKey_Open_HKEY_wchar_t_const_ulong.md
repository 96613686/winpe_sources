# RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x180031424`
- end: `0x1800314bb`
- name: `?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z`
- size: `151`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800145f0`
- `0x180019c34`
- `0x18001a99c`
- `0x18001bc10`
- `0x18001c1e4`

## callees

- `0x18002fef4`
- `0x180031314`
- `0x180031424`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003145e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003145e`

## string_xrefs

- `0x180031481`: `RegOpenKeyEx`

## pseudocode

```c
__int64 __fastcall RegistryKey::Open(RegistryKey *a1, HKEY a2, const WCHAR *a3, int a4)
{
  int v6; // eax
  __int64 result; // rax
  HKEY v8; // rbx
  HKEY v9; // [rsp+30h] [rbp-18h] BYREF

  v9 = 0;
  v6 = RegOpenKeyExW(a2, a3, 0, a4 | 0x100, &v9);
  if ( v6 )
  {
    if ( v6 != 2 )
    {
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      SystemError::ThrowHelper(L"RegOpenKeyEx", v6);
    }
    return 1;
  }
  else
  {
    v8 = v9;
    RegistryKey::Clear(a1);
    result = 0;
    *(_QWORD *)a1 = v8;
    *((_DWORD *)a1 + 2) = a4;
  }
  return result;
}

```

## disassembly

```asm
0x180031424  mov     r11, rsp
0x180031427  mov     [r11+8], rbx
0x18003142b  mov     [r11+10h], rsi
0x18003142f  push    rdi
0x180031430  sub     rsp, 40h
0x180031434  mov     rdi, rcx
0x180031437  mov     qword ptr [r11-18h], 0
0x18003143f  lea     rcx, [r11-18h]
0x180031443  mov     rax, r8
0x180031446  mov     r10, rdx
0x180031449  mov     [r11-28h], rcx
0x18003144d  mov     esi, r9d
0x180031450  mov     rcx, r10; hKey
0x180031453  bts     r9d, 8; samDesired
0x180031458  xor     r8d, r8d; ulOptions
0x18003145b  mov     rdx, rax; lpSubKey
0x18003145e  call    cs:__imp_RegOpenKeyExW
0x180031465  nop     dword ptr [rax+rax+00h]
0x18003146a  test    eax, eax
0x18003146c  jz      short loc_180031495
0x18003146e  cmp     eax, 2
0x180031471  jz      short loc_18003148E
0x180031473  test    eax, eax
0x180031475  jle     short loc_18003147F
0x180031477  movzx   eax, ax
0x18003147a  or      eax, 80070000h
0x18003147f  mov     edx, eax; int
0x180031481  lea     rcx, aRegopenkeyex; "RegOpenKeyEx"
0x180031488  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x18003148e  mov     eax, 1
0x180031493  jmp     short loc_1800314AA
0x180031495  mov     rbx, [rsp+48h+var_18]
0x18003149a  mov     rcx, rdi; this
0x18003149d  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x1800314a2  xor     eax, eax
0x1800314a4  mov     [rdi], rbx
0x1800314a7  mov     [rdi+8], esi
0x1800314aa  mov     rbx, [rsp+48h+arg_0]
0x1800314af  mov     rsi, [rsp+48h+arg_8]
0x1800314b4  add     rsp, 40h
0x1800314b8  pop     rdi
0x1800314b9  retn
```
