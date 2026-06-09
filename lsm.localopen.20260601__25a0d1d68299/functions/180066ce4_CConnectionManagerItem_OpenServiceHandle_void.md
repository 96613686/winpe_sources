# CConnectionManagerItem::OpenServiceHandle(void)

- ea: `0x180066ce4`
- end: `0x180066e22`
- name: `?OpenServiceHandle@CConnectionManagerItem@@QEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(CConnectionManagerItem *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001f6a8`

## callees

- `0x1800077a0`
- `0x18002701c`
- `0x180066ce4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066dc1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180066da9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180066da9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180066d00`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180066d00`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180066e03`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180066e03`

## string_xrefs

- `0x180066d33`: `CConnectionManagerItem::OpenServiceHandle`
- `0x180066de0`: `CConnectionManagerItem::OpenServiceHandle`
- `0x180066d3d`: `OpenSCManager failed: 0x%x in %s`
- `0x180066d6e`: `Service name is empty, can't open to service handle, returning E_FAIL`
- `0x180066dea`: `OpenService failed: 0x%x in %s`

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
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        v12 = "Service name is empty, can't open to service handle, returning E_FAIL";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v3,
          (unsigned int)&word_1800C82F6,
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
0x180066ce4  mov     [rsp+arg_0], rbx
0x180066ce9  mov     [rsp+arg_10], rsi
0x180066cee  push    rdi
0x180066cef  sub     rsp, 30h
0x180066cf3  mov     rsi, rcx
0x180066cf6  xor     ebx, ebx
0x180066cf8  xor     edx, edx; lpDatabaseName
0x180066cfa  xor     ecx, ecx; lpMachineName
0x180066cfc  lea     r8d, [rbx+1]; dwDesiredAccess
0x180066d00  call    cs:__imp_OpenSCManagerW
0x180066d07  nop     dword ptr [rax+rax+00h]
0x180066d0c  mov     rdi, rax
0x180066d0f  test    rax, rax
0x180066d12  jnz     short loc_180066D53
0x180066d14  call    cs:__imp_GetLastError
0x180066d1b  nop     dword ptr [rax+rax+00h]
0x180066d20  mov     ebx, eax
0x180066d22  test    eax, eax
0x180066d24  jle     short loc_180066D2F
0x180066d26  movzx   ebx, ax
0x180066d29  or      ebx, 80070000h
0x180066d2f  test    ebx, ebx
0x180066d31  jns     short loc_180066D53
0x180066d33  lea     r9, aCconnectionman; "CConnectionManagerItem::OpenServiceHand"...
0x180066d3a  mov     r8d, ebx
0x180066d3d  lea     rdx, aOpenscmanagerF; "OpenSCManager failed: 0x%x in %s"
0x180066d44  mov     ecx, 8; int
0x180066d49  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180066d4e  jmp     loc_180066E0F
0x180066d53  cmp     qword ptr [rsi+18h], 0
0x180066d58  jnz     short loc_180066D92
0x180066d5a  mov     eax, cs:dword_1800DF020
0x180066d60  mov     ebx, 80004005h
0x180066d65  cmp     eax, 2
0x180066d68  jbe     loc_180066DFB
0x180066d6e  lea     rax, aServiceNameIsE; "Service name is empty, can't open to se"...
0x180066d75  mov     [rsp+38h+arg_8], rax
0x180066d7a  lea     rdx, word_1800C82F6
0x180066d81  lea     rax, [rsp+38h+arg_8]
0x180066d86  mov     [rsp+38h+var_18], rax
0x180066d8b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180066d90  jmp     short loc_180066DFB
0x180066d92  lea     rdx, [rsi+8]
0x180066d96  cmp     qword ptr [rdx+18h], 7
0x180066d9b  jbe     short loc_180066DA0
0x180066d9d  mov     rdx, [rdx]; lpServiceName
0x180066da0  mov     r8d, 4; dwDesiredAccess
0x180066da6  mov     rcx, rdi; hSCManager
0x180066da9  call    cs:__imp_OpenServiceW
0x180066db0  nop     dword ptr [rax+rax+00h]
0x180066db5  mov     [rsi+0A0h], rax
0x180066dbc  test    rax, rax
0x180066dbf  jnz     short loc_180066DFB
0x180066dc1  call    cs:__imp_GetLastError
0x180066dc8  nop     dword ptr [rax+rax+00h]
0x180066dcd  mov     ebx, eax
0x180066dcf  test    eax, eax
0x180066dd1  jle     short loc_180066DDC
0x180066dd3  movzx   ebx, ax
0x180066dd6  or      ebx, 80070000h
0x180066ddc  test    ebx, ebx
0x180066dde  jns     short loc_180066DFB
0x180066de0  lea     r9, aCconnectionman; "CConnectionManagerItem::OpenServiceHand"...
0x180066de7  mov     r8d, ebx
0x180066dea  lea     rdx, aOpenserviceFai; "OpenService failed: 0x%x in %s"
0x180066df1  mov     ecx, 8; int
0x180066df6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180066dfb  test    rdi, rdi
0x180066dfe  jz      short loc_180066E0F
0x180066e00  mov     rcx, rdi; hSCObject
0x180066e03  call    cs:__imp_CloseServiceHandle
0x180066e0a  nop     dword ptr [rax+rax+00h]
0x180066e0f  mov     rsi, [rsp+38h+arg_10]
0x180066e14  mov     eax, ebx
0x180066e16  mov     rbx, [rsp+38h+arg_0]
0x180066e1b  add     rsp, 30h
0x180066e1f  pop     rdi
0x180066e20  retn
```
