# FrameworkToLctype(ushort *)

- ea: `0x18000cf94`
- end: `0x18000d019`
- name: `?FrameworkToLctype@@YAKPEAG@Z`
- size: `133`
- prototype: `unsigned int __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c870`

## callees

- `0x18000cf94`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000cff4`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000cff4`

## pseudocode

```c
__int64 __fastcall FrameworkToLctype(LPCWCH lpString1)
{
  int i; // ebx

  for ( i = 0; i < 28; ++i )
  {
    if ( CompareStringEx(&LocaleName, 0x10u, lpString1, -1, (LPCWCH)(&FRAMEWORK_STRINGS)[i], -1, 0, 0, 0) == 2 )
      return (unsigned int)dword_1800308C0[i];
  }
  return 0;
}

```

## disassembly

```asm
0x18000cf94  push    rbx
0x18000cf96  push    rsi
0x18000cf97  push    rdi
0x18000cf98  push    r14
0x18000cf9a  sub     rsp, 58h
0x18000cf9e  mov     rsi, rcx
0x18000cfa1  lea     r14, cs:180000000h
0x18000cfa8  xor     ebx, ebx
0x18000cfaa  cmp     ebx, 1Ch
0x18000cfad  jge     short loc_18000D00D
0x18000cfaf  mov     [rsp+78h+lParam], 0; lParam
0x18000cfb8  lea     rcx, LocaleName; lpLocaleName
0x18000cfbf  mov     [rsp+78h+lpReserved], 0; lpReserved
0x18000cfc8  or      r9d, 0FFFFFFFFh; cchCount1
0x18000cfcc  mov     [rsp+78h+lpVersionInformation], 0; lpVersionInformation
0x18000cfd5  mov     r8, rsi; lpString1
0x18000cfd8  movsxd  rdi, ebx
0x18000cfdb  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000cfe3  lea     edx, [r9+11h]; dwCmpFlags
0x18000cfe7  mov     rax, ds:rva ?FRAMEWORK_STRINGS@@3PAPEBGA[r14+rdi*8]; ushort const * near * FRAMEWORK_STRINGS ...
0x18000cfef  mov     [rsp+78h+lpString2], rax; lpString2
0x18000cff4  call    cs:__imp_CompareStringEx
0x18000cffa  cmp     eax, 2
0x18000cffd  jz      short loc_18000D003
0x18000cfff  inc     ebx
0x18000d001  jmp     short loc_18000CFAA
0x18000d003  mov     eax, ds:rva dword_1800308C0[r14+rdi*4]
0x18000d00b  jmp     short loc_18000D00F
0x18000d00d  xor     eax, eax
0x18000d00f  add     rsp, 58h
0x18000d013  pop     r14
0x18000d015  pop     rdi
0x18000d016  pop     rsi
0x18000d017  pop     rbx
0x18000d018  retn
```
