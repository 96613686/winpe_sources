# CSmbFile::AsyncOpen(_FILETIME,unsigned __int64,ulong)

- ea: `0x1800ed0a0`
- end: `0x1800ed916`
- name: `?AsyncOpen@CSmbFile@@UEAAXU_FILETIME@@_KK@Z`
- size: `2166`
- prototype: `void __fastcall(CSmbFile *this, struct _FILETIME, __int64, char)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180008b70`
- `0x18000f5f0`
- `0x180012b18`
- `0x180014310`
- `0x18001d7f0`
- `0x180033420`
- `0x180033480`
- `0x18003dcb0`
- `0x180050560`
- `0x1800586f0`
- `0x18006b0c0`
- `0x18009d024`
- `0x1800a1114`
- `0x1800ba40c`
- `0x1800c7278`
- `0x1800caac0`
- `0x1800ed0a0`
- `0x1800ed91c`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed2a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed3bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed4fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed50f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed59d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed5a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed5b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed631`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed76f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed2a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed3bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed4fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed50f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed59d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed5a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed5b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed631`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed76f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed783`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ed3a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ed3a1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800ed4e9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800ed4e9`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800ed3ae`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800ed3ae`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800ed765`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800ed765`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800ed58f`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800ed613`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800ed58f`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800ed613`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CSmbFile::AsyncOpen(CSmbFile *this, struct _FILETIME a2, __int64 a3, char a4)
{
  __int64 v8; // rax
  char *v9; // rdx
  bool v10; // zf
  char v11; // r14
  const struct TokenHandle *v12; // rbx
  CNestedImpersonation *v13; // rcx
  int v14; // ebx
  bool IsAppContainerToken; // al
  int v16; // edx
  unsigned int v17; // eax
  unsigned int v18; // edx
  __int64 v19; // rax
  unsigned int LastError; // ecx
  signed int v21; // ebx
  struct _TP_CALLBACK_ENVIRON_V3 *v22; // r9
  PTP_IO ThreadpoolIo; // rax
  unsigned int v24; // ecx
  void *v25; // rcx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  char v28; // bl
  struct _FILETIME v29; // rax
  unsigned int v30; // ecx
  __int64 v31; // rcx
  ComError *v32; // rdi
  ComError *v33; // rax
  CSmbFile *v34; // rbx
  void *v35; // [rsp+30h] [rbp-428h]
  char v36[8]; // [rsp+50h] [rbp-408h] BYREF
  char *v37; // [rsp+58h] [rbp-400h]
  ComError *v38; // [rsp+60h] [rbp-3F8h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-3E8h] BYREF
  __int128 v40; // [rsp+78h] [rbp-3E0h]
  int v41; // [rsp+88h] [rbp-3D0h]
  int v42; // [rsp+8Ch] [rbp-3CCh]
  int v43; // [rsp+90h] [rbp-3C8h]
  void **v44; // [rsp+D0h] [rbp-388h] BYREF
  __int128 v45; // [rsp+D8h] [rbp-380h]
  unsigned int v46; // [rsp+E8h] [rbp-370h]
  int v47; // [rsp+ECh] [rbp-36Ch]
  int v48; // [rsp+F0h] [rbp-368h]
  void **v49; // [rsp+130h] [rbp-328h] BYREF
  __int128 v50; // [rsp+138h] [rbp-320h]
  int v51; // [rsp+148h] [rbp-310h]
  int v52; // [rsp+14Ch] [rbp-30Ch]
  int v53; // [rsp+150h] [rbp-308h]
  void **v54; // [rsp+190h] [rbp-2C8h] BYREF
  __int128 v55; // [rsp+198h] [rbp-2C0h]
  signed int v56; // [rsp+1A8h] [rbp-2B0h]
  int v57; // [rsp+1ACh] [rbp-2ACh]
  int v58; // [rsp+1B0h] [rbp-2A8h]
  void **v59; // [rsp+1F0h] [rbp-268h] BYREF
  __int128 v60; // [rsp+1F8h] [rbp-260h]
  unsigned int v61; // [rsp+208h] [rbp-250h]
  int v62; // [rsp+20Ch] [rbp-24Ch]
  int v63; // [rsp+210h] [rbp-248h]
  void **v64; // [rsp+250h] [rbp-208h] BYREF
  __int128 v65; // [rsp+258h] [rbp-200h]
  unsigned int v66; // [rsp+268h] [rbp-1F0h]
  int v67; // [rsp+26Ch] [rbp-1ECh]
  int v68; // [rsp+270h] [rbp-1E8h]
  void **v69; // [rsp+2B0h] [rbp-1A8h] BYREF
  __int128 v70; // [rsp+2B8h] [rbp-1A0h]
  unsigned int v71; // [rsp+2C8h] [rbp-190h]
  int v72; // [rsp+2CCh] [rbp-18Ch]
  int v73; // [rsp+2D0h] [rbp-188h]
  void **v74; // [rsp+310h] [rbp-148h] BYREF
  __int128 v75; // [rsp+318h] [rbp-140h]
  unsigned int v76; // [rsp+328h] [rbp-130h]
  int v77; // [rsp+32Ch] [rbp-12Ch]
  int v78; // [rsp+330h] [rbp-128h]
  void **v79; // [rsp+370h] [rbp-E8h] BYREF
  __int128 v80; // [rsp+378h] [rbp-E0h]
  int v81; // [rsp+388h] [rbp-D0h]
  int v82; // [rsp+38Ch] [rbp-CCh]
  int v83; // [rsp+390h] [rbp-C8h]
  void **v84[17]; // [rsp+3D0h] [rbp-88h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+468h] [rbp+10h] BYREF
  const unsigned __int16 *v87; // [rsp+470h] [rbp+18h] BYREF

  v37 = (char *)this + 8;
  CCritSec2::enter((CSmbFile *)((char *)this + 8));
  v36[0] = 1;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_544ed435ee403dfadff71ae516532c05_Traceguids,
      *((_QWORD *)this + 13) + 12LL);
  _InterlockedAdd(&dword_180145058, 1u);
  v87 = (const unsigned __int16 *)&GenericStringHandle<unsigned short>::s_EmptyString;
  if ( *((_BYTE *)this + 376) || (v8 = *((_QWORD *)this + 48), v9 = (char *)(v8 + 24), !v8) )
    v9 = (char *)this + 104;
  GenericStringHandle<unsigned short>::operator=(&v87, v9);
  if ( !*((_BYTE *)this + 376) || (v10 = (a4 & 8) == 0, v11 = 1, v10) )
    v11 = 0;
  try
  {
    *((struct _FILETIME *)this + 42) = a2;
    *((_QWORD *)this + 19) = a3;
    if ( v11 )
    {
      TokenHandle::copyEx((char *)this + 392, &LastWriteTime, 3, 2);
      TokenHandle::EnablePrivilege((TokenHandle *)&LastWriteTime, 8);
      v12 = (CSmbFile *)((char *)this + 400);
      TokenHandle::operator=((char *)this + 400, &LastWriteTime);
      TokenHandle::Decrement((TokenHandle *)&LastWriteTime);
    }
    else
    {
      v12 = (CSmbFile *)((char *)this + 400);
      TokenHandle::operator=((char *)this + 400, (char *)this + 392);
    }
    CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)v84, v12);
    CNestedImpersonation::CallSetTokenEnterpriseExempt(v13, *((const unsigned __int16 **)this + 34));
    v14 = *((_BYTE *)this + 312) != 0 ? 1610612736 : 0x40000000;
    IsAppContainerToken = CNestedImpersonation::IsAppContainerToken((CNestedImpersonation *)v84);
    v16 = v14 | 0x110000;
    if ( IsAppContainerToken )
      v16 = v14;
    v17 = v16 | 0x8000000;
    if ( !*((_BYTE *)this + 376) )
      v17 = v16;
    v18 = (*((_BYTE *)this + 376) != 0 ? 0x80000000 : 0x40000000) | 0x1000000;
    if ( !v11 )
      v18 = *((_BYTE *)this + 376) != 0 ? 0x80000000 : 0x40000000;
    v19 = BITSCreateFile2(v87 + 6, v18, 1u, 0, 3u, v17, v35);
    *((_QWORD *)this + 40) = v19;
    if ( v19 == -1 )
    {
      if ( !*((_BYTE *)this + 376) && GetLastError() == 2 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_544ed435ee403dfadff71ae516532c05_Traceguids);
        }
        v40 = 0;
        pExceptionObject = &ComError::`vftable';
        v41 = -2147221503;
        v42 = 491;
        v43 = 1;
        throw (ComError *)&pExceptionObject;
      }
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v45 = 0;
      v44 = &ComError::`vftable';
      v46 = LastError;
      v47 = 494;
      v48 = 1;
      throw (ComError *)&v44;
    }
    CNestedImpersonation::~CNestedImpersonation(v84);
    SetLastError(0);
    if ( GetFileType(*((HANDLE *)this + 40)) != 1 )
    {
      v21 = GetLastError();
      if ( !v21 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_544ed435ee403dfadff71ae516532c05_Traceguids);
        v50 = 0;
        v49 = &ComError::`vftable';
        v51 = -2147024809;
        v52 = 0;
        v53 = 1;
        throw (ComError *)&v49;
      }
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_544ed435ee403dfadff71ae516532c05_Traceguids);
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      v55 = 0;
      v54 = &ComError::`vftable';
      v56 = v21;
      v57 = 0;
      v58 = 1;
      throw (ComError *)&v54;
    }
    v22 = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)this + 35);
    if ( !v22 )
      v22 = (struct _TP_CALLBACK_ENVIRON_V3 *)((char *)g_Manager + 992);
    ThreadpoolIo = CreateThreadpoolIo(*((HANDLE *)this + 40), CSmbFile::StaticCompletionRoutine, this, v22);
    *((_QWORD *)this + 52) = ThreadpoolIo;
    if ( !ThreadpoolIo )
    {
      if ( (int)GetLastError() > 0 )
        v24 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v24 = GetLastError();
      v60 = 0;
      v59 = &ComError::`vftable';
      v61 = v24;
      v62 = 528;
      v63 = 1;
      throw (ComError *)&v59;
    }
    LastWriteTime = 0;
    v25 = (void *)*((_QWORD *)this + 40);
    if ( *((_BYTE *)this + 376) )
    {
      if ( !GetFileTime(v25, 0, 0, &LastWriteTime) )
      {
        if ( (int)GetLastError() > 0 )
          v26 = (unsigned __int16)GetLastError() | 0x80070000;
        else
          v26 = GetLastError();
        v65 = 0;
        v64 = &ComError::`vftable';
        v66 = v26;
        v67 = 541;
        v68 = 1;
        throw (ComError *)&v64;
      }
    }
    else if ( !GetFileTime(v25, &LastWriteTime, 0, 0) )
    {
      if ( (int)GetLastError() > 0 )
        v27 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v27 = GetLastError();
      v70 = 0;
      v69 = &ComError::`vftable';
      v71 = v27;
      v72 = 551;
      v73 = 1;
      throw (ComError *)&v69;
    }
    v28 = 0;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_DDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_544ed435ee403dfadff71ae516532c05_Traceguids,
        *((unsigned int *)this + 85),
        *((_DWORD *)this + 84),
        LastWriteTime.dwHighDateTime,
        LastWriteTime.dwLowDateTime);
    if ( *((_QWORD *)this + 48) || !*((_QWORD *)this + 42) )
    {
      v29 = LastWriteTime;
    }
    else
    {
      v29 = LastWriteTime;
      if ( *((_QWORD *)this + 42) != LastWriteTime )
        v28 = 1;
    }
    *((struct _FILETIME *)this + 42) = v29;
    LastWriteTime = 0;
    if ( !GetFileSizeEx(*((HANDLE *)this + 40), (PLARGE_INTEGER)&LastWriteTime) )
    {
      if ( (int)GetLastError() > 0 )
        v30 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v30 = GetLastError();
      v75 = 0;
      v74 = &ComError::`vftable';
      v76 = v30;
      v77 = 576;
      v78 = 1;
      throw (ComError *)&v74;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_DDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_544ed435ee403dfadff71ae516532c05_Traceguids,
        HIDWORD(*((_QWORD *)this + 19)),
        *((_DWORD *)this + 38),
        LastWriteTime.dwHighDateTime,
        LastWriteTime.dwLowDateTime);
    v31 = *((_QWORD *)this + 19);
    if ( v31 == -1 || v31 == LastWriteTime )
    {
      *((struct _FILETIME *)this + 19) = LastWriteTime;
      if ( !v28 )
      {
LABEL_83:
        (*(void (__fastcall **)(CSmbFile *, _QWORD, _QWORD))(*(_QWORD *)this + 488LL))(this, 0, 0);
        goto LABEL_88;
      }
    }
    else
    {
      *((struct _FILETIME *)this + 19) = LastWriteTime;
    }
    if ( *((_QWORD *)this + 48) )
    {
      (*(void (__fastcall **)(CSmbFile *))(*(_QWORD *)this + 56LL))(this);
      CSmbFile::DeleteTheFile(this);
      v80 = 0;
      v79 = &ComError::`vftable';
      v81 = -2147221503;
      v82 = 595;
      v83 = 1;
      throw (ComError *)&v79;
    }
    goto LABEL_83;
  }
  catch ( ComError *v38 )
  {
    v32 = v38;
    v33 = ComError::ComError((ComError *)v84, v38);
    LogException(v33);
    v34 = this;
    (*(void (__fastcall **)(CSmbFile *))(*(_QWORD *)v34 + 56LL))(v34);
    (*(void (__fastcall **)(CSmbFile *, _QWORD, _QWORD))(*(_QWORD *)v34 + 488LL))(v34, *((unsigned int *)v32 + 6), 0);
  }
LABEL_88:
  GenericStringHandle<unsigned short>::FreeIt(&v87);
  HoldCritSec::~HoldCritSec((HoldCritSec *)v36);
}

```

## disassembly

```asm
0x1800ed0a0  mov     [rsp+arg_18], rbx
0x1800ed0a5  mov     [rsp+arg_0], rcx
0x1800ed0aa  push    rdi
0x1800ed0ab  push    r12
0x1800ed0ad  push    r13
0x1800ed0af  push    r14
0x1800ed0b1  push    r15
0x1800ed0b3  sub     rsp, 430h
0x1800ed0ba  mov     r14d, r9d
0x1800ed0bd  mov     r15, r8
0x1800ed0c0  mov     rbx, rdx
0x1800ed0c3  mov     rdi, rcx
0x1800ed0c6  add     rcx, 8; this
0x1800ed0ca  mov     [rsp+458h+var_400], rcx
0x1800ed0cf  call    ?enter@CCritSec2@@QEAAXXZ; CCritSec2::enter(void)
0x1800ed0d4  mov     r13d, 1
0x1800ed0da  mov     [rsp+458h+var_408], r13b
0x1800ed0df  lea     rax, WPP_GLOBAL_Control
0x1800ed0e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed0ed  cmp     rcx, rax
0x1800ed0f0  jz      short loc_1800ED117
0x1800ed0f2  test    dword ptr [rcx+1Ch], 800h
0x1800ed0f9  jz      short loc_1800ED117
0x1800ed0fb  mov     r9, [rdi+68h]
0x1800ed0ff  add     r9, 0Ch
0x1800ed103  lea     edx, [r13+11h]
0x1800ed107  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x1800ed10e  mov     rcx, [rcx+10h]
0x1800ed112  call    WPP_SF_S
0x1800ed117  lock add cs:dword_180145058, r13d
0x1800ed11f  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x1800ed126  mov     [rsp+458h+arg_10], rax
0x1800ed12e  xor     r12d, r12d
0x1800ed131  cmp     [rdi+178h], r12b
0x1800ed138  jnz     short loc_1800ED14A
0x1800ed13a  mov     rax, [rdi+180h]
0x1800ed141  test    rax, rax
0x1800ed144  lea     rdx, [rax+18h]
0x1800ed148  jnz     short loc_1800ED14E
0x1800ed14a  lea     rdx, [rdi+68h]
0x1800ed14e  lea     rcx, [rsp+458h+arg_10]
0x1800ed156  call    ??4?$GenericStringHandle@G@@QEAAAEAV0@AEBV0@@Z; GenericStringHandle<ushort>::operator=(GenericStringHandle<ushort> const &)
0x1800ed15b  cmp     [rdi+178h], r12b
0x1800ed162  jz      short loc_1800ED16D
0x1800ed164  test    r14b, 8
0x1800ed168  mov     r14b, r13b
0x1800ed16b  jnz     short loc_1800ED170
0x1800ed16d  mov     r14b, r12b
0x1800ed170  mov     [rdi+150h], rbx
0x1800ed177  mov     [rdi+98h], r15
0x1800ed17e  lea     rax, [rdi+188h]
0x1800ed185  test    r14b, r14b
0x1800ed188  jz      short loc_1800ED1DE
0x1800ed18a  mov     r9d, 2
0x1800ed190  lea     r8d, [r9+1]
0x1800ed194  lea     rdx, [rsp+458h+LastWriteTime]
0x1800ed19c  mov     rcx, rax
0x1800ed19f  call    ?copyEx@TokenHandle@@QEBA?AV1@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z; TokenHandle::copyEx(_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)
0x1800ed1a4  nop
0x1800ed1a5  mov     edx, 8; int
0x1800ed1aa  lea     rcx, [rsp+458h+LastWriteTime]; this
0x1800ed1b2  call    ?EnablePrivilege@TokenHandle@@QEAAXJ@Z; TokenHandle::EnablePrivilege(long)
0x1800ed1b7  lea     rbx, [rdi+190h]
0x1800ed1be  lea     rdx, [rsp+458h+LastWriteTime]
0x1800ed1c6  mov     rcx, rbx
0x1800ed1c9  call    ??4TokenHandle@@QEAAAEAV0@AEBV0@@Z; TokenHandle::operator=(TokenHandle const &)
0x1800ed1ce  nop
0x1800ed1cf  lea     rcx, [rsp+458h+LastWriteTime]; this
0x1800ed1d7  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x1800ed1dc  jmp     short loc_1800ED1F0
0x1800ed1de  lea     rbx, [rdi+190h]
0x1800ed1e5  mov     rdx, rax
0x1800ed1e8  mov     rcx, rbx
0x1800ed1eb  call    ??4TokenHandle@@QEAAAEAV0@AEBV0@@Z; TokenHandle::operator=(TokenHandle const &)
0x1800ed1f0  mov     rdx, rbx; struct TokenHandle *
0x1800ed1f3  lea     rcx, [rsp+458h+var_88]; this
0x1800ed1fb  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x1800ed200  nop
0x1800ed201  mov     rdx, [rdi+110h]; unsigned __int16 *
0x1800ed208  call    ?CallSetTokenEnterpriseExempt@CNestedImpersonation@@QEAAXPEBG@Z; CNestedImpersonation::CallSetTokenEnterpriseExempt(ushort const *)
0x1800ed20d  mov     al, [rdi+138h]
0x1800ed213  neg     al
0x1800ed215  sbb     ebx, ebx
0x1800ed217  and     ebx, 20000000h
0x1800ed21d  mov     r15d, 40000000h
0x1800ed223  add     ebx, r15d
0x1800ed226  lea     rcx, [rsp+458h+var_88]; this
0x1800ed22e  call    ?IsAppContainerToken@CNestedImpersonation@@QEAA_NXZ; CNestedImpersonation::IsAppContainerToken(void)
0x1800ed233  mov     edx, ebx
0x1800ed235  or      edx, 110000h
0x1800ed23b  test    al, al
0x1800ed23d  cmovnz  edx, ebx
0x1800ed240  mov     cl, [rdi+178h]
0x1800ed246  mov     al, cl
0x1800ed248  neg     al
0x1800ed24a  sbb     r8d, r8d
0x1800ed24d  and     r8d, r15d
0x1800ed250  add     r8d, r15d
0x1800ed253  mov     eax, edx
0x1800ed255  bts     eax, 1Bh
0x1800ed259  test    cl, cl
0x1800ed25b  cmovz   eax, edx
0x1800ed25e  mov     edx, r8d
0x1800ed261  bts     edx, 18h
0x1800ed265  test    r14b, r14b
0x1800ed268  cmovz   edx, r8d; unsigned int
0x1800ed26c  mov     rcx, [rsp+458h+arg_10]
0x1800ed274  add     rcx, 0Ch; unsigned __int16 *
0x1800ed278  mov     [rsp+458h+var_430], eax; unsigned int
0x1800ed27c  mov     [rsp+458h+var_438], 3; unsigned int
0x1800ed284  xor     r9d, r9d; struct _SECURITY_ATTRIBUTES *
0x1800ed287  mov     r8d, r13d; unsigned int
0x1800ed28a  call    ?BITSCreateFile2@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; BITSCreateFile2(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x1800ed28f  mov     [rdi+140h], rax
0x1800ed296  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ed29a  jnz     loc_1800ED392
0x1800ed2a0  cmp     [rdi+178h], r12b
0x1800ed2a7  jnz     short loc_1800ED326
0x1800ed2a9  call    cs:__imp_GetLastError
0x1800ed2af  cmp     eax, 2
0x1800ed2b2  jnz     short loc_1800ED326
0x1800ed2b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed2bb  lea     r14, WPP_GLOBAL_Control
0x1800ed2c2  cmp     rcx, r14
0x1800ed2c5  jz      short loc_1800ED2E3
0x1800ed2c7  test    dword ptr [rcx+1Ch], 800h
0x1800ed2ce  jz      short loc_1800ED2E3
0x1800ed2d0  lea     edx, [rax+11h]
0x1800ed2d3  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x1800ed2da  mov     rcx, [rcx+10h]
0x1800ed2de  call    WPP_SF_
0x1800ed2e3  xorps   xmm0, xmm0
0x1800ed2e6  movups  [rsp+458h+var_3E0], xmm0
0x1800ed2eb  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ed2f2  mov     [rsp+458h+pExceptionObject], rax
0x1800ed2f7  mov     [rsp+458h+var_3D0], 80040001h
0x1800ed302  mov     [rsp+458h+var_3CC], 1EBh
0x1800ed30d  mov     [rsp+458h+var_3C8], r13d
0x1800ed315  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ed31c  lea     rcx, [rsp+458h+pExceptionObject]; pExceptionObject
0x1800ed321  call    _CxxThrowException_0
0x1800ed326  call    cs:__imp_GetLastError
0x1800ed32c  test    eax, eax
0x1800ed32e  jg      short loc_1800ED33A
0x1800ed330  call    cs:__imp_GetLastError
0x1800ed336  mov     ecx, eax
0x1800ed338  jmp     short loc_1800ED349
0x1800ed33a  call    cs:__imp_GetLastError
0x1800ed340  movzx   ecx, ax
0x1800ed343  or      ecx, 80070000h
0x1800ed349  xorps   xmm0, xmm0
0x1800ed34c  movups  [rsp+458h+var_380], xmm0
0x1800ed354  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ed35b  mov     [rsp+458h+var_388], rax
0x1800ed363  mov     [rsp+458h+var_370], ecx
0x1800ed36a  mov     [rsp+458h+var_36C], 1EEh
0x1800ed375  mov     [rsp+458h+var_368], r13d
0x1800ed37d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ed384  lea     rcx, [rsp+458h+var_388]; pExceptionObject
0x1800ed38c  call    _CxxThrowException_0
0x1800ed392  lea     rcx, [rsp+458h+var_88]; this
0x1800ed39a  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800ed39f  xor     ecx, ecx; dwErrCode
0x1800ed3a1  call    cs:__imp_SetLastError
0x1800ed3a7  mov     rcx, [rdi+140h]; hFile
0x1800ed3ae  call    cs:__imp_GetFileType
0x1800ed3b4  cmp     eax, r13d
0x1800ed3b7  jz      loc_1800ED4BE
0x1800ed3bd  call    cs:__imp_GetLastError
0x1800ed3c3  mov     ebx, eax
0x1800ed3c5  test    eax, eax
0x1800ed3c7  jnz     short loc_1800ED43E
0x1800ed3c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed3d0  lea     r14, WPP_GLOBAL_Control
0x1800ed3d7  cmp     rcx, r14
0x1800ed3da  jz      short loc_1800ED3F5
0x1800ed3dc  test    byte ptr [rcx+1Ch], 4
0x1800ed3e0  jz      short loc_1800ED3F5
0x1800ed3e2  lea     edx, [rax+14h]
0x1800ed3e5  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x1800ed3ec  mov     rcx, [rcx+10h]
0x1800ed3f0  call    WPP_SF_
0x1800ed3f5  xorps   xmm0, xmm0
0x1800ed3f8  movups  [rsp+458h+var_320], xmm0
0x1800ed400  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ed407  mov     [rsp+458h+var_328], rax
0x1800ed40f  mov     [rsp+458h+var_310], 80070057h
0x1800ed41a  mov     [rsp+458h+var_30C], r12d
0x1800ed422  mov     [rsp+458h+var_308], r13d
0x1800ed42a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ed431  lea     rcx, [rsp+458h+var_328]; pExceptionObject
0x1800ed439  call    _CxxThrowException_0
0x1800ed43e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed445  lea     r14, WPP_GLOBAL_Control
0x1800ed44c  cmp     rcx, r14
0x1800ed44f  jz      short loc_1800ED46C
0x1800ed451  test    byte ptr [rcx+1Ch], 4
0x1800ed455  jz      short loc_1800ED46C
0x1800ed457  mov     edx, 15h
0x1800ed45c  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x1800ed463  mov     rcx, [rcx+10h]
0x1800ed467  call    WPP_SF_
0x1800ed46c  test    ebx, ebx
0x1800ed46e  jle     short loc_1800ED479
0x1800ed470  movzx   ebx, bx
0x1800ed473  or      ebx, 80070000h
0x1800ed479  xorps   xmm0, xmm0
0x1800ed47c  movups  [rsp+458h+var_2C0], xmm0
0x1800ed484  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ed48b  mov     [rsp+458h+var_2C8], rax
0x1800ed493  mov     [rsp+458h+var_2B0], ebx
0x1800ed49a  mov     [rsp+458h+var_2AC], r12d
0x1800ed4a2  mov     [rsp+458h+var_2A8], r13d
0x1800ed4aa  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ed4b1  lea     rcx, [rsp+458h+var_2C8]; pExceptionObject
0x1800ed4b9  call    _CxxThrowException_0
0x1800ed4be  mov     r9, [rdi+118h]
0x1800ed4c5  test    r9, r9
0x1800ed4c8  jnz     short loc_1800ED4D8
0x1800ed4ca  mov     r9, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x1800ed4d1  add     r9, 3E0h; pcbe
0x1800ed4d8  mov     r8, rdi; pv
0x1800ed4db  lea     rdx, ?StaticCompletionRoutine@CSmbFile@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1800ed4e2  mov     rcx, [rdi+140h]; fl
0x1800ed4e9  call    cs:__imp_CreateThreadpoolIo
0x1800ed4ef  mov     [rdi+1A0h], rax
0x1800ed4f6  test    rax, rax
0x1800ed4f9  jnz     short loc_1800ED566
0x1800ed4fb  call    cs:__imp_GetLastError
0x1800ed501  test    eax, eax
0x1800ed503  jg      short loc_1800ED50F
0x1800ed505  call    cs:__imp_GetLastError
0x1800ed50b  mov     ecx, eax
0x1800ed50d  jmp     short loc_1800ED51E
0x1800ed50f  call    cs:__imp_GetLastError
0x1800ed515  movzx   ecx, ax
0x1800ed518  or      ecx, 80070000h
0x1800ed51e  xorps   xmm0, xmm0
0x1800ed521  movups  [rsp+458h+var_260], xmm0
0x1800ed529  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ed530  mov     [rsp+458h+var_268], rax
0x1800ed538  mov     [rsp+458h+var_250], ecx
0x1800ed53f  mov     [rsp+458h+var_24C], 210h
0x1800ed54a  mov     [rsp+458h+var_248], r13d
0x1800ed552  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ed559  lea     rcx, [rsp+458h+var_268]; pExceptionObject
0x1800ed561  call    _CxxThrowException_0
0x1800ed566  mov     qword ptr [rsp+458h+LastWriteTime.dwLowDateTime], r12
0x1800ed56e  mov     rcx, [rdi+140h]; hFile
0x1800ed575  xor     r8d, r8d; lpLastAccessTime
0x1800ed578  cmp     [rdi+178h], r12b
0x1800ed57f  jz      loc_1800ED608
0x1800ed585  lea     r9, [rsp+458h+LastWriteTime]; lpLastWriteTime
0x1800ed58d  xor     edx, edx; lpCreationTime
0x1800ed58f  call    cs:__imp_GetFileTime
0x1800ed595  test    eax, eax
0x1800ed597  jnz     loc_1800ED688
0x1800ed59d  call    cs:__imp_GetLastError
0x1800ed5a3  test    eax, eax
0x1800ed5a5  jg      short loc_1800ED5B1
0x1800ed5a7  call    cs:__imp_GetLastError
0x1800ed5ad  mov     ecx, eax
0x1800ed5af  jmp     short loc_1800ED5C0
0x1800ed5b1  call    cs:__imp_GetLastError
0x1800ed5b7  movzx   ecx, ax
0x1800ed5ba  or      ecx, 80070000h
0x1800ed5c0  xorps   xmm0, xmm0
0x1800ed5c3  movups  [rsp+458h+var_200], xmm0
0x1800ed5cb  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ed5d2  mov     [rsp+458h+var_208], rax
0x1800ed5da  mov     [rsp+458h+var_1F0], ecx
0x1800ed5e1  mov     [rsp+458h+var_1EC], 21Dh
0x1800ed5ec  mov     [rsp+458h+var_1E8], r13d
0x1800ed5f4  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ed5fb  lea     rcx, [rsp+458h+var_208]; pExceptionObject
0x1800ed603  call    _CxxThrowException_0
0x1800ed608  xor     r9d, r9d; lpLastWriteTime
0x1800ed60b  lea     rdx, [rsp+458h+LastWriteTime]; lpCreationTime
0x1800ed613  call    cs:__imp_GetFileTime
0x1800ed619  test    eax, eax
0x1800ed61b  jnz     short loc_1800ED688
0x1800ed61d  call    cs:__imp_GetLastError
0x1800ed623  test    eax, eax
0x1800ed625  jg      short loc_1800ED631
0x1800ed627  call    cs:__imp_GetLastError
0x1800ed62d  mov     ecx, eax
0x1800ed62f  jmp     short loc_1800ED640
0x1800ed631  call    cs:__imp_GetLastError
0x1800ed637  movzx   ecx, ax
0x1800ed63a  or      ecx, 80070000h
0x1800ed640  xorps   xmm0, xmm0
0x1800ed643  movups  [rsp+458h+var_1A0], xmm0
0x1800ed64b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ed652  mov     [rsp+458h+var_1A8], rax
0x1800ed65a  mov     [rsp+458h+var_190], ecx
0x1800ed661  mov     [rsp+458h+var_18C], 227h
0x1800ed66c  mov     [rsp+458h+var_188], r13d
0x1800ed674  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ed67b  lea     rcx, [rsp+458h+var_1A8]; pExceptionObject
0x1800ed683  call    _CxxThrowException_0
  ... truncated ...
```
