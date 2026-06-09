# CMeasurerLS::GetPols(void)

- ea: `0x180012270`
- end: `0x180012427`
- name: `?GetPols@CMeasurerLS@@QEAAPEAUols@Ptls6@@XZ`
- size: `439`
- prototype: `struct Ptls6::ols *__fastcall(CMeasurerLS *__hidden this)`
- caller_count: `6`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18002bf6c`
- `0x18003b04c`
- `0x180058efc`
- `0x18005928c`
- `0x1800943dc`
- `0x180191eb8`

## callees

- `0x18001189c`
- `0x180012270`
- `0x180012430`
- `0x180057560`
- `0x1800dda98`
- `0x1801023d8`
- `0x18013d268`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001238e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001238e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012364`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800122d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001239a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800122d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001239a`

## pseudocode

```c
struct Ptls6::ols *__fastcall CMeasurerLS::GetPols(CMeasurerLS *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdi
  int v4; // ebx
  Ptls6::ols **v5; // rbx
  Ptls6::ols *v6; // rax
  unsigned int v7; // edx
  CMeasurerNoFC *v8; // rcx
  Ptls6::ols *v9; // rbx
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  Ptls6::ols *v13; // rax

  if ( !*(_QWORD *)this )
    return 0;
  v2 = *(_QWORD *)(*(_QWORD *)this + 16LL);
  if ( !v2 )
    return 0;
  v3 = *(_QWORD *)(v2 + 40);
  if ( !v3 || CLSLock::_fNoLS || (*(_BYTE *)(v3 + 358) & 1) == 0 )
    return 0;
  v4 = (int)CLockSharedData::LockOwner;
  if ( (_DWORD)CLockSharedData::LockOwner && v4 == GetCurrentThreadId() )
  {
    LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry + 1;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    CurrentThreadId = GetCurrentThreadId();
    ++dword_1802E474C[0];
    LODWORD(CLockSharedData::LockOwner) = CurrentThreadId;
  }
  v5 = (Ptls6::ols **)(v3 + 616);
  if ( (*(_DWORD *)(v3 + 184) & 0x40000000) == 0 )
    v5 = &CLSLock::_pols;
  v6 = *v5;
  if ( *v5 )
    goto LABEL_12;
  if ( (*(_DWORD *)(v3 + 184) & 0x40000000) != 0 )
  {
    *v5 = 0;
  }
  else
  {
    v13 = (Ptls6::ols *)operator new(0x420u);
    v6 = (Ptls6::ols *)Ptls6::ols::ols(v13);
    *v5 = v6;
    if ( v6 )
    {
LABEL_12:
      *((_OWORD *)this + 3) = *(_OWORD *)((char *)v6 + 56);
      *((_QWORD *)this + 8) = *((_QWORD *)v6 + 9);
      if ( (unsigned int)Ptls6::ols::Init(*v5, this) )
      {
        if ( (*(_DWORD *)(v3 + 184) & 0x40000000) == 0 && *v5 )
          Ptls6::ols::`scalar deleting destructor'(*v5, v7);
        *v5 = 0;
      }
      v8 = *(CMeasurerNoFC **)this;
      *((_QWORD *)this + 5) = *v5;
      CMeasurerNoFC::UpdatePF(v8);
    }
  }
  v9 = *v5;
  if ( (int)CLockSharedData::LockTelemetry > 0 )
  {
    LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry - 1;
  }
  else
  {
    LODWORD(CLockSharedData::LockOwner) = 0;
    ReleaseSRWLockExclusive(&SRW_RELock);
  }
  return v9;
}

```

## disassembly

```asm
0x180012270  mov     [rsp+arg_0], rbx
0x180012275  mov     [rsp+arg_8], rsi
0x18001227a  push    rdi
0x18001227b  sub     rsp, 20h
0x18001227f  mov     rax, [rcx]
0x180012282  mov     rsi, rcx
0x180012285  test    rax, rax
0x180012288  jz      loc_1800123C1
0x18001228e  mov     rdi, [rax+10h]
0x180012292  test    rdi, rdi
0x180012295  jz      loc_1800123C1
0x18001229b  mov     rdi, [rdi+28h]
0x18001229f  test    rdi, rdi
0x1800122a2  jz      loc_1800123C1
0x1800122a8  cmp     cs:?_fNoLS@CLSLock@@1_NA, 0; bool CLSLock::_fNoLS
0x1800122af  jnz     loc_1800123C1
0x1800122b5  test    byte ptr [rdi+166h], 1
0x1800122bc  jz      loc_1800123C1
0x1800122c2  mov     ebx, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800122c8  test    ebx, ebx
0x1800122ca  jz      loc_180012384
0x1800122d0  call    cs:__imp_GetCurrentThreadId
0x1800122d7  nop     dword ptr [rax+rax+00h]
0x1800122dc  cmp     ebx, eax
0x1800122de  jnz     loc_180012384
0x1800122e4  inc     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800122ea  mov     ecx, [rdi+0B8h]
0x1800122f0  lea     rbx, [rdi+268h]
0x1800122f7  shr     ecx, 1Eh
0x1800122fa  and     cl, 1
0x1800122fd  jnz     short loc_180012306
0x1800122ff  lea     rbx, ?_pols@CLSLock@@1PEAUols@Ptls6@@EA; Ptls6::ols * CLSLock::_pols
0x180012306  mov     rax, [rbx]
0x180012309  test    rax, rax
0x18001230c  jz      loc_1800123C5
0x180012312  movups  xmm0, xmmword ptr [rax+38h]
0x180012316  mov     rdx, rsi; struct CMeasurerLS *
0x180012319  movups  xmmword ptr [rsi+30h], xmm0
0x18001231d  movsd   xmm1, qword ptr [rax+48h]
0x180012322  movsd   qword ptr [rsi+40h], xmm1
0x180012327  mov     rcx, [rbx]; this
0x18001232a  call    ?Init@ols@Ptls6@@QEAAJAEBVCMeasurerLS@@@Z; Ptls6::ols::Init(CMeasurerLS const &)
0x18001232f  test    eax, eax
0x180012331  jnz     loc_180012401
0x180012337  mov     rax, [rbx]
0x18001233a  mov     rcx, [rsi]; this
0x18001233d  mov     [rsi+28h], rax
0x180012341  call    ?UpdatePF@CMeasurerNoFC@@QEAAXXZ; CMeasurerNoFC::UpdatePF(void)
0x180012346  mov     eax, cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18001234c  mov     rbx, [rbx]
0x18001234f  test    eax, eax
0x180012351  jg      short loc_1800123B7
0x180012353  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001235a  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, 0; uint near * CLockSharedData::LockOwner
0x180012364  call    cs:__imp_ReleaseSRWLockExclusive
0x18001236b  nop     dword ptr [rax+rax+00h]
0x180012370  mov     rax, rbx
0x180012373  mov     rbx, [rsp+28h+arg_0]
0x180012378  mov     rsi, [rsp+28h+arg_8]
0x18001237d  add     rsp, 20h
0x180012381  pop     rdi
0x180012382  retn
0x180012384  xor     ecx, ecx
0x180012386  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18001238b  mov     rcx, rax; SRWLock
0x18001238e  call    cs:__imp_AcquireSRWLockExclusive
0x180012395  nop     dword ptr [rax+rax+00h]
0x18001239a  call    cs:__imp_GetCurrentThreadId
0x1800123a1  nop     dword ptr [rax+rax+00h]
0x1800123a6  inc     cs:dword_1802E474C
0x1800123ac  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x1800123b2  jmp     loc_1800122EA
0x1800123b7  dec     eax
0x1800123b9  mov     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A, eax; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800123bf  jmp     short loc_180012370
0x1800123c1  xor     eax, eax
0x1800123c3  jmp     short loc_180012373
0x1800123c5  test    cl, cl
0x1800123c7  jnz     short loc_1800123F5
0x1800123c9  test    rax, rax
0x1800123cc  jnz     loc_180012312
0x1800123d2  mov     ecx, 420h; Size
0x1800123d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800123dc  mov     rcx, rax; this
0x1800123df  call    ??0ols@Ptls6@@QEAA@XZ; Ptls6::ols::ols(void)
0x1800123e4  mov     [rbx], rax
0x1800123e7  test    rax, rax
0x1800123ea  jz      loc_180012346
0x1800123f0  jmp     loc_180012312
0x1800123f5  mov     qword ptr [rbx], 0
0x1800123fc  jmp     loc_180012346
0x180012401  mov     eax, [rdi+0B8h]
0x180012407  shr     eax, 1Eh
0x18001240a  test    al, 1
0x18001240c  jnz     short loc_18001241B
0x18001240e  mov     rcx, [rbx]; this
0x180012411  test    rcx, rcx
0x180012414  jz      short loc_18001241B
0x180012416  call    ??_Gols@Ptls6@@QEAAPEAXI@Z; Ptls6::ols::`scalar deleting destructor'(uint)
0x18001241b  mov     qword ptr [rbx], 0
0x180012422  jmp     loc_180012337
```
