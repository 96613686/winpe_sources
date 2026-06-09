# HTTP_FILTER_DLL::OpenFilter(ushort const *,int,HTTP_FILTER_DLL * *,FILTER_FAILURE_POINT *)

- ea: `0x180006f50`
- end: `0x18000714f`
- name: `?OpenFilter@HTTP_FILTER_DLL@@SAJPEBGHPEAPEAV1@PEAW4FILTER_FAILURE_POINT@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, struct HTTP_FILTER_DLL **, enum FILTER_FAILURE_POINT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180006e10`

## callees

- `0x1800064e0`
- `0x180006f50`
- `0x180007490`
- `0x1800088bc`
- `0x1800088fc`
- `0x180009258`
- `0x18000a35c`
- `0x18000c970`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006fd0`
- `msvcrt!_wcsicmp` at `0x180006fd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006fa0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006fa0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007108`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007108`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180007072`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180007072`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006fc4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006fc4`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800070c0`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800070c0`

## pseudocode

```c
__int64 __fastcall HTTP_FILTER_DLL::OpenFilter(
        const unsigned __int16 *a1,
        int a2,
        struct HTTP_FILTER_DLL **a3,
        enum FILTER_FAILURE_POINT *a4)
{
  struct _LIST_ENTRY *i; // r15
  HTTP_FILTER_DLL *p_Blink; // r14
  const wchar_t *Str; // rax
  signed int Dll; // r15d
  HTTP_FILTER_DLL *v12; // rax
  HTTP_FILTER_DLL *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // edx
  unsigned __int16 v16; // r8
  __int64 result; // rax
  const unsigned __int16 *v18; // [rsp+30h] [rbp-98h] BYREF
  WCHAR *v19; // [rsp+38h] [rbp-90h]
  WCHAR Buffer[32]; // [rsp+40h] [rbp-88h] BYREF

