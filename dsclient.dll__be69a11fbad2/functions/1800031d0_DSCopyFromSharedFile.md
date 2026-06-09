# DSCopyFromSharedFile

- ea: `0x1800031d0`
- end: `0x18000329a`
- name: `DSCopyFromSharedFile`
- size: `202`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
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
- `0x1800031d0`
- `0x1800039c0`

## string_xrefs

- `0x1800031ff`: `DSCopyFromSharedFile started.`
- `0x180003252`: `DSCopyFromSharedFile finished.`
- `0x18000327e`: `DSCopyFromSharedFile`

## pseudocode

```c
__int64 __fastcall DSCopyFromSharedFile(unsigned __int16 *a1, unsigned __int16 *a2)
{
  DSLogger *v4; // rax
  int v5; // ebx
  int i; // esi
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  DSLogger *v11; // rax
  DSLogger *v12; // rax
  int v14; // [rsp+20h] [rbp-38h]

  if ( !a1 || !*a1 || !a2 || !*a2 )
  {
    v5 = -2147024809;
LABEL_13:
    v12 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v14 = v5;
    DSLogger::LogError(v12, L"DSCopyFromSharedFile", 0x1FAu, L"hr=0x%x.", v14);
    return (unsigned int)v5;
  }
  v4 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogClientApiStarted(v4, L"DSCopyFromSharedFile started.");
  v5 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( (unsigned int)CheckForRpcRetry(v5) )
    {
      v5 = EnsureDSSvcRunning(v8, v7, v9, v10);
      if ( v5 < 0 )
        break;
    }
    v5 = DSCCopyFromSharedFile(a1, a2);
    if ( !(unsigned int)CheckForRpcRetry(v5) )
      break;
  }
  if ( v5 < 0 )
    goto LABEL_13;
  v11 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogClientApiCompleted(v11, L"DSCopyFromSharedFile finished.");
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800031d0  push    rbx
0x1800031d2  push    rbp
0x1800031d3  push    rsi
0x1800031d4  push    rdi
0x1800031d5  push    r14
0x1800031d7  sub     rsp, 30h
0x1800031db  xor     r14d, r14d
0x1800031de  mov     rdi, rdx
0x1800031e1  mov     rbp, rcx
0x1800031e4  test    rcx, rcx
0x1800031e7  jz      short loc_180003263
0x1800031e9  cmp     [rcx], r14w
0x1800031ed  jz      short loc_180003263
0x1800031ef  test    rdx, rdx
0x1800031f2  jz      short loc_180003263
0x1800031f4  cmp     [rdx], r14w
0x1800031f8  jz      short loc_180003263
0x1800031fa  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800031ff  lea     rdx, aDscopyfromshar_1; "DSCopyFromSharedFile started."
0x180003206  mov     rcx, rax; this
0x180003209  call    ?LogClientApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogClientApiStarted(ushort const *)
0x18000320e  mov     ebx, r14d
0x180003211  mov     esi, r14d
0x180003214  mov     ecx, ebx; int
0x180003216  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x18000321b  test    eax, eax
0x18000321d  jz      short loc_18000322A
0x18000321f  call    ?EnsureDSSvcRunning@@YAJXZ; EnsureDSSvcRunning(void)
0x180003224  mov     ebx, eax
0x180003226  test    eax, eax
0x180003228  js      short loc_180003249
0x18000322a  mov     rdx, rdi; unsigned __int16 *
0x18000322d  mov     rcx, rbp; unsigned __int16 *
0x180003230  call    ?DSCCopyFromSharedFile@@YAJPEBG0@Z; DSCCopyFromSharedFile(ushort const *,ushort const *)
0x180003235  mov     ecx, eax; int
0x180003237  mov     ebx, eax
0x180003239  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x18000323e  test    eax, eax
0x180003240  jz      short loc_180003249
0x180003242  inc     esi
0x180003244  cmp     esi, 2
0x180003247  jl      short loc_180003214
0x180003249  test    ebx, ebx
0x18000324b  js      short loc_180003268
0x18000324d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180003252  lea     rdx, aDscopyfromshar_2; "DSCopyFromSharedFile finished."
0x180003259  mov     rcx, rax; this
0x18000325c  call    ?LogClientApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogClientApiCompleted(ushort const *)
0x180003261  jmp     short loc_18000328D
0x180003263  mov     ebx, 80070057h
0x180003268  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000326d  lea     r9, aHr0xX; "hr=0x%x."
0x180003274  mov     [rsp+58h+var_38], ebx
0x180003278  mov     r8d, 1FAh; unsigned int
0x18000327e  lea     rdx, aDscopyfromshar_0; "DSCopyFromSharedFile"
0x180003285  mov     rcx, rax; this
0x180003288  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000328d  mov     eax, ebx
0x18000328f  add     rsp, 30h
0x180003293  pop     r14
0x180003295  pop     rdi
0x180003296  pop     rsi
0x180003297  pop     rbp
0x180003298  pop     rbx
0x180003299  retn
```
