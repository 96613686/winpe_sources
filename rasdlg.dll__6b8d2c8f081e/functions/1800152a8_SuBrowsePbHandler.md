# SuBrowsePbHandler

- ea: `0x1800152a8`
- end: `0x18001548f`
- name: `SuBrowsePbHandler`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180018a30`

## callees

- `0x1800152a8`
- `0x180039514`
- `0x18003bea0`
- `0x18003c43c`
- `0x18003cec0`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `RASAPI32!GetPhonebookDirectory` at `0x1800153ba`
- `RASAPI32!GetPhonebookDirectory` at `0x1800153ba`
- `USER32!SetWindowTextW` at `0x180015444`
- `USER32!SetWindowTextW` at `0x180015444`
- `USER32!GetParent` at `0x1800153de`
- `USER32!GetParent` at `0x1800153de`

## pseudocode

```c
__int64 __fastcall SuBrowsePbHandler(__int64 a1, __int16 a2)
{
  WCHAR *v4; // r14
  WCHAR *v5; // r15
  void *v6; // rdi
  void *v7; // rbx
  unsigned int v8; // esi
  __int64 v9; // rax
  __int64 v10; // rax
  HWND v11; // rcx
  HWND Parent; // rax
  tagOFNW v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[128]; // [rsp+D0h] [rbp-30h] BYREF
  _WORD v16[264]; // [rsp+150h] [rbp+50h] BYREF
  __int16 v17; // [rsp+360h] [rbp+260h] BYREF

  *(&v14.lStructSize + 1) = 0;
  memset_0(&v14, 0, 0x94u);
  v4 = 0;
  v5 = 0;
  if ( a2 )
  {
    v6 = 0;
    v7 = 0;
LABEL_3:
    v8 = 0;
    goto LABEL_9;
  }
  v6 = (void *)PszFromId(g_hinstDll, 0x1CAu);
  v9 = PszFromId(g_hinstDll, 0x1C9u);
  v7 = (void *)v9;
  if ( v6 )
  {
    if ( v9 )
    {
      memset_0(v15, 0, sizeof(v15));
      if ( (unsigned int)StringCchPrintfWrapW(v15, 64, L"%s%s", v6, v7) )
        goto LABEL_3;
    }
  }
  v5 = (WCHAR *)PszFromId(g_hinstDll, 0x1CBu);
  v10 = PszFromId(g_hinstDll, 0x1C8u);
  v8 = 1;
  v17 = 0;
  v16[0] = 0;
  v4 = (WCHAR *)v10;
  GetPhonebookDirectory(2, v16, 261);
  memset_0(&v14.lStructSize + 1, 0, 0x94u);
  v11 = *(HWND *)(a1 + 16);
  v14.lStructSize = 152;
  Parent = GetParent(v11);
  v14.nFilterIndex = 1;
  v14.hwndOwner = Parent;
  v14.hInstance = g_hinstDll;
  v14.lpstrFilter = (LPCWSTR)v15;
  v14.lpstrFile = (LPWSTR)&v17;
  v14.lpstrInitialDir = v16;
  v14.nMaxFile = 260;
  v14.lpstrTitle = v5;
  v14.lpstrDefExt = v4;
  v14.Flags = 4;
  if ( GetOpenFileNameW(&v14) )
    SetWindowTextW(*(HWND *)(a1 + 16), v14.lpstrFile);
LABEL_9:
  Free0(v6);
  Free0(v7);
  Free0(v5);
  Free0(v4);
  return v8;
}

