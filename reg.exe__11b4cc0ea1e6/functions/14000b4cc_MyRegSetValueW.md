# MyRegSetValueW

- ea: `0x14000b4cc`
- end: `0x14000b59f`
- name: `MyRegSetValueW`
- size: `211`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000b1d4`

## callees

- `0x14000b4cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000b56c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000b56c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000b540`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000b540`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b57e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b57e`

## pseudocode

```c
__int64 __fastcall MyRegSetValueW(HKEY a1, const WCHAR *a2, __int64 a3, const BYTE *a4)
{
  HKEY v5; // rdi
  __int64 v6; // rax
  unsigned __int64 v7; // rbp
  unsigned int v8; // ebx
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF

  hKey = 0;
  v5 = a1;
  if ( a4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a4[2 * v6] );
    v7 = 2 * v6 + 2;
    if ( v7 > 0xFFFFFFFF )
    {
      return 87;
    }
    else
    {
      if ( !a2 || !*a2 )
      {
        hKey = a1;
LABEL_10:
        v8 = RegSetValueExW(a1, 0, 0, 1u, a4, v7);
        if ( hKey != v5 )
          RegCloseKey(hKey);
        return v8;
      }
      v8 = RegCreateKeyExW(a1, a2, 0, 0, 0, 2u, 0, &hKey, 0);
      if ( !v8 )
      {
        a1 = hKey;
        goto LABEL_10;
      }
    }
    return v8;
  }
  return 87;
}

```

## disassembly

```asm
0x14000b4cc  push    rbx
0x14000b4ce  push    rbp
0x14000b4cf  push    rsi
0x14000b4d0  push    rdi
0x14000b4d1  push    r14
0x14000b4d3  sub     rsp, 60h
0x14000b4d7  xor     r14d, r14d
0x14000b4da  mov     rsi, r9
0x14000b4dd  mov     [rsp+88h+hKey], r14
0x14000b4e2  mov     rdi, rcx
0x14000b4e5  test    r9, r9
0x14000b4e8  jz      loc_14000B58F
0x14000b4ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b4f2  inc     rax
0x14000b4f5  cmp     [r9+rax*2], r14w
0x14000b4fa  jnz     short loc_14000B4F2
0x14000b4fc  lea     rbp, ds:2[rax*2]
0x14000b504  mov     eax, 0FFFFFFFFh
0x14000b509  cmp     rbp, rax
0x14000b50c  ja      short loc_14000B586
0x14000b50e  test    rdx, rdx
0x14000b511  jz      short loc_14000B553
0x14000b513  cmp     [rdx], r14w
0x14000b517  jz      short loc_14000B553
0x14000b519  mov     [rsp+88h+lpdwDisposition], r14; lpdwDisposition
0x14000b51e  lea     rax, [rsp+88h+hKey]
0x14000b523  mov     [rsp+88h+phkResult], rax; phkResult
0x14000b528  xor     r9d, r9d; lpClass
0x14000b52b  mov     [rsp+88h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14000b530  xor     r8d, r8d; Reserved
0x14000b533  mov     [rsp+88h+samDesired], 2; samDesired
0x14000b53b  mov     [rsp+88h+dwOptions], r14d; dwOptions
0x14000b540  call    cs:__imp_RegCreateKeyExW
0x14000b546  mov     ebx, eax
0x14000b548  test    eax, eax
0x14000b54a  jnz     short loc_14000B58B
0x14000b54c  mov     rcx, [rsp+88h+hKey]; hKey
0x14000b551  jmp     short loc_14000B558
0x14000b553  mov     [rsp+88h+hKey], rcx
0x14000b558  mov     [rsp+88h+samDesired], ebp; cbData
0x14000b55c  mov     r9d, 1; dwType
0x14000b562  xor     r8d, r8d; Reserved
0x14000b565  mov     qword ptr [rsp+88h+dwOptions], rsi; lpData
0x14000b56a  xor     edx, edx; lpValueName
0x14000b56c  call    cs:__imp_RegSetValueExW
0x14000b572  mov     rcx, [rsp+88h+hKey]; hKey
0x14000b577  mov     ebx, eax
0x14000b579  cmp     rcx, rdi
0x14000b57c  jz      short loc_14000B58B
0x14000b57e  call    cs:__imp_RegCloseKey
0x14000b584  jmp     short loc_14000B58B
0x14000b586  mov     ebx, 57h ; 'W'
0x14000b58b  mov     eax, ebx
0x14000b58d  jmp     short loc_14000B594
0x14000b58f  mov     eax, 57h ; 'W'
0x14000b594  add     rsp, 60h
0x14000b598  pop     r14
0x14000b59a  pop     rdi
0x14000b59b  pop     rsi
0x14000b59c  pop     rbp
0x14000b59d  pop     rbx
0x14000b59e  retn
```
