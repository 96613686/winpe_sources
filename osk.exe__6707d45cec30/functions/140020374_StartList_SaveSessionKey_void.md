# StartList::SaveSessionKey(void)

- ea: `0x140020374`
- end: `0x1400205a1`
- name: `?SaveSessionKey@StartList@@AEAAXXZ`
- size: `557`
- prototype: `void __fastcall(StartList *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x140020938`
- `0x140020d24`

## callees

- `0x140004700`
- `0x140005c90`
- `0x140007e90`
- `0x140009524`
- `0x14000df20`
- `0x14000df60`
- `0x1400170d8`
- `0x14001b068`
- `0x14001caa4`
- `0x14001cb58`
- `0x14001dc50`
- `0x140020374`
- `0x1400255dc`
- `0x14002562c`

## string_xrefs

- `0x1400204ab`: `SecureConfiguration`
- `0x140020504`: `Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall StartList::SaveSessionKey(StartList *this)
{
  char v2; // si
  LPCWSTR *v3; // rax
  int v4; // ebx
  LPCWSTR *v5; // rax
  unsigned __int16 *v6; // r9
  int v7; // ebx
  _QWORD *v8; // rax
  ATL::CStringData *v9; // rcx
  unsigned int v10; // eax
  unsigned __int16 *v11; // rbx
  unsigned int v12; // eax
  HKEY v13; // [rsp+30h] [rbp-40h]
  _BYTE v14[16]; // [rsp+40h] [rbp-30h] BYREF
  HKEY v15[4]; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v16; // [rsp+98h] [rbp+28h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+30h] BYREF

  v2 = 0;
  LODWORD(v16) = 0;
  _Trace::_Trace((_Trace *)v14, L"StartList::SaveSessionKey", 0);
  memset(v15, 0, 24);
  v3 = (LPCWSTR *)CATUtils::SessionKeyString((__int64)&v16);
  v4 = ATL::CRegKey::Open((ATL::CRegKey *)v15, HKEY_LOCAL_MACHINE, *v3, 0x20006u);
  ATL::CStringData::Release((ATL::CStringData *)(v16 - 12));
  if ( !v4
    || (v5 = (LPCWSTR *)CATUtils::SessionKeyString((__int64)&v17),
        v7 = ATL::CRegKey::Create((ATL::CRegKey *)v15, HKEY_LOCAL_MACHINE, *v5, v6, 1u, 3u, v13, (unsigned int *)&v16),
        ATL::CStringData::Release((ATL::CStringData *)(v17 - 24)),
        !v7) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v16);
    StartList::BuildConfigString(&v16, (char *)this + 96);
    v10 = ATL::CRegKey::SetStringValue(v15, L"SecureConfiguration", (const BYTE *)v16);
    if ( v10 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v10);
    StartList::BuildConfigString(&v16, (char *)this + 48);
    v11 = v16;
    v12 = ATL::CRegKey::SetStringValue(v15, StartList::_configuration, (const BYTE *)v16);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v12);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v11);
    }
    v9 = (ATL::CStringData *)(v11 - 12);
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v8 = (_QWORD *)CATUtils::SessionKeyString((__int64)&v16);
    v2 = 1;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)&WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids,
      *v8,
      v7);
  }
  if ( (v2 & 1) != 0 )
  {
    v9 = (ATL::CStringData *)(v16 - 12);
LABEL_20:
    ATL::CStringData::Release(v9);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v15);
  _Trace::~_Trace((_Trace *)v14);
}

```

## disassembly

