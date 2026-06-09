# RegKeyNotificationsInitialize

- ea: `0x18007a8b4`
- end: `0x18007aafc`
- name: `RegKeyNotificationsInitialize`
- size: `584`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180076828`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18004d378`
- `0x18004f2e0`
- `0x180050d34`
- `0x180051fa4`
- `0x18007a8b4`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18007aac9`
- `ntoskrnl!ZwClose` at `0x18007aac9`
- `ntoskrnl!KeInitializeEvent` at `0x18007a9bd`
- `ntoskrnl!KeInitializeEvent` at `0x18007a9bd`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18007a910`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18007a9c9`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18007a910`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18007a9c9`
- `ntoskrnl!PsCreateSystemThread` at `0x18007aa38`
- `ntoskrnl!PsCreateSystemThread` at `0x18007aa38`

## string_xrefs

- `0x18007aa52`: `RegKeyNotificationsInitialize:: PsCreateSystemThread failed. ntStatus: %ld`
- `0x18007a95b`: `RegKeyNotificationsInitialize:: pCngConfigContext == nullptr`
- `0x18007aa83`: `RegKeyNotificationsInitialize:: PsCreateSystemThread failed`

## pseudocode

```c
__int64 __fastcall RegKeyNotificationsInitialize(PVOID StartContext, __int64 a2)
{
  __int64 CurrentServerSilo; // rax
  int v4; // r8d
  int v5; // r9d
  const char *v6; // rcx
  unsigned int v7; // ebx
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  __int64 v10; // rdx
  struct _KEVENT *v11; // rax
  NTSTATUS v12; // eax
  int v13; // eax
  wchar_t *v14; // rcx
  __int64 v15; // rax
  void *v16; // rcx
  PVOID StartContexta; // [rsp+30h] [rbp-D0h]
  void *ThreadHandle; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  const char *v21; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[1024]; // [rsp+90h] [rbp-70h] BYREF

  if ( (unsigned int)dword_1800D1588 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D1588, 0x200000000000LL) )
  {
    v20 = 0x1000000;
    CurrentServerSilo = PsGetCurrentServerSilo();
    v6 = "Container";
    if ( !CurrentServerSilo )
      v6 = "Host";
    v21 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v6,
      (unsigned int)&unk_1800C93C8,
      v4,
      v5,
      (__int64)&v21,
      (__int64)&v20);
  }
  if ( StartContext )
  {
    v8 = (_QWORD *)MSCryptAlloc(96, a2);
    *((_QWORD *)StartContext + 53) = v8;
    v9 = v8;
    if ( v8 && (memset(v8, 0, 0x60u), v11 = (struct _KEVENT *)MSCryptAlloc(24, v10), (v9[1] = v11) != 0) )
    {
      KeInitializeEvent(v11, NotificationEvent, 0);
      v9[11] = PsGetCurrentServerSilo();
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 512;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ThreadHandle = 0;
      v12 = PsCreateSystemThread(
              &ThreadHandle,
              0,
              &ObjectAttributes,
              0,
              0,
              (PKSTART_ROUTINE)ConfigRegChangeWatch,
              StartContext);
      v7 = v12;
      if ( v12 >= 0 )
      {
        ZwClose(ThreadHandle);
        return v7;
      }
      LODWORD(StartContexta) = v12;
      v13 = StringCchPrintfExW(
              pszDest,
              0x400u,
              0,
              0,
              0,
              L"RegKeyNotificationsInitialize:: PsCreateSystemThread failed. ntStatus: %ld",
              StartContexta);
      if ( (int)(v13 + 0x80000000) < 0
        || (v14 = L"RegKeyNotificationsInitialize:: PsCreateSystemThread failed", v13 == -2147024774) )
      {
        v14 = pszDest;
      }
      SendTelemetry(v14);
      v7 = 0;
    }
    else
    {
      v7 = -1073741801;
    }
    v15 = *((_QWORD *)StartContext + 53);
    if ( v15 )
    {
      v16 = *(void **)(v15 + 8);
      if ( v16 )
        MSCryptFree(v16);
      MSCryptFree(*((PVOID *)StartContext + 53));
    }
  }
  else
  {
    SendTelemetry(L"RegKeyNotificationsInitialize:: pCngConfigContext == nullptr");
    return (unsigned int)-1073741816;
  }
  return v7;
}

