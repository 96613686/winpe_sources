# Pki_strnicmp

- ea: `0x18001a1e4`
- end: `0x18001a244`
- name: `Pki_strnicmp`
- size: `96`
- prototype: `__int64 __fastcall(PCNZCH lpString1, PCNZCH lpString2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010ed8`

## callees

- `0x18001a1e4`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18001a236`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18001a236`

## pseudocode

```c
__int64 __fastcall Pki_strnicmp(PCNZCH lpString1, PCNZCH lpString2, unsigned __int64 a3)
{
  unsigned __int64 v3; // r9
  PCNZCH i; // rax
  unsigned __int64 cchCount2; // rax
  PCNZCH j; // rcx

  v3 = 0;
  for ( i = lpString1; v3 < a3; ++i )
  {
    if ( !*i )
      break;
    ++v3;
  }
  cchCount2 = 0;
  for ( j = lpString2; cchCount2 < a3; ++j )
  {
    if ( !*j )
      break;
    ++cchCount2;
  }
  return (unsigned int)(CompareStringA(0x409u, 1u, lpString1, v3, lpString2, cchCount2) - 2);
}

```

## disassembly

```asm
0x18001a1e4  sub     rsp, 38h
0x18001a1e8  xor     r9d, r9d
0x18001a1eb  mov     r10, rcx
0x18001a1ee  mov     rax, rcx
0x18001a1f1  test    r8, r8
0x18001a1f4  jz      short loc_18001A206
0x18001a1f6  cmp     byte ptr [rax], 0
0x18001a1f9  jz      short loc_18001A206
0x18001a1fb  inc     r9; cchCount1
0x18001a1fe  inc     rax
0x18001a201  cmp     r9, r8
0x18001a204  jb      short loc_18001A1F6
0x18001a206  xor     eax, eax
0x18001a208  mov     rcx, rdx
0x18001a20b  test    r8, r8
0x18001a20e  jz      short loc_18001A220
0x18001a210  cmp     byte ptr [rcx], 0
0x18001a213  jz      short loc_18001A220
0x18001a215  inc     rax
0x18001a218  inc     rcx
0x18001a21b  cmp     rax, r8
0x18001a21e  jb      short loc_18001A210
0x18001a220  mov     [rsp+38h+cchCount2], eax; cchCount2
0x18001a224  mov     r8, r10; lpString1
0x18001a227  mov     [rsp+38h+lpString2], rdx; lpString2
0x18001a22c  mov     ecx, 409h; Locale
0x18001a231  mov     edx, 1; dwCmpFlags
0x18001a236  call    cs:__imp_CompareStringA
0x18001a23c  sub     eax, 2
0x18001a23f  add     rsp, 38h
0x18001a243  retn
```
