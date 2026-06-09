# ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z

- ea: `0x1000f290`
- end: `0x1000f49f`
- name: `?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1000ebe0`

## callees

- `0x100084f0`
- `0x10008950`
- `0x10009170`
- `0x10009ce0`
- `0x10009e60`
- `0x1000c1a0`
- `0x1000f290`
- `0x1005e3b0`
- `0x1005f180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1000f3b1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1000f3b1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1000f459`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1000f459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000f3ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000f3ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000f3f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000f3f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000f3ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000f3ff`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(
        WCHAR *a1,
        _DWORD *a2,
        _DWORD *a3)
{
  unsigned int v4; // eax
  wil::details::in1diag3 *v5; // ecx
  void *v6; // esi
  WCHAR *v7; // ecx
  int v8; // edx
  int v9; // esi
  WCHAR *v10; // eax
  int v11; // ecx
  WCHAR *v12; // eax
  LONG v13; // eax
  HANDLE Semaphore; // edi
  void *LastErrorFailHr; // eax
  wil::details::in1diag3 *v16; // ecx
  wil::details::in1diag3 *v17; // ecx
  HANDLE ProcessHeap; // eax
  char *v19; // ebx
  void *v21; // [esp-4h] [ebp-238h]
  wil::details *v22; // [esp+0h] [ebp-234h]
  wil::details::in1diag3 *v23; // [esp+0h] [ebp-234h]
  unsigned int v24; // [esp+0h] [ebp-234h]
  unsigned int v25; // [esp+0h] [ebp-234h]
  unsigned int v26; // [esp+4h] [ebp-230h]
  const char *v27; // [esp+4h] [ebp-230h]
  const char *v28; // [esp+4h] [ebp-230h]
  unsigned int v29; // [esp+8h] [ebp-22Ch]
  int v30; // [esp+8h] [ebp-22Ch]
  int v31; // [esp+8h] [ebp-22Ch]
  LONG lInitialCount; // [esp+18h] [ebp-21Ch]
  LPVOID lpMem; // [esp+1Ch] [ebp-218h]
  WCHAR Name[262]; // [esp+20h] [ebp-214h] BYREF

  *a3 = 0;
  v4 = (unsigned int)wil::details::ProcessHeapAlloc(v22, v26, v29);
  lpMem = (LPVOID)v4;
  if ( v4 )
  {
    if ( (v4 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    v7 = Name;
    lInitialCount = v4 >> 2;
    v8 = 2147483646;
    v9 = 260;
    do
    {
      if ( !v8 )
        break;
      if ( !*a1 )
        break;
      *v7++ = *a1++;
      --v8;
      --v9;
    }
    while ( v9 );
    v10 = v7 - 1;
    if ( v9 )
      v10 = v7;
    *v10 = 0;
    v11 = 260;
    v12 = Name;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    if ( v11 )
      StringCopyWorkerW((STRSAFE_LPWSTR)v11, (size_t)L"_p0", (size_t *)v11, (STRSAFE_PCNZWCH)v23, (size_t)v27);
    v13 = 1;
    if ( lInitialCount )
      v13 = lInitialCount;
    Semaphore = CreateSemaphoreExW(0, lInitialCount, v13, Name, 0, 0x1F0003u);
    if ( Semaphore )
    {
      GetLastError();
    }
    else
    {
      LastErrorFailHr = (void *)wil::details::GetLastErrorFailHr(v23);
      v6 = LastErrorFailHr;
      if ( (int)LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(v16, LastErrorFailHr, v24, v27, v30);
        wil::details::in1diag3::Return_Hr(v17, v6, v25, v28, v31);
        v21 = lpMem;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v21);
        return (int)v6;
      }
    }
    v19 = (char *)lpMem;
    *(_DWORD *)lpMem = 1;
    *((_DWORD *)v19 + 1) = *a2;
    *a2 = 0;
    *((_DWORD *)v19 + 2) = Semaphore;
    *((_DWORD *)v19 + 3) = 0;
    memset(v19 + 20, 0, 0x94u);
    *((_DWORD *)v19 + 4) = 0;
    wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v19 + 20));
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v19 + 128), 0, 0);
    *((_DWORD *)v19 + 38) = 0;
    *((_DWORD *)v19 + 39) = 0;
    *((_DWORD *)v19 + 40) = 0;
    *((_DWORD *)v19 + 41) = 0;
    v6 = 0;
    *a3 = v19;
    return (int)v6;
  }
  wil::details::in1diag3::Return_Hr(v5, (void *)0x8007000E, (unsigned int)v23, v27, v30);
  return -2147024882;
}

```

