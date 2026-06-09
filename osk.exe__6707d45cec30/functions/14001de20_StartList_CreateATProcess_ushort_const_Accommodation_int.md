# StartList::CreateATProcess(ushort const *,Accommodation *,int)

- ea: `0x14001de20`
- end: `0x14001e0d8`
- name: `?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z`
- size: `696`
- prototype: `int(StartList *__hidden this, const unsigned __int16 *, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140020938`

## callees

- `0x140009f28`
- `0x140013a34`
- `0x14001b068`
- `0x14001c494`
- `0x14001de20`
- `0x1400211d0`
- `0x1400255dc`
- `0x14002562c`
- `0x140025d70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001df07`
- `KERNEL32!GetLastError` at `0x14001df07`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14001defb`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14001defb`
- `msvcrt!free` at `0x14001dedd`
- `msvcrt!free` at `0x14001df1f`
- `msvcrt!free` at `0x14001df32`
- `msvcrt!free` at `0x14001e05d`
- `msvcrt!free` at `0x14001e089`
- `msvcrt!free` at `0x14001dedd`
- `msvcrt!free` at `0x14001df1f`
- `msvcrt!free` at `0x14001df32`
- `msvcrt!free` at `0x14001e05d`
- `msvcrt!free` at `0x14001e089`
- `SHELL32!ShellExecuteW` at `0x14001e004`
- `SHELL32!ShellExecuteW` at `0x14001e004`

## string_xrefs

- `0x14001df67`: `/launchnarratorupdates`
- `0x14001de65`: `StartList::CreateATProcess`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::CreateATProcess(StartList *this, const unsigned __int16 *a2, struct Accommodation *a3)
{
  const unsigned __int16 *v5; // r15
  char *v6; // rsi
  int v7; // edi
  void *v8; // rbx
  DWORD v9; // eax
  signed int LastError; // eax
  char IsEnabled; // al
  const unsigned __int16 *v12; // r9
  const wchar_t *v13; // rcx
  const wchar_t *v14; // rdx
  const wchar_t *v15; // rax
  HINSTANCE v16; // rsi
  char *v17; // rsi
  char *v18; // rsi
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Parameters[256]; // [rsp+60h] [rbp-A0h] BYREF

  v21 = 0;
  _Trace::_Trace((_Trace *)v22, L"StartList::CreateATProcess", &v21);
  if ( a2 && *a2 )
  {
    v5 = (const unsigned __int16 *)*((_QWORD *)a3 + 4);
    Block = 0;
    if ( (int)StringCchLengthW(a2, 0x7FFFFFFFu, (unsigned __int64 *)&Block) < 0 )
      goto LABEL_39;
    v6 = (char *)Block + 260;
    if ( (char *)Block + 260 < Block )
      goto LABEL_39;
    Block = 0;
    if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v6) )
    {
      free(Block);
      v7 = -2147024882;
LABEL_40:
      _Trace::~_Trace((_Trace *)v22);
      return (unsigned int)v7;
    }
    v8 = Block;
    v9 = ExpandEnvironmentStringsW(a2, (LPWSTR)Block, (DWORD)v6);
    v7 = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError <= 0 )
      {
LABEL_11:
        free(v8);
        goto LABEL_40;
      }
      v7 = (unsigned __int16)LastError;
LABEL_10:
      v7 |= 0x80070000;
      goto LABEL_11;
    }
    if ( v9 > (unsigned __int64)v6 )
    {
      free(v8);
      v7 = -2147024774;
      goto LABEL_40;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
    v12 = &qword_14002AAD0;
    v13 = L"/launchnarratorhome";
    v14 = L"/hardwarebuttonlaunch";
    if ( IsEnabled )
    {
      v15 = L"/launchnarratorupdates";
      if ( !*((_BYTE *)a3 + 86) )
        v15 = &qword_14002AAD0;
      if ( !*((_BYTE *)a3 + 85) )
        v13 = &qword_14002AAD0;
      if ( !*((_BYTE *)a3 + 84) )
        v14 = &qword_14002AAD0;
      if ( v5 )
        v12 = v5;
      StringCchPrintfW(Parameters, 0x100u, L"%s %s %s %s", v12, v14, v13, v15);
    }
    else
    {
      if ( !*((_BYTE *)a3 + 85) )
        v13 = &qword_14002AAD0;
      if ( !*((_BYTE *)a3 + 84) )
        v14 = &qword_14002AAD0;
      if ( v5 )
        v12 = v5;
      StringCchPrintfW(Parameters, 0x100u, L"%s %s %s", v12, v14, v13);
    }
    v16 = ShellExecuteW(0, 0, (LPCWSTR)v8, Parameters, 0, 5);
    if ( (__int64)v16 <= 32 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)&WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids,
          (_DWORD)v8,
          (char)v16);
      v17 = (char *)v16 - 2;
      if ( !v17 || (v18 = v17 - 1) == 0 || v18 == (char *)8 )
      {
        if ( v7 <= 0 )
          goto LABEL_11;
        v7 = (unsigned __int16)v7;
        goto LABEL_10;
      }
      free(v8);
