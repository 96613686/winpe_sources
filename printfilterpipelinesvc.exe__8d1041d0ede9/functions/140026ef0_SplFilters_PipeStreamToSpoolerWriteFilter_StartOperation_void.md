# SplFilters::PipeStreamToSpoolerWriteFilter::StartOperation(void)

- ea: `0x140026ef0`
- end: `0x140027290`
- name: `?StartOperation@PipeStreamToSpoolerWriteFilter@SplFilters@@UEAAJXZ`
- size: `928`
- prototype: `__int64 __fastcall(SplFilters::PipeStreamToSpoolerWriteFilter *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140007ce0`
- `0x1400086f8`
- `0x14000fa68`
- `0x14001fbf8`
- `0x140026ef0`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14004650c`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x140027012`
- `OLEAUT32!__imp_SetErrorInfo` at `0x140027012`

## string_xrefs

- `0x140027117`: `cbRead != cbWritten`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SplFilters::PipeStreamToSpoolerWriteFilter::StartOperation(
        SplFilters::PipeStreamToSpoolerWriteFilter *this)
{
  SplFilters::PipeStreamToSpoolerWriteFilter *v1; // rdi
  unsigned int v2; // r14d
  int v3; // eax
  int v4; // edx
  const char *v5; // r8
  unsigned int v6; // r9d
  int v7; // eax
  int v8; // edx
  const char *v9; // r8
  unsigned int v10; // r9d
  __int64 *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // r8
  unsigned int v16; // r9d
  __int64 v17; // r8
  int v18; // eax
  int v19; // edx
  const char *v20; // r8
  unsigned int v21; // r9d
  const struct SplException::TSystemException *v22; // r8
  const struct _GUID *v23; // r9
  int v24; // ecx
  PVOID *v25; // rax
  __int64 v26; // rcx
  SplException *v28; // rbx
  struct SplException::TSystemException *v29; // rdx
  __int64 v30; // [rsp+0h] [rbp-1F8h] BYREF
  unsigned int v31[2]; // [rsp+20h] [rbp-1D8h]
  const struct win_musl::TStringEllipseBase *v32; // [rsp+28h] [rbp-1D0h]
  HINSTANCE v33; // [rsp+30h] [rbp-1C8h]
  unsigned int v34; // [rsp+40h] [rbp-1B8h] BYREF
  unsigned int v35; // [rsp+44h] [rbp-1B4h] BYREF
  int v36; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v37; // [rsp+50h] [rbp-1A8h] BYREF
  __int64 v38; // [rsp+58h] [rbp-1A0h] BYREF
  SplFilters::PipeStreamToSpoolerWriteFilter *v39; // [rsp+60h] [rbp-198h]
  SplException::TSystemException *v40; // [rsp+68h] [rbp-190h] BYREF
  _BYTE v41[160]; // [rsp+70h] [rbp-188h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+110h] [rbp-E8h] BYREF
  std::bad_alloc *v43; // [rsp+1B0h] [rbp-48h] BYREF
  std::exception *v44; // [rsp+1B8h] [rbp-40h] BYREF

  try
  {
    v1 = this;
    v39 = this;
    v2 = 0;
    v35 = 0;
    v37 = 0;
    v3 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
           *((_QWORD *)this + 3),
           &IID_IPrintWriteStreamFlush,
           &v37);
    if ( v3 == -2147467262 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_94258a397080385d6808b2748fb65100_Traceguids);
      }
    }
    else if ( v3 < 0 )
    {
      SplException::RealThrowFromHR((SplException *)(unsigned int)v3, v4, v5, v6);
    }
    v38 = 0;
    v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v1 + 4))(
           *((_QWORD *)v1 + 4),
           &IID_IPrintReadStreamX,
           &v38);
    if ( v7 == -2147467262 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_94258a397080385d6808b2748fb65100_Traceguids);
      }
    }
    else if ( v7 < 0 )
    {
      SplException::RealThrowFromHR((SplException *)(unsigned int)v7, v8, v9, v10);
    }
    while ( !*((_BYTE *)v1 + 64) && !v35 )
    {
      v34 = 0;
      SetErrorInfo(0, 0);
      v11 = (__int64 *)*((_QWORD *)v1 + 4);
      v12 = *v11;
      *(_QWORD *)v31 = &v35;
      v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, unsigned int *))(v12 + 32))(
              v11,
              *((_QWORD *)v1 + 7),
              *((unsigned int *)v1 + 12),
              &v34);
      SplException::ThrowFromHRErrorInfo((SplException *)v13, v14, v15, v16);
      v17 = v34;
      if ( v34 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_94258a397080385d6808b2748fb65100_Traceguids, v34);
          v17 = v34;
        }
        v36 = 0;
        v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *))(**((_QWORD **)v1 + 3) + 32LL))(
                *((_QWORD *)v1 + 3),
                *((_QWORD *)v1 + 7),
                v17,
                &v36);
        if ( v18 < 0 )
          SplException::RealThrowFromHR((SplException *)(unsigned int)v18, v19, v20, v21);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_94258a397080385d6808b2748fb65100_Traceguids, v34);
        }
        if ( v34 != v36 )
        {
          SplException::THResultException::THResultException((SplException::THResultException *)v41, "-", 0);
          SplException::TSystemException::InternalInit(
            (SplException::TSystemException *)v41,
            0x8000FFFF,
            v22,
            v23,
            v31[0],
            v32,
            v33);
          SplException::TSystemException::Message((SplException::TSystemException *)v41, "cbRead != cbWritten");
          SplException::THResultException::THResultException(
            (SplException::THResultException *)pExceptionObject,
            (const struct SplException::THResultException *)v41);
          throw (SplException::THResultException *)pExceptionObject;
        }
      }
      if ( v38 )
      {
        v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 56LL))(v38);
        if ( v24 != *((_DWORD *)v1 + 17) )
        {
          *((_DWORD *)v1 + 17) = v24;
          v25 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_94258a397080385d6808b2748fb65100_Traceguids);
            v25 = (PVOID *)WPP_GLOBAL_Control;
          }
          v26 = v37;
          if ( v37 )
          {
            if ( v25 != &WPP_GLOBAL_Control && (*((_DWORD *)v25 + 7) & 0x200) != 0 && *((_BYTE *)v25 + 25) >= 3u )
            {
              WPP_SF_(v25[2], 19, WPP_94258a397080385d6808b2748fb65100_Traceguids);
              v26 = v37;
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 24LL))(v26);
          }
        }
      }
    }
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 24LL))(v37);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v38);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v37);
  }
  catch ( SplException::TSystemException *v40 )
  {
    v29 = (struct SplException::TSystemException *)&v30;
    v28 = v40;
    if ( SplException::gpfnExceptionLogger )
      SplException::gpfnExceptionLogger(v40);
    v34 = SplException::SetErrorInfoFromException(v28, v29);
    v2 = v34;
    if ( (v34 & 0x80000000) != 0 )
    {
LABEL_48:
      v1 = v39;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v39 + 5) + 24LL))(*((_QWORD *)v39 + 5), v2, 0);
    }
    else
    {
      v1 = v39;
    }
  }
  catch ( std::bad_alloc *v43 )
  {
    v34 = -2147024882;
    SetErrorInfo(0, 0);
    v2 = v34;
    goto LABEL_48;
  }
  catch ( std::exception *v44 )
  {
    v34 = -2147418113;
    SetErrorInfo(0, 0);
    v2 = v34;
    goto LABEL_48;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 5) + 32LL))(*((_QWORD *)v1 + 5));
  return v2;
}

