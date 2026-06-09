# CSessionManager::CRestrictedCalls::OpenAndSignalEvent(ushort const *,int)

- ea: `0x18003d108`
- end: `0x18003d2b2`
- name: `?OpenAndSignalEvent@CRestrictedCalls@CSessionManager@@AEAAJPEBGH@Z`
- size: `426`
- prototype: `int(CSessionManager::CRestrictedCalls *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003ccd0`

## callees

- `0x1800015c0`
- `0x180022bb8`
- `0x180027030`
- `0x18003d108`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x18003d180`
- `ntdll!NtOpenEvent` at `0x18003d180`
- `ntdll!RtlInitUnicodeString` at `0x18003d147`
- `ntdll!RtlInitUnicodeString` at `0x18003d147`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003d233`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003d233`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003d1e1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003d1e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d24e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d24e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d281`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d29f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d29f`

## string_xrefs

- `0x18003d19f`: `NtOpenEvent failed in OpenAndSignalEvent`
- `0x18003d26e`: `OpenEvent failed in OpenAndSignalEvent`

## pseudocode

```c
__int64 __fastcall CSessionManager::CRestrictedCalls::OpenAndSignalEvent(
        CSessionManager::CRestrictedCalls *this,
        const unsigned __int16 *a2,
        int a3)
{
  NTSTATUS v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // ebx
  const char *v9; // rax
  __int16 *v10; // rdx
  void *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  HANDLE v15; // rax
  signed int v16; // eax
  signed int LastError; // eax
  const char *v19; // [rsp+40h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+Fh] BYREF
  void *EventHandle; // [rsp+B0h] [rbp+67h] BYREF
  unsigned int v23; // [rsp+C0h] [rbp+77h] BYREF
  __int64 *v24; // [rsp+C8h] [rbp+7Fh] BYREF

  EventHandle = 0;
  if ( a3 )
  {
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = NtOpenEvent(&EventHandle, 2u, &ObjectAttributes);
    v8 = v4 | 0x10000000;
    if ( v4 < 0 )
    {
      if ( (unsigned int)dword_1800DA020 <= 5 )
        goto LABEL_18;
      v9 = "NtOpenEvent failed in OpenAndSignalEvent";
      v10 = word_1800C7EBA;
      goto LABEL_5;
    }
    v11 = EventHandle;
    goto LABEL_7;
  }
  v15 = OpenEventW(2u, 0, a2);
  SmartHANDLE::operator=(&EventHandle, v15);
  v11 = EventHandle;
  if ( EventHandle )
  {
LABEL_7:
    if ( SetEvent(v11) )
    {
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        v24 = (__int64 *)a2;
        v19 = "Successfully signaled event";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned __int8 *)qword_1800C7E40,
          v13,
          v14,
          (const unsigned __int16 **)&v19,
          &v24);
      }
      v8 = 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_18;
  }
  v16 = GetLastError();
  v8 = v16;
  if ( v16 > 0 )
    v8 = (unsigned __int16)v16 | 0x80070000;
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    v9 = "OpenEvent failed in OpenAndSignalEvent";
    v10 = &word_1800C7EEE;
LABEL_5:
    v19 = v9;
    v24 = (__int64 *)a2;
    v23 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v5,
      (int)v10,
      v6,
      v7,
      (const unsigned __int16 **)&v19,
      &v24,
      (__int64)&v23);
  }
LABEL_18:
  if ( EventHandle )
    CloseHandle(EventHandle);
  return v8;
}

