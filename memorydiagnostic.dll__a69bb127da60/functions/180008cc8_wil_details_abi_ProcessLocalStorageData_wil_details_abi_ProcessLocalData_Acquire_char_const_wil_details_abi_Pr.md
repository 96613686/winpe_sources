# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008cc8`
- end: `0x180009090`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000d384`

## callees

- `0x180002e50`
- `0x180003940`
- `0x180008cc8`
- `0x18000a294`
- `0x18000bfdc`
- `0x18000d078`
- `0x18000e6ac`
- `0x1800109d4`
- `0x180013510`
- `0x180014570`
- `0x1800155f4`
- `0x180015604`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180008efe`
- `KERNEL32!GetProcessHeap` at `0x180008efe`
- `KERNEL32!GetCurrentProcessId` at `0x180008d01`
- `KERNEL32!GetCurrentProcessId` at `0x180008d01`
- `KERNEL32!CreateMutexExW` at `0x180008d40`
- `KERNEL32!CreateMutexExW` at `0x180008d40`
- `KERNEL32!CloseHandle` at `0x180008e08`
- `KERNEL32!CloseHandle` at `0x180008ed8`
- `KERNEL32!CloseHandle` at `0x180008ef0`
- `KERNEL32!CloseHandle` at `0x180008f46`
- `KERNEL32!CloseHandle` at `0x180008fbb`
- `KERNEL32!CloseHandle` at `0x180008e08`
- `KERNEL32!CloseHandle` at `0x180008ed8`
- `KERNEL32!CloseHandle` at `0x180008ef0`
- `KERNEL32!CloseHandle` at `0x180008f46`
- `KERNEL32!CloseHandle` at `0x180008fbb`
- `KERNEL32!WaitForSingleObjectEx` at `0x180008d61`
- `KERNEL32!WaitForSingleObjectEx` at `0x180008d61`
- `KERNEL32!ReleaseMutex` at `0x180008df7`
- `KERNEL32!ReleaseMutex` at `0x180008f35`
- `KERNEL32!ReleaseMutex` at `0x180008fa5`
- `KERNEL32!ReleaseMutex` at `0x180008df7`
- `KERNEL32!ReleaseMutex` at `0x180008f35`
- `KERNEL32!ReleaseMutex` at `0x180008fa5`
- `KERNEL32!HeapFree` at `0x180008f0c`
- `KERNEL32!HeapFree` at `0x180008f0c`

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
0x180008cc8  mov     [rsp-8+arg_10], rbx
0x180008ccd  push    rbp
0x180008cce  push    rsi
0x180008ccf  push    rdi
0x180008cd0  push    r14
0x180008cd2  push    r15
0x180008cd4  lea     rbp, [rsp-160h]
0x180008cdc  sub     rsp, 260h
0x180008ce3  mov     rax, cs:__security_cookie
0x180008cea  xor     rax, rsp
0x180008ced  mov     [rbp+180h+var_30], rax
0x180008cf4  mov     r15, rdx
0x180008cf7  mov     qword ptr [rdx], 0
0x180008cfe  mov     rbx, rcx
0x180008d01  call    cs:__imp_GetCurrentProcessId
0x180008d07  mov     r14d, 78h ; 'x'
0x180008d0d  mov     [rsp+280h+var_258], rbx
0x180008d12  mov     r9d, eax
0x180008d15  mov     [rsp+280h+var_260], r14d; int
0x180008d1a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008d21  mov     edx, 104h; unsigned __int64
0x180008d26  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008d2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008d30  mov     r9d, 1F0001h; dwDesiredAccess
0x180008d36  lea     rdx, [rsp+280h+Name]; lpName
0x180008d3b  xor     r8d, r8d; dwFlags
0x180008d3e  xor     ecx, ecx; lpMutexAttributes
0x180008d40  call    cs:__imp_CreateMutexExW
0x180008d46  mov     rbx, rax
0x180008d49  test    rax, rax
0x180008d4c  jnz     short loc_180008D58
0x180008d4e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008d53  jmp     loc_180008FC7
0x180008d58  xor     r8d, r8d; bAlertable
0x180008d5b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008d5e  mov     rcx, rbx; hHandle
0x180008d61  call    cs:__imp_WaitForSingleObjectEx
0x180008d67  cmp     eax, 102h
0x180008d6c  jz      short loc_180008D7E
0x180008d6e  test    eax, 0FFFFFF7Fh
0x180008d73  jnz     loc_180008FFF
0x180008d79  mov     rdi, rbx
0x180008d7c  jmp     short loc_180008D80
0x180008d7e  xor     edi, edi
0x180008d80  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008d85  mov     [rsp+280h+hObject], 0
0x180008d8e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008d93  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008d98  mov     esi, eax
0x180008d9a  test    eax, eax
0x180008d9c  jns     short loc_180008E1D
0x180008d9e  mov     rcx, [rbp+188h]; this
0x180008da5  lea     r8, aWil; "wil"
0x180008dac  mov     r9d, eax; char *
0x180008daf  mov     edx, 66h ; 'f'; void *
0x180008db4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008db9  mov     rcx, [rbp+188h]; this
0x180008dc0  lea     r8, aWil; "wil"
0x180008dc7  mov     r9d, esi; char *
0x180008dca  mov     edx, 6Fh ; 'o'; void *
0x180008dcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008dd4  mov     rcx, [rbp+188h]; this
0x180008ddb  lea     r8, aWil; "wil"
0x180008de2  mov     r9d, esi; char *
0x180008de5  mov     edx, 12Eh; void *
0x180008dea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008def  test    rdi, rdi
0x180008df2  jz      short loc_180008E05
0x180008df4  mov     rcx, rdi; hMutex
0x180008df7  call    cs:__imp_ReleaseMutex
0x180008dfd  test    eax, eax
0x180008dff  jz      loc_18000900C
0x180008e05  mov     rcx, rbx; hObject
0x180008e08  call    cs:__imp_CloseHandle
0x180008e0e  test    eax, eax
0x180008e10  jz      loc_18000901E
0x180008e16  mov     eax, esi
0x180008e18  jmp     loc_180008FC7
0x180008e1d  mov     rax, [rsp+280h+hObject]
0x180008e22  lea     rcx, ds:0[rax*4]
0x180008e2a  test    rcx, rcx
0x180008e2d  jz      short loc_180008E3D
0x180008e2f  mov     [r15], rcx
0x180008e32  mov     eax, [rcx]
0x180008e34  inc     eax
0x180008e36  mov     [rcx], eax
0x180008e38  jmp     loc_180008F9D
0x180008e3d  mov     rdx, r14; dwBytes
0x180008e40  mov     qword ptr [r15], 0
0x180008e47  mov     ecx, 8; dwFlags
0x180008e4c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008e51  mov     rsi, rax
0x180008e54  test    rax, rax
0x180008e57  jnz     short loc_180008E7F
0x180008e59  mov     rcx, [rbp+188h]; this
0x180008e60  lea     r8, aWil; "wil"
0x180008e67  mov     r14d, 8007000Eh
0x180008e6d  mov     edx, 14Bh; void *
0x180008e72  mov     r9d, r14d; char *
0x180008e75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e7a  jmp     loc_180008F12
0x180008e7f  xorps   xmm0, xmm0
0x180008e82  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180008e88  test    sil, 3
0x180008e8c  jnz     loc_180009030
0x180008e92  mov     r9, rsi
0x180008e95  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180008e9a  shr     r9, 2; unsigned __int64
0x180008e9e  lea     rcx, [rsp+280h+hObject]; this
0x180008ea3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180008ea8  mov     r14d, eax
0x180008eab  test    eax, eax
0x180008ead  jns     loc_180008F59
0x180008eb3  mov     rcx, [rbp+188h]; this
0x180008eba  lea     r8, aWil; "wil"
0x180008ec1  mov     r9d, eax; char *
0x180008ec4  mov     edx, 14Eh; void *
0x180008ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ece  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180008ed3  test    rcx, rcx
0x180008ed6  jz      short loc_180008EE6
0x180008ed8  call    cs:__imp_CloseHandle
0x180008ede  test    eax, eax
0x180008ee0  jz      loc_180009036
0x180008ee6  mov     rcx, [rsp+280h+hObject]; hObject
0x180008eeb  test    rcx, rcx
0x180008eee  jz      short loc_180008EFE
0x180008ef0  call    cs:__imp_CloseHandle
0x180008ef6  test    eax, eax
0x180008ef8  jz      loc_180009048
0x180008efe  call    cs:__imp_GetProcessHeap
0x180008f04  mov     r8, rsi; lpMem
0x180008f07  xor     edx, edx; dwFlags
0x180008f09  mov     rcx, rax; hHeap
0x180008f0c  call    cs:__imp_HeapFree
0x180008f12  mov     rcx, [rbp+188h]; this
0x180008f19  lea     r8, aWil; "wil"
0x180008f20  mov     r9d, r14d; char *
0x180008f23  mov     edx, 137h; void *
0x180008f28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f2d  test    rdi, rdi
0x180008f30  jz      short loc_180008F43
0x180008f32  mov     rcx, rdi; hMutex
0x180008f35  call    cs:__imp_ReleaseMutex
0x180008f3b  test    eax, eax
0x180008f3d  jz      loc_18000905A
0x180008f43  mov     rcx, rbx; hObject
0x180008f46  call    cs:__imp_CloseHandle
0x180008f4c  test    eax, eax
0x180008f4e  jz      loc_18000906C
0x180008f54  mov     eax, r14d
0x180008f57  jmp     short loc_180008FC7
0x180008f59  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008f5e  xor     edx, edx; Val
0x180008f60  mov     dword ptr [rsi], 1
0x180008f66  lea     rcx, [rsi+22h]; void *
0x180008f6a  mov     [rsi+8], rbx
0x180008f6e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180008f73  lea     r8d, [rdx+56h]; Size
0x180008f77  call    memset_0
0x180008f7c  xor     edx, edx; Val
0x180008f7e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180008f84  lea     rcx, [rsi+28h]; void *
0x180008f88  mov     dword ptr [rsi+24h], 1
0x180008f8f  lea     r8d, [rdx+50h]; Size
0x180008f93  call    memset_0
0x180008f98  xor     ebx, ebx
0x180008f9a  mov     [r15], rsi
0x180008f9d  test    rdi, rdi
0x180008fa0  jz      short loc_180008FB3
0x180008fa2  mov     rcx, rdi; hMutex
0x180008fa5  call    cs:__imp_ReleaseMutex
0x180008fab  test    eax, eax
0x180008fad  jz      loc_18000907E
0x180008fb3  test    rbx, rbx
0x180008fb6  jz      short loc_180008FC5
0x180008fb8  mov     rcx, rbx; hObject
0x180008fbb  call    cs:__imp_CloseHandle
0x180008fc1  test    eax, eax
0x180008fc3  jz      short loc_180008FED
0x180008fc5  xor     eax, eax
0x180008fc7  mov     rcx, [rbp+180h+var_30]
0x180008fce  xor     rcx, rsp; StackCookie
0x180008fd1  call    __security_check_cookie
0x180008fd6  mov     rbx, [rsp+280h+arg_10]
0x180008fde  add     rsp, 260h
0x180008fe5  pop     r15
0x180008fe7  pop     r14
0x180008fe9  pop     rdi
0x180008fea  pop     rsi
0x180008feb  pop     rbp
0x180008fec  retn
0x180008fed  mov     rcx, [rbp+188h]; this
0x180008ff4  mov     edx, 0A0Bh; void *
0x180008ff9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008fff  mov     rcx, [rbp+188h]; this
0x180009006  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000900c  mov     rcx, [rbp+188h]; this
0x180009013  mov     edx, 0A15h; void *
0x180009018  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000901e  mov     rcx, [rbp+188h]; this
0x180009025  mov     edx, 0A0Bh; void *
0x18000902a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009030  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009036  mov     rcx, [rbp+188h]; this
0x18000903d  mov     edx, 0A0Bh; void *
0x180009042  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009048  mov     rcx, [rbp+188h]; this
0x18000904f  mov     edx, 0A0Bh; void *
0x180009054  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000905a  mov     rcx, [rbp+188h]; this
0x180009061  mov     edx, 0A15h; void *
0x180009066  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000906c  mov     rcx, [rbp+188h]; this
0x180009073  mov     edx, 0A0Bh; void *
0x180009078  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000907e  mov     rcx, [rbp+188h]; this
0x180009085  mov     edx, 0A15h; void *
0x18000908a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
