# CAsyncProgressRouter::Initialize(void)

- ea: `0x1800656f0`
- end: `0x18006583a`
- name: `?Initialize@CAsyncProgressRouter@@UEAAJXZ`
- size: `330`
- prototype: `__int64 __fastcall(CAsyncProgressRouter *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000d640`
- `0x18001b150`
- `0x18002f078`
- `0x18002f10c`
- `0x1800656f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800657ca`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800657ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180065805`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180065805`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180065706`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180065706`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065732`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006575c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065732`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006575c`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180065787`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180065787`

## string_xrefs

- `0x1800657b3`: `%systemroot%\system32\cscsvc.dll`

## pseudocode

```c
__int64 __fastcall CAsyncProgressRouter::Initialize(struct _RTL_CRITICAL_SECTION *this)
{
  int Error; // ebx
  HANDLE EventW; // rax
  HANDLE v4; // rax
  HANDLE SemaphoreW; // rax
  HMODULE LibraryW; // rax
  void *v7; // rdx
  struct _RTL_CRITICAL_SECTION_DEBUG *Thread; // rax
  LPCWSTR lpLibFileName; // [rsp+40h] [rbp+8h] BYREF

  if ( InitializeCriticalSectionAndSpinCount(this + 20, 0) )
  {
    LODWORD(this[21].DebugInfo) = 1;
    EventW = CreateEventW(0, 1, 0, 0);
    this->SpinCount = (ULONG_PTR)EventW;
    if ( EventW || (Error = ResultFromLastError(), Error >= 0) )
    {
      v4 = CreateEventW(0, 1, 0, 0);
      this[1].LockSemaphore = v4;
      if ( v4 || (Error = ResultFromLastError(), Error >= 0) )
      {
        SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
        this[1].OwningThread = SemaphoreW;
        if ( SemaphoreW || (Error = ResultFromLastError(), Error >= 0) )
        {
          lpLibFileName = 0;
          Error = CscUtil_ExpandEnvironmentStringsAlloc(
                    L"%systemroot%\\system32\\cscsvc.dll",
                    (unsigned __int16 **)&lpLibFileName);
          if ( Error >= 0 )
          {
            LibraryW = LoadLibraryW(lpLibFileName);
            this[1].SpinCount = (ULONG_PTR)LibraryW;
            if ( LibraryW )
            {
              _InterlockedIncrement(&this->LockCount);
              Thread = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateThread(
                                                               0,
                                                               0,
                                                               CAsyncProgressRouter::_ThreadProc,
                                                               this,
                                                               0,
                                                               (LPDWORD)&this[1].LockCount);
              this[1].DebugInfo = Thread;
              if ( !Thread )
              {
                Error = ResultFromLastError();
                CRefCounted::ReleaseReference((CRefCounted *)this);
              }
            }
            else
            {
              Error = ResultFromLastError();
            }
            CscUtil_HeapFree((void *)lpLibFileName, v7);
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)ResultFromLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800656f0  mov     [rsp+arg_8], rbx
0x1800656f5  push    rdi
0x1800656f6  sub     rsp, 30h
0x1800656fa  mov     rdi, rcx
0x1800656fd  xor     edx, edx; dwSpinCount
0x1800656ff  add     rcx, 320h; lpCriticalSection
0x180065706  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18006570c  test    eax, eax
0x18006570e  jnz     short loc_18006571C
0x180065710  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180065715  mov     ebx, eax
0x180065717  jmp     loc_18006582D
0x18006571c  xor     r9d, r9d; lpName
0x18006571f  mov     dword ptr [rdi+348h], 1
0x180065729  xor     r8d, r8d; bInitialState
0x18006572c  xor     ecx, ecx; lpEventAttributes
0x18006572e  lea     edx, [r9+1]; bManualReset
0x180065732  call    cs:__imp_CreateEventW
0x180065738  mov     [rdi+20h], rax
0x18006573c  test    rax, rax
0x18006573f  jnz     short loc_180065750
0x180065741  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180065746  mov     ebx, eax
0x180065748  test    eax, eax
0x18006574a  js      loc_18006582D
0x180065750  xor     r9d, r9d; lpName
0x180065753  xor     r8d, r8d; bInitialState
0x180065756  xor     ecx, ecx; lpEventAttributes
0x180065758  lea     edx, [r9+1]; bManualReset
0x18006575c  call    cs:__imp_CreateEventW
0x180065762  mov     [rdi+40h], rax
0x180065766  test    rax, rax
0x180065769  jnz     short loc_18006577A
0x18006576b  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180065770  mov     ebx, eax
0x180065772  test    eax, eax
0x180065774  js      loc_18006582D
0x18006577a  xor     r9d, r9d; lpName
0x18006577d  xor     edx, edx; lInitialCount
0x18006577f  xor     ecx, ecx; lpSemaphoreAttributes
0x180065781  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180065787  call    cs:__imp_CreateSemaphoreW
0x18006578d  mov     [rdi+38h], rax
0x180065791  test    rax, rax
0x180065794  jnz     short loc_1800657A5
0x180065796  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18006579b  mov     ebx, eax
0x18006579d  test    eax, eax
0x18006579f  js      loc_18006582D
0x1800657a5  lea     rdx, [rsp+38h+lpLibFileName]; unsigned __int16 **
0x1800657aa  mov     [rsp+38h+lpLibFileName], 0
0x1800657b3  lea     rcx, aSystemrootSyst; "%systemroot%\\system32\\cscsvc.dll"
0x1800657ba  call    ?CscUtil_ExpandEnvironmentStringsAlloc@@YAJPEBGPEAPEAG@Z; CscUtil_ExpandEnvironmentStringsAlloc(ushort const *,ushort * *)
0x1800657bf  mov     ebx, eax
0x1800657c1  test    eax, eax
0x1800657c3  js      short loc_18006582D
0x1800657c5  mov     rcx, [rsp+38h+lpLibFileName]; lpLibFileName
0x1800657ca  call    cs:__imp_LoadLibraryW
0x1800657d0  mov     [rdi+48h], rax
0x1800657d4  test    rax, rax
0x1800657d7  jnz     short loc_1800657E2
0x1800657d9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800657de  mov     ebx, eax
0x1800657e0  jmp     short loc_180065823
0x1800657e2  lock inc dword ptr [rdi+8]
0x1800657e6  lea     rax, [rdi+30h]
0x1800657ea  mov     r9, rdi; lpParameter
0x1800657ed  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800657f2  lea     r8, ?_ThreadProc@CAsyncProgressRouter@@CAKPEAX@Z; lpStartAddress
0x1800657f9  xor     edx, edx; dwStackSize
0x1800657fb  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180065803  xor     ecx, ecx; lpThreadAttributes
0x180065805  call    cs:__imp_CreateThread
0x18006580b  mov     [rdi+28h], rax
0x18006580f  test    rax, rax
0x180065812  jnz     short loc_180065823
0x180065814  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180065819  mov     rcx, rdi; this
0x18006581c  mov     ebx, eax
0x18006581e  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x180065823  mov     rcx, [rsp+38h+lpLibFileName]; lpMem
0x180065828  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18006582d  mov     eax, ebx
0x18006582f  mov     rbx, [rsp+38h+arg_8]
0x180065834  add     rsp, 30h
0x180065838  pop     rdi
0x180065839  retn
```
