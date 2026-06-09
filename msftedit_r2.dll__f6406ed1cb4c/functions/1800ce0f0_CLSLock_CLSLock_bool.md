# CLSLock::CLSLock(bool)

- ea: `0x1800ce0f0`
- end: `0x1800ce1d7`
- name: `??0CLSLock@@QEAA@_N@Z`
- size: `231`
- prototype: `CLSLock *__fastcall(CLSLock *__hidden this, bool)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180012430`
- `0x1800bd190`
- `0x180191e44`

## callees

- `0x1800ce0f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ce171`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ce171`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce17d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce17d`

## pseudocode

```c
CLSLock *__fastcall CLSLock::CLSLock(CLSLock *this, char a2)
{
  int v2; // edi
  struct LOCK_TELEMETRY near **v5; // rax
  RTL_SRWLOCK *v7; // rcx
  DWORD CurrentThreadId; // eax
  bool v9; // cc
  __int64 v10; // rcx
  __int64 v11; // rcx

  v2 = (int)CLockSharedData::LockOwner;
  *(_DWORD *)this = 0;
  if ( !v2 || v2 != GetCurrentThreadId() )
  {
    switch ( *(_DWORD *)this )
    {
      case 0:
        goto LABEL_10;
      case 1:
        v7 = &SRW_PTSLock;
        break;
      case 2:
        v7 = &SRW_IdealHDCLock;
        break;
      default:
LABEL_10:
        v7 = &SRW_RELock;
        break;
    }
    AcquireSRWLockExclusive(v7);
    CurrentThreadId = GetCurrentThreadId();
    v9 = *(_DWORD *)this <= 3u;
    v10 = *(int *)this;
    *((_DWORD *)&CLockSharedData::LockOwner + v10) = CurrentThreadId;
    if ( v9 )
      v11 = (__int64)&dword_1802E474C[4 * v10];
    else
      v11 = 4;
    ++*(_DWORD *)v11;
    goto LABEL_6;
  }
  if ( *(_DWORD *)this > 3u )
    v5 = 0;
  else
    v5 = &CLockSharedData::LockTelemetry + 2 * *(int *)this;
  ++*(_DWORD *)v5;
LABEL_6:
  *((_BYTE *)this + 4) = a2;
  if ( a2 )
    ++CLSLock::_cOLSBusy;
  return this;
}

```

## disassembly

```asm
0x1800ce0f0  mov     [rsp+arg_0], rbx
0x1800ce0f5  mov     [rsp+arg_8], rsi
0x1800ce0fa  push    rdi
0x1800ce0fb  sub     rsp, 20h
0x1800ce0ff  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800ce105  mov     sil, dl
0x1800ce108  mov     dword ptr [rcx], 0
0x1800ce10e  mov     rbx, rcx
0x1800ce111  test    edi, edi
0x1800ce113  jz      short loc_1800CE164
0x1800ce115  call    cs:__imp_GetCurrentThreadId
0x1800ce11c  nop     dword ptr [rax+rax+00h]
0x1800ce121  cmp     edi, eax
0x1800ce123  jnz     short loc_1800CE164
0x1800ce125  cmp     dword ptr [rbx], 3
0x1800ce128  ja      loc_1800CE1C0
0x1800ce12e  movsxd  rax, dword ptr [rbx]
0x1800ce131  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800ce138  shl     rax, 4
0x1800ce13c  add     rax, rcx
0x1800ce13f  inc     dword ptr [rax]
0x1800ce141  mov     [rbx+4], sil
0x1800ce145  test    sil, sil
0x1800ce148  jz      short loc_1800CE150
0x1800ce14a  inc     cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x1800ce150  mov     rsi, [rsp+28h+arg_8]
0x1800ce155  mov     rax, rbx
0x1800ce158  mov     rbx, [rsp+28h+arg_0]
0x1800ce15d  add     rsp, 20h
0x1800ce161  pop     rdi
0x1800ce162  retn
0x1800ce164  mov     ecx, [rbx]
0x1800ce166  test    ecx, ecx
0x1800ce168  jnz     short loc_1800CE1AD
0x1800ce16a  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800ce171  call    cs:__imp_AcquireSRWLockExclusive
0x1800ce178  nop     dword ptr [rax+rax+00h]
0x1800ce17d  call    cs:__imp_GetCurrentThreadId
0x1800ce184  nop     dword ptr [rax+rax+00h]
0x1800ce189  cmp     dword ptr [rbx], 3
0x1800ce18c  lea     rdx, ?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800ce193  movsxd  rcx, dword ptr [rbx]
0x1800ce196  mov     [rdx+rcx*4], eax
0x1800ce199  ja      short loc_1800CE1C7
0x1800ce19b  shl     rcx, 4
0x1800ce19f  lea     rax, dword_1802E474C
0x1800ce1a6  add     rcx, rax
0x1800ce1a9  inc     dword ptr [rcx]
0x1800ce1ab  jmp     short loc_1800CE141
0x1800ce1ad  sub     ecx, 1
0x1800ce1b0  jz      short loc_1800CE1CE
0x1800ce1b2  cmp     ecx, 1
0x1800ce1b5  jnz     short loc_1800CE16A
0x1800ce1b7  lea     rcx, ?SRW_IdealHDCLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SRW_IdealHDCLock
0x1800ce1be  jmp     short loc_1800CE171
0x1800ce1c0  xor     eax, eax
0x1800ce1c2  jmp     loc_1800CE13F
0x1800ce1c7  mov     ecx, 4
0x1800ce1cc  jmp     short loc_1800CE1A9
0x1800ce1ce  lea     rcx, ?SRW_PTSLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SRW_PTSLock
0x1800ce1d5  jmp     short loc_1800CE171
```
