# IsolationAwareCreateWindowExW

- ea: `0x180030a38`
- end: `0x180030b53`
- name: `IsolationAwareCreateWindowExW`
- size: `283`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, int, HWND, int, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002f3cc`

## callees

- `0x18002d87c`
- `0x180030a38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d21a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030b45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d23d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030b45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d23d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180030b39`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005d231`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180030b39`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005d231`
- `USER32!CreateWindowExW` at `0x180030af9`
- `USER32!CreateWindowExW` at `0x180030af9`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExW(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int X,
        int Y,
        int nWidth,
        int nHeight,
        HWND hWndParent,
        int a10,
        HINSTANCE hInstance)
{
  HWND Window; // rax
  HWND v13; // rsi
  int v14; // edi
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
             L"MSDRM Trident Window",
             L"MSDRM Trident Window",
             0x50000000u,
             X,
             Y,
             nWidth,
             nHeight,
             hWndParent,
             0,
             hInstance,
             0);
  v13 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v14 = 0;
      LastError = 0;
    }
    else
    {
      v14 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v14 )
      SetLastError(LastError);
  }
  return v13;
}

```

## disassembly

```asm
0x180030a38  mov     rax, rsp
0x180030a3b  mov     [rax+8], rbx
0x180030a3f  mov     [rax+10h], rsi
0x180030a43  mov     [rax+18h], r8
0x180030a47  push    rdi
0x180030a48  sub     rsp, 70h
0x180030a4c  mov     qword ptr [rax-18h], 0
0x180030a54  mov     qword ptr [rax+18h], 0
0x180030a5c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180030a63  jnz     short loc_180030A8F
0x180030a65  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180030a6c  jnz     short loc_180030A8F
0x180030a6e  lea     rcx, [rax+18h]; lpCookie
0x180030a72  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180030a77  test    eax, eax
0x180030a79  jnz     short loc_180030A8F
0x180030a7b  xor     eax, eax
0x180030a7d  lea     r11, [rsp+78h+var_8]
0x180030a82  mov     rbx, [r11+10h]
0x180030a86  mov     rsi, [r11+18h]
0x180030a8a  mov     rsp, r11
0x180030a8d  pop     rdi
0x180030a8e  retn
0x180030a8f  mov     [rsp+78h+lpParam], 0; lpParam
0x180030a98  mov     rax, [rsp+78h+arg_50]
0x180030aa0  mov     [rsp+78h+hInstance], rax; hInstance
0x180030aa5  mov     [rsp+78h+hMenu], 0; hMenu
0x180030aae  mov     rax, [rsp+78h+arg_40]
0x180030ab6  mov     [rsp+78h+hWndParent], rax; hWndParent
0x180030abb  mov     eax, [rsp+78h+arg_38]
0x180030ac2  mov     [rsp+78h+nHeight], eax; nHeight
0x180030ac6  mov     eax, [rsp+78h+arg_30]
0x180030acd  mov     [rsp+78h+nWidth], eax; nWidth
0x180030ad1  mov     eax, [rsp+78h+arg_28]
0x180030ad8  mov     [rsp+78h+Y], eax; Y
0x180030adc  mov     eax, [rsp+78h+arg_20]
0x180030ae3  mov     [rsp+78h+X], eax; X
0x180030ae7  mov     r9d, 50000000h; dwStyle
0x180030aed  lea     rdx, ClassName; "MSDRM Trident Window"
0x180030af4  mov     r8, rdx; lpWindowName
0x180030af7  xor     ecx, ecx; dwExStyle
0x180030af9  call    cs:__imp_CreateWindowExW
0x180030aff  mov     rsi, rax
0x180030b02  mov     [rsp+78h+var_18], rax
0x180030b07  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180030b0e  jz      short loc_180030B19
0x180030b10  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180030b17  jnz     short loc_180030B4B
0x180030b19  test    rsi, rsi
0x180030b1c  jnz     short loc_180030B2B
0x180030b1e  lea     edi, [rsi+1]
0x180030b21  call    cs:__imp_GetLastError
0x180030b27  mov     ebx, eax
0x180030b29  jmp     short loc_180030B2F
0x180030b2b  xor     edi, edi
0x180030b2d  xor     ebx, ebx
0x180030b2f  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x180030b37  xor     ecx, ecx; dwFlags
0x180030b39  call    cs:__imp_DeactivateActCtx
0x180030b3f  test    edi, edi
0x180030b41  jz      short loc_180030B4B
0x180030b43  mov     ecx, ebx; dwErrCode
0x180030b45  call    cs:__imp_SetLastError
0x180030b4b  mov     rax, rsi
0x180030b4e  jmp     loc_180030A7D
0x18005d1f1  push    rbx
0x18005d1f3  push    rbp
0x18005d1f4  push    rdi
0x18005d1f5  sub     rsp, 60h
0x18005d1f9  mov     rbp, rdx
0x18005d1fc  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18005d203  jz      short loc_18005D20E
0x18005d205  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18005d20c  jnz     short loc_18005D244
0x18005d20e  cmp     qword ptr [rbp+60h], 0
0x18005d213  jnz     short loc_18005D224
0x18005d215  mov     edi, 1
0x18005d21a  call    cs:__imp_GetLastError
0x18005d220  mov     ebx, eax
0x18005d222  jmp     short loc_18005D228
0x18005d224  xor     edi, edi
0x18005d226  xor     ebx, ebx
0x18005d228  mov     rdx, [rbp+90h]; ulCookie
0x18005d22f  xor     ecx, ecx; dwFlags
0x18005d231  call    cs:__imp_DeactivateActCtx
0x18005d237  test    edi, edi
0x18005d239  jz      short loc_18005D244
0x18005d23b  mov     ecx, ebx; dwErrCode
0x18005d23d  call    cs:__imp_SetLastError
0x18005d243  nop
0x18005d244  add     rsp, 60h
0x18005d248  pop     rdi
0x18005d249  pop     rbp
0x18005d24a  pop     rbx
0x18005d24b  retn
```
