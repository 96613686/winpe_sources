# DxgkCompositionObject::Open(_OB_OPEN_REASON,char,_EPROCESS *,void *,ulong *,ulong)

- ea: `0x140010a20`
- end: `0x140010e20`
- name: `?Open@DxgkCompositionObject@@SAJW4_OB_OPEN_REASON@@DPEAU_EPROCESS@@PEAXPEAKK@Z`
- size: `1024`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140010a20`
- `0x1400113b4`
- `0x140012380`
- `0x14001b890`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x1403c35dc`
- `0x1403e1278`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140010aba`
- `ntoskrnl!PsGetCurrentProcess` at `0x140010cd3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140010aba`
- `ntoskrnl!PsGetCurrentProcess` at `0x140010cd3`
- `ntoskrnl!ObfDereferenceObject` at `0x140010e0f`
- `ntoskrnl!ObfDereferenceObject` at `0x140010e0f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140010dfe`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140010dfe`
- `ntoskrnl!KeStackAttachProcess` at `0x140010cbe`
- `ntoskrnl!KeStackAttachProcess` at `0x140010cbe`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140010cf0`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140010cf0`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010a92`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010ac9`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010ce2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010cff`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010a92`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010ac9`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010ce2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010cff`
- `ntoskrnl!KeIsAttachedProcess` at `0x140010b1c`
- `ntoskrnl!KeIsAttachedProcess` at `0x140010b1c`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140010d32`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140010d7a`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140010d32`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140010d7a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140010d48`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140010d58`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140010d48`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140010d58`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010afe`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010afe`
- `ntoskrnl!PsIsSystemProcess` at `0x140010a7f`
- `ntoskrnl!PsIsSystemProcess` at `0x140010a7f`
- `watchdog!WdLogSingleEntry0` at `0x140010c30`
- `watchdog!WdLogSingleEntry0` at `0x140010d94`
- `watchdog!WdLogSingleEntry0` at `0x140010c30`
- `watchdog!WdLogSingleEntry0` at `0x140010d94`

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
  int v11; // eax
  int v12; // ebx
  __int64 CurrentProcess; // rax
  unsigned int v14; // edi
  _QWORD *CurrentThreadWin32Thread; // rax
  _QWORD *v16; // rdi
  __int64 Win32kImportTable; // rax
  DXGGLOBAL *Global; // rax
  DXGSESSIONMGR *SessionMgr; // rax
  __int64 v21; // rax
  int ProcessSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  _QWORD v24[22]; // [rsp+58h] [rbp-B0h] BYREF
  char v25; // [rsp+108h] [rbp+0h]
  char v26; // [rsp+118h] [rbp+10h]
  PRKPROCESS PROCESS; // [rsp+120h] [rbp+18h] BYREF
  unsigned int v28; // [rsp+128h] [rbp+20h]
  struct _KAPC_STATE ApcState; // [rsp+130h] [rbp+28h] BYREF

  v6 = *(_DWORD *)(a4 + 8);
  v26 = 0;
  PROCESS = 0;
  v28 = v6;
  if ( (unsigned __int8)PsIsSystemProcess(a3)
    || (v11 = PsGetProcessSessionIdEx(a3), v11 != -1) && v11 == *(_DWORD *)(a4 + 8) )
  {
    v12 = 0;
    CurrentProcess = PsGetCurrentProcess();
    v14 = v28;
    if ( (unsigned int)PsGetProcessSessionIdEx(CurrentProcess) != v28 )
    {
      Global = DXGGLOBAL::GetGlobal();
      SessionMgr = DXGGLOBAL::GetSessionMgr(Global);
      v12 = DXGSESSIONMGR::ReferenceSessionCSRSSProcess(SessionMgr, v14, &PROCESS);
      if ( v12 >= 0 )
      {
        KeStackAttachProcess(PROCESS, &ApcState);
        v26 = 1;
      }
    }
    if ( v12 >= 0 )
    {
      memset(v24, 0, sizeof(v24));
      v25 = 0;
      CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
      v16 = CurrentThreadWin32Thread;
      if ( CurrentThreadWin32Thread )
      {
        if ( *CurrentThreadWin32Thread )
        {
          if ( !(unsigned __int8)KeIsAttachedProcess()
            || (v21 = PsGetCurrentProcess(),
                ProcessSessionId = PsGetProcessSessionIdEx(v21),
                CurrentThreadProcess = PsGetCurrentThreadProcess(),
                ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
          {
            if ( *(_DWORD *)(*v16 + 368LL) )
            {
              v24[0] = *v16;
              Win32kImportTable = DxgkGetWin32kImportTable();
              if ( (*(int (__fastcall **)(_QWORD))(Win32kImportTable + 8))(*v16) <= 1 )
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
        ExInitializeFastOwnerEntry(&v24[4]);
        ExInitializeFastOwnerEntry(&v24[13]);
        LODWORD(v24[3]) |= 1u;
        PsSetThreadWin32Thread(KeGetCurrentThread(), v24, 0);
        v25 = 1;
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64, __int64, int))(**(_QWORD **)(a4 + 16)
                                                                                              + 8LL))(
              *(_QWORD *)(a4 + 16),
              a1,
              a2,
              a3,
              a4,
              a5,
              a6);
      if ( v25 )
      {
        PsSetThreadWin32Thread(KeGetCurrentThread(), 0, v24);
      }
      else if ( v24[0] )
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
    v12 = -1073741790;
  }
  if ( v26 )
    KeUnstackDetachProcess(&ApcState);
  if ( PROCESS )
    ObfDereferenceObject(PROCESS);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140010a20  mov     r11, rsp
0x140010a23  push    rbp
0x140010a24  push    rbx
0x140010a25  lea     rbp, [r11-0B8h]
0x140010a2c  sub     rsp, 1A8h
0x140010a33  mov     rax, cs:__security_cookie
0x140010a3a  xor     rax, rsp
0x140010a3d  mov     [rbp+0B0h+var_50], rax
0x140010a41  mov     eax, [r9+8]
0x140010a45  mov     [r11-18h], rsi
0x140010a49  mov     rsi, r9
0x140010a4c  mov     [r11-28h], r12
0x140010a50  movzx   r12d, dl
0x140010a54  mov     [r11-30h], r13
0x140010a58  mov     r13, [rbp+0B0h+arg_20]
0x140010a5f  mov     [r11-38h], r14
0x140010a63  mov     r14, r8
0x140010a66  mov     [r11-40h], r15
0x140010a6a  mov     r15d, ecx
0x140010a6d  mov     rcx, r8
0x140010a70  mov     [rbp+0B0h+var_A0], 0
0x140010a74  mov     [rbp+0B0h+PROCESS], 0
0x140010a7c  mov     [rbp+0B0h+var_90], eax
0x140010a7f  call    cs:__imp_PsIsSystemProcess
0x140010a86  nop     dword ptr [rax+rax+00h]
0x140010a8b  test    al, al
0x140010a8d  jnz     short loc_140010AB0
0x140010a8f  mov     rcx, r14
0x140010a92  call    cs:__imp_PsGetProcessSessionIdEx
0x140010a99  nop     dword ptr [rax+rax+00h]
0x140010a9e  cmp     eax, 0FFFFFFFFh
0x140010aa1  jz      loc_140010D18
0x140010aa7  cmp     eax, [rsi+8]
0x140010aaa  jnz     loc_140010D18
0x140010ab0  mov     [rsp+1B0h+var_18], rdi
0x140010ab8  xor     ebx, ebx
0x140010aba  call    cs:__imp_PsGetCurrentProcess
0x140010ac1  nop     dword ptr [rax+rax+00h]
0x140010ac6  mov     rcx, rax
0x140010ac9  call    cs:__imp_PsGetProcessSessionIdEx
0x140010ad0  nop     dword ptr [rax+rax+00h]
0x140010ad5  mov     edi, [rbp+0B0h+var_90]
0x140010ad8  cmp     eax, edi
0x140010ada  jnz     loc_140010C91
0x140010ae0  test    ebx, ebx
0x140010ae2  js      loc_140010BAC
0x140010ae8  xor     edx, edx; Val
0x140010aea  lea     rcx, [rsp+1B0h+var_160]; void *
0x140010aef  mov     r8d, 0B0h; Size
0x140010af5  call    memset
0x140010afa  mov     [rbp+0B0h+var_B0], 0
0x140010afe  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010b05  nop     dword ptr [rax+rax+00h]
0x140010b0a  mov     rdi, rax
0x140010b0d  test    rax, rax
0x140010b10  jz      loc_140010D43
0x140010b16  cmp     qword ptr [rax], 0
0x140010b1a  jz      short loc_140010B40
0x140010b1c  call    cs:__imp_KeIsAttachedProcess
0x140010b23  nop     dword ptr [rax+rax+00h]
0x140010b28  test    al, al
0x140010b2a  jnz     loc_140010CD3
0x140010b30  mov     rax, [rdi]
0x140010b33  cmp     dword ptr [rax+170h], 0
0x140010b3a  jnz     loc_140010C0C
0x140010b40  mov     r10, [rsi+10h]
0x140010b44  mov     r9, r14
0x140010b47  mov     ecx, [rbp+0B0h+arg_28]
0x140010b4d  movzx   r8d, r12b
0x140010b51  mov     dword ptr [rsp+1B0h+var_180], ecx
0x140010b55  mov     edx, r15d
0x140010b58  mov     [rsp+1B0h+var_188], r13
0x140010b5d  mov     rcx, r10
0x140010b60  mov     rax, [r10]
0x140010b63  mov     [rsp+1B0h+var_190], rsi
0x140010b68  mov     rax, [rax+8]
0x140010b6c  call    _guard_dispatch_icall
0x140010b71  cmp     [rbp+0B0h+var_B0], 0
0x140010b75  mov     ebx, eax
0x140010b77  jnz     loc_140010D22
0x140010b7d  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x140010b82  test    rcx, rcx
0x140010b85  jz      short loc_140010BAC
0x140010b87  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, 0; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140010b8f  jz      loc_140010D8F
0x140010b95  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140010b9c  mov     rdx, [rax+4A748h]
0x140010ba3  mov     rax, [rdx+10h]
0x140010ba7  call    _guard_dispatch_icall
0x140010bac  mov     rdi, [rsp+1B0h+var_18]
0x140010bb4  cmp     [rbp+0B0h+var_A0], 0
0x140010bb8  mov     r15, [rsp+1B0h+var_38]
0x140010bc0  mov     r14, [rsp+1B0h+var_30]
0x140010bc8  mov     r13, [rsp+1B0h+var_28]
0x140010bd0  mov     r12, [rsp+1B0h+var_20]
0x140010bd8  mov     rsi, [rsp+1A0h]
0x140010be0  jnz     loc_140010DFA
0x140010be6  mov     rcx, [rbp+0B0h+PROCESS]; Object
0x140010bea  test    rcx, rcx
0x140010bed  jnz     loc_140010E0F
0x140010bf3  mov     eax, ebx
0x140010bf5  mov     rcx, [rbp+0B0h+var_50]
0x140010bf9  xor     rcx, rsp; StackCookie
0x140010bfc  call    __security_check_cookie
0x140010c01  add     rsp, 1A8h
0x140010c08  pop     rbx
0x140010c09  pop     rbp
0x140010c0a  retn
0x140010c0c  mov     qword ptr [rsp+1B0h+var_160], rax
0x140010c11  call    DxgkGetWin32kImportTable
0x140010c16  mov     rcx, [rdi]
0x140010c19  mov     rax, [rax+8]
0x140010c1d  call    _guard_dispatch_icall
0x140010c22  cmp     eax, 1
0x140010c25  jg      loc_140010B40
0x140010c2b  mov     ecx, 1
0x140010c30  call    cs:__imp_WdLogSingleEntry0
0x140010c37  nop     dword ptr [rax+rax+00h]
0x140010c3c  mov     qword ptr [rsp+40h], 0
0x140010c45  lea     r9, aNewrefcount1; "newRefCount > 1"
0x140010c4c  mov     [rsp+1B0h+var_178], 0
0x140010c55  mov     edx, 40002h
0x140010c5a  mov     [rsp+1B0h+var_180], 0
0x140010c63  xor     ecx, ecx
0x140010c65  mov     [rsp+1B0h+var_188], 0
0x140010c6e  mov     r8d, 0FFFFFFFFh
0x140010c74  mov     [rsp+1B0h+var_190], 64h ; 'd'
0x140010c7d  mov     cs:WdLogGlobalForLineNumber, 64h ; 'd'
0x140010c87  call    DxgkLogInternalTriageEvent
0x140010c8c  jmp     loc_140010B40
0x140010c91  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140010c96  mov     rcx, rax; this
0x140010c99  call    ?GetSessionMgr@DXGGLOBAL@@QEAAPEAVDXGSESSIONMGR@@XZ; DXGGLOBAL::GetSessionMgr(void)
0x140010c9e  mov     rcx, rax; this
0x140010ca1  lea     r8, [rbp+0B0h+PROCESS]; struct _KPROCESS **
0x140010ca5  mov     edx, edi; unsigned int
0x140010ca7  call    ?ReferenceSessionCSRSSProcess@DXGSESSIONMGR@@QEAAJKPEAPEAU_KPROCESS@@@Z; DXGSESSIONMGR::ReferenceSessionCSRSSProcess(ulong,_KPROCESS * *)
0x140010cac  mov     ebx, eax
0x140010cae  test    eax, eax
0x140010cb0  js      loc_140010AE0
0x140010cb6  mov     rcx, [rbp+0B0h+PROCESS]; PROCESS
0x140010cba  lea     rdx, [rbp+0B0h+ApcState]; ApcState
0x140010cbe  call    cs:__imp_KeStackAttachProcess
0x140010cc5  nop     dword ptr [rax+rax+00h]
0x140010cca  mov     [rbp+0B0h+var_A0], 1
0x140010cce  jmp     loc_140010AE0
0x140010cd3  call    cs:__imp_PsGetCurrentProcess
0x140010cda  nop     dword ptr [rax+rax+00h]
0x140010cdf  mov     rcx, rax
0x140010ce2  call    cs:__imp_PsGetProcessSessionIdEx
0x140010ce9  nop     dword ptr [rax+rax+00h]
0x140010cee  mov     ebx, eax
0x140010cf0  call    cs:__imp_PsGetCurrentThreadProcess
0x140010cf7  nop     dword ptr [rax+rax+00h]
0x140010cfc  mov     rcx, rax
0x140010cff  call    cs:__imp_PsGetProcessSessionIdEx
0x140010d06  nop     dword ptr [rax+rax+00h]
0x140010d0b  cmp     ebx, eax
0x140010d0d  jz      loc_140010B30
0x140010d13  jmp     loc_140010B40
0x140010d18  mov     ebx, 0C0000022h
0x140010d1d  jmp     loc_140010BB4
0x140010d22  mov     rcx, gs:188h
0x140010d2b  lea     r8, [rsp+1B0h+var_160]
0x140010d30  xor     edx, edx
0x140010d32  call    cs:__imp_PsSetThreadWin32Thread
0x140010d39  nop     dword ptr [rax+rax+00h]
0x140010d3e  jmp     loc_140010BAC
0x140010d43  lea     rcx, [rsp+70h]
0x140010d48  call    cs:__imp_ExInitializeFastOwnerEntry
0x140010d4f  nop     dword ptr [rax+rax+00h]
0x140010d54  lea     rcx, [rbp+0B0h+var_F8]
0x140010d58  call    cs:__imp_ExInitializeFastOwnerEntry
0x140010d5f  nop     dword ptr [rax+rax+00h]
0x140010d64  or      dword ptr [rsp+1B0h+var_148], 1
0x140010d69  lea     rdx, [rsp+1B0h+var_160]
0x140010d6e  mov     rcx, gs:188h
0x140010d77  xor     r8d, r8d
0x140010d7a  call    cs:__imp_PsSetThreadWin32Thread
0x140010d81  nop     dword ptr [rax+rax+00h]
0x140010d86  mov     [rbp+0B0h+var_B0], 1
0x140010d8a  jmp     loc_140010B40
0x140010d8f  mov     ecx, 1
0x140010d94  call    cs:__imp_WdLogSingleEntry0
0x140010d9b  nop     dword ptr [rax+rax+00h]
0x140010da0  mov     qword ptr [rsp+40h], 0
0x140010da9  lea     r9, aMPglobalNull; "m_pGlobal != NULL"
0x140010db0  mov     [rsp+1B0h+var_178], 0
0x140010db9  mov     edx, 40002h
0x140010dbe  mov     [rsp+1B0h+var_180], 0
0x140010dc7  xor     ecx, ecx
0x140010dc9  mov     [rsp+1B0h+var_188], 0
0x140010dd2  mov     r8d, 0FFFFFFFFh
0x140010dd8  mov     [rsp+1B0h+var_190], 0A5Ah
0x140010de1  mov     cs:WdLogGlobalForLineNumber, 0A5Ah
0x140010deb  call    DxgkLogInternalTriageEvent
0x140010df0  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x140010df5  jmp     loc_140010B95
0x140010dfa  lea     rcx, [rbp+0B0h+ApcState]; ApcState
0x140010dfe  call    cs:__imp_KeUnstackDetachProcess
0x140010e05  nop     dword ptr [rax+rax+00h]
0x140010e0a  jmp     loc_140010BE6
0x140010e0f  call    cs:__imp_ObfDereferenceObject
0x140010e16  nop     dword ptr [rax+rax+00h]
0x140010e1b  jmp     loc_140010BF3
```
