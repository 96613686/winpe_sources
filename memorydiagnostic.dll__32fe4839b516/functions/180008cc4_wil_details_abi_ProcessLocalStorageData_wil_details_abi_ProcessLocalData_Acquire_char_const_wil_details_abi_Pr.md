# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008cc4`
- end: `0x1800090af`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000dafc`

## callees

- `0x1800026b0`
- `0x180003374`
- `0x1800084d8`
- `0x180008cc4`
- `0x18000a490`
- `0x18000c960`
- `0x18000d7a8`
- `0x18000efd0`
- `0x1800113a4`
- `0x180014060`
- `0x1800152b8`
- `0x1800162e8`
- `0x1800188bc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180008cfa`
- `KERNEL32!GetCurrentProcessId` at `0x180008cfa`
- `KERNEL32!GetProcessHeap` at `0x180008ef9`
- `KERNEL32!GetProcessHeap` at `0x180008ef9`
- `KERNEL32!CreateMutexExW` at `0x180008d45`
- `KERNEL32!CreateMutexExW` at `0x180008d45`
- `KERNEL32!CloseHandle` at `0x180008e2f`
- `KERNEL32!CloseHandle` at `0x180008f58`
- `KERNEL32!CloseHandle` at `0x180008ffd`
- `KERNEL32!CloseHandle` at `0x180008e2f`
- `KERNEL32!CloseHandle` at `0x180008f58`
- `KERNEL32!CloseHandle` at `0x180008ffd`
- `KERNEL32!WaitForSingleObjectEx` at `0x180008d7b`
- `KERNEL32!WaitForSingleObjectEx` at `0x180008d7b`
- `KERNEL32!ReleaseMutex` at `0x180008e18`
- `KERNEL32!ReleaseMutex` at `0x180008f3c`
- `KERNEL32!ReleaseMutex` at `0x180008fe1`
- `KERNEL32!ReleaseMutex` at `0x180008e18`
- `KERNEL32!ReleaseMutex` at `0x180008f3c`
- `KERNEL32!ReleaseMutex` at `0x180008fe1`
- `KERNEL32!HeapFree` at `0x180008f0d`
- `KERNEL32!HeapFree` at `0x180008f0d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rsi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // edi
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  HANDLE v21; // rbx
  _QWORD *v22; // rax
  _QWORD *v23; // rdi
  unsigned int v24; // r14d
  int v25; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v41; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
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
  v42 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v42, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)v15, v37);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, (unsigned int)"wil", (const char *)v15, v38);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v42);
  if ( 4 * v42 )
  {
    *a2 = v20;
    v21 = hHandle;
    *(_DWORD *)*a2 = *v20 + 1;
    goto LABEL_24;
  }
  *a2 = 0;
  v22 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v23 = v22;
  if ( v22 )
  {
    v41 = 0;
    v25 = wil::details_abi::SemaphoreValue::CreateFromPointer(
            (wil::details_abi::SemaphoreValue *)&v41,
            (char *)Name,
            (unsigned __int64)v22);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v31 = v41;
      v23[1] = v6;
      v21 = 0;
      v23[2] = v31;
      v32 = *((_QWORD *)&v41 + 1);
      v41 = 0u;
      *(_DWORD *)v23 = 1;
      hHandle = 0;
      v23[3] = v32;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      *a2 = v23;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v41);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v33, v34);
      if ( v21 && !CloseHandle(v21) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v35, v36);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v41);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, (unsigned int)"wil", (const char *)v24, v39);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v27, v28);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v29, v30);
  return v24;
}

