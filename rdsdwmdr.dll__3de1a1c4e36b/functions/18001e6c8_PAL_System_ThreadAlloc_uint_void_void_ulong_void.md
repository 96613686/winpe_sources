# PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)

- ea: `0x18001e6c8`
- end: `0x18001e8d8`
- name: `?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z`
- size: `528`
- prototype: `__int64 __fastcall(unsigned int (*)(void *), void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e8e0`

## callees

- `0x18000160c`
- `0x180001f98`
- `0x18001e6c8`
- `0x18001f2b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e801`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e801`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001e740`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001e740`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e818`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e762`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e82e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e82e`

## string_xrefs

- `0x18001e784`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001e869`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001e779`: `PAL_System_ThreadAlloc`
- `0x18001e850`: `PAL_System_ThreadAlloc`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadAlloc(unsigned int (*a1)(void *), void *a2, unsigned int *a3, void **a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  HANDLE v13; // rcx
  DWORD LastError; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+54h] [rbp-2Ch] BYREF
  int v17; // [rsp+58h] [rbp-28h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-20h] BYREF
  const char *v19; // [rsp+68h] [rbp-18h] BYREF
  const char *v20; // [rsp+70h] [rbp-10h] BYREF
  const char *v21; // [rsp+78h] [rbp-8h] BYREF
  DWORD ThreadId; // [rsp+A0h] [rbp+20h] BYREF
  int v23; // [rsp+A4h] [rbp+24h]

  v23 = HIDWORD(a1);
  ThreadId = 0;
  phModule = 0;
  if ( a3 )
  {
    v7 = (_QWORD *)PAL_System_MemAlloc(24);
    v8 = v7;
    if ( v7 )
    {
      v7[1] = a2;
      *v7 = CTSThread::TSStaticThreadEntry;
      if ( GetModuleHandleExW(4u, &g_TsSystemPalDllModule, &phModule) )
      {
        v8[2] = phModule;
        v13 = CreateThread(0, 0, PAL_System_Win32_ThreadProcWrapper, v8, 0, &ThreadId);
        if ( v13 )
        {
          *a3 = ThreadId;
          v9 = 0;
          *a4 = v13;
          return v9;
        }
        if ( phModule )
        {
          FreeLibrary(phModule);
          phModule = 0;
        }
        v9 = -2147467259;
      }
      else
      {
        v9 = -2147467259;
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v16 = 1295;
          LastError = GetLastError();
          v19 = "PAL_System_ThreadAlloc";
          v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
          v21 = "Failed GetModuleHandleEx.  GetLastError: 0x%x";
          v17 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v10,
            (__int64)byte_18003EC93,
            v11,
            v12,
            (const unsigned __int16 **)&v21,
            (__int64)&v17,
            (const unsigned __int16 **)&v20,
            (__int64)&v16,
            (const unsigned __int16 **)&v19,
            (__int64)&LastError);
        }
      }
      LocalFree(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v17 = 1268;
      v21 = "PAL_System_ThreadAlloc";
      v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v19 = "NULL parameter passed";
      v16 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)a1,
        (__int64)&word_18003F066,
        0,
        (__int64)a4,
        (const unsigned __int16 **)&v19,
        (__int64)&v16,
        (const unsigned __int16 **)&v20,
        (__int64)&v17,
        (const unsigned __int16 **)&v21);
    }
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x18001e6c8  mov     [rsp-18h+arg_8], rbx
0x18001e6cd  mov     [rsp-18h+arg_10], rsi
0x18001e6d2  mov     qword ptr [rsp-18h+ThreadId], rcx
0x18001e6d7  push    rbp
0x18001e6d8  push    rdi
0x18001e6d9  push    r14
0x18001e6db  mov     rbp, rsp
0x18001e6de  sub     rsp, 80h
0x18001e6e5  mov     [rbp+ThreadId], 0
0x18001e6ec  mov     rsi, r9
0x18001e6ef  mov     [rbp+phModule], 0
0x18001e6f7  mov     rbx, r8
0x18001e6fa  mov     r14, rdx
0x18001e6fd  test    r8, r8
0x18001e700  jz      loc_18001E845
0x18001e706  mov     ecx, 18h
0x18001e70b  call    PAL_System_MemAlloc
0x18001e710  mov     rdi, rax
0x18001e713  test    rax, rax
0x18001e716  jnz     short loc_18001E722
0x18001e718  mov     ebx, 8007000Eh
0x18001e71d  jmp     loc_18001E8BE
0x18001e722  mov     [rax+8], r14
0x18001e726  lea     r8, [rbp+phModule]; phModule
0x18001e72a  lea     rax, ?TSStaticThreadEntry@CTSThread@@CAIPEAX@Z; CTSThread::TSStaticThreadEntry(void *)
0x18001e731  mov     ecx, 4; dwFlags
0x18001e736  lea     rdx, ?g_TsSystemPalDllModule@@3HA; lpModuleName
0x18001e73d  mov     [rdi], rax
0x18001e740  call    cs:__imp_GetModuleHandleExW
0x18001e746  test    eax, eax
0x18001e748  jnz     loc_18001E7DA
0x18001e74e  mov     eax, cs:dword_180044008
0x18001e754  mov     ebx, 80004005h
0x18001e759  cmp     eax, 2
0x18001e75c  jbe     loc_18001E82B
0x18001e762  call    cs:__imp_GetLastError
0x18001e768  lea     rdx, byte_18003EC93
0x18001e76f  mov     [rbp+var_2C], 50Fh
0x18001e776  mov     [rbp+var_30], eax
0x18001e779  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x18001e780  mov     [rbp+var_18], rax
0x18001e784  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001e78b  mov     [rbp+var_10], rax
0x18001e78f  lea     rax, aFailedGetmodul; "Failed GetModuleHandleEx.  GetLastError"...
0x18001e796  mov     [rbp+var_8], rax
0x18001e79a  lea     rax, [rbp+var_30]
0x18001e79e  mov     [rsp+80h+var_38], rax
0x18001e7a3  lea     rax, [rbp+var_18]
0x18001e7a7  mov     [rsp+80h+var_40], rax
0x18001e7ac  lea     rax, [rbp+var_2C]
0x18001e7b0  mov     [rsp+80h+var_48], rax
0x18001e7b5  lea     rax, [rbp+var_10]
0x18001e7b9  mov     [rsp+80h+var_50], rax
0x18001e7be  lea     rax, [rbp+var_28]
0x18001e7c2  mov     [rsp+80h+lpThreadId], rax
0x18001e7c7  lea     rax, [rbp+var_8]
0x18001e7cb  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x18001e7d0  mov     [rbp+var_28], ebx
0x18001e7d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001e7d8  jmp     short loc_18001E82B
0x18001e7da  mov     rax, [rbp+phModule]
0x18001e7de  lea     r8, ?PAL_System_Win32_ThreadProcWrapper@@YAKPEAX@Z; lpStartAddress
0x18001e7e5  mov     [rdi+10h], rax
0x18001e7e9  mov     r9, rdi; lpParameter
0x18001e7ec  lea     rax, [rbp+ThreadId]
0x18001e7f0  xor     edx, edx; dwStackSize
0x18001e7f2  mov     [rsp+80h+lpThreadId], rax; lpThreadId
0x18001e7f7  xor     ecx, ecx; lpThreadAttributes
0x18001e7f9  mov     [rsp+80h+dwCreationFlags], 0; dwCreationFlags
0x18001e801  call    cs:__imp_CreateThread
0x18001e807  mov     rcx, rax
0x18001e80a  test    rax, rax
0x18001e80d  jnz     short loc_18001E839
0x18001e80f  mov     rcx, [rbp+phModule]; hLibModule
0x18001e813  test    rcx, rcx
0x18001e816  jz      short loc_18001E826
0x18001e818  call    cs:__imp_FreeLibrary
0x18001e81e  mov     [rbp+phModule], 0
0x18001e826  mov     ebx, 80004005h
0x18001e82b  mov     rcx, rdi; hMem
0x18001e82e  call    cs:__imp_LocalFree
0x18001e834  jmp     loc_18001E8BE
0x18001e839  mov     eax, [rbp+ThreadId]
0x18001e83c  mov     [rbx], eax
0x18001e83e  xor     ebx, ebx
0x18001e840  mov     [rsi], rcx
0x18001e843  jmp     short loc_18001E8BE
0x18001e845  mov     eax, cs:dword_180044008
0x18001e84b  cmp     eax, 2
0x18001e84e  jbe     short loc_18001E8B9
0x18001e850  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x18001e857  mov     [rbp+var_28], 4F4h
0x18001e85e  mov     [rbp+var_8], rax
0x18001e862  lea     rdx, word_18003F066
0x18001e869  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001e870  mov     ebx, 80004005h
0x18001e875  mov     [rbp+var_10], rax
0x18001e879  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001e880  mov     [rbp+var_18], rax
0x18001e884  lea     rax, [rbp+var_8]
0x18001e888  mov     [rsp+80h+var_40], rax
0x18001e88d  lea     rax, [rbp+var_28]
0x18001e891  mov     [rsp+80h+var_48], rax
0x18001e896  lea     rax, [rbp+var_10]
0x18001e89a  mov     [rsp+80h+var_50], rax
0x18001e89f  lea     rax, [rbp+var_2C]
0x18001e8a3  mov     [rsp+80h+lpThreadId], rax
0x18001e8a8  lea     rax, [rbp+var_18]
0x18001e8ac  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x18001e8b1  mov     [rbp+var_2C], ebx
0x18001e8b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001e8b9  mov     ebx, 80070057h
0x18001e8be  lea     r11, [rsp+80h+var_s0]
0x18001e8c6  mov     eax, ebx
0x18001e8c8  mov     rbx, [r11+28h]
0x18001e8cc  mov     rsi, [r11+30h]
0x18001e8d0  mov     rsp, r11
0x18001e8d3  pop     r14
0x18001e8d5  pop     rdi
0x18001e8d6  pop     rbp
0x18001e8d7  retn
```
