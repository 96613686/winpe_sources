# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003d74`
- end: `0x140004119`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400054c4`

## callees

- `0x140002463`
- `0x140003a18`
- `0x140003d74`
- `0x140004520`
- `0x1400049a4`
- `0x140005240`
- `0x140006068`
- `0x1400076e4`
- `0x1400080fc`
- `0x14000865c`
- `0x140009040`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003f80`
- `KERNEL32!HeapFree` at `0x140003f80`
- `KERNEL32!GetProcessHeap` at `0x140003f6c`
- `KERNEL32!GetProcessHeap` at `0x140003f6c`
- `KERNEL32!GetCurrentProcessId` at `0x140003dad`
- `KERNEL32!GetCurrentProcessId` at `0x140003dad`
- `KERNEL32!CreateMutexExW` at `0x140003df2`
- `KERNEL32!CreateMutexExW` at `0x140003df2`
- `KERNEL32!CloseHandle` at `0x140003eb7`
- `KERNEL32!CloseHandle` at `0x140003fbf`
- `KERNEL32!CloseHandle` at `0x140004067`
- `KERNEL32!CloseHandle` at `0x140003eb7`
- `KERNEL32!CloseHandle` at `0x140003fbf`
- `KERNEL32!CloseHandle` at `0x140004067`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003e19`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003e19`
- `KERNEL32!ReleaseMutex` at `0x140003ea0`
- `KERNEL32!ReleaseMutex` at `0x140003fa8`
- `KERNEL32!ReleaseMutex` at `0x14000404b`
- `KERNEL32!ReleaseMutex` at `0x140003ea0`
- `KERNEL32!ReleaseMutex` at `0x140003fa8`
- `KERNEL32!ReleaseMutex` at `0x14000404b`

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
0x140003d74  mov     [rsp-8+arg_10], rbx
0x140003d79  push    rbp
0x140003d7a  push    rsi
0x140003d7b  push    rdi
0x140003d7c  push    r14
0x140003d7e  push    r15
0x140003d80  lea     rbp, [rsp-160h]
0x140003d88  sub     rsp, 260h
0x140003d8f  mov     rax, cs:__security_cookie
0x140003d96  xor     rax, rsp
0x140003d99  mov     [rbp+180h+var_30], rax
0x140003da0  mov     r15, rdx
0x140003da3  mov     qword ptr [rdx], 0
0x140003daa  mov     rbx, rcx
0x140003dad  call    cs:__imp_GetCurrentProcessId
0x140003db4  nop     dword ptr [rax+rax+00h]
0x140003db9  mov     r14d, 78h ; 'x'
0x140003dbf  mov     [rsp+280h+var_258], rbx
0x140003dc4  mov     r9d, eax
0x140003dc7  mov     [rsp+280h+var_260], r14d; int
0x140003dcc  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003dd3  mov     edx, 104h; unsigned __int64
0x140003dd8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003ddd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003de2  mov     r9d, 1F0001h; dwDesiredAccess
0x140003de8  lea     rdx, [rsp+280h+Name]; lpName
0x140003ded  xor     r8d, r8d; dwFlags
0x140003df0  xor     ecx, ecx; lpMutexAttributes
0x140003df2  call    cs:__imp_CreateMutexExW
0x140003df9  nop     dword ptr [rax+rax+00h]
0x140003dfe  mov     rbx, rax
0x140003e01  test    rax, rax
0x140003e04  jnz     short loc_140003E10
0x140003e06  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003e0b  jmp     loc_140004079
0x140003e10  xor     r8d, r8d; bAlertable
0x140003e13  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003e16  mov     rcx, rbx; hHandle
0x140003e19  call    cs:__imp_WaitForSingleObjectEx
0x140003e20  nop     dword ptr [rax+rax+00h]
0x140003e25  cmp     eax, 102h
0x140003e2a  jz      short loc_140003E3C
0x140003e2c  test    eax, 0FFFFFF7Fh
0x140003e31  jnz     loc_1400040C4
0x140003e37  mov     rdi, rbx
0x140003e3a  jmp     short loc_140003E3E
0x140003e3c  xor     edi, edi
0x140003e3e  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140003e43  mov     [rsp+280h+var_250], 0
0x140003e4c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003e51  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003e56  mov     esi, eax
0x140003e58  test    eax, eax
0x140003e5a  jns     short loc_140003ED2
0x140003e5c  mov     rcx, [rbp+188h]; this
0x140003e63  mov     r9d, eax; char *
0x140003e66  mov     edx, 66h ; 'f'; void *
0x140003e6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e70  mov     rcx, [rbp+188h]; this
0x140003e77  mov     r9d, esi; char *
0x140003e7a  mov     edx, 6Fh ; 'o'; void *
0x140003e7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e84  mov     rcx, [rbp+188h]; this
0x140003e8b  mov     r9d, esi; char *
0x140003e8e  mov     edx, 12Eh; void *
0x140003e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e98  test    rdi, rdi
0x140003e9b  jz      short loc_140003EB4
0x140003e9d  mov     rcx, rdi; hMutex
0x140003ea0  call    cs:__imp_ReleaseMutex
0x140003ea7  nop     dword ptr [rax+rax+00h]
0x140003eac  test    eax, eax
0x140003eae  jz      loc_1400040D1
0x140003eb4  mov     rcx, rbx; hObject
0x140003eb7  call    cs:__imp_CloseHandle
0x140003ebe  nop     dword ptr [rax+rax+00h]
0x140003ec3  test    eax, eax
0x140003ec5  jz      loc_1400040E3
0x140003ecb  mov     eax, esi
0x140003ecd  jmp     loc_140004079
0x140003ed2  mov     rax, [rsp+280h+var_250]
0x140003ed7  lea     rcx, ds:0[rax*4]
0x140003edf  test    rcx, rcx
0x140003ee2  jz      short loc_140003EF2
0x140003ee4  mov     [r15], rcx
0x140003ee7  mov     eax, [rcx]
0x140003ee9  inc     eax
0x140003eeb  mov     [rcx], eax
0x140003eed  jmp     loc_140004043
0x140003ef2  mov     rdx, r14; dwBytes
0x140003ef5  mov     qword ptr [r15], 0
0x140003efc  mov     ecx, 8; dwFlags
0x140003f01  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003f06  mov     r14, rax
0x140003f09  test    rax, rax
0x140003f0c  jnz     short loc_140003F29
0x140003f0e  mov     rcx, [rbp+188h]; this
0x140003f15  mov     esi, 8007000Eh
0x140003f1a  mov     r9d, esi; char *
0x140003f1d  mov     edx, 14Bh; void *
0x140003f22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f27  jmp     short loc_140003F8C
0x140003f29  xorps   xmm0, xmm0
0x140003f2c  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003f31  mov     r8, r14; void *
0x140003f34  lea     rcx, [rsp+280h+var_250]; this
0x140003f39  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x140003f3f  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x140003f44  mov     esi, eax
0x140003f46  test    eax, eax
0x140003f48  jns     loc_140003FD8
0x140003f4e  mov     rcx, [rbp+188h]; this
0x140003f55  mov     r9d, eax; char *
0x140003f58  mov     edx, 14Eh; void *
0x140003f5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f62  lea     rcx, [rsp+280h+var_250]; this
0x140003f67  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140003f6c  call    cs:__imp_GetProcessHeap
0x140003f73  nop     dword ptr [rax+rax+00h]
0x140003f78  mov     r8, r14; lpMem
0x140003f7b  xor     edx, edx; dwFlags
0x140003f7d  mov     rcx, rax; hHeap
0x140003f80  call    cs:__imp_HeapFree
0x140003f87  nop     dword ptr [rax+rax+00h]
0x140003f8c  mov     rcx, [rbp+188h]; this
0x140003f93  mov     r9d, esi; char *
0x140003f96  mov     edx, 137h; void *
0x140003f9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fa0  test    rdi, rdi
0x140003fa3  jz      short loc_140003FBC
0x140003fa5  mov     rcx, rdi; hMutex
0x140003fa8  call    cs:__imp_ReleaseMutex
0x140003faf  nop     dword ptr [rax+rax+00h]
0x140003fb4  test    eax, eax
0x140003fb6  jz      loc_1400040F5
0x140003fbc  mov     rcx, rbx; hObject
0x140003fbf  call    cs:__imp_CloseHandle
0x140003fc6  nop     dword ptr [rax+rax+00h]
0x140003fcb  test    eax, eax
0x140003fcd  jz      loc_1400040B2
0x140003fd3  jmp     loc_140003ECB
0x140003fd8  mov     rax, [rsp+280h+var_250]
0x140003fdd  lea     rcx, [r14+22h]; void *
0x140003fe1  xor     edx, edx; Val
0x140003fe3  mov     [r14+10h], rax
0x140003fe7  mov     rax, [rsp+280h+var_250+8]
0x140003fec  mov     dword ptr [r14], 1
0x140003ff3  mov     [r14+8], rbx
0x140003ff7  lea     r8d, [rdx+56h]; Size
0x140003ffb  mov     [rsp+280h+var_250], 0
0x140004004  mov     [r14+18h], rax
0x140004008  mov     [rsp+280h+var_250+8], 0
0x140004011  call    memset_0
0x140004016  xor     edx, edx; Val
0x140004018  mov     word ptr [r14+20h], 58h ; 'X'
0x14000401f  lea     rcx, [r14+28h]; void *
0x140004023  mov     dword ptr [r14+24h], 1
0x14000402b  lea     r8d, [rdx+50h]; Size
0x14000402f  call    memset_0
0x140004034  lea     rcx, [rsp+280h+var_250]; this
0x140004039  mov     [r15], r14
0x14000403c  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140004041  xor     ebx, ebx
0x140004043  test    rdi, rdi
0x140004046  jz      short loc_14000405F
0x140004048  mov     rcx, rdi; hMutex
0x14000404b  call    cs:__imp_ReleaseMutex
0x140004052  nop     dword ptr [rax+rax+00h]
0x140004057  test    eax, eax
0x140004059  jz      loc_140004107
0x14000405f  test    rbx, rbx
0x140004062  jz      short loc_140004077
0x140004064  mov     rcx, rbx; hObject
0x140004067  call    cs:__imp_CloseHandle
0x14000406e  nop     dword ptr [rax+rax+00h]
0x140004073  test    eax, eax
0x140004075  jz      short loc_1400040A0
0x140004077  xor     eax, eax
0x140004079  mov     rcx, [rbp+180h+var_30]
0x140004080  xor     rcx, rsp; StackCookie
0x140004083  call    __security_check_cookie
0x140004088  mov     rbx, [rsp+280h+arg_10]
0x140004090  add     rsp, 260h
0x140004097  pop     r15
0x140004099  pop     r14
0x14000409b  pop     rdi
0x14000409c  pop     rsi
0x14000409d  pop     rbp
0x14000409e  retn
0x1400040a0  mov     rcx, [rbp+188h]; this
0x1400040a7  mov     edx, 0A0Bh; void *
0x1400040ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400040b2  mov     rcx, [rbp+188h]; this
0x1400040b9  mov     edx, 0A0Bh; void *
0x1400040be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400040c4  mov     rcx, [rbp+188h]; this
0x1400040cb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400040d1  mov     rcx, [rbp+188h]; this
0x1400040d8  mov     edx, 0A15h; void *
0x1400040dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400040e3  mov     rcx, [rbp+188h]; this
0x1400040ea  mov     edx, 0A0Bh; void *
0x1400040ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400040f5  mov     rcx, [rbp+188h]; this
0x1400040fc  mov     edx, 0A15h; void *
0x140004101  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004107  mov     rcx, [rbp+188h]; this
0x14000410e  mov     edx, 0A15h; void *
0x140004113  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
