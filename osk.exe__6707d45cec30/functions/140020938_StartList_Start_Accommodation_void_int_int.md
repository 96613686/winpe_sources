# StartList::Start(Accommodation *,void *,int,int)

- ea: `0x140020938`
- end: `0x140020d1c`
- name: `?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z`
- size: `996`
- prototype: `__int64 __usercall@<rax>(StartList *__hidden this@<rcx>, struct Accommodation *@<rdx>, void *@<r8>, int@<r9d>, int)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002091c`

## callees

- `0x1400045c8`
- `0x140005c90`
- `0x140009524`
- `0x140009938`
- `0x1400170d8`
- `0x14001c748`
- `0x14001c768`
- `0x14001c82c`
- `0x14001d250`
- `0x14001d298`
- `0x14001d930`
- `0x14001d9b8`
- `0x14001dab0`
- `0x14001de20`
- `0x14001e0e0`
- `0x14001e8b0`
- `0x14001f588`
- `0x14001f728`
- `0x14001fbb0`
- `0x140020374`
- `0x1400206b8`
- `0x14002091c`
- `0x140020938`
- `0x14002180c`
- `0x140021f84`
- `0x1400237b8`
- `0x140025184`
- `0x140025d42`

## import_xrefs

- `msvcrt!_wtoi` at `0x140020a1b`
- `msvcrt!_wtoi` at `0x140020a1b`

## string_xrefs

