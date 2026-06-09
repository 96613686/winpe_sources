# ReadRegMultiString(ushort const *,ushort const *,ulong,ushort *)

- ea: `0x18006df28`
- end: `0x18006e038`
- name: `?ReadRegMultiString@@YAJPEBG0KPEAG@Z`
- size: `272`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180075d90`

## callees

- `0x18006df28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e014`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180122782`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e014`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180122782`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006dfd2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006dfd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006df7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006df7d`

## pseudocode

```c
__int64 __fastcall ReadRegMultiString(const unsigned __int16 *a1, const unsigned __int16 *a2, __int64 a3, BYTE *a4)
{
  int v5; // esi
  __int64 v6; // rdi
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  bool v9; // cc
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  DWORD Type; // [rsp+68h] [rbp+10h] BYREF
  int v13; // [rsp+6Ch] [rbp+14h]
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF

  v13 = HIDWORD(a2);
  Type = 0;
  v5 = 0;
  cbData = 0;
  hKey = 0;
  v6 = 0;
  v7 = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Session Manager\\Memory Management",
         0,
         0x20019u,
         &hKey);
  v9 = v8 <= 0;
  if ( v8
    || (v5 = 1, cbData = 520, v8 = RegQueryValueExW(hKey, L"PagingFiles", 0, &Type, a4, &cbData), v9 = v8 <= 0, v8) )
  {
    if ( v9 )
      v7 = v8;
    else
      v7 = (unsigned __int16)v8 | 0x80070000;
  }
  else if ( Type == 7 && cbData >= 2 )
  {
    v6 = cbData >> 1;
    if ( (unsigned int)v6 >= 0x104 )
      v6 = 259;
  }
  else
  {
    v7 = -2147024883;
  }
  if ( v5 )
    RegCloseKey(hKey);
  *(_WORD *)&a4[2 * v6] = 0;
  return v7;
}

```

## disassembly

```asm
0x18006df28  mov     rax, rsp
0x18006df2b  mov     [rax+20h], rbx
0x18006df2f  mov     [rax+18h], r8d
0x18006df33  mov     [rax+10h], rdx
0x18006df37  mov     [rax+8], rcx
0x18006df3b  push    rsi
0x18006df3c  push    rdi
0x18006df3d  push    r14
0x18006df3f  sub     rsp, 40h
0x18006df43  mov     r14, r9
0x18006df46  mov     dword ptr [rax+10h], 0
0x18006df4d  xor     esi, esi
0x18006df4f  mov     [rax-28h], esi
0x18006df52  mov     [rax+18h], esi
0x18006df55  mov     [rax+8], rsi
0x18006df59  xor     edi, edi
0x18006df5b  xor     ebx, ebx
0x18006df5d  lea     rax, [rax+8]
0x18006df61  mov     [rsp+58h+phkResult], rax; phkResult
0x18006df66  mov     r9d, 20019h; samDesired
0x18006df6c  xor     r8d, r8d; ulOptions
0x18006df6f  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Ses"...
0x18006df76  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006df7d  call    cs:__imp_RegOpenKeyExW
0x18006df84  nop     dword ptr [rax+rax+00h]
0x18006df89  test    eax, eax
0x18006df8b  jz      short loc_18006DF9E
0x18006df8d  jg      short loc_18006DF93
0x18006df8f  mov     ebx, eax
0x18006df91  jmp     short loc_18006E00B
0x18006df93  movzx   ebx, ax
0x18006df96  or      ebx, 80070000h
0x18006df9c  jmp     short loc_18006E00B
0x18006df9e  mov     esi, 1
0x18006dfa3  mov     [rsp+58h+var_28], esi
0x18006dfa7  mov     [rsp+58h+cbData], 208h
0x18006dfaf  lea     rax, [rsp+58h+cbData]
0x18006dfb4  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18006dfb9  mov     [rsp+58h+phkResult], r14; lpData
0x18006dfbe  lea     r9, [rsp+58h+Type]; lpType
0x18006dfc3  xor     r8d, r8d; lpReserved
0x18006dfc6  lea     rdx, aPagingfiles; "PagingFiles"
0x18006dfcd  mov     rcx, [rsp+58h+hKey]; hKey
0x18006dfd2  call    cs:__imp_RegQueryValueExW
0x18006dfd9  nop     dword ptr [rax+rax+00h]
0x18006dfde  test    eax, eax
0x18006dfe0  jnz     short loc_18006DF8D
0x18006dfe2  cmp     [rsp+58h+Type], 7
0x18006dfe7  jnz     short loc_18006E006
0x18006dfe9  cmp     [rsp+58h+cbData], 2
0x18006dfee  jb      short loc_18006E006
0x18006dff0  mov     edi, [rsp+58h+cbData]
0x18006dff4  shr     edi, 1
0x18006dff6  mov     eax, 103h
0x18006dffb  cmp     edi, 104h
0x18006e001  cmovnb  edi, eax
0x18006e004  jmp     short loc_18006E00B
0x18006e006  mov     ebx, 8007000Dh
0x18006e00b  test    esi, esi
0x18006e00d  jz      short loc_18006E020
0x18006e00f  mov     rcx, [rsp+58h+hKey]; hKey
0x18006e014  call    cs:__imp_RegCloseKey
0x18006e01b  nop     dword ptr [rax+rax+00h]
0x18006e020  xor     ecx, ecx
0x18006e022  mov     [r14+rdi*2], cx
0x18006e027  mov     eax, ebx
0x18006e029  mov     rbx, [rsp+58h+arg_18]
0x18006e02e  add     rsp, 40h
0x18006e032  pop     r14
0x18006e034  pop     rdi
0x18006e035  pop     rsi
0x18006e036  retn
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
