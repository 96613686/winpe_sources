# CCscNetApiInterfaceImpl::NetShareEnum(ulong,ushort const *,ulong,uchar * *,ulong,ulong *,ulong *,ulong *)

- ea: `0x1800016b0`
- end: `0x180001ff7`
- name: `?NetShareEnum@CCscNetApiInterfaceImpl@@UEAAKKPEBGKPEAPEAEKPEAK22@Z`
- size: `2375`
- prototype: `unsigned int __fastcall(CCscNetApiInterfaceImpl *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned __int8 **, unsigned int, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x1800016a0`

## callees

- `0x1800016b0`
- `0x180002000`
- `0x180002820`
- `0x1800029a0`
- `0x180002b70`
- `0x1800036b0`
- `0x180003da0`
- `0x180005f30`
- `0x180006560`
- `0x180008384`
- `0x180008604`
- `0x180008af4`
- `0x180009456`
- `0x180009462`
- `0x180009490`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800018f5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800018f5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180001a2c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180001a2c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180001fea`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180001fea`

## pseudocode

```c
__int64 __fastcall CCscNetApiInterfaceImpl::NetShareEnum(
        CCscNetApiInterfaceImpl *this,
        ULONG a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int8 **a5,
        char a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int *a9)
{
  ULONG v11; // esi
  void *v12; // r14
  void *v13; // r15
  __int64 v14; // r13
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 i; // r8
  unsigned int v18; // r12d
  int v19; // r12d
  char v20; // di
  unsigned int *v21; // r13
  BOOL v23; // ecx
  unsigned __int8 v24; // r12
  int v25; // ecx
  unsigned int v26; // ecx
  __int16 v27; // ax
  bool v28; // cc
  _DWORD *v29; // rax
  __int64 v30; // r12
  __int64 v31; // rcx
  unsigned int v32; // eax
  unsigned int v33; // ecx
  int OpenPattern; // eax
  unsigned int v35; // eax
  int v36; // edx
  int v37; // ecx
  unsigned __int16 v38; // ax
  unsigned __int64 v39; // rcx
  unsigned __int64 v40; // r14
  __int64 v41; // rdx
  int Next; // eax
  int v43; // r9d
  unsigned int v44; // ecx
  unsigned __int8 *v45; // rax
  int v46; // eax
  bool v47; // cf
  unsigned int v48; // ecx
  signed int Status; // [rsp+60h] [rbp-A0h]
  NTSTATUS Statusa; // [rsp+60h] [rbp-A0h]
  char v51; // [rsp+64h] [rbp-9Ch]
  int v53; // [rsp+68h] [rbp-98h]
  int v54; // [rsp+68h] [rbp-98h]
  char v55; // [rsp+6Ch] [rbp-94h] BYREF
  char v56; // [rsp+6Dh] [rbp-93h]
  unsigned int *v57; // [rsp+70h] [rbp-90h]
  unsigned int v58; // [rsp+78h] [rbp-88h] BYREF
  void *v59; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 *v60; // [rsp+88h] [rbp-78h] BYREF
  __int64 v61; // [rsp+90h] [rbp-70h] BYREF
  void *Src[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v63; // [rsp+A8h] [rbp-58h]
  HANDLE FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  int v65[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v66; // [rsp+C0h] [rbp-40h]
  CCscNetApiInterfaceImpl *v67; // [rsp+C8h] [rbp-38h]
  unsigned __int8 **v68; // [rsp+D0h] [rbp-30h]
  unsigned int *v69; // [rsp+D8h] [rbp-28h]
  int v70[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v71; // [rsp+E8h] [rbp-18h]
  _OWORD v72[5]; // [rsp+F0h] [rbp-10h] BYREF
  int v73[4]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v74; // [rsp+150h] [rbp+50h]
  int v75[2]; // [rsp+160h] [rbp+60h] BYREF
  void *v76; // [rsp+168h] [rbp+68h]
  _DWORD Size[4]; // [rsp+170h] [rbp+70h]
  __int128 v78; // [rsp+180h] [rbp+80h] BYREF
  __int128 v79; // [rsp+190h] [rbp+90h]
  int v80; // [rsp+1A0h] [rbp+A0h]
  unsigned int v81; // [rsp+1A4h] [rbp+A4h]
  char v82; // [rsp+1A8h] [rbp+A8h]
  char v83; // [rsp+1B0h] [rbp+B0h] BYREF
  _WORD v84[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v85; // [rsp+1D4h] [rbp+D4h] BYREF

  v11 = 0;
  v68 = a5;
  v12 = 0;
  v67 = this;
  v57 = a8;
  v69 = a7;
  v13 = 0;
  Status = -1073741811;
  v56 = 0;
  v55 = 0;
  *(_OWORD *)Src = 0;
  v59 = 0;
  memset_0(v84, 0, 0x226u);
  v14 = *a7;
  memset(v72, 0, sizeof(v72));
  v15 = (__int64)*a5;
  v16 = *a8;
  *(_QWORD *)v65 = 0;
  v76 = &v83;
  v80 = -1;
  *(_QWORD *)v75 = &CDescriptor_SHARE_INFO::`vftable';
  v60 = 0;
  v66 = v15;
  v63 = v16;
  Size[0] = 24;
  v78 = 0;
  v81 = 0;
  v79 = 0;
  v82 = 0;
  *(_OWORD *)v73 = 0;
  v74 = 0;
  i = (__int64)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 225) < 4u )
  {
    v18 = a4;
  }
  else
  {
    if ( a9 )
      v37 = *a9;
    else
      LOBYTE(v37) = 0;
    v18 = a4;
    WPP_SF_DSDqDDDqD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v15,
      (unsigned int)&WPP_GLOBAL_Control,
      a2,
      (__int64)a3,
      a4,
      v15,
      a6,
      v14,
      v16,
      (char)a9,
      v37);
    v16 = v63;
    v15 = v66;
  }
  if ( a2 == 234 || a2 == 2123 )
  {
    v19 = 3041;
    goto LABEL_6;
  }
  if ( (_DWORD)v14 != v16 || (v23 = v14 != 0, (v15 != 0) != v23) || (a2 == 0) != v23 )
  {
    v19 = 3055;
    goto LABEL_6;
  }
  if ( !a3 || !*a3 )
  {
    v19 = 3065;
    goto LABEL_6;
  }
  if ( v18 > 1 )
  {
    v19 = 3086;
    goto LABEL_6;
  }
  v24 = 0;
  if ( *a3 == 92 )
  {
    if ( a3[1] != 92 || (v38 = a3[2], v38 == 92) || v38 == 47 || !v38 )
    {
LABEL_82:
      v19 = 3098;
      *(_OWORD *)Src = 0;
      goto LABEL_6;
    }
    v24 = 1;
  }
  v25 = 2 * v24;
  v15 = (unsigned int)(v25 + 1);
  v26 = v25 + 256;
  for ( i = (__int64)&a3[v15]; ; i += 2 )
  {
    v27 = *(_WORD *)i;
    if ( !*(_WORD *)i )
    {
      v28 = (unsigned int)v15 <= v26;
LABEL_38:
      if ( v28 )
        goto LABEL_39;
      goto LABEL_82;
    }
    v28 = (unsigned int)v15 <= v26;
    if ( (unsigned int)v15 >= v26 )
      goto LABEL_38;
    if ( v27 == 92 || v27 == 47 )
      break;
    v15 = (unsigned int)(v15 + 1);
  }
  if ( *(_WORD *)(i + 2) )
    goto LABEL_82;
