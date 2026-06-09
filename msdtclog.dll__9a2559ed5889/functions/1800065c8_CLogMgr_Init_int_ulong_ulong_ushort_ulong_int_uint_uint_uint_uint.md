# CLogMgr::Init(int,ulong *,ulong *,ushort *,ulong,int,uint,uint,uint,uint)

- ea: `0x1800065c8`
- end: `0x180006996`
- name: `?Init@CLogMgr@@IEAAJHPEAK0PEAGKHIIII@Z`
- size: `974`
- prototype: `__int64 __fastcall(CLogMgr *this, int, unsigned int *, unsigned int *, unsigned __int16 *lpFileName, unsigned int, int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180002150`
- `0x1800022f0`
- `0x1800025e0`
- `0x1800026c0`

## callees

- `0x1800012c0`
- `0x18000130c`
- `0x180006328`
- `0x1800065c8`
- `0x180006e80`
- `0x180009050`
- `0x180009e6c`
- `0x18000a288`
- `0x18000bc44`
- `0x18000c350`
- `0x18000d998`
- `0x18001280a`
- `0x180015010`

## string_xrefs

- `0x180006748`: `com\complus\dtc\dtc\log\logmgr\src\logmgr.cpp`
- `0x18000693f`: `com\complus\dtc\dtc\log\logmgr\src\logmgr.cpp`

## pseudocode

