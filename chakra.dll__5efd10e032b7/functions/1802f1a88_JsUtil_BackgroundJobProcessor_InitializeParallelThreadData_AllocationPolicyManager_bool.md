# JsUtil::BackgroundJobProcessor::InitializeParallelThreadData(AllocationPolicyManager *,bool)

- ea: `0x1802f1a88`
- end: `0x1802f1c7f`
- name: `?InitializeParallelThreadData@BackgroundJobProcessor@JsUtil@@AEAAXPEAVAllocationPolicyManager@@_N@Z`
- size: `503`
- prototype: `void __fastcall(JsUtil::BackgroundJobProcessor *__hidden this, struct AllocationPolicyManager *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x1802f31ac`

## callees

- `0x180072650`
- `0x1802f1a88`
- `0x1802f1c88`
- `0x1802f1cd0`
- `0x1802f1d20`
- `0x1802f1e2c`
- `0x18032e784`
- `0x1803822a4`
- `0x1803c4080`
- `0x1803d8884`
- `0x1805cd010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x1802f1b4d`
- `msvcrt!_beginthreadex` at `0x1802f1b4d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802f1c09`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802f1c09`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1802f1bcc`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1802f1bcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802f1c2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802f1c2d`

## string_xrefs

- `0x1802f1b96`: `Chakra Parallel Worker Thread`
- `0x1802f1b77`: `SetThreadDescription`

## pseudocode

```c
void __fastcall JsUtil::BackgroundJobProcessor::InitializeParallelThreadData(
        JsUtil::BackgroundJobProcessor *this,
        struct AllocationPolicyManager *a2,
        char a3)
{
  _DWORD *v3; // rsi
  __int64 i; // rbp
  JsUtil::ParallelThreadData *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  uintptr_t v9; // r14
  __int64 (*Function)(void); // rax
  void **v11; // rdx
  void *v12; // rcx
  unsigned int v13; // r9d
  __int64 v14; // rax

  v3 = (_DWORD *)((char *)this + 140);
  if ( a3 )
    *v3 = 1;
  else
    JsUtil::BackgroundJobProcessor::InitializeThreadCount(this);
  *((_QWORD *)this + 18) = Memory::AllocateArray<Memory::HeapAllocator,JsUtil::ParallelThreadData *,0>(
                             this,
                             a2,
                             (unsigned int)*v3);
  for ( i = 0; (unsigned int)i < *v3; i = (unsigned int)(i + 1) )
  {
    v6 = (JsUtil::ParallelThreadData *)Memory::HeapAllocator::NoThrowAlloc(
                                         (Memory::HeapAllocator *)&Memory::HeapAllocator::Instance,
                                         0x148u);
    if ( v6 )
      v7 = JsUtil::ParallelThreadData::ParallelThreadData(v6, a2);
    else
      v7 = 0;
    *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i) = v7;
    v8 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i);
    if ( !v8 )
    {
      if ( !(_DWORD)i )
      {
        Memory::DeleteArray<Memory::HeapAllocator,_FILETIME>(v7, (unsigned int)*v3);
        Js::Throw::OutOfMemory();
      }
      return;
    }
    *(_QWORD *)(v8 + 296) = this;
    v9 = _beginthreadex(
           0,
           0,
           JsUtil::BackgroundJobProcessor::StaticThreadProc,
           *(void **)(*((_QWORD *)this + 18) + 8 * i),
           4u,
           0);
    if ( v9 )
    {
      if ( qword_180737FD0 )
      {
        Function = (__int64 (*)(void))qword_180737FE0;
        if ( qword_180737FE0
          || (Function = DelayLoadLibrary::GetFunction((DelayLoadLibrary *)&off_180737FC8, "SetThreadDescription"),
              (qword_180737FE0 = (__int64)Function) != 0) )
        {
          ((void (__fastcall *)(uintptr_t, const wchar_t *))Function)(v9, L"Chakra Parallel Worker Thread");
        }
      }
      if ( v9 != -1 )
        **(_QWORD **)(*((_QWORD *)this + 18) + 8 * i) = v9;
    }
    v11 = *(void ***)(*((_QWORD *)this + 18) + 8 * i);
    v12 = *v11;
    if ( !*v11 )
      goto LABEL_21;
    if ( ResumeThread(v12) == -1 )
    {
      _mm_lfence();
      CloseHandle(**(HANDLE **)(*((_QWORD *)this + 18) + 8 * i));
      v11 = *(void ***)(*((_QWORD *)this + 18) + 8 * i);
LABEL_21:
      Memory::DeleteObject<Memory::HeapAllocator,0,JsUtil::ParallelThreadData>(v12, v11);
      *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i) = 0;
      if ( !(_DWORD)i )
        Js::Throw::OutOfMemory();
      return;
    }
    v14 = *((_QWORD *)this + 18);
    ++*((_DWORD *)this + 34);
    JsUtil::BackgroundJobProcessor::WaitWithThread(
      this,
      *(struct JsUtil::ParallelThreadData **)(v14 + 8 * i),
      (const struct Event *)(*(_QWORD *)(v14 + 8 * i) + 24LL),
      v13);
    ResetEvent(*(HANDLE *)(*(_QWORD *)(*((_QWORD *)this + 18) + 8 * i) + 24LL));
  }
}

