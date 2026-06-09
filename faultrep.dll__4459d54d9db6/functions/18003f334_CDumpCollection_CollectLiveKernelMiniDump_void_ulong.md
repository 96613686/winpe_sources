# CDumpCollection::CollectLiveKernelMiniDump(void *,ulong)

- ea: `0x18003f334`
- end: `0x18003f61b`
- name: `?CollectLiveKernelMiniDump@CDumpCollection@@QEAAJPEAXK@Z`
- size: `743`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, HANDLE hFile, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1800086e0`

## callees

- `0x1800028b4`
- `0x1800047cc`
- `0x180009ed8`
- `0x180009f00`
- `0x18003e824`
- `0x18003f334`
- `0x180040584`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003f469`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003f469`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f460`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f4ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f460`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f4ba`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003f486`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003f4c8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003f486`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003f4c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f587`
- `ntdll!RtlNtStatusToDosError` at `0x18003f4d4`
- `ntdll!RtlNtStatusToDosError` at `0x18003f4d4`
- `ntdll!NtSystemDebugControl` at `0x18003f4aa`
- `ntdll!NtSystemDebugControl` at `0x18003f4aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f374`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f5e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f5e4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f57d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f57d`

## pseudocode

```c
__int64 __fastcall CDumpCollection::CollectLiveKernelMiniDump(struct _RTL_CRITICAL_SECTION *this, HANDLE hFile, int a3)
{
  void *v6; // rsi
  int AllThreads; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  HANDLE CurrentThread; // rax
  int ThreadPriority; // edi
  HANDLE v14; // rax
  int v15; // ebx
  HANDLE v16; // rax
  signed int v17; // eax
  DWORD v18; // r8d
  signed int LastError; // eax
  const struct std::nothrow_t *v20; // rdx
  __m128i si128; // [rsp+48h] [rbp-21h] BYREF
  __int64 v23; // [rsp+58h] [rbp-11h]
  _DWORD InputBuffer[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 InputBuffer_8; // [rsp+68h] [rbp-1h]
  __int128 v26; // [rsp+70h] [rbp+7h]
  __int64 v27; // [rsp+80h] [rbp+17h]
  int v28; // [rsp+88h] [rbp+1Fh]
  int v29; // [rsp+8Ch] [rbp+23h]
  __int64 v30; // [rsp+90h] [rbp+27h]
  ULONG nNumberOfBytesToWrite; // [rsp+D0h] [rbp+67h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+E8h] [rbp+7Fh] BYREF

  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v23 = -1;
  v6 = 0;
  EnterCriticalSection(this);
  AllThreads = CDumpCollection::_GetAllThreads((DWORD **)this, si128.m128i_i64);
  v8 = AllThreads;
  if ( AllThreads >= 0 )
  {
    v6 = operator new[](0x100000u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
      v8 = -2147024882;
      goto LABEL_37;
    }
    v26 = 0;
    v27 = 0;
    InputBuffer[0] = 1;
    InputBuffer[1] = a3;
    InputBuffer_8 = 2;
    v28 = 0;
    v29 = (si128.m128i_i64[1] - si128.m128i_i64[0]) >> 3;
    v30 = si128.m128i_i64[0];
    nNumberOfBytesToWrite = 0;
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v14 = GetCurrentThread();
      SetThreadPriority(v14, 0x10000);
    }
    v15 = NtSystemDebugControl(SysDbgGetTriageDump, InputBuffer, 0x38u, v6, 0x100000u, &nNumberOfBytesToWrite);
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v16 = GetCurrentThread();
      SetThreadPriority(v16, 0x20000);
    }
    if ( v15 >= 0 )
    {
      v18 = nNumberOfBytesToWrite;
      if ( nNumberOfBytesToWrite > 0x100000 )
      {
        v8 = -2147024785;
        goto LABEL_37;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids,
          nNumberOfBytesToWrite);
        v18 = nNumberOfBytesToWrite;
      }
      NumberOfBytesWritten = 0;
      if ( WriteFile(hFile, v6, v18, &NumberOfBytesWritten, 0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
        v8 = 0;
        goto LABEL_37;
      }
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v10 = 67;
    }
    else
    {
      v17 = RtlNtStatusToDosError(v15);
      v8 = v17;
      if ( v17 > 0 )
        v8 = (unsigned __int16)v17 | 0x80070000;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v10 = 65;
    }
    v11 = v8;
    goto LABEL_5;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 63;
    v11 = (unsigned int)AllThreads;
LABEL_5:
    WPP_SF_d(v9[2], v10, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v11);
  }
LABEL_37:
  LeaveCriticalSection(this);
  if ( v6 )
    operator delete(v6, v20);
  utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(&si128);
  return v8;
}

```

## disassembly