```

## disassembly

```asm
0x1800152a8  push    rbp
0x1800152aa  push    rbx
0x1800152ab  push    rsi
0x1800152ac  push    rdi
0x1800152ad  push    r12
0x1800152af  push    r13
0x1800152b1  push    r14
0x1800152b3  push    r15
0x1800152b5  lea     rbp, [rsp-488h]
0x1800152bd  sub     rsp, 588h
0x1800152c4  mov     rax, cs:__security_cookie
0x1800152cb  xor     rax, rsp
0x1800152ce  mov     [rbp+4C0h+var_50], rax
0x1800152d5  movzx   ebx, dx
0x1800152d8  mov     r13, rcx
0x1800152db  xor     eax, eax
0x1800152dd  lea     rcx, [rsp+5C0h+var_590]; void *
0x1800152e2  xor     edx, edx; Val
0x1800152e4  mov     dword ptr [rsp+5C0h+var_590+4], eax
0x1800152e8  mov     r8d, 94h; Size
0x1800152ee  call    memset_0
0x1800152f3  xor     r12d, r12d
0x1800152f6  mov     r14d, r12d
0x1800152f9  mov     r15d, r12d
0x1800152fc  test    bx, bx
0x1800152ff  jz      short loc_18001530F
0x180015301  mov     edi, r12d
0x180015304  mov     ebx, r12d
0x180015307  mov     esi, r12d
0x18001530a  jmp     loc_18001544A
0x18001530f  mov     rcx, cs:g_hinstDll; hInstance
0x180015316  mov     edx, 1CAh; uID
0x18001531b  call    PszFromId
0x180015320  mov     rcx, cs:g_hinstDll; hInstance
0x180015327  mov     edx, 1C9h; uID
0x18001532c  mov     rdi, rax
0x18001532f  call    PszFromId
0x180015334  mov     rbx, rax
0x180015337  test    rdi, rdi
0x18001533a  jz      short loc_180015373
0x18001533c  test    rax, rax
0x18001533f  jz      short loc_180015373
0x180015341  xor     edx, edx; Val
0x180015343  lea     rcx, [rbp+4C0h+var_4F0]; void *
0x180015347  mov     r8d, 80h; Size
0x18001534d  call    memset_0
0x180015352  mov     r9, rdi
0x180015355  mov     [rsp+5C0h+var_5A0], rbx
0x18001535a  lea     r8, aSS_1; "%s%s"
0x180015361  mov     edx, 40h ; '@'
0x180015366  lea     rcx, [rbp+4C0h+var_4F0]
0x18001536a  call    StringCchPrintfWrapW
0x18001536f  test    eax, eax
0x180015371  jnz     short loc_180015307
0x180015373  mov     rcx, cs:g_hinstDll; hInstance
0x18001537a  mov     edx, 1CBh; uID
0x18001537f  call    PszFromId
0x180015384  mov     rcx, cs:g_hinstDll; hInstance
0x18001538b  mov     edx, 1C8h; uID
0x180015390  mov     r15, rax
0x180015393  call    PszFromId
0x180015398  mov     esi, 1
0x18001539d  mov     [rbp+4C0h+var_260], r12w
0x1800153a5  mov     r8d, 105h
0x1800153ab  mov     [rbp+4C0h+var_470], r12w
0x1800153b0  lea     rdx, [rbp+4C0h+var_470]
0x1800153b4  mov     r14, rax
0x1800153b7  lea     ecx, [rsi+1]
0x1800153ba  call    cs:__imp_GetPhonebookDirectory
0x1800153c0  xor     edx, edx; Val
0x1800153c2  lea     rcx, [rsp+5C0h+var_590+4]; void *
0x1800153c7  mov     r8d, 94h; Size
0x1800153cd  call    memset_0
0x1800153d2  mov     rcx, [r13+10h]; hWnd
0x1800153d6  mov     [rsp+5C0h+var_590.lStructSize], 98h
0x1800153de  call    cs:__imp_GetParent
0x1800153e4  lea     rcx, [rsp+5C0h+var_590]; LPOPENFILENAMEW
0x1800153e9  mov     [rsp+5C0h+var_590.nFilterIndex], esi
0x1800153ed  mov     [rsp+5C0h+var_590.hwndOwner], rax
0x1800153f2  mov     rax, cs:g_hinstDll
0x1800153f9  mov     [rsp+5C0h+var_590.hInstance], rax
0x1800153fe  lea     rax, [rbp+4C0h+var_4F0]
0x180015402  mov     [rsp+5C0h+var_590.lpstrFilter], rax
0x180015407  lea     rax, [rbp+4C0h+var_260]
0x18001540e  mov     [rsp+5C0h+var_590.lpstrFile], rax
0x180015413  lea     rax, [rbp+4C0h+var_470]
0x180015417  mov     [rbp+4C0h+var_590.lpstrInitialDir], rax
0x18001541b  mov     [rsp+5C0h+var_590.nMaxFile], 104h
0x180015423  mov     [rbp+4C0h+var_590.lpstrTitle], r15
0x180015427  mov     [rbp+4C0h+var_590.lpstrDefExt], r14
0x18001542b  mov     [rbp+4C0h+var_590.Flags], 4
0x180015432  call    GetOpenFileNameW
0x180015437  test    eax, eax
0x180015439  jz      short loc_18001544A
0x18001543b  mov     rdx, [rsp+5C0h+var_590.lpstrFile]; lpString
0x180015440  mov     rcx, [r13+10h]; hWnd
0x180015444  call    cs:__imp_SetWindowTextW
0x18001544a  mov     rcx, rdi
0x18001544d  call    Free0
0x180015452  mov     rcx, rbx
0x180015455  call    Free0
0x18001545a  mov     rcx, r15
0x18001545d  call    Free0
0x180015462  mov     rcx, r14
0x180015465  call    Free0
0x18001546a  mov     eax, esi
0x18001546c  mov     rcx, [rbp+4C0h+var_50]
0x180015473  xor     rcx, rsp; StackCookie
0x180015476  call    __security_check_cookie
0x18001547b  add     rsp, 588h
0x180015482  pop     r15
0x180015484  pop     r14
0x180015486  pop     r13
0x180015488  pop     r12
0x18001548a  pop     rdi
0x18001548b  pop     rsi
0x18001548c  pop     rbx
0x18001548d  pop     rbp
0x18001548e  retn
```
