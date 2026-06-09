# CTray::_RecordMonitorInfo(void)

- ea: `0x140015168`
- end: `0x1400155de`
- name: `?_RecordMonitorInfo@CTray@@AEAAXXZ`
- size: `1142`
- prototype: `void __fastcall(CTray *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400da6b8`
- `0x140123a38`

## callees

- `0x140015168`
- `0x1400158a4`
- `0x140015a38`
- `0x140015abc`
- `0x140015b30`
- `0x140023fe0`
- `0x140024058`
- `0x1400240a8`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400154f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140015527`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400154f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140015527`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x140015215`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x140015215`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1400152ca`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1400152ca`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1400152b8`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1400152b8`
- `USER32!MonitorFromRect` at `0x14001528a`
- `USER32!MonitorFromRect` at `0x14001528a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x140015559`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x140015559`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x1400153b9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x1400155b7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x1400153b9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x1400155b7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x1400151f3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x14001546f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x1400151f3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x14001546f`

## pseudocode

```c
void __fastcall CTray::_RecordMonitorInfo(CTray *this)
{
  FARPROC ProcAddress; // rax
  void *v3; // rax
  _QWORD *v4; // r13
  struct _DSA *v5; // rcx
  HDSA v6; // rax
  _DWORD *v7; // rdi
  struct _DSA *v8; // rbx
  unsigned int v9; // ecx
  __int64 (__fastcall *v10)(_DWORD *, _QWORD); // rax
  __int64 v11; // r13
  HMONITOR v12; // rax
  const RECT *TrayMonitorInfo; // rax
  const RECT *v14; // r14
  unsigned int v15; // r15d
  FARPROC v16; // rax
  unsigned int i; // esi
  __int64 v18; // rdi
  __int64 v19; // rcx
  unsigned int v20; // r14d
  unsigned int m; // edi
  int j; // esi
  _QWORD *v23; // r15
  int *v24; // rcx
  int v25; // esi
  unsigned int k; // edi
  __int64 v27; // r14
  _QWORD *v28; // rcx
  __int64 v29; // rdi
  __int64 v30; // r14
  HMODULE v31; // rcx
  _QWORD *ItemPtr; // r15
  int n; // esi
  __int64 v34; // [rsp+20h] [rbp-A9h]
  unsigned int v35; // [rsp+30h] [rbp-99h]
  _DWORD *v36; // [rsp+38h] [rbp-91h] BYREF
  unsigned int v37; // [rsp+40h] [rbp-89h]
  __int64 v38; // [rsp+48h] [rbp-81h]
  HDSA v39; // [rsp+50h] [rbp-79h] BYREF
  LPARAM dwData[2]; // [rsp+58h] [rbp-71h] BYREF
  WCHAR v41[28]; // [rsp+68h] [rbp-61h] BYREF
  WCHAR String[28]; // [rsp+A0h] [rbp-29h] BYREF

  ProcAddress = (FARPROC)qword_140252998;
  v36 = 0;
  if ( qword_140252998 == -1 )
  {
    v31 = g_hinstCC;
    if ( g_hinstCC || (DelayLoadCC(), (v31 = g_hinstCC) != 0) )
      ProcAddress = GetProcAddress(v31, (LPCSTR)0x140);
    else
      ProcAddress = 0;
    qword_140252998 = (__int64)ProcAddress;
  }
  if ( ProcAddress )
  {
    v36 = (_DWORD *)((__int64 (__fastcall *)(__int64))ProcAddress)(40);
    if ( v36 )
    {
      v3 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 64LL))(*((_QWORD *)this + 133));
      SetPropW(*((HWND *)this + 1), L"LastAutoHideBarStuckMonitor", v3);
      dwData[0] = (LPARAM)this;
      dwData[1] = (LPARAM)&v36;
      EnumDisplayMonitors(0, 0, MonitorRectsEnumProc, (LPARAM)dwData);
      v4 = (_QWORD *)((char *)this + 688);
      v5 = (struct _DSA *)*((_QWORD *)this + 86);
      if ( v5 )
      {
        v6 = DSA_Clone(v5);
        v7 = v36;
        v8 = v6;
        v39 = v6;
        if ( v36 )
        {
          v9 = 0;
          v37 = *v36;
          v35 = 0;
          if ( v37 )
          {
            while ( 1 )
            {
              v10 = (__int64 (__fastcall *)(_DWORD *, _QWORD))qword_140252990;
              if ( qword_140252990 == -1 )
              {
                GetProcFromComCtl32(&qword_140252990, 323);
                v10 = (__int64 (__fastcall *)(_DWORD *, _QWORD))qword_140252990;
                v9 = v35;
              }
              if ( v10 )
                v11 = v10(v7, v9);
              else
                v11 = 0;
              v12 = MonitorFromRect((LPCRECT)v11, 0);
              if ( v12 )
              {
                *(_QWORD *)(v11 + 32) = v12;
                TrayMonitorInfo = (const RECT *)CTray::GetTrayMonitorInfo((CTray *)((char *)this + 56), v12);
                v14 = TrayMonitorInfo;
                if ( TrayMonitorInfo )
                {
                  if ( EqualRect((const RECT *)v11, TrayMonitorInfo) )
                  {
                    CopyRect((LPRECT)(v11 + 16), v14 + 1);
                    if ( v8 )
                      v15 = *(_DWORD *)v8;
                    else
                      v15 = 0;
                    v16 = (FARPROC)qword_140252990;
                    for ( i = 0; i < v15; ++i )
                    {
                      if ( v16 == (FARPROC)-1LL )
                      {
                        if ( g_hinstCC || (DelayLoadCC(), g_hinstCC) )
                          v16 = GetProcAddress(g_hinstCC, (LPCSTR)0x143);
                        else
                          v16 = 0;
                        qword_140252990 = (__int64)v16;
                      }
                      if ( v16 )
                      {
                        v18 = ((__int64 (__fastcall *)(struct _DSA *, _QWORD))v16)(v8, i);
                        v16 = (FARPROC)qword_140252990;
                      }
                      else
                      {
                        v18 = 0;
                      }
                      v19 = *(_QWORD *)(v18 + 32);
                      if ( v19 == *(_QWORD *)&v14[2].left )
                      {
                        if ( v19 )
                        {
                          for ( j = 0; j < 4; ++j )
                          {
                            LODWORD(v34) = j;
                            StringCchPrintfW(String, 0x19u, L"WindowOnEdge:%08x:%1u", *(unsigned int *)(v18 + 32), v34);
                            RemovePropW(*((HWND *)this + 1), String);
                          }
                          *(_QWORD *)(v18 + 32) = 0;
                          v16 = (FARPROC)qword_140252990;
                        }
                        break;
                      }
                    }
                    v23 = 0;
                    v38 = *(_QWORD *)(v11 + 32);
                    v24 = (int *)*((_QWORD *)this + 56);
                    if ( v24 )
                      v25 = *v24;
                    else
                      v25 = 0;
                    for ( k = 0; (int)k < v25; ++k )
                    {
                      v27 = *((_QWORD *)this + 56);
                      if ( v16 == (FARPROC)-1LL )
                      {
                        GetProcFromComCtl32(&qword_140252990, 323);
                        v16 = (FARPROC)qword_140252990;
                      }
                      if ( v16 )
                      {
                        v28 = (_QWORD *)((__int64 (__fastcall *)(__int64, _QWORD))v16)(v27, k);
                        v16 = (FARPROC)qword_140252990;
                      }
                      else
                      {
                        v28 = 0;
                      }
                      if ( *v28 == v38 )
                      {
                        v23 = v28;
                        break;
                      }
                    }
                    v29 = 0;
                    do
                    {
                      v30 = 1;
                      LODWORD(v34) = v29;
                      StringCchPrintfW(v41, 0x19u, L"WindowOnEdge:%08x:%1u", *(unsigned int *)(v11 + 32), v34);
                      if ( v23 && IsWindow((HWND)v23[v29 + 1]) )
                        v30 = v23[v29 + 1];
                      SetPropW(*((HWND *)this + 1), v41, (HANDLE)v30);
                      v29 = (unsigned int)(v29 + 1);
                    }
                    while ( (int)v29 < 4 );
                  }
                }
              }
              v9 = v35 + 1;
              v35 = v9;
              if ( v9 >= v37 )
                break;
              v7 = v36;
            }
            v4 = (_QWORD *)((char *)this + 688);
          }
        }
        if ( v8 )
        {
          v20 = *(_DWORD *)v8;
          for ( m = 0; m < v20; ++m )
          {
            ItemPtr = DSA_GetItemPtr(v8, m);
            if ( ItemPtr[4] )
            {
              for ( n = 0; n < 4; ++n )
              {
                LODWORD(v34) = n;
                StringCchPrintfW(v41, 0x19u, L"WindowOnEdge:%08x:%1u", *((unsigned int *)ItemPtr + 8), v34);
                RemovePropW(*((HWND *)this + 1), v41);
              }
            }
          }
        }
        CDSA_Base<TrayCommon::TRAYMONITORINFO>::Destroy(&v39);
        CDSA_Base<TrayCommon::TRAYMONITORINFO>::Destroy(v4);
      }
      *v4 = v36;
    }
  }
}

```

