# NativeCodeGenerator::CodeGen(Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>> *,CodeGenWorkItemIDL *,JITOutputIDL &,bool,Js::EntryPointInfo *)

- ea: `0x180044004`
- end: `0x18004428e`
- name: `?CodeGen@NativeCodeGenerator@@AEAAXPEAV?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@PEAUCodeGenWorkItemIDL@@AEAUJITOutputIDL@@_NPEAVEntryPointInfo@Js@@@Z`
- size: `650`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180043858`

## callees

- `0x180044004`
- `0x180044294`
- `0x180044390`
- `0x180069aa0`
- `0x1801c8690`
- `0x1802f76f8`
- `0x1803f07b0`
- `0x1803f1974`
- `0x1803f4558`
- `0x1803f5754`
- `0x18053fa54`
- `0x18055d6f4`
- `0x1805a9a91`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044237`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044265`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044237`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044265`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18004424c`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18004427d`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18004424c`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18004427d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall NativeCodeGenerator::CodeGen(
        __int64 a1,
        __int64 a2,
        struct CodeGenWorkItemIDL *a3,
        __int64 a4,
        char a5,
        struct Js::EntryPointInfo *a6)
{
  void *v6; // r14
  JITTimeWorkItem *v7; // rax
  JITTimeWorkItem *v8; // rax
  __int64 v9; // rcx
  void *v10; // rdx
  unsigned __int64 v11; // r10
  int result; // eax
  JITManager *v13; // rcx
  void *v14; // r8
  unsigned int v15; // ebx
  __int64 v16; // r9
  unsigned int v17; // ebx
  const void *v18; // rdi
  HANDLE CurrentProcess; // rax
  const void *v20; // rbx
  HANDLE v21; // rax
  const struct FunctionJITRuntimeInfo *v22; // [rsp+38h] [rbp-99h]
  struct Js::ScriptContextProfiler *v23; // [rsp+50h] [rbp-81h]
  char pExceptionObject; // [rsp+68h] [rbp-69h] BYREF
  _QWORD v25[2]; // [rsp+78h] [rbp-59h] BYREF
  __int128 v26; // [rsp+88h] [rbp-49h]
  __int64 v27; // [rsp+98h] [rbp-39h]
  __int64 v28; // [rsp+A0h] [rbp-31h]
  __int64 v29; // [rsp+A8h] [rbp-29h]
  char v30; // [rsp+B0h] [rbp-21h]
  __int64 v31; // [rsp+B8h] [rbp-19h]
  __int64 v32; // [rsp+C0h] [rbp-11h]
  int v33; // [rsp+C8h] [rbp-9h]
  __int64 v34; // [rsp+D0h] [rbp-1h]
  __int64 v35; // [rsp+D8h] [rbp+7h]
  __int64 v36; // [rsp+E8h] [rbp+17h]

