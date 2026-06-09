# Imapi2Utility::SQMLogFSImageSession(ulong,ulong,ulong,ulong,ulong,ulong,ulong,int,FsiFileSystems,ulong,int,long,long,ulong,ulong)

- ea: `0x180077f7c`
- end: `0x180078384`
- name: `?SQMLogFSImageSession@Imapi2Utility@@YAJKKKKKKKHW4FsiFileSystems@@KHJJKK@Z`
- size: `1032`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, enum FsiFileSystems, unsigned int, unsigned int, unsigned int, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180019dd0`

## callees

- `0x180077f7c`
- `0x1800786c0`
- `0x180078724`
- `0x180078784`
- `0x1800787f4`
- `0x18008170e`
- `0x180081750`

## import_xrefs

- `ole32!CoCreateGuid` at `0x180077fe1`
- `ole32!CoCreateGuid` at `0x180077fe1`
- `KERNEL32!GetVersionExW` at `0x180077ffa`
- `KERNEL32!GetVersionExW` at `0x180077ffa`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::SQMLogFSImageSession(
        Imapi2Utility *this,
        signed int a2,
        signed int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        enum FsiFileSystems a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13,
        unsigned int a14,
        unsigned int a15)
{
  unsigned int v16; // r15d
  HRESULT v20; // ebx
  unsigned int v21; // edx
  const struct _EVENT_DESCRIPTOR *v22; // rcx
  unsigned int v23; // r8d
  const struct _EVENT_DESCRIPTOR *v24; // rcx
  const struct _EVENT_DESCRIPTOR *v25; // rcx
  const struct _EVENT_DESCRIPTOR *v26; // rcx
  unsigned int v27; // r9d
  const struct _EVENT_DESCRIPTOR *v28; // rcx
  const struct _EVENT_DESCRIPTOR *v29; // rcx
  const struct _EVENT_DESCRIPTOR *v30; // rcx
  const struct _EVENT_DESCRIPTOR *v31; // rcx
  const struct _EVENT_DESCRIPTOR *v32; // rcx
  const struct _EVENT_DESCRIPTOR *v33; // rcx
  const struct _EVENT_DESCRIPTOR *v34; // rcx
  const struct _EVENT_DESCRIPTOR *v35; // rcx
  const struct _EVENT_DESCRIPTOR *v36; // rcx
  const struct _EVENT_DESCRIPTOR *v37; // rcx
  const struct _EVENT_DESCRIPTOR *v38; // rcx
  unsigned int v39; // edx
  const struct _EVENT_DESCRIPTOR *v40; // rcx
  GUID *p_pguid; // rcx
  struct _GUID *started; // rdi
  const struct _EVENT_DESCRIPTOR *v43; // rcx
  const struct _EVENT_DESCRIPTOR *v44; // rcx
  const struct _EVENT_DESCRIPTOR *v45; // rcx
  const struct _EVENT_DESCRIPTOR *v46; // rcx
  unsigned int v47; // r9d
  const struct _EVENT_DESCRIPTOR *v48; // rcx
  const struct _EVENT_DESCRIPTOR *v49; // rcx
  const struct _EVENT_DESCRIPTOR *v50; // rcx
  const struct _EVENT_DESCRIPTOR *v51; // rcx
  const struct _EVENT_DESCRIPTOR *v52; // rcx
  const struct _EVENT_DESCRIPTOR *v53; // rcx
  const struct _EVENT_DESCRIPTOR *v54; // rcx
  const struct _EVENT_DESCRIPTOR *v55; // rcx
  const struct _EVENT_DESCRIPTOR *v56; // rcx
  const struct _EVENT_DESCRIPTOR *v57; // rcx
  const struct _EVENT_DESCRIPTOR *v58; // rcx
  unsigned int v59; // edx
  const struct _EVENT_DESCRIPTOR *v60; // rcx
  GUID pguid; // [rsp+20h] [rbp-E0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-D0h] BYREF

  v16 = (unsigned int)this;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  pguid = 0;
  if ( !(unsigned int)WinSqmIsOptedIn() )
    return 1;
  v20 = CoCreateGuid(&pguid);
  if ( v20 >= 0 )
  {
    VersionInformation.dwOSVersionInfoSize = 276;
    if ( GetVersionExW(&VersionInformation) )
    {
      if ( VersionInformation.dwMajorVersion > 6
        || VersionInformation.dwMajorVersion >= 6 && VersionInformation.dwMinorVersion )
      {
        started = WinSqmStartSession(&pguid, v21, v23);
        _WinSqmDWORDEvent(v43, started, 0x8D7u, v16);
        _WinSqmDWORDEvent(v44, started, 0x8DEu, a2);
        _WinSqmDWORDEvent(v45, started, 0x14E2u, a3);
        if ( a2 )
          v47 = (int)((double)a3 / (double)a2 * 100.0);
        else
          v47 = 0;
        _WinSqmDWORDEvent(v46, started, 0x14E3u, v47);
        _WinSqmDWORDEvent(v48, started, 0x14E4u, a4);
        _WinSqmDWORDEvent(v49, started, 0x14DEu, a5);
        _WinSqmDWORDEvent(v50, started, 0x8D9u, a6);
        _WinSqmDWORDEvent(v51, started, 0x8D8u, 0);
        _WinSqmDWORDEvent(v52, started, 0x8DAu, a8);
        _WinSqmDWORDEvent(v53, started, 0x8DBu, a9);
        _WinSqmDWORDEvent(v54, started, 0x14DDu, a10);
        _WinSqmDWORDEvent(v55, started, 0x14DFu, a11);
        _WinSqmDWORDEvent(v56, started, 0x8DCu, a12);
        _WinSqmDWORDEvent(v57, started, 0x8DDu, a13);
        v59 = -1;
        if ( a14 != -1 )
          v59 = a14 / 0x3E8;
        _WinSqmDWORDEvent(v58, started, 0x1502u, v59);
        _WinSqmDWORDEvent(v60, started, 0x14E5u, a15 / 0x3E8);
        p_pguid = started;
      }
      else
      {
        _WinSqmDWORDEvent(v22, &pguid, 0x8D7u, v16);
        _WinSqmDWORDEvent(v24, &pguid, 0x8DEu, a2);
        _WinSqmDWORDEvent(v25, &pguid, 0x14E2u, a3);
        if ( a3 )
        {
          v26 = (const struct _EVENT_DESCRIPTOR *)(unsigned int)(a3 + a2);
          v27 = (int)((double)a3 / (double)(int)v26 * 100.0);
        }
        else
        {
          v27 = 0;
        }
        _WinSqmDWORDEvent(v26, &pguid, 0x14E3u, v27);
        _WinSqmDWORDEvent(v28, &pguid, 0x14E4u, a4);
        _WinSqmDWORDEvent(v29, &pguid, 0x14DEu, a5);
        _WinSqmDWORDEvent(v30, &pguid, 0x8D9u, a6);
        _WinSqmDWORDEvent(v31, &pguid, 0x8D8u, 0);
        _WinSqmDWORDEvent(v32, &pguid, 0x8DAu, a8);
        _WinSqmDWORDEvent(v33, &pguid, 0x8DBu, a9);
        _WinSqmDWORDEvent(v34, &pguid, 0x14DDu, a10);
        _WinSqmDWORDEvent(v35, &pguid, 0x14DFu, a11);
        _WinSqmDWORDEvent(v36, &pguid, 0x8DCu, a12);
        _WinSqmDWORDEvent(v37, &pguid, 0x8DDu, a13);
        v39 = -1;
        if ( a14 != -1 )
          v39 = a14 / 0x3E8;
        _WinSqmDWORDEvent(v38, &pguid, 0x1502u, v39);
        _WinSqmDWORDEvent(v40, &pguid, 0x14E5u, a15 / 0x3E8);
        p_pguid = &pguid;
      }
      WinSqmEndSession(p_pguid);
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180077f7c  push    rbp
0x180077f7e  push    rbx
0x180077f7f  push    rsi
0x180077f80  push    rdi
0x180077f81  push    r12
0x180077f83  push    r14
0x180077f85  push    r15
0x180077f87  lea     rbp, [rsp-60h]
0x180077f8c  sub     rsp, 160h
0x180077f93  mov     rax, cs:__security_cookie
0x180077f9a  xor     rax, rsp
0x180077f9d  mov     [rbp+90h+var_40], rax
0x180077fa1  mov     esi, r8d
0x180077fa4  mov     r15d, ecx
0x180077fa7  mov     r14d, edx
0x180077faa  lea     rcx, [rsp+190h+VersionInformation]; void *
0x180077faf  mov     edi, 114h
0x180077fb4  xor     edx, edx; Val
0x180077fb6  mov     r8d, edi; Size
0x180077fb9  mov     r12d, r9d
0x180077fbc  call    memset_0
0x180077fc1  xorps   xmm0, xmm0
0x180077fc4  movups  xmmword ptr [rsp+190h+pguid.Data1], xmm0
0x180077fc9  call    ?WinSqmIsOptedIn@@YAHXZ; WinSqmIsOptedIn(void)
0x180077fce  test    eax, eax
0x180077fd0  jnz     short loc_180077FDC
0x180077fd2  mov     eax, 1
0x180077fd7  jmp     loc_180078366
0x180077fdc  lea     rcx, [rsp+190h+pguid]; pguid
0x180077fe1  call    cs:__imp_CoCreateGuid
0x180077fe7  mov     ebx, eax
0x180077fe9  test    eax, eax
0x180077feb  js      loc_180078364
0x180077ff1  lea     rcx, [rsp+190h+VersionInformation]; lpVersionInformation
0x180077ff6  mov     [rsp+190h+VersionInformation.dwOSVersionInfoSize], edi
0x180077ffa  call    cs:__imp_GetVersionExW
0x180078000  test    eax, eax
0x180078002  jnz     short loc_18007800E
0x180078004  mov     ebx, 8000FFFFh
0x180078009  jmp     loc_180078364
0x18007800e  cmp     [rsp+190h+VersionInformation.dwMajorVersion], 6
0x180078013  ja      loc_1800781D1
0x180078019  jb      short loc_180078026
0x18007801b  cmp     [rsp+190h+VersionInformation.dwMinorVersion], 0
0x180078020  ja      loc_1800781D1
0x180078026  mov     r9d, r15d; unsigned int
0x180078029  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x18007802e  mov     r8d, 8D7h; unsigned int
0x180078034  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078039  mov     r9d, r14d; unsigned int
0x18007803c  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x180078041  mov     r8d, 8DEh; unsigned int
0x180078047  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x18007804c  mov     r9d, esi; unsigned int
0x18007804f  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x180078054  mov     r8d, 14E2h; unsigned int
0x18007805a  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x18007805f  test    esi, esi
0x180078061  jz      short loc_18007808A
0x180078063  xorps   xmm1, xmm1
0x180078066  lea     ecx, [rsi+r14]
0x18007806a  cvtsi2sd xmm1, rsi
0x18007806f  xorps   xmm0, xmm0
0x180078072  cvtsi2sd xmm0, rcx
0x180078077  divsd   xmm1, xmm0
0x18007807b  mulsd   xmm1, cs:__real@4059000000000000
0x180078083  cvttsd2si r9, xmm1
0x180078088  jmp     short loc_18007808D
0x18007808a  xor     r9d, r9d; unsigned int
0x18007808d  mov     r8d, 14E3h; unsigned int
0x180078093  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x180078098  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x18007809d  mov     r9d, r12d; unsigned int
0x1800780a0  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x1800780a5  mov     r8d, 14E4h; unsigned int
0x1800780ab  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800780b0  mov     r9d, [rbp+90h+arg_20]; unsigned int
0x1800780b7  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x1800780bc  mov     r8d, 14DEh; unsigned int
0x1800780c2  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800780c7  mov     r9d, [rbp+90h+arg_28]; unsigned int
0x1800780ce  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x1800780d3  mov     r8d, 8D9h; unsigned int
0x1800780d9  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800780de  xor     r9d, r9d; unsigned int
0x1800780e1  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x1800780e6  mov     r8d, 8D8h; unsigned int
0x1800780ec  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800780f1  mov     r9d, [rbp+90h+arg_38]; unsigned int
0x1800780f8  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x1800780fd  mov     r8d, 8DAh; unsigned int
0x180078103  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078108  mov     r9d, [rbp+90h+arg_40]; unsigned int
0x18007810f  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x180078114  mov     r8d, 8DBh; unsigned int
0x18007811a  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x18007811f  mov     r9d, [rbp+90h+arg_48]; unsigned int
0x180078126  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x18007812b  mov     r8d, 14DDh; unsigned int
0x180078131  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078136  mov     r9d, [rbp+90h+arg_50]; unsigned int
0x18007813d  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x180078142  mov     r8d, 14DFh; unsigned int
0x180078148  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x18007814d  mov     r9d, [rbp+90h+arg_58]; unsigned int
0x180078154  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x180078159  mov     r8d, 8DCh; unsigned int
0x18007815f  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078164  mov     r9d, [rbp+90h+arg_60]; unsigned int
0x18007816b  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x180078170  mov     r8d, 8DDh; unsigned int
0x180078176  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x18007817b  or      edx, 0FFFFFFFFh
0x18007817e  mov     esi, 10624DD3h
0x180078183  cmp     [rbp+90h+arg_68], edx
0x180078189  jz      short loc_180078196
0x18007818b  mov     eax, esi
0x18007818d  mul     [rbp+90h+arg_68]
0x180078193  shr     edx, 6
0x180078196  mov     r9d, edx; unsigned int
0x180078199  mov     r8d, 1502h; unsigned int
0x18007819f  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x1800781a4  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800781a9  mov     eax, esi
0x1800781ab  mov     r8d, 14E5h; unsigned int
0x1800781b1  mul     [rbp+90h+arg_70]
0x1800781b7  shr     edx, 6
0x1800781ba  mov     r9d, edx; unsigned int
0x1800781bd  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x1800781c2  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800781c7  lea     rcx, [rsp+190h+pguid]
0x1800781cc  jmp     loc_18007835F
0x1800781d1  lea     rcx, [rsp+190h+pguid]; struct _GUID *
0x1800781d6  call    ?WinSqmStartSession@@YAPEAU_GUID@@PEAU1@KK@Z; WinSqmStartSession(_GUID *,ulong,ulong)
0x1800781db  mov     r9d, r15d; unsigned int
0x1800781de  mov     r8d, 8D7h; unsigned int
0x1800781e4  mov     rdx, rax; struct _GUID *
0x1800781e7  mov     rdi, rax
0x1800781ea  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800781ef  mov     r9d, r14d; unsigned int
0x1800781f2  mov     r8d, 8DEh; unsigned int
0x1800781f8  mov     rdx, rdi; struct _GUID *
0x1800781fb  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078200  mov     r9d, esi; unsigned int
0x180078203  mov     r8d, 14E2h; unsigned int
0x180078209  mov     rdx, rdi; struct _GUID *
0x18007820c  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078211  test    r14d, r14d
0x180078214  jz      short loc_180078239
0x180078216  xorps   xmm1, xmm1
0x180078219  xorps   xmm0, xmm0
0x18007821c  cvtsi2sd xmm1, rsi
0x180078221  cvtsi2sd xmm0, r14
0x180078226  divsd   xmm1, xmm0
0x18007822a  mulsd   xmm1, cs:__real@4059000000000000
0x180078232  cvttsd2si r9, xmm1
0x180078237  jmp     short loc_18007823C
0x180078239  xor     r9d, r9d; unsigned int
0x18007823c  mov     r8d, 14E3h; unsigned int
0x180078242  mov     rdx, rdi; struct _GUID *
0x180078245  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x18007824a  mov     r9d, r12d; unsigned int
0x18007824d  mov     r8d, 14E4h; unsigned int
0x180078253  mov     rdx, rdi; struct _GUID *
0x180078256  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x18007825b  mov     r9d, [rbp+90h+arg_20]; unsigned int
0x180078262  mov     r8d, 14DEh; unsigned int
0x180078268  mov     rdx, rdi; struct _GUID *
0x18007826b  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078270  mov     r9d, [rbp+90h+arg_28]; unsigned int
0x180078277  mov     r8d, 8D9h; unsigned int
0x18007827d  mov     rdx, rdi; struct _GUID *
0x180078280  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078285  xor     r9d, r9d; unsigned int
0x180078288  mov     r8d, 8D8h; unsigned int
0x18007828e  mov     rdx, rdi; struct _GUID *
0x180078291  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078296  mov     r9d, [rbp+90h+arg_38]; unsigned int
0x18007829d  mov     r8d, 8DAh; unsigned int
0x1800782a3  mov     rdx, rdi; struct _GUID *
0x1800782a6  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800782ab  mov     r9d, [rbp+90h+arg_40]; unsigned int
0x1800782b2  mov     r8d, 8DBh; unsigned int
0x1800782b8  mov     rdx, rdi; struct _GUID *
0x1800782bb  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800782c0  mov     r9d, [rbp+90h+arg_48]; unsigned int
0x1800782c7  mov     r8d, 14DDh; unsigned int
0x1800782cd  mov     rdx, rdi; struct _GUID *
0x1800782d0  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800782d5  mov     r9d, [rbp+90h+arg_50]; unsigned int
0x1800782dc  mov     r8d, 14DFh; unsigned int
0x1800782e2  mov     rdx, rdi; struct _GUID *
0x1800782e5  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800782ea  mov     r9d, [rbp+90h+arg_58]; unsigned int
0x1800782f1  mov     r8d, 8DCh; unsigned int
0x1800782f7  mov     rdx, rdi; struct _GUID *
0x1800782fa  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800782ff  mov     r9d, [rbp+90h+arg_60]; unsigned int
0x180078306  mov     r8d, 8DDh; unsigned int
0x18007830c  mov     rdx, rdi; struct _GUID *
0x18007830f  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078314  or      edx, 0FFFFFFFFh
0x180078317  mov     esi, 10624DD3h
0x18007831c  cmp     [rbp+90h+arg_68], edx
0x180078322  jz      short loc_18007832F
0x180078324  mov     eax, esi
0x180078326  mul     [rbp+90h+arg_68]
0x18007832c  shr     edx, 6
0x18007832f  mov     r9d, edx; unsigned int
0x180078332  mov     r8d, 1502h; unsigned int
0x180078338  mov     rdx, rdi; struct _GUID *
0x18007833b  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180078340  mov     eax, esi
0x180078342  mov     r8d, 14E5h; unsigned int
0x180078348  mul     [rbp+90h+arg_70]
0x18007834e  shr     edx, 6
0x180078351  mov     r9d, edx; unsigned int
0x180078354  mov     rdx, rdi; struct _GUID *
0x180078357  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x18007835c  mov     rcx, rdi; struct _GUID *
0x18007835f  call    ?WinSqmEndSession@@YAXPEAU_GUID@@@Z; WinSqmEndSession(_GUID *)
0x180078364  mov     eax, ebx
0x180078366  mov     rcx, [rbp+90h+var_40]
0x18007836a  xor     rcx, rsp; StackCookie
0x18007836d  call    __security_check_cookie
0x180078372  add     rsp, 160h
0x180078379  pop     r15
0x18007837b  pop     r14
0x18007837d  pop     r12
0x18007837f  pop     rdi
0x180078380  pop     rsi
0x180078381  pop     rbx
0x180078382  pop     rbp
0x180078383  retn
```
