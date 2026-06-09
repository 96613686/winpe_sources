# FetchNTStatusSymbolicName

- ea: `0x1800457cc`
- end: `0x1800457f3`
- name: `FetchNTStatusSymbolicName`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x180043390`

## callees

- `0x180021c58`
- `0x1800457cc`

## import_xrefs

- `ext-ms-win-core-symbolicnames-l1-1-0!GetNTStatusSymbolicName` at `0x1800457e4`

## pseudocode

```c
__int64 __fastcall FetchNTStatusSymbolicName(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx

  v2 = a1;
  if ( (unsigned __int8)IsGetNetEventSymbolicNamePresent(a1, a2) )
    return GetNTStatusSymbolicName(v2);
  else
    return 0;
}

```

## disassembly

```asm
0x1800457cc  push    rbx
0x1800457ce  sub     rsp, 20h
0x1800457d2  mov     ebx, ecx
0x1800457d4  call    IsGetNetEventSymbolicNamePresent
0x1800457d9  test    al, al
0x1800457db  jz      short loc_1800457EB
0x1800457dd  mov     ecx, ebx
0x1800457df  add     rsp, 20h
0x1800457e3  pop     rbx
0x1800457e4  jmp     cs:__imp_GetNTStatusSymbolicName
0x1800457eb  xor     eax, eax
0x1800457ed  add     rsp, 20h
0x1800457f1  pop     rbx
0x1800457f2  retn
```
