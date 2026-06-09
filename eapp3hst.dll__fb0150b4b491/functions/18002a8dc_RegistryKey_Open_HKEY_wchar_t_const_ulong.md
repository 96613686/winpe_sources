# RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x18002a8dc`
- end: `0x18002a96c`
- name: `?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800213a8`
- `0x1800247e0`
- `0x18002990c`
- `0x18002b8dc`
- `0x18002ca50`
- `0x18002d040`

## callees

- `0x180012a70`
- `0x18002a7dc`
- `0x18002a8dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a916`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a916`

## string_xrefs

- `0x18002a933`: `RegOpenKeyEx`

## pseudocode

```c
__int64 __fastcall RegistryKey::Open(__int64 a1, HKEY a2, const WCHAR *a3, int a4)
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
    RegistryKey::Clear((HKEY *)a1);
    result = 0;
    *(_QWORD *)a1 = v8;
    *(_DWORD *)(a1 + 8) = a4;
  }
  return result;
}

```

## disassembly

```asm
0x18002a8dc  mov     r11, rsp
0x18002a8df  mov     [r11+8], rbx
0x18002a8e3  mov     [r11+10h], rsi
0x18002a8e7  push    rdi
0x18002a8e8  sub     rsp, 40h
0x18002a8ec  mov     rdi, rcx
0x18002a8ef  mov     qword ptr [r11-18h], 0
0x18002a8f7  lea     rcx, [r11-18h]
0x18002a8fb  mov     rax, r8
0x18002a8fe  mov     r10, rdx
0x18002a901  mov     [r11-28h], rcx
0x18002a905  mov     esi, r9d
0x18002a908  mov     rcx, r10; hKey
0x18002a90b  bts     r9d, 8; samDesired
0x18002a910  xor     r8d, r8d; ulOptions
0x18002a913  mov     rdx, rax; lpSubKey
0x18002a916  call    cs:__imp_RegOpenKeyExW
0x18002a91c  test    eax, eax
0x18002a91e  jz      short loc_18002A947
0x18002a920  cmp     eax, 2
0x18002a923  jz      short loc_18002A940
0x18002a925  test    eax, eax
0x18002a927  jle     short loc_18002A931
0x18002a929  movzx   eax, ax
0x18002a92c  or      eax, 80070000h
0x18002a931  mov     edx, eax; int
0x18002a933  lea     rcx, aRegopenkeyex; "RegOpenKeyEx"
0x18002a93a  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x18002a940  mov     eax, 1
0x18002a945  jmp     short loc_18002A95C
0x18002a947  mov     rbx, [rsp+48h+var_18]
0x18002a94c  mov     rcx, rdi; this
0x18002a94f  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002a954  xor     eax, eax
0x18002a956  mov     [rdi], rbx
0x18002a959  mov     [rdi+8], esi
0x18002a95c  mov     rbx, [rsp+48h+arg_0]
0x18002a961  mov     rsi, [rsp+48h+arg_8]
0x18002a966  add     rsp, 40h
0x18002a96a  pop     rdi
0x18002a96b  retn
```
