# ResetUserBrokerCookie(ulong)

- ea: `0x18005e4c0`
- end: `0x18005e580`
- name: `?ResetUserBrokerCookie@@YAJK@Z`
- size: `192`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180030d70`
- `0x18005e4c0`
- `0x18005e588`
- `0x18005e610`
- `0x18005e85c`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e560`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e560`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e4e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e4e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e4fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e4fc`

## pseudocode

```c
__int64 __fastcall ResetUserBrokerCookie(unsigned int a1)
{
  int v2; // ebx
  int v3; // ecx
  int v4; // r8d
  DWORD CurrentThreadId; // [rsp+48h] [rbp-20h] BYREF
  __int64 v7; // [rsp+4Ch] [rbp-1Ch]

  v2 = -2147467259;
  EnterCriticalSection(&g_csInit);
  if ( a1 )
  {
    v2 = EnsureCDSA();
    if ( v2 >= 0 )
    {
      v7 = 0;
      CurrentThreadId = GetCurrentThreadId();
      v2 = CDSA_Base<THREAD_GIT_MAPPING>::Search(v3, (unsigned int)&CurrentThreadId, v4, (unsigned int)CompareTids);
      if ( v2 < 0 )
        v2 = SetUserBroker(a1);
      else
        *((_DWORD *)DSA_GetItemPtr(*(HDSA *)g_pcdsaThreadData, 0) + 1) = a1;
    }
  }
  LeaveCriticalSection(&g_csInit);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005e4c0  mov     [rsp+arg_8], rbx
0x18005e4c5  push    rdi
0x18005e4c6  sub     rsp, 60h
0x18005e4ca  mov     rax, cs:__security_cookie
0x18005e4d1  xor     rax, rsp
0x18005e4d4  mov     [rsp+68h+var_10], rax
0x18005e4d9  mov     edi, ecx
0x18005e4db  mov     ebx, 80004005h
0x18005e4e0  lea     rcx, ?g_csInit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005e4e7  call    cs:__imp_EnterCriticalSection
0x18005e4ed  test    edi, edi
0x18005e4ef  jz      short loc_18005E559
0x18005e4f1  call    _EnsureCDSA
0x18005e4f6  mov     ebx, eax
0x18005e4f8  test    eax, eax
0x18005e4fa  js      short loc_18005E559
0x18005e4fc  call    cs:__imp_GetCurrentThreadId
0x18005e502  lea     r9, _CompareTids
0x18005e509  mov     [rsp+68h+var_1C], 0
0x18005e512  mov     [rsp+68h+var_20], eax
0x18005e516  lea     rdx, [rsp+68h+var_20]
0x18005e51b  lea     rax, [rsp+68h+i]
0x18005e520  mov     [rsp+68h+i], 0
0x18005e528  mov     [rsp+68h+var_38], rax
0x18005e52d  call    ?Search@?$CDSA_Base@UTHREAD_GIT_MAPPING@@@@QEBAJPEBUTHREAD_GIT_MAPPING@@HP6AH00_J@Z1IPEAH@Z; CDSA_Base<THREAD_GIT_MAPPING>::Search(THREAD_GIT_MAPPING const *,int,int (*)(THREAD_GIT_MAPPING const *,THREAD_GIT_MAPPING const *,__int64),__int64,uint,int *)
0x18005e532  mov     ebx, eax
0x18005e534  test    eax, eax
0x18005e536  js      short loc_18005E550
0x18005e538  mov     rcx, cs:?g_pcdsaThreadData@@3PEAV?$CDSA@UTHREAD_GIT_MAPPING@@@@EA; CDSA<THREAD_GIT_MAPPING> * g_pcdsaThreadData
0x18005e53f  mov     edx, [rsp+68h+i]; i
0x18005e543  mov     rcx, [rcx]; hdsa
0x18005e546  call    DSA_GetItemPtr
0x18005e54b  mov     [rax+4], edi
0x18005e54e  jmp     short loc_18005E559
0x18005e550  mov     ecx, edi; unsigned int
0x18005e552  call    ?SetUserBroker@@YAJK@Z; SetUserBroker(ulong)
0x18005e557  mov     ebx, eax
0x18005e559  lea     rcx, ?g_csInit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005e560  call    cs:__imp_LeaveCriticalSection
0x18005e566  mov     eax, ebx
0x18005e568  mov     rcx, [rsp+68h+var_10]
0x18005e56d  xor     rcx, rsp; StackCookie
0x18005e570  call    __security_check_cookie
0x18005e575  mov     rbx, [rsp+68h+arg_8]
0x18005e57a  add     rsp, 60h
0x18005e57e  pop     rdi
0x18005e57f  retn
```
