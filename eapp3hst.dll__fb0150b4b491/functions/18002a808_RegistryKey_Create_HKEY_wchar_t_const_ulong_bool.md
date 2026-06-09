# RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)

- ea: `0x18002a808`
- end: `0x18002a8d4`
- name: `?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z`
- size: `204`
- prototype: `__int64 __fastcall(__int64, HKEY, const WCHAR *, int, DWORD dwDisposition)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002cee8`

## callees

- `0x180012a70`
- `0x18002a7dc`
- `0x18002a808`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a879`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a879`

## string_xrefs

- `0x18002a88f`: `RegCreateKeyExW`

## pseudocode

```c
__int64 __fastcall RegistryKey::Create(__int64 a1, HKEY a2, const WCHAR *a3, int a4, DWORD dwDisposition)
{
  int v7; // eax
  HKEY v8; // rbx
  HKEY phkResult; // [rsp+50h] [rbp-18h] BYREF
  int v11; // [rsp+58h] [rbp-10h]

  phkResult = 0;
  v11 = 1;
  dwDisposition = 0;
  v7 = RegCreateKeyExW(a2, a3, 0, 0, 0, a4 | 0x100, 0, &phkResult, &dwDisposition);
  if ( v7 )
  {
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    SystemError::ThrowHelper(L"RegCreateKeyExW", v7);
  }
  v8 = phkResult;
  phkResult = 0;
  RegistryKey::Clear((HKEY *)a1);
  *(_QWORD *)a1 = v8;
  *(_DWORD *)(a1 + 8) = a4;
  RegistryKey::Clear(&phkResult);
  return 0;
}

```

## disassembly

```asm
0x18002a808  mov     rax, rsp
0x18002a80b  mov     [rax+8], rbx
0x18002a80f  mov     [rax+10h], rsi
0x18002a813  push    rdi
0x18002a814  sub     rsp, 60h
0x18002a818  mov     esi, r9d
0x18002a81b  mov     r10, r8
0x18002a81e  mov     r11, rdx
0x18002a821  mov     rdi, rcx
0x18002a824  mov     qword ptr [rax-18h], 0
0x18002a82c  mov     dword ptr [rax-10h], 1
0x18002a833  mov     dword ptr [rax+28h], 0
0x18002a83a  mov     eax, r9d
0x18002a83d  bts     eax, 8
0x18002a841  lea     rcx, [rsp+68h+dwDisposition]
0x18002a849  mov     [rsp+68h+lpdwDisposition], rcx; lpdwDisposition
0x18002a84e  lea     rcx, [rsp+68h+var_18]
0x18002a853  mov     [rsp+68h+phkResult], rcx; phkResult
0x18002a858  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002a861  mov     [rsp+68h+samDesired], eax; samDesired
0x18002a865  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18002a86d  xor     r9d, r9d; lpClass
0x18002a870  xor     r8d, r8d; Reserved
0x18002a873  mov     rdx, r10; lpSubKey
0x18002a876  mov     rcx, r11; hKey
0x18002a879  call    cs:__imp_RegCreateKeyExW
0x18002a87f  test    eax, eax
0x18002a881  jz      short loc_18002A89C
0x18002a883  jle     short loc_18002A88D
0x18002a885  movzx   eax, ax
0x18002a888  or      eax, 80070000h
0x18002a88d  mov     edx, eax; int
0x18002a88f  lea     rcx, aRegcreatekeyex; "RegCreateKeyExW"
0x18002a896  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x18002a89c  mov     rbx, [rsp+68h+var_18]
0x18002a8a1  mov     [rsp+68h+var_18], 0
0x18002a8aa  mov     rcx, rdi; this
0x18002a8ad  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002a8b2  mov     [rdi], rbx
0x18002a8b5  mov     [rdi+8], esi
0x18002a8b8  lea     rcx, [rsp+68h+var_18]; this
0x18002a8bd  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002a8c2  xor     eax, eax
0x18002a8c4  mov     rbx, [rsp+68h+arg_0]
0x18002a8c9  mov     rsi, [rsp+68h+arg_8]
0x18002a8ce  add     rsp, 60h
0x18002a8d2  pop     rdi
0x18002a8d3  retn
```
