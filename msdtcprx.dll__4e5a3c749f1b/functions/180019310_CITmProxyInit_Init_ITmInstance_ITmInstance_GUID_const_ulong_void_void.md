# CITmProxyInit::Init(ITmInstance *,ITmInstance *,_GUID const &,ulong,void *,void * *)

- ea: `0x180019310`
- end: `0x180019901`
- name: `?Init@CITmProxyInit@@UEAAJPEAUITmInstance@@0AEBU_GUID@@KPEAXPEAPEAX@Z`
- size: `1521`
- prototype: `__int64 __usercall@<rax>(CITmProxyInit *__hidden this@<rcx>, struct ITmInstance *@<rdx>, struct ITmInstance *@<r8>, const struct _GUID *@<r9>, unsigned int, void *, void **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180012130`
- `0x180019310`
- `0x180019908`
- `0x18001d138`
- `0x18001d178`
- `0x180021288`
- `0x180021444`
- `0x180021504`
- `0x18002187c`
- `0x18002199c`
- `0x180021bc0`
- `0x18004e078`
- `0x18007ce08`
- `0x18007d018`
- `0x180081d9e`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019869`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019869`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800193a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800193a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800196b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800196ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800196b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800196ea`
- `WS2_32!__imp_WSAStartup` at `0x180019476`
- `WS2_32!__imp_WSAStartup` at `0x180019476`
- `WS2_32!__imp_WSACleanup` at `0x180019496`
- `WS2_32!__imp_WSACleanup` at `0x180019496`

## string_xrefs

- `0x1800193e1`: `com\complus\dtc\dtc\msdtcprx\src\dtcinit.cpp`
- `0x18001978c`: `com\complus\dtc\dtc\msdtcprx\src\dtcinit.cpp`
- `0x180019805`: `com\complus\dtc\dtc\msdtcprx\src\dtcinit.cpp`
- `0x180019412`: `com\complus\dtc\dtc\msdtcprx\src\dtcinit.cpp`
- `0x1800194ff`: `com\complus\dtc\dtc\msdtcprx\src\dtcinit.cpp`

## pseudocode

```c
__int64 __fastcall CITmProxyInit::Init(
        CITmProxyInit *this,
        struct ITmInstance *a2,
        struct ITmInstance *a3,
        const struct _GUID *a4,
        unsigned int a5,
        _DWORD *a6,
        void **a7)
{
  struct INameObject *v7; // rsi
  struct INameObject *v8; // r12
  struct INameObject *v9; // r15
  struct INameObject *v10; // r14
  struct ITmInstance *v11; // rbx
  CITmProxyInit *v14; // rcx
  int v15; // ebx
  int v16; // eax
  CITmProxyInit *v17; // rcx
  bool v18; // sf
  struct ITmInstance *v19; // rsi
  signed int NeededNameObjects; // eax
  int inited; // eax
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // r10
  const char *v24; // r8
  __int64 v25; // rax
  struct CTipTmId *v26; // rax
  struct CTipTmId *v27; // rbx
  DWORD v28; // ecx
  struct INameObject *v29; // rcx
  unsigned int v30; // ebx
  struct INameObject **v31; // [rsp+28h] [rbp-D8h]
  struct INameObject **v32; // [rsp+28h] [rbp-D8h]
  void *v33; // [rsp+50h] [rbp-B0h]
  struct INameObject *v34; // [rsp+60h] [rbp-A0h] BYREF
  struct INameObject *v35; // [rsp+68h] [rbp-98h] BYREF
  struct INameObject *v36; // [rsp+70h] [rbp-90h] BYREF
  struct INameObject *v37; // [rsp+78h] [rbp-88h] BYREF
  struct ITmInstance *v38; // [rsp+80h] [rbp-80h]
  struct INameObject *v39; // [rsp+88h] [rbp-78h] BYREF
  struct ITmInstance *v40; // [rsp+90h] [rbp-70h]
  _DWORD *v41; // [rsp+98h] [rbp-68h]
  void **v42; // [rsp+A0h] [rbp-60h]
  const struct _GUID *v43; // [rsp+A8h] [rbp-58h]
  WSAData WSAData; // [rsp+B0h] [rbp-50h] BYREF
  char v45[1040]; // [rsp+250h] [rbp+150h] BYREF

  v7 = 0;
  v8 = 0;
  v41 = a6;
  v9 = 0;
  v10 = 0;
  v43 = a4;
  v38 = a2;
  v11 = a3;
  v40 = a3;
  v42 = a7;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v39 = 0;
  if ( !a7 )
    return 2147942487LL;
  *a7 = 0;
  EnterCriticalSection(&stru_1800D5298);
  if ( (a5 & 0x40000000) != 0 )
  {
    g_fInternalTmComponent = 1;
    goto LABEL_8;
  }
  v15 = CITmProxyInit::CheckAndProcessRestore(v14);
  if ( v15 >= 0 )
  {
    v11 = v40;
LABEL_8:
    if ( *((_DWORD *)this + 6) )
      goto LABEL_48;
    memset_0(&WSAData, 0, sizeof(WSAData));
    v16 = WSAStartup(1u, &WSAData);
    v18 = v16 < 0;
    if ( v16 > 0 )
    {
      v16 = (unsigned __int16)v16 | 0x80070000;
      v18 = v16 < 0;
    }
    if ( !v18 )
    {
      if ( !LOBYTE(WSAData.wVersion) )
      {
        WSACleanup();
        v16 = -2147418113;
      }
      if ( v16 >= 0 )
        *(_DWORD *)(*((_QWORD *)this + 1) + 3836LL) = 1;
    }
    v19 = v38;
    NeededNameObjects = CITmProxyInit::GetNeededNameObjects(v17, v38, v11, &v34, &v35, &v36, &v37, &v39);
    if ( NeededNameObjects )
    {
      if ( NeededNameObjects > 0 )
        NeededNameObjects = (unsigned __int16)NeededNameObjects | 0x80070000;
      DELLog(
        v19,
        1u,
        0xAu,
        0xC000114B,
        NeededNameObjects,
        1,
        0,
        0,
        "com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinit.cpp",
        574,
        v33);
      v8 = v34;
      v15 = -2147168217;
      goto LABEL_20;
    }
    inited = CITmProxyInit::InitProxyGlobalVariables(this, v19, v11);
    v8 = v34;
    v15 = inited;
    if ( inited < 0 )
    {
LABEL_20:
      v9 = v35;
      v10 = v36;
      v7 = v37;
      goto LABEL_49;
    }
    *(_DWORD *)(*((_QWORD *)this + 1) + 3560LL) = (a5 >> 1) & 1;
    *(_QWORD *)(*((_QWORD *)this + 1) + 3488LL) = v8;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 3488LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 3488LL));
    v9 = v35;
    *(_QWORD *)(*((_QWORD *)this + 1) + 3496LL) = v35;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 3496LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 3496LL));
    v10 = v36;
    *(_QWORD *)(*((_QWORD *)this + 1) + 3504LL) = v36;
    if ( v10 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 3504LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 3504LL));
    v7 = v37;
    *(_QWORD *)(*((_QWORD *)this + 1) + 3512LL) = v37;
    if ( !v7 )
      goto LABEL_40;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 3512LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 3512LL));
    if ( (int)GetFullHostName(v38, v45) < 0 )
    {
LABEL_39:
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 3512LL) + 16LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 3512LL));
      *(_QWORD *)(*((_QWORD *)this + 1) + 3512LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 1) + 3556LL) = 1;
      goto LABEL_40;
    }
    v23 = 1026;
    v24 = (const char *)(*((_QWORD *)this + 1) + 3576LL);
    if ( *v24 )
      StringCbCopyA(v45, 0x402u, v24);
    v25 = -1;
    do
      ++v25;
    while ( v45[v25] );
    if ( v25 + 2 > v23 )
    {
      v15 = -2147024809;
      goto LABEL_49;
    }
    StringCbCatA(v45, v22, v24);
    LODWORD(v34) = CTipTmId::GetSizeForStringDerivation(v45);
    v26 = (struct CTipTmId *)operator new((unsigned int)v34);
    v27 = v26;
    if ( v26 )
    {
      if ( !(unsigned int)CTipTmId::DeriveFromString(v26, (unsigned int)v34, v45) )
      {
        SetLastError(0);
LABEL_38:
        *(_QWORD *)(*((_QWORD *)this + 1) + 3528LL) = v27;
        if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 3528LL) )
          goto LABEL_39;