LABEL_39:
  LOWORD(v15) = 2 * v15;
  Src[1] = (void *)a3;
  LOWORD(Src[0]) = v15;
  WORD1(Src[0]) = v15;
  if ( !CscUmpLibraryState )
  {
    Status = -1073741436;
    goto LABEL_41;
  }
  FileHandle = 0;
  Status = CscDriverpReferenceControlHandle(&FileHandle);
  if ( Status < 0
    || (v58 = 0,
        v61 = 0x1C00000008LL,
        Status = CscDriverpFsControlEx(FileHandle, v15, &v58, &v61, 8u, &v55, 1u),
        CscDriverpDereferenceControlHandle(&FileHandle),
        Status < 0)
    || !v55 )
  {
LABEL_41:
    v19 = 3109;
    goto LABEL_6;
  }
  v20 = 0;
  if ( v24 )
    goto LABEL_48;
  v29 = LocalAlloc(0, LOWORD(Src[0]) + 4LL);
  v13 = v29;
  if ( !v29 )
  {
    Status = -1073741670;
    v19 = 3120;
    goto LABEL_7;
  }
  *v29 = 6029404;
  memcpy_0(v29 + 1, Src[1], LOWORD(Src[0]));
  Src[1] = v13;
  LOWORD(Src[0]) += 4;
  WORD1(Src[0]) = Src[0];
