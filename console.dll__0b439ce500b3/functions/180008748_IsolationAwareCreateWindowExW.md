# IsolationAwareCreateWindowExW

- ea: `0x180008748`
- end: `0x180008863`
- name: `IsolationAwareCreateWindowExW`
- size: `283`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, int, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000788c`

## callees

- `0x1800071a0`
- `0x180008748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000884f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019204`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000884f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000881f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800191d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000881f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800191d5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000883d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800191f2`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000883d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800191f2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800087f4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800087f4`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExW(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        HWND hWndParent)
{
  HINSTANCE hInstance; // rbx
  int v11; // esi
  HWND Window; // rax
  HWND v13; // rdi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+90h] [rbp+18h] BYREF

  hInstance = ghInstance;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  v11 = 1;
  Window = CreateWindowExW(
             0,
             L"tooltips_class32",
             0,
             1u,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             hWndParent,
             0,
             hInstance,
             0);
  v13 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v11 = 0;
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v11 )
      SetLastError(LastError);
  }
  return v13;
}

```

## disassembly

```asm
0x180008748  mov     rax, rsp
0x18000874b  mov     [rax+8], rbx
0x18000874f  mov     [rax+10h], rsi
0x180008753  mov     [rax+18h], r8
0x180008757  push    rdi
0x180008758  sub     rsp, 70h
0x18000875c  mov     rbx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghInstance
0x180008763  mov     qword ptr [rax-18h], 0
0x18000876b  mov     qword ptr [rax+18h], 0
0x180008773  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000877a  jnz     short loc_1800087A7
0x18000877c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180008783  jnz     short loc_1800087A7
0x180008785  lea     rcx, [rax+18h]; lpCookie
0x180008789  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000878e  test    eax, eax
0x180008790  jnz     short loc_1800087A7
0x180008792  xor     eax, eax
0x180008794  lea     r11, [rsp+78h+var_8]
0x180008799  mov     rbx, [r11+10h]
0x18000879d  mov     rsi, [r11+18h]
0x1800087a1  mov     rsp, r11
0x1800087a4  pop     rdi
0x1800087a5  retn
0x1800087a7  mov     [rsp+78h+lpParam], 0; lpParam
0x1800087b0  mov     [rsp+78h+hInstance], rbx; hInstance
0x1800087b5  mov     [rsp+78h+hMenu], 0; hMenu
0x1800087be  mov     rax, [rsp+78h+arg_40]
0x1800087c6  mov     [rsp+78h+hWndParent], rax; hWndParent
0x1800087cb  mov     eax, 80000000h
0x1800087d0  mov     [rsp+78h+nHeight], eax; nHeight
0x1800087d4  mov     [rsp+78h+nWidth], eax; nWidth
0x1800087d8  mov     [rsp+78h+Y], eax; Y
0x1800087dc  mov     [rsp+78h+X], eax; X
0x1800087e0  mov     esi, 1
0x1800087e5  mov     r9d, esi; dwStyle
0x1800087e8  xor     r8d, r8d; lpWindowName
0x1800087eb  lea     rdx, ClassName; "tooltips_class32"
0x1800087f2  xor     ecx, ecx; dwExStyle
0x1800087f4  call    cs:__imp_CreateWindowExW
0x1800087fb  nop     dword ptr [rax+rax+00h]
0x180008800  mov     rdi, rax
0x180008803  mov     [rsp+78h+var_18], rax
0x180008808  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000880f  jz      short loc_18000881A
0x180008811  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180008818  jnz     short loc_18000885B
0x18000881a  test    rdi, rdi
0x18000881d  jnz     short loc_18000882F
0x18000881f  call    cs:__imp_GetLastError
0x180008826  nop     dword ptr [rax+rax+00h]
0x18000882b  mov     ebx, eax
0x18000882d  jmp     short loc_180008833
0x18000882f  xor     esi, esi
0x180008831  xor     ebx, ebx
0x180008833  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x18000883b  xor     ecx, ecx; dwFlags
0x18000883d  call    cs:__imp_DeactivateActCtx
0x180008844  nop     dword ptr [rax+rax+00h]
0x180008849  test    esi, esi
0x18000884b  jz      short loc_18000885B
0x18000884d  mov     ecx, ebx; dwErrCode
0x18000884f  call    cs:__imp_SetLastError
0x180008856  nop     dword ptr [rax+rax+00h]
0x18000885b  mov     rax, rdi
0x18000885e  jmp     loc_180008794
0x1800191ac  push    rbx
0x1800191ae  push    rbp
0x1800191af  push    rdi
0x1800191b0  sub     rsp, 60h
0x1800191b4  mov     rbp, rdx
0x1800191b7  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800191be  jz      short loc_1800191C9
0x1800191c0  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800191c7  jnz     short loc_180019211
0x1800191c9  cmp     qword ptr [rbp+60h], 0
0x1800191ce  jnz     short loc_1800191E5
0x1800191d0  mov     edi, 1
0x1800191d5  call    cs:__imp_GetLastError
0x1800191dc  nop     dword ptr [rax+rax+00h]
0x1800191e1  mov     ebx, eax
0x1800191e3  jmp     short loc_1800191E9
0x1800191e5  xor     edi, edi
0x1800191e7  xor     ebx, ebx
0x1800191e9  mov     rdx, [rbp+90h]; ulCookie
0x1800191f0  xor     ecx, ecx; dwFlags
0x1800191f2  call    cs:__imp_DeactivateActCtx
0x1800191f9  nop     dword ptr [rax+rax+00h]
0x1800191fe  test    edi, edi
0x180019200  jz      short loc_180019211
0x180019202  mov     ecx, ebx; dwErrCode
0x180019204  call    cs:__imp_SetLastError
0x18001920b  nop     dword ptr [rax+rax+00h]
0x180019210  nop
0x180019211  add     rsp, 60h
0x180019215  pop     rdi
0x180019216  pop     rbp
0x180019217  pop     rbx
0x180019218  retn
```
