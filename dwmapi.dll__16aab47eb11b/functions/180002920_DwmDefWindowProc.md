# DwmDefWindowProc

- ea: `0x180002920`
- end: `0x180002e7d`
- name: `DwmDefWindowProc`
- size: `1373`
- prototype: `BOOL __stdcall(HWND hWnd, UINT msg, WPARAM wParam, LPARAM lParam, LRESULT *plResult)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002920`
- `0x180002e90`
- `0x18000352c`
- `0x180003820`
- `0x18000387c`
- `0x1800045e8`
- `0x18000ad58`
- `0x18000aebc`
- `0x18000b25c`
- `0x18000b284`
- `0x18000b880`
- `0x18000bab0`
- `0x18000d0a0`
- `0x180017010`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x180002cd1`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180002cd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002af8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ddb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002af8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ddb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800029a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ab9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800029a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ab9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cf9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002c74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002c74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d07`
- `USER32!IsThreadDesktopComposited` at `0x18000296d`
- `USER32!IsThreadDesktopComposited` at `0x180002c0d`
- `USER32!IsThreadDesktopComposited` at `0x18000296d`
- `USER32!IsThreadDesktopComposited` at `0x180002c0d`
- `USER32!GetCapture` at `0x180002986`
- `USER32!GetCapture` at `0x180002986`
- `USER32!GetWindowInfo` at `0x1800029f8`
- `USER32!GetWindowInfo` at `0x1800029f8`
- `USER32!TrackMouseEvent` at `0x180002b81`
- `USER32!TrackMouseEvent` at `0x180002b81`
- `USER32!__imp_TransformPoint` at `0x180002a54`
- `USER32!__imp_TransformPoint` at `0x180002a54`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x180002a3f`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x180002a3f`

## pseudocode

