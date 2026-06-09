# RemoveUserStateSetting(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180028af8`
- end: `0x180028baf`
- name: `?RemoveUserStateSetting@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `183`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a084`

## callees

- `0x18000f5cc`
- `0x180028af8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180028b54`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180028b54`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028b39`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028b39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028b25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028b25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b46`

## pseudocode

```c
__int64 __fastcall RemoveUserStateSetting(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  LSTATUS v4; // edi
  int v5; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( a3 )
  {
    hKey = 0;
    v4 = RegOpenKeyExW(a1, a2, 0, 2u, &hKey);
    if ( !v4 )
    {
      v4 = RegDeleteValueW(hKey, a3);
      RegCloseKey(hKey);
    }
  }
  else
  {
    v4 = RegDeleteKeyExW(a1, a2, 0, 0);
  }
  v5 = 0;
  if ( v4 != 2 )
    v5 = v4;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      34,
      WPP_313c576492293c0704086ae70e07ed75_Traceguids,
      (unsigned int)v5);
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028af8  mov     r11, rsp
0x180028afb  mov     [r11+8], rbx
0x180028aff  push    rdi
0x180028b00  sub     rsp, 30h
0x180028b04  mov     rbx, r8
0x180028b07  test    r8, r8
0x180028b0a  jz      short loc_180028B4E
0x180028b0c  lea     rax, [r11+18h]
0x180028b10  mov     qword ptr [r11+18h], 0
0x180028b18  mov     r9d, 2; samDesired
0x180028b1e  mov     [r11-18h], rax
0x180028b22  xor     r8d, r8d; ulOptions
0x180028b25  call    cs:__imp_RegOpenKeyExW
0x180028b2b  mov     edi, eax
0x180028b2d  test    eax, eax
0x180028b2f  jnz     short loc_180028B5C
0x180028b31  mov     rcx, [rsp+38h+hKey]; hKey
0x180028b36  mov     rdx, rbx; lpValueName
0x180028b39  call    cs:__imp_RegDeleteValueW
0x180028b3f  mov     rcx, [rsp+38h+hKey]; hKey
0x180028b44  mov     edi, eax
0x180028b46  call    cs:__imp_RegCloseKey
0x180028b4c  jmp     short loc_180028B5C
0x180028b4e  xor     r9d, r9d; Reserved
0x180028b51  xor     r8d, r8d; samDesired
0x180028b54  call    cs:__imp_RegDeleteKeyExW
0x180028b5a  mov     edi, eax
0x180028b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b63  lea     rax, WPP_GLOBAL_Control
0x180028b6a  xor     ebx, ebx
0x180028b6c  cmp     edi, 2
0x180028b6f  cmovnz  ebx, edi
0x180028b72  cmp     rcx, rax
0x180028b75  jz      short loc_180028B95
0x180028b77  test    byte ptr [rcx+1Ch], 2
0x180028b7b  jz      short loc_180028B95
0x180028b7d  mov     rcx, [rcx+10h]
0x180028b81  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180028b88  mov     edx, 22h ; '"'
0x180028b8d  mov     r9d, ebx
0x180028b90  call    WPP_SF_d
0x180028b95  test    ebx, ebx
0x180028b97  jle     short loc_180028BA2
0x180028b99  movzx   ebx, bx
0x180028b9c  or      ebx, 80070000h
0x180028ba2  mov     eax, ebx
0x180028ba4  mov     rbx, [rsp+38h+arg_0]
0x180028ba9  add     rsp, 30h
0x180028bad  pop     rdi
0x180028bae  retn
```
