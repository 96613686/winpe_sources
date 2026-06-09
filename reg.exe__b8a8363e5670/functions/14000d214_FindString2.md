# FindString2

- ea: `0x14000d214`
- end: `0x14000d2c9`
- name: `FindString2`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400056ec`
- `0x14000672c`
- `0x14000a6d8`
- `0x14000d990`

## callees

- `0x14000d214`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d29c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d29c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d2af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d2af`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x14000d280`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x14000d280`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d231`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d242`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d231`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d242`

## pseudocode

```c
__int64 __fastcall FindString2(const WCHAR *a1, const WCHAR *a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rsi
  unsigned int v7; // edi
  unsigned int v8; // eax
  int StringOrdinal; // eax
  DWORD v11; // ecx

  v4 = a4;
  if ( a1 && a2 )
  {
    v7 = lstrlenW(a1);
    v8 = lstrlenW(a2);
    if ( v8 )
    {
      if ( v7 )
      {
        if ( (unsigned int)v4 < v7 && v7 - (unsigned int)v4 >= v8 )
        {
          StringOrdinal = FindStringOrdinal(0x400000u, &a1[v4], -1, a2, -1, 1);
          if ( StringOrdinal != -1 )
            return (unsigned int)(v4 + StringOrdinal);
        }
      }
    }
    v11 = 1168;
    goto LABEL_12;
  }
  if ( !GetLastError() )
  {
    v11 = 87;
LABEL_12:
    SetLastError(v11);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14000d214  push    rbp
0x14000d216  push    rsi
0x14000d217  push    rdi
0x14000d218  push    r14
0x14000d21a  sub     rsp, 38h
0x14000d21e  mov     esi, r9d
0x14000d221  mov     rbp, rdx
0x14000d224  mov     r14, rcx
0x14000d227  test    rcx, rcx
0x14000d22a  jz      short loc_14000D29C
0x14000d22c  test    rdx, rdx
0x14000d22f  jz      short loc_14000D29C
0x14000d231  call    cs:__imp_lstrlenW
0x14000d238  nop     dword ptr [rax+rax+00h]
0x14000d23d  mov     rcx, rbp; lpString
0x14000d240  mov     edi, eax
0x14000d242  call    cs:__imp_lstrlenW
0x14000d249  nop     dword ptr [rax+rax+00h]
0x14000d24e  test    eax, eax
0x14000d250  jz      short loc_14000D295
0x14000d252  test    edi, edi
0x14000d254  jz      short loc_14000D295
0x14000d256  cmp     esi, edi
0x14000d258  jnb     short loc_14000D295
0x14000d25a  sub     edi, esi
0x14000d25c  cmp     edi, eax
0x14000d25e  jb      short loc_14000D295
0x14000d260  lea     rdx, [r14+rsi*2]; lpStringSource
0x14000d264  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x14000d26c  mov     r9, rbp; lpStringValue
0x14000d26f  mov     [rsp+58h+cchValue], 0FFFFFFFFh; cchValue
0x14000d277  or      r8d, 0FFFFFFFFh; cchSource
0x14000d27b  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x14000d280  call    cs:__imp_FindStringOrdinal
0x14000d287  nop     dword ptr [rax+rax+00h]
0x14000d28c  cmp     eax, 0FFFFFFFFh
0x14000d28f  jz      short loc_14000D295
0x14000d291  add     eax, esi
0x14000d293  jmp     short loc_14000D2BE
0x14000d295  mov     ecx, 490h
0x14000d29a  jmp     short loc_14000D2AF
0x14000d29c  call    cs:__imp_GetLastError
0x14000d2a3  nop     dword ptr [rax+rax+00h]
0x14000d2a8  test    eax, eax
0x14000d2aa  jnz     short loc_14000D2BB
0x14000d2ac  lea     ecx, [rax+57h]; dwErrCode
0x14000d2af  call    cs:__imp_SetLastError
0x14000d2b6  nop     dword ptr [rax+rax+00h]
0x14000d2bb  or      eax, 0FFFFFFFFh
0x14000d2be  add     rsp, 38h
0x14000d2c2  pop     r14
0x14000d2c4  pop     rdi
0x14000d2c5  pop     rsi
0x14000d2c6  pop     rbp
0x14000d2c7  retn
```
