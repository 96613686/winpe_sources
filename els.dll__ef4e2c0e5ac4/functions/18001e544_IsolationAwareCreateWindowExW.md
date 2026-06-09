# IsolationAwareCreateWindowExW

- ea: `0x18001e544`
- end: `0x18001e652`
- name: `IsolationAwareCreateWindowExW`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e178`

## callees

- `0x18000911c`
- `0x18001e544`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e620`
- `KERNEL32!GetLastError` at `0x1800233c4`
- `KERNEL32!GetLastError` at `0x18001e620`
- `KERNEL32!GetLastError` at `0x1800233c4`
- `KERNEL32!SetLastError` at `0x18001e644`
- `KERNEL32!SetLastError` at `0x1800233e7`
- `KERNEL32!SetLastError` at `0x18001e644`
- `KERNEL32!SetLastError` at `0x1800233e7`
- `KERNEL32!DeactivateActCtx` at `0x18001e638`
- `KERNEL32!DeactivateActCtx` at `0x1800233db`
- `KERNEL32!DeactivateActCtx` at `0x18001e638`
- `KERNEL32!DeactivateActCtx` at `0x1800233db`
- `USER32!CreateWindowExW` at `0x18001e5f8`
- `USER32!CreateWindowExW` at `0x18001e5f8`

## pseudocode

```c
HWND IsolationAwareCreateWindowExW()
{
  HINSTANCE hInstance; // rbx
  HWND Window; // rax
  HWND v3; // rbx
  int v4; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+90h] [rbp+18h] BYREF

  hInstance = g_hinst;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Window = CreateWindowExW(
             0,
             L"Event Viewer Snapin Synch",
             &String,
             0,
             0,
             0,
             0,
             0,
             HWND_MESSAGE,
             0,
             hInstance,
             &g_SynchWnd);
  v3 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v4 = 0;
      LastError = 0;
    }
    else
    {
      v4 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v4 )
      SetLastError(LastError);
  }
  return v3;
}

```

## disassembly

```asm
0x18001e544  mov     rax, rsp
0x18001e547  mov     [rax+8], rbx
0x18001e54b  mov     [rax+10h], rsi
0x18001e54f  mov     [rax+18h], r8
0x18001e553  push    rdi
0x18001e554  sub     rsp, 70h
0x18001e558  mov     rbx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18001e55f  mov     qword ptr [rax-18h], 0
0x18001e567  mov     qword ptr [rax+18h], 0
0x18001e56f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001e576  jnz     short loc_18001E5A2
0x18001e578  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e57f  jnz     short loc_18001E5A2
0x18001e581  lea     rcx, [rax+18h]; lpCookie
0x18001e585  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001e58a  test    eax, eax
0x18001e58c  jnz     short loc_18001E5A2
0x18001e58e  xor     eax, eax
0x18001e590  lea     r11, [rsp+78h+var_8]
0x18001e595  mov     rbx, [r11+10h]
0x18001e599  mov     rsi, [r11+18h]
0x18001e59d  mov     rsp, r11
0x18001e5a0  pop     rdi
0x18001e5a1  retn
0x18001e5a2  lea     rax, ?g_SynchWnd@@3VCSynchWindow@@A; CSynchWindow g_SynchWnd
0x18001e5a9  mov     [rsp+78h+lpParam], rax; lpParam
0x18001e5ae  mov     [rsp+78h+hInstance], rbx; hInstance
0x18001e5b3  mov     [rsp+78h+hMenu], 0; hMenu
0x18001e5bc  mov     [rsp+78h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18001e5c5  mov     [rsp+78h+nHeight], 0; nHeight
0x18001e5cd  mov     [rsp+78h+nWidth], 0; nWidth
0x18001e5d5  mov     [rsp+78h+Y], 0; Y
0x18001e5dd  mov     [rsp+78h+X], 0; X
0x18001e5e5  xor     r9d, r9d; dwStyle
0x18001e5e8  lea     r8, String; lpWindowName
0x18001e5ef  lea     rdx, ClassName; "Event Viewer Snapin Synch"
0x18001e5f6  xor     ecx, ecx; dwExStyle
0x18001e5f8  call    cs:__imp_CreateWindowExW
0x18001e5fe  mov     rbx, rax
0x18001e601  mov     [rsp+78h+var_18], rax
0x18001e606  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001e60d  jz      short loc_18001E618
0x18001e60f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e616  jnz     short loc_18001E64A
0x18001e618  test    rbx, rbx
0x18001e61b  jnz     short loc_18001E62A
0x18001e61d  lea     esi, [rbx+1]
0x18001e620  call    cs:__imp_GetLastError
0x18001e626  mov     edi, eax
0x18001e628  jmp     short loc_18001E62E
0x18001e62a  xor     esi, esi
0x18001e62c  xor     edi, edi
0x18001e62e  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x18001e636  xor     ecx, ecx; dwFlags
0x18001e638  call    cs:__imp_DeactivateActCtx
0x18001e63e  test    esi, esi
0x18001e640  jz      short loc_18001E64A
0x18001e642  mov     ecx, edi; dwErrCode
0x18001e644  call    cs:__imp_SetLastError
0x18001e64a  mov     rax, rbx
0x18001e64d  jmp     loc_18001E590
0x18002339b  push    rbx
0x18002339d  push    rbp
0x18002339e  push    rdi
0x18002339f  sub     rsp, 60h
0x1800233a3  mov     rbp, rdx
0x1800233a6  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800233ad  jz      short loc_1800233B8
0x1800233af  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800233b6  jnz     short loc_1800233EE
0x1800233b8  cmp     qword ptr [rbp+60h], 0
0x1800233bd  jnz     short loc_1800233CE
0x1800233bf  mov     edi, 1
0x1800233c4  call    cs:__imp_GetLastError
0x1800233ca  mov     ebx, eax
0x1800233cc  jmp     short loc_1800233D2
0x1800233ce  xor     edi, edi
0x1800233d0  xor     ebx, ebx
0x1800233d2  mov     rdx, [rbp+90h]; ulCookie
0x1800233d9  xor     ecx, ecx; dwFlags
0x1800233db  call    cs:__imp_DeactivateActCtx
0x1800233e1  test    edi, edi
0x1800233e3  jz      short loc_1800233EE
0x1800233e5  mov     ecx, ebx; dwErrCode
0x1800233e7  call    cs:__imp_SetLastError
0x1800233ed  nop
0x1800233ee  add     rsp, 60h
0x1800233f2  pop     rdi
0x1800233f3  pop     rbp
0x1800233f4  pop     rbx
0x1800233f5  retn
```
