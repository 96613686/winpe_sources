# FltpGetNextNameGenerateNodesForInstance

- ea: `0x18001ee00`
- end: `0x18001ef7e`
- name: `FltpGetNextNameGenerateNodesForInstance`
- size: `382`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eb80`
- `0x18005e010`

## callees

- `0x18001ee00`
- `0x180024c00`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x18001ee31`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x18001ee31`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18001ee86`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18001ee86`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001ee68`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001ee68`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001ef3c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001ef3c`
- `ntoskrnl!ExReleaseFastResource` at `0x18001ef30`
- `ntoskrnl!ExReleaseFastResource` at `0x18001ef30`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x18001ee59`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x18001ee59`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18001ee48`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18001ee48`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18001ef0c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18001ef0c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18001eec6`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18001eeef`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18001eec6`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18001eeef`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001ef59`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001ef59`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x18001ef4d`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x18001ef4d`

## pseudocode

```c
void __fastcall FltpGetNextNameGenerateNodesForInstance(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbp
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // r13
  __int64 v10; // r14
  __int64 v11; // r8
  __int64 *v12; // rbx
  __int64 *v13; // rsi
  __int64 v14; // rdi
  _BYTE v15[152]; // [rsp+20h] [rbp-98h] BYREF

  v6 = 0;
  memset(v15, 0, 0x48u);
  ExInitializeFastOwnerEntry(v15);
  v7 = *(_QWORD *)(a1 + 64);
  v8 = qword_18003E9A0;
  KeEnterGuardedRegion();
  v9 = ExAcquireCacheAwarePushLockSharedEx(v8, 0);
  KeEnterCriticalRegion();
  v10 = v7 + 192;
  LOBYTE(v11) = 1;
  ExAcquireFastResourceShared(v7 + 192, v15, v11);
  v12 = *(__int64 **)(a1 + 16);
  v13 = (__int64 *)(v7 + 296);
  if ( v12 != (__int64 *)(v7 + 296) )
  {
    while ( 1 )
    {
      if ( (v12[8] & 6) == 0 )
      {
        v6 = v12[37];
        if ( v6 )
        {
          if ( ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v6 + 16) + 56LL), 1u) )
          {
            v14 = v12[36];
            if ( !v14
              || ExAcquireRundownProtectionCacheAwareEx(
                   *(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v14 + 16) + 56LL),
                   1u) )
            {
              goto LABEL_12;
            }
            ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v6 + 16) + 56LL), 1u);
          }
          v6 = 0;
        }
      }
      v12 = (__int64 *)*v12;
      v14 = 0;
      if ( v12 == v13 )
        goto LABEL_12;
    }
  }
  v14 = 0;
LABEL_12:
  ExReleaseFastResource(v10, v15);
  KeLeaveCriticalRegion();
  ExReleaseCacheAwarePushLockSharedEx(v9, 0);
  KeLeaveGuardedRegion();
  *a2 = v6;
  *a3 = v14;
}

```

## disassembly

