# CRdpUdpStream::AsyncCloseStream(long)

- ea: `0x18040a630`
- end: `0x18040aa25`
- name: `?AsyncCloseStream@CRdpUdpStream@@QEAAXJ@Z`
- size: `1013`
- prototype: `void __fastcall(CRdpUdpStream *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18040dbd0`

## callees

- `0x180002058`
- `0x18040a630`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18040a9f1`
- `KERNEL32!CloseHandle` at `0x18040a9f1`
- `KERNEL32!GetModuleHandleExW` at `0x18040a74b`
- `KERNEL32!GetModuleHandleExW` at `0x18040a74b`
- `KERNEL32!GetLastError` at `0x18040a7f2`
- `KERNEL32!GetLastError` at `0x18040a826`
- `KERNEL32!GetLastError` at `0x18040a955`
- `KERNEL32!GetLastError` at `0x18040a981`
- `KERNEL32!GetLastError` at `0x18040a7f2`
- `KERNEL32!GetLastError` at `0x18040a826`
- `KERNEL32!GetLastError` at `0x18040a955`
- `KERNEL32!GetLastError` at `0x18040a981`
- `KERNEL32!CreateThread` at `0x18040a8ad`
- `KERNEL32!CreateThread` at `0x18040a8ad`
- `ADVAPI32!EventWriteTransfer` at `0x18040a729`
- `ADVAPI32!EventWriteTransfer` at `0x18040a7ec`
- `ADVAPI32!EventWriteTransfer` at `0x18040a94f`
- `ADVAPI32!EventWriteTransfer` at `0x18040a729`
- `ADVAPI32!EventWriteTransfer` at `0x18040a7ec`
- `ADVAPI32!EventWriteTransfer` at `0x18040a94f`

## string_xrefs

- `0x18040a8cb`: `CRdpUdpStream::AsyncCloseStream: CreateThread() failed`
- `0x18040a99d`: `Failed to call CreateThread()`

## pseudocode

```c
void __fastcall CRdpUdpStream::AsyncCloseStream(CRdpUdpStream *this, int a2)
{
  signed int v3; // eax
  bool v4; // sf
  signed int v5; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  HANDLE Thread; // rax
  signed int LastError; // eax
  bool v11; // sf
  signed int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // [rsp+48h] [rbp-39h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-31h] BYREF
  const char *v18; // [rsp+60h] [rbp-21h] BYREF
  _QWORD v19[2]; // [rsp+68h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-9h] BYREF
  __int16 *v21; // [rsp+88h] [rbp+7h]
  int v22; // [rsp+90h] [rbp+Fh]
  int v23; // [rsp+94h] [rbp+13h]
  const char *v24; // [rsp+98h] [rbp+17h]
  __int64 v25; // [rsp+A0h] [rbp+1Fh]
  const char **v26; // [rsp+A8h] [rbp+27h]
  __int64 v27; // [rsp+B0h] [rbp+2Fh]

  if ( !*((_DWORD *)this + 172) )
  {
    *((_DWORD *)this + 172) = a2;
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      LODWORD(v18) = a2;
      v26 = &v18;
      v27 = 4;
      v24 = "CRdpUdpStream::AsyncCloseStream called";
      *(_DWORD *)&EventDescriptor.Level = 4;
      UserData.Ptr = (ULONGLONG)off_1808B5858;
      v25 = 39;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_1808B5858;
      v21 = (__int16 *)qword_1808795A0;
      UserData.Reserved = 2;
      v22 = 29;
      v23 = 1;
      v16 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
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
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v25 = 55;
          v24 = "CRdpUdpStream::AsyncCloseStream: CreateThread() failed";
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = (ULONGLONG)off_1808B5858;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_1808B5858;
          v21 = &word_18087AE4E;
          UserData.Reserved = 2;
          v22 = 19;
          v23 = 1;
          v16 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        }
        LastError = GetLastError();
        v11 = LastError < 0;
        if ( LastError > 0 )
          v11 = 1;
        if ( v11 && (unsigned int)dword_1808B5850 > 3 )
        {
          *(_QWORD *)&EventDescriptor.Id = "AsyncCloseStream";
          v12 = GetLastError();
          if ( v12 > 0 )
            v12 = (unsigned __int16)v12 | 0x80070000;
          v16 = v12;
          v19[0] = "Failed to call CreateThread()";
          v18 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v13,
            (unsigned int)byte_18087A5B1,
            v14,
            v15,
            (__int64)&v18,
            (__int64)v19,
            (__int64)&v16,
            (__int64)&EventDescriptor);
        }
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
      }
    }
    else
    {
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v25 = 60;
        v24 = "CRdpUdpStream::AsyncCloseStream: GetModuleHandleEx() failed";
        *(_DWORD *)&EventDescriptor.Level = 4;
        UserData.Ptr = (ULONGLONG)off_1808B5858;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_1808B5858;
        v21 = &word_180879D76;
        UserData.Reserved = 2;
        v22 = 19;
        v23 = 1;
        v16 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
      v3 = GetLastError();
      v4 = v3 < 0;
      if ( v3 > 0 )
        v4 = 1;
      if ( v4 && (unsigned int)dword_1808B5850 > 3 )
      {
        v18 = "AsyncCloseStream";
        v5 = GetLastError();
        if ( v5 > 0 )
          v5 = (unsigned __int16)v5 | 0x80070000;
        v16 = v5;
        v19[0] = "Failed to call GetModuleHandleEx()";
        *(_QWORD *)&EventDescriptor.Id = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v6,
          (unsigned int)&byte_180879CE7,
          v7,
          v8,
          (__int64)&EventDescriptor,
          (__int64)v19,
          (__int64)&v16,
          (__int64)&v18);
      }
    }
  }
}

