# PerfDiagDm::GetSnapshotPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,WDILOGGER,void *)

- ea: `0x1800ae95c`
- end: `0x1800aea8b`
- name: `?GetSnapshotPath@PerfDiagDm@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4WDILOGGER@@PEAX@Z`
- size: `303`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800ae878`
- `0x1800ae914`

## callees

- `0x180016a1c`
- `0x180026ea0`
- `0x180031e34`
- `0x1800421dc`
- `0x1800ae95c`
- `0x1800cf032`

## import_xrefs

- `msvcrt!malloc` at `0x1800ae9ec`
- `msvcrt!malloc` at `0x1800ae9ec`
- `msvcrt!free` at `0x1800aea41`
- `msvcrt!free` at `0x1800aea50`
- `msvcrt!free` at `0x1800aea6f`
- `msvcrt!free` at `0x1800aea41`
- `msvcrt!free` at `0x1800aea50`
- `msvcrt!free` at `0x1800aea6f`
- `wdi!WdiGetLoggerSnapshotPath` at `0x1800ae999`
- `wdi!WdiGetLoggerSnapshotPath` at `0x1800aea1b`
- `wdi!WdiGetLoggerSnapshotPath` at `0x1800ae999`
- `wdi!WdiGetLoggerSnapshotPath` at `0x1800aea1b`

## pseudocode

```c
__int64 __fastcall PerfDiagDm::GetSnapshotPath(__int64 a1, unsigned int a2, __int64 a3)
{
  void *v6; // rbx
  int LoggerSnapshotPath; // edi
  void *v8; // rcx
  __int64 v9; // rdi
  void *v10; // rax
  __int64 result; // rax
  _BYTE v12[8]; // [rsp+20h] [rbp-38h] BYREF
  size_t Size; // [rsp+28h] [rbp-30h] BYREF
  ATL::CAtlException *v14; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+20h] BYREF

  v6 = 0;
  PerfDiagDm::ThreadPriorityContext::ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)v12, 2);
  v15 = 0;
  LoggerSnapshotPath = WdiGetLoggerSnapshotPath(a3, a2, 0, &v15);
  if ( LoggerSnapshotPath < 0 )
    goto LABEL_4;
  if ( !v15 )
  {
    LoggerSnapshotPath = -2147467259;
LABEL_4:
    PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)v12);
    v8 = 0;
LABEL_11:
    free(v8);
    return (unsigned int)LoggerSnapshotPath;
  }
  v9 = v15;
  Size = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(&Size, v15, 2) < 0
    || (v10 = malloc(Size), v6 = v10, (Size = (size_t)v10) == 0) )
  {
    LoggerSnapshotPath = -2147024882;
    goto LABEL_10;
  }
  memset_0(v10, 0, 2 * v9);
  LoggerSnapshotPath = WdiGetLoggerSnapshotPath(a3, a2, v6, &v15);
  if ( LoggerSnapshotPath < 0 )
  {
LABEL_10:
    PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)v12);
    v8 = v6;
    goto LABEL_11;
  }
  PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)v12);
  try
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1, v6);
    free(v6);
    result = 0;
  }
  catch ( ATL::CAtlException *v14 )
  {
    v15 = *(_DWORD *)v14;
    free((void *)Size);
    return v15;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(a1, v6);
}

