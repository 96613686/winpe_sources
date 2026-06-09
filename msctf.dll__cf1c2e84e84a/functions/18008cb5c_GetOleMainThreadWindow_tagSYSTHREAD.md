# GetOleMainThreadWindow(tagSYSTHREAD *)

- ea: `0x18008cb5c`
- end: `0x18008cc13`
- name: `?GetOleMainThreadWindow@@YAPEAUHWND__@@PEAUtagSYSTHREAD@@@Z`
- size: `183`
- prototype: `HWND __fastcall(struct tagSYSTHREAD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002f140`
- `0x180030d30`

## callees

- `0x1800514fc`
- `0x18008cb5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008cba8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008cba8`
- `USER32!GetWindow` at `0x18008cbf1`
- `USER32!GetWindow` at `0x18008cbf1`
- `USER32!FindWindowExW` at `0x18008cbc0`
- `USER32!FindWindowExW` at `0x18008cbc0`
- `USER32!IsWindow` at `0x18008cb7a`
- `USER32!IsWindow` at `0x18008cb7a`
- `USER32!GetWindowThreadProcessId` at `0x18008cbd3`
- `USER32!GetWindowThreadProcessId` at `0x18008cbd3`

## string_xrefs

- `0x18008cbb0`: `OleMainThreadWndClass`

## pseudocode

```c
HWND __fastcall GetOleMainThreadWindow(struct tagSYSTHREAD *a1)
{
  HWND v2; // rcx
  DWORD CurrentThreadId; // esi
  HWND i; // rax
  HWND v6; // rbx

  v2 = (HWND)*((_QWORD *)a1 + 18);
  if ( v2 )
  {
    if ( IsWindow(v2) && (unsigned int)IsOleMainThreadWindow(*((HWND *)a1 + 18)) )
      return (HWND)*((_QWORD *)a1 + 18);
    *((_QWORD *)a1 + 18) = 0;
  }
  CurrentThreadId = GetCurrentThreadId();
  for ( i = FindWindowExW(HWND_MESSAGE, 0, L"OleMainThreadWndClass", 0); ; i = GetWindow(v6, 2u) )
  {
    v6 = i;
    if ( !i || CurrentThreadId == GetWindowThreadProcessId(i, 0) && (unsigned int)IsOleMainThreadWindow(v6) )
      break;
  }
  *((_QWORD *)a1 + 18) = v6;
  return v6;
}

```

## disassembly

```asm
0x18008cb5c  mov     [rsp+arg_0], rbx
0x18008cb61  mov     [rsp+arg_8], rsi
0x18008cb66  push    rdi
0x18008cb67  sub     rsp, 20h
0x18008cb6b  mov     rdi, rcx
0x18008cb6e  mov     rcx, [rcx+90h]; hWnd
0x18008cb75  test    rcx, rcx
0x18008cb78  jz      short loc_18008CBA8
0x18008cb7a  call    cs:__imp_IsWindow
0x18008cb80  test    eax, eax
0x18008cb82  jz      short loc_18008CB9D
0x18008cb84  mov     rcx, [rdi+90h]; HWND
0x18008cb8b  call    ?IsOleMainThreadWindow@@YAHPEAUHWND__@@@Z; IsOleMainThreadWindow(HWND__ *)
0x18008cb90  test    eax, eax
0x18008cb92  jz      short loc_18008CB9D
0x18008cb94  mov     rax, [rdi+90h]
0x18008cb9b  jmp     short loc_18008CC03
0x18008cb9d  mov     qword ptr [rdi+90h], 0
0x18008cba8  call    cs:__imp_GetCurrentThreadId
0x18008cbae  xor     edx, edx; hWndChildAfter
0x18008cbb0  lea     r8, szClass; "OleMainThreadWndClass"
0x18008cbb7  xor     r9d, r9d; lpszWindow
0x18008cbba  mov     esi, eax
0x18008cbbc  lea     rcx, [rdx-3]; hWndParent
0x18008cbc0  call    cs:__imp_FindWindowExW
0x18008cbc6  mov     rbx, rax
0x18008cbc9  test    rbx, rbx
0x18008cbcc  jz      short loc_18008CBF9
0x18008cbce  xor     edx, edx; lpdwProcessId
0x18008cbd0  mov     rcx, rax; hWnd
0x18008cbd3  call    cs:__imp_GetWindowThreadProcessId
0x18008cbd9  cmp     esi, eax
0x18008cbdb  jnz     short loc_18008CBE9
0x18008cbdd  mov     rcx, rbx; HWND
0x18008cbe0  call    ?IsOleMainThreadWindow@@YAHPEAUHWND__@@@Z; IsOleMainThreadWindow(HWND__ *)
0x18008cbe5  test    eax, eax
0x18008cbe7  jnz     short loc_18008CBF9
0x18008cbe9  mov     edx, 2; uCmd
0x18008cbee  mov     rcx, rbx; hWnd
0x18008cbf1  call    cs:__imp_GetWindow
0x18008cbf7  jmp     short loc_18008CBC6
0x18008cbf9  mov     [rdi+90h], rbx
0x18008cc00  mov     rax, rbx
0x18008cc03  mov     rbx, [rsp+28h+arg_0]
0x18008cc08  mov     rsi, [rsp+28h+arg_8]
0x18008cc0d  add     rsp, 20h
0x18008cc11  pop     rdi
0x18008cc12  retn
```