LABEL_40:
        v29 = v39;
        v30 = 0;
        *(_QWORD *)(*((_QWORD *)this + 1) + 3520LL) = v39;
        if ( v29 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 3520LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 3520LL));
        if ( v41 && *v41 )
          v30 = v41[1];
        TraceStringInline(
          15,
          4,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinit.cpp",
          678,
          L"CITmProxyInit::Init",
          0,
          L"Initializing the CM");
        v15 = InitializeCm(
                v30,
                g_ProxyVersionInfo,
                *(_QWORD *)(*((_QWORD *)this + 1) + 3488LL),
                *(_QWORD *)(*((_QWORD *)this + 1) + 3496LL),
                (_QWORD *)(*((_QWORD *)this + 1) + 3536LL),
                (_QWORD *)(*((_QWORD *)this + 1) + 3544LL));
        if ( v15 )
        {
          LODWORD(v32) = v15;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinit.cpp",
            688,
            L"CITmProxyInit::Init",
            v32,
            L"Error from InitializeCm");
          goto LABEL_49;
        }
        *((_DWORD *)this + 6) = 1;
LABEL_48:
        v15 = CITmProxyInit::InitiateStartupSequence(
                this,
                v38,
                *(struct INameObject **)(*((_QWORD *)this + 1) + 3496LL),
                (a5 & 1) == 0,
                a5 & 0x80000000);
        goto LABEL_49;
      }
      operator delete(v27);
      v28 = -2147024809;
    }
    else
    {
      v28 = -2147024882;
    }
    SetLastError(v28);
    v27 = 0;
    goto LABEL_38;
  }
  LODWORD(v31) = v15;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinit.cpp",
    539,
    L"CITmProxyInit::Init",
    v31,
    L"CheckAndProcessRestore failed");
  DELLog(v38, 1u, 0xAu, 0xC0001160, v15, 1, 0, 0, "com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinit.cpp", 540, v33);
