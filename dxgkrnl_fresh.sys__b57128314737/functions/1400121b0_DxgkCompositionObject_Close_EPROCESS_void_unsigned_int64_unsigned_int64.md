# DxgkCompositionObject::Close(_EPROCESS *,void *,unsigned __int64,unsigned __int64)

- ea: `0x1400121b0`
- end: `0x14001252f`
- name: `?Close@DxgkCompositionObject@@SAXPEAU_EPROCESS@@PEAX_K2@Z`
- size: `895`
- prototype: `void __fastcall(struct _EPROCESS *, void *, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140011574`
- `0x1400121b0`
- `0x140012540`
- `0x14001b9c0`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1403c298c`
- `0x1403e1958`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140012205`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400123d7`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012205`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400123d7`
- `ntoskrnl!ObfDereferenceObject` at `0x14001251e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001251e`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001250d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001250d`
- `ntoskrnl!KeStackAttachProcess` at `0x14001244d`
- `ntoskrnl!KeStackAttachProcess` at `0x14001244d`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400123f4`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400123f4`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140012214`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400123e6`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140012403`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140012214`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400123e6`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140012403`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001225e`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001225e`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140012434`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140012499`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140012434`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140012499`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140012467`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140012477`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140012467`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140012477`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140012241`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140012241`
- `watchdog!WdLogSingleEntry0` at `0x14001237e`
- `watchdog!WdLogSingleEntry0` at `0x1400124b3`
- `watchdog!WdLogSingleEntry0` at `0x14001237e`
- `watchdog!WdLogSingleEntry0` at `0x1400124b3`

## pseudocode

```c
void __fastcall DxgkCompositionObject::Close(struct _EPROCESS *a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // eax
  __int64 CurrentProcess; // rax
  unsigned int v10; // ebx
  _QWORD *CurrentThreadWin32Thread; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  DXGGLOBAL *Global; // rax
  DXGSESSIONMGR *SessionMgr; // rax
  __int64 Win32kImportTable; // rax
  __int64 v18; // rax
  int ProcessSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  _QWORD v21[22]; // [rsp+58h] [rbp-B0h] BYREF
  char v22; // [rsp+108h] [rbp+0h]
  char v23; // [rsp+118h] [rbp+10h]
  PRKPROCESS PROCESS; // [rsp+120h] [rbp+18h] BYREF
  unsigned int v25; // [rsp+128h] [rbp+20h]
  struct _KAPC_STATE ApcState; // [rsp+130h] [rbp+28h] BYREF

  v4 = a2[2];
  PROCESS = 0;
  v23 = 0;
  v25 = v4;
  CurrentProcess = PsGetCurrentProcess(a1, a2);
  v10 = v25;
  if ( (unsigned int)PsGetProcessSessionIdEx(CurrentProcess) != v25 )
  {
    Global = DXGGLOBAL::GetGlobal();
    SessionMgr = DXGGLOBAL::GetSessionMgr(Global);
    if ( (int)DXGSESSIONMGR::ReferenceSessionCSRSSProcess(SessionMgr, v10, &PROCESS) < 0 )
      goto LABEL_12;
    KeStackAttachProcess(PROCESS, &ApcState);
    v23 = 1;
  }
  memset(v21, 0, sizeof(v21));
  v22 = 0;
  CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
  v12 = CurrentThreadWin32Thread;
  if ( CurrentThreadWin32Thread )
  {
    if ( *CurrentThreadWin32Thread )
    {
      if ( !(unsigned __int8)KeIsAttachedProcess()
        || (v18 = PsGetCurrentProcess(v14, v13),
            ProcessSessionId = PsGetProcessSessionIdEx(v18),
            CurrentThreadProcess = PsGetCurrentThreadProcess(),
            ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
      {
        if ( *(_DWORD *)(*v12 + 368LL) )
        {
          v21[0] = *v12;
          Win32kImportTable = DxgkGetWin32kImportTable(v14);
          if ( (*(int (__fastcall **)(_QWORD))(Win32kImportTable + 8))(*v12) <= 1 )
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
    ExInitializeFastOwnerEntry(&v21[4]);
    ExInitializeFastOwnerEntry(&v21[13]);
    LODWORD(v21[3]) |= 1u;
    PsSetThreadWin32Thread(KeGetCurrentThread(), v21, 0);
    v22 = 1;
  }
  (*(void (__fastcall **)(_QWORD, struct _EPROCESS *, _DWORD *, __int64, __int64))(**((_QWORD **)a2 + 2) + 24LL))(
    *((_QWORD *)a2 + 2),
    a1,
    a2,
    a3,
    a4);
  if ( v22 )
  {
    PsSetThreadWin32Thread(KeGetCurrentThread(), 0, v21);
  }
  else if ( v21[0] )
  {
    if ( !*(_QWORD *)&DXGGLOBAL::m_pGlobal )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2650;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pGlobal != NULL", 2650, 0, 0, 0, 0);
    }
    (*(void (**)(void))(*(_QWORD *)(*(_QWORD *)&DXGGLOBAL::m_pGlobal + 304968LL) + 16LL))();
  }
LABEL_12:
  if ( v23 )
    KeUnstackDetachProcess(&ApcState);
  if ( PROCESS )
    ObfDereferenceObject(PROCESS);
}

```

