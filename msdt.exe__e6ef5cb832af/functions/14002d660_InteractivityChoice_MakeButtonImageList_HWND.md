# InteractivityChoice::MakeButtonImageList(HWND__ *)

- ea: `0x14002d660`
- end: `0x14002d824`
- name: `?MakeButtonImageList@InteractivityChoice@@QEAAJPEAUHWND__@@@Z`
- size: `452`
- prototype: `int(InteractivityChoice *__hidden this, HWND)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002eed0`
- `0x14002f270`
- `0x1400309e0`

## callees

- `0x140020420`
- `0x14002d660`
- `0x140041e30`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002d7a1`
- `KERNEL32!GetLastError` at `0x14002d7a1`
- `USER32!GetWindowLongW` at `0x14002d6a2`
- `USER32!GetWindowLongW` at `0x14002d6a2`
- `USER32!GetSystemMetrics` at `0x14002d6ed`
- `USER32!GetSystemMetrics` at `0x14002d700`
- `USER32!GetSystemMetrics` at `0x14002d6ed`
- `USER32!GetSystemMetrics` at `0x14002d700`
- `USER32!SendMessageW` at `0x14002d7f2`
- `USER32!SendMessageW` at `0x14002d7f2`
- `COMCTL32!ImageList_ReplaceIcon` at `0x14002d746`
- `COMCTL32!ImageList_ReplaceIcon` at `0x14002d746`
- `COMCTL32!ImageList_Create` at `0x14002d721`
- `COMCTL32!ImageList_Create` at `0x14002d721`

## pseudocode

```c
__int64 __fastcall InteractivityChoice::MakeButtonImageList(InteractivityChoice *this, HWND a2)
{
  unsigned int v3; // edi
  LONG WindowLongW; // eax
  const unsigned __int16 *v6; // rcx
  UINT v7; // ebp
  int v8; // eax
  int SystemMetrics; // ebx
  int v10; // eax
  struct _IMAGELIST *v11; // rax
  signed int LastError; // eax
  HICON hicon; // [rsp+30h] [rbp-48h] BYREF
  LPARAM lParam[4]; // [rsp+38h] [rbp-40h] BYREF

  v3 = 0;
  hicon = 0;
  memset(lParam, 0, sizeof(lParam));
  WindowLongW = GetWindowLongW(a2, -20);
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 3);
  v7 = (WindowLongW & 0x400000 | 0x4200u) >> 9;
  if ( !v6 )
    goto LABEL_12;
  v8 = DwzLoadSmallIcon(v6, &hicon);
  v3 = v8;
  if ( v8 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityChoice::MakeButtonImageList", 279, v8);
LABEL_12:
    SendMessageW(a2, 0x1602u, 0, (LPARAM)lParam);
    return v3;
  }
  SystemMetrics = GetSystemMetrics(50);
  v10 = GetSystemMetrics(49);
  v11 = ImageList_Create(v10, SystemMetrics, v7, 1, 1);
  *((_QWORD *)this + 4) = v11;
  if ( (unsigned __int64)v11 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( ImageList_ReplaceIcon(v11, -1, hicon) == -1 )
    {
      v3 = -2147467259;
      SdpDebugPrint(
        1u,
        "Dwz ERROR: %s:%d - hr = 0x%08X\n",
        "InteractivityChoice::MakeButtonImageList",
        291,
        -2147467259);
    }
    else
    {
      lParam[0] = *((_QWORD *)this + 4);
      *(__m128i *)&lParam[1] = _mm_load_si128((const __m128i *)&_xmm);
      LODWORD(lParam[3]) = 0;
    }
    goto LABEL_12;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityChoice::MakeButtonImageList", 287, v3);
  if ( (v3 & 0x80000000) != 0 )
    goto LABEL_12;
  return v3;
}

