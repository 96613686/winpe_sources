# SetThreadPriority

- ea: `0x1800c44b0`
- end: `0x1800c475c`
- name: `SetThreadPriority`
- size: `684`
- prototype: `BOOL __stdcall(HANDLE hThread, int nPriority)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800c4290`

## callees

- `0x1800134a0`
- `0x1800c44b0`
- `0x1800c4764`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800c45d6`
- `ntdll!RtlSetLastWin32Error` at `0x1800c471c`
- `ntdll!RtlSetLastWin32Error` at `0x1800c474a`
- `ntdll!RtlSetLastWin32Error` at `0x1800c45d6`
- `ntdll!RtlSetLastWin32Error` at `0x1800c471c`
- `ntdll!RtlSetLastWin32Error` at `0x1800c474a`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800c45e3`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800c45e3`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800c45ad`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800c45ad`
- `ntdll!RtlFreeHeap` at `0x1800c46d3`
- `ntdll!RtlFreeHeap` at `0x1800c46d3`
- `ntdll!NtSetInformationThread` at `0x1800c4518`
- `ntdll!NtSetInformationThread` at `0x1800c4675`
- `ntdll!NtSetInformationThread` at `0x1800c4696`
- `ntdll!NtSetInformationThread` at `0x1800c46b7`
- `ntdll!NtSetInformationThread` at `0x1800c4518`
- `ntdll!NtSetInformationThread` at `0x1800c4675`
- `ntdll!NtSetInformationThread` at `0x1800c4696`
- `ntdll!NtSetInformationThread` at `0x1800c46b7`
- `ntdll!NtQueryInformationThread` at `0x1800c456e`
- `ntdll!NtQueryInformationThread` at `0x1800c456e`
- `ntdll!TpCaptureCaller` at `0x1800c4529`
- `ntdll!TpCaptureCaller` at `0x1800c464d`
- `ntdll!TpCaptureCaller` at `0x1800c46e7`
- `ntdll!TpCaptureCaller` at `0x1800c4529`
- `ntdll!TpCaptureCaller` at `0x1800c464d`
- `ntdll!TpCaptureCaller` at `0x1800c46e7`

## pseudocode

```c
BOOL __stdcall SetThreadPriority(HANDLE hThread, int nPriority)
{
  NTSTATUS v2; // eax
  struct _TEB *v4; // rdi
  NTSTATUS InformationThread; // eax
  BOOL v6; // ebx
  _DWORD *SavedPriorityState; // rsi
  int v8; // eax
  THREADINFOCLASS v9; // edx
  __int64 v10; // rcx
  _OWORD v11[3]; // [rsp+30h] [rbp-48h] BYREF
  int ThreadInformation; // [rsp+88h] [rbp+10h] BYREF
  void *v13; // [rsp+90h] [rbp+18h] BYREF

  ThreadInformation = nPriority;
  v13 = 0;
  memset(v11, 0, 44);
  if ( (nPriority & 0x30000) != 0 && (nPriority & 0xFFFCFFFF) == 0 )
  {
    v4 = NtCurrentTeb();
    if ( hThread != (HANDLE)-2LL )
    {
      InformationThread = NtQueryInformationThread(hThread, ThreadBasicInformation, v11, 0x30u, 0);
      if ( InformationThread < 0 )
      {
        BaseSetLastNTError((unsigned int)InformationThread);
        return 0;
      }
      if ( (HANDLE)*((_QWORD *)&v11[1] + 1) != v4->ClientId.UniqueThread )
      {
        BaseSetLastNTError(3221225711LL);
        return 0;
      }
    }
    v6 = 0;
    RtlAcquireSRWLockShared(&BasepPriorityStateLock);
    if ( ThreadInformation != 0x20000 )
    {
      if ( ThreadInformation == 0x10000 )
      {
        if ( v4->SavedPriorityState )
        {
          RtlSetLastWin32Error(0x190u);
          goto LABEL_15;
        }
        if ( (BasepSavedPriorityState & 0xF) != 0 )
        {
          RtlSetLastWin32Error(0x192u);
          goto LABEL_15;
        }
        v8 = BasepSetThreadBackground(&v13);
        if ( v8 >= 0 )
        {
          v6 = 1;
          v4->SavedPriorityState = v13;
          TpCaptureCaller(1);
          goto LABEL_15;
        }
        v10 = (unsigned int)v8;
      }
      else
      {
        v10 = 3221225712LL;
      }
      BaseSetLastNTError(v10);
      goto LABEL_15;
    }
    SavedPriorityState = v4->SavedPriorityState;
    if ( !SavedPriorityState )
    {
      RtlSetLastWin32Error(0x191u);
LABEL_15:
      RtlReleaseSRWLockShared(&BasepPriorityStateLock);
      return v6;
    }
    if ( (*SavedPriorityState & 2) != 0 )
    {
      v9 = ThreadBasePriority;
    }
    else
    {
      if ( (*SavedPriorityState & 1) == 0 )
        goto LABEL_24;
      v9 = ThreadActualBasePriority;
    }
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, v9, SavedPriorityState + 1, 4u);
LABEL_24:
    if ( (*(_BYTE *)SavedPriorityState & 4) != 0 )
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, SavedPriorityState + 2, 4u);
    if ( (*(_BYTE *)SavedPriorityState & 8) != 0 )
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, SavedPriorityState + 3, 4u);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4->SavedPriorityState);
    v6 = 1;
    v4->SavedPriorityState = 0;
    TpCaptureCaller(1);
    goto LABEL_15;
  }
  if ( nPriority == 15 )
  {
    ThreadInformation = 16;
  }
  else if ( nPriority == -15 )
  {
    ThreadInformation = -16;
  }
  v2 = NtSetInformationThread(hThread, ThreadBasePriority, &ThreadInformation, 4u);
  if ( v2 < 0 )
  {
    BaseSetLastNTError((unsigned int)v2);
    return 0;
  }
  else
  {
    TpCaptureCaller(1);
    return 1;
  }
}

