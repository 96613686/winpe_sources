# IsolationAwareCreateWindowExW

- ea: `0x1800aa580`
- end: `0x1800aa673`
- name: `IsolationAwareCreateWindowExW`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18011f70c`

## callees

- `0x180051c7c`
- `0x1800aa580`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800aa63e`
- `KERNEL32!GetLastError` at `0x18014a461`
- `KERNEL32!GetLastError` at `0x1800aa63e`
- `KERNEL32!GetLastError` at `0x18014a461`
- `KERNEL32!SetLastError` at `0x1800aa664`
- `KERNEL32!SetLastError` at `0x18014a484`
- `KERNEL32!SetLastError` at `0x1800aa664`
- `KERNEL32!SetLastError` at `0x18014a484`
- `KERNEL32!DeactivateActCtx` at `0x1800aa658`
- `KERNEL32!DeactivateActCtx` at `0x18014a478`
- `KERNEL32!DeactivateActCtx` at `0x1800aa658`
- `KERNEL32!DeactivateActCtx` at `0x18014a478`
- `USER32!CreateWindowExW` at `0x1800aa616`
- `USER32!CreateWindowExW` at `0x1800aa616`

## pseudocode

```c
HWND IsolationAwareCreateWindowExW()
{
  HWND Window; // rax
  HWND v2; // rbx
  int v3; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+90h] [rbp+18h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Window = CreateWindowExW(
             0,
             L"OfficePowerManagerWindow",
             L"OfficePowerManagerWindow",
             0x8000000u,
             0,
             0,
             0,
             0,
             0,
             0,
             0,
             0);
  v2 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v3 = 0;
      LastError = 0;
    }
    else
    {
      v3 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v3 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x1800aa580  mov     rax, rsp
0x1800aa583  mov     [rax+8], rbx
0x1800aa587  mov     [rax+10h], rsi
0x1800aa58b  mov     [rax+20h], rdi
0x1800aa58f  mov     [rax+18h], r8
0x1800aa593  push    r14
0x1800aa595  sub     rsp, 70h
0x1800aa599  xor     r14d, r14d
0x1800aa59c  mov     [rax-18h], r14
0x1800aa5a0  mov     [rax+18h], r14
0x1800aa5a4  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, r14d
0x1800aa5ab  jnz     short loc_1800AA5DC
0x1800aa5ad  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, r14d
0x1800aa5b4  jnz     short loc_1800AA5DC
0x1800aa5b6  lea     rcx, [rax+18h]; lpCookie
0x1800aa5ba  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800aa5bf  test    eax, eax
0x1800aa5c1  jnz     short loc_1800AA5DC
0x1800aa5c3  xor     eax, eax
0x1800aa5c5  lea     r11, [rsp+78h+var_8]
0x1800aa5ca  mov     rbx, [r11+10h]
0x1800aa5ce  mov     rsi, [r11+18h]
0x1800aa5d2  mov     rdi, [r11+28h]
0x1800aa5d6  mov     rsp, r11
0x1800aa5d9  pop     r14
0x1800aa5db  retn
0x1800aa5dc  mov     [rsp+78h+lpParam], r14; lpParam
0x1800aa5e1  mov     [rsp+78h+hInstance], r14; hInstance
0x1800aa5e6  mov     [rsp+78h+hMenu], r14; hMenu
0x1800aa5eb  mov     [rsp+78h+hWndParent], r14; hWndParent
0x1800aa5f0  mov     [rsp+78h+nHeight], r14d; nHeight
0x1800aa5f5  mov     [rsp+78h+nWidth], r14d; nWidth
0x1800aa5fa  mov     [rsp+78h+Y], r14d; Y
0x1800aa5ff  mov     [rsp+78h+X], r14d; X
0x1800aa604  mov     r9d, 8000000h; dwStyle
0x1800aa60a  lea     rdx, ?c_szPowerManagerWindowClassName@@3QB_WB; "OfficePowerManagerWindow"
0x1800aa611  mov     r8, rdx; lpWindowName
0x1800aa614  xor     ecx, ecx; dwExStyle
0x1800aa616  call    cs:__imp_CreateWindowExW
0x1800aa61c  mov     rbx, rax
0x1800aa61f  mov     [rsp+78h+var_18], rax
0x1800aa624  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, r14d
0x1800aa62b  jz      short loc_1800AA636
0x1800aa62d  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, r14d
0x1800aa634  jnz     short loc_1800AA66A
0x1800aa636  test    rbx, rbx
0x1800aa639  jnz     short loc_1800AA648
0x1800aa63b  lea     esi, [rbx+1]
0x1800aa63e  call    cs:__imp_GetLastError
0x1800aa644  mov     edi, eax
0x1800aa646  jmp     short loc_1800AA64E
0x1800aa648  mov     esi, r14d
0x1800aa64b  mov     edi, r14d
0x1800aa64e  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x1800aa656  xor     ecx, ecx; dwFlags
0x1800aa658  call    cs:__imp_DeactivateActCtx
0x1800aa65e  test    esi, esi
0x1800aa660  jz      short loc_1800AA66A
0x1800aa662  mov     ecx, edi; dwErrCode
0x1800aa664  call    cs:__imp_SetLastError
0x1800aa66a  mov     rax, rbx
0x1800aa66d  jmp     loc_1800AA5C5
0x18014a438  push    rbx
0x18014a43a  push    rbp
0x18014a43b  push    rdi
0x18014a43c  sub     rsp, 60h
0x18014a440  mov     rbp, rdx
0x18014a443  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18014a44a  jz      short loc_18014A455
0x18014a44c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18014a453  jnz     short loc_18014A48B
0x18014a455  cmp     qword ptr [rbp+60h], 0
0x18014a45a  jnz     short loc_18014A46B
0x18014a45c  mov     edi, 1
0x18014a461  call    cs:__imp_GetLastError
0x18014a467  mov     ebx, eax
0x18014a469  jmp     short loc_18014A46F
0x18014a46b  xor     edi, edi
0x18014a46d  xor     ebx, ebx
0x18014a46f  mov     rdx, [rbp+90h]; ulCookie
0x18014a476  xor     ecx, ecx; dwFlags
0x18014a478  call    cs:__imp_DeactivateActCtx
0x18014a47e  test    edi, edi
0x18014a480  jz      short loc_18014A48B
0x18014a482  mov     ecx, ebx; dwErrCode
0x18014a484  call    cs:__imp_SetLastError
0x18014a48a  nop
0x18014a48b  add     rsp, 60h
0x18014a48f  pop     rdi
0x18014a490  pop     rbp
0x18014a491  pop     rbx
0x18014a492  retn
```
