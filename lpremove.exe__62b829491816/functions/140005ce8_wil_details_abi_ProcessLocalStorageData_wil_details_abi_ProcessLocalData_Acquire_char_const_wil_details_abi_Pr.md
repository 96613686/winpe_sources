# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140005ce8`
- end: `0x1400060b0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140007ac0`

## callees

- `0x140002190`
- `0x140002c2c`
- `0x140005ce8`
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

- `KERNEL32!GetProcessHeap` at `0x140005f1e`
- `KERNEL32!GetProcessHeap` at `0x140005f1e`
- `KERNEL32!HeapFree` at `0x140005f2c`
- `KERNEL32!HeapFree` at `0x140005f2c`
- `KERNEL32!ReleaseMutex` at `0x140005e17`
- `KERNEL32!ReleaseMutex` at `0x140005f55`
- `KERNEL32!ReleaseMutex` at `0x140005fc5`
- `KERNEL32!ReleaseMutex` at `0x140005e17`
- `KERNEL32!ReleaseMutex` at `0x140005f55`
- `KERNEL32!ReleaseMutex` at `0x140005fc5`
- `KERNEL32!WaitForSingleObjectEx` at `0x140005d81`
- `KERNEL32!WaitForSingleObjectEx` at `0x140005d81`
- `KERNEL32!GetCurrentProcessId` at `0x140005d21`
- `KERNEL32!GetCurrentProcessId` at `0x140005d21`
- `KERNEL32!CreateMutexExW` at `0x140005d60`
- `KERNEL32!CreateMutexExW` at `0x140005d60`
- `KERNEL32!CloseHandle` at `0x140005e28`
- `KERNEL32!CloseHandle` at `0x140005ef8`
- `KERNEL32!CloseHandle` at `0x140005f10`
- `KERNEL32!CloseHandle` at `0x140005f66`
- `KERNEL32!CloseHandle` at `0x140005fdb`
- `KERNEL32!CloseHandle` at `0x140005e28`
- `KERNEL32!CloseHandle` at `0x140005ef8`
- `KERNEL32!CloseHandle` at `0x140005f10`
- `KERNEL32!CloseHandle` at `0x140005f66`
- `KERNEL32!CloseHandle` at `0x140005fdb`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x140005ce8  mov     [rsp-8+arg_10], rbx
0x140005ced  push    rbp
0x140005cee  push    rsi
0x140005cef  push    rdi
0x140005cf0  push    r14
0x140005cf2  push    r15
0x140005cf4  lea     rbp, [rsp-160h]
0x140005cfc  sub     rsp, 260h
0x140005d03  mov     rax, cs:__security_cookie
0x140005d0a  xor     rax, rsp
0x140005d0d  mov     [rbp+180h+var_30], rax
0x140005d14  mov     r15, rdx
0x140005d17  mov     qword ptr [rdx], 0
0x140005d1e  mov     rbx, rcx
0x140005d21  call    cs:__imp_GetCurrentProcessId
0x140005d27  mov     r14d, 78h ; 'x'
0x140005d2d  mov     [rsp+280h+var_258], rbx
0x140005d32  mov     r9d, eax
0x140005d35  mov     [rsp+280h+var_260], r14d; int
0x140005d3a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140005d41  mov     edx, 104h; unsigned __int64
0x140005d46  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005d4b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005d50  mov     r9d, 1F0001h; dwDesiredAccess
0x140005d56  lea     rdx, [rsp+280h+Name]; lpName
0x140005d5b  xor     r8d, r8d; dwFlags
0x140005d5e  xor     ecx, ecx; lpMutexAttributes
0x140005d60  call    cs:__imp_CreateMutexExW
0x140005d66  mov     rbx, rax
0x140005d69  test    rax, rax
0x140005d6c  jnz     short loc_140005D78
0x140005d6e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005d73  jmp     loc_140005FE7
0x140005d78  xor     r8d, r8d; bAlertable
0x140005d7b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005d7e  mov     rcx, rbx; hHandle
0x140005d81  call    cs:__imp_WaitForSingleObjectEx
0x140005d87  cmp     eax, 102h
0x140005d8c  jz      short loc_140005D9E
0x140005d8e  test    eax, 0FFFFFF7Fh
0x140005d93  jnz     loc_14000601F
0x140005d99  mov     rdi, rbx
0x140005d9c  jmp     short loc_140005DA0
0x140005d9e  xor     edi, edi
0x140005da0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140005da5  mov     [rsp+280h+hObject], 0
0x140005dae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005db3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140005db8  mov     esi, eax
0x140005dba  test    eax, eax
0x140005dbc  jns     short loc_140005E3D
0x140005dbe  mov     rcx, [rbp+188h]; this
0x140005dc5  lea     r8, aWil; "wil"
0x140005dcc  mov     r9d, eax; char *
0x140005dcf  mov     edx, 66h ; 'f'; void *
0x140005dd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005dd9  mov     rcx, [rbp+188h]; this
0x140005de0  lea     r8, aWil; "wil"
0x140005de7  mov     r9d, esi; char *
0x140005dea  mov     edx, 6Fh ; 'o'; void *
0x140005def  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005df4  mov     rcx, [rbp+188h]; this
0x140005dfb  lea     r8, aWil; "wil"
0x140005e02  mov     r9d, esi; char *
0x140005e05  mov     edx, 12Eh; void *
0x140005e0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005e0f  test    rdi, rdi
0x140005e12  jz      short loc_140005E25
0x140005e14  mov     rcx, rdi; hMutex
0x140005e17  call    cs:__imp_ReleaseMutex
0x140005e1d  test    eax, eax
0x140005e1f  jz      loc_14000602C
0x140005e25  mov     rcx, rbx; hObject
0x140005e28  call    cs:__imp_CloseHandle
0x140005e2e  test    eax, eax
0x140005e30  jz      loc_14000603E
0x140005e36  mov     eax, esi
0x140005e38  jmp     loc_140005FE7
0x140005e3d  mov     rax, [rsp+280h+hObject]
0x140005e42  lea     rcx, ds:0[rax*4]
0x140005e4a  test    rcx, rcx
0x140005e4d  jz      short loc_140005E5D
0x140005e4f  mov     [r15], rcx
0x140005e52  mov     eax, [rcx]
0x140005e54  inc     eax
0x140005e56  mov     [rcx], eax
0x140005e58  jmp     loc_140005FBD
0x140005e5d  mov     rdx, r14; dwBytes
0x140005e60  mov     qword ptr [r15], 0
0x140005e67  mov     ecx, 8; dwFlags
0x140005e6c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005e71  mov     rsi, rax
0x140005e74  test    rax, rax
0x140005e77  jnz     short loc_140005E9F
0x140005e79  mov     rcx, [rbp+188h]; this
0x140005e80  lea     r8, aWil; "wil"
0x140005e87  mov     r14d, 8007000Eh
0x140005e8d  mov     edx, 14Bh; void *
0x140005e92  mov     r9d, r14d; char *
0x140005e95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005e9a  jmp     loc_140005F32
0x140005e9f  xorps   xmm0, xmm0
0x140005ea2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140005ea8  test    sil, 3
0x140005eac  jnz     loc_140006050
0x140005eb2  mov     r9, rsi
0x140005eb5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140005eba  shr     r9, 2; unsigned __int64
0x140005ebe  lea     rcx, [rsp+280h+hObject]; this
0x140005ec3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140005ec8  mov     r14d, eax
0x140005ecb  test    eax, eax
0x140005ecd  jns     loc_140005F79
0x140005ed3  mov     rcx, [rbp+188h]; this
0x140005eda  lea     r8, aWil; "wil"
0x140005ee1  mov     r9d, eax; char *
0x140005ee4  mov     edx, 14Eh; void *
0x140005ee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005eee  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140005ef3  test    rcx, rcx
0x140005ef6  jz      short loc_140005F06
0x140005ef8  call    cs:__imp_CloseHandle
0x140005efe  test    eax, eax
0x140005f00  jz      loc_140006056
0x140005f06  mov     rcx, [rsp+280h+hObject]; hObject
0x140005f0b  test    rcx, rcx
0x140005f0e  jz      short loc_140005F1E
0x140005f10  call    cs:__imp_CloseHandle
0x140005f16  test    eax, eax
0x140005f18  jz      loc_140006068
0x140005f1e  call    cs:__imp_GetProcessHeap
0x140005f24  mov     r8, rsi; lpMem
0x140005f27  xor     edx, edx; dwFlags
0x140005f29  mov     rcx, rax; hHeap
0x140005f2c  call    cs:__imp_HeapFree
0x140005f32  mov     rcx, [rbp+188h]; this
0x140005f39  lea     r8, aWil; "wil"
0x140005f40  mov     r9d, r14d; char *
0x140005f43  mov     edx, 137h; void *
0x140005f48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005f4d  test    rdi, rdi
0x140005f50  jz      short loc_140005F63
0x140005f52  mov     rcx, rdi; hMutex
0x140005f55  call    cs:__imp_ReleaseMutex
0x140005f5b  test    eax, eax
0x140005f5d  jz      loc_14000607A
0x140005f63  mov     rcx, rbx; hObject
0x140005f66  call    cs:__imp_CloseHandle
0x140005f6c  test    eax, eax
0x140005f6e  jz      loc_14000608C
0x140005f74  mov     eax, r14d
0x140005f77  jmp     short loc_140005FE7
0x140005f79  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140005f7e  xor     edx, edx; Val
0x140005f80  mov     dword ptr [rsi], 1
0x140005f86  lea     rcx, [rsi+22h]; void *
0x140005f8a  mov     [rsi+8], rbx
0x140005f8e  movdqu  xmmword ptr [rsi+10h], xmm0
0x140005f93  lea     r8d, [rdx+56h]; Size
0x140005f97  call    memset_0
0x140005f9c  xor     edx, edx; Val
0x140005f9e  mov     word ptr [rsi+20h], 58h ; 'X'
0x140005fa4  lea     rcx, [rsi+28h]; void *
0x140005fa8  mov     dword ptr [rsi+24h], 1
0x140005faf  lea     r8d, [rdx+50h]; Size
0x140005fb3  call    memset_0
0x140005fb8  xor     ebx, ebx
0x140005fba  mov     [r15], rsi
0x140005fbd  test    rdi, rdi
0x140005fc0  jz      short loc_140005FD3
0x140005fc2  mov     rcx, rdi; hMutex
0x140005fc5  call    cs:__imp_ReleaseMutex
0x140005fcb  test    eax, eax
0x140005fcd  jz      loc_14000609E
0x140005fd3  test    rbx, rbx
0x140005fd6  jz      short loc_140005FE5
0x140005fd8  mov     rcx, rbx; hObject
0x140005fdb  call    cs:__imp_CloseHandle
0x140005fe1  test    eax, eax
0x140005fe3  jz      short loc_14000600D
0x140005fe5  xor     eax, eax
0x140005fe7  mov     rcx, [rbp+180h+var_30]
0x140005fee  xor     rcx, rsp; StackCookie
0x140005ff1  call    __security_check_cookie
0x140005ff6  mov     rbx, [rsp+280h+arg_10]
0x140005ffe  add     rsp, 260h
0x140006005  pop     r15
0x140006007  pop     r14
0x140006009  pop     rdi
0x14000600a  pop     rsi
0x14000600b  pop     rbp
0x14000600c  retn
0x14000600d  mov     rcx, [rbp+188h]; this
0x140006014  mov     edx, 0A0Bh; void *
0x140006019  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000601f  mov     rcx, [rbp+188h]; this
0x140006026  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000602c  mov     rcx, [rbp+188h]; this
0x140006033  mov     edx, 0A15h; void *
0x140006038  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000603e  mov     rcx, [rbp+188h]; this
0x140006045  mov     edx, 0A0Bh; void *
0x14000604a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006050  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140006056  mov     rcx, [rbp+188h]; this
0x14000605d  mov     edx, 0A0Bh; void *
0x140006062  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006068  mov     rcx, [rbp+188h]; this
0x14000606f  mov     edx, 0A0Bh; void *
0x140006074  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000607a  mov     rcx, [rbp+188h]; this
0x140006081  mov     edx, 0A15h; void *
0x140006086  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000608c  mov     rcx, [rbp+188h]; this
0x140006093  mov     edx, 0A0Bh; void *
0x140006098  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000609e  mov     rcx, [rbp+188h]; this
0x1400060a5  mov     edx, 0A15h; void *
0x1400060aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
