# ProgressPage::OnMessage(uint,unsigned __int64,__int64,__int64 *)

- ea: `0x140016d90`
- end: `0x1400172cf`
- name: `?OnMessage@ProgressPage@@MEAA_NI_K_JPEA_J@Z`
- size: `1343`
- prototype: `bool __fastcall(ProgressPage *__hidden this, unsigned int, unsigned __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task`

## callees

- `0x14000e72c`
- `0x14000f1a0`
- `0x1400104bc`
- `0x140010680`
- `0x140016d90`
- `0x1400186b4`
- `0x140020420`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001714c`
- `KERNEL32!GetLastError` at `0x140017197`
- `KERNEL32!GetLastError` at `0x14001724f`
- `KERNEL32!GetLastError` at `0x14001714c`
- `KERNEL32!GetLastError` at `0x140017197`
- `KERNEL32!GetLastError` at `0x14001724f`
- `KERNEL32!HeapAlloc` at `0x1400171eb`
- `KERNEL32!HeapAlloc` at `0x1400171eb`
- `KERNEL32!HeapFree` at `0x14001729f`
- `KERNEL32!HeapFree` at `0x14001729f`
- `KERNEL32!GetProcessHeap` at `0x1400171d6`
- `KERNEL32!GetProcessHeap` at `0x14001728b`
- `KERNEL32!GetProcessHeap` at `0x1400171d6`
- `KERNEL32!GetProcessHeap` at `0x14001728b`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140017182`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140017182`
- `KERNEL32!CreateTimerQueueTimer` at `0x14001723f`
- `KERNEL32!CreateTimerQueueTimer` at `0x14001723f`
- `KERNEL32!ResetEvent` at `0x140017136`
- `KERNEL32!ResetEvent` at `0x140017136`
- `USER32!SetWindowLongPtrW` at `0x140016f29`
- `USER32!SetWindowLongPtrW` at `0x140016f56`
- `USER32!SetWindowLongPtrW` at `0x140016f29`
- `USER32!SetWindowLongPtrW` at `0x140016f56`
- `USER32!GetWindowLongW` at `0x140016f01`
- `USER32!GetWindowLongW` at `0x140016f01`
- `USER32!SendMessageW` at `0x140016ec5`
- `USER32!SendMessageW` at `0x140016ec5`
- `OLEAUT32!__imp_SysAllocString` at `0x140017098`
- `OLEAUT32!__imp_SysAllocString` at `0x140017098`
- `OLEAUT32!__imp_SysFreeString` at `0x140017082`
- `OLEAUT32!__imp_SysFreeString` at `0x140017082`
- `UxTheme!SetWindowTheme` at `0x140016e37`
- `UxTheme!SetWindowTheme` at `0x140016e37`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1400170bb`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1400170bb`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140016db8`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140016db8`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140016dd6`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140016dd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall ProgressPage::OnMessage(
        void **this,
        unsigned int a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4,
        __int64 *a5)
{
  bool v9; // bp
  signed int NamedHandle; // eax
  int v11; // r9d
  HWND v12; // rbx
  int v13; // esi
  UINT v14; // edx
  int v15; // esi
  HWND v16; // rcx
  WPARAM v17; // r8
  LPARAM v18; // r9
  __int16 WindowLongW; // ax
  int v20; // ebx
  void *v21; // rcx
  OLECHAR *v22; // rcx
  bool v24; // sf
  _QWORD *v25; // rbx
  void *v26; // rdx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  _DWORD *v29; // rax
  void *v30; // rsi
  signed int v31; // eax
  bool v32; // sf
  HANDLE v33; // rax
  const unsigned __int16 *DueTime; // [rsp+20h] [rbp-88h]
  const unsigned __int16 *DueTimea; // [rsp+20h] [rbp-88h]
  const unsigned __int16 *DueTimeb; // [rsp+20h] [rbp-88h]
  HWND hwnd; // [rsp+40h] [rbp-68h] BYREF
  DirectUI::Element *Element; // [rsp+48h] [rbp-60h]
  unsigned int v39[22]; // [rsp+50h] [rbp-58h] BYREF

  v9 = 0;
  hwnd = 0;
  Element = DirectUI::TaskPage::GetElement((DirectUI::TaskPage *)this);
  v39[0] = 0;
  DirectUI::Element::StartDefer(Element, v39);
  NamedHandle = WizardPage::GetNamedHandle((WizardPage *)this, L"progress", &hwnd);
  if ( NamedHandle >= 0 )
  {
    v12 = hwnd;
    SetWindowTheme(hwnd, L" ", L" ");
    if ( a2 == 2524 )
    {
      if ( !ResetEvent(g_ProgressPageLoaded) )
      {
        NamedHandle = GetLastError();
        v24 = NamedHandle < 0;
        if ( NamedHandle > 0 )
        {
          NamedHandle = (unsigned __int16)NamedHandle | 0x80070000;
          v24 = NamedHandle < 0;
        }
        if ( v24 )
        {
          v11 = 1535;
          goto LABEL_3;
        }
      }
      v25 = this + 15;
      v26 = this[15];
      if ( v26 )
      {
        if ( DeleteTimerQueueTimer(0, v26, 0) )
        {
          *v25 = 0;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          *v25 = 0;
          if ( LastError < 0 )
            SdpDebugPrint(1u, "Dwz IGNORED: %s:%d - hr = 0x%08X\n", "ProgressPage::OnMessage", 1546, LastError);
        }
      }
      ProcessHeap = GetProcessHeap();
      v29 = HeapAlloc(ProcessHeap, 0, 0x10u);
      v30 = v29;
      if ( !v29 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ProgressPage::OnMessage", 1553, -2147024882);
        goto LABEL_45;
      }
      *((_QWORD *)v29 + 1) = this;
      *v29 = *((_DWORD *)this + 40);
      if ( !CreateTimerQueueTimer(this + 15, 0, ProgressPage::ShowPageMinimumTimeCallback, v29, 0x2EEu, 0, 0) )
      {
        v31 = GetLastError();
        v32 = v31 < 0;
        if ( v31 > 0 )
        {
          v31 = (unsigned __int16)v31 | 0x80070000;
          v32 = v31 < 0;
        }
        if ( v32 )
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ProgressPage::OnMessage", 1566, v31);
          v33 = GetProcessHeap();
          HeapFree(v33, 0, v30);
          v9 = 0;
          goto LABEL_45;
        }
      }
      NamedHandle = ProgressPage::SetVisible((ProgressPage *)this);
      if ( NamedHandle < 0 )
      {
        v11 = 1574;
        goto LABEL_3;
      }
    }
    else if ( a2 == 2525 )
    {
      NamedHandle = WizardPage::SetNamedValues((WizardPage *)this, L"txtProgress", a4, 0, DueTime, 0);
      if ( NamedHandle < 0 )
      {
        v11 = 1586;
        goto LABEL_3;
      }
      NamedHandle = WizardPage::SetNamedValues((WizardPage *)this, L"txtSubProgress", L" ", 0, DueTimeb, 0);
      if ( NamedHandle < 0 )
      {
        v11 = 1589;
        goto LABEL_3;
      }
    }
    else if ( a2 == 2526 )
    {
      NamedHandle = WizardPage::SetNamedValues((WizardPage *)this, L"txtProgress", L" ", 0, DueTime, 0);
      if ( NamedHandle < 0 )
      {
        v11 = 1619;
        goto LABEL_3;
      }
      NamedHandle = WizardPage::SetNamedValues((WizardPage *)this, L"txtSubProgress", L" ", 0, DueTimea, 0);
      if ( NamedHandle < 0 )
      {
        v11 = 1622;
        goto LABEL_3;
      }
      if ( *((_DWORD *)this + 32) )
      {
        NamedHandle = WizardPage::SetHeader((WizardPage *)this, a4);
        if ( NamedHandle < 0 )
        {
          v11 = 1626;
          goto LABEL_3;
        }
      }
      v22 = (OLECHAR *)this[18];
      if ( v22 )
      {
        SysFreeString(v22);
        this[18] = 0;
      }
      this[18] = SysAllocString(a4);
    }
    else if ( a2 == 2531 )
    {
      NamedHandle = WizardPage::SetNamedValues((WizardPage *)this, L"txtSubProgress", a4, 0, DueTime, 0);
      if ( NamedHandle < 0 )
      {
        v11 = 1604;
        goto LABEL_3;
      }
    }
    else
    {
      if ( a2 != 2534 )
      {
        if ( a2 == 2538 )
        {
          WindowLongW = GetWindowLongW(v12, -16);
          if ( (_DWORD)a4 == 1 )
          {
            if ( (WindowLongW & 0x40A) != 0 )
              SetWindowLongPtrW(v12, -16, 1342177280);
            v17 = (int)a3;
            v18 = 0;
            v14 = 1026;
          }
          else
          {
            if ( (WindowLongW & 0x40A) != 0 )
              goto LABEL_45;
            SetWindowLongPtrW(v12, -16, 1342177288);
            v18 = 35;
            v17 = 1;
            v14 = 1034;
          }
        }
        else
        {
          if ( a2 != 2539 )
          {
            v9 = WizardPage::OnMessage((WizardPage *)this, a2, a3, (__int64)a4, a5);
            goto LABEL_45;
          }
          v13 = a3 - 100;
          v14 = 1033;
          if ( v13 )
          {
            v15 = v13 - 1;
            v16 = v12;
            if ( v15 )
            {
              v17 = 0;
              if ( v15 == 1 )
                v18 = 1080336;
              else
                v18 = 4278190080LL;
            }
            else
            {
              v18 = 47615;
              v17 = 0;
            }
            goto LABEL_17;
          }
          v18 = 2298344;
          v17 = 0;
        }
        v16 = v12;
LABEL_17:
        SendMessageW(v16, v14, v17, v18);
        goto LABEL_45;
      }
      v20 = *((_DWORD *)Config + 48);
      if ( (*((unsigned int (__fastcall **)(void **))*this + 22))(this) == v20 )
      {
        v21 = this[19];
        if ( v21 )
        {
          NamedHandle = (*(__int64 (__fastcall **)(void *, HWND, __int64))(*(_QWORD *)v21 + 80LL))(v21, g_HWND, 1);
          if ( NamedHandle < 0 )
          {
            v11 = 1643;
            goto LABEL_3;
          }
        }
      }
    }
    v9 = 1;
    goto LABEL_45;
  }
  v11 = 1448;
