# CSingleton<CDimsJobTaskHandler>::Release(void)

- ea: `0x1800020f0`
- end: `0x1800021b0`
- name: `?Release@?$CSingleton@VCDimsJobTaskHandler@@@@UEAAKXZ`
- size: `192`
- prototype: `__int64 __fastcall(CDimsJobTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800020f0`
- `0x1800022f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000215a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000215a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000213e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002175`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000213e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002175`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800021a8`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800021a8`
- `ntdll!RtlAcquireSRWLockShared` at `0x180002194`
- `ntdll!RtlAcquireSRWLockShared` at `0x180002194`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000211f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000211f`

## pseudocode

```c
__int64 __fastcall CSingleton<CDimsJobTaskHandler>::Release(CDimsJobTaskHandler *this)
{
  __int64 v2; // rbp
  char *v3; // rdi
  unsigned __int32 v4; // ebx
  __int64 v6; // rax
  __int64 v7; // rdi

  v2 = *((_QWORD *)this + 1);
  v3 = (char *)&CSingleton<CDimsJobTaskHandler>::sm_rwlock + SHIDWORD((*CSingleton<CDimsJobTaskHandler>::sm_rwlock)[1]);
  RtlAcquireSRWLockExclusive(&v3[*(int *)(*(_QWORD *)v3 + 4LL)]);
  v4 = _InterlockedDecrement((volatile signed __int32 *)this + 15);
  if ( v4 )
  {
    RtlReleaseSRWLockExclusive(&v3[*(int *)(*(_QWORD *)v3 + 4LL)]);
  }
  else
  {
    CDimsJobTaskHandler::~CDimsJobTaskHandler(this);
    LocalFree(this);
    v6 = *(_QWORD *)v3;
    CSingleton<CDimsJobTaskHandler>::sm_singleton = 0;
    RtlReleaseSRWLockExclusive(&v3[*(int *)(v6 + 4)]);
    v7 = v2 + *(int *)(*(_QWORD *)(v2 + 16) + 8LL) + 16LL;
    RtlAcquireSRWLockShared(v7 + *(int *)(*(_QWORD *)v7 + 4LL));
    _InterlockedDecrement((volatile signed __int32 *)(v2 + 8));
    RtlReleaseSRWLockShared(v7 + *(int *)(*(_QWORD *)v7 + 4LL));
  }
  return v4;
}

```

## disassembly

```asm
0x1800020f0  push    rbx
0x1800020f2  push    rbp
0x1800020f3  push    rsi
0x1800020f4  push    rdi
0x1800020f5  sub     rsp, 28h
0x1800020f9  mov     rax, cs:?sm_rwlock@?$CSingleton@VCDimsJobTaskHandler@@@@0U_CRwlock@@A; _CRwlock CSingleton<CDimsJobTaskHandler>::sm_rwlock
0x180002100  mov     rsi, rcx
0x180002103  mov     rbp, [rcx+8]
0x180002107  movsxd  rdi, dword ptr [rax+0Ch]
0x18000210b  lea     rax, ?sm_rwlock@?$CSingleton@VCDimsJobTaskHandler@@@@0U_CRwlock@@A; _CRwlock CSingleton<CDimsJobTaskHandler>::sm_rwlock
0x180002112  add     rdi, rax
0x180002115  mov     rax, [rdi]
0x180002118  movsxd  rcx, dword ptr [rax+4]
0x18000211c  add     rcx, rdi
0x18000211f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002125  mov     ebx, 0FFFFFFFFh
0x18000212a  lock xadd [rsi+3Ch], ebx
0x18000212f  sub     ebx, 1
0x180002132  jz      short loc_18000214F
0x180002134  mov     rax, [rdi]
0x180002137  movsxd  rcx, dword ptr [rax+4]
0x18000213b  add     rcx, rdi
0x18000213e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002144  mov     eax, ebx
0x180002146  add     rsp, 28h
0x18000214a  pop     rdi
0x18000214b  pop     rsi
0x18000214c  pop     rbp
0x18000214d  pop     rbx
0x18000214e  retn
0x18000214f  mov     rcx, rsi; this
0x180002152  call    ??1CDimsJobTaskHandler@@IEAA@XZ; CDimsJobTaskHandler::~CDimsJobTaskHandler(void)
0x180002157  mov     rcx, rsi; hMem
0x18000215a  call    cs:__imp_LocalFree
0x180002160  mov     rax, [rdi]
0x180002163  mov     cs:?sm_singleton@?$CSingleton@VCDimsJobTaskHandler@@@@0PEAVCDimsJobTaskHandler@@EA, 0; CDimsJobTaskHandler * CSingleton<CDimsJobTaskHandler>::sm_singleton
0x18000216e  movsxd  rcx, dword ptr [rax+4]
0x180002172  add     rcx, rdi
0x180002175  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000217b  mov     rax, [rbp+10h]
0x18000217f  movsxd  rdi, dword ptr [rax+8]
0x180002183  add     rdi, 10h
0x180002187  add     rdi, rbp
0x18000218a  mov     rax, [rdi]
0x18000218d  movsxd  rcx, dword ptr [rax+4]
0x180002191  add     rcx, rdi
0x180002194  call    cs:__imp_RtlAcquireSRWLockShared
0x18000219a  lock dec dword ptr [rbp+8]
0x18000219e  mov     rax, [rdi]
0x1800021a1  movsxd  rcx, dword ptr [rax+4]
0x1800021a5  add     rcx, rdi
0x1800021a8  call    cs:__imp_RtlReleaseSRWLockShared
0x1800021ae  jmp     short loc_180002144
```
