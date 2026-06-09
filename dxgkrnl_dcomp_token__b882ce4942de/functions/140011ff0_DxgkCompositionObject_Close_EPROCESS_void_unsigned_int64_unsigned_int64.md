# DxgkCompositionObject::Close(_EPROCESS *,void *,unsigned __int64,unsigned __int64)

- ea: `0x140011ff0`
- end: `0x14001236f`
- name: `?Close@DxgkCompositionObject@@SAXPEAU_EPROCESS@@PEAX_K2@Z`
- size: `895`
- prototype: `void __fastcall(struct _EPROCESS *, void *, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400113b4`
- `0x140011ff0`
- `0x140012380`
- `0x14001b890`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x1403c35dc`
- `0x1403e1278`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140012045`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012217`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012045`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012217`
- `ntoskrnl!ObfDereferenceObject` at `0x14001235e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001235e`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001234d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001234d`
- `ntoskrnl!KeStackAttachProcess` at `0x14001228d`
- `ntoskrnl!KeStackAttachProcess` at `0x14001228d`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140012234`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140012234`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140012054`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140012226`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140012243`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140012054`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140012226`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140012243`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001209e`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001209e`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140012274`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400122d9`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140012274`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400122d9`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400122a7`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400122b7`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400122a7`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400122b7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140012081`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140012081`
- `watchdog!WdLogSingleEntry0` at `0x1400121be`
- `watchdog!WdLogSingleEntry0` at `0x1400122f3`
- `watchdog!WdLogSingleEntry0` at `0x1400121be`
- `watchdog!WdLogSingleEntry0` at `0x1400122f3`

## pseudocode

```c
void __fastcall DxgkCompositionObject::Close(struct _EPROCESS *a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // eax
  __int64 CurrentProcess; // rax
  unsigned int v10; // ebx
  _QWORD *CurrentThreadWin32Thread; // rax
  _QWORD *v12; // rbx
  DXGGLOBAL *Global; // rax
  DXGSESSIONMGR *SessionMgr; // rax
  __int64 Win32kImportTable; // rax
  __int64 v16; // rax
  int ProcessSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  _QWORD v19[22]; // [rsp+58h] [rbp-B0h] BYREF
  char v20; // [rsp+108h] [rbp+0h]
  char v21; // [rsp+118h] [rbp+10h]
  PRKPROCESS PROCESS; // [rsp+120h] [rbp+18h] BYREF
  unsigned int v23; // [rsp+128h] [rbp+20h]
  struct _KAPC_STATE ApcState; // [rsp+130h] [rbp+28h] BYREF

  v4 = a2[2];
  PROCESS = 0;
  v21 = 0;
  v23 = v4;
  CurrentProcess = PsGetCurrentProcess();
  v10 = v23;
  if ( (unsigned int)PsGetProcessSessionIdEx(CurrentProcess) != v23 )
  {
    Global = DXGGLOBAL::GetGlobal();
    SessionMgr = DXGGLOBAL::GetSessionMgr(Global);
    if ( (int)DXGSESSIONMGR::ReferenceSessionCSRSSProcess(SessionMgr, v10, &PROCESS) < 0 )
      goto LABEL_12;
    KeStackAttachProcess(PROCESS, &ApcState);
    v21 = 1;
  }
  memset(v19, 0, sizeof(v19));
  v20 = 0;
  CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
  v12 = CurrentThreadWin32Thread;
  if ( CurrentThreadWin32Thread )
  {
    if ( *CurrentThreadWin32Thread )
    {
      if ( !(unsigned __int8)KeIsAttachedProcess()
        || (v16 = PsGetCurrentProcess(),
            ProcessSessionId = PsGetProcessSessionIdEx(v16),
            CurrentThreadProcess = PsGetCurrentThreadProcess(),
            ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
      {
        if ( *(_DWORD *)(*v12 + 368LL) )
        {
          v19[0] = *v12;
          Win32kImportTable = DxgkGetWin32kImportTable();
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
    ExInitializeFastOwnerEntry(&v19[4]);
    ExInitializeFastOwnerEntry(&v19[13]);
    LODWORD(v19[3]) |= 1u;
    PsSetThreadWin32Thread(KeGetCurrentThread(), v19, 0);
    v20 = 1;
  }
  (*(void (__fastcall **)(_QWORD, struct _EPROCESS *, _DWORD *, __int64, __int64))(**((_QWORD **)a2 + 2) + 24LL))(
    *((_QWORD *)a2 + 2),
    a1,
    a2,
    a3,
    a4);
  if ( v20 )
  {
    PsSetThreadWin32Thread(KeGetCurrentThread(), 0, v19);
  }
  else if ( v19[0] )
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
  if ( v21 )
    KeUnstackDetachProcess(&ApcState);
  if ( PROCESS )
    ObfDereferenceObject(PROCESS);
}

```

## disassembly

```asm
0x140011ff0  mov     r11, rsp
0x140011ff3  push    rbp
0x140011ff4  lea     rbp, [r11-0B8h]
0x140011ffb  sub     rsp, 1B0h
0x140012002  mov     rax, cs:__security_cookie
0x140012009  xor     rax, rsp
0x14001200c  mov     [rbp+0B0h+var_50], rax
0x140012010  mov     eax, [rdx+8]
0x140012013  mov     [r11-10h], rbx
0x140012017  mov     [r11-18h], rsi
0x14001201b  mov     rsi, rdx
0x14001201e  mov     [r11-28h], r12
0x140012022  mov     r12, r9
0x140012025  mov     [r11-30h], r13
0x140012029  xor     r13d, r13d
0x14001202c  mov     [r11-38h], r14
0x140012030  mov     r14, rcx
0x140012033  mov     [r11-40h], r15
0x140012037  mov     r15, r8
0x14001203a  mov     [rbp+0B0h+PROCESS], r13
0x14001203e  mov     [rbp+0B0h+var_A0], 0
0x140012042  mov     [rbp+0B0h+var_90], eax
0x140012045  call    cs:__imp_PsGetCurrentProcess
0x14001204c  nop     dword ptr [rax+rax+00h]
0x140012051  mov     rcx, rax
0x140012054  call    cs:__imp_PsGetProcessSessionIdEx
0x14001205b  nop     dword ptr [rax+rax+00h]
0x140012060  mov     ebx, [rbp+0B0h+var_90]
0x140012063  cmp     eax, ebx
0x140012065  jnz     loc_14001211A
0x14001206b  xor     edx, edx; Val
0x14001206d  lea     rcx, [rsp+1B0h+var_160]; void *
0x140012072  mov     r8d, 0B0h; Size
0x140012078  call    memset
0x14001207d  mov     [rbp+0B0h+var_B0], r13b
0x140012081  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140012088  nop     dword ptr [rax+rax+00h]
0x14001208d  mov     rbx, rax
0x140012090  test    rax, rax
0x140012093  jz      loc_1400122A2
0x140012099  cmp     [rax], r13
0x14001209c  jz      short loc_1400120C2
0x14001209e  call    cs:__imp_KeIsAttachedProcess
0x1400120a5  nop     dword ptr [rax+rax+00h]
0x1400120aa  test    al, al
0x1400120ac  jnz     loc_14001220F
0x1400120b2  mov     rax, [rbx]
0x1400120b5  cmp     [rax+170h], r13d
0x1400120bc  jnz     loc_14001219A
0x1400120c2  mov     rcx, [rsi+10h]
0x1400120c6  mov     r9, r15
0x1400120c9  mov     r8, rsi
0x1400120cc  mov     [rsp+1B0h+var_190], r12
0x1400120d1  mov     rdx, r14
0x1400120d4  mov     rax, [rcx]
0x1400120d7  mov     rax, [rax+18h]
0x1400120db  call    _guard_dispatch_icall
0x1400120e0  cmp     [rbp+0B0h+var_B0], r13b
0x1400120e4  jnz     loc_140012264
0x1400120ea  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x1400120ef  test    rcx, rcx
0x1400120f2  jz      short loc_14001213D
0x1400120f4  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, r13; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x1400120fb  jz      loc_1400122EE
0x140012101  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140012108  mov     rdx, [rax+4A748h]
0x14001210f  mov     rax, [rdx+10h]
0x140012113  call    _guard_dispatch_icall
0x140012118  jmp     short loc_14001213D
0x14001211a  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14001211f  mov     rcx, rax; this
0x140012122  call    ?GetSessionMgr@DXGGLOBAL@@QEAAPEAVDXGSESSIONMGR@@XZ; DXGGLOBAL::GetSessionMgr(void)
0x140012127  mov     rcx, rax; this
0x14001212a  lea     r8, [rbp+0B0h+PROCESS]; struct _KPROCESS **
0x14001212e  mov     edx, ebx; unsigned int
0x140012130  call    ?ReferenceSessionCSRSSProcess@DXGSESSIONMGR@@QEAAJKPEAPEAU_KPROCESS@@@Z; DXGSESSIONMGR::ReferenceSessionCSRSSProcess(ulong,_KPROCESS * *)
0x140012135  test    eax, eax
0x140012137  jns     loc_140012285
0x14001213d  cmp     [rbp+0B0h+var_A0], 0
0x140012141  mov     r15, [rsp+1B0h+var_38]
0x140012149  mov     r14, [rsp+1B0h+var_30]
0x140012151  mov     r13, [rsp+1B0h+var_28]
0x140012159  mov     r12, [rsp+1B0h+var_20]
0x140012161  mov     rsi, [rsp+1B0h+var_10]
0x140012169  mov     rbx, [rsp+1A8h]
0x140012171  jnz     loc_140012349
0x140012177  mov     rcx, [rbp+0B0h+PROCESS]; Object
0x14001217b  test    rcx, rcx
0x14001217e  jnz     loc_14001235E
0x140012184  mov     rcx, [rbp+0B0h+var_50]
0x140012188  xor     rcx, rsp; StackCookie
0x14001218b  call    __security_check_cookie
0x140012190  add     rsp, 1B0h
0x140012197  pop     rbp
0x140012198  retn
0x14001219a  mov     qword ptr [rsp+1B0h+var_160], rax
0x14001219f  call    DxgkGetWin32kImportTable
0x1400121a4  mov     rcx, [rbx]
0x1400121a7  mov     rax, [rax+8]
0x1400121ab  call    _guard_dispatch_icall
0x1400121b0  cmp     eax, 1
0x1400121b3  jg      loc_1400120C2
0x1400121b9  mov     ecx, 1
0x1400121be  call    cs:__imp_WdLogSingleEntry0
0x1400121c5  nop     dword ptr [rax+rax+00h]
0x1400121ca  mov     [rsp+40h], r13
0x1400121cf  lea     r9, aNewrefcount1; "newRefCount > 1"
0x1400121d6  mov     [rsp+1B0h+var_178], r13
0x1400121db  mov     edx, 40002h
0x1400121e0  mov     [rsp+1B0h+var_180], r13
0x1400121e5  xor     ecx, ecx
0x1400121e7  mov     [rsp+1B0h+var_188], r13
0x1400121ec  mov     r8d, 0FFFFFFFFh
0x1400121f2  mov     [rsp+1B0h+var_190], 64h ; 'd'
0x1400121fb  mov     cs:WdLogGlobalForLineNumber, 64h ; 'd'
0x140012205  call    DxgkLogInternalTriageEvent
0x14001220a  jmp     loc_1400120C2
0x14001220f  mov     [rsp+1B0h+var_18], rdi
0x140012217  call    cs:__imp_PsGetCurrentProcess
0x14001221e  nop     dword ptr [rax+rax+00h]
0x140012223  mov     rcx, rax
0x140012226  call    cs:__imp_PsGetProcessSessionIdEx
0x14001222d  nop     dword ptr [rax+rax+00h]
0x140012232  mov     edi, eax
0x140012234  call    cs:__imp_PsGetCurrentThreadProcess
0x14001223b  nop     dword ptr [rax+rax+00h]
0x140012240  mov     rcx, rax
0x140012243  call    cs:__imp_PsGetProcessSessionIdEx
0x14001224a  nop     dword ptr [rax+rax+00h]
0x14001224f  cmp     edi, eax
0x140012251  mov     rdi, [rsp+1B0h+var_18]
0x140012259  jz      loc_1400120B2
0x14001225f  jmp     loc_1400120C2
0x140012264  mov     rcx, gs:188h
0x14001226d  lea     r8, [rsp+1B0h+var_160]
0x140012272  xor     edx, edx
0x140012274  call    cs:__imp_PsSetThreadWin32Thread
0x14001227b  nop     dword ptr [rax+rax+00h]
0x140012280  jmp     loc_14001213D
0x140012285  mov     rcx, [rbp+0B0h+PROCESS]; PROCESS
0x140012289  lea     rdx, [rbp+0B0h+ApcState]; ApcState
0x14001228d  call    cs:__imp_KeStackAttachProcess
0x140012294  nop     dword ptr [rax+rax+00h]
0x140012299  mov     [rbp+0B0h+var_A0], 1
0x14001229d  jmp     loc_14001206B
0x1400122a2  lea     rcx, [rsp+70h]
0x1400122a7  call    cs:__imp_ExInitializeFastOwnerEntry
0x1400122ae  nop     dword ptr [rax+rax+00h]
0x1400122b3  lea     rcx, [rbp+0B0h+var_F8]
0x1400122b7  call    cs:__imp_ExInitializeFastOwnerEntry
0x1400122be  nop     dword ptr [rax+rax+00h]
0x1400122c3  or      dword ptr [rsp+1B0h+var_148], 1
0x1400122c8  lea     rdx, [rsp+1B0h+var_160]
0x1400122cd  mov     rcx, gs:188h
0x1400122d6  xor     r8d, r8d
0x1400122d9  call    cs:__imp_PsSetThreadWin32Thread
0x1400122e0  nop     dword ptr [rax+rax+00h]
0x1400122e5  mov     [rbp+0B0h+var_B0], 1
0x1400122e9  jmp     loc_1400120C2
0x1400122ee  mov     ecx, 1
0x1400122f3  call    cs:__imp_WdLogSingleEntry0
0x1400122fa  nop     dword ptr [rax+rax+00h]
0x1400122ff  mov     [rsp+40h], r13
0x140012304  lea     r9, aMPglobalNull; "m_pGlobal != NULL"
0x14001230b  mov     [rsp+1B0h+var_178], r13
0x140012310  mov     edx, 40002h
0x140012315  mov     [rsp+1B0h+var_180], r13
0x14001231a  xor     ecx, ecx
0x14001231c  mov     [rsp+1B0h+var_188], r13
0x140012321  mov     r8d, 0FFFFFFFFh
0x140012327  mov     [rsp+1B0h+var_190], 0A5Ah
0x140012330  mov     cs:WdLogGlobalForLineNumber, 0A5Ah
0x14001233a  call    DxgkLogInternalTriageEvent
0x14001233f  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x140012344  jmp     loc_140012101
0x140012349  lea     rcx, [rbp+0B0h+ApcState]; ApcState
0x14001234d  call    cs:__imp_KeUnstackDetachProcess
0x140012354  nop     dword ptr [rax+rax+00h]
0x140012359  jmp     loc_140012177
0x14001235e  call    cs:__imp_ObfDereferenceObject
0x140012365  nop     dword ptr [rax+rax+00h]
0x14001236a  jmp     loc_140012184
```
