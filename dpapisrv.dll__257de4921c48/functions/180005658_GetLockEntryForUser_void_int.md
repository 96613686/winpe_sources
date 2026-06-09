# GetLockEntryForUser(void *,int)

- ea: `0x180005658`
- end: `0x18000571f`
- name: `?GetLockEntryForUser@@YAPEAU_PER_USER_LOCK_ENTRY@@PEAXH@Z`
- size: `199`
- prototype: `struct _PER_USER_LOCK_ENTRY *__fastcall(PSID pSourceSid, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800048e4`
- `0x180005a2c`

## callees

- `0x180005658`
- `0x180005728`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800056a4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800056a4`
- `ntdll!RtlEnterCriticalSection` at `0x180005676`
- `ntdll!RtlEnterCriticalSection` at `0x180005676`
- `ntdll!RtlLeaveCriticalSection` at `0x1800056bf`
- `ntdll!RtlLeaveCriticalSection` at `0x1800056bf`

## pseudocode

```c
struct _PER_USER_LOCK_ENTRY *__fastcall GetLockEntryForUser(PSID pSourceSid, int a2)
{
  struct _PER_USER_LOCK_ENTRY *i; // rbx
  __int64 v6; // rax

  if ( !pSourceSid )
    return 0;
  RtlEnterCriticalSection(&CriticalSection);
  for ( i = (struct _PER_USER_LOCK_ENTRY *)qword_18004C968; ; i = *(struct _PER_USER_LOCK_ENTRY **)i )
  {
    if ( i == (struct _PER_USER_LOCK_ENTRY *)&qword_18004C968 )
    {
      if ( a2 )
      {
        i = InitPerUserLock(pSourceSid);
        if ( i )
        {
          v6 = qword_18004C968;
          if ( *(__int64 **)(qword_18004C968 + 8) != &qword_18004C968 )
            __fastfail(3u);
          *(_QWORD *)i = qword_18004C968;
          *((_QWORD *)i + 1) = &qword_18004C968;
          *(_QWORD *)(v6 + 8) = i;
          qword_18004C968 = (__int64)i;
        }
      }
      else
      {
        i = 0;
      }
      goto LABEL_9;
    }
    if ( EqualSid(*((PSID *)i + 4), pSourceSid) )
      break;
  }
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)i + 6);
LABEL_9:
  RtlLeaveCriticalSection(&CriticalSection);
  return i;
}

```

## disassembly

```asm
0x180005658  push    rbx
0x18000565a  push    rbp
0x18000565b  push    rsi
0x18000565c  push    rdi
0x18000565d  sub     rsp, 28h
0x180005661  mov     esi, edx
0x180005663  mov     rdi, rcx
0x180005666  test    rcx, rcx
0x180005669  jz      loc_18000570E
0x18000566f  lea     rcx, CriticalSection; CriticalSection
0x180005676  call    cs:__imp_RtlEnterCriticalSection
0x18000567d  nop     dword ptr [rax+rax+00h]
0x180005682  mov     rbx, cs:qword_18004C968
0x180005689  lea     rbp, qword_18004C968
0x180005690  cmp     rbx, rbp
0x180005693  jnz     short loc_18000569D
0x180005695  test    esi, esi
0x180005697  jnz     short loc_1800056D8
0x180005699  xor     ebx, ebx
0x18000569b  jmp     short loc_1800056B8
0x18000569d  mov     rcx, [rbx+20h]; pSid1
0x1800056a1  mov     rdx, rdi; pSid2
0x1800056a4  call    cs:__imp_EqualSid
0x1800056ab  nop     dword ptr [rax+rax+00h]
0x1800056b0  test    eax, eax
0x1800056b2  jz      short loc_180005709
0x1800056b4  test    esi, esi
0x1800056b6  jnz     short loc_180005712
0x1800056b8  lea     rcx, CriticalSection; CriticalSection
0x1800056bf  call    cs:__imp_RtlLeaveCriticalSection
0x1800056c6  nop     dword ptr [rax+rax+00h]
0x1800056cb  mov     rax, rbx
0x1800056ce  add     rsp, 28h
0x1800056d2  pop     rdi
0x1800056d3  pop     rsi
0x1800056d4  pop     rbp
0x1800056d5  pop     rbx
0x1800056d6  retn
0x1800056d8  mov     rcx, rdi; pSourceSid
0x1800056db  call    ?InitPerUserLock@@YAPEAU_PER_USER_LOCK_ENTRY@@PEAX@Z; InitPerUserLock(void *)
0x1800056e0  mov     rbx, rax
0x1800056e3  test    rax, rax
0x1800056e6  jz      short loc_1800056B8
0x1800056e8  mov     rax, cs:qword_18004C968
0x1800056ef  cmp     [rax+8], rbp
0x1800056f3  jnz     short loc_180005718
0x1800056f5  mov     [rbx], rax
0x1800056f8  mov     [rbx+8], rbp
0x1800056fc  mov     [rax+8], rbx
0x180005700  mov     cs:qword_18004C968, rbx
0x180005707  jmp     short loc_1800056B8
0x180005709  mov     rbx, [rbx]
0x18000570c  jmp     short loc_180005690
0x18000570e  xor     eax, eax
0x180005710  jmp     short loc_1800056CE
0x180005712  lock inc dword ptr [rbx+18h]
0x180005716  jmp     short loc_1800056B8
0x180005718  mov     ecx, 3
0x18000571d  int     29h; Win8: RtlFailFast(ecx)
```
