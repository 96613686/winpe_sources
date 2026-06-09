# RegKeyNotificationsInitialize

- ea: `0x180070714`
- end: `0x18007095c`
- name: `RegKeyNotificationsInitialize`
- size: `584`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006c688`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180043398`
- `0x1800451f0`
- `0x180046c44`
- `0x180047eb4`
- `0x180070714`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180070929`
- `ntoskrnl!ZwClose` at `0x180070929`
- `ntoskrnl!KeInitializeEvent` at `0x18007081d`
- `ntoskrnl!KeInitializeEvent` at `0x18007081d`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180070770`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180070829`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180070770`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180070829`
- `ntoskrnl!PsCreateSystemThread` at `0x180070898`
- `ntoskrnl!PsCreateSystemThread` at `0x180070898`

## string_xrefs

- `0x1800707bb`: `RegKeyNotificationsInitialize:: pCngConfigContext == nullptr`
- `0x1800708e3`: `RegKeyNotificationsInitialize:: PsCreateSystemThread failed`
- `0x1800708b2`: `RegKeyNotificationsInitialize:: PsCreateSystemThread failed. ntStatus: %ld`

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

  if ( (unsigned int)dword_1800C9588 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C9588, 0x200000000000LL) )
  {
    v20 = 0x1000000;
    CurrentServerSilo = PsGetCurrentServerSilo();
    v6 = "Container";
    if ( !CurrentServerSilo )
      v6 = "Host";
    v21 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v6,
      (unsigned int)&unk_1800C0B48,
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
0x180070714  mov     [rsp-8+arg_8], rbx
0x180070719  mov     [rsp-8+arg_10], rdi
0x18007071e  push    rbp
0x18007071f  lea     rbp, [rsp-7A0h]
0x180070727  sub     rsp, 8A0h
0x18007072e  mov     rax, cs:__security_cookie
0x180070735  xor     rax, rsp
0x180070738  mov     [rbp+7A0h+var_10], rax
0x18007073f  mov     eax, cs:dword_1800C9588
0x180070745  mov     rdi, rcx
0x180070748  cmp     eax, 5
0x18007074b  jbe     short loc_1800707B6
0x18007074d  mov     rdx, 200000000000h
0x180070757  lea     rcx, dword_1800C9588
0x18007075e  call    _tlgKeywordOn
0x180070763  test    al, al
0x180070765  jz      short loc_1800707B6
0x180070767  mov     [rsp+8A0h+var_858], 1000000h
0x180070770  call    cs:__imp_PsGetCurrentServerSilo
0x180070777  nop     dword ptr [rax+rax+00h]
0x18007077c  test    rax, rax
0x18007077f  lea     rdx, aHost; "Host"
0x180070786  lea     rax, [rsp+8A0h+var_858]
0x18007078b  mov     [rsp+8A0h+StartRoutine], rax
0x180070790  lea     rcx, aContainer; "Container"
0x180070797  cmovz   rcx, rdx
0x18007079b  lea     rax, [rsp+8A0h+var_850]
0x1800707a0  lea     rdx, unk_1800C0B48
0x1800707a7  mov     [rsp+8A0h+ClientId], rax
0x1800707ac  mov     [rsp+8A0h+var_850], rcx
0x1800707b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800707b6  test    rdi, rdi
0x1800707b9  jnz     short loc_1800707D1
0x1800707bb  lea     rcx, aRegkeynotifica_1; "RegKeyNotificationsInitialize:: pCngCon"...
0x1800707c2  call    SendTelemetry
0x1800707c7  mov     ebx, 0C0000008h
0x1800707cc  jmp     loc_180070935
0x1800707d1  mov     ecx, 60h ; '`'
0x1800707d6  call    MSCryptAlloc
0x1800707db  mov     [rdi+1A8h], rax
0x1800707e2  mov     rbx, rax
0x1800707e5  test    rax, rax
0x1800707e8  jnz     short loc_1800707F4
0x1800707ea  mov     ebx, 0C0000017h
0x1800707ef  jmp     loc_1800708FC
0x1800707f4  xor     edx, edx; Val
0x1800707f6  mov     rcx, rbx; void *
0x1800707f9  lea     r8d, [rdx+60h]; Size
0x1800707fd  call    memset
0x180070802  mov     ecx, 18h
0x180070807  call    MSCryptAlloc
0x18007080c  mov     [rbx+8], rax
0x180070810  test    rax, rax
0x180070813  jz      short loc_1800707EA
0x180070815  xor     r8d, r8d; State
0x180070818  xor     edx, edx; Type
0x18007081a  mov     rcx, rax; Event
0x18007081d  call    cs:__imp_KeInitializeEvent
0x180070824  nop     dword ptr [rax+rax+00h]
0x180070829  call    cs:__imp_PsGetCurrentServerSilo
0x180070830  nop     dword ptr [rax+rax+00h]
0x180070835  xorps   xmm0, xmm0
0x180070838  mov     [rsp+8A0h+StartContext], rdi; StartContext
0x18007083d  mov     [rbx+58h], rax
0x180070841  lea     r8, [rsp+8A0h+ObjectAttributes]; ObjectAttributes
0x180070846  lea     rax, ConfigRegChangeWatch
0x18007084d  mov     qword ptr [rsp+8A0h+ObjectAttributes.Length], 30h ; '0'
0x180070856  mov     [rsp+8A0h+StartRoutine], rax; StartRoutine
0x18007085b  lea     rcx, [rsp+8A0h+ThreadHandle]; ThreadHandle
0x180070860  xor     r9d, r9d; ProcessHandle
0x180070863  mov     [rsp+8A0h+ClientId], 0; ClientId
0x18007086c  xor     edx, edx; DesiredAccess
0x18007086e  mov     qword ptr [rsp+8A0h+ObjectAttributes.Attributes], 200h
0x180070877  mov     [rsp+8A0h+ObjectAttributes.RootDirectory], 0
0x180070880  mov     [rsp+8A0h+ObjectAttributes.ObjectName], 0
0x180070889  movdqu  xmmword ptr [rsp+8A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007088f  mov     [rsp+8A0h+ThreadHandle], 0
0x180070898  call    cs:__imp_PsCreateSystemThread
0x18007089f  nop     dword ptr [rax+rax+00h]
0x1800708a4  mov     ebx, eax
0x1800708a6  test    eax, eax
0x1800708a8  jns     short loc_180070924
0x1800708aa  mov     dword ptr [rsp+8A0h+StartContext], eax
0x1800708ae  lea     rcx, [rbp+7A0h+pszDest]; pszDest
0x1800708b2  lea     rax, aRegkeynotifica; "RegKeyNotificationsInitialize:: PsCreat"...
0x1800708b9  xor     r9d, r9d; unsigned __int64 *
0x1800708bc  mov     [rsp+8A0h+StartRoutine], rax; unsigned __int16 *
0x1800708c1  xor     r8d, r8d; unsigned __int16 **
0x1800708c4  mov     edx, 400h; unsigned __int64
0x1800708c9  mov     [rsp+8A0h+ClientId], 0; unsigned int
0x1800708d2  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800708d7  mov     edx, 80000000h
0x1800708dc  lea     ecx, [rax+rdx]
0x1800708df  test    edx, ecx
0x1800708e1  jnz     short loc_1800708F1
0x1800708e3  lea     rcx, aRegkeynotifica_0; "RegKeyNotificationsInitialize:: PsCreat"...
0x1800708ea  cmp     eax, 8007007Ah
0x1800708ef  jnz     short loc_1800708F5
0x1800708f1  lea     rcx, [rbp+7A0h+pszDest]
0x1800708f5  call    SendTelemetry
0x1800708fa  xor     ebx, ebx
0x1800708fc  mov     rax, [rdi+1A8h]
0x180070903  test    rax, rax
0x180070906  jz      short loc_180070935
0x180070908  mov     rcx, [rax+8]; P
0x18007090c  test    rcx, rcx
0x18007090f  jz      short loc_180070916
0x180070911  call    MSCryptFree
0x180070916  mov     rcx, [rdi+1A8h]; P
0x18007091d  call    MSCryptFree
0x180070922  jmp     short loc_180070935
0x180070924  mov     rcx, [rsp+8A0h+ThreadHandle]; Handle
0x180070929  call    cs:__imp_ZwClose
0x180070930  nop     dword ptr [rax+rax+00h]
0x180070935  mov     eax, ebx
0x180070937  mov     rcx, [rbp+7A0h+var_10]
0x18007093e  xor     rcx, rsp; StackCookie
0x180070941  call    __security_check_cookie
0x180070946  lea     r11, [rsp+8A0h+var_s0]
0x18007094e  mov     rbx, [r11+18h]
0x180070952  mov     rdi, [r11+20h]
0x180070956  mov     rsp, r11
0x180070959  pop     rbp
0x18007095a  retn
```
