# ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z

- ea: `0x1000f4b0`
- end: `0x1000f684`
- name: `?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1000eef0`

## callees

- `0x100084f0`
- `0x10008950`
- `0x10009170`
- `0x10009ce0`
- `0x10009e60`
- `0x1000f4b0`
- `0x1005e3b0`
- `0x1005f180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1000f5bd`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1000f5bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000f5f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000f5f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000f5fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000f5fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000f606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000f606`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
        WCHAR *a1,
        _DWORD *a2,
        _DWORD *a3)
{
  unsigned int v4; // eax
  wil::details::in1diag3 *v5; // ecx
  void *v6; // esi
  WCHAR *v7; // ecx
  int v8; // esi
  int v9; // edx
  WCHAR *v10; // eax
  int v11; // ecx
  WCHAR *v12; // eax
  LONG v13; // eax
  HANDLE Semaphore; // edi
  void *LastErrorFailHr; // eax
  wil::details::in1diag3 *v16; // ecx
  wil::details::in1diag3 *v17; // ecx
  HANDLE ProcessHeap; // eax
  _DWORD *v19; // eax
  wil::details *v21; // [esp+0h] [ebp-230h]
  wil::details::in1diag3 *v22; // [esp+0h] [ebp-230h]
  unsigned int v23; // [esp+0h] [ebp-230h]
  unsigned int v24; // [esp+0h] [ebp-230h]
  unsigned int v25; // [esp+4h] [ebp-22Ch]
  const char *v26; // [esp+4h] [ebp-22Ch]
  const char *v27; // [esp+4h] [ebp-22Ch]
  unsigned int v28; // [esp+8h] [ebp-228h]
  int v29; // [esp+8h] [ebp-228h]
  int v30; // [esp+8h] [ebp-228h]
  char *lpMem; // [esp+10h] [ebp-220h]
  LONG lInitialCount; // [esp+14h] [ebp-21Ch]
  _DWORD *v34; // [esp+1Ch] [ebp-214h]
  WCHAR Name[262]; // [esp+20h] [ebp-210h] BYREF

  v34 = a3;
  *a3 = 0;
  v4 = (unsigned int)wil::details::ProcessHeapAlloc(v21, v25, v28);
  lpMem = (char *)v4;
  if ( v4 )
  {
    if ( (v4 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
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
      StringCopyWorkerW((STRSAFE_LPWSTR)v11, (size_t)L"_p0", (size_t *)v11, (STRSAFE_PCNZWCH)v22, (size_t)v26);
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
      LastErrorFailHr = (void *)wil::details::GetLastErrorFailHr(v22);
      v6 = LastErrorFailHr;
      if ( (int)LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(v16, LastErrorFailHr, v23, v26, v29);
        wil::details::in1diag3::Return_Hr(v17, v6, v24, v27, v30);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, lpMem);
        return (int)v6;
      }
    }
    *(_DWORD *)lpMem = 1;
    *((_DWORD *)lpMem + 1) = *a2;
    *a2 = 0;
    *((_DWORD *)lpMem + 2) = Semaphore;
    *((_DWORD *)lpMem + 3) = 0;
    memset(lpMem + 16, 0, 0x30u);
    *((_WORD *)lpMem + 8) = 48;
    v19 = v34;
    *((_DWORD *)lpMem + 5) = 1;
    *(_OWORD *)(lpMem + 24) = 0;
    *(_OWORD *)(lpMem + 40) = 0;
    *((_QWORD *)lpMem + 7) = 0;
    v6 = 0;
    *v19 = lpMem;
    return (int)v6;
  }
  wil::details::in1diag3::Return_Hr(v5, (void *)0x8007000E, (unsigned int)v22, v26, v29);
  return -2147024882;
}

```

## disassembly