```

## disassembly

```asm
0x140026ef0  push    rbx
0x140026ef2  push    rdi
0x140026ef3  push    r14
0x140026ef5  push    r15
0x140026ef7  sub     rsp, 1D8h
0x140026efe  mov     rax, cs:__security_cookie
0x140026f05  xor     rax, rsp
0x140026f08  mov     [rsp+1F8h+var_38], rax
0x140026f10  mov     rdi, rcx
0x140026f13  mov     [rsp+1F8h+var_198], rcx
0x140026f18  xor     ebx, ebx
0x140026f1a  mov     r14d, ebx
0x140026f1d  mov     [rsp+1F8h+var_1B4], ebx
0x140026f21  mov     [rsp+1F8h+var_1A8], rbx
0x140026f26  mov     rcx, [rcx+18h]
0x140026f2a  mov     rax, [rcx]
0x140026f2d  lea     r8, [rsp+1F8h+var_1A8]
0x140026f32  lea     rdx, IID_IPrintWriteStreamFlush
0x140026f39  mov     rax, [rax]
0x140026f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f41  cmp     eax, 80004002h
0x140026f46  jz      short loc_140026F5C
0x140026f48  test    eax, eax
0x140026f4a  jns     short loc_140026F53
0x140026f4c  mov     ecx, eax; this
0x140026f4e  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140026f53  lea     r15, WPP_GLOBAL_Control
0x140026f5a  jmp     short loc_140026F93
0x140026f5c  lea     r15, WPP_GLOBAL_Control
0x140026f63  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f6a  cmp     rcx, r15
0x140026f6d  jz      short loc_140026F93
0x140026f6f  test    dword ptr [rcx+1Ch], 200h
0x140026f76  jz      short loc_140026F93
0x140026f78  cmp     byte ptr [rcx+19h], 3
0x140026f7c  jb      short loc_140026F93
0x140026f7e  mov     edx, 0Eh
0x140026f83  lea     r8, WPP_94258a397080385d6808b2748fb65100_Traceguids
0x140026f8a  mov     rcx, [rcx+10h]
0x140026f8e  call    WPP_SF_
0x140026f93  mov     [rsp+1F8h+var_1A0], rbx
0x140026f98  mov     rcx, [rdi+20h]
0x140026f9c  mov     rax, [rcx]
0x140026f9f  lea     r8, [rsp+1F8h+var_1A0]
0x140026fa4  lea     rdx, IID_IPrintReadStreamX
0x140026fab  mov     rax, [rax]
0x140026fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fb3  cmp     eax, 80004002h
0x140026fb8  jz      short loc_140026FC5
0x140026fba  test    eax, eax
0x140026fbc  jns     short loc_140026FF5
0x140026fbe  mov     ecx, eax; this
0x140026fc0  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140026fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140026fcc  cmp     rcx, r15
0x140026fcf  jz      short loc_140026FF5
0x140026fd1  test    dword ptr [rcx+1Ch], 200h
0x140026fd8  jz      short loc_140026FF5
0x140026fda  cmp     byte ptr [rcx+19h], 3
0x140026fde  jb      short loc_140026FF5
0x140026fe0  mov     edx, 0Fh
0x140026fe5  lea     r8, WPP_94258a397080385d6808b2748fb65100_Traceguids
0x140026fec  mov     rcx, [rcx+10h]
0x140026ff0  call    WPP_SF_
0x140026ff5  mov     al, [rdi+40h]
0x140026ff8  test    al, al
0x140026ffa  jnz     loc_1400271FD
0x140027000  cmp     [rsp+1F8h+var_1B4], ebx
0x140027004  jnz     loc_1400271FD
0x14002700a  mov     [rsp+1F8h+var_1B8], ebx
0x14002700e  xor     edx, edx; perrinfo
0x140027010  xor     ecx, ecx; dwReserved
0x140027012  call    cs:__imp_SetErrorInfo
0x140027018  mov     rcx, [rdi+20h]
0x14002701c  mov     rax, [rcx]
0x14002701f  lea     rdx, [rsp+1F8h+var_1B4]
0x140027024  mov     qword ptr [rsp+1F8h+var_1D8], rdx; unsigned int
0x140027029  lea     r9, [rsp+1F8h+var_1B8]
0x14002702e  mov     r8d, [rdi+30h]
0x140027032  mov     rdx, [rdi+38h]
0x140027036  mov     rax, [rax+20h]
0x14002703a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002703f  mov     ecx, eax; this
0x140027041  call    ?ThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::ThrowFromHRErrorInfo(long,char const *,ulong)
0x140027046  mov     r8d, [rsp+1F8h+var_1B8]
0x14002704b  test    r8d, r8d
0x14002704e  jz      loc_14002714F
0x140027054  mov     rcx, cs:WPP_GLOBAL_Control
0x14002705b  cmp     rcx, r15
0x14002705e  jz      short loc_14002708C
0x140027060  test    dword ptr [rcx+1Ch], 200h
0x140027067  jz      short loc_14002708C
0x140027069  cmp     byte ptr [rcx+19h], 3
0x14002706d  jb      short loc_14002708C
0x14002706f  mov     edx, 10h
0x140027074  mov     r9d, r8d
0x140027077  lea     r8, WPP_94258a397080385d6808b2748fb65100_Traceguids
0x14002707e  mov     rcx, [rcx+10h]
0x140027082  call    WPP_SF_d
0x140027087  mov     r8d, [rsp+1F8h+var_1B8]
0x14002708c  mov     [rsp+1F8h+var_1B0], ebx
0x140027090  mov     rcx, [rdi+18h]
0x140027094  mov     rax, [rcx]
0x140027097  lea     r9, [rsp+1F8h+var_1B0]
0x14002709c  mov     rdx, [rdi+38h]
0x1400270a0  mov     rax, [rax+20h]
0x1400270a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400270a9  test    eax, eax
0x1400270ab  jns     short loc_1400270B4
0x1400270ad  mov     ecx, eax; this
0x1400270af  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400270b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400270bb  cmp     rcx, r15
0x1400270be  jz      short loc_1400270E9
0x1400270c0  test    dword ptr [rcx+1Ch], 200h
0x1400270c7  jz      short loc_1400270E9
0x1400270c9  cmp     byte ptr [rcx+19h], 3
0x1400270cd  jb      short loc_1400270E9
0x1400270cf  mov     edx, 11h
0x1400270d4  mov     r9d, [rsp+1F8h+var_1B8]
0x1400270d9  lea     r8, WPP_94258a397080385d6808b2748fb65100_Traceguids
0x1400270e0  mov     rcx, [rcx+10h]
0x1400270e4  call    WPP_SF_d
0x1400270e9  mov     eax, [rsp+1F8h+var_1B0]
0x1400270ed  cmp     [rsp+1F8h+var_1B8], eax
0x1400270f1  jz      short loc_14002714F
0x1400270f3  xor     r8d, r8d; unsigned int
0x1400270f6  lea     rdx, asc_1400696D8; "-"
0x1400270fd  lea     rcx, [rsp+1F8h+var_188]; this
0x140027102  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140027107  nop
0x140027108  mov     edx, 8000FFFFh; unsigned int
0x14002710d  lea     rcx, [rsp+1F8h+var_188]; this
0x140027112  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140027117  lea     rdx, aCbreadCbwritte; "cbRead != cbWritten"
0x14002711e  lea     rcx, [rsp+1F8h+var_188]; this
0x140027123  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140027128  lea     rdx, [rsp+1F8h+var_188]; struct SplException::THResultException *
0x14002712d  lea     rcx, [rsp+1F8h+pExceptionObject]; this
0x140027135  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14002713a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140027141  lea     rcx, [rsp+1F8h+pExceptionObject]; pExceptionObject
0x140027149  call    _CxxThrowException_0
0x14002714f  mov     rcx, [rsp+1F8h+var_1A0]
0x140027154  test    rcx, rcx
0x140027157  jz      loc_140026FF5
0x14002715d  mov     rax, [rcx]
0x140027160  mov     rax, [rax+38h]
0x140027164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027169  mov     ecx, eax
0x14002716b  mov     eax, [rdi+44h]
0x14002716e  cmp     ecx, eax
0x140027170  jz      loc_140026FF5
0x140027176  mov     [rdi+44h], ecx
0x140027179  mov     rax, cs:WPP_GLOBAL_Control
0x140027180  cmp     rax, r15
0x140027183  jz      short loc_1400271B0
0x140027185  test    dword ptr [rax+1Ch], 200h
0x14002718c  jz      short loc_1400271B0
0x14002718e  cmp     byte ptr [rax+19h], 3
0x140027192  jb      short loc_1400271B0
0x140027194  mov     edx, 12h
0x140027199  lea     r8, WPP_94258a397080385d6808b2748fb65100_Traceguids
0x1400271a0  mov     rcx, [rax+10h]
0x1400271a4  call    WPP_SF_
0x1400271a9  mov     rax, cs:WPP_GLOBAL_Control
0x1400271b0  mov     rcx, [rsp+1F8h+var_1A8]
0x1400271b5  test    rcx, rcx
0x1400271b8  jz      loc_140026FF5
0x1400271be  cmp     rax, r15
0x1400271c1  jz      short loc_1400271EC
0x1400271c3  test    dword ptr [rax+1Ch], 200h
0x1400271ca  jz      short loc_1400271EC
0x1400271cc  cmp     byte ptr [rax+19h], 3
0x1400271d0  jb      short loc_1400271EC
0x1400271d2  mov     edx, 13h
0x1400271d7  lea     r8, WPP_94258a397080385d6808b2748fb65100_Traceguids
0x1400271de  mov     rcx, [rax+10h]
0x1400271e2  call    WPP_SF_
0x1400271e7  mov     rcx, [rsp+1F8h+var_1A8]
0x1400271ec  mov     rax, [rcx]
0x1400271ef  mov     rax, [rax+18h]
0x1400271f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400271f8  jmp     loc_140026FF5
0x1400271fd  mov     rcx, [rsp+1F8h+var_1A8]
0x140027202  test    rcx, rcx
0x140027205  jz      short loc_140027214
0x140027207  mov     rax, [rcx]
0x14002720a  mov     rax, [rax+18h]
0x14002720e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027213  nop
0x140027214  lea     rcx, [rsp+1F8h+var_1A0]
0x140027219  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002721e  nop
0x14002721f  lea     rcx, [rsp+1F8h+var_1A8]
0x140027224  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140027229  nop
0x14002722a  jmp     short loc_14002725F
0x14002722c  mov     r14d, [rsp+1F8h+var_1B8]
0x140027231  test    r14d, r14d
0x140027234  js      short loc_140027244
0x140027236  mov     rdi, [rsp+1F8h+var_198]
0x14002723b  jmp     short loc_14002725F
0x14002723d  jmp     short $+2
0x14002723f  mov     r14d, [rsp+1F8h+var_1B8]
0x140027244  mov     rdi, [rsp+1F8h+var_198]
0x140027249  mov     rcx, [rdi+28h]
0x14002724d  mov     rax, [rcx]
0x140027250  xor     r8d, r8d
0x140027253  mov     edx, r14d
0x140027256  mov     rax, [rax+18h]
0x14002725a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002725f  mov     rcx, [rdi+28h]
0x140027263  mov     rdx, [rcx]
0x140027266  mov     rax, [rdx+20h]
0x14002726a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002726f  mov     eax, r14d
0x140027272  mov     rcx, [rsp+1F8h+var_38]
0x14002727a  xor     rcx, rsp; StackCookie
0x14002727d  call    __security_check_cookie
0x140027282  add     rsp, 1D8h
0x140027289  pop     r15
0x14002728b  pop     r14
0x14002728d  pop     rdi
0x14002728e  pop     rbx
0x14002728f  retn
```