```asm
0x140020374  mov     [rsp-18h+arg_0], rbx
0x140020379  mov     [rsp-18h+arg_18], rsi
0x14002037e  push    rbp
0x14002037f  push    rdi
0x140020380  push    r14
0x140020382  mov     rbp, rsp
0x140020385  sub     rsp, 70h
0x140020389  mov     r14, rcx
0x14002038c  xor     esi, esi
0x14002038e  mov     dword ptr [rbp+arg_8], esi
0x140020391  xor     r8d, r8d; int *
0x140020394  lea     rdx, aStartlistSaves; "StartList::SaveSessionKey"
0x14002039b  lea     rcx, [rbp+var_30]; this
0x14002039f  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x1400203a4  nop
0x1400203a5  mov     [rbp+var_20], rsi
0x1400203a9  mov     [rbp+var_18], rsi
0x1400203ad  mov     [rbp+var_10], rsi
0x1400203b1  lea     rcx, [rbp+arg_8]
0x1400203b5  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x1400203ba  mov     r9d, 20006h; unsigned int
0x1400203c0  mov     r8, [rax]; lpSubKey
0x1400203c3  mov     rdi, 0FFFFFFFF80000002h
0x1400203ca  mov     rdx, rdi; hKey
0x1400203cd  lea     rcx, [rbp+var_20]; this
0x1400203d1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400203d6  mov     ebx, eax
0x1400203d8  mov     rcx, [rbp+arg_8]
0x1400203dc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400203e0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400203e5  test    ebx, ebx
0x1400203e7  jz      loc_140020490
0x1400203ed  lea     rcx, [rbp+arg_10]
0x1400203f1  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x1400203f6  lea     rcx, [rbp+arg_8]
0x1400203fa  mov     [rsp+70h+var_38], rcx; unsigned int *
0x1400203ff  mov     [rsp+70h+var_48], 3; REGSAM
0x140020407  mov     [rsp+70h+var_50], 1; DWORD
0x14002040f  mov     r8, [rax]; lpSubKey
0x140020412  mov     rdx, rdi; hKey
0x140020415  lea     rcx, [rbp+var_20]; this
0x140020419  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14002041e  mov     ebx, eax
0x140020420  mov     rcx, [rbp+arg_10]
0x140020424  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140020428  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14002042d  test    ebx, ebx
0x14002042f  jz      short loc_140020490
0x140020431  lea     rdi, WPP_GLOBAL_Control
0x140020438  mov     rcx, cs:WPP_GLOBAL_Control
0x14002043f  cmp     rcx, rdi
0x140020442  jz      short loc_140020479
0x140020444  test    byte ptr [rcx+1Ch], 8
0x140020448  jz      short loc_140020479
0x14002044a  lea     rcx, [rbp+arg_8]
0x14002044e  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x140020453  mov     esi, 1
0x140020458  lea     edx, [rsi+18h]
0x14002045b  mov     [rsp+70h+var_50], ebx
0x14002045f  mov     r9, [rax]
0x140020462  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x140020469  mov     rcx, cs:WPP_GLOBAL_Control
0x140020470  mov     rcx, [rcx+10h]
0x140020474  call    WPP_SF_Sd
0x140020479  test    sil, 1
0x14002047d  jz      loc_140020579
0x140020483  mov     rcx, [rbp+arg_8]
0x140020487  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14002048b  jmp     loc_140020573
0x140020490  lea     rcx, [rbp+arg_8]
0x140020494  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140020499  nop
0x14002049a  lea     rdx, [r14+60h]
0x14002049e  lea     rcx, [rbp+arg_8]
0x1400204a2  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x1400204a7  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x1400204ab  lea     rdx, ?c_secureConfiguration@StartList@@0QBGB; "SecureConfiguration"
0x1400204b2  lea     rcx, [rbp+var_20]; this
0x1400204b6  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x1400204bb  lea     rdi, WPP_GLOBAL_Control
0x1400204c2  test    eax, eax
0x1400204c4  jz      short loc_1400204F0
0x1400204c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400204cd  cmp     rcx, rdi
0x1400204d0  jz      short loc_1400204F0
0x1400204d2  test    byte ptr [rcx+1Ch], 8
0x1400204d6  jz      short loc_1400204F0
0x1400204d8  mov     edx, 1Ah
0x1400204dd  mov     r9d, eax
0x1400204e0  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400204e7  mov     rcx, [rcx+10h]
0x1400204eb  call    WPP_SF_d
0x1400204f0  lea     rdx, [r14+30h]
0x1400204f4  lea     rcx, [rbp+arg_8]
0x1400204f8  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x1400204fd  mov     rbx, [rbp+arg_8]
0x140020501  mov     r8, rbx; unsigned __int16 *
0x140020504  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x14002050b  lea     rcx, [rbp+var_20]; this
0x14002050f  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x140020514  test    eax, eax
0x140020516  jz      short loc_140020544
0x140020518  mov     rcx, cs:WPP_GLOBAL_Control
0x14002051f  cmp     rcx, rdi
0x140020522  jz      short loc_14002056F
0x140020524  test    byte ptr [rcx+1Ch], 8
0x140020528  jz      short loc_14002056F
0x14002052a  mov     edx, 1Bh
0x14002052f  mov     r9d, eax
0x140020532  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x140020539  mov     rcx, [rcx+10h]
0x14002053d  call    WPP_SF_d
0x140020542  jmp     short loc_14002056F
0x140020544  mov     rcx, cs:WPP_GLOBAL_Control
0x14002054b  cmp     rcx, rdi
0x14002054e  jz      short loc_14002056F
0x140020550  test    byte ptr [rcx+1Ch], 10h
0x140020554  jz      short loc_14002056F
0x140020556  mov     edx, 1Ch
0x14002055b  mov     r9, rbx
0x14002055e  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x140020565  mov     rcx, [rcx+10h]
0x140020569  call    WPP_SF_S
0x14002056e  nop
0x14002056f  lea     rcx, [rbx-18h]; this
0x140020573  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140020578  nop
0x140020579  lea     rcx, [rbp+var_20]; this
0x14002057d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140020582  nop
0x140020583  lea     rcx, [rbp+var_30]; this
0x140020587  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14002058c  lea     r11, [rsp+70h+var_s0]
0x140020591  mov     rbx, [r11+20h]
0x140020595  mov     rsi, [r11+38h]
0x140020599  mov     rsp, r11
0x14002059c  pop     r14
0x14002059e  pop     rdi
0x14002059f  pop     rbp
0x1400205a0  retn
```
