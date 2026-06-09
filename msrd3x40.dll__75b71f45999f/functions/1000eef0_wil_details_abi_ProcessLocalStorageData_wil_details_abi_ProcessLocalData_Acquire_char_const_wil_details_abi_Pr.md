# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1000eef0`
- end: `0x1000f07b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SGJPBDPAPAV123@@Z`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1000a550`

## callees

- `0x10008470`
- `0x10009170`
- `0x10009ce0`
- `0x10009d80`
- `0x10009dc0`
- `0x1000e110`
- `0x1000eef0`
- `0x1000f4b0`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1000ef6c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1000ef6c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1000ef48`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1000ef48`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1000f02a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1000f02a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1000ef18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1000ef18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000f03a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000f03a`

## pseudocode

```c
void *__usercall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire@<eax>(
        char *a1@<edx>,
        int a2@<ecx>,
        void *a3@<ebx>)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // eax
  void *v5; // esi
  void *LastErrorFailHr; // edi
  DWORD v7; // eax
  wil::details::in1diag3 *v8; // ecx
  void *v9; // ebx
  void *v10; // eax
  wil::details::in1diag3 *v11; // ecx
  wil::details::in1diag3 *v12; // ecx
  _DWORD *v13; // eax
  void *v14; // eax
  wil::details::in1diag3 *v15; // ecx
  wil::details::in1diag3 *v16; // ecx
  wil::details::in1diag3 *v17; // ecx
  void *v20; // [esp-4h] [ebp-224h]
  unsigned int v21; // [esp-4h] [ebp-224h]
  wil::details *v22; // [esp+0h] [ebp-220h]
  const char *v23; // [esp+0h] [ebp-220h]
  const char *v24; // [esp+4h] [ebp-21Ch]
  int v25; // [esp+4h] [ebp-21Ch]
  int v27; // [esp+Ch] [ebp-214h] BYREF
  HANDLE v28; // [esp+10h] [ebp-210h] BYREF
  WCHAR Name[260]; // [esp+14h] [ebp-20Ch] BYREF

  *(_DWORD *)a1 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, (wchar_t *)L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 64, a2);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v5 = Mutex;
  v28 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = (void *)wil::details::GetLastErrorFailHr(v22);
    goto LABEL_18;
  }
  v20 = a3;
  v7 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v9 = 0;
  }
  else
  {
    if ( v7 && v7 != 128 )
      wil::details::in1diag3::FailFast_Unexpected(v8, a3, (unsigned int)v22, v24);
    v9 = v5;
  }
  v27 = 0;
  v10 = (void *)wil::details_abi::SemaphoreValue::TryGetValue<unsigned long>(Name, &v27, v8);
  LastErrorFailHr = v10;
  if ( (int)v10 >= 0 )
  {
    v13 = (_DWORD *)(4 * v27);
    if ( 4 * v27 )
    {
      *(_DWORD *)a1 = v13;
      **(_DWORD **)a1 = *v13 + 1;
    }
    else
    {
      v14 = (void *)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
                      Name,
                      &v28,
                      a1);
      LastErrorFailHr = v14;
      if ( (int)v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(v15, v14, (unsigned int)v20, (const char *)v22, (int)v24);
        v5 = v28;
        goto LABEL_16;
      }
      v5 = v28;
    }
    LastErrorFailHr = 0;
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(v11, v10, (unsigned int)v20, (const char *)v22, (int)v24);
  wil::details::in1diag3::Return_Hr(v12, LastErrorFailHr, v21, v23, v25);
LABEL_16:
  if ( v9 && !ReleaseMutex(v9) )
    wil::details::in1diag3::_FailFast_GetLastError(v16, v20, (unsigned int)v22, v24);
LABEL_18:
  if ( v5 && !CloseHandle(v5) )
    wil::details::in1diag3::_FailFast_GetLastError(v17, v22, (unsigned int)v24, a1);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1000eef0  mov     edi, edi
0x1000eef2  push    ebp
0x1000eef3  mov     ebp, esp
0x1000eef5  sub     esp, 218h
0x1000eefb  mov     eax, ___security_cookie
0x1000ef00  xor     eax, ebp
0x1000ef02  mov     [ebp+var_4], eax
0x1000ef05  push    esi; unsigned int
0x1000ef06  push    edi; void *
0x1000ef07  mov     eax, edx
0x1000ef09  push    ecx
0x1000ef0a  push    40h ; '@'
0x1000ef0c  mov     [ebp+var_218], eax
0x1000ef12  mov     dword ptr [eax], 0
0x1000ef18  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1000ef1e  push    eax
0x1000ef1f  push    offset aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1000ef24  lea     eax, [ebp+Name]
0x1000ef2a  push    104h; unsigned int
0x1000ef2f  push    eax; Buffer
0x1000ef30  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1000ef35  add     esp, 18h
0x1000ef38  lea     eax, [ebp+Name]
0x1000ef3e  push    1F0001h; dwDesiredAccess
0x1000ef43  push    0; dwFlags
0x1000ef45  push    eax; lpName
0x1000ef46  push    0; lpMutexAttributes
0x1000ef48  call    ds:__imp__CreateMutexExW@16; CreateMutexExW(x,x,x,x)
0x1000ef4e  mov     esi, eax
0x1000ef50  mov     [ebp+var_210], esi
0x1000ef56  test    esi, esi
0x1000ef58  jnz     short loc_1000EF66
0x1000ef5a  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x1000ef5f  mov     edi, eax
0x1000ef61  jmp     loc_1000F035
0x1000ef66  push    ebx; void *
0x1000ef67  push    0; bAlertable
0x1000ef69  push    0FFFFFFFFh; dwMilliseconds
0x1000ef6b  push    esi; hHandle
0x1000ef6c  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x1000ef72  cmp     eax, 102h
0x1000ef77  jz      short loc_1000EF8C
0x1000ef79  test    eax, eax
0x1000ef7b  jz      short loc_1000EF88
0x1000ef7d  cmp     eax, 80h
0x1000ef82  jnz     loc_1000F056
0x1000ef88  mov     ebx, esi
0x1000ef8a  jmp     short loc_1000EF8E
0x1000ef8c  xor     ebx, ebx
0x1000ef8e  push    ecx
0x1000ef8f  lea     edx, [ebp+var_214]
0x1000ef95  mov     [ebp+var_214], 0
0x1000ef9f  lea     ecx, [ebp+Name]
0x1000efa5  call    ??$TryGetValue@K@SemaphoreValue@details_abi@wil@@SGJPBGPAKPA_N@Z; wil::details_abi::SemaphoreValue::TryGetValue<ulong>(ushort const *,ulong *,bool *)
0x1000efaa  mov     edi, eax
0x1000efac  test    edi, edi
0x1000efae  jns     short loc_1000EFD0
0x1000efb0  push    edi; void *
0x1000efb1  push    ecx; this
0x1000efb2  mov     ecx, [ebp+4]
0x1000efb5  mov     edx, 6Fh ; 'o'
0x1000efba  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000efbf  push    edi; void *
0x1000efc0  push    ecx; this
0x1000efc1  mov     ecx, [ebp+4]
0x1000efc4  mov     edx, 12Eh
0x1000efc9  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000efce  jmp     short loc_1000F025
0x1000efd0  mov     eax, [ebp+var_214]
0x1000efd6  mov     edx, [ebp+var_218]
0x1000efdc  shl     eax, 2
0x1000efdf  test    eax, eax
0x1000efe1  jz      short loc_1000EFEE
0x1000efe3  mov     [edx], eax
0x1000efe5  mov     ecx, [eax]
0x1000efe7  mov     eax, [edx]
0x1000efe9  inc     ecx
0x1000efea  mov     [eax], ecx
0x1000efec  jmp     short loc_1000F023
0x1000efee  push    edx
0x1000efef  lea     edx, [ebp+var_210]
0x1000eff5  lea     ecx, [ebp+Name]
0x1000effb  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z
0x1000f000  mov     edi, eax
0x1000f002  test    edi, edi
0x1000f004  jns     short loc_1000F01D
0x1000f006  push    edi; void *
0x1000f007  push    ecx; this
0x1000f008  mov     ecx, [ebp+4]
0x1000f00b  mov     edx, 137h
0x1000f010  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000f015  mov     esi, [ebp+var_210]
0x1000f01b  jmp     short loc_1000F025
0x1000f01d  mov     esi, [ebp+var_210]
0x1000f023  xor     edi, edi
0x1000f025  test    ebx, ebx
0x1000f027  jz      short loc_1000F034
0x1000f029  push    ebx; hMutex
0x1000f02a  call    ds:__imp__ReleaseMutex@4; ReleaseMutex(x)
0x1000f030  test    eax, eax
0x1000f032  jz      short loc_1000F05F
0x1000f034  pop     ebx
0x1000f035  test    esi, esi
0x1000f037  jz      short loc_1000F044
0x1000f039  push    esi; hObject
0x1000f03a  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000f040  test    eax, eax
0x1000f042  jz      short loc_1000F06D
0x1000f044  mov     ecx, [ebp+var_4]
0x1000f047  mov     eax, edi
0x1000f049  pop     edi
0x1000f04a  xor     ecx, ebp; StackCookie
0x1000f04c  pop     esi
0x1000f04d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000f052  mov     esp, ebp
0x1000f054  pop     ebp
0x1000f055  retn
0x1000f056  push    ecx; this
0x1000f057  mov     ecx, [ebp+4]
0x1000f05a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1000f05f  push    ecx; this
0x1000f060  mov     ecx, [ebp+4]
0x1000f063  mov     edx, 0A15h
0x1000f068  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1000f06d  push    ecx; this
0x1000f06e  mov     ecx, [ebp+4]
0x1000f071  mov     edx, 0A0Bh
0x1000f076  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
