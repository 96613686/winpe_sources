# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800aed6c`
- end: `0x1800af10a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800b228c`

## callees

- `0x18000e564`
- `0x1800aed6c`
- `0x1800b0594`
- `0x1800b0b30`
- `0x1800b2028`
- `0x1800b4ff4`
- `0x1800b6e74`
- `0x1800b7700`
- `0x1800b7fac`
- `0x1800b7fbc`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aeda5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aeda5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aee97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aef59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aef71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aefc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af035`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aee97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aef59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aef71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aefc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af035`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aee86`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aefaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af01f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aee86`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aefaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af01f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800aee05`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800aee05`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800aede4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800aede4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aef8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aef8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aef7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aef7f`

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
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x1800aed6c  mov     [rsp-8+arg_10], rbx
0x1800aed71  push    rbp
0x1800aed72  push    rsi
0x1800aed73  push    rdi
0x1800aed74  push    r14
0x1800aed76  push    r15
0x1800aed78  lea     rbp, [rsp-160h]
0x1800aed80  sub     rsp, 260h
0x1800aed87  mov     rax, cs:__security_cookie
0x1800aed8e  xor     rax, rsp
0x1800aed91  mov     [rbp+180h+var_30], rax
0x1800aed98  mov     r15, rdx
0x1800aed9b  mov     qword ptr [rdx], 0
0x1800aeda2  mov     rbx, rcx
0x1800aeda5  call    cs:__imp_GetCurrentProcessId
0x1800aedab  mov     r14d, 78h ; 'x'
0x1800aedb1  mov     [rsp+280h+var_258], rbx
0x1800aedb6  mov     r9d, eax
0x1800aedb9  mov     [rsp+280h+var_260], r14d; int
0x1800aedbe  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800aedc5  mov     edx, 104h; unsigned __int64
0x1800aedca  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800aedcf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800aedd4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800aedda  lea     rdx, [rsp+280h+Name]; lpName
0x1800aeddf  xor     r8d, r8d; dwFlags
0x1800aede2  xor     ecx, ecx; lpMutexAttributes
0x1800aede4  call    cs:__imp_CreateMutexExW
0x1800aedea  mov     rbx, rax
0x1800aeded  test    rax, rax
0x1800aedf0  jnz     short loc_1800AEDFC
0x1800aedf2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800aedf7  jmp     loc_1800AF041
0x1800aedfc  xor     r8d, r8d; bAlertable
0x1800aedff  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800aee02  mov     rcx, rbx; hHandle
0x1800aee05  call    cs:__imp_WaitForSingleObjectEx
0x1800aee0b  cmp     eax, 102h
0x1800aee10  jz      short loc_1800AEE22
0x1800aee12  test    eax, 0FFFFFF7Fh
0x1800aee17  jnz     loc_1800AF079
0x1800aee1d  mov     rdi, rbx
0x1800aee20  jmp     short loc_1800AEE24
0x1800aee22  xor     edi, edi
0x1800aee24  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800aee29  mov     [rsp+280h+hObject], 0
0x1800aee32  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800aee37  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800aee3c  mov     esi, eax
0x1800aee3e  test    eax, eax
0x1800aee40  jns     short loc_1800AEEAC
0x1800aee42  mov     rcx, [rbp+188h]; this
0x1800aee49  mov     r9d, eax; char *
0x1800aee4c  mov     edx, 66h ; 'f'; void *
0x1800aee51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aee56  mov     rcx, [rbp+188h]; this
0x1800aee5d  mov     r9d, esi; char *
0x1800aee60  mov     edx, 6Fh ; 'o'; void *
0x1800aee65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aee6a  mov     rcx, [rbp+188h]; this
0x1800aee71  mov     r9d, esi; char *
0x1800aee74  mov     edx, 12Eh; void *
0x1800aee79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aee7e  test    rdi, rdi
0x1800aee81  jz      short loc_1800AEE94
0x1800aee83  mov     rcx, rdi; hMutex
0x1800aee86  call    cs:__imp_ReleaseMutex
0x1800aee8c  test    eax, eax
0x1800aee8e  jz      loc_1800AF086
0x1800aee94  mov     rcx, rbx; hObject
0x1800aee97  call    cs:__imp_CloseHandle
0x1800aee9d  test    eax, eax
0x1800aee9f  jz      loc_1800AF098
0x1800aeea5  mov     eax, esi
0x1800aeea7  jmp     loc_1800AF041
0x1800aeeac  mov     rax, [rsp+280h+hObject]
0x1800aeeb1  lea     rcx, ds:0[rax*4]
0x1800aeeb9  test    rcx, rcx
0x1800aeebc  jz      short loc_1800AEECC
0x1800aeebe  mov     [r15], rcx
0x1800aeec1  mov     eax, [rcx]
0x1800aeec3  inc     eax
0x1800aeec5  mov     [rcx], eax
0x1800aeec7  jmp     loc_1800AF017
0x1800aeecc  mov     rdx, r14; dwBytes
0x1800aeecf  mov     qword ptr [r15], 0
0x1800aeed6  mov     ecx, 8; dwFlags
0x1800aeedb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800aeee0  mov     rsi, rax
0x1800aeee3  test    rax, rax
0x1800aeee6  jnz     short loc_1800AEF07
0x1800aeee8  mov     rcx, [rbp+188h]; this
0x1800aeeef  mov     r14d, 8007000Eh
0x1800aeef5  mov     r9d, r14d; char *
0x1800aeef8  mov     edx, 14Bh; void *
0x1800aeefd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aef02  jmp     loc_1800AEF93
0x1800aef07  xorps   xmm0, xmm0
0x1800aef0a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800aef10  test    sil, 3
0x1800aef14  jnz     loc_1800AF0AA
0x1800aef1a  mov     r9, rsi
0x1800aef1d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800aef22  shr     r9, 2; unsigned __int64
0x1800aef26  lea     rcx, [rsp+280h+hObject]; this
0x1800aef2b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800aef30  mov     r14d, eax
0x1800aef33  test    eax, eax
0x1800aef35  jns     loc_1800AEFD3
0x1800aef3b  mov     rcx, [rbp+188h]; this
0x1800aef42  mov     r9d, eax; char *
0x1800aef45  mov     edx, 14Eh; void *
0x1800aef4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aef4f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800aef54  test    rcx, rcx
0x1800aef57  jz      short loc_1800AEF67
0x1800aef59  call    cs:__imp_CloseHandle
0x1800aef5f  test    eax, eax
0x1800aef61  jz      loc_1800AF0B0
0x1800aef67  mov     rcx, [rsp+280h+hObject]; hObject
0x1800aef6c  test    rcx, rcx
0x1800aef6f  jz      short loc_1800AEF7F
0x1800aef71  call    cs:__imp_CloseHandle
0x1800aef77  test    eax, eax
0x1800aef79  jz      loc_1800AF0C2
0x1800aef7f  call    cs:__imp_GetProcessHeap
0x1800aef85  mov     r8, rsi; lpMem
0x1800aef88  xor     edx, edx; dwFlags
0x1800aef8a  mov     rcx, rax; hHeap
0x1800aef8d  call    cs:__imp_HeapFree
0x1800aef93  mov     rcx, [rbp+188h]; this
0x1800aef9a  mov     r9d, r14d; char *
0x1800aef9d  mov     edx, 137h; void *
0x1800aefa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aefa7  test    rdi, rdi
0x1800aefaa  jz      short loc_1800AEFBD
0x1800aefac  mov     rcx, rdi; hMutex
0x1800aefaf  call    cs:__imp_ReleaseMutex
0x1800aefb5  test    eax, eax
0x1800aefb7  jz      loc_1800AF0D4
0x1800aefbd  mov     rcx, rbx; hObject
0x1800aefc0  call    cs:__imp_CloseHandle
0x1800aefc6  test    eax, eax
0x1800aefc8  jz      loc_1800AF0E6
0x1800aefce  mov     eax, r14d
0x1800aefd1  jmp     short loc_1800AF041
0x1800aefd3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800aefd8  xor     edx, edx; Val
0x1800aefda  mov     dword ptr [rsi], 1
0x1800aefe0  lea     rcx, [rsi+22h]; void *
0x1800aefe4  mov     [rsi+8], rbx
0x1800aefe8  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800aefed  lea     r8d, [rdx+56h]; Size
0x1800aeff1  call    memset_0
0x1800aeff6  xor     edx, edx; Val
0x1800aeff8  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800aeffe  lea     rcx, [rsi+28h]; void *
0x1800af002  mov     dword ptr [rsi+24h], 1
0x1800af009  lea     r8d, [rdx+50h]; Size
0x1800af00d  call    memset_0
0x1800af012  xor     ebx, ebx
0x1800af014  mov     [r15], rsi
0x1800af017  test    rdi, rdi
0x1800af01a  jz      short loc_1800AF02D
0x1800af01c  mov     rcx, rdi; hMutex
0x1800af01f  call    cs:__imp_ReleaseMutex
0x1800af025  test    eax, eax
0x1800af027  jz      loc_1800AF0F8
0x1800af02d  test    rbx, rbx
0x1800af030  jz      short loc_1800AF03F
0x1800af032  mov     rcx, rbx; hObject
0x1800af035  call    cs:__imp_CloseHandle
0x1800af03b  test    eax, eax
0x1800af03d  jz      short loc_1800AF067
0x1800af03f  xor     eax, eax
0x1800af041  mov     rcx, [rbp+180h+var_30]
0x1800af048  xor     rcx, rsp; StackCookie
0x1800af04b  call    __security_check_cookie
0x1800af050  mov     rbx, [rsp+280h+arg_10]
0x1800af058  add     rsp, 260h
0x1800af05f  pop     r15
0x1800af061  pop     r14
0x1800af063  pop     rdi
0x1800af064  pop     rsi
0x1800af065  pop     rbp
0x1800af066  retn
0x1800af067  mov     rcx, [rbp+188h]; this
0x1800af06e  mov     edx, 0A0Bh; void *
0x1800af073  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af079  mov     rcx, [rbp+188h]; this
0x1800af080  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800af086  mov     rcx, [rbp+188h]; this
0x1800af08d  mov     edx, 0A15h; void *
0x1800af092  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af098  mov     rcx, [rbp+188h]; this
0x1800af09f  mov     edx, 0A0Bh; void *
0x1800af0a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af0aa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800af0b0  mov     rcx, [rbp+188h]; this
0x1800af0b7  mov     edx, 0A0Bh; void *
0x1800af0bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af0c2  mov     rcx, [rbp+188h]; this
0x1800af0c9  mov     edx, 0A0Bh; void *
0x1800af0ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af0d4  mov     rcx, [rbp+188h]; this
0x1800af0db  mov     edx, 0A15h; void *
0x1800af0e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af0e6  mov     rcx, [rbp+188h]; this
0x1800af0ed  mov     edx, 0A0Bh; void *
0x1800af0f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af0f8  mov     rcx, [rbp+188h]; this
0x1800af0ff  mov     edx, 0A15h; void *
0x1800af104  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
