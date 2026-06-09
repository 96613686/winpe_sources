# IsServiceSid(ushort const *)

- ea: `0x180021d00`
- end: `0x180021d87`
- name: `?IsServiceSid@@YAHPEBG@Z`
- size: `135`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002b2a0`
- `0x18002f4fc`

## callees

- `0x180021d00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180021d21`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180021d47`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180021d6d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180021d21`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180021d47`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180021d6d`

## pseudocode

```c
_BOOL8 __fastcall IsServiceSid(LPCWCH lpString1)
{
  return CompareStringOrdinal(lpString1, -1, L"S-1-5-18", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"S-1-5-19", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"S-1-5-20", -1, 1) == 2;
}

```

## disassembly

```asm
0x180021d00  push    rbx
0x180021d02  sub     rsp, 30h
0x180021d06  mov     r9d, 0FFFFFFFFh; cchCount2
0x180021d0c  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180021d14  mov     edx, r9d; cchCount1
0x180021d17  lea     r8, String2; "S-1-5-18"
0x180021d1e  mov     rbx, rcx
0x180021d21  call    cs:__imp_CompareStringOrdinal
0x180021d27  cmp     eax, 2
0x180021d2a  jz      short loc_180021D80
0x180021d2c  mov     r9d, 0FFFFFFFFh; cchCount2
0x180021d32  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180021d3a  mov     edx, r9d; cchCount1
0x180021d3d  lea     r8, aS1519; "S-1-5-19"
0x180021d44  mov     rcx, rbx; lpString1
0x180021d47  call    cs:__imp_CompareStringOrdinal
0x180021d4d  cmp     eax, 2
0x180021d50  jz      short loc_180021D80
0x180021d52  mov     r9d, 0FFFFFFFFh; cchCount2
0x180021d58  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180021d60  mov     edx, r9d; cchCount1
0x180021d63  lea     r8, aS1520_0; "S-1-5-20"
0x180021d6a  mov     rcx, rbx; lpString1
0x180021d6d  call    cs:__imp_CompareStringOrdinal
0x180021d73  cmp     eax, 2
0x180021d76  jz      short loc_180021D80
0x180021d78  xor     eax, eax
0x180021d7a  add     rsp, 30h
0x180021d7e  pop     rbx
0x180021d7f  retn
0x180021d80  mov     eax, 1
0x180021d85  jmp     short loc_180021D7A
```