LABEL_3:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ProgressPage::OnMessage", v11, NamedHandle);
LABEL_45:
  if ( v39[0] )
    DirectUI::Element::EndDefer(Element, v39[0]);
  return v9;
}

```

## disassembly

```asm
0x140016d90  push    rbx
0x140016d92  push    rbp
0x140016d93  push    rsi
0x140016d94  push    rdi
0x140016d95  push    r12
0x140016d97  push    r13
0x140016d99  push    r14
0x140016d9b  push    r15
0x140016d9d  sub     rsp, 68h
0x140016da1  mov     r14, r9
0x140016da4  mov     rsi, r8
0x140016da7  mov     r15d, edx
0x140016daa  mov     rdi, rcx
0x140016dad  xor     r12d, r12d
0x140016db0  mov     bpl, r12b
0x140016db3  mov     [rsp+0A8h+hwnd], r12
0x140016db8  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x140016dbf  nop     dword ptr [rax+rax+00h]
0x140016dc4  mov     [rsp+0A8h+var_60], rax
0x140016dc9  mov     [rsp+0A8h+var_58], r12d
0x140016dce  lea     rdx, [rsp+0A8h+var_58]
0x140016dd3  mov     rcx, rax
0x140016dd6  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x140016ddd  nop     dword ptr [rax+rax+00h]
0x140016de2  nop
0x140016de3  lea     r8, [rsp+0A8h+hwnd]; HWND *
0x140016de8  lea     rdx, aProgress; "progress"
0x140016def  mov     rcx, rdi; this
0x140016df2  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x140016df7  test    eax, eax
0x140016df9  jns     short loc_140016E22
0x140016dfb  mov     r9d, 5A8h
0x140016e01  mov     [rsp+0A8h+DueTime], eax
0x140016e05  lea     r8, aProgresspageOn_0; "ProgressPage::OnMessage"
0x140016e0c  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140016e13  mov     ecx, 1; Level
0x140016e18  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140016e1d  jmp     loc_1400170AE
0x140016e22  lea     r13, pszSubIdList; " "
0x140016e29  mov     r8, r13; pszSubIdList
0x140016e2c  mov     rdx, r13; pszSubAppName
0x140016e2f  mov     rbx, [rsp+0A8h+hwnd]
0x140016e34  mov     rcx, rbx; hwnd
0x140016e37  call    cs:__imp_SetWindowTheme
0x140016e3e  nop     dword ptr [rax+rax+00h]
0x140016e43  mov     eax, r15d
0x140016e46  sub     eax, 9DCh
0x140016e4b  jz      loc_14001712F
0x140016e51  sub     eax, 1
0x140016e54  jz      loc_1400170DD
0x140016e5a  sub     eax, 1
0x140016e5d  jz      loc_140017001
0x140016e63  sub     eax, 5
0x140016e66  jz      loc_140016FD4
0x140016e6c  sub     eax, 3
0x140016e6f  jz      loc_140016F71
0x140016e75  sub     eax, 4
0x140016e78  jz      short loc_140016EF7
0x140016e7a  cmp     eax, 1
0x140016e7d  jz      short loc_140016EA5
0x140016e7f  mov     rax, [rsp+0A8h+arg_20]
0x140016e87  mov     qword ptr [rsp+0A8h+DueTime], rax; __int64 *
0x140016e8c  mov     r9, r14; __int64
0x140016e8f  mov     r8, rsi; unsigned __int64
0x140016e92  mov     edx, r15d; unsigned int
0x140016e95  mov     rcx, rdi; this
0x140016e98  call    ?OnMessage@WizardPage@@MEAA_NI_K_JPEA_J@Z; WizardPage::OnMessage(uint,unsigned __int64,__int64,__int64 *)
0x140016e9d  mov     bpl, al
0x140016ea0  jmp     loc_1400170AE
0x140016ea5  sub     esi, 64h ; 'd'
0x140016ea8  mov     edx, 409h; Msg
0x140016ead  jz      short loc_140016EE9
0x140016eaf  sub     esi, 1
0x140016eb2  mov     rcx, rbx; hWnd
0x140016eb5  jz      short loc_140016EDE
0x140016eb7  xor     r8d, r8d; wParam
0x140016eba  cmp     esi, 1
0x140016ebd  jz      short loc_140016ED6
0x140016ebf  mov     r9d, 0FF000000h; lParam
0x140016ec5  call    cs:__imp_SendMessageW
0x140016ecc  nop     dword ptr [rax+rax+00h]
0x140016ed1  jmp     loc_1400170AE
0x140016ed6  mov     r9d, 107C10h
0x140016edc  jmp     short loc_140016EC5
0x140016ede  mov     r9d, 0B9FFh
0x140016ee4  xor     r8d, r8d
0x140016ee7  jmp     short loc_140016EC5
0x140016ee9  mov     r9d, 2311E8h
0x140016eef  xor     r8d, r8d
0x140016ef2  mov     rcx, rbx
0x140016ef5  jmp     short loc_140016EC5
0x140016ef7  mov     edi, 0FFFFFFF0h
0x140016efc  mov     rcx, rbx; hWnd
0x140016eff  mov     edx, edi; nIndex
0x140016f01  call    cs:__imp_GetWindowLongW
0x140016f08  nop     dword ptr [rax+rax+00h]
0x140016f0d  cmp     r14d, 1
0x140016f11  mov     r14d, 40Ah
0x140016f17  jnz     short loc_140016F42
0x140016f19  test    r14d, eax
0x140016f1c  jz      short loc_140016F35
0x140016f1e  mov     r8d, 50000000h; dwNewLong
0x140016f24  mov     edx, edi; nIndex
0x140016f26  mov     rcx, rbx; hWnd
0x140016f29  call    cs:__imp_SetWindowLongPtrW
0x140016f30  nop     dword ptr [rax+rax+00h]
0x140016f35  movsxd  r8, esi
0x140016f38  xor     r9d, r9d
0x140016f3b  mov     edx, 402h
0x140016f40  jmp     short loc_140016EF2
0x140016f42  test    r14d, eax
0x140016f45  jnz     loc_1400170AE
0x140016f4b  mov     r8d, 50000008h; dwNewLong
0x140016f51  mov     edx, edi; nIndex
0x140016f53  mov     rcx, rbx; hWnd
0x140016f56  call    cs:__imp_SetWindowLongPtrW
0x140016f5d  nop     dword ptr [rax+rax+00h]
0x140016f62  mov     r9d, 23h ; '#'
0x140016f68  lea     r8d, [r9-22h]
0x140016f6c  mov     edx, r14d
0x140016f6f  jmp     short loc_140016EF2
0x140016f71  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140016f78  mov     ebx, [rax+0C0h]
0x140016f7e  mov     rax, [rdi]
0x140016f81  mov     rcx, rdi
0x140016f84  mov     rax, [rax+0B0h]
0x140016f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016f90  cmp     eax, ebx
0x140016f92  jnz     loc_1400170AB
0x140016f98  mov     rcx, [rdi+98h]
0x140016f9f  test    rcx, rcx
0x140016fa2  jz      loc_1400170AB
0x140016fa8  mov     rax, [rcx]
0x140016fab  mov     r8d, 1
0x140016fb1  mov     rdx, cs:?g_HWND@@3PEAUHWND__@@EA; HWND__ * g_HWND
0x140016fb8  mov     rax, [rax+50h]
0x140016fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016fc1  test    eax, eax
0x140016fc3  jns     loc_1400170AB
0x140016fc9  mov     r9d, 66Bh
0x140016fcf  jmp     loc_140016E01
0x140016fd4  mov     qword ptr [rsp+0A8h+Period], r12; unsigned __int16 *
0x140016fd9  xor     r9d, r9d; unsigned __int16 *
0x140016fdc  mov     r8, r14; unsigned __int16 *
0x140016fdf  lea     rdx, aTxtsubprogress; "txtSubProgress"
0x140016fe6  mov     rcx, rdi; this
0x140016fe9  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140016fee  test    eax, eax
0x140016ff0  jns     loc_1400170AB
0x140016ff6  mov     r9d, 644h
0x140016ffc  jmp     loc_140016E01
0x140017001  mov     qword ptr [rsp+0A8h+Period], r12; unsigned __int16 *
0x140017006  xor     r9d, r9d; unsigned __int16 *
0x140017009  mov     r8, r13; unsigned __int16 *
0x14001700c  lea     rdx, aTxtprogress; "txtProgress"
0x140017013  mov     rcx, rdi; this
0x140017016  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x14001701b  test    eax, eax
0x14001701d  jns     short loc_14001702A
0x14001701f  mov     r9d, 653h
0x140017025  jmp     loc_140016E01
0x14001702a  mov     qword ptr [rsp+0A8h+Period], r12; unsigned __int16 *
0x14001702f  xor     r9d, r9d; unsigned __int16 *
0x140017032  mov     r8, r13; unsigned __int16 *
0x140017035  lea     rdx, aTxtsubprogress; "txtSubProgress"
0x14001703c  mov     rcx, rdi; this
0x14001703f  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140017044  test    eax, eax
0x140017046  jns     short loc_140017053
0x140017048  mov     r9d, 656h
0x14001704e  jmp     loc_140016E01
0x140017053  cmp     [rdi+80h], r12d
0x14001705a  jz      short loc_140017076
0x14001705c  mov     rdx, r14; unsigned __int16 *
0x14001705f  mov     rcx, rdi; this
0x140017062  call    ?SetHeader@WizardPage@@IEAAJPEBG@Z; WizardPage::SetHeader(ushort const *)
0x140017067  test    eax, eax
0x140017069  jns     short loc_140017076
0x14001706b  mov     r9d, 65Ah
0x140017071  jmp     loc_140016E01
0x140017076  mov     rcx, [rdi+90h]; bstrString
0x14001707d  test    rcx, rcx
0x140017080  jz      short loc_140017095
0x140017082  call    cs:__imp_SysFreeString
0x140017089  nop     dword ptr [rax+rax+00h]
0x14001708e  mov     [rdi+90h], r12
0x140017095  mov     rcx, r14; psz
0x140017098  call    cs:__imp_SysAllocString
0x14001709f  nop     dword ptr [rax+rax+00h]
0x1400170a4  mov     [rdi+90h], rax
0x1400170ab  mov     bpl, 1
0x1400170ae  mov     edx, [rsp+0A8h+var_58]
0x1400170b2  test    edx, edx
0x1400170b4  jz      short loc_1400170C8
0x1400170b6  mov     rcx, [rsp+0A8h+var_60]
0x1400170bb  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x1400170c2  nop     dword ptr [rax+rax+00h]
0x1400170c7  nop
0x1400170c8  mov     al, bpl
0x1400170cb  add     rsp, 68h
0x1400170cf  pop     r15
0x1400170d1  pop     r14
0x1400170d3  pop     r13
0x1400170d5  pop     r12
0x1400170d7  pop     rdi
0x1400170d8  pop     rsi
0x1400170d9  pop     rbp
0x1400170da  pop     rbx
0x1400170db  retn
0x1400170dd  mov     qword ptr [rsp+0A8h+Period], r12; unsigned __int16 *
0x1400170e2  xor     r9d, r9d; unsigned __int16 *
0x1400170e5  mov     r8, r14; unsigned __int16 *
0x1400170e8  lea     rdx, aTxtprogress; "txtProgress"
0x1400170ef  mov     rcx, rdi; this
0x1400170f2  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1400170f7  test    eax, eax
0x1400170f9  jns     short loc_140017106
0x1400170fb  mov     r9d, 632h
0x140017101  jmp     loc_140016E01
0x140017106  mov     qword ptr [rsp+0A8h+Period], r12; unsigned __int16 *
0x14001710b  xor     r9d, r9d; unsigned __int16 *
0x14001710e  mov     r8, r13; unsigned __int16 *
0x140017111  lea     rdx, aTxtsubprogress; "txtSubProgress"
0x140017118  mov     rcx, rdi; this
0x14001711b  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140017120  test    eax, eax
0x140017122  jns     short loc_1400170AB
0x140017124  mov     r9d, 635h
0x14001712a  jmp     loc_140016E01
0x14001712f  mov     rcx, cs:?g_ProgressPageLoaded@@3PEAXEA; hEvent
0x140017136  call    cs:__imp_ResetEvent
0x14001713d  nop     dword ptr [rax+rax+00h]
0x140017142  mov     r14d, 80070000h
0x140017148  test    eax, eax
0x14001714a  jnz     short loc_140017171
0x14001714c  call    cs:__imp_GetLastError
0x140017153  nop     dword ptr [rax+rax+00h]
0x140017158  test    eax, eax
0x14001715a  jle     short loc_140017164
0x14001715c  movzx   eax, ax
0x14001715f  or      eax, r14d
0x140017162  test    eax, eax
0x140017164  jns     short loc_140017171
0x140017166  mov     r9d, 5FFh
0x14001716c  jmp     loc_140016E01
0x140017171  lea     rbx, [rdi+78h]
0x140017175  mov     rdx, [rbx]; Timer
0x140017178  test    rdx, rdx
0x14001717b  jz      short loc_1400171D6
0x14001717d  xor     r8d, r8d; CompletionEvent
0x140017180  xor     ecx, ecx; TimerQueue
0x140017182  call    cs:__imp_DeleteTimerQueueTimer
0x140017189  nop     dword ptr [rax+rax+00h]
0x14001718e  test    eax, eax
0x140017190  jz      short loc_140017197
0x140017192  mov     [rbx], r12
0x140017195  jmp     short loc_1400171D6
0x140017197  call    cs:__imp_GetLastError
0x14001719e  nop     dword ptr [rax+rax+00h]
0x1400171a3  test    eax, eax
0x1400171a5  jle     short loc_1400171AD
0x1400171a7  movzx   eax, ax
0x1400171aa  or      eax, r14d
0x1400171ad  mov     [rbx], r12
0x1400171b0  test    eax, eax
0x1400171b2  jns     short loc_1400171D6
0x1400171b4  mov     [rsp+0A8h+DueTime], eax
0x1400171b8  mov     r9d, 60Ah
0x1400171be  lea     r8, aProgresspageOn_0; "ProgressPage::OnMessage"
0x1400171c5  lea     rdx, aDwzIgnoredSDHr; "Dwz IGNORED: %s:%d - hr = 0x%08X\n"
0x1400171cc  mov     ecx, 1; Level
0x1400171d1  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400171d6  call    cs:__imp_GetProcessHeap
0x1400171dd  nop     dword ptr [rax+rax+00h]
0x1400171e2  mov     rcx, rax; hHeap
0x1400171e5  xor     edx, edx; dwFlags
0x1400171e7  lea     r8d, [rdx+10h]; dwBytes
0x1400171eb  call    cs:__imp_HeapAlloc
0x1400171f2  nop     dword ptr [rax+rax+00h]
0x1400171f7  mov     rsi, rax
0x1400171fa  test    rax, rax
0x1400171fd  jnz     short loc_140017212
0x1400171ff  mov     [rsp+0A8h+DueTime], 8007000Eh
0x140017207  mov     r9d, 611h
0x14001720d  jmp     loc_140016E05
0x140017212  mov     [rax+8], rdi
0x140017216  mov     eax, [rdi+0A0h]
0x14001721c  mov     [rsi], eax
0x14001721e  mov     [rsp+0A8h+Flags], r12d; Flags
0x140017223  mov     [rsp+0A8h+Period], r12d; Period
0x140017228  mov     [rsp+0A8h+DueTime], 2EEh; DueTime
0x140017230  mov     r9, rsi; Parameter
0x140017233  lea     r8, ?ShowPageMinimumTimeCallback@ProgressPage@@KAXPEAXE@Z; Callback
0x14001723a  xor     edx, edx; TimerQueue
0x14001723c  mov     rcx, rbx; phNewTimer
0x14001723f  call    cs:__imp_CreateTimerQueueTimer
0x140017246  nop     dword ptr [rax+rax+00h]
0x14001724b  test    eax, eax
0x14001724d  jnz     short loc_1400172B3
0x14001724f  call    cs:__imp_GetLastError
  ... truncated ...
```
