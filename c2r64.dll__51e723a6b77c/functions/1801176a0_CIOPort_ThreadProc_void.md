# CIOPort::ThreadProc(void *)

- ea: `0x1801176a0`
- end: `0x1801177c9`
- name: `?ThreadProc@CIOPort@@KAKPEAX@Z`
- size: `297`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x1800264b4`
- `0x1801148a0`
- `0x180115394`
- `0x180115550`
- `0x180116ea0`
- `0x1801176a0`
- `0x180146090`

## import_xrefs

- `KERNEL32!Sleep` at `0x180117770`
- `KERNEL32!Sleep` at `0x180117770`
- `KERNEL32!GetThreadIOPendingFlag` at `0x18011775b`
- `KERNEL32!GetThreadIOPendingFlag` at `0x18011775b`
- `KERNEL32!GetCurrentThread` at `0x18011774e`
- `KERNEL32!GetCurrentThread` at `0x18011774e`
- `ADVAPI32!RevertToSelf` at `0x1801176e7`
- `ADVAPI32!RevertToSelf` at `0x1801176e7`

## pseudocode

```c
__int64 __fastcall CIOPort::ThreadProc(volatile signed __int32 *lpThreadParameter)
{
  volatile signed __int32 *v1; // rbx
  struct CThreadState *v2; // r8
  HANDLE CurrentThread; // rax
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  __int128 v7; // [rsp+20h] [rbp-40h] BYREF
  __int64 v8; // [rsp+30h] [rbp-30h]
  int v9; // [rsp+40h] [rbp-20h]
  __int64 v10; // [rsp+48h] [rbp-18h]
  __int64 v11; // [rsp+50h] [rbp-10h]
  int v12; // [rsp+58h] [rbp-8h]
  BOOL IOIsPending; // [rsp+70h] [rbp+10h] BYREF

  v1 = lpThreadParameter;
  _InterlockedIncrement(lpThreadParameter + 6);
  v11 = 0;
  v9 = 0;
  v7 = 0;
  v8 = 0;
  v10 = 0;
  v12 = 0;
  if ( RevertToSelf() && CThreadManager::FSetThreadState(*((CThreadManager **)v1 + 1), (const struct CThreadState *)&v7) )
  {
    *(_QWORD *)&v7 = v1;
    while ( (unsigned int)CIOPort::ProcessItems(v1, &v7) )
      v1 = (volatile signed __int32 *)v7;
    *(_QWORD *)&v7 = 0;
  }
  else
  {
    MsoShipAssertTagProc(507553762);
    CIOPort::FReduceIdleThreadCounter((CIOPort *)v1, 0, v2);
  }
  CThreadManager::FSetThreadState(*((CThreadManager **)v1 + 1), 0);
  IOIsPending = 0;
  while ( (v1[4] & 0x40000000) == 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( !GetThreadIOPendingFlag(CurrentThread, &IOIsPending) || !IOIsPending )
      break;
    Sleep(1u);
  }
  CThreadState::~CThreadState((CThreadState *)&v7);
  v4 = **(_QWORD ***)(*((_QWORD *)v1 + 1) + 336LL);
  while ( v4 )
  {
    v5 = v4[3];
    v4 = (_QWORD *)*v4;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  }
  _InterlockedDecrement(v1 + 6);
  return 0;
}

