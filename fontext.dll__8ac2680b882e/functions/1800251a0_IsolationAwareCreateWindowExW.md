# IsolationAwareCreateWindowExW

- ea: `0x1800251a0`
- end: `0x1800252b8`
- name: `IsolationAwareCreateWindowExW`
- size: `280`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, int, HWND, int, int, LPVOID)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180023d94`

## callees

- `0x18001ba28`
- `0x1800251a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003158d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003158d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800252aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800315b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800252aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800315b0`
- `KERNEL32!DeactivateActCtx` at `0x18002529e`
- `KERNEL32!DeactivateActCtx` at `0x1800315a4`
- `KERNEL32!DeactivateActCtx` at `0x18002529e`
- `KERNEL32!DeactivateActCtx` at `0x1800315a4`
- `USER32!CreateWindowExW` at `0x18002525e`
- `USER32!CreateWindowExW` at `0x18002525e`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExW(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int nWidth,
        int nHeight,
        HWND hWndParent,
        int a10,
        int a11,
        LPVOID lpParam)
{
  HINSTANCE hInstance; // rbx
  HWND Window; // rax
  HWND v15; // rsi
  int v16; // edi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+90h] [rbp+18h] BYREF

  hInstance = g_hInstance;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Window = CreateWindowExW(
             0,
             L"ShellFontPreview",
             L"ShellFontPreview",
             0x50200000u,
             0,
             0,
             nWidth,
             nHeight,
             hWndParent,
             0,
             hInstance,
             lpParam);
  v15 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v16 = 0;
      LastError = 0;
    }
    else
    {
      v16 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v16 )
      SetLastError(LastError);
  }
  return v15;
}

```

## disassembly

```asm
0x1800251a0  mov     rax, rsp
0x1800251a3  mov     [rax+8], rbx
0x1800251a7  mov     [rax+10h], rsi
0x1800251ab  mov     [rax+18h], r8
0x1800251af  push    rdi
0x1800251b0  sub     rsp, 70h
0x1800251b4  mov     rbx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800251bb  mov     qword ptr [rax-18h], 0
0x1800251c3  mov     qword ptr [rax+18h], 0
0x1800251cb  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800251d2  jnz     short loc_1800251FE
0x1800251d4  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800251db  jnz     short loc_1800251FE
0x1800251dd  lea     rcx, [rax+18h]; lpCookie
0x1800251e1  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800251e6  test    eax, eax
0x1800251e8  jnz     short loc_1800251FE
0x1800251ea  xor     eax, eax
0x1800251ec  lea     r11, [rsp+78h+var_8]
0x1800251f1  mov     rbx, [r11+10h]
0x1800251f5  mov     rsi, [r11+18h]
0x1800251f9  mov     rsp, r11
0x1800251fc  pop     rdi
0x1800251fd  retn
0x1800251fe  mov     rax, [rsp+78h+arg_58]
0x180025206  mov     [rsp+78h+lpParam], rax; lpParam
0x18002520b  mov     [rsp+78h+hInstance], rbx; hInstance
0x180025210  mov     [rsp+78h+hMenu], 0; hMenu
0x180025219  mov     rax, [rsp+78h+arg_40]
0x180025221  mov     [rsp+78h+hWndParent], rax; hWndParent
0x180025226  mov     eax, [rsp+78h+arg_38]
0x18002522d  mov     [rsp+78h+nHeight], eax; nHeight
0x180025231  mov     eax, [rsp+78h+arg_30]
0x180025238  mov     [rsp+78h+nWidth], eax; nWidth
0x18002523c  mov     [rsp+78h+Y], 0; Y
0x180025244  mov     [rsp+78h+X], 0; X
0x18002524c  mov     r9d, 50200000h; dwStyle
0x180025252  lea     rdx, ClassName; "ShellFontPreview"
0x180025259  mov     r8, rdx; lpWindowName
0x18002525c  xor     ecx, ecx; dwExStyle
0x18002525e  call    cs:__imp_CreateWindowExW
0x180025264  mov     rsi, rax
0x180025267  mov     [rsp+78h+var_18], rax
0x18002526c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180025273  jz      short loc_18002527E
0x180025275  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002527c  jnz     short loc_1800252B0
0x18002527e  test    rsi, rsi
0x180025281  jnz     short loc_180025290
0x180025283  lea     edi, [rsi+1]
0x180025286  call    cs:__imp_GetLastError
0x18002528c  mov     ebx, eax
0x18002528e  jmp     short loc_180025294
0x180025290  xor     edi, edi
0x180025292  xor     ebx, ebx
0x180025294  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x18002529c  xor     ecx, ecx; dwFlags
0x18002529e  call    cs:__imp_DeactivateActCtx
0x1800252a4  test    edi, edi
0x1800252a6  jz      short loc_1800252B0
0x1800252a8  mov     ecx, ebx; dwErrCode
0x1800252aa  call    cs:__imp_SetLastError
0x1800252b0  mov     rax, rsi
0x1800252b3  jmp     loc_1800251EC
0x180031564  push    rbx
0x180031566  push    rbp
0x180031567  push    rdi
0x180031568  sub     rsp, 60h
0x18003156c  mov     rbp, rdx
0x18003156f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180031576  jz      short loc_180031581
0x180031578  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003157f  jnz     short loc_1800315B7
0x180031581  cmp     qword ptr [rbp+60h], 0
0x180031586  jnz     short loc_180031597
0x180031588  mov     edi, 1
0x18003158d  call    cs:__imp_GetLastError
0x180031593  mov     ebx, eax
0x180031595  jmp     short loc_18003159B
0x180031597  xor     edi, edi
0x180031599  xor     ebx, ebx
0x18003159b  mov     rdx, [rbp+90h]; ulCookie
0x1800315a2  xor     ecx, ecx; dwFlags
0x1800315a4  call    cs:__imp_DeactivateActCtx
0x1800315aa  test    edi, edi
0x1800315ac  jz      short loc_1800315B7
0x1800315ae  mov     ecx, ebx; dwErrCode
0x1800315b0  call    cs:__imp_SetLastError
0x1800315b6  nop
0x1800315b7  add     rsp, 60h
0x1800315bb  pop     rdi
0x1800315bc  pop     rbp
0x1800315bd  pop     rbx
0x1800315be  retn
```
