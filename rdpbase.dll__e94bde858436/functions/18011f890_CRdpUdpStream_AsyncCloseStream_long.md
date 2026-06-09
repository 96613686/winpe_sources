# CRdpUdpStream::AsyncCloseStream(long)

- ea: `0x18011f890`
- end: `0x18011fafe`
- name: `?AsyncCloseStream@CRdpUdpStream@@QEAAXJ@Z`
- size: `622`
- prototype: `void __fastcall(CRdpUdpStream *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801234a0`

## callees

- `0x180002550`
- `0x180004a94`
- `0x180005090`
- `0x18011f890`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18011f907`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18011f907`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18011fa0d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18011fa0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f94a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f97e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fa51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fa7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f94a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f97e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fa51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fa7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011faed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011faed`

## string_xrefs

- `0x18011fa99`: `Failed to call CreateThread()`
- `0x18011fa27`: `CRdpUdpStream::AsyncCloseStream: CreateThread() failed`

## pseudocode

```c
void __fastcall CRdpUdpStream::AsyncCloseStream(CRdpUdpStream *this, int a2, int a3, int a4)
{
  int v5; // r9d
  signed int v6; // eax
  bool v7; // sf
  signed int v8; // eax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  HANDLE Thread; // rax
  int v13; // r9d
  signed int LastError; // eax
  bool v15; // sf
  signed int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  _QWORD v20[2]; // [rsp+40h] [rbp-10h] BYREF
  const char *v21; // [rsp+60h] [rbp+10h] BYREF
  const char *v22; // [rsp+70h] [rbp+20h] BYREF
  const char *v23; // [rsp+78h] [rbp+28h] BYREF

  if ( !*((_DWORD *)this + 172) )
  {
    *((_DWORD *)this + 172) = a2;
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v21) = a2;
      v22 = "CRdpUdpStream::AsyncCloseStream called";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)this,
        (unsigned int)byte_1801CD97B,
        a3,
        a4,
        (__int64)&v22,
        (__int64)&v21);
    }
    if ( *((_QWORD *)this + 87)
      || GetModuleHandleExW(4u, (LPCWSTR)CRdpUdpStream::STATIC_AsyncCloseStream, (HMODULE *)this + 87) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4));
      Thread = CreateThread(0, 0, CRdpUdpStream::STATIC_AsyncCloseStream, this, 0, 0);
      if ( Thread )
      {
        CloseHandle(Thread);
      }
      else
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v21 = "CRdpUdpStream::AsyncCloseStream: CreateThread() failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)byte_1801CF2BD,
            0,
            v13,
            (__int64)&v21);
        }
        LastError = GetLastError();
        v15 = LastError < 0;
        if ( LastError > 0 )
          v15 = 1;
        if ( v15 && (unsigned int)CallbackContext > 3 )
        {
          v22 = "AsyncCloseStream";
          v16 = GetLastError();
          if ( v16 > 0 )
            v16 = (unsigned __int16)v16 | 0x80070000;
          LODWORD(v21) = v16;
          v23 = "Failed to call CreateThread()";
          v20[0] = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v17,
            (unsigned int)byte_1801CEB01,
            v18,
            v19,
            (__int64)v20,
            (__int64)&v23,
            (__int64)&v21,
            (__int64)&v22);
        }
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
      }
    }
    else
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v21 = "CRdpUdpStream::AsyncCloseStream: GetModuleHandleEx() failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)&word_1801CE22E,
          0,
          v5,
          (__int64)&v21);
      }
      v6 = GetLastError();
      v7 = v6 < 0;
      if ( v6 > 0 )
        v7 = 1;
      if ( v7 && (unsigned int)CallbackContext > 3 )
      {
        v22 = "AsyncCloseStream";
        v8 = GetLastError();
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        LODWORD(v21) = v8;
        v23 = "Failed to call GetModuleHandleEx()";
        v20[0] = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v9,
          (unsigned int)qword_1801CE298,
          v10,
          v11,
          (__int64)v20,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v22);
      }
    }
  }
}

