# BaseReadAppCompatDataForProcessWorker

- ea: `0x18003ebe0`
- end: `0x18003ee7e`
- name: `BaseReadAppCompatDataForProcessWorker`
- size: `670`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003ebe0`
- `0x18003ee84`
- `0x18003ef38`
- `0x180082751`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003ee58`
- `ntdll!RtlNtStatusToDosError` at `0x18003ee58`
- `ntdll!RtlFreeHeap` at `0x18003edcd`
- `ntdll!RtlFreeHeap` at `0x18003edcd`
- `ntdll!RtlAllocateHeap` at `0x18003ec76`
- `ntdll!RtlAllocateHeap` at `0x18003ec76`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003ed35`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003ed35`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003eca2`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003ecbf`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003eca2`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003ecbf`

## pseudocode

```c
__int64 __fastcall BaseReadAppCompatDataForProcessWorker(HANDLE hProcess, _QWORD *a2, unsigned __int64 *a3)
{
  _DWORD *Heap; // rsi
  unsigned __int64 pShimData; // rdi
  int v8; // r14d
  ULONG Peb32FromProcess; // ebx
  struct _PEB *v11; // rax
  BOOL v12; // [rsp+30h] [rbp-D0h] BYREF
  BOOL Wow64Process; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v14[728]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v15; // [rsp+318h] [rbp+218h]
  _BYTE Buffer[488]; // [rsp+810h] [rbp+710h] BYREF
  LPCVOID lpBaseAddress; // [rsp+9F8h] [rbp+8F8h]

  memset_0(v14, 0, 0x7D0u);
  memset_0(Buffer, 0, 0x488u);
  Wow64Process = 0;
  v12 = 0;
  if ( !hProcess || !a2 )
    return 87;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x11D8u);
  if ( !Heap )
    return 8;
  if ( hProcess == (HANDLE)-1LL )
  {
    v11 = NtCurrentPeb();
    pShimData = (unsigned __int64)v11->pShimData;
    if ( pShimData )
    {
      memcpy_0(Heap, v11->pShimData, 0x11D8u);
      goto LABEL_30;
    }
LABEL_22:
    Peb32FromProcess = 1168;
    goto LABEL_23;
  }
  pShimData = 0;
  if ( !IsWow64Process(hProcess, &Wow64Process) || !IsWow64Process((HANDLE)0xFFFFFFFFFFFFFFFFLL, &v12) )
    goto LABEL_14;
  if ( !v12 || Wow64Process )
  {
    v8 = 0;
    if ( Wow64Process )
    {
      Peb32FromProcess = BasepGetPeb32FromProcess(hProcess, Buffer);
      if ( !Peb32FromProcess )
      {
        pShimData = (unsigned int)lpBaseAddress;
        goto LABEL_11;
      }
LABEL_23:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      return Peb32FromProcess;
    }
  }
  else
  {
    v8 = 1;
  }
  if ( v12 )
  {
    Peb32FromProcess = 1359;
    goto LABEL_23;
  }
  Peb32FromProcess = BasepGetPebFromProcess(hProcess, v14);
  if ( Peb32FromProcess )
    goto LABEL_23;
  pShimData = v15;
LABEL_11:
  if ( !pShimData )
    goto LABEL_22;
  if ( !v12 || !v8 )
  {
    if ( !ReadProcessMemory(hProcess, (LPCVOID)pShimData, Heap, 0x11D8u, 0) )
    {
LABEL_14:
      Peb32FromProcess = NtCurrentTeb()->LastErrorValue;
      goto LABEL_15;
    }
LABEL_30:
    Peb32FromProcess = 0;
    goto LABEL_16;
  }
  Peb32FromProcess = RtlNtStatusToDosError(-1073741823);
LABEL_15:
  if ( Peb32FromProcess )
    goto LABEL_23;
LABEL_16:
  if ( Heap[130] == 4568 && Heap[131] == -1408373333 )
  {
    *a2 = Heap;
    if ( a3 )
      *a3 = pShimData;
    return Peb32FromProcess;
  }
  return 13;
}

```

## disassembly

