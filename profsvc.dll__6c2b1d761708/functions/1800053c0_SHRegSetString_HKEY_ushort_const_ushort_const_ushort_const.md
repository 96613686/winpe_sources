# SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800053c0`
- end: `0x1800054c4`
- name: `?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `260`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004730`
- `0x180013db0`
- `0x18002d508`
- `0x180030628`
- `0x1800393f8`
- `0x18003a7d8`
- `0x180051820`

## callees

- `0x1800053c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800054b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800054b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000542c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000542c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000549a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000549a`

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
0x1800053c0  push    rbx
0x1800053c2  push    rbp
0x1800053c3  push    rdi
0x1800053c4  push    r14
0x1800053c6  sub     rsp, 68h
0x1800053ca  mov     rdi, r9
0x1800053cd  mov     r14, r8
0x1800053d0  mov     rbp, rcx
0x1800053d3  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800053da  nop     word ptr [rax+rax+00h]
0x1800053e0  inc     rbx
0x1800053e3  cmp     word ptr [r9+rbx*2], 0
0x1800053e9  jnz     short loc_1800053E0
0x1800053eb  mov     [rsp+88h+arg_0], rsi
0x1800053f3  cmp     rbx, 7FFFFFFFh
0x1800053fa  jnb     short loc_18000545D
0x1800053fc  xor     ecx, ecx
0x1800053fe  mov     [rsp+88h+hKey], rcx
0x180005403  test    rdx, rdx
0x180005406  jnz     short loc_18000546C
0x180005408  mov     rcx, rbp; hKey
0x18000540b  mov     [rsp+88h+hKey], rcx
0x180005410  lea     ebx, ds:2[rbx*2]
0x180005417  mov     r9d, 1; dwType
0x18000541d  mov     [rsp+88h+cbData], ebx; cbData
0x180005421  xor     r8d, r8d; Reserved
0x180005424  mov     rdx, r14; lpValueName
0x180005427  mov     [rsp+88h+lpData], rdi; lpData
0x18000542c  call    cs:__imp_RegSetValueExW
0x180005433  nop     dword ptr [rax+rax+00h]
0x180005438  mov     rcx, [rsp+88h+hKey]; hKey
0x18000543d  mov     esi, eax
0x18000543f  cmp     rcx, rbp
0x180005442  jnz     short loc_1800054B6
0x180005444  test    esi, esi
0x180005446  jg      short loc_180005462
0x180005448  mov     eax, esi
0x18000544a  mov     rsi, [rsp+88h+arg_0]
0x180005452  add     rsp, 68h
0x180005456  pop     r14
0x180005458  pop     rdi
0x180005459  pop     rbp
0x18000545a  pop     rbx
0x18000545b  retn
0x18000545d  mov     esi, 216h
0x180005462  movzx   eax, si
0x180005465  or      eax, 80070000h
0x18000546a  jmp     short loc_18000544A
0x18000546c  cmp     [rdx], cx
0x18000546f  jz      short loc_180005408
0x180005471  mov     [rsp+88h+lpdwDisposition], rcx; lpdwDisposition
0x180005476  lea     rax, [rsp+88h+hKey]
0x18000547b  mov     [rsp+88h+phkResult], rax; phkResult
0x180005480  xor     r9d, r9d; lpClass
0x180005483  mov     [rsp+88h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180005488  xor     r8d, r8d; Reserved
0x18000548b  mov     [rsp+88h+cbData], 2; samDesired
0x180005493  mov     dword ptr [rsp+88h+lpData], ecx; dwOptions
0x180005497  mov     rcx, rbp; hKey
0x18000549a  call    cs:__imp_RegCreateKeyExW
0x1800054a1  nop     dword ptr [rax+rax+00h]
0x1800054a6  mov     esi, eax
0x1800054a8  test    eax, eax
0x1800054aa  jnz     short loc_180005444
0x1800054ac  mov     rcx, [rsp+88h+hKey]
0x1800054b1  jmp     loc_180005410
0x1800054b6  call    cs:__imp_RegCloseKey
0x1800054bd  nop     dword ptr [rax+rax+00h]
0x1800054c2  jmp     short loc_180005444
```
