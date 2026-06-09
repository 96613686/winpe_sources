# CCdnAddrPool::_ResolveHost(char const *,bool)

- ea: `0x1800c3128`
- end: `0x1800c32eb`
- name: `?_ResolveHost@CCdnAddrPool@@IEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUaddrinfoex2W@@P6AXPEAU1@@Z$1?addrinfo_deleter@CHostAddressInfo@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBD_N@Z`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800c2a30`

## callees

- `0x18000ef98`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800a979c`
- `0x1800c3128`
- `0x1800f82f0`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c317c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c317c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3288`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c329b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c329b`
- `WS2_32!GetAddrInfoExW` at `0x1800c3249`
- `WS2_32!GetAddrInfoExW` at `0x1800c3249`
- `WS2_32!FreeAddrInfoExW` at `0x1800c3293`
- `WS2_32!FreeAddrInfoExW` at `0x1800c3293`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3257`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3257`
- `DNSAPI!DnsFlushResolverCacheEntry_A` at `0x1800c316d`
- `DNSAPI!DnsFlushResolverCacheEntry_A` at `0x1800c316d`

## string_xrefs

- `0x1800c31a1`: `DnsFlushResolverCacheEntry failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WCHAR *__fastcall CCdnAddrPool::_ResolveHost(__int64 a1, WCHAR *a2, const char *a3, unsigned __int8 a4)
{
  int v4; // r14d
  signed int v7; // ebx
  signed int LastError; // eax
  unsigned int v9; // r9d
  const WCHAR *v10; // rcx
  int Error; // eax
  PADDRINFOEXW v12; // r14
  struct addrinfoexW *v13; // rsi
  DWORD v14; // ebx
  PCWSTR pName[5]; // [rsp+58h] [rbp-71h] BYREF
  PADDRINFOEXW ppResult; // [rsp+80h] [rbp-49h] BYREF
  ADDRINFOEXW hints; // [rsp+90h] [rbp-39h] BYREF

  v4 = a4;
  pName[4] = a2;
  *(_QWORD *)a2 = 0;
  v7 = -2147467259;
  if ( !(unsigned int)DnsFlushResolverCacheEntry_A(a3) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v9 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v9 = LastError;
    }
    else
    {
      v9 = -2147467259;
    }
    LogResult(5u, "CCdnAddrPool::_ResolveHost", 0xE0u, v9, "DnsFlushResolverCacheEntry failed");
  }
  memset(&hints.ai_socktype, 0, 0x50u);
  hints.ai_flags = 132098;
  hints.ai_family = 2 * (v4 ^ 1);
  ppResult = 0;
  UTF8toWstr(pName, a3, 0);
  v10 = (const WCHAR *)pName;
  if ( pName[3] > (PCWSTR)7 )
    v10 = pName[0];
  if ( GetAddrInfoExW(v10, 0, 0xCu, 0, &hints, &ppResult, 0, 0, 0, 0) )
  {
    Error = WSAGetLastError();
    if ( Error )
    {
      v7 = (unsigned __int16)Error | 0x80070000;
      if ( Error <= 0 )
        v7 = Error;
    }
  }
  else
  {
    v7 = 0;
  }
  std::wstring::~wstring(pName);
  if ( v7 < 0 )
  {
    LogMessage(3u, "CCdnAddrPool::_ResolveHost", 0xFCu, "GetAddrInfoEx failed (0x%x), ignoring host '%s'", v7, a3);
  }
  else
  {
    v12 = ppResult;
    v13 = *(struct addrinfoexW **)a2;
    if ( *(_QWORD *)a2 )
    {
      v14 = GetLastError();
      FreeAddrInfoExW(v13);
      SetLastError(v14);
    }
    *(_QWORD *)a2 = v12;
  }
  return a2;
}

```

## disassembly