```

## disassembly

```asm
0x18007a8b4  mov     [rsp-8+arg_8], rbx
0x18007a8b9  mov     [rsp-8+arg_10], rdi
0x18007a8be  push    rbp
0x18007a8bf  lea     rbp, [rsp-7A0h]
0x18007a8c7  sub     rsp, 8A0h
0x18007a8ce  mov     rax, cs:__security_cookie
0x18007a8d5  xor     rax, rsp
0x18007a8d8  mov     [rbp+7A0h+var_10], rax
0x18007a8df  mov     eax, cs:dword_1800D1588
0x18007a8e5  mov     rdi, rcx
0x18007a8e8  cmp     eax, 5
0x18007a8eb  jbe     short loc_18007A956
0x18007a8ed  mov     rdx, 200000000000h
0x18007a8f7  lea     rcx, dword_1800D1588
0x18007a8fe  call    _tlgKeywordOn
0x18007a903  test    al, al
0x18007a905  jz      short loc_18007A956
0x18007a907  mov     [rsp+8A0h+var_858], 1000000h
0x18007a910  call    cs:__imp_PsGetCurrentServerSilo
0x18007a917  nop     dword ptr [rax+rax+00h]
0x18007a91c  test    rax, rax
0x18007a91f  lea     rdx, aHost; "Host"
0x18007a926  lea     rax, [rsp+8A0h+var_858]
0x18007a92b  mov     [rsp+8A0h+StartRoutine], rax
0x18007a930  lea     rcx, aContainer; "Container"
0x18007a937  cmovz   rcx, rdx
0x18007a93b  lea     rax, [rsp+8A0h+var_850]
0x18007a940  lea     rdx, unk_1800C93C8
0x18007a947  mov     [rsp+8A0h+ClientId], rax
0x18007a94c  mov     [rsp+8A0h+var_850], rcx
0x18007a951  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18007a956  test    rdi, rdi
0x18007a959  jnz     short loc_18007A971
0x18007a95b  lea     rcx, aRegkeynotifica_1; "RegKeyNotificationsInitialize:: pCngCon"...
0x18007a962  call    SendTelemetry
0x18007a967  mov     ebx, 0C0000008h
0x18007a96c  jmp     loc_18007AAD5
0x18007a971  mov     ecx, 60h ; '`'
0x18007a976  call    MSCryptAlloc
0x18007a97b  mov     [rdi+1A8h], rax
0x18007a982  mov     rbx, rax
0x18007a985  test    rax, rax
0x18007a988  jnz     short loc_18007A994
0x18007a98a  mov     ebx, 0C0000017h
0x18007a98f  jmp     loc_18007AA9C
0x18007a994  xor     edx, edx; Val
0x18007a996  mov     rcx, rbx; void *
0x18007a999  lea     r8d, [rdx+60h]; Size
0x18007a99d  call    memset
0x18007a9a2  mov     ecx, 18h
0x18007a9a7  call    MSCryptAlloc
0x18007a9ac  mov     [rbx+8], rax
0x18007a9b0  test    rax, rax
0x18007a9b3  jz      short loc_18007A98A
0x18007a9b5  xor     r8d, r8d; State
0x18007a9b8  xor     edx, edx; Type
0x18007a9ba  mov     rcx, rax; Event
0x18007a9bd  call    cs:__imp_KeInitializeEvent
0x18007a9c4  nop     dword ptr [rax+rax+00h]
0x18007a9c9  call    cs:__imp_PsGetCurrentServerSilo
0x18007a9d0  nop     dword ptr [rax+rax+00h]
0x18007a9d5  xorps   xmm0, xmm0
0x18007a9d8  mov     [rsp+8A0h+StartContext], rdi; StartContext
0x18007a9dd  mov     [rbx+58h], rax
0x18007a9e1  lea     r8, [rsp+8A0h+ObjectAttributes]; ObjectAttributes
0x18007a9e6  lea     rax, ConfigRegChangeWatch
0x18007a9ed  mov     qword ptr [rsp+8A0h+ObjectAttributes.Length], 30h ; '0'
0x18007a9f6  mov     [rsp+8A0h+StartRoutine], rax; StartRoutine
0x18007a9fb  lea     rcx, [rsp+8A0h+ThreadHandle]; ThreadHandle
0x18007aa00  xor     r9d, r9d; ProcessHandle
0x18007aa03  mov     [rsp+8A0h+ClientId], 0; ClientId
0x18007aa0c  xor     edx, edx; DesiredAccess
0x18007aa0e  mov     qword ptr [rsp+8A0h+ObjectAttributes.Attributes], 200h
0x18007aa17  mov     [rsp+8A0h+ObjectAttributes.RootDirectory], 0
0x18007aa20  mov     [rsp+8A0h+ObjectAttributes.ObjectName], 0
0x18007aa29  movdqu  xmmword ptr [rsp+8A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007aa2f  mov     [rsp+8A0h+ThreadHandle], 0
0x18007aa38  call    cs:__imp_PsCreateSystemThread
0x18007aa3f  nop     dword ptr [rax+rax+00h]
0x18007aa44  mov     ebx, eax
0x18007aa46  test    eax, eax
0x18007aa48  jns     short loc_18007AAC4
0x18007aa4a  mov     dword ptr [rsp+8A0h+StartContext], eax
0x18007aa4e  lea     rcx, [rbp+7A0h+pszDest]; pszDest
0x18007aa52  lea     rax, aRegkeynotifica; "RegKeyNotificationsInitialize:: PsCreat"...
0x18007aa59  xor     r9d, r9d; unsigned __int64 *
0x18007aa5c  mov     [rsp+8A0h+StartRoutine], rax; unsigned __int16 *
0x18007aa61  xor     r8d, r8d; unsigned __int16 **
0x18007aa64  mov     edx, 400h; unsigned __int64
0x18007aa69  mov     [rsp+8A0h+ClientId], 0; unsigned int
0x18007aa72  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18007aa77  mov     edx, 80000000h
0x18007aa7c  lea     ecx, [rax+rdx]
0x18007aa7f  test    edx, ecx
0x18007aa81  jnz     short loc_18007AA91
0x18007aa83  lea     rcx, aRegkeynotifica_0; "RegKeyNotificationsInitialize:: PsCreat"...
0x18007aa8a  cmp     eax, 8007007Ah
0x18007aa8f  jnz     short loc_18007AA95
0x18007aa91  lea     rcx, [rbp+7A0h+pszDest]
0x18007aa95  call    SendTelemetry
0x18007aa9a  xor     ebx, ebx
0x18007aa9c  mov     rax, [rdi+1A8h]
0x18007aaa3  test    rax, rax
0x18007aaa6  jz      short loc_18007AAD5
0x18007aaa8  mov     rcx, [rax+8]; P
0x18007aaac  test    rcx, rcx
0x18007aaaf  jz      short loc_18007AAB6
0x18007aab1  call    MSCryptFree
0x18007aab6  mov     rcx, [rdi+1A8h]; P
0x18007aabd  call    MSCryptFree
0x18007aac2  jmp     short loc_18007AAD5
0x18007aac4  mov     rcx, [rsp+8A0h+ThreadHandle]; Handle
0x18007aac9  call    cs:__imp_ZwClose
0x18007aad0  nop     dword ptr [rax+rax+00h]
0x18007aad5  mov     eax, ebx
0x18007aad7  mov     rcx, [rbp+7A0h+var_10]
0x18007aade  xor     rcx, rsp; StackCookie
0x18007aae1  call    __security_check_cookie
0x18007aae6  lea     r11, [rsp+8A0h+var_s0]
0x18007aaee  mov     rbx, [r11+18h]
0x18007aaf2  mov     rdi, [r11+20h]
0x18007aaf6  mov     rsp, r11
0x18007aaf9  pop     rbp
0x18007aafa  retn
```
