# ReadRegString(ushort const *,ushort const *,ulong,ushort *)

- ea: `0x18006e040`
- end: `0x18006e13d`
- name: `?ReadRegString@@YAJPEBG0KPEAG@Z`
- size: `253`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180038488`
- `0x18007d980`

## callees

- `0x18006e040`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e119`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801227af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e119`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801227af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006e0dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006e0dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e08c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e08c`

## pseudocode

```c
__int64 __fastcall ReadRegString(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int a3, BYTE *a4)
{
  int v7; // esi
  __int64 v8; // rdi
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  bool v11; // cc
  DWORD cbData; // [rsp+30h] [rbp-58h] BYREF
  DWORD Type; // [rsp+34h] [rbp-54h] BYREF
  int v15; // [rsp+38h] [rbp-50h]
  HKEY hKey; // [rsp+40h] [rbp-48h] BYREF

  Type = 0;
  v7 = 0;
  v15 = 0;
  cbData = 0;
  hKey = 0;
  v8 = 0;
  v9 = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v11 = v10 <= 0;
  if ( v10
    || (v7 = 1,
        v15 = 1,
        cbData = 2 * a3,
        v10 = RegQueryValueExW(hKey, lpValueName, 0, &Type, a4, &cbData),
        v11 = v10 <= 0,
        v10) )
  {
    if ( v11 )
      v9 = v10;
    else
      v9 = (unsigned __int16)v10 | 0x80070000;
  }
  else if ( Type == 1 && cbData >= 2 )
  {
    v8 = cbData >> 1;
    if ( (unsigned int)v8 >= a3 )
      v8 = a3 - 1;
  }
  else
  {
    v9 = -2147024883;
  }
  if ( v7 )
    RegCloseKey(hKey);
  *(_WORD *)&a4[2 * v8] = 0;
  return v9;
}

```

## disassembly

```asm
0x18006e040  mov     rax, rsp
0x18006e043  push    rbx
0x18006e044  push    rsi
0x18006e045  push    rdi
0x18006e046  push    r12
0x18006e048  push    r14
0x18006e04a  push    r15
0x18006e04c  sub     rsp, 58h
0x18006e050  mov     r12, r9
0x18006e053  mov     r14d, r8d
0x18006e056  mov     r15, rdx
0x18006e059  mov     dword ptr [rax-54h], 0
0x18006e060  xor     esi, esi
0x18006e062  mov     [rax-50h], esi
0x18006e065  mov     [rax-58h], esi
0x18006e068  mov     [rax-48h], rsi
0x18006e06c  xor     edi, edi
0x18006e06e  xor     ebx, ebx
0x18006e070  lea     rax, [rax-48h]
0x18006e074  mov     [rsp+88h+phkResult], rax; phkResult
0x18006e079  mov     r9d, 20019h; samDesired
0x18006e07f  xor     r8d, r8d; ulOptions
0x18006e082  mov     rdx, rcx; lpSubKey
0x18006e085  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e08c  call    cs:__imp_RegOpenKeyExW
0x18006e093  nop     dword ptr [rax+rax+00h]
0x18006e098  test    eax, eax
0x18006e09a  jz      short loc_18006E0AD
0x18006e09c  jg      short loc_18006E0A2
0x18006e09e  mov     ebx, eax
0x18006e0a0  jmp     short loc_18006E110
0x18006e0a2  movzx   ebx, ax
0x18006e0a5  or      ebx, 80070000h
0x18006e0ab  jmp     short loc_18006E110
0x18006e0ad  mov     esi, 1
0x18006e0b2  mov     [rsp+88h+var_50], esi
0x18006e0b6  lea     eax, [r14+r14]
0x18006e0ba  mov     [rsp+88h+cbData], eax
0x18006e0be  lea     rax, [rsp+88h+cbData]
0x18006e0c3  mov     [rsp+88h+lpcbData], rax; lpcbData
0x18006e0c8  mov     [rsp+88h+phkResult], r12; lpData
0x18006e0cd  lea     r9, [rsp+88h+Type]; lpType
0x18006e0d2  xor     r8d, r8d; lpReserved
0x18006e0d5  mov     rdx, r15; lpValueName
0x18006e0d8  mov     rcx, [rsp+88h+hKey]; hKey
0x18006e0dd  call    cs:__imp_RegQueryValueExW
0x18006e0e4  nop     dword ptr [rax+rax+00h]
0x18006e0e9  test    eax, eax
0x18006e0eb  jnz     short loc_18006E09C
0x18006e0ed  cmp     [rsp+88h+Type], esi
0x18006e0f1  jnz     short loc_18006E10B
0x18006e0f3  cmp     [rsp+88h+cbData], 2
0x18006e0f8  jb      short loc_18006E10B
0x18006e0fa  mov     edi, [rsp+88h+cbData]
0x18006e0fe  shr     edi, 1
0x18006e100  cmp     edi, r14d
0x18006e103  jb      short loc_18006E110
0x18006e105  lea     edi, [r14-1]
0x18006e109  jmp     short loc_18006E110
0x18006e10b  mov     ebx, 8007000Dh
0x18006e110  test    esi, esi
0x18006e112  jz      short loc_18006E125
0x18006e114  mov     rcx, [rsp+88h+hKey]; hKey
0x18006e119  call    cs:__imp_RegCloseKey
0x18006e120  nop     dword ptr [rax+rax+00h]
0x18006e125  xor     ecx, ecx
0x18006e127  mov     [r12+rdi*2], cx
0x18006e12c  mov     eax, ebx
0x18006e12e  add     rsp, 58h
0x18006e132  pop     r15
0x18006e134  pop     r14
0x18006e136  pop     r12
0x18006e138  pop     rdi
0x18006e139  pop     rsi
0x18006e13a  pop     rbx
0x18006e13b  retn
0x18012279c  push    rbp
0x18012279e  sub     rsp, 30h
0x1801227a2  mov     rbp, rdx
0x1801227a5  cmp     dword ptr [rbp+38h], 0
0x1801227a9  jz      short loc_1801227BC
0x1801227ab  mov     rcx, [rbp+40h]; hKey
0x1801227af  call    cs:__imp_RegCloseKey
0x1801227b6  nop     dword ptr [rax+rax+00h]
0x1801227bb  nop
0x1801227bc  add     rsp, 30h
0x1801227c0  pop     rbp
0x1801227c1  retn
```