```asm
0x1800c3128  push    rbp
0x1800c312a  push    rbx
0x1800c312b  push    rsi
0x1800c312c  push    rdi
0x1800c312d  push    r14
0x1800c312f  lea     rbp, [rsp-37h]
0x1800c3134  sub     rsp, 100h
0x1800c313b  mov     rax, cs:__security_cookie
0x1800c3142  xor     rax, rsp
0x1800c3145  mov     [rbp+57h+var_30], rax
0x1800c3149  movzx   r14d, r9b
0x1800c314d  mov     rsi, r8
0x1800c3150  mov     rdi, rdx
0x1800c3153  mov     [rbp+57h+var_A8], rdx
0x1800c3157  mov     [rbp+57h+var_D0], 0
0x1800c315e  xor     eax, eax
0x1800c3160  mov     [rdx], rax
0x1800c3163  mov     [rbp+57h+var_D0], 1
0x1800c316a  mov     rcx, r8
0x1800c316d  call    cs:__imp_DnsFlushResolverCacheEntry_A
0x1800c3173  mov     ebx, 80004005h
0x1800c3178  test    eax, eax
0x1800c317a  jnz     short loc_1800C31C4
0x1800c317c  call    cs:__imp_GetLastError
0x1800c3182  test    eax, eax
0x1800c3184  jz      short loc_1800C319E
0x1800c3186  movzx   r9d, ax
0x1800c318a  or      r9d, 80070000h
0x1800c3191  test    eax, eax
0x1800c3193  cmovle  r9d, eax
0x1800c3197  test    r9d, r9d
0x1800c319a  jns     short loc_1800C31C4
0x1800c319c  jmp     short loc_1800C31A1
0x1800c319e  mov     r9d, ebx; int
0x1800c31a1  lea     rax, aDnsflushresolv_0; "DnsFlushResolverCacheEntry failed"
0x1800c31a8  mov     [rsp+120h+hints], rax; char *
0x1800c31ad  mov     r8d, 0E0h; unsigned int
0x1800c31b3  lea     rdx, aCcdnaddrpoolRe; "CCdnAddrPool::_ResolveHost"
0x1800c31ba  mov     ecx, 5; unsigned __int8
0x1800c31bf  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800c31c4  xor     edx, edx; Val
0x1800c31c6  lea     r8d, [rdx+50h]; Size
0x1800c31ca  lea     rcx, [rbp+57h+var_90.ai_socktype]; void *
0x1800c31ce  call    memset
0x1800c31d3  mov     [rbp+57h+var_90.ai_flags], 20402h
0x1800c31da  mov     eax, r14d
0x1800c31dd  xor     eax, 1
0x1800c31e0  add     eax, eax
0x1800c31e2  mov     [rbp+57h+var_90.ai_family], eax
0x1800c31e5  mov     [rbp+57h+var_A0], 0
0x1800c31ed  xor     r8d, r8d
0x1800c31f0  mov     rdx, rsi
0x1800c31f3  lea     rcx, [rbp+57h+pName]
0x1800c31f7  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800c31fc  lea     rcx, [rbp+57h+pName]
0x1800c3200  cmp     [rbp+57h+var_B0], 7
0x1800c3205  cmova   rcx, [rbp+57h+pName]; pName
0x1800c320a  mov     [rsp+120h+lpHandle], 0; lpHandle
0x1800c3213  mov     [rsp+120h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800c321c  mov     [rsp+120h+lpOverlapped], 0; lpOverlapped
0x1800c3225  mov     [rsp+120h+timeout], 0; timeout
0x1800c322e  lea     rax, [rbp+57h+var_A0]
0x1800c3232  mov     [rsp+120h+ppResult], rax; ppResult
0x1800c3237  lea     rax, [rbp+57h+var_90]
0x1800c323b  mov     [rsp+120h+hints], rax; hints
0x1800c3240  xor     r9d, r9d; lpNspId
0x1800c3243  xor     edx, edx; pServiceName
0x1800c3245  lea     r8d, [r9+0Ch]; dwNameSpace
0x1800c3249  call    cs:__imp_GetAddrInfoExW
0x1800c324f  test    eax, eax
0x1800c3251  jnz     short loc_1800C3257
0x1800c3253  xor     ebx, ebx
0x1800c3255  jmp     short loc_1800C326F
0x1800c3257  call    cs:__imp_WSAGetLastError
0x1800c325d  test    eax, eax
0x1800c325f  jz      short loc_1800C326F
0x1800c3261  movzx   ebx, ax
0x1800c3264  or      ebx, 80070000h
0x1800c326a  test    eax, eax
0x1800c326c  cmovle  ebx, eax
0x1800c326f  lea     rcx, [rbp+57h+pName]
0x1800c3273  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c3278  test    ebx, ebx
0x1800c327a  js      short loc_1800C32A6
0x1800c327c  mov     r14, [rbp+57h+var_A0]
0x1800c3280  mov     rsi, [rdi]
0x1800c3283  test    rsi, rsi
0x1800c3286  jz      short loc_1800C32A1
0x1800c3288  call    cs:__imp_GetLastError
0x1800c328e  mov     ebx, eax
0x1800c3290  mov     rcx, rsi; pAddrInfoEx
0x1800c3293  call    cs:__imp_FreeAddrInfoExW
0x1800c3299  mov     ecx, ebx; dwErrCode
0x1800c329b  call    cs:__imp_SetLastError
0x1800c32a1  mov     [rdi], r14
0x1800c32a4  jmp     short loc_1800C32CD
0x1800c32a6  mov     [rsp+120h+ppResult], rsi
0x1800c32ab  mov     dword ptr [rsp+120h+hints], ebx
0x1800c32af  lea     r9, aGetaddrinfoexF; "GetAddrInfoEx failed (0x%x), ignoring h"...
0x1800c32b6  mov     r8d, 0FCh; unsigned int
0x1800c32bc  lea     rdx, aCcdnaddrpoolRe; "CCdnAddrPool::_ResolveHost"
0x1800c32c3  mov     ecx, 3; unsigned __int8
0x1800c32c8  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800c32cd  mov     rax, rdi
0x1800c32d0  mov     rcx, [rbp+57h+var_30]
0x1800c32d4  xor     rcx, rsp; StackCookie
0x1800c32d7  call    __security_check_cookie
0x1800c32dc  add     rsp, 100h
0x1800c32e3  pop     r14
0x1800c32e5  pop     rdi
0x1800c32e6  pop     rsi
0x1800c32e7  pop     rbx
0x1800c32e8  pop     rbp
0x1800c32e9  retn
```
