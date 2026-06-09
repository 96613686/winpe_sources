# WriteReg32Bit(ushort const *,ushort const *,ulong)

- ea: `0x18006e144`
- end: `0x18006e214`
- name: `?WriteReg32Bit@@YAJPEBG0K@Z`
- size: `208`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180075d90`

## callees

- `0x18006e144`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006e1a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006e1a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e1e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e1e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e1ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801227db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e1ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801227db`

## pseudocode

```c
__int64 __fastcall WriteReg32Bit(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  int Data; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  Data = 1;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Session Manager\\Memory Management",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2
    || (v2 = RegSetValueExW(hKey, L"PagefileOnOsVolume", 0, 4u, (const BYTE *)&Data, 4u), v3 = v2, v4 = v2 <= 0, v2) )
  {
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80070000;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18006e144  mov     r11, rsp
0x18006e147  mov     [r11+18h], r8d
0x18006e14b  mov     [r11+10h], rdx
0x18006e14f  push    rbx
0x18006e150  sub     rsp, 50h
0x18006e154  mov     qword ptr [r11+10h], 0
0x18006e15c  mov     [rsp+58h+Data], 1
0x18006e164  mov     qword ptr [r11-18h], 0
0x18006e16c  lea     rax, [r11+10h]
0x18006e170  mov     [r11-20h], rax
0x18006e174  mov     qword ptr [r11-28h], 0
0x18006e17c  mov     [rsp+58h+samDesired], 2; samDesired
0x18006e184  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18006e18c  xor     r9d, r9d; lpClass
0x18006e18f  xor     r8d, r8d; Reserved
0x18006e192  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Ses"...
0x18006e199  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e1a0  call    cs:__imp_RegCreateKeyExW
0x18006e1a7  nop     dword ptr [rax+rax+00h]
0x18006e1ac  mov     ebx, eax
0x18006e1ae  test    eax, eax
0x18006e1b0  jz      short loc_18006E1BF
0x18006e1b2  jle     short loc_18006E1F5
0x18006e1b4  movzx   ebx, ax
0x18006e1b7  or      ebx, 80070000h
0x18006e1bd  jmp     short loc_18006E1F5
0x18006e1bf  mov     r9d, 4; dwType
0x18006e1c5  mov     [rsp+58h+samDesired], r9d; cbData
0x18006e1ca  lea     rax, [rsp+58h+Data]
0x18006e1cf  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18006e1d4  xor     r8d, r8d; Reserved
0x18006e1d7  lea     rdx, aPagefileonosvo; "PagefileOnOsVolume"
0x18006e1de  mov     rcx, [rsp+58h+hKey]; hKey
0x18006e1e3  call    cs:__imp_RegSetValueExW
0x18006e1ea  nop     dword ptr [rax+rax+00h]
0x18006e1ef  mov     ebx, eax
0x18006e1f1  test    eax, eax
0x18006e1f3  jnz     short loc_18006E1B2
0x18006e1f5  mov     rcx, [rsp+58h+hKey]; hKey
0x18006e1fa  test    rcx, rcx
0x18006e1fd  jz      short loc_18006E20B
0x18006e1ff  call    cs:__imp_RegCloseKey
0x18006e206  nop     dword ptr [rax+rax+00h]
0x18006e20b  mov     eax, ebx
0x18006e20d  add     rsp, 50h
0x18006e211  pop     rbx
0x18006e212  retn
0x1801227c9  push    rbp
0x1801227cb  sub     rsp, 50h
0x1801227cf  mov     rbp, rdx
0x1801227d2  mov     rcx, [rbp+68h]; hKey
0x1801227d6  test    rcx, rcx
0x1801227d9  jz      short loc_1801227E8
0x1801227db  call    cs:__imp_RegCloseKey
0x1801227e2  nop     dword ptr [rax+rax+00h]
0x1801227e7  nop
0x1801227e8  add     rsp, 50h
0x1801227ec  pop     rbp
0x1801227ed  retn
```
