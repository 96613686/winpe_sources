# RegKeyNotificationsInitialize

- ea: `0x180071114`
- end: `0x18007135c`
- name: `RegKeyNotificationsInitialize`
- size: `584`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006d088`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180043e28`
- `0x180045c80`
- `0x1800476d4`
- `0x180048944`
- `0x180071114`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180071329`
- `ntoskrnl!ZwClose` at `0x180071329`
- `ntoskrnl!KeInitializeEvent` at `0x18007121d`
- `ntoskrnl!KeInitializeEvent` at `0x18007121d`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180071170`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180071229`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180071170`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180071229`
- `ntoskrnl!PsCreateSystemThread` at `0x180071298`
- `ntoskrnl!PsCreateSystemThread` at `0x180071298`

## string_xrefs

- `0x1800711bb`: `RegKeyNotificationsInitialize:: pCngConfigContext == nullptr`
- `0x1800712e3`: `RegKeyNotificationsInitialize:: PsCreateSystemThread failed`
- `0x1800712b2`: `RegKeyNotificationsInitialize:: PsCreateSystemThread failed. ntStatus: %ld`

## pseudocode

```c
__int64 __fastcall RegKeyNotificationsInitialize(PVOID StartContext, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 CurrentServerSilo; // rax
  int v6; // r8d
  int v7; // r9d
  const char *v8; // rcx
  unsigned int v9; // ebx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  struct _KEVENT *v15; // rax
  NTSTATUS v16; // eax
  int v17; // eax
  wchar_t *v18; // rcx
  __int64 v19; // rax
  void *v20; // rcx
  PVOID StartContexta; // [rsp+30h] [rbp-D0h]
  void *ThreadHandle; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  const char *v25; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[1024]; // [rsp+90h] [rbp-70h] BYREF

  if ( (unsigned int)dword_1800CB588 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800CB588, 0x200000000000LL) )
  {
    v24 = 0x1000000;
    CurrentServerSilo = PsGetCurrentServerSilo();
    v8 = "Container";
    if ( !CurrentServerSilo )
      v8 = "Host";
    v25 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v8,
      (unsigned int)&unk_1800C3148,
      v6,
      v7,
      (__int64)&v25,
      (__int64)&v24);
  }
  if ( StartContext )
  {
    v10 = (_QWORD *)MSCryptAlloc(96, a2, a3, a4);
    *((_QWORD *)StartContext + 53) = v10;
    v11 = v10;
    if ( v10 && (memset(v10, 0, 0x60u), v15 = (struct _KEVENT *)MSCryptAlloc(24, v12, v13, v14), (v11[1] = v15) != 0) )
    {
      KeInitializeEvent(v15, NotificationEvent, 0);
      v11[11] = PsGetCurrentServerSilo();
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 512;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ThreadHandle = 0;
      v16 = PsCreateSystemThread(
              &ThreadHandle,
              0,
              &ObjectAttributes,
              0,
              0,
              (PKSTART_ROUTINE)ConfigRegChangeWatch,
              StartContext);
      v9 = v16;
      if ( v16 >= 0 )
      {
        ZwClose(ThreadHandle);
        return v9;
      }
      LODWORD(StartContexta) = v16;
      v17 = StringCchPrintfExW(
              pszDest,
              0x400u,
              0,
              0,
              0,
              L"RegKeyNotificationsInitialize:: PsCreateSystemThread failed. ntStatus: %ld",
              StartContexta);
      if ( (int)(v17 + 0x80000000) < 0
        || (v18 = L"RegKeyNotificationsInitialize:: PsCreateSystemThread failed", v17 == -2147024774) )
      {
        v18 = pszDest;
      }
      SendTelemetry(v18);
      v9 = 0;
    }
    else
    {
      v9 = -1073741801;
    }
    v19 = *((_QWORD *)StartContext + 53);
    if ( v19 )
    {
      v20 = *(void **)(v19 + 8);
      if ( v20 )
        MSCryptFree(v20);
      MSCryptFree(*((PVOID *)StartContext + 53));
    }
  }
  else
  {
    SendTelemetry(L"RegKeyNotificationsInitialize:: pCngConfigContext == nullptr");
    return (unsigned int)-1073741816;
  }
  return v9;
}

