# JITThunkEmitter<Memory::SectionAllocWrapper>::CreateThunk(unsigned __int64)

- ea: `0x180560b70`
- end: `0x180560e2c`
- name: `?CreateThunk@?$JITThunkEmitter@VSectionAllocWrapper@Memory@@@@QEAA_K_K@Z`
- size: `700`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801b4d50`

## callees

- `0x1801b51b8`
- `0x1801b51e4`
- `0x1801b5270`
- `0x1801b5c3c`
- `0x1803bcf80`
- `0x1803d0cec`
- `0x1803f4404`
- `0x180491f24`
- `0x180492408`
- `0x18049244c`
- `0x180560b70`
- `0x1805a9c5a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180560cf9`
- `msvcrt!memcpy_s` at `0x180560d12`
- `msvcrt!memcpy_s` at `0x180560cf9`
- `msvcrt!memcpy_s` at `0x180560d12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560bba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560bf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560c3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560c9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560dee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560e03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560bba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560bf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560c3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560c9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560dee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560e03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180560b9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180560b9d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x180560d7d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x180560d7d`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180560dda`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180560dda`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall JITThunkEmitter<Memory::SectionAllocWrapper>::CreateThunk(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2)
{
  unsigned int NextBit; // eax
  unsigned __int64 v5; // r15
  char *v6; // rdi
  __int64 v7; // r12
  char *v8; // rsi
  Memory *v9; // rbp
  unsigned __int64 v10; // rax
  void *v11; // rdx
  char *v12; // r14
  __int64 v13; // r13
  void *v14; // rdx
  void *v15; // rdx
  ThreadContextInfo *v16; // rbp
  ThreadContextInfo *LockSemaphore; // rcx
  unsigned int v18; // [rsp+20h] [rbp-78h]
  bool v19; // [rsp+28h] [rbp-70h]
  void *v20; // [rsp+48h] [rbp-50h] BYREF
  void *v21; // [rsp+50h] [rbp-48h] BYREF

  EnterCriticalSection(lpCriticalSection);
  if ( !JITThunkEmitter<Memory::SectionAllocWrapper>::EnsureInitialized(lpCriticalSection)
    || (NextBit = BVStatic<25600>::GetNextBit(
                    &lpCriticalSection[1].LockSemaphore,
                    LODWORD(lpCriticalSection[81].SpinCount)),
        v5 = NextBit,
        NextBit == -1)
    || (v6 = (char *)(16LL * NextBit + *(_QWORD *)&lpCriticalSection[1].LockCount),
        v7 = (16 * (_WORD)NextBit + LOWORD(lpCriticalSection[1].LockCount)) & 0xFFF,
        v8 = &v6[-v7],
        (v9 = (Memory *)Memory::SectionAllocWrapper::AllocLocal(
                          (Memory::SectionAllocWrapper *)lpCriticalSection[1].DebugInfo,
                          &v6[-v7],
                          0x1000u)) == 0) )
  {
    LeaveCriticalSection(lpCriticalSection);
    return 0;
  }
  v10 = (unsigned __int64)&v8[-*(_QWORD *)&lpCriticalSection[1].LockCount] >> 4;
  if ( v10 > 0xFFFFFFFF )
    LODWORD(v10) = -1;
  if ( (unsigned __int8)BVStatic<256>::IsAllSet(&lpCriticalSection[1].LockSemaphore + ((unsigned __int64)(unsigned int)v10 >> 6)) )
  {
    if ( !Memory::SectionAllocWrapper::AllocPages(
            (Memory::SectionAllocWrapper *)lpCriticalSection[1].DebugInfo,
            v8,
            1u,
            0x1000u,
            v18,
            v19) )
    {
      Memory::FreeLocalView(v9, v11);
      LeaveCriticalSection(lpCriticalSection);
      return 0;
    }
    memset_0(v9, 204, 0x1000u);
  }
  v12 = (char *)v9 + v7;
  v13 = a2 - (_QWORD)v6 - 5;
  if ( (unsigned __int64)(v13 + 0x80000000LL) > 0xFFFFFFFF )
  {
    memcpy_s(v12, 0x10u, JITThunkEmitter<Memory::SectionAllocWrapper>::IndirectJmp, 0x10u);
    *(_QWORD *)(v12 + 2) = a2;
  }
  else
  {
    memcpy_s(v12, 0x10u, JITThunkEmitter<Memory::SectionAllocWrapper>::DirectJmp, 0x10u);
    *(_QWORD *)(v12 + 1) = v13;
  }
  Memory::FreeLocalView(v9, v14);
  v15 = v6;
  if ( !*(&word_18073FD88 + 1) )
  {
    LockSemaphore = (ThreadContextInfo *)lpCriticalSection[81].LockSemaphore;
LABEL_23:
    ThreadContextInfo::SetValidCallTargetForCFG(LockSemaphore, v15, 1);
    goto LABEL_24;
  }
  if ( !Memory::SectionAllocWrapper::GetFileInfo(
          (Memory::SectionAllocWrapper *)lpCriticalSection[1].DebugInfo,
          v6,
          &v21,
          &v20) )
  {
    Js::Throw::FatalInternalError(-2147467259);
    __debugbreak();
  }
  v16 = (ThreadContextInfo *)lpCriticalSection[81].LockSemaphore;
  if ( ThreadContextInfo::IsCFGEnabled(v16) )
  {
    if ( GlobalSecurityPolicy::s_ro_disableSetProcessValidCallTargets )
      RaiseFailFastException(0, 0, 1u);
    v15 = v6;
    LockSemaphore = v16;
    goto LABEL_23;
  }
LABEL_24:
  LODWORD(lpCriticalSection[81].SpinCount) = (unsigned int)(v5 + 1) < 0x6400 ? v5 + 1 : 0;
  *((_QWORD *)&lpCriticalSection[1].LockSemaphore + (v5 >> 6)) &= ~(1LL << (v5 & 0x3F));
  if ( !FlushInstructionCache(lpCriticalSection[1].OwningThread, v6, 0x10u) )
  {
    LeaveCriticalSection(lpCriticalSection);
    return 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  return v6;
}

```

