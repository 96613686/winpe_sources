# CSplash::DisplaySplashScreen(MAINPARAM *,ushort const *,bool,std::function<bool (HINSTANCE__ * *,uint *,uint *,uint *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)>,ushort const *,PIDFamily,HKEY__ *,int,ulong,bool)

- ea: `0x14002e9c0`
- end: `0x14002ec12`
- name: `?DisplaySplashScreen@CSplash@@QEAAXPEAUMAINPARAM@@PEBG_NV?$function@$$A6A_NPEAPEAUHINSTANCE__@@PEAI11AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z@std@@1W4PIDFamily@@PEAUHKEY__@@HK2@Z`
- size: `594`
- prototype: `__int64 __usercall@<rax>(CSplash *this@<rcx>, __int64, __int64, int, __int64, int, int, char)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14002e85c`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140003160`
- `0x140003ec0`
- `0x140008730`
- `0x14002dca0`
- `0x14002ddc0`
- `0x14002e088`
- `0x14002e9c0`
- `0x14002ec14`
- `0x14002ec90`
- `0x14002ed94`
- `0x14002f6b0`
- `0x140033ab0`

## import_xrefs

- `KERNEL32!ResumeThread` at `0x14002eb39`
- `KERNEL32!ResumeThread` at `0x14002eb39`
- `KERNEL32!SetThreadPriority` at `0x14002eb30`
- `KERNEL32!SetThreadPriority` at `0x14002eb30`
- `KERNEL32!GetSystemInfo` at `0x14002eb0e`
- `KERNEL32!GetSystemInfo` at `0x14002eb0e`
- `KERNEL32!CloseHandle` at `0x14002eb42`
- `KERNEL32!CloseHandle` at `0x14002eb42`
- `USER32!MessageBoxW` at `0x14002ebb0`
- `USER32!MessageBoxW` at `0x14002ebb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CSplash::DisplaySplashScreen(
        CSplash *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  int v8; // r14d
  __int64 v9; // r15
  __int64 (__fastcall ***v10)(_QWORD, _BYTE *); // rcx
  struct ATL::IAtlStringMgr *Instance; // rax
  int v12; // r8d
  HANDLE DisplayThreadSuspended; // rax
  void *v14; // rbx
  SplashWindow *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v18[4]; // [rsp+60h] [rbp-A8h] BYREF
  struct tagRECT v19; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v20[56]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v21; // [rsp+C8h] [rbp-40h]
  struct _SYSTEM_INFO SystemInfo; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v23[128]; // [rsp+108h] [rbp+0h] BYREF

  v18[3] = a5;
  v8 = CDevEnvAppId::ms_fSplash;
  if ( a2 )
  {
    *((_QWORD *)this + 18) = a2;
    if ( !SplashWindow::sm_pThis && !*((_QWORD *)this + 16) )
    {
      *(_QWORD *)&v19.left = v18;
      v18[1] = v20;
      v18[0] = &v17;
      v9 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
             v18,
             a6);
      v21 = 0;
      v10 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a5 + 56);
      if ( v10 )
        v21 = (**v10)(v10, v20);
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      v17 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
      ATL::CSimpleStringT<unsigned short,0>::Empty(&v17);
      CSplash::DisplayParams::DisplayParams((unsigned int)v23, (unsigned int)&v17, v12, (unsigned int)v20, v9, a7);
      CSplash::DisplayParams::operator=((char *)this + 8, v23);
      if ( v8
        || (memset(&SystemInfo, 0, sizeof(SystemInfo)), GetSystemInfo(&SystemInfo), SystemInfo.dwNumberOfProcessors <= 1)
        || (DisplayThreadSuspended = CSplash::CreateDisplayThreadSuspended(this), (v14 = DisplayThreadSuspended) == 0) )
      {
        if ( CSplash::CreateSplashWindow(this, (const struct CSplash::DisplayParams *)v23) )
        {
          *(struct tagRECT *)&v18[1] = *CSplash::GetSplashWindowCenterRectangle(
                                          &v19,
                                          (const struct CSplash::DisplayParams *)v23);
          if ( !SplashWindow::sm_pThis || !SplashWindow::Show(v15, (const struct tagRECT *)&v18[1]) )
            SplashWindow::DeleteInstance();
        }
        if ( v8 )
          MessageBoxW(0, L"Click OK to continue", L"Splash Screen", 0);
        CSplash::DisplayParams::~DisplayParams((CSplash::DisplayParams *)v23);
      }
      else
      {
        SetThreadPriority(DisplayThreadSuspended, -1);
        ResumeThread(v14);
        CloseHandle(v14);
        CSplash::DisplayParams::~DisplayParams((CSplash::DisplayParams *)v23);
      }
    }
  }
  v16 = *(_QWORD *)(a5 + 56);
  if ( v16 )
  {
    LOBYTE(a2) = v16 != a5;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 32LL))(v16, a2);
    *(_QWORD *)(a5 + 56) = 0;
  }
}