## disassembly

```asm
0x140015168  push    rbp
0x14001516a  push    rbx
0x14001516b  push    rsi
0x14001516c  push    rdi
0x14001516d  push    r12
0x14001516f  push    r13
0x140015171  push    r14
0x140015173  push    r15
0x140015175  lea     rbp, [rsp-1Fh]
0x14001517a  sub     rsp, 0E8h
0x140015181  mov     rax, cs:__security_cookie
0x140015188  xor     rax, rsp
0x14001518b  mov     [rbp+57h+var_48], rax
0x14001518f  mov     rax, cs:qword_140252998
0x140015196  mov     r12, rcx
0x140015199  mov     [rsp+120h+var_E8], 0
0x1400151a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400151a6  jz      loc_14001549B
0x1400151ac  test    rax, rax
0x1400151af  jz      loc_1400155D0
0x1400151b5  mov     edx, 2
0x1400151ba  lea     ecx, [rdx+26h]
0x1400151bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151c2  mov     [rsp+120h+var_E8], rax
0x1400151c7  test    rax, rax
0x1400151ca  jz      loc_14001536C
0x1400151d0  mov     rcx, [r12+428h]
0x1400151d8  mov     rax, [rcx]
0x1400151db  mov     rax, [rax+40h]
0x1400151df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151e4  mov     rcx, [r12+8]; hWnd
0x1400151e9  lea     rdx, String; "LastAutoHideBarStuckMonitor"
0x1400151f0  mov     r8, rax; hData
0x1400151f3  call    cs:__imp_SetPropW
0x1400151f9  lea     rax, [rsp+120h+var_E8]
0x1400151fe  mov     [rbp+57h+dwData], r12
0x140015202  lea     r9, [rbp+57h+dwData]; dwData
0x140015206  mov     [rbp+57h+var_C0], rax
0x14001520a  lea     r8, ?MonitorRectsEnumProc@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x140015211  xor     edx, edx; lprcClip
0x140015213  xor     ecx, ecx; hdc
0x140015215  call    cs:__imp_EnumDisplayMonitors
0x14001521b  lea     r13, [r12+2B0h]
0x140015223  mov     rcx, [r13+0]; hdsa
0x140015227  test    rcx, rcx
0x14001522a  jz      loc_140015363
0x140015230  call    DSA_Clone
0x140015235  mov     rdi, [rsp+120h+var_E8]
0x14001523a  mov     rbx, rax
0x14001523d  mov     [rbp+57h+var_D0], rax
0x140015241  test    rdi, rdi
0x140015244  jz      loc_14001533F
0x14001524a  mov     eax, [rdi]
0x14001524c  xor     ecx, ecx
0x14001524e  mov     [rsp+120h+var_E0], eax
0x140015252  mov     [rsp+120h+var_F0], ecx
0x140015256  test    eax, eax
0x140015258  jz      loc_14001533F
0x14001525e  mov     rax, cs:qword_140252990
0x140015265  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140015269  jz      loc_1400154FA
0x14001526f  test    rax, rax
0x140015272  jz      loc_140015493
0x140015278  mov     edx, ecx
0x14001527a  mov     rcx, rdi
0x14001527d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015282  mov     r13, rax
0x140015285  xor     edx, edx; dwFlags
0x140015287  mov     rcx, r13; lprc
0x14001528a  call    cs:__imp_MonitorFromRect
0x140015290  test    rax, rax
0x140015293  jz      loc_140015323
0x140015299  lea     rcx, [r12+38h]; this
0x14001529e  mov     [r13+20h], rax
0x1400152a2  mov     rdx, rax; HMONITOR
0x1400152a5  call    ?GetTrayMonitorInfo@CTray@@UEAAPEAUTRAYMONITORINFO@TrayCommon@@PEAUHMONITOR__@@@Z; CTray::GetTrayMonitorInfo(HMONITOR__ *)
0x1400152aa  mov     r14, rax
0x1400152ad  test    rax, rax
0x1400152b0  jz      short loc_140015323
0x1400152b2  mov     rdx, rax; lprc2
0x1400152b5  mov     rcx, r13; lprc1
0x1400152b8  call    cs:__imp_EqualRect
0x1400152be  test    eax, eax
0x1400152c0  jz      short loc_140015323
0x1400152c2  lea     rdx, [r14+10h]; lprcSrc
0x1400152c6  lea     rcx, [r13+10h]; lprcDst
0x1400152ca  call    cs:__imp_CopyRect
0x1400152d0  test    rbx, rbx
0x1400152d3  jz      loc_14001554C
0x1400152d9  mov     r15d, [rbx]
0x1400152dc  mov     rax, cs:qword_140252990
0x1400152e3  xor     esi, esi
0x1400152e5  cmp     esi, r15d
0x1400152e8  jnb     loc_1400153D5
0x1400152ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400152f2  jz      loc_1400154C6
0x1400152f8  test    rax, rax
0x1400152fb  jz      loc_140015488
0x140015301  mov     edx, esi
0x140015303  mov     rcx, rbx
0x140015306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001530b  mov     rdi, rax
0x14001530e  mov     rax, cs:qword_140252990
0x140015315  mov     rcx, [rdi+20h]
0x140015319  cmp     rcx, [r14+20h]
0x14001531d  jz      short loc_14001538C
0x14001531f  inc     esi
0x140015321  jmp     short loc_1400152E5
0x140015323  mov     ecx, [rsp+120h+var_F0]
0x140015327  inc     ecx
0x140015329  mov     [rsp+120h+var_F0], ecx
0x14001532d  cmp     ecx, [rsp+120h+var_E0]
0x140015331  jb      loc_140015571
0x140015337  lea     r13, [r12+2B0h]
0x14001533f  test    rbx, rbx
0x140015342  jz      short loc_140015352
0x140015344  mov     r14d, [rbx]
0x140015347  xor     edi, edi
0x140015349  test    r14d, r14d
0x14001534c  jnz     loc_14001557B
0x140015352  lea     rcx, [rbp+57h+var_D0]
0x140015356  call    ?Destroy@?$CDSA_Base@UTRAYMONITORINFO@TrayCommon@@@@QEAAHXZ; CDSA_Base<TrayCommon::TRAYMONITORINFO>::Destroy(void)
0x14001535b  mov     rcx, r13
0x14001535e  call    ?Destroy@?$CDSA_Base@UTRAYMONITORINFO@TrayCommon@@@@QEAAHXZ; CDSA_Base<TrayCommon::TRAYMONITORINFO>::Destroy(void)
0x140015363  mov     rax, [rsp+120h+var_E8]
0x140015368  mov     [r13+0], rax
0x14001536c  mov     rcx, [rbp+57h+var_48]
0x140015370  xor     rcx, rsp; StackCookie
0x140015373  call    __security_check_cookie
0x140015378  add     rsp, 0E8h
0x14001537f  pop     r15
0x140015381  pop     r14
0x140015383  pop     r13
0x140015385  pop     r12
0x140015387  pop     rdi
0x140015388  pop     rsi
0x140015389  pop     rbx
0x14001538a  pop     rbp
0x14001538b  retn
0x14001538c  test    rcx, rcx
0x14001538f  jz      short loc_1400153D5
0x140015391  xor     esi, esi
0x140015393  mov     r9d, [rdi+20h]
0x140015397  lea     r8, aWindowonedge08; "WindowOnEdge:%08x:%1u"
0x14001539e  mov     edx, 19h; unsigned __int64
0x1400153a3  mov     [rsp+120h+var_100], esi
0x1400153a7  lea     rcx, [rbp+57h+String]; unsigned __int16 *
0x1400153ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400153b0  mov     rcx, [r12+8]; hWnd
0x1400153b5  lea     rdx, [rbp+57h+String]; lpString
0x1400153b9  call    cs:__imp_RemovePropW
0x1400153bf  inc     esi
0x1400153c1  cmp     esi, 4
0x1400153c4  jl      short loc_140015393
0x1400153c6  mov     qword ptr [rdi+20h], 0
0x1400153ce  mov     rax, cs:qword_140252990
0x1400153d5  mov     rcx, [r13+20h]
0x1400153d9  xor     r15d, r15d
0x1400153dc  mov     [rsp+120h+var_D8], rcx
0x1400153e1  mov     rcx, [r12+1C0h]
0x1400153e9  test    rcx, rcx
0x1400153ec  jz      loc_140015481
0x1400153f2  mov     esi, [rcx]
0x1400153f4  xor     edi, edi
0x1400153f6  cmp     edi, esi
0x1400153f8  jge     short loc_140015436
0x1400153fa  mov     r14, [r12+1C0h]
0x140015402  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140015406  jz      loc_14001552F
0x14001540c  test    rax, rax
0x14001540f  jz      short loc_14001548F
0x140015411  mov     edx, edi
0x140015413  mov     rcx, r14
0x140015416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001541b  mov     rcx, rax
0x14001541e  mov     rax, cs:qword_140252990
0x140015425  mov     rdx, [rsp+120h+var_D8]
0x14001542a  cmp     [rcx], rdx
0x14001542d  jz      short loc_140015433
0x14001542f  inc     edi
0x140015431  jmp     short loc_1400153F6
0x140015433  mov     r15, rcx
0x140015436  xor     edi, edi
0x140015438  mov     r9d, [r13+20h]
0x14001543c  lea     r8, aWindowonedge08; "WindowOnEdge:%08x:%1u"
0x140015443  mov     r14d, 1
0x140015449  mov     [rsp+120h+var_100], edi
0x14001544d  lea     rcx, [rbp+57h+var_B8]; unsigned __int16 *
0x140015451  lea     edx, [r14+18h]; unsigned __int64
0x140015455  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001545a  test    r15, r15
0x14001545d  jnz     loc_140015554
0x140015463  mov     rcx, [r12+8]; hWnd
0x140015468  lea     rdx, [rbp+57h+var_B8]; lpString
0x14001546c  mov     r8, r14; hData
0x14001546f  call    cs:__imp_SetPropW
0x140015475  inc     edi
0x140015477  cmp     edi, 4
0x14001547a  jl      short loc_140015438
0x14001547c  jmp     loc_140015323
0x140015481  xor     esi, esi
0x140015483  jmp     loc_1400153F4
0x140015488  xor     edi, edi
0x14001548a  jmp     loc_140015315
0x14001548f  xor     ecx, ecx
0x140015491  jmp     short loc_140015425
0x140015493  xor     r13d, r13d
0x140015496  jmp     loc_140015285
0x14001549b  mov     rcx, cs:g_hinstCC; hModule
0x1400154a2  test    rcx, rcx
0x1400154a5  jnz     short loc_1400154ED
0x1400154a7  call    DelayLoadCC
0x1400154ac  mov     rcx, cs:g_hinstCC
0x1400154b3  test    rcx, rcx
0x1400154b6  jnz     short loc_1400154ED
0x1400154b8  xor     eax, eax
0x1400154ba  mov     cs:qword_140252998, rax
0x1400154c1  jmp     loc_1400151AC
0x1400154c6  cmp     cs:g_hinstCC, 0
0x1400154ce  jnz     short loc_14001551B
0x1400154d0  call    DelayLoadCC
0x1400154d5  cmp     cs:g_hinstCC, 0
0x1400154dd  jnz     short loc_14001551B
0x1400154df  xor     eax, eax
0x1400154e1  mov     cs:qword_140252990, rax
0x1400154e8  jmp     loc_1400152F8
0x1400154ed  mov     edx, 140h; lpProcName
0x1400154f2  call    cs:__imp_GetProcAddress
0x1400154f8  jmp     short loc_1400154BA
0x1400154fa  mov     edx, 143h
0x1400154ff  lea     rcx, qword_140252990
0x140015506  call    _GetProcFromComCtl32
0x14001550b  mov     rax, cs:qword_140252990
0x140015512  mov     ecx, [rsp+120h+var_F0]
0x140015516  jmp     loc_14001526F
0x14001551b  mov     rcx, cs:g_hinstCC; hModule
0x140015522  mov     edx, 143h; lpProcName
0x140015527  call    cs:__imp_GetProcAddress
0x14001552d  jmp     short loc_1400154E1
0x14001552f  mov     edx, 143h
0x140015534  lea     rcx, qword_140252990
0x14001553b  call    _GetProcFromComCtl32
0x140015540  mov     rax, cs:qword_140252990
0x140015547  jmp     loc_14001540C
0x14001554c  xor     r15d, r15d
0x14001554f  jmp     loc_1400152DC
0x140015554  mov     rcx, [r15+rdi*8+8]; hWnd
0x140015559  call    cs:__imp_IsWindow
0x14001555f  test    eax, eax
0x140015561  jz      loc_140015463
0x140015567  mov     r14, [r15+rdi*8+8]
0x14001556c  jmp     loc_140015463
0x140015571  mov     rdi, [rsp+120h+var_E8]
0x140015576  jmp     loc_14001525E
0x14001557b  mov     edx, edi; i
0x14001557d  mov     rcx, rbx; hdsa
0x140015580  call    DSA_GetItemPtr
0x140015585  mov     r15, rax
0x140015588  cmp     qword ptr [rax+20h], 0
0x14001558d  jz      short loc_1400155C4
0x14001558f  xor     esi, esi
0x140015591  mov     r9d, [r15+20h]
0x140015595  lea     r8, aWindowonedge08; "WindowOnEdge:%08x:%1u"
0x14001559c  mov     edx, 19h; unsigned __int64
0x1400155a1  mov     [rsp+120h+var_100], esi
0x1400155a5  lea     rcx, [rbp+57h+var_B8]; unsigned __int16 *
0x1400155a9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400155ae  mov     rcx, [r12+8]; hWnd
0x1400155b3  lea     rdx, [rbp+57h+var_B8]; lpString
0x1400155b7  call    cs:__imp_RemovePropW
0x1400155bd  inc     esi
0x1400155bf  cmp     esi, 4
0x1400155c2  jl      short loc_140015591
0x1400155c4  inc     edi
0x1400155c6  cmp     edi, r14d
0x1400155c9  jb      short loc_14001557B
0x1400155cb  jmp     loc_140015352
0x1400155d0  mov     [rsp+120h+var_E8], 0
0x1400155d9  jmp     loc_14001536C
```
