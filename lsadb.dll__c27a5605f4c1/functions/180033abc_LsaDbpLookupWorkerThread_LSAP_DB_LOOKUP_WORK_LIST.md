# LsaDbpLookupWorkerThread(_LSAP_DB_LOOKUP_WORK_LIST *)

- ea: `0x180033abc`
- end: `0x180033c46`
- name: `?LsaDbpLookupWorkerThread@@YAXPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z`
- size: `394`
- prototype: `void __fastcall(struct _LSAP_DB_LOOKUP_WORK_LIST *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180032e3c`
- `0x180033c50`

## callees

- `0x1800333f0`
- `0x180033884`
- `0x1800339d4`
- `0x180033abc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180033c3f`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180033c3f`
- `ntdll!NtWaitForSingleObject` at `0x180033c0d`
- `ntdll!NtWaitForSingleObject` at `0x180033c0d`
- `ntdll!RtlLeaveCriticalSection` at `0x180033afa`
- `ntdll!RtlLeaveCriticalSection` at `0x180033b74`
- `ntdll!RtlLeaveCriticalSection` at `0x180033bbb`
- `ntdll!RtlLeaveCriticalSection` at `0x180033bfb`
- `ntdll!RtlLeaveCriticalSection` at `0x180033afa`
- `ntdll!RtlLeaveCriticalSection` at `0x180033b74`
- `ntdll!RtlLeaveCriticalSection` at `0x180033bbb`
- `ntdll!RtlLeaveCriticalSection` at `0x180033bfb`
- `ntdll!RtlEnterCriticalSection` at `0x180033ae0`
- `ntdll!RtlEnterCriticalSection` at `0x180033b03`
- `ntdll!RtlEnterCriticalSection` at `0x180033b96`
- `ntdll!RtlEnterCriticalSection` at `0x180033bde`
- `ntdll!RtlEnterCriticalSection` at `0x180033c1e`
- `ntdll!RtlEnterCriticalSection` at `0x180033ae0`
- `ntdll!RtlEnterCriticalSection` at `0x180033b03`
- `ntdll!RtlEnterCriticalSection` at `0x180033b96`
- `ntdll!RtlEnterCriticalSection` at `0x180033bde`
- `ntdll!RtlEnterCriticalSection` at `0x180033c1e`

## pseudocode

```c
void __fastcall LsaDbpLookupWorkerThread(struct _LSAP_DB_LOOKUP_WORK_LIST *a1)
{
  char v2; // r14
  NTSTATUS updated; // ebx
  unsigned __int128 v4; // kr00_16
  __int64 v5; // rax
  int v6; // ebx
  NTSTATUS v7; // ebx
  int v8; // ecx

  if ( a1 )
  {
    v2 = 1;
    goto LABEL_5;
  }
  if ( RtlEnterCriticalSection(&LookupWorkQueue) < 0 )
    return;
  v2 = 0;
  ++dword_180048250;
  RtlLeaveCriticalSection(&LookupWorkQueue);
  do
  {
LABEL_5:
    while ( 1 )
    {
      updated = RtlEnterCriticalSection(&LookupWorkQueue);
      if ( updated < 0 )
        break;
      v4 = 0u;
      if ( !(_QWORD)xmmword_180048240 )
        goto LABEL_7;
      if ( a1 )
      {
        v5 = *((_QWORD *)a1 + 3);
        if ( !v5 )
        {
LABEL_7:
          updated = -2147483622;
          goto LABEL_13;
        }
        *(_DWORD *)(v5 + 16) = 2;
        v4 = __PAIR128__(*((_QWORD *)a1 + 3), (unsigned __int64)a1);
      }
      else
      {
        *(_DWORD *)(*((_QWORD *)&xmmword_180048240 + 1) + 16LL) = 2;
        v4 = xmmword_180048240;
      }
      updated = LsaDbpLookupUpdateAssignableWorkItem(*((struct _LSAP_DB_LOOKUP_WORK_ITEM **)&v4 + 1), a1, 0);
LABEL_13:
      RtlLeaveCriticalSection(&LookupWorkQueue);
      if ( updated < 0 )
        break;
      v6 = LsaDbpLookupProcessWorkItem(
             (struct _LSAP_DB_LOOKUP_WORK_LIST *)v4,
             *((struct _LSAP_DB_LOOKUP_WORK_ITEM **)&v4 + 1));
      if ( v6 < 0 )
      {
        if ( RtlEnterCriticalSection(&LookupWorkQueue) >= 0 )
        {
          *(_DWORD *)(v4 + 32) = v6;
          if ( (_QWORD)v4 == (_QWORD)xmmword_180048240 )
            LsaDbpLookupUpdateAssignableWorkItem(0, 0, 1u);
          RtlLeaveCriticalSection(&LookupWorkQueue);
        }
        return;
      }
    }
    if ( updated != -2147483622 )
      return;
    if ( v2 )
      return;
    v7 = RtlEnterCriticalSection(&LookupWorkQueue);
    if ( v7 < 0 )
      return;
    v8 = dword_180048250;
    if ( dword_180048250 > (unsigned int)dword_180048258 )
      goto LABEL_27;
    RtlLeaveCriticalSection(&LookupWorkQueue);
  }
  while ( NtWaitForSingleObject(LsaDbpLookupStartedEvent, 1u, 0) >= 0 );
  v7 = RtlEnterCriticalSection(&LookupWorkQueue);
  if ( v7 >= 0 )
  {
    v8 = dword_180048250;
LABEL_27:
    dword_180048250 = v8 - 1;
    LsaDbpLookupReleaseWorkQueueLock();
    ExitThread(v7);
  }
}

