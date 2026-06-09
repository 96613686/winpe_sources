# BasepSetThreadBackground

- ea: `0x1800ca298`
- end: `0x1800ca489`
- name: `BasepSetThreadBackground`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800c9fa0`

## callees

- `0x1800ca298`
- `0x1800f3d20`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1801a08cc`
- `ntdll!RtlFreeHeap` at `0x1801a08cc`
- `ntdll!NtSetInformationThread` at `0x1800ca3d3`
- `ntdll!NtSetInformationThread` at `0x1800ca3fc`
- `ntdll!NtSetInformationThread` at `0x1800ca424`
- `ntdll!NtSetInformationThread` at `0x1800ca3d3`
- `ntdll!NtSetInformationThread` at `0x1800ca3fc`
- `ntdll!NtSetInformationThread` at `0x1800ca424`
- `ntdll!NtQueryInformationThread` at `0x1800ca321`
- `ntdll!NtQueryInformationThread` at `0x1800ca35d`
- `ntdll!NtQueryInformationThread` at `0x1800ca38e`
- `ntdll!NtQueryInformationThread` at `0x1800ca321`
- `ntdll!NtQueryInformationThread` at `0x1800ca35d`
- `ntdll!NtQueryInformationThread` at `0x1800ca38e`
- `ntdll!RtlAllocateHeap` at `0x1800ca2ed`
- `ntdll!RtlAllocateHeap` at `0x1800ca2ed`

## pseudocode

```c
__int64 __fastcall BasepSetThreadBackground(_QWORD *a1)
{
  _DWORD *Heap; // rdi
  __int64 v3; // rdx
  NTSTATUS InformationThread; // ebx
  int v5; // eax
  THREADINFOCLASS v6; // edx
  char v7; // al
  _BYTE ThreadInformation[44]; // [rsp+30h] [rbp-29h] BYREF
  int v10; // [rsp+5Ch] [rbp+3h]
  __int128 v11; // [rsp+60h] [rbp+7h] BYREF

  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  v11 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData | 8, 0x10u);
  if ( !Heap )
    return (unsigned int)-1073741801;
  InformationThread = NtQueryInformationThread(
                        (HANDLE)0xFFFFFFFFFFFFFFFELL,
                        ThreadBasicInformation,
                        ThreadInformation,
                        0x30u,
                        0);
  if ( InformationThread < 0 )
    goto LABEL_17;
  v5 = v10;
  *Heap |= 2u;
  Heap[1] = v5;
  InformationThread = NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, Heap + 2, 4u, 0);
  if ( InformationThread < 0 )
    goto LABEL_17;
  *Heap |= 4u;
  InformationThread = NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, Heap + 3, 4u, 0);
  if ( InformationThread < 0 )
    goto LABEL_17;
  *Heap |= 8u;
  v6 = ThreadBasePriority;
  DWORD1(v11) = 4;
  *((_QWORD *)&v11 + 1) = 1;
  LODWORD(v11) = v11 | 0xD;
  if ( (v11 & 2) == 0 )
    v6 = ThreadActualBasePriority;
  InformationThread = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, v6, (char *)&v11 + 4, 4u);
  if ( InformationThread < 0 )
    goto LABEL_17;
  v7 = v11;
  if ( (v11 & 4) != 0 )
  {
    InformationThread = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, (char *)&v11 + 8, 4u);
    if ( InformationThread < 0 )
      goto LABEL_17;
    v7 = v11;
  }
  if ( (v7 & 8) == 0
    || (InformationThread = NtSetInformationThread(
                              (HANDLE)0xFFFFFFFFFFFFFFFELL,
                              ThreadIoPriority,
                              (char *)&v11 + 12,
                              4u),
        InformationThread >= 0) )
  {
    *a1 = Heap;
    return 0;
  }
LABEL_17:
  if ( (v11 & 7) != 0 )
  {
    LOBYTE(v3) = 1;
    BasepSetThreadPriorities(Heap, v3);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)InformationThread;
}

```

## disassembly

