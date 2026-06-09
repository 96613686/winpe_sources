# _DeleteAllKey(HKEY__ *)

- ea: `0x180005d90`
- end: `0x180005efa`
- name: `?_DeleteAllKey@@YAJPEAUHKEY__@@@Z`
- size: `362`
- prototype: `LSTATUS __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800056f0`

## callees

- `0x180005d90`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005e2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005e2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ec1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ed6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ec1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ed6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005e8b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005e8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005dd8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005dd8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180005ea3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180005ea3`

## pseudocode

```c
LSTATUS __fastcall _DeleteAllKey(HKEY hKey)
{
  LSTATUS result; // eax
  WCHAR *v3; // rsi
  SIZE_T v4; // rdx
  DWORD i; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // edi
  bool v8; // cc
  unsigned int v9; // edi
  DWORD v10; // [rsp+98h] [rbp+10h] BYREF
  DWORD v11; // [rsp+A0h] [rbp+18h] BYREF
  DWORD cchName; // [rsp+A8h] [rbp+20h] BYREF

  v10 = 0;
  v11 = 0;
  result = RegQueryInfoKeyW(hKey, 0, 0, 0, &v11, &v10, 0, 0, 0, 0, 0, 0);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v3 = 0;
    if ( v11 )
    {
      v4 = 2LL * ++v10;
      v3 = (WCHAR *)LocalAlloc(0, v4);
      if ( !v3 )
        return -2147024882;
      for ( i = 0; i < v11; ++i )
      {
        cchName = v10;
        v6 = RegEnumKeyExW(hKey, 0, v3, &cchName, 0, 0, 0, 0);
        v7 = v6;
        v8 = v6 <= 0;
        if ( !v6 )
        {
          v6 = RegDeleteKeyExW(hKey, v3, 0, 0);
          v7 = v6;
          v8 = v6 <= 0;
          if ( !v6 )
            continue;
        }
        if ( v8 )
          goto LABEL_15;
        v9 = (unsigned __int16)v6 | 0x80070000;
        LocalFree(v3);
        return v9;
      }
    }
    v7 = 0;
    if ( v3 )
    {
LABEL_15:
      LocalFree(v3);
      return v7;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005d90  mov     r11, rsp
0x180005d93  push    rbp
0x180005d94  push    r14
0x180005d96  sub     rsp, 78h
0x180005d9a  xor     r14d, r14d
0x180005d9d  lea     rax, [r11+10h]
0x180005da1  mov     [r11-30h], r14
0x180005da5  xor     r9d, r9d; lpReserved
0x180005da8  mov     [r11-38h], r14
0x180005dac  xor     r8d, r8d; lpcchClass
0x180005daf  mov     [r11-40h], r14
0x180005db3  xor     edx, edx; lpClass
0x180005db5  mov     [r11-48h], r14
0x180005db9  mov     rbp, rcx
0x180005dbc  mov     [r11-50h], r14
0x180005dc0  mov     [r11-58h], r14
0x180005dc4  mov     [r11-60h], rax
0x180005dc8  lea     rax, [r11+18h]
0x180005dcc  mov     [r11-68h], rax
0x180005dd0  mov     [r11+10h], r14d
0x180005dd4  mov     [r11+18h], r14d
0x180005dd8  call    cs:__imp_RegQueryInfoKeyW
0x180005dde  test    eax, eax
0x180005de0  jz      short loc_180005DF8
0x180005de2  jle     loc_180005EF2
0x180005de8  movzx   eax, ax
0x180005deb  or      eax, 80070000h
0x180005df0  add     rsp, 78h
0x180005df4  pop     r14
0x180005df6  pop     rbp
0x180005df7  retn
0x180005df8  mov     [rsp+88h+var_18], rbx
0x180005dfd  mov     [rsp+88h+var_20], rsi
0x180005e02  mov     rsi, r14
0x180005e05  mov     [rsp+88h+var_28], rdi
0x180005e0a  cmp     [rsp+88h+arg_10], esi
0x180005e11  jz      loc_180005ECB
0x180005e17  mov     eax, [rsp+88h+arg_8]
0x180005e1e  xor     ecx, ecx; uFlags
0x180005e20  inc     eax
0x180005e22  mov     edx, eax
0x180005e24  add     rdx, rdx; uBytes
0x180005e27  mov     [rsp+88h+arg_8], eax
0x180005e2e  call    cs:__imp_LocalAlloc
0x180005e34  mov     rsi, rax
0x180005e37  test    rax, rax
0x180005e3a  jnz     short loc_180005E46
0x180005e3c  mov     eax, 8007000Eh
0x180005e41  jmp     loc_180005EE3
0x180005e46  mov     ebx, r14d
0x180005e49  nop     dword ptr [rax+00000000h]
0x180005e50  cmp     ebx, [rsp+88h+arg_10]
0x180005e57  jnb     short loc_180005ECB
0x180005e59  mov     eax, [rsp+88h+arg_8]
0x180005e60  lea     r9, [rsp+88h+cchName]; lpcchName
0x180005e68  mov     [rsp+88h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180005e6d  mov     r8, rsi; lpName
0x180005e70  mov     [rsp+88h+lpcchClass], r14; lpcchClass
0x180005e75  xor     edx, edx; dwIndex
0x180005e77  mov     [rsp+88h+lpClass], r14; lpClass
0x180005e7c  mov     rcx, rbp; hKey
0x180005e7f  mov     [rsp+88h+lpReserved], r14; lpReserved
0x180005e84  mov     [rsp+88h+cchName], eax
0x180005e8b  call    cs:__imp_RegEnumKeyExW
0x180005e91  mov     edi, eax
0x180005e93  test    eax, eax
0x180005e95  jnz     short loc_180005EB3
0x180005e97  xor     r9d, r9d; Reserved
0x180005e9a  xor     r8d, r8d; samDesired
0x180005e9d  mov     rdx, rsi; lpSubKey
0x180005ea0  mov     rcx, rbp; hKey
0x180005ea3  call    cs:__imp_RegDeleteKeyExW
0x180005ea9  mov     edi, eax
0x180005eab  test    eax, eax
0x180005ead  jnz     short loc_180005EB3
0x180005eaf  inc     ebx
0x180005eb1  jmp     short loc_180005E50
0x180005eb3  jle     short loc_180005ED3
0x180005eb5  movzx   edi, ax
0x180005eb8  mov     rcx, rsi; hMem
0x180005ebb  or      edi, 80070000h
0x180005ec1  call    cs:__imp_LocalFree
0x180005ec7  mov     eax, edi
0x180005ec9  jmp     short loc_180005EE3
0x180005ecb  mov     edi, r14d
0x180005ece  test    rsi, rsi
0x180005ed1  jz      short loc_180005EE0
0x180005ed3  mov     rcx, rsi; hMem
0x180005ed6  call    cs:__imp_LocalFree
0x180005edc  mov     eax, edi
0x180005ede  jmp     short loc_180005EE3
0x180005ee0  mov     eax, r14d
0x180005ee3  mov     rsi, [rsp+88h+var_20]
0x180005ee8  mov     rbx, [rsp+88h+var_18]
0x180005eed  mov     rdi, [rsp+88h+var_28]
0x180005ef2  add     rsp, 78h
0x180005ef6  pop     r14
0x180005ef8  pop     rbp
0x180005ef9  retn
```
