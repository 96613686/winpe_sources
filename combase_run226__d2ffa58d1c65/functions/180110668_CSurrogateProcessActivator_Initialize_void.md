# CSurrogateProcessActivator::Initialize(void)

- ea: `0x180110668`
- end: `0x18011073a`
- name: `?Initialize@CSurrogateProcessActivator@@QEAAJXZ`
- size: `210`
- prototype: `HRESULT __fastcall(CSurrogateProcessActivator *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180110020`

## callees

- `0x180110668`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110722`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1801106f2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18011070e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1801106f2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18011070e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011067f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011069c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801106b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801106d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011067f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011069c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801106b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801106d4`

## pseudocode

```c
HRESULT __fastcall CSurrogateProcessActivator::Initialize(CSurrogateProcessActivator *this)
{
  CSurrogateProcessActivator *v1; // rbx
  HANDLE EventW; // rax
  HANDLE v3; // rax
  HANDLE v4; // rax
  HANDLE v5; // rax
  BOOL v6; // eax
  BOOL v7; // eax
  HRESULT result; // eax

  v1 = s_pCSPA;
  EventW = CreateEventW(0, 0, 0, 0);
  v1->m_hStopPingingSCM = EventW;
  if ( EventW )
  {
    v3 = CreateEventW(0, 0, 0, 0);
    v1->m_hTimeoutEvent = v3;
    if ( v3 )
    {
      v4 = CreateEventW(0, 0, 0, 0);
      v1->m_hInitCompleted = v4;
      if ( v4 )
      {
        v5 = CreateEventW(0, 0, 0, 0);
        v1->m_hServiceStarted = v5;
        if ( v5 )
        {
          v6 = InitializeCriticalSectionAndSpinCount(&v1->m_timeoutLock, 0x3E8u);
          v1->m_bLockValid = v6;
          if ( v6 )
          {
            v7 = InitializeCriticalSectionAndSpinCount(&v1->m_serviceStatusLock, 0x3E8u);
            v1->m_fServiceStatusLockValid = v7;
            if ( v7 )
              return 0;
          }
        }
      }
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180110668  push    rbx
0x18011066a  sub     rsp, 20h
0x18011066e  mov     rbx, cs:?s_pCSPA@@3PEAVCSurrogateProcessActivator@@EA; CSurrogateProcessActivator * s_pCSPA
0x180110675  xor     r9d, r9d; lpName
0x180110678  xor     r8d, r8d; bInitialState
0x18011067b  xor     edx, edx; bManualReset
0x18011067d  xor     ecx, ecx; lpEventAttributes
0x18011067f  call    cs:__imp_CreateEventW
0x180110685  mov     [rbx+48h], rax
0x180110689  test    rax, rax
0x18011068c  jz      $failed_win32
0x180110692  xor     r9d, r9d; lpName
0x180110695  xor     r8d, r8d; bInitialState
0x180110698  xor     edx, edx; bManualReset
0x18011069a  xor     ecx, ecx; lpEventAttributes
0x18011069c  call    cs:__imp_CreateEventW
0x1801106a2  mov     [rbx+0D0h], rax
0x1801106a9  test    rax, rax
0x1801106ac  jz      short $failed_win32
0x1801106ae  xor     r9d, r9d; lpName
0x1801106b1  xor     r8d, r8d; bInitialState
0x1801106b4  xor     edx, edx; bManualReset
0x1801106b6  xor     ecx, ecx; lpEventAttributes
0x1801106b8  call    cs:__imp_CreateEventW
0x1801106be  mov     [rbx+80h], rax
0x1801106c5  test    rax, rax
0x1801106c8  jz      short $failed_win32
0x1801106ca  xor     r9d, r9d; lpName
0x1801106cd  xor     r8d, r8d; bInitialState
0x1801106d0  xor     edx, edx; bManualReset
0x1801106d2  xor     ecx, ecx; lpEventAttributes
0x1801106d4  call    cs:__imp_CreateEventW
0x1801106da  mov     [rbx+0F8h], rax
0x1801106e1  test    rax, rax
0x1801106e4  jz      short $failed_win32
0x1801106e6  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1801106ed  mov     edx, 3E8h; dwSpinCount
0x1801106f2  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1801106f8  mov     [rbx+0C8h], eax
0x1801106fe  test    eax, eax
0x180110700  jz      short $failed_win32
0x180110702  lea     rcx, [rbx+128h]; lpCriticalSection
0x180110709  mov     edx, 3E8h; dwSpinCount
0x18011070e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180110714  mov     [rbx+150h], eax
0x18011071a  test    eax, eax
0x18011071c  jz      short $failed_win32
0x18011071e  xor     eax, eax
0x180110720  jmp     short loc_180110734
0x180110722  call    cs:__imp_GetLastError
0x180110728  test    eax, eax
0x18011072a  jle     short loc_180110734
0x18011072c  movzx   eax, ax
0x18011072f  or      eax, 80070000h
0x180110734  add     rsp, 20h
0x180110738  pop     rbx
0x180110739  retn
```
