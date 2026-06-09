# CRASConnectionFinishPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800186a0`
- end: `0x180018bf0`
- name: `?PageDlgProc@CRASConnectionFinishPage@@KAHPEAUHWND__@@I_K_J@Z`
- size: `1360`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800182bc`
- `0x180018518`
- `0x1800186a0`
- `0x18002b5e4`
- `0x18002b970`
- `0x18002f382`
- `0x18002f3b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a20`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800189ab`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018a16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800189ab`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018a16`
- `connect!IsInternetConnected` at `0x1800187cc`
- `connect!IsInternetConnected` at `0x1800187cc`
- `RASAPI32!RasGetErrorStringW` at `0x1800189eb`
- `RASAPI32!RasGetErrorStringW` at `0x1800189eb`
- `USER32!SetWindowLongPtrW` at `0x180018bb2`
- `USER32!SetWindowLongPtrW` at `0x180018be5`
- `USER32!SetWindowLongPtrW` at `0x180018bb2`
- `USER32!SetWindowLongPtrW` at `0x180018be5`
- `USER32!PostMessageW` at `0x180018ad1`
- `USER32!PostMessageW` at `0x180018b0b`
- `USER32!PostMessageW` at `0x180018bc8`
- `USER32!PostMessageW` at `0x180018ad1`
- `USER32!PostMessageW` at `0x180018b0b`
- `USER32!PostMessageW` at `0x180018bc8`
- `USER32!GetPropW` at `0x180018740`
- `USER32!GetPropW` at `0x180018740`
- `USER32!RemovePropW` at `0x18001870d`
- `USER32!RemovePropW` at `0x18001870d`
- `USER32!SetWindowTextW` at `0x180018a32`
- `USER32!SetWindowTextW` at `0x180018a32`
- `USER32!ShowWindow` at `0x180018a4e`
- `USER32!ShowWindow` at `0x180018a7e`
- `USER32!ShowWindow` at `0x180018a8b`
- `USER32!ShowWindow` at `0x180018aa5`
- `USER32!ShowWindow` at `0x180018ab1`
- `USER32!ShowWindow` at `0x180018b9e`
- `USER32!ShowWindow` at `0x180018a4e`
- `USER32!ShowWindow` at `0x180018a7e`
- `USER32!ShowWindow` at `0x180018a8b`
- `USER32!ShowWindow` at `0x180018aa5`
- `USER32!ShowWindow` at `0x180018ab1`
- `USER32!ShowWindow` at `0x180018b9e`
- `USER32!SetPropW` at `0x1800186f9`
- `USER32!SetPropW` at `0x1800186f9`
- `USER32!EnableWindow` at `0x180018a41`
- `USER32!EnableWindow` at `0x180018a41`
- `USER32!SendMessageW` at `0x180018920`
- `USER32!SendMessageW` at `0x180018935`
- `USER32!SendMessageW` at `0x1800189c0`
- `USER32!SendMessageW` at `0x1800189d6`
- `USER32!SendMessageW` at `0x180018b20`
- `USER32!SendMessageW` at `0x180018b35`
- `USER32!SendMessageW` at `0x180018b67`
- `USER32!SendMessageW` at `0x180018b7c`
- `USER32!SendMessageW` at `0x180018920`
- `USER32!SendMessageW` at `0x180018935`
- `USER32!SendMessageW` at `0x1800189c0`
- `USER32!SendMessageW` at `0x1800189d6`
- `USER32!SendMessageW` at `0x180018b20`
- `USER32!SendMessageW` at `0x180018b35`
- `USER32!SendMessageW` at `0x180018b67`
- `USER32!SendMessageW` at `0x180018b7c`
- `USER32!GetParent` at `0x1800187d8`
- `USER32!GetParent` at `0x1800187d8`

## pseudocode

