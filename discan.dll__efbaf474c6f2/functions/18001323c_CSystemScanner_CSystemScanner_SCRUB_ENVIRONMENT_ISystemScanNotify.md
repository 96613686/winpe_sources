# CSystemScanner::CSystemScanner(_SCRUB_ENVIRONMENT *,ISystemScanNotify *)

- ea: `0x18001323c`
- end: `0x180013509`
- name: `??0CSystemScanner@@QEAA@PEAU_SCRUB_ENVIRONMENT@@PEAUISystemScanNotify@@@Z`
- size: `717`
- prototype: `CSystemScanner *__fastcall(char *pv, struct _SCRUB_ENVIRONMENT *, struct ISystemScanNotify *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800056f8`

## callees

- `0x1800032f8`
- `0x180003640`
- `0x180006498`
- `0x180006688`
- `0x1800068b4`
- `0x18001323c`
- `0x180018d88`
- `0x180035684`

## import_xrefs

- `KERNEL32!InitializeSRWLock` at `0x180013278`
- `KERNEL32!InitializeSRWLock` at `0x180013287`
- `KERNEL32!InitializeSRWLock` at `0x1800132c3`
- `KERNEL32!InitializeSRWLock` at `0x180013335`
- `KERNEL32!InitializeSRWLock` at `0x180013278`
- `KERNEL32!InitializeSRWLock` at `0x180013287`
- `KERNEL32!InitializeSRWLock` at `0x1800132c3`
- `KERNEL32!InitializeSRWLock` at `0x180013335`
- `KERNEL32!GetLastError` at `0x180013401`
- `KERNEL32!GetLastError` at `0x18001348a`
- `KERNEL32!GetLastError` at `0x180013401`
- `KERNEL32!GetLastError` at `0x18001348a`
- `KERNEL32!CreateThreadpoolWork` at `0x180013478`
- `KERNEL32!CreateThreadpoolWork` at `0x180013478`

## string_xrefs

- `0x1800134c6`: `BOOL_HR( m_SystemScanCompleteWork.AttachEx( CreateThreadpoolWork( SystemScanCompleteWork, this, m_ScrubEnvironment->ScrubWorkerCallbackEnv ) ) )`

## pseudocode

```c
CSystemScanner *__fastcall CSystemScanner::CSystemScanner(
        char *pv,
        struct _SCRUB_ENVIRONMENT *a2,
        struct ISystemScanNotify *a3)
{
  __int64 v4; // rdx
  signed int LastError; // eax
  signed int v6; // ebx
  PTP_WORK ThreadpoolWork; // rax
  signed int v8; // eax
  signed int v9; // ebx
  const char *v11; // [rsp+40h] [rbp-28h] BYREF
  signed int v12; // [rsp+48h] [rbp-20h]

  *(_QWORD *)pv = &CSystemScanner::`vftable'{for `IDiskScanNotify'};
  *((_QWORD *)pv + 1) = &CSystemScanner::`vftable'{for `IDiskPnpNotify'};
  *((_QWORD *)pv + 2) = a2;
  *((_QWORD *)pv + 3) = a3;
  InitializeSRWLock((PSRWLOCK)pv + 6);
  *((_DWORD *)pv + 17) = 0;
  InitializeSRWLock((PSRWLOCK)pv + 9);
  *((_QWORD *)pv + 10) = 0;
  *((_QWORD *)pv + 11) = 0;
  *((_QWORD *)pv + 12) = 0;
  *((_QWORD *)pv + 13) = 0;
  *((_QWORD *)pv + 14) = 0;
  *((_DWORD *)pv + 30) = 10;
  *((_QWORD *)pv + 16) = 0;
  *((_QWORD *)pv + 17) = 0;
  *((_DWORD *)pv + 36) = 0;
  InitializeSRWLock((PSRWLOCK)pv + 19);
  *((_QWORD *)pv + 20) = 0;
  *((_QWORD *)pv + 21) = 0;
  *((_QWORD *)pv + 22) = 0;
  *((_QWORD *)pv + 23) = 0;
  *((_QWORD *)pv + 24) = 0;
  *((_DWORD *)pv + 50) = 10;
  *((_QWORD *)pv + 26) = 0;
  *((_QWORD *)pv + 27) = 0;
  *((_DWORD *)pv + 56) = 0;
  *((_DWORD *)pv + 58) = 0;
  *((_DWORD *)pv + 59) = -2147221008;
  *((_QWORD *)pv + 30) = 0;
  *((_DWORD *)pv + 62) = 0;
  pv[252] = 0;
  InitializeSRWLock((PSRWLOCK)pv + 32);
  *((_DWORD *)pv + 66) = 0;
  CDiskPnpMonitor::CDiskPnpMonitor((CDiskPnpMonitor *)(pv + 272), (struct IDiskPnpNotify *)(pv + 8));
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v4 + 16) = "CSystemScanner::CSystemScanner";
  v11 = "CSystemScanner::CSystemScanner";
  v12 = 0;
  ++*(_WORD *)(v4 + 8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CSystemScanner::CSystemScanner");
  }
  if ( (unsigned int)SuInitialize() )
  {
    v6 = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
  }
  *((_DWORD *)pv + 59) = v6;
  v12 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids,
        (unsigned int)v6);
    }
    ATL::AtlThrowImpl(v6);
  }
  ThreadpoolWork = CreateThreadpoolWork(
                     CSystemScanner::SystemScanCompleteWork,
                     pv,
                     *(PTP_CALLBACK_ENVIRON *)(*((_QWORD *)pv + 2) + 72LL));
  *((_QWORD *)pv + 30) = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids,
        (unsigned int)"BOOL_HR( m_SystemScanCompleteWork.AttachEx( CreateThreadpoolWork( SystemScanCompleteWork, this, m_"
                      "ScrubEnvironment->ScrubWorkerCallbackEnv ) ) )",
        v9);
    }
    ATL::AtlThrowImpl(v9);
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v11);
  return (CSystemScanner *)pv;
}