## disassembly

```asm
0x180560b70  mov     rax, rsp
0x180560b73  mov     [rax+10h], rdx
0x180560b77  mov     [rax+8], rcx
0x180560b7b  push    rbp
0x180560b7c  push    rsi
0x180560b7d  push    rdi
0x180560b7e  push    r12
0x180560b80  push    r13
0x180560b82  push    r14
0x180560b84  push    r15
0x180560b86  sub     rsp, 60h
0x180560b8a  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x180560b92  mov     [rax+18h], rbx
0x180560b96  mov     rbx, rcx
0x180560b99  mov     [rax-58h], rcx
0x180560b9d  call    cs:__imp_EnterCriticalSection
0x180560ba4  nop     dword ptr [rax+rax+00h]
0x180560ba9  nop
0x180560baa  mov     rcx, rbx; lpCriticalSection
0x180560bad  call    ?EnsureInitialized@?$JITThunkEmitter@VSectionAllocWrapper@Memory@@@@QEAA_KXZ; JITThunkEmitter<Memory::SectionAllocWrapper>::EnsureInitialized(void)
0x180560bb2  test    rax, rax
0x180560bb5  jnz     short loc_180560BCE
0x180560bb7  mov     rcx, rbx; lpCriticalSection
0x180560bba  call    cs:__imp_LeaveCriticalSection
0x180560bc1  nop     dword ptr [rax+rax+00h]
0x180560bc6  nop
0x180560bc7  xor     eax, eax
0x180560bc9  jmp     loc_180560E13
0x180560bce  lea     r14, [rbx+40h]
0x180560bd2  mov     edx, [rbx+0CC8h]
0x180560bd8  mov     rcx, r14
0x180560bdb  call    ?GetNextBit@?$BVStatic@$0GEAA@@@QEBAII@Z; BVStatic<25600>::GetNextBit(uint)
0x180560be0  mov     r15d, eax
0x180560be3  mov     r13d, 0FFFFFFFFh
0x180560be9  cmp     eax, r13d
0x180560bec  jnz     short loc_180560C00
0x180560bee  mov     rcx, rbx; lpCriticalSection
0x180560bf1  call    cs:__imp_LeaveCriticalSection
0x180560bf8  nop     dword ptr [rax+rax+00h]
0x180560bfd  nop
0x180560bfe  jmp     short loc_180560BC7
0x180560c00  mov     rcx, r15
0x180560c03  shl     rcx, 4
0x180560c07  mov     rdi, [rbx+30h]
0x180560c0b  add     rdi, rcx
0x180560c0e  mov     r12, rdi
0x180560c11  and     r12d, 0FFFh
0x180560c18  mov     rsi, rdi
0x180560c1b  sub     rsi, r12
0x180560c1e  mov     r8d, 1000h; unsigned __int64
0x180560c24  mov     rdx, rsi; void *
0x180560c27  mov     rcx, [rbx+28h]; this
0x180560c2b  call    ?AllocLocal@SectionAllocWrapper@Memory@@QEAAPEAXPEAX_K@Z; Memory::SectionAllocWrapper::AllocLocal(void *,unsigned __int64)
0x180560c30  mov     rbp, rax
0x180560c33  test    rax, rax
0x180560c36  jnz     short loc_180560C4D
0x180560c38  mov     rcx, rbx; lpCriticalSection
0x180560c3b  call    cs:__imp_LeaveCriticalSection
0x180560c42  nop     dword ptr [rax+rax+00h]
0x180560c47  nop
0x180560c48  jmp     loc_180560BC7
0x180560c4d  mov     rax, rsi
0x180560c50  sub     rax, [rbx+30h]
0x180560c54  shr     rax, 4
0x180560c58  cmp     rax, r13
0x180560c5b  cmova   rax, r13
0x180560c5f  mov     eax, eax
0x180560c61  shr     rax, 6
0x180560c65  lea     rcx, [r14+rax*8]
0x180560c69  call    ?IsAllSet@?$BVStatic@$0BAA@@@QEBA_NXZ; BVStatic<256>::IsAllSet(void)
0x180560c6e  test    al, al
0x180560c70  jz      short loc_180560CBD
0x180560c72  mov     r14d, 1000h
0x180560c78  mov     r9d, r14d; unsigned int
0x180560c7b  mov     r8d, 1; unsigned __int64
0x180560c81  mov     rdx, rsi; void *
0x180560c84  mov     rcx, [rbx+28h]; this
0x180560c88  call    ?AllocPages@SectionAllocWrapper@Memory@@QEAAPEAXPEAX_KKK_N@Z; Memory::SectionAllocWrapper::AllocPages(void *,unsigned __int64,ulong,ulong,bool)
0x180560c8d  mov     rcx, rbp; this
0x180560c90  test    rax, rax
0x180560c93  jnz     short loc_180560CB0
0x180560c95  call    ?FreeLocalView@Memory@@YAHPEAX@Z; Memory::FreeLocalView(void *)
0x180560c9a  nop
0x180560c9b  mov     rcx, rbx; lpCriticalSection
0x180560c9e  call    cs:__imp_LeaveCriticalSection
0x180560ca5  nop     dword ptr [rax+rax+00h]
0x180560caa  nop
0x180560cab  jmp     loc_180560BC7
0x180560cb0  mov     r8, r14; Size
0x180560cb3  mov     edx, 0CCh; Val
0x180560cb8  call    memset_0
0x180560cbd  lea     r14, [r12+rbp]
0x180560cc1  mov     r12, [rsp+98h+arg_8]
0x180560cc9  mov     r13, r12
0x180560ccc  sub     r13, rdi
0x180560ccf  add     r13, 0FFFFFFFFFFFFFFFBh
0x180560cd3  mov     eax, 80000000h
0x180560cd8  add     rax, r13
0x180560cdb  mov     ecx, 0FFFFFFFFh
0x180560ce0  mov     esi, 10h
0x180560ce5  mov     r9d, esi; SourceSize
0x180560ce8  mov     edx, esi; DestinationSize
0x180560cea  cmp     rax, rcx
0x180560ced  mov     rcx, r14; Destination
0x180560cf0  ja      short loc_180560D0B
0x180560cf2  lea     r8, ?DirectJmp@?$JITThunkEmitter@VSectionAllocWrapper@Memory@@@@0QBEB; Source
0x180560cf9  call    cs:__imp_memcpy_s
0x180560d00  nop     dword ptr [rax+rax+00h]
0x180560d05  mov     [r14+1], r13
0x180560d09  jmp     short loc_180560D22
0x180560d0b  lea     r8, ?IndirectJmp@?$JITThunkEmitter@VSectionAllocWrapper@Memory@@@@0QBEB; Source
0x180560d12  call    cs:__imp_memcpy_s
0x180560d19  nop     dword ptr [rax+rax+00h]
0x180560d1e  mov     [r14+2], r12
0x180560d22  mov     rcx, rbp; this
0x180560d25  call    ?FreeLocalView@Memory@@YAHPEAX@Z; Memory::FreeLocalView(void *)
0x180560d2a  mov     rdx, rdi; void *
0x180560d2d  cmp     byte ptr cs:word_18073FD88+1, 0
0x180560d34  jz      short loc_180560D91
0x180560d36  lea     r9, [rsp+98h+var_50]; void **
0x180560d3b  lea     r8, [rsp+98h+var_48]; void **
0x180560d40  mov     rcx, [rbx+28h]; this
0x180560d44  call    ?GetFileInfo@SectionAllocWrapper@Memory@@QEAA_NPEAXPEAPEAX1@Z; Memory::SectionAllocWrapper::GetFileInfo(void *,void * *,void * *)
0x180560d49  test    al, al
0x180560d4b  jnz     short loc_180560D58
0x180560d4d  mov     ecx, 80004005h; int
0x180560d52  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x180560d57  int     3; Trap to Debugger
0x180560d58  mov     rbp, [rbx+0CC0h]
0x180560d5f  mov     rcx, rbp; this
0x180560d62  call    ?IsCFGEnabled@ThreadContextInfo@@QEAA_NXZ; ThreadContextInfo::IsCFGEnabled(void)
0x180560d67  test    al, al
0x180560d69  jz      short loc_180560DA0
0x180560d6b  mov     al, cs:?s_ro_disableSetProcessValidCallTargets@GlobalSecurityPolicy@@0_NC; bool volatile GlobalSecurityPolicy::s_ro_disableSetProcessValidCallTargets
0x180560d71  test    al, al
0x180560d73  jz      short loc_180560D89
0x180560d75  xor     edx, edx; pContextRecord
0x180560d77  xor     ecx, ecx; pExceptionRecord
0x180560d79  lea     r8d, [rdx+1]; dwFlags
0x180560d7d  call    cs:__imp_RaiseFailFastException
0x180560d84  nop     dword ptr [rax+rax+00h]
0x180560d89  mov     rdx, rdi
0x180560d8c  mov     rcx, rbp
0x180560d8f  jmp     short loc_180560D98
0x180560d91  mov     rcx, [rbx+0CC0h]; this
0x180560d98  mov     r8b, 1; bool
0x180560d9b  call    ?SetValidCallTargetForCFG@ThreadContextInfo@@QEAAXPEAX_N@Z; ThreadContextInfo::SetValidCallTargetForCFG(void *,bool)
0x180560da0  lea     ecx, [r15+1]
0x180560da4  cmp     ecx, 6400h
0x180560daa  sbb     eax, eax
0x180560dac  and     eax, ecx
0x180560dae  mov     [rbx+0CC8h], eax
0x180560db4  mov     rdx, r15
0x180560db7  shr     rdx, 6
0x180560dbb  and     r15d, 3Fh
0x180560dbf  mov     ecx, r15d
0x180560dc2  mov     rax, [rbx+rdx*8+40h]
0x180560dc7  btr     rax, rcx
0x180560dcb  mov     [rbx+rdx*8+40h], rax
0x180560dd0  mov     r8, rsi; dwSize
0x180560dd3  mov     rdx, rdi; lpBaseAddress
0x180560dd6  mov     rcx, [rbx+38h]; hProcess
0x180560dda  call    cs:__imp_FlushInstructionCache
0x180560de1  nop     dword ptr [rax+rax+00h]
0x180560de6  nop
0x180560de7  test    eax, eax
0x180560de9  jnz     short loc_180560E00
0x180560deb  mov     rcx, rbx; lpCriticalSection
0x180560dee  call    cs:__imp_LeaveCriticalSection
0x180560df5  nop     dword ptr [rax+rax+00h]
0x180560dfa  nop
0x180560dfb  jmp     loc_180560BC7
0x180560e00  mov     rcx, rbx; lpCriticalSection
0x180560e03  call    cs:__imp_LeaveCriticalSection
0x180560e0a  nop     dword ptr [rax+rax+00h]
0x180560e0f  nop
0x180560e10  mov     rax, rdi
0x180560e13  mov     rbx, [rsp+98h+arg_10]
0x180560e1b  add     rsp, 60h
0x180560e1f  pop     r15
0x180560e21  pop     r14
0x180560e23  pop     r13
0x180560e25  pop     r12
0x180560e27  pop     rdi
0x180560e28  pop     rsi
0x180560e29  pop     rbp
0x180560e2a  retn
```
