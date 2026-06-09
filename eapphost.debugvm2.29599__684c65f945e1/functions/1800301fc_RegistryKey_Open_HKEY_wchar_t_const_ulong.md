# RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x1800301fc`
- end: `0x18003028c`
- name: `?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z`
- size: `144`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013e00`
- `0x18001926c`
- `0x180019fbc`
- `0x18001b200`
- `0x18001b7cc`

## callees

- `0x18002edf4`
- `0x1800300fc`
- `0x1800301fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030236`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030236`

## string_xrefs

- `0x180030253`: `RegOpenKeyEx`

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
0x1800301fc  mov     r11, rsp
0x1800301ff  mov     [r11+8], rbx
0x180030203  mov     [r11+10h], rsi
0x180030207  push    rdi
0x180030208  sub     rsp, 40h
0x18003020c  mov     rdi, rcx
0x18003020f  mov     qword ptr [r11-18h], 0
0x180030217  lea     rcx, [r11-18h]
0x18003021b  mov     rax, r8
0x18003021e  mov     r10, rdx
0x180030221  mov     [r11-28h], rcx
0x180030225  mov     esi, r9d
0x180030228  mov     rcx, r10; hKey
0x18003022b  bts     r9d, 8; samDesired
0x180030230  xor     r8d, r8d; ulOptions
0x180030233  mov     rdx, rax; lpSubKey
0x180030236  call    cs:__imp_RegOpenKeyExW
0x18003023c  test    eax, eax
0x18003023e  jz      short loc_180030267
0x180030240  cmp     eax, 2
0x180030243  jz      short loc_180030260
0x180030245  test    eax, eax
0x180030247  jle     short loc_180030251
0x180030249  movzx   eax, ax
0x18003024c  or      eax, 80070000h
0x180030251  mov     edx, eax; int
0x180030253  lea     rcx, aRegopenkeyex; "RegOpenKeyEx"
0x18003025a  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x180030260  mov     eax, 1
0x180030265  jmp     short loc_18003027C
0x180030267  mov     rbx, [rsp+48h+var_18]
0x18003026c  mov     rcx, rdi; this
0x18003026f  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x180030274  xor     eax, eax
0x180030276  mov     [rdi], rbx
0x180030279  mov     [rdi+8], esi
0x18003027c  mov     rbx, [rsp+48h+arg_0]
0x180030281  mov     rsi, [rsp+48h+arg_8]
0x180030286  add     rsp, 40h
0x18003028a  pop     rdi
0x18003028b  retn
```
