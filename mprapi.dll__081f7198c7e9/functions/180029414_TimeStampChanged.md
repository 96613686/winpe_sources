# TimeStampChanged

- ea: `0x180029414`
- end: `0x18002949d`
- name: `TimeStampChanged`
- size: `137`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002175c`
- `0x180022324`
- `0x180024530`
- `0x1800255a0`
- `0x180025880`
- `0x180025ac0`
- `0x180027da0`
- `0x1800281c0`
- `0x180028430`

## callees

- `0x180029414`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002946f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002946f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180029488`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180029488`

## pseudocode

```c
_BOOL8 __fastcall TimeStampChanged(HKEY a1, const FILETIME *a2)
{
  FILETIME FileTime1; // [rsp+80h] [rbp+18h] BYREF

  FileTime1 = 0;
  return !RegQueryInfoKeyW(a1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &FileTime1) && CompareFileTime(&FileTime1, a2) != 0;
}

```

## disassembly

```asm
0x180029414  mov     r11, rsp
0x180029417  push    rbx
0x180029418  sub     rsp, 60h
0x18002941c  lea     rax, [r11+18h]
0x180029420  mov     qword ptr [r11+18h], 0
0x180029428  mov     [r11-10h], rax
0x18002942c  mov     rbx, rdx
0x18002942f  mov     qword ptr [r11-18h], 0
0x180029437  xor     r9d, r9d; lpReserved
0x18002943a  mov     qword ptr [r11-20h], 0
0x180029442  xor     r8d, r8d; lpcchClass
0x180029445  mov     qword ptr [r11-28h], 0
0x18002944d  xor     edx, edx; lpClass
0x18002944f  mov     qword ptr [r11-30h], 0
0x180029457  mov     qword ptr [r11-38h], 0
0x18002945f  mov     qword ptr [r11-40h], 0
0x180029467  mov     qword ptr [r11-48h], 0
0x18002946f  call    cs:__imp_RegQueryInfoKeyW
0x180029475  test    eax, eax
0x180029477  jz      short loc_18002947D
0x180029479  xor     eax, eax
0x18002947b  jmp     short loc_180029497
0x18002947d  mov     rdx, rbx; lpFileTime2
0x180029480  lea     rcx, [rsp+68h+FileTime1]; lpFileTime1
0x180029488  call    cs:__imp_CompareFileTime
0x18002948e  xor     ecx, ecx
0x180029490  test    eax, eax
0x180029492  setnz   cl
0x180029495  mov     eax, ecx
0x180029497  add     rsp, 60h
0x18002949b  pop     rbx
0x18002949c  retn
```
