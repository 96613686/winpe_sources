# GetLoggedOnUserImpersonationToken(void * *)

- ea: `0x180012ff0`
- end: `0x180013219`
- name: `?GetLoggedOnUserImpersonationToken@@YAJPEAPEAX@Z`
- size: `553`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012274`

## callees

- `0x180006f94`
- `0x180008584`
- `0x18000910c`
- `0x18000cc14`
- `0x18000cc34`
- `0x1800102ec`
- `0x180010330`
- `0x180012ff0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800130ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001315e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800130ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001315e`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18001317c`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18001317c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18001307d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18001307d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18001310f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18001310f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180013050`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180013050`

## string_xrefs

- `0x18001308b`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180013121`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x18001318a`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800131e5`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetLoggedOnUserImpersonationToken(void **a1)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  _DWORD *v5; // rcx
  __int64 v6; // rdi
  const char *v7; // r9
  const char *v8; // r9
  HANDLE v9; // rcx
  int pCount; // [rsp+20h] [rbp-20h]
  HANDLE hObject; // [rsp+30h] [rbp-10h] BYREF
  PVOID pMemory; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD v15; // [rsp+60h] [rbp+20h] BYREF
  char v16; // [rsp+68h] [rbp+28h] BYREF

  *a1 = 0;
  pMemory = 0;
  hObject = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() && (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v15 = 0;
    pMemory = 0;
    if ( !WTSEnumerateSessionsW(0, 0, 1u, (PWTS_SESSION_INFOW *)&pMemory, &v15) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xE2,
                    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
                    v2);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      goto LABEL_21;
    }
    v4 = 0;
    v5 = pMemory;
    while ( (unsigned int)v4 < v15 )
    {
      v6 = 3 * v4;
      if ( *((_DWORD *)pMemory + 6 * v4) && !*((_DWORD *)pMemory + 6 * v4 + 4) )
      {
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
          CloseHandle(hObject);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
          v5 = pMemory;
        }
        hObject = 0;
        if ( !WTSQueryUserToken(v5[2 * v6], &hObject) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xED,
                        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
                        v7);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
          goto LABEL_21;
        }
        break;
      }
      v4 = (unsigned int)(v4 + 1);
    }
  }
  else
  {
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v15);
      CloseHandle(hObject);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v15);
    }
    hObject = 0;
    if ( !(unsigned int)QueryUserToken(0, &hObject) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xF9,
                    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
                    v8);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      goto LABEL_21;
    }
  }
  v9 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    hObject = 0;
    *a1 = v9;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<_WTS_SESSION_INFOW *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTS_SESSION_INFOW *,_WTS_SESSION_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WTS_SESSION_INFOW *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTS_SESSION_INFOW *,_WTS_SESSION_INFOW *,0,std::nullptr_t>>(&pMemory);
    return 0;
  }
  LastError = -2145844841;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFE,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
    (const char *)0x80190197LL,
    pCount);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<_WTS_SESSION_INFOW *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTS_SESSION_INFOW *,_WTS_SESSION_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WTS_SESSION_INFOW *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTS_SESSION_INFOW *,_WTS_SESSION_INFOW *,0,std::nullptr_t>>(&pMemory);
  return LastError;
}

```

## disassembly