```

## disassembly

```asm
0x14002e9c0  mov     rax, rsp
0x14002e9c3  mov     [rax+10h], rbx
0x14002e9c7  mov     [rax+18h], rsi
0x14002e9cb  mov     [rax+20h], rdi
0x14002e9cf  push    rbp
0x14002e9d0  push    r14
0x14002e9d2  push    r15
0x14002e9d4  lea     rbp, [rax-0A8h]
0x14002e9db  sub     rsp, 190h
0x14002e9e2  mov     rax, cs:__security_cookie
0x14002e9e9  xor     rax, rsp
0x14002e9ec  mov     [rbp+0A0h+var_20], rax
0x14002e9f3  mov     rsi, rcx
0x14002e9f6  mov     rdi, [rbp+0A0h+arg_20]
0x14002e9fd  mov     [rsp+1A0h+var_130], rdi
0x14002ea02  mov     rax, [rbp+0A0h+arg_28]
0x14002ea09  mov     bl, [rbp+0A0h+arg_50]
0x14002ea0f  mov     r14d, cs:?ms_fSplash@CDevEnvAppId@@1HA; int CDevEnvAppId::ms_fSplash
0x14002ea16  test    rdx, rdx
0x14002ea19  jnz     short loc_14002EA20
0x14002ea1b  jmp     loc_14002EBC1
0x14002ea20  mov     [rcx+90h], rdx
0x14002ea27  cmp     cs:?sm_pThis@SplashWindow@@0PEAV1@EA, 0; SplashWindow * SplashWindow::sm_pThis
0x14002ea2f  jz      short loc_14002EA36
0x14002ea31  jmp     loc_14002EBC1
0x14002ea36  cmp     qword ptr [rcx+80h], 0
0x14002ea3e  jz      short loc_14002EA45
0x14002ea40  jmp     loc_14002EBC1
0x14002ea45  lea     rcx, [rsp+1A0h+var_148]
0x14002ea4a  mov     qword ptr [rsp+1A0h+var_128.left], rcx
0x14002ea4f  lea     rcx, [rbp+0A0h+var_118]
0x14002ea53  mov     qword ptr [rsp+1A0h+var_148+8], rcx
0x14002ea58  lea     rcx, [rsp+1A0h+var_150]
0x14002ea5d  mov     qword ptr [rsp+1A0h+var_148], rcx
0x14002ea62  mov     rdx, rax
0x14002ea65  lea     rcx, [rsp+1A0h+var_148]
0x14002ea6a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002ea6f  mov     r15, rax
0x14002ea72  and     [rbp+0A0h+var_E0], 0
0x14002ea77  mov     rcx, [rdi+38h]
0x14002ea7b  test    rcx, rcx
0x14002ea7e  jz      short loc_14002EA8E
0x14002ea80  mov     r8, [rcx]
0x14002ea83  lea     rdx, [rbp+0A0h+var_118]
0x14002ea87  call    qword ptr [r8]
0x14002ea8a  mov     [rbp+0A0h+var_E0], rax
0x14002ea8e  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002ea93  mov     rcx, rax
0x14002ea96  test    rax, rax
0x14002ea99  jz      loc_14002EC07
0x14002ea9f  mov     rax, [rax]
0x14002eaa2  call    qword ptr [rax+18h]
0x14002eaa5  add     rax, 18h
0x14002eaa9  mov     [rsp+1A0h+var_150], rax
0x14002eaae  lea     rcx, [rsp+1A0h+var_150]
0x14002eab3  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14002eab8  mov     [rsp+1A0h+var_160], bl
0x14002eabc  mov     rax, [rbp+0A0h+arg_38]
0x14002eac3  mov     qword ptr [rsp+1A0h+var_168], rax
0x14002eac8  mov     eax, [rbp+0A0h+arg_30]
0x14002eace  mov     [rsp+1A0h+var_178], eax
0x14002ead2  mov     qword ptr [rsp+1A0h+var_180], r15
0x14002ead7  lea     r9, [rbp+0A0h+var_118]
0x14002eadb  lea     rdx, [rsp+1A0h+var_150]
0x14002eae0  lea     rcx, [rbp+0A0h+var_A0]
0x14002eae4  call    ??0DisplayParams@CSplash@@QEAA@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NV?$function@$$A6A_NPEAPEAUHINSTANCE__@@PEAI11AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z@std@@0W4PIDFamily@@KPEAUHKEY__@@1@Z; CSplash::DisplayParams::DisplayParams(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,std::function<bool (HINSTANCE__ * *,uint *,uint *,uint *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PIDFamily,ulong,HKEY__ *,bool)
0x14002eae9  lea     rcx, [rsi+8]
0x14002eaed  lea     rdx, [rbp+0A0h+var_A0]
0x14002eaf1  call    ??4DisplayParams@CSplash@@QEAAAEAU01@AEBU01@@Z; CSplash::DisplayParams::operator=(CSplash::DisplayParams const &)
0x14002eaf6  test    r14d, r14d
0x14002eaf9  jnz     short loc_14002EB54
0x14002eafb  xorps   xmm0, xmm0
0x14002eafe  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm0
0x14002eb02  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x14002eb06  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm0
0x14002eb0a  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x14002eb0e  call    cs:__imp_GetSystemInfo
0x14002eb14  cmp     [rbp+0A0h+SystemInfo.dwNumberOfProcessors], 1
0x14002eb18  jbe     short loc_14002EB54
0x14002eb1a  mov     rcx, rsi; this
0x14002eb1d  call    ?CreateDisplayThreadSuspended@CSplash@@AEAAPEAXXZ; CSplash::CreateDisplayThreadSuspended(void)
0x14002eb22  mov     rbx, rax
0x14002eb25  test    rax, rax
0x14002eb28  jz      short loc_14002EB54
0x14002eb2a  or      edx, 0FFFFFFFFh; nPriority
0x14002eb2d  mov     rcx, rax; hThread
0x14002eb30  call    cs:__imp_SetThreadPriority
0x14002eb36  mov     rcx, rbx; hThread
0x14002eb39  call    cs:__imp_ResumeThread
0x14002eb3f  mov     rcx, rbx; hObject
0x14002eb42  call    cs:__imp_CloseHandle
0x14002eb48  nop
0x14002eb49  lea     rcx, [rbp+0A0h+var_A0]; this
0x14002eb4d  call    ??1DisplayParams@CSplash@@QEAA@XZ; CSplash::DisplayParams::~DisplayParams(void)
0x14002eb52  jmp     short loc_14002EBC1
0x14002eb54  lea     rdx, [rbp+0A0h+var_A0]; struct CSplash::DisplayParams *
0x14002eb58  mov     rcx, rsi; this
0x14002eb5b  call    ?CreateSplashWindow@CSplash@@AEAA_NAEBUDisplayParams@1@@Z; CSplash::CreateSplashWindow(CSplash::DisplayParams const &)
0x14002eb60  test    al, al
0x14002eb62  jz      short loc_14002EB98
0x14002eb64  lea     rdx, [rbp+0A0h+var_A0]; struct CSplash::DisplayParams *
0x14002eb68  lea     rcx, [rsp+1A0h+var_128]; retstr
0x14002eb6d  call    ?GetSplashWindowCenterRectangle@CSplash@@CA?AUtagRECT@@AEBUDisplayParams@1@@Z; CSplash::GetSplashWindowCenterRectangle(CSplash::DisplayParams const &)
0x14002eb72  movups  xmm0, xmmword ptr [rax]
0x14002eb75  movdqu  xmmword ptr [rsp+1A0h+var_148+8], xmm0
0x14002eb7b  cmp     cs:?sm_pThis@SplashWindow@@0PEAV1@EA, 0; SplashWindow * SplashWindow::sm_pThis
0x14002eb83  jz      short loc_14002EB93
0x14002eb85  lea     rdx, [rsp+1A0h+var_148+8]; struct tagRECT *
0x14002eb8a  call    ?Show@SplashWindow@@AEAA_NAEBUtagRECT@@@Z; SplashWindow::Show(tagRECT const &)
0x14002eb8f  test    al, al
0x14002eb91  jnz     short loc_14002EB98
0x14002eb93  call    ?DeleteInstance@SplashWindow@@SAXXZ; SplashWindow::DeleteInstance(void)
0x14002eb98  test    r14d, r14d
0x14002eb9b  jz      short loc_14002EBB7
0x14002eb9d  xor     r9d, r9d; uType
0x14002eba0  lea     r8, Caption; "Splash Screen"
0x14002eba7  lea     rdx, Text; "Click OK to continue"
0x14002ebae  xor     ecx, ecx; hWnd
0x14002ebb0  call    cs:__imp_MessageBoxW
0x14002ebb6  nop
0x14002ebb7  lea     rcx, [rbp+0A0h+var_A0]; this
0x14002ebbb  call    ??1DisplayParams@CSplash@@QEAA@XZ; CSplash::DisplayParams::~DisplayParams(void)
0x14002ebc0  nop
0x14002ebc1  mov     rcx, [rdi+38h]
0x14002ebc5  test    rcx, rcx
0x14002ebc8  jz      short loc_14002EBDB
0x14002ebca  cmp     rcx, rdi
0x14002ebcd  mov     rax, [rcx]
0x14002ebd0  setnz   dl
0x14002ebd3  call    qword ptr [rax+20h]
0x14002ebd6  and     qword ptr [rdi+38h], 0
0x14002ebdb  mov     rcx, [rbp+0A0h+var_20]
0x14002ebe2  xor     rcx, rsp; StackCookie
0x14002ebe5  call    __security_check_cookie
0x14002ebea  lea     r11, [rsp+1A0h+var_10]
0x14002ebf2  mov     rbx, [r11+28h]
0x14002ebf6  mov     rsi, [r11+30h]
0x14002ebfa  mov     rdi, [r11+38h]
0x14002ebfe  mov     rsp, r11
0x14002ec01  pop     r15
0x14002ec03  pop     r14
0x14002ec05  pop     rbp
0x14002ec06  retn
0x14002ec07  mov     ecx, 80004005h; int
0x14002ec0c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
