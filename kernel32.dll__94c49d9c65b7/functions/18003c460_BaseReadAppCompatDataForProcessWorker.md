# BaseReadAppCompatDataForProcessWorker

- ea: `0x18003c460`
- end: `0x18003c6d9`
- name: `BaseReadAppCompatDataForProcessWorker`
- size: `633`
- prototype: `__int64 __fastcall(HANDLE hProcess, _QWORD *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003c460`
- `0x18003c6e0`
- `0x18003c780`
- `0x18007a7d1`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003c6b9`
- `ntdll!RtlNtStatusToDosError` at `0x18003c6b9`
- `ntdll!RtlFreeHeap` at `0x18003c634`
- `ntdll!RtlFreeHeap` at `0x18003c634`
- `ntdll!RtlAllocateHeap` at `0x18003c4f6`
- `ntdll!RtlAllocateHeap` at `0x18003c4f6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003c5a3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003c5a3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003c51c`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003c533`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003c51c`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003c533`

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
0x18003c460  mov     [rsp-8+arg_18], rbx
0x18003c465  push    rbp
0x18003c466  push    rsi
0x18003c467  push    rdi
0x18003c468  push    r12
0x18003c46a  push    r13
0x18003c46c  push    r14
0x18003c46e  push    r15
0x18003c470  lea     rbp, [rsp-0BB0h]
0x18003c478  sub     rsp, 0CB0h
0x18003c47f  mov     rax, cs:__security_cookie
0x18003c486  xor     rax, rsp
0x18003c489  mov     [rbp+0BE0h+var_40], rax
0x18003c490  mov     r12, r8
0x18003c493  mov     r13, rdx
0x18003c496  mov     r15, rcx
0x18003c499  xor     edx, edx; Val
0x18003c49b  mov     r8d, 7D0h; Size
0x18003c4a1  lea     rcx, [rsp+0CE0h+var_CA0]; void *
0x18003c4a6  call    memset_0
0x18003c4ab  xor     edx, edx; Val
0x18003c4ad  lea     rcx, [rbp+0BE0h+Buffer]; void *
0x18003c4b4  mov     r8d, 488h; Size
0x18003c4ba  call    memset_0
0x18003c4bf  mov     [rsp+0CE0h+Wow64Process], 0
0x18003c4c7  mov     [rsp+0CE0h+var_CB0], 0
0x18003c4cf  test    r15, r15
0x18003c4d2  jz      loc_18003C616
0x18003c4d8  test    r13, r13
0x18003c4db  jz      loc_18003C616
0x18003c4e1  mov     rcx, gs:60h
0x18003c4ea  xor     edx, edx; Flags
0x18003c4ec  mov     r8d, 11D8h; Size
0x18003c4f2  mov     rcx, [rcx+30h]; HeapHandle
0x18003c4f6  call    cs:__imp_RtlAllocateHeap
0x18003c4fc  mov     rsi, rax
0x18003c4ff  test    rax, rax
0x18003c502  jz      loc_18003C63C
0x18003c508  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18003c50c  jz      loc_18003C666
0x18003c512  lea     rdx, [rsp+0CE0h+Wow64Process]; Wow64Process
0x18003c517  mov     rcx, r15; hProcess
0x18003c51a  xor     edi, edi
0x18003c51c  call    cs:__imp_IsWow64Process
0x18003c522  test    eax, eax
0x18003c524  jz      loc_18003C5B1
0x18003c52a  lea     rdx, [rsp+0CE0h+var_CB0]; Wow64Process
0x18003c52f  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x18003c533  call    cs:__imp_IsWow64Process
0x18003c539  test    eax, eax
0x18003c53b  jz      short loc_18003C5B1
0x18003c53d  mov     ecx, [rsp+0CE0h+var_CB0]
0x18003c541  mov     eax, [rsp+0CE0h+Wow64Process]
0x18003c545  test    ecx, ecx
0x18003c547  jnz     loc_18003C693
0x18003c54d  xor     r14d, r14d
0x18003c550  test    eax, eax
0x18003c552  jz      loc_18003C643
0x18003c558  lea     rdx, [rbp+0BE0h+Buffer]; lpBuffer
0x18003c55f  mov     rcx, r15; hProcess
0x18003c562  call    BasepGetPeb32FromProcess
0x18003c567  mov     ebx, eax
0x18003c569  test    eax, eax
0x18003c56b  jnz     loc_18003C622
0x18003c571  mov     edi, dword ptr [rbp+0BE0h+lpBaseAddress]
0x18003c577  test    rdi, rdi
0x18003c57a  jz      loc_18003C61D
0x18003c580  cmp     [rsp+0CE0h+var_CB0], 0
0x18003c585  jnz     loc_18003C6AB
0x18003c58b  mov     r9d, 11D8h; nSize
0x18003c591  mov     [rsp+0CE0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18003c59a  mov     r8, rsi; lpBuffer
0x18003c59d  mov     rdx, rdi; lpBaseAddress
0x18003c5a0  mov     rcx, r15; hProcess
0x18003c5a3  call    cs:__imp_ReadProcessMemory
0x18003c5a9  test    eax, eax
0x18003c5ab  jnz     loc_18003C68C
0x18003c5b1  mov     ebx, gs:68h
0x18003c5b9  test    ebx, ebx
0x18003c5bb  jnz     short loc_18003C622
0x18003c5bd  cmp     dword ptr [rsi+208h], 11D8h
0x18003c5c7  jnz     loc_18003C6CF
0x18003c5cd  cmp     dword ptr [rsi+20Ch], 0AC0DEDABh
0x18003c5d7  jnz     loc_18003C6CF
0x18003c5dd  mov     [r13+0], rsi
0x18003c5e1  test    r12, r12
0x18003c5e4  jnz     loc_18003C6C6
0x18003c5ea  mov     eax, ebx
0x18003c5ec  mov     rcx, [rbp+0BE0h+var_40]
0x18003c5f3  xor     rcx, rsp; StackCookie
0x18003c5f6  call    __security_check_cookie
0x18003c5fb  mov     rbx, [rsp+0CE0h+arg_18]
0x18003c603  add     rsp, 0CB0h
0x18003c60a  pop     r15
0x18003c60c  pop     r14
0x18003c60e  pop     r13
0x18003c610  pop     r12
0x18003c612  pop     rdi
0x18003c613  pop     rsi
0x18003c614  pop     rbp
0x18003c615  retn
0x18003c616  mov     ebx, 57h ; 'W'
0x18003c61b  jmp     short loc_18003C5EA
0x18003c61d  mov     ebx, 490h
0x18003c622  mov     rcx, gs:60h
0x18003c62b  mov     r8, rsi; P
0x18003c62e  xor     edx, edx; Flags
0x18003c630  mov     rcx, [rcx+30h]; HeapHandle
0x18003c634  call    cs:__imp_RtlFreeHeap
0x18003c63a  jmp     short loc_18003C5EA
0x18003c63c  mov     ebx, 8
0x18003c641  jmp     short loc_18003C5EA
0x18003c643  test    ecx, ecx
0x18003c645  jnz     short loc_18003C6A1
0x18003c647  lea     rdx, [rsp+0CE0h+var_CA0]; lpBuffer
0x18003c64c  mov     rcx, r15; hProcess
0x18003c64f  call    BasepGetPebFromProcess
0x18003c654  mov     ebx, eax
0x18003c656  test    eax, eax
0x18003c658  jnz     short loc_18003C622
0x18003c65a  mov     rdi, [rbp+0BE0h+var_9C8]
0x18003c661  jmp     loc_18003C577
0x18003c666  mov     rax, gs:60h
0x18003c66f  mov     rdi, [rax+2D8h]
0x18003c676  test    rdi, rdi
0x18003c679  jz      short loc_18003C61D
0x18003c67b  mov     r8d, 11D8h; Size
0x18003c681  mov     rdx, rdi; Src
0x18003c684  mov     rcx, rsi; void *
0x18003c687  call    memcpy_0
0x18003c68c  xor     ebx, ebx
0x18003c68e  jmp     loc_18003C5BD
0x18003c693  test    eax, eax
0x18003c695  jnz     loc_18003C54D
0x18003c69b  lea     r14d, [rax+1]
0x18003c69f  jmp     short loc_18003C643
0x18003c6a1  mov     ebx, 54Fh
0x18003c6a6  jmp     loc_18003C622
0x18003c6ab  test    r14d, r14d
0x18003c6ae  jz      loc_18003C58B
0x18003c6b4  mov     ecx, 0C0000001h; Status
0x18003c6b9  call    cs:__imp_RtlNtStatusToDosError
0x18003c6bf  mov     ebx, eax
0x18003c6c1  jmp     loc_18003C5B9
0x18003c6c6  mov     [r12], rdi
0x18003c6ca  jmp     loc_18003C5EA
0x18003c6cf  mov     eax, 0Dh
0x18003c6d4  jmp     loc_18003C5EC
```
