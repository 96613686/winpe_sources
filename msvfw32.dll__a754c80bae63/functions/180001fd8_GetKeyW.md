# GetKeyW

- ea: `0x180001fd8`
- end: `0x180002110`
- name: `GetKeyW`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000241c`
- `0x18000be48`

## callees

- `0x1800014b0`
- `0x180001fd8`
- `0x180002198`
- `0x180002280`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180002095`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180002095`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800020e0`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800020e0`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18000200d`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18000200d`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x1800020af`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x1800020af`

## pseudocode

```c
HKEY __fastcall GetKeyW(__int64 a1, _DWORD *a2, int a3)
{
  ATOM AtomW; // dx
  unsigned int i; // ecx
  unsigned int v8; // r11d
  LSTATUS KeyW; // eax
  ATOM v10; // ax
  __int64 v11; // rdx
  HKEY phkResult[2]; // [rsp+20h] [rbp-258h] BYREF
  wchar_t pszDest[264]; // [rsp+30h] [rbp-248h] BYREF

  phkResult[0] = 0;
  *a2 = 0;
  AtomW = FindAtomW(L"DrawDib");
  if ( AtomW )
  {
    for ( i = 0; i < keyscached; ++i )
    {
      if ( akeyatoms[i] == AtomW )
        return (HKEY)ahkey[i];
    }
  }
  StringCchCopyW(pszDest, 0x104u, L"Software\\Microsoft\\Multimedia\\");
  if ( StringCchCatW(pszDest, v8, L"DrawDib") < 0 )
    return 0;
  if ( a3 )
    KeyW = RegCreateKeyW(HKEY_CURRENT_USER, pszDest, phkResult);
  else
    KeyW = RegOpenKeyW(HKEY_CURRENT_USER, pszDest, phkResult);
  if ( !KeyW )
  {
    if ( (unsigned int)keyscached < 2 && (v10 = AddAtomW(L"DrawDib")) != 0 )
    {
      v11 = (unsigned int)keyscached;
      akeyatoms[keyscached] = v10;
      ahkey[v11] = (__int64)phkResult[0];
      keyscached = v11 + 1;
    }
    else
    {
      *a2 = 1;
    }
  }
  return phkResult[0];
}

```

## disassembly

```asm
0x180001fd8  push    rbx
0x180001fda  push    rsi
0x180001fdb  push    rdi
0x180001fdc  push    r14
0x180001fde  sub     rsp, 258h
0x180001fe5  mov     rax, cs:__security_cookie
0x180001fec  xor     rax, rsp
0x180001fef  mov     [rsp+278h+var_38], rax
0x180001ff7  xor     esi, esi
0x180001ff9  lea     rcx, aDrawdib; "DrawDib"
0x180002000  mov     [rsp+278h+phkResult], rsi
0x180002005  mov     edi, r8d
0x180002008  mov     [rdx], esi
0x18000200a  mov     rbx, rdx
0x18000200d  call    cs:__imp_FindAtomW
0x180002013  lea     r14, cs:180000000h
0x18000201a  movzx   edx, ax
0x18000201d  test    ax, ax
0x180002020  jz      short loc_18000204A
0x180002022  mov     ecx, esi
0x180002024  cmp     ecx, cs:keyscached
0x18000202a  jnb     short loc_18000204A
0x18000202c  mov     eax, ecx
0x18000202e  cmp     rva akeyatoms[r14+rax*2], dx
0x180002037  jz      short loc_18000203D
0x180002039  inc     ecx
0x18000203b  jmp     short loc_180002024
0x18000203d  mov     rax, rva ahkey[r14+rax*8]
0x180002045  jmp     loc_1800020F3
0x18000204a  mov     r11d, 104h
0x180002050  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Multimedia\\"
0x180002057  mov     edx, r11d; cchDest
0x18000205a  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18000205f  call    StringCchCopyW
0x180002064  lea     r8, aDrawdib; "DrawDib"
0x18000206b  mov     edx, r11d; cchDest
0x18000206e  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180002073  call    StringCchCatW
0x180002078  test    eax, eax
0x18000207a  jns     short loc_180002080
0x18000207c  xor     eax, eax
0x18000207e  jmp     short loc_1800020F3
0x180002080  lea     r8, [rsp+278h+phkResult]; phkResult
0x180002085  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000208c  lea     rdx, [rsp+278h+pszDest]; lpSubKey
0x180002091  test    edi, edi
0x180002093  jnz     short loc_1800020E0
0x180002095  call    cs:__imp_RegOpenKeyW
0x18000209b  test    eax, eax
0x18000209d  jnz     short loc_1800020EE
0x18000209f  cmp     cs:keyscached, 2
0x1800020a6  jnb     short loc_1800020E8
0x1800020a8  lea     rcx, aDrawdib; "DrawDib"
0x1800020af  call    cs:__imp_AddAtomW
0x1800020b5  test    ax, ax
0x1800020b8  jz      short loc_1800020E8
0x1800020ba  mov     edx, cs:keyscached
0x1800020c0  mov     rva akeyatoms[r14+rdx*2], ax
0x1800020c9  mov     rax, [rsp+278h+phkResult]
0x1800020ce  mov     rva ahkey[r14+rdx*8], rax
0x1800020d6  inc     edx
0x1800020d8  mov     cs:keyscached, edx
0x1800020de  jmp     short loc_1800020EE
0x1800020e0  call    cs:__imp_RegCreateKeyW
0x1800020e6  jmp     short loc_18000209B
0x1800020e8  mov     dword ptr [rbx], 1
0x1800020ee  mov     rax, [rsp+278h+phkResult]
0x1800020f3  mov     rcx, [rsp+278h+var_38]
0x1800020fb  xor     rcx, rsp; StackCookie
0x1800020fe  call    __security_check_cookie
0x180002103  add     rsp, 258h
0x18000210a  pop     r14
0x18000210c  pop     rdi
0x18000210d  pop     rsi
0x18000210e  pop     rbx
0x18000210f  retn
```
