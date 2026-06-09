# FindChar2

- ea: `0x14000d0c4`
- end: `0x14000d15b`
- name: `FindChar2`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e90`
- `0x140002578`
- `0x14000263c`
- `0x140002b6c`
- `0x14000d164`

## callees

- `0x14000d0c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d0de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d0de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d140`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d140`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x14000d126`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x14000d126`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d0f3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d0f3`

## pseudocode

```c
__int64 __fastcall FindChar2(const WCHAR *a1, WCHAR a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rbx
  DWORD v6; // ecx
  unsigned int v7; // eax
  int StringOrdinal; // eax
  WCHAR StringValue; // [rsp+48h] [rbp+10h] BYREF

  StringValue = a2;
  v4 = a4;
  if ( a1 )
  {
    v7 = lstrlenW(a1);
    if ( v7 )
    {
      if ( (unsigned int)v4 < v7 )
      {
        StringOrdinal = FindStringOrdinal(0x400000u, &a1[v4], -1, &StringValue, 1, 1);
        if ( StringOrdinal != -1 )
          return (unsigned int)(v4 + StringOrdinal);
      }
    }
    v6 = 1168;
    goto LABEL_9;
  }
  if ( !GetLastError() )
  {
    v6 = 87;
LABEL_9:
    SetLastError(v6);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14000d0c4  mov     [rsp+arg_0], rbx
0x14000d0c9  mov     [rsp+StringValue], dx
0x14000d0ce  push    rdi
0x14000d0cf  sub     rsp, 30h
0x14000d0d3  mov     ebx, r9d
0x14000d0d6  mov     rdi, rcx
0x14000d0d9  test    rcx, rcx
0x14000d0dc  jnz     short loc_14000D0F3
0x14000d0de  call    cs:__imp_GetLastError
0x14000d0e5  nop     dword ptr [rax+rax+00h]
0x14000d0ea  test    eax, eax
0x14000d0ec  jnz     short loc_14000D14C
0x14000d0ee  lea     ecx, [rdi+57h]; lpString
0x14000d0f1  jmp     short loc_14000D140
0x14000d0f3  call    cs:__imp_lstrlenW
0x14000d0fa  nop     dword ptr [rax+rax+00h]
0x14000d0ff  test    eax, eax
0x14000d101  jz      short loc_14000D13B
0x14000d103  cmp     ebx, eax
0x14000d105  jnb     short loc_14000D13B
0x14000d107  mov     eax, 1
0x14000d10c  lea     rdx, [rdi+rbx*2]; lpStringSource
0x14000d110  mov     [rsp+38h+bIgnoreCase], eax; bIgnoreCase
0x14000d114  lea     r9, [rsp+38h+StringValue]; lpStringValue
0x14000d119  or      r8d, 0FFFFFFFFh; cchSource
0x14000d11d  mov     [rsp+38h+cchValue], eax; cchValue
0x14000d121  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x14000d126  call    cs:__imp_FindStringOrdinal
0x14000d12d  nop     dword ptr [rax+rax+00h]
0x14000d132  cmp     eax, 0FFFFFFFFh
0x14000d135  jz      short loc_14000D13B
0x14000d137  add     eax, ebx
0x14000d139  jmp     short loc_14000D14F
0x14000d13b  mov     ecx, 490h; dwErrCode
0x14000d140  call    cs:__imp_SetLastError
0x14000d147  nop     dword ptr [rax+rax+00h]
0x14000d14c  or      eax, 0FFFFFFFFh
0x14000d14f  mov     rbx, [rsp+38h+arg_0]
0x14000d154  add     rsp, 30h
0x14000d158  pop     rdi
0x14000d159  retn
```
