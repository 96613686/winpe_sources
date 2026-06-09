# IsolationAwareCreateWindowExW

- ea: `0x180012b18`
- end: `0x180012c1c`
- name: `IsolationAwareCreateWindowExW`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180011740`
- `0x18003d7ec`

## callees

- `0x180005160`
- `0x180012b18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ede1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ede1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ee04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ee04`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180012c02`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003edf8`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180012c02`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003edf8`
- `USER32!CreateWindowExW` at `0x180012bc2`
- `USER32!CreateWindowExW` at `0x180012bc2`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExW(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        DWORD a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        HWND hWndParent,
        __int64 a10,
        HINSTANCE hInstance)
{
  HWND Window; // rax
  HWND v14; // rdi
  int v15; // esi
  DWORD LastError; // ebx
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
             L"tooltips_class32",
             0,
             a4,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             hWndParent,
             0,
             hInstance,
             0);
  v14 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v15 = 0;
      LastError = 0;
    }
    else
    {
      v15 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v15 )
      SetLastError(LastError);
  }
  return v14;
}

```

## disassembly

```asm
0x180012b18  mov     rax, rsp
0x180012b1b  mov     [rax+8], rbx
0x180012b1f  mov     [rax+10h], rsi
0x180012b23  mov     [rax+18h], r8
0x180012b27  push    rdi
0x180012b28  sub     rsp, 70h
0x180012b2c  mov     ebx, r9d
0x180012b2f  mov     qword ptr [rax-18h], 0
0x180012b37  mov     qword ptr [rax+18h], 0
0x180012b3f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180012b46  jnz     short loc_180012B72
0x180012b48  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180012b4f  jnz     short loc_180012B72
0x180012b51  lea     rcx, [rax+18h]; lpCookie
0x180012b55  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180012b5a  test    eax, eax
0x180012b5c  jnz     short loc_180012B72
0x180012b5e  xor     eax, eax
0x180012b60  lea     r11, [rsp+78h+var_8]
0x180012b65  mov     rbx, [r11+10h]
0x180012b69  mov     rsi, [r11+18h]
0x180012b6d  mov     rsp, r11
0x180012b70  pop     rdi
0x180012b71  retn
0x180012b72  mov     [rsp+78h+lpParam], 0; lpParam
0x180012b7b  mov     rax, [rsp+78h+arg_50]
0x180012b83  mov     [rsp+78h+hInstance], rax; hInstance
0x180012b88  mov     [rsp+78h+hMenu], 0; hMenu
0x180012b91  mov     rax, [rsp+78h+arg_40]
0x180012b99  mov     [rsp+78h+hWndParent], rax; hWndParent
0x180012b9e  mov     eax, 80000000h
0x180012ba3  mov     [rsp+78h+nHeight], eax; nHeight
0x180012ba7  mov     [rsp+78h+nWidth], eax; nWidth
0x180012bab  mov     [rsp+78h+Y], eax; Y
0x180012baf  mov     [rsp+78h+X], eax; X
0x180012bb3  mov     r9d, ebx; dwStyle
0x180012bb6  xor     r8d, r8d; lpWindowName
0x180012bb9  lea     rdx, ClassName; "tooltips_class32"
0x180012bc0  xor     ecx, ecx; dwExStyle
0x180012bc2  call    cs:__imp_CreateWindowExW
0x180012bc8  mov     rdi, rax
0x180012bcb  mov     [rsp+78h+var_18], rax
0x180012bd0  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180012bd7  jz      short loc_180012BE2
0x180012bd9  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180012be0  jnz     short loc_180012C14
0x180012be2  test    rdi, rdi
0x180012be5  jnz     short loc_180012BF4
0x180012be7  lea     esi, [rdi+1]
0x180012bea  call    cs:__imp_GetLastError
0x180012bf0  mov     ebx, eax
0x180012bf2  jmp     short loc_180012BF8
0x180012bf4  xor     esi, esi
0x180012bf6  xor     ebx, ebx
0x180012bf8  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x180012c00  xor     ecx, ecx; dwFlags
0x180012c02  call    cs:__imp_DeactivateActCtx
0x180012c08  test    esi, esi
0x180012c0a  jz      short loc_180012C14
0x180012c0c  mov     ecx, ebx; dwErrCode
0x180012c0e  call    cs:__imp_SetLastError
0x180012c14  mov     rax, rdi
0x180012c17  jmp     loc_180012B60
0x18003edb8  push    rbx
0x18003edba  push    rbp
0x18003edbb  push    rdi
0x18003edbc  sub     rsp, 60h
0x18003edc0  mov     rbp, rdx
0x18003edc3  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003edca  jz      short loc_18003EDD5
0x18003edcc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003edd3  jnz     short loc_18003EE0B
0x18003edd5  cmp     qword ptr [rbp+60h], 0
0x18003edda  jnz     short loc_18003EDEB
0x18003eddc  mov     edi, 1
0x18003ede1  call    cs:__imp_GetLastError
0x18003ede7  mov     ebx, eax
0x18003ede9  jmp     short loc_18003EDEF
0x18003edeb  xor     edi, edi
0x18003eded  xor     ebx, ebx
0x18003edef  mov     rdx, [rbp+90h]; ulCookie
0x18003edf6  xor     ecx, ecx; dwFlags
0x18003edf8  call    cs:__imp_DeactivateActCtx
0x18003edfe  test    edi, edi
0x18003ee00  jz      short loc_18003EE0B
0x18003ee02  mov     ecx, ebx; dwErrCode
0x18003ee04  call    cs:__imp_SetLastError
0x18003ee0a  nop
0x18003ee0b  add     rsp, 60h
0x18003ee0f  pop     rdi
0x18003ee10  pop     rbp
0x18003ee11  pop     rbx
0x18003ee12  retn
```
