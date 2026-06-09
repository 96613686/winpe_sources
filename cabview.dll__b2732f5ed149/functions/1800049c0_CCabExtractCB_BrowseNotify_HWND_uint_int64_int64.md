# CCabExtractCB::BrowseNotify(HWND__ *,uint,__int64,__int64)

- ea: `0x1800049c0`
- end: `0x180004a25`
- name: `?BrowseNotify@CCabExtractCB@@CAHPEAUHWND__@@I_J1@Z`
- size: `101`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800049c0`

## import_xrefs

- `SHLWAPI!PathAddBackslashA` at `0x1800049f4`
- `SHLWAPI!PathAddBackslashA` at `0x1800049f4`
- `KERNEL32!lstrlenA` at `0x1800049e1`
- `KERNEL32!lstrlenA` at `0x1800049e1`
- `USER32!SendMessageW` at `0x180004a12`
- `USER32!SendMessageW` at `0x180004a12`

## pseudocode

```c
__int64 __fastcall CCabExtractCB::BrowseNotify(HWND hWnd, int a2, __int64 a3, __int64 a4)
{
  if ( a2 != 1 )
    return 0;
  if ( lstrlenA(*(LPCSTR *)(*(_QWORD *)(a4 + 64) + 24LL)) < 3 )
    PathAddBackslashA(*(LPSTR *)(*(_QWORD *)(a4 + 64) + 24LL));
  SendMessageW(hWnd, 0x467u, 1u, *(_QWORD *)(*(_QWORD *)(a4 + 64) + 24LL));
  return 1;
}

```

## disassembly

```asm
0x1800049c0  mov     [rsp+arg_0], rbx
0x1800049c5  push    rdi
0x1800049c6  sub     rsp, 20h
0x1800049ca  mov     rbx, r9
0x1800049cd  mov     rdi, rcx
0x1800049d0  cmp     edx, 1
0x1800049d3  jz      short loc_1800049D9
0x1800049d5  xor     eax, eax
0x1800049d7  jmp     short loc_180004A1A
0x1800049d9  mov     rcx, [r9+40h]
0x1800049dd  mov     rcx, [rcx+18h]; lpString
0x1800049e1  call    cs:__imp_lstrlenA
0x1800049e7  cmp     eax, 3
0x1800049ea  jge     short loc_1800049FA
0x1800049ec  mov     rcx, [rbx+40h]
0x1800049f0  mov     rcx, [rcx+18h]; pszPath
0x1800049f4  call    cs:__imp_PathAddBackslashA
0x1800049fa  mov     r9, [rbx+40h]
0x1800049fe  mov     edx, 467h; Msg
0x180004a03  mov     ebx, 1
0x180004a08  mov     rcx, rdi; hWnd
0x180004a0b  mov     r8d, ebx; wParam
0x180004a0e  mov     r9, [r9+18h]; lParam
0x180004a12  call    cs:__imp_SendMessageW
0x180004a18  mov     eax, ebx
0x180004a1a  mov     rbx, [rsp+28h+arg_0]
0x180004a1f  add     rsp, 20h
0x180004a23  pop     rdi
0x180004a24  retn
```
