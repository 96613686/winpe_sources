# RescheduleLeaseRenewalOnModernStandbyEntry

- ea: `0x180024ff8`
- end: `0x18002519c`
- name: `RescheduleLeaseRenewalOnModernStandbyEntry`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800230fc`

## callees

- `0x1800141fc`
- `0x18001f120`
- `0x1800202ec`
- `0x180024ff8`
- `0x18004a364`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025168`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025168`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002507f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002507f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002509b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002509b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800250c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800250c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025007`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025007`

## string_xrefs

- `0x180025124`: `Rescheduled`

## pseudocode

```c
void RescheduleLeaseRenewalOnModernStandbyEntry()
{
  ULONGLONG TickCount64; // rsi
  unsigned __int64 v1; // rsi
  RTL_SRWLOCK *i; // rdi
  int Ptr; // r12d
  unsigned __int64 v4; // rbp
  int v5; // r14d
  PVOID v6; // r15
  int v7; // edx
  int v8; // r8d
  int v9; // ebx
  unsigned int v10; // eax
  const char *v11; // r9

  TickCount64 = GetTickCount64();
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 83, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
  if ( (unsigned int)DhcpIsMachineInModernStandby() )
  {
    v1 = TickCount64 / 0x3E8;
    EnterCriticalSection(&DhcpGlobalNicListCritSect);
    for ( i = (RTL_SRWLOCK *)DhcpGlobalConnectedNICList;
          i != (RTL_SRWLOCK *)&DhcpGlobalConnectedNICList;
          i = (RTL_SRWLOCK *)i->Ptr )
    {
      AcquireSRWLockShared(i + 84);
      Ptr = (int)i[99].Ptr;
      v4 = (unsigned __int64)i[69].Ptr;
      v5 = (int)i[82].Ptr;
      v6 = i[57].Ptr;
      ReleaseSRWLockShared(i + 84);
      if ( Ptr && v5 && LODWORD(i[15].Ptr) && (PVOID)v4 == v6 && v4 > v1 )
      {
        v9 = 1;
        v10 = CalculateTimeToSleep(i);
        ScheduleDhcpRenewal(i, v10, 0, 0);
      }
      else
      {
        v9 = 0;
      }
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        v11 = "Rescheduled";
        if ( !v9 )
          v11 = "Not rescheduling";
        WPP_SF_s_guid_JlDli(
          (_DWORD)i + 2112,
          v7,
          v8,
          (_DWORD)v11,
          (__int64)&i[264],
          (char)i[3].Ptr,
          Ptr,
          (char)i[15].Ptr,
          v5,
          (char)v6);
      }
    }
    LeaveCriticalSection(&DhcpGlobalNicListCritSect);
  }
  else
  {
    if ( (xmmword_1800616A0 & 0x10) == 0 )
      return;
    WPP_SF_(1028, 84, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 86, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
}

```

## disassembly

```asm
0x180024ff8  push    rbx
0x180024ffa  push    rbp
0x180024ffb  push    rsi
0x180024ffc  push    rdi
0x180024ffd  push    r12
0x180024fff  push    r14
0x180025001  push    r15
0x180025003  sub     rsp, 50h
0x180025007  call    cs:__imp_GetTickCount64
0x18002500d  mov     rsi, rax
0x180025010  test    byte ptr cs:xmmword_1800616A0, 10h
0x180025017  jz      short loc_18002502F
0x180025019  mov     edx, 53h ; 'S'
0x18002501e  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180025025  mov     ecx, 404h
0x18002502a  call    WPP_SF_
0x18002502f  call    DhcpIsMachineInModernStandby
0x180025034  test    eax, eax
0x180025036  jnz     short loc_18002505E
0x180025038  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002503f  jz      loc_18002518D
0x180025045  lea     edx, [rax+54h]
0x180025048  mov     ecx, 404h
0x18002504d  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180025054  call    WPP_SF_
0x180025059  jmp     loc_18002516E
0x18002505e  mov     rax, 624DD2F1A9FBE77h
0x180025068  lea     rcx, DhcpGlobalNicListCritSect; lpCriticalSection
0x18002506f  mul     rsi
0x180025072  sub     rsi, rdx
0x180025075  shr     rsi, 1
0x180025078  add     rsi, rdx
0x18002507b  shr     rsi, 9
0x18002507f  call    cs:__imp_EnterCriticalSection
0x180025085  mov     rdi, cs:DhcpGlobalConnectedNICList
0x18002508c  jmp     loc_180025151
0x180025091  lea     rbx, [rdi+2A0h]
0x180025098  mov     rcx, rbx; SRWLock
0x18002509b  call    cs:__imp_AcquireSRWLockShared
0x1800250a1  mov     r12d, [rdi+318h]
0x1800250a8  mov     rcx, rbx; SRWLock
0x1800250ab  mov     rbp, [rdi+228h]
0x1800250b2  mov     r14d, [rdi+290h]
0x1800250b9  mov     r15, [rdi+1C8h]
0x1800250c0  call    cs:__imp_ReleaseSRWLockShared
0x1800250c6  test    r12d, r12d
0x1800250c9  jz      short loc_1800250FF
0x1800250cb  test    r14d, r14d
0x1800250ce  jz      short loc_1800250FF
0x1800250d0  cmp     dword ptr [rdi+78h], 0
0x1800250d4  jz      short loc_1800250FF
0x1800250d6  cmp     rbp, r15
0x1800250d9  jnz     short loc_1800250FF
0x1800250db  cmp     rbp, rsi
0x1800250de  jbe     short loc_1800250FF
0x1800250e0  mov     rcx, rdi
0x1800250e3  mov     ebx, 1
0x1800250e8  call    CalculateTimeToSleep
0x1800250ed  xor     r9d, r9d
0x1800250f0  xor     r8d, r8d
0x1800250f3  mov     edx, eax
0x1800250f5  mov     rcx, rdi
0x1800250f8  call    ScheduleDhcpRenewal
0x1800250fd  jmp     short loc_180025101
0x1800250ff  xor     ebx, ebx
0x180025101  test    byte ptr cs:xmmword_1800616A0, 10h
0x180025108  jz      short loc_18002514E
0x18002510a  mov     [rsp+88h+var_40], r15
0x18002510f  lea     rax, aNotReschedulin; "Not rescheduling"
0x180025116  mov     [rsp+88h+var_48], r14d
0x18002511b  lea     rcx, [rdi+840h]
0x180025122  test    ebx, ebx
0x180025124  lea     r9, aRescheduled; "Rescheduled"
0x18002512b  cmovz   r9, rax
0x18002512f  mov     eax, [rdi+78h]
0x180025132  mov     [rsp+88h+var_50], eax
0x180025136  mov     rax, [rdi+18h]
0x18002513a  mov     [rsp+88h+var_58], r12d
0x18002513f  mov     [rsp+88h+var_60], rax
0x180025144  mov     [rsp+88h+var_68], rcx
0x180025149  call    WPP_SF_s_guid_JlDli
0x18002514e  mov     rdi, [rdi]
0x180025151  lea     rax, DhcpGlobalConnectedNICList
0x180025158  cmp     rdi, rax
0x18002515b  jnz     loc_180025091
0x180025161  lea     rcx, DhcpGlobalNicListCritSect; lpCriticalSection
0x180025168  call    cs:__imp_LeaveCriticalSection
0x18002516e  test    byte ptr cs:xmmword_1800616A0, 10h
0x180025175  jz      short loc_18002518D
0x180025177  mov     edx, 56h ; 'V'
0x18002517c  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180025183  mov     ecx, 404h
0x180025188  call    WPP_SF_
0x18002518d  add     rsp, 50h
0x180025191  pop     r15
0x180025193  pop     r14
0x180025195  pop     r12
0x180025197  pop     rdi
0x180025198  pop     rsi
0x180025199  pop     rbp
0x18002519a  pop     rbx
0x18002519b  retn
```
