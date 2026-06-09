# DSOpenSharedFile

- ea: `0x180003380`
- end: `0x180003453`
- name: `DSOpenSharedFile`
- size: `211`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001200`
- `0x180001ae0`
- `0x180001e50`
- `0x180001ed0`
- `0x180002350`
- `0x1800031a8`
- `0x180003380`
- `0x180003b38`

## string_xrefs

- `0x1800033b4`: `DSOpenSharedFile started.`
- `0x180003409`: `DSOpenSharedFile finished.`
- `0x180003435`: `DSOpenSharedFile`

## pseudocode

```c
__int64 __fastcall DSOpenSharedFile(unsigned __int16 *a1, unsigned int a2, unsigned __int64 *a3)
{
  DSLogger *v6; // rax
  int v7; // ebx
  int i; // edi
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  DSLogger *v13; // rax
  DSLogger *v14; // rax
  int v16; // [rsp+20h] [rbp-48h]

  if ( !a1 || !*a1 || !a3 )
  {
    v7 = -2147024809;
LABEL_12:
    v14 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v16 = v7;
    DSLogger::LogError(v14, L"DSOpenSharedFile", 0x1E0u, L"hr=0x%x.", v16);
    return (unsigned int)v7;
  }
  *a3 = -1;
  v6 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogClientApiStarted(v6, L"DSOpenSharedFile started.");
  v7 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( (unsigned int)CheckForRpcRetry(v7) )
    {
      v7 = EnsureDSSvcRunning(v10, v9, v11, v12);
      if ( v7 < 0 )
        break;
    }
    v7 = DSCOpenSharedFile(a1, a2, a3);
    if ( !(unsigned int)CheckForRpcRetry(v7) )
      break;
  }
  if ( v7 < 0 )
    goto LABEL_12;
  v13 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogClientApiCompleted(v13, L"DSOpenSharedFile finished.");
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003380  push    rbx
0x180003382  push    rbp
0x180003383  push    rsi
0x180003384  push    rdi
0x180003385  push    r14
0x180003387  push    r15
0x180003389  sub     rsp, 38h
0x18000338d  xor     r15d, r15d
0x180003390  mov     r14, r8
0x180003393  mov     ebp, edx
0x180003395  mov     rsi, rcx
0x180003398  test    rcx, rcx
0x18000339b  jz      short loc_18000341A
0x18000339d  cmp     [rcx], r15w
0x1800033a1  jz      short loc_18000341A
0x1800033a3  test    r8, r8
0x1800033a6  jz      short loc_18000341A
0x1800033a8  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x1800033af  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800033b4  lea     rdx, aDsopensharedfi_2; "DSOpenSharedFile started."
0x1800033bb  mov     rcx, rax; this
0x1800033be  call    ?LogClientApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogClientApiStarted(ushort const *)
0x1800033c3  mov     ebx, r15d
0x1800033c6  mov     edi, r15d
0x1800033c9  mov     ecx, ebx; int
0x1800033cb  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x1800033d0  test    eax, eax
0x1800033d2  jz      short loc_1800033DF
0x1800033d4  call    ?EnsureDSSvcRunning@@YAJXZ; EnsureDSSvcRunning(void)
0x1800033d9  mov     ebx, eax
0x1800033db  test    eax, eax
0x1800033dd  js      short loc_180003400
0x1800033df  mov     r8, r14; unsigned __int64 *
0x1800033e2  mov     edx, ebp; unsigned int
0x1800033e4  mov     rcx, rsi; unsigned __int16 *
0x1800033e7  call    ?DSCOpenSharedFile@@YAJPEBGKPEA_K@Z; DSCOpenSharedFile(ushort const *,ulong,unsigned __int64 *)
0x1800033ec  mov     ecx, eax; int
0x1800033ee  mov     ebx, eax
0x1800033f0  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x1800033f5  test    eax, eax
0x1800033f7  jz      short loc_180003400
0x1800033f9  inc     edi
0x1800033fb  cmp     edi, 2
0x1800033fe  jl      short loc_1800033C9
0x180003400  test    ebx, ebx
0x180003402  js      short loc_18000341F
0x180003404  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180003409  lea     rdx, aDsopensharedfi_1; "DSOpenSharedFile finished."
0x180003410  mov     rcx, rax; this
0x180003413  call    ?LogClientApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogClientApiCompleted(ushort const *)
0x180003418  jmp     short loc_180003444
0x18000341a  mov     ebx, 80070057h
0x18000341f  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180003424  lea     r9, aHr0xX; "hr=0x%x."
0x18000342b  mov     [rsp+68h+var_48], ebx
0x18000342f  mov     r8d, 1E0h; unsigned int
0x180003435  lea     rdx, aDsopensharedfi_0; "DSOpenSharedFile"
0x18000343c  mov     rcx, rax; this
0x18000343f  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180003444  mov     eax, ebx
0x180003446  add     rsp, 38h
0x18000344a  pop     r15
0x18000344c  pop     r14
0x18000344e  pop     rdi
0x18000344f  pop     rsi
0x180003450  pop     rbp
0x180003451  pop     rbx
0x180003452  retn
```