LABEL_39:
      v7 = -2147467259;
      goto LABEL_40;
    }
    free(v8);
    _Trace::~_Trace((_Trace *)v22);
    return 0;
  }
  else
  {
    _Trace::~_Trace((_Trace *)v22);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14001de20  mov     [rsp-8+arg_0], rbx
0x14001de25  mov     [rsp-8+arg_18], rsi
0x14001de2a  push    rbp
0x14001de2b  push    rdi
0x14001de2c  push    r12
0x14001de2e  push    r14
0x14001de30  push    r15
0x14001de32  lea     rbp, [rsp-170h]
0x14001de3a  sub     rsp, 270h
0x14001de41  mov     rax, cs:__security_cookie
0x14001de48  xor     rax, rsp
0x14001de4b  mov     [rbp+190h+var_30], rax
0x14001de52  mov     r14, r8
0x14001de55  mov     rdi, rdx
0x14001de58  xor     r12d, r12d
0x14001de5b  mov     [rsp+290h+var_248], r12d
0x14001de60  lea     r8, [rsp+290h+var_248]; int *
0x14001de65  lea     rdx, aStartlistCreat; "StartList::CreateATProcess"
0x14001de6c  lea     rcx, [rsp+290h+var_240]; this
0x14001de71  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x14001de76  nop
0x14001de77  test    rdi, rdi
0x14001de7a  jz      loc_14001E09E
0x14001de80  cmp     [rdi], r12w
0x14001de84  jz      loc_14001E09E
0x14001de8a  mov     r15, [r14+20h]
0x14001de8e  mov     [rsp+290h+Block], r12
0x14001de93  lea     r8, [rsp+290h+Block]; unsigned __int64 *
0x14001de98  mov     edx, 7FFFFFFFh; unsigned __int64
0x14001de9d  mov     rcx, rdi; unsigned __int16 *
0x14001dea0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001dea5  test    eax, eax
0x14001dea7  js      loc_14001E063
0x14001dead  mov     rax, [rsp+290h+Block]
0x14001deb2  lea     rsi, [rax+104h]
0x14001deb9  cmp     rsi, rax
0x14001debc  jb      loc_14001E063
0x14001dec2  mov     [rsp+290h+Block], r12
0x14001dec7  mov     rdx, rsi
0x14001deca  lea     rcx, [rsp+290h+Block]
0x14001decf  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14001ded4  test    al, al
0x14001ded6  jnz     short loc_14001DEED
0x14001ded8  mov     rcx, [rsp+290h+Block]; Block
0x14001dedd  call    cs:__imp_free
0x14001dee3  mov     edi, 8007000Eh
0x14001dee8  jmp     loc_14001E068
0x14001deed  mov     r8d, esi; nSize
0x14001def0  mov     rbx, [rsp+290h+Block]
0x14001def5  mov     rdx, rbx; lpDst
0x14001def8  mov     rcx, rdi; lpSrc
0x14001defb  call    cs:__imp_ExpandEnvironmentStringsW
0x14001df01  mov     edi, eax
0x14001df03  test    eax, eax
0x14001df05  jnz     short loc_14001DF2A
0x14001df07  call    cs:__imp_GetLastError
0x14001df0d  mov     edi, eax
0x14001df0f  test    eax, eax
0x14001df11  jle     short loc_14001DF1C
0x14001df13  movzx   edi, ax
0x14001df16  or      edi, 80070000h
0x14001df1c  mov     rcx, rbx; Block
0x14001df1f  call    cs:__imp_free
0x14001df25  jmp     loc_14001E068
0x14001df2a  cmp     rdi, rsi
0x14001df2d  jbe     short loc_14001DF42
0x14001df2f  mov     rcx, rbx; Block
0x14001df32  call    cs:__imp_free
0x14001df38  mov     edi, 8007007Ah
0x14001df3d  jmp     loc_14001E068
0x14001df42  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x14001df49  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x14001df4e  lea     r9, qword_14002AAD0
0x14001df55  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x14001df5c  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x14001df63  test    al, al
0x14001df65  jz      short loc_14001DFB4
0x14001df67  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x14001df6e  cmp     [r14+56h], r12b
0x14001df72  cmovz   rax, r9
0x14001df76  cmp     [r14+55h], r12b
0x14001df7a  cmovz   rcx, r9
0x14001df7e  cmp     [r14+54h], r12b
0x14001df82  cmovz   rdx, r9
0x14001df86  test    r15, r15
0x14001df89  cmovnz  r9, r15
0x14001df8d  mov     [rsp+290h+var_260], rax
0x14001df92  mov     qword ptr [rsp+290h+nShowCmd], rcx
0x14001df97  mov     [rsp+290h+lpDirectory], rdx
0x14001df9c  lea     r8, aSSSS; "%s %s %s %s"
0x14001dfa3  mov     edx, 100h; unsigned __int64
0x14001dfa8  lea     rcx, [rsp+290h+Parameters]; unsigned __int16 *
0x14001dfad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001dfb2  jmp     short loc_14001DFEB
0x14001dfb4  cmp     [r14+55h], r12b
0x14001dfb8  cmovz   rcx, r9
0x14001dfbc  cmp     [r14+54h], r12b
0x14001dfc0  cmovz   rdx, r9
0x14001dfc4  test    r15, r15
0x14001dfc7  cmovnz  r9, r15
0x14001dfcb  mov     qword ptr [rsp+290h+nShowCmd], rcx
0x14001dfd0  mov     [rsp+290h+lpDirectory], rdx
0x14001dfd5  lea     r8, aSSS; "%s %s %s"
0x14001dfdc  mov     edx, 100h; unsigned __int64
0x14001dfe1  lea     rcx, [rsp+290h+Parameters]; unsigned __int16 *
0x14001dfe6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001dfeb  mov     [rsp+290h+nShowCmd], 5; nShowCmd
0x14001dff3  mov     [rsp+290h+lpDirectory], r12; lpDirectory
0x14001dff8  lea     r9, [rsp+290h+Parameters]; lpParameters
0x14001dffd  mov     r8, rbx; lpFile
0x14001e000  xor     edx, edx; lpOperation
0x14001e002  xor     ecx, ecx; hwnd
0x14001e004  call    cs:__imp_ShellExecuteW
0x14001e00a  mov     rsi, rax
0x14001e00d  cmp     rax, 20h ; ' '
0x14001e011  jg      short loc_14001E086
0x14001e013  lea     rax, WPP_GLOBAL_Control
0x14001e01a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e021  cmp     rcx, rax
0x14001e024  jz      short loc_14001E048
0x14001e026  test    byte ptr [rcx+1Ch], 8
0x14001e02a  jz      short loc_14001E048
0x14001e02c  mov     edx, 1Eh
0x14001e031  mov     dword ptr [rsp+290h+lpDirectory], esi
0x14001e035  mov     r9, rbx
0x14001e038  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001e03f  mov     rcx, [rcx+10h]
0x14001e043  call    WPP_SF_Sd
0x14001e048  sub     rsi, 2
0x14001e04c  jz      short loc_14001E076
0x14001e04e  sub     rsi, 1
0x14001e052  jz      short loc_14001E076
0x14001e054  cmp     rsi, 8
0x14001e058  jz      short loc_14001E076
0x14001e05a  mov     rcx, rbx; Block
0x14001e05d  call    cs:__imp_free
0x14001e063  mov     edi, 80004005h
0x14001e068  lea     rcx, [rsp+290h+var_240]; this
0x14001e06d  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14001e072  mov     eax, edi
0x14001e074  jmp     short loc_14001E0AD
0x14001e076  test    edi, edi
0x14001e078  jle     loc_14001DF1C
0x14001e07e  movzx   edi, di
0x14001e081  jmp     loc_14001DF16
0x14001e086  mov     rcx, rbx; Block
0x14001e089  call    cs:__imp_free
0x14001e08f  nop
0x14001e090  lea     rcx, [rsp+290h+var_240]; this
0x14001e095  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14001e09a  xor     eax, eax
0x14001e09c  jmp     short loc_14001E0AD
0x14001e09e  lea     rcx, [rsp+290h+var_240]; this
0x14001e0a3  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14001e0a8  mov     eax, 80070057h
0x14001e0ad  mov     rcx, [rbp+190h+var_30]
0x14001e0b4  xor     rcx, rsp; StackCookie
0x14001e0b7  call    __security_check_cookie
0x14001e0bc  lea     r11, [rsp+290h+var_20]
0x14001e0c4  mov     rbx, [r11+30h]
0x14001e0c8  mov     rsi, [r11+48h]
0x14001e0cc  mov     rsp, r11
0x14001e0cf  pop     r15
0x14001e0d1  pop     r14
0x14001e0d3  pop     r12
0x14001e0d5  pop     rdi
0x14001e0d6  pop     rbp
0x14001e0d7  retn
```
