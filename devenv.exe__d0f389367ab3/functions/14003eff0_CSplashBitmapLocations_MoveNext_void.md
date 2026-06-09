# CSplashBitmapLocations::MoveNext(void)

- ea: `0x14003eff0`
- end: `0x14003f241`
- name: `?MoveNext@CSplashBitmapLocations@@QEAAXXZ`
- size: `593`
- prototype: `void __fastcall(CSplashBitmapLocations *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14003f244`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002c10`
- `0x140003160`
- `0x140004950`
- `0x140009b10`
- `0x140022db0`
- `0x140033ab0`
- `0x14003eff0`
- `0x14003f580`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14003f1d7`
- `KERNEL32!GetModuleFileNameW` at `0x14003f1d7`
- `SHLWAPI!PathFindFileNameW` at `0x14003f099`
- `SHLWAPI!PathFindFileNameW` at `0x14003f155`
- `SHLWAPI!PathFindFileNameW` at `0x14003f204`
- `SHLWAPI!PathFindFileNameW` at `0x14003f099`
- `SHLWAPI!PathFindFileNameW` at `0x14003f155`
- `SHLWAPI!PathFindFileNameW` at `0x14003f204`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSplashBitmapLocations::MoveNext(LPCWSTR *this)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  _QWORD *v3; // rdx
  struct ATL::IAtlStringMgr *v4; // rax
  LPWSTR FileNameW; // rax
  _QWORD v6[2]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Filename; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v8[526]; // [rsp+32h] [rbp-CEh] BYREF

  if ( *(_DWORD *)this )
  {
    if ( *(_DWORD *)this != 1 )
    {
      if ( *(_DWORD *)this != 2 )
      {
        if ( *(_DWORD *)this != 3 )
          return;
LABEL_20:
        *(_DWORD *)this = 4;
        return;
      }
      goto LABEL_18;
    }
  }
  else
  {
    *(_DWORD *)this = 1;
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      goto LABEL_21;
    v6[0] = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
    PathFindFileNameW(this[1]);
    if ( (unsigned __int8)CSplash::MakeFullProfilePath(26) )
      goto LABEL_8;
    if ( _InterlockedDecrement((volatile signed __int32 *)(v6[0] - 24LL + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6[0] - 24LL) + 8LL))(*(_QWORD *)(v6[0] - 24LL));
    }
  }
  if ( !*((_BYTE *)this + 24) )
  {
    *(_DWORD *)this = 2;
    v4 = ATL::CAtlStringMgr::GetInstance();
    if ( v4 )
    {
      v6[0] = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v4 + 24LL))(v4) + 24;
      PathFindFileNameW(this[1]);
      if ( !(unsigned __int8)CSplash::MakeFullProfilePath(35) )
      {
        if ( _InterlockedDecrement((volatile signed __int32 *)(v6[0] - 24LL + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6[0] - 24LL) + 8LL))(*(_QWORD *)(v6[0] - 24LL));
        }
        goto LABEL_18;
      }
LABEL_8:
      ATL::CSimpleStringT<unsigned short,0>::operator=(this + 1, v6);
      goto LABEL_9;
    }
LABEL_21:
    ATL::AtlThrowImpl(-2147467259);
  }
LABEL_18:
  *(_DWORD *)this = 3;
  Filename = 0;
  memset_0(v8, 0, 0x208u);
  if ( !GetModuleFileNameW(0, &Filename, 0x105u) )
    goto LABEL_20;
  v6[0] = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v6,
    &Filename);
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec(v6);
  FileNameW = PathFindFileNameW(this[1]);
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
    v6,
    FileNameW);
  ATL::CSimpleStringT<unsigned short,0>::operator=(this + 1, v6);
LABEL_9:
  v3 = (_QWORD *)(v6[0] - 24LL);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v6[0] - 24LL + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 8LL))(*v3);
  }
}

