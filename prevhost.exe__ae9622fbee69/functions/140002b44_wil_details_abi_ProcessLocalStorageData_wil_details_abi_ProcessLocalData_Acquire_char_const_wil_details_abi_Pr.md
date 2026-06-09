# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140002b44`
- end: `0x140002ee2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140003c2c`

## callees

- `0x140001470`
- `0x140001e52`
- `0x140002b44`
- `0x140002f74`
- `0x140003364`
- `0x1400039c8`
- `0x1400047f8`
- `0x140004d54`
- `0x1400050b0`
- `0x140005298`
- `0x14000564c`
- `0x14000565c`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x140002c5e`
- `KERNEL32!ReleaseMutex` at `0x140002d87`
- `KERNEL32!ReleaseMutex` at `0x140002df7`
- `KERNEL32!ReleaseMutex` at `0x140002c5e`
- `KERNEL32!ReleaseMutex` at `0x140002d87`
- `KERNEL32!ReleaseMutex` at `0x140002df7`
- `KERNEL32!WaitForSingleObjectEx` at `0x140002bdd`
- `KERNEL32!WaitForSingleObjectEx` at `0x140002bdd`
- `KERNEL32!CloseHandle` at `0x140002c6f`
- `KERNEL32!CloseHandle` at `0x140002d31`
- `KERNEL32!CloseHandle` at `0x140002d49`
- `KERNEL32!CloseHandle` at `0x140002d98`
- `KERNEL32!CloseHandle` at `0x140002e0d`
- `KERNEL32!CloseHandle` at `0x140002c6f`
- `KERNEL32!CloseHandle` at `0x140002d31`
- `KERNEL32!CloseHandle` at `0x140002d49`
- `KERNEL32!CloseHandle` at `0x140002d98`
- `KERNEL32!CloseHandle` at `0x140002e0d`
- `KERNEL32!CreateMutexExW` at `0x140002bbc`
- `KERNEL32!CreateMutexExW` at `0x140002bbc`
- `KERNEL32!GetCurrentProcessId` at `0x140002b7d`
- `KERNEL32!GetCurrentProcessId` at `0x140002b7d`
- `KERNEL32!GetProcessHeap` at `0x140002d57`
- `KERNEL32!GetProcessHeap` at `0x140002d57`
- `KERNEL32!HeapFree` at `0x140002d65`
- `KERNEL32!HeapFree` at `0x140002d65`

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
0x140002b44  mov     [rsp-8+arg_10], rbx
0x140002b49  push    rbp
0x140002b4a  push    rsi
0x140002b4b  push    rdi
0x140002b4c  push    r14
0x140002b4e  push    r15
0x140002b50  lea     rbp, [rsp-160h]
0x140002b58  sub     rsp, 260h
0x140002b5f  mov     rax, cs:__security_cookie
0x140002b66  xor     rax, rsp
0x140002b69  mov     [rbp+180h+var_30], rax
0x140002b70  mov     r15, rdx
0x140002b73  mov     qword ptr [rdx], 0
0x140002b7a  mov     rbx, rcx
0x140002b7d  call    cs:__imp_GetCurrentProcessId
0x140002b83  mov     r14d, 78h ; 'x'
0x140002b89  mov     [rsp+280h+var_258], rbx
0x140002b8e  mov     r9d, eax
0x140002b91  mov     [rsp+280h+var_260], r14d; int
0x140002b96  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140002b9d  mov     edx, 104h; unsigned __int64
0x140002ba2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002ba7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002bac  mov     r9d, 1F0001h; dwDesiredAccess
0x140002bb2  lea     rdx, [rsp+280h+Name]; lpName
0x140002bb7  xor     r8d, r8d; dwFlags
0x140002bba  xor     ecx, ecx; lpMutexAttributes
0x140002bbc  call    cs:__imp_CreateMutexExW
0x140002bc2  mov     rbx, rax
0x140002bc5  test    rax, rax
0x140002bc8  jnz     short loc_140002BD4
0x140002bca  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002bcf  jmp     loc_140002E19
0x140002bd4  xor     r8d, r8d; bAlertable
0x140002bd7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140002bda  mov     rcx, rbx; hHandle
0x140002bdd  call    cs:__imp_WaitForSingleObjectEx
0x140002be3  cmp     eax, 102h
0x140002be8  jz      short loc_140002BFA
0x140002bea  test    eax, 0FFFFFF7Fh
0x140002bef  jnz     loc_140002E51
0x140002bf5  mov     rdi, rbx
0x140002bf8  jmp     short loc_140002BFC
0x140002bfa  xor     edi, edi
0x140002bfc  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140002c01  mov     [rsp+280h+hObject], 0
0x140002c0a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002c0f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140002c14  mov     esi, eax
0x140002c16  test    eax, eax
0x140002c18  jns     short loc_140002C84
0x140002c1a  mov     rcx, [rbp+188h]; this
0x140002c21  mov     r9d, eax; char *
0x140002c24  mov     edx, 66h ; 'f'; void *
0x140002c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002c2e  mov     rcx, [rbp+188h]; this
0x140002c35  mov     r9d, esi; char *
0x140002c38  mov     edx, 6Fh ; 'o'; void *
0x140002c3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002c42  mov     rcx, [rbp+188h]; this
0x140002c49  mov     r9d, esi; char *
0x140002c4c  mov     edx, 12Eh; void *
0x140002c51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002c56  test    rdi, rdi
0x140002c59  jz      short loc_140002C6C
0x140002c5b  mov     rcx, rdi; hMutex
0x140002c5e  call    cs:__imp_ReleaseMutex
0x140002c64  test    eax, eax
0x140002c66  jz      loc_140002E5E
0x140002c6c  mov     rcx, rbx; hObject
0x140002c6f  call    cs:__imp_CloseHandle
0x140002c75  test    eax, eax
0x140002c77  jz      loc_140002E70
0x140002c7d  mov     eax, esi
0x140002c7f  jmp     loc_140002E19
0x140002c84  mov     rax, [rsp+280h+hObject]
0x140002c89  lea     rcx, ds:0[rax*4]
0x140002c91  test    rcx, rcx
0x140002c94  jz      short loc_140002CA4
0x140002c96  mov     [r15], rcx
0x140002c99  mov     eax, [rcx]
0x140002c9b  inc     eax
0x140002c9d  mov     [rcx], eax
0x140002c9f  jmp     loc_140002DEF
0x140002ca4  mov     rdx, r14; dwBytes
0x140002ca7  mov     qword ptr [r15], 0
0x140002cae  mov     ecx, 8; dwFlags
0x140002cb3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140002cb8  mov     rsi, rax
0x140002cbb  test    rax, rax
0x140002cbe  jnz     short loc_140002CDF
0x140002cc0  mov     rcx, [rbp+188h]; this
0x140002cc7  mov     r14d, 8007000Eh
0x140002ccd  mov     r9d, r14d; char *
0x140002cd0  mov     edx, 14Bh; void *
0x140002cd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002cda  jmp     loc_140002D6B
0x140002cdf  xorps   xmm0, xmm0
0x140002ce2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140002ce8  test    sil, 3
0x140002cec  jnz     loc_140002E82
0x140002cf2  mov     r9, rsi
0x140002cf5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140002cfa  shr     r9, 2; unsigned __int64
0x140002cfe  lea     rcx, [rsp+280h+hObject]; this
0x140002d03  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140002d08  mov     r14d, eax
0x140002d0b  test    eax, eax
0x140002d0d  jns     loc_140002DAB
0x140002d13  mov     rcx, [rbp+188h]; this
0x140002d1a  mov     r9d, eax; char *
0x140002d1d  mov     edx, 14Eh; void *
0x140002d22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002d27  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140002d2c  test    rcx, rcx
0x140002d2f  jz      short loc_140002D3F
0x140002d31  call    cs:__imp_CloseHandle
0x140002d37  test    eax, eax
0x140002d39  jz      loc_140002E88
0x140002d3f  mov     rcx, [rsp+280h+hObject]; hObject
0x140002d44  test    rcx, rcx
0x140002d47  jz      short loc_140002D57
0x140002d49  call    cs:__imp_CloseHandle
0x140002d4f  test    eax, eax
0x140002d51  jz      loc_140002E9A
0x140002d57  call    cs:__imp_GetProcessHeap
0x140002d5d  mov     r8, rsi; lpMem
0x140002d60  xor     edx, edx; dwFlags
0x140002d62  mov     rcx, rax; hHeap
0x140002d65  call    cs:__imp_HeapFree
0x140002d6b  mov     rcx, [rbp+188h]; this
0x140002d72  mov     r9d, r14d; char *
0x140002d75  mov     edx, 137h; void *
0x140002d7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002d7f  test    rdi, rdi
0x140002d82  jz      short loc_140002D95
0x140002d84  mov     rcx, rdi; hMutex
0x140002d87  call    cs:__imp_ReleaseMutex
0x140002d8d  test    eax, eax
0x140002d8f  jz      loc_140002EAC
0x140002d95  mov     rcx, rbx; hObject
0x140002d98  call    cs:__imp_CloseHandle
0x140002d9e  test    eax, eax
0x140002da0  jz      loc_140002EBE
0x140002da6  mov     eax, r14d
0x140002da9  jmp     short loc_140002E19
0x140002dab  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140002db0  xor     edx, edx; Val
0x140002db2  mov     dword ptr [rsi], 1
0x140002db8  lea     rcx, [rsi+22h]; void *
0x140002dbc  mov     [rsi+8], rbx
0x140002dc0  movdqu  xmmword ptr [rsi+10h], xmm0
0x140002dc5  lea     r8d, [rdx+56h]; Size
0x140002dc9  call    memset_0
0x140002dce  xor     edx, edx; Val
0x140002dd0  mov     word ptr [rsi+20h], 58h ; 'X'
0x140002dd6  lea     rcx, [rsi+28h]; void *
0x140002dda  mov     dword ptr [rsi+24h], 1
0x140002de1  lea     r8d, [rdx+50h]; Size
0x140002de5  call    memset_0
0x140002dea  xor     ebx, ebx
0x140002dec  mov     [r15], rsi
0x140002def  test    rdi, rdi
0x140002df2  jz      short loc_140002E05
0x140002df4  mov     rcx, rdi; hMutex
0x140002df7  call    cs:__imp_ReleaseMutex
0x140002dfd  test    eax, eax
0x140002dff  jz      loc_140002ED0
0x140002e05  test    rbx, rbx
0x140002e08  jz      short loc_140002E17
0x140002e0a  mov     rcx, rbx; hObject
0x140002e0d  call    cs:__imp_CloseHandle
0x140002e13  test    eax, eax
0x140002e15  jz      short loc_140002E3F
0x140002e17  xor     eax, eax
0x140002e19  mov     rcx, [rbp+180h+var_30]
0x140002e20  xor     rcx, rsp; StackCookie
0x140002e23  call    __security_check_cookie
0x140002e28  mov     rbx, [rsp+280h+arg_10]
0x140002e30  add     rsp, 260h
0x140002e37  pop     r15
0x140002e39  pop     r14
0x140002e3b  pop     rdi
0x140002e3c  pop     rsi
0x140002e3d  pop     rbp
0x140002e3e  retn
0x140002e3f  mov     rcx, [rbp+188h]; this
0x140002e46  mov     edx, 0A0Bh; void *
0x140002e4b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002e51  mov     rcx, [rbp+188h]; this
0x140002e58  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140002e5e  mov     rcx, [rbp+188h]; this
0x140002e65  mov     edx, 0A15h; void *
0x140002e6a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002e70  mov     rcx, [rbp+188h]; this
0x140002e77  mov     edx, 0A0Bh; void *
0x140002e7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002e82  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002e88  mov     rcx, [rbp+188h]; this
0x140002e8f  mov     edx, 0A0Bh; void *
0x140002e94  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002e9a  mov     rcx, [rbp+188h]; this
0x140002ea1  mov     edx, 0A0Bh; void *
0x140002ea6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002eac  mov     rcx, [rbp+188h]; this
0x140002eb3  mov     edx, 0A15h; void *
0x140002eb8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002ebe  mov     rcx, [rbp+188h]; this
0x140002ec5  mov     edx, 0A0Bh; void *
0x140002eca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002ed0  mov     rcx, [rbp+188h]; this
0x140002ed7  mov     edx, 0A15h; void *
0x140002edc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