```asm
0x1800ca298  push    rbp
0x1800ca29a  push    rbx
0x1800ca29b  push    rsi
0x1800ca29c  push    rdi
0x1800ca29d  push    r12
0x1800ca29f  push    r15
0x1800ca2a1  lea     rbp, [rsp-2Fh]
0x1800ca2a6  sub     rsp, 88h
0x1800ca2ad  mov     rax, cs:__security_cookie
0x1800ca2b4  xor     rax, rsp
0x1800ca2b7  mov     [rbp+57h+var_40], rax
0x1800ca2bb  mov     edx, cs:KernelBaseGlobalData
0x1800ca2c1  xorps   xmm0, xmm0
0x1800ca2c4  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800ca2c8  mov     rsi, rcx
0x1800ca2cb  xor     eax, eax
0x1800ca2cd  movups  xmmword ptr [rbp+57h+var_70+0Ch], xmm0
0x1800ca2d1  or      edx, 8; Flags
0x1800ca2d4  movups  [rbp+57h+ThreadInformation], xmm0
0x1800ca2d8  lea     r8d, [rax+10h]; Size
0x1800ca2dc  movups  [rbp+57h+var_50], xmm0
0x1800ca2e0  mov     rcx, gs:60h
0x1800ca2e9  mov     rcx, [rcx+30h]; HeapHandle
0x1800ca2ed  call    cs:__imp_RtlAllocateHeap
0x1800ca2f4  nop     dword ptr [rax+rax+00h]
0x1800ca2f9  mov     rdi, rax
0x1800ca2fc  test    rax, rax
0x1800ca2ff  jz      loc_1800CA468
0x1800ca305  xor     edx, edx; ThreadInformationClass
0x1800ca307  mov     [rsp+0B0h+ReturnLength], 0; ReturnLength
0x1800ca310  mov     r9d, 30h ; '0'; ThreadInformationLength
0x1800ca316  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x1800ca31a  lea     r12, [rdx-2]
0x1800ca31e  mov     rcx, r12; ThreadHandle
0x1800ca321  call    cs:__imp_NtQueryInformationThread
0x1800ca328  nop     dword ptr [rax+rax+00h]
0x1800ca32d  mov     ebx, eax
0x1800ca32f  test    eax, eax
0x1800ca331  js      loc_1800CA46F
0x1800ca337  mov     eax, [rbp+57h+var_54]
0x1800ca33a  lea     r15d, [r12+6]
0x1800ca33f  or      dword ptr [rdi], 2
0x1800ca342  lea     r8, [rdi+8]; ThreadInformation
0x1800ca346  mov     r9d, r15d; ThreadInformationLength
0x1800ca349  mov     [rdi+4], eax
0x1800ca34c  lea     edx, [r12+1Ah]; ThreadInformationClass
0x1800ca351  mov     [rsp+0B0h+ReturnLength], 0; ReturnLength
0x1800ca35a  mov     rcx, r12; ThreadHandle
0x1800ca35d  call    cs:__imp_NtQueryInformationThread
0x1800ca364  nop     dword ptr [rax+rax+00h]
0x1800ca369  mov     ebx, eax
0x1800ca36b  test    eax, eax
0x1800ca36d  js      loc_1800CA46F
0x1800ca373  or      [rdi], r15d
0x1800ca376  lea     r8, [rdi+0Ch]; ThreadInformation
0x1800ca37a  mov     r9d, r15d; ThreadInformationLength
0x1800ca37d  mov     [rsp+0B0h+ReturnLength], 0; ReturnLength
0x1800ca386  lea     edx, [r12+18h]; ThreadInformationClass
0x1800ca38b  mov     rcx, r12; ThreadHandle
0x1800ca38e  call    cs:__imp_NtQueryInformationThread
0x1800ca395  nop     dword ptr [rax+rax+00h]
0x1800ca39a  mov     ebx, eax
0x1800ca39c  test    eax, eax
0x1800ca39e  js      loc_1800CA46F
0x1800ca3a4  or      dword ptr [rdi], 8
0x1800ca3a7  lea     r8, [rbp+57h+var_50+4]; ThreadInformation
0x1800ca3ab  mov     eax, dword ptr [rbp+57h+var_50]
0x1800ca3ae  lea     edx, [r12+5]; ThreadInformationClass
0x1800ca3b3  or      eax, 0Dh
0x1800ca3b6  mov     dword ptr [rbp+57h+var_50+4], r15d
0x1800ca3ba  mov     qword ptr [rbp+57h+var_50+8], 1
0x1800ca3c2  mov     r9d, r15d; ThreadInformationLength
0x1800ca3c5  mov     dword ptr [rbp+57h+var_50], eax
0x1800ca3c8  mov     rcx, r12; ThreadHandle
0x1800ca3cb  test    al, 2
0x1800ca3cd  jz      loc_1800CA45E
0x1800ca3d3  call    cs:__imp_NtSetInformationThread
0x1800ca3da  nop     dword ptr [rax+rax+00h]
0x1800ca3df  mov     ebx, eax
0x1800ca3e1  test    eax, eax
0x1800ca3e3  js      short loc_1800CA436
0x1800ca3e5  mov     eax, dword ptr [rbp+57h+var_50]
0x1800ca3e8  test    r15b, al
0x1800ca3eb  jz      short loc_1800CA411
0x1800ca3ed  mov     r9d, r15d; ThreadInformationLength
0x1800ca3f0  lea     r8, [rbp+57h+var_50+8]; ThreadInformation
0x1800ca3f4  mov     edx, 18h; ThreadInformationClass
0x1800ca3f9  mov     rcx, r12; ThreadHandle
0x1800ca3fc  call    cs:__imp_NtSetInformationThread
0x1800ca403  nop     dword ptr [rax+rax+00h]
0x1800ca408  mov     ebx, eax
0x1800ca40a  test    eax, eax
0x1800ca40c  js      short loc_1800CA436
0x1800ca40e  mov     eax, dword ptr [rbp+57h+var_50]
0x1800ca411  test    al, 8
0x1800ca413  jz      short loc_1800CA43A
0x1800ca415  mov     r9d, r15d; ThreadInformationLength
0x1800ca418  lea     r8, [rbp+57h+var_50+0Ch]; ThreadInformation
0x1800ca41c  mov     edx, 16h; ThreadInformationClass
0x1800ca421  mov     rcx, r12; ThreadHandle
0x1800ca424  call    cs:__imp_NtSetInformationThread
0x1800ca42b  nop     dword ptr [rax+rax+00h]
0x1800ca430  mov     ebx, eax
0x1800ca432  test    eax, eax
0x1800ca434  jns     short loc_1800CA43A
0x1800ca436  test    ebx, ebx
0x1800ca438  js      short loc_1800CA46F
0x1800ca43a  mov     [rsi], rdi
0x1800ca43d  xor     ebx, ebx
0x1800ca43f  mov     eax, ebx
0x1800ca441  mov     rcx, [rbp+57h+var_40]
0x1800ca445  xor     rcx, rsp; StackCookie
0x1800ca448  call    __security_check_cookie
0x1800ca44d  add     rsp, 88h
0x1800ca454  pop     r15
0x1800ca456  pop     r12
0x1800ca458  pop     rdi
0x1800ca459  pop     rsi
0x1800ca45a  pop     rbx
0x1800ca45b  pop     rbp
0x1800ca45c  retn
0x1800ca45e  mov     edx, 19h
0x1800ca463  jmp     loc_1800CA3D3
0x1800ca468  mov     ebx, 0C0000017h
0x1800ca46d  jmp     short loc_1800CA43F
0x1800ca46f  test    byte ptr [rbp+57h+var_50], 7
0x1800ca473  jz      loc_1801A08BA
0x1800ca479  mov     dl, 1
0x1800ca47b  mov     rcx, rdi
0x1800ca47e  call    BasepSetThreadPriorities
0x1800ca483  nop
0x1800ca484  jmp     loc_1801A08BA
0x1801a08ba  mov     rcx, gs:60h
0x1801a08c3  mov     r8, rdi; P
0x1801a08c6  xor     edx, edx; Flags
0x1801a08c8  mov     rcx, [rcx+30h]; HeapHandle
0x1801a08cc  call    cs:__imp_RtlFreeHeap
0x1801a08d3  nop     dword ptr [rax+rax+00h]
0x1801a08d8  nop
0x1801a08d9  jmp     loc_1800CA43F
```
