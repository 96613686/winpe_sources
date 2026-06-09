# DCGetReadonlyHKey

- ea: `0x1400576f0`
- end: `0x140057781`
- name: `DCGetReadonlyHKey`
- size: `145`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140056b74`
- `0x1400585f0`

## callees

- `0x1400576f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005772d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005772d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057767`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057767`

## pseudocode

```c
__int64 __fastcall DCGetReadonlyHKey(LPCWSTR lpSubKey, _QWORD *a2)
{
  HKEY v4; // rcx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  HKEY v8; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  v8 = 0;
  if ( lpSubKey && a2 )
  {
    *a2 = 0;
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &v8);
    v6 = v5;
    if ( !v5 )
    {
      v6 = 0;
      *a2 = v8;
      return v6;
    }
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v4 = v8;
  }
  else
  {
    v6 = -2147024809;
  }
  if ( v4 )
    RegCloseKey(v4);
  return v6;
}

```

## disassembly

```asm
0x1400576f0  mov     r11, rsp
0x1400576f3  mov     [r11+10h], rbx
0x1400576f7  push    rdi
0x1400576f8  sub     rsp, 30h
0x1400576fc  mov     rdi, rdx
0x1400576ff  mov     rdx, rcx; lpSubKey
0x140057702  xor     ecx, ecx; hKey
0x140057704  mov     [r11+8], rcx
0x140057708  test    rdx, rdx
0x14005770b  jz      short loc_14005775D
0x14005770d  test    rdi, rdi
0x140057710  jz      short loc_14005775D
0x140057712  mov     [rdi], rcx
0x140057715  lea     rax, [r11+8]
0x140057719  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140057720  mov     [r11-18h], rax
0x140057724  mov     r9d, 20119h; samDesired
0x14005772a  xor     r8d, r8d; ulOptions
0x14005772d  call    cs:__imp_RegOpenKeyExW
0x140057734  nop     dword ptr [rax+rax+00h]
0x140057739  mov     ebx, eax
0x14005773b  test    eax, eax
0x14005773d  jz      short loc_140057751
0x14005773f  jle     short loc_14005774A
0x140057741  movzx   ebx, ax
0x140057744  or      ebx, 80070000h
0x14005774a  mov     rcx, [rsp+38h+arg_0]
0x14005774f  jmp     short loc_140057762
0x140057751  mov     rax, [rsp+38h+arg_0]
0x140057756  xor     ebx, ebx
0x140057758  mov     [rdi], rax
0x14005775b  jmp     short loc_140057773
0x14005775d  mov     ebx, 80070057h
0x140057762  test    rcx, rcx
0x140057765  jz      short loc_140057773
0x140057767  call    cs:__imp_RegCloseKey
0x14005776e  nop     dword ptr [rax+rax+00h]
0x140057773  mov     eax, ebx
0x140057775  mov     rbx, [rsp+38h+arg_8]
0x14005777a  add     rsp, 30h
0x14005777e  pop     rdi
0x14005777f  retn
```