```c
_BOOL8 __fastcall CRASConnectionFinishPage::PageDlgProc(
        HWND a1,
        int a2,
        unsigned __int64 a3,
        CRASConnectionFinishPage **a4)
{
  CRASConnectionFinishPage *v4; // rsi
  CRASConnectionFinishPage *PropW; // rax
  __int64 v10; // r9
  CRASConnectionFinishPage *v11; // rdi
  int v12; // ebx
  int v13; // ebx
  int v14; // r13d
  HWND Parent; // rax
  __int64 v16; // rcx
  int v17; // eax
  LPARAM v18; // rbx
  int v19; // eax
  const void *v20; // rax
  int v21; // eax
  DWORD ErrorStringW; // eax
  LPARAM StringPcch; // rbx
  LPARAM v24; // rbx
  int v25; // eax
  HWND v26; // rcx
  LONG_PTR v27; // r8
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v32; // [rsp+68h] [rbp-98h] BYREF
  va_list Arguments; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[56]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szString[512]; // [rsp+F0h] [rbp-10h] BYREF

  v4 = (CRASConnectionFinishPage *)a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = a4[6];
    SetPropW(a1, L"_Win32_this_", v4);
    goto LABEL_14;
  }
  if ( a2 == 2 )
  {
    RemovePropW(a1, L"_Win32_this_");
    return 0;
  }
  PropW = (CRASConnectionFinishPage *)GetPropW(a1, L"_Win32_this_");
  v11 = PropW;
  v12 = a2 - 78;
  if ( !v12 )
  {
    switch ( *((_DWORD *)v4 + 4) )
    {
      case 0xFFFFFF2B:
        v27 = *((_QWORD *)PropW + 13);
        if ( v27 )
        {
          SetWindowLongPtrW(a1, 0, v27);
          return 1;
        }
        break;
      case 0xFFFFFF31:
        SetWindowLongPtrW(a1, 0, -1);
        PostMessageW(*((HWND *)v11 + 2), 0x471u, 2u, 0);
        return 0;
      case 0xFFFFFF38:
        if ( a3 != 4294967089 )
          return 1;
        v30 = 0;
        v31 = 0;
        v28 = 0;
        v29 = 0;
        v32 = 0;
        v14 = IsInternetConnected();
        Parent = GetParent(a1);
        v16 = *((_QWORD *)v11 + 20);
        *((_QWORD *)v11 + 2) = Parent;
        (*(void (__fastcall **)(__int64, __int64, const wchar_t *, __int64 *, _QWORD))(*(_QWORD *)v16 + 48LL))(
          v16,
          (__int64)v11 + 120,
          L"SkipConnectionLaunch",
          &v30,
          0);
        (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *, __int64 *, _QWORD))(**((_QWORD **)v11 + 20) + 48LL))(
          *((_QWORD *)v11 + 20),
          (__int64)v11 + 120,
          L"SkipConnectionTesting",
          &v31,
          0);
        (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *, unsigned __int64 *, _QWORD))(**((_QWORD **)v11 + 20)
                                                                                             + 48LL))(
          *((_QWORD *)v11 + 20),
          (__int64)v11 + 120,
          L"ConnectionResult",
          &v29,
          0);
        (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *, __int64 *, _QWORD))(**((_QWORD **)v11 + 20) + 48LL))(
          *((_QWORD *)v11 + 20),
          (__int64)v11 + 120,
          L"InternetTestFailed",
          &v28,
          0);
        v17 = v29;
        if ( v29 > 0xFFFFFFFF )
          v17 = -1;
        *((_DWORD *)v11 + 28) = v17;
        (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *, _QWORD **, _QWORD))(**((_QWORD **)v11 + 20) + 48LL))(
          *((_QWORD *)v11 + 20),
          (__int64)v11 + 120,
          L"RASConnectionDetails",
          &v32,
          0);
        *((_QWORD *)v11 + 13) = 0;
        if ( v30 || v31 || !*((_DWORD *)v11 + 28) && !v28 )
        {
          StringPcch = PszLoadStringPcch(hInst);
          PostMessageW(*((HWND *)v11 + 2), 0x48Au, 0, 16);
          SendMessageW(*((HWND *)v11 + 2), 0x489u, 0, StringPcch);
          SendMessageW(*((HWND *)v11 + 2), 0x479u, 0, StringPcch);
          v24 = PszLoadStringPcch(qword_18004D9B0);
          v25 = SendMessageW(*((HWND *)v11 + 2), 0x481u, (WPARAM)a1, 0);
          SendMessageW(*((HWND *)v11 + 2), 0x47Eu, v25, v24);
          if ( *((_DWORD *)v11 + 34) || !v14 )
            v26 = (HWND)*((_QWORD *)v11 + 7);
          else
            v26 = (HWND)*((_QWORD *)v11 + 8);
          ShowWindow(v26, 5);
          return 1;
        }
        if ( v28 )
        {
          v18 = PszLoadStringPcch(qword_18004D9B0);
          v19 = SendMessageW(*((HWND *)v11 + 2), 0x481u, (WPARAM)a1, 0);
          SendMessageW(*((HWND *)v11 + 2), 0x47Eu, v19, v18);
          goto LABEL_33;
        }
        memset_0(Buffer, 0, 0x64u);
        memset_0(szString, 0, sizeof(szString));
        Arguments = (va_list)*((unsigned int *)v11 + 28);
        v20 = (const void *)PszLoadStringPcch(qword_18004D9B0);
        FormatMessageW(0x2400u, v20, 0, 0, Buffer, 0x32u, &Arguments);
        v21 = SendMessageW(*((HWND *)v11 + 2), 0x481u, (WPARAM)a1, 0);
        SendMessageW(*((HWND *)v11 + 2), 0x47Eu, v21, (LPARAM)Buffer);
        ErrorStringW = RasGetErrorStringW(*((_DWORD *)v11 + 28), szString, 0x200u);
        if ( ErrorStringW == 87 )
        {
          if ( FormatMessageW(0x1000u, 0, *((_DWORD *)v11 + 28), 0, szString, 0x200u, 0) )
          {
LABEL_32:
            SetWindowTextW(*((HWND *)v11 + 3), szString);
            EnableWindow(*((HWND *)v11 + 3), 1);
            ShowWindow(*((HWND *)v11 + 3), 5);
LABEL_33:
            if ( v32 && *v32 && *(_DWORD *)*v32 == 2 && (unsigned int)IsDiagnosableError(*((unsigned int *)v11 + 28)) )
              ShowWindow(*((HWND *)v11 + 5), 5);
            ShowWindow(*((HWND *)v11 + 6), 5);
            if ( *((_DWORD *)v11 + 34) || !v14 )
            {
              ShowWindow(*((HWND *)v11 + 4), 5);
              *((_QWORD *)v11 + 13) = *((_QWORD *)v11 + 4);
            }
            else
            {
              ShowWindow(*((HWND *)v11 + 8), 5);
            }
            PostMessageW(*((HWND *)v11 + 2), 0x48Au, 0, 2);
            return 1;
          }
          ErrorStringW = GetLastError();
        }
        if ( ErrorStringW )
          goto LABEL_33;
        goto LABEL_32;
    }
    return 0;
  }
  v13 = v12 - 194;
  if ( v13 )
    return v13 == 1 && !CRASConnectionFinishPage::HrHandleNavigation(PropW, a1, a3, v10);
  v4 = PropW;
LABEL_14:
  CRASConnectionFinishPage::InitDialogControls(v4, a1);
  return 1;
}

```

