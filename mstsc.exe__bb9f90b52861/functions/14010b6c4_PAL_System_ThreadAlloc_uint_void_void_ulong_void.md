# PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)

- ea: `0x14010b6c4`
- end: `0x14010b8d4`
- name: `?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z`
- size: `528`
- prototype: `__int64 __fastcall(unsigned int (*)(void *), void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14010b8dc`

## callees

- `0x1400019e8`
- `0x140001b00`
- `0x1400b3ef0`
- `0x14010b6c4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14010b82a`
- `KERNEL32!LocalFree` at `0x14010b82a`
- `KERNEL32!CreateThread` at `0x14010b7fd`
- `KERNEL32!CreateThread` at `0x14010b7fd`
- `KERNEL32!FreeLibrary` at `0x14010b814`
- `KERNEL32!FreeLibrary` at `0x14010b814`
- `KERNEL32!GetLastError` at `0x14010b75e`
- `KERNEL32!GetLastError` at `0x14010b75e`
- `KERNEL32!GetModuleHandleExW` at `0x14010b73c`
- `KERNEL32!GetModuleHandleExW` at `0x14010b73c`

## string_xrefs

- `0x14010b780`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x14010b865`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x14010b775`: `PAL_System_ThreadAlloc`
- `0x14010b84c`: `PAL_System_ThreadAlloc`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadAlloc(unsigned int (*a1)(void *), void *a2, unsigned int *a3, void **a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ebx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
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
    v7 = MIDL_user_allocate(0x18u);
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
        if ( (unsigned int)dword_140152118 > 2 )
        {
          v16 = 1295;
          LastError = GetLastError();
          v19 = "PAL_System_ThreadAlloc";
          v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
          v21 = "Failed GetModuleHandleEx.  GetLastError: 0x%x";
          v17 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)word_140146252,
            v11,
            v12,
            (__int64)&v21,
            (__int64)&v17,
            (__int64)&v20,
            (__int64)&v16,
            (__int64)&v19,
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
    if ( (unsigned int)dword_140152118 > 2 )
    {
      v17 = 1268;
      v21 = "PAL_System_ThreadAlloc";
      v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v19 = "NULL parameter passed";
      v16 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)byte_14014658B,
        0,
        (_DWORD)a4,
        (__int64)&v19,
        (__int64)&v16,
        (__int64)&v20,
        (__int64)&v17,
        (__int64)&v21);
    }
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x14010b6c4  mov     [rsp-18h+arg_8], rbx
0x14010b6c9  mov     [rsp-18h+arg_10], rsi
0x14010b6ce  mov     qword ptr [rsp-18h+ThreadId], rcx
0x14010b6d3  push    rbp
0x14010b6d4  push    rdi
0x14010b6d5  push    r14
0x14010b6d7  mov     rbp, rsp
0x14010b6da  sub     rsp, 80h
0x14010b6e1  mov     [rbp+ThreadId], 0
0x14010b6e8  mov     rsi, r9
0x14010b6eb  mov     [rbp+phModule], 0
0x14010b6f3  mov     rbx, r8
0x14010b6f6  mov     r14, rdx
0x14010b6f9  test    r8, r8
0x14010b6fc  jz      loc_14010B841
0x14010b702  mov     ecx, 18h; size
0x14010b707  call    MIDL_user_allocate
0x14010b70c  mov     rdi, rax
0x14010b70f  test    rax, rax
0x14010b712  jnz     short loc_14010B71E
0x14010b714  mov     ebx, 8007000Eh
0x14010b719  jmp     loc_14010B8BA
0x14010b71e  mov     [rax+8], r14
0x14010b722  lea     r8, [rbp+phModule]; phModule
0x14010b726  lea     rax, ?TSStaticThreadEntry@CTSThread@@CAIPEAX@Z; CTSThread::TSStaticThreadEntry(void *)
0x14010b72d  mov     ecx, 4; dwFlags
0x14010b732  lea     rdx, ?g_TsSystemPalDllModule@@3HA; lpModuleName
0x14010b739  mov     [rdi], rax
0x14010b73c  call    cs:__imp_GetModuleHandleExW
0x14010b742  test    eax, eax
0x14010b744  jnz     loc_14010B7D6
0x14010b74a  mov     eax, cs:dword_140152118
0x14010b750  mov     ebx, 80004005h
0x14010b755  cmp     eax, 2
0x14010b758  jbe     loc_14010B827
0x14010b75e  call    cs:__imp_GetLastError
0x14010b764  lea     rdx, word_140146252
0x14010b76b  mov     [rbp+var_2C], 50Fh
0x14010b772  mov     [rbp+var_30], eax
0x14010b775  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x14010b77c  mov     [rbp+var_18], rax
0x14010b780  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14010b787  mov     [rbp+var_10], rax
0x14010b78b  lea     rax, aFailedGetmodul; "Failed GetModuleHandleEx.  GetLastError"...
0x14010b792  mov     [rbp+var_8], rax
0x14010b796  lea     rax, [rbp+var_30]
0x14010b79a  mov     [rsp+80h+var_38], rax
0x14010b79f  lea     rax, [rbp+var_18]
0x14010b7a3  mov     [rsp+80h+var_40], rax
0x14010b7a8  lea     rax, [rbp+var_2C]
0x14010b7ac  mov     [rsp+80h+var_48], rax
0x14010b7b1  lea     rax, [rbp+var_10]
0x14010b7b5  mov     [rsp+80h+var_50], rax
0x14010b7ba  lea     rax, [rbp+var_28]
0x14010b7be  mov     [rsp+80h+lpThreadId], rax
0x14010b7c3  lea     rax, [rbp+var_8]
0x14010b7c7  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x14010b7cc  mov     [rbp+var_28], ebx
0x14010b7cf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14010b7d4  jmp     short loc_14010B827
0x14010b7d6  mov     rax, [rbp+phModule]
0x14010b7da  lea     r8, ?PAL_System_Win32_ThreadProcWrapper@@YAKPEAX@Z; lpStartAddress
0x14010b7e1  mov     [rdi+10h], rax
0x14010b7e5  mov     r9, rdi; lpParameter
0x14010b7e8  lea     rax, [rbp+ThreadId]
0x14010b7ec  xor     edx, edx; dwStackSize
0x14010b7ee  mov     [rsp+80h+lpThreadId], rax; lpThreadId
0x14010b7f3  xor     ecx, ecx; lpThreadAttributes
0x14010b7f5  mov     [rsp+80h+dwCreationFlags], 0; dwCreationFlags
0x14010b7fd  call    cs:__imp_CreateThread
0x14010b803  mov     rcx, rax
0x14010b806  test    rax, rax
0x14010b809  jnz     short loc_14010B835
0x14010b80b  mov     rcx, [rbp+phModule]; hLibModule
0x14010b80f  test    rcx, rcx
0x14010b812  jz      short loc_14010B822
0x14010b814  call    cs:__imp_FreeLibrary
0x14010b81a  mov     [rbp+phModule], 0
0x14010b822  mov     ebx, 80004005h
0x14010b827  mov     rcx, rdi; hMem
0x14010b82a  call    cs:__imp_LocalFree
0x14010b830  jmp     loc_14010B8BA
0x14010b835  mov     eax, [rbp+ThreadId]
0x14010b838  mov     [rbx], eax
0x14010b83a  xor     ebx, ebx
0x14010b83c  mov     [rsi], rcx
0x14010b83f  jmp     short loc_14010B8BA
0x14010b841  mov     eax, cs:dword_140152118
0x14010b847  cmp     eax, 2
0x14010b84a  jbe     short loc_14010B8B5
0x14010b84c  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x14010b853  mov     [rbp+var_28], 4F4h
0x14010b85a  mov     [rbp+var_8], rax
0x14010b85e  lea     rdx, byte_14014658B
0x14010b865  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14010b86c  mov     ebx, 80004005h
0x14010b871  mov     [rbp+var_10], rax
0x14010b875  lea     rax, aNullParameterP; "NULL parameter passed"
0x14010b87c  mov     [rbp+var_18], rax
0x14010b880  lea     rax, [rbp+var_8]
0x14010b884  mov     [rsp+80h+var_40], rax
0x14010b889  lea     rax, [rbp+var_28]
0x14010b88d  mov     [rsp+80h+var_48], rax
0x14010b892  lea     rax, [rbp+var_10]
0x14010b896  mov     [rsp+80h+var_50], rax
0x14010b89b  lea     rax, [rbp+var_2C]
0x14010b89f  mov     [rsp+80h+lpThreadId], rax
0x14010b8a4  lea     rax, [rbp+var_18]
0x14010b8a8  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x14010b8ad  mov     [rbp+var_2C], ebx
0x14010b8b0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14010b8b5  mov     ebx, 80070057h
0x14010b8ba  lea     r11, [rsp+80h+var_s0]
0x14010b8c2  mov     eax, ebx
0x14010b8c4  mov     rbx, [r11+28h]
0x14010b8c8  mov     rsi, [r11+30h]
0x14010b8cc  mov     rsp, r11
0x14010b8cf  pop     r14
0x14010b8d1  pop     rdi
0x14010b8d2  pop     rbp
0x14010b8d3  retn
```
