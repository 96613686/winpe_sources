# MRxDAVRefreshTheServerLocks

- ea: `0x1400052a0`
- end: `0x140005481`
- name: `MRxDAVRefreshTheServerLocks`
- size: `481`
- prototype: `void __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001680`
- `0x1400052a0`
- `0x1400059e4`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400053a6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140005401`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400053a6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140005401`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400052bf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005448`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400052bf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005448`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005433`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005465`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005433`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005465`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140005312`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140005312`
- `rdbss!RxCreateRxContext` at `0x1400052f4`
- `rdbss!RxCreateRxContext` at `0x1400052f4`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x1400053ca`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x1400053ca`

## pseudocode

```c
void __fastcall MRxDAVRefreshTheServerLocks(PVOID Context)
{
  struct _RDBSS_DEVICE_OBJECT *v1; // r15
  __int64 *v2; // rdi
  __int64 v3; // rbx
  PRX_CONTEXT RxContext; // rsi
  __int64 *v5; // rbp
  ULONG TimeIncrement; // eax
  __int64 v7; // r9
  ULONG v8; // ecx
  __int64 v9; // r8
  __int128 v10; // rax
  int v11; // r14d
  __int64 v12; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rbx
  HANDLE v17; // rax

  v1 = g_MRxDAVDeviceObject;
  ExAcquireResourceExclusiveLite(&LockTokenEntryListLock, 1u);
  v2 = (__int64 *)LockTokenEntryList;
  if ( (__int64 *)LockTokenEntryList != &LockTokenEntryList )
  {
    while ( 1 )
    {
      v3 = *v2;
      RxContext = RxCreateRxContext(0, v1, 0);
      if ( !RxContext )
        break;
      v5 = v2;
      v2 = (__int64 *)v3;
      TimeIncrement = KeQueryTimeIncrement();
      v7 = *((unsigned int *)v5 + 16);
      v8 = TimeIncrement;
      if ( *((_DWORD *)v5 + 13) )
      {
        v9 = MEMORY[0xFFFFF78000000320] - v5[9];
        v10 = v7 * (0x989680 / TimeIncrement);
        if ( v9 > v7 * (0x989680 / v8) / 2 )
        {
          RxContext->MRxContext[3] = v5;
          v11 = UMRxAsyncEngOuterWrapper(
                  (__int64)RxContext,
                  *((__int64 *)&v10 + 1),
                  v9,
                  0xFu,
                  (__int64 (__fastcall *)(__int64, __int64))MRxDAVRefreshTheServerLocksContinuation,
                  (__int64)"MRxDAVRefreshTheServerLocks");
          if ( v11 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
            {
              v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              CurrentThreadId = PsGetCurrentThreadId();
              WPP_SF_qqL(v12, v14, v15, CurrentThreadId, v5, v11);
            }
          }
        }
      }
      RxDereferenceAndDeleteRxContext_Real(RxContext);
      if ( v2 == &LockTokenEntryList )
        goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v17 = PsGetCurrentThreadId();
      WPP_SF_qD(v16, 40, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v17, -1073741670);
    }
  }
LABEL_14:
  ExReleaseResourceLite(&LockTokenEntryListLock);
  ExAcquireResourceExclusiveLite(&QueueLockRefreshWorkItemLock, 1u);
  QueueLockRefreshWorkItem = 1;
  ExReleaseResourceLite(&QueueLockRefreshWorkItemLock);
}

```

## disassembly