  v36 = -2;
  if ( word_18073FD88 )
  {
    Js::ScriptContext::GetRemoteScriptAddr(*(Js::ScriptContext **)(a1 + 72), 1);
    if ( !JITManager::IsConnected((JITManager *)&JITManager::s_jitManager) )
      throw (Js::OperationAbortedException *)&pExceptionObject;
    v15 = JITManager::RemoteCodeGenCall(v13, a3, v14, (struct JITOutputIDL *)a4);
    if ( v15 == -2147024891
      && (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 72) + 272LL))(*(_QWORD *)(a1 + 72)) )
    {
      v15 = -2147467260;
    }
    JITManager::HandleServerCallResult(v15, 0);
    if ( !Memory::PreReservedVirtualAllocWrapper::IsInRange(
            *(void **)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 880LL) + 240LL),
            *(void **)(a4 + 72)) )
      Js::JITPageAddrToFuncRangeCache::AddFuncRange(
        *(Js::JITPageAddrToFuncRangeCache **)(v16 + 40),
        *(void **)(a4 + 72),
        *(_DWORD *)(a4 + 32));
    v17 = *(_DWORD *)(a4 + 32);
    v18 = *(const void **)(a4 + 72);
    CurrentProcess = GetCurrentProcess();
    result = FlushInstructionCache(CurrentProcess, v18, v17);
    v20 = *(const void **)(a4 + 80);
    if ( v20 )
    {
      v21 = GetCurrentProcess();
      return FlushInstructionCache(v21, v20, 0x10u);
    }
  }
  else
  {
    if ( a5 )
      v6 = (void *)NativeCodeGenerator::EnsureForegroundAllocators(a1, a2);
    else
      v6 = *(void **)(a1 + 240);
    v25[0] = Js::Throw::OutOfMemory;
    v25[1] = 0;
    v26 = 0;
    v27 = 0;
    v28 = a2;
    v29 = 0;
    v30 = 0;
    v31 = 3;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v7 = (JITTimeWorkItem *)Memory::ArenaAllocator::Alloc((Memory::ArenaAllocator *)v25, 0x1D0u);
    v8 = JITTimeWorkItem::JITTimeWorkItem(v7, a3);
    Func::Codegen(
      (struct Memory::JitArenaAllocator *)v25,
      v8,
      (struct ThreadContextInfo *)((*(_QWORD *)(*(_QWORD *)(a1 + 72) + 880LL) + 16LL)
                                 & -(__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 880LL) != 0)),
      *(struct ScriptContextInfo **)(a1 + 72),
      (struct JITOutputIDL *)a4,
      a6,
      v22,
      *(struct JITTimePolymorphicInlineCacheInfo *const *)(*((_QWORD *)v8 + 1) + 24LL),
      v6,
      v23,
      a5 != 1);
    v9 = *(_QWORD *)(a1 + 72);
    v10 = *(void **)(a4 + 72);
    v11 = *(_QWORD *)(*(_QWORD *)(v9 + 880) + 856LL);
    if ( !v11 || (unsigned __int64)v10 < v11 || (unsigned __int64)v10 >= v11 + (unsigned int)(dword_18073F464 << 24) )
      Js::JITPageAddrToFuncRangeCache::AddFuncRange(
        *(Js::JITPageAddrToFuncRangeCache **)(v9 + 40),
        v10,
        *(_DWORD *)(a4 + 32));
    return Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>(v25);
  }
  return result;
}