```

## disassembly

```asm
0x180071114  mov     [rsp-8+arg_8], rbx
0x180071119  mov     [rsp-8+arg_10], rdi
0x18007111e  push    rbp
0x18007111f  lea     rbp, [rsp-7A0h]
0x180071127  sub     rsp, 8A0h
0x18007112e  mov     rax, cs:__security_cookie
0x180071135  xor     rax, rsp
0x180071138  mov     [rbp+7A0h+var_10], rax
0x18007113f  mov     eax, cs:dword_1800CB588
0x180071145  mov     rdi, rcx
0x180071148  cmp     eax, 5
0x18007114b  jbe     short loc_1800711B6
0x18007114d  mov     rdx, 200000000000h
0x180071157  lea     rcx, dword_1800CB588
0x18007115e  call    _tlgKeywordOn
0x180071163  test    al, al
0x180071165  jz      short loc_1800711B6
0x180071167  mov     [rsp+8A0h+var_858], 1000000h
0x180071170  call    cs:__imp_PsGetCurrentServerSilo
0x180071177  nop     dword ptr [rax+rax+00h]
0x18007117c  test    rax, rax
0x18007117f  lea     rdx, aHost; "Host"
0x180071186  lea     rax, [rsp+8A0h+var_858]
0x18007118b  mov     [rsp+8A0h+StartRoutine], rax
0x180071190  lea     rcx, aContainer; "Container"
0x180071197  cmovz   rcx, rdx
0x18007119b  lea     rax, [rsp+8A0h+var_850]
0x1800711a0  lea     rdx, unk_1800C3148
0x1800711a7  mov     [rsp+8A0h+ClientId], rax
0x1800711ac  mov     [rsp+8A0h+var_850], rcx
0x1800711b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800711b6  test    rdi, rdi
0x1800711b9  jnz     short loc_1800711D1
0x1800711bb  lea     rcx, aRegkeynotifica_1; "RegKeyNotificationsInitialize:: pCngCon"...
0x1800711c2  call    SendTelemetry
0x1800711c7  mov     ebx, 0C0000008h
0x1800711cc  jmp     loc_180071335
0x1800711d1  mov     ecx, 60h ; '`'
0x1800711d6  call    MSCryptAlloc
0x1800711db  mov     [rdi+1A8h], rax
0x1800711e2  mov     rbx, rax
0x1800711e5  test    rax, rax
0x1800711e8  jnz     short loc_1800711F4
0x1800711ea  mov     ebx, 0C0000017h
0x1800711ef  jmp     loc_1800712FC
0x1800711f4  xor     edx, edx; Val
0x1800711f6  mov     rcx, rbx; void *
0x1800711f9  lea     r8d, [rdx+60h]; Size
0x1800711fd  call    memset
0x180071202  mov     ecx, 18h
0x180071207  call    MSCryptAlloc
0x18007120c  mov     [rbx+8], rax
0x180071210  test    rax, rax
0x180071213  jz      short loc_1800711EA
0x180071215  xor     r8d, r8d; State
0x180071218  xor     edx, edx; Type
0x18007121a  mov     rcx, rax; Event
0x18007121d  call    cs:__imp_KeInitializeEvent
0x180071224  nop     dword ptr [rax+rax+00h]
0x180071229  call    cs:__imp_PsGetCurrentServerSilo
0x180071230  nop     dword ptr [rax+rax+00h]
0x180071235  xorps   xmm0, xmm0
0x180071238  mov     [rsp+8A0h+StartContext], rdi; StartContext
0x18007123d  mov     [rbx+58h], rax
0x180071241  lea     r8, [rsp+8A0h+ObjectAttributes]; ObjectAttributes
0x180071246  lea     rax, ConfigRegChangeWatch
0x18007124d  mov     qword ptr [rsp+8A0h+ObjectAttributes.Length], 30h ; '0'
0x180071256  mov     [rsp+8A0h+StartRoutine], rax; StartRoutine
0x18007125b  lea     rcx, [rsp+8A0h+ThreadHandle]; ThreadHandle
0x180071260  xor     r9d, r9d; ProcessHandle
0x180071263  mov     [rsp+8A0h+ClientId], 0; ClientId
0x18007126c  xor     edx, edx; DesiredAccess
0x18007126e  mov     qword ptr [rsp+8A0h+ObjectAttributes.Attributes], 200h
0x180071277  mov     [rsp+8A0h+ObjectAttributes.RootDirectory], 0
0x180071280  mov     [rsp+8A0h+ObjectAttributes.ObjectName], 0
0x180071289  movdqu  xmmword ptr [rsp+8A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007128f  mov     [rsp+8A0h+ThreadHandle], 0
0x180071298  call    cs:__imp_PsCreateSystemThread
0x18007129f  nop     dword ptr [rax+rax+00h]
0x1800712a4  mov     ebx, eax
0x1800712a6  test    eax, eax
0x1800712a8  jns     short loc_180071324
0x1800712aa  mov     dword ptr [rsp+8A0h+StartContext], eax
0x1800712ae  lea     rcx, [rbp+7A0h+pszDest]; pszDest
0x1800712b2  lea     rax, aRegkeynotifica; "RegKeyNotificationsInitialize:: PsCreat"...
0x1800712b9  xor     r9d, r9d; unsigned __int64 *
0x1800712bc  mov     [rsp+8A0h+StartRoutine], rax; unsigned __int16 *
0x1800712c1  xor     r8d, r8d; unsigned __int16 **
0x1800712c4  mov     edx, 400h; unsigned __int64
0x1800712c9  mov     [rsp+8A0h+ClientId], 0; unsigned int
0x1800712d2  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800712d7  mov     edx, 80000000h
0x1800712dc  lea     ecx, [rax+rdx]
0x1800712df  test    edx, ecx
0x1800712e1  jnz     short loc_1800712F1
0x1800712e3  lea     rcx, aRegkeynotifica_0; "RegKeyNotificationsInitialize:: PsCreat"...
0x1800712ea  cmp     eax, 8007007Ah
0x1800712ef  jnz     short loc_1800712F5
0x1800712f1  lea     rcx, [rbp+7A0h+pszDest]
0x1800712f5  call    SendTelemetry
0x1800712fa  xor     ebx, ebx
0x1800712fc  mov     rax, [rdi+1A8h]
0x180071303  test    rax, rax
0x180071306  jz      short loc_180071335
0x180071308  mov     rcx, [rax+8]; P
0x18007130c  test    rcx, rcx
0x18007130f  jz      short loc_180071316
0x180071311  call    MSCryptFree
0x180071316  mov     rcx, [rdi+1A8h]; P
0x18007131d  call    MSCryptFree
0x180071322  jmp     short loc_180071335
0x180071324  mov     rcx, [rsp+8A0h+ThreadHandle]; Handle
0x180071329  call    cs:__imp_ZwClose
0x180071330  nop     dword ptr [rax+rax+00h]
0x180071335  mov     eax, ebx
0x180071337  mov     rcx, [rbp+7A0h+var_10]
0x18007133e  xor     rcx, rsp; StackCookie
0x180071341  call    __security_check_cookie
0x180071346  lea     r11, [rsp+8A0h+var_s0]
0x18007134e  mov     rbx, [r11+18h]
0x180071352  mov     rdi, [r11+20h]
0x180071356  mov     rsp, r11
0x180071359  pop     rbp
0x18007135a  retn
```
