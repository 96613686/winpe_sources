# JITThunkEmitter<Memory::VirtualAllocWrapper>::CreateThunk(unsigned __int64)

- ea: `0x1801b4f58`
- end: `0x1801b51b0`
- name: `?CreateThunk@?$JITThunkEmitter@VVirtualAllocWrapper@Memory@@@@QEAA_K_K@Z`
- size: `600`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801b4d50`

## callees

- `0x180075b24`
- `0x1801b4f58`
- `0x1801b51b8`
- `0x1801b51e4`
- `0x1801b5270`
- `0x1801b529c`
- `0x1801b5324`
- `0x1801b53b4`
- `0x1801b543c`
- `0x1801b5c3c`
- `0x1805a9c5a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b509c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b50c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b514c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b5161`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b5176`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b518b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b509c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b50c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b514c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b5161`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b5176`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b518b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b4f84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b4f84`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801b5135`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801b5135`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x1801b5088`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x1801b5088`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall JITThunkEmitter<Memory::VirtualAllocWrapper>::CreateThunk(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2)
{
  unsigned int NextBit; // ebp
  __int64 v5; // r11
  __int64 v6; // rcx
  unsigned __int64 v7; // rsi
  void *v8; // rdi
  unsigned __int64 v9; // rax
  ThreadContextInfo *LockSemaphore; // rdi
  ThreadContextInfo *v11; // rcx

  EnterCriticalSection(lpCriticalSection);
  if ( !JITThunkEmitter<Memory::VirtualAllocWrapper>::EnsureInitialized(lpCriticalSection) )
    goto LABEL_12;
  NextBit = BVStatic<25600>::GetNextBit(&lpCriticalSection[1].LockSemaphore, LODWORD(lpCriticalSection[81].SpinCount));
  if ( NextBit == -1 )
    goto LABEL_12;
  v6 = *(_QWORD *)&lpCriticalSection[1].LockCount;
  v7 = v6 + 16LL * NextBit;
  v8 = (void *)(v7 & 0xFFFFFFFFFFFFF000uLL);
  if ( (v7 & 0xFFFFFFFFFFFFF000uLL) == 0 )
    goto LABEL_12;
  v9 = ((unsigned __int64)v8 - v6) >> 4;
  if ( v9 > 0xFFFFFFFF )
    LODWORD(v9) = -1;
  if ( (unsigned __int8)BVStatic<256>::IsAllSet(v5 + 8 * ((unsigned __int64)(unsigned int)v9 >> 6)) )
  {
    if ( !Memory::VirtualAllocWrapper::AllocPages(
            (Memory::VirtualAllocWrapper *)lpCriticalSection[1].DebugInfo,
            v8,
            1u,
            0x1000u,
            0x20u,
            1) )
      goto LABEL_12;
    JITThunkEmitter<Memory::VirtualAllocWrapper>::UnprotectPage(lpCriticalSection, v8);
    memset_0(v8, 204, 0x1000u);
  }
  else
  {
    JITThunkEmitter<Memory::VirtualAllocWrapper>::UnprotectPage(lpCriticalSection, v8);
  }
  JITThunkEmitter<Memory::VirtualAllocWrapper>::EncodeJmp(v8, v7, a2);
  JITThunkEmitter<Memory::VirtualAllocWrapper>::ProtectPage(lpCriticalSection, v8);
  LockSemaphore = (ThreadContextInfo *)lpCriticalSection[81].LockSemaphore;
  v11 = LockSemaphore;
  if ( !*(&word_18073FD88 + 1) )
    goto LABEL_9;
  if ( ThreadContextInfo::IsCFGEnabled(LockSemaphore) )
  {
    if ( GlobalSecurityPolicy::s_ro_disableSetProcessValidCallTargets )
      RaiseFailFastException(0, 0, 1u);
    v11 = LockSemaphore;
LABEL_9:
    ThreadContextInfo::SetValidCallTargetForCFG(v11, (void *)v7, 1);
  }
  LODWORD(lpCriticalSection[81].SpinCount) = NextBit + 1 < 0x6400 ? NextBit + 1 : 0;
  *((_QWORD *)&lpCriticalSection[1].LockSemaphore + ((unsigned __int64)NextBit >> 6)) &= ~(1LL << (NextBit & 0x3F));
  if ( FlushInstructionCache(lpCriticalSection[1].OwningThread, (LPCVOID)v7, 0x10u) )
  {
    LeaveCriticalSection(lpCriticalSection);
    return v7;
  }
LABEL_12:
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x1801b4f58  mov     rax, rsp
0x1801b4f5b  mov     [rax+10h], rdx
0x1801b4f5f  mov     [rax+8], rcx
0x1801b4f63  push    rbp
0x1801b4f64  push    rsi
0x1801b4f65  push    rdi
0x1801b4f66  push    r14
0x1801b4f68  push    r15
0x1801b4f6a  sub     rsp, 40h
0x1801b4f6e  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1801b4f76  mov     [rax+18h], rbx
0x1801b4f7a  mov     rbx, rcx
0x1801b4f7d  mov     r15, rdx
0x1801b4f80  mov     [rax-30h], rcx
0x1801b4f84  call    cs:__imp_EnterCriticalSection
0x1801b4f8b  nop     dword ptr [rax+rax+00h]
0x1801b4f90  nop
0x1801b4f91  mov     rcx, rbx
0x1801b4f94  call    ?EnsureInitialized@?$JITThunkEmitter@VVirtualAllocWrapper@Memory@@@@QEAA_KXZ; JITThunkEmitter<Memory::VirtualAllocWrapper>::EnsureInitialized(void)
0x1801b4f99  test    rax, rax
0x1801b4f9c  jz      loc_1801B5149
0x1801b4fa2  lea     r11, [rbx+40h]
0x1801b4fa6  mov     edx, [rbx+0CC8h]
0x1801b4fac  mov     rcx, r11
0x1801b4faf  call    ?GetNextBit@?$BVStatic@$0GEAA@@@QEBAII@Z; BVStatic<25600>::GetNextBit(uint)
0x1801b4fb4  mov     ebp, eax
0x1801b4fb6  mov     edx, 0FFFFFFFFh
0x1801b4fbb  cmp     eax, edx
0x1801b4fbd  jz      loc_1801B515E
0x1801b4fc3  mov     rcx, [rbx+30h]
0x1801b4fc7  mov     r14d, ebp
0x1801b4fca  mov     esi, ebp
0x1801b4fcc  shl     rsi, 4
0x1801b4fd0  add     rsi, rcx
0x1801b4fd3  mov     rdi, rsi
0x1801b4fd6  and     rdi, 0FFFFFFFFFFFFF000h
0x1801b4fdd  jz      loc_1801B5173
0x1801b4fe3  mov     rax, rdi
0x1801b4fe6  sub     rax, rcx
0x1801b4fe9  shr     rax, 4
0x1801b4fed  cmp     rax, rdx
0x1801b4ff0  cmova   rax, rdx
0x1801b4ff4  mov     eax, eax
0x1801b4ff6  shr     rax, 6
0x1801b4ffa  lea     rcx, [r11+rax*8]
0x1801b4ffe  call    ?IsAllSet@?$BVStatic@$0BAA@@@QEBA_NXZ; BVStatic<256>::IsAllSet(void)
0x1801b5003  mov     rdx, rdi; void *
0x1801b5006  test    al, al
0x1801b5008  jnz     loc_1801B50D5
0x1801b500e  mov     rcx, rbx
0x1801b5011  call    ?UnprotectPage@?$JITThunkEmitter@VVirtualAllocWrapper@Memory@@@@AEAAXPEAX@Z; JITThunkEmitter<Memory::VirtualAllocWrapper>::UnprotectPage(void *)
0x1801b5016  mov     r8, r15
0x1801b5019  mov     rdx, rsi
0x1801b501c  mov     rcx, rdi
0x1801b501f  call    ?EncodeJmp@?$JITThunkEmitter@VVirtualAllocWrapper@Memory@@@@CAXPEAD_K1@Z; JITThunkEmitter<Memory::VirtualAllocWrapper>::EncodeJmp(char *,unsigned __int64,unsigned __int64)
0x1801b5024  mov     rdx, rdi
0x1801b5027  mov     rcx, rbx
0x1801b502a  call    ?ProtectPage@?$JITThunkEmitter@VVirtualAllocWrapper@Memory@@@@AEAAXPEAX@Z; JITThunkEmitter<Memory::VirtualAllocWrapper>::ProtectPage(void *)
0x1801b502f  mov     rdi, [rbx+0CC0h]
0x1801b5036  mov     rcx, rdi; this
0x1801b5039  cmp     byte ptr cs:word_18073FD88+1, 0
0x1801b5040  jnz     loc_1801B519D
0x1801b5046  mov     r8b, 1; bool
0x1801b5049  mov     rdx, rsi; void *
0x1801b504c  call    ?SetValidCallTargetForCFG@ThreadContextInfo@@QEAAXPEAX_N@Z; ThreadContextInfo::SetValidCallTargetForCFG(void *,bool)
0x1801b5051  lea     ecx, [rbp+1]
0x1801b5054  cmp     ecx, 6400h
0x1801b505a  sbb     eax, eax
0x1801b505c  and     eax, ecx
0x1801b505e  mov     [rbx+0CC8h], eax
0x1801b5064  shr     r14, 6
0x1801b5068  and     ebp, 3Fh
0x1801b506b  mov     ecx, ebp
0x1801b506d  mov     rax, [rbx+r14*8+40h]
0x1801b5072  btr     rax, rcx
0x1801b5076  mov     [rbx+r14*8+40h], rax
0x1801b507b  mov     r8d, 10h; dwSize
0x1801b5081  mov     rdx, rsi; lpBaseAddress
0x1801b5084  mov     rcx, [rbx+38h]; hProcess
0x1801b5088  call    cs:__imp_FlushInstructionCache
0x1801b508f  nop     dword ptr [rax+rax+00h]
0x1801b5094  nop
0x1801b5095  test    eax, eax
0x1801b5097  jz      short loc_1801B50C1
0x1801b5099  mov     rcx, rbx; lpCriticalSection
0x1801b509c  call    cs:__imp_LeaveCriticalSection
0x1801b50a3  nop     dword ptr [rax+rax+00h]
0x1801b50a8  nop
0x1801b50a9  mov     rax, rsi
0x1801b50ac  mov     rbx, [rsp+68h+arg_10]
0x1801b50b4  add     rsp, 40h
0x1801b50b8  pop     r15
0x1801b50ba  pop     r14
0x1801b50bc  pop     rdi
0x1801b50bd  pop     rsi
0x1801b50be  pop     rbp
0x1801b50bf  retn
0x1801b50c1  mov     rcx, rbx; lpCriticalSection
0x1801b50c4  call    cs:__imp_LeaveCriticalSection
0x1801b50cb  nop     dword ptr [rax+rax+00h]
0x1801b50d0  nop
0x1801b50d1  xor     eax, eax
0x1801b50d3  jmp     short loc_1801B50AC
0x1801b50d5  mov     [rsp+68h+var_40], 1; bool
0x1801b50da  mov     [rsp+68h+flProtect], 20h ; ' '; flProtect
0x1801b50e2  mov     r9d, 1000h; unsigned int
0x1801b50e8  mov     r8d, 1; unsigned __int64
0x1801b50ee  mov     rcx, [rbx+28h]; this
0x1801b50f2  call    ?AllocPages@VirtualAllocWrapper@Memory@@QEAAPEAXPEAX_KKK_N@Z; Memory::VirtualAllocWrapper::AllocPages(void *,unsigned __int64,ulong,ulong,bool)
0x1801b50f7  test    rax, rax
0x1801b50fa  jz      loc_1801B5188
0x1801b5100  mov     rdx, rdi
0x1801b5103  mov     rcx, rbx
0x1801b5106  call    ?UnprotectPage@?$JITThunkEmitter@VVirtualAllocWrapper@Memory@@@@AEAAXPEAX@Z; JITThunkEmitter<Memory::VirtualAllocWrapper>::UnprotectPage(void *)
0x1801b510b  mov     edx, 0CCh; Val
0x1801b5110  mov     r8d, 1000h; Size
0x1801b5116  mov     rcx, rdi; void *
0x1801b5119  call    memset_0
0x1801b511e  jmp     loc_1801B5016
0x1801b5123  mov     al, cs:?s_ro_disableSetProcessValidCallTargets@GlobalSecurityPolicy@@0_NC; bool volatile GlobalSecurityPolicy::s_ro_disableSetProcessValidCallTargets
0x1801b5129  test    al, al
0x1801b512b  jz      short loc_1801B5141
0x1801b512d  xor     edx, edx; pContextRecord
0x1801b512f  xor     ecx, ecx; pExceptionRecord
0x1801b5131  lea     r8d, [rdx+1]; dwFlags
0x1801b5135  call    cs:__imp_RaiseFailFastException
0x1801b513c  nop     dword ptr [rax+rax+00h]
0x1801b5141  mov     rcx, rdi
0x1801b5144  jmp     loc_1801B5046
0x1801b5149  mov     rcx, rbx; lpCriticalSection
0x1801b514c  call    cs:__imp_LeaveCriticalSection
0x1801b5153  nop     dword ptr [rax+rax+00h]
0x1801b5158  nop
0x1801b5159  jmp     loc_1801B50D1
0x1801b515e  mov     rcx, rbx; lpCriticalSection
0x1801b5161  call    cs:__imp_LeaveCriticalSection
0x1801b5168  nop     dword ptr [rax+rax+00h]
0x1801b516d  nop
0x1801b516e  jmp     loc_1801B50D1
0x1801b5173  mov     rcx, rbx; lpCriticalSection
0x1801b5176  call    cs:__imp_LeaveCriticalSection
0x1801b517d  nop     dword ptr [rax+rax+00h]
0x1801b5182  nop
0x1801b5183  jmp     loc_1801B50D1
0x1801b5188  mov     rcx, rbx; lpCriticalSection
0x1801b518b  call    cs:__imp_LeaveCriticalSection
0x1801b5192  nop     dword ptr [rax+rax+00h]
0x1801b5197  nop
0x1801b5198  jmp     loc_1801B50D1
0x1801b519d  call    ?IsCFGEnabled@ThreadContextInfo@@QEAA_NXZ; ThreadContextInfo::IsCFGEnabled(void)
0x1801b51a2  test    al, al
0x1801b51a4  jz      loc_1801B5051
0x1801b51aa  jmp     loc_1801B5123
```
