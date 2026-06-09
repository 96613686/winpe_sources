# ReleaseSharedLockForUser(void *)

- ea: `0x1800057e8`
- end: `0x18000587a`
- name: `?ReleaseSharedLockForUser@@YAXPEAX@Z`
- size: `146`
- prototype: `void __fastcall(PSID pSid2)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005a2c`

## callees

- `0x180004818`
- `0x1800057e8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180005865`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180005865`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000583e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000583e`
- `ntdll!RtlEnterCriticalSection` at `0x180005801`
- `ntdll!RtlEnterCriticalSection` at `0x180005801`
- `ntdll!RtlLeaveCriticalSection` at `0x180005829`
- `ntdll!RtlLeaveCriticalSection` at `0x180005829`

## pseudocode

```c
void __fastcall ReleaseSharedLockForUser(PSID pSid2)
{
  __int64 i; // rbx

  if ( pSid2 )
  {
    RtlEnterCriticalSection(&CriticalSection);
    for ( i = qword_18004C968; (__int64 *)i != &qword_18004C968; i = *(_QWORD *)i )
    {
      if ( EqualSid(*(PSID *)(i + 32), pSid2) )
        goto LABEL_5;
    }
    i = 0;
LABEL_5:
    RtlLeaveCriticalSection(&CriticalSection);
    if ( i )
    {
      ReleaseSRWLockShared((PSRWLOCK)(i + 16));
      TryUnInitPerUserLock((HLOCAL)i);
    }
  }
}

```

## disassembly

```asm
0x1800057e8  test    rcx, rcx
0x1800057eb  jz      short locret_18000585C
0x1800057ed  mov     [rsp+arg_0], rbx
0x1800057f2  push    rdi
0x1800057f3  sub     rsp, 20h
0x1800057f7  mov     rdi, rcx
0x1800057fa  lea     rcx, CriticalSection; CriticalSection
0x180005801  call    cs:__imp_RtlEnterCriticalSection
0x180005808  nop     dword ptr [rax+rax+00h]
0x18000580d  mov     rbx, cs:qword_18004C968
0x180005814  lea     rax, qword_18004C968
0x18000581b  cmp     rbx, rax
0x18000581e  jnz     short loc_18000585E
0x180005820  xor     ebx, ebx
0x180005822  lea     rcx, CriticalSection; CriticalSection
0x180005829  call    cs:__imp_RtlLeaveCriticalSection
0x180005830  nop     dword ptr [rax+rax+00h]
0x180005835  test    rbx, rbx
0x180005838  jz      short loc_180005852
0x18000583a  lea     rcx, [rbx+10h]; SRWLock
0x18000583e  call    cs:__imp_ReleaseSRWLockShared
0x180005845  nop     dword ptr [rax+rax+00h]
0x18000584a  mov     rcx, rbx; hMem
0x18000584d  call    ?TryUnInitPerUserLock@@YAXPEAU_PER_USER_LOCK_ENTRY@@@Z; TryUnInitPerUserLock(_PER_USER_LOCK_ENTRY *)
0x180005852  mov     rbx, [rsp+28h+arg_0]
0x180005857  add     rsp, 20h
0x18000585b  pop     rdi
0x18000585c  retn
0x18000585e  mov     rcx, [rbx+20h]; pSid1
0x180005862  mov     rdx, rdi; pSid2
0x180005865  call    cs:__imp_EqualSid
0x18000586c  nop     dword ptr [rax+rax+00h]
0x180005871  test    eax, eax
0x180005873  jnz     short loc_180005822
0x180005875  mov     rbx, [rbx]
0x180005878  jmp     short loc_180005814
```
