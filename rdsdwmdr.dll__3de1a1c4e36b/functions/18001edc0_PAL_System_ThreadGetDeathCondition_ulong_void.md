# PAL_System_ThreadGetDeathCondition(ulong,void * *)

- ea: `0x18001edc0`
- end: `0x18001eea5`
- name: `?PAL_System_ThreadGetDeathCondition@@YAJKPEAPEAX@Z`
- size: `229`
- prototype: `__int64 __fastcall(DWORD dwThreadId, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800234e0`

## callees

- `0x1800020bc`
- `0x18001edc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18001edec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18001edec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee0f`

## string_xrefs

- `0x18001ee2d`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001ee22`: `PAL_System_ThreadGetDeathCondition`
- `0x18001ee38`: `Failed to open thread %#x. GetLastError: 0x%x`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadGetDeathCondition(DWORD dwThreadId, void **a2)
{
  unsigned int v4; // ebx
  HANDLE v5; // rax
  DWORD LastError; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
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
      if ( (unsigned int)dword_180044008 > 2 )
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
          (__int64)&dword_18003EE0C,
          v8,
          v9,
          (const unsigned __int16 **)&v14,
          (__int64)&v11,
          (const unsigned __int16 **)&v13,
          (__int64)&v17,
          (const unsigned __int16 **)&v12,
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
0x18001edc0  push    rbp
0x18001edc2  push    rbx
0x18001edc3  push    rdi
0x18001edc4  mov     rbp, rsp
0x18001edc7  sub     rsp, 80h
0x18001edce  mov     rbx, rdx
0x18001edd1  mov     edi, ecx
0x18001edd3  test    rdx, rdx
0x18001edd6  jnz     short loc_18001EDE2
0x18001edd8  mov     ebx, 80070057h
0x18001eddd  jmp     loc_18001EE98
0x18001ede2  mov     r8d, edi; dwThreadId
0x18001ede5  xor     edx, edx; bInheritHandle
0x18001ede7  mov     ecx, 100000h; dwDesiredAccess
0x18001edec  call    cs:__imp_OpenThread
0x18001edf2  test    rax, rax
0x18001edf5  jnz     loc_18001EE93
0x18001edfb  mov     eax, cs:dword_180044008
0x18001ee01  mov     ebx, 80004005h
0x18001ee06  cmp     eax, 2
0x18001ee09  jbe     loc_18001EE98
0x18001ee0f  call    cs:__imp_GetLastError
0x18001ee15  lea     rdx, dword_18003EE0C
0x18001ee1c  mov     [rbp+arg_10], edi
0x18001ee1f  mov     [rbp+arg_8], eax
0x18001ee22  lea     rax, aPalSystemThrea_5; "PAL_System_ThreadGetDeathCondition"
0x18001ee29  mov     [rbp+var_18], rax
0x18001ee2d  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ee34  mov     [rbp+var_10], rax
0x18001ee38  lea     rax, aFailedToOpenTh; "Failed to open thread %#x. GetLastError"...
0x18001ee3f  mov     [rbp+var_8], rax
0x18001ee43  lea     rax, [rbp+arg_8]
0x18001ee47  mov     [rsp+80h+var_30], rax
0x18001ee4c  lea     rax, [rbp+arg_10]
0x18001ee50  mov     [rsp+80h+var_38], rax
0x18001ee55  lea     rax, [rbp+var_18]
0x18001ee59  mov     [rsp+80h+var_40], rax
0x18001ee5e  lea     rax, [rbp+arg_18]
0x18001ee62  mov     [rsp+80h+var_48], rax
0x18001ee67  lea     rax, [rbp+var_10]
0x18001ee6b  mov     [rsp+80h+var_50], rax
0x18001ee70  lea     rax, [rbp+var_20]
0x18001ee74  mov     [rsp+80h+var_58], rax
0x18001ee79  lea     rax, [rbp+var_8]
0x18001ee7d  mov     [rsp+80h+var_60], rax
0x18001ee82  mov     [rbp+arg_18], 5F2h
0x18001ee89  mov     [rbp+var_20], ebx
0x18001ee8c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001ee91  jmp     short loc_18001EE98
0x18001ee93  mov     [rbx], rax
0x18001ee96  xor     ebx, ebx
0x18001ee98  mov     eax, ebx
0x18001ee9a  add     rsp, 80h
0x18001eea1  pop     rdi
0x18001eea2  pop     rbx
0x18001eea3  pop     rbp
0x18001eea4  retn
```
