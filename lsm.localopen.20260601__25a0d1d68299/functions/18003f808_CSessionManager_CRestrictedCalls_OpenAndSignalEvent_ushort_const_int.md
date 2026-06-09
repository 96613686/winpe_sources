# CSessionManager::CRestrictedCalls::OpenAndSignalEvent(ushort const *,int)

- ea: `0x18003f808`
- end: `0x18003f9d1`
- name: `?OpenAndSignalEvent@CRestrictedCalls@CSessionManager@@AEAAJPEBGH@Z`
- size: `457`
- prototype: `int(CSessionManager::CRestrictedCalls *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003f3d0`

## callees

- `0x1800015c4`
- `0x180012650`
- `0x1800248ac`
- `0x1800291f4`
- `0x18003f808`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x18003f886`
- `ntdll!NtOpenEvent` at `0x18003f886`
- `ntdll!RtlInitUnicodeString` at `0x18003f847`
- `ntdll!RtlInitUnicodeString` at `0x18003f847`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003f945`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003f945`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f8ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f8ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f99f`

## string_xrefs

- `0x18003f8ab`: `NtOpenEvent failed in OpenAndSignalEvent`
- `0x18003f98c`: `OpenEvent failed in OpenAndSignalEvent`

## pseudocode

```c
__int64 __fastcall CSessionManager::CRestrictedCalls::OpenAndSignalEvent(
        CSessionManager::CRestrictedCalls *this,
        const unsigned __int16 *a2,
        int a3)
{
  NTSTATUS v4; // eax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // ebx
  const char *v9; // rax
  __int16 *v10; // rdx
  void *v11; // rcx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  HANDLE v15; // rax
  signed int v16; // eax
  signed int LastError; // eax
  const char *v19; // [rsp+40h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+Fh] BYREF
  void *EventHandle; // [rsp+B0h] [rbp+67h] BYREF
  unsigned int v23; // [rsp+C0h] [rbp+77h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+7Fh] BYREF

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
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        v9 = "NtOpenEvent failed in OpenAndSignalEvent";
        v10 = &word_1800CD076;
LABEL_5:
        v19 = v9;
        v24 = a2;
        v23 = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v5,
          (_DWORD)v10,
          v6,
          v7,
          (__int64)&v19,
          (__int64)&v24,
          (__int64)&v23);
        goto LABEL_18;
      }
      goto LABEL_18;
    }
    v11 = EventHandle;
LABEL_7:
    if ( SetEvent(v11) )
    {
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        v24 = a2;
        v19 = "Successfully signaled event";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)byte_1800CD013,
          v13,
          v14,
          (__int64)&v19,
          (__int64)&v24);
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
  v15 = OpenEventW(2u, 0, a2);
  SmartHANDLE::operator=(&EventHandle, v15);
  v11 = EventHandle;
  if ( EventHandle )
    goto LABEL_7;
  v16 = GetLastError();
  v8 = v16;
  if ( v16 > 0 )
    v8 = (unsigned __int16)v16 | 0x80070000;
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    v9 = "OpenEvent failed in OpenAndSignalEvent";
    v10 = word_1800CD042;
    goto LABEL_5;
  }
LABEL_18:
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&EventHandle);
  return v8;
}

```

## disassembly

