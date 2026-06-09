# ConvertStringToType(ushort *)

- ea: `0x180001afc`
- end: `0x180001b89`
- name: `?ConvertStringToType@@YAKPEAG@Z`
- size: `141`
- prototype: `unsigned int __fastcall(wchar_t *String1)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000224c`
- `0x18000283c`
- `0x180002b90`
- `0x180002d14`

## callees

- `0x180001afc`
- `0x18000361d`

## pseudocode

```c
__int64 __fastcall ConvertStringToType(wchar_t *String1)
{
  if ( !wcscmp_0(String1, L"REG_DWORD") )
    return 4;
  if ( !wcscmp_0(String1, L"REG_SZ") )
    return 1;
  if ( !wcscmp_0(String1, L"REG_EXPAND_SZ") )
    return 2;
  if ( !wcscmp_0(String1, L"REG_MULTI_SZ") )
    return 7;
  return wcscmp_0(String1, L"REG_BINARY") != 0 ? -1 : 3;
}

```

## disassembly

```asm
0x180001afc  push    rbx
0x180001afe  sub     rsp, 20h
0x180001b02  lea     rdx, aRegDword; "REG_DWORD"
0x180001b09  mov     rbx, rcx
0x180001b0c  call    wcscmp_0
0x180001b11  test    eax, eax
0x180001b13  jnz     short loc_180001B1C
0x180001b15  mov     eax, 4
0x180001b1a  jmp     short loc_180001B83
0x180001b1c  lea     rdx, aRegSz; "REG_SZ"
0x180001b23  mov     rcx, rbx; String1
0x180001b26  call    wcscmp_0
0x180001b2b  test    eax, eax
0x180001b2d  jnz     short loc_180001B36
0x180001b2f  mov     eax, 1
0x180001b34  jmp     short loc_180001B83
0x180001b36  lea     rdx, aRegExpandSz; "REG_EXPAND_SZ"
0x180001b3d  mov     rcx, rbx; String1
0x180001b40  call    wcscmp_0
0x180001b45  test    eax, eax
0x180001b47  jnz     short loc_180001B50
0x180001b49  mov     eax, 2
0x180001b4e  jmp     short loc_180001B83
0x180001b50  lea     rdx, aRegMultiSz; "REG_MULTI_SZ"
0x180001b57  mov     rcx, rbx; String1
0x180001b5a  call    wcscmp_0
0x180001b5f  test    eax, eax
0x180001b61  jnz     short loc_180001B6A
0x180001b63  mov     eax, 7
0x180001b68  jmp     short loc_180001B83
0x180001b6a  lea     rdx, aRegBinary; "REG_BINARY"
0x180001b71  mov     rcx, rbx; String1
0x180001b74  call    wcscmp_0
0x180001b79  neg     eax
0x180001b7b  sbb     eax, eax
0x180001b7d  and     eax, 0FFFFFFFCh
0x180001b80  add     eax, 3
0x180001b83  add     rsp, 20h
0x180001b87  pop     rbx
0x180001b88  retn
```
