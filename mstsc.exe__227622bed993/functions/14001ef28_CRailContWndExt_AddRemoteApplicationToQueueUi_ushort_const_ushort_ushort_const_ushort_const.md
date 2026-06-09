# CRailContWndExt::AddRemoteApplicationToQueueUi(ushort const *,ushort *,ushort const *,ushort const *)

- ea: `0x14001ef28`
- end: `0x14001f3ac`
- name: `?AddRemoteApplicationToQueueUi@CRailContWndExt@@AEAAJPEBGPEAG00@Z`
- size: `1156`
- prototype: `__int64 __usercall@<rax>(CRailContWndExt *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400222d0`
- `0x140025770`

## callees

- `0x140003b14`
- `0x140003b20`
- `0x140004703`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001ef28`
- `0x14002522c`
- `0x140025fc4`
- `0x14009d6f8`
- `0x1400b1d80`

## import_xrefs

- `USER32!DestroyIcon` at `0x14001f2e5`
- `USER32!DestroyIcon` at `0x14001f377`
- `USER32!DestroyIcon` at `0x14001f2e5`
- `USER32!DestroyIcon` at `0x14001f377`
- `USER32!LoadImageW` at `0x14001efbd`
- `USER32!LoadImageW` at `0x14001efbd`
- `USER32!LoadIconW` at `0x14001f02d`
- `USER32!LoadIconW` at `0x14001f02d`
- `USER32!SetForegroundWindow` at `0x14001f352`
- `USER32!SetForegroundWindow` at `0x14001f352`
- `USER32!SendMessageW` at `0x14001f27f`
- `USER32!SendMessageW` at `0x14001f27f`
- `SHLWAPI!PathIsNetworkPathW` at `0x14001ef9c`
- `SHLWAPI!PathIsNetworkPathW` at `0x14001ef9c`
- `KERNEL32!LocalFree` at `0x14001f389`
- `KERNEL32!LocalFree` at `0x14001f389`
- `COMCTL32!ImageList_ReplaceIcon` at `0x14001f043`
- `COMCTL32!ImageList_ReplaceIcon` at `0x14001f043`

## string_xrefs

- `0x14001ef7a`: `AllowRemoteAppIconFromNetworkPath`
- `0x14001f208`: `StringCchCopy failed!`

## pseudocode

```c
__int64 __fastcall CRailContWndExt::AddRemoteApplicationToQueueUi(
        CRailContWndExt *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  unsigned __int16 *v7; // r12
  int RegistryInt; // eax
  HICON IconW; // rbp
  int v10; // r13d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v12; // eax
  __int64 v13; // r15
  unsigned int v14; // eax
  int v15; // ebx
  unsigned int v16; // eax
  void *v17; // rcx
  unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rbx
  __int64 v20; // rax
  unsigned __int64 v21; // r14
  unsigned __int16 *v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // eax
  HWND v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // eax
  LPARAM lParam[4]; // [rsp+30h] [rbp-98h] BYREF
  int v30; // [rsp+54h] [rbp-74h]
  unsigned __int16 *v31; // [rsp+58h] [rbp-70h]

  memset_0(lParam, 0, 0x58u);
  v7 = 0;
  if ( (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88443>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MSRC88443>::GetImpl'::`2'::impl)
     || (RegistryInt = CUT::UT_ReadRegistryInt(L"RemoteApplications", L"AllowRemoteAppIconFromNetworkPath", 0, 1), a2)
     && (RegistryInt || !PathIsNetworkPathW(a2)))
    && (IconW = (HICON)LoadImageW(0, a2, 1u, 0, 0, 0x2050u)) != 0 )
  {
    v10 = 1;
  }
  else
  {
    v10 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    IconW = LoadIconW(*(HINSTANCE *)(*((_QWORD *)this + 8) + 2664LL), (LPCWSTR)0x65);
  }
  v12 = ImageList_ReplaceIcon(*((HIMAGELIST *)this + 18), -1, IconW);
  v13 = v12;
  if ( v12 == -1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(v13 + 35),
        &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
        v14,
        -2147467259);
    }
