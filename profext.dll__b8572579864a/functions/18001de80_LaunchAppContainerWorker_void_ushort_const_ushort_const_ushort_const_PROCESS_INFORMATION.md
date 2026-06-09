# LaunchAppContainerWorker(void *,ushort const *,ushort const *,ushort const *,_PROCESS_INFORMATION *)

- ea: `0x18001de80`
- end: `0x18001e27a`
- name: `?LaunchAppContainerWorker@@YAJPEAXPEBG11PEAU_PROCESS_INFORMATION@@@Z`
- size: `1018`
- prototype: `__int64 __usercall@<rax>(HANDLE hToken@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct _PROCESS_INFORMATION *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004594`
- `0x18000c7d4`
- `0x18000c938`
- `0x18000f864`
- `0x18000f884`
- `0x18001de80`
- `0x18001e2b8`
- `0x18001e374`
- `0x180020664`
- `0x1800227f2`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001df6f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001df95`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e231`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e257`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001df6f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001df95`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e231`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfc9`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001e0ba`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001e206`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001e0ba`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001e206`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001dfb9`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001e08b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001dfb9`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001e08b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001e0ec`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001e128`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001e173`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001e0ec`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001e128`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001e173`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001e1e7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001e1e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e004`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e004`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e02c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e02c`

## string_xrefs

- `0x18001deb5`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001df49`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001dfe1`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001e05d`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001e0a7`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LaunchAppContainerWorker(
        HANDLE hToken,
        char *a2,
        const unsigned __int16 *a3,
        WCHAR *a4,
        LPPROCESS_INFORMATION a5)
{
  __int64 v9; // rdx
  struct _PROCESS_INFORMATION *lpProcessInformation; // rsi
  int LpacLaunchParameters; // eax
  unsigned int LastError; // edi
  __int64 v14; // rcx
  void *v15; // rbx
  const char *v16; // r9
  HLOCAL v17; // rbx
  const char *v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  void *v21; // rbx
  int cbSize; // [rsp+20h] [rbp-E0h]
  int cbSizea; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  PVOID lpValue[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v26; // [rsp+78h] [rbp-88h]
  __int64 v27; // [rsp+88h] [rbp-78h]
  ULONG_PTR Size; // [rsp+90h] [rbp-70h] BYREF
  __int128 v29; // [rsp+98h] [rbp-68h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  __int128 Value; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-40h]
  struct _STARTUPINFOW StartupInfo; // [rsp+D0h] [rbp-30h] BYREF
  HLOCAL v34; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]
  int v36; // [rsp+198h] [rbp+98h] BYREF

  if ( !a2 )
  {
    v9 = 102;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
      (const char *)0x80070057LL,
      cbSize);
    return 2147942487LL;
  }
  lpProcessInformation = a5;
  if ( !a5 )
  {
    v9 = 103;
    goto LABEL_3;
  }
  Value = 0;
  v32 = 0;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  lpValue[0] = 0;
  lpValue[1] = 0;
  wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(lpValue);
  LpacLaunchParameters = LpacRegHelper::GetLpacLaunchParameters(a2, (__int64)lpValue);
  LastError = LpacLaunchParameters;
  if ( LpacLaunchParameters < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
      (const char *)(unsigned int)LpacLaunchParameters,
      cbSizea);
LABEL_8:
    wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(lpValue);
    v14 = v29;
    if ( (_QWORD)v29 )
      operator delete((void *)v29);
    v15 = (void *)v26;
    if ( (_QWORD)v26 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Destroy(
        v14,
        v26,
        *((_QWORD *)&v26 + 1));
      operator delete(v15);
    }
    return LastError;
  }
  Size = 0;
  if ( !InitializeProcThreadAttributeList(0, 3u, 0, &Size) && GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7E,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
                  v16);
    goto LABEL_8;
  }
  v17 = LocalAlloc(0, Size);
  hMem = v17;
  if ( !v17 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
      (const char *)0x8007000ELL,
      cbSizea);
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&hMem);
    goto LABEL_8;
  }
  if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v17, 3u, 0, &Size) )
  {
    v19 = 150;
LABEL_21:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v19,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
                  v18);
    DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)hMem);
    goto LABEL_18;
  }
  if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x20009u, &Value, 0x18u, 0, 0) )
  {
    v19 = 161;
    goto LABEL_21;
  }
  if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x20007u, lpValue[0], 0x10u, 0, 0) )
  {
    v19 = 172;
    goto LABEL_21;
  }
  v36 = 1;
  if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x2000Fu, &v36, 4u, 0, 0) )
  {
    v19 = 185;
    goto LABEL_21;
  }
  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  StartupInfo.cb = 112;
  v34 = hMem;
  if ( !CreateProcessAsUserW(hToken, a3, a4, 0, 0, 0, 0x80000u, 0, 0, &StartupInfo, lpProcessInformation) )
  {
    v19 = 204;
    goto LABEL_21;
  }
  DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)hMem);
  wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&hMem);
  wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(lpValue);
  v20 = v29;
  if ( (_QWORD)v29 )
    operator delete((void *)v29);
  v21 = (void *)v26;
  if ( (_QWORD)v26 )
  {
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Destroy(
      v20,
      v26,
      *((_QWORD *)&v26 + 1));
    operator delete(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x18001de80  push    rbp
0x18001de82  push    rbx
0x18001de83  push    rsi
0x18001de84  push    rdi
0x18001de85  push    r12
0x18001de87  push    r13
0x18001de89  push    r14
0x18001de8b  push    r15
0x18001de8d  lea     rbp, [rsp-48h]
0x18001de92  sub     rsp, 148h
0x18001de99  mov     r14, r9
0x18001de9c  mov     r15, r8
0x18001de9f  mov     rbx, rdx
0x18001dea2  mov     r12, rcx
0x18001dea5  xor     r13d, r13d
0x18001dea8  test    rdx, rdx
0x18001deab  jnz     short loc_18001DED2
0x18001dead  lea     edx, [rbx+66h]; void *
0x18001deb0  mov     ebx, 80070057h
0x18001deb5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001debc  mov     r9d, ebx; char *
0x18001debf  mov     rcx, [rbp+88h]; this
0x18001dec6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001decb  mov     eax, ebx
0x18001decd  jmp     loc_18001E265
0x18001ded2  mov     rsi, [rbp+80h+arg_20]
0x18001ded9  test    rsi, rsi
0x18001dedc  jnz     short loc_18001DEE3
0x18001dede  lea     edx, [rsi+67h]
0x18001dee1  jmp     short loc_18001DEB0
0x18001dee3  xorps   xmm0, xmm0
0x18001dee6  xor     eax, eax
0x18001dee8  movups  [rbp+80h+Value], xmm0
0x18001deec  mov     [rbp+80h+var_C0], rax
0x18001def0  xorps   xmm1, xmm1
0x18001def3  movdqu  [rsp+180h+var_108], xmm1
0x18001def9  mov     [rbp+80h+var_F8], r13
0x18001defd  movdqu  [rbp+80h+var_E8], xmm0
0x18001df02  mov     [rbp+80h+var_D8], r13
0x18001df06  mov     [rsp+180h+lpValue], r13
0x18001df0b  mov     [rsp+180h+var_110], r13
0x18001df10  lea     rcx, [rsp+180h+lpValue]
0x18001df15  call    ?reset@?$unique_any_array_ptr@_KU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18001df1a  lea     rax, [rsp+180h+lpValue]
0x18001df1f  mov     [rsp+180h+cbSize], rax; int
0x18001df24  lea     r9, [rbp+80h+var_E8]
0x18001df28  lea     r8, [rsp+180h+var_108]
0x18001df2d  lea     rdx, [rbp+80h+Value]
0x18001df31  mov     rcx, rbx; char *
0x18001df34  call    ?GetLpacLaunchParameters@LpacRegHelper@@SAJPEBGPEAU_SECURITY_CAPABILITIES@@AEAV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAV?$vector@U_SID_AND_ATTRIBUTES@@V?$allocator@U_SID_AND_ATTRIBUTES@@@std@@@4@PEAPEA_KK@Z; LpacRegHelper::GetLpacLaunchParameters(ushort const *,_SECURITY_CAPABILITIES *,std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &,std::vector<_SID_AND_ATTRIBUTES> &,unsigned __int64 * *,ulong)
0x18001df39  mov     edi, eax
0x18001df3b  test    eax, eax
0x18001df3d  jns     short loc_18001DFA8
0x18001df3f  mov     rcx, [rbp+88h]; this
0x18001df46  mov     r9d, eax; char *
0x18001df49  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001df50  mov     edx, 74h ; 't'; void *
0x18001df55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df5a  nop
0x18001df5b  lea     rcx, [rsp+180h+lpValue]
0x18001df60  call    ?reset@?$unique_any_array_ptr@_KU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18001df65  nop
0x18001df66  mov     rcx, qword ptr [rbp+80h+var_E8]
0x18001df6a  test    rcx, rcx
0x18001df6d  jz      short loc_18001DF7C
0x18001df6f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001df76  nop     dword ptr [rax+rax+00h]
0x18001df7b  nop
0x18001df7c  mov     rbx, qword ptr [rsp+180h+var_108]
0x18001df81  test    rbx, rbx
0x18001df84  jz      short loc_18001DFA1
0x18001df86  mov     r8, qword ptr [rbp+80h+var_108+8]
0x18001df8a  mov     rdx, rbx
0x18001df8d  call    ?_Destroy@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@IEAAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@0@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Destroy(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *)
0x18001df92  mov     rcx, rbx
0x18001df95  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001df9c  nop     dword ptr [rax+rax+00h]
0x18001dfa1  mov     eax, edi
0x18001dfa3  jmp     loc_18001E265
0x18001dfa8  mov     [rbp+80h+Size], r13
0x18001dfac  lea     r9, [rbp+80h+Size]; lpSize
0x18001dfb0  xor     r8d, r8d; dwFlags
0x18001dfb3  lea     edx, [r8+3]; dwAttributeCount
0x18001dfb7  xor     ecx, ecx; lpAttributeList
0x18001dfb9  call    cs:__imp_InitializeProcThreadAttributeList
0x18001dfc0  nop     dword ptr [rax+rax+00h]
0x18001dfc5  test    eax, eax
0x18001dfc7  jnz     short loc_18001DFF9
0x18001dfc9  call    cs:__imp_GetLastError
0x18001dfd0  nop     dword ptr [rax+rax+00h]
0x18001dfd5  cmp     eax, 7Ah ; 'z'
0x18001dfd8  jz      short loc_18001DFF9
0x18001dfda  mov     rcx, [rbp+88h]; this
0x18001dfe1  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dfe8  mov     edx, 7Eh ; '~'; void *
0x18001dfed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001dff2  mov     edi, eax
0x18001dff4  jmp     loc_18001DF5B
0x18001dff9  mov     [rsp+180h+hMem], r13
0x18001dffe  mov     rdx, [rbp+80h+Size]; uBytes
0x18001e002  xor     ecx, ecx; uFlags
0x18001e004  call    cs:__imp_LocalAlloc
0x18001e00b  nop     dword ptr [rax+rax+00h]
0x18001e010  mov     rbx, rax
0x18001e013  mov     rdi, [rsp+180h+hMem]
0x18001e018  test    rdi, rdi
0x18001e01b  jz      short loc_18001E044
0x18001e01d  lea     rcx, [rbp+80h+arg_8]; this
0x18001e024  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001e029  mov     rcx, rdi; hMem
0x18001e02c  call    cs:__imp_LocalFree
0x18001e033  nop     dword ptr [rax+rax+00h]
0x18001e038  lea     rcx, [rbp+80h+arg_8]; this
0x18001e03f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001e044  mov     [rsp+180h+hMem], rbx
0x18001e049  test    rbx, rbx
0x18001e04c  jnz     short loc_18001E07D
0x18001e04e  mov     rcx, [rbp+88h]; this
0x18001e055  mov     edi, 8007000Eh
0x18001e05a  mov     r9d, edi; char *
0x18001e05d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001e064  mov     edx, 83h; void *
0x18001e069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e06e  lea     rcx, [rsp+180h+hMem]
0x18001e073  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001e078  jmp     loc_18001DF5B
0x18001e07d  lea     r9, [rbp+80h+Size]; lpSize
0x18001e081  xor     r8d, r8d; dwFlags
0x18001e084  lea     edx, [r8+3]; dwAttributeCount
0x18001e088  mov     rcx, rbx; lpAttributeList
0x18001e08b  call    cs:__imp_InitializeProcThreadAttributeList
0x18001e092  nop     dword ptr [rax+rax+00h]
0x18001e097  test    eax, eax
0x18001e099  jnz     short loc_18001E0C8
0x18001e09b  mov     edx, 96h; void *
0x18001e0a0  mov     rcx, [rbp+88h]; this
0x18001e0a7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001e0ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e0b3  mov     edi, eax
0x18001e0b5  mov     rcx, [rsp+180h+hMem]; lpAttributeList
0x18001e0ba  call    cs:__imp_DeleteProcThreadAttributeList
0x18001e0c1  nop     dword ptr [rax+rax+00h]
0x18001e0c6  jmp     short loc_18001E06E
0x18001e0c8  mov     [rsp+180h+lpReturnSize], r13; lpReturnSize
0x18001e0cd  mov     [rsp+180h+lpPreviousValue], r13; lpPreviousValue
0x18001e0d2  mov     [rsp+180h+cbSize], 18h; cbSize
0x18001e0db  lea     r9, [rbp+80h+Value]; lpValue
0x18001e0df  xor     edx, edx; dwFlags
0x18001e0e1  mov     r8d, 20009h; Attribute
0x18001e0e7  mov     rcx, [rsp+180h+hMem]; lpAttributeList
0x18001e0ec  call    cs:__imp_UpdateProcThreadAttribute
0x18001e0f3  nop     dword ptr [rax+rax+00h]
0x18001e0f8  test    eax, eax
0x18001e0fa  jnz     short loc_18001E103
0x18001e0fc  mov     edx, 0A1h
0x18001e101  jmp     short loc_18001E0A0
0x18001e103  mov     [rsp+180h+lpReturnSize], r13; lpReturnSize
0x18001e108  mov     [rsp+180h+lpPreviousValue], r13; lpPreviousValue
0x18001e10d  mov     [rsp+180h+cbSize], 10h; cbSize
0x18001e116  mov     r9, [rsp+180h+lpValue]; lpValue
0x18001e11b  xor     edx, edx; dwFlags
0x18001e11d  mov     r8d, 20007h; Attribute
0x18001e123  mov     rcx, [rsp+180h+hMem]; lpAttributeList
0x18001e128  call    cs:__imp_UpdateProcThreadAttribute
0x18001e12f  nop     dword ptr [rax+rax+00h]
0x18001e134  test    eax, eax
0x18001e136  jnz     short loc_18001E142
0x18001e138  mov     edx, 0ACh
0x18001e13d  jmp     loc_18001E0A0
0x18001e142  mov     [rbp+80h+arg_8], 1
0x18001e14c  mov     [rsp+180h+lpReturnSize], r13; lpReturnSize
0x18001e151  mov     [rsp+180h+lpPreviousValue], r13; lpPreviousValue
0x18001e156  mov     [rsp+180h+cbSize], 4; cbSize
0x18001e15f  lea     r9, [rbp+80h+arg_8]; lpValue
0x18001e166  xor     edx, edx; dwFlags
0x18001e168  mov     r8d, 2000Fh; Attribute
0x18001e16e  mov     rcx, [rsp+180h+hMem]; lpAttributeList
0x18001e173  call    cs:__imp_UpdateProcThreadAttribute
0x18001e17a  nop     dword ptr [rax+rax+00h]
0x18001e17f  test    eax, eax
0x18001e181  jnz     short loc_18001E18D
0x18001e183  mov     edx, 0B9h
0x18001e188  jmp     loc_18001E0A0
0x18001e18d  xor     eax, eax
0x18001e18f  mov     dword ptr [rbp+80h+StartupInfo+4], eax
0x18001e192  xor     edx, edx; Val
0x18001e194  lea     r8d, [rax+68h]; Size
0x18001e198  lea     rcx, [rbp+80h+StartupInfo.lpReserved]; void *
0x18001e19c  call    memset_0
0x18001e1a1  mov     [rbp+80h+StartupInfo.cb], 70h ; 'p'
0x18001e1a8  mov     rax, [rsp+180h+hMem]
0x18001e1ad  mov     [rbp+80h+var_48], rax
0x18001e1b1  mov     [rsp+180h+lpProcessInformation], rsi; lpProcessInformation
0x18001e1b6  lea     rax, [rbp+80h+StartupInfo]
0x18001e1ba  mov     [rsp+180h+lpStartupInfo], rax; lpStartupInfo
0x18001e1bf  mov     [rsp+180h+lpCurrentDirectory], r13; lpCurrentDirectory
0x18001e1c4  mov     [rsp+180h+lpEnvironment], r13; lpEnvironment
0x18001e1c9  mov     dword ptr [rsp+180h+lpReturnSize], 80000h; dwCreationFlags
0x18001e1d1  mov     dword ptr [rsp+180h+lpPreviousValue], r13d; bInheritHandles
0x18001e1d6  mov     [rsp+180h+cbSize], r13; lpThreadAttributes
0x18001e1db  xor     r9d, r9d; lpProcessAttributes
0x18001e1de  mov     r8, r14; lpCommandLine
0x18001e1e1  mov     rdx, r15; lpApplicationName
0x18001e1e4  mov     rcx, r12; hToken
0x18001e1e7  call    cs:__imp_CreateProcessAsUserW
0x18001e1ee  nop     dword ptr [rax+rax+00h]
0x18001e1f3  test    eax, eax
0x18001e1f5  jnz     short loc_18001E201
0x18001e1f7  mov     edx, 0CCh
0x18001e1fc  jmp     loc_18001E0A0
0x18001e201  mov     rcx, [rsp+180h+hMem]; lpAttributeList
0x18001e206  call    cs:__imp_DeleteProcThreadAttributeList
0x18001e20d  nop     dword ptr [rax+rax+00h]
0x18001e212  lea     rcx, [rsp+180h+hMem]
0x18001e217  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001e21c  nop
0x18001e21d  lea     rcx, [rsp+180h+lpValue]
0x18001e222  call    ?reset@?$unique_any_array_ptr@_KU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18001e227  nop
0x18001e228  mov     rcx, qword ptr [rbp+80h+var_E8]
0x18001e22c  test    rcx, rcx
0x18001e22f  jz      short loc_18001E23E
0x18001e231  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e238  nop     dword ptr [rax+rax+00h]
0x18001e23d  nop
0x18001e23e  mov     rbx, qword ptr [rsp+180h+var_108]
0x18001e243  test    rbx, rbx
0x18001e246  jz      short loc_18001E263
0x18001e248  mov     r8, qword ptr [rbp+80h+var_108+8]
0x18001e24c  mov     rdx, rbx
0x18001e24f  call    ?_Destroy@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@IEAAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@0@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Destroy(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *)
0x18001e254  mov     rcx, rbx
0x18001e257  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e25e  nop     dword ptr [rax+rax+00h]
0x18001e263  xor     eax, eax
0x18001e265  add     rsp, 148h
0x18001e26c  pop     r15
0x18001e26e  pop     r14
0x18001e270  pop     r13
0x18001e272  pop     r12
0x18001e274  pop     rdi
0x18001e275  pop     rsi
0x18001e276  pop     rbx
0x18001e277  pop     rbp
0x18001e278  retn
```