```asm
0x1000f4b0  mov     edi, edi
0x1000f4b2  push    ebp
0x1000f4b3  mov     ebp, esp
0x1000f4b5  and     esp, 0FFFFFFF8h
0x1000f4b8  sub     esp, 224h
0x1000f4be  mov     eax, ___security_cookie
0x1000f4c3  xor     eax, esp
0x1000f4c5  mov     [esp+224h+var_4], eax
0x1000f4cc  mov     eax, [ebp+arg_0]
0x1000f4cf  push    ebx; int
0x1000f4d0  mov     [esp+228h+var_218], edx
0x1000f4d4  mov     edx, 40h ; '@'
0x1000f4d9  push    esi; char *
0x1000f4da  push    edi; this
0x1000f4db  mov     edi, ecx
0x1000f4dd  mov     [esp+230h+var_214], eax
0x1000f4e1  lea     ecx, [edx-38h]
0x1000f4e4  mov     dword ptr [eax], 0
0x1000f4ea  call    ?ProcessHeapAlloc@details@wil@@YGPAXKI@Z; wil::details::ProcessHeapAlloc(ulong,uint)
0x1000f4ef  mov     ebx, eax
0x1000f4f1  mov     [esp+230h+lpMem], ebx
0x1000f4f5  test    ebx, ebx
0x1000f4f7  jnz     short loc_1000F516
0x1000f4f9  push    8007000Eh; void *
0x1000f4fe  push    ecx; this
0x1000f4ff  mov     ecx, [ebp+4]
0x1000f502  mov     edx, 14Bh
0x1000f507  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000f50c  mov     esi, 8007000Eh
0x1000f511  jmp     loc_1000F666
0x1000f516  test    bl, 3
0x1000f519  jnz     loc_1000F67F
0x1000f51f  shr     ebx, 2
0x1000f522  lea     ecx, [esp+230h+Name]
0x1000f526  mov     [esp+230h+lInitialCount], ebx
0x1000f52a  mov     esi, 7FFFFFFEh
0x1000f52f  mov     edx, 104h
0x1000f534  test    esi, esi
0x1000f536  jz      short loc_1000F551
0x1000f538  movzx   eax, word ptr [edi]
0x1000f53b  mov     ebx, eax
0x1000f53d  test    ax, ax
0x1000f540  jz      short loc_1000F551
0x1000f542  mov     [ecx], bx
0x1000f545  add     edi, 2
0x1000f548  add     ecx, 2
0x1000f54b  dec     esi
0x1000f54c  sub     edx, 1
0x1000f54f  jnz     short loc_1000F534
0x1000f551  lea     eax, [ecx-2]
0x1000f554  test    edx, edx
0x1000f556  cmovnz  eax, ecx
0x1000f559  xor     ecx, ecx
0x1000f55b  mov     [eax], cx
0x1000f55e  mov     ecx, 104h
0x1000f563  lea     eax, [esp+230h+Name]
0x1000f567  cmp     word ptr [eax], 0
0x1000f56b  jz      short loc_1000F575
0x1000f56d  add     eax, 2
0x1000f570  sub     ecx, 1
0x1000f573  jnz     short loc_1000F567
0x1000f575  mov     edx, 104h
0x1000f57a  mov     esi, ecx
0x1000f57c  mov     eax, edx
0x1000f57e  sub     eax, ecx
0x1000f580  neg     esi
0x1000f582  sbb     esi, esi
0x1000f584  and     esi, eax
0x1000f586  test    ecx, ecx
0x1000f588  jz      short loc_1000F59F
0x1000f58a  push    ecx; pcchNewDestLength
0x1000f58b  push    offset aP0; "_p0"
0x1000f590  push    ecx; pszDest
0x1000f591  lea     ecx, [esp+23Ch+Name]
0x1000f595  sub     edx, esi
0x1000f597  lea     ecx, [ecx+esi*2]
0x1000f59a  call    StringCopyWorkerW
0x1000f59f  mov     ecx, [esp+230h+lInitialCount]
0x1000f5a3  lea     eax, [esp+230h+Name]
0x1000f5a7  push    1F0003h; dwDesiredAccess
0x1000f5ac  push    0; dwFlags
0x1000f5ae  push    eax; lpName
0x1000f5af  test    ecx, ecx
0x1000f5b1  mov     eax, 1
0x1000f5b6  cmovnz  eax, ecx
0x1000f5b9  push    eax; lMaximumCount
0x1000f5ba  push    ecx; lInitialCount
0x1000f5bb  push    0; lpSemaphoreAttributes
0x1000f5bd  call    ds:__imp__CreateSemaphoreExW@24; CreateSemaphoreExW(x,x,x,x,x,x)
0x1000f5c3  mov     edi, eax
0x1000f5c5  test    edi, edi
0x1000f5c7  jnz     short loc_1000F606
0x1000f5c9  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x1000f5ce  mov     esi, eax
0x1000f5d0  test    esi, esi
0x1000f5d2  jns     short loc_1000F60C
0x1000f5d4  push    esi; void *
0x1000f5d5  push    ecx; this
0x1000f5d6  mov     ecx, [ebp+4]
0x1000f5d9  mov     edx, 8Bh
0x1000f5de  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000f5e3  push    esi; void *
0x1000f5e4  push    ecx; this
0x1000f5e5  mov     ecx, [ebp+4]
0x1000f5e8  mov     edx, 14Eh
0x1000f5ed  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000f5f2  push    [esp+230h+lpMem]; lpMem
0x1000f5f6  push    edi; dwFlags
0x1000f5f7  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000f5fd  push    eax; hHeap
0x1000f5fe  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000f604  jmp     short loc_1000F666
0x1000f606  call    ds:__imp__GetLastError@0; GetLastError()
0x1000f60c  mov     ebx, [esp+230h+lpMem]
0x1000f610  mov     ecx, [esp+230h+var_218]
0x1000f614  push    30h ; '0'; Size
0x1000f616  push    0; Val
0x1000f618  mov     dword ptr [ebx], 1
0x1000f61e  lea     esi, [ebx+10h]
0x1000f621  mov     eax, [ecx]
0x1000f623  mov     [ebx+4], eax
0x1000f626  mov     dword ptr [ecx], 0
0x1000f62c  push    esi; void *
0x1000f62d  mov     [ebx+8], edi
0x1000f630  mov     dword ptr [ebx+0Ch], 0
0x1000f637  call    _memset
0x1000f63c  mov     eax, 30h ; '0'
0x1000f641  xorps   xmm0, xmm0
0x1000f644  mov     [esi], ax
0x1000f647  add     esp, 0Ch
0x1000f64a  mov     eax, [esp+230h+var_214]
0x1000f64e  mov     dword ptr [esi+4], 1
0x1000f655  movups  xmmword ptr [esi+8], xmm0
0x1000f659  movups  xmmword ptr [esi+18h], xmm0
0x1000f65d  movq    qword ptr [esi+28h], xmm0
0x1000f662  xor     esi, esi
0x1000f664  mov     [eax], ebx
0x1000f666  mov     ecx, [esp+230h+var_4]
0x1000f66d  mov     eax, esi
0x1000f66f  pop     edi
0x1000f670  pop     esi
0x1000f671  pop     ebx
0x1000f672  xor     ecx, esp; StackCookie
0x1000f674  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000f679  mov     esp, ebp
0x1000f67b  pop     ebp
0x1000f67c  retn    4
0x1000f67f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
