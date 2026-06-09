# FileExistsInPath(ushort *,ushort const *,ushort *,ulong)

- ea: `0x18000cd74`
- end: `0x18000cdc6`
- name: `?FileExistsInPath@@YAHPEAGPEBG0K@Z`
- size: `82`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR lpPath, wchar_t *Str, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001010`

## callees

- `0x180001610`
- `0x18000cd74`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18000cda5`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18000cda5`

## pseudocode

```c
__int64 __fastcall FileExistsInPath(LPCWSTR lpFileName, LPCWSTR lpPath, wchar_t *Str)
{
  unsigned __int64 v4; // rdx
  LPWSTR v6; // [rsp+30h] [rbp-18h] BYREF

  v6 = 0;
  if ( SearchPathW(lpPath, lpFileName, 0, 0x105u, Str, &v6) - 1 > 0x104 )
    return 0;
  else
    return FileExists(Str, v4);
}

```

## disassembly

```asm
0x18000cd74  mov     r11, rsp
0x18000cd77  push    rbx
0x18000cd78  sub     rsp, 40h
0x18000cd7c  mov     rax, rdx
0x18000cd7f  mov     qword ptr [r11-18h], 0
0x18000cd87  lea     rdx, [r11-18h]
0x18000cd8b  mov     rbx, r8
0x18000cd8e  mov     [r11-20h], rdx
0x18000cd92  mov     r9d, 105h; nBufferLength
0x18000cd98  mov     rdx, rcx; lpFileName
0x18000cd9b  mov     [r11-28h], rbx
0x18000cd9f  mov     rcx, rax; lpPath
0x18000cda2  xor     r8d, r8d; lpExtension
0x18000cda5  call    cs:__imp_SearchPathW
0x18000cdab  dec     eax
0x18000cdad  cmp     eax, 104h
0x18000cdb2  ja      short loc_18000CDBE
0x18000cdb4  mov     rcx, rbx; Str
0x18000cdb7  call    ?FileExists@@YAHPEAG_K@Z; FileExists(ushort *,unsigned __int64)
0x18000cdbc  jmp     short loc_18000CDC0
0x18000cdbe  xor     eax, eax
0x18000cdc0  add     rsp, 40h
0x18000cdc4  pop     rbx
0x18000cdc5  retn
```
