# ServiceCallbacks::TerminateProcessIfHangDetected(long)

- ea: `0x180009a80`
- end: `0x180009be5`
- name: `?TerminateProcessIfHangDetected@ServiceCallbacks@@UEAAXJ@Z`
- size: `357`
- prototype: `void __fastcall(ServiceCallbacks *this, DWORD)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180001d00`
- `0x180002722`
- `0x1800065ac`
- `0x180009660`
- `0x180009a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009b36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009b36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009ab9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009ab9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180009bb8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180009bb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009bad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009bad`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180009ba5`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180009ba5`

## pseudocode

```c
void __fastcall ServiceCallbacks::TerminateProcessIfHangDetected(ServiceCallbacks *this, DWORD a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  unsigned int v4; // r14d
  unsigned int v5; // ebp
  unsigned int v6; // esi
  __int64 *v8; // rax
  __int64 **v9; // rdx
  __int64 *i; // rcx
  __int64 *j; // rdx
  _DWORD *v12; // rax
  OfflineMapsTelemetry *v13; // rax
  HANDLE CurrentProcess; // rax
  EXCEPTION_RECORD pExceptionRecord; // [rsp+30h] [rbp-D8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v4 = 0;
  v5 = 0;
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v8 = (__int64 *)**((_QWORD **)this + 6);
  while ( !*((_BYTE *)v8 + 25) )
  {
    switch ( *((_DWORD *)v8 + 8) )
    {
      case 1:
        ++v4;
        break;
      case 2:
        ++v5;
        break;
      case 3:
        ++v6;
        break;
    }
    v9 = (__int64 **)v8[2];
    if ( *((_BYTE *)v9 + 25) )
    {
      for ( i = (__int64 *)v8[1]; !*((_BYTE *)i + 25) && v8 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v8 = i;
      v8 = i;
    }
    else
    {
      v8 = (__int64 *)v8[2];
      for ( j = *v9; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v8 = j;
    }
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  if ( !v4 && !v5 && !v6 )
  {
LABEL_29:
    memset_0(&pExceptionRecord.ExceptionFlags, 0, 0x94u);
    pExceptionRecord.ExceptionCode = a2;
    RaiseFailFastException(&pExceptionRecord, 0, 0);
    return;
  }
  v12 = (_DWORD *)*((_QWORD *)OfflineMapsTelemetry::Instance() + 1);
  if ( v12 && *v12 )
  {
    v13 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::ScopedWatchdogHangDetected_(v13, a2, v4, v5, v6);
  }
  if ( !v4 && !v5 )
  {
    if ( v6 )
      return;
    goto LABEL_29;
  }
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0);
}

```

## disassembly

