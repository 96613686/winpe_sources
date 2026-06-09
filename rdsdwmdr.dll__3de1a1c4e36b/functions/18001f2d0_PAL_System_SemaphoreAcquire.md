# PAL_System_SemaphoreAcquire

- ea: `0x18001f2d0`
- end: `0x18001f3b0`
- name: `PAL_System_SemaphoreAcquire`
- size: `224`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021e1c`
- `0x180024fd0`
- `0x180029818`

## callees

- `0x180001f98`
- `0x18001f2d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f2e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f2e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f318`

## string_xrefs

- `0x18001f33a`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_SemaphoreAcquire(void *a1)
{
  DWORD v1; // eax
  unsigned int v2; // ebx
  DWORD LastError; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  const char *v8; // [rsp+50h] [rbp-20h] BYREF
  const char *v9; // [rsp+58h] [rbp-18h] BYREF
  const char *v10; // [rsp+60h] [rbp-10h] BYREF
  DWORD v11; // [rsp+88h] [rbp+18h] BYREF
  int v12; // [rsp+90h] [rbp+20h] BYREF
  int v13; // [rsp+98h] [rbp+28h] BYREF

  v1 = WaitForSingleObject(a1, 0xFFFFFFFF);
  if ( v1 )
  {
    if ( v1 == 128 )
    {
      return (unsigned int)-2092629814;
    }
    else if ( v1 == 258 )
    {
      return (unsigned int)-2092629813;
    }
    else
    {
      v2 = -2147467259;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LastError = GetLastError();
        v12 = 1118;
        v11 = LastError;
        v8 = "PAL_System_SemaphoreAcquire";
        v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
        v10 = "WaitForSingleObject failed with error %d";
        v13 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v4,
          (__int64)byte_18003F011,
          v5,
          v6,
          (const unsigned __int16 **)&v10,
          (__int64)&v13,
          (const unsigned __int16 **)&v9,
          (__int64)&v12,
          (const unsigned __int16 **)&v8,
          (__int64)&v11);
      }
    }
  }
  else
  {
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18001f2d0  mov     [rsp-8+arg_0], rbx
0x18001f2d5  push    rbp
0x18001f2d6  mov     rbp, rsp
0x18001f2d9  sub     rsp, 70h
0x18001f2dd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f2e0  call    cs:__imp_WaitForSingleObject
0x18001f2e6  test    eax, eax
0x18001f2e8  jz      loc_18001F39E
0x18001f2ee  cmp     eax, 80h
0x18001f2f3  jz      loc_18001F397
0x18001f2f9  cmp     eax, 102h
0x18001f2fe  jz      loc_18001F390
0x18001f304  mov     eax, cs:dword_180044008
0x18001f30a  mov     ebx, 80004005h
0x18001f30f  cmp     eax, 2
0x18001f312  jbe     loc_18001F3A0
0x18001f318  call    cs:__imp_GetLastError
0x18001f31e  lea     rdx, byte_18003F011
0x18001f325  mov     [rbp+arg_10], 45Eh
0x18001f32c  mov     [rbp+arg_8], eax
0x18001f32f  lea     rax, aPalSystemSemap; "PAL_System_SemaphoreAcquire"
0x18001f336  mov     [rbp+var_20], rax
0x18001f33a  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001f341  mov     [rbp+var_18], rax
0x18001f345  lea     rax, aWaitforsingleo; "WaitForSingleObject failed with error %"...
0x18001f34c  mov     [rbp+var_10], rax
0x18001f350  lea     rax, [rbp+arg_8]
0x18001f354  mov     [rsp+70h+var_28], rax
0x18001f359  lea     rax, [rbp+var_20]
0x18001f35d  mov     [rsp+70h+var_30], rax
0x18001f362  lea     rax, [rbp+arg_10]
0x18001f366  mov     [rsp+70h+var_38], rax
0x18001f36b  lea     rax, [rbp+var_18]
0x18001f36f  mov     [rsp+70h+var_40], rax
0x18001f374  lea     rax, [rbp+arg_18]
0x18001f378  mov     [rsp+70h+var_48], rax
0x18001f37d  lea     rax, [rbp+var_10]
0x18001f381  mov     [rsp+70h+var_50], rax
0x18001f386  mov     [rbp+arg_18], ebx
0x18001f389  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001f38e  jmp     short loc_18001F3A0
0x18001f390  mov     ebx, 834500CBh
0x18001f395  jmp     short loc_18001F3A0
0x18001f397  mov     ebx, 834500CAh
0x18001f39c  jmp     short loc_18001F3A0
0x18001f39e  xor     ebx, ebx
0x18001f3a0  mov     eax, ebx
0x18001f3a2  mov     rbx, [rsp+70h+arg_0]
0x18001f3aa  add     rsp, 70h
0x18001f3ae  pop     rbp
0x18001f3af  retn
```