LABEL_17:
    v15 = -2147467259;
    goto LABEL_60;
  }
  if ( v12 >= 32 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v16, v13);
    }
    goto LABEL_17;
  }
  v17 = (void *)*((_QWORD *)this + v12 + 19);
  if ( v17 )
  {
    operator delete(v17);
    *((_QWORD *)this + v13 + 19) = 0;
  }
  if ( v10 )
  {
    v18 = (unsigned __int16 *)operator new[](0x208u);
    *((_QWORD *)this + v13 + 19) = v18;
    if ( v18 )
      StringCchCopyW(v18, 0x104u, a2);
  }
  v19 = a5;
  if ( !*a5 )
    v19 = a4;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  v21 = v20 + 1;
  v22 = (unsigned __int16 *)MIDL_user_allocate(2 * (v20 + 1));
  v7 = v22;
  if ( v22 )
  {
    v15 = StringCchCopyW(v22, v21, v19);
    if ( v15 >= 0 )
    {
      memset_0(lParam, 0, 0x58u);
      v25 = (HWND)*((_QWORD *)this + 17);
      lParam[3] = (LPARAM)a3;
      LODWORD(lParam[0]) = 7;
      v30 = v13;
      v31 = v7;
      if ( (unsigned int)SendMessageW(v25, 0x104Du, 0, (LPARAM)lParam) == -1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v26, v15);
        }
        goto LABEL_17;
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88443>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MSRC88443>::GetImpl'::`2'::impl)
        && v10
        && IconW )
      {
        DestroyIcon(IconW);
      }
      if ( (*((_BYTE *)this + 2068) & 0x40) == 0 )
        CRailContWndExt::ShowConQueuePane(this, 1);
      if ( (*((_BYTE *)this + 2068) & 2) == 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v27);
        }
        SetForegroundWindow(*(HWND *)(*((_QWORD *)this + 7) + 8LL));
      }
      v15 = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)&WPP_054707ce312e306d358833de4c0f150b_Traceguids,
        v24,
        (__int64)"StringCchCopy failed!",
        v15);
    }
  }
  else
  {
    v15 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v23, v21);
    }
  }
LABEL_60:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88443>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MSRC88443>::GetImpl'::`2'::impl)
    && v10
    && IconW )
  {
    DestroyIcon(IconW);
  }
  if ( v15 < 0 && v7 )
    LocalFree(v7);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14001ef28  mov     [rsp+arg_0], rbx