```asm
0x180012ff0  mov     [rsp-18h+arg_10], rbx
0x180012ff5  push    rbp
0x180012ff6  push    rsi
0x180012ff7  push    rdi
0x180012ff8  mov     rbp, rsp
0x180012ffb  sub     rsp, 40h
0x180012fff  mov     rsi, rcx
0x180013002  mov     qword ptr [rcx], 0
0x180013009  mov     [rbp+pMemory], 0
0x180013011  mov     [rbp+hObject], 0
0x180013019  call    IsWTSEnumerateSessionsWPresent
0x18001301e  test    al, al
0x180013020  jz      loc_180013143
0x180013026  call    IsWTSEnumerateSessionsWPresent
0x18001302b  test    al, al
0x18001302d  jz      loc_180013143
0x180013033  mov     [rbp+arg_0], 0
0x18001303a  mov     rbx, [rbp+pMemory]
0x18001303e  test    rbx, rbx
0x180013041  jz      short loc_180013060
0x180013043  lea     rcx, [rbp+arg_8]; this
0x180013047  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001304c  nop
0x18001304d  mov     rcx, rbx; pMemory
0x180013050  call    cs:__imp_WTSFreeMemory
0x180013056  nop
0x180013057  lea     rcx, [rbp+arg_8]; this
0x18001305b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180013060  mov     [rbp+pMemory], 0
0x180013068  lea     rax, [rbp+arg_0]
0x18001306c  mov     qword ptr [rsp+40h+pCount], rax; int
0x180013071  lea     r9, [rbp+pMemory]; ppSessionInfo
0x180013075  xor     edx, edx; Reserved
0x180013077  xor     ecx, ecx; hServer
0x180013079  lea     r8d, [rdx+1]; Version
0x18001307d  call    cs:__imp_WTSEnumerateSessionsW
0x180013083  test    eax, eax
0x180013085  jnz     short loc_1800130AD
0x180013087  mov     rcx, [rbp+18h]; this
0x18001308b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180013092  mov     edx, 0E2h; void *
0x180013097  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001309c  mov     ebx, eax
0x18001309e  lea     rcx, [rbp+hObject]
0x1800130a2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800130a7  nop
0x1800130a8  jmp     loc_180013201
0x1800130ad  xor     edx, edx
0x1800130af  mov     rcx, [rbp+pMemory]
0x1800130b3  cmp     edx, [rbp+arg_0]
0x1800130b6  jnb     loc_1800131A9
0x1800130bc  lea     rdi, [rdx+rdx*2]
0x1800130c0  cmp     dword ptr [rcx+rdi*8], 0
0x1800130c4  jz      short loc_1800130CD
0x1800130c6  cmp     dword ptr [rcx+rdi*8+10h], 0
0x1800130cb  jz      short loc_1800130D1
0x1800130cd  inc     edx
0x1800130cf  jmp     short loc_1800130B3
0x1800130d1  mov     rbx, [rbp+hObject]
0x1800130d5  lea     rax, [rbx-1]
0x1800130d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800130dd  ja      short loc_180013100
0x1800130df  lea     rcx, [rbp+arg_8]; this
0x1800130e3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800130e8  nop
0x1800130e9  mov     rcx, rbx; hObject
0x1800130ec  call    cs:__imp_CloseHandle
0x1800130f2  nop
0x1800130f3  lea     rcx, [rbp+arg_8]; this
0x1800130f7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800130fc  mov     rcx, [rbp+pMemory]
0x180013100  mov     [rbp+hObject], 0
0x180013108  lea     rdx, [rbp+hObject]; phToken
0x18001310c  mov     ecx, [rcx+rdi*8]; SessionId
0x18001310f  call    cs:__imp_WTSQueryUserToken
0x180013115  test    eax, eax
0x180013117  jnz     loc_1800131A9
0x18001311d  mov     rcx, [rbp+18h]; this
0x180013121  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180013128  mov     edx, 0EDh; void *
0x18001312d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013132  mov     ebx, eax
0x180013134  lea     rcx, [rbp+hObject]
0x180013138  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001313d  nop
0x18001313e  jmp     loc_180013201
0x180013143  mov     rbx, [rbp+hObject]
0x180013147  lea     rax, [rbx-1]
0x18001314b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001314f  ja      short loc_18001316E
0x180013151  lea     rcx, [rbp+arg_0]; this
0x180013155  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001315a  nop
0x18001315b  mov     rcx, rbx; hObject
0x18001315e  call    cs:__imp_CloseHandle
0x180013164  nop
0x180013165  lea     rcx, [rbp+arg_0]; this
0x180013169  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001316e  mov     [rbp+hObject], 0
0x180013176  lea     rdx, [rbp+hObject]
0x18001317a  xor     ecx, ecx
0x18001317c  call    cs:__imp_QueryUserToken
0x180013182  test    eax, eax
0x180013184  jnz     short loc_1800131A9
0x180013186  mov     rcx, [rbp+18h]; this
0x18001318a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180013191  mov     edx, 0F9h; void *
0x180013196  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001319b  mov     ebx, eax
0x18001319d  lea     rcx, [rbp+hObject]
0x1800131a1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800131a6  nop
0x1800131a7  jmp     short loc_180013201
0x1800131a9  mov     rcx, [rbp+hObject]
0x1800131ad  lea     rax, [rcx-1]
0x1800131b1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800131b5  ja      short loc_1800131D9
0x1800131b7  mov     [rbp+hObject], 0
0x1800131bf  mov     [rsi], rcx
0x1800131c2  lea     rcx, [rbp+hObject]
0x1800131c6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800131cb  nop
0x1800131cc  lea     rcx, [rbp+pMemory]
0x1800131d0  call    ??1?$unique_storage@U?$resource_policy@PEAU_WTS_SESSION_INFOW@@P6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WTS_SESSION_INFOW *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTS_SESSION_INFOW *,_WTS_SESSION_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WTS_SESSION_INFOW *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTS_SESSION_INFOW *,_WTS_SESSION_INFOW *,0,std::nullptr_t>>(void)
0x1800131d5  xor     eax, eax
0x1800131d7  jmp     short loc_18001320C
0x1800131d9  mov     rcx, [rbp+18h]; this
0x1800131dd  mov     ebx, 80190197h
0x1800131e2  mov     r9d, ebx; char *
0x1800131e5  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800131ec  mov     edx, 0FEh; void *
0x1800131f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800131f6  nop
0x1800131f7  lea     rcx, [rbp+hObject]
0x1800131fb  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013200  nop
0x180013201  lea     rcx, [rbp+pMemory]
0x180013205  call    ??1?$unique_storage@U?$resource_policy@PEAU_WTS_SESSION_INFOW@@P6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WTS_SESSION_INFOW *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTS_SESSION_INFOW *,_WTS_SESSION_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WTS_SESSION_INFOW *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTS_SESSION_INFOW *,_WTS_SESSION_INFOW *,0,std::nullptr_t>>(void)
0x18001320a  mov     eax, ebx
0x18001320c  mov     rbx, [rsp+40h+arg_10]
0x180013211  add     rsp, 40h
0x180013215  pop     rdi
0x180013216  pop     rsi
0x180013217  pop     rbp
0x180013218  retn
```
