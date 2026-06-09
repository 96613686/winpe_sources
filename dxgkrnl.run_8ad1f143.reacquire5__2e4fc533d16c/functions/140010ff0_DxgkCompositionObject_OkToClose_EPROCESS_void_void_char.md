# DxgkCompositionObject::OkToClose(_EPROCESS *,void *,void *,char)

- ea: `0x140010ff0`
- end: `0x1400113a0`
- name: `?OkToClose@DxgkCompositionObject@@SAEPEAU_EPROCESS@@PEAX1D@Z`
- size: `944`
- prototype: `unsigned __int8 __fastcall(struct _EPROCESS *, void *, void *, char)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140010ff0`
- `0x140011574`
- `0x140012540`
- `0x14001b9c0`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1403c298c`
- `0x1403e1958`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140011068`
- `ntoskrnl!PsGetCurrentProcess` at `0x140011263`
- `ntoskrnl!PsGetCurrentProcess` at `0x140011068`
- `ntoskrnl!PsGetCurrentProcess` at `0x140011263`
- `ntoskrnl!ObfDereferenceObject` at `0x14001138f`
- `ntoskrnl!ObfDereferenceObject` at `0x14001138f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001137e`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001137e`
- `ntoskrnl!KeStackAttachProcess` at `0x14001124e`
- `ntoskrnl!KeStackAttachProcess` at `0x14001124e`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140011280`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140011280`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140011048`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140011077`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140011272`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001128f`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140011048`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140011077`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140011272`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001128f`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400110c9`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400110c9`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400112c2`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14001130a`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400112c2`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14001130a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400112d8`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400112e8`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400112d8`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400112e8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400110ac`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400110ac`
- `watchdog!WdLogSingleEntry0` at `0x1400111d0`
- `watchdog!WdLogSingleEntry0` at `0x140011324`
- `watchdog!WdLogSingleEntry0` at `0x1400111d0`
- `watchdog!WdLogSingleEntry0` at `0x140011324`

## pseudocode

```c
_BOOL8 __fastcall DxgkCompositionObject::OkToClose(struct _EPROCESS *a1, _DWORD *a2, void *a3, char a4)
{
  unsigned int v4; // eax
  int v9; // ebx
  __int64 CurrentProcess; // rax
  unsigned int v11; // edi
  _QWORD *CurrentThreadWin32Thread; // rax
  _QWORD *v13; // rdi
  bool v14; // bl
  __int64 Win32kImportTable; // rax
  DXGGLOBAL *Global; // rax
  DXGSESSIONMGR *SessionMgr; // rax
  __int64 v19; // rax
  int ProcessSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  int v22; // [rsp+28h] [rbp-E0h]
  _QWORD v23[22]; // [rsp+58h] [rbp-B0h] BYREF
  char v24; // [rsp+108h] [rbp+0h]
  char v25; // [rsp+118h] [rbp+10h]
  PRKPROCESS PROCESS; // [rsp+120h] [rbp+18h] BYREF
  unsigned int v27; // [rsp+128h] [rbp+20h]
  struct _KAPC_STATE ApcState; // [rsp+130h] [rbp+28h] BYREF

  v4 = a2[2];
  v25 = 0;
  PROCESS = 0;
  v27 = v4;
  if ( a4 && (unsigned int)PsGetProcessSessionIdEx(a1) == -1 )
  {
    v9 = -1073741790;
  }
  else
  {
    v9 = 0;
    CurrentProcess = PsGetCurrentProcess();
    v11 = v27;
    if ( (unsigned int)PsGetProcessSessionIdEx(CurrentProcess) != v27 )
    {
      Global = DXGGLOBAL::GetGlobal();
      SessionMgr = DXGGLOBAL::GetSessionMgr(Global);
      v9 = DXGSESSIONMGR::ReferenceSessionCSRSSProcess(SessionMgr, v11, &PROCESS);
      if ( v9 >= 0 )
      {
        KeStackAttachProcess(PROCESS, &ApcState);
        v25 = 1;
      }
    }
    if ( v9 >= 0 )
    {
      memset(v23, 0, sizeof(v23));
      v24 = 0;
      CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
      v13 = CurrentThreadWin32Thread;
      if ( CurrentThreadWin32Thread )
      {
        if ( *CurrentThreadWin32Thread )
        {
          if ( !(unsigned __int8)KeIsAttachedProcess()
            || (v19 = PsGetCurrentProcess(),
                ProcessSessionId = PsGetProcessSessionIdEx(v19),
                CurrentThreadProcess = PsGetCurrentThreadProcess(),
                ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
          {
            if ( *(_DWORD *)(*v13 + 368LL) )
            {
              v23[0] = *v13;
              Win32kImportTable = DxgkGetWin32kImportTable();
              if ( (*(int (__fastcall **)(_QWORD))(Win32kImportTable + 8))(*v13) <= 1 )
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
        ExInitializeFastOwnerEntry(&v23[4]);
        ExInitializeFastOwnerEntry(&v23[13]);
        LODWORD(v23[3]) |= 1u;
        PsSetThreadWin32Thread(KeGetCurrentThread(), v23, 0);
        v24 = 1;
      }
      LOBYTE(v22) = a4;
      v9 = (*(__int64 (__fastcall **)(_QWORD, struct _EPROCESS *, _DWORD *, void *, int))(**((_QWORD **)a2 + 2) + 16LL))(
             *((_QWORD *)a2 + 2),
             a1,
             a2,
             a3,
             v22);
      if ( v24 )
      {
        PsSetThreadWin32Thread(KeGetCurrentThread(), 0, v23);
      }
      else if ( v23[0] )
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
  v14 = v9 >= 0;
  if ( v25 )
    KeUnstackDetachProcess(&ApcState);
  if ( PROCESS )
    ObfDereferenceObject(PROCESS);
  return v14;
}

```

## disassembly

```asm
0x140010ff0  mov     r11, rsp
0x140010ff3  push    rbp
0x140010ff4  push    rbx
0x140010ff5  lea     rbp, [r11-0B8h]
0x140010ffc  sub     rsp, 1A8h
0x140011003  mov     rax, cs:__security_cookie
0x14001100a  xor     rax, rsp
0x14001100d  mov     [rbp+0B0h+var_50], rax
0x140011011  mov     eax, [rdx+8]
0x140011014  mov     [r11-18h], rsi
0x140011018  mov     rsi, rdx
0x14001101b  mov     [r11-28h], r12
0x14001101f  mov     r12, r8
0x140011022  mov     [r11-30h], r13
0x140011026  xor     r13d, r13d
0x140011029  mov     [r11-38h], r14
0x14001102d  movzx   r14d, r9b
0x140011031  mov     [r11-40h], r15
0x140011035  mov     r15, rcx
0x140011038  mov     [rbp+0B0h+var_A0], 0
0x14001103c  mov     [rbp+0B0h+PROCESS], r13
0x140011040  mov     [rbp+0B0h+var_90], eax
0x140011043  test    r9b, r9b
0x140011046  jz      short loc_14001105D
0x140011048  call    cs:__imp_PsGetProcessSessionIdEx
0x14001104f  nop     dword ptr [rax+rax+00h]
0x140011054  cmp     eax, 0FFFFFFFFh
0x140011057  jz      loc_1400112A8
0x14001105d  mov     [rsp+1B0h+var_18], rdi
0x140011065  mov     ebx, r13d
0x140011068  call    cs:__imp_PsGetCurrentProcess
0x14001106f  nop     dword ptr [rax+rax+00h]
0x140011074  mov     rcx, rax
0x140011077  call    cs:__imp_PsGetProcessSessionIdEx
0x14001107e  nop     dword ptr [rax+rax+00h]
0x140011083  mov     edi, [rbp+0B0h+var_90]
0x140011086  cmp     eax, edi
0x140011088  jnz     loc_140011221
0x14001108e  test    ebx, ebx
0x140011090  js      loc_140011145
0x140011096  xor     edx, edx; Val
0x140011098  lea     rcx, [rsp+1B0h+var_160]; void *
0x14001109d  mov     r8d, 0B0h; Size
0x1400110a3  call    memset
0x1400110a8  mov     [rbp+0B0h+var_B0], r13b
0x1400110ac  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400110b3  nop     dword ptr [rax+rax+00h]
0x1400110b8  mov     rdi, rax
0x1400110bb  test    rax, rax
0x1400110be  jz      loc_1400112D3
0x1400110c4  cmp     [rax], r13
0x1400110c7  jz      short loc_1400110ED
0x1400110c9  call    cs:__imp_KeIsAttachedProcess
0x1400110d0  nop     dword ptr [rax+rax+00h]
0x1400110d5  test    al, al
0x1400110d7  jnz     loc_140011263
0x1400110dd  mov     rax, [rdi]
0x1400110e0  cmp     [rax+170h], r13d
0x1400110e7  jnz     loc_1400111AC
0x1400110ed  mov     rcx, [rsi+10h]
0x1400110f1  mov     r9, r12
0x1400110f4  mov     r8, rsi
0x1400110f7  mov     byte ptr [rsp+1B0h+var_190], r14b
0x1400110fc  mov     rdx, r15
0x1400110ff  mov     rax, [rcx]
0x140011102  mov     rax, [rax+10h]
0x140011106  call    _guard_dispatch_icall
0x14001110b  mov     ebx, eax
0x14001110d  cmp     [rbp+0B0h+var_B0], r13b
0x140011111  jnz     loc_1400112B2
0x140011117  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x14001111c  test    rcx, rcx
0x14001111f  jz      short loc_140011145
0x140011121  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, r13; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140011128  jz      loc_14001131F
0x14001112e  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140011135  mov     rdx, [rax+4A748h]
0x14001113c  mov     rax, [rdx+10h]
0x140011140  call    _guard_dispatch_icall
0x140011145  mov     rdi, [rsp+1B0h+var_18]
0x14001114d  mov     r15, [rsp+1B0h+var_38]
0x140011155  mov     r14, [rsp+1B0h+var_30]
0x14001115d  mov     r13, [rsp+1B0h+var_28]
0x140011165  mov     r12, [rsp+1B0h+var_20]
0x14001116d  mov     rsi, [rsp+1A0h]
0x140011175  shr     ebx, 1Fh
0x140011178  xor     bl, 1
0x14001117b  cmp     [rbp+0B0h+var_A0], 0
0x14001117f  jnz     loc_14001137A
0x140011185  mov     rcx, [rbp+0B0h+PROCESS]; Object
0x140011189  test    rcx, rcx
0x14001118c  jnz     loc_14001138F
0x140011192  movzx   eax, bl
0x140011195  mov     rcx, [rbp+0B0h+var_50]
0x140011199  xor     rcx, rsp; StackCookie
0x14001119c  call    __security_check_cookie
0x1400111a1  add     rsp, 1A8h
0x1400111a8  pop     rbx
0x1400111a9  pop     rbp
0x1400111aa  retn
0x1400111ac  mov     qword ptr [rsp+1B0h+var_160], rax
0x1400111b1  call    DxgkGetWin32kImportTable
0x1400111b6  mov     rcx, [rdi]
0x1400111b9  mov     rax, [rax+8]
0x1400111bd  call    _guard_dispatch_icall
0x1400111c2  cmp     eax, 1
0x1400111c5  jg      loc_1400110ED
0x1400111cb  mov     ecx, 1
0x1400111d0  call    cs:__imp_WdLogSingleEntry0
0x1400111d7  nop     dword ptr [rax+rax+00h]
0x1400111dc  mov     [rsp+40h], r13
0x1400111e1  lea     r9, aNewrefcount1; "newRefCount > 1"
0x1400111e8  mov     [rsp+1B0h+var_178], r13
0x1400111ed  mov     edx, 40002h
0x1400111f2  mov     [rsp+1B0h+var_180], r13
0x1400111f7  xor     ecx, ecx
0x1400111f9  mov     [rsp+1B0h+var_188], r13
0x1400111fe  mov     r8d, 0FFFFFFFFh
0x140011204  mov     [rsp+1B0h+var_190], 64h ; 'd'
0x14001120d  mov     cs:WdLogGlobalForLineNumber, 64h ; 'd'
0x140011217  call    DxgkLogInternalTriageEvent
0x14001121c  jmp     loc_1400110ED
0x140011221  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140011226  mov     rcx, rax; this
0x140011229  call    ?GetSessionMgr@DXGGLOBAL@@QEAAPEAVDXGSESSIONMGR@@XZ; DXGGLOBAL::GetSessionMgr(void)
0x14001122e  mov     rcx, rax; this
0x140011231  lea     r8, [rbp+0B0h+PROCESS]; struct _KPROCESS **
0x140011235  mov     edx, edi; unsigned int
0x140011237  call    ?ReferenceSessionCSRSSProcess@DXGSESSIONMGR@@QEAAJKPEAPEAU_KPROCESS@@@Z; DXGSESSIONMGR::ReferenceSessionCSRSSProcess(ulong,_KPROCESS * *)
0x14001123c  mov     ebx, eax
0x14001123e  test    eax, eax
0x140011240  js      loc_14001108E
0x140011246  mov     rcx, [rbp+0B0h+PROCESS]; PROCESS
0x14001124a  lea     rdx, [rbp+0B0h+ApcState]; ApcState
0x14001124e  call    cs:__imp_KeStackAttachProcess
0x140011255  nop     dword ptr [rax+rax+00h]
0x14001125a  mov     [rbp+0B0h+var_A0], 1
0x14001125e  jmp     loc_14001108E
0x140011263  call    cs:__imp_PsGetCurrentProcess
0x14001126a  nop     dword ptr [rax+rax+00h]
0x14001126f  mov     rcx, rax
0x140011272  call    cs:__imp_PsGetProcessSessionIdEx
0x140011279  nop     dword ptr [rax+rax+00h]
0x14001127e  mov     ebx, eax
0x140011280  call    cs:__imp_PsGetCurrentThreadProcess
0x140011287  nop     dword ptr [rax+rax+00h]
0x14001128c  mov     rcx, rax
0x14001128f  call    cs:__imp_PsGetProcessSessionIdEx
0x140011296  nop     dword ptr [rax+rax+00h]
0x14001129b  cmp     ebx, eax
0x14001129d  jz      loc_1400110DD
0x1400112a3  jmp     loc_1400110ED
0x1400112a8  mov     ebx, 0C0000022h
0x1400112ad  jmp     loc_14001114D
0x1400112b2  mov     rcx, gs:188h
0x1400112bb  lea     r8, [rsp+1B0h+var_160]
0x1400112c0  xor     edx, edx
0x1400112c2  call    cs:__imp_PsSetThreadWin32Thread
0x1400112c9  nop     dword ptr [rax+rax+00h]
0x1400112ce  jmp     loc_140011145
0x1400112d3  lea     rcx, [rsp+70h]
0x1400112d8  call    cs:__imp_ExInitializeFastOwnerEntry
0x1400112df  nop     dword ptr [rax+rax+00h]
0x1400112e4  lea     rcx, [rbp+0B0h+var_F8]
0x1400112e8  call    cs:__imp_ExInitializeFastOwnerEntry
0x1400112ef  nop     dword ptr [rax+rax+00h]
0x1400112f4  or      dword ptr [rsp+1B0h+var_148], 1
0x1400112f9  lea     rdx, [rsp+1B0h+var_160]
0x1400112fe  mov     rcx, gs:188h
0x140011307  xor     r8d, r8d
0x14001130a  call    cs:__imp_PsSetThreadWin32Thread
0x140011311  nop     dword ptr [rax+rax+00h]
0x140011316  mov     [rbp+0B0h+var_B0], 1
0x14001131a  jmp     loc_1400110ED
0x14001131f  mov     ecx, 1
0x140011324  call    cs:__imp_WdLogSingleEntry0
0x14001132b  nop     dword ptr [rax+rax+00h]
0x140011330  mov     [rsp+40h], r13
0x140011335  lea     r9, aMPglobalNull; "m_pGlobal != NULL"
0x14001133c  mov     [rsp+1B0h+var_178], r13
0x140011341  mov     edx, 40002h
0x140011346  mov     [rsp+1B0h+var_180], r13
0x14001134b  xor     ecx, ecx
0x14001134d  mov     [rsp+1B0h+var_188], r13
0x140011352  mov     r8d, 0FFFFFFFFh
0x140011358  mov     [rsp+1B0h+var_190], 0A5Ah
0x140011361  mov     cs:WdLogGlobalForLineNumber, 0A5Ah
0x14001136b  call    DxgkLogInternalTriageEvent
0x140011370  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x140011375  jmp     loc_14001112E
0x14001137a  lea     rcx, [rbp+0B0h+ApcState]; ApcState
0x14001137e  call    cs:__imp_KeUnstackDetachProcess
0x140011385  nop     dword ptr [rax+rax+00h]
0x14001138a  jmp     loc_140011185
0x14001138f  call    cs:__imp_ObfDereferenceObject
0x140011396  nop     dword ptr [rax+rax+00h]
0x14001139b  jmp     loc_140011192
```
