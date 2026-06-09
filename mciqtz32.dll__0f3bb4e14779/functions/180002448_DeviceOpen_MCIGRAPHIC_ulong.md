# DeviceOpen(_MCIGRAPHIC *,ulong)

- ea: `0x180002448`
- end: `0x180002af8`
- name: `?DeviceOpen@@YAKPEAU_MCIGRAPHIC@@K@Z`
- size: `1712`
- prototype: `unsigned int __fastcall(LPVOID *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800050c0`

## callees

- `0x180001d22`
- `0x180001e7c`
- `0x180002448`
- `0x180003210`
- `0x180003bc8`
- `0x180006494`
- `0x180007010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18000279b`
- `KERNEL32!CreateThread` at `0x18000279b`
- `KERNEL32!CreateEventW` at `0x18000270a`
- `KERNEL32!CreateEventW` at `0x180002736`
- `KERNEL32!CreateEventW` at `0x18000270a`
- `KERNEL32!CreateEventW` at `0x180002736`
- `USER32!LoadCursorW` at `0x18000297d`
- `USER32!LoadCursorW` at `0x18000297d`
- `USER32!CreateWindowExW` at `0x180002a79`
- `USER32!CreateWindowExW` at `0x180002a79`
- `USER32!GetSystemMetrics` at `0x1800029c0`
- `USER32!GetSystemMetrics` at `0x1800029ce`
- `USER32!GetSystemMetrics` at `0x1800029c0`
- `USER32!GetSystemMetrics` at `0x1800029ce`
- `USER32!SetWindowTextW` at `0x180002ad2`
- `USER32!SetWindowTextW` at `0x180002ad2`
- `USER32!RegisterClassW` at `0x1800029b8`
- `USER32!RegisterClassW` at `0x1800029b8`
- `ole32!CoCreateInstance` at `0x180002482`
- `ole32!CoCreateInstance` at `0x180002482`
- `ole32!CoTaskMemFree` at `0x1800028e2`
- `ole32!CoTaskMemFree` at `0x1800028e2`

## pseudocode

