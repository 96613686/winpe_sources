# GetPreservedFileNameCasing(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,bool)

- ea: `0x14002a810`
- end: `0x14002ac40`
- name: `?GetPreservedFileNameCasing@@YAJAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@_N@Z`
- size: `1072`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x14002a644`
- `0x14002a810`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002c10`
- `0x140002dd0`
- `0x140003160`
- `0x140004950`
- `0x14000fd70`
- `0x14000fdcc`
- `0x140010450`
- `0x1400107f0`
- `0x140022db0`
- `0x140023824`
- `0x140023b80`
- `0x14002891c`
- `0x14002a810`
- `0x14002b618`
- `0x140033ab0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsupr_s` at `0x14002a92b`
- `api-ms-win-crt-string-l1-1-0!_wcsupr_s` at `0x14002a92b`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x14002a85d`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x14002a85d`
- `SHLWAPI!PathIsFileSpecW` at `0x14002a9f6`
- `SHLWAPI!PathIsFileSpecW` at `0x14002a9f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall GetPreservedFileNameCasing(LPCWSTR *a1)
{
  const wchar_t *v2; // rcx
  wchar_t *v3; // rax
  __int64 v4; // rax
  struct ATL::IAtlStringMgr *Instance; // rax
  struct ATL::IAtlStringMgr *v6; // rax
  __int64 v7; // rdi
  unsigned __int16 **v8; // rax
  int v9; // edi
  _QWORD *v10; // rdx
  _QWORD *v11; // rdx
  int PreservedFileNameCasing; // edi
  const unsigned __int16 **v13; // rax
  int File; // edi
  _QWORD *v15; // rdx
  _QWORD *FileName; // rax
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rdx
  _QWORD *v21; // rdx
  _QWORD *v22; // rdx
  _QWORD *v23; // rdx
  __int64 v25; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v29[624]; // [rsp+48h] [rbp-C0h] BYREF

  v2 = *a1;
  if ( !*((_DWORD *)v2 - 4) )
    return 2147942487LL;
  v3 = wcspbrk(v2, L"*?");
  if ( v3 )
    v4 = v3 - *a1;
  else
    LODWORD(v4) = -1;
  if ( (int)v4 >= 0 )
    return 2147942487LL;
  v28 = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v28 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  v6 = ATL::CAtlStringMgr::GetInstance();
  if ( !v6 )
    ATL::AtlThrowImpl(-2147467259);
  v26 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v6 + 24LL))(v6) + 24;
  ATL::CSimpleStringT<unsigned short,0>::operator=(&v28, a1);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&v26, a1);
  if ( (unsigned int)ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec(&v28) )
  {
    v8 = (unsigned __int16 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
                                &v26,
                                &v25,
                                1);
    v9 = **v8 - 92;
    if ( **v8 == 92 )
      v9 = (*v8)[1];
    v10 = (_QWORD *)(v25 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
    }
    if ( v9 )
    {
      ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::StripPath(&v26);
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v25,
        &WindowName);
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v26, &v25);
      v11 = (_QWORD *)(v25 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
      }
    }
    if ( !PathIsFileSpecW(*a1) )
    {
      PreservedFileNameCasing = GetPreservedFileNameCasing(&v28);
      if ( PreservedFileNameCasing < 0 )
        goto LABEL_38;
    }
    ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::AddBackslash(&v28);
    if ( *(_DWORD *)(v26 - 16) )
    {
      memset_0(v29, 0, 0x268u);
      CFindFile::CFindFile((CFindFile *)v29);
      v13 = (const unsigned __int16 **)ATL::operator+(&v25, &v28, &v26);
      File = CFindFile::FindFile((CFindFile *)v29, *v13);
      v15 = (_QWORD *)(v25 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
      }
      if ( File )
      {
        FileName = (_QWORD *)CFindFile::GetFileName(v29, &v27);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v25,
          *FileName);
        ATL::CSimpleStringT<unsigned short,0>::operator=(&v26, &v25);
        v17 = (_QWORD *)(v25 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 8LL))(*v17);
        }
        v18 = (_QWORD *)(v27 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
        }
      }
      CFindFile::~CFindFile((CFindFile *)v29);
    }
    v19 = (_QWORD *)ATL::operator+(&v27, &v28, &v26);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v25,
      *v19);
    ATL::CSimpleStringT<unsigned short,0>::operator=(a1, &v25);
    v20 = (_QWORD *)(v25 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
    }
    v21 = (_QWORD *)(v27 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
    }
  }
  else
  {
    v7 = *((int *)*a1 - 4);
    if ( (int)v7 < 0 )
      goto LABEL_44;
    _mm_lfence();
    if ( ((1 - *((_DWORD *)*a1 - 2)) | (*((_DWORD *)*a1 - 3) - (int)v7)) < 0 )
    {
      _mm_lfence();
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v7);
    }
    _wcsupr_s((wchar_t *)*a1, (int)v7 + 1);
    if ( (int)v7 > *((_DWORD *)*a1 - 3) )
LABEL_44:
      ATL::AtlThrowImpl(-2147024809);
    *((_DWORD *)*a1 - 4) = v7;
    (*a1)[v7] = 0;
  }
  PreservedFileNameCasing = 0;
LABEL_38:
  v22 = (_QWORD *)(v26 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v26 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
  }
  v23 = (_QWORD *)(v28 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
  }
  return (unsigned int)PreservedFileNameCasing;
}

```

