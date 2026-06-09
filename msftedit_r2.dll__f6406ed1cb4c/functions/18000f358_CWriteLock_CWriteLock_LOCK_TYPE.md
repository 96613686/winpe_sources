# CWriteLock::CWriteLock(LOCK_TYPE)

- ea: `0x18000f358`
- end: `0x18000f422`
- name: `??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `86`
- callee_count: `1`
- tags: ``

## callers

- `0x180007f68`
- `0x18000891c`
- `0x1800095d0`
- `0x180009848`
- `0x180009e4c`
- `0x18000a5bc`
- `0x18000a680`
- `0x18000aa3c`
- `0x18000aebc`
- `0x18000b20c`
- `0x18000e040`
- `0x18000e410`
- `0x18000e490`
- `0x18000e8c0`
- `0x18000ea0c`
- `0x18000ee90`
- `0x18000ef24`
- `0x18000f800`
- `0x180025844`
- `0x18002fa30`
- `0x180036ec4`
- `0x18003e150`
- `0x180043e7c`
- `0x1800440f0`
- `0x180044200`
- `0x180052d00`
- `0x180056298`
- `0x18005674c`
- `0x180056d48`
- `0x180058d30`
- `0x180087310`
- `0x18009d060`
- `0x1800a7c44`
- `0x1800aa25c`
- `0x1800ae0d0`
- `0x1800ae310`
- `0x1800aea10`
- `0x1800b61b0`
- `0x1800c0b20`
- `0x1800cd63c`
- `0x1800dce08`
- `0x1800dce48`
- `0x1800dd018`
- `0x1800dd178`
- `0x1800dd21c`
- `0x1800dd3d0`
- `0x1800dd438`
- `0x1800dd490`
- `0x1800dd6d8`
- `0x1800dd800`

## callees

- `0x18000f358`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f3c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f3c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f37d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f3d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f37d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f3d2`

## pseudocode

```c
unsigned int *__fastcall CWriteLock::CWriteLock(unsigned int *a1, unsigned int a2)
{
  int v3; // edi
  struct LOCK_TELEMETRY near **v4; // rax
  RTL_SRWLOCK *v6; // rcx
  DWORD CurrentThreadId; // eax
  bool v8; // cc
  __int64 v9; // rcx
  __int64 v10; // rcx

  *a1 = a2;
  v3 = *((_DWORD *)&CLockSharedData::LockOwner + (int)a2);
  if ( v3 && v3 == GetCurrentThreadId() )
  {
    if ( *a1 > 3 )
      v4 = 0;
    else
      v4 = &CLockSharedData::LockTelemetry + 2 * (int)*a1;
    ++*(_DWORD *)v4;
    return a1;
  }
  switch ( *a1 )
  {
    case 0u:
      goto LABEL_8;
    case 1u:
      v6 = &SRW_PTSLock;
      break;
    case 2u:
      v6 = &SRW_IdealHDCLock;
      break;
    default:
LABEL_8:
      v6 = &SRW_RELock;
      break;
  }
  AcquireSRWLockExclusive(v6);
  CurrentThreadId = GetCurrentThreadId();
  v8 = *a1 <= 3;
  v9 = (int)*a1;
  *((_DWORD *)&CLockSharedData::LockOwner + v9) = CurrentThreadId;
  if ( v8 )
    v10 = (__int64)&dword_1802E474C[4 * v9];
  else
    v10 = 4;
  ++*(_DWORD *)v10;
  return a1;
}

```

## disassembly

```asm
0x18000f358  mov     [rsp+arg_0], rbx
0x18000f35d  mov     [rsp+arg_8], rsi
0x18000f362  push    rdi
0x18000f363  sub     rsp, 20h
0x18000f367  movsxd  rax, edx
0x18000f36a  lea     rsi, ?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18000f371  mov     rbx, rcx
0x18000f374  mov     [rcx], edx
0x18000f376  mov     edi, [rsi+rax*4]
0x18000f379  test    edi, edi
0x18000f37b  jz      short loc_18000F3B9
0x18000f37d  call    cs:__imp_GetCurrentThreadId
0x18000f384  nop     dword ptr [rax+rax+00h]
0x18000f389  cmp     edi, eax
0x18000f38b  jnz     short loc_18000F3B9
0x18000f38d  cmp     dword ptr [rbx], 3
0x18000f390  ja      short loc_18000F40E
0x18000f392  movsxd  rax, dword ptr [rbx]
0x18000f395  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18000f39c  shl     rax, 4
0x18000f3a0  add     rax, rcx
0x18000f3a3  inc     dword ptr [rax]
0x18000f3a5  mov     rsi, [rsp+28h+arg_8]
0x18000f3aa  mov     rax, rbx
0x18000f3ad  mov     rbx, [rsp+28h+arg_0]
0x18000f3b2  add     rsp, 20h
0x18000f3b6  pop     rdi
0x18000f3b7  retn
0x18000f3b9  mov     ecx, [rbx]
0x18000f3bb  test    ecx, ecx
0x18000f3bd  jnz     short loc_18000F3FB
0x18000f3bf  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000f3c6  call    cs:__imp_AcquireSRWLockExclusive
0x18000f3cd  nop     dword ptr [rax+rax+00h]
0x18000f3d2  call    cs:__imp_GetCurrentThreadId
0x18000f3d9  nop     dword ptr [rax+rax+00h]
0x18000f3de  cmp     dword ptr [rbx], 3
0x18000f3e1  movsxd  rcx, dword ptr [rbx]
0x18000f3e4  mov     [rsi+rcx*4], eax
0x18000f3e7  ja      short loc_18000F412
0x18000f3e9  shl     rcx, 4
0x18000f3ed  lea     rax, dword_1802E474C
0x18000f3f4  add     rcx, rax
0x18000f3f7  inc     dword ptr [rcx]
0x18000f3f9  jmp     short loc_18000F3A5
0x18000f3fb  sub     ecx, 1
0x18000f3fe  jz      short loc_18000F419
0x18000f400  cmp     ecx, 1
0x18000f403  jnz     short loc_18000F3BF
0x18000f405  lea     rcx, ?SRW_IdealHDCLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SRW_IdealHDCLock
0x18000f40c  jmp     short loc_18000F3C6
0x18000f40e  xor     eax, eax
0x18000f410  jmp     short loc_18000F3A3
0x18000f412  mov     ecx, 4
0x18000f417  jmp     short loc_18000F3F7
0x18000f419  lea     rcx, ?SRW_PTSLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SRW_PTSLock
0x18000f420  jmp     short loc_18000F3C6
```
