# RdsDWMDirectSharedMemory::CreateFileMappingW(ulong,void * *)

- ea: `0x1800088c0`
- end: `0x180008a54`
- name: `?CreateFileMappingW@RdsDWMDirectSharedMemory@@UEAAJKPEAPEAX@Z`
- size: `404`
- prototype: `__int64 __fastcall(const WCHAR *this, DWORD dwMaximumSizeLow, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x180001724`
- `0x180007b44`
- `0x1800088c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088fe`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800088ec`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800088ec`

## string_xrefs

- `0x180008922`: `Failed to create the file mapping`
- `0x18000893b`: `CreateFileMappingW`
- `0x1800089d5`: `CreateFileMappingW`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectSharedMemory::CreateFileMappingW(const WCHAR *this, DWORD dwMaximumSizeLow, void **a3)
{
  HANDLE FileMappingW; // rax
  RdsDWMDirectSharedMemory *v5; // rcx
  void *v6; // rdi
  signed int LastError; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // r8d
  int v14; // r9d
  const char *v16; // [rsp+50h] [rbp-20h] BYREF
  const char *v17; // [rsp+58h] [rbp-18h] BYREF
  const char *v18; // [rsp+60h] [rbp-10h] BYREF
  const char *v19; // [rsp+68h] [rbp-8h] BYREF
  int v20; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v21; // [rsp+A8h] [rbp+38h] BYREF

  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, dwMaximumSizeLow, this + 4);
  v6 = FileMappingW;
  if ( FileMappingW )
  {
    v12 = RdsDWMDirectSharedMemory::AddTermsrvACEToSectionObject(v5, FileMappingW);
    v11 = v12;
    if ( v12 >= 0 )
    {
      *a3 = v6;
    }
    else
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v20 = 135;
        v19 = "Failed to add the termsrv ACE to the section object";
        v21 = v12;
        v18 = "CreateFileMappingW";
        v17 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
        v16 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          dword_180044008,
          (unsigned int)byte_180038B11,
          v13,
          v14,
          (__int64)&v16,
          (__int64)&v21,
          (__int64)&v17,
          (__int64)&v20,
          (__int64)&v18,
          (__int64)&v19);
      }
      CloseHandle(v6);
    }
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v20 = 132;
      v16 = "Failed to create the file mapping";
      v21 = v11;
      v17 = "CreateFileMappingW";
      v18 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
      v19 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v8,
        (unsigned int)&word_180038B66,
        v9,
        v10,
        (__int64)&v19,
        (__int64)&v21,
        (__int64)&v18,
        (__int64)&v20,
        (__int64)&v17,
        (__int64)&v16);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1800088c0  mov     [rsp-18h+arg_8], rbx
