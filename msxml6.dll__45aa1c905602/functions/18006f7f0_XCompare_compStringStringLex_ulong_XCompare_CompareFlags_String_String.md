# XCompare::compStringStringLex(ulong,XCompare::CompareFlags,String *,String *)

- ea: `0x18006f7f0`
- end: `0x18006f886`
- name: `?compStringStringLex@XCompare@@SAHKW4CompareFlags@1@PEAVString@@1@Z`
- size: `150`
- prototype: `int __fastcall(unsigned int lcid, XCompare::CompareFlags flags, String *str1, String *str2)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006f790`
- `0x180117e70`

## callees

- `0x18006f7f0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006f833`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006f867`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006f833`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006f867`

## pseudocode

```c
__int64 __fastcall XCompare::compStringStringLex(LCID lcid, XCompare::CompareFlags flags, String *str1, String *str2)
{
  char v4; // bl
  DWORD v6; // edx
  unsigned int v9; // ecx

  v4 = flags;
  v6 = 0;
  if ( (v4 & 0x18) != 0 )
    v6 = (v4 & 8) != 0 ? 196609 : 1;
  v9 = CompareStringW(lcid, v6, str1->_pwsz, str1->_length, str2->_pwsz, str2->_length) - 2;
  if ( (v4 & 0x10) != 0 && !v9 )
    return (unsigned int)(2 - CompareStringW(lcid, 0, str1->_pwsz, str1->_length, str2->_pwsz, str2->_length));
  return v9;
}

```

## disassembly

```asm
0x18006f7f0  push    rbx
0x18006f7f2  push    rbp
0x18006f7f3  push    rsi
0x18006f7f4  push    rdi
0x18006f7f5  sub     rsp, 38h
0x18006f7f9  mov     ebx, flags
0x18006f7fb  mov     rdi, str2
0x18006f7fe  xor     flags, flags
0x18006f800  mov     rsi, str1
0x18006f803  mov     ebp, lcid
0x18006f805  test    bl, 18h
0x18006f808  jz      short loc_18006F81A
0x18006f80a  mov     al, bl
0x18006f80c  and     al, 8
0x18006f80e  neg     al
0x18006f810  sbb     flags, flags
0x18006f812  and     flags, 30000h
0x18006f818  inc     flags; dwCmpFlags
0x18006f81a  mov     eax, [str2+10h]
0x18006f81e  mov     [rsp+58h+cchCount2], eax; cchCount2
0x18006f822  mov     rax, [str2+18h]
0x18006f826  mov     r9d, [str1+10h]; cchCount1
0x18006f82a  mov     str1, [str1+18h]; lpString1
0x18006f82e  mov     [rsp+58h+lpString2], rax; lpString2
0x18006f833  call    cs:__imp_CompareStringW
0x18006f83a  nop     dword ptr [rax+rax+00h]
0x18006f83f  lea     lcid, [rax-2]
0x18006f842  test    bl, 10h
0x18006f845  jz      short loc_18006F87A
0x18006f847  test    lcid, lcid
0x18006f849  jnz     short loc_18006F87A
0x18006f84b  mov     eax, [rdi+10h]
0x18006f84e  xor     flags, flags; dwCmpFlags
0x18006f850  mov     r9d, [rsi+10h]; cchCount1
0x18006f854  mov     lcid, ebp; Locale
0x18006f856  mov     str1, [rsi+18h]; lpString1
0x18006f85a  mov     [rsp+58h+cchCount2], eax; cchCount2
0x18006f85e  mov     rax, [rdi+18h]
0x18006f862  mov     [rsp+58h+lpString2], rax; lpString2
0x18006f867  call    cs:__imp_CompareStringW
0x18006f86e  nop     dword ptr [rax+rax+00h]
0x18006f873  mov     lcid, 2
0x18006f878  sub     lcid, eax
0x18006f87a  mov     eax, lcid
0x18006f87c  add     rsp, 38h
0x18006f880  pop     rdi
0x18006f881  pop     rsi
0x18006f882  pop     rbp
0x18006f883  pop     rbx
0x18006f884  retn
```