LABEL_48:
  v80 = a4;
  v81 = 0;
  memset_0(v76, 0, Size[0]);
  *(_QWORD *)&Size[1] = -1;
  v82 = (**(__int64 (__fastcall ***)(int *, _QWORD))v75)(v75, a4);
  if ( !v82 )
  {
    Status = 0;
    v19 = 3130;
    goto LABEL_6;
  }
  if ( (_DWORD)v14 )
  {
    v30 = v66;
    v15 = 0;
    v31 = v81;
    v32 = 0;
    v53 = 0;
    i = 0xFFFFFFFFLL;
    while ( 1 )
    {
      Statusa = v32;
      if ( v32 >= (unsigned int)v14 )
        break;
      CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::ExtractStrings(v75, &v78, v30);
      v33 = 0;
      i = 0xFFFFFFFFLL;
      if ( Size[1] != -1 )
        v33 = (unsigned __int16)v78 + 2;
      if ( Size[2] != -1 )
        v33 += (unsigned __int16)v79 + 2;
      v15 = v33 + v53;
      v53 = v15;
      if ( (unsigned int)v15 < v33 )
        goto LABEL_57;
      v31 = v81;
      v30 += v81;
      v32 = Statusa + 1;
    }
    v39 = v14 * v31;
    v71 = v39;
    if ( v39 > 0xFFFFFFFF )
    {
LABEL_57:
      Status = -1073741675;
LABEL_68:
      v19 = 3148;
      goto LABEL_7;
    }
    v35 = v15 + v39;
    v36 = -1;
    if ( v35 >= (unsigned int)v39 )
      v36 = v35;
    v58 = v36;
    v15 = v35 < (unsigned int)v39 ? 0xC0000095 : 0;
    Status = v35 < (unsigned int)v39 ? 0xC0000095 : 0;
    if ( v35 < (unsigned int)v39 )
      goto LABEL_68;
    v51 = 1;
  }
  else
  {
    v51 = 0;
    LODWORD(v71) = 0;
    v58 = 0;
  }
  v19 = 0;
  DWORD1(v74) = v65[0];
  *((_QWORD *)&v74 + 1) = L"[Offline Share]";
  LODWORD(v74) = 2097182;
  LODWORD(v61) = 2048;
