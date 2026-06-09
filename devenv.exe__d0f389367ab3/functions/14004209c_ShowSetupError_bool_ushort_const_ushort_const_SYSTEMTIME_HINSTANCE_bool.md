# ShowSetupError(bool,ushort const *,ushort const *,_SYSTEMTIME *,HINSTANCE__ *,bool *)

- ea: `0x14004209c`
- end: `0x140042572`
- name: `?ShowSetupError@@YAJ_NPEBG1PEAU_SYSTEMTIME@@PEAUHINSTANCE__@@PEA_N@Z`
- size: `1238`
- prototype: `__int64 __fastcall(bool, const unsigned __int16 *, const unsigned __int16 *, struct _SYSTEMTIME *, HINSTANCE, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140003160`
- `0x140003ec0`
- `0x140033310`
- `0x140033ab0`
- `0x140041ef0`
- `0x14004209c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004240a`
- `ADVAPI32!RegCloseKey` at `0x14004247b`
- `ADVAPI32!RegCloseKey` at `0x1400424d1`
- `ADVAPI32!RegCloseKey` at `0x14004240a`
- `ADVAPI32!RegCloseKey` at `0x14004247b`
- `ADVAPI32!RegCloseKey` at `0x1400424d1`
- `ADVAPI32!RegOpenKeyExW` at `0x1400423ac`
- `ADVAPI32!RegOpenKeyExW` at `0x1400423ac`
- `ADVAPI32!RegSetValueExW` at `0x140042453`
- `ADVAPI32!RegSetValueExW` at `0x140042453`
- `KERNEL32!SystemTimeToFileTime` at `0x1400423e1`
- `KERNEL32!SystemTimeToFileTime` at `0x1400423e1`
- `KERNEL32!GetSystemTime` at `0x140042382`
- `KERNEL32!GetSystemTime` at `0x140042382`
- `KERNEL32!GetLastError` at `0x1400423eb`
- `KERNEL32!GetLastError` at `0x1400423eb`
- `USER32!MessageBoxW` at `0x1400421d7`
- `USER32!MessageBoxW` at `0x14004236f`
- `USER32!MessageBoxW` at `0x1400421d7`
- `USER32!MessageBoxW` at `0x14004236f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ShowSetupError(
        char a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SYSTEMTIME *a4,
        HINSTANCE a5,
        bool *a6)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  struct ATL::IAtlStringMgr *v8; // rax
  const WCHAR *v9; // rbx
  signed int v10; // r15d
  volatile signed __int32 *v11; // rdx
  volatile signed __int32 *v12; // rdx
  LPCWSTR v13; // rdi
  LPCWSTR v14; // rbx
  _QWORD *v15; // rdx
  __int64 v16; // rcx
  int v17; // ebx
  LPCWSTR v18; // rdx
  int ShouldShowMessage; // eax
  struct ATL::IAtlStringMgr *v21; // rax
  struct ATL::IAtlStringMgr *v22; // rax
  const WCHAR *v23; // rbx
  volatile signed __int32 *v24; // rdx
  LPCWSTR v25; // rdi
  LPCWSTR v26; // rbx
  LSTATUS v27; // eax
  WCHAR *v28; // r12
  signed int LastError; // eax
  LSTATUS v30; // eax
  LPCWSTR lpCaption; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpText; // [rsp+38h] [rbp-28h] BYREF
  struct _FILETIME FileTime; // [rsp+40h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-18h] BYREF

  if ( a2 && a4 && a5 && a6 )
  {
    if ( !a1 )
    {
      *a6 = 0;
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( Instance )
      {
        lpCaption = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                            + 24);
        v8 = ATL::CAtlStringMgr::GetInstance();
        if ( !v8 )
          ATL::AtlThrowImpl(-2147467259);
        v9 = (const WCHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v8 + 24LL))(v8) + 24);
        lpText = v9;
        ATL::CSimpleStringT<unsigned short,0>::Empty(&lpCaption);
        if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                              &lpCaption,
                              a5,
                              28684) )
        {
          v10 = -2147023728;
          v11 = (volatile signed __int32 *)(v9 - 12);
          goto LABEL_10;
        }
        ATL::CSimpleStringT<unsigned short,0>::Empty(&lpText);
        if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                              &lpText,
                              a5,
                              28685) )
        {
          v10 = -2147023728;
          v11 = (volatile signed __int32 *)(lpText - 12);
LABEL_10:
          if ( _InterlockedDecrement(v11 + 4) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
          }
LABEL_12:
          v12 = (volatile signed __int32 *)(lpCaption - 12);
LABEL_58:
          if ( _InterlockedDecrement(v12 + 4) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
          }
LABEL_60:
          _mm_lfence();
          return (unsigned int)v10;
        }
        v13 = lpCaption;
        v14 = lpText;
        MessageBoxW(0, lpText, lpCaption, 0x30u);
        if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
        }
        v15 = v13 - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)v13 - 2) > 0 )
          return 0;
LABEL_67:
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
        return 0;
      }
LABEL_72:
      ATL::AtlThrowImpl(-2147467259);
    }
    lpText = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &lpText,
      a2);
    v17 = *lpText - 49;
    if ( *lpText == 49 )
    {
      v16 = 0;
      v17 = lpText[1];
    }
    v18 = lpText - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)lpText - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
    }
    if ( !v17 )
      return 2147549183LL;
    *a6 = 0;
    ShouldShowMessage = anonymous_namespace_::ShouldShowMessage(v16, a4);
    v10 = ShouldShowMessage;
    if ( ShouldShowMessage < 0 )
      goto LABEL_60;
    if ( ShouldShowMessage == 1 )
    {
      *a6 = 1;
      return 0;
    }
    v21 = ATL::CAtlStringMgr::GetInstance();
    if ( !v21 )
      goto LABEL_72;
    lpCaption = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v21 + 24LL))(v21) + 24);
    v22 = ATL::CAtlStringMgr::GetInstance();
    if ( !v22 )
      ATL::AtlThrowImpl(-2147467259);
    v23 = (const WCHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v22 + 24LL))(v22) + 24);
    lpText = v23;
    ATL::CSimpleStringT<unsigned short,0>::Empty(&lpCaption);
    if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                          &lpCaption,
                          a5,
                          28684) )
    {
      v10 = -2147023728;
      v24 = (volatile signed __int32 *)(v23 - 12);
      goto LABEL_32;
    }
    ATL::CSimpleStringT<unsigned short,0>::Empty(&lpText);
    if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                          &lpText,
                          a5,
                          28686) )
    {
      v10 = -2147023728;
      v24 = (volatile signed __int32 *)(lpText - 12);
LABEL_32:
      if ( _InterlockedDecrement(v24 + 4) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24);
      }
      goto LABEL_12;
    }
    v25 = lpCaption;
    v26 = lpText;
    if ( MessageBoxW(0, lpText, lpCaption, 0x134u) == 6 )
    {
      GetSystemTime(&SystemTime);
      lpText = 0;
      v27 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\VisualStudio\\17.0", 0, 0x20006u, (PHKEY)&lpText);
      if ( v27 )
      {
        v10 = (unsigned __int16)v27 | 0x80070000;
        if ( v27 <= 0 )
          v10 = v27;
        goto LABEL_55;
      }
      v28 = (WCHAR *)lpText;
      if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
      {
        lpText = (LPCWSTR)FileTime;
        v30 = RegSetValueExW((HKEY)v28, L"SetupMessageTimestamp", 0, 0xBu, (const BYTE *)&lpText, 8u);
        if ( v30 )
        {
          v10 = (unsigned __int16)v30 | 0x80070000;
          if ( v30 <= 0 )
            v10 = v30;
          if ( v28 )
            RegCloseKey((HKEY)v28);
          goto LABEL_55;
        }
        if ( v28 )
          RegCloseKey((HKEY)v28);
      }
      else
      {
        LastError = GetLastError();
        v10 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v10 = LastError;
        if ( v28 )
          RegCloseKey((HKEY)v28);
        if ( v10 < 0 )
        {
LABEL_55:
          if ( _InterlockedDecrement((volatile signed __int32 *)v26 - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v26 - 3) + 8LL))(*((_QWORD *)v26 - 3));
          }
          v12 = (volatile signed __int32 *)(v25 - 12);
          goto LABEL_58;
        }
      }
      *a6 = 1;
    }
    if ( _InterlockedDecrement((volatile signed __int32 *)v26 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v26 - 3) + 8LL))(*((_QWORD *)v26 - 3));
    }
    v15 = v25 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v25 - 2) > 0 )
      return 0;
    goto LABEL_67;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x14004209c  mov     [rsp-38h+arg_0], rbx
0x1400420a1  push    rbp
0x1400420a2  push    rsi
0x1400420a3  push    rdi
0x1400420a4  push    r12
0x1400420a6  push    r13
0x1400420a8  push    r14
0x1400420aa  push    r15
0x1400420ac  mov     rbp, rsp
0x1400420af  sub     rsp, 60h
0x1400420b3  mov     rax, cs:__security_cookie
0x1400420ba  xor     rax, rsp
0x1400420bd  mov     [rbp+var_8], rax
0x1400420c1  mov     r15, r9
0x1400420c4  mov     r13, [rbp+arg_28]
0x1400420c8  mov     rdi, [rbp+arg_20]
0x1400420cc  xor     esi, esi
0x1400420ce  test    rdx, rdx
0x1400420d1  jz      loc_140042520
0x1400420d7  test    r9, r9
0x1400420da  jz      loc_140042520
0x1400420e0  test    rdi, rdi
0x1400420e3  jz      loc_140042520
0x1400420e9  test    r13, r13
0x1400420ec  jz      loc_140042520
0x1400420f2  test    cl, cl
0x1400420f4  jnz     loc_140042229
0x1400420fa  mov     [r13+0], sil
0x1400420fe  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140042103  mov     rcx, rax
0x140042106  test    rax, rax
0x140042109  jz      loc_140042567
0x14004210f  mov     rax, [rax]
0x140042112  call    qword ptr [rax+18h]
0x140042115  add     rax, 18h
0x140042119  mov     [rbp+lpCaption], rax
0x14004211d  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140042122  mov     rcx, rax
0x140042125  test    rax, rax
0x140042128  jz      loc_140042559
0x14004212e  mov     rax, [rax]
0x140042131  call    qword ptr [rax+18h]
0x140042134  lea     rbx, [rax+18h]
0x140042138  mov     [rbp+lpText], rbx
0x14004213c  lea     rcx, [rbp+lpCaption]
0x140042140  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140042145  mov     r8d, 700Ch
0x14004214b  mov     rdx, rdi
0x14004214e  lea     rcx, [rbp+lpCaption]
0x140042152  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x140042157  test    eax, eax
0x140042159  jnz     short loc_140042192
0x14004215b  mov     r15d, 80070490h
0x140042161  lea     rdx, [rbx-18h]
0x140042165  or      r14d, 0FFFFFFFFh
0x140042169  mov     eax, r14d
0x14004216c  lock xadd [rdx+10h], eax
0x140042171  add     eax, r14d
0x140042174  test    eax, eax
0x140042176  jg      short loc_140042185
0x140042178  lfence
0x14004217b  mov     rcx, [rdx]
0x14004217e  mov     rax, [rcx]
0x140042181  call    qword ptr [rax+8]
0x140042184  nop
0x140042185  mov     rdx, [rbp+lpCaption]
0x140042189  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004218d  jmp     loc_1400424A6
0x140042192  lea     rcx, [rbp+lpText]
0x140042196  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14004219b  mov     r8d, 700Dh
0x1400421a1  mov     rdx, rdi
0x1400421a4  lea     rcx, [rbp+lpText]
0x1400421a8  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x1400421ad  test    eax, eax
0x1400421af  jnz     short loc_1400421C1
0x1400421b1  mov     r15d, 80070490h
0x1400421b7  mov     rdx, [rbp+lpText]
0x1400421bb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400421bf  jmp     short loc_140042165
0x1400421c1  mov     r9d, 30h ; '0'; uType
0x1400421c7  mov     rdi, [rbp+lpCaption]
0x1400421cb  mov     r8, rdi; lpCaption
0x1400421ce  mov     rbx, [rbp+lpText]
0x1400421d2  mov     rdx, rbx; lpText
0x1400421d5  xor     ecx, ecx; hWnd
0x1400421d7  call    cs:__imp_MessageBoxW
0x1400421dd  lea     rdx, [rbx-18h]
0x1400421e1  or      r14d, 0FFFFFFFFh
0x1400421e5  mov     eax, r14d
0x1400421e8  lock xadd [rdx+10h], eax
0x1400421ed  add     eax, r14d
0x1400421f0  test    eax, eax
0x1400421f2  jg      short loc_140042201
0x1400421f4  lfence
0x1400421f7  mov     rcx, [rdx]
0x1400421fa  mov     rax, [rcx]
0x1400421fd  call    qword ptr [rax+8]
0x140042200  nop
0x140042201  lea     rdx, [rdi-18h]
0x140042205  mov     eax, r14d
0x140042208  lock xadd [rdx+10h], eax
0x14004220d  add     eax, r14d
0x140042210  test    eax, eax
0x140042212  jg      loc_14004251C
0x140042218  lfence
0x14004221b  mov     rcx, [rdx]
0x14004221e  mov     rax, [rcx]
0x140042221  call    qword ptr [rax+8]
0x140042224  jmp     loc_14004251C
0x140042229  mov     [rbp+lpText], rsi
0x14004222d  lea     rcx, [rbp+lpText]
0x140042231  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140042236  nop
0x140042237  mov     rax, [rbp+lpText]
0x14004223b  movzx   ebx, word ptr [rax]
0x14004223e  sub     ebx, 31h ; '1'
0x140042241  jnz     short loc_14004224C
0x140042243  movzx   ebx, word ptr [rax+2]
0x140042247  movzx   ecx, si
0x14004224a  sub     ebx, ecx
0x14004224c  lea     rdx, [rax-18h]
0x140042250  or      r14d, 0FFFFFFFFh
0x140042254  mov     eax, r14d
0x140042257  lock xadd [rdx+10h], eax
0x14004225c  add     eax, r14d
0x14004225f  test    eax, eax
0x140042261  jg      short loc_14004226F
0x140042263  lfence
0x140042266  mov     rcx, [rdx]
0x140042269  mov     rax, [rcx]
0x14004226c  call    qword ptr [rax+8]
0x14004226f  test    ebx, ebx
0x140042271  jnz     short loc_14004227D
0x140042273  mov     eax, 8000FFFFh
0x140042278  jmp     loc_140042525
0x14004227d  mov     [r13+0], sil
0x140042281  mov     rdx, r15
0x140042284  call    _anonymous_namespace___ShouldShowMessage
0x140042289  mov     r15d, eax
0x14004228c  test    eax, eax
0x14004228e  js      loc_1400424C1
0x140042294  cmp     eax, 1
0x140042297  jnz     short loc_1400422A2
0x140042299  mov     [r13+0], al
0x14004229d  jmp     loc_14004251C
0x1400422a2  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400422a7  mov     rcx, rax
0x1400422aa  test    rax, rax
0x1400422ad  jz      loc_140042567
0x1400422b3  mov     rax, [rax]
0x1400422b6  call    qword ptr [rax+18h]
0x1400422b9  add     rax, 18h
0x1400422bd  mov     [rbp+lpCaption], rax
0x1400422c1  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400422c6  mov     rcx, rax
0x1400422c9  test    rax, rax
0x1400422cc  jz      loc_140042549
0x1400422d2  mov     rax, [rax]
0x1400422d5  call    qword ptr [rax+18h]
0x1400422d8  lea     rbx, [rax+18h]
0x1400422dc  mov     [rbp+lpText], rbx
0x1400422e0  lea     rcx, [rbp+lpCaption]
0x1400422e4  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400422e9  mov     r8d, 700Ch
0x1400422ef  mov     rdx, rdi
0x1400422f2  lea     rcx, [rbp+lpCaption]
0x1400422f6  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x1400422fb  test    eax, eax
0x1400422fd  jnz     short loc_14004232A
0x1400422ff  mov     r15d, 80070490h
0x140042305  lea     rdx, [rbx-18h]
0x140042309  mov     eax, r14d
0x14004230c  lock xadd [rdx+10h], eax
0x140042311  add     eax, r14d
0x140042314  test    eax, eax
0x140042316  jg      short loc_140042325
0x140042318  lfence
0x14004231b  mov     rcx, [rdx]
0x14004231e  mov     rax, [rcx]
0x140042321  call    qword ptr [rax+8]
0x140042324  nop
0x140042325  jmp     loc_140042185
0x14004232a  lea     rcx, [rbp+lpText]
0x14004232e  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140042333  mov     r8d, 700Eh
0x140042339  mov     rdx, rdi
0x14004233c  lea     rcx, [rbp+lpText]
0x140042340  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x140042345  test    eax, eax
0x140042347  jnz     short loc_140042359
0x140042349  mov     r15d, 80070490h
0x14004234f  mov     rdx, [rbp+lpText]
0x140042353  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140042357  jmp     short loc_140042309
0x140042359  mov     r9d, 134h; uType
0x14004235f  mov     rdi, [rbp+lpCaption]
0x140042363  mov     r8, rdi; lpCaption
0x140042366  mov     rbx, [rbp+lpText]
0x14004236a  mov     rdx, rbx; lpText
0x14004236d  xor     ecx, ecx; hWnd
0x14004236f  call    cs:__imp_MessageBoxW
0x140042375  cmp     eax, 6
0x140042378  jnz     loc_1400424DC
0x14004237e  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x140042382  call    cs:__imp_GetSystemTime
0x140042388  mov     [rbp+lpText], rsi
0x14004238c  lea     rax, [rbp+lpText]
0x140042390  mov     [rsp+60h+phkResult], rax; phkResult
0x140042395  mov     r9d, 20006h; samDesired
0x14004239b  xor     r8d, r8d; ulOptions
0x14004239e  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\VisualStudio\\17.0"
0x1400423a5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400423ac  call    cs:__imp_RegOpenKeyExW
0x1400423b2  test    eax, eax
0x1400423b4  jnz     short loc_1400423BC
0x1400423b6  mov     r12, [rbp+lpText]
0x1400423ba  jmp     short loc_1400423D9
0x1400423bc  movzx   r15d, ax
0x1400423c0  or      r15d, 80070000h
0x1400423c7  test    eax, eax
0x1400423c9  cmovle  r15d, eax
0x1400423cd  mov     r12, rsi
0x1400423d0  test    r15d, r15d
0x1400423d3  js      loc_140042482
0x1400423d9  lea     rdx, [rbp+FileTime]; lpFileTime
0x1400423dd  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1400423e1  call    cs:__imp_SystemTimeToFileTime
0x1400423e7  test    eax, eax
0x1400423e9  jnz     short loc_14004241B
0x1400423eb  call    cs:__imp_GetLastError
0x1400423f1  movzx   r15d, ax
0x1400423f5  or      r15d, 80070000h
0x1400423fc  test    eax, eax
0x1400423fe  cmovle  r15d, eax
0x140042402  test    r12, r12
0x140042405  jz      short loc_140042410
0x140042407  mov     rcx, r12; hKey
0x14004240a  call    cs:__imp_RegCloseKey
0x140042410  test    r15d, r15d
0x140042413  jns     loc_1400424D7
0x140042419  jmp     short loc_140042482
0x14004241b  mov     eax, [rbp+FileTime.dwHighDateTime]
0x14004241e  mov     dword ptr [rbp+lpText+4], eax
0x140042421  mov     eax, [rbp+FileTime.dwLowDateTime]
0x140042424  mov     dword ptr [rbp+lpText], eax
0x140042427  mov     rax, [rbp+lpText]
0x14004242b  mov     [rbp+lpText], rax
0x14004242f  mov     [rsp+60h+cbData], 8; cbData
0x140042437  lea     rax, [rbp+lpText]
0x14004243b  mov     [rsp+60h+phkResult], rax; lpData
0x140042440  mov     r9d, 0Bh; dwType
0x140042446  xor     r8d, r8d; Reserved
0x140042449  lea     rdx, aSetupmessageti; "SetupMessageTimestamp"
0x140042450  mov     rcx, r12; hKey
0x140042453  call    cs:__imp_RegSetValueExW
0x140042459  test    eax, eax
0x14004245b  jz      short loc_1400424C9
0x14004245d  movzx   r15d, ax
0x140042461  or      r15d, 80070000h
0x140042468  test    eax, eax
0x14004246a  cmovle  r15d, eax
0x14004246e  test    r15d, r15d
0x140042471  jns     short loc_1400424C9
0x140042473  test    r12, r12
0x140042476  jz      short loc_140042482
0x140042478  mov     rcx, r12; hKey
0x14004247b  call    cs:__imp_RegCloseKey
0x140042481  nop
0x140042482  lea     rdx, [rbx-18h]
0x140042486  mov     eax, r14d
0x140042489  lock xadd [rdx+10h], eax
0x14004248e  add     eax, r14d
0x140042491  test    eax, eax
0x140042493  jg      short loc_1400424A2
0x140042495  lfence
0x140042498  mov     rcx, [rdx]
0x14004249b  mov     rax, [rcx]
0x14004249e  call    qword ptr [rax+8]
0x1400424a1  nop
0x1400424a2  lea     rdx, [rdi-18h]
0x1400424a6  mov     eax, r14d
0x1400424a9  lock xadd [rdx+10h], eax
0x1400424ae  add     eax, r14d
0x1400424b1  test    eax, eax
0x1400424b3  jg      short loc_1400424C1
0x1400424b5  lfence
0x1400424b8  mov     rcx, [rdx]
0x1400424bb  mov     rax, [rcx]
0x1400424be  call    qword ptr [rax+8]
0x1400424c1  lfence
0x1400424c4  mov     eax, r15d
0x1400424c7  jmp     short loc_140042525
0x1400424c9  test    r12, r12
0x1400424cc  jz      short loc_1400424D7
0x1400424ce  mov     rcx, r12; hKey
0x1400424d1  call    cs:__imp_RegCloseKey
0x1400424d7  mov     byte ptr [r13+0], 1
0x1400424dc  lea     rdx, [rbx-18h]
0x1400424e0  mov     eax, r14d
  ... truncated ...
```