```asm
0x180009a80  mov     [rsp+arg_10], rbx
0x180009a85  push    rbp
0x180009a86  push    rsi
0x180009a87  push    rdi
0x180009a88  push    r14
0x180009a8a  push    r15
0x180009a8c  sub     rsp, 0E0h
0x180009a93  mov     rax, cs:__security_cookie
0x180009a9a  xor     rax, rsp
0x180009a9d  mov     [rsp+108h+var_38], rax
0x180009aa5  lea     rbx, [rcx+8]
0x180009aa9  mov     rdi, rcx
0x180009aac  mov     rcx, rbx; lpCriticalSection
0x180009aaf  xor     r14d, r14d
0x180009ab2  xor     ebp, ebp
0x180009ab4  xor     esi, esi
0x180009ab6  mov     r15d, edx
0x180009ab9  call    cs:__imp_EnterCriticalSection
0x180009abf  mov     rax, [rdi+30h]
0x180009ac3  mov     rax, [rax]
0x180009ac6  cmp     byte ptr [rax+19h], 0
0x180009aca  jnz     short loc_180009B2E
0x180009acc  mov     edx, [rax+20h]
0x180009acf  sub     edx, 1
0x180009ad2  jz      short loc_180009AE6
0x180009ad4  sub     edx, 1
0x180009ad7  jz      short loc_180009AE2
0x180009ad9  cmp     edx, 1
0x180009adc  jnz     short loc_180009AE9
0x180009ade  inc     esi
0x180009ae0  jmp     short loc_180009AE9
0x180009ae2  inc     ebp
0x180009ae4  jmp     short loc_180009AE9
0x180009ae6  inc     r14d
0x180009ae9  mov     rdx, [rax+10h]
0x180009aed  cmp     byte ptr [rdx+19h], 0
0x180009af1  jz      short loc_180009B11
0x180009af3  mov     rcx, [rax+8]
0x180009af7  jmp     short loc_180009B06
0x180009af9  cmp     rax, [rcx+10h]
0x180009afd  jnz     short loc_180009B0C
0x180009aff  mov     rax, rcx
0x180009b02  mov     rcx, [rcx+8]
0x180009b06  cmp     byte ptr [rcx+19h], 0
0x180009b0a  jz      short loc_180009AF9
0x180009b0c  mov     rax, rcx
0x180009b0f  jmp     short loc_180009AC6
0x180009b11  mov     rax, rdx
0x180009b14  mov     rdx, [rdx]
0x180009b17  cmp     byte ptr [rdx+19h], 0
0x180009b1b  jnz     short loc_180009AC6
0x180009b1d  mov     rcx, [rdx]
0x180009b20  mov     rax, rdx
0x180009b23  mov     rdx, rcx
0x180009b26  cmp     byte ptr [rcx+19h], 0
0x180009b2a  jz      short loc_180009B1D
0x180009b2c  jmp     short loc_180009AC6
0x180009b2e  test    rbx, rbx
0x180009b31  jz      short loc_180009B3C
0x180009b33  mov     rcx, rbx; lpCriticalSection
0x180009b36  call    cs:__imp_LeaveCriticalSection
0x180009b3c  test    r14d, r14d
0x180009b3f  jnz     short loc_180009B49
0x180009b41  test    ebp, ebp
0x180009b43  jnz     short loc_180009B49
0x180009b45  test    esi, esi
0x180009b47  jz      short loc_180009B84
0x180009b49  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180009b4e  mov     rax, [rax+8]
0x180009b52  test    rax, rax
0x180009b55  jz      short loc_180009B77
0x180009b57  mov     eax, [rax]
0x180009b59  test    eax, eax
0x180009b5b  jz      short loc_180009B77
0x180009b5d  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180009b62  mov     r9d, ebp; unsigned int
0x180009b65  mov     [rsp+108h+var_E8], esi; unsigned int
0x180009b69  mov     r8d, r14d; unsigned int
0x180009b6c  mov     edx, r15d; int
0x180009b6f  mov     rcx, rax; this
0x180009b72  call    ?ScopedWatchdogHangDetected_@OfflineMapsTelemetry@@QEAAXJKKK@Z; OfflineMapsTelemetry::ScopedWatchdogHangDetected_(long,ulong,ulong,ulong)
0x180009b77  test    r14d, r14d
0x180009b7a  jnz     short loc_180009BAD
0x180009b7c  test    ebp, ebp
0x180009b7e  jnz     short loc_180009BAD
0x180009b80  test    esi, esi
0x180009b82  jnz     short loc_180009BBE
0x180009b84  xor     edx, edx; Val
0x180009b86  lea     rcx, [rsp+108h+pExceptionRecord.ExceptionFlags]; void *
0x180009b8b  mov     r8d, 94h; Size
0x180009b91  call    memset_0
0x180009b96  xor     r8d, r8d; dwFlags
0x180009b99  mov     [rsp+108h+pExceptionRecord.ExceptionCode], r15d
0x180009b9e  xor     edx, edx; pContextRecord
0x180009ba0  lea     rcx, [rsp+108h+pExceptionRecord]; pExceptionRecord
0x180009ba5  call    cs:__imp_RaiseFailFastException
0x180009bab  jmp     short loc_180009BBE
0x180009bad  call    cs:__imp_GetCurrentProcess
0x180009bb3  mov     rcx, rax; hProcess
0x180009bb6  xor     edx, edx; uExitCode
0x180009bb8  call    cs:__imp_TerminateProcess
0x180009bbe  mov     rcx, [rsp+108h+var_38]
0x180009bc6  xor     rcx, rsp; StackCookie
0x180009bc9  call    __security_check_cookie
0x180009bce  mov     rbx, [rsp+108h+arg_10]
0x180009bd6  add     rsp, 0E0h
0x180009bdd  pop     r15
0x180009bdf  pop     r14
0x180009be1  pop     rdi
0x180009be2  pop     rsi
0x180009be3  pop     rbp
0x180009be4  retn
```