```

## disassembly

```asm
0x18011f890  mov     [rsp-8+arg_8], rdi
0x18011f895  push    rbp
0x18011f896  mov     rbp, rsp
0x18011f899  sub     rsp, 50h
0x18011f89d  cmp     dword ptr [rcx+2B0h], 0
0x18011f8a4  mov     rdi, rcx
0x18011f8a7  jnz     loc_18011FAF3
0x18011f8ad  mov     [rcx+2B0h], edx
0x18011f8b3  mov     eax, cs:CallbackContext
0x18011f8b9  cmp     eax, 4
0x18011f8bc  jbe     short loc_18011F8EA
0x18011f8be  lea     rax, aCrdpudpstreamA; "CRdpUdpStream::AsyncCloseStream called"
0x18011f8c5  mov     dword ptr [rbp+arg_0], edx
0x18011f8c8  mov     [rbp+arg_10], rax
0x18011f8cc  lea     rdx, byte_1801CD97B
0x18011f8d3  lea     rax, [rbp+arg_0]
0x18011f8d7  mov     [rsp+50h+lpThreadId], rax
0x18011f8dc  lea     rax, [rbp+arg_10]
0x18011f8e0  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x18011f8e5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18011f8ea  lea     r8, [rdi+2B8h]; phModule
0x18011f8f1  cmp     qword ptr [r8], 0
0x18011f8f5  jnz     loc_18011F9DE
0x18011f8fb  lea     rdx, ?STATIC_AsyncCloseStream@CRdpUdpStream@@KAKPEAX@Z; lpModuleName
0x18011f902  mov     ecx, 4; dwFlags
0x18011f907  call    cs:__imp_GetModuleHandleExW
0x18011f90d  test    eax, eax
0x18011f90f  jnz     loc_18011F9DE
0x18011f915  mov     eax, cs:CallbackContext
0x18011f91b  cmp     eax, 4
0x18011f91e  jbe     short loc_18011F94A
0x18011f920  lea     rax, aCrdpudpstreamA_1; "CRdpUdpStream::AsyncCloseStream: GetMod"...
0x18011f927  xor     r8d, r8d
0x18011f92a  mov     [rbp+arg_0], rax
0x18011f92e  lea     rdx, word_1801CE22E
0x18011f935  lea     rax, [rbp+arg_0]
0x18011f939  lea     rcx, CallbackContext
0x18011f940  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x18011f945  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18011f94a  call    cs:__imp_GetLastError
0x18011f950  test    eax, eax
0x18011f952  jle     short loc_18011F95E
0x18011f954  movzx   eax, ax
0x18011f957  or      eax, 80070000h
0x18011f95c  test    eax, eax
0x18011f95e  jns     loc_18011FAF3
0x18011f964  mov     eax, cs:CallbackContext
0x18011f96a  cmp     eax, 3
0x18011f96d  jbe     loc_18011FAF3
0x18011f973  lea     rax, aAsyncclosestre; "AsyncCloseStream"
0x18011f97a  mov     [rbp+arg_10], rax
0x18011f97e  call    cs:__imp_GetLastError
0x18011f984  test    eax, eax
0x18011f986  jle     short loc_18011F990
0x18011f988  movzx   eax, ax
0x18011f98b  or      eax, 80070000h
0x18011f990  mov     dword ptr [rbp+arg_0], eax
0x18011f993  lea     rdx, qword_1801CE298
0x18011f99a  lea     rax, aFailedToCallGe; "Failed to call GetModuleHandleEx()"
0x18011f9a1  mov     [rbp+arg_18], rax
0x18011f9a5  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18011f9ac  mov     [rbp+var_10], rax
0x18011f9b0  lea     rax, [rbp+arg_10]
0x18011f9b4  mov     [rsp+50h+var_18], rax
0x18011f9b9  lea     rax, [rbp+arg_0]
0x18011f9bd  mov     [rsp+50h+var_20], rax
0x18011f9c2  lea     rax, [rbp+arg_18]
0x18011f9c6  mov     [rsp+50h+lpThreadId], rax
0x18011f9cb  lea     rax, [rbp+var_10]
0x18011f9cf  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x18011f9d4  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18011f9d9  jmp     loc_18011FAF3
0x18011f9de  mov     rcx, [rdi+20h]
0x18011f9e2  mov     rax, [rcx]
0x18011f9e5  mov     rax, [rax+8]
0x18011f9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f9ee  mov     r9, rdi; lpParameter
0x18011f9f1  mov     [rsp+50h+lpThreadId], 0; lpThreadId
0x18011f9fa  lea     r8, ?STATIC_AsyncCloseStream@CRdpUdpStream@@KAKPEAX@Z; lpStartAddress
0x18011fa01  mov     [rsp+50h+dwCreationFlags], 0; dwCreationFlags
0x18011fa09  xor     edx, edx; dwStackSize
0x18011fa0b  xor     ecx, ecx; lpThreadAttributes
0x18011fa0d  call    cs:__imp_CreateThread
0x18011fa13  test    rax, rax
0x18011fa16  jnz     loc_18011FAEA
0x18011fa1c  mov     eax, cs:CallbackContext
0x18011fa22  cmp     eax, 4
0x18011fa25  jbe     short loc_18011FA51
0x18011fa27  lea     rax, aCrdpudpstreamA_0; "CRdpUdpStream::AsyncCloseStream: Create"...
0x18011fa2e  xor     r8d, r8d
0x18011fa31  mov     [rbp+arg_0], rax
0x18011fa35  lea     rdx, byte_1801CF2BD
0x18011fa3c  lea     rax, [rbp+arg_0]
0x18011fa40  lea     rcx, CallbackContext
0x18011fa47  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x18011fa4c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18011fa51  call    cs:__imp_GetLastError
0x18011fa57  test    eax, eax
0x18011fa59  jle     short loc_18011FA65
0x18011fa5b  movzx   eax, ax
0x18011fa5e  or      eax, 80070000h
0x18011fa63  test    eax, eax
0x18011fa65  jns     short loc_18011FAD8
0x18011fa67  mov     eax, cs:CallbackContext
0x18011fa6d  cmp     eax, 3
0x18011fa70  jbe     short loc_18011FAD8
0x18011fa72  lea     rax, aAsyncclosestre; "AsyncCloseStream"
0x18011fa79  mov     [rbp+arg_10], rax
0x18011fa7d  call    cs:__imp_GetLastError
0x18011fa83  test    eax, eax
0x18011fa85  jle     short loc_18011FA8F
0x18011fa87  movzx   eax, ax
0x18011fa8a  or      eax, 80070000h
0x18011fa8f  mov     dword ptr [rbp+arg_0], eax
0x18011fa92  lea     rdx, byte_1801CEB01
0x18011fa99  lea     rax, aFailedToCallCr; "Failed to call CreateThread()"
0x18011faa0  mov     [rbp+arg_18], rax
0x18011faa4  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18011faab  mov     [rbp+var_10], rax
0x18011faaf  lea     rax, [rbp+arg_10]
0x18011fab3  mov     [rsp+50h+var_18], rax
0x18011fab8  lea     rax, [rbp+arg_0]
0x18011fabc  mov     [rsp+50h+var_20], rax
0x18011fac1  lea     rax, [rbp+arg_18]
0x18011fac5  mov     [rsp+50h+lpThreadId], rax
0x18011faca  lea     rax, [rbp+var_10]
0x18011face  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x18011fad3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18011fad8  mov     rcx, [rdi+20h]
0x18011fadc  mov     rax, [rcx]
0x18011fadf  mov     rax, [rax+10h]
0x18011fae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fae8  jmp     short loc_18011FAF3
0x18011faea  mov     rcx, rax; hObject
0x18011faed  call    cs:__imp_CloseHandle
0x18011faf3  mov     rdi, [rsp+50h+arg_8]
0x18011faf8  add     rsp, 50h
0x18011fafc  pop     rbp
0x18011fafd  retn
```
