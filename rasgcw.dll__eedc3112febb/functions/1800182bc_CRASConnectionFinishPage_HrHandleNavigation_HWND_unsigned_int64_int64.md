# CRASConnectionFinishPage::HrHandleNavigation(HWND__ *,unsigned __int64,__int64)

- ea: `0x1800182bc`
- end: `0x18001850f`
- name: `?HrHandleNavigation@CRASConnectionFinishPage@@IEAAJPEAUHWND__@@_K_J@Z`
- size: `595`
- prototype: `int(CRASConnectionFinishPage *__hidden this, HWND, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800186a0`

## callees

- `0x180011540`
- `0x1800182bc`
- `0x180030010`

## import_xrefs

- `USER32!PostMessageW` at `0x1800184ae`
- `USER32!PostMessageW` at `0x1800184ae`
- `USER32!SendMessageW` at `0x1800184fa`
- `USER32!SendMessageW` at `0x1800184fa`
- `USER32!GetParent` at `0x1800182e0`
- `USER32!GetParent` at `0x1800182e0`
- `rtutils!TracePrintfExA` at `0x18001835a`
- `rtutils!TracePrintfExA` at `0x1800183a4`
- `rtutils!TracePrintfExA` at `0x1800184d2`
- `rtutils!TracePrintfExA` at `0x18001835a`
- `rtutils!TracePrintfExA` at `0x1800183a4`
- `rtutils!TracePrintfExA` at `0x1800184d2`

## string_xrefs

- `0x18001834e`: `Failed to ensure the 'skip connection launch' flag is removed. hr = %#x`
- `0x180018398`: `Failed to ensure the 'skip connection Testing' flag is removed. hr = %#x`

## pseudocode

