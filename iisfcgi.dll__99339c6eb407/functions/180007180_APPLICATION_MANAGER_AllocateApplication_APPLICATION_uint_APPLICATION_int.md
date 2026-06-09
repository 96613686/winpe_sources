# APPLICATION_MANAGER::AllocateApplication(APPLICATION * *,uint *,APPLICATION *,int *)

- ea: `0x180007180`
- end: `0x1800075e9`
- name: `?AllocateApplication@APPLICATION_MANAGER@@AEAAJPEAPEAVAPPLICATION@@PEAIPEAV2@PEAH@Z`
- size: `1129`
- prototype: `__int64 __fastcall(APPLICATION_MANAGER *this, struct APPLICATION **, unsigned int *, struct APPLICATION *, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000794c`
- `0x1800083d0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180004b90`
- `0x180005030`
- `0x180005294`
- `0x180006480`
- `0x180007090`
- `0x180007180`
- `0x180008128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007553`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007296`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000748f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007296`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000748f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800072fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000743d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800072fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000743d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007424`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007431`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007424`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007431`

## pseudocode

```c
__int64 __fastcall APPLICATION_MANAGER::AllocateApplication(
        APPLICATION_MANAGER *this,
        struct APPLICATION **a2,
        unsigned int *a3,
        struct APPLICATION *a4,
        int *a5)
{
  int v7; // ebp
  _QWORD **v8; // r12
  _DWORD *v9; // r14
  _QWORD *v10; // rax
  __int64 v11; // rdi
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // ebx
  _DWORD *v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  struct APPLICATION *v22; // [rsp+E8h] [rbp+20h]

  v22 = a4;
  *a2 = 0;
  *a3 = 0;
  *a5 = 0;
  if ( *((_DWORD *)this + 36) )
    return (unsigned int)-2147023901;
  v7 = 0;
  v8 = (_QWORD **)((char *)this + 88);
  v9 = (_DWORD *)((char *)this + 80);
  while ( 1 )
  {
    v10 = *v8;
    v11 = 0;
    if ( *v8 == v8 )
      break;
    while ( 1 )
    {
      v11 = (__int64)(v10 - 3);
      if ( !a4 || !*(_DWORD *)(v11 + 276) || (struct APPLICATION *)v11 == a4 )
        break;
      v10 = (_QWORD *)*v10;
      v11 = 0;
      if ( v10 == v8 )
      {
        v9 = (_DWORD *)((char *)this + 80);
        goto LABEL_10;
      }
    }
    v12 = (_QWORD *)*v10;
    if ( *(_QWORD **)(*v10 + 8LL) != v10 )
      goto LABEL_33;
    v13 = (_QWORD *)v10[1];
    if ( (_QWORD *)*v13 != v10 )
      goto LABEL_33;
    *v13 = v12;
    v9 = (_DWORD *)((char *)this + 80);
    v12[1] = v13;
    --*((_DWORD *)this + 20);
    if ( v10 == (_QWORD *)24 )
      break;
    v14 = (_QWORD *)((char *)this + 64);
    v15 = *((_QWORD *)this + 8);
    if ( *(APPLICATION_MANAGER **)(v15 + 8) != (APPLICATION_MANAGER *)((char *)this + 64) )
      goto LABEL_33;
    *v10 = v15;
    v10[1] = v14;
    *(_QWORD *)(v15 + 8) = v10;
    *v14 = v10;
    ++*((_DWORD *)this + 15);
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 156));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v7 = APPLICATION::BeginRequest((APPLICATION *)v11);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( v7 >= 0 )
      goto LABEL_29;
    APPLICATION::RealShutdown((APPLICATION *)v11, v7, 0, 1, 1);
    APPLICATION::DereferenceApplication((APPLICATION *)v11);
    a4 = v22;
  }
LABEL_10:
  if ( *v9 + *((_DWORD *)this + 15) >= APPLICATION_MANAGER::QueryMaxApplications(this) )
  {
    *a5 = 1;
    if ( v7 < 0 )
    {
      if ( !v11 )
        return (unsigned int)v7;
LABEL_28:
      APPLICATION::RealShutdown((APPLICATION *)v11, v7, 0, 0, 1);
      APPLICATION::DereferenceApplication((APPLICATION *)v11);
      return (unsigned int)v7;
    }
    goto LABEL_29;
  }
  if ( *((_DWORD *)this + 127) )
  {
    v16 = *((_DWORD *)this + *((unsigned int *)this + 1130) + 130);
    if ( GetTickCount() - v16 < 0xEA60 )
    {
      v7 = -2147467259;
      *a3 = 200009;
      return (unsigned int)v7;
    }
  }
  _InterlockedAdd((volatile signed __int32 *)this + 35, 1u);
  v17 = operator new(0x980u);
  v11 = (__int64)v17;
  if ( v17 )
  {
    v17[4] = 1095189318;
    *(_QWORD *)v17 = &APPLICATION::`vftable'{for `ISEND_QUEUE_PRODUCER'};
    *((_QWORD *)v17 + 5) = 0;
    *((_QWORD *)v17 + 1) = &APPLICATION::`vftable'{for `ISEND_QUEUE_CONSUMER'};
    *((_QWORD *)v17 + 6) = 0;
    v17[14] = 0;
    *((_QWORD *)v17 + 8) = 0;
    *((_QWORD *)v17 + 9) = 0;
    *((_QWORD *)v17 + 10) = 0;
    *((_QWORD *)v17 + 11) = 0;
    *((_QWORD *)v17 + 12) = 0;
    v17[26] = 0;
    v17[38] = 0;
    v17[39] = 1;
    *((_QWORD *)v17 + 20) = 1;
    *((_QWORD *)v17 + 25) = 0;
    v17[53] = 0;
    *((_QWORD *)v17 + 27) = 0;
    *((_QWORD *)v17 + 28) = 0;
    *((_QWORD *)v17 + 29) = 0;
    *((_QWORD *)v17 + 30) = 0;
    v17[62] = 0;
    v17[63] = -1;
    *((_QWORD *)v17 + 32) = 0;
    *((_QWORD *)v17 + 33) = 0;
    *((_QWORD *)v17 + 34) = 1;
    *((_QWORD *)v17 + 35) = 0;
    *((_QWORD *)v17 + 36) = 0;
    *((_QWORD *)v17 + 37) = 0;
    *((_QWORD *)v17 + 38) = 0;
    STRU::STRU((STRU *)(v17 + 78));
    STRU::STRU((STRU *)(v11 + 368));
    *(_DWORD *)(v11 + 424) = 0;
    *(_DWORD *)(v11 + 428) = GetTickCount();
    _InterlockedAdd(&APPLICATION::sm_cTotalApplications, 1u);
    v18 = (_QWORD *)((char *)this + 64);
    *(_QWORD *)(v11 + 32) = v11 + 24;
    *(_QWORD *)(v11 + 24) = v11 + 24;
    v19 = *((_QWORD *)this + 8);
    if ( *(APPLICATION_MANAGER **)(v19 + 8) != (APPLICATION_MANAGER *)((char *)this + 64) )
