# DxgkCompositionObject::OkToClose(_EPROCESS *,void *,void *,char)

- ea: `0x140010e30`
- end: `0x1400111e0`
- name: `?OkToClose@DxgkCompositionObject@@SAEPEAU_EPROCESS@@PEAX1D@Z`
- size: `944`
- prototype: `unsigned __int8 __fastcall(struct _EPROCESS *, void *, void *, char)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140010e30`
- `0x1400113b4`
- `0x140012380`
- `0x14001b890`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x1403c35dc`
- `0x1403e1278`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140010ea8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400110a3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140010ea8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400110a3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400111cf`
- `ntoskrnl!ObfDereferenceObject` at `0x1400111cf`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400111be`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400111be`
- `ntoskrnl!KeStackAttachProcess` at `0x14001108e`
- `ntoskrnl!KeStackAttachProcess` at `0x14001108e`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400110c0`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400110c0`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010e88`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010eb7`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400110b2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400110cf`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010e88`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010eb7`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400110b2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400110cf`
- `ntoskrnl!KeIsAttachedProcess` at `0x140010f09`
- `ntoskrnl!KeIsAttachedProcess` at `0x140010f09`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140011102`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14001114a`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140011102`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14001114a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140011118`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140011128`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140011118`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140011128`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010eec`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010eec`
- `watchdog!WdLogSingleEntry0` at `0x140011010`
- `watchdog!WdLogSingleEntry0` at `0x140011164`
- `watchdog!WdLogSingleEntry0` at `0x140011010`
- `watchdog!WdLogSingleEntry0` at `0x140011164`

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
0x140010e30  mov     r11, rsp
0x140010e33  push    rbp
0x140010e34  push    rbx
0x140010e35  lea     rbp, [r11-0B8h]
0x140010e3c  sub     rsp, 1A8h
0x140010e43  mov     rax, cs:__security_cookie
0x140010e4a  xor     rax, rsp
0x140010e4d  mov     [rbp+0B0h+var_50], rax
0x140010e51  mov     eax, [rdx+8]
0x140010e54  mov     [r11-18h], rsi
0x140010e58  mov     rsi, rdx
0x140010e5b  mov     [r11-28h], r12
0x140010e5f  mov     r12, r8
0x140010e62  mov     [r11-30h], r13
0x140010e66  xor     r13d, r13d
0x140010e69  mov     [r11-38h], r14
0x140010e6d  movzx   r14d, r9b
0x140010e71  mov     [r11-40h], r15
0x140010e75  mov     r15, rcx
0x140010e78  mov     [rbp+0B0h+var_A0], 0
0x140010e7c  mov     [rbp+0B0h+PROCESS], r13
0x140010e80  mov     [rbp+0B0h+var_90], eax
0x140010e83  test    r9b, r9b
0x140010e86  jz      short loc_140010E9D
0x140010e88  call    cs:__imp_PsGetProcessSessionIdEx
0x140010e8f  nop     dword ptr [rax+rax+00h]
0x140010e94  cmp     eax, 0FFFFFFFFh
0x140010e97  jz      loc_1400110E8
0x140010e9d  mov     [rsp+1B0h+var_18], rdi
0x140010ea5  mov     ebx, r13d
0x140010ea8  call    cs:__imp_PsGetCurrentProcess
0x140010eaf  nop     dword ptr [rax+rax+00h]
0x140010eb4  mov     rcx, rax
0x140010eb7  call    cs:__imp_PsGetProcessSessionIdEx
0x140010ebe  nop     dword ptr [rax+rax+00h]
0x140010ec3  mov     edi, [rbp+0B0h+var_90]
0x140010ec6  cmp     eax, edi
0x140010ec8  jnz     loc_140011061
0x140010ece  test    ebx, ebx
0x140010ed0  js      loc_140010F85
0x140010ed6  xor     edx, edx; Val
0x140010ed8  lea     rcx, [rsp+1B0h+var_160]; void *
0x140010edd  mov     r8d, 0B0h; Size
0x140010ee3  call    memset
0x140010ee8  mov     [rbp+0B0h+var_B0], r13b
0x140010eec  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010ef3  nop     dword ptr [rax+rax+00h]
0x140010ef8  mov     rdi, rax
0x140010efb  test    rax, rax
0x140010efe  jz      loc_140011113
0x140010f04  cmp     [rax], r13
0x140010f07  jz      short loc_140010F2D
0x140010f09  call    cs:__imp_KeIsAttachedProcess
0x140010f10  nop     dword ptr [rax+rax+00h]
0x140010f15  test    al, al
0x140010f17  jnz     loc_1400110A3
0x140010f1d  mov     rax, [rdi]
0x140010f20  cmp     [rax+170h], r13d
0x140010f27  jnz     loc_140010FEC
0x140010f2d  mov     rcx, [rsi+10h]
0x140010f31  mov     r9, r12
0x140010f34  mov     r8, rsi
0x140010f37  mov     byte ptr [rsp+1B0h+var_190], r14b
0x140010f3c  mov     rdx, r15
0x140010f3f  mov     rax, [rcx]
0x140010f42  mov     rax, [rax+10h]
0x140010f46  call    _guard_dispatch_icall
0x140010f4b  mov     ebx, eax
0x140010f4d  cmp     [rbp+0B0h+var_B0], r13b
0x140010f51  jnz     loc_1400110F2
0x140010f57  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x140010f5c  test    rcx, rcx
0x140010f5f  jz      short loc_140010F85
0x140010f61  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, r13; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140010f68  jz      loc_14001115F
0x140010f6e  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140010f75  mov     rdx, [rax+4A748h]
0x140010f7c  mov     rax, [rdx+10h]
0x140010f80  call    _guard_dispatch_icall
0x140010f85  mov     rdi, [rsp+1B0h+var_18]
0x140010f8d  mov     r15, [rsp+1B0h+var_38]
0x140010f95  mov     r14, [rsp+1B0h+var_30]
0x140010f9d  mov     r13, [rsp+1B0h+var_28]
0x140010fa5  mov     r12, [rsp+1B0h+var_20]
0x140010fad  mov     rsi, [rsp+1A0h]
0x140010fb5  shr     ebx, 1Fh
0x140010fb8  xor     bl, 1
0x140010fbb  cmp     [rbp+0B0h+var_A0], 0
0x140010fbf  jnz     loc_1400111BA
0x140010fc5  mov     rcx, [rbp+0B0h+PROCESS]; Object
0x140010fc9  test    rcx, rcx
0x140010fcc  jnz     loc_1400111CF
0x140010fd2  movzx   eax, bl
0x140010fd5  mov     rcx, [rbp+0B0h+var_50]
0x140010fd9  xor     rcx, rsp; StackCookie
0x140010fdc  call    __security_check_cookie
0x140010fe1  add     rsp, 1A8h
0x140010fe8  pop     rbx
0x140010fe9  pop     rbp
0x140010fea  retn
0x140010fec  mov     qword ptr [rsp+1B0h+var_160], rax
0x140010ff1  call    DxgkGetWin32kImportTable
0x140010ff6  mov     rcx, [rdi]
0x140010ff9  mov     rax, [rax+8]
0x140010ffd  call    _guard_dispatch_icall
0x140011002  cmp     eax, 1
0x140011005  jg      loc_140010F2D
0x14001100b  mov     ecx, 1
0x140011010  call    cs:__imp_WdLogSingleEntry0
0x140011017  nop     dword ptr [rax+rax+00h]
0x14001101c  mov     [rsp+40h], r13
0x140011021  lea     r9, aNewrefcount1; "newRefCount > 1"
0x140011028  mov     [rsp+1B0h+var_178], r13
0x14001102d  mov     edx, 40002h
0x140011032  mov     [rsp+1B0h+var_180], r13
0x140011037  xor     ecx, ecx
0x140011039  mov     [rsp+1B0h+var_188], r13
0x14001103e  mov     r8d, 0FFFFFFFFh
0x140011044  mov     [rsp+1B0h+var_190], 64h ; 'd'
0x14001104d  mov     cs:WdLogGlobalForLineNumber, 64h ; 'd'
0x140011057  call    DxgkLogInternalTriageEvent
0x14001105c  jmp     loc_140010F2D
0x140011061  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140011066  mov     rcx, rax; this
0x140011069  call    ?GetSessionMgr@DXGGLOBAL@@QEAAPEAVDXGSESSIONMGR@@XZ; DXGGLOBAL::GetSessionMgr(void)
0x14001106e  mov     rcx, rax; this
0x140011071  lea     r8, [rbp+0B0h+PROCESS]; struct _KPROCESS **
0x140011075  mov     edx, edi; unsigned int
0x140011077  call    ?ReferenceSessionCSRSSProcess@DXGSESSIONMGR@@QEAAJKPEAPEAU_KPROCESS@@@Z; DXGSESSIONMGR::ReferenceSessionCSRSSProcess(ulong,_KPROCESS * *)
0x14001107c  mov     ebx, eax
0x14001107e  test    eax, eax
0x140011080  js      loc_140010ECE
0x140011086  mov     rcx, [rbp+0B0h+PROCESS]; PROCESS
0x14001108a  lea     rdx, [rbp+0B0h+ApcState]; ApcState
0x14001108e  call    cs:__imp_KeStackAttachProcess
0x140011095  nop     dword ptr [rax+rax+00h]
0x14001109a  mov     [rbp+0B0h+var_A0], 1
0x14001109e  jmp     loc_140010ECE
0x1400110a3  call    cs:__imp_PsGetCurrentProcess
0x1400110aa  nop     dword ptr [rax+rax+00h]
0x1400110af  mov     rcx, rax
0x1400110b2  call    cs:__imp_PsGetProcessSessionIdEx
0x1400110b9  nop     dword ptr [rax+rax+00h]
0x1400110be  mov     ebx, eax
0x1400110c0  call    cs:__imp_PsGetCurrentThreadProcess
0x1400110c7  nop     dword ptr [rax+rax+00h]
0x1400110cc  mov     rcx, rax
0x1400110cf  call    cs:__imp_PsGetProcessSessionIdEx
0x1400110d6  nop     dword ptr [rax+rax+00h]
0x1400110db  cmp     ebx, eax
0x1400110dd  jz      loc_140010F1D
0x1400110e3  jmp     loc_140010F2D
0x1400110e8  mov     ebx, 0C0000022h
0x1400110ed  jmp     loc_140010F8D
0x1400110f2  mov     rcx, gs:188h
0x1400110fb  lea     r8, [rsp+1B0h+var_160]
0x140011100  xor     edx, edx
0x140011102  call    cs:__imp_PsSetThreadWin32Thread
0x140011109  nop     dword ptr [rax+rax+00h]
0x14001110e  jmp     loc_140010F85
0x140011113  lea     rcx, [rsp+70h]
0x140011118  call    cs:__imp_ExInitializeFastOwnerEntry
0x14001111f  nop     dword ptr [rax+rax+00h]
0x140011124  lea     rcx, [rbp+0B0h+var_F8]
0x140011128  call    cs:__imp_ExInitializeFastOwnerEntry
0x14001112f  nop     dword ptr [rax+rax+00h]
0x140011134  or      dword ptr [rsp+1B0h+var_148], 1
0x140011139  lea     rdx, [rsp+1B0h+var_160]
0x14001113e  mov     rcx, gs:188h
0x140011147  xor     r8d, r8d
0x14001114a  call    cs:__imp_PsSetThreadWin32Thread
0x140011151  nop     dword ptr [rax+rax+00h]
0x140011156  mov     [rbp+0B0h+var_B0], 1
0x14001115a  jmp     loc_140010F2D
0x14001115f  mov     ecx, 1
0x140011164  call    cs:__imp_WdLogSingleEntry0
0x14001116b  nop     dword ptr [rax+rax+00h]
0x140011170  mov     [rsp+40h], r13
0x140011175  lea     r9, aMPglobalNull; "m_pGlobal != NULL"
0x14001117c  mov     [rsp+1B0h+var_178], r13
0x140011181  mov     edx, 40002h
0x140011186  mov     [rsp+1B0h+var_180], r13
0x14001118b  xor     ecx, ecx
0x14001118d  mov     [rsp+1B0h+var_188], r13
0x140011192  mov     r8d, 0FFFFFFFFh
0x140011198  mov     [rsp+1B0h+var_190], 0A5Ah
0x1400111a1  mov     cs:WdLogGlobalForLineNumber, 0A5Ah
0x1400111ab  call    DxgkLogInternalTriageEvent
0x1400111b0  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x1400111b5  jmp     loc_140010F6E
0x1400111ba  lea     rcx, [rbp+0B0h+ApcState]; ApcState
0x1400111be  call    cs:__imp_KeUnstackDetachProcess
0x1400111c5  nop     dword ptr [rax+rax+00h]
0x1400111ca  jmp     loc_140010FC5
0x1400111cf  call    cs:__imp_ObfDereferenceObject
0x1400111d6  nop     dword ptr [rax+rax+00h]
0x1400111db  jmp     loc_140010FD2
```
