# IsAttachment(wchar_t const *)

- ea: `0x18001c9fc`
- end: `0x18001ca65`
- name: `?IsAttachment@@YAHPEB_W@Z`
- size: `105`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b814`
- `0x18001ca6c`
- `0x18001ce70`
- `0x18001ed10`
- `0x18001ff80`
- `0x180020180`

## callees

- `0x18001c9fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001ca07`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001ca07`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ca4b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ca4b`

## pseudocode

```c
_BOOL8 __fastcall IsAttachment(const wchar_t *a1)
{
  wchar_t *v1; // rax
  unsigned __int64 v2; // rcx

  v1 = wcsrchr(a1, 0x2Fu);
  if ( !v1 )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( v1[v2] );
  return v2 > 4 && CompareStringW(0x7Fu, 1u, v1, 4, L"/AT=", 4) == 2;
}

```

## disassembly

```asm
0x18001c9fc  push    rbx
0x18001c9fe  sub     rsp, 30h
0x18001ca02  mov     edx, 2Fh ; '/'; Ch
0x18001ca07  call    cs:__imp_wcsrchr
0x18001ca0d  xor     ebx, ebx
0x18001ca0f  test    rax, rax
0x18001ca12  jz      short loc_18001CA5D
0x18001ca14  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001ca18  inc     rcx
0x18001ca1b  cmp     [rax+rcx*2], bx
0x18001ca1f  jnz     short loc_18001CA18
0x18001ca21  cmp     rcx, 4
0x18001ca25  jbe     short loc_18001CA5D
0x18001ca27  lea     rcx, aAt_0; "/AT="
0x18001ca2e  mov     [rsp+38h+cchCount2], 4; cchCount2
0x18001ca36  mov     r9d, 4; cchCount1
0x18001ca3c  mov     [rsp+38h+lpString2], rcx; lpString2
0x18001ca41  mov     r8, rax; lpString1
0x18001ca44  lea     edx, [r9-3]; dwCmpFlags
0x18001ca48  lea     ecx, [rdx+7Eh]; Locale
0x18001ca4b  call    cs:__imp_CompareStringW
0x18001ca51  cmp     eax, 2
0x18001ca54  mov     ecx, ebx
0x18001ca56  setz    cl
0x18001ca59  mov     eax, ecx
0x18001ca5b  jmp     short loc_18001CA5F
0x18001ca5d  xor     eax, eax
0x18001ca5f  add     rsp, 30h
0x18001ca63  pop     rbx
0x18001ca64  retn
```
