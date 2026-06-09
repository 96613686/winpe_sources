# CFontRegistry::Insert(CFontRegValue const &)

- ea: `0x180025cd4`
- end: `0x180025da1`
- name: `?Insert@CFontRegistry@@SAJAEBVCFontRegValue@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(const struct CFontRegValue *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180026704`
- `0x18002680c`

## callees

- `0x180025cd4`
- `0x180025e80`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025d76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025d76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025d90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025d90`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025d23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025d23`

## pseudocode

```c
__int64 __fastcall CFontRegistry::Insert(const struct CFontRegValue *a1)
{
  int v2; // ebx
  DWORD v3; // edi
  DWORD v4; // eax
  LSTATUS v5; // eax
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v2 = CFontRegistry::OpenKey(a1, 0x20006u, &hKey);
  if ( v2 >= 0 )
  {
    if ( RegQueryValueExW(hKey, (LPCWSTR)a1 + 6, 0, 0, 0, 0) )
    {
      v3 = (*(__int64 (__fastcall **)(const struct CFontRegValue *))(*(_QWORD *)a1 + 8LL))(a1);
      v4 = (*(__int64 (__fastcall **)(const struct CFontRegValue *, char *))(*(_QWORD *)a1 + 24LL))(
             a1,
             (char *)a1 + 532);
      v5 = RegSetValueExW(hKey, (LPCWSTR)a1 + 6, 0, v3, (const BYTE *)a1 + 532, v4);
      v2 = v5;
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      v2 = -2147024713;
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180025cd4  push    rbx
0x180025cd6  push    rbp
0x180025cd7  push    rsi
0x180025cd8  push    rdi
0x180025cd9  sub     rsp, 38h
0x180025cdd  lea     r8, [rsp+58h+hKey]; HKEY *
0x180025ce2  mov     [rsp+58h+hKey], 0
0x180025ceb  mov     edx, 20006h; unsigned int
0x180025cf0  mov     rsi, rcx
0x180025cf3  call    ?OpenKey@CFontRegistry@@SAJAEBVCFontRegValue@@KPEAPEAUHKEY__@@@Z; CFontRegistry::OpenKey(CFontRegValue const &,ulong,HKEY__ * *)
0x180025cf8  mov     ebx, eax
0x180025cfa  test    eax, eax
0x180025cfc  js      loc_180025D96
0x180025d02  mov     rcx, [rsp+58h+hKey]; hKey
0x180025d07  lea     rdx, [rsi+0Ch]; lpValueName
0x180025d0b  mov     [rsp+58h+lpcbData], 0; lpcbData
0x180025d14  xor     r9d, r9d; lpType
0x180025d17  xor     r8d, r8d; lpReserved
0x180025d1a  mov     [rsp+58h+lpData], 0; lpData
0x180025d23  call    cs:__imp_RegQueryValueExW
0x180025d29  test    eax, eax
0x180025d2b  jnz     short loc_180025D34
0x180025d2d  mov     ebx, 800700B7h
0x180025d32  jmp     short loc_180025D8B
0x180025d34  mov     rax, [rsi]
0x180025d37  mov     rcx, rsi
0x180025d3a  mov     rax, [rax+8]
0x180025d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d43  mov     rcx, [rsi]
0x180025d46  lea     rbx, [rsi+214h]
0x180025d4d  mov     edi, eax
0x180025d4f  mov     rdx, rbx
0x180025d52  mov     rax, [rcx+18h]
0x180025d56  mov     rcx, rsi
0x180025d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d5e  mov     rcx, [rsp+58h+hKey]; hKey
0x180025d63  lea     rdx, [rsi+0Ch]; lpValueName
0x180025d67  mov     dword ptr [rsp+58h+lpcbData], eax; cbData
0x180025d6b  mov     r9d, edi; dwType
0x180025d6e  xor     r8d, r8d; Reserved
0x180025d71  mov     [rsp+58h+lpData], rbx; lpData
0x180025d76  call    cs:__imp_RegSetValueExW
0x180025d7c  mov     ebx, eax
0x180025d7e  test    eax, eax
0x180025d80  jle     short loc_180025D8B
0x180025d82  movzx   ebx, ax
0x180025d85  or      ebx, 80070000h
0x180025d8b  mov     rcx, [rsp+58h+hKey]; hKey
0x180025d90  call    cs:__imp_RegCloseKey
0x180025d96  mov     eax, ebx
0x180025d98  add     rsp, 38h
0x180025d9c  pop     rdi
0x180025d9d  pop     rsi
0x180025d9e  pop     rbp
0x180025d9f  pop     rbx
0x180025da0  retn
```