## disassembly

```asm
0x1800186a0  mov     [rsp-8+arg_8], rbx
0x1800186a5  mov     [rsp-8+arg_10], rsi
0x1800186aa  push    rbp
0x1800186ab  push    rdi
0x1800186ac  push    r13
0x1800186ae  push    r14
0x1800186b0  push    r15
0x1800186b2  lea     rbp, [rsp-400h]
0x1800186ba  sub     rsp, 500h
0x1800186c1  mov     rax, cs:__security_cookie
0x1800186c8  xor     rax, rsp
0x1800186cb  mov     [rbp+420h+var_30], rax
0x1800186d2  mov     rsi, r9
0x1800186d5  mov     r14, r8
0x1800186d8  mov     ebx, edx
0x1800186da  mov     r15, rcx
0x1800186dd  cmp     edx, 110h
0x1800186e3  jnz     short loc_180018701
0x1800186e5  cmp     dword ptr [r9], 68h ; 'h'
0x1800186e9  jnz     short loc_1800186EF
0x1800186eb  mov     rsi, [r9+30h]
0x1800186ef  mov     r8, rsi; hData
0x1800186f2  lea     rdx, aWin32This_1; "_Win32_this_"
0x1800186f9  call    cs:__imp_SetPropW
0x1800186ff  jmp     short loc_180018772
0x180018701  lea     rdx, aWin32This_1; "_Win32_this_"
0x180018708  cmp     ebx, 2
0x18001870b  jnz     short loc_180018740
0x18001870d  call    cs:__imp_RemovePropW
0x180018713  xor     eax, eax
0x180018715  mov     rcx, [rbp+420h+var_30]
0x18001871c  xor     rcx, rsp; StackCookie
0x18001871f  call    __security_check_cookie
0x180018724  lea     r11, [rsp+520h+var_20]
0x18001872c  mov     rbx, [r11+38h]
0x180018730  mov     rsi, [r11+40h]
0x180018734  mov     rsp, r11
0x180018737  pop     r15
0x180018739  pop     r14
0x18001873b  pop     r13
0x18001873d  pop     rdi
0x18001873e  pop     rbp
0x18001873f  retn
0x180018740  call    cs:__imp_GetPropW
0x180018746  mov     rdi, rax
0x180018749  sub     ebx, 4Eh ; 'N'
0x18001874c  jz      short loc_180018784
0x18001874e  sub     ebx, 0C2h
0x180018754  jz      short loc_18001876F
0x180018756  cmp     ebx, 1
0x180018759  jnz     short loc_180018713
0x18001875b  mov     r8, r14; unsigned __int64
0x18001875e  mov     rdx, r15; HWND
0x180018761  mov     rcx, rax; this
0x180018764  call    ?HrHandleNavigation@CRASConnectionFinishPage@@IEAAJPEAUHWND__@@_K_J@Z; CRASConnectionFinishPage::HrHandleNavigation(HWND__ *,unsigned __int64,__int64)
0x180018769  test    eax, eax
0x18001876b  jz      short loc_18001877D
0x18001876d  jmp     short loc_180018713
0x18001876f  mov     rsi, rdi
0x180018772  mov     rdx, r15; HWND
0x180018775  mov     rcx, rsi; this
0x180018778  call    ?InitDialogControls@CRASConnectionFinishPage@@IEAAXPEAUHWND__@@@Z; CRASConnectionFinishPage::InitDialogControls(HWND__ *)
0x18001877d  mov     eax, 1
0x180018782  jmp     short loc_180018715
0x180018784  cmp     dword ptr [rsi+10h], 0FFFFFF2Bh
0x18001878b  jz      loc_180018BD3
0x180018791  mov     eax, 0FFFFFF31h
0x180018796  cmp     [rsi+10h], eax
0x180018799  jz      loc_180018BA9
0x18001879f  cmp     dword ptr [rsi+10h], 0FFFFFF38h
0x1800187a6  jnz     loc_180018713
0x1800187ac  cmp     r14, rax
0x1800187af  jnz     short loc_18001877D
0x1800187b1  xor     esi, esi
0x1800187b3  mov     [rsp+520h+var_4C8], rsi
0x1800187b8  mov     [rsp+520h+var_4C0], rsi
0x1800187bd  mov     [rsp+520h+var_4D8], rsi
0x1800187c2  mov     [rsp+520h+var_4D0], rsi
0x1800187c7  mov     [rsp+520h+var_4B8], rsi
0x1800187cc  call    cs:__imp_IsInternetConnected
0x1800187d2  mov     rcx, r15; hWnd
0x1800187d5  mov     r13d, eax
0x1800187d8  call    cs:__imp_GetParent
0x1800187de  mov     rcx, [rdi+0A0h]
0x1800187e5  lea     rbx, [rdi+78h]
0x1800187e9  mov     [rdi+10h], rax
0x1800187ed  lea     r9, [rsp+520h+var_4C8]
0x1800187f2  lea     r8, aSkipconnection_2; "SkipConnectionLaunch"
0x1800187f9  mov     [rsp+520h+lpBuffer], rsi
0x1800187fe  mov     rdx, [rcx]
0x180018801  mov     rax, [rdx+30h]
0x180018805  mov     rdx, rbx
0x180018808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001880d  mov     rcx, [rdi+0A0h]
0x180018814  lea     r9, [rsp+520h+var_4C0]
0x180018819  lea     r8, aSkipconnection_3; "SkipConnectionTesting"
0x180018820  mov     [rsp+520h+lpBuffer], rsi
0x180018825  mov     rdx, rbx
0x180018828  mov     rax, [rcx]
0x18001882b  mov     rax, [rax+30h]
0x18001882f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018834  mov     rcx, [rdi+0A0h]
0x18001883b  lea     r9, [rsp+520h+var_4D0]
0x180018840  lea     r8, aConnectionresu; "ConnectionResult"
0x180018847  mov     [rsp+520h+lpBuffer], rsi
0x18001884c  mov     rdx, rbx
0x18001884f  mov     rax, [rcx]
0x180018852  mov     rax, [rax+30h]
0x180018856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001885b  mov     rcx, [rdi+0A0h]
0x180018862  lea     r9, [rsp+520h+var_4D8]
0x180018867  lea     r8, aInternettestfa; "InternetTestFailed"
0x18001886e  mov     [rsp+520h+lpBuffer], rsi
0x180018873  mov     rdx, rbx
0x180018876  mov     rax, [rcx]
0x180018879  mov     rax, [rax+30h]
0x18001887d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018882  mov     rax, [rsp+520h+var_4D0]
0x180018887  mov     ecx, 0FFFFFFFFh
0x18001888c  cmp     rax, rcx
0x18001888f  jbe     short loc_180018893
0x180018891  mov     eax, ecx
0x180018893  mov     [rdi+70h], eax
0x180018896  lea     r9, [rsp+520h+var_4B8]
0x18001889b  mov     rcx, [rdi+0A0h]
0x1800188a2  lea     r8, aRasconnectiond_0; "RASConnectionDetails"
0x1800188a9  mov     rdx, rbx
0x1800188ac  mov     [rsp+520h+lpBuffer], rsi
0x1800188b1  mov     rax, [rcx]
0x1800188b4  mov     rax, [rax+30h]
0x1800188b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188bd  mov     [rdi+68h], rsi
0x1800188c1  cmp     [rsp+520h+var_4C8], rsi
0x1800188c6  jnz     loc_180018ADC
0x1800188cc  cmp     [rsp+520h+var_4C0], rsi
0x1800188d1  jnz     loc_180018ADC
0x1800188d7  cmp     [rdi+70h], esi
0x1800188da  jnz     short loc_1800188E7
0x1800188dc  cmp     [rsp+520h+var_4D8], rsi
0x1800188e1  jz      loc_180018ADC
0x1800188e7  mov     r14d, 5
0x1800188ed  cmp     [rsp+520h+var_4D8], rsi
0x1800188f2  jz      short loc_180018940
0x1800188f4  mov     rcx, cs:qword_18004D9B0; hModule
0x1800188fb  lea     r8, [rsp+520h+var_4E0]
0x180018900  mov     edx, 0C9Ah
0x180018905  mov     [rsp+520h+var_4E0], esi
0x180018909  call    PszLoadStringPcch
0x18001890e  mov     rcx, [rdi+10h]; hWnd
0x180018912  xor     r9d, r9d; lParam
0x180018915  mov     r8, r15; wParam
0x180018918  mov     edx, 481h; Msg
0x18001891d  mov     rbx, rax
0x180018920  call    cs:__imp_SendMessageW
0x180018926  mov     rcx, [rdi+10h]; hWnd
0x18001892a  mov     r9, rbx; lParam
0x18001892d  movsxd  r8, eax; wParam
0x180018930  mov     edx, 47Eh; Msg
0x180018935  call    cs:__imp_SendMessageW
0x18001893b  jmp     loc_180018A54
0x180018940  xor     edx, edx; Val
0x180018942  lea     rcx, [rbp+420h+Buffer]; void *
0x180018946  lea     r8d, [rdx+64h]; Size
0x18001894a  call    memset_0
0x18001894f  xor     edx, edx; Val
0x180018951  lea     rcx, [rbp+420h+szString]; void *
0x180018955  mov     r8d, 400h; Size
0x18001895b  call    memset_0
0x180018960  mov     eax, [rdi+70h]
0x180018963  lea     r8, [rsp+520h+var_4E0]
0x180018968  mov     rcx, cs:qword_18004D9B0; hModule
0x18001896f  mov     edx, 0C9Bh
0x180018974  mov     [rsp+520h+var_4B0], rax
0x180018979  mov     [rsp+520h+var_4E0], esi
0x18001897d  call    PszLoadStringPcch
0x180018982  lea     rcx, [rsp+520h+var_4B0]
0x180018987  xor     r9d, r9d; dwLanguageId
0x18001898a  mov     [rsp+520h+Arguments], rcx; Arguments
0x18001898f  xor     r8d, r8d; dwMessageId
0x180018992  lea     rcx, [rbp+420h+Buffer]
0x180018996  mov     [rsp+520h+nSize], 32h ; '2'; nSize
0x18001899e  mov     [rsp+520h+lpBuffer], rcx; lpBuffer
0x1800189a3  mov     rdx, rax; lpSource
0x1800189a6  mov     ecx, 2400h; dwFlags
0x1800189ab  call    cs:__imp_FormatMessageW
0x1800189b1  mov     rcx, [rdi+10h]; hWnd
0x1800189b5  xor     r9d, r9d; lParam
0x1800189b8  mov     r8, r15; wParam
0x1800189bb  mov     edx, 481h; Msg
0x1800189c0  call    cs:__imp_SendMessageW
0x1800189c6  mov     rcx, [rdi+10h]; hWnd
0x1800189ca  lea     r9, [rbp+420h+Buffer]; lParam
0x1800189ce  movsxd  r8, eax; wParam
0x1800189d1  mov     edx, 47Eh; Msg
0x1800189d6  call    cs:__imp_SendMessageW
0x1800189dc  mov     ecx, [rdi+70h]; ResourceId
0x1800189df  lea     rdx, [rbp+420h+szString]; lpszString
0x1800189e3  mov     ebx, 200h
0x1800189e8  mov     r8d, ebx; InBufSize
0x1800189eb  call    cs:__imp_RasGetErrorStringW
0x1800189f1  cmp     eax, 57h ; 'W'
0x1800189f4  jnz     short loc_180018A26
0x1800189f6  mov     r8d, [rdi+70h]; dwMessageId
0x1800189fa  lea     rax, [rbp+420h+szString]
0x1800189fe  mov     [rsp+520h+Arguments], rsi; Arguments
0x180018a03  xor     r9d, r9d; dwLanguageId
0x180018a06  mov     [rsp+520h+nSize], ebx; nSize
0x180018a0a  xor     edx, edx; lpSource
0x180018a0c  mov     ecx, 1000h; dwFlags
0x180018a11  mov     [rsp+520h+lpBuffer], rax; lpBuffer
0x180018a16  call    cs:__imp_FormatMessageW
0x180018a1c  test    eax, eax
0x180018a1e  jnz     short loc_180018A2A
0x180018a20  call    cs:__imp_GetLastError
0x180018a26  test    eax, eax
0x180018a28  jnz     short loc_180018A54
0x180018a2a  mov     rcx, [rdi+18h]; hWnd
0x180018a2e  lea     rdx, [rbp+420h+szString]; lpString
0x180018a32  call    cs:__imp_SetWindowTextW
0x180018a38  mov     rcx, [rdi+18h]; hWnd
0x180018a3c  mov     edx, 1; bEnable
0x180018a41  call    cs:__imp_EnableWindow
0x180018a47  mov     rcx, [rdi+18h]; hWnd
0x180018a4b  mov     edx, r14d; nCmdShow
0x180018a4e  call    cs:__imp_ShowWindow
0x180018a54  mov     rax, [rsp+520h+var_4B8]
0x180018a59  test    rax, rax
0x180018a5c  jz      short loc_180018A84
0x180018a5e  mov     rcx, [rax]
0x180018a61  test    rcx, rcx
0x180018a64  jz      short loc_180018A84
0x180018a66  cmp     dword ptr [rcx], 2
0x180018a69  jnz     short loc_180018A84
0x180018a6b  mov     ecx, [rdi+70h]
0x180018a6e  call    IsDiagnosableError
0x180018a73  test    eax, eax
0x180018a75  jz      short loc_180018A84
0x180018a77  mov     rcx, [rdi+28h]; hWnd
0x180018a7b  mov     edx, r14d; nCmdShow
0x180018a7e  call    cs:__imp_ShowWindow
0x180018a84  mov     rcx, [rdi+30h]; hWnd
0x180018a88  mov     edx, r14d; nCmdShow
0x180018a8b  call    cs:__imp_ShowWindow
0x180018a91  mov     edx, r14d; nCmdShow
0x180018a94  cmp     [rdi+88h], esi
0x180018a9a  jnz     short loc_180018AAD
0x180018a9c  test    r13d, r13d
0x180018a9f  jz      short loc_180018AAD
0x180018aa1  mov     rcx, [rdi+40h]; hWnd
0x180018aa5  call    cs:__imp_ShowWindow
0x180018aab  jmp     short loc_180018ABF
0x180018aad  mov     rcx, [rdi+20h]; hWnd
0x180018ab1  call    cs:__imp_ShowWindow
0x180018ab7  mov     rax, [rdi+20h]
0x180018abb  mov     [rdi+68h], rax
0x180018abf  mov     rcx, [rdi+10h]; hWnd
0x180018ac3  mov     r9d, 2; lParam
0x180018ac9  xor     r8d, r8d; wParam
0x180018acc  mov     edx, 48Ah; Msg
0x180018ad1  call    cs:__imp_PostMessageW
0x180018ad7  jmp     loc_18001877D
0x180018adc  mov     rcx, cs:hInst; hModule
0x180018ae3  lea     r8, [rsp+520h+var_4E0]
0x180018ae8  mov     edx, 0BFEh
0x180018aed  mov     [rsp+520h+var_4E0], esi
0x180018af1  call    PszLoadStringPcch
0x180018af6  mov     rcx, [rdi+10h]; hWnd
0x180018afa  mov     r9d, 10h; lParam
0x180018b00  xor     r8d, r8d; wParam
0x180018b03  mov     edx, 48Ah; Msg
0x180018b08  mov     rbx, rax
0x180018b0b  call    cs:__imp_PostMessageW
0x180018b11  mov     rcx, [rdi+10h]; hWnd
0x180018b15  mov     r9, rbx; lParam
0x180018b18  xor     r8d, r8d; wParam
0x180018b1b  mov     edx, 489h; Msg
0x180018b20  call    cs:__imp_SendMessageW
0x180018b26  mov     rcx, [rdi+10h]; hWnd
0x180018b2a  mov     r9, rbx; lParam
0x180018b2d  xor     r8d, r8d; wParam
0x180018b30  mov     edx, 479h; Msg
0x180018b35  call    cs:__imp_SendMessageW
0x180018b3b  mov     rcx, cs:qword_18004D9B0; hModule
0x180018b42  lea     r8, [rsp+520h+var_4E0]
0x180018b47  mov     edx, 0C99h
0x180018b4c  mov     [rsp+520h+var_4E0], esi
0x180018b50  call    PszLoadStringPcch
0x180018b55  mov     rcx, [rdi+10h]; hWnd
0x180018b59  xor     r9d, r9d; lParam
0x180018b5c  mov     r8, r15; wParam
0x180018b5f  mov     edx, 481h; Msg
0x180018b64  mov     rbx, rax
0x180018b67  call    cs:__imp_SendMessageW
0x180018b6d  mov     rcx, [rdi+10h]; hWnd
0x180018b71  mov     r9, rbx; lParam
0x180018b74  movsxd  r8, eax; wParam
0x180018b77  mov     edx, 47Eh; Msg
0x180018b7c  call    cs:__imp_SendMessageW
0x180018b82  cmp     [rdi+88h], esi
0x180018b88  jz      short loc_180018B90
  ... truncated ...
```