```

## disassembly

```asm
0x1801176a0  mov     [rsp-8+arg_8], rbx
0x1801176a5  mov     [rsp-8+arg_10], rdi
0x1801176aa  push    rbp
0x1801176ab  mov     rbp, rsp
0x1801176ae  sub     rsp, 60h
0x1801176b2  mov     rbx, rcx
0x1801176b5  lock inc dword ptr [rcx+18h]
0x1801176b9  mov     [rbp+var_10], 0
0x1801176c1  mov     [rbp+var_20], 0
0x1801176c8  xorps   xmm0, xmm0
0x1801176cb  movdqa  [rbp+var_40], xmm0
0x1801176d0  mov     [rbp+var_30], 0
0x1801176d8  mov     [rbp+var_18], 0
0x1801176e0  mov     [rbp+var_8], 0
0x1801176e7  call    cs:__imp_RevertToSelf
0x1801176ed  test    eax, eax
0x1801176ef  jz      short loc_180117726
0x1801176f1  lea     rdx, [rbp+var_40]; struct CThreadState *
0x1801176f5  mov     rcx, [rbx+8]; this
0x1801176f9  call    ?FSetThreadState@CThreadManager@@QEBA_NPEBUCThreadState@@@Z; CThreadManager::FSetThreadState(CThreadState const *)
0x1801176fe  test    al, al
0x180117700  jz      short loc_180117726
0x180117702  mov     qword ptr [rbp+var_40], rbx
0x180117706  jmp     short loc_18011770C
0x180117708  mov     rbx, qword ptr [rbp+var_40]
0x18011770c  lea     rdx, [rbp+var_40]
0x180117710  mov     rcx, rbx
0x180117713  call    ?ProcessItems@CIOPort@@IEAA?AW4eThreadNextStep@@PEAUCThreadState@@@Z; CIOPort::ProcessItems(CThreadState *)
0x180117718  test    eax, eax
0x18011771a  jnz     short loc_180117708
0x18011771c  mov     qword ptr [rbp+var_40], 0
0x180117724  jmp     short loc_18011773A
0x180117726  mov     ecx, 1E40A7E2h
0x18011772b  call    MsoShipAssertTagProc
0x180117730  xor     edx, edx; bool
0x180117732  mov     rcx, rbx; this
0x180117735  call    ?FReduceIdleThreadCounter@CIOPort@@IEAA_N_NPEAUCThreadState@@@Z; CIOPort::FReduceIdleThreadCounter(bool,CThreadState *)
0x18011773a  xor     edx, edx; struct CThreadState *
0x18011773c  mov     rcx, [rbx+8]; this
0x180117740  call    ?FSetThreadState@CThreadManager@@QEBA_NPEBUCThreadState@@@Z; CThreadManager::FSetThreadState(CThreadState const *)
0x180117745  mov     [rbp+IOIsPending], 0
0x18011774c  jmp     short loc_180117776
0x18011774e  call    cs:__imp_GetCurrentThread
0x180117754  mov     rcx, rax; hThread
0x180117757  lea     rdx, [rbp+IOIsPending]; lpIOIsPending
0x18011775b  call    cs:__imp_GetThreadIOPendingFlag
0x180117761  test    eax, eax
0x180117763  jz      short loc_18011777F
0x180117765  cmp     [rbp+IOIsPending], 0
0x180117769  jz      short loc_18011777F
0x18011776b  mov     ecx, 1; dwMilliseconds
0x180117770  call    cs:__imp_Sleep
0x180117776  mov     eax, [rbx+10h]
0x180117779  bt      eax, 1Eh
0x18011777d  jnb     short loc_18011774E
0x18011777f  lea     rcx, [rbp+var_40]; this
0x180117783  call    ??1CThreadState@@QEAA@XZ; CThreadState::~CThreadState(void)
0x180117788  mov     rax, [rbx+8]
0x18011778c  mov     rcx, [rax+150h]
0x180117793  mov     rdi, [rcx]
0x180117796  jmp     short loc_1801177AC
0x180117798  mov     rcx, [rdi+18h]
0x18011779c  mov     rdi, [rdi]
0x18011779f  mov     rax, [rcx]
0x1801177a2  mov     rax, [rax+18h]
0x1801177a6  call    cs:__guard_dispatch_icall_fptr
0x1801177ac  test    rdi, rdi
0x1801177af  jnz     short loc_180117798
0x1801177b1  lock dec dword ptr [rbx+18h]
0x1801177b5  xor     eax, eax
0x1801177b7  lea     r11, [rsp+60h+var_s0]
0x1801177bc  mov     rbx, [r11+18h]
0x1801177c0  mov     rdi, [r11+20h]
0x1801177c4  mov     rsp, r11
0x1801177c7  pop     rbp
0x1801177c8  retn
```