```asm
0x1400052a0  push    rbx
0x1400052a2  push    rbp
0x1400052a3  push    rsi
0x1400052a4  push    rdi
0x1400052a5  push    r13
0x1400052a7  push    r14
0x1400052a9  push    r15
0x1400052ab  sub     rsp, 30h
0x1400052af  mov     r15, cs:g_MRxDAVDeviceObject
0x1400052b6  lea     rcx, LockTokenEntryListLock; Resource
0x1400052bd  mov     dl, 1; Wait
0x1400052bf  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400052c6  nop     dword ptr [rax+rax+00h]
0x1400052cb  mov     rdi, cs:LockTokenEntryList
0x1400052d2  lea     rax, LockTokenEntryList
0x1400052d9  cmp     rdi, rax
0x1400052dc  jz      loc_14000542C
0x1400052e2  lea     r13, WPP_GLOBAL_Control
0x1400052e9  mov     rbx, [rdi]
0x1400052ec  xor     r8d, r8d; InitialContextFlags
0x1400052ef  mov     rdx, r15; RxDeviceObject
0x1400052f2  xor     ecx, ecx; Irp
0x1400052f4  call    cs:__imp_RxCreateRxContext
0x1400052fb  nop     dword ptr [rax+rax+00h]
0x140005300  mov     rsi, rax
0x140005303  test    rax, rax
0x140005306  jz      loc_1400053E8
0x14000530c  mov     rbp, rdi
0x14000530f  mov     rdi, rbx
0x140005312  call    cs:__imp_KeQueryTimeIncrement
0x140005319  nop     dword ptr [rax+rax+00h]
0x14000531e  mov     r9d, [rbp+40h]
0x140005322  mov     r8, 0FFFFF78000000320h
0x14000532c  mov     ecx, eax
0x14000532e  mov     r8, [r8]
0x140005331  cmp     dword ptr [rbp+34h], 0
0x140005335  jz      loc_1400053C7
0x14000533b  sub     r8, [rbp+48h]
0x14000533f  xor     edx, edx
0x140005341  mov     eax, 989680h
0x140005346  div     ecx
0x140005348  imul    rax, r9
0x14000534c  cqo
0x14000534e  sub     rax, rdx
0x140005351  sar     rax, 1
0x140005354  cmp     r8, rax
0x140005357  jle     short loc_1400053C7
0x140005359  lea     rax, aMrxdavrefresht; "MRxDAVRefreshTheServerLocks"
0x140005360  mov     [rsi+0D8h], rbp
0x140005367  mov     [rsp+68h+var_40], rax
0x14000536c  mov     r9d, 0Fh
0x140005372  lea     rax, MRxDAVRefreshTheServerLocksContinuation
0x140005379  mov     rcx, rsi
0x14000537c  mov     [rsp+68h+var_48], rax
0x140005381  call    UMRxAsyncEngOuterWrapper
0x140005386  mov     r14d, eax
0x140005389  test    eax, eax
0x14000538b  jz      short loc_1400053C7
0x14000538d  mov     rbx, cs:WPP_GLOBAL_Control
0x140005394  cmp     rbx, r13
0x140005397  jz      short loc_1400053C7
0x140005399  test    dword ptr [rbx+2Ch], 2000h
0x1400053a0  jz      short loc_1400053C7
0x1400053a2  mov     rbx, [rbx+18h]
0x1400053a6  call    cs:__imp_PsGetCurrentThreadId
0x1400053ad  nop     dword ptr [rax+rax+00h]
0x1400053b2  mov     dword ptr [rsp+68h+var_40], r14d
0x1400053b7  mov     rcx, rbx
0x1400053ba  mov     r9, rax
0x1400053bd  mov     [rsp+68h+var_48], rbp
0x1400053c2  call    WPP_SF_qqL
0x1400053c7  mov     rcx, rsi; RxContext
0x1400053ca  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x1400053d1  nop     dword ptr [rax+rax+00h]
0x1400053d6  lea     rax, LockTokenEntryList
0x1400053dd  cmp     rdi, rax
0x1400053e0  jnz     loc_1400052E9
0x1400053e6  jmp     short loc_14000542C
0x1400053e8  mov     rbx, cs:WPP_GLOBAL_Control
0x1400053ef  cmp     rbx, r13
0x1400053f2  jz      short loc_14000542C
0x1400053f4  test    dword ptr [rbx+2Ch], 2000h
0x1400053fb  jz      short loc_14000542C
0x1400053fd  mov     rbx, [rbx+18h]
0x140005401  call    cs:__imp_PsGetCurrentThreadId
0x140005408  nop     dword ptr [rax+rax+00h]
0x14000540d  mov     edx, 28h ; '('
0x140005412  mov     dword ptr [rsp+68h+var_48], 0C000009Ah
0x14000541a  mov     r9, rax
0x14000541d  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x140005424  mov     rcx, rbx
0x140005427  call    WPP_SF_qD
0x14000542c  lea     rcx, LockTokenEntryListLock; Resource
0x140005433  call    cs:__imp_ExReleaseResourceLite
0x14000543a  nop     dword ptr [rax+rax+00h]
0x14000543f  mov     dl, 1; Wait
0x140005441  lea     rcx, QueueLockRefreshWorkItemLock; Resource
0x140005448  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000544f  nop     dword ptr [rax+rax+00h]
0x140005454  lea     rcx, QueueLockRefreshWorkItemLock; Resource
0x14000545b  mov     cs:QueueLockRefreshWorkItem, 1
0x140005465  call    cs:__imp_ExReleaseResourceLite
0x14000546c  nop     dword ptr [rax+rax+00h]
0x140005471  add     rsp, 30h
0x140005475  pop     r15
0x140005477  pop     r14
0x140005479  pop     r13
0x14000547b  pop     rdi
0x14000547c  pop     rsi
0x14000547d  pop     rbp
0x14000547e  pop     rbx
0x14000547f  retn
```
