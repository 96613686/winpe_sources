# aesUtf8StringFromUnicodeString

- ea: `0x180006530`
- end: `0x180006633`
- name: `aesUtf8StringFromUnicodeString`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005eac`

## callees

- `0x180006530`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006558`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800065c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006558`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800065c5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180006597`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180006607`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180006597`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180006607`

## pseudocode

```c
__int64 __fastcall aesUtf8StringFromUnicodeString(unsigned __int16 *a1, __int64 a2)
{
  HLOCAL v4; // rax
  unsigned __int16 v6; // ax
  unsigned __int16 v7; // ax
  CHAR *lpMultiByteStr; // rax
  __int16 v9; // ax

  if ( !*a1 )
  {
    *(_DWORD *)a2 = 0x10000;
    v4 = LocalAlloc(0x40u, 1u);
    *(_QWORD *)(a2 + 8) = v4;
    if ( v4 )
      return 0;
    return 3221225495LL;
  }
  v6 = WideCharToMultiByte(0xFDE9u, 0, *((LPCWCH *)a1 + 1), *a1 >> 1, *(LPSTR *)(a2 + 8), 0, 0, 0);
  if ( !v6 )
    return 3221225626LL;
  if ( v6 > 0xFFFDu )
    return 3221225734LL;
  *(_WORD *)a2 = v6;
  v7 = v6 + 1;
  *(_WORD *)(a2 + 2) = v7;
  lpMultiByteStr = (CHAR *)LocalAlloc(0x40u, v7);
  *(_QWORD *)(a2 + 8) = lpMultiByteStr;
  if ( !lpMultiByteStr )
    return 3221225495LL;
  v9 = WideCharToMultiByte(
         0xFDE9u,
         0,
         *((LPCWCH *)a1 + 1),
         *a1 >> 1,
         lpMultiByteStr,
         *(unsigned __int16 *)(a2 + 2),
         0,
         0);
  *(_WORD *)a2 = v9;
  return v9 == 0 ? 0xC000009A : 0;
}

```

## disassembly

```asm
0x180006530  mov     [rsp+arg_0], rbx
0x180006535  mov     [rsp+arg_8], rsi
0x18000653a  push    rdi
0x18000653b  sub     rsp, 40h
0x18000653f  xor     esi, esi
0x180006541  mov     rbx, rdx
0x180006544  mov     rdi, rcx
0x180006547  cmp     [rcx], si
0x18000654a  jnz     short loc_18000656E
0x18000654c  mov     dword ptr [rdx], 10000h
0x180006552  lea     ecx, [rsi+40h]; uFlags
0x180006555  lea     edx, [rsi+1]; uBytes
0x180006558  call    cs:__imp_LocalAlloc
0x18000655e  mov     [rbx+8], rax
0x180006562  test    rax, rax
0x180006565  jz      short loc_1800065D7
0x180006567  xor     eax, eax
0x180006569  jmp     loc_180006623
0x18000656e  movzx   r9d, word ptr [rcx]
0x180006572  mov     rax, [rdx+8]
0x180006576  xor     edx, edx; dwFlags
0x180006578  mov     r8, [rcx+8]; lpWideCharStr
0x18000657c  mov     ecx, 0FDE9h; CodePage
0x180006581  mov     [rsp+48h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x180006586  mov     [rsp+48h+lpDefaultChar], rsi; lpDefaultChar
0x18000658b  shr     r9d, 1; cchWideChar
0x18000658e  mov     [rsp+48h+cbMultiByte], esi; cbMultiByte
0x180006592  mov     [rsp+48h+lpMultiByteStr], rax; lpMultiByteStr
0x180006597  call    cs:__imp_WideCharToMultiByte
0x18000659d  test    ax, ax
0x1800065a0  jz      short loc_18000661E
0x1800065a2  mov     ecx, 0FFFDh
0x1800065a7  cmp     ax, cx
0x1800065aa  jbe     short loc_1800065B3
0x1800065ac  mov     eax, 0C0000106h
0x1800065b1  jmp     short loc_180006623
0x1800065b3  mov     [rbx], ax
0x1800065b6  mov     ecx, 40h ; '@'; uFlags
0x1800065bb  inc     ax
0x1800065be  movzx   edx, ax; uBytes
0x1800065c1  mov     [rbx+2], dx
0x1800065c5  call    cs:__imp_LocalAlloc
0x1800065cb  mov     [rbx+8], rax
0x1800065cf  mov     rcx, rax
0x1800065d2  test    rax, rax
0x1800065d5  jnz     short loc_1800065DE
0x1800065d7  mov     eax, 0C0000017h
0x1800065dc  jmp     short loc_180006623
0x1800065de  movzx   eax, word ptr [rbx+2]
0x1800065e2  xor     edx, edx; dwFlags
0x1800065e4  movzx   r9d, word ptr [rdi]
0x1800065e8  mov     r8, [rdi+8]; lpWideCharStr
0x1800065ec  mov     [rsp+48h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x1800065f1  mov     [rsp+48h+lpDefaultChar], rsi; lpDefaultChar
0x1800065f6  mov     [rsp+48h+cbMultiByte], eax; cbMultiByte
0x1800065fa  mov     [rsp+48h+lpMultiByteStr], rcx; lpMultiByteStr
0x1800065ff  mov     ecx, 0FDE9h; CodePage
0x180006604  shr     r9d, 1; cchWideChar
0x180006607  call    cs:__imp_WideCharToMultiByte
0x18000660d  mov     [rbx], ax
0x180006610  neg     ax
0x180006613  sbb     eax, eax
0x180006615  not     eax
0x180006617  and     eax, 0C000009Ah
0x18000661c  jmp     short loc_180006623
0x18000661e  mov     eax, 0C000009Ah
0x180006623  mov     rbx, [rsp+48h+arg_0]
0x180006628  mov     rsi, [rsp+48h+arg_8]
0x18000662d  add     rsp, 40h
0x180006631  pop     rdi
0x180006632  retn
```
