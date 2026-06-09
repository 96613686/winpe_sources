# JITThunkEmitter<Memory::SectionAllocWrapper>::FreeThunk(unsigned __int64)

- ea: `0x180560e34`
- end: `0x180560ff7`
- name: `?FreeThunk@?$JITThunkEmitter@VSectionAllocWrapper@Memory@@@@QEAAX_K@Z`
- size: `451`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801b3378`
- `0x18056120c`

## callees

- `0x1801b51b8`
- `0x1801b5270`
- `0x1801b5c3c`
- `0x1803bcf80`
- `0x1803d0cec`
- `0x180492338`
- `0x180492408`
- `0x18049244c`
- `0x180560e34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560f84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560fc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560fdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560f84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560fc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180560fdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180560e5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180560e5c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x180560efc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x180560efc`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180560fb0`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180560fb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall JITThunkEmitter<Memory::SectionAllocWrapper>::FreeThunk(
        LPCRITICAL_SECTION lpCriticalSection,
        unsigned __int64 a2)
{
  unsigned __int64 v4; // rcx
  void *v5; // rdx
  ThreadContextInfo *LockSemaphore; // rsi
  ThreadContextInfo *v7; // rcx
  unsigned __int64 v8; // rax
  char IsAllSet; // al
  void *v10; // r10
  Memory::SectionAllocWrapper *DebugInfo; // rcx
  Memory *v12; // rax
  void *v13; // rdx
  void *v14; // [rsp+30h] [rbp-28h] BYREF
  void *v15; // [rsp+38h] [rbp-20h] BYREF

  EnterCriticalSection(lpCriticalSection);
  v4 = (a2 - *(_QWORD *)&lpCriticalSection[1].LockCount) >> 4;
  if ( v4 > 0xFFFFFFFF )
    LODWORD(v4) = -1;
  if ( (unsigned int)v4 >= 0x6400 || _bittestandset((signed __int32 *)&lpCriticalSection[1].LockSemaphore, v4) )
  {
    LODWORD(lpCriticalSection[81].SpinCount) = 0;
    LeaveCriticalSection(lpCriticalSection);
    return;
  }
  if ( (unsigned int)v4 < LODWORD(lpCriticalSection[81].SpinCount) )
    LODWORD(lpCriticalSection[81].SpinCount) = v4;
  v5 = (void *)a2;
  if ( *(&word_18073FD88 + 1) )
  {
    if ( !Memory::SectionAllocWrapper::GetFileInfo(
            (Memory::SectionAllocWrapper *)lpCriticalSection[1].DebugInfo,
            (void *)a2,
            &v15,
            &v14) )
    {
      Js::Throw::FatalInternalError(-2147467259);
      __debugbreak();
    }
    LockSemaphore = (ThreadContextInfo *)lpCriticalSection[81].LockSemaphore;
    if ( !ThreadContextInfo::IsCFGEnabled(LockSemaphore) )
      goto LABEL_16;
    if ( GlobalSecurityPolicy::s_ro_disableSetProcessValidCallTargets )
      RaiseFailFastException(0, 0, 1u);
    v5 = (void *)a2;
    v7 = LockSemaphore;
  }
  else
  {
    v7 = (ThreadContextInfo *)lpCriticalSection[81].LockSemaphore;
  }
  ThreadContextInfo::SetValidCallTargetForCFG(v7, v5, 0);
LABEL_16:
  v8 = ((a2 & 0xFFFFFFFFFFFFF000uLL) - *(_QWORD *)&lpCriticalSection[1].LockCount) >> 4;
  if ( v8 > 0xFFFFFFFF )
    LODWORD(v8) = -1;
  IsAllSet = BVStatic<256>::IsAllSet(&lpCriticalSection[1].LockSemaphore + ((unsigned __int64)(unsigned int)v8 >> 6));
  DebugInfo = (Memory::SectionAllocWrapper *)lpCriticalSection[1].DebugInfo;
  if ( IsAllSet )
  {
    Memory::SectionAllocWrapper::Free(DebugInfo, v10, 0x1000u, 0x4000u);
  }
  else
  {
    v12 = (Memory *)Memory::SectionAllocWrapper::AllocLocal(DebugInfo, (void *)a2, 0x10u);
    if ( !v12 )
    {
      LeaveCriticalSection(lpCriticalSection);
      return;
    }
    *(__m128i *)v12 = _mm_load_si128((const __m128i *)&_xmm_cccccccccccccccccccccccccccccccc);
    Memory::FreeLocalView(v12, v13);
  }
  FlushInstructionCache(lpCriticalSection[1].OwningThread, (LPCVOID)a2, 0x10u);
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180560e34  mov     rax, rsp
0x180560e37  mov     [rax+10h], rdx
0x180560e3b  mov     [rax+8], rcx
0x180560e3f  push    rbp
0x180560e40  push    rsi
0x180560e41  push    rdi
0x180560e42  sub     rsp, 40h
0x180560e46  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180560e4e  mov     [rax+18h], rbx
0x180560e52  mov     rdi, rdx
0x180560e55  mov     rbx, rcx
0x180560e58  mov     [rax-30h], rcx
0x180560e5c  call    cs:__imp_EnterCriticalSection
0x180560e63  nop     dword ptr [rax+rax+00h]
0x180560e68  nop
0x180560e69  mov     rcx, rdi
0x180560e6c  sub     rcx, [rbx+30h]
0x180560e70  shr     rcx, 4
0x180560e74  mov     ebp, 0FFFFFFFFh
0x180560e79  cmp     rcx, rbp
0x180560e7c  cmova   rcx, rbp
0x180560e80  cmp     ecx, 6400h
0x180560e86  jnb     loc_180560FCF
0x180560e8c  bts     [rbx+40h], ecx
0x180560e90  setb    al
0x180560e93  test    al, al
0x180560e95  jnz     loc_180560FCF
0x180560e9b  cmp     ecx, [rbx+0CC8h]
0x180560ea1  jnb     short loc_180560EA9
0x180560ea3  mov     [rbx+0CC8h], ecx
0x180560ea9  mov     rdx, rdi; void *
0x180560eac  cmp     byte ptr cs:word_18073FD88+1, 0
0x180560eb3  jz      short loc_180560F10
0x180560eb5  lea     r9, [rsp+58h+var_28]; void **
0x180560eba  lea     r8, [rsp+58h+var_20]; void **
0x180560ebf  mov     rcx, [rbx+28h]; this
0x180560ec3  call    ?GetFileInfo@SectionAllocWrapper@Memory@@QEAA_NPEAXPEAPEAX1@Z; Memory::SectionAllocWrapper::GetFileInfo(void *,void * *,void * *)
0x180560ec8  test    al, al
0x180560eca  jnz     short loc_180560ED7
0x180560ecc  mov     ecx, 80004005h; int
0x180560ed1  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x180560ed6  int     3; Trap to Debugger
0x180560ed7  mov     rsi, [rbx+0CC0h]
0x180560ede  mov     rcx, rsi; this
0x180560ee1  call    ?IsCFGEnabled@ThreadContextInfo@@QEAA_NXZ; ThreadContextInfo::IsCFGEnabled(void)
0x180560ee6  test    al, al
0x180560ee8  jz      short loc_180560F1F
0x180560eea  mov     al, cs:?s_ro_disableSetProcessValidCallTargets@GlobalSecurityPolicy@@0_NC; bool volatile GlobalSecurityPolicy::s_ro_disableSetProcessValidCallTargets
0x180560ef0  test    al, al
0x180560ef2  jz      short loc_180560F08
0x180560ef4  xor     edx, edx; pContextRecord
0x180560ef6  xor     ecx, ecx; pExceptionRecord
0x180560ef8  lea     r8d, [rdx+1]; dwFlags
0x180560efc  call    cs:__imp_RaiseFailFastException
0x180560f03  nop     dword ptr [rax+rax+00h]
0x180560f08  mov     rdx, rdi
0x180560f0b  mov     rcx, rsi
0x180560f0e  jmp     short loc_180560F17
0x180560f10  mov     rcx, [rbx+0CC0h]; this
0x180560f17  xor     r8d, r8d; bool
0x180560f1a  call    ?SetValidCallTargetForCFG@ThreadContextInfo@@QEAAXPEAX_N@Z; ThreadContextInfo::SetValidCallTargetForCFG(void *,bool)
0x180560f1f  mov     r10, rdi
0x180560f22  and     r10, 0FFFFFFFFFFFFF000h
0x180560f29  mov     rax, r10
0x180560f2c  sub     rax, [rbx+30h]
0x180560f30  shr     rax, 4
0x180560f34  cmp     rax, rbp
0x180560f37  cmova   rax, rbp
0x180560f3b  mov     eax, eax
0x180560f3d  shr     rax, 6
0x180560f41  add     rax, 8
0x180560f45  lea     rcx, [rbx+rax*8]
0x180560f49  call    ?IsAllSet@?$BVStatic@$0BAA@@@QEBA_NXZ; BVStatic<256>::IsAllSet(void)
0x180560f4e  mov     esi, 10h
0x180560f53  mov     rcx, [rbx+28h]; this
0x180560f57  test    al, al
0x180560f59  jz      short loc_180560F71
0x180560f5b  mov     r9d, 4000h; unsigned int
0x180560f61  mov     r8d, 1000h; unsigned __int64
0x180560f67  mov     rdx, r10; void *
0x180560f6a  call    ?Free@SectionAllocWrapper@Memory@@QEAAHPEAX_KK@Z; Memory::SectionAllocWrapper::Free(void *,unsigned __int64,ulong)
0x180560f6f  jmp     short loc_180560FA6
0x180560f71  mov     r8, rsi; unsigned __int64
0x180560f74  mov     rdx, rdi; void *
0x180560f77  call    ?AllocLocal@SectionAllocWrapper@Memory@@QEAAPEAXPEAX_K@Z; Memory::SectionAllocWrapper::AllocLocal(void *,unsigned __int64)
0x180560f7c  test    rax, rax
0x180560f7f  jnz     short loc_180560F93
0x180560f81  mov     rcx, rbx; lpCriticalSection
0x180560f84  call    cs:__imp_LeaveCriticalSection
0x180560f8b  nop     dword ptr [rax+rax+00h]
0x180560f90  nop
0x180560f91  jmp     short loc_180560FE9
0x180560f93  movdqa  xmm0, cs:__xmm@cccccccccccccccccccccccccccccccc
0x180560f9b  movups  xmmword ptr [rax], xmm0
0x180560f9e  mov     rcx, rax; this
0x180560fa1  call    ?FreeLocalView@Memory@@YAHPEAX@Z; Memory::FreeLocalView(void *)
0x180560fa6  mov     r8, rsi; dwSize
0x180560fa9  mov     rdx, rdi; lpBaseAddress
0x180560fac  mov     rcx, [rbx+38h]; hProcess
0x180560fb0  call    cs:__imp_FlushInstructionCache
0x180560fb7  nop     dword ptr [rax+rax+00h]
0x180560fbc  nop
0x180560fbd  mov     rcx, rbx; lpCriticalSection
0x180560fc0  call    cs:__imp_LeaveCriticalSection
0x180560fc7  nop     dword ptr [rax+rax+00h]
0x180560fcc  nop
0x180560fcd  jmp     short loc_180560FE9
0x180560fcf  mov     dword ptr [rbx+0CC8h], 0
0x180560fd9  mov     rcx, rbx; lpCriticalSection
0x180560fdc  call    cs:__imp_LeaveCriticalSection
0x180560fe3  nop     dword ptr [rax+rax+00h]
0x180560fe8  nop
0x180560fe9  mov     rbx, [rsp+58h+arg_10]
0x180560fee  add     rsp, 40h
0x180560ff2  pop     rdi
0x180560ff3  pop     rsi
0x180560ff4  pop     rbp
0x180560ff5  retn
```
