# CMeasurerLS::CMeasurerLS(CMeasurer &)

- ea: `0x180057068`
- end: `0x1800571ef`
- name: `??0CMeasurerLS@@QEAA@AEAVCMeasurer@@@Z`
- size: `391`
- prototype: `CMeasurerLS *__fastcall(CMeasurerLS *__hidden this, struct CMeasurer *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18002bf6c`
- `0x18003b04c`
- `0x1800943dc`
- `0x180191eb8`

## callees

- `0x180057068`
- `0x180057560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057179`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057179`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800570f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800570f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057185`

## pseudocode

```c
CMeasurerLS *__fastcall CMeasurerLS::CMeasurerLS(CMeasurerLS *this, struct CMeasurer *a2)
{
  __int64 v3; // rax
  bool *v5; // rcx
  __int64 v6; // rdx
  __int64 *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  __int64 v12; // rsi
  int v13; // edi
  struct LOCK_TELEMETRY near **v14; // rax
  int v15; // eax
  CMeasurerLS *result; // rax
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  bool v19; // cc
  __int64 v20; // rcx
  __int64 v21; // rcx

  *(_QWORD *)this = a2;
  v3 = *((_QWORD *)a2 + 2);
  if ( v3 )
    v3 = *(_QWORD *)(v3 + 40);
  v5 = (bool *)this + 16;
  if ( v5 )
    *v5 = 0;
  v6 = *(_QWORD *)(v3 + 256);
  if ( v6 && (v7 = *(__int64 **)(v6 + 80)) != 0 )
  {
    if ( v5 )
      *v5 = (v7[2] & 4) != 0;
    v8 = *v7;
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 1) = v8;
  *((_BYTE *)this + 17) = 0;
  v9 = *((_QWORD *)a2 + 2);
  if ( v9 )
    v9 = *(_QWORD *)(v9 + 40);
  v10 = *(_QWORD *)(v9 + 256);
  if ( v10 && (v11 = *(__int64 **)(v10 + 80)) != 0 )
    v12 = *v11;
  else
    v12 = 0;
  v13 = (int)CLockSharedData::LockOwner;
  *((_DWORD *)this + 6) = 0;
  if ( v13 && v13 == GetCurrentThreadId() )
  {
    if ( *((_DWORD *)this + 6) > 3u )
      v14 = 0;
    else
      v14 = &CLockSharedData::LockTelemetry + 2 * *((int *)this + 6);
    ++*(_DWORD *)v14;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(*((unsigned int *)this + 6));
    AcquireSRWLockExclusive(Lock);
    CurrentThreadId = GetCurrentThreadId();
    v19 = *((_DWORD *)this + 6) <= 3u;
    v20 = *((int *)this + 6);
    *((_DWORD *)&CLockSharedData::LockOwner + v20) = CurrentThreadId;
    if ( v19 )
      v21 = (__int64)&dword_1802E474C[4 * v20];
    else
      v21 = 4;
    ++*(_DWORD *)v21;
  }
  ++CLSLock::_cOLSBusy;
  *((_BYTE *)this + 28) = 1;
  v15 = v12 == 0;
  g_cFCLock += v15;
  *((_DWORD *)this + 8) = v15;
  result = this;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_WORD *)this + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x180057068  mov     [rsp+arg_0], rbx
0x18005706d  mov     [rsp+arg_8], rsi
0x180057072  push    rdi
0x180057073  sub     rsp, 20h
0x180057077  mov     [rcx], rdx
0x18005707a  mov     r8, rdx
0x18005707d  mov     rax, [rdx+10h]
0x180057081  mov     rbx, rcx
0x180057084  test    rax, rax
0x180057087  jz      short loc_18005708D
0x180057089  mov     rax, [rax+28h]
0x18005708d  add     rcx, 10h
0x180057091  jnz     loc_1800571BA
0x180057097  mov     rdx, [rax+100h]
0x18005709e  test    rdx, rdx
0x1800570a1  jz      short loc_1800570B0
0x1800570a3  mov     rdx, [rdx+50h]
0x1800570a7  test    rdx, rdx
0x1800570aa  jnz     loc_1800571D0
0x1800570b0  xor     eax, eax
0x1800570b2  mov     [rbx+8], rax
0x1800570b6  mov     byte ptr [rbx+11h], 0
0x1800570ba  mov     rax, [r8+10h]
0x1800570be  test    rax, rax
0x1800570c1  jz      short loc_1800570C7
0x1800570c3  mov     rax, [rax+28h]
0x1800570c7  mov     rcx, [rax+100h]
0x1800570ce  test    rcx, rcx
0x1800570d1  jz      short loc_1800570E0
0x1800570d3  mov     rax, [rcx+50h]
0x1800570d7  test    rax, rax
0x1800570da  jnz     loc_1800571E7
0x1800570e0  xor     esi, esi
0x1800570e2  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800570e8  mov     dword ptr [rbx+18h], 0
0x1800570ef  test    edi, edi
0x1800570f1  jz      short loc_18005716E
0x1800570f3  call    cs:__imp_GetCurrentThreadId
0x1800570fa  nop     dword ptr [rax+rax+00h]
0x1800570ff  cmp     edi, eax
0x180057101  jnz     short loc_18005716E
0x180057103  cmp     dword ptr [rbx+18h], 3
0x180057107  ja      loc_1800571C2
0x18005710d  movsxd  rax, dword ptr [rbx+18h]
0x180057111  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x180057118  shl     rax, 4
0x18005711c  add     rax, rcx
0x18005711f  inc     dword ptr [rax]
0x180057121  inc     cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x180057127  xor     eax, eax
0x180057129  mov     byte ptr [rbx+1Ch], 1
0x18005712d  test    rsi, rsi
0x180057130  mov     rsi, [rsp+28h+arg_8]
0x180057135  setz    al
0x180057138  add     cs:?g_cFCLock@@3JA, eax; long g_cFCLock
0x18005713e  mov     [rbx+20h], eax
0x180057141  mov     rax, rbx
0x180057144  mov     qword ptr [rbx+28h], 0
0x18005714c  mov     qword ptr [rbx+30h], 0
0x180057154  mov     qword ptr [rbx+38h], 0
0x18005715c  mov     word ptr [rbx+40h], 0
0x180057162  mov     rbx, [rsp+28h+arg_0]
0x180057167  add     rsp, 20h
0x18005716b  pop     rdi
0x18005716c  retn
0x18005716e  mov     ecx, [rbx+18h]
0x180057171  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180057176  mov     rcx, rax; SRWLock
0x180057179  call    cs:__imp_AcquireSRWLockExclusive
0x180057180  nop     dword ptr [rax+rax+00h]
0x180057185  call    cs:__imp_GetCurrentThreadId
0x18005718c  nop     dword ptr [rax+rax+00h]
0x180057191  cmp     dword ptr [rbx+18h], 3
0x180057195  lea     rdx, ?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18005719c  movsxd  rcx, dword ptr [rbx+18h]
0x1800571a0  mov     [rdx+rcx*4], eax
0x1800571a3  ja      short loc_1800571C9
0x1800571a5  shl     rcx, 4
0x1800571a9  lea     rax, dword_1802E474C
0x1800571b0  add     rcx, rax
0x1800571b3  inc     dword ptr [rcx]
0x1800571b5  jmp     loc_180057121
0x1800571ba  mov     byte ptr [rcx], 0
0x1800571bd  jmp     loc_180057097
0x1800571c2  xor     eax, eax
0x1800571c4  jmp     loc_18005711F
0x1800571c9  mov     ecx, 4
0x1800571ce  jmp     short loc_1800571B3
0x1800571d0  test    rcx, rcx
0x1800571d3  jz      short loc_1800571DF
0x1800571d5  mov     eax, [rdx+10h]
0x1800571d8  shr     eax, 2
0x1800571db  and     al, 1
0x1800571dd  mov     [rcx], al
0x1800571df  mov     rax, [rdx]
0x1800571e2  jmp     loc_1800570B2
0x1800571e7  mov     rsi, [rax]
0x1800571ea  jmp     loc_1800570E2
```