## disassembly

```asm
0x14002a810  mov     rax, rsp
0x14002a813  mov     [rax+10h], rbx
0x14002a817  mov     [rax+18h], rsi
0x14002a81b  mov     [rax+20h], rdi
0x14002a81f  push    rbp
0x14002a820  push    r14
0x14002a822  push    r15
0x14002a824  lea     rbp, [rax-1D8h]
0x14002a82b  sub     rsp, 2C0h
0x14002a832  mov     rax, cs:__security_cookie
0x14002a839  xor     rax, rsp
0x14002a83c  mov     [rbp+1D0h+var_20], rax
0x14002a843  mov     rbx, rcx
0x14002a846  mov     rcx, [rcx]; String
0x14002a849  xor     r14d, r14d
0x14002a84c  cmp     [rcx-10h], r14d
0x14002a850  jz      loc_14002ABE7
0x14002a856  lea     rdx, asc_1400775C0; "*?"
0x14002a85d  call    cs:__imp_wcspbrk
0x14002a863  or      r15d, 0FFFFFFFFh
0x14002a867  test    rax, rax
0x14002a86a  jnz     short loc_14002A871
0x14002a86c  mov     eax, r15d
0x14002a86f  jmp     short loc_14002A877
0x14002a871  sub     rax, [rbx]
0x14002a874  sar     rax, 1
0x14002a877  shr     eax, 1Fh
0x14002a87a  test    al, al
0x14002a87c  jz      loc_14002ABE7
0x14002a882  mov     [rsp+2D0h+var_298], r14
0x14002a887  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a88c  mov     rcx, rax
0x14002a88f  test    rax, rax
0x14002a892  jz      loc_14002AC27
0x14002a898  mov     rax, [rax]
0x14002a89b  call    qword ptr [rax+18h]
0x14002a89e  add     rax, 18h
0x14002a8a2  mov     [rsp+2D0h+var_298], rax
0x14002a8a7  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a8ac  mov     rcx, rax
0x14002a8af  test    rax, rax
0x14002a8b2  jz      loc_14002AC35
0x14002a8b8  mov     rax, [rax]
0x14002a8bb  call    qword ptr [rax+18h]
0x14002a8be  add     rax, 18h
0x14002a8c2  mov     [rsp+2D0h+var_2A8], rax
0x14002a8c7  mov     rdx, rbx
0x14002a8ca  lea     rcx, [rsp+2D0h+var_298]
0x14002a8cf  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002a8d4  mov     rdx, rbx
0x14002a8d7  lea     rcx, [rsp+2D0h+var_2A8]
0x14002a8dc  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002a8e1  lea     rcx, [rsp+2D0h+var_298]
0x14002a8e6  call    ?RemoveFileSpec@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveFileSpec(void)
0x14002a8eb  test    eax, eax
0x14002a8ed  jnz     short loc_14002A94D
0x14002a8ef  mov     rax, [rbx]
0x14002a8f2  movsxd  rdi, dword ptr [rax-10h]
0x14002a8f6  test    edi, edi
0x14002a8f8  js      loc_14002AC18
0x14002a8fe  lfence
0x14002a901  mov     rax, [rbx]
0x14002a904  mov     esi, 1
0x14002a909  sub     esi, [rax-8]
0x14002a90c  mov     eax, [rax-0Ch]
0x14002a90f  sub     eax, edi
0x14002a911  or      eax, esi
0x14002a913  jge     short loc_14002A922
0x14002a915  lfence
0x14002a918  mov     edx, edi
0x14002a91a  mov     rcx, rbx
0x14002a91d  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14002a922  lea     eax, [rdi+1]
0x14002a925  movsxd  rdx, eax; Size
0x14002a928  mov     rcx, [rbx]; String
0x14002a92b  call    cs:__imp__wcsupr_s
0x14002a931  mov     rax, [rbx]
0x14002a934  cmp     edi, [rax-0Ch]
0x14002a937  jg      loc_14002AC18
0x14002a93d  mov     [rax-10h], edi
0x14002a940  mov     rax, [rbx]
0x14002a943  mov     [rax+rdi*2], r14w
0x14002a948  jmp     loc_14002AB96
0x14002a94d  mov     esi, 1
0x14002a952  mov     r8d, esi
0x14002a955  lea     rdx, [rsp+2D0h+var_2B0]
0x14002a95a  lea     rcx, [rsp+2D0h+var_2A8]
0x14002a95f  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Right(int)
0x14002a964  mov     rcx, [rax]
0x14002a967  movzx   edi, word ptr [rcx]
0x14002a96a  sub     edi, 5Ch ; '\'
0x14002a96d  jnz     short loc_14002A979
0x14002a96f  movzx   edi, word ptr [rcx+2]
0x14002a973  movzx   eax, r14w
0x14002a977  sub     edi, eax
0x14002a979  mov     rdx, [rsp+2D0h+var_2B0]
0x14002a97e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002a982  mov     eax, r15d
0x14002a985  lock xadd [rdx+10h], eax
0x14002a98a  add     eax, r15d
0x14002a98d  test    eax, eax
0x14002a98f  jg      short loc_14002A99D
0x14002a991  lfence
0x14002a994  mov     rcx, [rdx]
0x14002a997  mov     rax, [rcx]
0x14002a99a  call    qword ptr [rax+8]
0x14002a99d  test    edi, edi
0x14002a99f  jnz     short loc_14002A9E9
0x14002a9a1  lea     rdx, WindowName
0x14002a9a8  lea     rcx, [rsp+2D0h+var_2B0]
0x14002a9ad  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002a9b2  nop
0x14002a9b3  lea     rdx, [rsp+2D0h+var_2B0]
0x14002a9b8  lea     rcx, [rsp+2D0h+var_2A8]
0x14002a9bd  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002a9c2  nop
0x14002a9c3  mov     rdx, [rsp+2D0h+var_2B0]
0x14002a9c8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002a9cc  mov     eax, r15d
0x14002a9cf  lock xadd [rdx+10h], eax
0x14002a9d4  add     eax, r15d
0x14002a9d7  test    eax, eax
0x14002a9d9  jg      short loc_14002A9F3
0x14002a9db  lfence
0x14002a9de  mov     rcx, [rdx]
0x14002a9e1  mov     rax, [rcx]
0x14002a9e4  call    qword ptr [rax+8]
0x14002a9e7  jmp     short loc_14002A9F3
0x14002a9e9  lea     rcx, [rsp+2D0h+var_2A8]
0x14002a9ee  call    ?StripPath@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::StripPath(void)
0x14002a9f3  mov     rcx, [rbx]; pszPath
0x14002a9f6  call    cs:__imp_PathIsFileSpecW
0x14002a9fc  test    eax, eax
0x14002a9fe  jnz     short loc_14002AA17
0x14002aa00  mov     dl, sil
0x14002aa03  lea     rcx, [rsp+2D0h+var_298]
0x14002aa08  call    ?GetPreservedFileNameCasing@@YAJAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@_N@Z; GetPreservedFileNameCasing(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,bool)
0x14002aa0d  mov     edi, eax
0x14002aa0f  test    eax, eax
0x14002aa11  js      loc_14002AB99
0x14002aa17  lea     rcx, [rsp+2D0h+var_298]
0x14002aa1c  call    ?AddBackslash@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::AddBackslash(void)
0x14002aa21  mov     rax, [rsp+2D0h+var_2A8]
0x14002aa26  cmp     [rax-10h], r14d
0x14002aa2a  jz      loc_14002AB1C
0x14002aa30  xor     edx, edx; Val
0x14002aa32  mov     r8d, 268h; Size
0x14002aa38  lea     rcx, [rsp+2D0h+var_290]; void *
0x14002aa3d  call    memset_0
0x14002aa42  lea     rcx, [rsp+2D0h+var_290]; this
0x14002aa47  call    ??0CFindFile@@QEAA@XZ; CFindFile::CFindFile(void)
0x14002aa4c  nop
0x14002aa4d  lea     r8, [rsp+2D0h+var_2A8]
0x14002aa52  lea     rdx, [rsp+2D0h+var_298]
0x14002aa57  lea     rcx, [rsp+2D0h+var_2B0]
0x14002aa5c  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002aa61  nop
0x14002aa62  mov     rdx, [rax]; unsigned __int16 *
0x14002aa65  lea     rcx, [rsp+2D0h+var_290]; this
0x14002aa6a  call    ?FindFile@CFindFile@@QEAAHPEBG@Z; CFindFile::FindFile(ushort const *)
0x14002aa6f  mov     edi, eax
0x14002aa71  mov     rdx, [rsp+2D0h+var_2B0]
0x14002aa76  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002aa7a  mov     ecx, r15d
0x14002aa7d  lock xadd [rdx+10h], ecx
0x14002aa82  add     ecx, r15d
0x14002aa85  test    ecx, ecx
0x14002aa87  jg      short loc_14002AA96
0x14002aa89  lfence
0x14002aa8c  mov     rcx, [rdx]
0x14002aa8f  mov     r8, [rcx]
0x14002aa92  call    qword ptr [r8+8]
0x14002aa96  test    edi, edi
0x14002aa98  jz      short loc_14002AB12
0x14002aa9a  lea     rdx, [rsp+2D0h+var_2A0]
0x14002aa9f  lea     rcx, [rsp+2D0h+var_290]
0x14002aaa4  call    ?GetFileName@CFindFile@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CFindFile::GetFileName(void)
0x14002aaa9  nop
0x14002aaaa  mov     rdx, [rax]
0x14002aaad  lea     rcx, [rsp+2D0h+var_2B0]
0x14002aab2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002aab7  nop
0x14002aab8  lea     rdx, [rsp+2D0h+var_2B0]
0x14002aabd  lea     rcx, [rsp+2D0h+var_2A8]
0x14002aac2  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002aac7  nop
0x14002aac8  mov     rdx, [rsp+2D0h+var_2B0]
0x14002aacd  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002aad1  mov     eax, r15d
0x14002aad4  lock xadd [rdx+10h], eax
0x14002aad9  add     eax, r15d
0x14002aadc  test    eax, eax
0x14002aade  jg      short loc_14002AAED
0x14002aae0  lfence
0x14002aae3  mov     rcx, [rdx]
0x14002aae6  mov     rax, [rcx]
0x14002aae9  call    qword ptr [rax+8]
0x14002aaec  nop
0x14002aaed  mov     rdx, [rsp+2D0h+var_2A0]
0x14002aaf2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002aaf6  mov     eax, r15d
0x14002aaf9  lock xadd [rdx+10h], eax
0x14002aafe  add     eax, r15d
0x14002ab01  test    eax, eax
0x14002ab03  jg      short loc_14002AB12
0x14002ab05  lfence
0x14002ab08  mov     rcx, [rdx]
0x14002ab0b  mov     rax, [rcx]
0x14002ab0e  call    qword ptr [rax+8]
0x14002ab11  nop
0x14002ab12  lea     rcx, [rsp+2D0h+var_290]; this
0x14002ab17  call    ??1CFindFile@@QEAA@XZ; CFindFile::~CFindFile(void)
0x14002ab1c  lea     r8, [rsp+2D0h+var_2A8]
0x14002ab21  lea     rdx, [rsp+2D0h+var_298]
0x14002ab26  lea     rcx, [rsp+2D0h+var_2A0]
0x14002ab2b  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002ab30  nop
0x14002ab31  mov     rdx, [rax]
0x14002ab34  lea     rcx, [rsp+2D0h+var_2B0]
0x14002ab39  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002ab3e  nop
0x14002ab3f  lea     rdx, [rsp+2D0h+var_2B0]
0x14002ab44  mov     rcx, rbx
0x14002ab47  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002ab4c  nop
0x14002ab4d  mov     rdx, [rsp+2D0h+var_2B0]
0x14002ab52  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002ab56  mov     eax, r15d
0x14002ab59  lock xadd [rdx+10h], eax
0x14002ab5e  add     eax, r15d
0x14002ab61  test    eax, eax
0x14002ab63  jg      short loc_14002AB72
0x14002ab65  lfence
0x14002ab68  mov     rcx, [rdx]
0x14002ab6b  mov     rax, [rcx]
0x14002ab6e  call    qword ptr [rax+8]
0x14002ab71  nop
0x14002ab72  mov     rdx, [rsp+2D0h+var_2A0]
0x14002ab77  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002ab7b  mov     eax, r15d
0x14002ab7e  lock xadd [rdx+10h], eax
0x14002ab83  add     eax, r15d
0x14002ab86  test    eax, eax
0x14002ab88  jg      short loc_14002AB96
0x14002ab8a  lfence
0x14002ab8d  mov     rcx, [rdx]
0x14002ab90  mov     rax, [rcx]
0x14002ab93  call    qword ptr [rax+8]
0x14002ab96  mov     edi, r14d
0x14002ab99  mov     rdx, [rsp+2D0h+var_2A8]
0x14002ab9e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002aba2  mov     eax, r15d
0x14002aba5  lock xadd [rdx+10h], eax
0x14002abaa  add     eax, r15d
0x14002abad  test    eax, eax
0x14002abaf  jg      short loc_14002ABBE
0x14002abb1  lfence
0x14002abb4  mov     rcx, [rdx]
0x14002abb7  mov     rax, [rcx]
0x14002abba  call    qword ptr [rax+8]
0x14002abbd  nop
0x14002abbe  mov     rdx, [rsp+2D0h+var_298]
0x14002abc3  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002abc7  mov     ecx, r15d
0x14002abca  lock xadd [rdx+10h], ecx
0x14002abcf  add     ecx, r15d
0x14002abd2  test    ecx, ecx
0x14002abd4  jg      short loc_14002ABE3
0x14002abd6  lfence
0x14002abd9  mov     rcx, [rdx]
0x14002abdc  mov     r8, [rcx]
0x14002abdf  call    qword ptr [r8+8]
0x14002abe3  mov     eax, edi
0x14002abe5  jmp     short loc_14002ABEC
0x14002abe7  mov     eax, 80070057h
0x14002abec  mov     rcx, [rbp+1D0h+var_20]
0x14002abf3  xor     rcx, rsp; StackCookie
0x14002abf6  call    __security_check_cookie
0x14002abfb  lea     r11, [rsp+2D0h+var_10]
0x14002ac03  mov     rbx, [r11+28h]
0x14002ac07  mov     rsi, [r11+30h]
0x14002ac0b  mov     rdi, [r11+38h]
0x14002ac0f  mov     rsp, r11
0x14002ac12  pop     r15
0x14002ac14  pop     r14
0x14002ac16  pop     rbp
0x14002ac17  retn
0x14002ac18  mov     ecx, 80070057h; int
0x14002ac1d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002ac23  jmp     short loc_14002AC26
0x14002ac26  nop
0x14002ac27  mov     ecx, 80004005h; int
0x14002ac2c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002ac32  jmp     short $+2
0x14002ac34  nop
0x14002ac35  mov     ecx, 80004005h; int
0x14002ac3a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