```

## disassembly

```asm
0x1802f1a88  mov     rax, rsp
0x1802f1a8b  mov     [rax+18h], r8b
0x1802f1a8f  mov     [rax+10h], rdx
0x1802f1a93  mov     [rax+8], rcx
0x1802f1a97  push    rbx
0x1802f1a98  push    rbp
0x1802f1a99  push    rsi
0x1802f1a9a  push    rdi
0x1802f1a9b  push    r14
0x1802f1a9d  sub     rsp, 30h
0x1802f1aa1  lea     rsi, [rcx+8Ch]
0x1802f1aa8  mov     rbx, rcx
0x1802f1aab  test    r8b, r8b
0x1802f1aae  jnz     short loc_1802F1AB7
0x1802f1ab0  call    ?InitializeThreadCount@BackgroundJobProcessor@JsUtil@@AEAAXXZ; JsUtil::BackgroundJobProcessor::InitializeThreadCount(void)
0x1802f1ab5  jmp     short loc_1802F1ABD
0x1802f1ab7  mov     dword ptr [rsi], 1
0x1802f1abd  mov     r8d, [rsi]
0x1802f1ac0  call    ??$AllocateArray@UHeapAllocator@Memory@@PEAUParallelThreadData@JsUtil@@$0A@@Memory@@YAPEAPEAUParallelThreadData@JsUtil@@PEAUHeapAllocator@0@P830@EAAPEAD_K@Z1@Z; Memory::AllocateArray<Memory::HeapAllocator,JsUtil::ParallelThreadData *,0>(Memory::HeapAllocator *,char * (Memory::HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x1802f1ac5  mov     [rbx+90h], rax
0x1802f1acc  xor     ebp, ebp
0x1802f1ace  cmp     ebp, [rsi]
0x1802f1ad0  jnb     loc_1802F1C73
0x1802f1ad6  mov     edx, 148h; unsigned __int64
0x1802f1adb  lea     rcx, ?Instance@HeapAllocator@Memory@@2U12@A; this
0x1802f1ae2  call    ?NoThrowAlloc@HeapAllocator@Memory@@QEAAPEAD_K@Z; Memory::HeapAllocator::NoThrowAlloc(unsigned __int64)
0x1802f1ae7  test    rax, rax
0x1802f1aea  jz      short loc_1802F1AFE
0x1802f1aec  mov     rdx, [rsp+58h+arg_8]; struct AllocationPolicyManager *
0x1802f1af1  mov     rcx, rax; this
0x1802f1af4  call    ??0ParallelThreadData@JsUtil@@QEAA@PEAVAllocationPolicyManager@@@Z; JsUtil::ParallelThreadData::ParallelThreadData(AllocationPolicyManager *)
0x1802f1af9  mov     rcx, rax
0x1802f1afc  jmp     short loc_1802F1B00
0x1802f1afe  xor     ecx, ecx
0x1802f1b00  mov     rax, [rbx+90h]
0x1802f1b07  mov     [rax+rbp*8], rcx
0x1802f1b0b  mov     r8, [rbx+90h]
0x1802f1b12  mov     rax, [r8+rbp*8]
0x1802f1b16  test    rax, rax
0x1802f1b19  jz      loc_1802F1C62
0x1802f1b1f  mov     [rax+128h], rbx
0x1802f1b26  lea     r8, ?StaticThreadProc@BackgroundJobProcessor@JsUtil@@CAIPEAX@Z; StartAddress
0x1802f1b2d  mov     r9, [rbx+90h]
0x1802f1b34  xor     edx, edx; StackSize
0x1802f1b36  mov     [rsp+58h+ThrdAddr], 0; ThrdAddr
0x1802f1b3f  xor     ecx, ecx; Security
0x1802f1b41  mov     [rsp+58h+InitFlag], 4; InitFlag
0x1802f1b49  mov     r9, [r9+rbp*8]; ArgList
0x1802f1b4d  call    cs:__imp__beginthreadex
0x1802f1b54  nop     dword ptr [rax+rax+00h]
0x1802f1b59  mov     r14, rax
0x1802f1b5c  test    rax, rax
0x1802f1b5f  jz      short loc_1802F1BB9
0x1802f1b61  cmp     cs:qword_180737FD0, 0
0x1802f1b69  jz      short loc_1802F1BA5
0x1802f1b6b  mov     rax, cs:qword_180737FE0
0x1802f1b72  test    rax, rax
0x1802f1b75  jnz     short loc_1802F1B96
0x1802f1b77  lea     rdx, aSetthreaddescr; "SetThreadDescription"
0x1802f1b7e  lea     rcx, off_180737FC8; this
0x1802f1b85  call    ?GetFunction@DelayLoadLibrary@@QEAAP6A_JXZPEBD@Z; DelayLoadLibrary::GetFunction(char const *)
0x1802f1b8a  mov     cs:qword_180737FE0, rax
0x1802f1b91  test    rax, rax
0x1802f1b94  jz      short loc_1802F1BA5
0x1802f1b96  lea     rdx, aChakraParallel; "Chakra Parallel Worker Thread"
0x1802f1b9d  mov     rcx, r14
0x1802f1ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f1ba5  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1802f1ba9  jz      short loc_1802F1BB9
0x1802f1bab  mov     rax, [rbx+90h]
0x1802f1bb2  mov     rcx, [rax+rbp*8]
0x1802f1bb6  mov     [rcx], r14
0x1802f1bb9  mov     rax, [rbx+90h]
0x1802f1bc0  mov     rdx, [rax+rbp*8]
0x1802f1bc4  mov     rcx, [rdx]; hThread
0x1802f1bc7  test    rcx, rcx
0x1802f1bca  jz      short loc_1802F1C44
0x1802f1bcc  call    cs:__imp_ResumeThread
0x1802f1bd3  nop     dword ptr [rax+rax+00h]
0x1802f1bd8  cmp     eax, 0FFFFFFFFh
0x1802f1bdb  jz      short loc_1802F1C1C
0x1802f1bdd  mov     rax, [rbx+90h]
0x1802f1be4  mov     rcx, rbx; this
0x1802f1be7  inc     dword ptr [rbx+88h]
0x1802f1bed  mov     rdx, [rax+rbp*8]; struct JsUtil::ParallelThreadData *
0x1802f1bf1  lea     r8, [rdx+18h]; struct Event *
0x1802f1bf5  call    ?WaitWithThread@BackgroundJobProcessor@JsUtil@@AEAA_NPEAUParallelThreadData@2@AEBVEvent@@I@Z; JsUtil::BackgroundJobProcessor::WaitWithThread(JsUtil::ParallelThreadData *,Event const &,uint)
0x1802f1bfa  mov     rax, [rbx+90h]
0x1802f1c01  mov     rcx, [rax+rbp*8]
0x1802f1c05  mov     rcx, [rcx+18h]; hEvent
0x1802f1c09  call    cs:__imp_ResetEvent
0x1802f1c10  nop     dword ptr [rax+rax+00h]
0x1802f1c15  inc     ebp
0x1802f1c17  jmp     loc_1802F1ACE
0x1802f1c1c  lfence
0x1802f1c1f  mov     rax, [rbx+90h]
0x1802f1c26  mov     rcx, [rax+rbp*8]
0x1802f1c2a  mov     rcx, [rcx]; hObject
0x1802f1c2d  call    cs:__imp_CloseHandle
0x1802f1c34  nop     dword ptr [rax+rax+00h]
0x1802f1c39  mov     rdx, [rbx+90h]
0x1802f1c40  mov     rdx, [rdx+rbp*8]
0x1802f1c44  call    ??$DeleteObject@UHeapAllocator@Memory@@$0A@UParallelThreadData@JsUtil@@@Memory@@YAXPEAUHeapAllocator@0@PEAUParallelThreadData@JsUtil@@@Z; Memory::DeleteObject<Memory::HeapAllocator,0,JsUtil::ParallelThreadData>(Memory::HeapAllocator *,JsUtil::ParallelThreadData *)
0x1802f1c49  mov     rax, [rbx+90h]
0x1802f1c50  mov     qword ptr [rax+rbp*8], 0
0x1802f1c58  test    ebp, ebp
0x1802f1c5a  jnz     short loc_1802F1C73
0x1802f1c5c  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1802f1c62  test    ebp, ebp
0x1802f1c64  jnz     short loc_1802F1C73
0x1802f1c66  mov     edx, [rsi]
0x1802f1c68  call    ??$DeleteArray@UHeapAllocator@Memory@@U_FILETIME@@@Memory@@YAXPEAUHeapAllocator@0@_KPEAU_FILETIME@@@Z; Memory::DeleteArray<Memory::HeapAllocator,_FILETIME>(Memory::HeapAllocator *,unsigned __int64,_FILETIME *)
0x1802f1c6d  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1802f1c73  add     rsp, 30h
0x1802f1c77  pop     r14
0x1802f1c79  pop     rdi
0x1802f1c7a  pop     rsi
0x1802f1c7b  pop     rbp
0x1802f1c7c  pop     rbx
0x1802f1c7d  retn
```
