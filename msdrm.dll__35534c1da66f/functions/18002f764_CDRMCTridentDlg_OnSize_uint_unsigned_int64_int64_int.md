# CDRMCTridentDlg::OnSize(uint,unsigned __int64,__int64,int &)

- ea: `0x18002f764`
- end: `0x18002f90a`
- name: `?OnSize@CDRMCTridentDlg@@QEAA_JI_K_JAEAH@Z`
- size: `422`
- prototype: `__int64 __fastcall(CDRMCTridentDlg *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002f910`

## callees

- `0x18002f764`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f801`
- `USER32!ShowWindow` at `0x18002f82e`
- `USER32!ShowWindow` at `0x18002f82e`
- `USER32!GetClientRect` at `0x18002f798`
- `USER32!GetClientRect` at `0x18002f798`
- `USER32!MoveWindow` at `0x18002f7f7`
- `USER32!MoveWindow` at `0x18002f7f7`

## pseudocode

```c
_BOOL8 __fastcall CDRMCTridentDlg::OnSize(CDRMCTridentDlg *this)
{
  HWND v2; // rcx
  signed int v3; // edi
  __int64 v4; // rbx
  signed int LastError; // eax
  struct tagRECT v7; // [rsp+40h] [rbp-38h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-28h] BYREF

  v2 = (HWND)*((_QWORD *)this + 1);
  Rect = 0;
  v3 = 0;
  GetClientRect(v2, &Rect);
  v4 = *((_QWORD *)this + 8);
  if ( v4 )
  {
    v7 = Rect;
    if ( *(_QWORD *)(v4 + 72) )
    {
      if ( MoveWindow(*(HWND *)(v4 + 56), 0, 0, Rect.right - Rect.left, Rect.bottom - Rect.top, 1)
        && ShowWindow(*(HWND *)(v4 + 56), 5) )
      {
        v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _DWORD, _QWORD, struct tagRECT *))(**(_QWORD **)(v4 + 72) + 88LL))(
               *(_QWORD *)(v4 + 72),
               4294967293LL,
               0,
               v4 + 8,
               0,
               *(_QWORD *)(v4 + 56),
               &v7);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _DWORD, _QWORD, struct tagRECT *))(**(_QWORD **)(v4 + 72) + 88LL))(
                 *(_QWORD *)(v4 + 72),
                 4294967291LL,
                 0,
                 v4 + 8,
                 0,
                 *(_QWORD *)(v4 + 56),
                 &v7);
          if ( v3 >= 0 )
            v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _DWORD, _QWORD, struct tagRECT *))(**(_QWORD **)(v4 + 72) + 88LL))(
                   *(_QWORD *)(v4 + 72),
                   0xFFFFFFFFLL,
                   0,
                   v4 + 8,
                   0,
                   *(_QWORD *)(v4 + 56),
                   &v7);
        }
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 >= 0 )
          v3 = -2147467259;
      }
    }
    else
    {
      v3 = -2147467261;
    }
  }
  return v3 == 0;
}

