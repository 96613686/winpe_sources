# _ReadSZValueFromRegistry

- ea: `0x18001f4fc`
- end: `0x18001f615`
- name: `_ReadSZValueFromRegistry`
- size: `281`
- prototype: `BYTE *__fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180017de4`
- `0x18001f17c`
- `0x18001f310`

## callees

- `0x180007c00`
- `0x18000a990`
- `0x18001f4fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f55e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f5e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f5f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f55e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f5e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f5f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f531`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f5c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f531`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f5c1`

## pseudocode

```c
BYTE *__fastcall ReadSZValueFromRegistry(HKEY hKey, LPCWSTR lpValueName)
{
  BYTE *lpData; // rbx
  LSTATUS v5; // eax
  DWORD v6; // ecx
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rcx
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  Type = 0;
  lpData = 0;
  cbData = 0;
  v5 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  if ( v5 )
    goto LABEL_15;
  if ( Type - 1 > 1 && Type != 7 || cbData < 2 || cbData > 0x1FFFFFE )
  {
    v6 = -2146885629;
LABEL_6:
    SetLastError(v6);
    return lpData;
  }
  v7 = (unsigned __int64)cbData >> 1;
  lpData = (BYTE *)operator new(saturated_mul(v7 + 2, 2u));
  if ( !lpData )
  {
    v6 = -2147024882;
    goto LABEL_6;
  }
  v5 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
  if ( v5 )
  {
LABEL_15:
    SetLastError(v5);
    if ( !lpData )
      return lpData;
LABEL_16:
    operator delete(lpData);
    return 0;
  }
  v8 = (unsigned __int64)cbData >> 1;
  if ( v7 < v8 )
    v8 = v7;
  *(_DWORD *)&lpData[2 * v8] = 0;
  if ( !*(_WORD *)lpData )
  {
    SetLastError(0x80092003);
    goto LABEL_16;
  }
  return lpData;
}

```

## disassembly

```asm
0x18001f4fc  mov     r11, rsp
0x18001f4ff  mov     [r11+8], rbx
0x18001f503  push    rbp
0x18001f504  push    rsi
0x18001f505  push    rdi
0x18001f506  sub     rsp, 30h
0x18001f50a  lea     rax, [r11+18h]
0x18001f50e  mov     [rsp+48h+Type], 0
0x18001f516  xor     ebx, ebx
0x18001f518  mov     [r11-20h], rax
0x18001f51c  lea     r9, [r11+20h]; lpType
0x18001f520  mov     [r11-28h], rbx
0x18001f524  xor     r8d, r8d; lpReserved
0x18001f527  mov     [rsp+48h+cbData], ebx
0x18001f52b  mov     rsi, rdx
0x18001f52e  mov     rbp, rcx
0x18001f531  call    cs:__imp_RegQueryValueExW
0x18001f537  test    eax, eax
0x18001f539  jnz     loc_18001F5EE
0x18001f53f  mov     ecx, [rsp+48h+Type]
0x18001f543  lea     eax, [rcx-1]
0x18001f546  cmp     eax, 1
0x18001f549  jbe     short loc_18001F550
0x18001f54b  cmp     ecx, 7
0x18001f54e  jnz     short loc_18001F559
0x18001f550  mov     eax, [rsp+48h+cbData]
0x18001f554  cmp     eax, 2
0x18001f557  jnb     short loc_18001F569
0x18001f559  mov     ecx, 80092003h; dwErrCode
0x18001f55e  call    cs:__imp_SetLastError
0x18001f564  jmp     loc_18001F605
0x18001f569  cmp     eax, 1FFFFFEh
0x18001f56e  ja      short loc_18001F559
0x18001f570  mov     rdi, rax
0x18001f573  mov     eax, 2
0x18001f578  shr     rdi, 1
0x18001f57b  lea     rcx, [rdi+2]
0x18001f57f  mul     rcx
0x18001f582  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f589  cmovb   rax, rcx
0x18001f58d  mov     rcx, rax; uBytes
0x18001f590  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f595  mov     rbx, rax
0x18001f598  test    rax, rax
0x18001f59b  jnz     short loc_18001F5A4
0x18001f59d  mov     ecx, 8007000Eh
0x18001f5a2  jmp     short loc_18001F55E
0x18001f5a4  lea     rax, [rsp+48h+cbData]
0x18001f5a9  xor     r8d, r8d; lpReserved
0x18001f5ac  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001f5b1  lea     r9, [rsp+48h+Type]; lpType
0x18001f5b6  mov     rdx, rsi; lpValueName
0x18001f5b9  mov     [rsp+48h+lpData], rbx; lpData
0x18001f5be  mov     rcx, rbp; hKey
0x18001f5c1  call    cs:__imp_RegQueryValueExW
0x18001f5c7  test    eax, eax
0x18001f5c9  jnz     short loc_18001F5EE
0x18001f5cb  mov     ecx, [rsp+48h+cbData]
0x18001f5cf  shr     rcx, 1
0x18001f5d2  cmp     rdi, rcx
0x18001f5d5  cmovb   rcx, rdi
0x18001f5d9  mov     [rbx+rcx*2], eax
0x18001f5dc  cmp     ax, [rbx]
0x18001f5df  jnz     short loc_18001F605
0x18001f5e1  mov     ecx, 80092003h; dwErrCode
0x18001f5e6  call    cs:__imp_SetLastError
0x18001f5ec  jmp     short loc_18001F5FB
0x18001f5ee  mov     ecx, eax; dwErrCode
0x18001f5f0  call    cs:__imp_SetLastError
0x18001f5f6  test    rbx, rbx
0x18001f5f9  jz      short loc_18001F605
0x18001f5fb  mov     rcx, rbx; hMem
0x18001f5fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f603  xor     ebx, ebx
0x18001f605  mov     rax, rbx
0x18001f608  mov     rbx, [rsp+48h+arg_0]
0x18001f60d  add     rsp, 30h
0x18001f611  pop     rdi
0x18001f612  pop     rsi
0x18001f613  pop     rbp
0x18001f614  retn
```
