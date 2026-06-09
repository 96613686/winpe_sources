# RassrvRegSetDwEx

- ea: `0x180021994`
- end: `0x180021a53`
- name: `RassrvRegSetDwEx`
- size: `191`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180026f44`
- `0x1800283bc`
- `0x180028964`
- `0x180028c40`
- `0x180029d34`
- `0x180029e34`
- `0x180029f24`

## callees

- `0x180021994`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021a40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021a40`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800219e7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800219e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800219ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800219ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021a2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021a2e`

## pseudocode

```c
__int64 __fastcall RassrvRegSetDwEx(int a1, const WCHAR *a2, const WCHAR *a3, int a4)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  HKEY phkResult[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD v9; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Data = a1;
  phkResult[0] = 0;
  if ( a4 )
  {
    v9 = 0;
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0x20006u, 0, phkResult, &v9);
  }
  else
  {
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20006u, phkResult);
  }
  v6 = v5;
  if ( !v5 )
    v6 = RegSetValueExW(phkResult[0], a3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( phkResult[0] )
    RegCloseKey(phkResult[0]);
  return v6;
}

```

## disassembly

```asm
0x180021994  mov     r11, rsp
0x180021997  mov     [r11+10h], rbx
0x18002199b  push    rdi
0x18002199c  sub     rsp, 60h
0x1800219a0  mov     rdi, r8
0x1800219a3  mov     [r11+20h], ecx
0x1800219a7  xor     r8d, r8d; ulOptions
0x1800219aa  mov     qword ptr [r11-18h], 0
0x1800219b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800219b9  test    r9d, r9d
0x1800219bc  jz      short loc_1800219EF
0x1800219be  lea     rax, [r11+8]
0x1800219c2  mov     [rsp+68h+arg_0], r8d
0x1800219c7  mov     [r11-28h], rax
0x1800219cb  xor     r9d, r9d; lpClass
0x1800219ce  lea     rax, [r11-18h]
0x1800219d2  mov     [r11-30h], rax
0x1800219d6  mov     [r11-38h], r8
0x1800219da  mov     [rsp+68h+samDesired], 20006h; samDesired
0x1800219e2  mov     [rsp+68h+dwOptions], r8d; dwOptions
0x1800219e7  call    cs:__imp_RegCreateKeyExW
0x1800219ed  jmp     short loc_180021A05
0x1800219ef  lea     rax, [rsp+68h+phkResult]
0x1800219f4  mov     r9d, 20006h; samDesired
0x1800219fa  mov     qword ptr [rsp+68h+dwOptions], rax; phkResult
0x1800219ff  call    cs:__imp_RegOpenKeyExW
0x180021a05  mov     ebx, eax
0x180021a07  test    eax, eax
0x180021a09  jnz     short loc_180021A36
0x180021a0b  mov     rcx, [rsp+68h+phkResult]; hKey
0x180021a10  lea     rax, [rsp+68h+Data]
0x180021a18  mov     r9d, 4; dwType
0x180021a1e  xor     r8d, r8d; Reserved
0x180021a21  mov     [rsp+68h+samDesired], r9d; cbData
0x180021a26  mov     rdx, rdi; lpValueName
0x180021a29  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180021a2e  call    cs:__imp_RegSetValueExW
0x180021a34  mov     ebx, eax
0x180021a36  mov     rcx, [rsp+68h+phkResult]; hKey
0x180021a3b  test    rcx, rcx
0x180021a3e  jz      short loc_180021A46
0x180021a40  call    cs:__imp_RegCloseKey
0x180021a46  mov     eax, ebx
0x180021a48  mov     rbx, [rsp+68h+arg_8]
0x180021a4d  add     rsp, 60h
0x180021a51  pop     rdi
0x180021a52  retn
```