```

## disassembly

```asm
0x14002d660  mov     [rsp+arg_10], rbx
0x14002d665  mov     [rsp+arg_18], rbp
0x14002d66a  push    rdi
0x14002d66b  push    r14
0x14002d66d  push    r15
0x14002d66f  sub     rsp, 60h
0x14002d673  mov     rax, cs:__security_cookie
0x14002d67a  xor     rax, rsp
0x14002d67d  mov     [rsp+78h+var_20], rax
0x14002d682  mov     r14, rdx
0x14002d685  xorps   xmm0, xmm0
0x14002d688  xor     edi, edi
0x14002d68a  mov     r15, rcx
0x14002d68d  mov     rcx, r14; hWnd
0x14002d690  mov     [rsp+78h+hicon], rdi
0x14002d695  movups  xmmword ptr [rsp+78h+lParam], xmm0
0x14002d69a  lea     edx, [rdi-14h]; nIndex
0x14002d69d  movups  [rsp+78h+var_30], xmm0
0x14002d6a2  call    cs:__imp_GetWindowLongW
0x14002d6a9  nop     dword ptr [rax+rax+00h]
0x14002d6ae  mov     rcx, [r15+18h]; unsigned __int16 *
0x14002d6b2  mov     ebp, eax
0x14002d6b4  and     ebp, 400000h
0x14002d6ba  or      ebp, 4200h
0x14002d6c0  shr     ebp, 9
0x14002d6c3  test    rcx, rcx
0x14002d6c6  jz      loc_14002D7E2
0x14002d6cc  lea     rdx, [rsp+78h+hicon]; HICON *
0x14002d6d1  call    ?DwzLoadSmallIcon@@YAJPEBGPEAPEAUHICON__@@@Z; DwzLoadSmallIcon(ushort const *,HICON__ * *)
0x14002d6d6  mov     edi, eax
0x14002d6d8  test    eax, eax
0x14002d6da  jns     short loc_14002D6E8
0x14002d6dc  mov     [rsp+78h+cGrow], eax
0x14002d6e0  mov     r9d, 117h
0x14002d6e6  jmp     short loc_14002D766
0x14002d6e8  mov     ecx, 32h ; '2'; nIndex
0x14002d6ed  call    cs:__imp_GetSystemMetrics
0x14002d6f4  nop     dword ptr [rax+rax+00h]
0x14002d6f9  mov     ecx, 31h ; '1'; nIndex
0x14002d6fe  mov     ebx, eax
0x14002d700  call    cs:__imp_GetSystemMetrics
0x14002d707  nop     dword ptr [rax+rax+00h]
0x14002d70c  mov     r9d, 1; cInitial
0x14002d712  mov     [rsp+78h+cGrow], 1; cGrow
0x14002d71a  mov     ecx, eax; cx
0x14002d71c  mov     r8d, ebp; flags
0x14002d71f  mov     edx, ebx; cy
0x14002d721  call    cs:__imp_ImageList_Create
0x14002d728  nop     dword ptr [rax+rax+00h]
0x14002d72d  mov     [r15+20h], rax
0x14002d731  lea     rcx, [rax-1]
0x14002d735  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14002d739  ja      short loc_14002D7A1
0x14002d73b  mov     r8, [rsp+78h+hicon]; hicon
0x14002d740  or      edx, 0FFFFFFFFh; i
0x14002d743  mov     rcx, rax; himl
0x14002d746  call    cs:__imp_ImageList_ReplaceIcon
0x14002d74d  nop     dword ptr [rax+rax+00h]
0x14002d752  cmp     eax, 0FFFFFFFFh
0x14002d755  jnz     short loc_14002D780
0x14002d757  mov     edi, 80004005h
0x14002d75c  mov     r9d, 123h
0x14002d762  mov     [rsp+78h+cGrow], edi
0x14002d766  lea     r8, aInteractivityc; "InteractivityChoice::MakeButtonImageLis"...
0x14002d76d  mov     ecx, 1; Level
0x14002d772  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002d779  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002d77e  jmp     short loc_14002D7E2
0x14002d780  mov     rax, [r15+20h]
0x14002d784  movdqa  xmm0, cs:__xmm@00000003000000030000000300000003
0x14002d78c  mov     [rsp+78h+lParam], rax
0x14002d791  movdqu  xmmword ptr [rsp+78h+lParam+8], xmm0
0x14002d797  mov     dword ptr [rsp+78h+var_30+8], 0
0x14002d79f  jmp     short loc_14002D7E2
0x14002d7a1  call    cs:__imp_GetLastError
0x14002d7a8  nop     dword ptr [rax+rax+00h]
0x14002d7ad  mov     edi, eax
0x14002d7af  test    eax, eax
0x14002d7b1  jle     short loc_14002D7BC
0x14002d7b3  movzx   edi, ax
0x14002d7b6  or      edi, 80070000h
0x14002d7bc  mov     r9d, 11Fh
0x14002d7c2  mov     [rsp+78h+cGrow], edi
0x14002d7c6  lea     r8, aInteractivityc; "InteractivityChoice::MakeButtonImageLis"...
0x14002d7cd  mov     ecx, 1; Level
0x14002d7d2  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002d7d9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002d7de  test    edi, edi
0x14002d7e0  jns     short loc_14002D7FE
0x14002d7e2  lea     r9, [rsp+78h+lParam]; lParam
0x14002d7e7  xor     r8d, r8d; wParam
0x14002d7ea  mov     edx, 1602h; Msg
0x14002d7ef  mov     rcx, r14; hWnd
0x14002d7f2  call    cs:__imp_SendMessageW
0x14002d7f9  nop     dword ptr [rax+rax+00h]
0x14002d7fe  mov     eax, edi
0x14002d800  mov     rcx, [rsp+78h+var_20]
0x14002d805  xor     rcx, rsp; StackCookie
0x14002d808  call    __security_check_cookie
0x14002d80d  lea     r11, [rsp+78h+var_18]
0x14002d812  mov     rbx, [r11+30h]
0x14002d816  mov     rbp, [r11+38h]
0x14002d81a  mov     rsp, r11
0x14002d81d  pop     r15
0x14002d81f  pop     r14
0x14002d821  pop     rdi
0x14002d822  retn
```