```c
__int64 __fastcall CRASConnectionFinishPage::HrHandleNavigation(CRASConnectionFinishPage *this, HWND a2, __int64 a3)
{
  int v4; // esi
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  HWND v14; // rcx
  __int64 *v15; // r9
  int v16; // eax
  int v17; // eax
  __int64 *v19; // [rsp+50h] [rbp+8h] BYREF
  __int64 v20; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  v20 = 0;
  *((_QWORD *)this + 2) = GetParent(a2);
  v7 = a3 - 2092;
  if ( !v7 )
    goto LABEL_5;
  v8 = v7 - 1;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( !v9 )
    {
      (*(void (__fastcall **)(_QWORD, char *, const wchar_t *, __int64, int))(**((_QWORD **)this + 20) + 40LL))(
        *((_QWORD *)this + 20),
        (char *)this + 120,
        L"ConnectionTested",
        1,
        2);
      v16 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, __int64, int))(**((_QWORD **)this + 20) + 40LL))(
              *((_QWORD *)this + 20),
              (char *)this + 120,
              L"SkipConnectionTesting",
              1,
              2);
      v14 = (HWND)*((_QWORD *)this + 2);
      v4 = v16;
      v15 = 0;
LABEL_21:
      SendMessageW(v14, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)v15);
      return (unsigned int)v4;
    }
    if ( v9 == 1 )
    {
LABEL_5:
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, _QWORD, _QWORD))(**((_QWORD **)this + 20) + 56LL))(
              *((_QWORD *)this + 20),
              (char *)this + 120,
              L"SkipConnectionLaunch",
              0,
              0);
      if ( v10 < 0 && g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "Failed to ensure the 'skip connection launch' flag is removed. hr = %#x",
          v10);
      v11 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, _QWORD, _QWORD))(**((_QWORD **)this + 20) + 56LL))(
              *((_QWORD *)this + 20),
              (char *)this + 120,
              L"SkipConnectionTesting",
              0,
              0);
      v4 = v11;
      if ( v11 < 0 && g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "Failed to ensure the 'skip connection Testing' flag is removed. hr = %#x",
          v11);
      v12 = *((_QWORD *)this + 20);
      v19 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, char *, const wchar_t *, __int64 **, _QWORD))(*(_QWORD *)v12 + 48LL))(
              v12,
              (char *)this + 120,
              L"ConnectionTesting",
              &v19,
              0);
      v14 = (HWND)*((_QWORD *)this + 2);
      if ( v13 )
      {
        v15 = qword_180038468;
        if ( !*((_DWORD *)this + 34) )
          v15 = (__int64 *)&qword_1800384C8;
      }
      else
      {
        v15 = v19;
      }
      goto LABEL_21;
    }
  }
  else
  {
    v17 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, __int64 *, _QWORD))(**((_QWORD **)this + 20) + 48LL))(
            *((_QWORD *)this + 20),
            (char *)this + 120,
            L"ConnectionGUID",
            &v20,
            0);
    v4 = v17;
    if ( v17 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to find the connection GUID. hr = %#x", v17);
    }
    else
    {
      v4 = HrInvokeDiagnostics(a2, v20, *((unsigned int *)this + 28));
      if ( v4 >= 0 )
        PostMessageW(*((HWND *)this + 2), 0x471u, 2u, 0);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800182bc  mov     [rsp+arg_8], rbx
0x1800182c1  mov     [rsp+arg_18], r9
0x1800182c6  push    rbp
0x1800182c7  push    rsi
0x1800182c8  push    rdi
0x1800182c9  sub     rsp, 30h
0x1800182cd  mov     rdi, rcx
0x1800182d0  xor     esi, esi
0x1800182d2  mov     rcx, rdx; hWnd
0x1800182d5  mov     [rsp+48h+arg_18], rsi
0x1800182da  mov     rbx, r8
0x1800182dd  mov     rbp, rdx
0x1800182e0  call    cs:__imp_GetParent
0x1800182e6  mov     [rdi+10h], rax
0x1800182ea  sub     rbx, 82Ch
0x1800182f1  jz      short loc_180018311
0x1800182f3  sub     rbx, 1
0x1800182f7  jz      loc_180018459
0x1800182fd  sub     rbx, 1
0x180018301  jz      loc_1800183F4
0x180018307  cmp     rbx, 1
0x18001830b  jnz     loc_180018500
0x180018311  mov     rcx, [rdi+0A0h]
0x180018318  lea     rbp, [rdi+78h]
0x18001831c  xor     r9d, r9d
0x18001831f  mov     [rsp+48h+var_28], rsi
0x180018324  lea     r8, aSkipconnection_2; "SkipConnectionLaunch"
0x18001832b  mov     rdx, rbp
0x18001832e  mov     rax, [rcx]
0x180018331  mov     rax, [rax+38h]
0x180018335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001833a  or      ebx, 0FFFFFFFFh
0x18001833d  test    eax, eax
0x18001833f  jns     short loc_180018360
0x180018341  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180018347  cmp     ecx, ebx
0x180018349  jz      short loc_180018360
0x18001834b  mov     r9d, eax
0x18001834e  lea     r8, aFailedToEnsure_0; "Failed to ensure the 'skip connection l"...
0x180018355  mov     edx, 0Ch; dwFlags
0x18001835a  call    cs:__imp_TracePrintfExA
0x180018360  mov     rcx, [rdi+0A0h]
0x180018367  lea     r8, aSkipconnection_3; "SkipConnectionTesting"
0x18001836e  xor     r9d, r9d
0x180018371  mov     [rsp+48h+var_28], rsi
0x180018376  mov     rdx, rbp
0x180018379  mov     rax, [rcx]
0x18001837c  mov     rax, [rax+38h]
0x180018380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018385  mov     esi, eax
0x180018387  test    eax, eax
0x180018389  jns     short loc_1800183AA
0x18001838b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180018391  cmp     ecx, ebx
0x180018393  jz      short loc_1800183AA
0x180018395  mov     r9d, eax
0x180018398  lea     r8, aFailedToEnsure; "Failed to ensure the 'skip connection T"...
0x18001839f  mov     edx, 0Ch; dwFlags
0x1800183a4  call    cs:__imp_TracePrintfExA
0x1800183aa  mov     rcx, [rdi+0A0h]
0x1800183b1  lea     r9, [rsp+48h+arg_0]
0x1800183b6  mov     [rsp+48h+arg_0], 0
0x1800183bf  lea     r8, aConnectiontest; "ConnectionTesting"
0x1800183c6  mov     rdx, rbp
0x1800183c9  mov     [rsp+48h+var_28], 0
0x1800183d2  mov     rax, [rcx]
0x1800183d5  mov     rax, [rax+30h]
0x1800183d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183de  mov     rcx, [rdi+10h]; hWnd
0x1800183e2  test    eax, eax
0x1800183e4  jnz     loc_1800184DA
0x1800183ea  mov     r9, [rsp+48h+arg_0]
0x1800183ef  jmp     loc_1800184F1
0x1800183f4  mov     rcx, [rdi+0A0h]
0x1800183fb  lea     r8, aConnectiontest_0; "ConnectionTested"
0x180018402  mov     esi, 1
0x180018407  mov     dword ptr [rsp+48h+var_28], 2
0x18001840f  mov     r9d, esi
0x180018412  lea     rdx, [rdi+78h]
0x180018416  mov     rax, [rcx]
0x180018419  mov     rax, [rax+28h]
0x18001841d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018422  mov     rcx, [rdi+0A0h]
0x180018429  lea     r8, aSkipconnection_3; "SkipConnectionTesting"
0x180018430  mov     r9d, esi
0x180018433  mov     dword ptr [rsp+48h+var_28], 2
0x18001843b  lea     rdx, [rdi+78h]
0x18001843f  mov     rax, [rcx]
0x180018442  mov     rax, [rax+28h]
0x180018446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001844b  mov     rcx, [rdi+10h]
0x18001844f  mov     esi, eax
0x180018451  xor     r9d, r9d
0x180018454  jmp     loc_1800184F1
0x180018459  mov     rcx, [rdi+0A0h]
0x180018460  lea     rdx, [rdi+78h]
0x180018464  lea     r9, [rsp+48h+arg_18]
0x180018469  mov     [rsp+48h+var_28], rsi
0x18001846e  lea     r8, aConnectionguid; "ConnectionGUID"
0x180018475  mov     rax, [rcx]
0x180018478  mov     rax, [rax+30h]
0x18001847c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018481  mov     esi, eax
0x180018483  test    eax, eax
0x180018485  jnz     short loc_1800184B6
0x180018487  mov     r8d, [rdi+70h]
0x18001848b  mov     rcx, rbp
0x18001848e  mov     rdx, [rsp+48h+arg_18]
0x180018493  call    HrInvokeDiagnostics
0x180018498  mov     esi, eax
0x18001849a  test    eax, eax
0x18001849c  js      short loc_180018500
0x18001849e  mov     rcx, [rdi+10h]; hWnd
0x1800184a2  xor     r9d, r9d; lParam
0x1800184a5  mov     edx, 471h; Msg
0x1800184aa  lea     r8d, [r9+2]; wParam
0x1800184ae  call    cs:__imp_PostMessageW
0x1800184b4  jmp     short loc_180018500
0x1800184b6  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800184bc  or      ebx, 0FFFFFFFFh
0x1800184bf  cmp     ecx, ebx
0x1800184c1  jz      short loc_180018500
0x1800184c3  mov     r9d, eax
0x1800184c6  lea     r8, aFailedToFindTh; "Failed to find the connection GUID. hr "...
0x1800184cd  mov     edx, 0Ch; dwFlags
0x1800184d2  call    cs:__imp_TracePrintfExA
0x1800184d8  jmp     short loc_180018500
0x1800184da  cmp     dword ptr [rdi+88h], 0
0x1800184e1  lea     r9, qword_180038468
0x1800184e8  jnz     short loc_1800184F1
0x1800184ea  lea     r9, qword_1800384C8; lParam
0x1800184f1  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800184f5  mov     edx, 465h; Msg
0x1800184fa  call    cs:__imp_SendMessageW
0x180018500  mov     rbx, [rsp+48h+arg_8]
0x180018505  mov     eax, esi
0x180018507  add     rsp, 30h
0x18001850b  pop     rdi
0x18001850c  pop     rsi
0x18001850d  pop     rbp
0x18001850e  retn
```
