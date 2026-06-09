# CsrProcessLazyRegister

- ea: `0x1800030a0`
- end: `0x1800034c7`
- name: `CsrProcessLazyRegister`
- size: `1063`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800021f0`

## callees

- `0x1800030a0`
- `0x180003930`
- `0x180003de0`
- `0x1800058b0`
- `0x18000ab61`
- `0x18000b010`

## import_xrefs

- `ntdll!NtClose` at `0x1800032f1`
- `ntdll!NtClose` at `0x18000333f`
- `ntdll!NtClose` at `0x180003352`
- `ntdll!NtClose` at `0x1800033f9`
- `ntdll!NtClose` at `0x18000340c`
- `ntdll!NtClose` at `0x1800034b6`
- `ntdll!NtClose` at `0x1800032f1`
- `ntdll!NtClose` at `0x18000333f`
- `ntdll!NtClose` at `0x180003352`
- `ntdll!NtClose` at `0x1800033f9`
- `ntdll!NtClose` at `0x18000340c`
- `ntdll!NtClose` at `0x1800034b6`
- `ntdll!RtlEnterCriticalSection` at `0x180003319`
- `ntdll!RtlEnterCriticalSection` at `0x180003484`
- `ntdll!RtlEnterCriticalSection` at `0x180003319`
- `ntdll!RtlEnterCriticalSection` at `0x180003484`
- `ntdll!RtlLeaveCriticalSection` at `0x180003365`
- `ntdll!RtlLeaveCriticalSection` at `0x1800033a8`
- `ntdll!RtlLeaveCriticalSection` at `0x180003454`
- `ntdll!RtlLeaveCriticalSection` at `0x180003365`
- `ntdll!RtlLeaveCriticalSection` at `0x1800033a8`
- `ntdll!RtlLeaveCriticalSection` at `0x180003454`
- `ntdll!NtQueryInformationProcess` at `0x18000323e`
- `ntdll!NtQueryInformationProcess` at `0x18000326f`
- `ntdll!NtQueryInformationProcess` at `0x18000323e`
- `ntdll!NtQueryInformationProcess` at `0x18000326f`
- `ntdll!NtAlpcOpenSenderProcess` at `0x1800031c6`
- `ntdll!NtAlpcOpenSenderProcess` at `0x180003204`
- `ntdll!NtAlpcOpenSenderProcess` at `0x1800031c6`
- `ntdll!NtAlpcOpenSenderProcess` at `0x180003204`
- `ntdll!NtAlpcOpenSenderThread` at `0x1800032d8`
- `ntdll!NtAlpcOpenSenderThread` at `0x1800032d8`

## pseudocode

```c
__int64 __fastcall CsrProcessLazyRegister(__int64 a1)
{
  struct _NT_TIB *Self; // r9
  _QWORD *v3; // rax
  __int64 result; // rax
  int v5; // ebx
  NTSTATUS v6; // eax
  HANDLE v7; // rcx
  NTSTATUS InformationProcess; // edi
  int v9; // eax
  __int16 v10; // bx
  __int64 v11; // rdi
  int v12; // ebx
  __int64 v13; // rdi
  __int64 v14; // rbx
  int v15; // ebx
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[48]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v18[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v19; // [rsp+A0h] [rbp-60h]
  __int128 v20; // [rsp+B0h] [rbp-50h]
  _BYTE v21[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v22; // [rsp+C8h] [rbp-38h]
  __int64 v23; // [rsp+D0h] [rbp-30h]
  __int64 v24; // [rsp+100h] [rbp+0h]
  __int64 v25[111]; // [rsp+108h] [rbp+8h] BYREF
  int ProcessInformation; // [rsp+4C0h] [rbp+3C0h] BYREF
  int v27; // [rsp+4C8h] [rbp+3C8h] BYREF
  HANDLE ProcessHandle; // [rsp+4D0h] [rbp+3D0h] BYREF
  HANDLE Handle; // [rsp+4D8h] [rbp+3D8h] BYREF

  memset_0(v21, 0, 0x3B8u);
  v24 = a1 + 8;
  v27 = 0;
  ProcessInformation = 0;
  memset(v17, 0, 44);
  ProcessHandle = 0;
  memset(v18, 0, sizeof(v18));
  Handle = 0;
  LODWORD(v25[0]) = 0;
  v19 = 0;
  v16 = 0;
  v20 = 0;
  Self = KeGetPcr()->NtTib.Self;
  v3 = *(_QWORD **)(CsrRootProcess + 32);
  if ( v3 == (_QWORD *)(CsrRootProcess + 32) )
    return 3221225473LL;
  while ( (PVOID)v3[5] != Self[1].StackLimit )
  {
    v3 = (_QWORD *)*v3;
    if ( v3 == (_QWORD *)(CsrRootProcess + 32) )
      return 3221225473LL;
  }
  Self[2].ExceptionList = (struct _EXCEPTION_REGISTRATION_RECORD *)(v3 - 1);
  *(_DWORD *)v17 = 48;
  v5 = 0;
  memset(&v17[8], 0, 20);
  *(_OWORD *)&v17[32] = 0;
  result = NtAlpcOpenSenderProcess(&ProcessHandle, CsrApiPort, a1, 0, 0x2000000, v17);
  if ( (_DWORD)result == -1073741790 )
  {
    v5 = 0x2000;
    result = NtAlpcOpenSenderProcess(&ProcessHandle, CsrApiPort, a1, 0, 1062912, v17);
  }
  if ( (int)result >= 0 )
  {
    v6 = NtQueryInformationProcess(ProcessHandle, ProcessSessionInformation, &ProcessInformation, 4u, 0);
    v7 = ProcessHandle;
    InformationProcess = v6;
    if ( v6 < 0 )
    {
LABEL_16:
      NtClose(v7);
      return (unsigned int)InformationProcess;
    }
    InformationProcess = NtQueryInformationProcess(ProcessHandle, ProcessImageInformation, v18, 0x40u, 0);
    if ( InformationProcess < 0 )
    {
LABEL_15:
      v7 = ProcessHandle;
      goto LABEL_16;
    }
    if ( ProcessInformation != *(_DWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 704LL) || (unsigned int)(v19 - 2) > 1 )
    {
      NtClose(ProcessHandle);
      return 3221225506LL;
    }
    v9 = 1055744;
    if ( !v5 )
      v9 = 0x2000000;
    InformationProcess = NtAlpcOpenSenderThread(&Handle, CsrApiPort, a1, 0, v9, v17);
    if ( InformationProcess < 0 )
      goto LABEL_15;
    v10 = v5 | 0x100;
    if ( (_DWORD)v19 == 2 )
      v10 |= 0x800u;
    RtlEnterCriticalSection(&CsrNtSessionLock);
    v11 = CsrNtSessionList;
    if ( (__int64 *)CsrNtSessionList == &CsrNtSessionList )
    {
      NtClose(ProcessHandle);
      NtClose(Handle);
      RtlLeaveCriticalSection(&CsrNtSessionLock);
      return 3221225506LL;
    }
    _InterlockedIncrement((volatile signed __int32 *)(CsrNtSessionList + 20));
    RtlLeaveCriticalSection(&CsrNtSessionLock);
    v12 = CsrpCreateProcess(ProcessHandle, Handle, (_DWORD *)(a1 + 8), v11, v10, (int *)v25, &v16);
    CsrDereferenceNtSession(v11);
    if ( v12 >= 0 )
    {
      v13 = v16;
      v22 = (unsigned int)KeGetPcr()->Unused[0];
      v14 = qword_180010368;
      v23 = (unsigned int)KeGetPcr()->Unused[1];
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 100));
      RtlLeaveCriticalSection(&CsrProcessStructureLock);
      v15 = (*(__int64 (__fastcall **)(_BYTE *, int *))(*(_QWORD *)(v14 + 40) + 208LL))(v21, &v27);
      RtlEnterCriticalSection(&CsrProcessStructureLock);
      if ( v15 >= 0 && (*(_BYTE *)(v13 + 92) & 8) != 0 )
        v15 = -1073741558;
      CsrLockedDereferenceProcess(v13);
      return (unsigned int)v15;
    }
    else
    {
      NtClose(ProcessHandle);
      NtClose(Handle);
      return (unsigned int)v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800030a0  push    rbp
0x1800030a2  push    rsi
0x1800030a3  push    r14
0x1800030a5  push    r15
0x1800030a7  lea     rbp, [rsp-398h]
0x1800030af  sub     rsp, 498h
0x1800030b6  mov     rsi, rcx
0x1800030b9  xor     edx, edx; Val
0x1800030bb  lea     rcx, [rbp+3B0h+var_3F0]; void *
0x1800030bf  mov     r8d, 3B8h; Size
0x1800030c5  call    memset_0
0x1800030ca  xorps   xmm0, xmm0
0x1800030cd  lea     r14, [rsi+8]
0x1800030d1  xor     r15d, r15d
0x1800030d4  mov     [rbp+3B0h+var_3B0], r14
0x1800030d8  movups  [rsp+4B0h+var_458], xmm0
0x1800030dd  xor     eax, eax
0x1800030df  mov     [rbp+3B0h+arg_8], r15d
0x1800030e6  movups  [rsp+4B0h+var_458+0Ch], xmm0
0x1800030eb  mov     [rbp+3B0h+ProcessInformation], r15d
0x1800030f2  movups  [rsp+4B0h+var_468], xmm0
0x1800030f7  mov     [rbp+3B0h+ProcessHandle], r15
0x1800030fe  movups  [rbp+3B0h+var_430], xmm0
0x180003102  mov     [rbp+3B0h+Handle], r15
0x180003109  movups  [rbp+3B0h+var_420], xmm0
0x18000310d  mov     dword ptr [rbp+3B0h+var_3A8], r15d
0x180003111  movups  [rbp+3B0h+var_410], xmm0
0x180003115  mov     [rsp+4B0h+var_470], r15
0x18000311a  movups  [rbp+3B0h+var_400], xmm0
0x18000311e  mov     r9, gs:30h
0x180003127  mov     rdx, cs:CsrRootProcess
0x18000312e  add     rdx, 20h ; ' '
0x180003132  mov     rax, [rdx]
0x180003135  cmp     rax, rdx
0x180003138  jz      short loc_180003152
0x18000313a  mov     r8, [r9+48h]
0x18000313e  xchg    ax, ax
0x180003140  cmp     [rax+28h], r8
0x180003144  lea     rcx, [rax-8]
0x180003148  jz      short loc_180003166
0x18000314a  mov     rax, [rax]
0x18000314d  cmp     rax, rdx
0x180003150  jnz     short loc_180003140
0x180003152  mov     eax, 0C0000001h
0x180003157  add     rsp, 498h
0x18000315e  pop     r15
0x180003160  pop     r14
0x180003162  pop     rsi
0x180003163  pop     rbp
0x180003164  retn
0x180003166  mov     [r9+70h], rcx
0x18000316a  lea     rax, [rsp+4B0h+var_468]
0x18000316f  mov     rdx, cs:CsrApiPort
0x180003176  lea     rcx, [rbp+3B0h+ProcessHandle]
0x18000317d  mov     [rsp+4B0h+var_20], rbx
0x180003185  xorps   xmm0, xmm0
0x180003188  mov     [rsp+4B0h+var_488], rax
0x18000318d  xor     r9d, r9d
0x180003190  mov     [rsp+4B0h+var_30], r12
0x180003198  mov     r8, rsi
0x18000319b  mov     r12d, 2000000h
0x1800031a1  mov     dword ptr [rsp+4B0h+var_468], 30h ; '0'
0x1800031a9  mov     dword ptr [rsp+4B0h+ReturnLength], r12d
0x1800031ae  mov     ebx, r15d
0x1800031b1  mov     qword ptr [rsp+4B0h+var_468+8], r15
0x1800031b6  mov     dword ptr [rsp+4B0h+var_458+8], r15d
0x1800031bb  mov     qword ptr [rsp+4B0h+var_458], r15
0x1800031c0  movdqu  [rsp+4B0h+var_448], xmm0
0x1800031c6  call    cs:__imp_NtAlpcOpenSenderProcess
0x1800031cd  nop     dword ptr [rax+rax+00h]
0x1800031d2  cmp     eax, 0C0000022h
0x1800031d7  jnz     short loc_180003210
0x1800031d9  mov     rdx, cs:CsrApiPort
0x1800031e0  lea     rax, [rsp+4B0h+var_468]
0x1800031e5  mov     [rsp+4B0h+var_488], rax
0x1800031ea  lea     rcx, [rbp+3B0h+ProcessHandle]
0x1800031f1  xor     r9d, r9d
0x1800031f4  mov     dword ptr [rsp+4B0h+ReturnLength], 103800h
0x1800031fc  mov     r8, rsi
0x1800031ff  mov     ebx, 2000h
0x180003204  call    cs:__imp_NtAlpcOpenSenderProcess
0x18000320b  nop     dword ptr [rax+rax+00h]
0x180003210  test    eax, eax
0x180003212  js      loc_18000337E
0x180003218  mov     rcx, [rbp+3B0h+ProcessHandle]; ProcessHandle
0x18000321f  lea     r8, [rbp+3B0h+ProcessInformation]; ProcessInformation
0x180003226  mov     r9d, 4; ProcessInformationLength
0x18000322c  mov     [rsp+4B0h+var_28], rdi
0x180003234  mov     edx, 18h; ProcessInformationClass
0x180003239  mov     [rsp+4B0h+ReturnLength], r15; ReturnLength
0x18000323e  call    cs:__imp_NtQueryInformationProcess
0x180003245  nop     dword ptr [rax+rax+00h]
0x18000324a  mov     rcx, [rbp+3B0h+ProcessHandle]; ProcessHandle
0x180003251  mov     edi, eax
0x180003253  test    eax, eax
0x180003255  js      loc_1800032F1
0x18000325b  mov     r9d, 40h ; '@'; ProcessInformationLength
0x180003261  mov     [rsp+4B0h+ReturnLength], r15; ReturnLength
0x180003266  lea     r8, [rbp+3B0h+var_430]; ProcessInformation
0x18000326a  mov     edx, 25h ; '%'; ProcessInformationClass
0x18000326f  call    cs:__imp_NtQueryInformationProcess
0x180003276  nop     dword ptr [rax+rax+00h]
0x18000327b  mov     edi, eax
0x18000327d  test    eax, eax
0x18000327f  js      short loc_1800032EA
0x180003281  mov     rax, gs:60h
0x18000328a  mov     ecx, [rax+2C0h]
0x180003290  cmp     [rbp+3B0h+ProcessInformation], ecx
0x180003296  jnz     loc_1800034AF
0x18000329c  mov     eax, dword ptr [rbp+3B0h+var_410]
0x18000329f  add     eax, 0FFFFFFFEh
0x1800032a2  cmp     eax, 1
0x1800032a5  ja      loc_1800034AF
0x1800032ab  mov     rdx, cs:CsrApiPort
0x1800032b2  lea     rcx, [rsp+4B0h+var_468]
0x1800032b7  mov     [rsp+4B0h+var_488], rcx
0x1800032bc  mov     eax, 101C00h
0x1800032c1  test    ebx, ebx
0x1800032c3  lea     rcx, [rbp+3B0h+Handle]
0x1800032ca  mov     r8, rsi
0x1800032cd  cmovz   eax, r12d
0x1800032d1  xor     r9d, r9d
0x1800032d4  mov     dword ptr [rsp+4B0h+ReturnLength], eax
0x1800032d8  call    cs:__imp_NtAlpcOpenSenderThread
0x1800032df  nop     dword ptr [rax+rax+00h]
0x1800032e4  mov     edi, eax
0x1800032e6  test    eax, eax
0x1800032e8  jns     short loc_180003301
0x1800032ea  mov     rcx, [rbp+3B0h+ProcessHandle]; Handle
0x1800032f1  call    cs:__imp_NtClose
0x1800032f8  nop     dword ptr [rax+rax+00h]
0x1800032fd  mov     eax, edi
0x1800032ff  jmp     short loc_180003376
0x180003301  bts     ebx, 8
0x180003305  lea     rcx, CsrNtSessionLock; CriticalSection
0x18000330c  mov     eax, ebx
0x18000330e  bts     eax, 0Bh
0x180003312  cmp     dword ptr [rbp+3B0h+var_410], 2
0x180003316  cmovz   ebx, eax
0x180003319  call    cs:__imp_RtlEnterCriticalSection
0x180003320  nop     dword ptr [rax+rax+00h]
0x180003325  mov     rdi, cs:CsrNtSessionList
0x18000332c  lea     rdx, CsrNtSessionList
0x180003333  cmp     rdi, rdx
0x180003336  jnz     short loc_18000339D
0x180003338  mov     rcx, [rbp+3B0h+ProcessHandle]; Handle
0x18000333f  call    cs:__imp_NtClose
0x180003346  nop     dword ptr [rax+rax+00h]
0x18000334b  mov     rcx, [rbp+3B0h+Handle]; Handle
0x180003352  call    cs:__imp_NtClose
0x180003359  nop     dword ptr [rax+rax+00h]
0x18000335e  lea     rcx, CsrNtSessionLock; CriticalSection
0x180003365  call    cs:__imp_RtlLeaveCriticalSection
0x18000336c  nop     dword ptr [rax+rax+00h]
0x180003371  mov     eax, 0C0000022h
0x180003376  mov     rdi, [rsp+4B0h+var_28]
0x18000337e  mov     rbx, [rsp+4B0h+var_20]
0x180003386  mov     r12, [rsp+4B0h+var_30]
0x18000338e  add     rsp, 498h
0x180003395  pop     r15
0x180003397  pop     r14
0x180003399  pop     rsi
0x18000339a  pop     rbp
0x18000339b  retn
0x18000339d  lock inc dword ptr [rdi+14h]
0x1800033a1  lea     rcx, CsrNtSessionLock; CriticalSection
0x1800033a8  call    cs:__imp_RtlLeaveCriticalSection
0x1800033af  nop     dword ptr [rax+rax+00h]
0x1800033b4  mov     rdx, [rbp+3B0h+Handle]
0x1800033bb  lea     rax, [rsp+4B0h+var_470]
0x1800033c0  mov     rcx, [rbp+3B0h+ProcessHandle]; Handle
0x1800033c7  mov     r9, rdi
0x1800033ca  mov     [rsp+4B0h+var_480], rax; __int64
0x1800033cf  mov     r8, r14
0x1800033d2  lea     rax, [rbp+3B0h+var_3A8]
0x1800033d6  mov     [rsp+4B0h+var_488], rax; __int64
0x1800033db  mov     dword ptr [rsp+4B0h+ReturnLength], ebx; int
0x1800033df  call    CsrpCreateProcess
0x1800033e4  mov     rcx, rdi
0x1800033e7  mov     ebx, eax
0x1800033e9  call    CsrDereferenceNtSession
0x1800033ee  test    ebx, ebx
0x1800033f0  jns     short loc_18000341F
0x1800033f2  mov     rcx, [rbp+3B0h+ProcessHandle]; Handle
0x1800033f9  call    cs:__imp_NtClose
0x180003400  nop     dword ptr [rax+rax+00h]
0x180003405  mov     rcx, [rbp+3B0h+Handle]; Handle
0x18000340c  call    cs:__imp_NtClose
0x180003413  nop     dword ptr [rax+rax+00h]
0x180003418  mov     eax, ebx
0x18000341a  jmp     loc_180003376
0x18000341f  mov     rax, gs:40h
0x180003428  mov     rdi, [rsp+4B0h+var_470]
0x18000342d  mov     ecx, eax
0x18000342f  mov     [rbp+3B0h+var_3E8], rcx
0x180003433  mov     rax, gs:48h
0x18000343c  mov     rbx, cs:qword_180010368
0x180003443  mov     ecx, eax
0x180003445  mov     [rbp+3B0h+var_3E0], rcx
0x180003449  lock inc dword ptr [rdi+64h]
0x18000344d  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003454  call    cs:__imp_RtlLeaveCriticalSection
0x18000345b  nop     dword ptr [rax+rax+00h]
0x180003460  mov     rax, [rbx+28h]
0x180003464  lea     rdx, [rbp+3B0h+arg_8]
0x18000346b  lea     rcx, [rbp+3B0h+var_3F0]
0x18000346f  mov     rax, [rax+0D0h]
0x180003476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000347b  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003482  mov     ebx, eax
0x180003484  call    cs:__imp_RtlEnterCriticalSection
0x18000348b  nop     dword ptr [rax+rax+00h]
0x180003490  test    ebx, ebx
0x180003492  js      short loc_1800034A0
0x180003494  test    byte ptr [rdi+5Ch], 8
0x180003498  mov     eax, 0C000010Ah
0x18000349d  cmovnz  ebx, eax
0x1800034a0  mov     rcx, rdi
0x1800034a3  call    CsrLockedDereferenceProcess
0x1800034a8  mov     eax, ebx
0x1800034aa  jmp     loc_180003376
0x1800034af  mov     rcx, [rbp+3B0h+ProcessHandle]; Handle
0x1800034b6  call    cs:__imp_NtClose
0x1800034bd  nop     dword ptr [rax+rax+00h]
0x1800034c2  jmp     loc_180003371
```
