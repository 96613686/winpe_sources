# OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)

- ea: `0x1400594a4`
- end: `0x140059544`
- name: `?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z`
- size: `160`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, __int64, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140057dd0`

## callees

- `0x140002070`
- `0x140002c68`
- `0x140057bd0`
- `0x1400594a4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140059508`
- `ADVAPI32!RegOpenKeyExW` at `0x140059508`

## pseudocode

```c
__int64 __fastcall OpenConnectionRegistryKey(STRSAFE_LPCWSTR pszSrc, __int64 a2, __int64 a3, HKEY *a4)
{
  unsigned int v6; // r8d
  int v7; // ebx
  LSTATUS v8; // eax
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  v7 = AssembleRegistrySubkey(pszSrc, SubKey, v6);
  if ( v7 >= 0 )
  {
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, a4);
    if ( v8 )
    {
      if ( v8 > 0 )
        return (unsigned __int16)v8 | 0x80070000;
      else
        return (unsigned int)v8;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400594a4  mov     [rsp+arg_8], rbx
0x1400594a9  push    rdi
0x1400594aa  sub     rsp, 250h
0x1400594b1  mov     rax, cs:__security_cookie
0x1400594b8  xor     rax, rsp
0x1400594bb  mov     [rsp+258h+var_18], rax
0x1400594c3  mov     rbx, rcx
0x1400594c6  xor     edx, edx; Val
0x1400594c8  lea     rcx, [rsp+258h+SubKey]; void *
0x1400594cd  mov     r8d, 208h; Size
0x1400594d3  mov     rdi, r9
0x1400594d6  call    memset_0
0x1400594db  lea     rdx, [rsp+258h+SubKey]; wchar_t *
0x1400594e0  mov     rcx, rbx; pszSrc
0x1400594e3  call    ?AssembleRegistrySubkey@@YAJPEBGPEAGK@Z; AssembleRegistrySubkey(ushort const *,ushort *,ulong)
0x1400594e8  mov     ebx, eax
0x1400594ea  test    eax, eax
0x1400594ec  js      short loc_140059521
0x1400594ee  mov     r9d, 20019h; samDesired
0x1400594f4  mov     [rsp+258h+phkResult], rdi; phkResult
0x1400594f9  xor     r8d, r8d; ulOptions
0x1400594fc  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x140059501  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140059508  call    cs:__imp_RegOpenKeyExW
0x14005950e  test    eax, eax
0x140059510  jz      short loc_140059521
0x140059512  jg      short loc_140059518
0x140059514  mov     ebx, eax
0x140059516  jmp     short loc_140059521
0x140059518  movzx   ebx, ax
0x14005951b  or      ebx, 80070000h
0x140059521  mov     eax, ebx
0x140059523  mov     rcx, [rsp+258h+var_18]
0x14005952b  xor     rcx, rsp; StackCookie
0x14005952e  call    __security_check_cookie
0x140059533  mov     rbx, [rsp+258h+arg_8]
0x14005953b  add     rsp, 250h
0x140059542  pop     rdi
0x140059543  retn
```
