# IsContainerSid(ushort const *)

- ea: `0x18000afac`
- end: `0x18000b017`
- name: `?IsContainerSid@@YAHPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b0a0`

## callees

- `0x18000afac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000afd0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000aff6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000afd0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000aff6`

## pseudocode

```c
__int64 __fastcall IsContainerSid(LPCWCH lpString1)
{
  unsigned int v1; // ebx

  v1 = 1;
  if ( CompareStringOrdinal(lpString1, -1, L"S-1-5-93-2-1", -1, 1) != 2 )
    return CompareStringOrdinal(lpString1, -1, L"S-1-5-93-2-2", -1, 1) == 2;
  return v1;
}

```

## disassembly

```asm
0x18000afac  mov     [rsp+arg_0], rbx
0x18000afb1  push    rdi
0x18000afb2  sub     rsp, 30h
0x18000afb6  or      r9d, 0FFFFFFFFh; cchCount2
0x18000afba  lea     r8, String2; "S-1-5-93-2-1"
0x18000afc1  mov     ebx, 1
0x18000afc6  or      edx, r9d; cchCount1
0x18000afc9  mov     rdi, rcx
0x18000afcc  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x18000afd0  call    cs:__imp_CompareStringOrdinal
0x18000afd7  nop     dword ptr [rax+rax+00h]
0x18000afdc  cmp     eax, 2
0x18000afdf  jz      short loc_18000B009
0x18000afe1  or      r9d, 0FFFFFFFFh; cchCount2
0x18000afe5  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x18000afe9  or      edx, r9d; cchCount1
0x18000afec  lea     r8, aS159322; "S-1-5-93-2-2"
0x18000aff3  mov     rcx, rdi; lpString1
0x18000aff6  call    cs:__imp_CompareStringOrdinal
0x18000affd  nop     dword ptr [rax+rax+00h]
0x18000b002  cmp     eax, 2
0x18000b005  jz      short loc_18000B009
0x18000b007  xor     ebx, ebx
0x18000b009  mov     eax, ebx
0x18000b00b  mov     rbx, [rsp+38h+arg_0]
0x18000b010  add     rsp, 30h
0x18000b014  pop     rdi
0x18000b015  retn
```
