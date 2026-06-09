# DetermineProfileTypeFromFile

- ea: `0x18003ff94`
- end: `0x180040120`
- name: `DetermineProfileTypeFromFile`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002435c`

## callees

- `0x18003d8c8`
- `0x18003ff94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040109`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040109`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180040020`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004004f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004009b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800400c6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800400f1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180040020`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004004f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004009b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800400c6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800400f1`

## pseudocode

```c
__int64 __fastcall DetermineProfileTypeFromFile(const unsigned __int16 *a1, _DWORD *a2)
{
  int v4; // eax
  DWORD v5; // ecx
  unsigned __int64 v6; // rsi
  unsigned int v7; // ebx
  unsigned __int64 v8; // r14
  const WCHAR *v9; // rsi
  unsigned __int64 v11; // [rsp+80h] [rbp+18h] BYREF

  v11 = 0;
  v4 = StringCchLengthW(a1, 0x104u, &v11);
  if ( v4 < 0 )
  {
    if ( (v4 & 0x1FFF0000) == 0x70000 )
      v4 = (unsigned __int16)v4;
    v5 = v4;
    goto LABEL_17;
  }
  v6 = v11;
  v7 = 1;
  if ( v11 < 4
    || (v8 = v11, CompareStringW(0x7Fu, 1u, &a1[v11 - 4], 4, L".ICC", 4) != 2)
    && CompareStringW(0x7Fu, 1u, &a1[v8 - 4], 4, L".ICM", 4) != 2 )
  {
    if ( v6 >= 5 )
    {
      v9 = &a1[v6 - 5];
      if ( CompareStringW(0x7Fu, 1u, v9, 5, L".CDMP", 5) == 2 )
      {
        *a2 = 1;
        return v7;
      }
      if ( CompareStringW(0x7Fu, 1u, v9, 5, L".CAMP", 5) == 2 )
      {
        *a2 = 2;
        return v7;
      }
      if ( CompareStringW(0x7Fu, 1u, v9, 5, L".GMMP", 5) == 2 )
      {
        *a2 = 3;
        return v7;
      }
    }
    v5 = 87;
LABEL_17:
    SetLastError(v5);
    return 0;
  }
  *a2 = 0;
  return v7;
}

