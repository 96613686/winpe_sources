# UnLoadFMIFS(FMIFSLib *)

- ea: `0x180002558`
- end: `0x1800025ee`
- name: `?UnLoadFMIFS@@YAJPEAUFMIFSLib@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(struct FMIFSLib *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e20`
- `0x180002280`

## callees

- `0x180002558`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000257a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000257a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002570`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002570`

## pseudocode

```c
signed int __fastcall UnLoadFMIFS(struct FMIFSLib *a1)
{
  signed int result; // eax

  if ( !a1 )
    return -2147024809;
  if ( FreeLibrary(*(HMODULE *)a1) )
  {
    *((_QWORD *)a1 + 1) = 0;
    result = 0;
    *((_QWORD *)a1 + 2) = 0;
    *((_QWORD *)a1 + 3) = 0;
    *((_QWORD *)a1 + 4) = 0;
    *((_QWORD *)a1 + 5) = 0;
    *((_QWORD *)a1 + 6) = 0;
    *((_QWORD *)a1 + 8) = 0;
    *((_QWORD *)a1 + 9) = 0;
    *((_QWORD *)a1 + 10) = 0;
    *((_QWORD *)a1 + 11) = 0;
    *((_QWORD *)a1 + 12) = 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180002558  push    rbx
0x18000255a  sub     rsp, 20h
0x18000255e  mov     rbx, rcx
0x180002561  test    rcx, rcx
0x180002564  jnz     short loc_18000256D
0x180002566  mov     eax, 80070057h
0x18000256b  jmp     short loc_1800025E8
0x18000256d  mov     rcx, [rcx]; hLibModule
0x180002570  call    cs:__imp_FreeLibrary
0x180002576  test    eax, eax
0x180002578  jnz     short loc_18000258E
0x18000257a  call    cs:__imp_GetLastError
0x180002580  test    eax, eax
0x180002582  jle     short loc_1800025E8
0x180002584  movzx   eax, ax
0x180002587  or      eax, 80070000h
0x18000258c  jmp     short loc_1800025E8
0x18000258e  mov     qword ptr [rbx+8], 0
0x180002596  xor     eax, eax
0x180002598  mov     qword ptr [rbx+10h], 0
0x1800025a0  mov     qword ptr [rbx+18h], 0
0x1800025a8  mov     qword ptr [rbx+20h], 0
0x1800025b0  mov     qword ptr [rbx+28h], 0
0x1800025b8  mov     qword ptr [rbx+30h], 0
0x1800025c0  mov     qword ptr [rbx+40h], 0
0x1800025c8  mov     qword ptr [rbx+48h], 0
0x1800025d0  mov     qword ptr [rbx+50h], 0
0x1800025d8  mov     qword ptr [rbx+58h], 0
0x1800025e0  mov     qword ptr [rbx+60h], 0
0x1800025e8  add     rsp, 20h
0x1800025ec  pop     rbx
0x1800025ed  retn
```
