# CCompRC::Init(ushort *,int)

- ea: `0x180004fe0`
- end: `0x180005183`
- name: `?Init@CCompRC@@QEAAJPEAGH@Z`
- size: `419`
- prototype: `int(CCompRC *__hidden this, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180003160`
- `0x18003efb0`

## callees

- `0x180003840`
- `0x180004d50`
- `0x180004eb0`
- `0x180004fe0`
- `0x180005538`
- `0x18000c1a8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005101`
- `KERNEL32!GetLastError` at `0x18000515a`
- `KERNEL32!GetLastError` at `0x180005101`
- `KERNEL32!GetLastError` at `0x18000515a`
- `KERNEL32!SetLastError` at `0x180005167`
- `KERNEL32!SetLastError` at `0x180005167`

## string_xrefs

- `0x180005012`: `mscorrc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCompRC::Init(CCompRC *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  unsigned __int8 near **v6; // rcx
  void *v7; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rbx
  DWORD LastError; // r14d
  wchar_t *v12; // rbx
  __int128 v13; // [rsp+30h] [rbp-28h] BYREF

  *((_DWORD *)this + 58) = a3;
  if ( !*((_QWORD *)this + 26) )
  {
    if ( a2 )
    {
      *(_QWORD *)&v13 = 0;
      DWORD2(v13) = 0;
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      v9 = (unsigned int)(v8 + 1);
      v10 = 2 * v9;
      if ( !is_mul_ok(v9, 2u) )
        v10 = -1;
      LastError = GetLastError();
      v12 = (wchar_t *)ClrAllocInProcessHeapBootstrap(0, v10);
      if ( LastError && !GetLastError() )
        SetLastError(LastError);
      *(_QWORD *)&v13 = v12;
      if ( v12 )
      {
        DWORD2(v13) = 1;
        wcscpy_s(v12, v9, a2);
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 26, (signed __int64)v12, 0) )
          operator delete(v12);
      }
    }
    else
    {
      _InterlockedCompareExchange64((volatile signed __int64 *)this + 26, (signed __int64)L"mscorrc.dll", 0);
    }
  }
  if ( !*((_QWORD *)this + 26) )
    return 2147942414LL;
  if ( !*((_QWORD *)this + 25) )
  {
    v6 = (unsigned __int8 near **)g_pExecutionEngine;
    if ( !g_pExecutionEngine )
    {
      UtilExecutionEngine::UtilExecutionEngine((UtilExecutionEngine *)&v13);
      *(_OWORD *)&g_ExecutionEngineInstance = v13;
      v6 = &g_ExecutionEngineInstance;
      g_pExecutionEngine = (struct IExecutionEngine *)&g_ExecutionEngineInstance;
    }
    v7 = (void *)(*((__int64 (__fastcall **)(unsigned __int8 near **, _QWORD, __int64, __int64))*v6 + 9))(v6, 0, 8, 152);
    if ( v7 && _InterlockedCompareExchange64((volatile signed __int64 *)this + 25, (signed __int64)v7, 0) )
      ClrDeleteCriticalSection(v7);
  }
  result = 0;
  if ( !*((_QWORD *)this + 25) )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x180004fe0  mov     [rsp+arg_8], rbx
0x180004fe5  mov     [rsp+arg_10], rbp
0x180004fea  push    rsi
0x180004feb  push    rdi
0x180004fec  push    r14
0x180004fee  sub     rsp, 40h
0x180004ff2  mov     rdi, rdx
0x180004ff5  mov     rsi, rcx
0x180004ff8  mov     [rcx+0E8h], r8d
0x180004fff  cmp     qword ptr [rcx+0D0h], 0
0x180005007  jnz     short loc_180005024
0x180005009  test    rdx, rdx
0x18000500c  jnz     loc_1800050C9
0x180005012  lea     rcx, aMscorrcDll; "mscorrc.dll"
0x180005019  xor     eax, eax
0x18000501b  lock cmpxchg [rsi+0D0h], rcx
0x180005024  cmp     qword ptr [rsi+0D0h], 0
0x18000502c  jnz     short loc_180005046
0x18000502e  mov     eax, 8007000Eh
0x180005033  mov     rbx, [rsp+58h+arg_8]
0x180005038  mov     rbp, [rsp+58h+arg_10]
0x18000503d  add     rsp, 40h
0x180005041  pop     r14
0x180005043  pop     rdi
0x180005044  pop     rsi
0x180005045  retn
0x180005046  cmp     qword ptr [rsi+0C8h], 0
0x18000504e  jnz     short loc_1800050B3
0x180005050  mov     rcx, cs:?g_pExecutionEngine@@3PEAUIExecutionEngine@@EA; IExecutionEngine * g_pExecutionEngine
0x180005057  test    rcx, rcx
0x18000505a  jnz     short loc_180005080
0x18000505c  lea     rcx, [rsp+58h+var_28]; this
0x180005061  call    ??0UtilExecutionEngine@@QEAA@XZ; UtilExecutionEngine::UtilExecutionEngine(void)
0x180005066  movups  xmm0, [rsp+58h+var_28]
0x18000506b  movups  cs:?g_ExecutionEngineInstance@@3PAEA, xmm0; uchar near * g_ExecutionEngineInstance
0x180005072  lea     rcx, ?g_ExecutionEngineInstance@@3PAEA; uchar near * g_ExecutionEngineInstance
0x180005079  mov     cs:?g_pExecutionEngine@@3PEAUIExecutionEngine@@EA, rcx; IExecutionEngine * g_pExecutionEngine
0x180005080  mov     rax, [rcx]
0x180005083  xor     edx, edx
0x180005085  mov     r9d, 98h
0x18000508b  mov     r8d, 8
0x180005091  mov     rax, [rax+48h]
0x180005095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000509a  mov     rcx, rax; void *
0x18000509d  test    rax, rax
0x1800050a0  jz      short loc_1800050B3
0x1800050a2  xor     eax, eax
0x1800050a4  lock cmpxchg [rsi+0C8h], rcx
0x1800050ad  jnz     loc_180005179
0x1800050b3  xor     eax, eax
0x1800050b5  mov     ecx, 8007000Eh
0x1800050ba  cmp     [rsi+0C8h], rax
0x1800050c1  cmovz   eax, ecx
0x1800050c4  jmp     loc_180005033
0x1800050c9  mov     qword ptr [rsp+58h+var_28], 0
0x1800050d2  mov     dword ptr [rsp+58h+var_28+8], 0
0x1800050da  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800050e1  mov     rax, rcx
0x1800050e4  lea     rax, [rax+1]
0x1800050e8  cmp     word ptr [rdx+rax*2], 0
0x1800050ed  jnz     short loc_1800050E4
0x1800050ef  lea     ebp, [rax+1]
0x1800050f2  mov     eax, 2
0x1800050f7  mul     rbp
0x1800050fa  mov     rbx, rax
0x1800050fd  cmovb   rbx, rcx
0x180005101  call    cs:__imp_GetLastError
0x180005107  mov     r14d, eax
0x18000510a  mov     [rsp+58h+arg_0], eax
0x18000510e  mov     [rsp+58h+arg_4], 2
0x180005116  mov     rdx, rbx; unsigned __int64
0x180005119  xor     ecx, ecx; unsigned int
0x18000511b  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x180005120  mov     rbx, rax
0x180005123  test    r14d, r14d
0x180005126  jnz     short loc_18000515A
0x180005128  mov     qword ptr [rsp+58h+var_28], rbx
0x18000512d  test    rbx, rbx
0x180005130  jz      short loc_180005155
0x180005132  mov     dword ptr [rsp+58h+var_28+8], 1
0x18000513a  mov     r8, rdi; Source
0x18000513d  mov     rdx, rbp; SizeInWords
0x180005140  mov     rcx, rbx; Destination
0x180005143  call    wcscpy_s
0x180005148  xor     eax, eax
0x18000514a  lock cmpxchg [rsi+0D0h], rbx
0x180005153  jnz     short loc_18000516F
0x180005155  jmp     loc_180005024
0x18000515a  call    cs:__imp_GetLastError
0x180005160  test    eax, eax
0x180005162  jnz     short loc_180005128
0x180005164  mov     ecx, r14d; dwErrCode
0x180005167  call    cs:__imp_SetLastError
0x18000516d  jmp     short loc_180005128
0x18000516f  mov     rcx, rbx; void *
0x180005172  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005177  jmp     short loc_180005155
0x180005179  call    ?ClrDeleteCriticalSection@@YAJPEAX@Z; ClrDeleteCriticalSection(void *)
0x18000517e  jmp     loc_1800050B3
```