- `0x140020bc0`: `Software\Microsoft\Windows NT\CurrentVersion\AccessibilityTemp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Start *__fastcall StartList::Start(Start *this, const wchar_t **a2, void *a3, int a4, int a5)
{
  char v8; // r15
  Start *result; // rax
  unsigned int v10; // esi
  struct Accommodation *v11; // rax
  int v12; // eax
  StartList *v13; // rcx
  const unsigned __int16 *v14; // rbx
  unsigned int v15; // eax
  _QWORD *v16; // rax
  bool v17; // bl
  _QWORD *v18; // rax
  __int64 v19; // rbx
  _QWORD *v20; // rax
  WCHAR *v21; // rcx
  unsigned __int16 *v22; // r9
  int ATProcess; // eax
  StartList *v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // rbx
  _QWORD *v27; // rax
  int v28; // edx
  HKEY v29; // [rsp+38h] [rbp-D0h]
  HKEY v30[4]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v31[352]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE *v32; // [rsp+208h] [rbp+100h] BYREF

  HIDWORD(v32) = HIDWORD(a3);
  v8 = 0;
  LODWORD(v32) = 0;
  if ( !a2 )
    return (Start *)2147942487LL;
  result = (Start *)StartList::LoadSettings(this);
  v10 = (unsigned int)result;
  if ( (int)result >= 0 )
  {
    if ( (unsigned __int8)ATL::operator!=(a2 + 9) && !(unsigned int)CATUtils::IsInteractiveUser() )
    {
      if ( CATUtils::IsDesktopOOBEUserSessionActive() && !wcscmp_0(a2[5], L"SystemSetting") )
        StartList::Add(this, (struct Accommodation *)a2);
      v11 = Accommodation::Open(a2[9]);
      if ( v11 )
        return (Start *)StartList::Start(this, v11, 0, 0);
      else
        return (Start *)2147942414LL;
    }
    v12 = wcscmp_0(a2[5], L"SystemSetting");
    v14 = a2[3];
    if ( !v12 )
    {
      v15 = _wtoi(a2[3]);
      if ( v15 < 0x16 )
      {
        v10 = SystemSettings::TurnOn(a2, v15, 0, *((_DWORD *)this + 73));
        if ( (v10 & 0x80000000) == 0 )
        {
          v17 = 0;
          if ( (unsigned int)CATUtils::IsInteractiveUser() )
          {
            v16 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                              &v32,
                              a2);
            v8 = 1;
            if ( ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
                   this,
                   *v16) )
            {
              v17 = 1;
            }
          }
          if ( (v8 & 1) != 0 )
            ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
          if ( v17 )
          {
            v18 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                              &v32,
                              a2);
            v19 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
                    (char *)this + 48,
                    *v18);
            ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
            if ( !v19 )
            {
              v20 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                &v32,
                                a2);
              ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
                (char *)this + 48,
                *v20);
              ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
            }
            StartList::SaveSessionKey(this);
          }
          else if ( CATUtils::IsDesktopOOBEUserSessionActive() )
          {
            StartList::Add(this, (struct Accommodation *)a2);
          }
        }
      }
      return (Start *)v10;
    }
    if ( !v14 )
      return (Start *)2147500037LL;
    if ( a5 || StartList::IsColorFiltering(v13, (struct Accommodation *)a2) )
    {
      if ( StartList::IsColorFiltering(v13, (struct Accommodation *)a2) )
        ColorFiltering::ColorFilterHelper::UpdateActiveFilter();
    }
    else
    {
      if ( (unsigned int)CATUtils::IsInteractiveUser() && !CATUtils::IsProcessInATJob(v21) )
      {
        if ( *((_DWORD *)a2 + 16) )
        {
          memset(v30, 0, 24);
          if ( !(unsigned int)ATL::CRegKey::Create(
                                (ATL::CRegKey *)v30,
                                HKEY_CURRENT_USER,
                                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AccessibilityTemp",
                                v22,
                                1u,
                                0x2001Fu,
                                v29,
                                0) )
            ATL::CRegKey::SetDWORDValue(v30, *a2, 3);
          ATL::CRegKey::Close((ATL::CRegKey *)v30);
          SendWinkeyPlusU();
        }
        else if ( a4 )
        {
          StartList::CreateBreakawayATProcess(v21, (struct Accommodation *)a2, 1);
        }
        else
        {
          StartList::CreateATProcess((StartList *)v21, v14, (struct Accommodation *)a2);
        }
        return 0;
      }
      if ( *((_DWORD *)a2 + 16) || !(unsigned int)CATUtils::IsInteractiveUser() )
        ATProcess = StartList::CreateATProcess((StartList *)v21, v14, (struct Accommodation *)a2);
      else
        ATProcess = StartList::CreateBreakawayATProcess(v21, (struct Accommodation *)a2, 0);
      v10 = ATProcess;
      if ( ATProcess < 0 )
        return (Start *)v10;
    }
    StartList::LogAccomodationToSQM(v24, (struct Accommodation *)a2);
    if ( (unsigned int)CATUtils::IsInteractiveUser() )
    {
      v25 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                        &v32,
                        a2);
      v26 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              (char *)this + 48,
              *v25);
      ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
      if ( !v26 )
      {
        v27 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                          &v32,
                          a2);
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          (char *)this + 48,
          *v27);
        ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
      }
      StartList::SaveSessionKey(this);
      if ( *((_DWORD *)a2 + 17) || !*((_DWORD *)a2 + 16) )
      {
        ATManager::ATManager((ATManager *)v31, v28);
        v32 = v31;
        SettingsCopier::InteractiveDesktopCopy((SettingsCopier *)&v32);
        ATManager::~ATManager((ATManager *)v31);
      }
    }
    return (Start *)v10;
  }
  return result;
}

```

## disassembly