LABEL_49:
  LeaveCriticalSection(&stru_1800D5298);
  if ( !v15 )
    v15 = (**(__int64 (__fastcall ***)(CITmProxyInit *, const struct _GUID *, void **))this)(this, v43, v42);
  if ( v8 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v9 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v10 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v7 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180019310  push    rbp
0x180019312  push    rbx
0x180019313  push    rsi
0x180019314  push    rdi
0x180019315  push    r12
0x180019317  push    r13
0x180019319  push    r14
0x18001931b  push    r15
0x18001931d  lea     rbp, [rsp-578h]
0x180019325  sub     rsp, 678h
0x18001932c  mov     rax, cs:__security_cookie
0x180019333  xor     rax, rsp
0x180019336  mov     [rbp+5B0h+var_50], rax
0x18001933d  mov     rax, [rbp+5B0h+arg_28]
0x180019344  xor     esi, esi
0x180019346  xor     r12d, r12d
0x180019349  mov     [rbp+5B0h+var_618], rax
0x18001934d  mov     rax, [rbp+5B0h+arg_30]
0x180019354  xor     r15d, r15d
0x180019357  xor     r14d, r14d
0x18001935a  mov     [rbp+5B0h+var_608], r9
0x18001935e  mov     [rbp+5B0h+var_630], rdx
0x180019362  mov     rbx, r8
0x180019365  mov     [rbp+5B0h+var_620], rbx
0x180019369  mov     rdi, rcx
0x18001936c  mov     [rbp+5B0h+var_610], rax
0x180019370  mov     [rsp+6B0h+var_650], r12
0x180019375  mov     [rsp+6B0h+var_648], r15
0x18001937a  mov     [rsp+6B0h+var_640], r14
0x18001937f  mov     [rsp+6B0h+var_638], rsi
0x180019384  mov     [rbp+5B0h+var_628], rsi
0x180019388  test    rax, rax
0x18001938b  jnz     short loc_180019397
0x18001938d  mov     eax, 80070057h
0x180019392  jmp     loc_1800198DE
0x180019397  lea     rcx, stru_1800D5298; lpCriticalSection
0x18001939e  mov     [rax], rsi
0x1800193a1  call    cs:__imp_EnterCriticalSection
0x1800193a7  mov     r13d, [rbp+5B0h+arg_20]
0x1800193ae  bt      r13d, 1Eh
0x1800193b3  jnb     short loc_1800193C4
0x1800193b5  mov     cs:?g_fInternalTmComponent@@3HA, 1; int g_fInternalTmComponent
0x1800193bf  jmp     loc_18001944F
0x1800193c4  call    ?CheckAndProcessRestore@CITmProxyInit@@AEAAJXZ; CITmProxyInit::CheckAndProcessRestore(void)
0x1800193c9  mov     ebx, eax
0x1800193cb  test    eax, eax
0x1800193cd  jns     short loc_18001944B
0x1800193cf  mov     r13d, 1
0x1800193d5  lea     rax, aCheckandproces; "CheckAndProcessRestore failed"
0x1800193dc  mov     [rsp+6B0h+var_680], rax
0x1800193e1  lea     r8, aComComplusDtcD_25; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800193e8  lea     rax, aCitmproxyinitI; "CITmProxyInit::Init"
0x1800193ef  mov     dword ptr [rsp+6B0h+var_688], ebx
0x1800193f3  mov     r9d, 21Bh
0x1800193f9  mov     [rsp+6B0h+var_690], rax
0x1800193fe  lea     ecx, [r13+0Eh]
0x180019402  mov     edx, r13d
0x180019405  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001940a  mov     [rsp+6B0h+var_668], 21Ch; int
0x180019412  lea     rcx, aComComplusDtcD_38; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180019419  mov     [rsp+6B0h+var_670], rcx; char *
0x18001941e  lea     r8d, [r13+9]; unsigned __int16
0x180019422  mov     rcx, [rbp+5B0h+var_630]; struct ITmInstance *
0x180019426  mov     edx, r13d; unsigned __int16
0x180019429  mov     [rsp+6B0h+var_678], rsi; void *
0x18001942e  mov     r9d, 0C0001160h; unsigned int
0x180019434  mov     dword ptr [rsp+6B0h+var_680], esi; unsigned int
0x180019438  mov     dword ptr [rsp+6B0h+var_688], r13d; int
0x18001943d  mov     dword ptr [rsp+6B0h+var_690], ebx; int
0x180019441  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x180019446  jmp     loc_180019862
0x18001944b  mov     rbx, [rbp+5B0h+var_620]
0x18001944f  cmp     [rdi+18h], esi
0x180019452  jnz     loc_180019833
0x180019458  xor     edx, edx; Val
0x18001945a  lea     rcx, [rbp+5B0h+WSAData]; void *
0x18001945e  mov     r8d, 198h; Size
0x180019464  call    memset_0
0x180019469  mov     r14d, 1
0x18001946f  lea     rdx, [rbp+5B0h+WSAData]; lpWSAData
0x180019473  mov     ecx, r14d; wVersionRequested
0x180019476  call    cs:__imp_WSAStartup
0x18001947c  mov     r15d, 80070000h
0x180019482  test    eax, eax
0x180019484  jle     short loc_18001948E
0x180019486  movzx   eax, ax
0x180019489  or      eax, r15d
0x18001948c  test    eax, eax
0x18001948e  js      short loc_1800194B0
0x180019490  cmp     byte ptr [rbp+5B0h+WSAData.wVersion], r14b
0x180019494  jnb     short loc_1800194A1
0x180019496  call    cs:__imp_WSACleanup
0x18001949c  mov     eax, 8000FFFFh
0x1800194a1  test    eax, eax
0x1800194a3  js      short loc_1800194B0
0x1800194a5  mov     rax, [rdi+8]
0x1800194a9  mov     [rax+0EFCh], r14d
0x1800194b0  mov     rsi, [rbp+5B0h+var_630]
0x1800194b4  lea     rax, [rbp+5B0h+var_628]
0x1800194b8  mov     [rsp+6B0h+var_678], rax; struct INameObject **
0x1800194bd  lea     r9, [rsp+6B0h+var_650]; struct INameObject **
0x1800194c2  lea     rax, [rsp+6B0h+var_638]
0x1800194c7  mov     r8, rbx; struct ITmInstance *
0x1800194ca  mov     [rsp+6B0h+var_680], rax; struct INameObject **
0x1800194cf  mov     rdx, rsi; struct ITmInstance *
0x1800194d2  lea     rax, [rsp+6B0h+var_640]
0x1800194d7  mov     [rsp+6B0h+var_688], rax; struct INameObject **
0x1800194dc  lea     rax, [rsp+6B0h+var_648]
0x1800194e1  mov     [rsp+6B0h+var_690], rax; struct INameObject **
0x1800194e6  call    ?GetNeededNameObjects@CITmProxyInit@@AEAAJPEAUITmInstance@@0PEAPEAUINameObject@@1111@Z; CITmProxyInit::GetNeededNameObjects(ITmInstance *,ITmInstance *,INameObject * *,INameObject * *,INameObject * *,INameObject * *,INameObject * *)
0x1800194eb  test    eax, eax
0x1800194ed  jz      short loc_180019553
0x1800194ef  jle     short loc_1800194F7
0x1800194f1  movzx   eax, ax
0x1800194f4  or      eax, r15d
0x1800194f7  mov     [rsp+6B0h+var_668], 23Eh; int
0x1800194ff  lea     rcx, aComComplusDtcD_38; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180019506  mov     [rsp+6B0h+var_670], rcx; char *
0x18001950b  mov     r8d, 0Ah; unsigned __int16
0x180019511  mov     [rsp+6B0h+var_678], r12; void *
0x180019516  mov     edx, r14d; unsigned __int16
0x180019519  mov     dword ptr [rsp+6B0h+var_680], r12d; unsigned int
0x18001951e  mov     r9d, 0C000114Bh; unsigned int
0x180019524  mov     dword ptr [rsp+6B0h+var_688], r14d; int
0x180019529  mov     rcx, rsi; struct ITmInstance *
0x18001952c  mov     dword ptr [rsp+6B0h+var_690], eax; int
0x180019530  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x180019535  mov     r12, [rsp+6B0h+var_650]
0x18001953a  mov     ebx, 8004D027h
0x18001953f  mov     r15, [rsp+6B0h+var_648]
0x180019544  mov     r14, [rsp+6B0h+var_640]
0x180019549  mov     rsi, [rsp+6B0h+var_638]
0x18001954e  jmp     loc_180019862
0x180019553  mov     r8, rbx; struct ITmInstance *
0x180019556  mov     rdx, rsi; struct ITmInstance *
0x180019559  mov     rcx, rdi; this
0x18001955c  call    ?InitProxyGlobalVariables@CITmProxyInit@@AEAAJPEAUITmInstance@@0@Z; CITmProxyInit::InitProxyGlobalVariables(ITmInstance *,ITmInstance *)
0x180019561  mov     r12, [rsp+6B0h+var_650]
0x180019566  mov     ebx, eax
0x180019568  test    eax, eax
0x18001956a  js      short loc_18001953F
0x18001956c  mov     rax, [rdi+8]
0x180019570  mov     ecx, r13d
0x180019573  shr     ecx, 1
0x180019575  and     ecx, r14d
0x180019578  mov     [rax+0DE8h], ecx
0x18001957e  mov     rax, [rdi+8]
0x180019582  mov     [rax+0DA0h], r12
0x180019589  mov     rax, [rdi+8]
0x18001958d  mov     rcx, [rax+0DA0h]
0x180019594  mov     rax, [rcx]
0x180019597  mov     rax, [rax+8]
0x18001959b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195a0  mov     rax, [rdi+8]
0x1800195a4  mov     r15, [rsp+6B0h+var_648]
0x1800195a9  mov     [rax+0DA8h], r15
0x1800195b0  mov     rax, [rdi+8]
0x1800195b4  mov     rcx, [rax+0DA8h]
0x1800195bb  mov     rax, [rcx]
0x1800195be  mov     rax, [rax+8]
0x1800195c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195c7  mov     r14, [rsp+6B0h+var_640]
0x1800195cc  mov     rax, [rdi+8]
0x1800195d0  mov     [rax+0DB0h], r14
0x1800195d7  test    r14, r14
0x1800195da  jz      short loc_1800195F3
0x1800195dc  mov     rax, [rdi+8]
0x1800195e0  mov     rcx, [rax+0DB0h]
0x1800195e7  mov     rax, [rcx]
0x1800195ea  mov     rax, [rax+8]
0x1800195ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195f3  mov     rsi, [rsp+6B0h+var_638]
0x1800195f8  mov     rax, [rdi+8]
0x1800195fc  mov     [rax+0DB8h], rsi
0x180019603  test    rsi, rsi
0x180019606  jz      loc_18001973D
0x18001960c  mov     rax, [rdi+8]
0x180019610  mov     rcx, [rax+0DB8h]
0x180019617  mov     rax, [rcx]
0x18001961a  mov     rax, [rax+8]
0x18001961e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019623  mov     rcx, [rbp+5B0h+var_630]
0x180019627  lea     rdx, [rbp+5B0h+var_460]
0x18001962e  call    GetFullHostName
0x180019633  test    eax, eax
0x180019635  js      loc_180019709
0x18001963b  mov     r8, [rdi+8]
0x18001963f  mov     r10d, 402h
0x180019645  add     r8, 0DF8h; char *
0x18001964c  cmp     byte ptr [r8], 0
0x180019650  jz      short loc_180019661
0x180019652  mov     edx, r10d; unsigned __int64
0x180019655  lea     rcx, [rbp+5B0h+var_460]; char *
0x18001965c  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180019661  lea     rcx, [rbp+5B0h+var_460]
0x180019668  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001966c  inc     rax
0x18001966f  cmp     byte ptr [rcx+rax], 0
0x180019673  jnz     short loc_18001966C
0x180019675  add     rax, 2
0x180019679  cmp     rax, r10
0x18001967c  jbe     short loc_180019688
0x18001967e  mov     ebx, 80070057h
0x180019683  jmp     loc_180019862
0x180019688  lea     rcx, [rbp+5B0h+var_460]; char *
0x18001968f  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180019694  lea     rcx, [rbp+5B0h+var_460]; char *
0x18001969b  call    ?GetSizeForStringDerivation@CTipTmId@@SAJPEAD@Z; CTipTmId::GetSizeForStringDerivation(char *)
0x1800196a0  mov     ecx, eax; Size
0x1800196a2  mov     dword ptr [rsp+6B0h+var_650], eax
0x1800196a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800196ab  mov     rbx, rax
0x1800196ae  test    rax, rax
0x1800196b1  jnz     short loc_1800196C2
0x1800196b3  mov     ecx, 8007000Eh; dwErrCode
0x1800196b8  call    cs:__imp_SetLastError
0x1800196be  xor     ebx, ebx
0x1800196c0  jmp     short loc_1800196F0
0x1800196c2  mov     edx, dword ptr [rsp+6B0h+var_650]; unsigned int
0x1800196c6  lea     r8, [rbp+5B0h+var_460]; char *
0x1800196cd  mov     rcx, rbx; struct CTipTmId *
0x1800196d0  call    ?DeriveFromString@CTipTmId@@SAJPEAV1@KPEAD@Z; CTipTmId::DeriveFromString(CTipTmId *,ulong,char *)
0x1800196d5  test    eax, eax
0x1800196d7  jz      short loc_1800196E8
0x1800196d9  mov     rcx, rbx; Block
0x1800196dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800196e1  mov     ecx, 80070057h
0x1800196e6  jmp     short loc_1800196B8
0x1800196e8  xor     ecx, ecx; dwErrCode
0x1800196ea  call    cs:__imp_SetLastError
0x1800196f0  mov     rax, [rdi+8]
0x1800196f4  mov     [rax+0DC8h], rbx
0x1800196fb  mov     rax, [rdi+8]
0x1800196ff  cmp     qword ptr [rax+0DC8h], 0
0x180019707  jnz     short loc_18001973D
0x180019709  mov     rax, [rdi+8]
0x18001970d  mov     rcx, [rax+0DB8h]
0x180019714  mov     rax, [rcx]
0x180019717  mov     rax, [rax+10h]
0x18001971b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019720  mov     rax, [rdi+8]
0x180019724  mov     qword ptr [rax+0DB8h], 0
0x18001972f  mov     rax, [rdi+8]
0x180019733  mov     dword ptr [rax+0DE4h], 1
0x18001973d  mov     rcx, [rbp+5B0h+var_628]
0x180019741  xor     ebx, ebx
0x180019743  mov     rax, [rdi+8]
0x180019747  mov     [rax+0DC0h], rcx
0x18001974e  test    rcx, rcx
0x180019751  jz      short loc_18001976A
0x180019753  mov     rax, [rdi+8]
0x180019757  mov     rcx, [rax+0DC0h]
0x18001975e  mov     rax, [rcx]
0x180019761  mov     rax, [rax+8]
0x180019765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001976a  mov     rax, [rbp+5B0h+var_618]
0x18001976e  test    rax, rax
0x180019771  jz      short loc_18001977B
0x180019773  cmp     dword ptr [rax], 1
0x180019776  jb      short loc_18001977B
0x180019778  mov     ebx, [rax+4]
0x18001977b  mov     edx, 4
0x180019780  lea     rax, aInitializingTh; "Initializing the CM"
0x180019787  mov     [rsp+6B0h+var_680], rax
0x18001978c  lea     r8, aComComplusDtcD_25; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180019793  lea     rax, aCitmproxyinitI; "CITmProxyInit::Init"
0x18001979a  mov     [rsp+6B0h+var_688], 0
0x1800197a3  mov     r9d, 2A6h
0x1800197a9  mov     [rsp+6B0h+var_690], rax
0x1800197ae  lea     ecx, [rdx+0Bh]
0x1800197b1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800197b6  mov     r8, [rdi+8]
0x1800197ba  mov     rdx, cs:?g_ProxyVersionInfo@@3U_VersionInfo@@A; _VersionInfo g_ProxyVersionInfo
0x1800197c1  mov     r9, [r8+0DA8h]
0x1800197c8  lea     rcx, [r8+0DD0h]
0x1800197cf  lea     rax, [r8+0DD8h]
0x1800197d6  mov     r8, [r8+0DA0h]
0x1800197dd  mov     [rsp+6B0h+var_688], rax
0x1800197e2  mov     [rsp+6B0h+var_690], rcx
0x1800197e7  mov     ecx, ebx
0x1800197e9  call    ?InitializeCm@@YAJKU_VersionInfo@@PEAUINameObject@@1PEAPEAUIConnectionManager@@PEAPEAUIConnectionDispenser@@@Z; InitializeCm(ulong,_VersionInfo,INameObject *,INameObject *,IConnectionManager * *,IConnectionDispenser * *)
0x1800197ee  mov     ebx, eax
0x1800197f0  test    eax, eax
0x1800197f2  jz      short loc_18001982C
0x1800197f4  mov     edx, 1
0x1800197f9  lea     rax, aErrorFromIniti_0; "Error from InitializeCm"
0x180019800  mov     [rsp+6B0h+var_680], rax
0x180019805  lea     r8, aComComplusDtcD_25; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18001980c  lea     rax, aCitmproxyinitI; "CITmProxyInit::Init"
0x180019813  mov     dword ptr [rsp+6B0h+var_688], ebx
0x180019817  mov     r9d, 2B0h
0x18001981d  mov     [rsp+6B0h+var_690], rax
0x180019822  lea     ecx, [rdx+0Eh]
0x180019825  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001982a  jmp     short loc_180019862
0x18001982c  mov     dword ptr [rdi+18h], 1
0x180019833  mov     r8, [rdi+8]
0x180019837  mov     eax, r13d
0x18001983a  mov     rdx, [rbp+5B0h+var_630]; struct ITmInstance *
0x18001983e  and     eax, 80000000h
  ... truncated ...
```
