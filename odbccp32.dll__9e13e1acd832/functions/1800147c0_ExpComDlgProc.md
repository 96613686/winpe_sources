# ExpComDlgProc

- ea: `0x1800147c0`
- end: `0x1800147e8`
- name: `ExpComDlgProc`
- size: `40`
- prototype: `__int64 __fastcall(HWND, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001450c`
- `0x1800147c0`

## import_xrefs

- `USER32!GetParent` at `0x1800147d3`
- `USER32!GetParent` at `0x1800147d3`

## pseudocode

```c
__int64 __fastcall ExpComDlgProc(HWND a1, int a2, __int64 a3, __int64 a4)
{
  HWND Parent; // rax

  if ( a2 == 78 && *(_DWORD *)(a4 + 16) == -601 )
  {
    Parent = GetParent(a1);
    CenterDlg(Parent);
  }
  return 0;
}

```

## disassembly

```asm
0x1800147c0  sub     rsp, 28h
0x1800147c4  cmp     edx, 4Eh ; 'N'
0x1800147c7  jnz     short loc_1800147E1
0x1800147c9  cmp     dword ptr [r9+10h], 0FFFFFDA7h
0x1800147d1  jnz     short loc_1800147E1
0x1800147d3  call    cs:__imp_GetParent
0x1800147d9  mov     rcx, rax; hWnd
0x1800147dc  call    CenterDlg
0x1800147e1  xor     eax, eax
0x1800147e3  add     rsp, 28h
0x1800147e7  retn
```
