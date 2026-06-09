# TaskScheduler::TaskScheduler(ulong)

- ea: `0x180086d90`
- end: `0x1800870b9`
- name: `??0TaskScheduler@@QEAA@K@Z`
- size: `809`
- prototype: `TaskScheduler *__fastcall(TaskScheduler *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008f1ec`

## callees

- `0x180086d90`
- `0x18008f6f4`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180086e01`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180086e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086ee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086f5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086ee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086f5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087048`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180086e60`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180086fc2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180086e60`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180086fc2`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180086ed8`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180086ed8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180086f4d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180086f4d`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180087039`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180087039`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
TaskScheduler *__fastcall TaskScheduler::TaskScheduler(TaskScheduler *this)
{
  _QWORD *v2; // rcx
  DWORD v3; // eax
  signed int LastError; // eax
  unsigned int v5; // ecx
  HANDLE MutexW; // rax
  signed int v7; // eax
  unsigned int v8; // ecx
  HANDLE WaitableTimer; // rax
  signed int v10; // eax
  unsigned int v11; // ecx
  HANDLE EventW; // rax
  signed int v13; // eax
  unsigned int v14; // ecx
  HANDLE v15; // rax
  signed int v16; // eax
  unsigned int v17; // ecx
  HANDLE SemaphoreW; // rax
  signed int v19; // eax
  unsigned int v20; // ecx
  void **pExceptionObject; // [rsp+30h] [rbp-2A8h] BYREF
  __int128 v24; // [rsp+38h] [rbp-2A0h]
  unsigned int v25; // [rsp+48h] [rbp-290h]
  int v26; // [rsp+4Ch] [rbp-28Ch]
  int v27; // [rsp+50h] [rbp-288h]
  void **v28; // [rsp+90h] [rbp-248h] BYREF
  __int128 v29; // [rsp+98h] [rbp-240h]
  unsigned int v30; // [rsp+A8h] [rbp-230h]
  int v31; // [rsp+ACh] [rbp-22Ch]
  int v32; // [rsp+B0h] [rbp-228h]
  void **v33; // [rsp+F0h] [rbp-1E8h] BYREF
  __int128 v34; // [rsp+F8h] [rbp-1E0h]
  unsigned int v35; // [rsp+108h] [rbp-1D0h]
  int v36; // [rsp+10Ch] [rbp-1CCh]
  int v37; // [rsp+110h] [rbp-1C8h]
  void **v38; // [rsp+150h] [rbp-188h] BYREF
  __int128 v39; // [rsp+158h] [rbp-180h]
  unsigned int v40; // [rsp+168h] [rbp-170h]
  int v41; // [rsp+16Ch] [rbp-16Ch]
  int v42; // [rsp+170h] [rbp-168h]
  void **v43; // [rsp+1B0h] [rbp-128h] BYREF
  __int128 v44; // [rsp+1B8h] [rbp-120h]
  unsigned int v45; // [rsp+1C8h] [rbp-110h]
  int v46; // [rsp+1CCh] [rbp-10Ch]
  int v47; // [rsp+1D0h] [rbp-108h]
  void **v48; // [rsp+210h] [rbp-C8h] BYREF
  __int128 v49; // [rsp+218h] [rbp-C0h]
  unsigned int v50; // [rsp+228h] [rbp-B0h]
  int v51; // [rsp+22Ch] [rbp-ACh]
  int v52; // [rsp+230h] [rbp-A8h]
  __int64 v53; // [rsp+270h] [rbp-68h] BYREF

  *(_QWORD *)this = &TaskScheduler::`vftable';
  *((_BYTE *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 13) = -1;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = (char *)this + 64;
  *((_QWORD *)this + 9) = (char *)this + 64;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 10) = (char *)this + 64;
  v2 = (_QWORD *)((char *)this + 104);
  *v2 = 0;
  v2[1] = 0;
  std::_Tree<std::_Tmap_traits<SidHandle,unsigned long,CSidSorter,std::allocator<std::pair<SidHandle const,unsigned long>>,0>>::_Alloc_sentinel_and_proxy();
  *((_DWORD *)this + 30) = 4;
  *((_QWORD *)this + 16) = 0;
  v3 = TlsAlloc();
  try
  {
    *((_DWORD *)this + 13) = v3;
    if ( v3 == -1 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v24 = 0;
      pExceptionObject = &ComError::`vftable';
      v25 = v5;
      v26 = 0;
      v27 = 1;
      throw (ComError *)&pExceptionObject;
    }
    MutexW = CreateMutexW(0, 0, 0);
    *((_QWORD *)this + 2) = MutexW;
    if ( !MutexW )
    {
      v7 = GetLastError();
      v8 = v7;
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      v29 = 0;
      v28 = &ComError::`vftable';
      v30 = v8;
      v31 = 0;
      v32 = 1;
      throw (ComError *)&v28;
    }
    WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)this + 3) = WaitableTimer;
    if ( !WaitableTimer )
    {
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      v34 = 0;
      v33 = &ComError::`vftable';
      v35 = v11;
      v36 = 0;
      v37 = 1;
      throw (ComError *)&v33;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 16) = EventW;
    if ( !EventW )
    {
      v13 = GetLastError();
      v14 = v13;
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
      v39 = 0;
      v38 = &ComError::`vftable';
      v40 = v14;
      v41 = 0;
      v42 = 1;
      throw (ComError *)&v38;
    }
    v15 = CreateMutexW(0, 0, 0);
    *((_QWORD *)this + 4) = v15;
    if ( !v15 )
    {
      v16 = GetLastError();
      v17 = v16;
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      v44 = 0;
      v43 = &ComError::`vftable';
      v45 = v17;
      v46 = 0;
      v47 = 1;
      throw (ComError *)&v43;
    }
    SemaphoreW = CreateSemaphoreW(0, 1, 1, 0);
    *((_QWORD *)this + 5) = SemaphoreW;
    if ( !SemaphoreW )
    {
      v19 = GetLastError();
      v20 = v19;
      if ( v19 > 0 )
        v20 = (unsigned __int16)v19 | 0x80070000;
      v49 = 0;
      v48 = &ComError::`vftable';
      v50 = v20;
      v51 = 0;
      v52 = 1;
      throw (ComError *)&v48;
    }
  }
  catch ( ComError v53 )
  {
    TaskScheduler::Cleanup(this);
    throw;
  }
  return this;
}

