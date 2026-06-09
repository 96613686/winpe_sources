# TlmInitializeFirstRunExpStatus

- ea: `0x180012b08`
- end: `0x180012c1f`
- name: `TlmInitializeFirstRunExpStatus`
- size: `279`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800064e0`

## callees

- `0x180012b08`
- `0x180019bec`
- `0x18001b45c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012b59`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012b59`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012c0c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012c0c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012bd7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012bd7`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180012ba0`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180012ba0`

## pseudocode

```c
void __fastcall TlmInitializeFirstRunExpStatus(__int64 a1, void *a2, void *a3)
{
  if ( byte_18002A930 && !NtCurrentPeb()->Ldr->ShutdownInProgress && !byte_18002A968 )
  {
    TlmiInitializeProviderGlobalData(a2, a3);
    RtlAcquireSRWLockExclusive(&qword_18002A970);
    if ( !byte_18002A968 )
    {
      qword_18002A978 = a1;
      qword_18002A988 = 0;
      qword_18002A990 = a1;
      qword_18002A998 = 0;
      hTimer = CreateWaitableTimerW(0, 1, 0);
      if ( hTimer )
      {
        qword_18002A9A0 = CreateThread(0, 0, TlmiFirstRunExpWorker, 0, 0, 0);
        if ( qword_18002A9A0 )
          byte_18002A968 = 1;
      }
    }
    if ( !byte_18002A968 )
      TlmiUninitializeFirstRunExpStatus();
    RtlReleaseSRWLockExclusive(&qword_18002A970);
  }
}

```

## disassembly

```asm
0x180012b08  push    rbx
0x180012b0a  sub     rsp, 30h
0x180012b0e  cmp     cs:byte_18002A930, 0
0x180012b15  mov     r10, rdx
0x180012b18  mov     rbx, rcx
0x180012b1b  jz      loc_180012C18
0x180012b21  mov     rax, gs:60h
0x180012b2a  mov     r9, [rax+18h]
0x180012b2e  cmp     byte ptr [r9+48h], 0
0x180012b33  jnz     loc_180012C18
0x180012b39  mov     al, cs:byte_18002A968
0x180012b3f  test    al, al
0x180012b41  jnz     loc_180012C18
0x180012b47  mov     rdx, r8; void *
0x180012b4a  mov     rcx, r10; Src
0x180012b4d  call    TlmiInitializeProviderGlobalData
0x180012b52  lea     rcx, qword_18002A970
0x180012b59  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180012b60  nop     dword ptr [rax+rax+00h]
0x180012b65  mov     al, cs:byte_18002A968
0x180012b6b  test    al, al
0x180012b6d  jnz     loc_180012BF6
0x180012b73  xor     r8d, r8d; lpTimerName
0x180012b76  mov     cs:qword_18002A978, rbx
0x180012b7d  xor     ecx, ecx; lpTimerAttributes
0x180012b7f  mov     cs:qword_18002A988, 0
0x180012b8a  mov     cs:qword_18002A990, rbx
0x180012b91  mov     cs:qword_18002A998, 0
0x180012b9c  lea     edx, [r8+1]; bManualReset
0x180012ba0  call    cs:__imp_CreateWaitableTimerW
0x180012ba7  nop     dword ptr [rax+rax+00h]
0x180012bac  mov     cs:hTimer, rax
0x180012bb3  test    rax, rax
0x180012bb6  jz      short loc_180012BF6
0x180012bb8  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180012bc1  lea     r8, TlmiFirstRunExpWorker; lpStartAddress
0x180012bc8  xor     r9d, r9d; lpParameter
0x180012bcb  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180012bd3  xor     edx, edx; dwStackSize
0x180012bd5  xor     ecx, ecx; lpThreadAttributes
0x180012bd7  call    cs:__imp_CreateThread
0x180012bde  nop     dword ptr [rax+rax+00h]
0x180012be3  mov     cs:qword_18002A9A0, rax
0x180012bea  test    rax, rax
0x180012bed  jz      short loc_180012BF6
0x180012bef  mov     cs:byte_18002A968, 1
0x180012bf6  mov     al, cs:byte_18002A968
0x180012bfc  test    al, al
0x180012bfe  jnz     short loc_180012C05
0x180012c00  call    TlmiUninitializeFirstRunExpStatus
0x180012c05  lea     rcx, qword_18002A970
0x180012c0c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180012c13  nop     dword ptr [rax+rax+00h]
0x180012c18  add     rsp, 30h
0x180012c1c  pop     rbx
0x180012c1d  retn
```
