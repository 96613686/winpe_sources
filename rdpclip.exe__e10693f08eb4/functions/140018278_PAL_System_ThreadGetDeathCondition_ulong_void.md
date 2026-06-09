# PAL_System_ThreadGetDeathCondition(ulong,void * *)

- ea: `0x140018278`
- end: `0x14001835d`
- name: `?PAL_System_ThreadGetDeathCondition@@YAJKPEAPEAX@Z`
- size: `229`
- prototype: `__int64 __fastcall(DWORD dwThreadId, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001aac0`

## callees

- `0x140001710`
- `0x140018278`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400182c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400182c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1400182a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1400182a4`

## string_xrefs

- `0x1400182e5`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x1400182da`: `PAL_System_ThreadGetDeathCondition`
- `0x1400182f0`: `Failed to open thread %#x. GetLastError: 0x%x`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadGetDeathCondition(DWORD dwThreadId, void **a2)
{
  unsigned int v4; // ebx
  HANDLE v5; // rax
  DWORD LastError; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v11; // [rsp+60h] [rbp-20h] BYREF
  const char *v12; // [rsp+68h] [rbp-18h] BYREF
  const char *v13; // [rsp+70h] [rbp-10h] BYREF
  const char *v14; // [rsp+78h] [rbp-8h] BYREF
  DWORD v15; // [rsp+A8h] [rbp+28h] BYREF
  DWORD v16; // [rsp+B0h] [rbp+30h] BYREF
  int v17; // [rsp+B8h] [rbp+38h] BYREF

  if ( a2 )
  {
    v5 = OpenThread(0x100000u, 0, dwThreadId);
    if ( v5 )
    {
      *a2 = v5;
      return 0;
    }
    else
    {
      v4 = -2147467259;
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        LastError = GetLastError();
        v16 = dwThreadId;
        v15 = LastError;
        v12 = "PAL_System_ThreadGetDeathCondition";
        v13 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
        v14 = "Failed to open thread %#x. GetLastError: 0x%x";
        v17 = 1522;
        v11 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v7,
          (unsigned int)word_14007DC2A,
          v8,
          v9,
          (__int64)&v14,
          (__int64)&v11,
          (__int64)&v13,
          (__int64)&v17,
          (__int64)&v12,
          (__int64)&v16,
          (__int64)&v15);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x140018278  push    rbp
0x14001827a  push    rbx
0x14001827b  push    rdi
0x14001827c  mov     rbp, rsp
0x14001827f  sub     rsp, 80h
0x140018286  mov     rbx, rdx
0x140018289  mov     edi, ecx
0x14001828b  test    rdx, rdx
0x14001828e  jnz     short loc_14001829A
0x140018290  mov     ebx, 80070057h
0x140018295  jmp     loc_140018350
0x14001829a  mov     r8d, edi; dwThreadId
0x14001829d  xor     edx, edx; bInheritHandle
0x14001829f  mov     ecx, 100000h; dwDesiredAccess
0x1400182a4  call    cs:__imp_OpenThread
0x1400182aa  test    rax, rax
0x1400182ad  jnz     loc_14001834B
0x1400182b3  mov     eax, cs:dword_1400880C8
0x1400182b9  mov     ebx, 80004005h
0x1400182be  cmp     eax, 2
0x1400182c1  jbe     loc_140018350
0x1400182c7  call    cs:__imp_GetLastError
0x1400182cd  lea     rdx, word_14007DC2A
0x1400182d4  mov     [rbp+arg_10], edi
0x1400182d7  mov     [rbp+arg_8], eax
0x1400182da  lea     rax, aPalSystemThrea_5; "PAL_System_ThreadGetDeathCondition"
0x1400182e1  mov     [rbp+var_18], rax
0x1400182e5  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1400182ec  mov     [rbp+var_10], rax
0x1400182f0  lea     rax, aFailedToOpenTh; "Failed to open thread %#x. GetLastError"...
0x1400182f7  mov     [rbp+var_8], rax
0x1400182fb  lea     rax, [rbp+arg_8]
0x1400182ff  mov     [rsp+80h+var_30], rax
0x140018304  lea     rax, [rbp+arg_10]
0x140018308  mov     [rsp+80h+var_38], rax
0x14001830d  lea     rax, [rbp+var_18]
0x140018311  mov     [rsp+80h+var_40], rax
0x140018316  lea     rax, [rbp+arg_18]
0x14001831a  mov     [rsp+80h+var_48], rax
0x14001831f  lea     rax, [rbp+var_10]
0x140018323  mov     [rsp+80h+var_50], rax
0x140018328  lea     rax, [rbp+var_20]
0x14001832c  mov     [rsp+80h+var_58], rax
0x140018331  lea     rax, [rbp+var_8]
0x140018335  mov     [rsp+80h+var_60], rax
0x14001833a  mov     [rbp+arg_18], 5F2h
0x140018341  mov     [rbp+var_20], ebx
0x140018344  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140018349  jmp     short loc_140018350
0x14001834b  mov     [rbx], rax
0x14001834e  xor     ebx, ebx
0x140018350  mov     eax, ebx
0x140018352  add     rsp, 80h
0x140018359  pop     rdi
0x14001835a  pop     rbx
0x14001835b  pop     rbp
0x14001835c  retn
```