```

## disassembly

```asm
0x180086d90  mov     [rsp+arg_8], rbx
0x180086d95  push    rdi
0x180086d96  sub     rsp, 2D0h
0x180086d9d  mov     rbx, rcx
0x180086da0  mov     [rsp+2D8h+var_2B8], rcx
0x180086da5  lea     rax, ??_7TaskScheduler@@6B@; const TaskScheduler::`vftable'
0x180086dac  mov     [rcx], rax
0x180086daf  xor     edi, edi
0x180086db1  mov     [rcx+8], dil
0x180086db5  mov     [rcx+18h], rdi
0x180086db9  mov     [rcx+20h], rdi
0x180086dbd  mov     [rcx+28h], rdi
0x180086dc1  mov     [rcx+30h], edi
0x180086dc4  mov     dword ptr [rcx+34h], 0FFFFFFFFh
0x180086dcb  mov     [rcx+38h], rdi
0x180086dcf  lea     rax, [rcx+40h]
0x180086dd3  mov     [rax], rax
0x180086dd6  mov     [rax+8], rax
0x180086dda  mov     [rax+18h], rdi
0x180086dde  mov     [rax+10h], rax
0x180086de2  add     rcx, 68h ; 'h'
0x180086de6  mov     [rcx], rdi
0x180086de9  mov     [rcx+8], rdi
0x180086ded  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@VSidHandle@@KVCSidSorter@@V?$allocator@U?$pair@$$CBVSidHandle@@K@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<SidHandle,ulong,CSidSorter,std::allocator<std::pair<SidHandle const,ulong>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180086df2  nop
0x180086df3  mov     dword ptr [rbx+78h], 4
0x180086dfa  mov     [rbx+80h], rdi
0x180086e01  call    cs:__imp_TlsAlloc
0x180086e07  mov     [rbx+34h], eax
0x180086e0a  cmp     eax, 0FFFFFFFFh
0x180086e0d  jnz     short loc_180086E59
0x180086e0f  call    cs:__imp_GetLastError
0x180086e15  mov     ecx, eax
0x180086e17  test    eax, eax
0x180086e19  jle     short loc_180086E24
0x180086e1b  movzx   ecx, ax
0x180086e1e  or      ecx, 80070000h
0x180086e24  xorps   xmm0, xmm0
0x180086e27  movups  [rsp+2D8h+var_2A0], xmm0
0x180086e2c  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180086e33  mov     [rsp+2D8h+pExceptionObject], rax
0x180086e38  mov     [rsp+2D8h+var_290], ecx
0x180086e3c  mov     [rsp+2D8h+var_28C], edi
0x180086e40  mov     [rsp+2D8h+var_288], 1
0x180086e48  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180086e4f  lea     rcx, [rsp+2D8h+pExceptionObject]; pExceptionObject
0x180086e54  call    _CxxThrowException_0
0x180086e59  xor     r8d, r8d; lpName
0x180086e5c  xor     edx, edx; bInitialOwner
0x180086e5e  xor     ecx, ecx; lpMutexAttributes
0x180086e60  call    cs:__imp_CreateMutexW
0x180086e66  mov     [rbx+10h], rax
0x180086e6a  test    rax, rax
0x180086e6d  jnz     short loc_180086ECB
0x180086e6f  call    cs:__imp_GetLastError
0x180086e75  mov     ecx, eax
0x180086e77  test    eax, eax
0x180086e79  jle     short loc_180086E84
0x180086e7b  movzx   ecx, ax
0x180086e7e  or      ecx, 80070000h
0x180086e84  xorps   xmm0, xmm0
0x180086e87  movups  [rsp+2D8h+var_240], xmm0
0x180086e8f  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180086e96  mov     [rsp+2D8h+var_248], rax
0x180086e9e  mov     [rsp+2D8h+var_230], ecx
0x180086ea5  mov     [rsp+2D8h+var_22C], edi
0x180086eac  mov     [rsp+2D8h+var_228], 1
0x180086eb7  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180086ebe  lea     rcx, [rsp+2D8h+var_248]; pExceptionObject
0x180086ec6  call    _CxxThrowException_0
0x180086ecb  mov     r9d, 1F0003h; dwDesiredAccess
0x180086ed1  xor     r8d, r8d; dwFlags
0x180086ed4  xor     edx, edx; lpTimerName
0x180086ed6  xor     ecx, ecx; lpTimerAttributes
0x180086ed8  call    cs:__imp_CreateWaitableTimerExW
0x180086ede  mov     [rbx+18h], rax
0x180086ee2  test    rax, rax
0x180086ee5  jnz     short loc_180086F43
0x180086ee7  call    cs:__imp_GetLastError
0x180086eed  mov     ecx, eax
0x180086eef  test    eax, eax
0x180086ef1  jle     short loc_180086EFC
0x180086ef3  movzx   ecx, ax
0x180086ef6  or      ecx, 80070000h
0x180086efc  xorps   xmm0, xmm0
0x180086eff  movups  [rsp+2D8h+var_1E0], xmm0
0x180086f07  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180086f0e  mov     [rsp+2D8h+var_1E8], rax
0x180086f16  mov     [rsp+2D8h+var_1D0], ecx
0x180086f1d  mov     [rsp+2D8h+var_1CC], edi
0x180086f24  mov     [rsp+2D8h+var_1C8], 1
0x180086f2f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180086f36  lea     rcx, [rsp+2D8h+var_1E8]; pExceptionObject
0x180086f3e  call    _CxxThrowException_0
0x180086f43  xor     r9d, r9d; lpName
0x180086f46  xor     r8d, r8d; bInitialState
0x180086f49  xor     edx, edx; bManualReset
0x180086f4b  xor     ecx, ecx; lpEventAttributes
0x180086f4d  call    cs:__imp_CreateEventW
0x180086f53  mov     [rbx+80h], rax
0x180086f5a  test    rax, rax
0x180086f5d  jnz     short loc_180086FBB
0x180086f5f  call    cs:__imp_GetLastError
0x180086f65  mov     ecx, eax
0x180086f67  test    eax, eax
0x180086f69  jle     short loc_180086F74
0x180086f6b  movzx   ecx, ax
0x180086f6e  or      ecx, 80070000h
0x180086f74  xorps   xmm0, xmm0
0x180086f77  movups  [rsp+2D8h+var_180], xmm0
0x180086f7f  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180086f86  mov     [rsp+2D8h+var_188], rax
0x180086f8e  mov     [rsp+2D8h+var_170], ecx
0x180086f95  mov     [rsp+2D8h+var_16C], edi
0x180086f9c  mov     [rsp+2D8h+var_168], 1
0x180086fa7  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180086fae  lea     rcx, [rsp+2D8h+var_188]; pExceptionObject
0x180086fb6  call    _CxxThrowException_0
0x180086fbb  xor     r8d, r8d; lpName
0x180086fbe  xor     edx, edx; bInitialOwner
0x180086fc0  xor     ecx, ecx; lpMutexAttributes
0x180086fc2  call    cs:__imp_CreateMutexW
0x180086fc8  mov     [rbx+20h], rax
0x180086fcc  test    rax, rax
0x180086fcf  jnz     short loc_18008702D
0x180086fd1  call    cs:__imp_GetLastError
0x180086fd7  mov     ecx, eax
0x180086fd9  test    eax, eax
0x180086fdb  jle     short loc_180086FE6
0x180086fdd  movzx   ecx, ax
0x180086fe0  or      ecx, 80070000h
0x180086fe6  xorps   xmm0, xmm0
0x180086fe9  movups  [rsp+2D8h+var_120], xmm0
0x180086ff1  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180086ff8  mov     [rsp+2D8h+var_128], rax
0x180087000  mov     [rsp+2D8h+var_110], ecx
0x180087007  mov     [rsp+2D8h+var_10C], edi
0x18008700e  mov     [rsp+2D8h+var_108], 1
0x180087019  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180087020  lea     rcx, [rsp+2D8h+var_128]; pExceptionObject
0x180087028  call    _CxxThrowException_0
0x18008702d  xor     r9d, r9d; lpName
0x180087030  lea     edx, [r9+1]; lInitialCount
0x180087034  xor     ecx, ecx; lpSemaphoreAttributes
0x180087036  mov     r8d, edx; lMaximumCount
0x180087039  call    cs:__imp_CreateSemaphoreW
0x18008703f  mov     [rbx+28h], rax
0x180087043  test    rax, rax
0x180087046  jnz     short loc_1800870A5
0x180087048  call    cs:__imp_GetLastError
0x18008704e  mov     ecx, eax
0x180087050  test    eax, eax
0x180087052  jle     short loc_18008705D
0x180087054  movzx   ecx, ax
0x180087057  or      ecx, 80070000h
0x18008705d  xorps   xmm0, xmm0
0x180087060  movups  [rsp+2D8h+var_C0], xmm0
0x180087068  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008706f  mov     [rsp+2D8h+var_C8], rax
0x180087077  mov     [rsp+2D8h+var_B0], ecx
0x18008707e  mov     [rsp+2D8h+var_AC], edi
0x180087085  mov     [rsp+2D8h+var_A8], 1
0x180087090  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180087097  lea     rcx, [rsp+2D8h+var_C8]; pExceptionObject
0x18008709f  call    _CxxThrowException_0
0x1800870a5  mov     rax, rbx
0x1800870a8  mov     rbx, [rsp+2D8h+arg_8]
0x1800870b0  add     rsp, 2D0h
0x1800870b7  pop     rdi
0x1800870b8  retn
```
