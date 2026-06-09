# SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800079b0`
- end: `0x180007aa1`
- name: `?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `241`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006e70`
- `0x18001f0c0`
- `0x18002cedc`
- `0x18002cf64`
- `0x180030c24`
- `0x180038de4`
- `0x18004e5b0`

## callees

- `0x1800079b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007a1c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007a1c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007a83`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007a83`

## pseudocode

```c
__int64 __fastcall SHRegSetString(HKEY hKey, const unsigned __int16 *a2, const unsigned __int16 *a3, const BYTE *a4)
{
  HKEY v6; // rbp
  unsigned __int64 v7; // rbx
  LSTATUS v8; // esi
  HKEY hKeya; // [rsp+50h] [rbp-38h] BYREF

  v6 = hKey;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&a4[2 * v7] );
  if ( v7 >= 0x7FFFFFFF )
  {
    LOWORD(v8) = 534;
    return (unsigned __int16)v8 | 0x80070000;
  }
  hKeya = 0;
  if ( a2 && *a2 )
  {
    v8 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 2u, 0, &hKeya, 0);
    if ( v8 )
      goto LABEL_8;
    hKey = hKeya;
  }
  else
  {
    hKeya = hKey;
  }
  v8 = RegSetValueExW(hKey, a3, 0, 1u, a4, 2 * v7 + 2);
  if ( hKeya != v6 )
    RegCloseKey(hKeya);
LABEL_8:
  if ( v8 <= 0 )
    return (unsigned int)v8;
  return (unsigned __int16)v8 | 0x80070000;
}

```

## disassembly

```asm
0x1800079b0  push    rbx
0x1800079b2  push    rbp
0x1800079b3  push    rdi
0x1800079b4  push    r14
0x1800079b6  sub     rsp, 68h
0x1800079ba  mov     rdi, r9
0x1800079bd  mov     r14, r8
0x1800079c0  mov     rbp, rcx
0x1800079c3  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800079ca  nop     word ptr [rax+rax+00h]
0x1800079d0  inc     rbx
0x1800079d3  cmp     word ptr [r9+rbx*2], 0
0x1800079d9  jnz     short loc_1800079D0
0x1800079db  mov     [rsp+88h+arg_0], rsi
0x1800079e3  cmp     rbx, 7FFFFFFFh
0x1800079ea  jnb     short loc_180007A46
0x1800079ec  xor     ecx, ecx
0x1800079ee  mov     [rsp+88h+hKey], rcx
0x1800079f3  test    rdx, rdx
0x1800079f6  jnz     short loc_180007A55
0x1800079f8  mov     rcx, rbp; hKey
0x1800079fb  mov     [rsp+88h+hKey], rcx
0x180007a00  lea     ebx, ds:2[rbx*2]
0x180007a07  mov     r9d, 1; dwType
0x180007a0d  mov     [rsp+88h+cbData], ebx; cbData
0x180007a11  xor     r8d, r8d; Reserved
0x180007a14  mov     rdx, r14; lpValueName
0x180007a17  mov     [rsp+88h+lpData], rdi; lpData
0x180007a1c  call    cs:__imp_RegSetValueExW
0x180007a22  mov     rcx, [rsp+88h+hKey]; hKey
0x180007a27  mov     esi, eax
0x180007a29  cmp     rcx, rbp
0x180007a2c  jnz     short loc_180007A99
0x180007a2e  test    esi, esi
0x180007a30  jg      short loc_180007A4B
0x180007a32  mov     eax, esi
0x180007a34  mov     rsi, [rsp+88h+arg_0]
0x180007a3c  add     rsp, 68h
0x180007a40  pop     r14
0x180007a42  pop     rdi
0x180007a43  pop     rbp
0x180007a44  pop     rbx
0x180007a45  retn
0x180007a46  mov     esi, 216h
0x180007a4b  movzx   eax, si
0x180007a4e  or      eax, 80070000h
0x180007a53  jmp     short loc_180007A34
0x180007a55  cmp     [rdx], cx
0x180007a58  jz      short loc_1800079F8
0x180007a5a  mov     [rsp+88h+lpdwDisposition], rcx; lpdwDisposition
0x180007a5f  lea     rax, [rsp+88h+hKey]
0x180007a64  mov     [rsp+88h+phkResult], rax; phkResult
0x180007a69  xor     r9d, r9d; lpClass
0x180007a6c  mov     [rsp+88h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180007a71  xor     r8d, r8d; Reserved
0x180007a74  mov     [rsp+88h+cbData], 2; samDesired
0x180007a7c  mov     dword ptr [rsp+88h+lpData], ecx; dwOptions
0x180007a80  mov     rcx, rbp; hKey
0x180007a83  call    cs:__imp_RegCreateKeyExW
0x180007a89  mov     esi, eax
0x180007a8b  test    eax, eax
0x180007a8d  jnz     short loc_180007A2E
0x180007a8f  mov     rcx, [rsp+88h+hKey]
0x180007a94  jmp     loc_180007A00
0x180007a99  call    cs:__imp_RegCloseKey
0x180007a9f  jmp     short loc_180007A2E
```
