# COfflineFilesSyncStatusProviderInternal::GetSyncStatusProperties(ushort const *,ushort const *,IOfflineFilesSyncItem * *)

- ea: `0x180024e70`
- end: `0x18002518d`
- name: `?GetSyncStatusProperties@COfflineFilesSyncStatusProviderInternal@@UEAAJPEBG0PEAPEAUIOfflineFilesSyncItem@@@Z`
- size: `797`
- prototype: `int(COfflineFilesSyncStatusProviderInternal *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IOfflineFilesSyncItem **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002810`
- `0x180005b70`
- `0x180007280`
- `0x18000735c`
- `0x180010ff4`
- `0x18001101c`
- `0x180024e70`
- `0x1800258d0`
- `0x180026280`
- `0x18003fc84`
- `0x18004c636`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x180024ef0`
- `SHLWAPI!PathIsUNCW` at `0x180024ef0`
- `SHLWAPI!__imp_SHFormatDateTimeW` at `0x1800250f3`
- `SHLWAPI!__imp_SHFormatDateTimeW` at `0x18002510a`
- `SHLWAPI!__imp_SHFormatDateTimeW` at `0x1800250f3`
- `SHLWAPI!__imp_SHFormatDateTimeW` at `0x18002510a`

## pseudocode

```c
__int64 __fastcall COfflineFilesSyncStatusProviderInternal::GetSyncStatusProperties(
        COfflineFilesSyncStatusProviderInternal *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IOfflineFilesSyncItem **a4)
{
  int v8; // ebx
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *ConstBuffer; // rax
  int v11; // eax
  struct IOfflineFilesSyncItem *v12; // rdi
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME pft; // [rsp+38h] [rbp-C8h] BYREF
  FILETIME v16; // [rsp+40h] [rbp-C0h] BYREF
  struct IOfflineFilesSyncItem *v17; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v18[260]; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+258h] [rbp+158h]
  _WORD *v20; // [rsp+260h] [rbp+160h]
  _WORD *v21; // [rsp+268h] [rbp+168h]
  _WORD *v22; // [rsp+270h] [rbp+170h]
  __int64 v23; // [rsp+278h] [rbp+178h]
  __int64 v24; // [rsp+280h] [rbp+180h]
  WCHAR v25; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v26[526]; // [rsp+292h] [rbp+192h] BYREF
  WCHAR pszBuf; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v28[526]; // [rsp+4A2h] [rbp+3A2h] BYREF

  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids);
  }
  v17 = 0;
  v8 = -2147024894;
  if ( a2 && PathIsUNCW(a2) )
  {
    v19 = 34078720;
    v23 = 520;
    v21 = v18;
    v24 = 520;
    v22 = v18;
    v20 = v18;
    v18[0] = 0;
    v8 = CPath::Copy((CPath *)v18, a2);
    if ( v8 >= 0 )
    {
      if ( (int)CPath::StripToUNCServerShare((CPath *)v18) >= 0
        && (v9 = CPath::_GetConstBuffer((CPath *)v18),
            (unsigned int)ShouldShowStatusForPath(v9, 1, *((struct IOfflineFilesCache **)this + 3))) )
      {
        pft = 0;
        v16 = 0;
        v14 = 1;
        ConstBuffer = CPath::_GetConstBuffer((CPath *)v18);
        v11 = CSyncItemLog::QueryEntry(*((CSyncItemLog **)this + 2), ConstBuffer, &v17, a3);
        v8 = v11;
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids,
            (_DWORD)a3,
            (__int64)a2,
            v11);
        }
        if ( v8 >= 0 )
        {
          v12 = v17;
          (*(void (__fastcall **)(struct IOfflineFilesSyncItem *, unsigned int *))(*(_QWORD *)v17 + 128LL))(v17, &v14);
          if ( v14 - 1 > 3 )
          {
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids, v14);
            }
            v14 = 1;
            (*(void (__fastcall **)(struct IOfflineFilesSyncItem *, unsigned int *))(*(_QWORD *)v12 + 64LL))(v12, &v14);
          }
          (*(void (__fastcall **)(struct IOfflineFilesSyncItem *, FILETIME *))(*(_QWORD *)v12 + 112LL))(v12, &pft);
          (*(void (__fastcall **)(struct IOfflineFilesSyncItem *, FILETIME *))(*(_QWORD *)v12 + 104LL))(v12, &v16);
          pszBuf = 0;
          memset_0(v28, 0, 0x206u);
          v25 = 0;
          memset_0(v26, 0, 0x206u);
          SHFormatDateTimeW(&pft, 0, &pszBuf, 0x104u);
          SHFormatDateTimeW(&v16, 0, &v25, 0x104u);
          if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
          {
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              (unsigned int)WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids,
              (unsigned int)&pszBuf,
              (__int64)&v25,
              v8);
          }
          *a4 = v12;
        }
      }
      else
      {
        v8 = -2147024894;
      }
    }
    CPath::~CPath((CPath *)v18);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180024e70  push    rbp
