# IsolationAwareCreateWindowExW

- ea: `0x18000bb1c`
- end: `0x18000bc31`
- name: `IsolationAwareCreateWindowExW`
- size: `277`
- prototype: `__int64 __fastcall(DWORD dwExStyle, LPCWSTR lpClassName, LPCWSTR lpWindowName, DWORD dwStyle, int, int, int, int, HWND, HMENU, HINSTANCE, ULONG_PTR ulCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b170`
- `0x1800102d4`
- `0x18001054c`

## callees

- `0x180002b18`
- `0x18000bb1c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000bbff`
- `KERNEL32!GetLastError` at `0x1800762ba`
- `KERNEL32!GetLastError` at `0x18000bbff`
- `KERNEL32!GetLastError` at `0x1800762ba`
- `KERNEL32!DeactivateActCtx` at `0x18000bc17`
- `KERNEL32!DeactivateActCtx` at `0x1800762d1`
- `KERNEL32!DeactivateActCtx` at `0x18000bc17`
- `KERNEL32!DeactivateActCtx` at `0x1800762d1`
- `KERNEL32!SetLastError` at `0x18000bc23`
- `KERNEL32!SetLastError` at `0x1800762dd`
- `KERNEL32!SetLastError` at `0x18000bc23`
- `KERNEL32!SetLastError` at `0x1800762dd`
- `USER32!CreateWindowExW` at `0x18000bbd7`
- `USER32!CreateWindowExW` at `0x18000bbd7`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExW(
        DWORD dwExStyle,
        LPCWSTR lpClassName,
        LPCWSTR lpWindowName,
        DWORD dwStyle,
        int X,
        int Y,
        int nWidth,
        int nHeight,
        HWND hWndParent,
        HMENU hMenu,
        HINSTANCE hInstance,
        ULONG_PTR ulCookie)
{
  HWND Window; // rax
  HWND v18; // rsi
  int v19; // edi
  DWORD LastError; // ebx

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Window = CreateWindowExW(
             dwExStyle,
             lpClassName,
             lpWindowName,
             dwStyle,
             X,
             Y,
             nWidth,
             nHeight,
             hWndParent,
             hMenu,
             hInstance,
             0);
  v18 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v19 = 0;
      LastError = 0;
    }
    else
    {
      v19 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v19 )
      SetLastError(LastError);
  }
  return v18;
}

```

## disassembly

```asm
0x18000bb1c  mov     rax, rsp
0x18000bb1f  push    rbx
0x18000bb20  push    rsi
0x18000bb21  push    rdi
0x18000bb22  push    r14
0x18000bb24  sub     rsp, 78h
0x18000bb28  mov     ebx, r9d
0x18000bb2b  mov     rdi, r8
0x18000bb2e  mov     rsi, rdx
0x18000bb31  mov     r14d, ecx
0x18000bb34  mov     qword ptr [rax-38h], 0
0x18000bb3c  mov     qword ptr [rax+60h], 0
0x18000bb44  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000bb4b  jnz     short loc_18000BB6F
0x18000bb4d  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bb54  jnz     short loc_18000BB6F
0x18000bb56  lea     rcx, [rax+60h]; lpCookie
0x18000bb5a  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000bb5f  test    eax, eax
0x18000bb61  jnz     short loc_18000BB6F
0x18000bb63  xor     eax, eax
0x18000bb65  add     rsp, 78h
0x18000bb69  pop     r14
0x18000bb6b  pop     rdi
0x18000bb6c  pop     rsi
0x18000bb6d  pop     rbx
0x18000bb6e  retn
0x18000bb6f  mov     [rsp+98h+lpParam], 0; lpParam
0x18000bb78  mov     rax, [rsp+98h+arg_50]
0x18000bb80  mov     [rsp+98h+hInstance], rax; hInstance
0x18000bb85  mov     rax, [rsp+98h+arg_48]
0x18000bb8d  mov     [rsp+98h+hMenu], rax; hMenu
0x18000bb92  mov     rax, [rsp+98h+arg_40]
0x18000bb9a  mov     [rsp+98h+hWndParent], rax; hWndParent
0x18000bb9f  mov     eax, [rsp+98h+arg_38]
0x18000bba6  mov     [rsp+98h+nHeight], eax; nHeight
0x18000bbaa  mov     eax, [rsp+98h+arg_30]
0x18000bbb1  mov     [rsp+98h+nWidth], eax; nWidth
0x18000bbb5  mov     eax, [rsp+98h+arg_28]
0x18000bbbc  mov     [rsp+98h+Y], eax; Y
0x18000bbc0  mov     eax, [rsp+98h+arg_20]
0x18000bbc7  mov     [rsp+98h+X], eax; X
0x18000bbcb  mov     r9d, ebx; dwStyle
0x18000bbce  mov     r8, rdi; lpWindowName
0x18000bbd1  mov     rdx, rsi; lpClassName
0x18000bbd4  mov     ecx, r14d; dwExStyle
0x18000bbd7  call    cs:__imp_CreateWindowExW
0x18000bbdd  mov     rsi, rax
0x18000bbe0  mov     [rsp+98h+var_38], rax
0x18000bbe5  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000bbec  jz      short loc_18000BBF7
0x18000bbee  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bbf5  jnz     short loc_18000BC29
0x18000bbf7  test    rsi, rsi
0x18000bbfa  jnz     short loc_18000BC09
0x18000bbfc  lea     edi, [rsi+1]
0x18000bbff  call    cs:__imp_GetLastError
0x18000bc05  mov     ebx, eax
0x18000bc07  jmp     short loc_18000BC0D
0x18000bc09  xor     edi, edi
0x18000bc0b  xor     ebx, ebx
0x18000bc0d  mov     rdx, [rsp+98h+ulCookie]; ulCookie
0x18000bc15  xor     ecx, ecx; dwFlags
0x18000bc17  call    cs:__imp_DeactivateActCtx
0x18000bc1d  test    edi, edi
0x18000bc1f  jz      short loc_18000BC29
0x18000bc21  mov     ecx, ebx; dwErrCode
0x18000bc23  call    cs:__imp_SetLastError
0x18000bc29  mov     rax, rsi
0x18000bc2c  jmp     loc_18000BB65
0x180076291  push    rbx
0x180076293  push    rbp
0x180076294  push    rdi
0x180076295  sub     rsp, 60h
0x180076299  mov     rbp, rdx
0x18007629c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800762a3  jz      short loc_1800762AE
0x1800762a5  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800762ac  jnz     short loc_1800762E4
0x1800762ae  cmp     qword ptr [rbp+60h], 0
0x1800762b3  jnz     short loc_1800762C4
0x1800762b5  mov     edi, 1
0x1800762ba  call    cs:__imp_GetLastError
0x1800762c0  mov     ebx, eax
0x1800762c2  jmp     short loc_1800762C8
0x1800762c4  xor     edi, edi
0x1800762c6  xor     ebx, ebx
0x1800762c8  mov     rdx, [rbp+0F8h]; ulCookie
0x1800762cf  xor     ecx, ecx; dwFlags
0x1800762d1  call    cs:__imp_DeactivateActCtx
0x1800762d7  test    edi, edi
0x1800762d9  jz      short loc_1800762E4
0x1800762db  mov     ecx, ebx; dwErrCode
0x1800762dd  call    cs:__imp_SetLastError
0x1800762e3  nop
0x1800762e4  add     rsp, 60h
0x1800762e8  pop     rdi
0x1800762e9  pop     rbp
0x1800762ea  pop     rbx
0x1800762eb  retn
```
