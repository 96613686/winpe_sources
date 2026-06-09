# CreateLinkInfoW

- ea: `0x180001ca0`
- end: `0x180001cd0`
- name: `CreateLinkInfoW`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054e0`

## callees

- `0x180001ca0`
- `0x180001f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001cae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001cae`

## pseudocode

```c
__int64 __fastcall CreateLinkInfoW(const unsigned __int16 *a1, struct _ilinkinfoW **a2)
{
  if ( a1 && a2 )
    return CreateILinkInfo(a1, a2);
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180001ca0  sub     rsp, 28h
0x180001ca4  test    rcx, rcx
0x180001ca7  jnz     short loc_180001CC2
0x180001ca9  mov     ecx, 57h ; 'W'; dwErrCode
0x180001cae  call    cs:__imp_SetLastError
0x180001cb5  nop     dword ptr [rax+rax+00h]
0x180001cba  xor     eax, eax
0x180001cbc  add     rsp, 28h
0x180001cc0  retn
0x180001cc2  test    rdx, rdx
0x180001cc5  jz      short loc_180001CA9
0x180001cc7  add     rsp, 28h
0x180001ccb  jmp     ?CreateILinkInfo@@YAHPEBGPEAPEAU_ilinkinfoW@@@Z; CreateILinkInfo(ushort const *,_ilinkinfoW * *)
```
