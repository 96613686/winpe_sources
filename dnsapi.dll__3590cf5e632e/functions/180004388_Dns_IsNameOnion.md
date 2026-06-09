# Dns_IsNameOnion

- ea: `0x180004388`
- end: `0x180004447`
- name: `Dns_IsNameOnion`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004164`

## callees

- `0x180004388`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800043a0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800043a0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800043ea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000441d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800043ea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000441d`

## pseudocode

```c
__int64 __fastcall Dns_IsNameOnion(const wchar_t *a1)
{
  const WCHAR *i; // rbx
  wchar_t *v2; // rax
  unsigned int v3; // edi

  for ( i = 0; ; i = v2 + 1 )
  {
    v2 = wcschr(a1, 0x2Eu);
    if ( !v2 )
      break;
    a1 = v2 + 1;
    if ( !v2[1] )
      break;
  }
  if ( !i )
    return 0;
  v3 = 1;
  if ( CompareStringW(0x409u, 1u, i, -1, L"onion", -1) != 2 )
    return CompareStringW(0x409u, 1u, i, -1, L"onion.", -1) == 2;
  return v3;
}

```

## disassembly

```asm
0x180004388  mov     [rsp+arg_0], rbx
0x18000438d  mov     [rsp+arg_8], rsi
0x180004392  push    rdi
0x180004393  sub     rsp, 30h
0x180004397  xor     esi, esi
0x180004399  mov     ebx, esi
0x18000439b  mov     edx, 2Eh ; '.'; Ch
0x1800043a0  call    cs:__imp_wcschr
0x1800043a7  nop     dword ptr [rax+rax+00h]
0x1800043ac  test    rax, rax
0x1800043af  jz      short loc_1800043BF
0x1800043b1  lea     rcx, [rax+2]
0x1800043b5  cmp     [rcx], si
0x1800043b8  jz      short loc_1800043BF
0x1800043ba  mov     rbx, rcx
0x1800043bd  jmp     short loc_18000439B
0x1800043bf  test    rbx, rbx
0x1800043c2  jz      short loc_180004434
0x1800043c4  or      r9d, 0FFFFFFFFh; cchCount1
0x1800043c8  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800043d0  lea     rax, aOnion_0; "onion"
0x1800043d7  mov     r8, rbx; lpString1
0x1800043da  mov     ecx, 409h; Locale
0x1800043df  mov     [rsp+38h+lpString2], rax; lpString2
0x1800043e4  lea     edi, [r9+2]
0x1800043e8  mov     edx, edi; dwCmpFlags
0x1800043ea  call    cs:__imp_CompareStringW
0x1800043f1  nop     dword ptr [rax+rax+00h]
0x1800043f6  cmp     eax, 2
0x1800043f9  jz      short loc_180004430
0x1800043fb  lea     rax, aOnion; "onion."
0x180004402  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000440a  or      r9d, 0FFFFFFFFh; cchCount1
0x18000440e  mov     [rsp+38h+lpString2], rax; lpString2
0x180004413  mov     r8, rbx; lpString1
0x180004416  mov     edx, edi; dwCmpFlags
0x180004418  mov     ecx, 409h; Locale
0x18000441d  call    cs:__imp_CompareStringW
0x180004424  nop     dword ptr [rax+rax+00h]
0x180004429  cmp     eax, 2
0x18000442c  jz      short loc_180004430
0x18000442e  mov     edi, esi
0x180004430  mov     eax, edi
0x180004432  jmp     short loc_180004436
0x180004434  xor     eax, eax
0x180004436  mov     rbx, [rsp+38h+arg_0]
0x18000443b  mov     rsi, [rsp+38h+arg_8]
0x180004440  add     rsp, 30h
0x180004444  pop     rdi
0x180004445  retn
```