0x14001ef2d  mov     [rsp+arg_18], r9
0x14001ef32  mov     [rsp+arg_10], r8
0x14001ef37  push    rbp
0x14001ef38  push    rsi
0x14001ef39  push    rdi
0x14001ef3a  push    r12
0x14001ef3c  push    r13
0x14001ef3e  push    r14
0x14001ef40  push    r15
0x14001ef42  sub     rsp, 90h
0x14001ef49  mov     r14, rdx
0x14001ef4c  mov     rsi, rcx
0x14001ef4f  xor     edx, edx; Val
0x14001ef51  lea     rcx, [rsp+0C8h+lParam]; void *
0x14001ef56  lea     r8d, [rdx+58h]; Size
0x14001ef5a  call    memset_0
0x14001ef5f  xor     ebx, ebx
0x14001ef61  mov     r12d, ebx
0x14001ef64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MSRC88443@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MSRC88443@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88443> `wil::Feature<__WilFeatureTraits_Feature_MSRC88443>::GetImpl(void)'::`2'::impl
0x14001ef6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MSRC88443@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88443>::__private_IsEnabled(void)
0x14001ef70  lea     edi, [rbx+1]
0x14001ef73  test    al, al
0x14001ef75  jz      short loc_14001EFA6
0x14001ef77  mov     r9d, edi
0x14001ef7a  lea     rdx, aAllowremoteapp; "AllowRemoteAppIconFromNetworkPath"
0x14001ef81  xor     r8d, r8d
0x14001ef84  lea     rcx, aRemoteapplicat_9; "RemoteApplications"
0x14001ef8b  call    ?UT_ReadRegistryInt@CUT@@SAHPEBG0HW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryInt(ushort const *,ushort const *,int,UT_REGREAD_LOCATION)
0x14001ef90  test    r14, r14
0x14001ef93  jz      short loc_14001EFD7
0x14001ef95  test    eax, eax
0x14001ef97  jnz     short loc_14001EFA6
0x14001ef99  mov     rcx, r14; pszPath
0x14001ef9c  call    cs:__imp_PathIsNetworkPathW
0x14001efa2  test    eax, eax
0x14001efa4  jnz     short loc_14001EFD7
0x14001efa6  mov     [rsp+0C8h+fuLoad], 2050h; fuLoad
0x14001efae  xor     r9d, r9d; cx
0x14001efb1  mov     r8d, edi; type
0x14001efb4  mov     [rsp+0C8h+cy], ebx; cy
0x14001efb8  mov     rdx, r14; name
0x14001efbb  xor     ecx, ecx; hInst
0x14001efbd  call    cs:__imp_LoadImageW
0x14001efc3  mov     rbp, rax
0x14001efc6  test    rax, rax
0x14001efc9  jz      short loc_14001EFD7
0x14001efcb  mov     r13d, edi
0x14001efce  lea     rbx, WPP_GLOBAL_Control
0x14001efd5  jmp     short loc_14001F036
0x14001efd7  mov     rax, cs:WPP_GLOBAL_Control
0x14001efde  mov     r13d, ebx
0x14001efe1  lea     rbx, WPP_GLOBAL_Control
0x14001efe8  cmp     rax, rbx
0x14001efeb  jz      short loc_14001F01D
0x14001efed  test    [rax+1Ch], dil
0x14001eff1  jz      short loc_14001F01D
0x14001eff3  cmp     byte ptr [rax+19h], 3
0x14001eff7  jb      short loc_14001F01D
0x14001eff9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001effe  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f005  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001f00c  mov     edx, 21h ; '!'
0x14001f011  mov     r9d, eax
0x14001f014  mov     rcx, [rcx+10h]
0x14001f018  call    WPP_SF_d
0x14001f01d  mov     rcx, [rsi+40h]
0x14001f021  mov     edx, 65h ; 'e'; lpIconName
0x14001f026  mov     rcx, [rcx+0A68h]; hInstance
0x14001f02d  call    cs:__imp_LoadIconW
0x14001f033  mov     rbp, rax
0x14001f036  mov     rcx, [rsi+90h]; himl
0x14001f03d  mov     r8, rbp; hicon
0x14001f040  or      edx, 0FFFFFFFFh; i
0x14001f043  call    cs:__imp_ImageList_ReplaceIcon
0x14001f049  movsxd  r15, eax
0x14001f04c  cmp     r15d, 0FFFFFFFFh
0x14001f050  jnz     short loc_14001F09F
0x14001f052  mov     rax, cs:WPP_GLOBAL_Control
0x14001f059  cmp     rax, rbx
0x14001f05c  jz      short loc_14001F095
0x14001f05e  test    [rax+1Ch], dil
0x14001f062  jz      short loc_14001F095
0x14001f064  cmp     byte ptr [rax+19h], 2
0x14001f068  jb      short loc_14001F095
0x14001f06a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001f06f  lea     edx, [r15+23h]
0x14001f073  mov     [rsp+0C8h+cy], 80004005h
0x14001f07b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f082  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001f089  mov     r9d, eax
0x14001f08c  mov     rcx, [rcx+10h]
0x14001f090  call    WPP_SF_Dd
0x14001f095  mov     ebx, 80004005h
0x14001f09a  jmp     loc_14001F35A
0x14001f09f  cmp     r15d, 20h ; ' '
0x14001f0a3  jl      short loc_14001F0E8
0x14001f0a5  mov     rax, cs:WPP_GLOBAL_Control
0x14001f0ac  cmp     rax, rbx
0x14001f0af  jz      short loc_14001F095
0x14001f0b1  test    [rax+1Ch], dil
0x14001f0b5  jz      short loc_14001F095
0x14001f0b7  cmp     byte ptr [rax+19h], 2
0x14001f0bb  jb      short loc_14001F095
0x14001f0bd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001f0c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f0c9  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001f0d0  mov     edx, 23h ; '#'
0x14001f0d5  mov     [rsp+0C8h+cy], r15d
0x14001f0da  mov     r9d, eax
0x14001f0dd  mov     rcx, [rcx+10h]
0x14001f0e1  call    WPP_SF_Dd
0x14001f0e6  jmp     short loc_14001F095
0x14001f0e8  mov     rcx, [rsi+r15*8+98h]; Block
0x14001f0f0  test    rcx, rcx
0x14001f0f3  jz      short loc_14001F102
0x14001f0f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001f0fa  mov     [rsi+r15*8+98h], r12
0x14001f102  test    r13d, r13d
0x14001f105  jz      short loc_14001F12E
0x14001f107  mov     ecx, 208h; unsigned __int64
0x14001f10c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001f111  mov     [rsi+r15*8+98h], rax
0x14001f119  test    rax, rax
0x14001f11c  jz      short loc_14001F12E
0x14001f11e  mov     r8, r14; unsigned __int16 *
0x14001f121  mov     edx, 104h; unsigned __int64
0x14001f126  mov     rcx, rax; unsigned __int16 *
0x14001f129  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001f12e  mov     rbx, [rsp+0C8h+arg_20]
0x14001f136  cmp     [rbx], r12w
0x14001f13a  cmovz   rbx, [rsp+0C8h+arg_18]
0x14001f143  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001f147  inc     rax
0x14001f14a  cmp     [rbx+rax*2], r12w
0x14001f14f  jnz     short loc_14001F147
0x14001f151  lea     r14, [rax+1]
0x14001f155  lea     rcx, [r14+r14]; size
0x14001f159  call    MIDL_user_allocate
0x14001f15e  mov     r12, rax
0x14001f161  test    rax, rax
0x14001f164  jnz     short loc_14001F1C4
0x14001f166  mov     ebx, 8007000Eh
0x14001f16b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f172  lea     rdx, WPP_GLOBAL_Control
0x14001f179  cmp     rcx, rdx
0x14001f17c  jz      loc_14001F35A
0x14001f182  test    [rcx+1Ch], dil
0x14001f186  jz      loc_14001F35A
0x14001f18c  cmp     byte ptr [rcx+19h], 2
0x14001f190  jb      loc_14001F35A
0x14001f196  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001f19b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f1a2  lea     edx, [r12+24h]
0x14001f1a7  mov     r9d, eax
0x14001f1aa  mov     [rsp+0C8h+cy], r14d
0x14001f1af  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001f1b6  mov     rcx, [rcx+10h]
0x14001f1ba  call    WPP_SF_Dd
0x14001f1bf  jmp     loc_14001F35A
0x14001f1c4  mov     r8, rbx; unsigned __int16 *
0x14001f1c7  mov     rdx, r14; unsigned __int64
0x14001f1ca  mov     rcx, r12; unsigned __int16 *
0x14001f1cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001f1d2  mov     ebx, eax
0x14001f1d4  test    eax, eax
0x14001f1d6  jns     short loc_14001F23C
0x14001f1d8  mov     rax, cs:WPP_GLOBAL_Control
0x14001f1df  lea     rdx, WPP_GLOBAL_Control
0x14001f1e6  cmp     rax, rdx
0x14001f1e9  jz      loc_14001F35A
0x14001f1ef  test    byte ptr [rax+1Ch], 8
0x14001f1f3  jz      loc_14001F35A
0x14001f1f9  cmp     byte ptr [rax+19h], 2
0x14001f1fd  jb      loc_14001F35A
0x14001f203  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001f208  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x14001f20f  mov     [rsp+0C8h+fuLoad], ebx
0x14001f213  mov     qword ptr [rsp+0C8h+cy], rcx
0x14001f218  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001f21f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f226  mov     edx, 25h ; '%'
0x14001f22b  mov     r9d, eax
0x14001f22e  mov     rcx, [rcx+10h]
0x14001f232  call    WPP_SF_DsD
0x14001f237  jmp     loc_14001F35A
0x14001f23c  xor     edx, edx; Val
0x14001f23e  lea     rcx, [rsp+0C8h+lParam]; void *
0x14001f243  lea     r8d, [rdx+58h]; Size
0x14001f247  call    memset_0
0x14001f24c  mov     rax, [rsp+0C8h+arg_10]
0x14001f254  lea     r9, [rsp+0C8h+lParam]; lParam
0x14001f259  mov     rcx, [rsi+88h]; hWnd
0x14001f260  xor     r8d, r8d; wParam
0x14001f263  mov     edx, 104Dh; Msg
0x14001f268  mov     [rsp+0C8h+var_80], rax
0x14001f26d  mov     dword ptr [rsp+0C8h+lParam], 7
0x14001f275  mov     [rsp+0C8h+var_74], r15d
0x14001f27a  mov     [rsp+0C8h+var_70], r12
0x14001f27f  call    cs:__imp_SendMessageW
0x14001f285  cmp     eax, 0FFFFFFFFh
0x14001f288  jnz     short loc_14001F2C8
0x14001f28a  mov     rax, cs:WPP_GLOBAL_Control
0x14001f291  lea     rdx, WPP_GLOBAL_Control
0x14001f298  cmp     rax, rdx
0x14001f29b  jz      loc_14001F095
0x14001f2a1  test    [rax+1Ch], dil
0x14001f2a5  jz      loc_14001F095
0x14001f2ab  cmp     byte ptr [rax+19h], 2
0x14001f2af  jb      loc_14001F095
0x14001f2b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001f2ba  mov     edx, 26h ; '&'
0x14001f2bf  mov     [rsp+0C8h+cy], ebx
0x14001f2c3  jmp     loc_14001F07B
0x14001f2c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MSRC88443@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MSRC88443@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88443> `wil::Feature<__WilFeatureTraits_Feature_MSRC88443>::GetImpl(void)'::`2'::impl
0x14001f2cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MSRC88443@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88443>::__private_IsEnabled(void)
0x14001f2d4  test    al, al
0x14001f2d6  jnz     short loc_14001F2EB
0x14001f2d8  test    r13d, r13d
0x14001f2db  jz      short loc_14001F2EB
0x14001f2dd  test    rbp, rbp
0x14001f2e0  jz      short loc_14001F2EB
0x14001f2e2  mov     rcx, rbp; hIcon
0x14001f2e5  call    cs:__imp_DestroyIcon
0x14001f2eb  test    byte ptr [rsi+814h], 40h
0x14001f2f2  jnz     short loc_14001F2FE
0x14001f2f4  mov     edx, edi; int
0x14001f2f6  mov     rcx, rsi; this
0x14001f2f9  call    ?ShowConQueuePane@CRailContWndExt@@AEAAXH@Z; CRailContWndExt::ShowConQueuePane(int)
0x14001f2fe  test    byte ptr [rsi+814h], 2
0x14001f305  jnz     short loc_14001F358
0x14001f307  mov     rax, cs:WPP_GLOBAL_Control
0x14001f30e  lea     rdx, WPP_GLOBAL_Control
0x14001f315  cmp     rax, rdx
0x14001f318  jz      short loc_14001F34A
0x14001f31a  test    [rax+1Ch], dil
0x14001f31e  jz      short loc_14001F34A
0x14001f320  cmp     byte ptr [rax+19h], 4
0x14001f324  jb      short loc_14001F34A
0x14001f326  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001f32b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f332  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001f339  mov     edx, 27h ; '''
0x14001f33e  mov     r9d, eax
0x14001f341  mov     rcx, [rcx+10h]
0x14001f345  call    WPP_SF_d
0x14001f34a  mov     rcx, [rsi+38h]
0x14001f34e  mov     rcx, [rcx+8]; hWnd
0x14001f352  call    cs:__imp_SetForegroundWindow
0x14001f358  xor     ebx, ebx
0x14001f35a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MSRC88443@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MSRC88443@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88443> `wil::Feature<__WilFeatureTraits_Feature_MSRC88443>::GetImpl(void)'::`2'::impl
0x14001f361  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MSRC88443@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88443>::__private_IsEnabled(void)
0x14001f366  test    al, al
0x14001f368  jz      short loc_14001F37D
0x14001f36a  test    r13d, r13d
0x14001f36d  jz      short loc_14001F37D
0x14001f36f  test    rbp, rbp
0x14001f372  jz      short loc_14001F37D
0x14001f374  mov     rcx, rbp; hIcon
0x14001f377  call    cs:__imp_DestroyIcon
0x14001f37d  test    ebx, ebx
0x14001f37f  jns     short loc_14001F38F
0x14001f381  test    r12, r12
0x14001f384  jz      short loc_14001F38F
0x14001f386  mov     rcx, r12; hMem
0x14001f389  call    cs:__imp_LocalFree
0x14001f38f  mov     eax, ebx
0x14001f391  mov     rbx, [rsp+0C8h+arg_0]
0x14001f399  add     rsp, 90h
0x14001f3a0  pop     r15
0x14001f3a2  pop     r14
0x14001f3a4  pop     r13
0x14001f3a6  pop     r12
0x14001f3a8  pop     rdi
0x14001f3a9  pop     rsi
0x14001f3aa  pop     rbp
0x14001f3ab  retn
```
