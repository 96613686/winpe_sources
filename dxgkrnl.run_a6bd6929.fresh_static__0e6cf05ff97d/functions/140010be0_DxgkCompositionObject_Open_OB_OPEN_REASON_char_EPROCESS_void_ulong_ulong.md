# DxgkCompositionObject::Open(_OB_OPEN_REASON,char,_EPROCESS *,void *,ulong *,ulong)

- ea: `0x140010be0`
- end: `0x140010fe0`
- name: `?Open@DxgkCompositionObject@@SAJW4_OB_OPEN_REASON@@DPEAU_EPROCESS@@PEAXPEAKK@Z`
- size: `1024`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140010be0`
- `0x140011574`
- `0x140012540`
- `0x14001b9c0`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1403c298c`
- `0x1403e1958`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140010c7a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140010e93`
- `ntoskrnl!PsGetCurrentProcess` at `0x140010c7a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140010e93`
- `ntoskrnl!ObfDereferenceObject` at `0x140010fcf`
- `ntoskrnl!ObfDereferenceObject` at `0x140010fcf`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140010fbe`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140010fbe`
- `ntoskrnl!KeStackAttachProcess` at `0x140010e7e`
- `ntoskrnl!KeStackAttachProcess` at `0x140010e7e`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140010eb0`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140010eb0`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010c52`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010c89`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010ea2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010ebf`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010c52`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010c89`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010ea2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010ebf`
- `ntoskrnl!KeIsAttachedProcess` at `0x140010cdc`
- `ntoskrnl!KeIsAttachedProcess` at `0x140010cdc`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140010ef2`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140010f3a`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140010ef2`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140010f3a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140010f08`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140010f18`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140010f08`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140010f18`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010cbe`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010cbe`
- `ntoskrnl!PsIsSystemProcess` at `0x140010c3f`
- `ntoskrnl!PsIsSystemProcess` at `0x140010c3f`
- `watchdog!WdLogSingleEntry0` at `0x140010df0`
- `watchdog!WdLogSingleEntry0` at `0x140010f54`
- `watchdog!WdLogSingleEntry0` at `0x140010df0`
- `watchdog!WdLogSingleEntry0` at `0x140010f54`

## pseudocode

