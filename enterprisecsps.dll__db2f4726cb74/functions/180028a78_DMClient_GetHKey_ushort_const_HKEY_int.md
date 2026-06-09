# DMClient::GetHKey(ushort const *,HKEY__ * *,int)

- ea: `0x180028a78`
- end: `0x180028b57`
- name: `?GetHKey@DMClient@@YAJPEBGPEAPEAUHKEY__@@H@Z`
- size: `223`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, HKEY *, int)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800260dc`
- `0x180026f80`
- `0x1800270d0`
- `0x18002722c`
- `0x1800274f8`
- `0x18002760c`
- `0x18002838c`
- `0x180028488`
- `0x1800285b4`
- `0x18002985c`
- `0x180029998`
- `0x180029b30`

## callees

- `0x180028a78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b3d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028adb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028adb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028b03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028b03`

## pseudocode

```c
__int64 __fastcall DMClient::GetHKey(LPCWSTR lpSubKey, unsigned __int16 *a2, HKEY *a3)
{
  HKEY v5; // rcx
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  DWORD v9; // [rsp+60h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  v5 = 0;
  phkResult = 0;
  if ( lpSubKey && a2 )
  {
    *(_QWORD *)a2 = 0;
    if ( (_DWORD)a3 )
    {
      v9 = 0;
      v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, &v9);
    }
    else
    {
      v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &phkResult);
    }
    v7 = v6;
    if ( !v6 )
    {
      v7 = 0;
      *(_QWORD *)a2 = phkResult;
      return v7;
    }
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v5 = phkResult;
  }
  else
  {
    v7 = -2147024809;
  }
  if ( v5 )
    RegCloseKey(v5);
  return v7;
}

```

## disassembly

```asm
0x180028a78  mov     r11, rsp
0x180028a7b  mov     [r11+10h], rbx
0x180028a7f  push    rdi
0x180028a80  sub     rsp, 50h
0x180028a84  mov     rdi, rdx
0x180028a87  mov     rdx, rcx; lpSubKey
0x180028a8a  xor     ecx, ecx; hKey
0x180028a8c  mov     [r11+20h], rcx
0x180028a90  test    rdx, rdx
0x180028a93  jz      loc_180028B33
0x180028a99  test    rdi, rdi
0x180028a9c  jz      loc_180028B33
0x180028aa2  mov     [rdi], rcx
0x180028aa5  test    r8d, r8d
0x180028aa8  jz      short loc_180028AE9
0x180028aaa  lea     rax, [r11+8]
0x180028aae  mov     [rsp+58h+arg_0], ecx
0x180028ab2  mov     [r11-18h], rax
0x180028ab6  xor     r9d, r9d; lpClass
0x180028ab9  lea     rax, [r11+20h]
0x180028abd  xor     r8d, r8d; Reserved
0x180028ac0  mov     [r11-20h], rax
0x180028ac4  mov     [r11-28h], rcx
0x180028ac8  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180028ad0  mov     [rsp+58h+dwOptions], ecx; dwOptions
0x180028ad4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028adb  call    cs:__imp_RegCreateKeyExW
0x180028ae2  nop     dword ptr [rax+rax+00h]
0x180028ae7  jmp     short loc_180028B0F
0x180028ae9  lea     rax, [rsp+58h+phkResult]
0x180028aee  mov     r9d, 20019h; samDesired
0x180028af4  xor     r8d, r8d; ulOptions
0x180028af7  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x180028afc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028b03  call    cs:__imp_RegOpenKeyExW
0x180028b0a  nop     dword ptr [rax+rax+00h]
0x180028b0f  mov     ebx, eax
0x180028b11  test    eax, eax
0x180028b13  jz      short loc_180028B27
0x180028b15  jle     short loc_180028B20
0x180028b17  movzx   ebx, bx
0x180028b1a  or      ebx, 80070000h
0x180028b20  mov     rcx, [rsp+58h+phkResult]
0x180028b25  jmp     short loc_180028B38
0x180028b27  mov     rax, [rsp+58h+phkResult]
0x180028b2c  xor     ebx, ebx
0x180028b2e  mov     [rdi], rax
0x180028b31  jmp     short loc_180028B49
0x180028b33  mov     ebx, 80070057h
0x180028b38  test    rcx, rcx
0x180028b3b  jz      short loc_180028B49
0x180028b3d  call    cs:__imp_RegCloseKey
0x180028b44  nop     dword ptr [rax+rax+00h]
0x180028b49  mov     eax, ebx
0x180028b4b  mov     rbx, [rsp+58h+arg_8]
0x180028b50  add     rsp, 50h
0x180028b54  pop     rdi
0x180028b55  retn
```
