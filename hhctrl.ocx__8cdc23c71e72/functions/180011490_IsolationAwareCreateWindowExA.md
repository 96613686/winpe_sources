# IsolationAwareCreateWindowExA

- ea: `0x180011490`
- end: `0x1800115a7`
- name: `IsolationAwareCreateWindowExA`
- size: `279`
- prototype: `__int64 __fastcall(DWORD dwExStyle, LPCSTR lpClassName, LPCSTR lpWindowName, DWORD dwStyle, int, int, int, int, HWND, HMENU, HINSTANCE, LPVOID)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1800102d4`
- `0x18001054c`
- `0x1800228c0`
- `0x180023300`
- `0x180025590`
- `0x180034a90`
- `0x180035510`
- `0x180043cd8`
- `0x180048be4`
- `0x1800500b4`
- `0x180050158`
- `0x1800586d0`
- `0x180058b0c`
- `0x18006c52c`
- `0x18006eaf4`

## callees

- `0x180002b18`
- `0x180011490`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011578`
- `KERNEL32!GetLastError` at `0x18007648b`
- `KERNEL32!GetLastError` at `0x180011578`
- `KERNEL32!GetLastError` at `0x18007648b`
- `KERNEL32!DeactivateActCtx` at `0x18001158d`
- `KERNEL32!DeactivateActCtx` at `0x18007649f`
- `KERNEL32!DeactivateActCtx` at `0x18001158d`
- `KERNEL32!DeactivateActCtx` at `0x18007649f`
- `KERNEL32!SetLastError` at `0x180011599`
- `KERNEL32!SetLastError` at `0x1800764ab`
- `KERNEL32!SetLastError` at `0x180011599`
- `KERNEL32!SetLastError` at `0x1800764ab`
- `USER32!CreateWindowExA` at `0x180011550`
- `USER32!CreateWindowExA` at `0x180011550`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExA(
        DWORD dwExStyle,
        LPCSTR lpClassName,
        LPCSTR lpWindowName,
        DWORD dwStyle,
        int X,
        int Y,
        int nWidth,
        int nHeight,
        HWND hWndParent,
        HMENU hMenu,
        HINSTANCE hInstance,
        LPVOID lpParam)
{
  HWND Window; // rax
  HWND v18; // rsi
  int v19; // edi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+60h] [rbp-38h] BYREF
  HWND v22; // [rsp+68h] [rbp-30h]

  v22 = 0;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Window = CreateWindowExA(
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
             lpParam);
  v18 = Window;
  v22 = Window;
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
0x180011490  push    rbx
0x180011492  push    rsi
0x180011493  push    rdi
0x180011494  push    r14
0x180011496  sub     rsp, 78h
0x18001149a  mov     ebx, r9d
0x18001149d  mov     rdi, r8
0x1800114a0  mov     rsi, rdx
0x1800114a3  mov     r14d, ecx
0x1800114a6  mov     [rsp+98h+var_30], 0
0x1800114af  mov     [rsp+98h+ulCookie], 0
0x1800114b8  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800114bf  jnz     short loc_1800114E4
0x1800114c1  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800114c8  jnz     short loc_1800114E4
0x1800114ca  lea     rcx, [rsp+98h+ulCookie]; lpCookie
0x1800114cf  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800114d4  test    eax, eax
0x1800114d6  jnz     short loc_1800114E4
0x1800114d8  xor     eax, eax
0x1800114da  add     rsp, 78h
0x1800114de  pop     r14
0x1800114e0  pop     rdi
0x1800114e1  pop     rsi
0x1800114e2  pop     rbx
0x1800114e3  retn
0x1800114e4  mov     rax, [rsp+98h+arg_58]
0x1800114ec  mov     [rsp+98h+lpParam], rax; lpParam
0x1800114f1  mov     rax, [rsp+98h+arg_50]
0x1800114f9  mov     [rsp+98h+hInstance], rax; hInstance
0x1800114fe  mov     rax, [rsp+98h+arg_48]
0x180011506  mov     [rsp+98h+hMenu], rax; hMenu
0x18001150b  mov     rax, [rsp+98h+arg_40]
0x180011513  mov     [rsp+98h+hWndParent], rax; hWndParent
0x180011518  mov     eax, [rsp+98h+arg_38]
0x18001151f  mov     [rsp+98h+nHeight], eax; nHeight
0x180011523  mov     eax, [rsp+98h+arg_30]
0x18001152a  mov     [rsp+98h+nWidth], eax; nWidth
0x18001152e  mov     eax, [rsp+98h+arg_28]
0x180011535  mov     [rsp+98h+Y], eax; Y
0x180011539  mov     eax, [rsp+98h+arg_20]
0x180011540  mov     [rsp+98h+X], eax; X
0x180011544  mov     r9d, ebx; dwStyle
0x180011547  mov     r8, rdi; lpWindowName
0x18001154a  mov     rdx, rsi; lpClassName
0x18001154d  mov     ecx, r14d; dwExStyle
0x180011550  call    cs:__imp_CreateWindowExA
0x180011556  mov     rsi, rax
0x180011559  mov     [rsp+98h+var_30], rax
0x18001155e  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180011565  jz      short loc_180011570
0x180011567  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001156e  jnz     short loc_18001159F
0x180011570  test    rsi, rsi
0x180011573  jnz     short loc_180011582
0x180011575  lea     edi, [rsi+1]
0x180011578  call    cs:__imp_GetLastError
0x18001157e  mov     ebx, eax
0x180011580  jmp     short loc_180011586
0x180011582  xor     edi, edi
0x180011584  xor     ebx, ebx
0x180011586  mov     rdx, [rsp+98h+ulCookie]; ulCookie
0x18001158b  xor     ecx, ecx; dwFlags
0x18001158d  call    cs:__imp_DeactivateActCtx
0x180011593  test    edi, edi
0x180011595  jz      short loc_18001159F
0x180011597  mov     ecx, ebx; dwErrCode
0x180011599  call    cs:__imp_SetLastError
0x18001159f  mov     rax, rsi
0x1800115a2  jmp     loc_1800114DA
0x180076462  push    rbx
0x180076464  push    rbp
0x180076465  push    rdi
0x180076466  sub     rsp, 60h
0x18007646a  mov     rbp, rdx
0x18007646d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180076474  jz      short loc_18007647F
0x180076476  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18007647d  jnz     short loc_1800764B2
0x18007647f  cmp     qword ptr [rbp+68h], 0
0x180076484  jnz     short loc_180076495
0x180076486  mov     edi, 1
0x18007648b  call    cs:__imp_GetLastError
0x180076491  mov     ebx, eax
0x180076493  jmp     short loc_180076499
0x180076495  xor     edi, edi
0x180076497  xor     ebx, ebx
0x180076499  mov     rdx, [rbp+60h]; ulCookie
0x18007649d  xor     ecx, ecx; dwFlags
0x18007649f  call    cs:__imp_DeactivateActCtx
0x1800764a5  test    edi, edi
0x1800764a7  jz      short loc_1800764B2
0x1800764a9  mov     ecx, ebx; dwErrCode
0x1800764ab  call    cs:__imp_SetLastError
0x1800764b1  nop
0x1800764b2  add     rsp, 60h
0x1800764b6  pop     rdi
0x1800764b7  pop     rbp
0x1800764b8  pop     rbx
0x1800764b9  retn
```
