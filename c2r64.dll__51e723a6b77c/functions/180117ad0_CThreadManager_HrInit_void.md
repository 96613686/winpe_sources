# CThreadManager::HrInit(void)

- ea: `0x180117ad0`
- end: `0x180117f07`
- name: `?HrInit@CThreadManager@@IEAAJXZ`
- size: `1079`
- prototype: `__int64 __fastcall(CThreadManager *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180115b14`

## callees

- `0x180005540`
- `0x1800264b4`
- `0x180026664`
- `0x18003981c`
- `0x180039b20`
- `0x180052cd0`
- `0x180052d34`
- `0x1800723a8`
- `0x1801069a0`
- `0x180107874`
- `0x18010cdc0`
- `0x18010cf88`
- `0x18010e438`
- `0x180117ad0`
- `0x1801183b4`
- `0x180146090`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x180117c6a`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180117c6a`
- `KERNEL32!FlsAlloc` at `0x180117b3c`
- `KERNEL32!FlsAlloc` at `0x180117b5d`
- `KERNEL32!FlsAlloc` at `0x180117b3c`
- `KERNEL32!FlsAlloc` at `0x180117b5d`
- `KERNEL32!CreateEventExW` at `0x180117c99`
- `KERNEL32!CreateEventExW` at `0x180117c99`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThreadManager::HrInit(CThreadManager *this)
{
  struct ITpNodeAllocator *v2; // rdi
  struct CFreeResList **v3; // rsi
  DWORD v4; // eax
  DWORD v5; // eax
  unsigned __int64 v6; // rdx
  unsigned int v7; // r8d
  struct ITpNodeAllocator *v8; // rax
  int v9; // ecx
  int v10; // eax
  void **v11; // rdx
  int Instance; // eax
  char *v13; // rax
  char *v14; // rdi
  HANDLE Event; // rax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  const struct Mso::Memory::NoThrow::MarkingLeak_t *v19; // rdx
  _QWORD *v20; // rax
  const struct Mso::Memory::NoThrow::MarkingLeak_t *v21; // rdx
  Mso::Threadpool::CTpIdleManager *v22; // rax
  struct CThreadManager *v23; // rdx
  Mso::Threadpool::CTpIdleManager *v24; // rax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  unsigned __int64 v28; // rdx
  unsigned int v29; // r8d
  CTpTimerManagerLegacy *v30; // rax
  CTpTimerManagerLegacy *v31; // rcx
  int v32; // eax
  const struct Mso::Memory::NoThrow::MarkingLeak_t *v33; // rdx
  CPowerManager *v34; // rax
  CPowerManager *v35; // rax
  void *v37; // [rsp+40h] [rbp+8h] BYREF
  struct ITpNodeAllocator *v38; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v38 = 0;
  if ( !*((_QWORD *)this + 7) )
    CrashWithRecoveryOnOOM(0x1E40B09Bu);
  if ( !*((_QWORD *)this + 8) )
    CrashWithRecoveryOnOOM(0x1E40B09Au);
  v3 = (struct CFreeResList **)((char *)this + 16);
  if ( *((_QWORD *)this + 2) )
    CrashWithRecovery(0x1E40B099u, 0);
  if ( *((_DWORD *)this + 13) )
    CrashWithRecovery(0x1E40B098u, 0);
  v4 = FlsAlloc(0);
  *((_DWORD *)this + 10) = v4;
  if ( v4 == -1 )
    CrashWithRecovery(0x1E40B097u, 0);
  if ( !v4 )
  {
    v5 = FlsAlloc(0);
    *((_DWORD *)this + 10) = v5;
    if ( !v5 )
      CrashWithRecovery(0x1E40B096u, 0);
  }
  v37 = 0;
  CSingletonBase::HrGetInstance((CSingletonBase *)&CSingleton<ITpNodeAllocator>::m_gSingleton, &v37, 1);
  v8 = (struct ITpNodeAllocator *)v37;
  if ( v37
    || ((v8 = (struct ITpNodeAllocator *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x18, v6, v7)) == 0
      ? (v8 = 0)
      : (struct ITpNodeAllocator *)(*(_QWORD *)v8 = &CSimpleNodeAllocator::`vftable',
                                    *((_QWORD *)v8 + 1) = 32,
                                    *((_DWORD *)v8 + 4) = 1),
        v8) )
  {
    v2 = v8;
    v38 = v8;
    v9 = 0;
  }
  else
  {
    v9 = -2147024882;
  }
  if ( v9 < 0 )
  {
    _mm_lfence();
    CrashWithRecoveryHrTag(v9, 0x1E40B095u);
  }
  v10 = CFreeResList::HrCreate(0x40u, 0x100u, v2, v3);
  if ( v10 < 0 )
  {
    _mm_lfence();
    CrashWithRecoveryHrTag(v10, 0x1E40B094u);
  }
  v11 = (void **)((char *)this + 80);
  if ( !*((_QWORD *)this + 10) )
  {
    _mm_lfence();
    Instance = CSingletonBase::HrGetInstance((CSingletonBase *)&CSingleton<IEventPool>::m_gSingleton, v11, 1);
    if ( Instance < 0 )
    {
      _mm_lfence();
      CrashWithRecoveryHrTag(Instance, 0x1E40B093u);
    }
  }
  v13 = (char *)operator new(0x30u, (const struct Mso::Memory::NoThrow::MarkingLeak_t *)v11);
  v14 = v13;
  if ( v13 )
  {
    *(_QWORD *)v13 = 0;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v13 + 8), 0, 0);
  }
  else
  {
    v14 = 0;
  }
  *((_QWORD *)this + 22) = v14;
  if ( !v14 )
    CrashWithRecoveryOnOOM(0x1E40B092u);
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  *((_QWORD *)this + 24) = Event;
  if ( !Event )
    CrashWithRecovery(0x1E40B091u, 0);
  _mm_lfence();
  v16 = CTpQueue::HrInit((CThreadManager *)((char *)this + 208), 0);
  _mm_lfence();
  if ( v16 < 0 )
    CrashWithRecoveryHrTag(v16, 0x1E40B090u);
  v17 = CTpQueue::HrInit((CThreadManager *)((char *)this + 336), 0);
  _mm_lfence();
  if ( v17 < 0 )
    CrashWithRecoveryHrTag(v17, 0x1E40B08Fu);
  v18 = (*(__int64 (__fastcall **)(_QWORD, CThreadManager *))(**((_QWORD **)this + 8) + 8LL))(
          *((_QWORD *)this + 8),
          this);
  if ( v18 < 0 )
  {
    _mm_lfence();
    CrashWithRecoveryHrTag(v18, 0x1E40B08Eu);
  }
  v20 = operator new(0x48u, v19);
  if ( v20 )
  {
    v20[6] = 1;
    *((_DWORD *)v20 + 8) = 1;
    *v20 = 0;
    v20[1] = 0;
    v20[2] = 0;
    v20[5] = 0;
    *((_DWORD *)v20 + 14) = 0;
    *((_DWORD *)v20 + 16) = 1;
  }
  else
  {
    v20 = 0;
  }
  *((_QWORD *)this + 9) = v20;
  if ( !v20 )
    CrashWithRecoveryOnOOM(0x1E40B08Du);
  v22 = (Mso::Threadpool::CTpIdleManager *)operator new(0x160u, v21);
  if ( v22 )
  {
    _mm_lfence();
    v24 = (Mso::Threadpool::CTpIdleManager *)Mso::Threadpool::CTpIdleManager::CTpIdleManager(
                                               v22,
                                               v23,
                                               *((struct CMainThreadState **)this + 9));
  }
  else
  {
    v24 = 0;
  }
  *((_QWORD *)this + 25) = v24;
  if ( !v24 )
    CrashWithRecoveryOnOOM(0x1E40B08Cu);
  _mm_lfence();
  v25 = Mso::Threadpool::CTpIdleManager::HrInit(v24, this);
  _mm_lfence();
  if ( v25 < 0 )
    CrashWithRecoveryHrTag(v25, 0x1E40B08Bu);
  v26 = (*(__int64 (__fastcall **)(_QWORD, CThreadManager *, struct CFreeResList *))(**((_QWORD **)this + 7) + 8LL))(
          *((_QWORD *)this + 7),
          this,
          *v3);
  _mm_lfence();
  if ( v26 < 0 )
    CrashWithRecoveryHrTag(v26, 0x1E40B08Au);
  v27 = CTpQueue::HrInit((CThreadManager *)((char *)this + 464), *v3);
  if ( v27 < 0 )
  {
    _mm_lfence();
    CrashWithRecoveryHrTag(v27, 0x1E40B089u);
  }
  v30 = (CTpTimerManagerLegacy *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0xC8, v28, v29);
  if ( v30 )
  {
    _mm_lfence();
    v31 = CTpTimerManagerLegacy::CTpTimerManagerLegacy(v30, this);
  }
  else
  {
    v31 = 0;
  }
  *((_QWORD *)this + 3) = v31;
  if ( !v31 )
    CrashWithRecoveryOnOOM(0x1E40B087u);
  _mm_lfence();
  v32 = (*(__int64 (__fastcall **)(CTpTimerManagerLegacy *))(*(_QWORD *)v31 + 40LL))(v31);
  if ( v32 < 0 )
  {
    _mm_lfence();
    CrashWithRecoveryHrTag(v32, 0x1E40B086u);
  }
  v34 = (CPowerManager *)operator new(0x320u, v33);
  if ( v34 )
  {
    _mm_lfence();
    v35 = CPowerManager::CPowerManager(v34, this);
  }
  else
  {
    v35 = 0;
  }
  *((_QWORD *)this + 4) = v35;
  if ( !v35 )
    CrashWithRecoveryOnOOM(0x1E40B084u);
  *((_QWORD *)this + 74) = 0;
  if ( *((_QWORD *)this + 19) != *((_QWORD *)this + 18)
    || (_mm_lfence(), (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 32LL))(*((_QWORD *)this + 7))) )
  {
    MsoShipAssertTagProc(507555971);
  }
  SafeRelease<CTpWorkObject>(&v38);
  return 0;
}

```

## disassembly

```asm
0x180117ad0  mov     [rsp+arg_10], rbx
0x180117ad5  mov     [rsp+arg_18], rbp
0x180117ada  push    rsi
0x180117adb  push    rdi
0x180117adc  push    r14
0x180117ade  sub     rsp, 20h
0x180117ae2  mov     rbx, rcx
0x180117ae5  xor     ebp, ebp
0x180117ae7  mov     edi, ebp
0x180117ae9  mov     [rsp+38h+arg_8], rbp
0x180117aee  cmp     [rcx+38h], rbp
0x180117af2  jnz     short loc_180117AFF
0x180117af4  mov     ecx, 1E40B09Bh; unsigned int
0x180117af9  call    ?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180117aff  cmp     [rcx+40h], rbp
0x180117b03  jnz     short loc_180117B10
0x180117b05  mov     ecx, 1E40B09Ah; unsigned int
0x180117b0a  call    ?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180117b10  lea     rsi, [rcx+10h]
0x180117b14  cmp     [rsi], rbp
0x180117b17  jz      short loc_180117B26
0x180117b19  xor     edx, edx; struct CrashContext *
0x180117b1b  mov     ecx, 1E40B099h; unsigned int
0x180117b20  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180117b26  mov     eax, [rcx+34h]
0x180117b29  test    eax, eax
0x180117b2b  jz      short loc_180117B3A
0x180117b2d  xor     edx, edx; struct CrashContext *
0x180117b2f  mov     ecx, 1E40B098h; unsigned int
0x180117b34  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180117b3a  xor     ecx, ecx; lpCallback
0x180117b3c  call    cs:__imp_FlsAlloc
0x180117b42  mov     [rbx+28h], eax
0x180117b45  cmp     eax, 0FFFFFFFFh
0x180117b48  jnz     short loc_180117B57
0x180117b4a  xor     edx, edx; struct CrashContext *
0x180117b4c  mov     ecx, 1E40B097h; unsigned int
0x180117b51  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180117b57  test    eax, eax
0x180117b59  jnz     short loc_180117B7B
0x180117b5b  xor     ecx, ecx; lpCallback
0x180117b5d  call    cs:__imp_FlsAlloc
0x180117b63  mov     [rbx+28h], eax
0x180117b66  test    eax, eax
0x180117b68  jnz     short loc_180117B7B
0x180117b6a  xor     edx, edx; struct CrashContext *
0x180117b6c  mov     ecx, 1E40B096h; unsigned int
0x180117b71  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180117b77  jmp     short loc_180117B7A
0x180117b7a  nop
0x180117b7b  mov     [rsp+38h+arg_0], rbp
0x180117b80  mov     r14d, 1
0x180117b86  mov     r8b, r14b; bool
0x180117b89  lea     rdx, [rsp+38h+arg_0]; void **
0x180117b8e  lea     rcx, ?m_gSingleton@?$CSingleton@UITpNodeAllocator@@@@2V1@A; this
0x180117b95  call    ?HrGetInstance@CSingletonBase@@IEAAJPEAPEAX_N@Z; CSingletonBase::HrGetInstance(void * *,bool)
0x180117b9a  mov     rax, [rsp+38h+arg_0]
0x180117b9f  test    rax, rax
0x180117ba2  jnz     short loc_180117BD8
0x180117ba4  lea     ecx, [rax+18h]; this
0x180117ba7  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180117bac  test    rax, rax
0x180117baf  jz      short loc_180117BC9
0x180117bb1  lea     rcx, ??_7CSimpleNodeAllocator@@6B@; const CSimpleNodeAllocator::`vftable'
0x180117bb8  mov     [rax], rcx
0x180117bbb  mov     qword ptr [rax+8], 20h ; ' '
0x180117bc3  mov     [rax+10h], r14d
0x180117bc7  jmp     short loc_180117BCC
0x180117bc9  mov     rax, rbp
0x180117bcc  test    rax, rax
0x180117bcf  jnz     short loc_180117BD8
0x180117bd1  mov     ecx, 8007000Eh
0x180117bd6  jmp     short loc_180117BE2
0x180117bd8  mov     rdi, rax
0x180117bdb  mov     [rsp+38h+arg_8], rax
0x180117be0  mov     ecx, ebp; int
0x180117be2  test    ecx, ecx
0x180117be4  jns     short loc_180117BF4
0x180117be6  lfence
0x180117be9  mov     edx, 1E40B095h; unsigned int
0x180117bee  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180117bf4  mov     r9, rsi; struct CFreeResList **
0x180117bf7  mov     r8, rdi; struct ITpNodeAllocator *
0x180117bfa  mov     edx, 100h; unsigned __int64
0x180117bff  mov     ecx, 40h ; '@'; unsigned __int64
0x180117c04  call    ?HrCreate@CFreeResList@@SAJ_K0PEAUITpNodeAllocator@@PEAPEAV1@@Z; CFreeResList::HrCreate(unsigned __int64,unsigned __int64,ITpNodeAllocator *,CFreeResList * *)
0x180117c09  test    eax, eax
0x180117c0b  jns     short loc_180117C1D
0x180117c0d  lfence
0x180117c10  mov     edx, 1E40B094h; unsigned int
0x180117c15  mov     ecx, eax; int
0x180117c17  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180117c1d  lea     rdx, [rbx+50h]; struct Mso::Memory::NoThrow::MarkingLeak_t *
0x180117c21  cmp     [rdx], rbp
0x180117c24  jnz     short loc_180117C4C
0x180117c26  lfence
0x180117c29  mov     r8b, r14b; bool
0x180117c2c  lea     rcx, ?m_gSingleton@?$CSingleton@UIEventPool@@@@2V1@A; this
0x180117c33  call    ?HrGetInstance@CSingletonBase@@IEAAJPEAPEAX_N@Z; CSingletonBase::HrGetInstance(void * *,bool)
0x180117c38  test    eax, eax
0x180117c3a  jns     short loc_180117C4C
0x180117c3c  lfence
0x180117c3f  mov     edx, 1E40B093h; unsigned int
0x180117c44  mov     ecx, eax; int
0x180117c46  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180117c4c  mov     ecx, 30h ; '0'; unsigned __int64
0x180117c51  call    ??2@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z; operator new(unsigned __int64,Mso::Memory::NoThrow::MarkingLeak_t const &)
0x180117c56  mov     rdi, rax
0x180117c59  test    rax, rax
0x180117c5c  jz      short loc_180117C72
0x180117c5e  mov     [rax], rbp
0x180117c61  lea     rcx, [rax+8]; lpCriticalSection
0x180117c65  xor     r8d, r8d; Flags
0x180117c68  xor     edx, edx; dwSpinCount
0x180117c6a  call    cs:__imp_InitializeCriticalSectionEx
0x180117c70  jmp     short loc_180117C75
0x180117c72  mov     rdi, rbp
0x180117c75  mov     [rbx+0B0h], rdi
0x180117c7c  test    rdi, rdi
0x180117c7f  jnz     short loc_180117C8C
0x180117c81  mov     ecx, 1E40B092h; unsigned int
0x180117c86  call    ?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180117c8c  mov     r9d, 1F0003h; dwDesiredAccess
0x180117c92  mov     r8d, r14d; dwFlags
0x180117c95  xor     edx, edx; lpName
0x180117c97  xor     ecx, ecx; lpEventAttributes
0x180117c99  call    cs:__imp_CreateEventExW
0x180117c9f  mov     [rbx+0C0h], rax
0x180117ca6  xor     edx, edx; struct CTpFreeList *
0x180117ca8  test    rax, rax
0x180117cab  jnz     short loc_180117CB8
0x180117cad  mov     ecx, 1E40B091h; unsigned int
0x180117cb2  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180117cb8  lfence
0x180117cbb  lea     rcx, [rbx+0D0h]; this
0x180117cc2  call    ?HrInit@CTpQueue@@QEAAJPEAVCTpFreeList@@@Z; CTpQueue::HrInit(CTpFreeList *)
0x180117cc7  lfence
0x180117cca  test    eax, eax
0x180117ccc  jns     short loc_180117CDB
0x180117cce  mov     edx, 1E40B090h; unsigned int
0x180117cd3  mov     ecx, eax; int
0x180117cd5  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180117cdb  lea     rcx, [rbx+150h]; this
0x180117ce2  xor     edx, edx; struct CTpFreeList *
0x180117ce4  call    ?HrInit@CTpQueue@@QEAAJPEAVCTpFreeList@@@Z; CTpQueue::HrInit(CTpFreeList *)
0x180117ce9  lfence
0x180117cec  test    eax, eax
0x180117cee  jns     short loc_180117CFD
0x180117cf0  mov     edx, 1E40B08Fh; unsigned int
0x180117cf5  mov     ecx, eax; int
0x180117cf7  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180117cfd  mov     rcx, [rbx+40h]
0x180117d01  mov     rax, [rcx]
0x180117d04  mov     rdx, rbx
0x180117d07  mov     rax, [rax+8]
0x180117d0b  call    cs:__guard_dispatch_icall_fptr
0x180117d11  test    eax, eax
0x180117d13  jns     short loc_180117D25
0x180117d15  lfence
0x180117d18  mov     edx, 1E40B08Eh; unsigned int
0x180117d1d  mov     ecx, eax; int
0x180117d1f  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180117d25  mov     ecx, 48h ; 'H'; unsigned __int64
0x180117d2a  call    ??2@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z; operator new(unsigned __int64,Mso::Memory::NoThrow::MarkingLeak_t const &)
0x180117d2f  test    rax, rax
0x180117d32  jz      short loc_180117D58
0x180117d34  mov     qword ptr [rax+30h], 1
0x180117d3c  mov     [rax+20h], r14d
0x180117d40  mov     [rax], rbp
0x180117d43  mov     [rax+8], rbp
0x180117d47  mov     [rax+10h], rbp
0x180117d4b  mov     [rax+28h], rbp
0x180117d4f  mov     [rax+38h], ebp
0x180117d52  mov     [rax+40h], r14d
0x180117d56  jmp     short loc_180117D5B
0x180117d58  mov     rax, rbp
0x180117d5b  mov     [rbx+48h], rax
0x180117d5f  test    rax, rax
0x180117d62  jnz     short loc_180117D6F
0x180117d64  mov     ecx, 1E40B08Dh; unsigned int
0x180117d69  call    ?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180117d6f  mov     ecx, 160h; unsigned __int64
0x180117d74  call    ??2@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z; operator new(unsigned __int64,Mso::Memory::NoThrow::MarkingLeak_t const &)
0x180117d79  test    rax, rax
0x180117d7c  jz      short loc_180117D8F
0x180117d7e  lfence
0x180117d81  mov     r8, [rbx+48h]; struct CMainThreadState *
0x180117d85  mov     rcx, rax; this
0x180117d88  call    ??0CTpIdleManager@Threadpool@Mso@@QEAA@PEAVCThreadManager@@PEAUCMainThreadState@@@Z; Mso::Threadpool::CTpIdleManager::CTpIdleManager(CThreadManager *,CMainThreadState *)
0x180117d8d  jmp     short loc_180117D92
0x180117d8f  mov     rax, rbp
0x180117d92  mov     [rbx+0C8h], rax
0x180117d99  test    rax, rax
0x180117d9c  jnz     short loc_180117DA9
0x180117d9e  mov     ecx, 1E40B08Ch; unsigned int
0x180117da3  call    ?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180117da9  lfence
0x180117dac  mov     rdx, rbx; struct CThreadManager *
0x180117daf  mov     rcx, rax; this
0x180117db2  call    ?HrInit@CTpIdleManager@Threadpool@Mso@@QEAAJPEAVCThreadManager@@@Z; Mso::Threadpool::CTpIdleManager::HrInit(CThreadManager *)
0x180117db7  lfence
0x180117dba  test    eax, eax
0x180117dbc  jns     short loc_180117DCB
0x180117dbe  mov     edx, 1E40B08Bh; unsigned int
0x180117dc3  mov     ecx, eax; int
0x180117dc5  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180117dcb  mov     rcx, [rbx+38h]
0x180117dcf  mov     rax, [rcx]
0x180117dd2  mov     r8, [rsi]
0x180117dd5  mov     rdx, rbx
0x180117dd8  mov     rax, [rax+8]
0x180117ddc  call    cs:__guard_dispatch_icall_fptr
0x180117de2  lfence
0x180117de5  test    eax, eax
0x180117de7  jns     short loc_180117DF6
0x180117de9  mov     edx, 1E40B08Ah; unsigned int
0x180117dee  mov     ecx, eax; int
0x180117df0  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180117df6  lea     rcx, [rbx+1D0h]; this
0x180117dfd  mov     rdx, [rsi]; struct CTpFreeList *
0x180117e00  call    ?HrInit@CTpQueue@@QEAAJPEAVCTpFreeList@@@Z; CTpQueue::HrInit(CTpFreeList *)
0x180117e05  test    eax, eax
0x180117e07  jns     short loc_180117E1C
0x180117e09  lfence
0x180117e0c  mov     edx, 1E40B089h; unsigned int
0x180117e11  mov     ecx, eax; int
0x180117e13  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180117e19  jmp     short $+2
0x180117e1b  nop
0x180117e1c  mov     ecx, 0C8h; this
0x180117e21  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180117e26  test    rax, rax
0x180117e29  jz      short loc_180117E3E
0x180117e2b  lfence
0x180117e2e  mov     rdx, rbx; struct CThreadManager *
0x180117e31  mov     rcx, rax; this
0x180117e34  call    ??0CTpTimerManagerLegacy@@QEAA@PEAVCThreadManager@@@Z; CTpTimerManagerLegacy::CTpTimerManagerLegacy(CThreadManager *)
0x180117e39  mov     rcx, rax
0x180117e3c  jmp     short loc_180117E41
0x180117e3e  mov     rcx, rbp
0x180117e41  mov     [rbx+18h], rcx
0x180117e45  test    rcx, rcx
0x180117e48  jnz     short loc_180117E55
0x180117e4a  mov     ecx, 1E40B087h; unsigned int
0x180117e4f  call    ?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180117e55  lfence
0x180117e58  mov     rax, [rcx]
0x180117e5b  mov     rax, [rax+28h]
0x180117e5f  call    cs:__guard_dispatch_icall_fptr
0x180117e65  test    eax, eax
0x180117e67  jns     short loc_180117E79
0x180117e69  lfence
0x180117e6c  mov     edx, 1E40B086h; unsigned int
0x180117e71  mov     ecx, eax; int
0x180117e73  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180117e79  mov     ecx, 320h; unsigned __int64
0x180117e7e  call    ??2@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z; operator new(unsigned __int64,Mso::Memory::NoThrow::MarkingLeak_t const &)
0x180117e83  test    rax, rax
0x180117e86  jz      short loc_180117E98
0x180117e88  lfence
0x180117e8b  mov     rdx, rbx; struct ITpThreadManager *
0x180117e8e  mov     rcx, rax; this
0x180117e91  call    ??0CPowerManager@@QEAA@PEAUITpThreadManager@@@Z; CPowerManager::CPowerManager(ITpThreadManager *)
0x180117e96  jmp     short loc_180117E9B
0x180117e98  mov     rax, rbp
0x180117e9b  mov     [rbx+20h], rax
0x180117e9f  test    rax, rax
0x180117ea2  jnz     short loc_180117EAF
0x180117ea4  mov     ecx, 1E40B084h; unsigned int
0x180117ea9  call    ?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180117eaf  mov     [rbx+250h], rbp
0x180117eb6  mov     rax, [rbx+98h]
0x180117ebd  cmp     rax, [rbx+90h]
0x180117ec4  jnz     short loc_180117EDE
0x180117ec6  lfence
0x180117ec9  mov     rcx, [rbx+38h]
0x180117ecd  mov     rax, [rcx]
0x180117ed0  mov     rax, [rax+20h]
0x180117ed4  call    cs:__guard_dispatch_icall_fptr
0x180117eda  test    eax, eax
0x180117edc  jz      short loc_180117EE8
0x180117ede  mov     ecx, 1E40B083h
0x180117ee3  call    MsoShipAssertTagProc
0x180117ee8  lea     rcx, [rsp+38h+arg_8]
0x180117eed  call    ??$SafeRelease@VCTpWorkObject@@@@YAXAEAPEAVCTpWorkObject@@@Z; SafeRelease<CTpWorkObject>(CTpWorkObject * &)
0x180117ef2  xor     eax, eax
0x180117ef4  mov     rbx, [rsp+38h+arg_10]
0x180117ef9  mov     rbp, [rsp+38h+arg_18]
0x180117efe  add     rsp, 20h
0x180117f02  pop     r14
0x180117f04  pop     rdi
0x180117f05  pop     rsi
0x180117f06  retn
```
