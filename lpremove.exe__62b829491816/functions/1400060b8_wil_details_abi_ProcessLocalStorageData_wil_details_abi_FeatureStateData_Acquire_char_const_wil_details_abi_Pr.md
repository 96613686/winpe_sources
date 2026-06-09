# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1400060b8`
- end: `0x1400064a9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140006b78`

## callees

- `0x140002190`
- `0x140002c2c`
- `0x140004bdc`
- `0x1400060b8`
- `0x140006810`
- `0x140006d28`
- `0x140007708`
- `0x140009080`
- `0x14000a914`
- `0x14000bccc`
- `0x14000c02c`
- `0x14000cdec`
- `0x14000cdfc`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1400062eb`
- `KERNEL32!GetProcessHeap` at `0x1400062eb`
- `KERNEL32!HeapFree` at `0x1400062f9`
- `KERNEL32!HeapFree` at `0x1400062f9`
- `KERNEL32!ReleaseMutex` at `0x1400061e6`
- `KERNEL32!ReleaseMutex` at `0x140006322`
- `KERNEL32!ReleaseMutex` at `0x1400063be`
- `KERNEL32!ReleaseMutex` at `0x1400061e6`
- `KERNEL32!ReleaseMutex` at `0x140006322`
- `KERNEL32!ReleaseMutex` at `0x1400063be`
- `KERNEL32!WaitForSingleObjectEx` at `0x140006150`
- `KERNEL32!WaitForSingleObjectEx` at `0x140006150`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14000638b`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14000638b`
- `KERNEL32!GetCurrentProcessId` at `0x1400060f1`
- `KERNEL32!GetCurrentProcessId` at `0x1400060f1`
- `KERNEL32!CreateMutexExW` at `0x14000612f`
- `KERNEL32!CreateMutexExW` at `0x14000612f`
- `KERNEL32!CloseHandle` at `0x1400061f7`
- `KERNEL32!CloseHandle` at `0x1400062c5`
- `KERNEL32!CloseHandle` at `0x1400062dd`
- `KERNEL32!CloseHandle` at `0x140006333`
- `KERNEL32!CloseHandle` at `0x1400063d4`
- `KERNEL32!CloseHandle` at `0x1400061f7`
- `KERNEL32!CloseHandle` at `0x1400062c5`
- `KERNEL32!CloseHandle` at `0x1400062dd`
- `KERNEL32!CloseHandle` at `0x140006333`
- `KERNEL32!CloseHandle` at `0x1400063d4`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x1400060b8  mov     [rsp-8+arg_10], rbx
0x1400060bd  push    rbp
0x1400060be  push    rsi
0x1400060bf  push    rdi
0x1400060c0  push    r14
0x1400060c2  push    r15
0x1400060c4  lea     rbp, [rsp-160h]
0x1400060cc  sub     rsp, 260h
0x1400060d3  mov     rax, cs:__security_cookie
0x1400060da  xor     rax, rsp
0x1400060dd  mov     [rbp+180h+var_30], rax
0x1400060e4  mov     r15, rdx
0x1400060e7  mov     qword ptr [rdx], 0
0x1400060ee  mov     rbx, rcx
0x1400060f1  call    cs:__imp_GetCurrentProcessId
0x1400060f7  mov     r14d, 130h
0x1400060fd  mov     [rsp+280h+var_258], rbx
0x140006102  mov     r9d, eax
0x140006105  mov     [rsp+280h+var_260], r14d; int
0x14000610a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140006111  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140006116  lea     edx, [r14-2Ch]; unsigned __int64
0x14000611a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000611f  mov     r9d, 1F0001h; dwDesiredAccess
0x140006125  lea     rdx, [rsp+280h+Name]; lpName
0x14000612a  xor     r8d, r8d; dwFlags
0x14000612d  xor     ecx, ecx; lpMutexAttributes
0x14000612f  call    cs:__imp_CreateMutexExW
0x140006135  mov     rbx, rax
0x140006138  test    rax, rax
0x14000613b  jnz     short loc_140006147
0x14000613d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140006142  jmp     loc_1400063E0
0x140006147  xor     r8d, r8d; bAlertable
0x14000614a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000614d  mov     rcx, rbx; hHandle
0x140006150  call    cs:__imp_WaitForSingleObjectEx
0x140006156  cmp     eax, 102h
0x14000615b  jz      short loc_14000616D
0x14000615d  test    eax, 0FFFFFF7Fh
0x140006162  jnz     loc_14000642A
0x140006168  mov     rdi, rbx
0x14000616b  jmp     short loc_14000616F
0x14000616d  xor     edi, edi
0x14000616f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140006174  mov     [rsp+280h+hObject], 0
0x14000617d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140006182  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140006187  mov     esi, eax
0x140006189  test    eax, eax
0x14000618b  jns     short loc_14000620C
0x14000618d  mov     rcx, [rbp+188h]; this
0x140006194  lea     r8, aWil; "wil"
0x14000619b  mov     r9d, eax; char *
0x14000619e  mov     edx, 66h ; 'f'; void *
0x1400061a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400061a8  mov     rcx, [rbp+188h]; this
0x1400061af  lea     r8, aWil; "wil"
0x1400061b6  mov     r9d, esi; char *
0x1400061b9  mov     edx, 6Fh ; 'o'; void *
0x1400061be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400061c3  mov     rcx, [rbp+188h]; this
0x1400061ca  lea     r8, aWil; "wil"
0x1400061d1  mov     r9d, esi; char *
0x1400061d4  mov     edx, 12Eh; void *
0x1400061d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400061de  test    rdi, rdi
0x1400061e1  jz      short loc_1400061F4
0x1400061e3  mov     rcx, rdi; hMutex
0x1400061e6  call    cs:__imp_ReleaseMutex
0x1400061ec  test    eax, eax
0x1400061ee  jz      loc_140006437
0x1400061f4  mov     rcx, rbx; hObject
0x1400061f7  call    cs:__imp_CloseHandle
0x1400061fd  test    eax, eax
0x1400061ff  jz      loc_140006449
0x140006205  mov     eax, esi
0x140006207  jmp     loc_1400063E0
0x14000620c  mov     rax, [rsp+280h+hObject]
0x140006211  lea     rcx, ds:0[rax*4]
0x140006219  test    rcx, rcx
0x14000621c  jz      short loc_14000622C
0x14000621e  mov     [r15], rcx
0x140006221  mov     eax, [rcx]
0x140006223  inc     eax
0x140006225  mov     [rcx], eax
0x140006227  jmp     loc_1400063B6
0x14000622c  mov     rdx, r14; dwBytes
0x14000622f  mov     qword ptr [r15], 0
0x140006236  mov     ecx, 8; dwFlags
0x14000623b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006240  mov     r14, rax
0x140006243  test    rax, rax
0x140006246  jnz     short loc_14000626D
0x140006248  mov     rcx, [rbp+188h]; this
0x14000624f  lea     r8, aWil; "wil"
0x140006256  mov     esi, 8007000Eh
0x14000625b  mov     edx, 14Bh; void *
0x140006260  mov     r9d, esi; char *
0x140006263  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006268  jmp     loc_1400062FF
0x14000626d  xorps   xmm0, xmm0
0x140006270  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140006276  test    r14b, 3
0x14000627a  jnz     loc_14000645B
0x140006280  mov     r9, r14
0x140006283  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140006288  shr     r9, 2; unsigned __int64
0x14000628c  lea     rcx, [rsp+280h+hObject]; this
0x140006291  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140006296  mov     esi, eax
0x140006298  test    eax, eax
0x14000629a  jns     loc_140006346
0x1400062a0  mov     rcx, [rbp+188h]; this
0x1400062a7  lea     r8, aWil; "wil"
0x1400062ae  mov     r9d, eax; char *
0x1400062b1  mov     edx, 14Eh; void *
0x1400062b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400062bb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400062c0  test    rcx, rcx
0x1400062c3  jz      short loc_1400062D3
0x1400062c5  call    cs:__imp_CloseHandle
0x1400062cb  test    eax, eax
0x1400062cd  jz      loc_140006461
0x1400062d3  mov     rcx, [rsp+280h+hObject]; hObject
0x1400062d8  test    rcx, rcx
0x1400062db  jz      short loc_1400062EB
0x1400062dd  call    cs:__imp_CloseHandle
0x1400062e3  test    eax, eax
0x1400062e5  jz      loc_140006473
0x1400062eb  call    cs:__imp_GetProcessHeap
0x1400062f1  mov     r8, r14; lpMem
0x1400062f4  xor     edx, edx; dwFlags
0x1400062f6  mov     rcx, rax; hHeap
0x1400062f9  call    cs:__imp_HeapFree
0x1400062ff  mov     rcx, [rbp+188h]; this
0x140006306  lea     r8, aWil; "wil"
0x14000630d  mov     r9d, esi; char *
0x140006310  mov     edx, 137h; void *
0x140006315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000631a  test    rdi, rdi
0x14000631d  jz      short loc_140006330
0x14000631f  mov     rcx, rdi; hMutex
0x140006322  call    cs:__imp_ReleaseMutex
0x140006328  test    eax, eax
0x14000632a  jz      loc_140006485
0x140006330  mov     rcx, rbx; hObject
0x140006333  call    cs:__imp_CloseHandle
0x140006339  test    eax, eax
0x14000633b  jz      loc_140006418
0x140006341  jmp     loc_140006205
0x140006346  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000634b  lea     rcx, [r14+28h]; void *
0x14000634f  mov     dword ptr [r14], 1
0x140006356  xor     edx, edx; Val
0x140006358  mov     [r14+8], rbx
0x14000635c  mov     r8d, 108h; Size
0x140006362  movdqu  xmmword ptr [r14+10h], xmm0
0x140006368  call    memset_0
0x14000636d  xor     eax, eax
0x14000636f  lea     rcx, [r14+28h]; this
0x140006373  mov     [r14+20h], rax
0x140006377  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000637c  lea     rbx, [r14+0E8h]
0x140006383  xor     r8d, r8d; Flags
0x140006386  mov     rcx, rbx; lpCriticalSection
0x140006389  xor     edx, edx; dwSpinCount
0x14000638b  call    cs:__imp_InitializeCriticalSectionEx
0x140006391  mov     qword ptr [rbx+28h], 0
0x140006399  mov     qword ptr [rbx+30h], 0
0x1400063a1  mov     qword ptr [rbx+38h], 0
0x1400063a9  mov     qword ptr [rbx+40h], 0
0x1400063b1  xor     ebx, ebx
0x1400063b3  mov     [r15], r14
0x1400063b6  test    rdi, rdi
0x1400063b9  jz      short loc_1400063CC
0x1400063bb  mov     rcx, rdi; hMutex
0x1400063be  call    cs:__imp_ReleaseMutex
0x1400063c4  test    eax, eax
0x1400063c6  jz      loc_140006497
0x1400063cc  test    rbx, rbx
0x1400063cf  jz      short loc_1400063DE
0x1400063d1  mov     rcx, rbx; hObject
0x1400063d4  call    cs:__imp_CloseHandle
0x1400063da  test    eax, eax
0x1400063dc  jz      short loc_140006406
0x1400063de  xor     eax, eax
0x1400063e0  mov     rcx, [rbp+180h+var_30]
0x1400063e7  xor     rcx, rsp; StackCookie
0x1400063ea  call    __security_check_cookie
0x1400063ef  mov     rbx, [rsp+280h+arg_10]
0x1400063f7  add     rsp, 260h
0x1400063fe  pop     r15
0x140006400  pop     r14
0x140006402  pop     rdi
0x140006403  pop     rsi
0x140006404  pop     rbp
0x140006405  retn
0x140006406  mov     rcx, [rbp+188h]; this
0x14000640d  mov     edx, 0A0Bh; void *
0x140006412  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006418  mov     rcx, [rbp+188h]; this
0x14000641f  mov     edx, 0A0Bh; void *
0x140006424  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000642a  mov     rcx, [rbp+188h]; this
0x140006431  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140006437  mov     rcx, [rbp+188h]; this
0x14000643e  mov     edx, 0A15h; void *
0x140006443  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006449  mov     rcx, [rbp+188h]; this
0x140006450  mov     edx, 0A0Bh; void *
0x140006455  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000645b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140006461  mov     rcx, [rbp+188h]; this
0x140006468  mov     edx, 0A0Bh; void *
0x14000646d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006473  mov     rcx, [rbp+188h]; this
0x14000647a  mov     edx, 0A0Bh; void *
0x14000647f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006485  mov     rcx, [rbp+188h]; this
0x14000648c  mov     edx, 0A15h; void *
0x140006491  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006497  mov     rcx, [rbp+188h]; this
0x14000649e  mov     edx, 0A15h; void *
0x1400064a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