0x1800088c5  push    rbp
0x1800088c6  push    rsi
0x1800088c7  push    rdi
0x1800088c8  mov     rbp, rsp
0x1800088cb  sub     rsp, 70h
0x1800088cf  lea     rax, [rcx+8]
0x1800088d3  xor     r9d, r9d; dwMaximumSizeHigh
0x1800088d6  mov     [rsp+70h+lpName], rax; lpName
0x1800088db  mov     rsi, r8
0x1800088de  mov     [rsp+70h+dwMaximumSizeLow], edx; dwMaximumSizeLow
0x1800088e2  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800088e6  xor     edx, edx; lpFileMappingAttributes
0x1800088e8  lea     r8d, [r9+4]; flProtect
0x1800088ec  call    cs:__imp_CreateFileMappingW
0x1800088f2  mov     rdi, rax
0x1800088f5  test    rax, rax
0x1800088f8  jnz     loc_18000899F
0x1800088fe  call    cs:__imp_GetLastError
0x180008904  mov     ebx, eax
0x180008906  test    eax, eax
0x180008908  jle     short loc_180008913
0x18000890a  movzx   ebx, ax
0x18000890d  or      ebx, 80070000h
0x180008913  mov     eax, cs:dword_180044008
0x180008919  cmp     eax, 2
0x18000891c  jbe     loc_180008A42
0x180008922  lea     rax, aFailedToCreate_0; "Failed to create the file mapping"
0x180008929  mov     [rbp+arg_0], 84h
0x180008930  mov     [rbp+var_20], rax
0x180008934  lea     rdx, word_180038B66
0x18000893b  lea     rax, aCreatefilemapp; "CreateFileMappingW"
0x180008942  mov     [rbp+arg_18], ebx
0x180008945  mov     [rbp+var_18], rax
0x180008949  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180008950  mov     [rbp+var_10], rax
0x180008954  lea     rax, aErrorCondition; "Error condition failed"
0x18000895b  mov     [rbp+var_8], rax
0x18000895f  lea     rax, [rbp+var_20]
0x180008963  mov     [rsp+70h+var_28], rax
0x180008968  lea     rax, [rbp+var_18]
0x18000896c  mov     [rsp+70h+var_30], rax
0x180008971  lea     rax, [rbp+arg_0]
0x180008975  mov     [rsp+70h+var_38], rax
0x18000897a  lea     rax, [rbp+var_10]
0x18000897e  mov     [rsp+70h+var_40], rax
0x180008983  lea     rax, [rbp+arg_18]
0x180008987  mov     [rsp+70h+lpName], rax
0x18000898c  lea     rax, [rbp+var_8]
0x180008990  mov     qword ptr [rsp+70h+dwMaximumSizeLow], rax
0x180008995  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000899a  jmp     loc_180008A42
0x18000899f  mov     rdx, rdi; void *
0x1800089a2  call    ?AddTermsrvACEToSectionObject@RdsDWMDirectSharedMemory@@AEAAJPEAX@Z; RdsDWMDirectSharedMemory::AddTermsrvACEToSectionObject(void *)
0x1800089a7  mov     ebx, eax
0x1800089a9  test    eax, eax
0x1800089ab  jns     loc_180008A3F
0x1800089b1  mov     ecx, cs:dword_180044008
0x1800089b7  cmp     ecx, 2
0x1800089ba  jbe     short loc_180008A34
0x1800089bc  lea     rax, aFailedToAddThe; "Failed to add the termsrv ACE to the se"...
0x1800089c3  mov     [rbp+arg_0], 87h
0x1800089ca  mov     [rbp+var_8], rax
0x1800089ce  lea     rdx, byte_180038B11
0x1800089d5  lea     rax, aCreatefilemapp; "CreateFileMappingW"
0x1800089dc  mov     [rbp+arg_18], ebx
0x1800089df  mov     [rbp+var_10], rax
0x1800089e3  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x1800089ea  mov     [rbp+var_18], rax
0x1800089ee  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800089f5  mov     [rbp+var_20], rax
0x1800089f9  lea     rax, [rbp+var_8]
0x1800089fd  mov     [rsp+70h+var_28], rax
0x180008a02  lea     rax, [rbp+var_10]
0x180008a06  mov     [rsp+70h+var_30], rax
0x180008a0b  lea     rax, [rbp+arg_0]
0x180008a0f  mov     [rsp+70h+var_38], rax
0x180008a14  lea     rax, [rbp+var_18]
0x180008a18  mov     [rsp+70h+var_40], rax
0x180008a1d  lea     rax, [rbp+arg_18]
0x180008a21  mov     [rsp+70h+lpName], rax
0x180008a26  lea     rax, [rbp+var_20]
0x180008a2a  mov     qword ptr [rsp+70h+dwMaximumSizeLow], rax
0x180008a2f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180008a34  mov     rcx, rdi; hObject
0x180008a37  call    cs:__imp_CloseHandle
0x180008a3d  jmp     short loc_180008A42
0x180008a3f  mov     [rsi], rdi
0x180008a42  mov     eax, ebx
0x180008a44  mov     rbx, [rsp+70h+arg_8]
0x180008a4c  add     rsp, 70h
0x180008a50  pop     rdi
0x180008a51  pop     rsi
0x180008a52  pop     rbp
0x180008a53  retn
```