```c
unsigned int __fastcall DeviceOpen(LPVOID *a1, int a2)
{
  int v2; // eax
  HANDLE v4; // rax
  BOOL v5; // ecx
  _QWORD **v6; // rax
  int v7; // esi
  int v8; // edi
  unsigned int i; // r14d
  void *v10; // rbx
  HCURSOR CursorW; // rax
  HWND v12; // rax
  HWND v13; // rcx
  WNDCLASSW WndClass; // [rsp+60h] [rbp-29h] BYREF
  LPVOID lpParameter; // [rsp+F0h] [rbp+67h] BYREF
  int nHeight; // [rsp+F8h] [rbp+6Fh] BYREF
  LPVOID pv; // [rsp+100h] [rbp+77h] BYREF
  DWORD ThreadId; // [rsp+108h] [rbp+7Fh] BYREF

  nHeight = a2;
  lpParameter = a1;
  if ( CoCreateInstance(&CLSID_FilterGraph, 0, 3u, &IID_IFilterGraph, a1 + 14) < 0
    || (***((int (__fastcall ****)(_QWORD, GUID *, char *))lpParameter + 14))(
         *((_QWORD *)lpParameter + 14),
         &IID_IGraphBuilder,
         (char *)lpParameter + 120) < 0 )
  {
    return 277;
  }
  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)lpParameter + 15) + 104LL))(
         *((_QWORD *)lpParameter + 15),
         *((_QWORD *)lpParameter + 8),
         0);
  if ( v2 < 0 )
    return CheckResult(v2);
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, char *))lpParameter + 14))(
         *((_QWORD *)lpParameter + 14),
         &IID_IMediaFilter,
         (char *)lpParameter + 128) < 0
    || (***((int (__fastcall ****)(_QWORD, GUID *, char *))lpParameter + 14))(
         *((_QWORD *)lpParameter + 14),
         &IID_IMediaControl,
         (char *)lpParameter + 152) < 0
    || (***((int (__fastcall ****)(_QWORD, GUID *, char *))lpParameter + 14))(
         *((_QWORD *)lpParameter + 14),
         &IID_IMediaEvent,
         (char *)lpParameter + 160) < 0
    || (***((int (__fastcall ****)(_QWORD, GUID *, char *))lpParameter + 14))(
         *((_QWORD *)lpParameter + 14),
         &IID_IMediaSeeking,
         (char *)lpParameter + 144) < 0 )
  {
    return 277;
  }
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))lpParameter + 14))(
    *((_QWORD *)lpParameter + 14),
    &IID_IBasicVideo,
    (char *)lpParameter + 168);
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, char *))lpParameter + 14))(
         *((_QWORD *)lpParameter + 14),
         &IID_IVideoWindow,
         (char *)lpParameter + 176) >= 0
    && (*(int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)lpParameter + 22) + 104LL))(
         *((_QWORD *)lpParameter + 22),
         0) < 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpParameter + 22) + 16LL))(*((_QWORD *)lpParameter + 22));
    *((_QWORD *)lpParameter + 22) = 0;
  }
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))lpParameter + 14))(
    *((_QWORD *)lpParameter + 14),
    &IID_IBasicAudio,
    (char *)lpParameter + 184);
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, char *))lpParameter + 14))(
         *((_QWORD *)lpParameter + 14),
         &IID_IMpegVideoDecoder,
         (char *)lpParameter + 336) >= 0
    || (int)FindInterface(
              *((struct IFilterGraph **)lpParameter + 14),
              &IID_IMpegVideoDecoder,
              (void **)lpParameter + 42) >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)lpParameter + 42) + 88LL))(
      *((_QWORD *)lpParameter + 42),
      (char *)lpParameter + 344);
  }
  if ( (int)FindInterface(
              *((struct IFilterGraph **)lpParameter + 14),
              &IID_IMpegAudioDecoder,
              (void **)lpParameter + 67) >= 0 )
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)lpParameter + 67) + 120LL))(
      *((_QWORD *)lpParameter + 67),
      (char *)lpParameter + 544);
  FindInterface(*((struct IFilterGraph **)lpParameter + 14), &IID_IAMStreamSelect, (void **)lpParameter + 24);
  FindInterface(*((struct IFilterGraph **)lpParameter + 14), &IID_IQualProp, (void **)lpParameter + 41);
  *((_QWORD *)lpParameter + 33) = CreateEventW(0, 0, 0, 0);
  if ( !*((_QWORD *)lpParameter + 33) )
    return 264;
  *((_QWORD *)lpParameter + 35) = CreateEventW(0, 0, 0, 0);
  if ( !*((_QWORD *)lpParameter + 35) )
    return 264;
  if ( (*(int (__fastcall **)(_QWORD, char *))(**((_QWORD **)lpParameter + 20) + 56LL))(
         *((_QWORD *)lpParameter + 20),
         (char *)lpParameter + 272) < 0 )
    return 277;
  ThreadId = 0;
  v4 = CreateThread(0, 0, DeviceThreadProc, lpParameter, 0, &ThreadId);
  *((_QWORD *)lpParameter + 32) = v4;
  if ( !*((_QWORD *)lpParameter + 32) )
    return 264;
  *((_DWORD *)lpParameter + 72) = 525;
  *((_DWORD *)lpParameter + 50) = 0;
  v5 = *((_QWORD *)lpParameter + 23) != 0;
  *((_DWORD *)lpParameter + 21) = v5;
  *((_DWORD *)lpParameter + 25) = v5;
  if ( *((_QWORD *)lpParameter + 21) )
  {
    *((_DWORD *)lpParameter + 22) = 1;
    if ( (*(int (__fastcall **)(_QWORD, char *))(**((_QWORD **)lpParameter + 21) + 56LL))(
           *((_QWORD *)lpParameter + 21),
           (char *)lpParameter + 584) < 0 )
      *((_QWORD *)lpParameter + 73) = 0;
  }
  else
  {
    *((_DWORD *)lpParameter + 22) = 0;
  }
  *((_DWORD *)lpParameter + 26) = *((_DWORD *)lpParameter + 22);
  v6 = (_QWORD **)lpParameter;
  if ( *((_QWORD *)lpParameter + 24) )
  {
    v7 = 0;
    pv = 0;
    v8 = 0;
    for ( i = 0;
          !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, LPVOID *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*v6[24] + 32LL))(
             v6[24],
             i,
             &pv,
             0,
             0,
             0,
             0,
             0,
             0);
          ++i )
    {
      v10 = pv;
      if ( *(_QWORD *)pv == *(_QWORD *)&MEDIATYPE_Audio.Data1 && *((_QWORD *)pv + 1) == *(_QWORD *)MEDIATYPE_Audio.Data4 )
      {
        ++v7;
      }
      else if ( *(_QWORD *)pv == *(_QWORD *)&MEDIATYPE_Video.Data1
             && *((_QWORD *)pv + 1) == *(_QWORD *)MEDIATYPE_Video.Data4 )
      {
        ++v8;
      }
      if ( pv )
      {
        FreeMediaType((struct _AMMediaType *)pv);
        CoTaskMemFree(v10);
      }
      v6 = (_QWORD **)lpParameter;
    }
    v6 = (_QWORD **)lpParameter;
    if ( v7 > *((_DWORD *)lpParameter + 21) )
    {
      *((_DWORD *)lpParameter + 21) = v7;
      v6 = (_QWORD **)lpParameter;
    }
    if ( v8 > *((_DWORD *)v6 + 22) )
    {
      *((_DWORD *)v6 + 22) = v8;
      v6 = (_QWORD **)lpParameter;
    }
  }
  *((_DWORD *)v6 + 56) = 0xFFFF;
  *((_DWORD *)lpParameter + 59) = 0xFFFF;
  *((_DWORD *)lpParameter + 14) = 1;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpParameter + 14) + 80LL))(*((_QWORD *)lpParameter + 14));
  if ( *((_QWORD *)lpParameter + 22) )
  {
    memset_0(&WndClass, 0, sizeof(WndClass));
    WndClass.style = 3;
    WndClass.lpszClassName = L"MCIQTZ_Window";
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
    WndClass.hIcon = 0;
    WndClass.hCursor = CursorW;
    WndClass.hInstance = ghModule;
    WndClass.lpfnWndProc = (WNDPROC)GraphicWndProc;
    WndClass.lpszMenuName = 0;
    WndClass.hbrBackground = 0;
    WndClass.cbClsExtra = 0;
    WndClass.cbWndExtra = 8;
    RegisterClassW(&WndClass);
    LODWORD(pv) = GetSystemMetrics(0);
    nHeight = GetSystemMetrics(1);
    (*(void (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)lpParameter + 22) + 192LL))(
      *((_QWORD *)lpParameter + 22),
      &pv);
    (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)lpParameter + 22) + 224LL))(
      *((_QWORD *)lpParameter + 22),
      &nHeight);
    v12 = CreateWindowExW(
            0,
            L"MCIQTZ_Window",
            &WindowName,
            *((_DWORD *)lpParameter + 10),
            (*((_DWORD *)lpParameter + 10) & 0xC0000000) != 0 ? 0 : 0x80000000,
            0,
            (int)pv,
            nHeight,
            *((HWND *)lpParameter + 4),
            0,
            ghModule,
            &lpParameter);
    *((_QWORD *)lpParameter + 6) = v12;
    *((_DWORD *)lpParameter + 61) = 0;
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)lpParameter + 22) + 136LL))(
      *((_QWORD *)lpParameter + 22),
      (unsigned int)-(*((_DWORD *)lpParameter + 14) != 0));
    DeviceSetWindow((struct _MCIGRAPHIC *)lpParameter, 0);
    v13 = (HWND)*((_QWORD *)lpParameter + 37);
    if ( v13 )
      SetWindowTextW(v13, *((LPCWSTR *)lpParameter + 8));
  }
  return 0;
}

```