LABEL_61:
  if ( v12 )
  {
    CscUmFindClose(v12);
    v59 = 0;
  }
  OpenPattern = CscUmFindOpenPattern(&v59, Src, 0);
  Status = OpenPattern;
  if ( OpenPattern == -1073741765
    || OpenPattern == -1073741809
    || OpenPattern == -1073741773
    || OpenPattern == -1073741772
    || OpenPattern == -1073741767
    || OpenPattern == -1073741766 )
  {
    v12 = v59;
    v19 = 3199;
    goto LABEL_6;
  }
  if ( OpenPattern < 0 )
  {
    v12 = v59;
    v19 = 3201;
    goto LABEL_7;
  }
  if ( v60 )
  {
    (*((void (**)(void))v67 + 3))();
    v40 = 2LL * (unsigned int)v61;
    v60 = 0;
    v61 = v40;
    if ( v40 > 0xFFFFFFFF )
    {
      v12 = v59;
      v21 = v57;
      Status = -1073741675;
      goto LABEL_10;
    }
  }
  else
  {
    LODWORD(v40) = v61;
  }
  LODWORD(FileHandle) = v40 + v58;
  if ( (unsigned int)v40 + v58 < (unsigned int)v40 )
  {
    v12 = v59;
    Status = -1073741675;
    goto LABEL_7;
  }
  Status = 0;
  v11 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int8 **))v67 + 2))((unsigned int)v40 + v58, &v60);
  if ( v11 )
  {
    v12 = v59;
    v19 = 3232;
    v56 = 1;
    goto LABEL_7;
  }
  v54 = 0;
  v41 = (unsigned int)(v71 + v40);
  *(_QWORD *)v70 = &v60[(unsigned int)v71];
  v12 = v59;
  *(_QWORD *)v65 = &v60[v41];
  while ( 1 )
  {
    Next = CscUmFindNext(v12, v84, v72);
    Status = Next;
    if ( Next == -2147483642 )
      break;
    if ( Next < 0 )
    {
      v19 = 3280;
      goto LABEL_7;
    }
    *(_QWORD *)&v73[2] = &v85;
    LOWORD(v73[0]) = v84[0];
    HIWORD(v73[0]) = v84[0];
    if ( (!v51
       || !(unsigned __int8)CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::IsStringAlreadyInBuffer(
                              (unsigned int)v75,
                              v66,
                              v14,
                              v43,
                              (__int64)v73))
      && (v72[0] & 0x800000) == 0 )
    {
      if ( !(unsigned __int8)CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::CopyOrFillEntry(
                               (int)v75,
                               (int)v70,
                               (int)v65,
                               (int)v73,
                               0) )
        goto LABEL_61;
      ++v54;
    }
  }
  if ( !v54 )
  {
    Status = 0;
    v19 = 3356;
    goto LABEL_6;
  }
  if ( !v51 || (*(_QWORD *)v65 = v60, v44 = 0, *(_QWORD *)v70 = &v60[(unsigned int)FileHandle], v58 = 0, !(_DWORD)v14) )
  {
LABEL_113:
    (*((void (__fastcall **)(unsigned __int8 *))v67 + 3))(*v68);
    v45 = v60;
    v15 = (__int64)v69;
    v60 = 0;
    *v68 = v45;
    v46 = v54 + v14;
    v47 = v54 + (int)v14 < (unsigned int)v14;
    v21 = v57;
    if ( v47 )
    {
      *(_DWORD *)v15 = -1;
      v19 = 3366;
      Status = -1073741675;
    }
    else
    {
      v48 = v63 + v54;
      *(_DWORD *)v15 = v46;
      if ( v48 < v63 )
      {
        *v21 = -1;
        v19 = 3371;
        Status = -1073741675;
      }
      else
      {
        *v21 = v48;
        Status = 0;
      }
    }
    goto LABEL_8;
  }
  while ( (unsigned __int8)CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::CopyOrFillEntry(
                             (int)v75,
                             (int)v65,
                             (int)v70,
                             0,
                             (void *)(v66 + v81 * v44)) )
  {
    v44 = v58 + 1;
    v58 = v44;
    if ( v44 >= (unsigned int)v14 )
      goto LABEL_113;
  }
  Status = -1073740768;
  v19 = 3338;
LABEL_6:
  v20 = 1;
LABEL_7:
  v21 = v57;
LABEL_8:
  if ( v60 )
    (*((void (__fastcall **)(unsigned __int8 *, __int64))v67 + 3))(v60, v15);
LABEL_10:
  if ( v12 )
    CscUmFindClose(v12);
  if ( v13 )
    LocalFree(v13);
  if ( v20 )
  {
    v11 = a2;
  }
  else if ( !v56 )
  {
    v11 = RtlNtStatusToDosErrorNoTeb(Status);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
  {
    WPP_SF_qDDDD(*((_QWORD *)WPP_GLOBAL_Control + 27), v15, i, *v68, *v69, *v21, v11, v19);
  }
  return v11;
}