```

## disassembly

```asm
0x180008cc4  mov     [rsp-8+arg_10], rbx
0x180008cc9  push    rbp
0x180008cca  push    rsi
0x180008ccb  push    rdi
0x180008ccc  push    r14
0x180008cce  push    r15
0x180008cd0  lea     rbp, [rsp-170h]
0x180008cd8  sub     rsp, 270h
0x180008cdf  mov     rax, cs:__security_cookie
0x180008ce6  xor     rax, rsp
0x180008ce9  mov     [rbp+190h+var_30], rax
0x180008cf0  and     qword ptr [rdx], 0
0x180008cf4  mov     r15, rdx
0x180008cf7  mov     rbx, rcx
0x180008cfa  call    cs:__imp_GetCurrentProcessId
0x180008d01  nop     dword ptr [rax+rax+00h]
0x180008d06  mov     r14d, 78h ; 'x'
0x180008d0c  mov     [rsp+290h+var_268], rbx
0x180008d11  mov     r9d, eax
0x180008d14  mov     [rsp+290h+var_270], r14d; int
0x180008d19  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008d20  mov     edx, 104h; unsigned __int64
0x180008d25  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180008d2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008d2f  and     [rsp+290h+hHandle], 0
0x180008d35  lea     rdx, [rsp+290h+Name]; lpName
0x180008d3a  mov     r9d, 1F0001h; dwDesiredAccess
0x180008d40  xor     r8d, r8d; dwFlags
0x180008d43  xor     ecx, ecx; lpMutexAttributes
0x180008d45  call    cs:__imp_CreateMutexExW
0x180008d4c  nop     dword ptr [rax+rax+00h]
0x180008d51  mov     rdx, rax
0x180008d54  lea     rcx, [rsp+290h+hHandle]
0x180008d59  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008d5e  mov     rbx, [rsp+290h+hHandle]
0x180008d63  test    rbx, rbx
0x180008d66  jnz     short loc_180008D72
0x180008d68  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008d6d  jmp     loc_18000900F
0x180008d72  xor     r8d, r8d; bAlertable
0x180008d75  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008d78  mov     rcx, rbx; hHandle
0x180008d7b  call    cs:__imp_WaitForSingleObjectEx
0x180008d82  nop     dword ptr [rax+rax+00h]
0x180008d87  cmp     eax, 102h
0x180008d8c  jz      short loc_180008D9E
0x180008d8e  test    eax, 0FFFFFF7Fh
0x180008d93  jnz     loc_180009048
0x180008d99  mov     rsi, rbx
0x180008d9c  jmp     short loc_180008DA0
0x180008d9e  xor     esi, esi
0x180008da0  and     [rsp+290h+var_248], 0
0x180008da6  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x180008dab  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180008db0  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008db5  mov     edi, eax
0x180008db7  test    eax, eax
0x180008db9  jns     loc_180008E4A
0x180008dbf  mov     rcx, [rbp+198h]; this
0x180008dc6  lea     r8, aWil; "wil"
0x180008dcd  mov     r9d, eax; char *
0x180008dd0  mov     edx, 64h ; 'd'; void *
0x180008dd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008dda  mov     rcx, [rbp+198h]; this
0x180008de1  lea     r8, aWil; "wil"
0x180008de8  mov     r9d, edi; char *
0x180008deb  mov     edx, 6Dh ; 'm'; void *
0x180008df0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008df5  mov     rcx, [rbp+198h]; this
0x180008dfc  lea     r8, aWil; "wil"
0x180008e03  mov     r9d, edi; char *
0x180008e06  mov     edx, 12Bh; void *
0x180008e0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e10  test    rsi, rsi
0x180008e13  jz      short loc_180008E2C
0x180008e15  mov     rcx, rsi; hMutex
0x180008e18  call    cs:__imp_ReleaseMutex
0x180008e1f  nop     dword ptr [rax+rax+00h]
0x180008e24  test    eax, eax
0x180008e26  jz      loc_180009055
0x180008e2c  mov     rcx, rbx; hObject
0x180008e2f  call    cs:__imp_CloseHandle
0x180008e36  nop     dword ptr [rax+rax+00h]
0x180008e3b  test    eax, eax
0x180008e3d  jz      loc_180009067
0x180008e43  mov     eax, edi
0x180008e45  jmp     loc_18000900F
0x180008e4a  mov     rax, [rsp+290h+var_248]
0x180008e4f  lea     rcx, ds:0[rax*4]
0x180008e57  test    rcx, rcx
0x180008e5a  jz      short loc_180008E72
0x180008e5c  mov     [r15], rcx
0x180008e5f  mov     ecx, [rcx]
0x180008e61  mov     rax, [r15]
0x180008e64  inc     ecx
0x180008e66  mov     rbx, [rsp+290h+hHandle]
0x180008e6b  mov     [rax], ecx
0x180008e6d  jmp     loc_180008FD9
0x180008e72  and     qword ptr [r15], 0
0x180008e76  mov     rdx, r14; dwBytes
0x180008e79  mov     ecx, 8; dwFlags
0x180008e7e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008e83  mov     rdi, rax
0x180008e86  test    rax, rax
0x180008e89  jnz     short loc_180008EAE
0x180008e8b  mov     rcx, [rbp+198h]; this
0x180008e92  lea     r8, aWil; "wil"
0x180008e99  mov     r14d, 8007000Eh
0x180008e9f  mov     edx, 148h; void *
0x180008ea4  mov     r9d, r14d; char *
0x180008ea7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008eac  jmp     short loc_180008F19
0x180008eae  xorps   xmm0, xmm0
0x180008eb1  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180008eb6  mov     r8, rdi; void *
0x180008eb9  lea     rcx, [rsp+290h+var_258]; this
0x180008ebe  movdqu  [rsp+290h+var_258], xmm0
0x180008ec4  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180008ec9  mov     r14d, eax
0x180008ecc  test    eax, eax
0x180008ece  jns     loc_180008F74
0x180008ed4  mov     rcx, [rbp+198h]; this
0x180008edb  lea     r8, aWil; "wil"
0x180008ee2  mov     r9d, eax; char *
0x180008ee5  mov     edx, 14Bh; void *
0x180008eea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008eef  lea     rcx, [rsp+290h+var_258]; this
0x180008ef4  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180008ef9  call    cs:__imp_GetProcessHeap
0x180008f00  nop     dword ptr [rax+rax+00h]
0x180008f05  mov     r8, rdi; lpMem
0x180008f08  xor     edx, edx; dwFlags
0x180008f0a  mov     rcx, rax; hHeap
0x180008f0d  call    cs:__imp_HeapFree
0x180008f14  nop     dword ptr [rax+rax+00h]
0x180008f19  mov     rcx, [rbp+198h]; this
0x180008f20  lea     r8, aWil; "wil"
0x180008f27  mov     r9d, r14d; char *
0x180008f2a  mov     edx, 134h; void *
0x180008f2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f34  test    rsi, rsi
0x180008f37  jz      short loc_180008F50
0x180008f39  mov     rcx, rsi; hMutex
0x180008f3c  call    cs:__imp_ReleaseMutex
0x180008f43  nop     dword ptr [rax+rax+00h]
0x180008f48  test    eax, eax
0x180008f4a  jz      loc_180009079
0x180008f50  test    rbx, rbx
0x180008f53  jz      short loc_180008F6C
0x180008f55  mov     rcx, rbx; hObject
0x180008f58  call    cs:__imp_CloseHandle
0x180008f5f  nop     dword ptr [rax+rax+00h]
0x180008f64  test    eax, eax
0x180008f66  jz      loc_18000908B
0x180008f6c  mov     eax, r14d
0x180008f6f  jmp     loc_18000900F
0x180008f74  mov     rax, qword ptr [rsp+290h+var_258]
0x180008f79  lea     rcx, [rdi+22h]; void *
0x180008f7d  mov     [rdi+8], rbx
0x180008f81  xor     edx, edx; Val
0x180008f83  xor     ebx, ebx
0x180008f85  mov     [rdi+10h], rax
0x180008f89  mov     rax, qword ptr [rsp+290h+var_258+8]
0x180008f8e  and     qword ptr [rsp+290h+var_258], rbx
0x180008f93  and     qword ptr [rsp+290h+var_258+8], rbx
0x180008f98  lea     r8d, [rbx+56h]; Size
0x180008f9c  mov     dword ptr [rdi], 1
0x180008fa2  mov     [rsp+290h+hHandle], rbx
0x180008fa7  mov     [rdi+18h], rax
0x180008fab  call    memset_0
0x180008fb0  mov     word ptr [rdi+20h], 58h ; 'X'
0x180008fb6  lea     rcx, [rdi+28h]; void *
0x180008fba  xor     edx, edx; Val
0x180008fbc  mov     dword ptr [rdi+24h], 1
0x180008fc3  lea     r8d, [rbx+50h]; Size
0x180008fc7  call    memset_0
0x180008fcc  lea     rcx, [rsp+290h+var_258]; this
0x180008fd1  mov     [r15], rdi
0x180008fd4  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180008fd9  test    rsi, rsi
0x180008fdc  jz      short loc_180008FF5
0x180008fde  mov     rcx, rsi; hMutex
0x180008fe1  call    cs:__imp_ReleaseMutex
0x180008fe8  nop     dword ptr [rax+rax+00h]
0x180008fed  test    eax, eax
0x180008fef  jz      loc_18000909D
0x180008ff5  test    rbx, rbx
0x180008ff8  jz      short loc_18000900D
0x180008ffa  mov     rcx, rbx; hObject
0x180008ffd  call    cs:__imp_CloseHandle
0x180009004  nop     dword ptr [rax+rax+00h]
0x180009009  test    eax, eax
0x18000900b  jz      short loc_180009036
0x18000900d  xor     eax, eax
0x18000900f  mov     rcx, [rbp+190h+var_30]
0x180009016  xor     rcx, rsp; StackCookie
0x180009019  call    __security_check_cookie
0x18000901e  mov     rbx, [rsp+290h+arg_10]
0x180009026  add     rsp, 270h
0x18000902d  pop     r15
0x18000902f  pop     r14
0x180009031  pop     rdi
0x180009032  pop     rsi
0x180009033  pop     rbp
0x180009034  retn
0x180009036  mov     rcx, [rbp+198h]; this
0x18000903d  mov     edx, 9DDh; void *
0x180009042  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009048  mov     rcx, [rbp+198h]; this
0x18000904f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009055  mov     rcx, [rbp+198h]; this
0x18000905c  mov     edx, 9E7h; void *
0x180009061  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009067  mov     rcx, [rbp+198h]; this
0x18000906e  mov     edx, 9DDh; void *
0x180009073  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009079  mov     rcx, [rbp+198h]; this
0x180009080  mov     edx, 9E7h; void *
0x180009085  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000908b  mov     rcx, [rbp+198h]; this
0x180009092  mov     edx, 9DDh; void *
0x180009097  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000909d  mov     rcx, [rbp+198h]; this
0x1800090a4  mov     edx, 9E7h; void *
0x1800090a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
