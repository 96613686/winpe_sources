# PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)

- ea: `0x140017b80`
- end: `0x140017d90`
- name: `?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z`
- size: `528`
- prototype: `__int64 __fastcall(unsigned int (*)(void *), void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017d98`

## callees

- `0x1400014d4`
- `0x1400015ec`
- `0x140017b80`
- `0x1400186e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140017bf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140017bf8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140017cd0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140017cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017c1a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140017cb9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140017cb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017ce6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017ce6`

## string_xrefs

- `0x140017c3c`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x140017d21`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x140017c31`: `PAL_System_ThreadAlloc`
- `0x140017d08`: `PAL_System_ThreadAlloc`

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
        if ( (unsigned int)dword_1400880C8 > 2 )
        {
          v16 = 1295;
          LastError = GetLastError();
          v19 = "PAL_System_ThreadAlloc";
          v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
          v21 = "Failed GetModuleHandleEx.  GetLastError: 0x%x";
          v17 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)byte_14007DAB1,
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
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v17 = 1268;
      v21 = "PAL_System_ThreadAlloc";
      v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v19 = "NULL parameter passed";
      v16 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)&dword_14007DE84,
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
0x140017b80  mov     [rsp-18h+arg_8], rbx
0x140017b85  mov     [rsp-18h+arg_10], rsi
0x140017b8a  mov     qword ptr [rsp-18h+ThreadId], rcx
0x140017b8f  push    rbp
0x140017b90  push    rdi
0x140017b91  push    r14
0x140017b93  mov     rbp, rsp
0x140017b96  sub     rsp, 80h
0x140017b9d  mov     [rbp+ThreadId], 0
0x140017ba4  mov     rsi, r9
0x140017ba7  mov     [rbp+phModule], 0
0x140017baf  mov     rbx, r8
0x140017bb2  mov     r14, rdx
0x140017bb5  test    r8, r8
0x140017bb8  jz      loc_140017CFD
0x140017bbe  mov     ecx, 18h
0x140017bc3  call    PAL_System_MemAlloc
0x140017bc8  mov     rdi, rax
0x140017bcb  test    rax, rax
0x140017bce  jnz     short loc_140017BDA
0x140017bd0  mov     ebx, 8007000Eh
0x140017bd5  jmp     loc_140017D76
0x140017bda  mov     [rax+8], r14
0x140017bde  lea     r8, [rbp+phModule]; phModule
0x140017be2  lea     rax, ?TSStaticThreadEntry@CTSThread@@CAIPEAX@Z; CTSThread::TSStaticThreadEntry(void *)
0x140017be9  mov     ecx, 4; dwFlags
0x140017bee  lea     rdx, ?g_TsSystemPalDllModule@@3HA; lpModuleName
0x140017bf5  mov     [rdi], rax
0x140017bf8  call    cs:__imp_GetModuleHandleExW
0x140017bfe  test    eax, eax
0x140017c00  jnz     loc_140017C92
0x140017c06  mov     eax, cs:dword_1400880C8
0x140017c0c  mov     ebx, 80004005h
0x140017c11  cmp     eax, 2
0x140017c14  jbe     loc_140017CE3
0x140017c1a  call    cs:__imp_GetLastError
0x140017c20  lea     rdx, byte_14007DAB1
0x140017c27  mov     [rbp+var_2C], 50Fh
0x140017c2e  mov     [rbp+var_30], eax
0x140017c31  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x140017c38  mov     [rbp+var_18], rax
0x140017c3c  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140017c43  mov     [rbp+var_10], rax
0x140017c47  lea     rax, aFailedGetmodul; "Failed GetModuleHandleEx.  GetLastError"...
0x140017c4e  mov     [rbp+var_8], rax
0x140017c52  lea     rax, [rbp+var_30]
0x140017c56  mov     [rsp+80h+var_38], rax
0x140017c5b  lea     rax, [rbp+var_18]
0x140017c5f  mov     [rsp+80h+var_40], rax
0x140017c64  lea     rax, [rbp+var_2C]
0x140017c68  mov     [rsp+80h+var_48], rax
0x140017c6d  lea     rax, [rbp+var_10]
0x140017c71  mov     [rsp+80h+var_50], rax
0x140017c76  lea     rax, [rbp+var_28]
0x140017c7a  mov     [rsp+80h+lpThreadId], rax
0x140017c7f  lea     rax, [rbp+var_8]
0x140017c83  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x140017c88  mov     [rbp+var_28], ebx
0x140017c8b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140017c90  jmp     short loc_140017CE3
0x140017c92  mov     rax, [rbp+phModule]
0x140017c96  lea     r8, ?PAL_System_Win32_ThreadProcWrapper@@YAKPEAX@Z; lpStartAddress
0x140017c9d  mov     [rdi+10h], rax
0x140017ca1  mov     r9, rdi; lpParameter
0x140017ca4  lea     rax, [rbp+ThreadId]
0x140017ca8  xor     edx, edx; dwStackSize
0x140017caa  mov     [rsp+80h+lpThreadId], rax; lpThreadId
0x140017caf  xor     ecx, ecx; lpThreadAttributes
0x140017cb1  mov     [rsp+80h+dwCreationFlags], 0; dwCreationFlags
0x140017cb9  call    cs:__imp_CreateThread
0x140017cbf  mov     rcx, rax
0x140017cc2  test    rax, rax
0x140017cc5  jnz     short loc_140017CF1
0x140017cc7  mov     rcx, [rbp+phModule]; hLibModule
0x140017ccb  test    rcx, rcx
0x140017cce  jz      short loc_140017CDE
0x140017cd0  call    cs:__imp_FreeLibrary
0x140017cd6  mov     [rbp+phModule], 0
0x140017cde  mov     ebx, 80004005h
0x140017ce3  mov     rcx, rdi; hMem
0x140017ce6  call    cs:__imp_LocalFree
0x140017cec  jmp     loc_140017D76
0x140017cf1  mov     eax, [rbp+ThreadId]
0x140017cf4  mov     [rbx], eax
0x140017cf6  xor     ebx, ebx
0x140017cf8  mov     [rsi], rcx
0x140017cfb  jmp     short loc_140017D76
0x140017cfd  mov     eax, cs:dword_1400880C8
0x140017d03  cmp     eax, 2
0x140017d06  jbe     short loc_140017D71
0x140017d08  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x140017d0f  mov     [rbp+var_28], 4F4h
0x140017d16  mov     [rbp+var_8], rax
0x140017d1a  lea     rdx, dword_14007DE84
0x140017d21  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140017d28  mov     ebx, 80004005h
0x140017d2d  mov     [rbp+var_10], rax
0x140017d31  lea     rax, aNullParameterP; "NULL parameter passed"
0x140017d38  mov     [rbp+var_18], rax
0x140017d3c  lea     rax, [rbp+var_8]
0x140017d40  mov     [rsp+80h+var_40], rax
0x140017d45  lea     rax, [rbp+var_28]
0x140017d49  mov     [rsp+80h+var_48], rax
0x140017d4e  lea     rax, [rbp+var_10]
0x140017d52  mov     [rsp+80h+var_50], rax
0x140017d57  lea     rax, [rbp+var_2C]
0x140017d5b  mov     [rsp+80h+lpThreadId], rax
0x140017d60  lea     rax, [rbp+var_18]
0x140017d64  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x140017d69  mov     [rbp+var_2C], ebx
0x140017d6c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140017d71  mov     ebx, 80070057h
0x140017d76  lea     r11, [rsp+80h+var_s0]
0x140017d7e  mov     eax, ebx
0x140017d80  mov     rbx, [r11+28h]
0x140017d84  mov     rsi, [r11+30h]
0x140017d88  mov     rsp, r11
0x140017d8b  pop     r14
0x140017d8d  pop     rdi
0x140017d8e  pop     rbp
0x140017d8f  retn
```
