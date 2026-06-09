# CanonicalizeTrailingSlash(ushort *)

- ea: `0x180001de0`
- end: `0x180001e28`
- name: `?CanonicalizeTrailingSlash@@YAXPEAG@Z`
- size: `72`
- prototype: `void __fastcall(LPCWSTR lpszStart)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ce0`
- `0x180001f10`

## callees

- `0x180001de0`
- `0x1800023d0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x180001dff`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x180001dff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180001de9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180001de9`

## pseudocode

```c
void __fastcall CanonicalizeTrailingSlash(LPCWSTR lpszStart)
{
  int v2; // eax
  unsigned __int16 *v3; // rax
  _WORD *v4; // rdx

  v2 = lstrlenW(lpszStart);
  v3 = CharPrevW(lpszStart, &lpszStart[v2]);
  if ( (unsigned int)CharIsSlash(*v3) )
    *v4 = 0;
}

```

## disassembly

```asm
0x180001de0  push    rbx
0x180001de2  sub     rsp, 20h
0x180001de6  mov     rbx, rcx
0x180001de9  call    cs:__imp_lstrlenW
0x180001df0  nop     dword ptr [rax+rax+00h]
0x180001df5  movsxd  rdx, eax
0x180001df8  mov     rcx, rbx; lpszStart
0x180001dfb  lea     rdx, [rbx+rdx*2]; lpszCurrent
0x180001dff  call    cs:__imp_CharPrevW
0x180001e06  nop     dword ptr [rax+rax+00h]
0x180001e0b  mov     rdx, rax
0x180001e0e  movzx   ecx, word ptr [rax]; unsigned __int16
0x180001e11  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x180001e16  test    eax, eax
0x180001e18  jnz     short loc_180001E21
0x180001e1a  add     rsp, 20h
0x180001e1e  pop     rbx
0x180001e1f  retn
0x180001e21  xor     eax, eax
0x180001e23  mov     [rdx], ax
0x180001e26  jmp     short loc_180001E1A
```