## disassembly

```asm
0x180002448  mov     [rsp-8+arg_8], edx
0x18000244c  mov     [rsp-8+lpParameter], rcx
0x180002451  push    rbp
0x180002452  push    rbx
0x180002453  push    rsi
0x180002454  push    rdi
0x180002455  push    r14
0x180002457  push    r15
0x180002459  lea     rbp, [rsp-2Fh]
0x18000245e  sub     rsp, 0B8h
0x180002465  lea     rax, [rcx+70h]
0x180002469  xor     edx, edx; pUnkOuter
0x18000246b  lea     r9, IID_IFilterGraph; riid
0x180002472  mov     [rsp+0E0h+ppv], rax; ppv
0x180002477  lea     rcx, CLSID_FilterGraph; rclsid
0x18000247e  lea     r8d, [rdx+3]; dwClsContext
0x180002482  call    cs:__imp_CoCreateInstance
0x180002488  xor     r15d, r15d
0x18000248b  test    eax, eax
0x18000248d  js      loc_180002AE3
0x180002493  mov     r8, [rbp+57h+lpParameter]
0x180002497  lea     rdx, IID_IGraphBuilder
0x18000249e  mov     rcx, [r8+70h]
0x1800024a2  add     r8, 78h ; 'x'
0x1800024a6  mov     rax, [rcx]
0x1800024a9  mov     rax, [rax]
0x1800024ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024b1  test    eax, eax
0x1800024b3  js      loc_180002AE3
0x1800024b9  mov     rdx, [rbp+57h+lpParameter]
0x1800024bd  xor     r8d, r8d
0x1800024c0  mov     rcx, [rdx+78h]
0x1800024c4  mov     rdx, [rdx+40h]
0x1800024c8  mov     rax, [rcx]
0x1800024cb  mov     rax, [rax+68h]
0x1800024cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024d4  test    eax, eax
0x1800024d6  jns     short loc_1800024E4
0x1800024d8  mov     ecx, eax; int
0x1800024da  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x1800024df  jmp     loc_180002AE8
0x1800024e4  mov     r8, [rbp+57h+lpParameter]
0x1800024e8  lea     rdx, IID_IMediaFilter
0x1800024ef  mov     rcx, [r8+70h]
0x1800024f3  sub     r8, 0FFFFFFFFFFFFFF80h
0x1800024f7  mov     rax, [rcx]
0x1800024fa  mov     rax, [rax]
0x1800024fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002502  test    eax, eax
0x180002504  js      loc_180002AE3
0x18000250a  mov     r8, [rbp+57h+lpParameter]
0x18000250e  lea     rdx, IID_IMediaControl
0x180002515  mov     rcx, [r8+70h]
0x180002519  add     r8, 98h
0x180002520  mov     rax, [rcx]
0x180002523  mov     rax, [rax]
0x180002526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000252b  test    eax, eax
0x18000252d  js      loc_180002AE3
0x180002533  mov     r8, [rbp+57h+lpParameter]
0x180002537  lea     rdx, IID_IMediaEvent
0x18000253e  mov     rcx, [r8+70h]
0x180002542  add     r8, 0A0h
0x180002549  mov     rax, [rcx]
0x18000254c  mov     rax, [rax]
0x18000254f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002554  test    eax, eax
0x180002556  js      loc_180002AE3
0x18000255c  mov     r8, [rbp+57h+lpParameter]
0x180002560  lea     rdx, IID_IMediaSeeking
0x180002567  mov     rcx, [r8+70h]
0x18000256b  add     r8, 90h
0x180002572  mov     rax, [rcx]
0x180002575  mov     rax, [rax]
0x180002578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000257d  test    eax, eax
0x18000257f  js      loc_180002AE3
0x180002585  mov     r8, [rbp+57h+lpParameter]
0x180002589  lea     rdx, IID_IBasicVideo
0x180002590  mov     rcx, [r8+70h]
0x180002594  add     r8, 0A8h
0x18000259b  mov     rax, [rcx]
0x18000259e  mov     rax, [rax]
0x1800025a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025a6  mov     r8, [rbp+57h+lpParameter]
0x1800025aa  lea     rdx, IID_IVideoWindow
0x1800025b1  mov     rcx, [r8+70h]
0x1800025b5  add     r8, 0B0h
0x1800025bc  mov     rax, [rcx]
0x1800025bf  mov     rax, [rax]
0x1800025c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c7  test    eax, eax
0x1800025c9  js      short loc_18000260A
0x1800025cb  mov     rax, [rbp+57h+lpParameter]
0x1800025cf  xor     edx, edx
0x1800025d1  mov     rcx, [rax+0B0h]
0x1800025d8  mov     rax, [rcx]
0x1800025db  mov     rax, [rax+68h]
0x1800025df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e4  test    eax, eax
0x1800025e6  jns     short loc_18000260A
0x1800025e8  mov     rax, [rbp+57h+lpParameter]
0x1800025ec  mov     rcx, [rax+0B0h]
0x1800025f3  mov     rax, [rcx]
0x1800025f6  mov     rax, [rax+10h]
0x1800025fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ff  mov     rax, [rbp+57h+lpParameter]
0x180002603  mov     [rax+0B0h], r15
0x18000260a  mov     r8, [rbp+57h+lpParameter]
0x18000260e  lea     rdx, IID_IBasicAudio
0x180002615  mov     rcx, [r8+70h]
0x180002619  add     r8, 0B8h
0x180002620  mov     rax, [rcx]
0x180002623  mov     rax, [rax]
0x180002626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000262b  mov     r8, [rbp+57h+lpParameter]
0x18000262f  lea     rdx, IID_IMpegVideoDecoder
0x180002636  mov     rcx, [r8+70h]
0x18000263a  add     r8, 150h
0x180002641  mov     rax, [rcx]
0x180002644  mov     rax, [rax]
0x180002647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000264c  test    eax, eax
0x18000264e  jns     short loc_18000266F
0x180002650  mov     rcx, [rbp+57h+lpParameter]
0x180002654  lea     rdx, IID_IMpegVideoDecoder; struct _GUID *
0x18000265b  lea     r8, [rcx+150h]; void **
0x180002662  mov     rcx, [rcx+70h]; struct IFilterGraph *
0x180002666  call    ?FindInterface@@YAJPEAUIFilterGraph@@AEBU_GUID@@PEAPEAX@Z; FindInterface(IFilterGraph *,_GUID const &,void * *)
0x18000266b  test    eax, eax
0x18000266d  js      short loc_18000268D
0x18000266f  mov     rdx, [rbp+57h+lpParameter]
0x180002673  mov     rcx, [rdx+150h]
0x18000267a  add     rdx, 158h
0x180002681  mov     rax, [rcx]
0x180002684  mov     rax, [rax+58h]
0x180002688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000268d  mov     rcx, [rbp+57h+lpParameter]
0x180002691  lea     rdx, IID_IMpegAudioDecoder; struct _GUID *
0x180002698  lea     r8, [rcx+218h]; void **
0x18000269f  mov     rcx, [rcx+70h]; struct IFilterGraph *
0x1800026a3  call    ?FindInterface@@YAJPEAUIFilterGraph@@AEBU_GUID@@PEAPEAX@Z; FindInterface(IFilterGraph *,_GUID const &,void * *)
0x1800026a8  test    eax, eax
0x1800026aa  js      short loc_1800026CA
0x1800026ac  mov     rdx, [rbp+57h+lpParameter]
0x1800026b0  mov     rcx, [rdx+218h]
0x1800026b7  add     rdx, 220h
0x1800026be  mov     rax, [rcx]
0x1800026c1  mov     rax, [rax+78h]
0x1800026c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ca  mov     rcx, [rbp+57h+lpParameter]
0x1800026ce  lea     rdx, IID_IAMStreamSelect; struct _GUID *
0x1800026d5  lea     r8, [rcx+0C0h]; void **
0x1800026dc  mov     rcx, [rcx+70h]; struct IFilterGraph *
0x1800026e0  call    ?FindInterface@@YAJPEAUIFilterGraph@@AEBU_GUID@@PEAPEAX@Z; FindInterface(IFilterGraph *,_GUID const &,void * *)
0x1800026e5  mov     rcx, [rbp+57h+lpParameter]
0x1800026e9  lea     rdx, IID_IQualProp; struct _GUID *
0x1800026f0  lea     r8, [rcx+148h]; void **
0x1800026f7  mov     rcx, [rcx+70h]; struct IFilterGraph *
0x1800026fb  call    ?FindInterface@@YAJPEAUIFilterGraph@@AEBU_GUID@@PEAPEAX@Z; FindInterface(IFilterGraph *,_GUID const &,void * *)
0x180002700  xor     r9d, r9d; lpName
0x180002703  xor     r8d, r8d; bInitialState
0x180002706  xor     edx, edx; bManualReset
0x180002708  xor     ecx, ecx; lpEventAttributes
0x18000270a  call    cs:__imp_CreateEventW
0x180002710  mov     rcx, [rbp+57h+lpParameter]
0x180002714  mov     [rcx+108h], rax
0x18000271b  mov     rax, [rbp+57h+lpParameter]
0x18000271f  cmp     [rax+108h], r15
0x180002726  jz      loc_180002ADC
0x18000272c  xor     r9d, r9d; lpName
0x18000272f  xor     r8d, r8d; bInitialState
0x180002732  xor     edx, edx; bManualReset
0x180002734  xor     ecx, ecx; lpEventAttributes
0x180002736  call    cs:__imp_CreateEventW
0x18000273c  mov     rcx, [rbp+57h+lpParameter]
0x180002740  mov     [rcx+118h], rax
0x180002747  mov     rdx, [rbp+57h+lpParameter]
0x18000274b  cmp     [rdx+118h], r15
0x180002752  jz      loc_180002ADC
0x180002758  mov     rcx, [rdx+0A0h]
0x18000275f  add     rdx, 110h
0x180002766  mov     rax, [rcx]
0x180002769  mov     rax, [rax+38h]
0x18000276d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002772  test    eax, eax
0x180002774  js      loc_180002AE3
0x18000277a  mov     r9, [rbp+57h+lpParameter]; lpParameter
0x18000277e  lea     rax, [rbp+57h+ThreadId]
0x180002782  mov     [rsp+0E0h+lpThreadId], rax; lpThreadId
0x180002787  lea     r8, ?DeviceThreadProc@@YAKPEAX@Z; lpStartAddress
0x18000278e  xor     edx, edx; dwStackSize
0x180002790  mov     dword ptr [rsp+0E0h+ppv], r15d; dwCreationFlags
0x180002795  xor     ecx, ecx; lpThreadAttributes
0x180002797  mov     [rbp+57h+ThreadId], r15d
0x18000279b  call    cs:__imp_CreateThread
0x1800027a1  mov     rcx, [rbp+57h+lpParameter]
0x1800027a5  mov     [rcx+100h], rax
0x1800027ac  mov     rax, [rbp+57h+lpParameter]
0x1800027b0  cmp     [rax+100h], r15
0x1800027b7  jz      loc_180002ADC
0x1800027bd  mov     dword ptr [rax+120h], 20Dh
0x1800027c7  mov     ecx, r15d
0x1800027ca  mov     rax, [rbp+57h+lpParameter]
0x1800027ce  mov     [rax+0C8h], r15d
0x1800027d5  mov     rax, [rbp+57h+lpParameter]
0x1800027d9  cmp     [rax+0B8h], r15
0x1800027e0  setnz   cl
0x1800027e3  mov     [rax+54h], ecx
0x1800027e6  mov     rax, [rbp+57h+lpParameter]
0x1800027ea  mov     [rax+64h], ecx
0x1800027ed  mov     rax, [rbp+57h+lpParameter]
0x1800027f1  cmp     [rax+0A8h], r15
0x1800027f8  jz      short loc_180002830
0x1800027fa  mov     dword ptr [rax+58h], 1
0x180002801  mov     rdx, [rbp+57h+lpParameter]
0x180002805  mov     rcx, [rdx+0A8h]
0x18000280c  add     rdx, 248h
0x180002813  mov     rax, [rcx]
0x180002816  mov     rax, [rax+38h]
0x18000281a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000281f  test    eax, eax
0x180002821  jns     short loc_180002834
0x180002823  mov     rax, [rbp+57h+lpParameter]
0x180002827  mov     [rax+248h], r15
0x18000282e  jmp     short loc_180002834
0x180002830  mov     [rax+58h], r15d
0x180002834  mov     rcx, [rbp+57h+lpParameter]
0x180002838  mov     eax, [rcx+58h]
0x18000283b  mov     [rcx+68h], eax
0x18000283e  mov     rax, [rbp+57h+lpParameter]
0x180002842  cmp     [rax+0C0h], r15
0x180002849  jz      loc_180002910
0x18000284f  mov     esi, r15d
0x180002852  mov     [rbp+57h+pv], r15
0x180002856  mov     edi, r15d
0x180002859  mov     r14d, r15d
0x18000285c  mov     rcx, [rax+0C0h]
0x180002863  lea     r8, [rbp+57h+pv]
0x180002867  mov     [rsp+0E0h+hWndParent], r15
0x18000286c  xor     r9d, r9d
0x18000286f  mov     qword ptr [rsp+0E0h+nHeight], r15
0x180002874  mov     edx, r14d
0x180002877  mov     qword ptr [rsp+0E0h+nWidth], r15
0x18000287c  mov     rax, [rcx]
0x18000287f  mov     [rsp+0E0h+lpThreadId], r15
0x180002884  mov     [rsp+0E0h+ppv], r15
0x180002889  mov     rax, [rax+20h]
0x18000288d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002892  test    eax, eax
0x180002894  jnz     short loc_1800028F4
0x180002896  mov     rbx, [rbp+57h+pv]
0x18000289a  mov     rax, [rbx]
0x18000289d  cmp     rax, qword ptr cs:MEDIATYPE_Audio.Data1
0x1800028a4  jnz     short loc_1800028B7
0x1800028a6  mov     rax, [rbx+8]
0x1800028aa  cmp     rax, qword ptr cs:MEDIATYPE_Audio.Data4
0x1800028b1  jnz     short loc_1800028B7
0x1800028b3  inc     esi
0x1800028b5  jmp     short loc_1800028D2
0x1800028b7  mov     rax, [rbx]
0x1800028ba  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x1800028c1  jnz     short loc_1800028D2
0x1800028c3  mov     rax, [rbx+8]
0x1800028c7  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x1800028ce  jnz     short loc_1800028D2
0x1800028d0  inc     edi
0x1800028d2  test    rbx, rbx
0x1800028d5  jz      short loc_1800028E8
0x1800028d7  mov     rcx, rbx; struct _AMMediaType *
0x1800028da  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800028df  mov     rcx, rbx; pv
0x1800028e2  call    cs:__imp_CoTaskMemFree
0x1800028e8  mov     rax, [rbp+57h+lpParameter]
0x1800028ec  inc     r14d
0x1800028ef  jmp     loc_18000285C
0x1800028f4  mov     rax, [rbp+57h+lpParameter]
0x1800028f8  cmp     esi, [rax+54h]
0x1800028fb  jle     short loc_180002904
0x1800028fd  mov     [rax+54h], esi
0x180002900  mov     rax, [rbp+57h+lpParameter]
0x180002904  cmp     edi, [rax+58h]
0x180002907  jle     short loc_180002910
0x180002909  mov     [rax+58h], edi
0x18000290c  mov     rax, [rbp+57h+lpParameter]
0x180002910  mov     ecx, 0FFFFh
0x180002915  mov     [rax+0E0h], ecx
0x18000291b  mov     rax, [rbp+57h+lpParameter]
0x18000291f  mov     [rax+0ECh], ecx
0x180002925  mov     rax, [rbp+57h+lpParameter]
0x180002929  mov     dword ptr [rax+38h], 1
0x180002930  mov     rax, [rbp+57h+lpParameter]
0x180002934  mov     rcx, [rax+70h]
0x180002938  mov     rax, [rcx]
0x18000293b  mov     rax, [rax+50h]
0x18000293f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002944  mov     rax, [rbp+57h+lpParameter]
0x180002948  cmp     [rax+0B0h], r15
0x18000294f  jz      loc_180002AD8
0x180002955  xor     edx, edx; Val
  ... truncated ...
```
