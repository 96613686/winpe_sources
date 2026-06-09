# PerfDiagShutdown::Impl::CScenarioBuilder::buildSessionShutdownNode(PerfDiagShared::RegressionAnalysis::CActivityNodeFolding &,bool (*)(ulong))

- ea: `0x18002c198`
- end: `0x18002c2f2`
- name: `?buildSessionShutdownNode@CScenarioBuilder@Impl@PerfDiagShutdown@@AEAAXAEAUCActivityNodeFolding@RegressionAnalysis@PerfDiagShared@@P6A_NK@Z@Z`
- size: `346`
- prototype: `void __fastcall(PerfDiagShutdown::Impl::CScenarioBuilder *__hidden this, struct PerfDiagShared::RegressionAnalysis::CActivityNodeFolding *, bool (*)(unsigned int))`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180036520`

## callees

- `0x18001dba0`
- `0x18002c198`
- `0x18003e2d0`
- `0x1800d6010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002c2b1`
- `msvcrt!_wcsicmp` at `0x18002c2b1`

## string_xrefs

- `0x18002c2aa`: `services.exe`

## pseudocode

```c
void __fastcall PerfDiagShutdown::Impl::CScenarioBuilder::buildSessionShutdownNode(
        PerfDiagShutdown::Impl::CScenarioBuilder *this,
        struct PerfDiagShared::RegressionAnalysis::CActivityNodeFolding *a2,
        bool (*a3)(unsigned int))
{
  unsigned __int64 i; // r15
  __int64 v7; // rdi
  __int64 v8; // rbx
  unsigned __int64 v9; // rbp
  struct PerfDiagShared::RegressionAnalysis::CActivityNodeFolding *j; // r14
  __int64 v11; // r8
  _QWORD *v12; // rcx
  unsigned __int64 v13; // r14
  __int64 v14; // rbp
  __int64 v15; // rax
  const wchar_t *v16; // rcx

  for ( i = 0; i < *((_QWORD *)this + 22); ++i )
  {
    v7 = *((_QWORD *)this + 20);
    v8 = *((_QWORD *)this + 21) * i;
    if ( *(_QWORD *)(v8 + v7) >= *((_QWORD *)this + 1)
      && ((unsigned __int8 (__fastcall *)(_QWORD))a3)(*(unsigned int *)(v8 + v7 + 16)) )
    {
      if ( *(_QWORD *)(v8 + v7 + 32) )
      {
        v9 = 0;
        for ( j = PerfDiagShutdown::Impl::CScenarioBuilder::fold(this, a2, L"Notifications", 0);
              v9 < *(_QWORD *)(v8 + v7 + 32);
              ++v9 )
        {
          v11 = *(_QWORD *)(*(_QWORD *)(v8 + v7 + 24) + 8 * v9);
          if ( *(_QWORD *)v11 != XPerfCore::TimeStamp::Min && *(_QWORD *)(v11 + 8) != XPerfCore::TimeStamp::Max )
          {
            PerfDiagShutdown::Impl::CScenarioBuilder::buildNotificationNode(
              this,
              j,
              (const struct XPerfAddIn::IWinlogonInfoSource::Notification *)v11);
            v12 = *(_QWORD **)(*(_QWORD *)(v8 + v7 + 24) + 8 * v9);
            *(_QWORD *)j += v12[1] - *v12;
          }
        }
      }
      if ( *(_QWORD *)(v8 + v7 + 48) )
      {
        v13 = 0;
        do
        {
          v14 = *(_QWORD *)(*(_QWORD *)(v8 + v7 + 40) + 8 * v13);
          if ( *(_QWORD *)v14 != XPerfCore::TimeStamp::Min && *(_QWORD *)(v14 + 8) != XPerfCore::TimeStamp::Max )
          {
            v15 = *(_QWORD *)(v14 + 16);
            if ( !*(_DWORD *)(v15 + 40) )
            {
              v16 = *(const wchar_t **)(v15 + 24);
              if ( v16 )
              {
                if ( !_wcsicmp(v16, L"services.exe") )
                  *((_OWORD *)this + 13) = *(_OWORD *)v14;
              }
            }
          }
          ++v13;
        }
        while ( v13 < *(_QWORD *)(v8 + v7 + 48) );
      }
    }
  }
}