```

## disassembly

```asm
0x18003ff94  mov     rax, rsp
0x18003ff97  push    rbx
0x18003ff98  push    rbp
0x18003ff99  push    rsi
0x18003ff9a  push    rdi
0x18003ff9b  push    r13
0x18003ff9d  push    r14
0x18003ff9f  sub     rsp, 38h
0x18003ffa3  mov     rdi, rdx
0x18003ffa6  mov     qword ptr [rax+18h], 0
0x18003ffae  mov     edx, 104h; unsigned __int64
0x18003ffb3  lea     r8, [rax+18h]; unsigned __int64 *
0x18003ffb7  mov     rbp, rcx
0x18003ffba  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003ffbf  test    eax, eax
0x18003ffc1  jns     short loc_18003FFDD
0x18003ffc3  mov     ecx, eax
0x18003ffc5  and     ecx, 1FFF0000h
0x18003ffcb  cmp     ecx, 70000h
0x18003ffd1  jnz     short loc_18003FFD6
0x18003ffd3  movzx   eax, ax
0x18003ffd6  mov     ecx, eax
0x18003ffd8  jmp     loc_180040109
0x18003ffdd  mov     rsi, [rsp+68h+arg_10]
0x18003ffe5  mov     ebx, 1
0x18003ffea  lea     r13d, [rbx+7Eh]
0x18003ffee  cmp     rsi, 4
0x18003fff2  jb      short loc_180040065
0x18003fff4  lea     rax, String2; ".ICC"
0x18003fffb  mov     [rsp+68h+cchCount2], 4; cchCount2
0x180040003  lea     r14, ds:0[rsi*2]
0x18004000b  mov     [rsp+68h+lpString2], rax; lpString2
0x180040010  lea     r8, [r14-8]
0x180040014  mov     edx, ebx; dwCmpFlags
0x180040016  add     r8, rbp; lpString1
0x180040019  lea     r9d, [rbx+3]; cchCount1
0x18004001d  mov     ecx, r13d; Locale
0x180040020  call    cs:__imp_CompareStringW
0x180040026  cmp     eax, 2
0x180040029  jz      short loc_18004005A
0x18004002b  lea     rax, aIcm; ".ICM"
0x180040032  mov     [rsp+68h+cchCount2], 4; cchCount2
0x18004003a  lea     r8, [rbp-8]
0x18004003e  mov     [rsp+68h+lpString2], rax; lpString2
0x180040043  add     r8, r14; lpString1
0x180040046  lea     r9d, [rbx+3]; cchCount1
0x18004004a  mov     edx, ebx; dwCmpFlags
0x18004004c  mov     ecx, r13d; Locale
0x18004004f  call    cs:__imp_CompareStringW
0x180040055  cmp     eax, 2
0x180040058  jnz     short loc_180040065
0x18004005a  mov     dword ptr [rdi], 0
0x180040060  jmp     loc_180040111
0x180040065  mov     r14d, 5
0x18004006b  cmp     rsi, r14
0x18004006e  jb      loc_180040104
0x180040074  lea     rax, aCdmp; ".CDMP"
0x18004007b  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x180040080  lea     rsi, ds:0FFFFFFFFFFFFFFF6h[rsi*2]
0x180040088  mov     [rsp+68h+lpString2], rax; lpString2
0x18004008d  add     rsi, rbp
0x180040090  mov     r9d, r14d; cchCount1
0x180040093  mov     r8, rsi; lpString1
0x180040096  mov     edx, ebx; dwCmpFlags
0x180040098  mov     ecx, r13d; Locale
0x18004009b  call    cs:__imp_CompareStringW
0x1800400a1  cmp     eax, 2
0x1800400a4  jnz     short loc_1800400AA
0x1800400a6  mov     [rdi], ebx
0x1800400a8  jmp     short loc_180040111
0x1800400aa  lea     rax, aCamp; ".CAMP"
0x1800400b1  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x1800400b6  mov     r9d, r14d; cchCount1
0x1800400b9  mov     [rsp+68h+lpString2], rax; lpString2
0x1800400be  mov     r8, rsi; lpString1
0x1800400c1  mov     edx, ebx; dwCmpFlags
0x1800400c3  mov     ecx, r13d; Locale
0x1800400c6  call    cs:__imp_CompareStringW
0x1800400cc  cmp     eax, 2
0x1800400cf  jnz     short loc_1800400D5
0x1800400d1  mov     [rdi], eax
0x1800400d3  jmp     short loc_180040111
0x1800400d5  lea     rax, aGmmp; ".GMMP"
0x1800400dc  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x1800400e1  mov     r9d, r14d; cchCount1
0x1800400e4  mov     [rsp+68h+lpString2], rax; lpString2
0x1800400e9  mov     r8, rsi; lpString1
0x1800400ec  mov     edx, ebx; dwCmpFlags
0x1800400ee  mov     ecx, r13d; Locale
0x1800400f1  call    cs:__imp_CompareStringW
0x1800400f7  cmp     eax, 2
0x1800400fa  jnz     short loc_180040104
0x1800400fc  mov     dword ptr [rdi], 3
0x180040102  jmp     short loc_180040111
0x180040104  mov     ecx, 57h ; 'W'; dwErrCode
0x180040109  call    cs:__imp_SetLastError
0x18004010f  xor     ebx, ebx
0x180040111  mov     eax, ebx
0x180040113  add     rsp, 38h
0x180040117  pop     r14
0x180040119  pop     r13
0x18004011b  pop     rdi
0x18004011c  pop     rsi
0x18004011d  pop     rbp
0x18004011e  pop     rbx
0x18004011f  retn
```
