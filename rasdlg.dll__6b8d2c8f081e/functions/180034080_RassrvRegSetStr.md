# RassrvRegSetStr

- ea: `0x180034080`
- end: `0x180034110`
- name: `RassrvRegSetStr`
- size: `144`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180036d34`

## callees

- `0x180034080`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800340be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800340be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800340ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800340ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800340ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800340ed`

## pseudocode

```c
__int64 __fastcall RassrvRegSetStr(BYTE *lpData, const WCHAR *a2)
{
  __int64 v3; // rbx
  unsigned int v4; // edi
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20006u, &hKey);
  if ( !v4 )
    v4 = RegSetValueExW(hKey, L"NetworkAdapterGUID", 0, 1u, lpData, 2 * v3 + 2);
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180034080  mov     [rsp+hKey], r8
0x180034085  push    rbx
0x180034086  push    rbp
0x180034087  push    rsi
0x180034088  push    rdi
0x180034089  sub     rsp, 38h
0x18003408d  xor     ebp, ebp
0x18003408f  mov     rsi, rcx
0x180034092  mov     [rsp+58h+hKey], rbp
0x180034097  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003409b  inc     rbx
0x18003409e  cmp     [rcx+rbx*2], bp
0x1800340a2  jnz     short loc_18003409B
0x1800340a4  lea     rax, [rsp+58h+hKey]
0x1800340a9  mov     r9d, 20006h; samDesired
0x1800340af  xor     r8d, r8d; ulOptions
0x1800340b2  mov     [rsp+58h+phkResult], rax; phkResult
0x1800340b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800340be  call    cs:__imp_RegOpenKeyExW
0x1800340c4  mov     edi, eax
0x1800340c6  test    eax, eax
0x1800340c8  jnz     short loc_1800340F5
0x1800340ca  mov     rcx, [rsp+58h+hKey]; hKey
0x1800340cf  lea     eax, ds:2[rbx*2]
0x1800340d6  mov     [rsp+58h+cbData], eax; cbData
0x1800340da  lea     r9d, [rdi+1]; dwType
0x1800340de  xor     r8d, r8d; Reserved
0x1800340e1  mov     [rsp+58h+phkResult], rsi; lpData
0x1800340e6  lea     rdx, Type; "NetworkAdapterGUID"
0x1800340ed  call    cs:__imp_RegSetValueExW
0x1800340f3  mov     edi, eax
0x1800340f5  mov     rcx, [rsp+58h+hKey]; hKey
0x1800340fa  test    rcx, rcx
0x1800340fd  jz      short loc_180034105
0x1800340ff  call    cs:__imp_RegCloseKey
0x180034105  mov     eax, edi
0x180034107  add     rsp, 38h
0x18003410b  pop     rdi
0x18003410c  pop     rsi
0x18003410d  pop     rbp
0x18003410e  pop     rbx
0x18003410f  retn
```
