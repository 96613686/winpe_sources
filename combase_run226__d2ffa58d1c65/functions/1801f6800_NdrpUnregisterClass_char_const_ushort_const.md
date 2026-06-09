# NdrpUnregisterClass(char const *,ushort const *)

- ea: `0x1801f6800`
- end: `0x1801f6927`
- name: `?NdrpUnregisterClass@@YAJPEBDPEBG@Z`
- size: `295`
- prototype: `HRESULT __fastcall(const char *pszClassID, const wchar_t *pszDllFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801f61f0`

## callees

- `0x1801f5fa4`
- `0x1801f6800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f68a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f68e8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f68a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f68e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f68c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f6902`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f68c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f6902`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801f6845`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801f6870`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801f6845`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801f6870`

## string_xrefs

- `0x1801f6831`: `CLSID`

## pseudocode

```c
__int64 __fastcall NdrpUnregisterClass(const char *pszClassID, const wchar_t *pszDllFileName)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  HKEY__ *hKeyClassID; // [rsp+50h] [rbp+18h] BYREF
  HKEY__ *hKeyCLSID; // [rsp+58h] [rbp+20h] BYREF

  hKeyCLSID = 0;
  hKeyClassID = 0;
  v4 = RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x20006u, &hKeyCLSID);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v6 = RegOpenKeyExA(hKeyCLSID, pszClassID, 0, 0x20006u, &hKeyClassID);
    v5 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v5 = CheckInprocServer32(hKeyClassID, pszDllFileName);
      if ( v5 >= 0 )
      {
        v7 = RegDeleteKeyExA(hKeyClassID, "InProcServer32", 0, 0);
        if ( v7 )
        {
          if ( v7 > 0 )
            v5 = (unsigned __int16)v7 | 0x80070000;
          else
            v5 = v7;
        }
      }
      RegCloseKey(hKeyClassID);
    }
    if ( v5 >= 0 )
    {
      v8 = RegDeleteKeyExA(hKeyCLSID, pszClassID, 0, 0);
      if ( v8 )
      {
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        else
          v5 = v8;
      }
    }
    RegCloseKey(hKeyCLSID);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801f6800  mov     r11, rsp
0x1801f6803  mov     [r11+8], rbx
0x1801f6807  mov     [r11+10h], rsi
0x1801f680b  push    rdi
0x1801f680c  sub     rsp, 30h
0x1801f6810  mov     rdi, pszDllFileName
0x1801f6813  mov     qword ptr [r11+20h], 0
0x1801f681b  mov     rsi, pszClassID
0x1801f681e  mov     qword ptr [r11+18h], 0
0x1801f6826  lea     rax, [r11+20h]
0x1801f682a  mov     pszClassID, 0FFFFFFFF80000000h; hKey
0x1801f6831  lea     pszDllFileName, aClsid_0; "CLSID"
0x1801f6838  mov     [r11-18h], rax
0x1801f683c  mov     r9d, 20006h; samDesired
0x1801f6842  xor     r8d, r8d; ulOptions
0x1801f6845  call    cs:__imp_RegOpenKeyExA
0x1801f684b  mov     ebx, eax
0x1801f684d  test    eax, eax
0x1801f684f  jnz     loc_1801F690A
0x1801f6855  mov     pszClassID, [rsp+38h+hKeyCLSID]; hKey
0x1801f685a  lea     rax, [rsp+38h+hKeyClassID]
0x1801f685f  mov     r9d, 20006h; samDesired
0x1801f6865  mov     [rsp+38h+phkResult], rax; phkResult
0x1801f686a  xor     r8d, r8d; ulOptions
0x1801f686d  mov     pszDllFileName, rsi; lpSubKey
0x1801f6870  call    cs:__imp_RegOpenKeyExA
0x1801f6876  mov     ebx, eax
0x1801f6878  test    eax, eax
0x1801f687a  jnz     short loc_1801F68C8
0x1801f687c  mov     pszClassID, [rsp+38h+hKeyClassID]; hKeyIID
0x1801f6881  mov     pszDllFileName, rdi; pszDllFileName
0x1801f6884  call    ?CheckInprocServer32@@YAJPEAUHKEY__@@PEBG@Z; CheckInprocServer32(HKEY__ *,ushort const *)
0x1801f6889  mov     ebx, eax
0x1801f688b  mov     edi, 80070000h
0x1801f6890  test    eax, eax
0x1801f6892  js      short loc_1801F68BB
0x1801f6894  mov     pszClassID, [rsp+38h+hKeyClassID]; hKey
0x1801f6899  lea     pszDllFileName, aInprocserver32; "InProcServer32"
0x1801f68a0  xor     r9d, r9d; Reserved
0x1801f68a3  xor     r8d, r8d; samDesired
0x1801f68a6  call    cs:__imp_RegDeleteKeyExA
0x1801f68ac  test    eax, eax
0x1801f68ae  jz      short loc_1801F68BB
0x1801f68b0  jg      short loc_1801F68B6
0x1801f68b2  mov     ebx, eax
0x1801f68b4  jmp     short loc_1801F68BB
0x1801f68b6  movzx   ebx, ax
0x1801f68b9  or      ebx, edi
0x1801f68bb  mov     pszClassID, [rsp+38h+hKeyClassID]; hKey
0x1801f68c0  call    cs:__imp_RegCloseKey
0x1801f68c6  jmp     short loc_1801F68D6
0x1801f68c8  mov     edi, 80070000h
0x1801f68cd  test    eax, eax
0x1801f68cf  jle     short loc_1801F68D6
0x1801f68d1  movzx   ebx, ax
0x1801f68d4  or      ebx, edi
0x1801f68d6  test    ebx, ebx
0x1801f68d8  js      short loc_1801F68FD
0x1801f68da  mov     pszClassID, [rsp+38h+hKeyCLSID]; hKey
0x1801f68df  xor     r9d, r9d; Reserved
0x1801f68e2  xor     r8d, r8d; samDesired
0x1801f68e5  mov     pszDllFileName, rsi; lpSubKey
0x1801f68e8  call    cs:__imp_RegDeleteKeyExA
0x1801f68ee  test    eax, eax
0x1801f68f0  jz      short loc_1801F68FD
0x1801f68f2  jg      short loc_1801F68F8
0x1801f68f4  mov     ebx, eax
0x1801f68f6  jmp     short loc_1801F68FD
0x1801f68f8  movzx   ebx, ax
0x1801f68fb  or      ebx, edi
0x1801f68fd  mov     pszClassID, [rsp+38h+hKeyCLSID]; hKey
0x1801f6902  call    cs:__imp_RegCloseKey
0x1801f6908  jmp     short loc_1801F6915
0x1801f690a  jle     short loc_1801F6915
0x1801f690c  movzx   ebx, ax
0x1801f690f  or      ebx, 80070000h
0x1801f6915  mov     rsi, [rsp+38h+arg_8]
0x1801f691a  mov     eax, ebx
0x1801f691c  mov     rbx, [rsp+38h+arg_0]
0x1801f6921  add     rsp, 30h
0x1801f6925  pop     rdi
0x1801f6926  retn
```