```asm
0x140020938  mov     rax, rsp
0x14002093b  mov     [rax+8], rbx
0x14002093f  mov     [rax+10h], rsi
0x140020943  mov     [rax+18h], r8
0x140020947  push    rbp
0x140020948  push    rdi
0x140020949  push    r12
0x14002094b  push    r14
0x14002094d  push    r15
0x14002094f  lea     rbp, [rax-0E8h]
0x140020956  sub     rsp, 1C0h
0x14002095d  mov     r12d, r9d
0x140020960  mov     rdi, rdx
0x140020963  mov     r14, rcx
0x140020966  xor     r15d, r15d
0x140020969  mov     dword ptr [rbp+0E0h+arg_10], r15d
0x140020970  test    rdx, rdx
0x140020973  jnz     short loc_14002097F
0x140020975  mov     eax, 80070057h
0x14002097a  jmp     loc_140020D00
0x14002097f  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x140020984  mov     esi, eax
0x140020986  test    eax, eax
0x140020988  js      loc_140020D00
0x14002098e  lea     rcx, [rdi+48h]
0x140020992  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBD@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,char const *)
0x140020997  test    al, al
0x140020999  jz      short loc_1400209FB
0x14002099b  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x1400209a0  test    eax, eax
0x1400209a2  jnz     short loc_1400209FB
0x1400209a4  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x1400209a9  test    al, al
0x1400209ab  jz      short loc_1400209CD
0x1400209ad  lea     rdx, aSystemsetting; "SystemSetting"
0x1400209b4  mov     rcx, [rdi+28h]; String1
0x1400209b8  call    wcscmp_0
0x1400209bd  nop
0x1400209be  test    eax, eax
0x1400209c0  jnz     short loc_1400209CD
0x1400209c2  mov     rdx, rdi; struct Accommodation *
0x1400209c5  mov     rcx, r14; this
0x1400209c8  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x1400209cd  mov     rcx, [rdi+48h]; unsigned __int16 *
0x1400209d1  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1400209d6  test    rax, rax
0x1400209d9  jnz     short loc_1400209E5
0x1400209db  mov     eax, 8007000Eh
0x1400209e0  jmp     loc_140020D00
0x1400209e5  xor     r9d, r9d; int
0x1400209e8  xor     r8d, r8d; int
0x1400209eb  mov     rdx, rax; struct Accommodation *
0x1400209ee  mov     rcx, r14; this
0x1400209f1  call    ?Start@StartList@@QEAAJPEAVAccommodation@@HH@Z; StartList::Start(Accommodation *,int,int)
0x1400209f6  jmp     loc_140020D00
0x1400209fb  lea     rdx, aSystemsetting; "SystemSetting"
0x140020a02  mov     rcx, [rdi+28h]; String1
0x140020a06  call    wcscmp_0
0x140020a0b  nop
0x140020a0c  mov     rbx, [rdi+18h]
0x140020a10  test    eax, eax
0x140020a12  jnz     loc_140020B21
0x140020a18  mov     rcx, rbx; String
0x140020a1b  call    cs:__imp__wtoi
0x140020a21  cmp     eax, 16h
0x140020a24  jnb     loc_140020CFE
0x140020a2a  mov     r9d, [r14+124h]
0x140020a31  xor     r8d, r8d
0x140020a34  mov     edx, eax
0x140020a36  mov     rcx, rdi
0x140020a39  call    ?TurnOn@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z; SystemSettings::TurnOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)
0x140020a3e  mov     esi, eax
0x140020a40  test    eax, eax
0x140020a42  js      loc_140020CFE
0x140020a48  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x140020a4d  test    eax, eax
0x140020a4f  jz      short loc_140020A7B
0x140020a51  mov     rdx, rdi
0x140020a54  lea     rcx, [rbp+0E0h+arg_10]
0x140020a5b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140020a60  mov     r15d, 1
0x140020a66  mov     rdx, [rax]
0x140020a69  mov     rcx, r14
0x140020a6c  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140020a71  test    rax, rax
0x140020a74  jz      short loc_140020A7B
0x140020a76  mov     bl, r15b
0x140020a79  jmp     short loc_140020A7D
0x140020a7b  xor     bl, bl
0x140020a7d  test    r15b, 1
0x140020a81  jz      short loc_140020A93
0x140020a83  mov     rcx, [rbp+0E0h+arg_10]
0x140020a8a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140020a8e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140020a93  test    bl, bl
0x140020a95  jz      short loc_140020B04
0x140020a97  mov     rdx, rdi
0x140020a9a  lea     rcx, [rbp+0E0h+arg_10]
0x140020aa1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140020aa6  mov     rdx, [rax]
0x140020aa9  lea     rcx, [r14+30h]
0x140020aad  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140020ab2  mov     rbx, rax
0x140020ab5  mov     rcx, [rbp+0E0h+arg_10]
0x140020abc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140020ac0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140020ac5  test    rbx, rbx
0x140020ac8  jnz     short loc_140020AF7
0x140020aca  mov     rdx, rdi
0x140020acd  lea     rcx, [rbp+0E0h+arg_10]
0x140020ad4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140020ad9  nop
0x140020ada  mov     rdx, [rax]
0x140020add  lea     rcx, [r14+30h]
0x140020ae1  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x140020ae6  nop
0x140020ae7  mov     rcx, [rbp+0E0h+arg_10]
0x140020aee  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140020af2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140020af7  mov     rcx, r14; this
0x140020afa  call    ?SaveSessionKey@StartList@@AEAAXXZ; StartList::SaveSessionKey(void)
0x140020aff  jmp     loc_140020CFE
0x140020b04  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x140020b09  test    al, al
0x140020b0b  jz      loc_140020CFE
0x140020b11  mov     rdx, rdi; struct Accommodation *
0x140020b14  mov     rcx, r14; this
0x140020b17  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x140020b1c  jmp     loc_140020CFE
0x140020b21  test    rbx, rbx
0x140020b24  jnz     short loc_140020B30
0x140020b26  mov     eax, 80004005h
0x140020b2b  jmp     loc_140020D00
0x140020b30  cmp     [rbp+0E0h+arg_20], 0
0x140020b37  jnz     loc_140020C36
0x140020b3d  mov     rdx, rdi; struct Accommodation *
0x140020b40  call    ?IsColorFiltering@StartList@@AEAA_NPEAVAccommodation@@@Z; StartList::IsColorFiltering(Accommodation *)
0x140020b45  test    al, al
0x140020b47  jnz     loc_140020C36
0x140020b4d  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x140020b52  test    eax, eax
0x140020b54  jz      loc_140020C03
0x140020b5a  call    ?IsProcessInATJob@CATUtils@@SAHPEAX@Z; CATUtils::IsProcessInATJob(void *)
0x140020b5f  test    eax, eax
0x140020b61  jnz     loc_140020C03
0x140020b67  cmp     [rdi+40h], eax
0x140020b6a  jnz     short loc_140020B8C
0x140020b6c  test    r12d, r12d
0x140020b6f  jz      short loc_140020B7F
0x140020b71  lea     r8d, [rax+1]; int
0x140020b75  mov     rdx, rdi; struct Accommodation *
0x140020b78  call    ?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z; StartList::CreateBreakawayATProcess(Accommodation *,int)
0x140020b7d  jmp     short loc_140020BFC
0x140020b7f  mov     r8, rdi; struct Accommodation *
0x140020b82  mov     rdx, rbx; unsigned __int16 *
0x140020b85  call    ?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z; StartList::CreateATProcess(ushort const *,Accommodation *,int)
0x140020b8a  jmp     short loc_140020BFC
0x140020b8c  mov     [rsp+1E0h+var_1A0], 0
0x140020b95  mov     [rsp+1E0h+var_198], 0
0x140020b9e  mov     [rsp+1E0h+var_190], 0
0x140020ba7  mov     [rsp+1E0h+var_1A8], 0; unsigned int *
0x140020bb0  mov     [rsp+1E0h+var_1B8], 2001Fh; REGSAM
0x140020bb8  mov     [rsp+1E0h+var_1C0], 1; DWORD
0x140020bc0  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x140020bc7  mov     rdx, 0FFFFFFFF80000001h; hKey
0x140020bce  lea     rcx, [rsp+1E0h+var_1A0]; this
0x140020bd3  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140020bd8  test    eax, eax
0x140020bda  jnz     short loc_140020BED
0x140020bdc  lea     r8d, [rax+3]; unsigned int
0x140020be0  mov     rdx, [rdi]; unsigned __int16 *
0x140020be3  lea     rcx, [rsp+1E0h+var_1A0]; this
0x140020be8  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x140020bed  lea     rcx, [rsp+1E0h+var_1A0]; this
0x140020bf2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140020bf7  call    ?SendWinkeyPlusU@@YAXXZ; SendWinkeyPlusU(void)
0x140020bfc  xor     eax, eax
0x140020bfe  jmp     loc_140020D00
0x140020c03  cmp     dword ptr [rdi+40h], 0
0x140020c07  jnz     short loc_140020C1F
0x140020c09  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x140020c0e  test    eax, eax
0x140020c10  jz      short loc_140020C1F
0x140020c12  xor     r8d, r8d; int
0x140020c15  mov     rdx, rdi; struct Accommodation *
0x140020c18  call    ?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z; StartList::CreateBreakawayATProcess(Accommodation *,int)
0x140020c1d  jmp     short loc_140020C2A
0x140020c1f  mov     r8, rdi; struct Accommodation *
0x140020c22  mov     rdx, rbx; unsigned __int16 *
0x140020c25  call    ?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z; StartList::CreateATProcess(ushort const *,Accommodation *,int)
0x140020c2a  mov     esi, eax
0x140020c2c  test    eax, eax
0x140020c2e  js      loc_140020CFE
0x140020c34  jmp     short loc_140020C47
0x140020c36  mov     rdx, rdi; struct Accommodation *
0x140020c39  call    ?IsColorFiltering@StartList@@AEAA_NPEAVAccommodation@@@Z; StartList::IsColorFiltering(Accommodation *)
0x140020c3e  test    al, al
0x140020c40  jz      short loc_140020C47
0x140020c42  call    ?UpdateActiveFilter@ColorFilterHelper@ColorFiltering@@SAXXZ; ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)
0x140020c47  mov     rdx, rdi; struct Accommodation *
0x140020c4a  call    ?LogAccomodationToSQM@StartList@@AEAAXPEAVAccommodation@@@Z; StartList::LogAccomodationToSQM(Accommodation *)
0x140020c4f  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x140020c54  test    eax, eax
0x140020c56  jz      loc_140020CFE
0x140020c5c  mov     rdx, rdi
0x140020c5f  lea     rcx, [rbp+0E0h+arg_10]
0x140020c66  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140020c6b  mov     rdx, [rax]
0x140020c6e  lea     rcx, [r14+30h]
0x140020c72  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140020c77  mov     rbx, rax
0x140020c7a  mov     rcx, [rbp+0E0h+arg_10]
0x140020c81  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140020c85  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140020c8a  test    rbx, rbx
0x140020c8d  jnz     short loc_140020CBC
0x140020c8f  mov     rdx, rdi
0x140020c92  lea     rcx, [rbp+0E0h+arg_10]
0x140020c99  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140020c9e  nop
0x140020c9f  mov     rdx, [rax]
0x140020ca2  lea     rcx, [r14+30h]
0x140020ca6  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x140020cab  nop
0x140020cac  mov     rcx, [rbp+0E0h+arg_10]
0x140020cb3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140020cb7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140020cbc  mov     rcx, r14; this
0x140020cbf  call    ?SaveSessionKey@StartList@@AEAAXXZ; StartList::SaveSessionKey(void)
0x140020cc4  cmp     dword ptr [rdi+44h], 0
0x140020cc8  jnz     short loc_140020CD0
0x140020cca  cmp     dword ptr [rdi+40h], 0
0x140020cce  jnz     short loc_140020CFE
0x140020cd0  lea     rcx, [rsp+1E0h+var_180]; this
0x140020cd5  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x140020cda  nop
0x140020cdb  lea     rax, [rsp+1E0h+var_180]
0x140020ce0  mov     [rbp+0E0h+arg_10], rax
0x140020ce7  lea     rcx, [rbp+0E0h+arg_10]; this
0x140020cee  call    ?InteractiveDesktopCopy@SettingsCopier@@QEAAJXZ; SettingsCopier::InteractiveDesktopCopy(void)
0x140020cf3  nop
0x140020cf4  lea     rcx, [rsp+1E0h+var_180]; this
0x140020cf9  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x140020cfe  mov     eax, esi
0x140020d00  lea     r11, [rsp+1E0h+var_20]
0x140020d08  mov     rbx, [r11+30h]
0x140020d0c  mov     rsi, [r11+38h]
0x140020d10  mov     rsp, r11
0x140020d13  pop     r15
0x140020d15  pop     r14
0x140020d17  pop     r12
0x140020d19  pop     rdi
0x140020d1a  pop     rbp
0x140020d1b  retn
```