```asm
0x18001ee00  push    rbx
0x18001ee02  push    rbp
0x18001ee03  push    rsi
0x18001ee04  push    rdi
0x18001ee05  push    r12
0x18001ee07  push    r13
0x18001ee09  push    r14
0x18001ee0b  push    r15
0x18001ee0d  sub     rsp, 78h
0x18001ee11  mov     r15, r8
0x18001ee14  mov     r12, rdx
0x18001ee17  mov     rsi, rcx
0x18001ee1a  xor     ebp, ebp
0x18001ee1c  xor     edx, edx; Val
0x18001ee1e  lea     rcx, [rsp+0B8h+var_98]; void *
0x18001ee23  lea     r8d, [rbp+48h]; Size
0x18001ee27  call    memset
0x18001ee2c  lea     rcx, [rsp+0B8h+var_98]
0x18001ee31  call    cs:__imp_ExInitializeFastOwnerEntry
0x18001ee38  nop     dword ptr [rax+rax+00h]
0x18001ee3d  mov     rdi, [rsi+40h]
0x18001ee41  mov     rbx, cs:qword_18003E9A0
0x18001ee48  call    cs:__imp_KeEnterGuardedRegion
0x18001ee4f  nop     dword ptr [rax+rax+00h]
0x18001ee54  xor     edx, edx
0x18001ee56  mov     rcx, rbx
0x18001ee59  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x18001ee60  nop     dword ptr [rax+rax+00h]
0x18001ee65  mov     r13, rax
0x18001ee68  call    cs:__imp_KeEnterCriticalRegion
0x18001ee6f  nop     dword ptr [rax+rax+00h]
0x18001ee74  lea     r14, [rdi+0C0h]
0x18001ee7b  mov     r8b, 1
0x18001ee7e  mov     rcx, r14
0x18001ee81  lea     rdx, [rsp+0B8h+var_98]
0x18001ee86  call    cs:__imp_ExAcquireFastResourceShared
0x18001ee8d  nop     dword ptr [rax+rax+00h]
0x18001ee92  mov     rbx, [rsi+10h]
0x18001ee96  lea     rsi, [rdi+128h]
0x18001ee9d  cmp     rbx, rsi
0x18001eea0  jz      loc_18001EF26
0x18001eea6  mov     eax, [rbx+40h]
0x18001eea9  test    al, 6
0x18001eeab  jnz     short loc_18001EF1A
0x18001eead  mov     rbp, [rbx+128h]
0x18001eeb4  test    rbp, rbp
0x18001eeb7  jz      short loc_18001EF1A
0x18001eeb9  mov     rcx, [rbp+10h]
0x18001eebd  mov     edx, 1; Count
0x18001eec2  mov     rcx, [rcx+38h]; RunRefCacheAware
0x18001eec6  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x18001eecd  nop     dword ptr [rax+rax+00h]
0x18001eed2  test    al, al
0x18001eed4  jz      short loc_18001EF18
0x18001eed6  mov     rdi, [rbx+120h]
0x18001eedd  test    rdi, rdi
0x18001eee0  jz      short loc_18001EF28
0x18001eee2  mov     rcx, [rdi+10h]
0x18001eee6  mov     edx, 1; Count
0x18001eeeb  mov     rcx, [rcx+38h]; RunRefCacheAware
0x18001eeef  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x18001eef6  nop     dword ptr [rax+rax+00h]
0x18001eefb  test    al, al
0x18001eefd  jnz     short loc_18001EF28
0x18001eeff  mov     rcx, [rbp+10h]
0x18001ef03  mov     edx, 1; Count
0x18001ef08  mov     rcx, [rcx+38h]; RunRef
0x18001ef0c  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x18001ef13  nop     dword ptr [rax+rax+00h]
0x18001ef18  xor     ebp, ebp
0x18001ef1a  mov     rbx, [rbx]
0x18001ef1d  xor     edi, edi
0x18001ef1f  cmp     rbx, rsi
0x18001ef22  jnz     short loc_18001EEA6
0x18001ef24  jmp     short loc_18001EF28
0x18001ef26  xor     edi, edi
0x18001ef28  lea     rdx, [rsp+0B8h+var_98]
0x18001ef2d  mov     rcx, r14
0x18001ef30  call    cs:__imp_ExReleaseFastResource
0x18001ef37  nop     dword ptr [rax+rax+00h]
0x18001ef3c  call    cs:__imp_KeLeaveCriticalRegion
0x18001ef43  nop     dword ptr [rax+rax+00h]
0x18001ef48  xor     edx, edx
0x18001ef4a  mov     rcx, r13
0x18001ef4d  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x18001ef54  nop     dword ptr [rax+rax+00h]
0x18001ef59  call    cs:__imp_KeLeaveGuardedRegion
0x18001ef60  nop     dword ptr [rax+rax+00h]
0x18001ef65  mov     [r12], rbp
0x18001ef69  mov     [r15], rdi
0x18001ef6c  add     rsp, 78h
0x18001ef70  pop     r15
0x18001ef72  pop     r14
0x18001ef74  pop     r13
0x18001ef76  pop     r12
0x18001ef78  pop     rdi
0x18001ef79  pop     rsi
0x18001ef7a  pop     rbp
0x18001ef7b  pop     rbx
0x18001ef7c  retn
```