```

## disassembly

```asm
0x18001323c  mov     [rsp+arg_8], rbx
0x180013241  mov     [rsp+arg_10], rsi
0x180013246  mov     [rsp+arg_0], rcx
0x18001324b  push    rdi
0x18001324c  push    r12
0x18001324e  push    r15
0x180013250  sub     rsp, 50h
0x180013254  mov     rdi, rcx
0x180013257  lea     rax, ??_7CSystemScanner@@6BIDiskScanNotify@@@; const CSystemScanner::`vftable'{for `IDiskScanNotify'}
0x18001325e  mov     [rcx], rax
0x180013261  lea     rax, ??_7CSystemScanner@@6BIDiskPnpNotify@@@; const CSystemScanner::`vftable'{for `IDiskPnpNotify'}
0x180013268  mov     [rcx+8], rax
0x18001326c  mov     [rcx+10h], rdx
0x180013270  mov     [rcx+18h], r8
0x180013274  add     rcx, 30h ; '0'; SRWLock
0x180013278  call    cs:__imp_InitializeSRWLock
0x18001327e  xor     esi, esi
0x180013280  mov     [rdi+44h], esi
0x180013283  lea     rcx, [rdi+48h]; SRWLock
0x180013287  call    cs:__imp_InitializeSRWLock
0x18001328d  mov     [rdi+50h], rsi
0x180013291  mov     [rdi+58h], rsi
0x180013295  mov     [rdi+60h], rsi
0x180013299  mov     [rdi+68h], rsi
0x18001329d  mov     [rdi+70h], rsi
0x1800132a1  mov     dword ptr [rdi+78h], 0Ah
0x1800132a8  mov     [rdi+80h], rsi
0x1800132af  mov     [rdi+88h], rsi
0x1800132b6  mov     [rdi+90h], esi
0x1800132bc  lea     rcx, [rdi+98h]; SRWLock
0x1800132c3  call    cs:__imp_InitializeSRWLock
0x1800132c9  mov     [rdi+0A0h], rsi
0x1800132d0  mov     [rdi+0A8h], rsi
0x1800132d7  mov     [rdi+0B0h], rsi
0x1800132de  mov     [rdi+0B8h], rsi
0x1800132e5  mov     [rdi+0C0h], rsi
0x1800132ec  mov     dword ptr [rdi+0C8h], 0Ah
0x1800132f6  mov     [rdi+0D0h], rsi
0x1800132fd  mov     [rdi+0D8h], rsi
0x180013304  mov     [rdi+0E0h], esi
0x18001330a  mov     [rdi+0E8h], esi
0x180013310  mov     dword ptr [rdi+0ECh], 800401F0h
0x18001331a  mov     [rdi+0F0h], rsi
0x180013321  mov     [rdi+0F8h], esi
0x180013327  mov     [rdi+0FCh], sil
0x18001332e  lea     rcx, [rdi+100h]; SRWLock
0x180013335  call    cs:__imp_InitializeSRWLock
0x18001333b  mov     [rdi+108h], esi
0x180013341  lea     rcx, [rdi+110h]; this
0x180013348  lea     rdx, [rdi+8]; struct IDiskPnpNotify *
0x18001334c  call    ??0CDiskPnpMonitor@@QEAA@PEAUIDiskPnpNotify@@@Z; CDiskPnpMonitor::CDiskPnpMonitor(IDiskPnpNotify *)
0x180013351  nop
0x180013352  mov     ecx, cs:_tls_index
0x180013358  mov     rax, gs:58h
0x180013361  mov     rdx, [rax+rcx*8]
0x180013365  mov     eax, 10h
0x18001336a  lea     r8, aCsystemscanner_6; "CSystemScanner::CSystemScanner"
0x180013371  mov     [rax+rdx], r8
0x180013375  mov     [rsp+68h+var_28], r8
0x18001337a  mov     [rsp+68h+var_20], esi
0x18001337e  mov     eax, 8
0x180013383  inc     word ptr [rax+rdx]
0x180013387  movzx   edx, word ptr [rax+rdx]
0x18001338b  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180013392  movzx   eax, cx
0x180013395  cmp     dx, cx
0x180013398  cmovb   ax, dx
0x18001339c  mov     [rsp+68h+var_38], ax
0x1800133a1  cmovb   cx, dx
0x1800133a5  mov     [rsp+68h+var_36], cx
0x1800133aa  xor     eax, eax
0x1800133ac  mov     [rsp+68h+var_34], eax
0x1800133b0  mov     rax, cs:off_180047060; "                                       "...
0x1800133b7  mov     [rsp+68h+var_30], rax
0x1800133bc  lea     r12, WPP_GLOBAL_Control
0x1800133c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133ca  cmp     rcx, r12
0x1800133cd  jz      short loc_1800133F2
0x1800133cf  test    byte ptr [rcx+1Ch], 1
0x1800133d3  jz      short loc_1800133F2
0x1800133d5  cmp     byte ptr [rcx+19h], 5
0x1800133d9  jb      short loc_1800133F2
0x1800133db  lea     edx, [rsi+0Dh]
0x1800133de  mov     [rsp+68h+var_48], r8; __int64
0x1800133e3  lea     r9, [rsp+68h+var_38]
0x1800133e8  mov     rcx, [rcx+10h]; LoggerHandle
0x1800133ec  call    WPP_SF_aZs
0x1800133f1  nop
0x1800133f2  call    ?SuInitialize@@YAHXZ; SuInitialize(void)
0x1800133f7  mov     r15d, 80004005h
0x1800133fd  test    eax, eax
0x1800133ff  jnz     short loc_18001341E
0x180013401  call    cs:__imp_GetLastError
0x180013407  mov     ebx, eax
0x180013409  test    eax, eax
0x18001340b  jle     short loc_180013416
0x18001340d  movzx   ebx, ax
0x180013410  or      ebx, 80070000h
0x180013416  test    ebx, ebx
0x180013418  cmovns  ebx, r15d
0x18001341c  jmp     short loc_180013420
0x18001341e  mov     ebx, esi
0x180013420  mov     [rdi+0ECh], ebx
0x180013426  mov     [rsp+68h+var_20], ebx
0x18001342a  test    ebx, ebx
0x18001342c  jns     short loc_180013466
0x18001342e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013435  cmp     rcx, r12
0x180013438  jz      short loc_18001345E
0x18001343a  test    byte ptr [rcx+1Ch], 1
0x18001343e  jz      short loc_18001345E
0x180013440  cmp     byte ptr [rcx+19h], 2
0x180013444  jb      short loc_18001345E
0x180013446  mov     edx, 0Ah
0x18001344b  mov     r9d, ebx
0x18001344e  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x180013455  mov     rcx, [rcx+10h]
0x180013459  call    WPP_SF_d
0x18001345e  mov     ecx, ebx; int
0x180013460  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180013466  mov     r8, [rdi+10h]
0x18001346a  mov     r8, [r8+48h]; pcbe
0x18001346e  mov     rdx, rdi; pv
0x180013471  lea     rcx, ?SystemScanCompleteWork@CSystemScanner@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180013478  call    cs:__imp_CreateThreadpoolWork
0x18001347e  mov     [rdi+0F0h], rax
0x180013485  test    rax, rax
0x180013488  jnz     short loc_1800134E5
0x18001348a  call    cs:__imp_GetLastError
0x180013490  mov     ebx, eax
0x180013492  test    eax, eax
0x180013494  jle     short loc_18001349F
0x180013496  movzx   ebx, ax
0x180013499  or      ebx, 80070000h
0x18001349f  test    ebx, ebx
0x1800134a1  cmovns  ebx, r15d
0x1800134a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134ac  cmp     rcx, r12
0x1800134af  jz      short loc_1800134DD
0x1800134b1  test    byte ptr [rcx+1Ch], 1
0x1800134b5  jz      short loc_1800134DD
0x1800134b7  cmp     byte ptr [rcx+19h], 2
0x1800134bb  jb      short loc_1800134DD
0x1800134bd  mov     edx, 0Bh
0x1800134c2  mov     dword ptr [rsp+68h+var_48], ebx
0x1800134c6  lea     r9, aBoolHrMSystems; "BOOL_HR( m_SystemScanCompleteWork.Attac"...
0x1800134cd  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x1800134d4  mov     rcx, [rcx+10h]
0x1800134d8  call    WPP_SF_sd
0x1800134dd  mov     ecx, ebx; int
0x1800134df  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800134e5  lea     rcx, [rsp+68h+var_28]; this
0x1800134ea  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800134ef  nop
0x1800134f0  mov     rax, rdi
0x1800134f3  lea     r11, [rsp+68h+var_18]
0x1800134f8  mov     rbx, [r11+28h]
0x1800134fc  mov     rsi, [r11+30h]
0x180013500  mov     rsp, r11
0x180013503  pop     r15
0x180013505  pop     r12
0x180013507  pop     rdi
0x180013508  retn
```