LABEL_33:
      __fastfail(3u);
    *(_QWORD *)(v11 + 24) = v19;
    *(_QWORD *)(v11 + 32) = v18;
    *(_QWORD *)(v19 + 8) = v11 + 24;
    *v18 = v11 + 24;
    ++*((_DWORD *)this + 15);
    _InterlockedAdd((volatile signed __int32 *)(v11 + 156), 1u);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v7 = APPLICATION::Init(
           v11,
           (__int64)this,
           *((const WCHAR **)this + 24),
           *((const unsigned __int16 **)this + 31),
           (APPLICATION_MANAGER *)((char *)this + 336),
           *((const WCHAR **)this + 53),
           *((_DWORD *)this + 112),
           *((_DWORD *)this + 113),
           *((_DWORD *)this + 114),
           *((_DWORD *)this + 115),
           *((_DWORD *)this + 116),
           *((_DWORD *)this + 117),
           *((_DWORD *)this + 125),
           *((_DWORD *)this + 126),
           *((_DWORD *)this + 128),
           *((_DWORD *)this + 129),
           a3,
           *((_DWORD *)this + 82));
    if ( v7 >= 0 )
      v7 = APPLICATION::BeginRequest((APPLICATION *)v11);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( v7 < 0 )
      goto LABEL_28;