```

## disassembly

```asm
0x18003d108  mov     [rsp-8+EventHandle], rcx
0x18003d10d  push    rbp
0x18003d10e  push    rbx
0x18003d10f  push    rdi
0x18003d110  lea     rbp, [rsp-47h]
0x18003d115  sub     rsp, 90h
0x18003d11c  mov     [rbp+57h+EventHandle], 0
0x18003d124  mov     rdi, rdx
0x18003d127  test    r8d, r8d
0x18003d12a  jz      loc_18003D22B
0x18003d130  xorps   xmm0, xmm0
0x18003d133  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003d137  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003d13b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18003d13f  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003d143  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003d147  call    cs:__imp_RtlInitUnicodeString
0x18003d14d  lea     rax, [rbp+57h+DestinationString]
0x18003d151  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003d158  xorps   xmm0, xmm0
0x18003d15b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003d15f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003d163  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18003d16b  mov     edx, 2; DesiredAccess
0x18003d170  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18003d177  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x18003d17b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003d180  call    cs:__imp_NtOpenEvent
0x18003d186  mov     ebx, eax
0x18003d188  or      ebx, 10000000h
0x18003d18e  jge     short loc_18003D1DD
0x18003d190  mov     eax, cs:dword_1800DA020
0x18003d196  cmp     eax, 5
0x18003d199  jbe     loc_18003D296
0x18003d19f  lea     rax, aNtopeneventFai; "NtOpenEvent failed in OpenAndSignalEven"...
0x18003d1a6  lea     rdx, word_1800C7EBA
0x18003d1ad  mov     [rbp+57h+var_60], rax
0x18003d1b1  lea     rax, [rbp+57h+arg_10]
0x18003d1b5  mov     [rsp+0A0h+var_70], rax
0x18003d1ba  lea     rax, [rbp+57h+arg_18]
0x18003d1be  mov     [rsp+0A0h+var_78], rax
0x18003d1c3  lea     rax, [rbp+57h+var_60]
0x18003d1c7  mov     [rsp+0A0h+var_80], rax
0x18003d1cc  mov     [rbp+57h+arg_18], rdi
0x18003d1d0  mov     [rbp+57h+arg_10], ebx
0x18003d1d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003d1d8  jmp     loc_18003D296
0x18003d1dd  mov     rcx, [rbp+57h+EventHandle]; hEvent
0x18003d1e1  call    cs:__imp_SetEvent
0x18003d1e7  test    eax, eax
0x18003d1e9  jz      loc_18003D281
0x18003d1ef  mov     eax, cs:dword_1800DA020
0x18003d1f5  cmp     eax, 5
0x18003d1f8  jbe     short loc_18003D227
0x18003d1fa  lea     rax, aSuccessfullySi; "Successfully signaled event"
0x18003d201  mov     [rbp+57h+arg_18], rdi
0x18003d205  mov     [rbp+57h+var_60], rax
0x18003d209  lea     rdx, qword_1800C7E40
0x18003d210  lea     rax, [rbp+57h+arg_18]
0x18003d214  mov     [rsp+0A0h+var_78], rax
0x18003d219  lea     rax, [rbp+57h+var_60]
0x18003d21d  mov     [rsp+0A0h+var_80], rax
0x18003d222  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003d227  xor     ebx, ebx
0x18003d229  jmp     short loc_18003D296
0x18003d22b  xor     edx, edx; bInheritHandle
0x18003d22d  mov     r8, rdi; lpName
0x18003d230  lea     ecx, [rdx+2]; dwDesiredAccess
0x18003d233  call    cs:__imp_OpenEventW
0x18003d239  mov     rdx, rax
0x18003d23c  lea     rcx, [rbp+57h+EventHandle]
0x18003d240  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x18003d245  mov     rcx, [rbp+57h+EventHandle]
0x18003d249  test    rcx, rcx
0x18003d24c  jnz     short loc_18003D1E1
0x18003d24e  call    cs:__imp_GetLastError
0x18003d254  mov     ebx, eax
0x18003d256  test    eax, eax
0x18003d258  jle     short loc_18003D263
0x18003d25a  movzx   ebx, ax
0x18003d25d  or      ebx, 80070000h
0x18003d263  mov     eax, cs:dword_1800DA020
0x18003d269  cmp     eax, 5
0x18003d26c  jbe     short loc_18003D296
0x18003d26e  lea     rax, aOpeneventFaile; "OpenEvent failed in OpenAndSignalEvent"
0x18003d275  lea     rdx, word_1800C7EEE
0x18003d27c  jmp     loc_18003D1AD
0x18003d281  call    cs:__imp_GetLastError
0x18003d287  mov     ebx, eax
0x18003d289  test    eax, eax
0x18003d28b  jle     short loc_18003D296
0x18003d28d  movzx   ebx, ax
0x18003d290  or      ebx, 80070000h
0x18003d296  mov     rcx, [rbp+57h+EventHandle]; hObject
0x18003d29a  test    rcx, rcx
0x18003d29d  jz      short loc_18003D2A5
0x18003d29f  call    cs:__imp_CloseHandle
0x18003d2a5  mov     eax, ebx
0x18003d2a7  add     rsp, 90h
0x18003d2ae  pop     rdi
0x18003d2af  pop     rbx
0x18003d2b0  pop     rbp
0x18003d2b1  retn
```