0x180024e72  push    rbx
0x180024e73  push    rsi
0x180024e74  push    rdi
0x180024e75  push    r14
0x180024e77  push    r15
0x180024e79  lea     rbp, [rsp-5C8h]
0x180024e81  sub     rsp, 6C8h
0x180024e88  mov     rax, cs:__security_cookie
0x180024e8f  xor     rax, rsp
0x180024e92  mov     [rbp+5F0h+var_40], rax
0x180024e99  mov     r15, r9
0x180024e9c  mov     r14, r8
0x180024e9f  mov     rdi, rdx
0x180024ea2  mov     rsi, rcx
0x180024ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180024eac  lea     rax, WPP_GLOBAL_Control
0x180024eb3  cmp     rcx, rax
0x180024eb6  jz      short loc_180024ED6
0x180024eb8  test    dword ptr [rcx+1Ch], 4000000h
0x180024ebf  jz      short loc_180024ED6
0x180024ec1  mov     rcx, [rcx+10h]
0x180024ec5  lea     r8, WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids
0x180024ecc  mov     edx, 1Eh
0x180024ed1  call    WPP_SF_
0x180024ed6  mov     [rsp+6F0h+var_6A8], 0
0x180024edf  mov     ebx, 80070002h
0x180024ee4  test    rdi, rdi
0x180024ee7  jz      loc_18002516C
0x180024eed  mov     rcx, rdi; pszPath
0x180024ef0  call    cs:__imp_PathIsUNCW
0x180024ef6  test    eax, eax
0x180024ef8  jz      loc_18002516C
0x180024efe  mov     ecx, 208h
0x180024f03  mov     [rbp+5F0h+var_498], 2080000h
0x180024f0d  lea     rax, [rsp+6F0h+var_6A0]
0x180024f12  mov     [rbp+5F0h+var_478], rcx
0x180024f19  mov     [rbp+5F0h+var_488], rax
0x180024f20  mov     rdx, rdi; unsigned __int16 *
0x180024f23  lea     rax, [rsp+6F0h+var_6A0]
0x180024f28  mov     [rbp+5F0h+var_470], rcx
0x180024f2f  mov     [rbp+5F0h+var_480], rax
0x180024f36  lea     rcx, [rsp+6F0h+var_6A0]; this
0x180024f3b  lea     rax, [rsp+6F0h+var_6A0]
0x180024f40  mov     [rbp+5F0h+var_490], rax
0x180024f47  xor     eax, eax
0x180024f49  mov     [rsp+6F0h+var_6A0], ax
0x180024f4e  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x180024f53  mov     ebx, eax
0x180024f55  test    eax, eax
0x180024f57  js      loc_180025162
0x180024f5d  lea     rcx, [rsp+6F0h+var_6A0]; this
0x180024f62  call    ?StripToUNCServerShare@CPath@@QEAAJXZ; CPath::StripToUNCServerShare(void)
0x180024f67  test    eax, eax
0x180024f69  js      loc_18002515D
0x180024f6f  lea     rcx, [rsp+6F0h+var_6A0]; this
0x180024f74  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180024f79  mov     r8, [rsi+18h]; struct IOfflineFilesCache *
0x180024f7d  mov     ebx, 1
0x180024f82  mov     edx, ebx; int
0x180024f84  mov     rcx, rax; unsigned __int16 *
0x180024f87  call    ?ShouldShowStatusForPath@@YAHPEBGHPEAUIOfflineFilesCache@@@Z; ShouldShowStatusForPath(ushort const *,int,IOfflineFilesCache *)
0x180024f8c  test    eax, eax
0x180024f8e  jz      loc_18002515D
0x180024f94  lea     rcx, [rsp+6F0h+var_6A0]; this
0x180024f99  mov     qword ptr [rsp+6F0h+pft.dwLowDateTime], 0
0x180024fa2  mov     qword ptr [rsp+6F0h+var_6B0.dwLowDateTime], 0
0x180024fab  mov     [rsp+6F0h+var_6C0], ebx
0x180024faf  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180024fb4  mov     rcx, [rsi+10h]; this
0x180024fb8  lea     r8, [rsp+6F0h+var_6A8]; struct IOfflineFilesSyncItem **
0x180024fbd  mov     rdx, rax; unsigned __int16 *
0x180024fc0  mov     r9, r14; unsigned __int16 *
0x180024fc3  call    ?QueryEntry@CSyncItemLog@@QEAAJPEBGPEAPEAUIOfflineFilesSyncItem@@0@Z; CSyncItemLog::QueryEntry(ushort const *,IOfflineFilesSyncItem * *,ushort const *)
0x180024fc8  mov     ebx, eax
0x180024fca  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fd1  lea     rsi, WPP_GLOBAL_Control
0x180024fd8  cmp     rcx, rsi
0x180024fdb  jz      short loc_180025007
0x180024fdd  test    dword ptr [rcx+1Ch], 4000000h
0x180024fe4  jz      short loc_180025007
0x180024fe6  mov     rcx, [rcx+10h]
0x180024fea  lea     r8, WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids
0x180024ff1  mov     [rsp+6F0h+var_6C8], eax
0x180024ff5  mov     edx, 1Fh
0x180024ffa  mov     r9, r14
0x180024ffd  mov     [rsp+6F0h+var_6D0], rdi
0x180025002  call    WPP_SF_SSD
0x180025007  test    ebx, ebx
0x180025009  js      loc_180025162
0x18002500f  mov     rdi, [rsp+6F0h+var_6A8]
0x180025014  lea     rdx, [rsp+6F0h+var_6C0]
0x180025019  mov     rcx, rdi
0x18002501c  mov     rax, [rdi]
0x18002501f  mov     rax, [rax+80h]
0x180025026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002502b  mov     r9d, [rsp+6F0h+var_6C0]
0x180025030  lea     eax, [r9-1]
0x180025034  cmp     eax, 3
0x180025037  jbe     short loc_18002507C
0x180025039  mov     rcx, cs:WPP_GLOBAL_Control
0x180025040  cmp     rcx, rsi
0x180025043  jz      short loc_180025060
0x180025045  test    byte ptr [rcx+1Ch], 2
0x180025049  jz      short loc_180025060
0x18002504b  mov     rcx, [rcx+10h]
0x18002504f  lea     r8, WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids
0x180025056  mov     edx, 20h ; ' '
0x18002505b  call    WPP_SF_d
0x180025060  mov     [rsp+6F0h+var_6C0], 1
0x180025068  lea     rdx, [rsp+6F0h+var_6C0]
0x18002506d  mov     rax, [rdi]
0x180025070  mov     rcx, rdi
0x180025073  mov     rax, [rax+40h]
0x180025077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002507c  mov     rax, [rdi]
0x18002507f  lea     rdx, [rsp+6F0h+pft]
0x180025084  mov     rcx, rdi
0x180025087  mov     rax, [rax+70h]
0x18002508b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025090  mov     rax, [rdi]
0x180025093  lea     rdx, [rsp+6F0h+var_6B0]
0x180025098  mov     rcx, rdi
0x18002509b  mov     rax, [rax+68h]
0x18002509f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250a4  xor     eax, eax
0x1800250a6  lea     rcx, [rbp+5F0h+var_24E]; void *
0x1800250ad  mov     esi, 206h
0x1800250b2  mov     [rbp+5F0h+pszBuf], ax
0x1800250b9  mov     r8d, esi; Size
0x1800250bc  xor     edx, edx; Val
0x1800250be  call    memset_0
0x1800250c3  xor     eax, eax
0x1800250c5  lea     rcx, [rbp+5F0h+var_45E]; void *
0x1800250cc  mov     r8d, esi; Size
0x1800250cf  mov     [rbp+5F0h+var_460], ax
0x1800250d6  xor     edx, edx; Val
0x1800250d8  call    memset_0
0x1800250dd  mov     esi, 104h
0x1800250e2  lea     r8, [rbp+5F0h+pszBuf]; pszBuf
0x1800250e9  mov     r9d, esi; cchBuf
0x1800250ec  lea     rcx, [rsp+6F0h+pft]; pft
0x1800250f1  xor     edx, edx; pdwFlags
0x1800250f3  call    cs:__imp_SHFormatDateTimeW
0x1800250f9  mov     r9d, esi; cchBuf
0x1800250fc  lea     r8, [rbp+5F0h+var_460]; pszBuf
0x180025103  xor     edx, edx; pdwFlags
0x180025105  lea     rcx, [rsp+6F0h+var_6B0]; pft
0x18002510a  call    cs:__imp_SHFormatDateTimeW
0x180025110  mov     rcx, cs:WPP_GLOBAL_Control
0x180025117  lea     rax, WPP_GLOBAL_Control
0x18002511e  cmp     rcx, rax
0x180025121  jz      short loc_180025158
0x180025123  test    dword ptr [rcx+1Ch], 4000000h
0x18002512a  jz      short loc_180025158
0x18002512c  mov     rcx, [rcx+10h]
0x180025130  lea     rax, [rbp+5F0h+var_460]
0x180025137  mov     edx, 21h ; '!'
0x18002513c  mov     [rsp+6F0h+var_6C8], ebx
0x180025140  lea     r9, [rbp+5F0h+pszBuf]
0x180025147  mov     [rsp+6F0h+var_6D0], rax
0x18002514c  lea     r8, WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids
0x180025153  call    WPP_SF_SSD
0x180025158  mov     [r15], rdi
0x18002515b  jmp     short loc_180025162
0x18002515d  mov     ebx, 80070002h
0x180025162  lea     rcx, [rsp+6F0h+var_6A0]; this
0x180025167  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x18002516c  mov     eax, ebx
0x18002516e  mov     rcx, [rbp+5F0h+var_40]
0x180025175  xor     rcx, rsp; StackCookie
0x180025178  call    __security_check_cookie
0x18002517d  add     rsp, 6C8h
0x180025184  pop     r15
0x180025186  pop     r14
0x180025188  pop     rdi
0x180025189  pop     rsi
0x18002518a  pop     rbx
0x18002518b  pop     rbp
0x18002518c  retn
```
