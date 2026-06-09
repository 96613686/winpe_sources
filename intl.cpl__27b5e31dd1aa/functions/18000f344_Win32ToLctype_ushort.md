# Win32ToLctype(ushort *)

- ea: `0x18000f344`
- end: `0x18000f3c9`
- name: `?Win32ToLctype@@YAKPEAG@Z`
- size: `133`
- prototype: `unsigned int __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c870`

## callees

- `0x18000f344`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000f3a4`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000f3a4`

## pseudocode

```c
__int64 __fastcall Win32ToLctype(LPCWCH lpString1)
{
  int i; // ebx

  for ( i = 0; i < 28; ++i )
  {
    if ( CompareStringEx(&LocaleName, 0x10u, lpString1, -1, (LPCWCH)(&WIN32_STRINGS)[i], -1, 0, 0, 0) == 2 )
      return (unsigned int)dword_1800308C0[i];
  }
  return 0;
}

```

## disassembly

```asm
0x18000f344  push    rbx
0x18000f346  push    rsi
0x18000f347  push    rdi
0x18000f348  push    r14
0x18000f34a  sub     rsp, 58h
0x18000f34e  mov     rsi, rcx
0x18000f351  lea     r14, cs:180000000h
0x18000f358  xor     ebx, ebx
0x18000f35a  cmp     ebx, 1Ch
0x18000f35d  jge     short loc_18000F3BD
0x18000f35f  mov     [rsp+78h+lParam], 0; lParam
0x18000f368  lea     rcx, LocaleName; lpLocaleName
0x18000f36f  mov     [rsp+78h+lpReserved], 0; lpReserved
0x18000f378  or      r9d, 0FFFFFFFFh; cchCount1
0x18000f37c  mov     [rsp+78h+lpVersionInformation], 0; lpVersionInformation
0x18000f385  mov     r8, rsi; lpString1
0x18000f388  movsxd  rdi, ebx
0x18000f38b  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000f393  lea     edx, [r9+11h]; dwCmpFlags
0x18000f397  mov     rax, ds:rva ?WIN32_STRINGS@@3PAPEBGA[r14+rdi*8]; ushort const * near * WIN32_STRINGS ...
0x18000f39f  mov     [rsp+78h+lpString2], rax; lpString2
0x18000f3a4  call    cs:__imp_CompareStringEx
0x18000f3aa  cmp     eax, 2
0x18000f3ad  jz      short loc_18000F3B3
0x18000f3af  inc     ebx
0x18000f3b1  jmp     short loc_18000F35A
0x18000f3b3  mov     eax, ds:rva dword_1800308C0[r14+rdi*4]
0x18000f3bb  jmp     short loc_18000F3BF
0x18000f3bd  xor     eax, eax
0x18000f3bf  add     rsp, 58h
0x18000f3c3  pop     r14
0x18000f3c5  pop     rdi
0x18000f3c6  pop     rsi
0x18000f3c7  pop     rbx
0x18000f3c8  retn
```
