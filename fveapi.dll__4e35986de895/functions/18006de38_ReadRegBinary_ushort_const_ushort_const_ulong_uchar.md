# ReadRegBinary(ushort const *,ushort const *,ulong,uchar *)

- ea: `0x18006de38`
- end: `0x18006df21`
- name: `?ReadRegBinary@@YAJPEBG0KPEAE@Z`
- size: `233`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180075d90`

## callees

- `0x18006de38`
- `0x18006df28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006df04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006df04`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006deda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006deda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006de8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006de8f`

## pseudocode

```c
__int64 __fastcall ReadRegBinary(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int8 *a4)
{
  int v5; // edi
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  bool v8; // cc
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  int v12; // [rsp+6Ch] [rbp+14h]
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF

  v12 = HIDWORD(a2);
  Type = 0;
  v5 = 0;
  hKey = 0;
  cbData = 520;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Session Manager\\Memory Management",
         0,
         0x20019u,
         &hKey);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 || (v5 = 1, v6 = RegQueryValueExW(hKey, L"PagingFiles", 0, &Type, a4, &cbData), v7 = v6, v8 = v6 <= 0, v6) )
  {
    if ( !v8 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    v7 = 0;
    if ( Type != 3 )
      v7 = -2147024883;
  }
  if ( v5 )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18006de38  mov     rax, rsp
0x18006de3b  mov     [rax+20h], rbx
0x18006de3f  mov     [rax+18h], r8d
0x18006de43  mov     [rax+10h], rdx
0x18006de47  mov     [rax+8], rcx
0x18006de4b  push    rsi
0x18006de4c  push    rdi
0x18006de4d  push    r14
0x18006de4f  sub     rsp, 40h
0x18006de53  mov     r14, r9
0x18006de56  mov     dword ptr [rax+18h], 0
0x18006de5d  xor     edi, edi
0x18006de5f  mov     [rax-28h], edi
0x18006de62  mov     [rax+8], rdi
0x18006de66  xor     esi, esi
0x18006de68  mov     dword ptr [rax+10h], 208h
0x18006de6f  lea     rax, [rax+8]
0x18006de73  mov     [rsp+58h+phkResult], rax; phkResult
0x18006de78  mov     r9d, 20019h; samDesired
0x18006de7e  xor     r8d, r8d; ulOptions
0x18006de81  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Ses"...
0x18006de88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006de8f  call    cs:__imp_RegOpenKeyExW
0x18006de96  nop     dword ptr [rax+rax+00h]
0x18006de9b  mov     ebx, eax
0x18006de9d  test    eax, eax
0x18006de9f  jz      short loc_18006DEAE
0x18006dea1  jle     short loc_18006DEFB
0x18006dea3  movzx   ebx, ax
0x18006dea6  or      ebx, 80070000h
0x18006deac  jmp     short loc_18006DEFB
0x18006deae  mov     edi, 1
0x18006deb3  mov     [rsp+58h+var_28], edi
0x18006deb7  lea     rax, [rsp+58h+cbData]
0x18006debc  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18006dec1  mov     [rsp+58h+phkResult], r14; lpData
0x18006dec6  lea     r9, [rsp+58h+Type]; lpType
0x18006decb  xor     r8d, r8d; lpReserved
0x18006dece  lea     rdx, aPagingfiles; "PagingFiles"
0x18006ded5  mov     rcx, [rsp+58h+hKey]; hKey
0x18006deda  call    cs:__imp_RegQueryValueExW
0x18006dee1  nop     dword ptr [rax+rax+00h]
0x18006dee6  mov     ebx, eax
0x18006dee8  test    eax, eax
0x18006deea  jnz     short loc_18006DEA1
0x18006deec  mov     ebx, esi
0x18006deee  mov     eax, 8007000Dh
0x18006def3  cmp     [rsp+58h+Type], 3
0x18006def8  cmovnz  ebx, eax
0x18006defb  test    edi, edi
0x18006defd  jz      short loc_18006DF10
0x18006deff  mov     rcx, [rsp+58h+hKey]; hKey
0x18006df04  call    cs:__imp_RegCloseKey
0x18006df0b  nop     dword ptr [rax+rax+00h]
0x18006df10  mov     eax, ebx
0x18006df12  mov     rbx, [rsp+58h+arg_18]
0x18006df17  add     rsp, 40h
0x18006df1b  pop     r14
0x18006df1d  pop     rdi
0x18006df1e  pop     rsi
0x18006df1f  retn
0x18012276f  push    rbp
0x180122771  sub     rsp, 30h
0x180122775  mov     rbp, rdx
0x180122778  cmp     dword ptr [rbp+30h], 0
0x18012277c  jz      short loc_18012278F
0x18012277e  mov     rcx, [rbp+60h]; hKey
0x180122782  call    cs:__imp_RegCloseKey
0x180122789  nop     dword ptr [rax+rax+00h]
0x18012278e  nop
0x18012278f  add     rsp, 30h
0x180122793  pop     rbp
0x180122794  retn
```
