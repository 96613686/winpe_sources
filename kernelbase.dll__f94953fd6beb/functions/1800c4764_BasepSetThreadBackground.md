# BasepSetThreadBackground

- ea: `0x1800c4764`
- end: `0x1800c4923`
- name: `BasepSetThreadBackground`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800c44b0`

## callees

- `0x1800c4764`
- `0x1800eb55c`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1801939fc`
- `ntdll!RtlFreeHeap` at `0x1801939fc`
- `ntdll!NtSetInformationThread` at `0x1800c4883`
- `ntdll!NtSetInformationThread` at `0x1800c48a6`
- `ntdll!NtSetInformationThread` at `0x1800c48c8`
- `ntdll!NtSetInformationThread` at `0x1800c4883`
- `ntdll!NtSetInformationThread` at `0x1800c48a6`
- `ntdll!NtSetInformationThread` at `0x1800c48c8`
- `ntdll!NtQueryInformationThread` at `0x1800c47e7`
- `ntdll!NtQueryInformationThread` at `0x1800c481d`
- `ntdll!NtQueryInformationThread` at `0x1800c4848`
- `ntdll!NtQueryInformationThread` at `0x1800c47e7`
- `ntdll!NtQueryInformationThread` at `0x1800c481d`
- `ntdll!NtQueryInformationThread` at `0x1800c4848`
- `ntdll!RtlAllocateHeap` at `0x1800c47b9`
- `ntdll!RtlAllocateHeap` at `0x1800c47b9`

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
0x1800c4764  push    rbp
0x1800c4766  push    rbx
0x1800c4767  push    rsi
0x1800c4768  push    rdi
0x1800c4769  push    r12
0x1800c476b  push    r15
0x1800c476d  lea     rbp, [rsp-2Fh]
0x1800c4772  sub     rsp, 88h
0x1800c4779  mov     rax, cs:__security_cookie
0x1800c4780  xor     rax, rsp
0x1800c4783  mov     [rbp+57h+var_40], rax
0x1800c4787  mov     edx, cs:KernelBaseGlobalData
0x1800c478d  xorps   xmm0, xmm0
0x1800c4790  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800c4794  mov     rsi, rcx
0x1800c4797  xor     eax, eax
0x1800c4799  movups  xmmword ptr [rbp+57h+var_70+0Ch], xmm0
0x1800c479d  or      edx, 8; Flags
0x1800c47a0  movups  [rbp+57h+ThreadInformation], xmm0
0x1800c47a4  lea     r8d, [rax+10h]; Size
0x1800c47a8  movups  [rbp+57h+var_50], xmm0
0x1800c47ac  mov     rcx, gs:60h
0x1800c47b5  mov     rcx, [rcx+30h]; HeapHandle
0x1800c47b9  call    cs:__imp_RtlAllocateHeap
0x1800c47bf  mov     rdi, rax
0x1800c47c2  test    rax, rax
0x1800c47c5  jz      loc_1800C4902
0x1800c47cb  xor     edx, edx; ThreadInformationClass
0x1800c47cd  mov     [rsp+0B0h+ReturnLength], 0; ReturnLength
0x1800c47d6  mov     r9d, 30h ; '0'; ThreadInformationLength
0x1800c47dc  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x1800c47e0  lea     r12, [rdx-2]
0x1800c47e4  mov     rcx, r12; ThreadHandle
0x1800c47e7  call    cs:__imp_NtQueryInformationThread
0x1800c47ed  mov     ebx, eax
0x1800c47ef  test    eax, eax
0x1800c47f1  js      loc_1800C4909
0x1800c47f7  mov     eax, [rbp+57h+var_54]
0x1800c47fa  lea     r15d, [r12+6]
0x1800c47ff  or      dword ptr [rdi], 2
0x1800c4802  lea     r8, [rdi+8]; ThreadInformation
0x1800c4806  mov     r9d, r15d; ThreadInformationLength
0x1800c4809  mov     [rdi+4], eax
0x1800c480c  lea     edx, [r12+1Ah]; ThreadInformationClass
0x1800c4811  mov     [rsp+0B0h+ReturnLength], 0; ReturnLength
0x1800c481a  mov     rcx, r12; ThreadHandle
0x1800c481d  call    cs:__imp_NtQueryInformationThread
0x1800c4823  mov     ebx, eax
0x1800c4825  test    eax, eax
0x1800c4827  js      loc_1800C4909
0x1800c482d  or      [rdi], r15d
0x1800c4830  lea     r8, [rdi+0Ch]; ThreadInformation
0x1800c4834  mov     r9d, r15d; ThreadInformationLength
0x1800c4837  mov     [rsp+0B0h+ReturnLength], 0; ReturnLength
0x1800c4840  lea     edx, [r12+18h]; ThreadInformationClass
0x1800c4845  mov     rcx, r12; ThreadHandle
0x1800c4848  call    cs:__imp_NtQueryInformationThread
0x1800c484e  mov     ebx, eax
0x1800c4850  test    eax, eax
0x1800c4852  js      loc_1800C4909
0x1800c4858  or      dword ptr [rdi], 8
0x1800c485b  lea     r8, [rbp+57h+var_50+4]; ThreadInformation
0x1800c485f  mov     eax, dword ptr [rbp+57h+var_50]
0x1800c4862  lea     edx, [r12+5]; ThreadInformationClass
0x1800c4867  or      eax, 0Dh
0x1800c486a  mov     dword ptr [rbp+57h+var_50+4], r15d
0x1800c486e  mov     qword ptr [rbp+57h+var_50+8], 1
0x1800c4876  mov     r9d, r15d; ThreadInformationLength
0x1800c4879  mov     dword ptr [rbp+57h+var_50], eax
0x1800c487c  mov     rcx, r12; ThreadHandle
0x1800c487f  test    al, 2
0x1800c4881  jz      short loc_1800C48FB
0x1800c4883  call    cs:__imp_NtSetInformationThread
0x1800c4889  mov     ebx, eax
0x1800c488b  test    eax, eax
0x1800c488d  js      short loc_1800C48D4
0x1800c488f  mov     eax, dword ptr [rbp+57h+var_50]
0x1800c4892  test    r15b, al
0x1800c4895  jz      short loc_1800C48B5
0x1800c4897  mov     r9d, r15d; ThreadInformationLength
0x1800c489a  lea     r8, [rbp+57h+var_50+8]; ThreadInformation
0x1800c489e  mov     edx, 18h; ThreadInformationClass
0x1800c48a3  mov     rcx, r12; ThreadHandle
0x1800c48a6  call    cs:__imp_NtSetInformationThread
0x1800c48ac  mov     ebx, eax
0x1800c48ae  test    eax, eax
0x1800c48b0  js      short loc_1800C48D4
0x1800c48b2  mov     eax, dword ptr [rbp+57h+var_50]
0x1800c48b5  test    al, 8
0x1800c48b7  jz      short loc_1800C48D8
0x1800c48b9  mov     r9d, r15d; ThreadInformationLength
0x1800c48bc  lea     r8, [rbp+57h+var_50+0Ch]; ThreadInformation
0x1800c48c0  mov     edx, 16h; ThreadInformationClass
0x1800c48c5  mov     rcx, r12; ThreadHandle
0x1800c48c8  call    cs:__imp_NtSetInformationThread
0x1800c48ce  mov     ebx, eax
0x1800c48d0  test    eax, eax
0x1800c48d2  jns     short loc_1800C48D8
0x1800c48d4  test    ebx, ebx
0x1800c48d6  js      short loc_1800C4909
0x1800c48d8  mov     [rsi], rdi
0x1800c48db  xor     ebx, ebx
0x1800c48dd  mov     eax, ebx
0x1800c48df  mov     rcx, [rbp+57h+var_40]
0x1800c48e3  xor     rcx, rsp; StackCookie
0x1800c48e6  call    __security_check_cookie
0x1800c48eb  add     rsp, 88h
0x1800c48f2  pop     r15
0x1800c48f4  pop     r12
0x1800c48f6  pop     rdi
0x1800c48f7  pop     rsi
0x1800c48f8  pop     rbx
0x1800c48f9  pop     rbp
0x1800c48fa  retn
0x1800c48fb  mov     edx, 19h
0x1800c4900  jmp     short loc_1800C4883
0x1800c4902  mov     ebx, 0C0000017h
0x1800c4907  jmp     short loc_1800C48DD
0x1800c4909  test    byte ptr [rbp+57h+var_50], 7
0x1800c490d  jz      loc_1801939EA
0x1800c4913  mov     dl, 1
0x1800c4915  mov     rcx, rdi
0x1800c4918  call    BasepSetThreadPriorities
0x1800c491d  nop
0x1800c491e  jmp     loc_1801939EA
0x1801939ea  mov     rcx, gs:60h
0x1801939f3  mov     r8, rdi; P
0x1801939f6  xor     edx, edx; Flags
0x1801939f8  mov     rcx, [rcx+30h]; HeapHandle
0x1801939fc  call    cs:__imp_RtlFreeHeap
0x180193a02  nop
0x180193a03  jmp     loc_1800C48DD
```