## disassembly

```asm
0x1000f290  mov     edi, edi
0x1000f292  push    ebp
0x1000f293  mov     ebp, esp
0x1000f295  sub     esp, 228h
0x1000f29b  mov     eax, ___security_cookie
0x1000f2a0  xor     eax, ebp
0x1000f2a2  mov     [ebp+var_8], eax
0x1000f2a5  mov     eax, [ebp+arg_0]
0x1000f2a8  push    ebx; int
0x1000f2a9  push    esi; char *
0x1000f2aa  push    edi; this
0x1000f2ab  mov     [ebp+var_220], edx
0x1000f2b1  mov     edi, ecx
0x1000f2b3  mov     edx, 0A8h
0x1000f2b8  mov     [ebp+var_224], eax
0x1000f2be  mov     ecx, 8
0x1000f2c3  mov     dword ptr [eax], 0
0x1000f2c9  call    ?ProcessHeapAlloc@details@wil@@YGPAXKI@Z; wil::details::ProcessHeapAlloc(ulong,uint)
0x1000f2ce  mov     ebx, eax
0x1000f2d0  mov     [ebp+lpMem], ebx
0x1000f2d6  test    ebx, ebx
0x1000f2d8  jnz     short loc_1000F2F7
0x1000f2da  push    8007000Eh; void *
0x1000f2df  push    ecx; this
0x1000f2e0  mov     ecx, [ebp+4]
0x1000f2e3  mov     edx, 14Bh
0x1000f2e8  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000f2ed  mov     esi, 8007000Eh
0x1000f2f2  jmp     loc_1000F485
0x1000f2f7  test    bl, 3
0x1000f2fa  jnz     loc_1000F49A
0x1000f300  shr     ebx, 2
0x1000f303  lea     ecx, [ebp+Name]
0x1000f309  mov     [ebp+lInitialCount], ebx
0x1000f30f  mov     edx, 7FFFFFFEh
0x1000f314  mov     esi, 104h
0x1000f319  nop     dword ptr [eax+00000000h]
0x1000f320  test    edx, edx
0x1000f322  jz      short loc_1000F33D
0x1000f324  movzx   eax, word ptr [edi]
0x1000f327  mov     ebx, eax
0x1000f329  test    ax, ax
0x1000f32c  jz      short loc_1000F33D
0x1000f32e  mov     [ecx], bx
0x1000f331  add     edi, 2
0x1000f334  add     ecx, 2
0x1000f337  dec     edx
0x1000f338  sub     esi, 1
0x1000f33b  jnz     short loc_1000F320
0x1000f33d  lea     eax, [ecx-2]
0x1000f340  test    esi, esi
0x1000f342  cmovnz  eax, ecx
0x1000f345  xor     ecx, ecx
0x1000f347  mov     [eax], cx
0x1000f34a  mov     ecx, 104h
0x1000f34f  lea     eax, [ebp+Name]
0x1000f355  cmp     word ptr [eax], 0
0x1000f359  jz      short loc_1000F363
0x1000f35b  add     eax, 2
0x1000f35e  sub     ecx, 1
0x1000f361  jnz     short loc_1000F355
0x1000f363  mov     edx, 104h
0x1000f368  mov     esi, ecx
0x1000f36a  mov     eax, edx
0x1000f36c  sub     eax, ecx
0x1000f36e  neg     esi
0x1000f370  sbb     esi, esi
0x1000f372  and     esi, eax
0x1000f374  test    ecx, ecx
0x1000f376  jz      short loc_1000F38F
0x1000f378  push    ecx; pcchNewDestLength
0x1000f379  push    offset aP0; "_p0"
0x1000f37e  push    ecx; pszDest
0x1000f37f  lea     ecx, [ebp+Name]
0x1000f385  sub     edx, esi
0x1000f387  lea     ecx, [ecx+esi*2]
0x1000f38a  call    StringCopyWorkerW
0x1000f38f  mov     ecx, [ebp+lInitialCount]
0x1000f395  lea     eax, [ebp+Name]
0x1000f39b  push    1F0003h; dwDesiredAccess
0x1000f3a0  push    0; dwFlags
0x1000f3a2  push    eax; lpName
0x1000f3a3  test    ecx, ecx
0x1000f3a5  mov     eax, 1
0x1000f3aa  cmovnz  eax, ecx
0x1000f3ad  push    eax; lMaximumCount
0x1000f3ae  push    ecx; lInitialCount
0x1000f3af  push    0; lpSemaphoreAttributes
0x1000f3b1  call    ds:__imp__CreateSemaphoreExW@24; CreateSemaphoreExW(x,x,x,x,x,x)
0x1000f3b7  mov     edi, eax
0x1000f3b9  test    edi, edi
0x1000f3bb  jnz     short loc_1000F3FF
0x1000f3bd  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x1000f3c2  mov     esi, eax
0x1000f3c4  test    esi, esi
0x1000f3c6  jns     short loc_1000F405
0x1000f3c8  push    esi; void *
0x1000f3c9  push    ecx; this
0x1000f3ca  mov     ecx, [ebp+4]
0x1000f3cd  mov     edx, 8Bh
0x1000f3d2  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000f3d7  push    esi; void *
0x1000f3d8  push    ecx; this
0x1000f3d9  mov     ecx, [ebp+4]
0x1000f3dc  mov     edx, 14Eh
0x1000f3e1  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000f3e6  push    [ebp+lpMem]; lpMem
0x1000f3ec  push    edi; dwFlags
0x1000f3ed  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000f3f3  push    eax; hHeap
0x1000f3f4  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000f3fa  jmp     loc_1000F485
0x1000f3ff  call    ds:__imp__GetLastError@0; GetLastError()
0x1000f405  mov     ebx, [ebp+lpMem]
0x1000f40b  mov     ecx, [ebp+var_220]
0x1000f411  push    94h; Size
0x1000f416  push    0; Val
0x1000f418  mov     dword ptr [ebx], 1
0x1000f41e  mov     eax, [ecx]
0x1000f420  mov     [ebx+4], eax
0x1000f423  lea     eax, [ebx+14h]
0x1000f426  mov     dword ptr [ecx], 0
0x1000f42c  push    eax; void *
0x1000f42d  mov     [ebx+8], edi
0x1000f430  mov     dword ptr [ebx+0Ch], 0
0x1000f437  call    _memset
0x1000f43c  add     esp, 0Ch
0x1000f43f  mov     dword ptr [ebx+10h], 0
0x1000f446  lea     ecx, [ebx+14h]; this
0x1000f449  call    ??0UsageIndexes@details_abi@wil@@QAE@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1000f44e  push    0; Flags
0x1000f450  push    0; dwSpinCount
0x1000f452  lea     esi, [ebx+80h]
0x1000f458  push    esi; lpCriticalSection
0x1000f459  call    ds:__imp__InitializeCriticalSectionEx@12; InitializeCriticalSectionEx(x,x,x)
0x1000f45f  mov     eax, [ebp+var_224]
0x1000f465  mov     dword ptr [esi+18h], 0
0x1000f46c  mov     dword ptr [esi+1Ch], 0
0x1000f473  mov     dword ptr [esi+20h], 0
0x1000f47a  mov     dword ptr [esi+24h], 0
0x1000f481  xor     esi, esi
0x1000f483  mov     [eax], ebx
0x1000f485  mov     ecx, [ebp+var_8]
0x1000f488  mov     eax, esi
0x1000f48a  pop     edi
0x1000f48b  pop     esi
0x1000f48c  xor     ecx, ebp; StackCookie
0x1000f48e  pop     ebx
0x1000f48f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000f494  mov     esp, ebp
0x1000f496  pop     ebp
0x1000f497  retn    4
0x1000f49a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
