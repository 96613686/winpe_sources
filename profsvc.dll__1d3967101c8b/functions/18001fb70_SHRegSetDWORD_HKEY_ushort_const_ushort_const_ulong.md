# SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x18001fb70`
- end: `0x18001fc39`
- name: `?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z`
- size: `201`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800123cc`
- `0x18001ecc4`
- `0x18001f0c0`
- `0x180026070`
- `0x180027364`
- `0x18002b938`
- `0x18002c630`
- `0x18002cf64`
- `0x18002ed00`

## callees

- `0x18001fb70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fc31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fc31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fbba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fbba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fc10`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fc10`

## pseudocode

```c
__int64 __fastcall SHRegSetDWORD(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  HKEY v5; // rdi
  LSTATUS v6; // ebx
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  v5 = a1;
  if ( a2 && *a2 )
  {
    v6 = RegCreateKeyExW(a1, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v6 )
      goto LABEL_5;
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v6 = RegSetValueExW(a1, a3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( hKey != v5 )
    RegCloseKey(hKey);
LABEL_5:
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001fb70  mov     [rsp+arg_0], rbx
0x18001fb75  mov     [rsp+Data], r9d
0x18001fb7a  push    rbp
0x18001fb7b  push    rsi
0x18001fb7c  push    rdi
0x18001fb7d  sub     rsp, 50h
0x18001fb81  xor     ebp, ebp
0x18001fb83  mov     rsi, r8
0x18001fb86  mov     [rsp+68h+hKey], rbp
0x18001fb8b  mov     rdi, rcx
0x18001fb8e  test    rdx, rdx
0x18001fb91  jnz     loc_18001FC26
0x18001fb97  mov     [rsp+68h+hKey], rcx
0x18001fb9c  mov     r9d, 4; dwType
0x18001fba2  lea     rax, [rsp+68h+Data]
0x18001fbaa  mov     [rsp+68h+cbData], r9d; cbData
0x18001fbaf  xor     r8d, r8d; Reserved
0x18001fbb2  mov     rdx, rsi; lpValueName
0x18001fbb5  mov     [rsp+68h+lpData], rax; lpData
0x18001fbba  call    cs:__imp_RegSetValueExW
0x18001fbc0  mov     rcx, [rsp+68h+hKey]; hKey
0x18001fbc5  mov     ebx, eax
0x18001fbc7  cmp     rcx, rdi
0x18001fbca  jnz     short loc_18001FC31
0x18001fbcc  test    ebx, ebx
0x18001fbce  jg      short loc_18001FBDF
0x18001fbd0  mov     eax, ebx
0x18001fbd2  mov     rbx, [rsp+68h+arg_0]
0x18001fbd7  add     rsp, 50h
0x18001fbdb  pop     rdi
0x18001fbdc  pop     rsi
0x18001fbdd  pop     rbp
0x18001fbde  retn
0x18001fbdf  movzx   ebx, bx
0x18001fbe2  or      ebx, 80070000h
0x18001fbe8  jmp     short loc_18001FBD0
0x18001fbea  mov     [rsp+68h+lpdwDisposition], rbp; lpdwDisposition
0x18001fbef  lea     rax, [rsp+68h+hKey]
0x18001fbf4  mov     [rsp+68h+phkResult], rax; phkResult
0x18001fbf9  xor     r9d, r9d; lpClass
0x18001fbfc  mov     [rsp+68h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18001fc01  xor     r8d, r8d; Reserved
0x18001fc04  mov     [rsp+68h+cbData], 2; samDesired
0x18001fc0c  mov     dword ptr [rsp+68h+lpData], ebp; dwOptions
0x18001fc10  call    cs:__imp_RegCreateKeyExW
0x18001fc16  mov     ebx, eax
0x18001fc18  test    eax, eax
0x18001fc1a  jnz     short loc_18001FBCC
0x18001fc1c  mov     rcx, [rsp+68h+hKey]
0x18001fc21  jmp     loc_18001FB9C
0x18001fc26  cmp     [rdx], bp
0x18001fc29  jz      loc_18001FB97
0x18001fc2f  jmp     short loc_18001FBEA
0x18001fc31  call    cs:__imp_RegCloseKey
0x18001fc37  jmp     short loc_18001FBCC
```