```

## disassembly

```asm
0x18002c198  push    rbx
0x18002c19a  push    rbp
0x18002c19b  push    rsi
0x18002c19c  push    rdi
0x18002c19d  push    r12
0x18002c19f  push    r13
0x18002c1a1  push    r14
0x18002c1a3  push    r15
0x18002c1a5  sub     rsp, 28h
0x18002c1a9  xor     r15d, r15d
0x18002c1ac  mov     r12, r8
0x18002c1af  mov     r13, rdx
0x18002c1b2  mov     rsi, rcx
0x18002c1b5  cmp     [rcx+0B0h], r15
0x18002c1bc  jbe     loc_18002C2E1
0x18002c1c2  mov     rdi, [rsi+0A0h]
0x18002c1c9  mov     rbx, r15
0x18002c1cc  imul    rbx, [rsi+0A8h]
0x18002c1d4  mov     rax, [rsi+8]
0x18002c1d8  cmp     [rbx+rdi], rax
0x18002c1dc  jl      loc_18002C2D1
0x18002c1e2  mov     ecx, [rbx+rdi+10h]
0x18002c1e6  mov     rax, r12
0x18002c1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1ee  test    al, al
0x18002c1f0  jz      loc_18002C2D1
0x18002c1f6  cmp     qword ptr [rbx+rdi+20h], 0
0x18002c1fc  jbe     short loc_18002C269
0x18002c1fe  mov     r8, cs:off_1800D77B0; unsigned __int16 *
0x18002c205  xor     r9d, r9d; __int64
0x18002c208  mov     rdx, r13; struct PerfDiagShared::RegressionAnalysis::CActivityNodeFolding *
0x18002c20b  mov     rcx, rsi; this
0x18002c20e  call    ?fold@CScenarioBuilder@Impl@PerfDiagShutdown@@AEAAAEAUCActivityNodeFolding@RegressionAnalysis@PerfDiagShared@@AEAU456@PEBG_J@Z; PerfDiagShutdown::Impl::CScenarioBuilder::fold(PerfDiagShared::RegressionAnalysis::CActivityNodeFolding &,ushort const *,__int64)
0x18002c213  xor     ebp, ebp
0x18002c215  mov     r14, rax
0x18002c218  cmp     [rbx+rdi+20h], rbp
0x18002c21d  jbe     short loc_18002C269
0x18002c21f  mov     rcx, [rbx+rdi+18h]
0x18002c224  mov     rax, cs:?Min@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::Min
0x18002c22b  mov     r8, [rcx+rbp*8]; struct XPerfAddIn::IWinlogonInfoSource::Notification *
0x18002c22f  cmp     [r8], rax
0x18002c232  jz      short loc_18002C25F
0x18002c234  mov     rax, cs:?Max@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::Max
0x18002c23b  cmp     [r8+8], rax
0x18002c23f  jz      short loc_18002C25F
0x18002c241  mov     rdx, r14; struct PerfDiagShared::RegressionAnalysis::CActivityNodeFolding *
0x18002c244  mov     rcx, rsi; this
0x18002c247  call    ?buildNotificationNode@CScenarioBuilder@Impl@PerfDiagShutdown@@AEAAXAEAUCActivityNodeFolding@RegressionAnalysis@PerfDiagShared@@AEBUNotification@IWinlogonInfoSource@XPerfAddIn@@@Z; PerfDiagShutdown::Impl::CScenarioBuilder::buildNotificationNode(PerfDiagShared::RegressionAnalysis::CActivityNodeFolding &,XPerfAddIn::IWinlogonInfoSource::Notification const &)
0x18002c24c  mov     rax, [rbx+rdi+18h]
0x18002c251  mov     rcx, [rax+rbp*8]
0x18002c255  mov     rax, [rcx+8]
0x18002c259  sub     rax, [rcx]
0x18002c25c  add     [r14], rax
0x18002c25f  inc     rbp
0x18002c262  cmp     rbp, [rbx+rdi+20h]
0x18002c267  jb      short loc_18002C21F
0x18002c269  cmp     qword ptr [rbx+rdi+30h], 0
0x18002c26f  jbe     short loc_18002C2D1
0x18002c271  xor     r14d, r14d
0x18002c274  mov     rax, [rbx+rdi+28h]
0x18002c279  mov     rbp, [rax+r14*8]
0x18002c27d  mov     rax, cs:?Min@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::Min
0x18002c284  cmp     [rbp+0], rax
0x18002c288  jz      short loc_18002C2C7
0x18002c28a  mov     rax, cs:?Max@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::Max
0x18002c291  cmp     [rbp+8], rax
0x18002c295  jz      short loc_18002C2C7
0x18002c297  mov     rax, [rbp+10h]
0x18002c29b  cmp     dword ptr [rax+28h], 0
0x18002c29f  jnz     short loc_18002C2C7
0x18002c2a1  mov     rcx, [rax+18h]; String1
0x18002c2a5  test    rcx, rcx
0x18002c2a8  jz      short loc_18002C2C7
0x18002c2aa  lea     rdx, aServicesExe; "services.exe"
0x18002c2b1  call    cs:__imp__wcsicmp
0x18002c2b7  test    eax, eax
0x18002c2b9  jnz     short loc_18002C2C7
0x18002c2bb  movups  xmm0, xmmword ptr [rbp+0]
0x18002c2bf  movdqu  xmmword ptr [rsi+0D0h], xmm0
0x18002c2c7  inc     r14
0x18002c2ca  cmp     r14, [rbx+rdi+30h]
0x18002c2cf  jb      short loc_18002C274
0x18002c2d1  inc     r15
0x18002c2d4  cmp     r15, [rsi+0B0h]
0x18002c2db  jb      loc_18002C1C2
0x18002c2e1  add     rsp, 28h
0x18002c2e5  pop     r15
0x18002c2e7  pop     r14
0x18002c2e9  pop     r13
0x18002c2eb  pop     r12
0x18002c2ed  pop     rdi
0x18002c2ee  pop     rsi
0x18002c2ef  pop     rbp
0x18002c2f0  pop     rbx
0x18002c2f1  retn
```
