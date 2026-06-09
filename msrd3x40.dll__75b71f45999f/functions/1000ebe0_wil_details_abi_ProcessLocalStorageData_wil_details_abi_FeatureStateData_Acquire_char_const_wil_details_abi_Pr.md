# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1000ebe0`
- end: `0x1000ed7f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SGJPBDPAPAV123@@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1000cad0`

## callees

- `0x10008470`
- `0x10009170`
- `0x10009ce0`
- `0x10009d80`
- `0x10009dc0`
- `0x1000e110`
- `0x1000ebe0`
- `0x1000f290`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1000ec76`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1000ec76`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1000ec3c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1000ec3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1000ed38`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1000ed38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1000ec0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1000ec0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000ec5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000ec5e`

## pseudocode

```c
void *__fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        int a1,
        _DWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // eax
  void *v4; // esi
  void *LastErrorFailHr; // edi
  wil::details::in1diag3 *v6; // ecx
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
  wil::details *v19; // [esp+0h] [ebp-228h]
  unsigned int v20; // [esp+0h] [ebp-228h]
  const char *v21; // [esp+4h] [ebp-224h]
  const char *v22; // [esp+4h] [ebp-224h]
  const char *v23; // [esp+8h] [ebp-220h]
  int v24; // [esp+8h] [ebp-220h]
  int v26; // [esp+10h] [ebp-218h] BYREF
  HANDLE v27; // [esp+14h] [ebp-214h] BYREF
  WCHAR Name[262]; // [esp+18h] [ebp-210h] BYREF

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, (wchar_t *)L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 168, a1);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v4 = Mutex;
  v27 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = (void *)wil::details::GetLastErrorFailHr(v19);
    goto LABEL_3;
  }
  v7 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v9 = 0;
  }
  else
  {
    if ( v7 && v7 != 128 )
      wil::details::in1diag3::FailFast_Unexpected(v8, v19, (unsigned int)v21, v23);
    v9 = v4;
  }
  v26 = 0;
  v10 = (void *)wil::details_abi::SemaphoreValue::TryGetValue<unsigned long>(Name, &v26, v8);
  LastErrorFailHr = v10;
  if ( (int)v10 >= 0 )
  {
    v13 = (_DWORD *)(4 * v26);
    if ( 4 * v26 )
    {
      *a2 = v13;
      *(_DWORD *)*a2 = *v13 + 1;
    }
    else
    {
      v14 = (void *)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(
                      Name,
                      &v27,
                      a2);
      LastErrorFailHr = v14;
      if ( (int)v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(v15, v14, (unsigned int)v19, v21, (int)v23);
        v4 = v27;
        goto LABEL_19;
      }
      v4 = v27;
    }
    LastErrorFailHr = 0;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(v11, v10, (unsigned int)v19, v21, (int)v23);
  wil::details::in1diag3::Return_Hr(v12, LastErrorFailHr, v20, v22, v24);
LABEL_19:
  if ( v9 && !ReleaseMutex(v9) )
    wil::details::in1diag3::_FailFast_GetLastError(v16, v19, (unsigned int)v21, v23);
LABEL_3:
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(v6, v19, (unsigned int)v21, v23);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1000ebe0  mov     edi, edi
0x1000ebe2  push    ebp
0x1000ebe3  mov     ebp, esp
0x1000ebe5  sub     esp, 21Ch
0x1000ebeb  mov     eax, ___security_cookie
0x1000ebf0  xor     eax, ebp
0x1000ebf2  mov     [ebp+var_4], eax
0x1000ebf5  push    ebx; char *
0x1000ebf6  push    esi; unsigned int
0x1000ebf7  push    edi; void *
0x1000ebf8  mov     eax, edx
0x1000ebfa  push    ecx
0x1000ebfb  push    0A8h
0x1000ec00  mov     [ebp+var_21C], eax
0x1000ec06  mov     dword ptr [eax], 0
0x1000ec0c  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1000ec12  push    eax
0x1000ec13  push    offset aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1000ec18  lea     eax, [ebp+Name]
0x1000ec1e  push    104h; unsigned int
0x1000ec23  push    eax; Buffer
0x1000ec24  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1000ec29  add     esp, 18h
0x1000ec2c  lea     eax, [ebp+Name]
0x1000ec32  push    1F0001h; dwDesiredAccess
0x1000ec37  push    0; dwFlags
0x1000ec39  push    eax; lpName
0x1000ec3a  push    0; lpMutexAttributes
0x1000ec3c  call    ds:__imp__CreateMutexExW@16; CreateMutexExW(x,x,x,x)
0x1000ec42  mov     esi, eax
0x1000ec44  mov     [ebp+var_214], esi
0x1000ec4a  test    esi, esi
0x1000ec4c  jnz     short loc_1000EC71
0x1000ec4e  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x1000ec53  mov     edi, eax
0x1000ec55  test    esi, esi
0x1000ec57  jz      loc_1000ED47
0x1000ec5d  push    esi; hObject
0x1000ec5e  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000ec64  test    eax, eax
0x1000ec66  jz      loc_1000ED5A
0x1000ec6c  jmp     loc_1000ED47
0x1000ec71  push    0; bAlertable
0x1000ec73  push    0FFFFFFFFh; dwMilliseconds
0x1000ec75  push    esi; hHandle
0x1000ec76  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x1000ec7c  cmp     eax, 102h
0x1000ec81  jz      short loc_1000EC96
0x1000ec83  test    eax, eax
0x1000ec85  jz      short loc_1000EC92
0x1000ec87  cmp     eax, 80h
0x1000ec8c  jnz     loc_1000ED68
0x1000ec92  mov     ebx, esi
0x1000ec94  jmp     short loc_1000EC98
0x1000ec96  xor     ebx, ebx
0x1000ec98  push    ecx
0x1000ec99  lea     edx, [ebp+var_218]
0x1000ec9f  mov     [ebp+var_218], 0
0x1000eca9  lea     ecx, [ebp+Name]
0x1000ecaf  call    ??$TryGetValue@K@SemaphoreValue@details_abi@wil@@SGJPBGPAKPA_N@Z; wil::details_abi::SemaphoreValue::TryGetValue<ulong>(ushort const *,ulong *,bool *)
0x1000ecb4  mov     edi, eax
0x1000ecb6  test    edi, edi
0x1000ecb8  jns     short loc_1000ECDA
0x1000ecba  push    edi; void *
0x1000ecbb  push    ecx; this
0x1000ecbc  mov     ecx, [ebp+4]
0x1000ecbf  mov     edx, 6Fh ; 'o'
0x1000ecc4  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000ecc9  push    edi; void *
0x1000ecca  push    ecx; this
0x1000eccb  mov     ecx, [ebp+4]
0x1000ecce  mov     edx, 12Eh
0x1000ecd3  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000ecd8  jmp     short loc_1000ED2F
0x1000ecda  mov     eax, [ebp+var_218]
0x1000ece0  mov     edx, [ebp+var_21C]
0x1000ece6  shl     eax, 2
0x1000ece9  test    eax, eax
0x1000eceb  jz      short loc_1000ECF8
0x1000eced  mov     [edx], eax
0x1000ecef  mov     ecx, [eax]
0x1000ecf1  mov     eax, [edx]
0x1000ecf3  inc     ecx
0x1000ecf4  mov     [eax], ecx
0x1000ecf6  jmp     short loc_1000ED2D
0x1000ecf8  push    edx
0x1000ecf9  lea     edx, [ebp+var_214]
0x1000ecff  lea     ecx, [ebp+Name]
0x1000ed05  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z
0x1000ed0a  mov     edi, eax
0x1000ed0c  test    edi, edi
0x1000ed0e  jns     short loc_1000ED27
0x1000ed10  push    edi; void *
0x1000ed11  push    ecx; this
0x1000ed12  mov     ecx, [ebp+4]
0x1000ed15  mov     edx, 137h
0x1000ed1a  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000ed1f  mov     esi, [ebp+var_214]
0x1000ed25  jmp     short loc_1000ED2F
0x1000ed27  mov     esi, [ebp+var_214]
0x1000ed2d  xor     edi, edi
0x1000ed2f  test    ebx, ebx
0x1000ed31  jz      loc_1000EC55
0x1000ed37  push    ebx; hMutex
0x1000ed38  call    ds:__imp__ReleaseMutex@4; ReleaseMutex(x)
0x1000ed3e  test    eax, eax
0x1000ed40  jz      short loc_1000ED71
0x1000ed42  jmp     loc_1000EC55
0x1000ed47  mov     ecx, [ebp+var_4]
0x1000ed4a  mov     eax, edi
0x1000ed4c  pop     edi
0x1000ed4d  pop     esi
0x1000ed4e  xor     ecx, ebp; StackCookie
0x1000ed50  pop     ebx
0x1000ed51  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000ed56  mov     esp, ebp
0x1000ed58  pop     ebp
0x1000ed59  retn
0x1000ed5a  push    ecx; this
0x1000ed5b  mov     ecx, [ebp+4]
0x1000ed5e  mov     edx, 0A0Bh
0x1000ed63  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1000ed68  push    ecx; this
0x1000ed69  mov     ecx, [ebp+4]
0x1000ed6c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1000ed71  push    ecx; this
0x1000ed72  mov     ecx, [ebp+4]
0x1000ed75  mov     edx, 0A15h
0x1000ed7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
