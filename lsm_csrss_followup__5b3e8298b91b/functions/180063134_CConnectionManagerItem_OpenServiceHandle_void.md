# CConnectionManagerItem::OpenServiceHandle(void)

- ea: `0x180063134`
- end: `0x180063253`
- name: `?OpenServiceHandle@CConnectionManagerItem@@QEAAJXZ`
- size: `287`
- prototype: `__int64 __fastcall(CConnectionManagerItem *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001df60`

## callees

- `0x1800074c0`
- `0x180025070`
- `0x180063134`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006315e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006315e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631ff`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800631ed`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800631ed`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180063150`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180063150`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006323b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006323b`

## string_xrefs

- `0x180063177`: `CConnectionManagerItem::OpenServiceHandle`
- `0x180063218`: `CConnectionManagerItem::OpenServiceHandle`
- `0x180063181`: `OpenSCManager failed: 0x%x in %s`
- `0x1800631b2`: `Service name is empty, can't open to service handle, returning E_FAIL`
- `0x180063222`: `OpenService failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CConnectionManagerItem::OpenServiceHandle(CConnectionManagerItem *this)
{
  signed int v2; // ebx
  int v3; // ecx
  SC_HANDLE v4; // rdi
  int v5; // r8d
  int v6; // r9d
  signed int LastError; // eax
  const WCHAR *v8; // rdx
  SC_HANDLE v9; // rax
  signed int v10; // eax
  const char *v12; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v4 = OpenSCManagerW(0, 0, 1u);
  if ( v4 )
    goto LABEL_21;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_21:
    if ( *((_QWORD *)this + 3) )
    {
      v8 = (const WCHAR *)((char *)this + 8);
      if ( *((_QWORD *)this + 4) > 7u )
        v8 = *(const WCHAR **)v8;
      v9 = OpenServiceW(v4, v8, 4u);
      *((_QWORD *)this + 20) = v9;
      if ( !v9 )
      {
        v10 = GetLastError();
        v2 = v10;
        if ( v10 > 0 )
          v2 = (unsigned __int16)v10 | 0x80070000;
        if ( v2 < 0 )
          _DbgPrintMessage(8, "OpenService failed: 0x%x in %s", v2, "CConnectionManagerItem::OpenServiceHandle");
      }
    }
    else
    {
      v2 = -2147467259;
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        v12 = "Service name is empty, can't open to service handle, returning E_FAIL";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v3,
          (unsigned int)&word_1800C316E,
          v5,
          v6,
          (__int64)&v12);
      }
    }
    if ( v4 )
      CloseServiceHandle(v4);
  }
  else
  {
    _DbgPrintMessage(8, "OpenSCManager failed: 0x%x in %s", v2, "CConnectionManagerItem::OpenServiceHandle");
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180063134  mov     [rsp+arg_0], rbx
0x180063139  mov     [rsp+arg_10], rsi
0x18006313e  push    rdi
0x18006313f  sub     rsp, 30h
0x180063143  mov     rsi, rcx
0x180063146  xor     ebx, ebx
0x180063148  xor     edx, edx; lpDatabaseName
0x18006314a  xor     ecx, ecx; lpMachineName
0x18006314c  lea     r8d, [rbx+1]; dwDesiredAccess
0x180063150  call    cs:__imp_OpenSCManagerW
0x180063156  mov     rdi, rax
0x180063159  test    rax, rax
0x18006315c  jnz     short loc_180063197
0x18006315e  call    cs:__imp_GetLastError
0x180063164  mov     ebx, eax
0x180063166  test    eax, eax
0x180063168  jle     short loc_180063173
0x18006316a  movzx   ebx, ax
0x18006316d  or      ebx, 80070000h
0x180063173  test    ebx, ebx
0x180063175  jns     short loc_180063197
0x180063177  lea     r9, aCconnectionman; "CConnectionManagerItem::OpenServiceHand"...
0x18006317e  mov     r8d, ebx
0x180063181  lea     rdx, aOpenscmanagerF; "OpenSCManager failed: 0x%x in %s"
0x180063188  mov     ecx, 8; int
0x18006318d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180063192  jmp     loc_180063241
0x180063197  cmp     qword ptr [rsi+18h], 0
0x18006319c  jnz     short loc_1800631D6
0x18006319e  mov     eax, cs:dword_1800DA020
0x1800631a4  mov     ebx, 80004005h
0x1800631a9  cmp     eax, 2
0x1800631ac  jbe     loc_180063233
0x1800631b2  lea     rax, aServiceNameIsE; "Service name is empty, can't open to se"...
0x1800631b9  mov     [rsp+38h+arg_8], rax
0x1800631be  lea     rdx, word_1800C316E
0x1800631c5  lea     rax, [rsp+38h+arg_8]
0x1800631ca  mov     [rsp+38h+var_18], rax
0x1800631cf  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800631d4  jmp     short loc_180063233
0x1800631d6  lea     rdx, [rsi+8]
0x1800631da  cmp     qword ptr [rdx+18h], 7
0x1800631df  jbe     short loc_1800631E4
0x1800631e1  mov     rdx, [rdx]; lpServiceName
0x1800631e4  mov     r8d, 4; dwDesiredAccess
0x1800631ea  mov     rcx, rdi; hSCManager
0x1800631ed  call    cs:__imp_OpenServiceW
0x1800631f3  mov     [rsi+0A0h], rax
0x1800631fa  test    rax, rax
0x1800631fd  jnz     short loc_180063233
0x1800631ff  call    cs:__imp_GetLastError
0x180063205  mov     ebx, eax
0x180063207  test    eax, eax
0x180063209  jle     short loc_180063214
0x18006320b  movzx   ebx, ax
0x18006320e  or      ebx, 80070000h
0x180063214  test    ebx, ebx
0x180063216  jns     short loc_180063233
0x180063218  lea     r9, aCconnectionman; "CConnectionManagerItem::OpenServiceHand"...
0x18006321f  mov     r8d, ebx
0x180063222  lea     rdx, aOpenserviceFai; "OpenService failed: 0x%x in %s"
0x180063229  mov     ecx, 8; int
0x18006322e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180063233  test    rdi, rdi
0x180063236  jz      short loc_180063241
0x180063238  mov     rcx, rdi; hSCObject
0x18006323b  call    cs:__imp_CloseServiceHandle
0x180063241  mov     rsi, [rsp+38h+arg_10]
0x180063246  mov     eax, ebx
0x180063248  mov     rbx, [rsp+38h+arg_0]
0x18006324d  add     rsp, 30h
0x180063251  pop     rdi
0x180063252  retn
```
