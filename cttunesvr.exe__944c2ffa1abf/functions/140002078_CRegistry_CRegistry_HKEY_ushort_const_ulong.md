# CRegistry::CRegistry(HKEY__ *,ushort const *,ulong)

- ea: `0x140002078`
- end: `0x14000214d`
- name: `??0CRegistry@@QEAA@PEAUHKEY__@@PEBGK@Z`
- size: `213`
- prototype: `CRegistry *__fastcall(CRegistry *this, HKEY, const unsigned __int16 *, REGSAM samDesired)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004c30`
- `0x140004d20`
- `0x140004dd0`

## callees

- `0x140002078`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000212d`
- `ADVAPI32!RegCloseKey` at `0x14000212d`
- `ADVAPI32!RegCreateKeyExW` at `0x1400020e0`
- `ADVAPI32!RegCreateKeyExW` at `0x140002120`
- `ADVAPI32!RegCreateKeyExW` at `0x1400020e0`
- `ADVAPI32!RegCreateKeyExW` at `0x140002120`

## pseudocode

```c
CRegistry *__fastcall CRegistry::CRegistry(CRegistry *this, HKEY a2, const unsigned __int16 *a3, REGSAM samDesired)
{
  LSTATUS v7; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp+10h] BYREF
  int v11; // [rsp+6Ch] [rbp+14h]

  v11 = HIDWORD(a2);
  *(_BYTE *)this = 0;
  hKey = 0;
  dwDisposition = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Avalon.Graphics",
          0,
          0,
          0,
          samDesired,
          0,
          &hKey,
          &dwDisposition) )
  {
    v7 = RegCreateKeyExW(hKey, a3, 0, 0, 0, samDesired, 0, (PHKEY)this + 1, &dwDisposition);
    RegCloseKey(hKey);
    if ( !v7 )
      *(_BYTE *)this = 1;
  }
  return this;
}

```

## disassembly

```asm
0x140002078  mov     r11, rsp
0x14000207b  mov     [r11+18h], rbx
0x14000207f  mov     [r11+20h], rsi
0x140002083  mov     [r11+10h], rdx
0x140002087  push    rdi
0x140002088  sub     rsp, 50h
0x14000208c  lea     rax, [r11+10h]
0x140002090  mov     byte ptr [rcx], 0
0x140002093  mov     [r11-18h], rax
0x140002097  lea     rdx, SubKey; "Software\\Microsoft\\Avalon.Graphics"
0x14000209e  mov     ebx, r9d
0x1400020a1  mov     qword ptr [r11+8], 0
0x1400020a9  lea     rax, [r11+8]
0x1400020ad  mov     [rsp+58h+dwDisposition], 0
0x1400020b5  mov     [r11-20h], rax
0x1400020b9  mov     rsi, r8
0x1400020bc  mov     qword ptr [r11-28h], 0
0x1400020c4  mov     rdi, rcx
0x1400020c7  mov     [rsp+58h+samDesired], ebx; samDesired
0x1400020cb  xor     r9d, r9d; lpClass
0x1400020ce  xor     r8d, r8d; Reserved
0x1400020d1  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1400020d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400020e0  call    cs:__imp_RegCreateKeyExW
0x1400020e6  test    eax, eax
0x1400020e8  jnz     short loc_14000213A
0x1400020ea  lea     rcx, [rsp+58h+dwDisposition]
0x1400020ef  xor     r9d, r9d; lpClass
0x1400020f2  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x1400020f7  lea     rax, [rdi+8]
0x1400020fb  mov     rcx, [rsp+58h+hKey]; hKey
0x140002100  xor     r8d, r8d; Reserved
0x140002103  mov     [rsp+58h+phkResult], rax; phkResult
0x140002108  mov     rdx, rsi; lpSubKey
0x14000210b  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140002114  mov     [rsp+58h+samDesired], ebx; samDesired
0x140002118  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140002120  call    cs:__imp_RegCreateKeyExW
0x140002126  mov     rcx, [rsp+58h+hKey]; hKey
0x14000212b  mov     ebx, eax
0x14000212d  call    cs:__imp_RegCloseKey
0x140002133  test    ebx, ebx
0x140002135  jnz     short loc_14000213A
0x140002137  mov     byte ptr [rdi], 1
0x14000213a  mov     rbx, [rsp+58h+arg_10]
0x14000213f  mov     rax, rdi
0x140002142  mov     rsi, [rsp+58h+arg_18]
0x140002147  add     rsp, 50h
0x14000214b  pop     rdi
0x14000214c  retn
```