```

## disassembly

```asm
0x18002f764  mov     [rsp+arg_8], rbx
0x18002f769  mov     [rsp+arg_10], rsi
0x18002f76e  push    rdi
0x18002f76f  sub     rsp, 70h
0x18002f773  mov     rax, cs:__security_cookie
0x18002f77a  xor     rax, rsp
0x18002f77d  mov     [rsp+78h+var_18], rax
0x18002f782  mov     rbx, rcx
0x18002f785  lea     rdx, [rsp+78h+Rect]; lpRect
0x18002f78a  mov     rcx, [rcx+8]; hWnd
0x18002f78e  xorps   xmm0, xmm0
0x18002f791  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x18002f796  xor     edi, edi
0x18002f798  call    cs:__imp_GetClientRect
0x18002f79e  mov     rbx, [rbx+40h]
0x18002f7a2  test    rbx, rbx
0x18002f7a5  jz      loc_18002F8E4
0x18002f7ab  movaps  xmm0, xmmword ptr [rsp+78h+Rect.left]
0x18002f7b0  movdqa  [rsp+78h+var_38], xmm0
0x18002f7b6  cmp     [rbx+48h], rdi
0x18002f7ba  jnz     short loc_18002F7C6
0x18002f7bc  mov     edi, 80004003h
0x18002f7c1  jmp     loc_18002F8E4
0x18002f7c6  mov     r9, qword ptr [rsp+78h+Rect.right]
0x18002f7cb  xor     r8d, r8d; Y
0x18002f7ce  mov     rax, qword ptr [rsp+78h+Rect.left]
0x18002f7d3  mov     rcx, r9
0x18002f7d6  sub     r9d, [rsp+78h+Rect.left]; nWidth
0x18002f7db  xor     edx, edx; X
0x18002f7dd  shr     rcx, 20h
0x18002f7e1  shr     rax, 20h
0x18002f7e5  sub     ecx, eax
0x18002f7e7  mov     [rsp+78h+bRepaint], 1; bRepaint
0x18002f7ef  mov     [rsp+78h+nHeight], ecx; nHeight
0x18002f7f3  mov     rcx, [rbx+38h]; hWnd
0x18002f7f7  call    cs:__imp_MoveWindow
0x18002f7fd  test    eax, eax
0x18002f7ff  jnz     short loc_18002F825
0x18002f801  call    cs:__imp_GetLastError
0x18002f807  mov     edi, eax
0x18002f809  test    eax, eax
0x18002f80b  jle     short loc_18002F816
0x18002f80d  movzx   edi, ax
0x18002f810  or      edi, 80070000h
0x18002f816  test    edi, edi
0x18002f818  mov     eax, 80004005h
0x18002f81d  cmovns  edi, eax
0x18002f820  jmp     loc_18002F8E4
0x18002f825  mov     rcx, [rbx+38h]; hWnd
0x18002f829  mov     edx, 5; nCmdShow
0x18002f82e  call    cs:__imp_ShowWindow
0x18002f834  test    eax, eax
0x18002f836  jz      short loc_18002F801
0x18002f838  mov     rcx, [rbx+48h]
0x18002f83c  lea     rdx, [rsp+78h+var_38]
0x18002f841  mov     [rsp+78h+var_48], rdx
0x18002f846  lea     rsi, [rbx+8]
0x18002f84a  mov     rdx, [rbx+38h]
0x18002f84e  xor     r8d, r8d
0x18002f851  mov     qword ptr [rsp+78h+bRepaint], rdx
0x18002f856  mov     r9, rsi
0x18002f859  mov     rax, [rcx]
0x18002f85c  mov     [rsp+78h+nHeight], edi
0x18002f860  lea     edx, [r8-3]
0x18002f864  mov     rax, [rax+58h]
0x18002f868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f86d  mov     edi, eax
0x18002f86f  test    eax, eax
0x18002f871  js      short loc_18002F8E4
0x18002f873  mov     rcx, [rbx+48h]
0x18002f877  lea     rdx, [rsp+78h+var_38]
0x18002f87c  mov     [rsp+78h+var_48], rdx
0x18002f881  xor     r8d, r8d
0x18002f884  mov     rdx, [rbx+38h]
0x18002f888  mov     r9, rsi
0x18002f88b  mov     qword ptr [rsp+78h+bRepaint], rdx
0x18002f890  mov     rax, [rcx]
0x18002f893  lea     edx, [r8-5]
0x18002f897  mov     [rsp+78h+nHeight], 0
0x18002f89f  mov     rax, [rax+58h]
0x18002f8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8a8  mov     edi, eax
0x18002f8aa  test    eax, eax
0x18002f8ac  js      short loc_18002F8E4
0x18002f8ae  mov     rcx, [rbx+48h]
0x18002f8b2  lea     rdx, [rsp+78h+var_38]
0x18002f8b7  mov     [rsp+78h+var_48], rdx
0x18002f8bc  mov     r9, rsi
0x18002f8bf  mov     rdx, [rbx+38h]
0x18002f8c3  xor     r8d, r8d
0x18002f8c6  mov     qword ptr [rsp+78h+bRepaint], rdx
0x18002f8cb  or      edx, 0FFFFFFFFh
0x18002f8ce  mov     rax, [rcx]
0x18002f8d1  mov     [rsp+78h+nHeight], 0
0x18002f8d9  mov     rax, [rax+58h]
0x18002f8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8e2  mov     edi, eax
0x18002f8e4  xor     eax, eax
0x18002f8e6  test    edi, edi
0x18002f8e8  setz    al
0x18002f8eb  mov     rcx, [rsp+78h+var_18]
0x18002f8f0  xor     rcx, rsp; StackCookie
0x18002f8f3  call    __security_check_cookie
0x18002f8f8  lea     r11, [rsp+78h+var_8]
0x18002f8fd  mov     rbx, [r11+18h]
0x18002f901  mov     rsi, [r11+20h]
0x18002f905  mov     rsp, r11
0x18002f908  pop     rdi
0x18002f909  retn
```
