# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001085c`
- end: `0x180010c23`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180010c2c`

## callees

- `0x1800034f0`
- `0x1800037c4`
- `0x180003e18`
- `0x1800048e8`
- `0x180004b30`
- `0x180004efc`
- `0x180004f88`
- `0x18000533c`
- `0x18000534c`
- `0x180010298`
- `0x18001085c`
- `0x180012dce`
- `0x180012e00`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180010a7a`
- `KERNEL32!HeapFree` at `0x180010a7a`
- `KERNEL32!ReleaseMutex` at `0x180010975`
- `KERNEL32!ReleaseMutex` at `0x180010a9c`
- `KERNEL32!ReleaseMutex` at `0x180010b38`
- `KERNEL32!ReleaseMutex` at `0x180010975`
- `KERNEL32!ReleaseMutex` at `0x180010a9c`
- `KERNEL32!ReleaseMutex` at `0x180010b38`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800108f4`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800108f4`
- `KERNEL32!CloseHandle` at `0x180010986`
- `KERNEL32!CloseHandle` at `0x180010a46`
- `KERNEL32!CloseHandle` at `0x180010a5e`
- `KERNEL32!CloseHandle` at `0x180010aad`
- `KERNEL32!CloseHandle` at `0x180010b4e`
- `KERNEL32!CloseHandle` at `0x180010986`
- `KERNEL32!CloseHandle` at `0x180010a46`
- `KERNEL32!CloseHandle` at `0x180010a5e`
- `KERNEL32!CloseHandle` at `0x180010aad`
- `KERNEL32!CloseHandle` at `0x180010b4e`
- `KERNEL32!CreateMutexExW` at `0x1800108d3`
- `KERNEL32!CreateMutexExW` at `0x1800108d3`
- `KERNEL32!GetCurrentProcessId` at `0x180010895`
- `KERNEL32!GetCurrentProcessId` at `0x180010895`
- `KERNEL32!GetProcessHeap` at `0x180010a6c`
- `KERNEL32!GetProcessHeap` at `0x180010a6c`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180010b05`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180010b05`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  __int64 v25; // r8
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x18001085c  mov     [rsp-8+arg_10], rbx
0x180010861  push    rbp
0x180010862  push    rsi
0x180010863  push    rdi
0x180010864  push    r14
0x180010866  push    r15
0x180010868  lea     rbp, [rsp-160h]
0x180010870  sub     rsp, 260h
0x180010877  mov     rax, cs:__security_cookie
0x18001087e  xor     rax, rsp
0x180010881  mov     [rbp+180h+var_30], rax
0x180010888  mov     r15, rdx
0x18001088b  mov     qword ptr [rdx], 0
0x180010892  mov     rbx, rcx
0x180010895  call    cs:__imp_GetCurrentProcessId
0x18001089b  mov     r14d, 130h
0x1800108a1  mov     [rsp+280h+var_258], rbx
0x1800108a6  mov     r9d, eax
0x1800108a9  mov     [rsp+280h+var_260], r14d; int
0x1800108ae  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800108b5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800108ba  lea     edx, [r14-2Ch]; unsigned __int64
0x1800108be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800108c3  mov     r9d, 1F0001h; dwDesiredAccess
0x1800108c9  lea     rdx, [rsp+280h+Name]; lpName
0x1800108ce  xor     r8d, r8d; dwFlags
0x1800108d1  xor     ecx, ecx; lpMutexAttributes
0x1800108d3  call    cs:__imp_CreateMutexExW
0x1800108d9  mov     rbx, rax
0x1800108dc  test    rax, rax
0x1800108df  jnz     short loc_1800108EB
0x1800108e1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800108e6  jmp     loc_180010B5A
0x1800108eb  xor     r8d, r8d; bAlertable
0x1800108ee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800108f1  mov     rcx, rbx; hHandle
0x1800108f4  call    cs:__imp_WaitForSingleObjectEx
0x1800108fa  cmp     eax, 102h
0x1800108ff  jz      short loc_180010911
0x180010901  test    eax, 0FFFFFF7Fh
0x180010906  jnz     loc_180010BA4
0x18001090c  mov     rdi, rbx
0x18001090f  jmp     short loc_180010913
0x180010911  xor     edi, edi
0x180010913  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180010918  mov     [rsp+280h+hObject], 0
0x180010921  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010926  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001092b  mov     esi, eax
0x18001092d  test    eax, eax
0x18001092f  jns     short loc_18001099B
0x180010931  mov     rcx, [rbp+188h]; this
0x180010938  mov     r9d, eax; char *
0x18001093b  mov     edx, 66h ; 'f'; void *
0x180010940  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010945  mov     rcx, [rbp+188h]; this
0x18001094c  mov     r9d, esi; char *
0x18001094f  mov     edx, 6Fh ; 'o'; void *
0x180010954  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010959  mov     rcx, [rbp+188h]; this
0x180010960  mov     r9d, esi; char *
0x180010963  mov     edx, 12Eh; void *
0x180010968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001096d  test    rdi, rdi
0x180010970  jz      short loc_180010983
0x180010972  mov     rcx, rdi; hMutex
0x180010975  call    cs:__imp_ReleaseMutex
0x18001097b  test    eax, eax
0x18001097d  jz      loc_180010BB1
0x180010983  mov     rcx, rbx; hObject
0x180010986  call    cs:__imp_CloseHandle
0x18001098c  test    eax, eax
0x18001098e  jz      loc_180010BC3
0x180010994  mov     eax, esi
0x180010996  jmp     loc_180010B5A
0x18001099b  mov     rax, [rsp+280h+hObject]
0x1800109a0  lea     rcx, ds:0[rax*4]
0x1800109a8  test    rcx, rcx
0x1800109ab  jz      short loc_1800109BB
0x1800109ad  mov     [r15], rcx
0x1800109b0  mov     eax, [rcx]
0x1800109b2  inc     eax
0x1800109b4  mov     [rcx], eax
0x1800109b6  jmp     loc_180010B30
0x1800109bb  mov     rdx, r14; dwBytes
0x1800109be  mov     qword ptr [r15], 0
0x1800109c5  mov     ecx, 8; dwFlags
0x1800109ca  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800109cf  mov     r14, rax
0x1800109d2  test    rax, rax
0x1800109d5  jnz     short loc_1800109F5
0x1800109d7  mov     rcx, [rbp+188h]; this
0x1800109de  mov     esi, 8007000Eh
0x1800109e3  mov     r9d, esi; char *
0x1800109e6  mov     edx, 14Bh; void *
0x1800109eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109f0  jmp     loc_180010A80
0x1800109f5  xorps   xmm0, xmm0
0x1800109f8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800109fe  test    r14b, 3
0x180010a02  jnz     loc_180010BD5
0x180010a08  mov     r9, r14
0x180010a0b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180010a10  shr     r9, 2; unsigned __int64
0x180010a14  lea     rcx, [rsp+280h+hObject]; this
0x180010a19  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180010a1e  mov     esi, eax
0x180010a20  test    eax, eax
0x180010a22  jns     loc_180010AC0
0x180010a28  mov     rcx, [rbp+188h]; this
0x180010a2f  mov     r9d, eax; char *
0x180010a32  mov     edx, 14Eh; void *
0x180010a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a3c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180010a41  test    rcx, rcx
0x180010a44  jz      short loc_180010A54
0x180010a46  call    cs:__imp_CloseHandle
0x180010a4c  test    eax, eax
0x180010a4e  jz      loc_180010BDB
0x180010a54  mov     rcx, [rsp+280h+hObject]; hObject
0x180010a59  test    rcx, rcx
0x180010a5c  jz      short loc_180010A6C
0x180010a5e  call    cs:__imp_CloseHandle
0x180010a64  test    eax, eax
0x180010a66  jz      loc_180010BED
0x180010a6c  call    cs:__imp_GetProcessHeap
0x180010a72  mov     r8, r14; lpMem
0x180010a75  xor     edx, edx; dwFlags
0x180010a77  mov     rcx, rax; hHeap
0x180010a7a  call    cs:__imp_HeapFree
0x180010a80  mov     rcx, [rbp+188h]; this
0x180010a87  mov     r9d, esi; char *
0x180010a8a  mov     edx, 137h; void *
0x180010a8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a94  test    rdi, rdi
0x180010a97  jz      short loc_180010AAA
0x180010a99  mov     rcx, rdi; hMutex
0x180010a9c  call    cs:__imp_ReleaseMutex
0x180010aa2  test    eax, eax
0x180010aa4  jz      loc_180010BFF
0x180010aaa  mov     rcx, rbx; hObject
0x180010aad  call    cs:__imp_CloseHandle
0x180010ab3  test    eax, eax
0x180010ab5  jz      loc_180010B92
0x180010abb  jmp     loc_180010994
0x180010ac0  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180010ac5  lea     rcx, [r14+28h]; void *
0x180010ac9  mov     dword ptr [r14], 1
0x180010ad0  xor     edx, edx; Val
0x180010ad2  mov     [r14+8], rbx
0x180010ad6  mov     r8d, 108h; Size
0x180010adc  movdqu  xmmword ptr [r14+10h], xmm0
0x180010ae2  call    memset_0
0x180010ae7  xor     eax, eax
0x180010ae9  lea     rcx, [r14+28h]; this
0x180010aed  mov     [r14+20h], rax
0x180010af1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180010af6  lea     rbx, [r14+0E8h]
0x180010afd  xor     r8d, r8d; Flags
0x180010b00  mov     rcx, rbx; lpCriticalSection
0x180010b03  xor     edx, edx; dwSpinCount
0x180010b05  call    cs:__imp_InitializeCriticalSectionEx
0x180010b0b  mov     qword ptr [rbx+28h], 0
0x180010b13  mov     qword ptr [rbx+30h], 0
0x180010b1b  mov     qword ptr [rbx+38h], 0
0x180010b23  mov     qword ptr [rbx+40h], 0
0x180010b2b  xor     ebx, ebx
0x180010b2d  mov     [r15], r14
0x180010b30  test    rdi, rdi
0x180010b33  jz      short loc_180010B46
0x180010b35  mov     rcx, rdi; hMutex
0x180010b38  call    cs:__imp_ReleaseMutex
0x180010b3e  test    eax, eax
0x180010b40  jz      loc_180010C11
0x180010b46  test    rbx, rbx
0x180010b49  jz      short loc_180010B58
0x180010b4b  mov     rcx, rbx; hObject
0x180010b4e  call    cs:__imp_CloseHandle
0x180010b54  test    eax, eax
0x180010b56  jz      short loc_180010B80
0x180010b58  xor     eax, eax
0x180010b5a  mov     rcx, [rbp+180h+var_30]
0x180010b61  xor     rcx, rsp; StackCookie
0x180010b64  call    __security_check_cookie
0x180010b69  mov     rbx, [rsp+280h+arg_10]
0x180010b71  add     rsp, 260h
0x180010b78  pop     r15
0x180010b7a  pop     r14
0x180010b7c  pop     rdi
0x180010b7d  pop     rsi
0x180010b7e  pop     rbp
0x180010b7f  retn
0x180010b80  mov     rcx, [rbp+188h]; this
0x180010b87  mov     edx, 0A0Bh; void *
0x180010b8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010b92  mov     rcx, [rbp+188h]; this
0x180010b99  mov     edx, 0A0Bh; void *
0x180010b9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010ba4  mov     rcx, [rbp+188h]; this
0x180010bab  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180010bb1  mov     rcx, [rbp+188h]; this
0x180010bb8  mov     edx, 0A15h; void *
0x180010bbd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010bc3  mov     rcx, [rbp+188h]; this
0x180010bca  mov     edx, 0A0Bh; void *
0x180010bcf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010bd5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180010bdb  mov     rcx, [rbp+188h]; this
0x180010be2  mov     edx, 0A0Bh; void *
0x180010be7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010bed  mov     rcx, [rbp+188h]; this
0x180010bf4  mov     edx, 0A0Bh; void *
0x180010bf9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010bff  mov     rcx, [rbp+188h]; this
0x180010c06  mov     edx, 0A15h; void *
0x180010c0b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010c11  mov     rcx, [rbp+188h]; this
0x180010c18  mov     edx, 0A15h; void *
0x180010c1d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
