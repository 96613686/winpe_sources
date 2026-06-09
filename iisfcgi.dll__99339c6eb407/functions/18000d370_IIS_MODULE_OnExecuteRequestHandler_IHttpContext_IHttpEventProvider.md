# IIS_MODULE::OnExecuteRequestHandler(IHttpContext *,IHttpEventProvider *)

- ea: `0x18000d370`
- end: `0x18000d69c`
- name: `?OnExecuteRequestHandler@IIS_MODULE@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `812`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180001048`
- `0x180007090`
- `0x18000794c`
- `0x180009d74`
- `0x18000bb5c`
- `0x18000bd94`
- `0x18000d370`
- `0x18000edde`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000d550`
- `msvcrt!wcsstr` at `0x18000d550`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d447`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d447`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d480`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d639`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d480`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d639`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d409`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d428`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d409`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d428`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d4e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d4eb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d4e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d4eb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d587`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d587`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000d56f`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000d56f`

## pseudocode

```c
__int64 __fastcall IIS_MODULE::OnExecuteRequestHandler(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // r13
  unsigned int v9; // r14d
  unsigned __int64 v10; // rsi
  const wchar_t *v11; // rbx
  int ApplicationManager; // ebx
  APPLICATION_MANAGER *v13; // rdi
  unsigned int v15; // eax
  wchar_t *v16; // rax
  const unsigned __int16 *v17; // rdx
  STRU *v18; // rcx
  wchar_t *v19; // rdi
  unsigned __int16 *v20; // rdx
  int Application; // eax
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v24; // [rsp+38h] [rbp-C8h] BYREF
  int v25; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  struct IAppHostConfigException *v28; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[32]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v30; // [rsp+78h] [rbp-88h]
  _BYTE v31[32]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v32; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v33[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v34[64]; // [rsp+150h] [rbp+50h] BYREF

  v4 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 192))(a2);
  v5 = *a2;
  v6 = v4;
  v25 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *))(v5 + 32))(a2);
  Block = 0;
  v23 = 0;
  v28 = 0;
  v8 = v7;
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v29, v33, 0x40u);
  memset_0(v34, 0, sizeof(v34));
  STRU::STRU((STRU *)v31, v34, 0x40u);
  v26 = 0;
  v9 = 0;
  v24 = 0;
  v22 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v10 = a1 - 32;
  *(_QWORD *)(a1 - 32 + 168) = a2;
  v11 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 24LL))(v6, &v25);
  if ( !v11 )
  {
    ApplicationManager = -2147024882;
LABEL_3:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    goto LABEL_4;
  }
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 72LL))(v6);
  *(_DWORD *)(a1 + 200) = v15;
  if ( v15 > 0x1000000 )
    *(_DWORD *)(a1 + 200) = 0x1000000;
  v16 = wcsstr(v11, L"|");
  v17 = v11;
  v18 = (STRU *)v29;
  v19 = v16;
  if ( v16 )
  {
    ApplicationManager = STRU::Copy((STRU *)v29, v11, v16 - v11);
    if ( ApplicationManager < 0 )
      goto LABEL_3;
    v17 = v19 + 1;
    v18 = (STRU *)v31;
  }
  ApplicationManager = STRU::Copy(v18, v17);
  if ( ApplicationManager < 0 )
    goto LABEL_3;
  ApplicationManager = IIS_CONFIG::GetApplicationManager(
                         IIS_FACTORY::sm_pConfig,
                         v30,
                         v32,
                         (struct APPLICATION_MANAGER **)&Block,
                         &v28,
                         &v23);
  if ( ApplicationManager < 0 )
  {
    if ( !v23 && !v28 )
    {
      if ( (int)IIS_MODULE::GetString((IIS_MODULE *)(a1 - 32), 0x3102Eu, (const unsigned __int16 **)&v26, &v24) >= 0 )
      {
        v20 = v26;
      }
      else
      {
        v20 = 0;
        v26 = 0;
      }
      if ( v20 )
        (*(void (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v8 + 192LL))(v8, v20, v24, 1);
    }
    goto LABEL_3;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 64LL))(a1 - 32);
  Application = APPLICATION_MANAGER::GetApplication(
                  (APPLICATION_MANAGER *)Block,
                  (struct IAPPLICATION_MANAGER_CALLBACK *)((a1 - 24) & ((unsigned __int128)-(__int128)v10 >> 64)),
                  &v22);
  v9 = v22;
  ApplicationManager = Application;
  if ( Application < 0 )
  {
    if ( !v22 )
      v9 = 200005;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 48LL))(a1 - 32);
  }