LABEL_29:
    if ( !*a5 )
    {
      if ( *(_DWORD *)(v11 + 48) != 3 )
        *(_DWORD *)(v11 + 48) = 1;
      *a2 = (struct APPLICATION *)v11;
    }
    return (unsigned int)v7;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 35, 0xFFFFFFFF) == 1 )
  {
    APPLICATION_MANAGER::~APPLICATION_MANAGER(this);
    operator delete(this);
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180007180  mov     [rsp+arg_0], rbx
0x180007185  mov     [rsp+arg_18], r9
0x18000718a  mov     [rsp+arg_8], rdx
0x18000718f  push    rbp
0x180007190  push    rsi
0x180007191  push    rdi
0x180007192  push    r12
0x180007194  push    r13
0x180007196  push    r14
0x180007198  push    r15
0x18000719a  sub     rsp, 90h
0x1800071a1  mov     r15, [rsp+0C8h+arg_20]
0x1800071a9  xor     ebx, ebx
0x1800071ab  mov     r13, r8
0x1800071ae  mov     rsi, rcx
0x1800071b1  mov     [rdx], rbx
0x1800071b4  mov     [r8], ebx
0x1800071b7  mov     [r15], ebx
0x1800071ba  cmp     [rcx+90h], ebx
0x1800071c0  jz      short loc_1800071CC
0x1800071c2  mov     ebp, 800703E3h
0x1800071c7  jmp     loc_1800075CC
0x1800071cc  mov     ebp, ebx
0x1800071ce  lea     r12, [rcx+58h]
0x1800071d2  lea     r14, [rcx+50h]
0x1800071d6  mov     rax, [r12]
0x1800071da  mov     rdi, rbx
0x1800071dd  cmp     rax, r12
0x1800071e0  jz      short loc_180007207
0x1800071e2  lea     rdi, [rax-18h]
0x1800071e6  test    r9, r9
0x1800071e9  jz      short loc_18000723C
0x1800071eb  cmp     [rdi+114h], ebx
0x1800071f1  jz      short loc_18000723C
0x1800071f3  cmp     rdi, r9
0x1800071f6  jz      short loc_18000723C
0x1800071f8  mov     rax, [rax]
0x1800071fb  mov     rdi, rbx
0x1800071fe  cmp     rax, r12
0x180007201  jnz     short loc_1800071E2
0x180007203  lea     r14, [rsi+50h]
0x180007207  mov     rcx, rsi; this
0x18000720a  call    ?QueryMaxApplications@APPLICATION_MANAGER@@QEAAKXZ; APPLICATION_MANAGER::QueryMaxApplications(void)
0x18000720f  mov     ecx, [rsi+3Ch]
0x180007212  add     ecx, [r14]
0x180007215  cmp     ecx, eax
0x180007217  jb      loc_1800072E5
0x18000721d  mov     r14d, 1
0x180007223  mov     [r15], r14d
0x180007226  test    ebp, ebp
0x180007228  jns     loc_180007584
0x18000722e  test    rdi, rdi
0x180007231  jz      loc_1800075CC
0x180007237  jmp     loc_18000755F
0x18000723c  mov     rcx, [rax]
0x18000723f  cmp     [rcx+8], rax
0x180007243  jnz     loc_1800075A0
0x180007249  mov     rdx, [rax+8]
0x18000724d  cmp     [rdx], rax
0x180007250  jnz     loc_1800075A0
0x180007256  mov     [rdx], rcx
0x180007259  lea     r14, [rsi+50h]
0x18000725d  mov     [rcx+8], rdx
0x180007261  dec     dword ptr [r14]
0x180007264  test    rdi, rdi
0x180007267  jz      short loc_180007207
0x180007269  lea     rcx, [rsi+40h]
0x18000726d  mov     rdx, [rcx]
0x180007270  cmp     [rdx+8], rcx
0x180007274  jnz     loc_1800075A0
0x18000727a  mov     [rax], rdx
0x18000727d  mov     [rax+8], rcx
0x180007281  mov     [rdx+8], rax
0x180007285  mov     [rcx], rax
0x180007288  inc     dword ptr [rsi+3Ch]
0x18000728b  lock inc dword ptr [rdi+9Ch]
0x180007292  lea     rcx, [rsi+10h]; lpCriticalSection
0x180007296  call    cs:__imp_LeaveCriticalSection
0x18000729c  mov     rcx, rdi; this
0x18000729f  call    ?BeginRequest@APPLICATION@@QEAAJXZ; APPLICATION::BeginRequest(void)
0x1800072a4  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800072a8  mov     ebp, eax
0x1800072aa  call    cs:__imp_EnterCriticalSection
0x1800072b0  xor     ebx, ebx
0x1800072b2  test    ebp, ebp
0x1800072b4  jns     loc_18000757E
0x1800072ba  lea     r9d, [rbx+1]; int
0x1800072be  xor     r8d, r8d; unsigned int
0x1800072c1  mov     edx, ebp; int
0x1800072c3  mov     [rsp+0C8h+var_A8], r9d; int
0x1800072c8  mov     rcx, rdi; this
0x1800072cb  call    ?RealShutdown@APPLICATION@@QEAAXJIHH@Z; APPLICATION::RealShutdown(long,uint,int,int)
0x1800072d0  mov     rcx, rdi; this
0x1800072d3  call    ?DereferenceApplication@APPLICATION@@QEAAXXZ; APPLICATION::DereferenceApplication(void)
0x1800072d8  mov     r9, [rsp+0C8h+arg_18]
0x1800072e0  jmp     loc_1800071D6
0x1800072e5  cmp     [rsi+1FCh], ebx
0x1800072eb  jz      short loc_18000731D
0x1800072ed  mov     eax, [rsi+11A8h]
0x1800072f3  mov     ebx, [rsi+rax*4+208h]
0x1800072fa  call    cs:__imp_GetTickCount
0x180007300  sub     eax, ebx
0x180007302  cmp     eax, 0EA60h
0x180007307  jnb     short loc_18000731B
0x180007309  mov     ebp, 80004005h
0x18000730e  mov     dword ptr [r13+0], 30D49h
0x180007316  jmp     loc_1800075CC
0x18000731b  xor     ebx, ebx
0x18000731d  mov     r14d, 1
0x180007323  lock add [rsi+8Ch], r14d
0x18000732b  mov     ecx, 980h; Size
0x180007330  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007335  mov     rdi, rax
0x180007338  test    rax, rax
0x18000733b  jz      loc_1800075A7
0x180007341  lea     rax, ??_7APPLICATION@@6BISEND_QUEUE_PRODUCER@@@; const APPLICATION::`vftable'{for `ISEND_QUEUE_PRODUCER'}
0x180007348  mov     dword ptr [rdi+10h], 41474346h
0x18000734f  mov     [rdi], rax
0x180007352  lea     rcx, [rdi+138h]
0x180007359  lea     rax, ??_7APPLICATION@@6BISEND_QUEUE_CONSUMER@@@; const APPLICATION::`vftable'{for `ISEND_QUEUE_CONSUMER'}
0x180007360  mov     qword ptr [rdi+28h], 0
0x180007368  mov     [rdi+8], rax
0x18000736c  mov     qword ptr [rdi+30h], 0
0x180007374  mov     [rdi+38h], ebx
0x180007377  mov     [rdi+40h], rbx
0x18000737b  mov     [rdi+48h], rbx
0x18000737f  mov     [rdi+50h], rbx
0x180007383  mov     [rdi+58h], rbx
0x180007387  mov     [rdi+60h], rbx
0x18000738b  mov     [rdi+68h], ebx
0x18000738e  mov     [rdi+98h], ebx
0x180007394  mov     [rdi+9Ch], r14d
0x18000739b  mov     [rdi+0A0h], r14
0x1800073a2  mov     [rdi+0C8h], rbx
0x1800073a9  mov     [rdi+0D4h], ebx
0x1800073af  mov     [rdi+0D8h], rbx
0x1800073b6  mov     [rdi+0E0h], rbx
0x1800073bd  mov     [rdi+0E8h], rbx
0x1800073c4  mov     [rdi+0F0h], rbx
0x1800073cb  mov     [rdi+0F8h], ebx
0x1800073d1  mov     dword ptr [rdi+0FCh], 0FFFFFFFFh
0x1800073db  mov     qword ptr [rdi+100h], 0
0x1800073e6  mov     qword ptr [rdi+108h], 0
0x1800073f1  mov     [rdi+110h], r14
0x1800073f8  mov     qword ptr [rdi+118h], 0
0x180007403  mov     qword ptr [rdi+120h], 0
0x18000740e  mov     qword ptr [rdi+128h], 0
0x180007419  mov     qword ptr [rdi+130h], 0
0x180007424  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000742a  lea     rcx, [rdi+170h]
0x180007431  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180007437  mov     [rdi+1A8h], ebx
0x18000743d  call    cs:__imp_GetTickCount
0x180007443  mov     [rdi+1ACh], eax
0x180007449  lock add cs:?sm_cTotalApplications@APPLICATION@@2JA, r14d; long APPLICATION::sm_cTotalApplications
0x180007451  lea     rax, [rdi+18h]
0x180007455  lea     rcx, [rsi+40h]
0x180007459  mov     [rax+8], rax
0x18000745d  mov     [rax], rax
0x180007460  mov     rdx, [rcx]
0x180007463  cmp     [rdx+8], rcx
0x180007467  jnz     loc_1800075A0
0x18000746d  lea     rax, [rdi+18h]
0x180007471  mov     [rax], rdx
0x180007474  mov     [rax+8], rcx
0x180007478  mov     [rdx+8], rax
0x18000747c  mov     [rcx], rax
0x18000747f  add     [rsi+3Ch], r14d
0x180007483  lock add [rdi+9Ch], r14d
0x18000748b  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000748f  call    cs:__imp_LeaveCriticalSection
0x180007495  mov     eax, [rsi+148h]
0x18000749b  lea     rcx, [rsi+150h]
0x1800074a2  mov     r9, [rsi+0F8h]
0x1800074a9  mov     rdx, rsi
0x1800074ac  mov     r8, [rsi+0C0h]
0x1800074b3  mov     [rsp+0C8h+var_40], eax
0x1800074ba  mov     eax, [rsi+204h]
0x1800074c0  mov     [rsp+0C8h+var_48], r13
0x1800074c8  mov     [rsp+0C8h+var_50], eax
0x1800074cc  mov     eax, [rsi+200h]
0x1800074d2  mov     [rsp+0C8h+var_58], eax
0x1800074d6  mov     eax, [rsi+1F8h]
0x1800074dc  mov     [rsp+0C8h+var_60], eax
0x1800074e0  mov     eax, [rsi+1F4h]
0x1800074e6  mov     [rsp+0C8h+var_68], eax
0x1800074ea  mov     eax, [rsi+1D4h]
0x1800074f0  mov     [rsp+0C8h+var_70], eax
0x1800074f4  mov     eax, [rsi+1D0h]
0x1800074fa  mov     [rsp+0C8h+var_78], eax
0x1800074fe  mov     eax, [rsi+1CCh]
0x180007504  mov     [rsp+0C8h+var_80], eax
0x180007508  mov     eax, [rsi+1C8h]
0x18000750e  mov     [rsp+0C8h+var_88], eax
0x180007512  mov     eax, [rsi+1C4h]
0x180007518  mov     [rsp+0C8h+var_90], eax
0x18000751c  mov     eax, [rsi+1C0h]
0x180007522  mov     [rsp+0C8h+var_98], eax
0x180007526  mov     rax, [rsi+1A8h]
0x18000752d  mov     [rsp+0C8h+var_A0], rax
0x180007532  mov     qword ptr [rsp+0C8h+var_A8], rcx
0x180007537  mov     rcx, rdi
0x18000753a  call    ?Init@APPLICATION@@QEAAJPEAVAPPLICATION_MANAGER@@PEBG1PEAVMULTISZ@@1HKKKKKHHKKPEAIW4FastCgiApplicationStdErrMode@@@Z; APPLICATION::Init(APPLICATION_MANAGER *,ushort const *,ushort const *,MULTISZ *,ushort const *,int,ulong,ulong,ulong,ulong,ulong,int,int,ulong,ulong,uint *,FastCgiApplicationStdErrMode)
0x18000753f  mov     ebp, eax
0x180007541  test    eax, eax
0x180007543  js      short loc_18000754F
0x180007545  mov     rcx, rdi; this
0x180007548  call    ?BeginRequest@APPLICATION@@QEAAJXZ; APPLICATION::BeginRequest(void)
0x18000754d  mov     ebp, eax
0x18000754f  lea     rcx, [rsi+10h]; lpCriticalSection
0x180007553  call    cs:__imp_EnterCriticalSection
0x180007559  xor     ebx, ebx
0x18000755b  test    ebp, ebp
0x18000755d  jns     short loc_180007584
0x18000755f  xor     r9d, r9d; int
0x180007562  mov     [rsp+0C8h+var_A8], r14d; int
0x180007567  xor     r8d, r8d; unsigned int
0x18000756a  mov     edx, ebp; int
0x18000756c  mov     rcx, rdi; this
0x18000756f  call    ?RealShutdown@APPLICATION@@QEAAXJIHH@Z; APPLICATION::RealShutdown(long,uint,int,int)
0x180007574  mov     rcx, rdi; this
0x180007577  call    ?DereferenceApplication@APPLICATION@@QEAAXXZ; APPLICATION::DereferenceApplication(void)
0x18000757c  jmp     short loc_1800075CC
0x18000757e  mov     r14d, 1
0x180007584  cmp     [r15], ebx
0x180007587  jnz     short loc_1800075CC
0x180007589  cmp     dword ptr [rdi+30h], 3
0x18000758d  jz      short loc_180007593
0x18000758f  mov     [rdi+30h], r14d
0x180007593  mov     rax, [rsp+0C8h+arg_8]
0x18000759b  mov     [rax], rdi
0x18000759e  jmp     short loc_1800075CC
0x1800075a0  mov     ecx, 3
0x1800075a5  int     29h; Win8: RtlFailFast(ecx)
0x1800075a7  or      eax, 0FFFFFFFFh
0x1800075aa  lock xadd [rsi+8Ch], eax
0x1800075b2  cmp     eax, r14d
0x1800075b5  jnz     short loc_1800075C7
0x1800075b7  mov     rcx, rsi; this
0x1800075ba  call    ??1APPLICATION_MANAGER@@AEAA@XZ; APPLICATION_MANAGER::~APPLICATION_MANAGER(void)
0x1800075bf  mov     rcx, rsi; Block
0x1800075c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800075c7  mov     ebp, 8007000Eh
0x1800075cc  mov     rbx, [rsp+0C8h+arg_0]
0x1800075d4  mov     eax, ebp
0x1800075d6  add     rsp, 90h
0x1800075dd  pop     r15
0x1800075df  pop     r14
0x1800075e1  pop     r13
0x1800075e3  pop     r12
0x1800075e5  pop     rdi
0x1800075e6  pop     rsi
0x1800075e7  pop     rbp
0x1800075e8  retn
```
