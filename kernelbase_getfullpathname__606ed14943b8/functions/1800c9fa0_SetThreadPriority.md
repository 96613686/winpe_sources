# SetThreadPriority

- ea: `0x1800c9fa0`
- end: `0x1800ca292`
- name: `SetThreadPriority`
- size: `754`
- prototype: `BOOL __stdcall(HANDLE hThread, int nPriority)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800c9d50`

## callees

- `0x18004b9d0`
- `0x1800c9fa0`
- `0x1800ca298`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800ca0e0`
- `ntdll!RtlSetLastWin32Error` at `0x1800ca246`
- `ntdll!RtlSetLastWin32Error` at `0x1800ca27a`
- `ntdll!RtlSetLastWin32Error` at `0x1800ca0e0`
- `ntdll!RtlSetLastWin32Error` at `0x1800ca246`
- `ntdll!RtlSetLastWin32Error` at `0x1800ca27a`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800ca0f3`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800ca0f3`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800ca0b1`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800ca0b1`
- `ntdll!RtlFreeHeap` at `0x1800ca204`
- `ntdll!RtlFreeHeap` at `0x1800ca204`
- `ntdll!NtSetInformationThread` at `0x1800ca008`
- `ntdll!NtSetInformationThread` at `0x1800ca194`
- `ntdll!NtSetInformationThread` at `0x1800ca1bb`
- `ntdll!NtSetInformationThread` at `0x1800ca1e2`
- `ntdll!NtSetInformationThread` at `0x1800ca008`
- `ntdll!NtSetInformationThread` at `0x1800ca194`
- `ntdll!NtSetInformationThread` at `0x1800ca1bb`
- `ntdll!NtSetInformationThread` at `0x1800ca1e2`
- `ntdll!NtQueryInformationThread` at `0x1800ca06c`
- `ntdll!NtQueryInformationThread` at `0x1800ca06c`
- `ntdll!TpCaptureCaller` at `0x1800ca01f`
- `ntdll!TpCaptureCaller` at `0x1800ca163`
- `ntdll!TpCaptureCaller` at `0x1800ca01f`
- `ntdll!TpCaptureCaller` at `0x1800ca163`

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
          v4->SavedPriorityState = v13;
LABEL_21:
          v6 = 1;
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
        goto LABEL_25;
      v9 = ThreadActualBasePriority;
    }
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, v9, SavedPriorityState + 1, 4u);
LABEL_25:
    if ( (*(_BYTE *)SavedPriorityState & 4) != 0 )
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, SavedPriorityState + 2, 4u);
    if ( (*(_BYTE *)SavedPriorityState & 8) != 0 )
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, SavedPriorityState + 3, 4u);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4->SavedPriorityState);
    v4->SavedPriorityState = 0;
    goto LABEL_21;
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
0x1800c9fa0  mov     r11, rsp
0x1800c9fa3  push    rbx
0x1800c9fa4  push    rbp
0x1800c9fa5  sub     rsp, 68h
0x1800c9fa9  xor     eax, eax
0x1800c9fab  mov     [r11+10h], edx
0x1800c9faf  xor     ebp, ebp
0x1800c9fb1  xorps   xmm0, xmm0
0x1800c9fb4  test    edx, 30000h
0x1800c9fba  mov     [r11+18h], rbp
0x1800c9fbe  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x1800c9fc3  setnz   r8b
0x1800c9fc7  test    edx, 0FFFCFFFFh
0x1800c9fcd  movups  [rsp+78h+var_48], xmm0
0x1800c9fd2  setz    al
0x1800c9fd5  movups  xmmword ptr [rsp+78h+var_38+0Ch], xmm0
0x1800c9fda  test    al, r8b
0x1800c9fdd  jnz     short loc_1800CA046
0x1800c9fdf  cmp     edx, 0Fh
0x1800c9fe2  jz      loc_1800CA090
0x1800c9fe8  cmp     edx, 0FFFFFFF1h
0x1800c9feb  jnz     short loc_1800C9FF5
0x1800c9fed  mov     dword ptr [r11+10h], 0FFFFFFF0h
0x1800c9ff5  mov     r9d, 4; ThreadInformationLength
0x1800c9ffb  lea     r8, [rsp+78h+ThreadInformation]; ThreadInformation
0x1800ca003  mov     edx, 3; ThreadInformationClass
0x1800ca008  call    cs:__imp_NtSetInformationThread
0x1800ca00f  nop     dword ptr [rax+rax+00h]
0x1800ca014  test    eax, eax
0x1800ca016  js      short loc_1800CA035
0x1800ca018  mov     ebx, 1
0x1800ca01d  mov     ecx, ebx
0x1800ca01f  call    cs:__imp_TpCaptureCaller
0x1800ca026  nop     dword ptr [rax+rax+00h]
0x1800ca02b  mov     eax, ebx
0x1800ca02d  add     rsp, 68h
0x1800ca031  pop     rbp
0x1800ca032  pop     rbx
0x1800ca033  retn
0x1800ca035  mov     ecx, eax
0x1800ca037  call    BaseSetLastNTError
0x1800ca03c  xor     eax, eax
0x1800ca03e  add     rsp, 68h
0x1800ca042  pop     rbp
0x1800ca043  pop     rbx
0x1800ca044  retn
0x1800ca046  mov     [rsp+78h+var_18], rdi
0x1800ca04b  mov     rdi, gs:30h
0x1800ca054  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x1800ca058  jz      short loc_1800CA0A0
0x1800ca05a  mov     r9d, 30h ; '0'; ThreadInformationLength
0x1800ca060  mov     [rsp+78h+ReturnLength], rbp; ReturnLength
0x1800ca065  lea     r8, [rsp+78h+var_48]; ThreadInformation
0x1800ca06a  xor     edx, edx; ThreadInformationClass
0x1800ca06c  call    cs:__imp_NtQueryInformationThread
0x1800ca073  nop     dword ptr [rax+rax+00h]
0x1800ca078  test    eax, eax
0x1800ca07a  jns     loc_1800CA21C
0x1800ca080  mov     ecx, eax
0x1800ca082  call    BaseSetLastNTError
0x1800ca087  mov     rdi, [rsp+78h+var_18]
0x1800ca08c  xor     eax, eax
0x1800ca08e  jmp     short loc_1800CA02D
0x1800ca090  mov     [rsp+78h+ThreadInformation], 10h
0x1800ca09b  jmp     loc_1800C9FF5
0x1800ca0a0  lea     rcx, BasepPriorityStateLock
0x1800ca0a7  mov     [rsp+78h+arg_0], rsi
0x1800ca0af  mov     ebx, ebp
0x1800ca0b1  call    cs:__imp_RtlAcquireSRWLockShared
0x1800ca0b8  nop     dword ptr [rax+rax+00h]
0x1800ca0bd  mov     eax, [rsp+78h+ThreadInformation]
0x1800ca0c4  cmp     eax, 20000h
0x1800ca0c9  jnz     short loc_1800CA113
0x1800ca0cb  mov     rsi, [rdi+1768h]
0x1800ca0d2  test    rsi, rsi
0x1800ca0d5  jnz     loc_1800CA174
0x1800ca0db  mov     ecx, 191h; LastError
0x1800ca0e0  call    cs:__imp_RtlSetLastWin32Error
0x1800ca0e7  nop     dword ptr [rax+rax+00h]
0x1800ca0ec  lea     rcx, BasepPriorityStateLock
0x1800ca0f3  call    cs:__imp_RtlReleaseSRWLockShared
0x1800ca0fa  nop     dword ptr [rax+rax+00h]
0x1800ca0ff  mov     rsi, [rsp+78h+arg_0]
0x1800ca107  mov     eax, ebx
0x1800ca109  mov     rdi, [rsp+78h+var_18]
0x1800ca10e  jmp     loc_1800CA02D
0x1800ca113  cmp     eax, 10000h
0x1800ca118  jnz     loc_1800CA28B
0x1800ca11e  cmp     [rdi+1768h], rbx
0x1800ca125  jnz     loc_1800CA275
0x1800ca12b  test    cs:BasepSavedPriorityState, 0Fh
0x1800ca132  jnz     loc_1800CA241
0x1800ca138  lea     rcx, [rsp+78h+arg_10]
0x1800ca140  call    BasepSetThreadBackground
0x1800ca145  test    eax, eax
0x1800ca147  js      loc_1800CA269
0x1800ca14d  mov     rax, [rsp+78h+arg_10]
0x1800ca155  mov     [rdi+1768h], rax
0x1800ca15c  mov     ebx, 1
0x1800ca161  mov     ecx, ebx
0x1800ca163  call    cs:__imp_TpCaptureCaller
0x1800ca16a  nop     dword ptr [rax+rax+00h]
0x1800ca16f  jmp     loc_1800CA0EC
0x1800ca174  mov     eax, [rsi]
0x1800ca176  test    al, 2
0x1800ca178  jz      loc_1800CA257
0x1800ca17e  mov     edx, 3; ThreadInformationClass
0x1800ca183  mov     r9d, 4; ThreadInformationLength
0x1800ca189  lea     r8, [rsi+4]; ThreadInformation
0x1800ca18d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800ca194  call    cs:__imp_NtSetInformationThread
0x1800ca19b  nop     dword ptr [rax+rax+00h]
0x1800ca1a0  test    byte ptr [rsi], 4
0x1800ca1a3  jz      short loc_1800CA1C7
0x1800ca1a5  lea     r8, [rsi+8]; ThreadInformation
0x1800ca1a9  mov     edx, 18h; ThreadInformationClass
0x1800ca1ae  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800ca1b5  mov     r9d, 4; ThreadInformationLength
0x1800ca1bb  call    cs:__imp_NtSetInformationThread
0x1800ca1c2  nop     dword ptr [rax+rax+00h]
0x1800ca1c7  test    byte ptr [rsi], 8
0x1800ca1ca  jz      short loc_1800CA1EE
0x1800ca1cc  lea     r8, [rsi+0Ch]; ThreadInformation
0x1800ca1d0  mov     edx, 16h; ThreadInformationClass
0x1800ca1d5  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800ca1dc  mov     r9d, 4; ThreadInformationLength
0x1800ca1e2  call    cs:__imp_NtSetInformationThread
0x1800ca1e9  nop     dword ptr [rax+rax+00h]
0x1800ca1ee  mov     rcx, gs:60h
0x1800ca1f7  xor     edx, edx; Flags
0x1800ca1f9  mov     r8, [rdi+1768h]; P
0x1800ca200  mov     rcx, [rcx+30h]; HeapHandle
0x1800ca204  call    cs:__imp_RtlFreeHeap
0x1800ca20b  nop     dword ptr [rax+rax+00h]
0x1800ca210  mov     [rdi+1768h], rbp
0x1800ca217  jmp     loc_1800CA15C
0x1800ca21c  mov     rax, [rdi+48h]
0x1800ca220  cmp     qword ptr [rsp+78h+var_38+8], rax
0x1800ca225  jz      loc_1800CA0A0
0x1800ca22b  mov     ecx, 0C00000EFh
0x1800ca230  call    BaseSetLastNTError
0x1800ca235  mov     rdi, [rsp+78h+var_18]
0x1800ca23a  xor     eax, eax
0x1800ca23c  jmp     loc_1800CA02D
0x1800ca241  mov     ecx, 192h; LastError
0x1800ca246  call    cs:__imp_RtlSetLastWin32Error
0x1800ca24d  nop     dword ptr [rax+rax+00h]
0x1800ca252  jmp     loc_1800CA0EC
0x1800ca257  test    al, 1
0x1800ca259  jz      loc_1800CA1A0
0x1800ca25f  mov     edx, 19h
0x1800ca264  jmp     loc_1800CA183
0x1800ca269  mov     ecx, eax
0x1800ca26b  call    BaseSetLastNTError
0x1800ca270  jmp     loc_1800CA0EC
0x1800ca275  mov     ecx, 190h; LastError
0x1800ca27a  call    cs:__imp_RtlSetLastWin32Error
0x1800ca281  nop     dword ptr [rax+rax+00h]
0x1800ca286  jmp     loc_1800CA0EC
0x1800ca28b  mov     ecx, 0C00000F0h
0x1800ca290  jmp     short loc_1800CA26B
```