```

## disassembly

```asm
0x1800c44b0  mov     r11, rsp
0x1800c44b3  push    rbx
0x1800c44b4  push    rbp
0x1800c44b5  sub     rsp, 68h
0x1800c44b9  xor     eax, eax
0x1800c44bb  mov     [r11+10h], edx
0x1800c44bf  xor     ebp, ebp
0x1800c44c1  xorps   xmm0, xmm0
0x1800c44c4  test    edx, 30000h
0x1800c44ca  mov     [r11+18h], rbp
0x1800c44ce  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x1800c44d3  setnz   r8b
0x1800c44d7  test    edx, 0FFFCFFFFh
0x1800c44dd  movups  [rsp+78h+var_48], xmm0
0x1800c44e2  setz    al
0x1800c44e5  movups  xmmword ptr [rsp+78h+var_38+0Ch], xmm0
0x1800c44ea  test    al, r8b
0x1800c44ed  jnz     short loc_1800C4548
0x1800c44ef  cmp     edx, 0Fh
0x1800c44f2  jz      loc_1800C458C
0x1800c44f8  cmp     edx, 0FFFFFFF1h
0x1800c44fb  jnz     short loc_1800C4505
0x1800c44fd  mov     dword ptr [r11+10h], 0FFFFFFF0h
0x1800c4505  mov     r9d, 4; ThreadInformationLength
0x1800c450b  lea     r8, [rsp+78h+ThreadInformation]; ThreadInformation
0x1800c4513  mov     edx, 3; ThreadInformationClass
0x1800c4518  call    cs:__imp_NtSetInformationThread
0x1800c451e  test    eax, eax
0x1800c4520  js      short loc_1800C4538
0x1800c4522  mov     ebx, 1
0x1800c4527  mov     ecx, ebx
0x1800c4529  call    cs:__imp_TpCaptureCaller
0x1800c452f  mov     eax, ebx
0x1800c4531  add     rsp, 68h
0x1800c4535  pop     rbp
0x1800c4536  pop     rbx
0x1800c4537  retn
0x1800c4538  mov     ecx, eax
0x1800c453a  call    BaseSetLastNTError
0x1800c453f  xor     eax, eax
0x1800c4541  add     rsp, 68h
0x1800c4545  pop     rbp
0x1800c4546  pop     rbx
0x1800c4547  retn
0x1800c4548  mov     [rsp+78h+var_18], rdi
0x1800c454d  mov     rdi, gs:30h
0x1800c4556  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x1800c455a  jz      short loc_1800C459C
0x1800c455c  mov     r9d, 30h ; '0'; ThreadInformationLength
0x1800c4562  mov     [rsp+78h+ReturnLength], rbp; ReturnLength
0x1800c4567  lea     r8, [rsp+78h+var_48]; ThreadInformation
0x1800c456c  xor     edx, edx; ThreadInformationClass
0x1800c456e  call    cs:__imp_NtQueryInformationThread
0x1800c4574  test    eax, eax
0x1800c4576  jns     loc_1800C46F2
0x1800c457c  mov     ecx, eax
0x1800c457e  call    BaseSetLastNTError
0x1800c4583  mov     rdi, [rsp+78h+var_18]
0x1800c4588  xor     eax, eax
0x1800c458a  jmp     short loc_1800C4531
0x1800c458c  mov     [rsp+78h+ThreadInformation], 10h
0x1800c4597  jmp     loc_1800C4505
0x1800c459c  lea     rcx, BasepPriorityStateLock
0x1800c45a3  mov     [rsp+78h+arg_0], rsi
0x1800c45ab  mov     ebx, ebp
0x1800c45ad  call    cs:__imp_RtlAcquireSRWLockShared
0x1800c45b3  mov     eax, [rsp+78h+ThreadInformation]
0x1800c45ba  cmp     eax, 20000h
0x1800c45bf  jnz     short loc_1800C45FD
0x1800c45c1  mov     rsi, [rdi+1768h]
0x1800c45c8  test    rsi, rsi
0x1800c45cb  jnz     loc_1800C4655
0x1800c45d1  mov     ecx, 191h; LastError
0x1800c45d6  call    cs:__imp_RtlSetLastWin32Error
0x1800c45dc  lea     rcx, BasepPriorityStateLock
0x1800c45e3  call    cs:__imp_RtlReleaseSRWLockShared
0x1800c45e9  mov     rsi, [rsp+78h+arg_0]
0x1800c45f1  mov     eax, ebx
0x1800c45f3  mov     rdi, [rsp+78h+var_18]
0x1800c45f8  jmp     loc_1800C4531
0x1800c45fd  cmp     eax, 10000h
0x1800c4602  jnz     loc_1800C4755
0x1800c4608  cmp     [rdi+1768h], rbx
0x1800c460f  jnz     loc_1800C4745
0x1800c4615  test    byte ptr cs:BasepSavedPriorityState, 0Fh
0x1800c461c  jnz     loc_1800C4717
0x1800c4622  lea     rcx, [rsp+78h+arg_10]
0x1800c462a  call    BasepSetThreadBackground
0x1800c462f  test    eax, eax
0x1800c4631  js      loc_1800C4739
0x1800c4637  mov     rax, [rsp+78h+arg_10]
0x1800c463f  mov     ebx, 1
0x1800c4644  mov     ecx, ebx
0x1800c4646  mov     [rdi+1768h], rax
0x1800c464d  call    cs:__imp_TpCaptureCaller
0x1800c4653  jmp     short loc_1800C45DC
0x1800c4655  mov     eax, [rsi]
0x1800c4657  test    al, 2
0x1800c4659  jz      loc_1800C4727
0x1800c465f  mov     edx, 3; ThreadInformationClass
0x1800c4664  mov     r9d, 4; ThreadInformationLength
0x1800c466a  lea     r8, [rsi+4]; ThreadInformation
0x1800c466e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c4675  call    cs:__imp_NtSetInformationThread
0x1800c467b  test    byte ptr [rsi], 4
0x1800c467e  jz      short loc_1800C469C
0x1800c4680  lea     r8, [rsi+8]; ThreadInformation
0x1800c4684  mov     edx, 18h; ThreadInformationClass
0x1800c4689  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c4690  mov     r9d, 4; ThreadInformationLength
0x1800c4696  call    cs:__imp_NtSetInformationThread
0x1800c469c  test    byte ptr [rsi], 8
0x1800c469f  jz      short loc_1800C46BD
0x1800c46a1  lea     r8, [rsi+0Ch]; ThreadInformation
0x1800c46a5  mov     edx, 16h; ThreadInformationClass
0x1800c46aa  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c46b1  mov     r9d, 4; ThreadInformationLength
0x1800c46b7  call    cs:__imp_NtSetInformationThread
0x1800c46bd  mov     rcx, gs:60h
0x1800c46c6  xor     edx, edx; Flags
0x1800c46c8  mov     r8, [rdi+1768h]; P
0x1800c46cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800c46d3  call    cs:__imp_RtlFreeHeap
0x1800c46d9  mov     ebx, 1
0x1800c46de  mov     [rdi+1768h], rbp
0x1800c46e5  mov     ecx, ebx
0x1800c46e7  call    cs:__imp_TpCaptureCaller
0x1800c46ed  jmp     loc_1800C45DC
0x1800c46f2  mov     rax, [rdi+48h]
0x1800c46f6  cmp     qword ptr [rsp+78h+var_38+8], rax
0x1800c46fb  jz      loc_1800C459C
0x1800c4701  mov     ecx, 0C00000EFh
0x1800c4706  call    BaseSetLastNTError
0x1800c470b  mov     rdi, [rsp+78h+var_18]
0x1800c4710  xor     eax, eax
0x1800c4712  jmp     loc_1800C4531
0x1800c4717  mov     ecx, 192h; LastError
0x1800c471c  call    cs:__imp_RtlSetLastWin32Error
0x1800c4722  jmp     loc_1800C45DC
0x1800c4727  test    al, 1
0x1800c4729  jz      loc_1800C467B
0x1800c472f  mov     edx, 19h
0x1800c4734  jmp     loc_1800C4664
0x1800c4739  mov     ecx, eax
0x1800c473b  call    BaseSetLastNTError
0x1800c4740  jmp     loc_1800C45DC
0x1800c4745  mov     ecx, 190h; LastError
0x1800c474a  call    cs:__imp_RtlSetLastWin32Error
0x1800c4750  jmp     loc_1800C45DC
0x1800c4755  mov     ecx, 0C00000F0h
0x1800c475a  jmp     short loc_1800C473B
```
