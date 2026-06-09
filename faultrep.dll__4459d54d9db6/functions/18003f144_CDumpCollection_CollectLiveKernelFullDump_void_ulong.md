# CDumpCollection::CollectLiveKernelFullDump(void *,ulong)

- ea: `0x18003f144`
- end: `0x18003f32b`
- name: `?CollectLiveKernelFullDump@CDumpCollection@@QEAAJPEAXK@Z`
- size: `487`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, void *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800086e0`

## callees

- `0x180003474`
- `0x180009ed8`
- `0x180009f00`
- `0x18003e824`
- `0x18003f144`
- `0x180040584`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003f232`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003f232`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f229`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f245`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f229`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f245`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f285`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003f253`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003f293`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003f253`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003f293`
- `ntdll!RtlNtStatusToDosError` at `0x18003f29f`
- `ntdll!RtlNtStatusToDosError` at `0x18003f29f`
- `ntdll!NtSystemDebugControl` at `0x18003f278`
- `ntdll!NtSystemDebugControl` at `0x18003f278`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f17b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f17b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f30a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f30a`

## pseudocode

```c
__int64 __fastcall CDumpCollection::CollectLiveKernelFullDump(struct _RTL_CRITICAL_SECTION *this, void *a2, int a3)
{
  int AllThreads; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // esi
  HANDLE v11; // rax
  int v12; // ebx
  HANDLE v13; // rax
  signed int v14; // eax
  __m128i si128; // [rsp+30h] [rbp-99h] BYREF
  __int64 v17; // [rsp+40h] [rbp-89h]
  _DWORD InputBuffer[2]; // [rsp+50h] [rbp-79h] BYREF
  __int64 InputBuffer_8; // [rsp+58h] [rbp-71h]
  __int128 v20; // [rsp+60h] [rbp-69h]
  __int64 v21; // [rsp+70h] [rbp-59h]
  void *v22; // [rsp+78h] [rbp-51h]
  __int128 v23; // [rsp+80h] [rbp-49h]
  __int64 v24; // [rsp+90h] [rbp-39h]
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+A0h] [rbp-29h]
  char v26; // [rsp+A8h] [rbp-21h]
  _OWORD v27[2]; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v28; // [rsp+D0h] [rbp+7h]
  __int128 v29; // [rsp+E0h] [rbp+17h]
  __int64 v30; // [rsp+F0h] [rbp+27h]

  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v17 = -1;
  v25 = this;
  EnterCriticalSection(this);
  v26 = 1;
  AllThreads = CDumpCollection::_GetAllThreads((DWORD **)this, si128.m128i_i64);
  if ( AllThreads >= 0 )
  {
    memset_0(v27, 0, 0x48u);
    v20 = v27[1];
    v21 = v28;
    v23 = v29;
    v24 = v30;
    InputBuffer[0] = 1;
    InputBuffer[1] = a3;
    InputBuffer_8 = 2;
    v22 = a2;
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v11 = GetCurrentThread();
      SetThreadPriority(v11, 0x10000);
    }
    v12 = NtSystemDebugControl(SysDbgClearUmAttachPid|SysDbgQueryTraceInformation, InputBuffer, 0x48u, 0, 0, 0);
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v13 = GetCurrentThread();
      SetThreadPriority(v13, 0x20000);
    }
    if ( v12 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
      AllThreads = 0;
    }
    else
    {
      v14 = RtlNtStatusToDosError(v12);
      AllThreads = v14;
      if ( v14 > 0 )
        AllThreads = (unsigned __int16)v14 | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 70;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 69;
LABEL_5:
      WPP_SF_d(v7[2], v8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, (unsigned int)AllThreads);
    }
  }
  LeaveCriticalSection(this);
  utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(&si128);
  return (unsigned int)AllThreads;
}