```

## disassembly

```asm
0x1800ae95c  mov     [rsp+arg_0], rbx
0x1800ae961  mov     [rsp+arg_8], rsi
0x1800ae966  push    rdi
0x1800ae967  push    r14
0x1800ae969  push    r15
0x1800ae96b  sub     rsp, 40h
0x1800ae96f  mov     r14, r8
0x1800ae972  mov     r15d, edx
0x1800ae975  mov     rsi, rcx
0x1800ae978  xor     ebx, ebx
0x1800ae97a  lea     edx, [rbx+2]; int
0x1800ae97d  lea     rcx, [rsp+58h+var_38]; this
0x1800ae982  call    ??0ThreadPriorityContext@PerfDiagDm@@QEAA@H@Z; PerfDiagDm::ThreadPriorityContext::ThreadPriorityContext(int)
0x1800ae987  mov     [rsp+58h+arg_18], ebx
0x1800ae98b  lea     r9, [rsp+58h+arg_18]
0x1800ae990  xor     r8d, r8d
0x1800ae993  mov     edx, r15d
0x1800ae996  mov     rcx, r14
0x1800ae999  call    cs:__imp_WdiGetLoggerSnapshotPath
0x1800ae99f  mov     edi, eax
0x1800ae9a1  test    eax, eax
0x1800ae9a3  js      short loc_1800AE9B2
0x1800ae9a5  mov     eax, [rsp+58h+arg_18]
0x1800ae9a9  test    eax, eax
0x1800ae9ab  jnz     short loc_1800AE9C4
0x1800ae9ad  mov     edi, 80004005h
0x1800ae9b2  lea     rcx, [rsp+58h+var_38]; this
0x1800ae9b7  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x1800ae9bc  nop
0x1800ae9bd  xor     ecx, ecx
0x1800ae9bf  jmp     loc_1800AEA6F
0x1800ae9c4  mov     rdi, rax
0x1800ae9c7  mov     [rsp+58h+Size], 0
0x1800ae9d0  mov     r8d, 2
0x1800ae9d6  mov     rdx, rax
0x1800ae9d9  lea     rcx, [rsp+58h+Size]
0x1800ae9de  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x1800ae9e3  test    eax, eax
0x1800ae9e5  js      short loc_1800AEA5C
0x1800ae9e7  mov     rcx, [rsp+58h+Size]; Size
0x1800ae9ec  call    cs:__imp_malloc
0x1800ae9f2  mov     rbx, rax
0x1800ae9f5  mov     [rsp+58h+Size], rax
0x1800ae9fa  test    rax, rax
0x1800ae9fd  jz      short loc_1800AEA5C
0x1800ae9ff  lea     r8, [rdi+rdi]; Size
0x1800aea03  xor     edx, edx; Val
0x1800aea05  mov     rcx, rax; void *
0x1800aea08  call    memset_0
0x1800aea0d  lea     r9, [rsp+58h+arg_18]
0x1800aea12  mov     r8, rbx
0x1800aea15  mov     edx, r15d
0x1800aea18  mov     rcx, r14
0x1800aea1b  call    cs:__imp_WdiGetLoggerSnapshotPath
0x1800aea21  mov     edi, eax
0x1800aea23  test    eax, eax
0x1800aea25  js      short loc_1800AEA61
0x1800aea27  lea     rcx, [rsp+58h+var_38]; this
0x1800aea2c  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x1800aea31  nop
0x1800aea32  mov     rdx, rbx
0x1800aea35  mov     rcx, rsi
0x1800aea38  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800aea3d  nop
0x1800aea3e  mov     rcx, rbx; Block
0x1800aea41  call    cs:__imp_free
0x1800aea47  xor     eax, eax
0x1800aea49  jmp     short loc_1800AEA77
0x1800aea4b  mov     rcx, [rsp+58h+Size]; Block
0x1800aea50  call    cs:__imp_free
0x1800aea56  mov     eax, [rsp+58h+arg_18]
0x1800aea5a  jmp     short loc_1800AEA77
0x1800aea5c  mov     edi, 8007000Eh
0x1800aea61  lea     rcx, [rsp+58h+var_38]; this
0x1800aea66  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x1800aea6b  nop
0x1800aea6c  mov     rcx, rbx; Block
0x1800aea6f  call    cs:__imp_free
0x1800aea75  mov     eax, edi
0x1800aea77  mov     rbx, [rsp+58h+arg_0]
0x1800aea7c  mov     rsi, [rsp+58h+arg_8]
0x1800aea81  add     rsp, 40h
0x1800aea85  pop     r15
0x1800aea87  pop     r14
0x1800aea89  pop     rdi
0x1800aea8a  retn
```
