# CRpcResolver::GetFQDN(ushort * *)

- ea: `0x1801ac6d4`
- end: `0x1801ac895`
- name: `?GetFQDN@CRpcResolver@@QEAAJPEAPEAG@Z`
- size: `449`
- prototype: `HRESULT __fastcall(CRpcResolver *this, wchar_t **ppwszFQDN)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18012498c`

## callees

- `0x180006250`
- `0x180006390`
- `0x180087660`
- `0x18008db2c`
- `0x1801ac6d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac80b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac80b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ac787`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ac787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801ac7b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801ac7b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801ac757`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801ac79f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801ac757`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801ac79f`

## string_xrefs

- `0x1801ac70e`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x1801ac85d`: `onecore\com\combase\dcomrem\resolver.cxx`

## pseudocode

```c
__int64 __fastcall CRpcResolver::GetFQDN(CRpcResolver *this, wchar_t **ppwszFQDN, __int64 a3, const char *a4)
{
  wchar_t *v4; // rax
  wchar_t *v7; // rax
  wchar_t *v8; // rsi
  signed int v9; // eax
  HRESULT v10; // ebx
  int v11; // r8d
  signed int LastError; // eax
  CRpcResolver *dwBuf; // [rsp+40h] [rbp+8h] BYREF

  dwBuf = this;
  v4 = CRpcResolver::_pwszFQDN;
  *ppwszFQDN = 0;
  if ( v4 )
  {
    *ppwszFQDN = v4;
    return 0;
  }
  COleStaticMutexSem::Request(&CRpcResolver::_mxsResolver, "onecore\\com\\combase\\dcomrem\\resolver.cxx", 0x224u, a4);
  if ( CRpcResolver::_pwszFQDN )
  {
    COleStaticMutexSem::Release(&CRpcResolver::_mxsResolver);
    *ppwszFQDN = CRpcResolver::_pwszFQDN;
    return 0;
  }
  LODWORD(dwBuf) = 0;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, 0, (LPDWORD)&dwBuf) || GetLastError() != 234 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      goto LABEL_25;
    v11 = 579;
LABEL_24:
    ComTraceMessageT<long>(
      "onecore\\com\\combase\\dcomrem\\resolver.cxx",
      "CRpcResolver::GetFQDN",
      v11,
      ERRORS,
      L"%!HRESULT!",
      v10);
    goto LABEL_25;
  }
  v7 = (wchar_t *)HeapAlloc(g_hHeap, 0, 2LL * (unsigned int)dwBuf);
  v8 = v7;
  if ( v7 )
  {
    if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v7, (LPDWORD)&dwBuf) )
    {
      HeapFree(g_hHeap, 0, v8);
      v9 = GetLastError();
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
        goto LABEL_25;
      v11 = 567;
      goto LABEL_24;
    }
    v10 = 0;
    CRpcResolver::_pwszFQDN = v8;
  }
  else
  {
    v10 = -2147024882;
  }
LABEL_25:
  if ( v10 >= 0 )
    *ppwszFQDN = CRpcResolver::_pwszFQDN;
  COleStaticMutexSem::Release(&CRpcResolver::_mxsResolver);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1801ac6d4  mov     [rsp+arg_8], rbx
0x1801ac6d9  mov     [rsp+arg_10], rsi
0x1801ac6de  mov     [rsp+dwBuf], rcx
0x1801ac6e3  push    rdi
0x1801ac6e4  sub     rsp, 30h
0x1801ac6e8  mov     rax, cs:?_pwszFQDN@CRpcResolver@@0PEAGEA; ushort * CRpcResolver::_pwszFQDN
0x1801ac6ef  mov     rdi, ppwszFQDN
0x1801ac6f2  mov     qword ptr [ppwszFQDN], 0
0x1801ac6f9  test    rax, rax
0x1801ac6fc  jz      short loc_1801AC708
0x1801ac6fe  mov     [ppwszFQDN], rax
0x1801ac701  xor     eax, eax
0x1801ac703  jmp     loc_1801AC885
0x1801ac708  mov     r8d, 224h; dwLine
0x1801ac70e  lea     ppwszFQDN, aOnecoreComComb_138; "onecore\\com\\combase\\dcomrem\\resolve"...
0x1801ac715  lea     rcx, ?_mxsResolver@CRpcResolver@@0VCOleStaticMutexSem@@A; this
0x1801ac71c  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x1801ac721  cmp     cs:?_pwszFQDN@CRpcResolver@@0PEAGEA, 0; ushort * CRpcResolver::_pwszFQDN
0x1801ac729  jz      short loc_1801AC743
0x1801ac72b  lea     rcx, ?_mxsResolver@CRpcResolver@@0VCOleStaticMutexSem@@A; this
0x1801ac732  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x1801ac737  mov     rax, cs:?_pwszFQDN@CRpcResolver@@0PEAGEA; ushort * CRpcResolver::_pwszFQDN
0x1801ac73e  mov     [rdi], rax
0x1801ac741  jmp     short loc_1801AC701
0x1801ac743  xor     edx, edx; lpBuffer
0x1801ac745  mov     dword ptr [rsp+38h+dwBuf], 0
0x1801ac74d  lea     r8, [rsp+38h+dwBuf]; nSize
0x1801ac752  lea     ebx, [ppwszFQDN+3]
0x1801ac755  mov     ecx, ebx; NameType
0x1801ac757  call    cs:__imp_GetComputerNameExW
0x1801ac75d  test    eax, eax
0x1801ac75f  jnz     loc_1801AC80B
0x1801ac765  call    cs:__imp_GetLastError
0x1801ac76b  cmp     eax, 0EAh
0x1801ac770  jnz     loc_1801AC80B
0x1801ac776  mov     r8d, dword ptr [rsp+38h+dwBuf]
0x1801ac77b  xor     edx, edx; dwFlags
0x1801ac77d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801ac784  add     r8, r8; dwBytes
0x1801ac787  call    cs:__imp_HeapAlloc
0x1801ac78d  mov     rsi, rax
0x1801ac790  test    rax, rax
0x1801ac793  jz      short loc_1801AC804
0x1801ac795  lea     r8, [rsp+38h+dwBuf]; nSize
0x1801ac79a  mov     ppwszFQDN, rax; lpBuffer
0x1801ac79d  mov     ecx, ebx; NameType
0x1801ac79f  call    cs:__imp_GetComputerNameExW
0x1801ac7a5  test    eax, eax
0x1801ac7a7  jnz     short loc_1801AC7F9
0x1801ac7a9  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801ac7b0  mov     r8, rsi; lpMem
0x1801ac7b3  xor     edx, edx; dwFlags
0x1801ac7b5  call    cs:__imp_HeapFree
0x1801ac7bb  call    cs:__imp_GetLastError
0x1801ac7c1  mov     ebx, eax
0x1801ac7c3  test    eax, eax
0x1801ac7c5  jle     short loc_1801AC7D0
0x1801ac7c7  movzx   ebx, ax
0x1801ac7ca  or      ebx, 80070000h
0x1801ac7d0  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801ac7d6  test    eax, eax
0x1801ac7d8  jnz     short loc_1801AC7F1
0x1801ac7da  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801ac7e0  jz      loc_1801AC869
0x1801ac7e6  xor     ecx, ecx; level
0x1801ac7e8  call    IsWppLevelEnabled
0x1801ac7ed  test    al, al
0x1801ac7ef  jz      short loc_1801AC869
0x1801ac7f1  mov     r8d, 237h
0x1801ac7f7  jmp     short loc_1801AC843
0x1801ac7f9  xor     ebx, ebx
0x1801ac7fb  mov     cs:?_pwszFQDN@CRpcResolver@@0PEAGEA, rsi; ushort * CRpcResolver::_pwszFQDN
0x1801ac802  jmp     short loc_1801AC869
0x1801ac804  mov     ebx, 8007000Eh
0x1801ac809  jmp     short loc_1801AC869
0x1801ac80b  call    cs:__imp_GetLastError
0x1801ac811  mov     ebx, eax
0x1801ac813  test    eax, eax
0x1801ac815  jle     short loc_1801AC820
0x1801ac817  movzx   ebx, ax
0x1801ac81a  or      ebx, 80070000h
0x1801ac820  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801ac826  test    eax, eax
0x1801ac828  jnz     short loc_1801AC83D
0x1801ac82a  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801ac830  jz      short loc_1801AC869
0x1801ac832  xor     ecx, ecx; level
0x1801ac834  call    IsWppLevelEnabled
0x1801ac839  test    al, al
0x1801ac83b  jz      short loc_1801AC869
0x1801ac83d  mov     r8d, 243h; line
0x1801ac843  lea     rax, aHresult; "%!HRESULT!"
0x1801ac84a  mov     [rsp+38h+var_10], ebx; <args_0>
0x1801ac84e  xor     r9d, r9d; level
0x1801ac851  mov     [rsp+38h+format], rax; format
0x1801ac856  lea     ppwszFQDN, aCrpcresolverGe; "CRpcResolver::GetFQDN"
0x1801ac85d  lea     rcx, aOnecoreComComb_138; "onecore\\com\\combase\\dcomrem\\resolve"...
0x1801ac864  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1801ac869  test    ebx, ebx
0x1801ac86b  js      short loc_1801AC877
0x1801ac86d  mov     rcx, cs:?_pwszFQDN@CRpcResolver@@0PEAGEA; ushort * CRpcResolver::_pwszFQDN
0x1801ac874  mov     [rdi], rcx
0x1801ac877  lea     rcx, ?_mxsResolver@CRpcResolver@@0VCOleStaticMutexSem@@A; this
0x1801ac87e  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x1801ac883  mov     eax, ebx
0x1801ac885  mov     rbx, [rsp+38h+arg_8]
0x1801ac88a  mov     rsi, [rsp+38h+arg_10]
0x1801ac88f  add     rsp, 30h
0x1801ac893  pop     rdi
0x1801ac894  retn
```