```

## disassembly

```asm
0x1800016b0  push    rbp
0x1800016b2  push    rbx
0x1800016b3  push    rsi
0x1800016b4  push    rdi
0x1800016b5  push    r12
0x1800016b7  push    r13
0x1800016b9  push    r14
0x1800016bb  push    r15
0x1800016bd  lea     rbp, [rsp-318h]
0x1800016c5  sub     rsp, 418h
0x1800016cc  mov     rax, cs:__security_cookie
0x1800016d3  xor     rax, rsp
0x1800016d6  mov     [rbp+350h+var_50], rax
0x1800016dd  mov     rax, [rbp+350h+arg_20]
0x1800016e4  mov     rdi, r8
0x1800016e7  mov     r13, [rbp+350h+arg_30]
0x1800016ee  mov     ebx, edx
0x1800016f0  mov     r12, [rbp+350h+arg_40]
0x1800016f7  xor     esi, esi
0x1800016f9  mov     [rbp+350h+var_380], rax
0x1800016fd  xorps   xmm0, xmm0
0x180001700  mov     rax, [rbp+350h+arg_38]
0x180001707  xor     r14d, r14d
0x18000170a  mov     [rbp+350h+var_388], rcx
0x18000170e  xor     edx, edx; Val
0x180001710  mov     r8d, 226h; Size
0x180001716  mov     [rsp+450h+var_3E0], rax
0x18000171b  lea     rcx, [rbp+350h+var_280]; void *
0x180001722  mov     [rsp+450h+var_3E8], r9d
0x180001727  mov     [rbp+350h+var_378], r13
0x18000172b  xor     r15d, r15d
0x18000172e  mov     [rsp+450h+Status], 0C000000Dh
0x180001736  mov     [rsp+450h+var_3E3], sil
0x18000173b  mov     [rsp+450h+var_3E4], sil
0x180001740  movups  xmmword ptr [rbp+350h+Src], xmm0
0x180001744  mov     [rbp+350h+var_3D0], r14
0x180001748  call    memset_0
0x18000174d  mov     rcx, [rbp+350h+var_380]
0x180001751  xorps   xmm0, xmm0
0x180001754  mov     rax, [rsp+450h+var_3E0]
0x180001759  xor     r9d, r9d
0x18000175c  mov     r13d, [r13+0]
0x180001760  movups  [rbp+350h+var_360], xmm0
0x180001764  mov     rdx, [rcx]
0x180001767  xor     ecx, ecx
0x180001769  mov     eax, [rax]
0x18000176b  mov     qword ptr [rbp+350h+var_398], rcx
0x18000176f  lea     rcx, [rbp+350h+var_2A0]
0x180001776  mov     [rbp+350h+var_2E8], rcx
0x18000177a  mov     ecx, 0FFFFFFFFh
0x18000177f  mov     [rbp+350h+var_2B0], ecx
0x180001785  lea     rcx, ??_7CDescriptor_SHARE_INFO@@6B@; const CDescriptor_SHARE_INFO::`vftable'
0x18000178c  mov     qword ptr [rbp+350h+var_2F0], rcx
0x180001790  movups  [rbp+350h+var_350], xmm0
0x180001794  mov     [rbp+350h+var_3C8], r9
0x180001798  movups  [rbp+350h+var_340], xmm0
0x18000179c  mov     [rbp+350h+var_390], rdx
0x1800017a0  movups  [rbp+350h+var_330], xmm0
0x1800017a4  mov     [rbp+350h+var_3A8], eax
0x1800017a7  movups  [rbp+350h+var_320], xmm0
0x1800017ab  mov     [rbp+350h+Size], 18h
0x1800017b2  movups  [rbp+350h+var_2D0], xmm0
0x1800017b9  mov     [rbp+350h+var_2AC], r9d
0x1800017c0  movups  [rbp+350h+var_2C0], xmm0
0x1800017c7  mov     [rbp+350h+var_2A8], sil
0x1800017ce  movups  xmmword ptr [rbp+350h+var_310], xmm0
0x1800017d2  movups  [rbp+350h+var_300], xmm0
0x1800017d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017dd  lea     r8, WPP_GLOBAL_Control
0x1800017e4  cmp     rcx, r8
0x1800017e7  jz      short loc_1800017F6
0x1800017e9  test    byte ptr [rcx+0E4h], 1
0x1800017f0  jnz     loc_180001BF5
0x1800017f6  mov     r12d, [rsp+450h+var_3E8]
0x1800017fb  cmp     ebx, 0EAh
0x180001801  jnz     short loc_180001873
0x180001803  mov     r12d, 0BE1h
0x180001809  mov     dil, 1
0x18000180c  mov     r13, [rsp+450h+var_3E0]
0x180001811  mov     rcx, [rbp+350h+var_3C8]
0x180001815  test    rcx, rcx
0x180001818  jnz     loc_180001FBC
0x18000181e  test    r14, r14
0x180001821  jnz     loc_180001FCE
0x180001827  test    r15, r15
0x18000182a  jnz     loc_1800018F2
0x180001830  test    dil, dil
0x180001833  jz      loc_180001FDB
0x180001839  mov     esi, ebx
0x18000183b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001842  lea     rax, WPP_GLOBAL_Control
0x180001849  cmp     rcx, rax
0x18000184c  jnz     short loc_1800018AD
0x18000184e  mov     eax, esi
0x180001850  mov     rcx, [rbp+350h+var_50]
0x180001857  xor     rcx, rsp; StackCookie
0x18000185a  call    __security_check_cookie
0x18000185f  add     rsp, 418h
0x180001866  pop     r15
0x180001868  pop     r14
0x18000186a  pop     r13
0x18000186c  pop     r12
0x18000186e  pop     rdi
0x18000186f  pop     rsi
0x180001870  pop     rbx
0x180001871  pop     rbp
0x180001872  retn
0x180001873  cmp     ebx, 84Bh
0x180001879  jz      short loc_180001803
0x18000187b  cmp     r13d, eax
0x18000187e  jnz     short loc_1800018A2
0x180001880  test    r13d, r13d
0x180001883  mov     ecx, r9d
0x180001886  mov     eax, r9d
0x180001889  setnz   cl
0x18000188c  test    rdx, rdx
0x18000188f  setnz   al
0x180001892  cmp     eax, ecx
0x180001894  jnz     short loc_1800018A2
0x180001896  test    ebx, ebx
0x180001898  mov     eax, r9d
0x18000189b  setz    al
0x18000189e  cmp     eax, ecx
0x1800018a0  jz      short loc_180001900
0x1800018a2  mov     r12d, 0BEFh
0x1800018a8  jmp     loc_180001809
0x1800018ad  test    byte ptr [rcx+0E4h], 1
0x1800018b4  jz      short loc_18000184E
0x1800018b6  cmp     byte ptr [rcx+0E1h], 4
0x1800018bd  jb      short loc_18000184E
0x1800018bf  mov     eax, [r13+0]
0x1800018c3  mov     rcx, [rcx+0D8h]
0x1800018ca  mov     [rsp+450h+var_418], r12d
0x1800018cf  mov     [rsp+450h+var_420], esi
0x1800018d3  mov     dword ptr [rsp+450h+var_428], eax
0x1800018d7  mov     rax, [rbp+350h+var_378]
0x1800018db  mov     eax, [rax]
0x1800018dd  mov     [rsp+450h+var_430], eax
0x1800018e1  mov     rax, [rbp+350h+var_380]
0x1800018e5  mov     r9, [rax]
0x1800018e8  call    WPP_SF_qDDDD
0x1800018ed  jmp     loc_18000184E
0x1800018f2  mov     rcx, r15; hMem
0x1800018f5  call    cs:__imp_LocalFree
0x1800018fb  jmp     loc_180001830
0x180001900  test    rdi, rdi
0x180001903  jnz     short loc_180001910
0x180001905  mov     r12d, 0BF9h
0x18000190b  jmp     loc_180001809
0x180001910  movzx   ecx, word ptr [rdi]
0x180001913  test    cx, cx
0x180001916  jz      short loc_180001905
0x180001918  mov     eax, r12d
0x18000191b  test    r12d, r12d
0x18000191e  jz      short loc_180001929
0x180001920  cmp     eax, 1
0x180001923  jnz     loc_180001C65
0x180001929  xor     r12b, r12b
0x18000192c  mov     eax, 5Ch ; '\'
0x180001931  cmp     ax, cx
0x180001934  jz      loc_180001C70
0x18000193a  movzx   eax, r12b
0x18000193e  lea     ecx, [rax+rax]
0x180001941  lea     edx, [rcx+1]
0x180001944  add     ecx, 100h
0x18000194a  lea     r8, [rdi+rdx*2]
0x18000194e  xchg    ax, ax
0x180001950  movzx   eax, word ptr [r8]
0x180001954  test    ax, ax
0x180001957  jz      short loc_180001979
0x180001959  cmp     edx, ecx
0x18000195b  jnb     short loc_18000197B
0x18000195d  cmp     ax, 5Ch ; '\'
0x180001961  jz      loc_180001C93
0x180001967  cmp     ax, 2Fh ; '/'
0x18000196b  jz      loc_180001C93
0x180001971  add     r8, 2
0x180001975  inc     edx
0x180001977  jmp     short loc_180001950
0x180001979  cmp     edx, ecx
0x18000197b  ja      loc_180001C9E
0x180001981  add     dx, dx
0x180001984  mov     [rbp+350h+Src+8], rdi
0x180001988  cmp     cs:CscUmpLibraryState, esi
0x18000198e  mov     word ptr [rbp+350h+Src], dx
0x180001992  mov     word ptr [rbp+350h+Src+2], dx
0x180001996  jnz     short loc_1800019AB
0x180001998  mov     [rsp+450h+Status], 0C0000184h
0x1800019a0  mov     r12d, 0C25h
0x1800019a6  jmp     loc_180001809
0x1800019ab  lea     rcx, [rbp+350h+FileHandle]
0x1800019af  mov     [rbp+350h+FileHandle], r9
0x1800019b3  call    CscDriverpReferenceControlHandle
0x1800019b8  mov     [rsp+450h+Status], eax
0x1800019bc  test    eax, eax
0x1800019be  js      short loc_1800019A0
0x1800019c0  mov     rcx, [rbp+350h+FileHandle]; FileHandle
0x1800019c4  lea     rax, [rsp+450h+var_3E4]
0x1800019c9  mov     [rsp+450h+var_420], 1; ULONG
0x1800019d1  lea     r9, [rbp+350h+var_3C0]
0x1800019d5  mov     [rsp+450h+var_428], rax; PVOID
0x1800019da  lea     r8, [rsp+450h+var_3D8]
0x1800019df  mov     [rsp+450h+var_430], 8; ULONG
0x1800019e7  mov     [rsp+450h+var_3D8], esi
0x1800019eb  mov     dword ptr [rbp+350h+var_3C0], 8
0x1800019f2  mov     dword ptr [rbp+350h+var_3C0+4], 1Ch
0x1800019f9  call    CscDriverpFsControlEx
0x1800019fe  mov     [rsp+450h+Status], eax
0x180001a02  lea     rcx, [rbp+350h+FileHandle]
0x180001a06  call    CscDriverpDereferenceControlHandle
0x180001a0b  mov     eax, [rsp+450h+Status]
0x180001a0f  test    eax, eax
0x180001a11  js      short loc_1800019A0
0x180001a13  cmp     [rsp+450h+var_3E4], sil
0x180001a18  jz      short loc_1800019A0
0x180001a1a  xor     dil, dil
0x180001a1d  test    r12b, r12b
0x180001a20  jnz     short loc_180001A6A
0x180001a22  movzx   edx, word ptr [rbp+350h+Src]
0x180001a26  xor     ecx, ecx; uFlags
0x180001a28  add     rdx, 4; uBytes
0x180001a2c  call    cs:__imp_LocalAlloc
0x180001a32  mov     r15, rax
0x180001a35  test    rax, rax
0x180001a38  jz      loc_180001CB0
0x180001a3e  mov     dword ptr [rax], 5C005Ch
0x180001a44  lea     rcx, [rax+4]; void *
0x180001a48  movzx   r8d, word ptr [rbp+350h+Src]; Size
0x180001a4d  mov     rdx, [rbp+350h+Src+8]; Src
0x180001a51  call    memcpy_0
0x180001a56  movzx   eax, word ptr [rbp+350h+Src]
0x180001a5a  add     ax, 4
0x180001a5e  mov     [rbp+350h+Src+8], r15
0x180001a62  mov     word ptr [rbp+350h+Src], ax
0x180001a66  mov     word ptr [rbp+350h+Src+2], ax
0x180001a6a  mov     r12d, [rsp+450h+var_3E8]
0x180001a6f  xor     edx, edx; Val
0x180001a71  mov     r8d, [rbp+350h+Size]; Size
0x180001a75  mov     rcx, [rbp+350h+var_2E8]; void *
0x180001a79  mov     [rbp+350h+var_2B0], r12d
0x180001a80  mov     [rbp+350h+var_2AC], esi
0x180001a86  call    memset_0
0x180001a8b  mov     rax, qword ptr [rbp+350h+var_2F0]
0x180001a8f  lea     rcx, [rbp+350h+var_2F0]
0x180001a93  mov     edx, r12d
0x180001a96  mov     qword ptr [rbp+350h+Size+4], 0FFFFFFFFFFFFFFFFh
0x180001a9e  mov     rax, [rax]
0x180001aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aa6  mov     [rbp+350h+var_2A8], al
0x180001aac  test    al, al
0x180001aae  jz      loc_180001B3E
0x180001ab4  test    r13d, r13d
0x180001ab7  jz      loc_180001B4D
0x180001abd  mov     r12, [rbp+350h+var_390]
0x180001ac1  xor     edx, edx
0x180001ac3  mov     ecx, [rbp+350h+var_2AC]
0x180001ac9  xor     eax, eax
0x180001acb  mov     [rsp+450h+var_3E8], edx
0x180001acf  mov     r8d, 0FFFFFFFFh
0x180001ad5  mov     [rsp+450h+Status], eax
0x180001ad9  cmp     eax, r13d
0x180001adc  jnb     loc_180001CC3
0x180001ae2  mov     r8, r12
0x180001ae5  lea     rdx, [rbp+350h+var_2D0]
0x180001aec  lea     rcx, [rbp+350h+var_2F0]
0x180001af0  call    ?ExtractStrings@?$CDescriptor@VCInfoLevelStringEnum_SHARE_INFO@@@@QEAAXPEAVCStrings@1@PEAX@Z; CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::ExtractStrings(CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::CStrings *,void *)
0x180001af5  xor     ecx, ecx
0x180001af7  mov     r8d, 0FFFFFFFFh
0x180001afd  cmp     [rbp+350h+Size+4], r8d
0x180001b01  jz      short loc_180001B0D
0x180001b03  movzx   ecx, word ptr [rbp+350h+var_2D0]
0x180001b0a  add     ecx, 2
0x180001b0d  cmp     [rbp+350h+Size+8], r8d
0x180001b11  jz      short loc_180001B1F
0x180001b13  movzx   eax, word ptr [rbp+350h+var_2C0]
0x180001b1a  add     eax, 2
0x180001b1d  add     ecx, eax
0x180001b1f  mov     edx, [rsp+450h+var_3E8]
0x180001b23  add     edx, ecx
0x180001b25  mov     [rsp+450h+var_3E8], edx
0x180001b29  cmp     edx, ecx
0x180001b2b  jnb     loc_180001BE1
0x180001b31  mov     [rsp+450h+Status], 0C0000095h
0x180001b39  jmp     loc_180001BD6
0x180001b3e  mov     [rsp+450h+Status], esi
0x180001b42  mov     r12d, 0C3Ah
0x180001b48  jmp     loc_180001809
0x180001b4d  mov     [rsp+450h+var_3EC], sil
0x180001b52  mov     dword ptr [rbp+350h+var_368], esi
0x180001b55  mov     [rsp+450h+var_3D8], esi
0x180001b59  mov     rax, qword ptr [rbp+350h+var_398]
0x180001b5d  xor     r12d, r12d
0x180001b60  mov     dword ptr [rbp+350h+var_300+4], eax
0x180001b63  lea     rax, aOfflineShare; "[Offline Share]"
0x180001b6a  mov     qword ptr [rbp+350h+var_300+8], rax
0x180001b6e  mov     dword ptr [rbp+350h+var_300], 20001Eh
0x180001b75  mov     dword ptr [rbp+350h+var_3C0], 800h
0x180001b7c  test    r14, r14
0x180001b7f  jnz     loc_180001CE3
0x180001b85  xor     r8d, r8d
  ... truncated ...
```