```c
BOOL __stdcall DwmDefWindowProc(HWND hWnd, UINT msg, WPARAM wParam, LPARAM lParam, LRESULT *plResult)
{
  BOOL v9; // edi
  __m128i v10; // xmm6
  char v11; // r13
  struct CDwmHwndData *Element; // rax
  int v13; // eax
  __int64 ThreadDpiAwarenessContext; // rax
  int v15; // r15d
  CApiPortClient *v16; // rcx
  int v17; // eax
  int v18; // r14d
  LRESULT v19; // rbx
  CApiPortClient *v21; // rcx
  CApiPortClient *v22; // rcx
  int IsConnected; // r15d
  int v24; // eax
  CPortClient *v25; // r13
  HANDLE ProcessHeap; // rax
  char *v27; // rax
  void *v28; // rbx
  int v29; // r14d
  int v30; // r9d
  HANDLE v31; // rax
  int v32; // eax
  int v33; // eax
  int v34; // edi
  int v35; // eax
  void *v36; // [rsp+28h] [rbp-D8h]
  int v37; // [rsp+40h] [rbp-C0h] BYREF
  int v38; // [rsp+44h] [rbp-BCh]
  tagTRACKMOUSEEVENT EventTrack; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v41; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h]
  int v43; // [rsp+80h] [rbp-80h] BYREF
  HWND v44; // [rsp+84h] [rbp-7Ch]
  UINT v45; // [rsp+8Ch] [rbp-74h]
  int v46; // [rsp+90h] [rbp-70h]
  int v47; // [rsp+94h] [rbp-6Ch]
  WPARAM v48; // [rsp+98h] [rbp-68h]
  LPARAM v49; // [rsp+A0h] [rbp-60h]
  int v50; // [rsp+A8h] [rbp-58h]
  __int64 v51; // [rsp+ACh] [rbp-54h]
  tagWINDOWINFO pwi; // [rsp+B8h] [rbp-48h] BYREF

  if ( msg != 132 )
  {
    if ( msg != 674 )
    {
      if ( msg == 161 )
        goto LABEL_2;
      v9 = 0;
      if ( msg != 675 )
        return v9;
    }
    if ( (unsigned int)IsThreadDesktopComposited() == 1 )
    {
      EnterCriticalSection(&CriticalSection);
      IsConnected = CApiPortClient::IsConnected(v21);
      do
      {
        v24 = CApiPortClient::EnsureConnected(v22);
        if ( v24 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &CApiPortClient::MILINSTRUMENTATIONHRESULTLIST,
            2u,
            v24,
            0x7Fu,
            v36);
          goto LABEL_29;
        }
        ++dword_18001F948;
        LeaveCriticalSection(&CriticalSection);
        v25 = (CPortClient *)g_PortClient;
        ProcessHeap = GetProcessHeap();
        v27 = (char *)HeapAlloc(ProcessHeap, 8u, 0x3Cu);
        v28 = v27;
        if ( v27 )
        {
          *((_DWORD *)v27 + 10) = 1073741851;
          *(_DWORD *)v27 = 3932180;
          *((_DWORD *)v27 + 12) = 1073741851;
          *(_QWORD *)(v27 + 52) = hWnd;
          v36 = 0;
          v29 = NtAlpcSendWaitReceivePort(*((_QWORD *)v25 + 2), 0x10000, v27, 0, 0) | 0x10000000;
          CPortClient::CheckHRESULT(v25, v29);
          if ( v30 < 0 )
            MilInstrumentationCheckHR_MaybeFailFast(4u, &CPortClient::MILINSTRUMENTATIONHRESULTLIST, 9u, v29, 0x19Cu, 0);
          else
            v29 = 0;
          v31 = GetProcessHeap();
          HeapFree(v31, 0, v28);
        }
        else
        {
          v29 = -2147024882;
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &CPortClient::MILINSTRUMENTATIONHRESULTLIST,
            9u,
            -2147024882,
            0x18Bu,
            v36);
        }
        EnterCriticalSection(&CriticalSection);
        if ( !--dword_18001F948 )
        {
          v22 = (CApiPortClient *)*(unsigned int *)(g_PortClient + 8LL);
          if ( (_DWORD)v22 )
            CApiPortClient::Disconnect((CApiPortClient *)&g_PortClient);
        }
        if ( v29 != -805306313 )
          break;
        v32 = IsConnected--;
      }
      while ( v32 > 0 );
      v33 = CApiPortClient::Translate(v29);
      if ( v33 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(4u, &CApiPortClient::MILINSTRUMENTATIONHRESULTLIST, 2u, v33, 0x91u, v36);
LABEL_29:
      LeaveCriticalSection(&CriticalSection);
    }
    return 0;
  }
LABEL_2:
  if ( (unsigned int)IsThreadDesktopComposited() != 1 )
    return 0;
  if ( msg != 132 || (v9 = 0, !GetCapture()) )
  {
    v10 = 0;
    v11 = 0;
    EnterCriticalSection(&CDwmHwndData::s_cs);
    Element = CDwmHwndData::FindElement(hWnd);
    if ( Element )
    {
      v10 = *(__m128i *)((char *)Element + 8);
      v11 = 1;
    }
    LeaveCriticalSection(&CDwmHwndData::s_cs);
    pwi.cbSize = 60;
    v9 = 0;
    memset(&pwi.rcWindow, 0, 56);
    if ( v11 )
    {
      if ( GetWindowInfo(hWnd, &pwi) )
      {
        v37 = (__int16)lParam;
        v38 = SWORD1(lParam);
        if ( pwi.rcWindow.top == pwi.rcClient.top )
        {
          v13 = _mm_cvtsi128_si32(_mm_srli_si128(v10, 8));
          if ( v13 < 0 || SWORD1(lParam) <= pwi.rcClient.top + v13 )
          {
            ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
            TransformPoint(&v37, -3, ThreadDpiAwarenessContext);
            v43 = 1073741848;
            v46 = v37;
            v48 = wParam;
            v15 = 0;
            v51 = 0;
            v47 = v38;
            v44 = hWnd;
            v45 = msg;
            v49 = lParam;
            v50 = -2;
            *(_QWORD *)&EventTrack.cbSize = &CStandardData::`vftable';
            *(_OWORD *)&EventTrack.hwndTrack = 0;
            v40 = 52;
            EnterCriticalSection(&CriticalSection);
            v17 = CApiPortClient::EnsureConnected(v16);
            v18 = v17;
            if ( v17 >= 0 )
            {
              ++dword_18001F948;
              LeaveCriticalSection(&CriticalSection);
              v42 = 0;
              v41 = 0;
              (*(void (__fastcall **)(tagTRACKMOUSEEVENT *, __int128 *))(*(_QWORD *)&EventTrack.cbSize + 8LL))(
                &EventTrack,
                &v41);
              v34 = CPortClient::SendKernelSyncRequest(
                      g_PortClient,
                      &v43,
                      &v40,
                      (const struct DCOMPOSITION_DWM_LPC_EXTRA_DATA *)&v41);
              EnterCriticalSection(&CriticalSection);
              CApiPortClient::DecrementConnectionLock((CApiPortClient *)&g_PortClient);
              v35 = CApiPortClient::Translate(v34);
              v18 = v35;
              if ( v35 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &CApiPortClient::MILINSTRUMENTATIONHRESULTLIST,
                  2u,
                  v35,
                  0xF0u,
                  v36);
              }
              else
              {
                v15 = -2147024872;
                if ( v40 >= 4 )
                  v15 = v43;
              }
            }
            else
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &CApiPortClient::MILINSTRUMENTATIONHRESULTLIST,
                2u,
                v17,
                0xDCu,
                v36);
            }
            LeaveCriticalSection(&CriticalSection);
            *(_QWORD *)&EventTrack.cbSize = &CStandardData::`vftable';
            if ( EventTrack.hwndTrack )
              CApiPortClient::UnlockExtraDataPointer((CApiPortClient *)EventTrack.hwndTrack);
            std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(&EventTrack.dwHoverTime);
            v9 = 0;
            if ( v18 >= 0 && v15 >= 0 )
            {
              if ( HIDWORD(v51) )
              {
                if ( msg == 132 )
                {
                  v19 = (unsigned int)v51;
                  if ( (unsigned int)v51 == 8 || (unsigned int)v51 == 9 || (unsigned __int64)(unsigned int)v51 - 20 <= 1 )
                  {
                    EventTrack.cbSize = 24;
                    EventTrack.dwHoverTime = 0;
                    EventTrack.dwFlags = 18;
                    EventTrack.hwndTrack = hWnd;
                    *(&EventTrack.dwHoverTime + 1) = 0;
                    TrackMouseEvent(&EventTrack);
                    *plResult = v19;
                    return 1;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180002920  push    rbp
0x180002922  push    rbx
0x180002923  push    rsi
0x180002924  push    rdi
0x180002925  push    r12
0x180002927  push    r13
0x180002929  push    r14
0x18000292b  push    r15
0x18000292d  lea     rbp, [rsp-18h]
0x180002932  sub     rsp, 118h
0x180002939  movaps  [rsp+150h+var_50], xmm6
0x180002941  mov     rax, cs:__security_cookie
0x180002948  xor     rax, rsp
0x18000294b  mov     [rbp+50h+var_58], rax
0x18000294f  mov     r12, [rbp+50h+plResult]
0x180002956  mov     r14, r9
0x180002959  mov     r15, r8
0x18000295c  mov     ebx, edx
0x18000295e  mov     rsi, rcx
0x180002961  cmp     edx, 84h
0x180002967  jnz     loc_180002B92
0x18000296d  call    cs:__imp_IsThreadDesktopComposited
0x180002973  cmp     eax, 1
0x180002976  jnz     loc_180002C09
0x18000297c  cmp     ebx, 84h
0x180002982  jnz     short loc_180002995
0x180002984  xor     edi, edi
0x180002986  call    cs:__imp_GetCapture
0x18000298c  test    rax, rax
0x18000298f  jnz     loc_180002BB0
0x180002995  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; lpCriticalSection
0x18000299c  xorps   xmm6, xmm6
0x18000299f  xor     r13b, r13b
0x1800029a2  call    cs:__imp_EnterCriticalSection
0x1800029a8  mov     rcx, rsi; HWND
0x1800029ab  call    ?FindElement@CDwmHwndData@@SAPEAV1@PEAUHWND__@@@Z; CDwmHwndData::FindElement(HWND__ *)
0x1800029b0  test    rax, rax
0x1800029b3  jz      short loc_1800029BC
0x1800029b5  movups  xmm6, xmmword ptr [rax+8]
0x1800029b9  mov     r13b, 1
0x1800029bc  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; lpCriticalSection
0x1800029c3  call    cs:__imp_LeaveCriticalSection
0x1800029c9  xorps   xmm0, xmm0
0x1800029cc  mov     edi, 3Ch ; '<'
0x1800029d1  xor     eax, eax
0x1800029d3  mov     [rbp+50h+pwi.cbSize], edi
0x1800029d6  xor     edi, edi
0x1800029d8  mov     qword ptr [rbp+50h+pwi.cyWindowBorders], rax
0x1800029dc  movups  xmmword ptr [rbp+50h+pwi.rcWindow.left], xmm0
0x1800029e0  movups  xmmword ptr [rbp+50h+pwi.rcClient.left], xmm0
0x1800029e4  movups  xmmword ptr [rbp+50h+pwi.dwStyle], xmm0
0x1800029e8  test    r13b, r13b
0x1800029eb  jz      loc_180002BB0
0x1800029f1  lea     rdx, [rbp+50h+pwi]; pwi
0x1800029f5  mov     rcx, rsi; hwnd
0x1800029f8  call    cs:__imp_GetWindowInfo
0x1800029fe  test    eax, eax
0x180002a00  jz      loc_180002BB0
0x180002a06  mov     edx, [rbp+50h+pwi.rcClient.top]
0x180002a09  movsx   eax, r14w
0x180002a0d  mov     [rsp+150h+var_110], eax
0x180002a11  mov     rax, r14
0x180002a14  shr     rax, 10h
0x180002a18  movsx   ecx, ax
0x180002a1b  mov     [rsp+150h+var_10C], ecx
0x180002a1f  cmp     [rbp+50h+pwi.rcWindow.top], edx
0x180002a22  jnz     loc_180002BB0
0x180002a28  psrldq  xmm6, 8
0x180002a2d  movd    eax, xmm6
0x180002a31  test    eax, eax
0x180002a33  js      short loc_180002A3F
0x180002a35  add     eax, edx
0x180002a37  cmp     ecx, eax
0x180002a39  jg      loc_180002BB0
0x180002a3f  call    cs:__imp_GetThreadDpiAwarenessContext
0x180002a45  mov     rdx, 0FFFFFFFFFFFFFFFDh
0x180002a4c  lea     rcx, [rsp+150h+var_110]
0x180002a51  mov     r8, rax
0x180002a54  call    cs:__imp_TransformPoint
0x180002a5a  mov     eax, [rsp+150h+var_110]
0x180002a5e  lea     r13, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x180002a65  xorps   xmm0, xmm0
0x180002a68  mov     [rbp+50h+var_D0], 40000018h
0x180002a6f  movups  [rbp+50h+var_CC], xmm0
0x180002a73  mov     dword ptr [rbp+50h+var_CC+0Ch], eax
0x180002a76  lea     rcx, CriticalSection; lpCriticalSection
0x180002a7d  mov     eax, [rsp+150h+var_10C]
0x180002a81  movups  [rbp+50h+var_BC], xmm0
0x180002a85  mov     qword ptr [rbp+50h+var_BC+4], r15
0x180002a89  xor     r15d, r15d
0x180002a8c  movups  [rbp+50h+var_AC], xmm0
0x180002a90  mov     dword ptr [rbp+50h+var_BC], eax
0x180002a93  mov     qword ptr [rbp+50h+var_CC], rsi
0x180002a97  mov     dword ptr [rbp+50h+var_CC+8], ebx
0x180002a9a  mov     qword ptr [rbp+50h+var_BC+0Ch], r14
0x180002a9e  mov     dword ptr [rbp+50h+var_AC+4], 0FFFFFFFEh
0x180002aa5  mov     qword ptr [rsp+150h+EventTrack.cbSize], r13
0x180002aaa  movdqu  xmmword ptr [rsp+150h+EventTrack.hwndTrack], xmm0
0x180002ab0  mov     [rsp+150h+var_F0], 34h ; '4'
0x180002ab9  call    cs:__imp_EnterCriticalSection
0x180002abf  call    ?EnsureConnected@CApiPortClient@@AEAAJXZ; CApiPortClient::EnsureConnected(void)
0x180002ac4  mov     r14d, eax
0x180002ac7  test    eax, eax
0x180002ac9  jns     loc_180002DCE
0x180002acf  mov     [rsp+150h+var_130], 0DCh; unsigned int
0x180002ad7  mov     r9d, eax; int
0x180002ada  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CApiPortClient@@0QBJB; int *
0x180002ae1  mov     r8d, 2; unsigned int
0x180002ae7  mov     ecx, 4; unsigned int
0x180002aec  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180002af1  lea     rcx, CriticalSection; lpCriticalSection
0x180002af8  call    cs:__imp_LeaveCriticalSection
0x180002afe  mov     rcx, [rsp+150h+EventTrack.hwndTrack]
0x180002b03  mov     qword ptr [rsp+150h+EventTrack.cbSize], r13
0x180002b08  test    rcx, rcx
0x180002b0b  jnz     loc_180002E6E
0x180002b11  lea     rcx, [rsp+150h+EventTrack.dwHoverTime]
0x180002b16  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x180002b1b  xor     edi, edi
0x180002b1d  test    r14d, r14d
0x180002b20  js      loc_180002BB0
0x180002b26  test    r15d, r15d
0x180002b29  js      loc_180002BB0
0x180002b2f  cmp     dword ptr [rbp+50h+var_AC+0Ch], edi
0x180002b32  jz      short loc_180002BB0
0x180002b34  cmp     ebx, 84h
0x180002b3a  jnz     short loc_180002BB0
0x180002b3c  mov     ebx, dword ptr [rbp+50h+var_AC+8]
0x180002b3f  mov     eax, ebx
0x180002b41  sub     rax, 8
0x180002b45  jz      short loc_180002B59
0x180002b47  sub     rax, 1
0x180002b4b  jz      short loc_180002B59
0x180002b4d  sub     rax, 0Bh
0x180002b51  jz      short loc_180002B59
0x180002b53  cmp     rax, 1
0x180002b57  jnz     short loc_180002BB0
0x180002b59  xorps   xmm0, xmm0
0x180002b5c  mov     [rsp+150h+EventTrack.cbSize], 18h
0x180002b64  movups  xmmword ptr [rsp+150h+EventTrack.dwFlags], xmm0
0x180002b69  xor     eax, eax
0x180002b6b  mov     [rsp+150h+EventTrack.dwFlags], 12h
0x180002b73  lea     rcx, [rsp+150h+EventTrack]; lpEventTrack
0x180002b78  mov     [rsp+150h+EventTrack.hwndTrack], rsi
0x180002b7d  mov     dword ptr [rsp+150h+EventTrack+14h], eax
0x180002b81  call    cs:__imp_TrackMouseEvent
0x180002b87  mov     [r12], rbx
0x180002b8b  mov     edi, 1
0x180002b90  jmp     short loc_180002BB0
0x180002b92  cmp     ebx, 2A2h
0x180002b98  jz      short loc_180002C0D
0x180002b9a  cmp     ebx, 0A1h
0x180002ba0  jz      loc_18000296D
0x180002ba6  xor     edi, edi
0x180002ba8  cmp     ebx, 2A3h
0x180002bae  jz      short loc_180002C0D
0x180002bb0  mov     eax, edi
0x180002bb2  mov     rcx, [rbp+50h+var_58]
0x180002bb6  xor     rcx, rsp; StackCookie
0x180002bb9  call    __security_check_cookie
0x180002bbe  movaps  xmm6, [rsp+150h+var_50]
0x180002bc6  add     rsp, 118h
0x180002bcd  pop     r15
0x180002bcf  pop     r14
0x180002bd1  pop     r13
0x180002bd3  pop     r12
0x180002bd5  pop     rdi
0x180002bd6  pop     rsi
0x180002bd7  pop     rbx
0x180002bd8  pop     rbp
0x180002bd9  retn
0x180002bda  mov     [rsp+150h+var_130], 7Fh; unsigned int
0x180002be2  mov     r9d, eax; int
0x180002be5  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CApiPortClient@@0QBJB; int *
0x180002bec  mov     r8d, 2; unsigned int
0x180002bf2  mov     ecx, 4; unsigned int
0x180002bf7  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180002bfc  lea     rcx, CriticalSection; lpCriticalSection
0x180002c03  call    cs:__imp_LeaveCriticalSection
0x180002c09  xor     edi, edi
0x180002c0b  jmp     short loc_180002BB0
0x180002c0d  call    cs:__imp_IsThreadDesktopComposited
0x180002c13  cmp     eax, 1
0x180002c16  jnz     short loc_180002C09
0x180002c18  lea     rcx, CriticalSection; lpCriticalSection
0x180002c1f  call    cs:__imp_EnterCriticalSection
0x180002c25  call    ?IsConnected@CApiPortClient@@AEAA_NXZ; CApiPortClient::IsConnected(void)
0x180002c2a  xor     r15d, r15d
0x180002c2d  mov     edi, 1
0x180002c32  test    al, al
0x180002c34  cmovnz  r15d, edi
0x180002c38  mov     edi, 3Ch ; '<'
0x180002c3d  nop     dword ptr [rax]
0x180002c40  call    ?EnsureConnected@CApiPortClient@@AEAAJXZ; CApiPortClient::EnsureConnected(void)
0x180002c45  test    eax, eax
0x180002c47  js      short loc_180002BDA
0x180002c49  inc     cs:dword_18001F948
0x180002c4f  lea     rcx, CriticalSection; lpCriticalSection
0x180002c56  call    cs:__imp_LeaveCriticalSection
0x180002c5c  mov     r13, cs:?g_PortClient@@3VCApiPortClient@@A; CApiPortClient g_PortClient
0x180002c63  call    cs:__imp_GetProcessHeap
0x180002c69  mov     r8, rdi; dwBytes
0x180002c6c  mov     edx, 8; dwFlags
0x180002c71  mov     rcx, rax; hHeap
0x180002c74  call    cs:__imp_HeapAlloc
0x180002c7a  mov     rbx, rax
0x180002c7d  test    rax, rax
0x180002c80  jz      loc_180002D69
0x180002c86  mov     dword ptr [rax+28h], 4000001Bh
0x180002c8d  xor     r9d, r9d
0x180002c90  mov     dword ptr [rax], 3C0014h
0x180002c96  mov     r8, rax
0x180002c99  mov     dword ptr [rax+30h], 4000001Bh
0x180002ca0  mov     edx, 10000h
0x180002ca5  mov     [rsp+150h+var_118], 0
0x180002cae  mov     [rax+34h], rsi
0x180002cb2  mov     rcx, [r13+10h]
0x180002cb6  mov     [rsp+150h+var_120], 0
0x180002cbf  mov     [rsp+150h+var_128], 0; void *
0x180002cc8  mov     qword ptr [rsp+150h+var_130], 0
0x180002cd1  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180002cd7  mov     r14d, eax
0x180002cda  mov     rcx, r13; this
0x180002cdd  bts     r14d, 1Ch
0x180002ce2  mov     r9d, eax
0x180002ce5  mov     edx, r14d; int
0x180002ce8  call    ?CheckHRESULT@CPortClient@@AEAAJJ@Z; CPortClient::CheckHRESULT(long)
0x180002ced  test    r9d, r9d
0x180002cf0  js      loc_180002D96
0x180002cf6  xor     r14d, r14d
0x180002cf9  call    cs:__imp_GetProcessHeap
0x180002cff  mov     r8, rbx; lpMem
0x180002d02  xor     edx, edx; dwFlags
0x180002d04  mov     rcx, rax; hHeap
0x180002d07  call    cs:__imp_HeapFree
0x180002d0d  lea     rcx, CriticalSection; lpCriticalSection
0x180002d14  call    cs:__imp_EnterCriticalSection
0x180002d1a  add     cs:dword_18001F948, 0FFFFFFFFh
0x180002d21  jnz     short loc_180002D35
0x180002d23  mov     rax, cs:?g_PortClient@@3VCApiPortClient@@A; CApiPortClient g_PortClient
0x180002d2a  mov     ecx, [rax+8]
0x180002d2d  test    ecx, ecx
0x180002d2f  jnz     loc_180002DBD
0x180002d35  cmp     r14d, 0D0000037h
0x180002d3c  jnz     short loc_180002D4C
0x180002d3e  mov     eax, r15d
0x180002d41  dec     r15d
0x180002d44  test    eax, eax
0x180002d46  jg      loc_180002C40
0x180002d4c  mov     ecx, r14d; int
0x180002d4f  call    ?Translate@CApiPortClient@@CAJJ@Z; CApiPortClient::Translate(long)
0x180002d54  test    eax, eax
0x180002d56  jns     loc_180002BFC
0x180002d5c  mov     [rsp+150h+var_130], 91h
0x180002d64  jmp     loc_180002BE2
0x180002d69  mov     r14d, 8007000Eh
0x180002d6f  mov     [rsp+150h+var_130], 18Bh; unsigned int
0x180002d77  mov     r9d, r14d; int
0x180002d7a  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x180002d81  mov     r8d, 9; unsigned int
0x180002d87  mov     ecx, 4; unsigned int
0x180002d8c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180002d91  jmp     loc_180002D0D
0x180002d96  mov     r9d, r14d; int
0x180002d99  mov     [rsp+150h+var_130], 19Ch; unsigned int
0x180002da1  mov     r8d, 9; unsigned int
0x180002da7  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x180002dae  mov     ecx, 4; unsigned int
0x180002db3  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180002db8  jmp     loc_180002CF9
0x180002dbd  lea     rcx, ?g_PortClient@@3VCApiPortClient@@A; this
0x180002dc4  call    ?Disconnect@CApiPortClient@@AEAAXXZ; CApiPortClient::Disconnect(void)
0x180002dc9  jmp     loc_180002D35
0x180002dce  inc     cs:dword_18001F948
0x180002dd4  lea     rcx, CriticalSection; lpCriticalSection
0x180002ddb  call    cs:__imp_LeaveCriticalSection
0x180002de1  xor     eax, eax
0x180002de3  lea     rdx, [rsp+150h+var_E8]
0x180002de8  mov     [rsp+150h+var_D8], rax
0x180002ded  lea     rcx, [rsp+150h+EventTrack]
0x180002df2  mov     rax, qword ptr [rsp+150h+EventTrack.cbSize]
0x180002df7  xorps   xmm0, xmm0
0x180002dfa  movups  [rsp+150h+var_E8], xmm0
0x180002dff  mov     rax, [rax+8]
0x180002e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e08  mov     rcx, cs:?g_PortClient@@3VCApiPortClient@@A; this
0x180002e0f  lea     r9, [rsp+150h+var_E8]; struct DCOMPOSITION_DWM_LPC_EXTRA_DATA *
0x180002e14  lea     r8, [rsp+150h+var_F0]; unsigned __int64 *
0x180002e19  lea     rdx, [rbp+50h+var_D0]; void *
0x180002e1d  call    ?SendKernelSyncRequest@CPortClient@@QEAAJPEAXPEA_KPEBUDCOMPOSITION_DWM_LPC_EXTRA_DATA@@@Z; CPortClient::SendKernelSyncRequest(void *,unsigned __int64 *,DCOMPOSITION_DWM_LPC_EXTRA_DATA const *)
0x180002e22  lea     rcx, CriticalSection; lpCriticalSection
0x180002e29  mov     edi, eax
0x180002e2b  call    cs:__imp_EnterCriticalSection
0x180002e31  lea     rcx, ?g_PortClient@@3VCApiPortClient@@A; this
0x180002e38  call    ?DecrementConnectionLock@CApiPortClient@@AEAAXXZ; CApiPortClient::DecrementConnectionLock(void)
0x180002e3d  mov     ecx, edi; int
0x180002e3f  call    ?Translate@CApiPortClient@@CAJJ@Z; CApiPortClient::Translate(long)
0x180002e44  mov     r14d, eax
0x180002e47  test    eax, eax
0x180002e49  js      short loc_180002E61
  ... truncated ...
```