```

## disassembly

```asm
0x18040a630  mov     r11, rsp
0x18040a633  push    rbp
0x18040a634  push    rbx
0x18040a635  lea     rbp, [r11-5Fh]
0x18040a639  sub     rsp, 0C8h
0x18040a640  mov     rax, cs:__security_cookie
0x18040a647  xor     rax, rsp
0x18040a64a  mov     [rbp+57h+var_20], rax
0x18040a64e  cmp     dword ptr [rcx+2B0h], 0
0x18040a655  mov     rbx, rcx
0x18040a658  jnz     loc_18040AA0F
0x18040a65e  mov     [r11+10h], rsi
0x18040a662  xor     esi, esi
0x18040a664  mov     [r11+18h], rdi
0x18040a668  lea     rdi, _TraceLoggingMetadataEnd
0x18040a66f  mov     [rcx+2B0h], edx
0x18040a675  mov     eax, cs:dword_1808B5850
0x18040a67b  mov     [r11-18h], r14
0x18040a67f  lea     r14, _TraceLoggingMetadata
0x18040a686  cmp     eax, 4
0x18040a689  jbe     loc_18040A72F
0x18040a68f  mov     dword ptr [rbp+57h+var_78], edx
0x18040a692  lea     rax, [rbp+57h+var_78]
0x18040a696  mov     [rbp+57h+var_30], rax
0x18040a69a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18040a69e  lea     rax, aCrdpudpstreamA; "CRdpUdpStream::AsyncCloseStream called"
0x18040a6a5  mov     [rbp+57h+var_28], 4
0x18040a6ad  mov     [rbp+57h+var_40], rax
0x18040a6b1  xor     r9d, r9d; RelatedActivityId
0x18040a6b4  movzx   eax, cs:word_180879596
0x18040a6bb  xor     r8d, r8d; ActivityId
0x18040a6be  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18040a6c1  mov     rax, cs:off_1808B5858
0x18040a6c8  mov     [rbp+57h+var_60.Ptr], rax
0x18040a6cc  mov     [rbp+57h+var_38], 27h ; '''
0x18040a6d4  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18040a6db  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x18040a6df  movzx   eax, word ptr [rax]
0x18040a6e2  mov     [rbp+57h+var_60.Size], eax
0x18040a6e5  lea     rax, qword_1808795A0
0x18040a6ec  mov     [rbp+57h+var_50], rax
0x18040a6f0  mov     rax, rdi
0x18040a6f3  sub     eax, r14d
0x18040a6f6  mov     dword ptr [rbp+57h+var_60.0Ch], 2
0x18040a6fd  mov     [rbp+57h+var_48], 1Dh
0x18040a704  mov     [rbp+57h+var_44], 1
0x18040a70b  mov     [rbp+57h+var_90], eax
0x18040a70e  mov     eax, [rbp+57h+var_90]
0x18040a711  mov     rcx, cs:RegHandle; RegHandle
0x18040a718  lea     rax, [rbp+57h+var_60]
0x18040a71c  mov     [rsp+0D0h+UserData], rax; UserData
0x18040a721  mov     [rsp+0D0h+UserDataCount], 4; UserDataCount
0x18040a729  call    cs:__imp_EventWriteTransfer
0x18040a72f  lea     r8, [rbx+2B8h]; phModule
0x18040a736  cmp     [r8], rsi
0x18040a739  jnz     loc_18040A886
0x18040a73f  lea     rdx, ?STATIC_AsyncCloseStream@CRdpUdpStream@@KAKPEAX@Z; lpModuleName
0x18040a746  mov     ecx, 4; dwFlags
0x18040a74b  call    cs:__imp_GetModuleHandleExW
0x18040a751  test    eax, eax
0x18040a753  jnz     loc_18040A886
0x18040a759  mov     eax, cs:dword_1808B5850
0x18040a75f  cmp     eax, 4
0x18040a762  jbe     loc_18040A7F2
0x18040a768  lea     rax, aCrdpudpstreamA_1; "CRdpUdpStream::AsyncCloseStream: GetMod"...
0x18040a76f  mov     [rbp+57h+var_38], 3Ch ; '<'
0x18040a777  mov     [rbp+57h+var_40], rax
0x18040a77b  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18040a77f  movzx   eax, cs:word_180879D6C
0x18040a786  sub     edi, r14d
0x18040a789  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18040a78c  xor     r9d, r9d; RelatedActivityId
0x18040a78f  mov     rax, cs:off_1808B5858
0x18040a796  xor     r8d, r8d; ActivityId
0x18040a799  mov     [rbp+57h+var_60.Ptr], rax
0x18040a79d  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18040a7a4  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x18040a7a8  movzx   eax, word ptr [rax]
0x18040a7ab  mov     [rbp+57h+var_60.Size], eax
0x18040a7ae  lea     rax, word_180879D76
0x18040a7b5  mov     [rbp+57h+var_50], rax
0x18040a7b9  mov     dword ptr [rbp+57h+var_60.0Ch], 2
0x18040a7c0  mov     [rbp+57h+var_48], 13h
0x18040a7c7  mov     [rbp+57h+var_44], 1
0x18040a7ce  mov     [rbp+57h+var_90], edi
0x18040a7d1  mov     eax, [rbp+57h+var_90]
0x18040a7d4  mov     rcx, cs:RegHandle; RegHandle
0x18040a7db  lea     rax, [rbp+57h+var_60]
0x18040a7df  mov     [rsp+0D0h+UserData], rax; UserData
0x18040a7e4  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x18040a7ec  call    cs:__imp_EventWriteTransfer
0x18040a7f2  call    cs:__imp_GetLastError
0x18040a7f8  test    eax, eax
0x18040a7fa  jle     short loc_18040A806
0x18040a7fc  movzx   eax, ax
0x18040a7ff  or      eax, 80070000h
0x18040a804  test    eax, eax
0x18040a806  jns     loc_18040A9F7
0x18040a80c  mov     eax, cs:dword_1808B5850
0x18040a812  cmp     eax, 3
0x18040a815  jbe     loc_18040A9F7
0x18040a81b  lea     rax, aAsyncclosestre; "AsyncCloseStream"
0x18040a822  mov     [rbp+57h+var_78], rax
0x18040a826  call    cs:__imp_GetLastError
0x18040a82c  test    eax, eax
0x18040a82e  jle     short loc_18040A838
0x18040a830  movzx   eax, ax
0x18040a833  or      eax, 80070000h
0x18040a838  mov     [rbp+57h+var_90], eax
0x18040a83b  lea     rdx, byte_180879CE7
0x18040a842  lea     rax, aFailedToCallGe; "Failed to call GetModuleHandleEx()"
0x18040a849  mov     [rbp+57h+var_70], rax
0x18040a84d  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18040a854  mov     qword ptr [rbp+57h+EventDescriptor.Id], rax
0x18040a858  lea     rax, [rbp+57h+var_78]
0x18040a85c  mov     [rsp+38h], rax
0x18040a861  lea     rax, [rbp+57h+var_90]
0x18040a865  mov     [rsp+0D0h+var_A0], rax
0x18040a86a  lea     rax, [rbp+57h+var_70]
0x18040a86e  mov     [rsp+0D0h+UserData], rax
0x18040a873  lea     rax, [rbp+57h+EventDescriptor]
0x18040a877  mov     qword ptr [rsp+0D0h+UserDataCount], rax
0x18040a87c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18040a881  jmp     loc_18040A9F7
0x18040a886  mov     rcx, [rbx+20h]
0x18040a88a  mov     rax, [rcx]
0x18040a88d  mov     rax, [rax+8]
0x18040a891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18040a896  mov     r9, rbx; lpParameter
0x18040a899  mov     [rsp+0D0h+UserData], rsi; lpThreadId
0x18040a89e  lea     r8, ?STATIC_AsyncCloseStream@CRdpUdpStream@@KAKPEAX@Z; lpStartAddress
0x18040a8a5  mov     [rsp+0D0h+UserDataCount], esi; dwCreationFlags
0x18040a8a9  xor     edx, edx; dwStackSize
0x18040a8ab  xor     ecx, ecx; lpThreadAttributes
0x18040a8ad  call    cs:__imp_CreateThread
0x18040a8b3  test    rax, rax
0x18040a8b6  jnz     loc_18040A9EE
0x18040a8bc  mov     eax, cs:dword_1808B5850
0x18040a8c2  cmp     eax, 4
0x18040a8c5  jbe     loc_18040A955
0x18040a8cb  lea     rax, aCrdpudpstreamA_0; "CRdpUdpStream::AsyncCloseStream: Create"...
0x18040a8d2  mov     [rbp+57h+var_38], 37h ; '7'
0x18040a8da  mov     [rbp+57h+var_40], rax
0x18040a8de  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18040a8e2  movzx   eax, cs:word_18087AE44
0x18040a8e9  sub     edi, r14d
0x18040a8ec  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18040a8ef  xor     r9d, r9d; RelatedActivityId
0x18040a8f2  mov     rax, cs:off_1808B5858
0x18040a8f9  xor     r8d, r8d; ActivityId
0x18040a8fc  mov     [rbp+57h+var_60.Ptr], rax
0x18040a900  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18040a907  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x18040a90b  movzx   eax, word ptr [rax]
0x18040a90e  mov     [rbp+57h+var_60.Size], eax
0x18040a911  lea     rax, word_18087AE4E
0x18040a918  mov     [rbp+57h+var_50], rax
0x18040a91c  mov     dword ptr [rbp+57h+var_60.0Ch], 2
0x18040a923  mov     [rbp+57h+var_48], 13h
0x18040a92a  mov     [rbp+57h+var_44], 1
0x18040a931  mov     [rbp+57h+var_90], edi
0x18040a934  mov     eax, [rbp+57h+var_90]
0x18040a937  mov     rcx, cs:RegHandle; RegHandle
0x18040a93e  lea     rax, [rbp+57h+var_60]
0x18040a942  mov     [rsp+0D0h+UserData], rax; UserData
0x18040a947  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x18040a94f  call    cs:__imp_EventWriteTransfer
0x18040a955  call    cs:__imp_GetLastError
0x18040a95b  test    eax, eax
0x18040a95d  jle     short loc_18040A969
0x18040a95f  movzx   eax, ax
0x18040a962  or      eax, 80070000h
0x18040a967  test    eax, eax
0x18040a969  jns     short loc_18040A9DC
0x18040a96b  mov     eax, cs:dword_1808B5850
0x18040a971  cmp     eax, 3
0x18040a974  jbe     short loc_18040A9DC
0x18040a976  lea     rax, aAsyncclosestre; "AsyncCloseStream"
0x18040a97d  mov     qword ptr [rbp+57h+EventDescriptor.Id], rax
0x18040a981  call    cs:__imp_GetLastError
0x18040a987  test    eax, eax
0x18040a989  jle     short loc_18040A993
0x18040a98b  movzx   eax, ax
0x18040a98e  or      eax, 80070000h
0x18040a993  mov     [rbp+57h+var_90], eax
0x18040a996  lea     rdx, byte_18087A5B1
0x18040a99d  lea     rax, aFailedToCallCr; "Failed to call CreateThread()"
0x18040a9a4  mov     [rbp+57h+var_70], rax
0x18040a9a8  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18040a9af  mov     [rbp+57h+var_78], rax
0x18040a9b3  lea     rax, [rbp+57h+EventDescriptor]
0x18040a9b7  mov     [rsp+38h], rax
0x18040a9bc  lea     rax, [rbp+57h+var_90]
0x18040a9c0  mov     [rsp+0D0h+var_A0], rax
0x18040a9c5  lea     rax, [rbp+57h+var_70]
0x18040a9c9  mov     [rsp+0D0h+UserData], rax
0x18040a9ce  lea     rax, [rbp+57h+var_78]
0x18040a9d2  mov     qword ptr [rsp+0D0h+UserDataCount], rax
0x18040a9d7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18040a9dc  mov     rcx, [rbx+20h]
0x18040a9e0  mov     rax, [rcx]
0x18040a9e3  mov     rax, [rax+10h]
0x18040a9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18040a9ec  jmp     short loc_18040A9F7
0x18040a9ee  mov     rcx, rax; hObject
0x18040a9f1  call    cs:__imp_CloseHandle
0x18040a9f7  mov     rdi, [rsp+0D0h+arg_10]
0x18040a9ff  mov     rsi, [rsp+0D0h+arg_8]
0x18040aa07  mov     r14, [rsp+0C0h]
0x18040aa0f  mov     rcx, [rbp+57h+var_20]
0x18040aa13  xor     rcx, rsp; StackCookie
0x18040aa16  call    __security_check_cookie
0x18040aa1b  add     rsp, 0C8h
0x18040aa22  pop     rbx
0x18040aa23  pop     rbp
0x18040aa24  retn
```
