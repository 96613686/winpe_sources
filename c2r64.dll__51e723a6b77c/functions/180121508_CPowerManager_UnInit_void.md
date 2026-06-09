# CPowerManager::UnInit(void)

- ea: `0x180121508`
- end: `0x18012178a`
- name: `?UnInit@CPowerManager@@IEAAXXZ`
- size: `642`
- prototype: `void __fastcall(CPowerManager *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18011e8a0`
- `0x18011e8b0`
- `0x18011f70c`

## callees

- `0x180013c78`
- `0x1800264b4`
- `0x18002d5c8`
- `0x18002d8d4`
- `0x18002d96c`
- `0x180030a94`
- `0x18003ab84`
- `0x1800aa674`
- `0x1801069a0`
- `0x18011e074`
- `0x18011e0d8`
- `0x18011e1e8`
- `0x18011e68c`
- `0x180121508`
- `0x1801219b0`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18012155f`
- `KERNEL32!GetCurrentThreadId` at `0x18012155f`
- `USER32!UnhookWindowsHookEx` at `0x18012154b`
- `USER32!UnhookWindowsHookEx` at `0x18012154b`
- `USER32!DestroyWindow` at `0x180121743`
- `USER32!DestroyWindow` at `0x180121743`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPowerManager::UnInit(CPowerManager *this)
{
  CPowerManager *v1; // rdi
  HHOOK v2; // rcx
  int v3; // ebx
  char v4; // bl
  __int64 v5; // rbx
  __int64 v6; // r14
  __int64 v7; // rax
  __int64 v8; // rcx
  HWND v9; // rcx
  _DWORD v10[10]; // [rsp+20h] [rbp-28h] BYREF
  CPowerManager *v11; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  v11 = this;
  v1 = this;
  if ( (byte_18021CCC1 & 2) != 0 )
    McTemplateU0p_EventWriteTransfer(guidProviderOfficeThreadpool_Context, PMShutdown, this);
  v2 = (HHOOK)*((_QWORD *)v1 + 99);
  if ( v2 )
  {
    UnhookWindowsHookEx(v2);
    *((_QWORD *)v1 + 99) = 0;
  }
  v3 = *((_DWORD *)v1 + 24);
  if ( GetCurrentThreadId() != v3 )
  {
    if ( v3 )
      MsoShipAssertTagProc(4014421);
    if ( *((_QWORD *)v1 + 21) )
      MsoShipAssertTagProc(4014422);
    if ( *((_BYTE *)v1 + 400) )
      MsoShipAssertTagProc(4014423);
    if ( *((_BYTE *)v1 + 402) )
      MsoShipAssertTagProc(4014424);
  }
  CExclusiveLock::FAcquire((CPowerManager *)((char *)v1 + 552));
  Mso::TCntPtr<MsoIdleTaskNoRefCount>::Clear((char *)v1 + 520);
  CExclusiveLock::ReleaseLock((CPowerManager *)((char *)v1 + 552));
  CExclusiveLock::FAcquire((CPowerManager *)((char *)v1 + 624));
  Mso::TCntPtr<MsoIdleTaskNoRefCount>::Clear((char *)v1 + 528);
  CExclusiveLock::ReleaseLock((CPowerManager *)((char *)v1 + 624));
  CPowerFlagsChangeHelper::CPowerFlagsChangeHelper(
    (CPowerFlagsChangeHelper *)v10,
    *((struct ITpThreadManager **)v1 + 20),
    v1);
  if ( *((_BYTE *)v1 + 403) )
    MsoShipAssertTagProc(4014426);
  v4 = *((_BYTE *)v1 + 403);
  *((_BYTE *)v1 + 403) = 1;
  v10[0] |= 0x4000u;
  CPowerFlagsChangeHelper::DoUpdate((CPowerFlagsChangeHelper *)v10, 0);
  CPowerFlagsChangeHelper::~CPowerFlagsChangeHelper((CPowerFlagsChangeHelper *)v10);
  if ( !v4 )
  {
    v5 = *((_QWORD *)v1 + 3);
    v6 = *((_QWORD *)v1 + 4);
    try
    {
      while ( v5 != v6 )
      {
        v12 = *(_QWORD *)(v5 + 16);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, 0);
        SafeRelease<CTpWorkObject>(&v12);
        v5 += 24;
      }
      v7 = *((_QWORD *)v1 + 3);
      if ( v7 != *((_QWORD *)v1 + 4) )
        *((_QWORD *)v1 + 4) = v7;
    }
    catch ( ... )
    {
      MsoShipAssertTagProc(4014427);
      v1 = v11;
    }
  }
  CKeepPowerProfDllInMemory::CKeepPowerProfDllInMemory((CKeepPowerProfDllInMemory *)&v11);
  sub_1801219B0((char *)v1 + 104);
  sub_1801219B0((char *)v1 + 112);
  sub_1801219B0((char *)v1 + 120);
  sub_1801219B0((char *)v1 + 136);
  sub_1801219B0((char *)v1 + 144);
  sub_1801219B0((char *)v1 + 152);
  CKeepPowerProfDllInMemory::~CKeepPowerProfDllInMemory((CKeepPowerProfDllInMemory *)&v11);
  v8 = *((_QWORD *)v1 + 64);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 24LL))(v8, 0);
    SafeRelease<CTpWorkObject>((char *)v1 + 512);
  }
  if ( *((_QWORD *)v1 + 62) )
    Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear((char *)v1 + 496);
  if ( *((_QWORD *)v1 + 63) )
    Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear((char *)v1 + 504);
  v9 = (HWND)*((_QWORD *)v1 + 21);
  if ( v9 )
    DestroyWindow(v9);
  *((_QWORD *)v1 + 21) = 0;
  *((_BYTE *)v1 + 402) = 0;
  if ( *((_BYTE *)v1 + 400) )
  {
    IsolationAwareUnregisterClassW(L"OfficePowerManagerWindow", 0);
    *((_BYTE *)v1 + 400) = 0;
  }
}

```