```c
__int64 __fastcall CLogMgr::Init(
        CLogMgr *this,
        int a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int16 *lpFileName,
        unsigned int a6,
        int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11)
{
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  CLogStorage *v19; // rax
  int v20; // r9d
  CLogStorage *v21; // rcx
  int v22; // ebx
  __int64 v23; // rcx
  int v24; // eax
  void *v25; // rax
  __int64 v26; // rcx
  unsigned __int16 i; // dx
  CLogState *v28; // rax
  CLogState *v29; // rax
  _DWORD *v30; // rax
  void *v31; // rax
  struct CInitSupport *v32; // rdx
  __int64 v33; // rcx
  int v34; // eax
  _BYTE v35[52]; // [rsp+60h] [rbp-98h] BYREF
  unsigned int v36; // [rsp+94h] [rbp-64h]
  unsigned __int16 v37; // [rsp+A0h] [rbp-58h]
  int v38; // [rsp+A4h] [rbp-54h]
  int v39; // [rsp+A8h] [rbp-50h]
  int v40; // [rsp+ACh] [rbp-4Ch]

  if ( !lpFileName )
    return 2147942487LL;
  *((_DWORD *)this + 158) = 0x2000;
  v16 = 10;
  if ( a8 )
    v16 = a8;
  *((_DWORD *)this + 124) = v16;
  v17 = 50;
  if ( a9 )
    v17 = a9;
  *((_DWORD *)this + 126) = v17;
  v18 = 50000;
  if ( a10 )
    v18 = a10;
  *((_DWORD *)this + 125) = v18;
  v19 = (CLogStorage *)operator new(0x310u);
  if ( v19 )
    v21 = CLogStorage::CLogStorage(v19, *((_DWORD *)this + 158), a6, v20, a11);
  else
    v21 = 0;
  *((_QWORD *)this + 49) = v21;
  if ( !v21 )
  {
    v22 = -2147024882;
LABEL_52:
    CLogMgr::_Cleanup(this);
    return (unsigned int)v22;
  }
  *((_QWORD *)v21 + 97) = *((_QWORD *)this + 3);
  if ( a2 )
  {
    if ( !a3 || !*a3 )
    {
      v22 = -2147024809;
      goto LABEL_52;
    }
    v22 = CLogStorage::_NewLogFile(*((CLogStorage **)this + 49), lpFileName, *a3, a7);
  }
  else
  {
    v22 = CLogStorage::_OpenLogFile(*((CLogStorage **)this + 49), lpFileName, (unsigned int *)this + 73);
  }
  if ( v22 )
  {
    v23 = *((_QWORD *)this + 3);
    if ( v23 )
    {
      v24 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v23 + 24LL))(v23, 4097, 4);
      if ( v24 < 0 )
        TraceFile(v24, "failed in m_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logmgr.cpp", 0x24Fu);
    }
    *((_DWORD *)this + 4) = 1;
    if ( v22 >= 0 )
      return (unsigned int)v22;
    goto LABEL_52;
  }
  memset_0(v35, 0, 0x54u);
  v25 = operator new[](0x1F74u);
  *((_QWORD *)this + 37) = v25;
  if ( !v25 )
  {
    v22 = -2147024882;
    goto LABEL_52;
  }
  memset_0(v25, 0, 0x1F74u);
  CLogStorage::GetRestart(*((CLogStorage **)this + 49), (struct _RESTARTLOG *)v35, *((struct _STRMTBL **)this + 37));
  v38 = *((_DWORD *)this + 124);
  v39 = *((_DWORD *)this + 126);
  v40 = *((_DWORD *)this + 125);
  if ( a3 )
    *a3 = v36;
  v26 = *((_QWORD *)this + 37);
  for ( i = 0; i < v37; ++i )
  {
    *(_QWORD *)(v26 + 20) = 0;
    v26 += 44;
  }
  v28 = (CLogState *)operator new(0x138u);
  if ( v28 )
    v29 = CLogState::CLogState(v28, (struct _RESTARTLOG *)v35, *((_DWORD *)this + 158), this);
  else
    v29 = 0;
  *((_QWORD *)this + 50) = v29;
  if ( !v29 )
  {
    v22 = -2147024882;
    goto LABEL_52;
  }
  v30 = operator new(0xD8u);
  if ( v30 )
  {
    *v30 = 0;
    v30[20] = 0;
    v30[6] = 0;
    *((_QWORD *)v30 + 1) = 0;
    *((_QWORD *)v30 + 2) = 0;
  }
  else
  {
    v30 = 0;
  }
  *((_QWORD *)this + 78) = v30;
  if ( !v30 )
  {
    v22 = -2147024882;
    goto LABEL_52;
  }
  if ( !a2 )
  {
    v31 = operator new[](0x190u);
    *((_QWORD *)this + 46) = v31;
    if ( v31 )
    {
      memset_0(v31, 0, 0x190u);
      *((_DWORD *)this + 94) = 0;
      CLogMgr::DoRecovery(this, v32);
      v33 = *((_QWORD *)this + 3);
      if ( v33 )
      {
        v34 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v33 + 24LL))(v33, 256, 4);
        if ( v34 < 0 )
          TraceFile(
            v34,
            "failed in m_pIDtcTrace->Trace",
            "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logmgr.cpp",
            0x2A6u);
      }
      if ( a4 )
        *a4 = *(_DWORD *)(*((_QWORD *)this + 50) + 16LL);
      return 0;
    }
    v22 = -2147024882;
    goto LABEL_52;
  }
  return 0;
}

```

## disassembly