  if ( a1 && a3 )
  {
    EnterCriticalSection(&HTTP_FILTER_DLL::sm_csFilterDlls);
    for ( i = HTTP_FILTER_DLL::sm_FilterHead.Flink; ; i = i->Flink )
    {
      p_Blink = 0;
      if ( i == &HTTP_FILTER_DLL::sm_FilterHead )
        break;
      p_Blink = (HTTP_FILTER_DLL *)&i[-1].Blink;
      Str = STRU::QueryStr((STRU *)&i[4]);
      if ( !_wcsicmp(a1, Str) )
      {
        Dll = 0;
        _InterlockedIncrement((volatile signed __int32 *)p_Blink + 17);
        if ( p_Blink )
          goto LABEL_24;
        break;
      }
    }
    if ( HTTP_FILTER_DLL::sm_cLoadedFilters == 50 )
    {
      Dll = -2147024846;
    }
    else
    {
      v12 = (HTTP_FILTER_DLL *)operator new(0x88u);
      if ( v12 )
      {
        v13 = HTTP_FILTER_DLL::HTTP_FILTER_DLL(v12, a2);
        p_Blink = v13;
        if ( v13 )
        {
          Dll = HTTP_FILTER_DLL::LoadDll(v13, a1, a4);
          if ( Dll >= 0 )
          {
            if ( !*(_QWORD *)((char *)p_Blink + 60) )
              *((_DWORD *)p_Blink + 33) = 1;
            ++HTTP_FILTER_DLL::sm_cLoadedFilters;
          }
          else
          {
            v18 = a1;
            v19 = L"???";
            if ( Dll == -2147024703 )
            {
              if ( GetEnvironmentVariableW(L"PROCESSOR_ARCHITECTURE", Buffer, 0x20u) )
                v19 = Buffer;
              v14 = WIN32_FROM_HRESULT(-2147024703);
              v15 = -1073739550;
              v16 = 2;
            }
            else
            {
              v14 = WIN32_FROM_HRESULT(Dll);
              v15 = -1073739610;
              v16 = 1;
            }
            EVENT_LOG::LogEvent((EVENT_LOG *)g_pEventLog, v15, v16, &v18, v14);
            HTTP_FILTER_DLL::~HTTP_FILTER_DLL(p_Blink);
            operator delete(p_Blink);
            p_Blink = 0;
          }
          goto LABEL_24;
        }
      }
      else
      {
        p_Blink = 0;
      }
      Dll = -2147024888;
    }
LABEL_24:
    LeaveCriticalSection(&HTTP_FILTER_DLL::sm_csFilterDlls);
    result = (unsigned int)Dll;
    *a3 = p_Blink;
    return result;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180006f50  mov     r11, rsp
0x180006f53  push    rbx
0x180006f54  push    rbp
0x180006f55  push    rsi
0x180006f56  push    rdi
0x180006f57  sub     rsp, 0A8h
0x180006f5e  mov     rax, cs:__security_cookie
0x180006f65  xor     rax, rsp
0x180006f68  mov     [rsp+0C8h+var_48], rax
0x180006f70  mov     rbp, r9
0x180006f73  mov     rdi, r8
0x180006f76  mov     esi, edx
0x180006f78  mov     rbx, rcx
0x180006f7b  test    rcx, rcx
0x180006f7e  jz      loc_18000712E
0x180006f84  test    r8, r8
0x180006f87  jz      loc_18000712E
0x180006f8d  mov     [r11-28h], r12
0x180006f91  lea     rcx, ?sm_csFilterDlls@HTTP_FILTER_DLL@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006f98  mov     [r11-30h], r14
0x180006f9c  mov     [r11-38h], r15
0x180006fa0  call    cs:__imp_EnterCriticalSection
0x180006fa6  mov     r15, cs:?sm_FilterHead@HTTP_FILTER_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_FILTER_DLL::sm_FilterHead
0x180006fad  lea     r12, ?sm_FilterHead@HTTP_FILTER_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_FILTER_DLL::sm_FilterHead
0x180006fb4  xor     r14d, r14d
0x180006fb7  cmp     r15, r12
0x180006fba  jz      short loc_180006FF0
0x180006fbc  lea     r14, [r15-8]
0x180006fc0  lea     rcx, [r14+48h]
0x180006fc4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006fca  mov     rdx, rax; String2
0x180006fcd  mov     rcx, rbx; String1
0x180006fd0  call    cs:__imp__wcsicmp
0x180006fd6  test    eax, eax
0x180006fd8  jz      short loc_180006FDF
0x180006fda  mov     r15, [r15]
0x180006fdd  jmp     short loc_180006FB4
0x180006fdf  xor     r15d, r15d
0x180006fe2  lock inc dword ptr [r14+44h]
0x180006fe7  test    r14, r14
0x180006fea  jnz     loc_180007101
0x180006ff0  cmp     cs:?sm_cLoadedFilters@HTTP_FILTER_DLL@@0KA, 32h ; '2'; ulong HTTP_FILTER_DLL::sm_cLoadedFilters
0x180006ff7  jnz     short loc_180007004
0x180006ff9  mov     r15d, 80070032h
0x180006fff  jmp     loc_180007101
0x180007004  mov     ecx, 88h; Size
0x180007009  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000700e  test    rax, rax
0x180007011  jz      loc_1800070F8
0x180007017  mov     edx, esi; int
0x180007019  mov     rcx, rax; this
0x18000701c  call    ??0HTTP_FILTER_DLL@@QEAA@H@Z; HTTP_FILTER_DLL::HTTP_FILTER_DLL(int)
0x180007021  mov     r14, rax
0x180007024  test    rax, rax
0x180007027  jz      loc_1800070FB
0x18000702d  mov     r8, rbp; enum FILTER_FAILURE_POINT *
0x180007030  mov     rdx, rbx; unsigned __int16 *
0x180007033  mov     rcx, rax; this
0x180007036  call    ?LoadDll@HTTP_FILTER_DLL@@QEAAJPEBGPEAW4FILTER_FAILURE_POINT@@@Z; HTTP_FILTER_DLL::LoadDll(ushort const *,FILTER_FAILURE_POINT *)
0x18000703b  mov     r15d, eax
0x18000703e  test    eax, eax
0x180007040  jns     loc_1800070DB
0x180007046  mov     [rsp+0C8h+var_98], rbx
0x18000704b  lea     rax, asc_18000FA28; "???"
0x180007052  mov     [rsp+0C8h+var_90], rax
0x180007057  cmp     r15d, 800700C1h
0x18000705e  jnz     short loc_18000709D
0x180007060  mov     r8d, 20h ; ' '; nSize
0x180007066  lea     rdx, [rsp+0C8h+Buffer]; lpBuffer
0x18000706b  lea     rcx, Name; "PROCESSOR_ARCHITECTURE"
0x180007072  call    cs:__imp_GetEnvironmentVariableW
0x180007078  test    eax, eax
0x18000707a  jz      short loc_180007086
0x18000707c  lea     rax, [rsp+0C8h+Buffer]
0x180007081  mov     [rsp+0C8h+var_90], rax
0x180007086  mov     ecx, 800700C1h; int
0x18000708b  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180007090  mov     edx, 0C00008E2h
0x180007095  mov     r8d, 2
0x18000709b  jmp     short loc_1800070B0
0x18000709d  mov     ecx, r15d; int
0x1800070a0  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800070a5  mov     edx, 0C00008A6h
0x1800070aa  mov     r8d, 1
0x1800070b0  mov     rcx, cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_pEventLog
0x1800070b7  lea     r9, [rsp+0C8h+var_98]
0x1800070bc  mov     [rsp+0C8h+var_A8], eax
0x1800070c0  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800070c6  mov     rcx, r14; this
0x1800070c9  call    ??1HTTP_FILTER_DLL@@QEAA@XZ; HTTP_FILTER_DLL::~HTTP_FILTER_DLL(void)
0x1800070ce  mov     rcx, r14; Block
0x1800070d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800070d6  xor     r14d, r14d
0x1800070d9  jmp     short loc_180007101
0x1800070db  mov     eax, [r14+40h]
0x1800070df  or      eax, [r14+3Ch]
0x1800070e3  jnz     short loc_1800070F0
0x1800070e5  mov     dword ptr [r14+84h], 1
0x1800070f0  inc     cs:?sm_cLoadedFilters@HTTP_FILTER_DLL@@0KA; ulong HTTP_FILTER_DLL::sm_cLoadedFilters
0x1800070f6  jmp     short loc_180007101
0x1800070f8  xor     r14d, r14d
0x1800070fb  mov     r15d, 80070008h
0x180007101  lea     rcx, ?sm_csFilterDlls@HTTP_FILTER_DLL@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007108  call    cs:__imp_LeaveCriticalSection
0x18000710e  mov     r12, [rsp+0C8h+var_28]
0x180007116  mov     eax, r15d
0x180007119  mov     r15, [rsp+0C8h+var_38]
0x180007121  mov     [rdi], r14
0x180007124  mov     r14, [rsp+0C8h+var_30]
0x18000712c  jmp     short loc_180007133
0x18000712e  mov     eax, 80070057h
0x180007133  mov     rcx, [rsp+0C8h+var_48]
0x18000713b  xor     rcx, rsp; StackCookie
0x18000713e  call    __security_check_cookie
0x180007143  add     rsp, 0A8h
0x18000714a  pop     rdi
0x18000714b  pop     rsi
0x18000714c  pop     rbp
0x18000714d  pop     rbx
0x18000714e  retn
```