```c
__int64 __fastcall DxgkCompositionObject::Open(
        unsigned int a1,
        unsigned __int8 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  unsigned int v6; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // ebx
  __int64 CurrentProcess; // rax
  unsigned int v16; // edi
  _QWORD *CurrentThreadWin32Thread; // rax
  _QWORD *v18; // rdi
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 Win32kImportTable; // rax
  DXGGLOBAL *Global; // rax
  DXGSESSIONMGR *SessionMgr; // rax
  __int64 v25; // rax
  int ProcessSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  _QWORD v28[22]; // [rsp+58h] [rbp-B0h] BYREF
  char v29; // [rsp+108h] [rbp+0h]
  char v30; // [rsp+118h] [rbp+10h]
  PRKPROCESS PROCESS; // [rsp+120h] [rbp+18h] BYREF
  unsigned int v32; // [rsp+128h] [rbp+20h]
  struct _KAPC_STATE ApcState; // [rsp+130h] [rbp+28h] BYREF

  v6 = *(_DWORD *)(a4 + 8);
  v30 = 0;
  PROCESS = 0;
  v32 = v6;
  if ( (unsigned __int8)PsIsSystemProcess(a3)
    || (v13 = PsGetProcessSessionIdEx(a3), v13 != -1) && v13 == *(_DWORD *)(a4 + 8) )
  {
    v14 = 0;
    CurrentProcess = PsGetCurrentProcess(v12, v11);
    v16 = v32;
    if ( (unsigned int)PsGetProcessSessionIdEx(CurrentProcess) != v32 )
    {
      Global = DXGGLOBAL::GetGlobal();
      SessionMgr = DXGGLOBAL::GetSessionMgr(Global);
      v14 = DXGSESSIONMGR::ReferenceSessionCSRSSProcess(SessionMgr, v16, &PROCESS);
      if ( v14 >= 0 )
      {
        KeStackAttachProcess(PROCESS, &ApcState);
        v30 = 1;
      }
    }
    if ( v14 >= 0 )
    {
      memset(v28, 0, sizeof(v28));
      v29 = 0;
      CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
      v18 = CurrentThreadWin32Thread;
      if ( CurrentThreadWin32Thread )
      {
        if ( *CurrentThreadWin32Thread )
        {
          if ( !(unsigned __int8)KeIsAttachedProcess()
            || (v25 = PsGetCurrentProcess(v20, v19),
                ProcessSessionId = PsGetProcessSessionIdEx(v25),
                CurrentThreadProcess = PsGetCurrentThreadProcess(),
                ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
          {
            if ( *(_DWORD *)(*v18 + 368LL) )
            {
              v28[0] = *v18;
              Win32kImportTable = DxgkGetWin32kImportTable();
              if ( (*(int (__fastcall **)(_QWORD))(Win32kImportTable + 8))(*v18) <= 1 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 100;
                DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"newRefCount > 1", 100, 0, 0, 0, 0);
              }
            }
          }
        }
      }
      else
      {
        ExInitializeFastOwnerEntry(&v28[4]);
        ExInitializeFastOwnerEntry(&v28[13]);
        LODWORD(v28[3]) |= 1u;
        PsSetThreadWin32Thread(KeGetCurrentThread(), v28, 0);
        v29 = 1;
      }
      v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64, __int64, int))(**(_QWORD **)(a4 + 16)
                                                                                              + 8LL))(
              *(_QWORD *)(a4 + 16),
              a1,
              a2,
              a3,
              a4,
              a5,
              a6);
      if ( v29 )
      {
        PsSetThreadWin32Thread(KeGetCurrentThread(), 0, v28);
      }
      else if ( v28[0] )
      {
        if ( !*(_QWORD *)&DXGGLOBAL::m_pGlobal )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 2650;
          DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pGlobal != NULL", 2650, 0, 0, 0, 0);
        }
        (*(void (**)(void))(*(_QWORD *)(*(_QWORD *)&DXGGLOBAL::m_pGlobal + 304968LL) + 16LL))();
      }
    }
  }
  else
  {
    v14 = -1073741790;
  }
  if ( v30 )
    KeUnstackDetachProcess(&ApcState);
  if ( PROCESS )
    ObfDereferenceObject(PROCESS);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140010be0  mov     r11, rsp
0x140010be3  push    rbp
0x140010be4  push    rbx
0x140010be5  lea     rbp, [r11-0B8h]
0x140010bec  sub     rsp, 1A8h
0x140010bf3  mov     rax, cs:__security_cookie
0x140010bfa  xor     rax, rsp
0x140010bfd  mov     [rbp+0B0h+var_50], rax
0x140010c01  mov     eax, [r9+8]
0x140010c05  mov     [r11-18h], rsi
0x140010c09  mov     rsi, r9
0x140010c0c  mov     [r11-28h], r12
0x140010c10  movzx   r12d, dl
0x140010c14  mov     [r11-30h], r13
0x140010c18  mov     r13, [rbp+0B0h+arg_20]
0x140010c1f  mov     [r11-38h], r14
0x140010c23  mov     r14, r8
0x140010c26  mov     [r11-40h], r15
0x140010c2a  mov     r15d, ecx
0x140010c2d  mov     rcx, r8
0x140010c30  mov     [rbp+0B0h+var_A0], 0
0x140010c34  mov     [rbp+0B0h+PROCESS], 0
0x140010c3c  mov     [rbp+0B0h+var_90], eax
0x140010c3f  call    cs:__imp_PsIsSystemProcess
0x140010c46  nop     dword ptr [rax+rax+00h]
0x140010c4b  test    al, al
0x140010c4d  jnz     short loc_140010C70
0x140010c4f  mov     rcx, r14
0x140010c52  call    cs:__imp_PsGetProcessSessionIdEx
0x140010c59  nop     dword ptr [rax+rax+00h]
0x140010c5e  cmp     eax, 0FFFFFFFFh
0x140010c61  jz      loc_140010ED8
0x140010c67  cmp     eax, [rsi+8]
0x140010c6a  jnz     loc_140010ED8
0x140010c70  mov     [rsp+1B0h+var_18], rdi
0x140010c78  xor     ebx, ebx
0x140010c7a  call    cs:__imp_PsGetCurrentProcess
0x140010c81  nop     dword ptr [rax+rax+00h]
0x140010c86  mov     rcx, rax
0x140010c89  call    cs:__imp_PsGetProcessSessionIdEx
0x140010c90  nop     dword ptr [rax+rax+00h]
0x140010c95  mov     edi, [rbp+0B0h+var_90]
0x140010c98  cmp     eax, edi
0x140010c9a  jnz     loc_140010E51
0x140010ca0  test    ebx, ebx
0x140010ca2  js      loc_140010D6C
0x140010ca8  xor     edx, edx; Val
0x140010caa  lea     rcx, [rsp+1B0h+var_160]; void *
0x140010caf  mov     r8d, 0B0h; Size
0x140010cb5  call    memset
0x140010cba  mov     [rbp+0B0h+var_B0], 0
0x140010cbe  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010cc5  nop     dword ptr [rax+rax+00h]
0x140010cca  mov     rdi, rax
0x140010ccd  test    rax, rax
0x140010cd0  jz      loc_140010F03
0x140010cd6  cmp     qword ptr [rax], 0
0x140010cda  jz      short loc_140010D00
0x140010cdc  call    cs:__imp_KeIsAttachedProcess
0x140010ce3  nop     dword ptr [rax+rax+00h]
0x140010ce8  test    al, al
0x140010cea  jnz     loc_140010E93
0x140010cf0  mov     rax, [rdi]
0x140010cf3  cmp     dword ptr [rax+170h], 0
0x140010cfa  jnz     loc_140010DCC
0x140010d00  mov     r10, [rsi+10h]
0x140010d04  mov     r9, r14
0x140010d07  mov     ecx, [rbp+0B0h+arg_28]
0x140010d0d  movzx   r8d, r12b
0x140010d11  mov     dword ptr [rsp+1B0h+var_180], ecx
0x140010d15  mov     edx, r15d
0x140010d18  mov     [rsp+1B0h+var_188], r13
0x140010d1d  mov     rcx, r10
0x140010d20  mov     rax, [r10]
0x140010d23  mov     [rsp+1B0h+var_190], rsi
0x140010d28  mov     rax, [rax+8]
0x140010d2c  call    _guard_dispatch_icall
0x140010d31  cmp     [rbp+0B0h+var_B0], 0
0x140010d35  mov     ebx, eax
0x140010d37  jnz     loc_140010EE2
0x140010d3d  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x140010d42  test    rcx, rcx
0x140010d45  jz      short loc_140010D6C
0x140010d47  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, 0; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140010d4f  jz      loc_140010F4F
0x140010d55  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140010d5c  mov     rdx, [rax+4A748h]
0x140010d63  mov     rax, [rdx+10h]
0x140010d67  call    _guard_dispatch_icall
0x140010d6c  mov     rdi, [rsp+1B0h+var_18]
0x140010d74  cmp     [rbp+0B0h+var_A0], 0
0x140010d78  mov     r15, [rsp+1B0h+var_38]
0x140010d80  mov     r14, [rsp+1B0h+var_30]
0x140010d88  mov     r13, [rsp+1B0h+var_28]
0x140010d90  mov     r12, [rsp+1B0h+var_20]
0x140010d98  mov     rsi, [rsp+1A0h]
0x140010da0  jnz     loc_140010FBA
0x140010da6  mov     rcx, [rbp+0B0h+PROCESS]; Object
0x140010daa  test    rcx, rcx
0x140010dad  jnz     loc_140010FCF
0x140010db3  mov     eax, ebx
0x140010db5  mov     rcx, [rbp+0B0h+var_50]
0x140010db9  xor     rcx, rsp; StackCookie
0x140010dbc  call    __security_check_cookie
0x140010dc1  add     rsp, 1A8h
0x140010dc8  pop     rbx
0x140010dc9  pop     rbp
0x140010dca  retn
0x140010dcc  mov     qword ptr [rsp+1B0h+var_160], rax
0x140010dd1  call    DxgkGetWin32kImportTable
0x140010dd6  mov     rcx, [rdi]
0x140010dd9  mov     rax, [rax+8]
0x140010ddd  call    _guard_dispatch_icall
0x140010de2  cmp     eax, 1
0x140010de5  jg      loc_140010D00
0x140010deb  mov     ecx, 1
0x140010df0  call    cs:__imp_WdLogSingleEntry0
0x140010df7  nop     dword ptr [rax+rax+00h]
0x140010dfc  mov     qword ptr [rsp+40h], 0
0x140010e05  lea     r9, aNewrefcount1; "newRefCount > 1"
0x140010e0c  mov     [rsp+1B0h+var_178], 0
0x140010e15  mov     edx, 40002h
0x140010e1a  mov     [rsp+1B0h+var_180], 0
0x140010e23  xor     ecx, ecx
0x140010e25  mov     [rsp+1B0h+var_188], 0
0x140010e2e  mov     r8d, 0FFFFFFFFh
0x140010e34  mov     [rsp+1B0h+var_190], 64h ; 'd'
0x140010e3d  mov     cs:WdLogGlobalForLineNumber, 64h ; 'd'
0x140010e47  call    DxgkLogInternalTriageEvent
0x140010e4c  jmp     loc_140010D00
0x140010e51  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140010e56  mov     rcx, rax; this
0x140010e59  call    ?GetSessionMgr@DXGGLOBAL@@QEAAPEAVDXGSESSIONMGR@@XZ; DXGGLOBAL::GetSessionMgr(void)
0x140010e5e  mov     rcx, rax; this
0x140010e61  lea     r8, [rbp+0B0h+PROCESS]; struct _KPROCESS **
0x140010e65  mov     edx, edi; unsigned int
0x140010e67  call    ?ReferenceSessionCSRSSProcess@DXGSESSIONMGR@@QEAAJKPEAPEAU_KPROCESS@@@Z; DXGSESSIONMGR::ReferenceSessionCSRSSProcess(ulong,_KPROCESS * *)
0x140010e6c  mov     ebx, eax
0x140010e6e  test    eax, eax
0x140010e70  js      loc_140010CA0
0x140010e76  mov     rcx, [rbp+0B0h+PROCESS]; PROCESS
0x140010e7a  lea     rdx, [rbp+0B0h+ApcState]; ApcState
0x140010e7e  call    cs:__imp_KeStackAttachProcess
0x140010e85  nop     dword ptr [rax+rax+00h]
0x140010e8a  mov     [rbp+0B0h+var_A0], 1
0x140010e8e  jmp     loc_140010CA0
0x140010e93  call    cs:__imp_PsGetCurrentProcess
0x140010e9a  nop     dword ptr [rax+rax+00h]
0x140010e9f  mov     rcx, rax
0x140010ea2  call    cs:__imp_PsGetProcessSessionIdEx
0x140010ea9  nop     dword ptr [rax+rax+00h]
0x140010eae  mov     ebx, eax
0x140010eb0  call    cs:__imp_PsGetCurrentThreadProcess
0x140010eb7  nop     dword ptr [rax+rax+00h]
0x140010ebc  mov     rcx, rax
0x140010ebf  call    cs:__imp_PsGetProcessSessionIdEx
0x140010ec6  nop     dword ptr [rax+rax+00h]
0x140010ecb  cmp     ebx, eax
0x140010ecd  jz      loc_140010CF0
0x140010ed3  jmp     loc_140010D00
0x140010ed8  mov     ebx, 0C0000022h
0x140010edd  jmp     loc_140010D74
0x140010ee2  mov     rcx, gs:188h
0x140010eeb  lea     r8, [rsp+1B0h+var_160]
0x140010ef0  xor     edx, edx
0x140010ef2  call    cs:__imp_PsSetThreadWin32Thread
0x140010ef9  nop     dword ptr [rax+rax+00h]
0x140010efe  jmp     loc_140010D6C
0x140010f03  lea     rcx, [rsp+70h]
0x140010f08  call    cs:__imp_ExInitializeFastOwnerEntry
0x140010f0f  nop     dword ptr [rax+rax+00h]
0x140010f14  lea     rcx, [rbp+0B0h+var_F8]
0x140010f18  call    cs:__imp_ExInitializeFastOwnerEntry
0x140010f1f  nop     dword ptr [rax+rax+00h]
0x140010f24  or      dword ptr [rsp+1B0h+var_148], 1
0x140010f29  lea     rdx, [rsp+1B0h+var_160]
0x140010f2e  mov     rcx, gs:188h
0x140010f37  xor     r8d, r8d
0x140010f3a  call    cs:__imp_PsSetThreadWin32Thread
0x140010f41  nop     dword ptr [rax+rax+00h]
0x140010f46  mov     [rbp+0B0h+var_B0], 1
0x140010f4a  jmp     loc_140010D00
0x140010f4f  mov     ecx, 1
0x140010f54  call    cs:__imp_WdLogSingleEntry0
0x140010f5b  nop     dword ptr [rax+rax+00h]
0x140010f60  mov     qword ptr [rsp+40h], 0
0x140010f69  lea     r9, aMPglobalNull; "m_pGlobal != NULL"
0x140010f70  mov     [rsp+1B0h+var_178], 0
0x140010f79  mov     edx, 40002h
0x140010f7e  mov     [rsp+1B0h+var_180], 0
0x140010f87  xor     ecx, ecx
0x140010f89  mov     [rsp+1B0h+var_188], 0
0x140010f92  mov     r8d, 0FFFFFFFFh
0x140010f98  mov     [rsp+1B0h+var_190], 0A5Ah
0x140010fa1  mov     cs:WdLogGlobalForLineNumber, 0A5Ah
0x140010fab  call    DxgkLogInternalTriageEvent
0x140010fb0  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x140010fb5  jmp     loc_140010D55
0x140010fba  lea     rcx, [rbp+0B0h+ApcState]; ApcState
0x140010fbe  call    cs:__imp_KeUnstackDetachProcess
0x140010fc5  nop     dword ptr [rax+rax+00h]
0x140010fca  jmp     loc_140010DA6
0x140010fcf  call    cs:__imp_ObfDereferenceObject
0x140010fd6  nop     dword ptr [rax+rax+00h]
0x140010fdb  jmp     loc_140010DB3
```