```asm
0x1800065c8  mov     [rsp+arg_0], rcx
0x1800065cd  push    rbx
0x1800065ce  push    rsi
0x1800065cf  push    rdi
0x1800065d0  push    r12
0x1800065d2  push    r14
0x1800065d4  push    r15
0x1800065d6  sub     rsp, 0C8h
0x1800065dd  mov     r15, r9
0x1800065e0  mov     rsi, r8
0x1800065e3  mov     r14d, edx
0x1800065e6  mov     rdi, rcx
0x1800065e9  mov     rbx, [rsp+0F8h+lpFileName]
0x1800065f1  xor     r12d, r12d
0x1800065f4  test    rbx, rbx
0x1800065f7  jnz     short loc_180006603
0x1800065f9  mov     eax, 80070057h
0x1800065fe  jmp     loc_180006984
0x180006603  mov     dword ptr [rcx+278h], 2000h
0x18000660d  mov     ecx, 0Ah
0x180006612  mov     eax, [rsp+0F8h+arg_38]
0x180006619  test    eax, eax
0x18000661b  cmovnz  ecx, eax
0x18000661e  mov     [rdi+1F0h], ecx
0x180006624  mov     ecx, 32h ; '2'
0x180006629  mov     eax, [rsp+0F8h+arg_40]
0x180006630  test    eax, eax
0x180006632  cmovnz  ecx, eax
0x180006635  mov     [rdi+1F8h], ecx
0x18000663b  mov     ecx, 0C350h
0x180006640  mov     eax, [rsp+0F8h+arg_48]
0x180006647  test    eax, eax
0x180006649  cmovnz  ecx, eax
0x18000664c  mov     [rdi+1F4h], ecx
0x180006652  mov     ecx, 310h; Size
0x180006657  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000665c  mov     [rsp+0F8h+lpFileName], rax
0x180006664  test    rax, rax
0x180006667  jz      short loc_18000668F
0x180006669  mov     ecx, [rsp+0F8h+arg_50]
0x180006670  mov     [rsp+0F8h+var_D8], ecx; unsigned int
0x180006674  mov     r8d, [rsp+0F8h+arg_28]; unsigned int
0x18000667c  mov     edx, [rdi+278h]; unsigned int
0x180006682  mov     rcx, rax; this
0x180006685  call    ??0CLogStorage@@QEAA@KKHK@Z; CLogStorage::CLogStorage(ulong,ulong,int,ulong)
0x18000668a  mov     rcx, rax
0x18000668d  jmp     short loc_180006692
0x18000668f  mov     rcx, r12
0x180006692  mov     [rdi+188h], rcx
0x180006699  test    rcx, rcx
0x18000669c  jnz     short loc_1800066A8
0x18000669e  mov     ebx, 8007000Eh
0x1800066a3  jmp     loc_18000697A
0x1800066a8  mov     rax, [rdi+18h]
0x1800066ac  mov     [rcx+308h], rax
0x1800066b3  test    r14d, r14d
0x1800066b6  jz      short loc_1800066EA
0x1800066b8  test    rsi, rsi
0x1800066bb  jz      short loc_1800066E0
0x1800066bd  mov     r8d, [rsi]; unsigned int
0x1800066c0  test    r8d, r8d
0x1800066c3  jz      short loc_1800066E0
0x1800066c5  mov     r9d, [rsp+0F8h+arg_30]; int
0x1800066cd  mov     rdx, rbx; lpFileName
0x1800066d0  mov     rcx, [rdi+188h]; this
0x1800066d7  call    ?_NewLogFile@CLogStorage@@AEAAJPEAGKHPEAK@Z; CLogStorage::_NewLogFile(ushort *,ulong,int,ulong *)
0x1800066dc  mov     ebx, eax
0x1800066de  jmp     short loc_180006702
0x1800066e0  mov     ebx, 80070057h
0x1800066e5  jmp     loc_18000697A
0x1800066ea  lea     r8, [rdi+124h]; unsigned int *
0x1800066f1  mov     rdx, rbx; unsigned __int16 *
0x1800066f4  mov     rcx, [rdi+188h]; this
0x1800066fb  call    ?_OpenLogFile@CLogStorage@@AEAAJPEAGPEAK@Z; CLogStorage::_OpenLogFile(ushort *,ulong *)
0x180006700  mov     ebx, eax
0x180006702  test    ebx, ebx
0x180006704  jz      short loc_180006771
0x180006706  mov     rcx, [rdi+18h]
0x18000670a  test    rcx, rcx
0x18000670d  jz      short loc_18000675D
0x18000670f  mov     rax, [rcx]
0x180006712  mov     [rsp+0F8h+var_C0], r12
0x180006717  mov     [rsp+0F8h+var_C8], r12
0x18000671c  mov     [rsp+0F8h+var_D0], r12d
0x180006721  mov     [rsp+0F8h+var_D8], 0C0001043h
0x180006729  xor     r9d, r9d
0x18000672c  mov     edx, 1001h
0x180006731  lea     r8d, [r9+4]
0x180006735  mov     rax, [rax+18h]
0x180006739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000673e  test    eax, eax
0x180006740  jns     short loc_18000675D
0x180006742  mov     r9d, 24Fh; unsigned int
0x180006748  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000674f  lea     rdx, aFailedInMPidtc; "failed in m_pIDtcTrace->Trace"
0x180006756  mov     ecx, eax; int
0x180006758  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000675d  mov     dword ptr [rdi+10h], 1
0x180006764  test    ebx, ebx
0x180006766  jns     loc_180006982
0x18000676c  jmp     loc_18000697A
0x180006771  xor     edx, edx; Val
0x180006773  lea     r8d, [rdx+54h]; Size
0x180006777  lea     rcx, [rsp+0F8h+var_98]; void *
0x18000677c  call    memset_0
0x180006781  mov     ebx, 1F74h
0x180006786  mov     ecx, ebx; unsigned __int64
0x180006788  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000678d  mov     [rdi+128h], rax
0x180006794  test    rax, rax
0x180006797  jnz     short loc_1800067A3
0x180006799  mov     ebx, 8007000Eh
0x18000679e  jmp     loc_18000697A
0x1800067a3  mov     r8, rbx; Size
0x1800067a6  xor     edx, edx; Val
0x1800067a8  mov     rcx, rax; void *
0x1800067ab  call    memset_0
0x1800067b0  mov     r8, [rdi+128h]; struct _STRMTBL *
0x1800067b7  lea     rdx, [rsp+0F8h+var_98]; struct _RESTARTLOG *
0x1800067bc  mov     rcx, [rdi+188h]; this
0x1800067c3  call    ?GetRestart@CLogStorage@@QEAAXPEAU_RESTARTLOG@@PEAU_STRMTBL@@@Z; CLogStorage::GetRestart(_RESTARTLOG *,_STRMTBL *)
0x1800067c8  mov     eax, [rdi+1F0h]
0x1800067ce  mov     [rsp+0F8h+var_54], eax
0x1800067d5  mov     eax, [rdi+1F8h]
0x1800067db  mov     [rsp+0F8h+var_50], eax
0x1800067e2  mov     eax, [rdi+1F4h]
0x1800067e8  mov     [rsp+0F8h+var_4C], eax
0x1800067ef  test    rsi, rsi
0x1800067f2  jz      short loc_1800067FD
0x1800067f4  mov     eax, [rsp+0F8h+var_64]
0x1800067fb  mov     [rsi], eax
0x1800067fd  mov     rcx, [rdi+128h]
0x180006804  mov     edx, r12d
0x180006807  cmp     r12w, [rsp+0F8h+var_58]
0x180006810  jnb     short loc_18000682C
0x180006812  mov     eax, 1
0x180006817  mov     [rcx+14h], r12
0x18000681b  lea     rcx, [rcx+2Ch]
0x18000681f  add     dx, ax
0x180006822  cmp     dx, [rsp+0F8h+var_58]
0x18000682a  jb      short loc_180006817
0x18000682c  mov     ecx, 138h; Size
0x180006831  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006836  mov     [rsp+0F8h+lpFileName], rax
0x18000683e  test    rax, rax
0x180006841  jz      short loc_18000685C
0x180006843  mov     r9, rdi; struct CLogMgr *
0x180006846  mov     r8d, [rdi+278h]; unsigned int
0x18000684d  lea     rdx, [rsp+0F8h+var_98]; struct _RESTARTLOG *
0x180006852  mov     rcx, rax; this
0x180006855  call    ??0CLogState@@QEAA@AEAU_RESTARTLOG@@KPEAVCLogMgr@@@Z; CLogState::CLogState(_RESTARTLOG &,ulong,CLogMgr *)
0x18000685a  jmp     short loc_18000685F
0x18000685c  mov     rax, r12
0x18000685f  mov     [rdi+190h], rax
0x180006866  test    rax, rax
0x180006869  jnz     short loc_180006875
0x18000686b  mov     ebx, 8007000Eh
0x180006870  jmp     loc_18000697A
0x180006875  mov     ecx, 0D8h; Size
0x18000687a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000687f  test    rax, rax
0x180006882  jz      short loc_180006899
0x180006884  mov     [rax], r12d
0x180006887  mov     [rax+50h], r12d
0x18000688b  mov     [rax+18h], r12d
0x18000688f  mov     [rax+8], r12
0x180006893  mov     [rax+10h], r12
0x180006897  jmp     short loc_18000689C
0x180006899  mov     rax, r12
0x18000689c  mov     [rdi+270h], rax
0x1800068a3  test    rax, rax
0x1800068a6  jnz     short loc_1800068B2
0x1800068a8  mov     ebx, 8007000Eh
0x1800068ad  jmp     loc_18000697A
0x1800068b2  test    r14d, r14d
0x1800068b5  jz      short loc_1800068BF
0x1800068b7  mov     ebx, r12d
0x1800068ba  jmp     loc_180006982
0x1800068bf  mov     ebx, 190h
0x1800068c4  mov     ecx, ebx; unsigned __int64
0x1800068c6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800068cb  mov     [rdi+170h], rax
0x1800068d2  test    rax, rax
0x1800068d5  jnz     short loc_1800068E1
0x1800068d7  mov     ebx, 8007000Eh
0x1800068dc  jmp     loc_18000697A
0x1800068e1  mov     r8, rbx; Size
0x1800068e4  xor     edx, edx; Val
0x1800068e6  mov     rcx, rax; void *
0x1800068e9  call    memset_0
0x1800068ee  mov     [rdi+178h], r12d
0x1800068f5  mov     rcx, rdi; this
0x1800068f8  call    ?DoRecovery@CLogMgr@@IEAAXPEAVCInitSupport@@@Z; CLogMgr::DoRecovery(CInitSupport *)
0x1800068fd  mov     rcx, [rdi+18h]
0x180006901  test    rcx, rcx
0x180006904  jz      short loc_180006954
0x180006906  mov     rax, [rcx]
0x180006909  mov     [rsp+0F8h+var_C0], r12
0x18000690e  mov     [rsp+0F8h+var_C8], r12
0x180006913  mov     [rsp+0F8h+var_D0], r12d
0x180006918  mov     [rsp+0F8h+var_D8], 4000101Ch
0x180006920  xor     r9d, r9d
0x180006923  mov     edx, 100h
0x180006928  lea     r8d, [r9+4]
0x18000692c  mov     rax, [rax+18h]
0x180006930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006935  test    eax, eax
0x180006937  jns     short loc_180006954
0x180006939  mov     r9d, 2A6h; unsigned int
0x18000693f  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x180006946  lea     rdx, aFailedInMPidtc; "failed in m_pIDtcTrace->Trace"
0x18000694d  mov     ecx, eax; int
0x18000694f  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180006954  test    r15, r15
0x180006957  jz      short loc_180006966
0x180006959  mov     rax, [rdi+190h]
0x180006960  mov     ecx, [rax+10h]
0x180006963  mov     [r15], ecx
0x180006966  mov     ebx, r12d
0x180006969  jmp     short loc_180006982
0x18000696b  mov     ebx, dword ptr [rsp+0F8h+lpFileName]
0x180006972  mov     rdi, [rsp+0F8h+arg_0]
0x18000697a  mov     rcx, rdi; this
0x18000697d  call    ?_Cleanup@CLogMgr@@AEAAXXZ; CLogMgr::_Cleanup(void)
0x180006982  mov     eax, ebx
0x180006984  add     rsp, 0C8h
0x18000698b  pop     r15
0x18000698d  pop     r14
0x18000698f  pop     r12
0x180006991  pop     rdi
0x180006992  pop     rsi
0x180006993  pop     rbx
0x180006994  retn
```