```

## disassembly

```asm
0x14003eff0  mov     [rsp-8+arg_8], rbx
0x14003eff5  mov     [rsp-8+arg_10], rsi
0x14003effa  push    rbp
0x14003effb  push    rdi
0x14003effc  push    r14
0x14003effe  lea     rbp, [rsp-150h]
0x14003f006  sub     rsp, 250h
0x14003f00d  mov     rax, cs:__security_cookie
0x14003f014  xor     rax, rsp
0x14003f017  mov     [rbp+160h+var_20], rax
0x14003f01e  mov     rbx, rcx
0x14003f021  mov     edx, [rcx]
0x14003f023  or      r14d, 0FFFFFFFFh
0x14003f027  xor     esi, esi
0x14003f029  test    edx, edx
0x14003f02b  jz      short loc_14003F06F
0x14003f02d  sub     edx, 1
0x14003f030  jz      loc_14003F121
0x14003f036  sub     edx, 1
0x14003f039  jz      loc_14003F1AD
0x14003f03f  cmp     edx, 1
0x14003f042  jz      loc_14003F22B
0x14003f048  mov     rcx, [rbp+160h+var_20]
0x14003f04f  xor     rcx, rsp; StackCookie
0x14003f052  call    __security_check_cookie
0x14003f057  lea     r11, [rsp+260h+var_10]
0x14003f05f  mov     rbx, [r11+28h]
0x14003f063  mov     rsi, [r11+30h]
0x14003f067  mov     rsp, r11
0x14003f06a  pop     r14
0x14003f06c  pop     rdi
0x14003f06d  pop     rbp
0x14003f06e  retn
0x14003f06f  mov     dword ptr [rcx], 1
0x14003f075  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14003f07a  mov     rcx, rax
0x14003f07d  test    rax, rax
0x14003f080  jz      loc_14003F236
0x14003f086  mov     rax, [rax]
0x14003f089  call    qword ptr [rax+18h]
0x14003f08c  add     rax, 18h
0x14003f090  mov     [rsp+260h+var_240], rax
0x14003f095  mov     rcx, [rbx+8]; pszPath
0x14003f099  call    cs:__imp_PathFindFileNameW
0x14003f09f  lea     r9, [rsp+260h+var_240]
0x14003f0a4  mov     r8, rax
0x14003f0a7  mov     rdx, [rbx+10h]
0x14003f0ab  mov     ecx, 1Ah; int
0x14003f0b0  call    ?MakeFullProfilePath@CSplash@@SA_NHPEBG0PEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z; CSplash::MakeFullProfilePath(int,ushort const *,ushort const *,ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> *)
0x14003f0b5  test    al, al
0x14003f0b7  jz      short loc_14003F0FD
0x14003f0b9  lea     rdx, [rsp+260h+var_240]
0x14003f0be  lea     rcx, [rbx+8]
0x14003f0c2  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14003f0c7  nop
0x14003f0c8  nop     dword ptr [rax+rax+00000000h]
0x14003f0d0  mov     rdx, [rsp+260h+var_240]
0x14003f0d5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14003f0d9  mov     eax, r14d
0x14003f0dc  lock xadd [rdx+10h], eax
0x14003f0e1  add     eax, r14d
0x14003f0e4  test    eax, eax
0x14003f0e6  jg      loc_14003F048
0x14003f0ec  lfence
0x14003f0ef  mov     rcx, [rdx]
0x14003f0f2  mov     rax, [rcx]
0x14003f0f5  call    qword ptr [rax+8]
0x14003f0f8  jmp     loc_14003F048
0x14003f0fd  mov     rdx, [rsp+260h+var_240]
0x14003f102  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14003f106  mov     eax, r14d
0x14003f109  lock xadd [rdx+10h], eax
0x14003f10e  add     eax, r14d
0x14003f111  test    eax, eax
0x14003f113  jg      short loc_14003F121
0x14003f115  lfence
0x14003f118  mov     rcx, [rdx]
0x14003f11b  mov     rax, [rcx]
0x14003f11e  call    qword ptr [rax+8]
0x14003f121  cmp     [rbx+18h], sil
0x14003f125  jnz     loc_14003F1AD
0x14003f12b  mov     dword ptr [rbx], 2
0x14003f131  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14003f136  mov     rcx, rax
0x14003f139  test    rax, rax
0x14003f13c  jz      loc_14003F236
0x14003f142  mov     rax, [rax]
0x14003f145  call    qword ptr [rax+18h]
0x14003f148  add     rax, 18h
0x14003f14c  mov     [rsp+260h+var_240], rax
0x14003f151  mov     rcx, [rbx+8]; pszPath
0x14003f155  call    cs:__imp_PathFindFileNameW
0x14003f15b  lea     r9, [rsp+260h+var_240]
0x14003f160  mov     r8, rax
0x14003f163  mov     rdx, [rbx+10h]
0x14003f167  mov     ecx, 23h ; '#'; int
0x14003f16c  call    ?MakeFullProfilePath@CSplash@@SA_NHPEBG0PEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z; CSplash::MakeFullProfilePath(int,ushort const *,ushort const *,ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> *)
0x14003f171  test    al, al
0x14003f173  jz      short loc_14003F189
0x14003f175  lea     rdx, [rsp+260h+var_240]
0x14003f17a  lea     rcx, [rbx+8]
0x14003f17e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14003f183  nop
0x14003f184  jmp     loc_14003F0D0
0x14003f189  mov     rdx, [rsp+260h+var_240]
0x14003f18e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14003f192  mov     eax, r14d
0x14003f195  lock xadd [rdx+10h], eax
0x14003f19a  add     eax, r14d
0x14003f19d  test    eax, eax
0x14003f19f  jg      short loc_14003F1AD
0x14003f1a1  lfence
0x14003f1a4  mov     rcx, [rdx]
0x14003f1a7  mov     rax, [rcx]
0x14003f1aa  call    qword ptr [rax+8]
0x14003f1ad  mov     dword ptr [rbx], 3
0x14003f1b3  mov     [rsp+260h+Filename], si
0x14003f1b8  xor     edx, edx; Val
0x14003f1ba  mov     r8d, 208h; Size
0x14003f1c0  lea     rcx, [rsp+260h+var_22E]; void *
0x14003f1c5  call    memset_0
0x14003f1ca  mov     r8d, 105h; nSize
0x14003f1d0  lea     rdx, [rsp+260h+Filename]; lpFilename
0x14003f1d5  xor     ecx, ecx; hModule
0x14003f1d7  call    cs:__imp_GetModuleFileNameW
0x14003f1dd  test    eax, eax
0x14003f1df  jz      short loc_14003F22B
0x14003f1e1  mov     [rsp+260h+var_240], rsi
0x14003f1e6  lea     rdx, [rsp+260h+Filename]
0x14003f1eb  lea     rcx, [rsp+260h+var_240]
0x14003f1f0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14003f1f5  nop
0x14003f1f6  lea     rcx, [rsp+260h+var_240]
0x14003f1fb  call    ?RemoveFileSpec@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveFileSpec(void)
0x14003f200  mov     rcx, [rbx+8]; pszPath
0x14003f204  call    cs:__imp_PathFindFileNameW
0x14003f20a  mov     rdx, rax
0x14003f20d  lea     rcx, [rsp+260h+var_240]
0x14003f212  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x14003f217  lea     rdx, [rsp+260h+var_240]
0x14003f21c  lea     rcx, [rbx+8]
0x14003f220  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14003f225  nop
0x14003f226  jmp     loc_14003F0D0
0x14003f22b  mov     dword ptr [rbx], 4
0x14003f231  jmp     loc_14003F048
0x14003f236  mov     ecx, 80004005h; int
0x14003f23b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