## disassembly

```asm
0x180121508  mov     [rsp+arg_10], rbx
0x18012150d  mov     [rsp+arg_18], rdi
0x180121512  mov     [rsp+arg_0], rcx
0x180121517  push    r14
0x180121519  sub     rsp, 40h
0x18012151d  mov     rdi, rcx
0x180121520  test    cs:byte_18021CCC1, 2
0x180121527  jz      short loc_18012153F
0x180121529  mov     r8, rcx
0x18012152c  lea     rdx, PMShutdown
0x180121533  lea     rcx, guidProviderOfficeThreadpool_Context
0x18012153a  call    McTemplateU0p_EventWriteTransfer
0x18012153f  mov     rcx, [rdi+318h]; hhk
0x180121546  test    rcx, rcx
0x180121549  jz      short loc_18012155C
0x18012154b  call    cs:__imp_UnhookWindowsHookEx
0x180121551  mov     qword ptr [rdi+318h], 0
0x18012155c  mov     ebx, [rdi+60h]
0x18012155f  call    cs:__imp_GetCurrentThreadId
0x180121565  cmp     eax, ebx
0x180121567  jz      short loc_1801215B1
0x180121569  test    ebx, ebx
0x18012156b  jz      short loc_180121577
0x18012156d  mov     ecx, 3D4155h
0x180121572  call    MsoShipAssertTagProc
0x180121577  cmp     qword ptr [rdi+0A8h], 0
0x18012157f  jz      short loc_18012158B
0x180121581  mov     ecx, 3D4156h
0x180121586  call    MsoShipAssertTagProc
0x18012158b  cmp     byte ptr [rdi+190h], 0
0x180121592  jz      short loc_18012159E
0x180121594  mov     ecx, 3D4157h
0x180121599  call    MsoShipAssertTagProc
0x18012159e  cmp     byte ptr [rdi+192h], 0
0x1801215a5  jz      short loc_1801215B1
0x1801215a7  mov     ecx, 3D4158h
0x1801215ac  call    MsoShipAssertTagProc
0x1801215b1  lea     rbx, [rdi+228h]
0x1801215b8  mov     rcx, rbx; this
0x1801215bb  call    ?FAcquire@CExclusiveLock@@QEAA_N_NK@Z; CExclusiveLock::FAcquire(bool,ulong)
0x1801215c0  lea     rcx, [rdi+208h]
0x1801215c7  call    ?Clear@?$TCntPtr@VMsoIdleTaskNoRefCount@@@Mso@@QEAAXXZ; Mso::TCntPtr<MsoIdleTaskNoRefCount>::Clear(void)
0x1801215cc  mov     rcx, rbx; this
0x1801215cf  call    ?ReleaseLock@CExclusiveLock@@QEAAXXZ; CExclusiveLock::ReleaseLock(void)
0x1801215d4  lea     rbx, [rdi+270h]
0x1801215db  mov     rcx, rbx; this
0x1801215de  call    ?FAcquire@CExclusiveLock@@QEAA_N_NK@Z; CExclusiveLock::FAcquire(bool,ulong)
0x1801215e3  lea     rcx, [rdi+210h]
0x1801215ea  call    ?Clear@?$TCntPtr@VMsoIdleTaskNoRefCount@@@Mso@@QEAAXXZ; Mso::TCntPtr<MsoIdleTaskNoRefCount>::Clear(void)
0x1801215ef  mov     rcx, rbx; this
0x1801215f2  call    ?ReleaseLock@CExclusiveLock@@QEAAXXZ; CExclusiveLock::ReleaseLock(void)
0x1801215f7  mov     r8, rdi; struct ITpPowerManagerInternal *
0x1801215fa  mov     rdx, [rdi+0A0h]; struct ITpThreadManager *
0x180121601  lea     rcx, [rsp+48h+var_28]; this
0x180121606  call    ??0CPowerFlagsChangeHelper@@QEAA@PEAUITpThreadManager@@PEAUITpPowerManagerInternal@@@Z; CPowerFlagsChangeHelper::CPowerFlagsChangeHelper(ITpThreadManager *,ITpPowerManagerInternal *)
0x18012160b  cmp     byte ptr [rdi+193h], 0
0x180121612  jz      short loc_18012161E
0x180121614  mov     ecx, 3D415Ah
0x180121619  call    MsoShipAssertTagProc
0x18012161e  mov     bl, [rdi+193h]
0x180121624  mov     byte ptr [rdi+193h], 1
0x18012162b  bts     [rsp+48h+var_28], 0Eh
0x180121631  xor     edx, edx; bool
0x180121633  lea     rcx, [rsp+48h+var_28]; this
0x180121638  call    ?DoUpdate@CPowerFlagsChangeHelper@@QEAAX_N@Z; CPowerFlagsChangeHelper::DoUpdate(bool)
0x18012163d  lea     rcx, [rsp+48h+var_28]; this
0x180121642  call    ??1CPowerFlagsChangeHelper@@QEAA@XZ; CPowerFlagsChangeHelper::~CPowerFlagsChangeHelper(void)
0x180121647  test    bl, bl
0x180121649  jnz     short loc_18012169A
0x18012164b  mov     rbx, [rdi+18h]
0x18012164f  mov     r14, [rdi+20h]
0x180121653  jmp     short loc_180121680
0x180121655  mov     rcx, [rbx+10h]
0x180121659  mov     [rsp+48h+arg_8], rcx
0x18012165e  mov     rax, [rcx]
0x180121661  xor     edx, edx
0x180121663  mov     rax, [rax+18h]
0x180121667  call    cs:__guard_dispatch_icall_fptr
0x18012166d  lea     rcx, [rsp+48h+arg_8]
0x180121672  call    ??$SafeRelease@VCTpWorkObject@@@@YAXAEAPEAVCTpWorkObject@@@Z; SafeRelease<CTpWorkObject>(CTpWorkObject * &)
0x180121677  add     rbx, 18h
0x18012167b  nop     dword ptr [rax+rax+00h]
0x180121680  cmp     rbx, r14
0x180121683  jnz     short loc_180121655
0x180121685  mov     rax, [rdi+18h]
0x180121689  cmp     rax, [rdi+20h]
0x18012168d  jz      short loc_180121693
0x18012168f  mov     [rdi+20h], rax
0x180121693  jmp     short loc_18012169A
0x180121695  mov     rdi, [rsp+48h+arg_0]
0x18012169a  lea     rcx, [rsp+48h+arg_0]; this
0x18012169f  call    ??0CKeepPowerProfDllInMemory@@QEAA@XZ; CKeepPowerProfDllInMemory::CKeepPowerProfDllInMemory(void)
0x1801216a4  lea     rcx, [rdi+68h]
0x1801216a8  call    sub_1801219B0
0x1801216ad  lea     rcx, [rdi+70h]
0x1801216b1  call    sub_1801219B0
0x1801216b6  lea     rcx, [rdi+78h]
0x1801216ba  call    sub_1801219B0
0x1801216bf  lea     rcx, [rdi+88h]
0x1801216c6  call    sub_1801219B0
0x1801216cb  lea     rcx, [rdi+90h]
0x1801216d2  call    sub_1801219B0
0x1801216d7  lea     rcx, [rdi+98h]
0x1801216de  call    sub_1801219B0
0x1801216e3  lea     rcx, [rsp+48h+arg_0]; this
0x1801216e8  call    ??1CKeepPowerProfDllInMemory@@QEAA@XZ; CKeepPowerProfDllInMemory::~CKeepPowerProfDllInMemory(void)
0x1801216ed  lea     rbx, [rdi+200h]
0x1801216f4  mov     rcx, [rbx]
0x1801216f7  test    rcx, rcx
0x1801216fa  jz      short loc_180121713
0x1801216fc  mov     rax, [rcx]
0x1801216ff  xor     edx, edx
0x180121701  mov     rax, [rax+18h]
0x180121705  call    cs:__guard_dispatch_icall_fptr
0x18012170b  mov     rcx, rbx
0x18012170e  call    ??$SafeRelease@VCTpWorkObject@@@@YAXAEAPEAVCTpWorkObject@@@Z; SafeRelease<CTpWorkObject>(CTpWorkObject * &)
0x180121713  lea     rcx, [rdi+1F0h]
0x18012171a  cmp     qword ptr [rcx], 0
0x18012171e  jz      short loc_180121725
0x180121720  call    ?clear@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXXZ; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear(void)
0x180121725  lea     rcx, [rdi+1F8h]
0x18012172c  cmp     qword ptr [rcx], 0
0x180121730  jz      short loc_180121737
0x180121732  call    ?clear@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXXZ; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear(void)
0x180121737  mov     rcx, [rdi+0A8h]; hWnd
0x18012173e  test    rcx, rcx
0x180121741  jz      short loc_180121749
0x180121743  call    cs:__imp_DestroyWindow
0x180121749  mov     qword ptr [rdi+0A8h], 0
0x180121754  mov     byte ptr [rdi+192h], 0
0x18012175b  cmp     byte ptr [rdi+190h], 0
0x180121762  jz      short loc_180121779
0x180121764  xor     edx, edx; hInstance
0x180121766  lea     rcx, ?c_szPowerManagerWindowClassName@@3QB_WB; "OfficePowerManagerWindow"
0x18012176d  call    IsolationAwareUnregisterClassW
0x180121772  mov     byte ptr [rdi+190h], 0
0x180121779  mov     rbx, [rsp+48h+arg_10]
0x18012177e  mov     rdi, [rsp+48h+arg_18]
0x180121783  add     rsp, 40h
0x180121787  pop     r14
0x180121789  retn
```