```asm
0x18003f334  mov     [rsp-8+arg_8], rbx
0x18003f339  push    rbp
0x18003f33a  push    rsi
0x18003f33b  push    rdi
0x18003f33c  push    r14
0x18003f33e  push    r15
0x18003f340  lea     rbp, [rsp-37h]
0x18003f345  sub     rsp, 0A0h
0x18003f34c  mov     edi, r8d
0x18003f34f  mov     r15, rdx
0x18003f352  mov     r14, rcx
0x18003f355  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003f35d  movdqu  [rbp+57h+var_78], xmm0
0x18003f362  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFFh
0x18003f36a  xor     esi, esi
0x18003f36c  mov     [rbp+57h+var_90], rsi
0x18003f370  mov     [rbp+57h+var_88], rcx
0x18003f374  call    cs:__imp_EnterCriticalSection
0x18003f37a  mov     [rbp+57h+var_80], 1
0x18003f37e  lea     rdx, [rbp+57h+var_78]
0x18003f382  mov     rcx, r14; this
0x18003f385  call    ?_GetAllThreads@CDumpCollection@@AEAAJAEAV?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@K@Z; CDumpCollection::_GetAllThreads(utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>> &,ulong)
0x18003f38a  mov     ebx, eax
0x18003f38c  test    eax, eax
0x18003f38e  jns     short loc_18003F3CC
0x18003f390  lea     rdi, WPP_GLOBAL_Control
0x18003f397  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f39e  cmp     rcx, rdi
0x18003f3a1  jz      loc_18003F5E1
0x18003f3a7  test    byte ptr [rcx+1Ch], 1
0x18003f3ab  jz      loc_18003F5E1
0x18003f3b1  lea     edx, [rsi+3Fh]
0x18003f3b4  mov     r9d, eax
0x18003f3b7  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003f3be  mov     rcx, [rcx+10h]
0x18003f3c2  call    WPP_SF_d
0x18003f3c7  jmp     loc_18003F5E1
0x18003f3cc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003f3d3  mov     ebx, 100000h
0x18003f3d8  mov     ecx, ebx; unsigned __int64
0x18003f3da  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003f3df  mov     rsi, rax
0x18003f3e2  test    rax, rax
0x18003f3e5  jnz     short loc_18003F41D
0x18003f3e7  lea     rdi, WPP_GLOBAL_Control
0x18003f3ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3f5  cmp     rcx, rdi
0x18003f3f8  jz      short loc_18003F413
0x18003f3fa  test    byte ptr [rcx+1Ch], 1
0x18003f3fe  jz      short loc_18003F413
0x18003f400  lea     edx, [rax+40h]
0x18003f403  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003f40a  mov     rcx, [rcx+10h]
0x18003f40e  call    WPP_SF_
0x18003f413  mov     ebx, 8007000Eh
0x18003f418  jmp     loc_18003F5E1
0x18003f41d  xorps   xmm0, xmm0
0x18003f420  xor     eax, eax
0x18003f422  movups  [rbp+57h+InputBuffer], xmm0
0x18003f426  movups  [rbp+57h+var_50], xmm0
0x18003f42a  movups  [rbp+57h+var_40], xmm0
0x18003f42e  mov     dword ptr [rbp+57h+InputBuffer], 1
0x18003f435  mov     dword ptr [rbp+57h+InputBuffer+4], edi
0x18003f438  mov     qword ptr [rbp+57h+InputBuffer+8], 2
0x18003f440  mov     dword ptr [rbp+57h+var_40+8], eax
0x18003f443  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x18003f447  mov     rax, qword ptr [rbp+57h+var_78]
0x18003f44b  sub     rcx, rax
0x18003f44e  sar     rcx, 3
0x18003f452  mov     dword ptr [rbp+57h+var_40+0Ch], ecx
0x18003f455  mov     [rbp+57h+var_30], rax
0x18003f459  mov     [rbp+57h+nNumberOfBytesToWrite], 0
0x18003f460  call    cs:__imp_GetCurrentThread
0x18003f466  mov     rcx, rax; hThread
0x18003f469  call    cs:__imp_GetThreadPriority
0x18003f46f  mov     edi, eax
0x18003f471  cmp     eax, 7FFFFFFFh
0x18003f476  jz      short loc_18003F48C
0x18003f478  call    cs:__imp_GetCurrentThread
0x18003f47e  mov     rcx, rax; hThread
0x18003f481  mov     edx, 10000h; nPriority
0x18003f486  call    cs:__imp_SetThreadPriority
0x18003f48c  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x18003f490  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18003f495  mov     [rsp+0C0h+OutputBufferLength], ebx; OutputBufferLength
0x18003f499  mov     r9, rsi; OutputBuffer
0x18003f49c  mov     r8d, 38h ; '8'; InputBufferLength
0x18003f4a2  lea     rdx, [rbp+57h+InputBuffer]; InputBuffer
0x18003f4a6  lea     ecx, [r8-1Bh]; ControlCode
0x18003f4aa  call    cs:__imp_NtSystemDebugControl
0x18003f4b0  mov     ebx, eax
0x18003f4b2  cmp     edi, 7FFFFFFFh
0x18003f4b8  jz      short loc_18003F4CE
0x18003f4ba  call    cs:__imp_GetCurrentThread
0x18003f4c0  mov     rcx, rax; hThread
0x18003f4c3  mov     edx, 20000h; nPriority
0x18003f4c8  call    cs:__imp_SetThreadPriority
0x18003f4ce  test    ebx, ebx
0x18003f4d0  jns     short loc_18003F517
0x18003f4d2  mov     ecx, ebx; Status
0x18003f4d4  call    cs:__imp_RtlNtStatusToDosError
0x18003f4da  mov     ebx, eax
0x18003f4dc  test    eax, eax
0x18003f4de  jle     short loc_18003F4E9
0x18003f4e0  movzx   ebx, ax
0x18003f4e3  or      ebx, 80070000h
0x18003f4e9  lea     rdi, WPP_GLOBAL_Control
0x18003f4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f4f7  cmp     rcx, rdi
0x18003f4fa  jz      loc_18003F5E1
0x18003f500  test    byte ptr [rcx+1Ch], 1
0x18003f504  jz      loc_18003F5E1
0x18003f50a  mov     edx, 41h ; 'A'
0x18003f50f  mov     r9d, ebx
0x18003f512  jmp     loc_18003F3B7
0x18003f517  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]
0x18003f51b  cmp     r8d, 100000h
0x18003f522  jbe     short loc_18003F52E
0x18003f524  mov     ebx, 8007006Fh
0x18003f529  jmp     loc_18003F5E1
0x18003f52e  lea     rdi, WPP_GLOBAL_Control
0x18003f535  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f53c  cmp     rcx, rdi
0x18003f53f  jz      short loc_18003F563
0x18003f541  test    byte ptr [rcx+1Ch], 4
0x18003f545  jz      short loc_18003F563
0x18003f547  mov     edx, 42h ; 'B'
0x18003f54c  mov     r9d, r8d
0x18003f54f  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003f556  mov     rcx, [rcx+10h]
0x18003f55a  call    WPP_SF_d
0x18003f55f  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18003f563  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18003f56a  mov     qword ptr [rsp+0C0h+OutputBufferLength], 0; lpOverlapped
0x18003f573  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003f577  mov     rdx, rsi; lpBuffer
0x18003f57a  mov     rcx, r15; hFile
0x18003f57d  call    cs:__imp_WriteFile
0x18003f583  test    eax, eax
0x18003f585  jnz     short loc_18003F5B8
0x18003f587  call    cs:__imp_GetLastError
0x18003f58d  mov     ebx, eax
0x18003f58f  test    eax, eax
0x18003f591  jle     short loc_18003F59C
0x18003f593  movzx   ebx, ax
0x18003f596  or      ebx, 80070000h
0x18003f59c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f5a3  cmp     rcx, rdi
0x18003f5a6  jz      short loc_18003F5E1
0x18003f5a8  test    byte ptr [rcx+1Ch], 1
0x18003f5ac  jz      short loc_18003F5E1
0x18003f5ae  mov     edx, 43h ; 'C'
0x18003f5b3  jmp     loc_18003F50F
0x18003f5b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f5bf  cmp     rcx, rdi
0x18003f5c2  jz      short loc_18003F5DF
0x18003f5c4  test    byte ptr [rcx+1Ch], 4
0x18003f5c8  jz      short loc_18003F5DF
0x18003f5ca  mov     edx, 44h ; 'D'
0x18003f5cf  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003f5d6  mov     rcx, [rcx+10h]
0x18003f5da  call    WPP_SF_
0x18003f5df  xor     ebx, ebx
0x18003f5e1  mov     rcx, r14; lpCriticalSection
0x18003f5e4  call    cs:__imp_LeaveCriticalSection
0x18003f5ea  nop
0x18003f5eb  test    rsi, rsi
0x18003f5ee  jz      short loc_18003F5F9
0x18003f5f0  mov     rcx, rsi; void *
0x18003f5f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003f5f8  nop
0x18003f5f9  lea     rcx, [rbp+57h+var_78]
0x18003f5fd  call    ??1?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(void)
0x18003f602  mov     eax, ebx
0x18003f604  mov     rbx, [rsp+0C0h+arg_8]
0x18003f60c  add     rsp, 0A0h
0x18003f613  pop     r15
0x18003f615  pop     r14
0x18003f617  pop     rdi
0x18003f618  pop     rsi
0x18003f619  pop     rbp
0x18003f61a  retn
```