```

## disassembly

```asm
0x180044004  mov     rax, rsp
0x180044007  mov     [rax+20h], r9
0x18004400b  mov     [rax+18h], r8
0x18004400f  mov     [rax+10h], rdx
0x180044013  mov     [rax+8], rcx
0x180044017  push    rbp
0x180044018  push    rbx
0x180044019  push    rsi
0x18004401a  push    rdi
0x18004401b  push    r14
0x18004401d  lea     rbp, [rax-4Fh]
0x180044021  sub     rsp, 0F0h
0x180044028  mov     [rbp+47h+var_30], 0FFFFFFFFFFFFFFFEh
0x180044030  cmp     byte ptr cs:word_18073FD88, 0
0x180044037  jnz     loc_18004418E
0x18004403d  mov     rsi, [rbp+47h+arg_8]
0x180044041  mov     dil, [rbp+47h+arg_20]
0x180044045  mov     rbx, [rbp+47h+arg_0]
0x180044049  test    dil, dil
0x18004404c  jnz     loc_18004417B
0x180044052  mov     r14, [rbx+0F0h]
0x180044059  lea     rax, ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x180044060  mov     [rbp+47h+var_A0], rax
0x180044064  mov     [rbp+47h+var_98], 0
0x18004406c  xorps   xmm0, xmm0
0x18004406f  movdqa  [rbp+47h+var_90], xmm0
0x180044074  mov     [rbp+47h+var_80], 0
0x18004407c  mov     [rbp+47h+var_78], rsi
0x180044080  mov     [rbp+47h+var_70], 0
0x180044088  mov     [rbp+47h+var_68], 0
0x18004408c  mov     [rbp+47h+var_60], 3
0x180044094  mov     [rbp+47h+var_58], 0
0x18004409c  mov     [rbp+47h+var_50], 0
0x1800440a3  mov     [rbp+47h+var_48], 0
0x1800440ab  mov     [rbp+47h+var_40], 0
0x1800440b3  mov     edx, 1D0h; unsigned __int64
0x1800440b8  lea     rcx, [rbp+47h+var_A0]; this
0x1800440bc  call    ?Alloc@ArenaAllocator@Memory@@QEAAPEAD_K@Z; Memory::ArenaAllocator::Alloc(unsigned __int64)
0x1800440c1  mov     rdx, [rbp+47h+arg_10]; struct CodeGenWorkItemIDL *
0x1800440c5  mov     rcx, rax; this
0x1800440c8  call    ??0JITTimeWorkItem@@QEAA@PEAUCodeGenWorkItemIDL@@@Z; JITTimeWorkItem::JITTimeWorkItem(CodeGenWorkItemIDL *)
0x1800440cd  mov     r11, rax
0x1800440d0  mov     r9, [rbx+48h]; struct ScriptContextInfo *
0x1800440d4  mov     rdx, [r9+370h]
0x1800440db  xor     dil, 1
0x1800440df  mov     rax, [rax+8]
0x1800440e3  lea     rcx, [rdx+10h]
0x1800440e7  neg     rdx
0x1800440ea  sbb     r8, r8
0x1800440ed  and     r8, rcx; struct ThreadContextInfo *
0x1800440f0  mov     [rsp+50h], dil; bool
0x1800440f5  mov     [rsp+40h], r14; void *
0x1800440fa  mov     rax, [rax+18h]
0x1800440fe  mov     [rsp+110h+var_D8], rax; struct JITTimePolymorphicInlineCacheInfo *
0x180044103  mov     rax, [rbp+47h+arg_28]
0x180044107  mov     [rsp+28h], rax; struct Js::EntryPointInfo *
0x18004410c  mov     rdi, [rbp+47h+arg_18]
0x180044110  mov     [rsp+110h+var_F0], rdi; struct JITOutputIDL *
0x180044115  mov     rdx, r11; struct JITTimeWorkItem *
0x180044118  lea     rcx, [rbp+47h+var_A0]; struct Memory::JitArenaAllocator *
0x18004411c  call    ?Codegen@Func@@SAXPEAVJitArenaAllocator@Memory@@PEAVJITTimeWorkItem@@PEAVThreadContextInfo@@PEAVScriptContextInfo@@PEAUJITOutputIDL@@PEAVEntryPointInfo@Js@@QEBVFunctionJITRuntimeInfo@@QEAVJITTimePolymorphicInlineCacheInfo@@QEAXQEAVScriptContextProfiler@9@_N@Z; Func::Codegen(Memory::JitArenaAllocator *,JITTimeWorkItem *,ThreadContextInfo *,ScriptContextInfo *,JITOutputIDL *,Js::EntryPointInfo *,FunctionJITRuntimeInfo const * const,JITTimePolymorphicInlineCacheInfo * const,void * const,Js::ScriptContextProfiler * const,bool)
0x180044121  mov     rcx, [rbx+48h]
0x180044125  mov     rdx, [rdi+48h]; void *
0x180044129  mov     rax, [rcx+370h]
0x180044130  mov     r10, [rax+358h]
0x180044137  test    r10, r10
0x18004413a  jz      short loc_18004416C
0x18004413c  cmp     rdx, r10
0x18004413f  jb      short loc_18004416C
0x180044141  mov     r9d, cs:dword_18073F464
0x180044148  shl     r9d, 18h
0x18004414c  add     r9, r10
0x18004414f  cmp     rdx, r9
0x180044152  jnb     short loc_18004416C
0x180044154  lea     rcx, [rbp+47h+var_A0]
0x180044158  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@Memory@@$03$0A@$0A@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>(void)
0x18004415d  add     rsp, 0F0h
0x180044164  pop     r14
0x180044166  pop     rdi
0x180044167  pop     rsi
0x180044168  pop     rbx
0x180044169  pop     rbp
0x18004416a  retn
0x18004416c  mov     r8d, [rdi+20h]; unsigned int
0x180044170  mov     rcx, [rcx+28h]; this
0x180044174  call    ?AddFuncRange@JITPageAddrToFuncRangeCache@Js@@QEAAXPEAXI@Z; Js::JITPageAddrToFuncRangeCache::AddFuncRange(void *,uint)
0x180044179  jmp     short loc_180044154
0x18004417b  mov     rdx, rsi
0x18004417e  mov     rcx, rbx
0x180044181  call    ?EnsureForegroundAllocators@NativeCodeGenerator@@AEAAPEAV?$CodeGenAllocators@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@@@PEAV?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@@Z; NativeCodeGenerator::EnsureForegroundAllocators(Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>> *)
0x180044186  mov     r14, rax
0x180044189  jmp     loc_180044059
0x18004418e  mov     rdi, [rbp+47h+arg_0]
0x180044192  mov     dl, 1; bool
0x180044194  mov     rcx, [rdi+48h]; this
0x180044198  call    ?GetRemoteScriptAddr@ScriptContext@Js@@QEAAPEAX_N@Z; Js::ScriptContext::GetRemoteScriptAddr(bool)
0x18004419d  mov     r8, rax
0x1800441a0  lea     rcx, ?s_jitManager@JITManager@@0V1@A; this
0x1800441a7  call    ?IsConnected@JITManager@@QEBA_NXZ; JITManager::IsConnected(void)
0x1800441ac  test    al, al
0x1800441ae  jnz     short loc_1800441C1
0x1800441b0  lea     rdx, _TI2?AVOperationAbortedException@Js@@; pThrowInfo
0x1800441b7  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x1800441bb  call    _CxxThrowException_0
0x1800441c1  mov     rsi, [rbp+47h+arg_18]
0x1800441c5  mov     r9, rsi; struct JITOutputIDL *
0x1800441c8  mov     rdx, [rbp+47h+arg_10]; struct CodeGenWorkItemIDL *
0x1800441cc  call    ?RemoteCodeGenCall@JITManager@@QEAAJPEAUCodeGenWorkItemIDL@@PEAXPEAUJITOutputIDL@@@Z; JITManager::RemoteCodeGenCall(CodeGenWorkItemIDL *,void *,JITOutputIDL *)
0x1800441d1  mov     ebx, eax
0x1800441d3  cmp     eax, 80070005h
0x1800441d8  jnz     short loc_1800441F7
0x1800441da  mov     rcx, [rdi+48h]
0x1800441de  mov     rdx, [rcx]
0x1800441e1  mov     rax, [rdx+110h]
0x1800441e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441ed  mov     ecx, 80004004h
0x1800441f2  test    al, al
0x1800441f4  cmovnz  ebx, ecx
0x1800441f7  xor     edx, edx
0x1800441f9  mov     ecx, ebx
0x1800441fb  call    ?HandleServerCallResult@JITManager@@SA_NJW4RemoteCallType@@@Z; JITManager::HandleServerCallResult(long,RemoteCallType)
0x180044200  mov     r9, [rdi+48h]
0x180044204  mov     rcx, [r9+370h]
0x18004420b  mov     rdx, [rsi+48h]; void *
0x18004420f  mov     rcx, [rcx+0F0h]; void *
0x180044216  call    ?IsInRange@PreReservedVirtualAllocWrapper@Memory@@SA_NPEAX0@Z; Memory::PreReservedVirtualAllocWrapper::IsInRange(void *,void *)
0x18004421b  test    al, al
0x18004421d  jnz     short loc_180044230
0x18004421f  mov     r8d, [rsi+20h]; unsigned int
0x180044223  mov     rdx, [rsi+48h]; void *
0x180044227  mov     rcx, [r9+28h]; this
0x18004422b  call    ?AddFuncRange@JITPageAddrToFuncRangeCache@Js@@QEAAXPEAXI@Z; Js::JITPageAddrToFuncRangeCache::AddFuncRange(void *,uint)
0x180044230  mov     ebx, [rsi+20h]
0x180044233  mov     rdi, [rsi+48h]
0x180044237  call    cs:__imp_GetCurrentProcess
0x18004423e  nop     dword ptr [rax+rax+00h]
0x180044243  mov     r8d, ebx; dwSize
0x180044246  mov     rdx, rdi; lpBaseAddress
0x180044249  mov     rcx, rax; hProcess
0x18004424c  call    cs:__imp_FlushInstructionCache
0x180044253  nop     dword ptr [rax+rax+00h]
0x180044258  mov     rbx, [rsi+50h]
0x18004425c  test    rbx, rbx
0x18004425f  jz      loc_18004415D
0x180044265  call    cs:__imp_GetCurrentProcess
0x18004426c  nop     dword ptr [rax+rax+00h]
0x180044271  mov     r8d, 10h; dwSize
0x180044277  mov     rdx, rbx; lpBaseAddress
0x18004427a  mov     rcx, rax; hProcess
0x18004427d  call    cs:__imp_FlushInstructionCache
0x180044284  nop     dword ptr [rax+rax+00h]
0x180044289  jmp     loc_18004415D
```
