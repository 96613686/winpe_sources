# IsValidCreateOrExpireTime(int,_FILETIME *,_FILETIME *,_FILETIME *)

- ea: `0x180010c9c`
- end: `0x180010cec`
- name: `?IsValidCreateOrExpireTime@@YAHHPEAU_FILETIME@@00@Z`
- size: `80`
- prototype: `__int64 __fastcall(int, struct _FILETIME *, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800101e0`

## callees

- `0x180010c9c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010cb7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010ce0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010cb7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010ce0`

## pseudocode

```c
__int64 __fastcall IsValidCreateOrExpireTime(int a1, struct _FILETIME *a2, struct _FILETIME *a3, struct _FILETIME *a4)
{
  if ( !a2 )
    return 1;
  if ( !a1 )
    return CompareFileTime(a2, a4) <= 0 || !a4->dwLowDateTime && !a4->dwHighDateTime;
  return CompareFileTime(a2, a3) <= 0;
}

```

## disassembly

```asm
0x180010c9c  push    rbx
0x180010c9e  sub     rsp, 20h
0x180010ca2  mov     rbx, r9
0x180010ca5  mov     rax, rdx
0x180010ca8  test    rdx, rdx
0x180010cab  jz      short loc_180010CC1
0x180010cad  test    ecx, ecx
0x180010caf  mov     rcx, rdx; lpFileTime1
0x180010cb2  jnz     short loc_180010CDD
0x180010cb4  mov     rdx, rbx; lpFileTime2
0x180010cb7  call    cs:__imp_CompareFileTime
0x180010cbd  test    eax, eax
0x180010cbf  jg      short loc_180010CCC
0x180010cc1  mov     eax, 1
0x180010cc6  add     rsp, 20h
0x180010cca  pop     rbx
0x180010ccb  retn
0x180010ccc  cmp     dword ptr [rbx], 0
0x180010ccf  jz      short loc_180010CD5
0x180010cd1  xor     eax, eax
0x180010cd3  jmp     short loc_180010CC6
0x180010cd5  cmp     dword ptr [rbx+4], 0
0x180010cd9  jz      short loc_180010CC1
0x180010cdb  jmp     short loc_180010CD1
0x180010cdd  mov     rdx, r8; lpFileTime2
0x180010ce0  call    cs:__imp_CompareFileTime
0x180010ce6  test    eax, eax
0x180010ce8  jle     short loc_180010CC1
0x180010cea  jmp     short loc_180010CD1
```