```

## disassembly

```asm
0x180033abc  push    rbx
0x180033abe  push    rbp
0x180033abf  push    rsi
0x180033ac0  push    rdi
0x180033ac1  push    r14
0x180033ac3  push    r15
0x180033ac5  sub     rsp, 28h
0x180033ac9  lea     r15, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; _LSAP_DB_LOOKUP_WORK_QUEUE LookupWorkQueue
0x180033ad0  mov     rsi, rcx
0x180033ad3  test    rcx, rcx
0x180033ad6  jz      short loc_180033ADD
0x180033ad8  mov     r14b, 1
0x180033adb  jmp     short loc_180033B00
0x180033add  mov     rcx, r15; CriticalSection
0x180033ae0  call    cs:__imp_RtlEnterCriticalSection
0x180033ae6  test    eax, eax
0x180033ae8  js      loc_180033BC1
0x180033aee  xor     r14b, r14b
0x180033af1  inc     cs:dword_180048250
0x180033af7  mov     rcx, r15; CriticalSection
0x180033afa  call    cs:__imp_RtlLeaveCriticalSection
0x180033b00  mov     rcx, r15; CriticalSection
0x180033b03  call    cs:__imp_RtlEnterCriticalSection
0x180033b09  mov     ebx, eax
0x180033b0b  test    eax, eax
0x180033b0d  js      loc_180033BCE
0x180033b13  xor     edi, edi
0x180033b15  xor     ebp, ebp
0x180033b17  cmp     qword ptr cs:xmmword_180048240, rdi
0x180033b1e  jnz     short loc_180033B27
0x180033b20  mov     ebx, 8000001Ah
0x180033b25  jmp     short loc_180033B71
0x180033b27  test    rsi, rsi
0x180033b2a  jz      short loc_180033B45
0x180033b2c  mov     rax, [rsi+18h]
0x180033b30  test    rax, rax
0x180033b33  jz      short loc_180033B20
0x180033b35  mov     dword ptr [rax+10h], 2
0x180033b3c  mov     rdi, rsi
0x180033b3f  mov     rbp, [rsi+18h]
0x180033b43  jmp     short loc_180033B61
0x180033b45  mov     rax, qword ptr cs:xmmword_180048240+8
0x180033b4c  mov     dword ptr [rax+10h], 2
0x180033b53  mov     rdi, qword ptr cs:xmmword_180048240
0x180033b5a  mov     rbp, qword ptr cs:xmmword_180048240+8
0x180033b61  xor     r8d, r8d; unsigned __int8
0x180033b64  mov     rdx, rsi; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x180033b67  mov     rcx, rbp; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x180033b6a  call    ?LsaDbpLookupUpdateAssignableWorkItem@@YAJPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@PEAU_LSAP_DB_LOOKUP_WORK_LIST@@E@Z; LsaDbpLookupUpdateAssignableWorkItem(_LSAP_DB_LOOKUP_WORK_ITEM *,_LSAP_DB_LOOKUP_WORK_LIST *,uchar)
0x180033b6f  mov     ebx, eax
0x180033b71  mov     rcx, r15; CriticalSection
0x180033b74  call    cs:__imp_RtlLeaveCriticalSection
0x180033b7a  test    ebx, ebx
0x180033b7c  js      short loc_180033BCE
0x180033b7e  mov     rdx, rbp; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x180033b81  mov     rcx, rdi; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x180033b84  call    ?LsaDbpLookupProcessWorkItem@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z; LsaDbpLookupProcessWorkItem(_LSAP_DB_LOOKUP_WORK_LIST *,_LSAP_DB_LOOKUP_WORK_ITEM *)
0x180033b89  mov     ebx, eax
0x180033b8b  test    eax, eax
0x180033b8d  jns     loc_180033B00
0x180033b93  mov     rcx, r15; CriticalSection
0x180033b96  call    cs:__imp_RtlEnterCriticalSection
0x180033b9c  test    eax, eax
0x180033b9e  js      short loc_180033BC1
0x180033ba0  mov     [rdi+20h], ebx
0x180033ba3  cmp     rdi, qword ptr cs:xmmword_180048240
0x180033baa  jnz     short loc_180033BB8
0x180033bac  mov     r8b, 1; unsigned __int8
0x180033baf  xor     edx, edx; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x180033bb1  xor     ecx, ecx; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x180033bb3  call    ?LsaDbpLookupUpdateAssignableWorkItem@@YAJPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@PEAU_LSAP_DB_LOOKUP_WORK_LIST@@E@Z; LsaDbpLookupUpdateAssignableWorkItem(_LSAP_DB_LOOKUP_WORK_ITEM *,_LSAP_DB_LOOKUP_WORK_LIST *,uchar)
0x180033bb8  mov     rcx, r15; CriticalSection
0x180033bbb  call    cs:__imp_RtlLeaveCriticalSection
0x180033bc1  add     rsp, 28h
0x180033bc5  pop     r15
0x180033bc7  pop     r14
0x180033bc9  pop     rdi
0x180033bca  pop     rsi
0x180033bcb  pop     rbp
0x180033bcc  pop     rbx
0x180033bcd  retn
0x180033bce  cmp     ebx, 8000001Ah
0x180033bd4  jnz     short loc_180033BC1
0x180033bd6  test    r14b, r14b
0x180033bd9  jnz     short loc_180033BC1
0x180033bdb  mov     rcx, r15; CriticalSection
0x180033bde  call    cs:__imp_RtlEnterCriticalSection
0x180033be4  mov     ebx, eax
0x180033be6  test    eax, eax
0x180033be8  js      short loc_180033BC1
0x180033bea  mov     ecx, cs:dword_180048250
0x180033bf0  cmp     ecx, cs:dword_180048258
0x180033bf6  ja      short loc_180033C30
0x180033bf8  mov     rcx, r15; CriticalSection
0x180033bfb  call    cs:__imp_RtlLeaveCriticalSection
0x180033c01  mov     rcx, cs:?LsaDbpLookupStartedEvent@@3PEAXEA; Handle
0x180033c08  xor     r8d, r8d; Timeout
0x180033c0b  mov     dl, 1; Alertable
0x180033c0d  call    cs:__imp_NtWaitForSingleObject
0x180033c13  test    eax, eax
0x180033c15  jns     loc_180033B00
0x180033c1b  mov     rcx, r15; CriticalSection
0x180033c1e  call    cs:__imp_RtlEnterCriticalSection
0x180033c24  mov     ebx, eax
0x180033c26  test    eax, eax
0x180033c28  js      short loc_180033BC1
0x180033c2a  mov     ecx, cs:dword_180048250
0x180033c30  dec     ecx
0x180033c32  mov     cs:dword_180048250, ecx
0x180033c38  call    ?LsaDbpLookupReleaseWorkQueueLock@@YAXXZ; LsaDbpLookupReleaseWorkQueueLock(void)
0x180033c3d  mov     ecx, ebx; dwExitCode
0x180033c3f  call    cs:__imp_ExitThread
```
