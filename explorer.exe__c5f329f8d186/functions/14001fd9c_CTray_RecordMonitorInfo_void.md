# CTray::_RecordMonitorInfo(void)

- ea: `0x14001fd9c`
- end: `0x140020259`
- name: `?_RecordMonitorInfo@CTray@@AEAAXXZ`
- size: `1213`
- prototype: `void __fastcall(CTray *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400e1ea8`
- `0x14012f08c`

## callees

- `0x14001fd9c`
- `0x140020580`
- `0x14002072c`
- `0x1400207b8`
- `0x140020830`
- `0x140021280`
- `0x1400212d8`
- `0x140021430`
- `0x14010e160`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140020155`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140020190`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140020155`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140020190`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x14001fe4f`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x14001fe4f`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x14001ff16`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x14001ff16`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x14001fefe`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x14001fefe`
- `USER32!MonitorFromRect` at `0x14001feca`
- `USER32!MonitorFromRect` at `0x14001feca`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1400201c8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1400201c8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14002000c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14002022c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14002000c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14002022c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x14001fe27`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x1400200cc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x14001fe27`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x1400200cc`

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

  ProcAddress = (FARPROC)qword_14024EAA0;
  v36 = 0;
  if ( qword_14024EAA0 == -1 )
  {
    v31 = g_hinstCC;
    if ( g_hinstCC || (DelayLoadCC(), (v31 = g_hinstCC) != 0) )
      ProcAddress = GetProcAddress(v31, (LPCSTR)0x140);
    else
      ProcAddress = 0;
    qword_14024EAA0 = (__int64)ProcAddress;
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
              v10 = (__int64 (__fastcall *)(_DWORD *, _QWORD))qword_14024EA90;
              if ( qword_14024EA90 == -1 )
              {
                GetProcFromComCtl32(&qword_14024EA90, 323);
                v10 = (__int64 (__fastcall *)(_DWORD *, _QWORD))qword_14024EA90;
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
                    v16 = (FARPROC)qword_14024EA90;
                    for ( i = 0; i < v15; ++i )
                    {
                      if ( v16 == (FARPROC)-1LL )
                      {
                        if ( g_hinstCC || (DelayLoadCC(), g_hinstCC) )
                          v16 = GetProcAddress(g_hinstCC, (LPCSTR)0x143);
                        else
                          v16 = 0;
                        qword_14024EA90 = (__int64)v16;
                      }
                      if ( v16 )
                      {
                        v18 = ((__int64 (__fastcall *)(struct _DSA *, _QWORD))v16)(v8, i);
                        v16 = (FARPROC)qword_14024EA90;
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
                          v16 = (FARPROC)qword_14024EA90;
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
                        GetProcFromComCtl32(&qword_14024EA90, 323);
                        v16 = (FARPROC)qword_14024EA90;
                      }
                      if ( v16 )
                      {
                        v28 = (_QWORD *)((__int64 (__fastcall *)(__int64, _QWORD))v16)(v27, k);
                        v16 = (FARPROC)qword_14024EA90;
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
0x14001fd9c  push    rbp
0x14001fd9e  push    rbx
0x14001fd9f  push    rsi
0x14001fda0  push    rdi
0x14001fda1  push    r12
0x14001fda3  push    r13
0x14001fda5  push    r14
0x14001fda7  push    r15
0x14001fda9  lea     rbp, [rsp-1Fh]
0x14001fdae  sub     rsp, 0E8h
0x14001fdb5  mov     rax, cs:__security_cookie
0x14001fdbc  xor     rax, rsp
0x14001fdbf  mov     [rbp+57h+var_48], rax
0x14001fdc3  mov     rax, cs:qword_14024EAA0
0x14001fdca  mov     r12, rcx
0x14001fdcd  mov     [rsp+120h+var_E8], 0
0x14001fdd6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001fdda  jz      loc_1400200FE
0x14001fde0  test    rax, rax
0x14001fde3  jz      loc_14002024B
0x14001fde9  mov     edx, 2
0x14001fdee  lea     ecx, [rdx+26h]
0x14001fdf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fdf6  mov     [rsp+120h+var_E8], rax
0x14001fdfb  test    rax, rax
0x14001fdfe  jz      loc_14001FFBE
0x14001fe04  mov     rcx, [r12+428h]
0x14001fe0c  mov     rax, [rcx]
0x14001fe0f  mov     rax, [rax+40h]
0x14001fe13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fe18  mov     rcx, [r12+8]; hWnd
0x14001fe1d  lea     rdx, aLastautohideba; "LastAutoHideBarStuckMonitor"
0x14001fe24  mov     r8, rax; hData
0x14001fe27  call    cs:__imp_SetPropW
0x14001fe2e  nop     dword ptr [rax+rax+00h]
0x14001fe33  lea     rax, [rsp+120h+var_E8]
0x14001fe38  mov     [rbp+57h+dwData], r12
0x14001fe3c  lea     r9, [rbp+57h+dwData]; dwData
0x14001fe40  mov     [rbp+57h+var_C0], rax
0x14001fe44  lea     r8, ?MonitorRectsEnumProc@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x14001fe4b  xor     edx, edx; lprcClip
0x14001fe4d  xor     ecx, ecx; hdc
0x14001fe4f  call    cs:__imp_EnumDisplayMonitors
0x14001fe56  nop     dword ptr [rax+rax+00h]
0x14001fe5b  lea     r13, [r12+2B0h]
0x14001fe63  mov     rcx, [r13+0]; hdsa
0x14001fe67  test    rcx, rcx
0x14001fe6a  jz      loc_14001FFB5
0x14001fe70  call    DSA_Clone
0x14001fe75  mov     rdi, [rsp+120h+var_E8]
0x14001fe7a  mov     rbx, rax
0x14001fe7d  mov     [rbp+57h+var_D0], rax
0x14001fe81  test    rdi, rdi
0x14001fe84  jz      loc_14001FF91
0x14001fe8a  mov     eax, [rdi]
0x14001fe8c  xor     ecx, ecx
0x14001fe8e  mov     [rsp+120h+var_E0], eax
0x14001fe92  mov     [rsp+120h+var_F0], ecx
0x14001fe96  test    eax, eax
0x14001fe98  jz      loc_14001FF91
0x14001fe9e  mov     rax, cs:qword_14024EA90
0x14001fea5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001fea9  jz      loc_140020163
0x14001feaf  test    rax, rax
0x14001feb2  jz      loc_1400200F6
0x14001feb8  mov     edx, ecx
0x14001feba  mov     rcx, rdi
0x14001febd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fec2  mov     r13, rax
0x14001fec5  xor     edx, edx; dwFlags
0x14001fec7  mov     rcx, r13; lprc
0x14001feca  call    cs:__imp_MonitorFromRect
0x14001fed1  nop     dword ptr [rax+rax+00h]
0x14001fed6  test    rax, rax
0x14001fed9  jz      loc_14001FF75
0x14001fedf  lea     rcx, [r12+38h]; this
0x14001fee4  mov     [r13+20h], rax
0x14001fee8  mov     rdx, rax; HMONITOR
0x14001feeb  call    ?GetTrayMonitorInfo@CTray@@UEAAPEAUTRAYMONITORINFO@TrayCommon@@PEAUHMONITOR__@@@Z; CTray::GetTrayMonitorInfo(HMONITOR__ *)
0x14001fef0  mov     r14, rax
0x14001fef3  test    rax, rax
0x14001fef6  jz      short loc_14001FF75
0x14001fef8  mov     rdx, rax; lprc2
0x14001fefb  mov     rcx, r13; lprc1
0x14001fefe  call    cs:__imp_EqualRect
0x14001ff05  nop     dword ptr [rax+rax+00h]
0x14001ff0a  test    eax, eax
0x14001ff0c  jz      short loc_14001FF75
0x14001ff0e  lea     rdx, [r14+10h]; lprcSrc
0x14001ff12  lea     rcx, [r13+10h]; lprcDst
0x14001ff16  call    cs:__imp_CopyRect
0x14001ff1d  nop     dword ptr [rax+rax+00h]
0x14001ff22  test    rbx, rbx
0x14001ff25  jz      loc_1400201BB
0x14001ff2b  mov     r15d, [rbx]
0x14001ff2e  mov     rax, cs:qword_14024EA90
0x14001ff35  xor     esi, esi
0x14001ff37  cmp     esi, r15d
0x14001ff3a  jnb     loc_14002002E
0x14001ff40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001ff44  jz      loc_140020129
0x14001ff4a  test    rax, rax
0x14001ff4d  jz      loc_1400200EB
0x14001ff53  mov     edx, esi
0x14001ff55  mov     rcx, rbx
0x14001ff58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ff5d  mov     rdi, rax
0x14001ff60  mov     rax, cs:qword_14024EA90
0x14001ff67  mov     rcx, [rdi+20h]
0x14001ff6b  cmp     rcx, [r14+20h]
0x14001ff6f  jz      short loc_14001FFDF
0x14001ff71  inc     esi
0x14001ff73  jmp     short loc_14001FF37
0x14001ff75  mov     ecx, [rsp+120h+var_F0]
0x14001ff79  inc     ecx
0x14001ff7b  mov     [rsp+120h+var_F0], ecx
0x14001ff7f  cmp     ecx, [rsp+120h+var_E0]
0x14001ff83  jb      loc_1400201E6
0x14001ff89  lea     r13, [r12+2B0h]
0x14001ff91  test    rbx, rbx
0x14001ff94  jz      short loc_14001FFA4
0x14001ff96  mov     r14d, [rbx]
0x14001ff99  xor     edi, edi
0x14001ff9b  test    r14d, r14d
0x14001ff9e  jnz     loc_1400201F0
0x14001ffa4  lea     rcx, [rbp+57h+var_D0]
0x14001ffa8  call    ?Destroy@?$CDSA_Base@UTRAYMONITORINFO@TrayCommon@@@@QEAAHXZ; CDSA_Base<TrayCommon::TRAYMONITORINFO>::Destroy(void)
0x14001ffad  mov     rcx, r13
0x14001ffb0  call    ?Destroy@?$CDSA_Base@UTRAYMONITORINFO@TrayCommon@@@@QEAAHXZ; CDSA_Base<TrayCommon::TRAYMONITORINFO>::Destroy(void)
0x14001ffb5  mov     rax, [rsp+120h+var_E8]
0x14001ffba  mov     [r13+0], rax
0x14001ffbe  mov     rcx, [rbp+57h+var_48]
0x14001ffc2  xor     rcx, rsp; StackCookie
0x14001ffc5  call    __security_check_cookie
0x14001ffca  add     rsp, 0E8h
0x14001ffd1  pop     r15
0x14001ffd3  pop     r14
0x14001ffd5  pop     r13
0x14001ffd7  pop     r12
0x14001ffd9  pop     rdi
0x14001ffda  pop     rsi
0x14001ffdb  pop     rbx
0x14001ffdc  pop     rbp
0x14001ffdd  retn
0x14001ffdf  test    rcx, rcx
0x14001ffe2  jz      short loc_14002002E
0x14001ffe4  xor     esi, esi
0x14001ffe6  mov     r9d, [rdi+20h]
0x14001ffea  lea     r8, aWindowonedge08; "WindowOnEdge:%08x:%1u"
0x14001fff1  mov     edx, 19h; unsigned __int64
0x14001fff6  mov     [rsp+120h+var_100], esi
0x14001fffa  lea     rcx, [rbp+57h+String]; unsigned __int16 *
0x14001fffe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140020003  mov     rcx, [r12+8]; hWnd
0x140020008  lea     rdx, [rbp+57h+String]; lpString
0x14002000c  call    cs:__imp_RemovePropW
0x140020013  nop     dword ptr [rax+rax+00h]
0x140020018  inc     esi
0x14002001a  cmp     esi, 4
0x14002001d  jl      short loc_14001FFE6
0x14002001f  mov     qword ptr [rdi+20h], 0
0x140020027  mov     rax, cs:qword_14024EA90
0x14002002e  mov     rcx, [r13+20h]
0x140020032  xor     r15d, r15d
0x140020035  mov     [rsp+120h+var_D8], rcx
0x14002003a  mov     rcx, [r12+1C0h]
0x140020042  test    rcx, rcx
0x140020045  jz      loc_1400200E4
0x14002004b  mov     esi, [rcx]
0x14002004d  xor     edi, edi
0x14002004f  cmp     edi, esi
0x140020051  jge     short loc_140020093
0x140020053  mov     r14, [r12+1C0h]
0x14002005b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002005f  jz      loc_14002019E
0x140020065  test    rax, rax
0x140020068  jz      loc_1400200F2
0x14002006e  mov     edx, edi
0x140020070  mov     rcx, r14
0x140020073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020078  mov     rcx, rax
0x14002007b  mov     rax, cs:qword_14024EA90
0x140020082  mov     rdx, [rsp+120h+var_D8]
0x140020087  cmp     [rcx], rdx
0x14002008a  jz      short loc_140020090
0x14002008c  inc     edi
0x14002008e  jmp     short loc_14002004F
0x140020090  mov     r15, rcx
0x140020093  xor     edi, edi
0x140020095  mov     r9d, [r13+20h]
0x140020099  lea     r8, aWindowonedge08; "WindowOnEdge:%08x:%1u"
0x1400200a0  mov     r14d, 1
0x1400200a6  mov     [rsp+120h+var_100], edi
0x1400200aa  lea     rcx, [rbp+57h+var_B8]; unsigned __int16 *
0x1400200ae  lea     edx, [r14+18h]; unsigned __int64
0x1400200b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400200b7  test    r15, r15
0x1400200ba  jnz     loc_1400201C3
0x1400200c0  mov     rcx, [r12+8]; hWnd
0x1400200c5  lea     rdx, [rbp+57h+var_B8]; lpString
0x1400200c9  mov     r8, r14; hData
0x1400200cc  call    cs:__imp_SetPropW
0x1400200d3  nop     dword ptr [rax+rax+00h]
0x1400200d8  inc     edi
0x1400200da  cmp     edi, 4
0x1400200dd  jl      short loc_140020095
0x1400200df  jmp     loc_14001FF75
0x1400200e4  xor     esi, esi
0x1400200e6  jmp     loc_14002004D
0x1400200eb  xor     edi, edi
0x1400200ed  jmp     loc_14001FF67
0x1400200f2  xor     ecx, ecx
0x1400200f4  jmp     short loc_140020082
0x1400200f6  xor     r13d, r13d
0x1400200f9  jmp     loc_14001FEC5
0x1400200fe  mov     rcx, cs:g_hinstCC; hModule
0x140020105  test    rcx, rcx
0x140020108  jnz     short loc_140020150
0x14002010a  call    DelayLoadCC
0x14002010f  mov     rcx, cs:g_hinstCC
0x140020116  test    rcx, rcx
0x140020119  jnz     short loc_140020150
0x14002011b  xor     eax, eax
0x14002011d  mov     cs:qword_14024EAA0, rax
0x140020124  jmp     loc_14001FDE0
0x140020129  cmp     cs:g_hinstCC, 0
0x140020131  jnz     short loc_140020184
0x140020133  call    DelayLoadCC
0x140020138  cmp     cs:g_hinstCC, 0
0x140020140  jnz     short loc_140020184
0x140020142  xor     eax, eax
0x140020144  mov     cs:qword_14024EA90, rax
0x14002014b  jmp     loc_14001FF4A
0x140020150  mov     edx, 140h; lpProcName
0x140020155  call    cs:__imp_GetProcAddress
0x14002015c  nop     dword ptr [rax+rax+00h]
0x140020161  jmp     short loc_14002011D
0x140020163  mov     edx, 143h
0x140020168  lea     rcx, qword_14024EA90
0x14002016f  call    _GetProcFromComCtl32
0x140020174  mov     rax, cs:qword_14024EA90
0x14002017b  mov     ecx, [rsp+120h+var_F0]
0x14002017f  jmp     loc_14001FEAF
0x140020184  mov     rcx, cs:g_hinstCC; hModule
0x14002018b  mov     edx, 143h; lpProcName
0x140020190  call    cs:__imp_GetProcAddress
0x140020197  nop     dword ptr [rax+rax+00h]
0x14002019c  jmp     short loc_140020144
0x14002019e  mov     edx, 143h
0x1400201a3  lea     rcx, qword_14024EA90
0x1400201aa  call    _GetProcFromComCtl32
0x1400201af  mov     rax, cs:qword_14024EA90
0x1400201b6  jmp     loc_140020065
0x1400201bb  xor     r15d, r15d
0x1400201be  jmp     loc_14001FF2E
0x1400201c3  mov     rcx, [r15+rdi*8+8]; hWnd
0x1400201c8  call    cs:__imp_IsWindow
0x1400201cf  nop     dword ptr [rax+rax+00h]
0x1400201d4  test    eax, eax
0x1400201d6  jz      loc_1400200C0
0x1400201dc  mov     r14, [r15+rdi*8+8]
0x1400201e1  jmp     loc_1400200C0
0x1400201e6  mov     rdi, [rsp+120h+var_E8]
0x1400201eb  jmp     loc_14001FE9E
0x1400201f0  mov     edx, edi; i
0x1400201f2  mov     rcx, rbx; hdsa
0x1400201f5  call    DSA_GetItemPtr
0x1400201fa  mov     r15, rax
0x1400201fd  cmp     qword ptr [rax+20h], 0
0x140020202  jz      short loc_14002023F
0x140020204  xor     esi, esi
0x140020206  mov     r9d, [r15+20h]
0x14002020a  lea     r8, aWindowonedge08; "WindowOnEdge:%08x:%1u"
0x140020211  mov     edx, 19h; unsigned __int64
0x140020216  mov     [rsp+120h+var_100], esi
0x14002021a  lea     rcx, [rbp+57h+var_B8]; unsigned __int16 *
0x14002021e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140020223  mov     rcx, [r12+8]; hWnd
0x140020228  lea     rdx, [rbp+57h+var_B8]; lpString
0x14002022c  call    cs:__imp_RemovePropW
0x140020233  nop     dword ptr [rax+rax+00h]
0x140020238  inc     esi
0x14002023a  cmp     esi, 4
0x14002023d  jl      short loc_140020206
0x14002023f  inc     edi
0x140020241  cmp     edi, r14d
0x140020244  jb      short loc_1400201F0
0x140020246  jmp     loc_14001FFA4
0x14002024b  mov     [rsp+120h+var_E8], 0
0x140020254  jmp     loc_14001FFBE
```