LABEL_4:
  v13 = (APPLICATION_MANAGER *)Block;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 35, 0xFFFFFFFF) == 1 && v13 )
  {
    APPLICATION_MANAGER::~APPLICATION_MANAGER(v13);
    operator delete(v13);
  }
  if ( ApplicationManager < 0 )
    IIS_MODULE::EndResponse((IIS_MODULE *)(a1 - 32), 0, ApplicationManager, v9, v28, 0);
  STRU::~STRU((STRU *)v31);
  STRU::~STRU((STRU *)v29);
  return 1;
}

```

## disassembly

```asm
0x18000d370  mov     [rsp-8+arg_10], rbx
0x18000d375  push    rbp
0x18000d376  push    rsi
0x18000d377  push    rdi
0x18000d378  push    r12
0x18000d37a  push    r13
0x18000d37c  push    r14
0x18000d37e  push    r15
0x18000d380  lea     rbp, [rsp-0E0h]
0x18000d388  sub     rsp, 1E0h
0x18000d38f  mov     rax, cs:__security_cookie
0x18000d396  xor     rax, rsp
0x18000d399  mov     [rbp+110h+var_40], rax
0x18000d3a0  mov     rax, [rdx]
0x18000d3a3  mov     r15, rcx
0x18000d3a6  mov     rcx, rdx
0x18000d3a9  mov     rbx, rdx
0x18000d3ac  mov     rax, [rax+0C0h]
0x18000d3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3b8  mov     rcx, [rbx]
0x18000d3bb  mov     rdi, rax
0x18000d3be  xor     r12d, r12d
0x18000d3c1  mov     [rsp+210h+var_1D4], r12d
0x18000d3c6  mov     rax, [rcx+20h]
0x18000d3ca  mov     rcx, rbx
0x18000d3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d2  mov     r14d, 80h
0x18000d3d8  mov     [rsp+210h+Block], r12
0x18000d3dd  mov     r8d, r14d; Size
0x18000d3e0  mov     [rsp+210h+var_1DC], r12d
0x18000d3e5  xor     edx, edx; Val
0x18000d3e7  mov     [rsp+210h+var_1C0], r12
0x18000d3ec  lea     rcx, [rbp+110h+var_140]; void *
0x18000d3f0  mov     r13, rax
0x18000d3f3  call    memset_0
0x18000d3f8  lea     esi, [r12+40h]
0x18000d3fd  mov     r8d, esi
0x18000d400  lea     rdx, [rbp+110h+var_140]
0x18000d404  lea     rcx, [rsp+210h+var_1B8]
0x18000d409  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d40f  mov     r8d, r14d; Size
0x18000d412  lea     rcx, [rbp+110h+var_C0]; void *
0x18000d416  xor     edx, edx; Val
0x18000d418  call    memset_0
0x18000d41d  mov     r8d, esi
0x18000d420  lea     rdx, [rbp+110h+var_C0]
0x18000d424  lea     rcx, [rbp+110h+var_180]
0x18000d428  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d42e  mov     [rsp+210h+var_1D0], r12
0x18000d433  mov     r14d, r12d
0x18000d436  mov     [rsp+210h+var_1D8], r12d
0x18000d43b  mov     [rsp+210h+var_1E0], r12d
0x18000d440  lea     r12, [r15+10h]
0x18000d444  mov     rcx, r12; lpCriticalSection
0x18000d447  call    cs:__imp_EnterCriticalSection
0x18000d44d  lea     rsi, [r15-20h]
0x18000d451  mov     rcx, rdi
0x18000d454  mov     [rsi+0A8h], rbx
0x18000d45b  lea     rdx, [rsp+210h+var_1D4]
0x18000d460  mov     rax, [rdi]
0x18000d463  mov     rax, [rax+18h]
0x18000d467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d46c  mov     rbx, rax
0x18000d46f  test    rax, rax
0x18000d472  jnz     loc_18000D520
0x18000d478  mov     ebx, 8007000Eh
0x18000d47d  mov     rcx, r12; lpCriticalSection
0x18000d480  call    cs:__imp_LeaveCriticalSection
0x18000d486  mov     rdi, [rsp+210h+Block]
0x18000d48b  test    rdi, rdi
0x18000d48e  jz      short loc_18000D4B5
0x18000d490  or      eax, 0FFFFFFFFh
0x18000d493  lock xadd [rdi+8Ch], eax
0x18000d49b  cmp     eax, 1
0x18000d49e  jnz     short loc_18000D4B5
0x18000d4a0  test    rdi, rdi
0x18000d4a3  jz      short loc_18000D4B5
0x18000d4a5  mov     rcx, rdi; this
0x18000d4a8  call    ??1APPLICATION_MANAGER@@AEAA@XZ; APPLICATION_MANAGER::~APPLICATION_MANAGER(void)
0x18000d4ad  mov     rcx, rdi; Block
0x18000d4b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d4b5  test    ebx, ebx
0x18000d4b7  jns     short loc_18000D4DC
0x18000d4b9  mov     rdx, [rsp+210h+var_1C0]
0x18000d4be  mov     r9d, r14d; unsigned int
0x18000d4c1  mov     [rsp+210h+var_1E8], 0; unsigned __int16 *
0x18000d4ca  mov     r8d, ebx; int
0x18000d4cd  mov     [rsp+210h+var_1F0], rdx; struct IAppHostConfigException *
0x18000d4d2  mov     rcx, rsi; this
0x18000d4d5  xor     edx, edx; int
0x18000d4d7  call    ?EndResponse@IIS_MODULE@@AEAAXHJIPEAUIAppHostConfigException@@PEBG@Z; IIS_MODULE::EndResponse(int,long,uint,IAppHostConfigException *,ushort const *)
0x18000d4dc  lea     rcx, [rbp+110h+var_180]
0x18000d4e0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d4e6  lea     rcx, [rsp+210h+var_1B8]
0x18000d4eb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d4f1  mov     eax, 1
0x18000d4f6  mov     rcx, [rbp+110h+var_40]
0x18000d4fd  xor     rcx, rsp; StackCookie
0x18000d500  call    __security_check_cookie
0x18000d505  mov     rbx, [rsp+210h+arg_10]
0x18000d50d  add     rsp, 1E0h
0x18000d514  pop     r15
0x18000d516  pop     r14
0x18000d518  pop     r13
0x18000d51a  pop     r12
0x18000d51c  pop     rdi
0x18000d51d  pop     rsi
0x18000d51e  pop     rbp
0x18000d51f  retn
0x18000d520  mov     rax, [rdi]
0x18000d523  mov     rcx, rdi
0x18000d526  mov     rax, [rax+48h]
0x18000d52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d52f  mov     ecx, 1000000h
0x18000d534  mov     [r15+0C8h], eax
0x18000d53b  cmp     eax, ecx
0x18000d53d  jbe     short loc_18000D546
0x18000d53f  mov     [r15+0C8h], ecx
0x18000d546  lea     rdx, SubStr; "|"
0x18000d54d  mov     rcx, rbx; Str
0x18000d550  call    cs:__imp_wcsstr
0x18000d556  mov     rdx, rbx
0x18000d559  lea     rcx, [rsp+210h+var_1B8]
0x18000d55e  mov     rdi, rax
0x18000d561  test    rax, rax
0x18000d564  jz      short loc_18000D587
0x18000d566  mov     r8, rax
0x18000d569  sub     r8, rbx
0x18000d56c  sar     r8, 1
0x18000d56f  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000d575  mov     ebx, eax
0x18000d577  test    eax, eax
0x18000d579  js      loc_18000D47D
0x18000d57f  lea     rdx, [rdi+2]
0x18000d583  lea     rcx, [rbp+110h+var_180]
0x18000d587  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000d58d  mov     ebx, eax
0x18000d58f  test    eax, eax
0x18000d591  js      loc_18000D47D
0x18000d597  mov     r8, [rbp+110h+var_160]; unsigned __int16 *
0x18000d59b  lea     rax, [rsp+210h+var_1DC]
0x18000d5a0  mov     rdx, [rsp+210h+var_198]; unsigned __int16 *
0x18000d5a5  lea     r9, [rsp+210h+Block]; struct APPLICATION_MANAGER **
0x18000d5aa  mov     rcx, cs:?sm_pConfig@IIS_FACTORY@@0PEAVIIS_CONFIG@@EA; this
0x18000d5b1  mov     [rsp+210h+var_1E8], rax; int *
0x18000d5b6  lea     rax, [rsp+210h+var_1C0]
0x18000d5bb  mov     [rsp+210h+var_1F0], rax; struct IAppHostConfigException **
0x18000d5c0  call    ?GetApplicationManager@IIS_CONFIG@@QEAAJPEBG0PEAPEAVAPPLICATION_MANAGER@@PEAPEAUIAppHostConfigException@@PEAH@Z; IIS_CONFIG::GetApplicationManager(ushort const *,ushort const *,APPLICATION_MANAGER * *,IAppHostConfigException * *,int *)
0x18000d5c5  mov     ebx, eax
0x18000d5c7  test    eax, eax
0x18000d5c9  jns     short loc_18000D636
0x18000d5cb  cmp     [rsp+210h+var_1DC], r14d
0x18000d5d0  jnz     loc_18000D47D
0x18000d5d6  cmp     [rsp+210h+var_1C0], r14
0x18000d5db  jnz     loc_18000D47D
0x18000d5e1  lea     r9, [rsp+210h+var_1D8]; unsigned int *
0x18000d5e6  mov     edx, 3102Eh; unsigned int
0x18000d5eb  lea     r8, [rsp+210h+var_1D0]; unsigned __int16 **
0x18000d5f0  mov     rcx, rsi; this
0x18000d5f3  call    ?GetString@IIS_MODULE@@AEAAJIPEAPEBGPEAK@Z; IIS_MODULE::GetString(uint,ushort const * *,ulong *)
0x18000d5f8  test    eax, eax
0x18000d5fa  jns     short loc_18000D605
0x18000d5fc  xor     edx, edx
0x18000d5fe  mov     [rsp+210h+var_1D0], rdx
0x18000d603  jmp     short loc_18000D60A
0x18000d605  mov     rdx, [rsp+210h+var_1D0]
0x18000d60a  test    rdx, rdx
0x18000d60d  jz      loc_18000D47D
0x18000d613  mov     rax, [r13+0]
0x18000d617  mov     r9d, 1
0x18000d61d  mov     r8d, [rsp+210h+var_1D8]
0x18000d622  mov     rcx, r13
0x18000d625  mov     rax, [rax+0C0h]
0x18000d62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d631  jmp     loc_18000D47D
0x18000d636  mov     rcx, r12; lpCriticalSection
0x18000d639  call    cs:__imp_LeaveCriticalSection
0x18000d63f  mov     rax, [rsi]
0x18000d642  mov     rcx, rsi
0x18000d645  mov     rax, [rax+40h]
0x18000d649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d64e  lea     rcx, [r15-18h]
0x18000d652  mov     rax, rsi
0x18000d655  neg     rax
0x18000d658  lea     r8, [rsp+210h+var_1E0]; unsigned int *
0x18000d65d  sbb     rdx, rdx
0x18000d660  and     rdx, rcx; struct IAPPLICATION_MANAGER_CALLBACK *
0x18000d663  mov     rcx, [rsp+210h+Block]; this
0x18000d668  call    ?GetApplication@APPLICATION_MANAGER@@QEAAJPEAVIAPPLICATION_MANAGER_CALLBACK@@PEAI@Z; APPLICATION_MANAGER::GetApplication(IAPPLICATION_MANAGER_CALLBACK *,uint *)
0x18000d66d  mov     r14d, [rsp+210h+var_1E0]
0x18000d672  mov     ebx, eax
0x18000d674  test    eax, eax
0x18000d676  jns     loc_18000D486
0x18000d67c  test    r14d, r14d
0x18000d67f  mov     eax, 30D45h
0x18000d684  mov     rcx, rsi
0x18000d687  cmovz   r14d, eax
0x18000d68b  mov     rax, [rsi]
0x18000d68e  mov     rax, [rax+30h]
0x18000d692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d697  jmp     loc_18000D486
```
