# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003ecc`
- end: `0x14000426a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140005c84`

## callees

- `0x140001fa0`
- `0x140002bc6`
- `0x140003ecc`
- `0x140004734`
- `0x140004cf8`
- `0x1400056c0`
- `0x14000756c`
- `0x140007d5c`
- `0x140009098`
- `0x140009124`
- `0x140009a1c`
- `0x140009a2c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140003ff7`
- `KERNEL32!CloseHandle` at `0x1400040b9`
- `KERNEL32!CloseHandle` at `0x1400040d1`
- `KERNEL32!CloseHandle` at `0x140004120`
- `KERNEL32!CloseHandle` at `0x140004195`
- `KERNEL32!CloseHandle` at `0x140003ff7`
- `KERNEL32!CloseHandle` at `0x1400040b9`
- `KERNEL32!CloseHandle` at `0x1400040d1`
- `KERNEL32!CloseHandle` at `0x140004120`
- `KERNEL32!CloseHandle` at `0x140004195`
- `KERNEL32!ReleaseMutex` at `0x140003fe6`
- `KERNEL32!ReleaseMutex` at `0x14000410f`
- `KERNEL32!ReleaseMutex` at `0x14000417f`
- `KERNEL32!ReleaseMutex` at `0x140003fe6`
- `KERNEL32!ReleaseMutex` at `0x14000410f`
- `KERNEL32!ReleaseMutex` at `0x14000417f`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003f65`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003f65`
- `KERNEL32!GetCurrentProcessId` at `0x140003f05`
- `KERNEL32!GetCurrentProcessId` at `0x140003f05`
- `KERNEL32!CreateMutexExW` at `0x140003f44`
- `KERNEL32!CreateMutexExW` at `0x140003f44`
- `KERNEL32!GetProcessHeap` at `0x1400040df`
- `KERNEL32!GetProcessHeap` at `0x1400040df`
- `KERNEL32!HeapFree` at `0x1400040ed`
- `KERNEL32!HeapFree` at `0x1400040ed`

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
  __int64 v25; // r8
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
0x140003ecc  mov     [rsp-8+arg_10], rbx
0x140003ed1  push    rbp
0x140003ed2  push    rsi
0x140003ed3  push    rdi
0x140003ed4  push    r14
0x140003ed6  push    r15
0x140003ed8  lea     rbp, [rsp-160h]
0x140003ee0  sub     rsp, 260h
0x140003ee7  mov     rax, cs:__security_cookie
0x140003eee  xor     rax, rsp
0x140003ef1  mov     [rbp+180h+var_30], rax
0x140003ef8  mov     r15, rdx
0x140003efb  mov     qword ptr [rdx], 0
0x140003f02  mov     rbx, rcx
0x140003f05  call    cs:__imp_GetCurrentProcessId
0x140003f0b  mov     r14d, 78h ; 'x'
0x140003f11  mov     [rsp+280h+var_258], rbx
0x140003f16  mov     r9d, eax
0x140003f19  mov     [rsp+280h+var_260], r14d; int
0x140003f1e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003f25  mov     edx, 104h; unsigned __int64
0x140003f2a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003f2f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003f34  mov     r9d, 1F0001h; dwDesiredAccess
0x140003f3a  lea     rdx, [rsp+280h+Name]; lpName
0x140003f3f  xor     r8d, r8d; dwFlags
0x140003f42  xor     ecx, ecx; lpMutexAttributes
0x140003f44  call    cs:__imp_CreateMutexExW
0x140003f4a  mov     rbx, rax
0x140003f4d  test    rax, rax
0x140003f50  jnz     short loc_140003F5C
0x140003f52  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003f57  jmp     loc_1400041A1
0x140003f5c  xor     r8d, r8d; bAlertable
0x140003f5f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003f62  mov     rcx, rbx; hHandle
0x140003f65  call    cs:__imp_WaitForSingleObjectEx
0x140003f6b  cmp     eax, 102h
0x140003f70  jz      short loc_140003F82
0x140003f72  test    eax, 0FFFFFF7Fh
0x140003f77  jnz     loc_1400041D9
0x140003f7d  mov     rdi, rbx
0x140003f80  jmp     short loc_140003F84
0x140003f82  xor     edi, edi
0x140003f84  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003f89  mov     [rsp+280h+hObject], 0
0x140003f92  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003f97  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003f9c  mov     esi, eax
0x140003f9e  test    eax, eax
0x140003fa0  jns     short loc_14000400C
0x140003fa2  mov     rcx, [rbp+188h]; this
0x140003fa9  mov     r9d, eax; char *
0x140003fac  mov     edx, 66h ; 'f'; void *
0x140003fb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fb6  mov     rcx, [rbp+188h]; this
0x140003fbd  mov     r9d, esi; char *
0x140003fc0  mov     edx, 6Fh ; 'o'; void *
0x140003fc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fca  mov     rcx, [rbp+188h]; this
0x140003fd1  mov     r9d, esi; char *
0x140003fd4  mov     edx, 12Eh; void *
0x140003fd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fde  test    rdi, rdi
0x140003fe1  jz      short loc_140003FF4
0x140003fe3  mov     rcx, rdi; hMutex
0x140003fe6  call    cs:__imp_ReleaseMutex
0x140003fec  test    eax, eax
0x140003fee  jz      loc_1400041E6
0x140003ff4  mov     rcx, rbx; hObject
0x140003ff7  call    cs:__imp_CloseHandle
0x140003ffd  test    eax, eax
0x140003fff  jz      loc_1400041F8
0x140004005  mov     eax, esi
0x140004007  jmp     loc_1400041A1
0x14000400c  mov     rax, [rsp+280h+hObject]
0x140004011  lea     rcx, ds:0[rax*4]
0x140004019  test    rcx, rcx
0x14000401c  jz      short loc_14000402C
0x14000401e  mov     [r15], rcx
0x140004021  mov     eax, [rcx]
0x140004023  inc     eax
0x140004025  mov     [rcx], eax
0x140004027  jmp     loc_140004177
0x14000402c  mov     rdx, r14; dwBytes
0x14000402f  mov     qword ptr [r15], 0
0x140004036  mov     ecx, 8; dwFlags
0x14000403b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004040  mov     rsi, rax
0x140004043  test    rax, rax
0x140004046  jnz     short loc_140004067
0x140004048  mov     rcx, [rbp+188h]; this
0x14000404f  mov     r14d, 8007000Eh
0x140004055  mov     r9d, r14d; char *
0x140004058  mov     edx, 14Bh; void *
0x14000405d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004062  jmp     loc_1400040F3
0x140004067  xorps   xmm0, xmm0
0x14000406a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140004070  test    sil, 3
0x140004074  jnz     loc_14000420A
0x14000407a  mov     r9, rsi
0x14000407d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140004082  shr     r9, 2; unsigned __int64
0x140004086  lea     rcx, [rsp+280h+hObject]; this
0x14000408b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140004090  mov     r14d, eax
0x140004093  test    eax, eax
0x140004095  jns     loc_140004133
0x14000409b  mov     rcx, [rbp+188h]; this
0x1400040a2  mov     r9d, eax; char *
0x1400040a5  mov     edx, 14Eh; void *
0x1400040aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400040af  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400040b4  test    rcx, rcx
0x1400040b7  jz      short loc_1400040C7
0x1400040b9  call    cs:__imp_CloseHandle
0x1400040bf  test    eax, eax
0x1400040c1  jz      loc_140004210
0x1400040c7  mov     rcx, [rsp+280h+hObject]; hObject
0x1400040cc  test    rcx, rcx
0x1400040cf  jz      short loc_1400040DF
0x1400040d1  call    cs:__imp_CloseHandle
0x1400040d7  test    eax, eax
0x1400040d9  jz      loc_140004222
0x1400040df  call    cs:__imp_GetProcessHeap
0x1400040e5  mov     r8, rsi; lpMem
0x1400040e8  xor     edx, edx; dwFlags
0x1400040ea  mov     rcx, rax; hHeap
0x1400040ed  call    cs:__imp_HeapFree
0x1400040f3  mov     rcx, [rbp+188h]; this
0x1400040fa  mov     r9d, r14d; char *
0x1400040fd  mov     edx, 137h; void *
0x140004102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004107  test    rdi, rdi
0x14000410a  jz      short loc_14000411D
0x14000410c  mov     rcx, rdi; hMutex
0x14000410f  call    cs:__imp_ReleaseMutex
0x140004115  test    eax, eax
0x140004117  jz      loc_140004234
0x14000411d  mov     rcx, rbx; hObject
0x140004120  call    cs:__imp_CloseHandle
0x140004126  test    eax, eax
0x140004128  jz      loc_140004246
0x14000412e  mov     eax, r14d
0x140004131  jmp     short loc_1400041A1
0x140004133  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140004138  xor     edx, edx; Val
0x14000413a  mov     dword ptr [rsi], 1
0x140004140  lea     rcx, [rsi+22h]; void *
0x140004144  mov     [rsi+8], rbx
0x140004148  movdqu  xmmword ptr [rsi+10h], xmm0
0x14000414d  lea     r8d, [rdx+56h]; Size
0x140004151  call    memset_0
0x140004156  xor     edx, edx; Val
0x140004158  mov     word ptr [rsi+20h], 58h ; 'X'
0x14000415e  lea     rcx, [rsi+28h]; void *
0x140004162  mov     dword ptr [rsi+24h], 1
0x140004169  lea     r8d, [rdx+50h]; Size
0x14000416d  call    memset_0
0x140004172  xor     ebx, ebx
0x140004174  mov     [r15], rsi
0x140004177  test    rdi, rdi
0x14000417a  jz      short loc_14000418D
0x14000417c  mov     rcx, rdi; hMutex
0x14000417f  call    cs:__imp_ReleaseMutex
0x140004185  test    eax, eax
0x140004187  jz      loc_140004258
0x14000418d  test    rbx, rbx
0x140004190  jz      short loc_14000419F
0x140004192  mov     rcx, rbx; hObject
0x140004195  call    cs:__imp_CloseHandle
0x14000419b  test    eax, eax
0x14000419d  jz      short loc_1400041C7
0x14000419f  xor     eax, eax
0x1400041a1  mov     rcx, [rbp+180h+var_30]
0x1400041a8  xor     rcx, rsp; StackCookie
0x1400041ab  call    __security_check_cookie
0x1400041b0  mov     rbx, [rsp+280h+arg_10]
0x1400041b8  add     rsp, 260h
0x1400041bf  pop     r15
0x1400041c1  pop     r14
0x1400041c3  pop     rdi
0x1400041c4  pop     rsi
0x1400041c5  pop     rbp
0x1400041c6  retn
0x1400041c7  mov     rcx, [rbp+188h]; this
0x1400041ce  mov     edx, 0A0Bh; void *
0x1400041d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400041d9  mov     rcx, [rbp+188h]; this
0x1400041e0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400041e6  mov     rcx, [rbp+188h]; this
0x1400041ed  mov     edx, 0A15h; void *
0x1400041f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400041f8  mov     rcx, [rbp+188h]; this
0x1400041ff  mov     edx, 0A0Bh; void *
0x140004204  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000420a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004210  mov     rcx, [rbp+188h]; this
0x140004217  mov     edx, 0A0Bh; void *
0x14000421c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004222  mov     rcx, [rbp+188h]; this
0x140004229  mov     edx, 0A0Bh; void *
0x14000422e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004234  mov     rcx, [rbp+188h]; this
0x14000423b  mov     edx, 0A15h; void *
0x140004240  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004246  mov     rcx, [rbp+188h]; this
0x14000424d  mov     edx, 0A0Bh; void *
0x140004252  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004258  mov     rcx, [rbp+188h]; this
0x14000425f  mov     edx, 0A15h; void *
0x140004264  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
