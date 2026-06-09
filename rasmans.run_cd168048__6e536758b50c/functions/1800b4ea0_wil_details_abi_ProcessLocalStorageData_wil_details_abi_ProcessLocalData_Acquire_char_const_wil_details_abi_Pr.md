# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800b4ea0`
- end: `0x1800b5245`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800b7cf0`

## callees

- `0x18000eb54`
- `0x1800b4c3c`
- `0x1800b4ea0`
- `0x1800b65c4`
- `0x1800b6ab8`
- `0x1800b7a70`
- `0x1800ba9a8`
- `0x1800bc8b0`
- `0x1800bd2cc`
- `0x1800bdbb0`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b4ed9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b4ed9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4fe3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b50eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5193`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4fe3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b50eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5193`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b4f45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b4f45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b4fcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b50d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b5177`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b4fcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b50d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b5177`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800b4f1e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800b4f1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b50ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b50ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5098`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5098`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  _DWORD *v23; // rax
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned __int64 v34; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v42[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v42[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v42, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v42[0]);
  if ( 4 * v42[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v42 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v42, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v42[0];
  v34 = v42[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v42[0] = 0;
  *((_QWORD *)v25 + 3) = v34;
  v42[1] = 0;
  memset_0((char *)v25 + 34, 0, 0x56u);
  *((_WORD *)v25 + 16) = 88;
  v25[9] = 1;
  memset_0(v25 + 10, 0, 0x50u);
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x1800b4ea0  mov     [rsp-8+arg_10], rbx
0x1800b4ea5  push    rbp
0x1800b4ea6  push    rsi
0x1800b4ea7  push    rdi
0x1800b4ea8  push    r14
0x1800b4eaa  push    r15
0x1800b4eac  lea     rbp, [rsp-160h]
0x1800b4eb4  sub     rsp, 260h
0x1800b4ebb  mov     rax, cs:__security_cookie
0x1800b4ec2  xor     rax, rsp
0x1800b4ec5  mov     [rbp+180h+var_30], rax
0x1800b4ecc  mov     r15, rdx
0x1800b4ecf  mov     qword ptr [rdx], 0
0x1800b4ed6  mov     rbx, rcx
0x1800b4ed9  call    cs:__imp_GetCurrentProcessId
0x1800b4ee0  nop     dword ptr [rax+rax+00h]
0x1800b4ee5  mov     r14d, 78h ; 'x'
0x1800b4eeb  mov     [rsp+280h+var_258], rbx
0x1800b4ef0  mov     r9d, eax
0x1800b4ef3  mov     [rsp+280h+var_260], r14d; int
0x1800b4ef8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800b4eff  mov     edx, 104h; unsigned __int64
0x1800b4f04  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800b4f09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b4f0e  mov     r9d, 1F0001h; dwDesiredAccess
0x1800b4f14  lea     rdx, [rsp+280h+Name]; lpName
0x1800b4f19  xor     r8d, r8d; dwFlags
0x1800b4f1c  xor     ecx, ecx; lpMutexAttributes
0x1800b4f1e  call    cs:__imp_CreateMutexExW
0x1800b4f25  nop     dword ptr [rax+rax+00h]
0x1800b4f2a  mov     rbx, rax
0x1800b4f2d  test    rax, rax
0x1800b4f30  jnz     short loc_1800B4F3C
0x1800b4f32  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800b4f37  jmp     loc_1800B51A5
0x1800b4f3c  xor     r8d, r8d; bAlertable
0x1800b4f3f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b4f42  mov     rcx, rbx; hHandle
0x1800b4f45  call    cs:__imp_WaitForSingleObjectEx
0x1800b4f4c  nop     dword ptr [rax+rax+00h]
0x1800b4f51  cmp     eax, 102h
0x1800b4f56  jz      short loc_1800B4F68
0x1800b4f58  test    eax, 0FFFFFF7Fh
0x1800b4f5d  jnz     loc_1800B51F0
0x1800b4f63  mov     rdi, rbx
0x1800b4f66  jmp     short loc_1800B4F6A
0x1800b4f68  xor     edi, edi
0x1800b4f6a  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800b4f6f  mov     [rsp+280h+var_250], 0
0x1800b4f78  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800b4f7d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800b4f82  mov     esi, eax
0x1800b4f84  test    eax, eax
0x1800b4f86  jns     short loc_1800B4FFE
0x1800b4f88  mov     rcx, [rbp+188h]; this
0x1800b4f8f  mov     r9d, eax; char *
0x1800b4f92  mov     edx, 66h ; 'f'; void *
0x1800b4f97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4f9c  mov     rcx, [rbp+188h]; this
0x1800b4fa3  mov     r9d, esi; char *
0x1800b4fa6  mov     edx, 6Fh ; 'o'; void *
0x1800b4fab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4fb0  mov     rcx, [rbp+188h]; this
0x1800b4fb7  mov     r9d, esi; char *
0x1800b4fba  mov     edx, 12Eh; void *
0x1800b4fbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4fc4  test    rdi, rdi
0x1800b4fc7  jz      short loc_1800B4FE0
0x1800b4fc9  mov     rcx, rdi; hMutex
0x1800b4fcc  call    cs:__imp_ReleaseMutex
0x1800b4fd3  nop     dword ptr [rax+rax+00h]
0x1800b4fd8  test    eax, eax
0x1800b4fda  jz      loc_1800B51FD
0x1800b4fe0  mov     rcx, rbx; hObject
0x1800b4fe3  call    cs:__imp_CloseHandle
0x1800b4fea  nop     dword ptr [rax+rax+00h]
0x1800b4fef  test    eax, eax
0x1800b4ff1  jz      loc_1800B520F
0x1800b4ff7  mov     eax, esi
0x1800b4ff9  jmp     loc_1800B51A5
0x1800b4ffe  mov     rax, [rsp+280h+var_250]
0x1800b5003  lea     rcx, ds:0[rax*4]
0x1800b500b  test    rcx, rcx
0x1800b500e  jz      short loc_1800B501E
0x1800b5010  mov     [r15], rcx
0x1800b5013  mov     eax, [rcx]
0x1800b5015  inc     eax
0x1800b5017  mov     [rcx], eax
0x1800b5019  jmp     loc_1800B516F
0x1800b501e  mov     rdx, r14; dwBytes
0x1800b5021  mov     qword ptr [r15], 0
0x1800b5028  mov     ecx, 8; dwFlags
0x1800b502d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800b5032  mov     r14, rax
0x1800b5035  test    rax, rax
0x1800b5038  jnz     short loc_1800B5055
0x1800b503a  mov     rcx, [rbp+188h]; this
0x1800b5041  mov     esi, 8007000Eh
0x1800b5046  mov     r9d, esi; char *
0x1800b5049  mov     edx, 14Bh; void *
0x1800b504e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5053  jmp     short loc_1800B50B8
0x1800b5055  xorps   xmm0, xmm0
0x1800b5058  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800b505d  mov     r8, r14; void *
0x1800b5060  lea     rcx, [rsp+280h+var_250]; this
0x1800b5065  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800b506b  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800b5070  mov     esi, eax
0x1800b5072  test    eax, eax
0x1800b5074  jns     loc_1800B5104
0x1800b507a  mov     rcx, [rbp+188h]; this
0x1800b5081  mov     r9d, eax; char *
0x1800b5084  mov     edx, 14Eh; void *
0x1800b5089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b508e  lea     rcx, [rsp+280h+var_250]; this
0x1800b5093  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800b5098  call    cs:__imp_GetProcessHeap
0x1800b509f  nop     dword ptr [rax+rax+00h]
0x1800b50a4  mov     r8, r14; lpMem
0x1800b50a7  xor     edx, edx; dwFlags
0x1800b50a9  mov     rcx, rax; hHeap
0x1800b50ac  call    cs:__imp_HeapFree
0x1800b50b3  nop     dword ptr [rax+rax+00h]
0x1800b50b8  mov     rcx, [rbp+188h]; this
0x1800b50bf  mov     r9d, esi; char *
0x1800b50c2  mov     edx, 137h; void *
0x1800b50c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b50cc  test    rdi, rdi
0x1800b50cf  jz      short loc_1800B50E8
0x1800b50d1  mov     rcx, rdi; hMutex
0x1800b50d4  call    cs:__imp_ReleaseMutex
0x1800b50db  nop     dword ptr [rax+rax+00h]
0x1800b50e0  test    eax, eax
0x1800b50e2  jz      loc_1800B5221
0x1800b50e8  mov     rcx, rbx; hObject
0x1800b50eb  call    cs:__imp_CloseHandle
0x1800b50f2  nop     dword ptr [rax+rax+00h]
0x1800b50f7  test    eax, eax
0x1800b50f9  jz      loc_1800B51DE
0x1800b50ff  jmp     loc_1800B4FF7
0x1800b5104  mov     rax, [rsp+280h+var_250]
0x1800b5109  lea     rcx, [r14+22h]; void *
0x1800b510d  xor     edx, edx; Val
0x1800b510f  mov     [r14+10h], rax
0x1800b5113  mov     rax, [rsp+280h+var_250+8]
0x1800b5118  mov     dword ptr [r14], 1
0x1800b511f  mov     [r14+8], rbx
0x1800b5123  lea     r8d, [rdx+56h]; Size
0x1800b5127  mov     [rsp+280h+var_250], 0
0x1800b5130  mov     [r14+18h], rax
0x1800b5134  mov     [rsp+280h+var_250+8], 0
0x1800b513d  call    memset_0
0x1800b5142  xor     edx, edx; Val
0x1800b5144  mov     word ptr [r14+20h], 58h ; 'X'
0x1800b514b  lea     rcx, [r14+28h]; void *
0x1800b514f  mov     dword ptr [r14+24h], 1
0x1800b5157  lea     r8d, [rdx+50h]; Size
0x1800b515b  call    memset_0
0x1800b5160  lea     rcx, [rsp+280h+var_250]; this
0x1800b5165  mov     [r15], r14
0x1800b5168  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800b516d  xor     ebx, ebx
0x1800b516f  test    rdi, rdi
0x1800b5172  jz      short loc_1800B518B
0x1800b5174  mov     rcx, rdi; hMutex
0x1800b5177  call    cs:__imp_ReleaseMutex
0x1800b517e  nop     dword ptr [rax+rax+00h]
0x1800b5183  test    eax, eax
0x1800b5185  jz      loc_1800B5233
0x1800b518b  test    rbx, rbx
0x1800b518e  jz      short loc_1800B51A3
0x1800b5190  mov     rcx, rbx; hObject
0x1800b5193  call    cs:__imp_CloseHandle
0x1800b519a  nop     dword ptr [rax+rax+00h]
0x1800b519f  test    eax, eax
0x1800b51a1  jz      short loc_1800B51CC
0x1800b51a3  xor     eax, eax
0x1800b51a5  mov     rcx, [rbp+180h+var_30]
0x1800b51ac  xor     rcx, rsp; StackCookie
0x1800b51af  call    __security_check_cookie
0x1800b51b4  mov     rbx, [rsp+280h+arg_10]
0x1800b51bc  add     rsp, 260h
0x1800b51c3  pop     r15
0x1800b51c5  pop     r14
0x1800b51c7  pop     rdi
0x1800b51c8  pop     rsi
0x1800b51c9  pop     rbp
0x1800b51ca  retn
0x1800b51cc  mov     rcx, [rbp+188h]; this
0x1800b51d3  mov     edx, 0A0Bh; void *
0x1800b51d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b51de  mov     rcx, [rbp+188h]; this
0x1800b51e5  mov     edx, 0A0Bh; void *
0x1800b51ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b51f0  mov     rcx, [rbp+188h]; this
0x1800b51f7  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800b51fd  mov     rcx, [rbp+188h]; this
0x1800b5204  mov     edx, 0A15h; void *
0x1800b5209  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b520f  mov     rcx, [rbp+188h]; this
0x1800b5216  mov     edx, 0A0Bh; void *
0x1800b521b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b5221  mov     rcx, [rbp+188h]; this
0x1800b5228  mov     edx, 0A15h; void *
0x1800b522d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b5233  mov     rcx, [rbp+188h]; this
0x1800b523a  mov     edx, 0A15h; void *
0x1800b523f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