```asm
0x18003ebe0  mov     [rsp-8+arg_18], rbx
0x18003ebe5  push    rbp
0x18003ebe6  push    rsi
0x18003ebe7  push    rdi
0x18003ebe8  push    r12
0x18003ebea  push    r13
0x18003ebec  push    r14
0x18003ebee  push    r15
0x18003ebf0  lea     rbp, [rsp-0BB0h]
0x18003ebf8  sub     rsp, 0CB0h
0x18003ebff  mov     rax, cs:__security_cookie
0x18003ec06  xor     rax, rsp
0x18003ec09  mov     [rbp+0BE0h+var_40], rax
0x18003ec10  mov     r12, r8
0x18003ec13  mov     r13, rdx
0x18003ec16  mov     r15, rcx
0x18003ec19  xor     edx, edx; Val
0x18003ec1b  mov     r8d, 7D0h; Size
0x18003ec21  lea     rcx, [rsp+0CE0h+var_CA0]; void *
0x18003ec26  call    memset_0
0x18003ec2b  xor     edx, edx; Val
0x18003ec2d  lea     rcx, [rbp+0BE0h+Buffer]; void *
0x18003ec34  mov     r8d, 488h; Size
0x18003ec3a  call    memset_0
0x18003ec3f  mov     [rsp+0CE0h+Wow64Process], 0
0x18003ec47  mov     [rsp+0CE0h+var_CB0], 0
0x18003ec4f  test    r15, r15
0x18003ec52  jz      loc_18003EDAF
0x18003ec58  test    r13, r13
0x18003ec5b  jz      loc_18003EDAF
0x18003ec61  mov     rcx, gs:60h
0x18003ec6a  xor     edx, edx; Flags
0x18003ec6c  mov     r8d, 11D8h; Size
0x18003ec72  mov     rcx, [rcx+30h]; HeapHandle
0x18003ec76  call    cs:__imp_RtlAllocateHeap
0x18003ec7d  nop     dword ptr [rax+rax+00h]
0x18003ec82  mov     rsi, rax
0x18003ec85  test    rax, rax
0x18003ec88  jz      loc_18003EDDB
0x18003ec8e  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18003ec92  jz      loc_18003EE05
0x18003ec98  lea     rdx, [rsp+0CE0h+Wow64Process]; Wow64Process
0x18003ec9d  mov     rcx, r15; hProcess
0x18003eca0  xor     edi, edi
0x18003eca2  call    cs:__imp_IsWow64Process
0x18003eca9  nop     dword ptr [rax+rax+00h]
0x18003ecae  test    eax, eax
0x18003ecb0  jz      loc_18003ED49
0x18003ecb6  lea     rdx, [rsp+0CE0h+var_CB0]; Wow64Process
0x18003ecbb  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x18003ecbf  call    cs:__imp_IsWow64Process
0x18003ecc6  nop     dword ptr [rax+rax+00h]
0x18003eccb  test    eax, eax
0x18003eccd  jz      short loc_18003ED49
0x18003eccf  mov     ecx, [rsp+0CE0h+var_CB0]
0x18003ecd3  mov     eax, [rsp+0CE0h+Wow64Process]
0x18003ecd7  test    ecx, ecx
0x18003ecd9  jnz     loc_18003EE32
0x18003ecdf  xor     r14d, r14d
0x18003ece2  test    eax, eax
0x18003ece4  jz      loc_18003EDE2
0x18003ecea  lea     rdx, [rbp+0BE0h+Buffer]; lpBuffer
0x18003ecf1  mov     rcx, r15; hProcess
0x18003ecf4  call    BasepGetPeb32FromProcess
0x18003ecf9  mov     ebx, eax
0x18003ecfb  test    eax, eax
0x18003ecfd  jnz     loc_18003EDBB
0x18003ed03  mov     edi, dword ptr [rbp+0BE0h+lpBaseAddress]
0x18003ed09  test    rdi, rdi
0x18003ed0c  jz      loc_18003EDB6
0x18003ed12  cmp     [rsp+0CE0h+var_CB0], 0
0x18003ed17  jnz     loc_18003EE4A
0x18003ed1d  mov     r9d, 11D8h; nSize
0x18003ed23  mov     [rsp+0CE0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18003ed2c  mov     r8, rsi; lpBuffer
0x18003ed2f  mov     rdx, rdi; lpBaseAddress
0x18003ed32  mov     rcx, r15; hProcess
0x18003ed35  call    cs:__imp_ReadProcessMemory
0x18003ed3c  nop     dword ptr [rax+rax+00h]
0x18003ed41  test    eax, eax
0x18003ed43  jnz     loc_18003EE2B
0x18003ed49  mov     ebx, gs:68h
0x18003ed51  test    ebx, ebx
0x18003ed53  jnz     short loc_18003EDBB
0x18003ed55  cmp     dword ptr [rsi+208h], 11D8h
0x18003ed5f  jnz     loc_18003EE74
0x18003ed65  cmp     dword ptr [rsi+20Ch], 0AC0DEDABh
0x18003ed6f  jnz     loc_18003EE74
0x18003ed75  mov     [r13+0], rsi
0x18003ed79  test    r12, r12
0x18003ed7c  jnz     loc_18003EE6B
0x18003ed82  mov     eax, ebx
0x18003ed84  mov     rcx, [rbp+0BE0h+var_40]
0x18003ed8b  xor     rcx, rsp; StackCookie
0x18003ed8e  call    __security_check_cookie
0x18003ed93  mov     rbx, [rsp+0CE0h+arg_18]
0x18003ed9b  add     rsp, 0CB0h
0x18003eda2  pop     r15
0x18003eda4  pop     r14
0x18003eda6  pop     r13
0x18003eda8  pop     r12
0x18003edaa  pop     rdi
0x18003edab  pop     rsi
0x18003edac  pop     rbp
0x18003edad  retn
0x18003edaf  mov     ebx, 57h ; 'W'
0x18003edb4  jmp     short loc_18003ED82
0x18003edb6  mov     ebx, 490h
0x18003edbb  mov     rcx, gs:60h
0x18003edc4  mov     r8, rsi; P
0x18003edc7  xor     edx, edx; Flags
0x18003edc9  mov     rcx, [rcx+30h]; HeapHandle
0x18003edcd  call    cs:__imp_RtlFreeHeap
0x18003edd4  nop     dword ptr [rax+rax+00h]
0x18003edd9  jmp     short loc_18003ED82
0x18003eddb  mov     ebx, 8
0x18003ede0  jmp     short loc_18003ED82
0x18003ede2  test    ecx, ecx
0x18003ede4  jnz     short loc_18003EE40
0x18003ede6  lea     rdx, [rsp+0CE0h+var_CA0]; lpBuffer
0x18003edeb  mov     rcx, r15; hProcess
0x18003edee  call    BasepGetPebFromProcess
0x18003edf3  mov     ebx, eax
0x18003edf5  test    eax, eax
0x18003edf7  jnz     short loc_18003EDBB
0x18003edf9  mov     rdi, [rbp+0BE0h+var_9C8]
0x18003ee00  jmp     loc_18003ED09
0x18003ee05  mov     rax, gs:60h
0x18003ee0e  mov     rdi, [rax+2D8h]
0x18003ee15  test    rdi, rdi
0x18003ee18  jz      short loc_18003EDB6
0x18003ee1a  mov     r8d, 11D8h; Size
0x18003ee20  mov     rdx, rdi; Src
0x18003ee23  mov     rcx, rsi; void *
0x18003ee26  call    memcpy_0
0x18003ee2b  xor     ebx, ebx
0x18003ee2d  jmp     loc_18003ED55
0x18003ee32  test    eax, eax
0x18003ee34  jnz     loc_18003ECDF
0x18003ee3a  lea     r14d, [rax+1]
0x18003ee3e  jmp     short loc_18003EDE2
0x18003ee40  mov     ebx, 54Fh
0x18003ee45  jmp     loc_18003EDBB
0x18003ee4a  test    r14d, r14d
0x18003ee4d  jz      loc_18003ED1D
0x18003ee53  mov     ecx, 0C0000001h; Status
0x18003ee58  call    cs:__imp_RtlNtStatusToDosError
0x18003ee5f  nop     dword ptr [rax+rax+00h]
0x18003ee64  mov     ebx, eax
0x18003ee66  jmp     loc_18003ED51
0x18003ee6b  mov     [r12], rdi
0x18003ee6f  jmp     loc_18003ED82
0x18003ee74  mov     eax, 0Dh
0x18003ee79  jmp     loc_18003ED84
```