```

## disassembly

```asm
0x18003f144  push    rbp
0x18003f146  push    rbx
0x18003f147  push    rsi
0x18003f148  push    rdi
0x18003f149  push    r14
0x18003f14b  lea     rbp, [rsp-37h]
0x18003f150  sub     rsp, 100h
0x18003f157  mov     esi, r8d
0x18003f15a  mov     r14, rdx
0x18003f15d  mov     rdi, rcx
0x18003f160  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003f168  movdqu  [rsp+120h+var_F0], xmm0
0x18003f16e  mov     [rsp+120h+var_E0], 0FFFFFFFFFFFFFFFFh
0x18003f177  mov     [rbp+57h+var_80], rcx
0x18003f17b  call    cs:__imp_EnterCriticalSection
0x18003f181  mov     [rbp+57h+var_78], 1
0x18003f185  lea     rdx, [rsp+120h+var_F0]
0x18003f18a  mov     rcx, rdi; this
0x18003f18d  call    ?_GetAllThreads@CDumpCollection@@AEAAJAEAV?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@K@Z; CDumpCollection::_GetAllThreads(utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>> &,ulong)
0x18003f192  mov     ebx, eax
0x18003f194  test    eax, eax
0x18003f196  jns     short loc_18003F1D6
0x18003f198  lea     rax, WPP_GLOBAL_Control
0x18003f19f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f1a6  cmp     rcx, rax
0x18003f1a9  jz      loc_18003F307
0x18003f1af  test    byte ptr [rcx+1Ch], 1
0x18003f1b3  jz      loc_18003F307
0x18003f1b9  mov     edx, 45h ; 'E'
0x18003f1be  mov     r9d, ebx
0x18003f1c1  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003f1c8  mov     rcx, [rcx+10h]
0x18003f1cc  call    WPP_SF_d
0x18003f1d1  jmp     loc_18003F307
0x18003f1d6  mov     ebx, 48h ; 'H'
0x18003f1db  mov     r8d, ebx; Size
0x18003f1de  xor     edx, edx; Val
0x18003f1e0  lea     rcx, [rbp+57h+var_70]; void *
0x18003f1e4  call    memset_0
0x18003f1e9  movups  xmm0, [rbp+57h+var_70]
0x18003f1ed  movaps  [rbp+57h+InputBuffer], xmm0
0x18003f1f1  movups  xmm1, [rbp+57h+var_60]
0x18003f1f5  movaps  [rbp+57h+var_C0], xmm1
0x18003f1f9  movups  xmm0, [rbp+57h+var_50]
0x18003f1fd  movaps  [rbp+57h+var_B0], xmm0
0x18003f201  movups  xmm1, [rbp+57h+var_40]
0x18003f205  movaps  [rbp+57h+var_A0], xmm1
0x18003f209  movsd   xmm0, [rbp+57h+var_30]
0x18003f20e  movsd   [rbp+57h+var_90], xmm0
0x18003f213  mov     dword ptr [rbp+57h+InputBuffer], 1
0x18003f21a  mov     dword ptr [rbp+57h+InputBuffer+4], esi
0x18003f21d  mov     qword ptr [rbp+57h+InputBuffer+8], 2
0x18003f225  mov     qword ptr [rbp+57h+var_B0+8], r14
0x18003f229  call    cs:__imp_GetCurrentThread
0x18003f22f  mov     rcx, rax; hThread
0x18003f232  call    cs:__imp_GetThreadPriority
0x18003f238  mov     esi, eax
0x18003f23a  mov     r14d, 7FFFFFFFh
0x18003f240  cmp     eax, r14d
0x18003f243  jz      short loc_18003F259
0x18003f245  call    cs:__imp_GetCurrentThread
0x18003f24b  mov     rcx, rax; hThread
0x18003f24e  mov     edx, 10000h; nPriority
0x18003f253  call    cs:__imp_SetThreadPriority
0x18003f259  mov     [rsp+120h+ReturnLength], 0; ReturnLength
0x18003f262  mov     [rsp+120h+OutputBufferLength], 0; OutputBufferLength
0x18003f26a  xor     r9d, r9d; OutputBuffer
0x18003f26d  mov     r8d, ebx; InputBufferLength
0x18003f270  lea     rdx, [rbp+57h+InputBuffer]; InputBuffer
0x18003f274  lea     ecx, [r9+25h]; ControlCode
0x18003f278  call    cs:__imp_NtSystemDebugControl
0x18003f27e  mov     ebx, eax
0x18003f280  cmp     esi, r14d
0x18003f283  jz      short loc_18003F299
0x18003f285  call    cs:__imp_GetCurrentThread
0x18003f28b  mov     rcx, rax; hThread
0x18003f28e  mov     edx, 20000h; nPriority
0x18003f293  call    cs:__imp_SetThreadPriority
0x18003f299  test    ebx, ebx
0x18003f29b  jns     short loc_18003F2D7
0x18003f29d  mov     ecx, ebx; Status
0x18003f29f  call    cs:__imp_RtlNtStatusToDosError
0x18003f2a5  mov     ebx, eax
0x18003f2a7  test    eax, eax
0x18003f2a9  jle     short loc_18003F2B4
0x18003f2ab  movzx   ebx, ax
0x18003f2ae  or      ebx, 80070000h
0x18003f2b4  lea     rax, WPP_GLOBAL_Control
0x18003f2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f2c2  cmp     rcx, rax
0x18003f2c5  jz      short loc_18003F307
0x18003f2c7  test    byte ptr [rcx+1Ch], 1
0x18003f2cb  jz      short loc_18003F307
0x18003f2cd  mov     edx, 46h ; 'F'
0x18003f2d2  jmp     loc_18003F1BE
0x18003f2d7  lea     rax, WPP_GLOBAL_Control
0x18003f2de  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f2e5  cmp     rcx, rax
0x18003f2e8  jz      short loc_18003F305
0x18003f2ea  test    byte ptr [rcx+1Ch], 4
0x18003f2ee  jz      short loc_18003F305
0x18003f2f0  mov     edx, 47h ; 'G'
0x18003f2f5  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003f2fc  mov     rcx, [rcx+10h]
0x18003f300  call    WPP_SF_
0x18003f305  xor     ebx, ebx
0x18003f307  mov     rcx, rdi; lpCriticalSection
0x18003f30a  call    cs:__imp_LeaveCriticalSection
0x18003f310  nop
0x18003f311  lea     rcx, [rsp+120h+var_F0]
0x18003f316  call    ??1?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(void)
0x18003f31b  mov     eax, ebx
0x18003f31d  add     rsp, 100h
0x18003f324  pop     r14
0x18003f326  pop     rdi
0x18003f327  pop     rsi
0x18003f328  pop     rbx
0x18003f329  pop     rbp
0x18003f32a  retn
```
