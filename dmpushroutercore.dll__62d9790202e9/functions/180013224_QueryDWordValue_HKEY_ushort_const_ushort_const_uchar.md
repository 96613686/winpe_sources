# QueryDWordValue(HKEY__ *,ushort const *,ushort const *,uchar * *)

- ea: `0x180013224`
- end: `0x1800132f5`
- name: `?QueryDWordValue@@YAJPEAUHKEY__@@PEBG1PEAPEAE@Z`
- size: `209`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180018060`

## callees

- `0x180013224`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001329e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001329e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001326b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001326b`

## pseudocode

```c
__int64 __fastcall QueryDWordValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, BYTE *a4)
{
  LSTATUS v7; // eax
  signed int v8; // ebx
  bool v9; // cc
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  cbData = 0;
  Type = 0;
  *(_QWORD *)a4 = 0;
  hKey = a1;
  if ( a2 )
  {
    v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
    v8 = v7;
    v9 = v7 <= 0;
    if ( v7 )
      goto LABEL_5;
    a1 = hKey;
  }
  cbData = 4;
  v7 = RegQueryValueExW(a1, a3, 0, &Type, a4, &cbData);
  v8 = v7;
  v9 = v7 <= 0;
  if ( !v7 )
  {
    v8 = 0;
    if ( Type == 4 )
      goto LABEL_12;
LABEL_11:
    v8 = 1;
    goto LABEL_12;
  }
LABEL_5:
  if ( !v9 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 < 0 && v8 != -2147024882 )
    goto LABEL_11;
LABEL_12:
  if ( hKey && a2 )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180013224  mov     rax, rsp
0x180013227  mov     [rax+18h], rbx
0x18001322b  push    rbp
0x18001322c  push    rsi
0x18001322d  push    rdi
0x18001322e  sub     rsp, 30h
0x180013232  mov     dword ptr [rax+8], 0
0x180013239  mov     rsi, r9
0x18001323c  mov     dword ptr [rax+10h], 0
0x180013243  mov     rbp, r8
0x180013246  mov     qword ptr [r9], 0
0x18001324d  mov     rdi, rdx
0x180013250  mov     [rax+20h], rcx
0x180013254  test    rdx, rdx
0x180013257  jz      short loc_18001327C
0x180013259  lea     rax, [rax+20h]
0x18001325d  mov     r9d, 20019h; samDesired
0x180013263  xor     r8d, r8d; ulOptions
0x180013266  mov     [rsp+48h+phkResult], rax; phkResult
0x18001326b  call    cs:__imp_RegOpenKeyExW
0x180013271  mov     ebx, eax
0x180013273  test    eax, eax
0x180013275  jnz     short loc_1800132AA
0x180013277  mov     rcx, [rsp+48h+hKey]; hKey
0x18001327c  lea     rax, [rsp+48h+cbData]
0x180013281  mov     [rsp+48h+cbData], 4
0x180013289  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001328e  lea     r9, [rsp+48h+Type]; lpType
0x180013293  xor     r8d, r8d; lpReserved
0x180013296  mov     [rsp+48h+phkResult], rsi; lpData
0x18001329b  mov     rdx, rbp; lpValueName
0x18001329e  call    cs:__imp_RegQueryValueExW
0x1800132a4  mov     ebx, eax
0x1800132a6  test    eax, eax
0x1800132a8  jz      short loc_1800132C3
0x1800132aa  jle     short loc_1800132B5
0x1800132ac  movzx   ebx, ax
0x1800132af  or      ebx, 80070000h
0x1800132b5  test    ebx, ebx
0x1800132b7  jns     short loc_1800132D1
0x1800132b9  cmp     ebx, 8007000Eh
0x1800132bf  jnz     short loc_1800132CC
0x1800132c1  jmp     short loc_1800132D1
0x1800132c3  xor     ebx, ebx
0x1800132c5  cmp     [rsp+48h+Type], 4
0x1800132ca  jz      short loc_1800132D1
0x1800132cc  mov     ebx, 1
0x1800132d1  mov     rcx, [rsp+48h+hKey]; hKey
0x1800132d6  test    rcx, rcx
0x1800132d9  jz      short loc_1800132E6
0x1800132db  test    rdi, rdi
0x1800132de  jz      short loc_1800132E6
0x1800132e0  call    cs:__imp_RegCloseKey
0x1800132e6  mov     eax, ebx
0x1800132e8  mov     rbx, [rsp+48h+arg_10]
0x1800132ed  add     rsp, 30h
0x1800132f1  pop     rdi
0x1800132f2  pop     rsi
0x1800132f3  pop     rbp
0x1800132f4  retn
```