```asm
0x18003f808  mov     [rsp-8+EventHandle], rcx
0x18003f80d  push    rbp
0x18003f80e  push    rbx
0x18003f80f  push    rdi
0x18003f810  lea     rbp, [rsp-47h]
0x18003f815  sub     rsp, 90h
0x18003f81c  mov     [rbp+57h+EventHandle], 0
0x18003f824  mov     rdi, rdx
0x18003f827  test    r8d, r8d
0x18003f82a  jz      loc_18003F93D
0x18003f830  xorps   xmm0, xmm0
0x18003f833  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003f837  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003f83b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18003f83f  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003f843  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003f847  call    cs:__imp_RtlInitUnicodeString
0x18003f84e  nop     dword ptr [rax+rax+00h]
0x18003f853  lea     rax, [rbp+57h+DestinationString]
0x18003f857  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003f85e  xorps   xmm0, xmm0
0x18003f861  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003f865  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003f869  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18003f871  mov     edx, 2; DesiredAccess
0x18003f876  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18003f87d  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x18003f881  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003f886  call    cs:__imp_NtOpenEvent
0x18003f88d  nop     dword ptr [rax+rax+00h]
0x18003f892  mov     ebx, eax
0x18003f894  or      ebx, 10000000h
0x18003f89a  jge     short loc_18003F8E9
0x18003f89c  mov     eax, cs:dword_1800DF020
0x18003f8a2  cmp     eax, 5
0x18003f8a5  jbe     loc_18003F9BA
0x18003f8ab  lea     rax, aNtopeneventFai; "NtOpenEvent failed in OpenAndSignalEven"...
0x18003f8b2  lea     rdx, word_1800CD076
0x18003f8b9  mov     [rbp+57h+var_60], rax
0x18003f8bd  lea     rax, [rbp+57h+arg_10]
0x18003f8c1  mov     [rsp+0A0h+var_70], rax
0x18003f8c6  lea     rax, [rbp+57h+arg_18]
0x18003f8ca  mov     [rsp+0A0h+var_78], rax
0x18003f8cf  lea     rax, [rbp+57h+var_60]
0x18003f8d3  mov     [rsp+0A0h+var_80], rax
0x18003f8d8  mov     [rbp+57h+arg_18], rdi
0x18003f8dc  mov     [rbp+57h+arg_10], ebx
0x18003f8df  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003f8e4  jmp     loc_18003F9BA
0x18003f8e9  mov     rcx, [rbp+57h+EventHandle]; hEvent
0x18003f8ed  call    cs:__imp_SetEvent
0x18003f8f4  nop     dword ptr [rax+rax+00h]
0x18003f8f9  test    eax, eax
0x18003f8fb  jz      loc_18003F99F
0x18003f901  mov     eax, cs:dword_1800DF020
0x18003f907  cmp     eax, 5
0x18003f90a  jbe     short loc_18003F939
0x18003f90c  lea     rax, aSuccessfullySi; "Successfully signaled event"
0x18003f913  mov     [rbp+57h+arg_18], rdi
0x18003f917  mov     [rbp+57h+var_60], rax
0x18003f91b  lea     rdx, byte_1800CD013
0x18003f922  lea     rax, [rbp+57h+arg_18]
0x18003f926  mov     [rsp+0A0h+var_78], rax
0x18003f92b  lea     rax, [rbp+57h+var_60]
0x18003f92f  mov     [rsp+0A0h+var_80], rax
0x18003f934  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003f939  xor     ebx, ebx
0x18003f93b  jmp     short loc_18003F9BA
0x18003f93d  xor     edx, edx; bInheritHandle
0x18003f93f  mov     r8, rdi; lpName
0x18003f942  lea     ecx, [rdx+2]; dwDesiredAccess
0x18003f945  call    cs:__imp_OpenEventW
0x18003f94c  nop     dword ptr [rax+rax+00h]
0x18003f951  mov     rdx, rax
0x18003f954  lea     rcx, [rbp+57h+EventHandle]
0x18003f958  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x18003f95d  mov     rcx, [rbp+57h+EventHandle]
0x18003f961  test    rcx, rcx
0x18003f964  jnz     short loc_18003F8ED
0x18003f966  call    cs:__imp_GetLastError
0x18003f96d  nop     dword ptr [rax+rax+00h]
0x18003f972  mov     ebx, eax
0x18003f974  test    eax, eax
0x18003f976  jle     short loc_18003F981
0x18003f978  movzx   ebx, ax
0x18003f97b  or      ebx, 80070000h
0x18003f981  mov     eax, cs:dword_1800DF020
0x18003f987  cmp     eax, 5
0x18003f98a  jbe     short loc_18003F9BA
0x18003f98c  lea     rax, aOpeneventFaile; "OpenEvent failed in OpenAndSignalEvent"
0x18003f993  lea     rdx, word_1800CD042
0x18003f99a  jmp     loc_18003F8B9
0x18003f99f  call    cs:__imp_GetLastError
0x18003f9a6  nop     dword ptr [rax+rax+00h]
0x18003f9ab  mov     ebx, eax
0x18003f9ad  test    eax, eax
0x18003f9af  jle     short loc_18003F9BA
0x18003f9b1  movzx   ebx, ax
0x18003f9b4  or      ebx, 80070000h
0x18003f9ba  lea     rcx, [rbp+57h+EventHandle]; this
0x18003f9be  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18003f9c3  mov     eax, ebx
0x18003f9c5  add     rsp, 90h
0x18003f9cc  pop     rdi
0x18003f9cd  pop     rbx
0x18003f9ce  pop     rbp
0x18003f9cf  retn
```
