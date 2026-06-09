# ReleaseExclusiveLockForUser(void *)

- ea: `0x180004780`
- end: `0x180004812`
- name: `?ReleaseExclusiveLockForUser@@YAXPEAX@Z`
- size: `146`
- prototype: `void __fastcall(PSID pSid2)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003908`
- `0x180003b98`

## callees

- `0x180004780`
- `0x180004818`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800047fd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800047fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800047d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800047d6`
- `ntdll!RtlEnterCriticalSection` at `0x180004799`
- `ntdll!RtlEnterCriticalSection` at `0x180004799`
- `ntdll!RtlLeaveCriticalSection` at `0x1800047c1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800047c1`

## pseudocode

```c
void __fastcall ReleaseExclusiveLockForUser(PSID pSid2)
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
      ReleaseSRWLockExclusive((PSRWLOCK)(i + 16));
      TryUnInitPerUserLock((HLOCAL)i);
    }
  }
}

```

## disassembly

```asm
0x180004780  test    rcx, rcx
0x180004783  jz      short locret_1800047F4
0x180004785  mov     [rsp+arg_0], rbx
0x18000478a  push    rdi
0x18000478b  sub     rsp, 20h
0x18000478f  mov     rdi, rcx
0x180004792  lea     rcx, CriticalSection; CriticalSection
0x180004799  call    cs:__imp_RtlEnterCriticalSection
0x1800047a0  nop     dword ptr [rax+rax+00h]
0x1800047a5  mov     rbx, cs:qword_18004C968
0x1800047ac  lea     rax, qword_18004C968
0x1800047b3  cmp     rbx, rax
0x1800047b6  jnz     short loc_1800047F6
0x1800047b8  xor     ebx, ebx
0x1800047ba  lea     rcx, CriticalSection; CriticalSection
0x1800047c1  call    cs:__imp_RtlLeaveCriticalSection
0x1800047c8  nop     dword ptr [rax+rax+00h]
0x1800047cd  test    rbx, rbx
0x1800047d0  jz      short loc_1800047EA
0x1800047d2  lea     rcx, [rbx+10h]; SRWLock
0x1800047d6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800047dd  nop     dword ptr [rax+rax+00h]
0x1800047e2  mov     rcx, rbx; hMem
0x1800047e5  call    ?TryUnInitPerUserLock@@YAXPEAU_PER_USER_LOCK_ENTRY@@@Z; TryUnInitPerUserLock(_PER_USER_LOCK_ENTRY *)
0x1800047ea  mov     rbx, [rsp+28h+arg_0]
0x1800047ef  add     rsp, 20h
0x1800047f3  pop     rdi
0x1800047f4  retn
0x1800047f6  mov     rcx, [rbx+20h]; pSid1
0x1800047fa  mov     rdx, rdi; pSid2
0x1800047fd  call    cs:__imp_EqualSid
0x180004804  nop     dword ptr [rax+rax+00h]
0x180004809  test    eax, eax
0x18000480b  jnz     short loc_1800047BA
0x18000480d  mov     rbx, [rbx]
0x180004810  jmp     short loc_1800047AC
```