## disassembly

```asm
0x1400121b0  mov     r11, rsp
0x1400121b3  push    rbp
0x1400121b4  lea     rbp, [r11-0B8h]
0x1400121bb  sub     rsp, 1B0h
0x1400121c2  mov     rax, cs:__security_cookie
0x1400121c9  xor     rax, rsp
0x1400121cc  mov     [rbp+0B0h+var_50], rax
0x1400121d0  mov     eax, [rdx+8]
0x1400121d3  mov     [r11-10h], rbx
0x1400121d7  mov     [r11-18h], rsi
0x1400121db  mov     rsi, rdx
0x1400121de  mov     [r11-28h], r12
0x1400121e2  mov     r12, r9
0x1400121e5  mov     [r11-30h], r13
0x1400121e9  xor     r13d, r13d
0x1400121ec  mov     [r11-38h], r14
0x1400121f0  mov     r14, rcx
0x1400121f3  mov     [r11-40h], r15
0x1400121f7  mov     r15, r8
0x1400121fa  mov     [rbp+0B0h+PROCESS], r13
0x1400121fe  mov     [rbp+0B0h+var_A0], 0
0x140012202  mov     [rbp+0B0h+var_90], eax
0x140012205  call    cs:__imp_PsGetCurrentProcess
0x14001220c  nop     dword ptr [rax+rax+00h]
0x140012211  mov     rcx, rax
0x140012214  call    cs:__imp_PsGetProcessSessionIdEx
0x14001221b  nop     dword ptr [rax+rax+00h]
0x140012220  mov     ebx, [rbp+0B0h+var_90]
0x140012223  cmp     eax, ebx
0x140012225  jnz     loc_1400122DA
0x14001222b  xor     edx, edx; Val
0x14001222d  lea     rcx, [rsp+1B0h+var_160]; void *
0x140012232  mov     r8d, 0B0h; Size
0x140012238  call    memset
0x14001223d  mov     [rbp+0B0h+var_B0], r13b
0x140012241  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140012248  nop     dword ptr [rax+rax+00h]
0x14001224d  mov     rbx, rax
0x140012250  test    rax, rax
0x140012253  jz      loc_140012462
0x140012259  cmp     [rax], r13
0x14001225c  jz      short loc_140012282
0x14001225e  call    cs:__imp_KeIsAttachedProcess
0x140012265  nop     dword ptr [rax+rax+00h]
0x14001226a  test    al, al
0x14001226c  jnz     loc_1400123CF
0x140012272  mov     rax, [rbx]
0x140012275  cmp     [rax+170h], r13d
0x14001227c  jnz     loc_14001235A
0x140012282  mov     rcx, [rsi+10h]
0x140012286  mov     r9, r15
0x140012289  mov     r8, rsi
0x14001228c  mov     [rsp+1B0h+var_190], r12
0x140012291  mov     rdx, r14
0x140012294  mov     rax, [rcx]
0x140012297  mov     rax, [rax+18h]
0x14001229b  call    _guard_dispatch_icall
0x1400122a0  cmp     [rbp+0B0h+var_B0], r13b
0x1400122a4  jnz     loc_140012424
0x1400122aa  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x1400122af  test    rcx, rcx
0x1400122b2  jz      short loc_1400122FD
0x1400122b4  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, r13; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x1400122bb  jz      loc_1400124AE
0x1400122c1  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x1400122c8  mov     rdx, [rax+4A748h]
0x1400122cf  mov     rax, [rdx+10h]
0x1400122d3  call    _guard_dispatch_icall
0x1400122d8  jmp     short loc_1400122FD
0x1400122da  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1400122df  mov     rcx, rax; this
0x1400122e2  call    ?GetSessionMgr@DXGGLOBAL@@QEAAPEAVDXGSESSIONMGR@@XZ; DXGGLOBAL::GetSessionMgr(void)
0x1400122e7  mov     rcx, rax; this
0x1400122ea  lea     r8, [rbp+0B0h+PROCESS]; struct _KPROCESS **
0x1400122ee  mov     edx, ebx; unsigned int
0x1400122f0  call    ?ReferenceSessionCSRSSProcess@DXGSESSIONMGR@@QEAAJKPEAPEAU_KPROCESS@@@Z; DXGSESSIONMGR::ReferenceSessionCSRSSProcess(ulong,_KPROCESS * *)
0x1400122f5  test    eax, eax
0x1400122f7  jns     loc_140012445
0x1400122fd  cmp     [rbp+0B0h+var_A0], 0
0x140012301  mov     r15, [rsp+1B0h+var_38]
0x140012309  mov     r14, [rsp+1B0h+var_30]
0x140012311  mov     r13, [rsp+1B0h+var_28]
0x140012319  mov     r12, [rsp+1B0h+var_20]
0x140012321  mov     rsi, [rsp+1B0h+var_10]
0x140012329  mov     rbx, [rsp+1A8h]
0x140012331  jnz     loc_140012509
0x140012337  mov     rcx, [rbp+0B0h+PROCESS]; Object
0x14001233b  test    rcx, rcx
0x14001233e  jnz     loc_14001251E
0x140012344  mov     rcx, [rbp+0B0h+var_50]
0x140012348  xor     rcx, rsp; StackCookie
0x14001234b  call    __security_check_cookie
0x140012350  add     rsp, 1B0h
0x140012357  pop     rbp
0x140012358  retn
0x14001235a  mov     qword ptr [rsp+1B0h+var_160], rax
0x14001235f  call    DxgkGetWin32kImportTable
0x140012364  mov     rcx, [rbx]
0x140012367  mov     rax, [rax+8]
0x14001236b  call    _guard_dispatch_icall
0x140012370  cmp     eax, 1
0x140012373  jg      loc_140012282
0x140012379  mov     ecx, 1
0x14001237e  call    cs:__imp_WdLogSingleEntry0
0x140012385  nop     dword ptr [rax+rax+00h]
0x14001238a  mov     [rsp+40h], r13
0x14001238f  lea     r9, aNewrefcount1; "newRefCount > 1"
0x140012396  mov     [rsp+1B0h+var_178], r13
0x14001239b  mov     edx, 40002h
0x1400123a0  mov     [rsp+1B0h+var_180], r13
0x1400123a5  xor     ecx, ecx
0x1400123a7  mov     [rsp+1B0h+var_188], r13
0x1400123ac  mov     r8d, 0FFFFFFFFh
0x1400123b2  mov     [rsp+1B0h+var_190], 64h ; 'd'
0x1400123bb  mov     cs:WdLogGlobalForLineNumber, 64h ; 'd'
0x1400123c5  call    DxgkLogInternalTriageEvent
0x1400123ca  jmp     loc_140012282
0x1400123cf  mov     [rsp+1B0h+var_18], rdi
0x1400123d7  call    cs:__imp_PsGetCurrentProcess
0x1400123de  nop     dword ptr [rax+rax+00h]
0x1400123e3  mov     rcx, rax
0x1400123e6  call    cs:__imp_PsGetProcessSessionIdEx
0x1400123ed  nop     dword ptr [rax+rax+00h]
0x1400123f2  mov     edi, eax
0x1400123f4  call    cs:__imp_PsGetCurrentThreadProcess
0x1400123fb  nop     dword ptr [rax+rax+00h]
0x140012400  mov     rcx, rax
0x140012403  call    cs:__imp_PsGetProcessSessionIdEx
0x14001240a  nop     dword ptr [rax+rax+00h]
0x14001240f  cmp     edi, eax
0x140012411  mov     rdi, [rsp+1B0h+var_18]
0x140012419  jz      loc_140012272
0x14001241f  jmp     loc_140012282
0x140012424  mov     rcx, gs:188h
0x14001242d  lea     r8, [rsp+1B0h+var_160]
0x140012432  xor     edx, edx
0x140012434  call    cs:__imp_PsSetThreadWin32Thread
0x14001243b  nop     dword ptr [rax+rax+00h]
0x140012440  jmp     loc_1400122FD
0x140012445  mov     rcx, [rbp+0B0h+PROCESS]; PROCESS
0x140012449  lea     rdx, [rbp+0B0h+ApcState]; ApcState
0x14001244d  call    cs:__imp_KeStackAttachProcess
0x140012454  nop     dword ptr [rax+rax+00h]
0x140012459  mov     [rbp+0B0h+var_A0], 1
0x14001245d  jmp     loc_14001222B
0x140012462  lea     rcx, [rsp+70h]
0x140012467  call    cs:__imp_ExInitializeFastOwnerEntry
0x14001246e  nop     dword ptr [rax+rax+00h]
0x140012473  lea     rcx, [rbp+0B0h+var_F8]
0x140012477  call    cs:__imp_ExInitializeFastOwnerEntry
0x14001247e  nop     dword ptr [rax+rax+00h]
0x140012483  or      dword ptr [rsp+1B0h+var_148], 1
0x140012488  lea     rdx, [rsp+1B0h+var_160]
0x14001248d  mov     rcx, gs:188h
0x140012496  xor     r8d, r8d
0x140012499  call    cs:__imp_PsSetThreadWin32Thread
0x1400124a0  nop     dword ptr [rax+rax+00h]
0x1400124a5  mov     [rbp+0B0h+var_B0], 1
0x1400124a9  jmp     loc_140012282
0x1400124ae  mov     ecx, 1
0x1400124b3  call    cs:__imp_WdLogSingleEntry0
0x1400124ba  nop     dword ptr [rax+rax+00h]
0x1400124bf  mov     [rsp+40h], r13
0x1400124c4  lea     r9, aMPglobalNull; "m_pGlobal != NULL"
0x1400124cb  mov     [rsp+1B0h+var_178], r13
0x1400124d0  mov     edx, 40002h
0x1400124d5  mov     [rsp+1B0h+var_180], r13
0x1400124da  xor     ecx, ecx
0x1400124dc  mov     [rsp+1B0h+var_188], r13
0x1400124e1  mov     r8d, 0FFFFFFFFh
0x1400124e7  mov     [rsp+1B0h+var_190], 0A5Ah
0x1400124f0  mov     cs:WdLogGlobalForLineNumber, 0A5Ah
0x1400124fa  call    DxgkLogInternalTriageEvent
0x1400124ff  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x140012504  jmp     loc_1400122C1
0x140012509  lea     rcx, [rbp+0B0h+ApcState]; ApcState
0x14001250d  call    cs:__imp_KeUnstackDetachProcess
0x140012514  nop     dword ptr [rax+rax+00h]
0x140012519  jmp     loc_140012337
0x14001251e  call    cs:__imp_ObfDereferenceObject
0x140012525  nop     dword ptr [rax+rax+00h]
0x14001252a  jmp     loc_140012344
```
