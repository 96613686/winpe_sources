# IsServiceSid(ushort const *)

- ea: `0x180024d10`
- end: `0x180024daa`
- name: `?IsServiceSid@@YAHPEBG@Z`
- size: `154`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180037544`
- `0x18003797c`

## callees

- `0x180024d10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024d31`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024d5d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024d89`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024d31`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024d5d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024d89`

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
0x180024d10  push    rbx
0x180024d12  sub     rsp, 30h
0x180024d16  mov     r9d, 0FFFFFFFFh; cchCount2
0x180024d1c  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180024d24  mov     edx, r9d; cchCount1
0x180024d27  lea     r8, aS1518_0; "S-1-5-18"
0x180024d2e  mov     rbx, rcx
0x180024d31  call    cs:__imp_CompareStringOrdinal
0x180024d38  nop     dword ptr [rax+rax+00h]
0x180024d3d  cmp     eax, 2
0x180024d40  jz      short loc_180024DA3
0x180024d42  mov     r9d, 0FFFFFFFFh; cchCount2
0x180024d48  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180024d50  mov     edx, r9d; cchCount1
0x180024d53  lea     r8, aS1519; "S-1-5-19"
0x180024d5a  mov     rcx, rbx; lpString1
0x180024d5d  call    cs:__imp_CompareStringOrdinal
0x180024d64  nop     dword ptr [rax+rax+00h]
0x180024d69  cmp     eax, 2
0x180024d6c  jz      short loc_180024DA3
0x180024d6e  mov     r9d, 0FFFFFFFFh; cchCount2
0x180024d74  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180024d7c  mov     edx, r9d; cchCount1
0x180024d7f  lea     r8, aS1520_0; "S-1-5-20"
0x180024d86  mov     rcx, rbx; lpString1
0x180024d89  call    cs:__imp_CompareStringOrdinal
0x180024d90  nop     dword ptr [rax+rax+00h]
0x180024d95  cmp     eax, 2
0x180024d98  jz      short loc_180024DA3
0x180024d9a  xor     eax, eax
0x180024d9c  add     rsp, 30h
0x180024da0  pop     rbx
0x180024da1  retn
0x180024da3  mov     eax, 1
0x180024da8  jmp     short loc_180024D9C
```
