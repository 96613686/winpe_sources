# RdsDWMDirectDriverIO::GetDxgkAdapter(ushort const *)

- ea: `0x180008fa4`
- end: `0x1800095a7`
- name: `?GetDxgkAdapter@RdsDWMDirectDriverIO@@IEAAHPEBG@Z`
- size: `1539`
- prototype: `__int64 __fastcall(RdsDWMDirectDriverIO *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000a140`
- `0x18000bdbc`

## callees

- `0x180001724`
- `0x180008fa4`
- `0x18000c4ec`
- `0x18002b93a`
- `0x18002b960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009414`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009414`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009278`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009278`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000926a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000926a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009208`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000942d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000942d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800093b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800093b5`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180008ff0`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180008ff0`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800090ca`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800090ca`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180009576`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180009576`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800091cd`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180009246`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800091cd`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180009246`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800091a0`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800092ab`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800091a0`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800092ab`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18000925b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18000925b`

## string_xrefs

- `0x180009030`: `DevObjCreateDeviceInfoList`
- `0x18000936c`: `Failed to copy graphics adapter device name`
- `0x1800093f3`: `Fail to open instance of RDPIDD`
- `0x180009455`: `Fail to create overlapped event`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::GetDxgkAdapter(RdsDWMDirectDriverIO *this, const unsigned __int16 *a2)
{
  unsigned int v3; // r14d
  __int64 DeviceInfoList; // rdi
  signed int LastError; // eax
  int v6; // r8d
  int v7; // r9d
  signed int v8; // ecx
  signed int v9; // eax
  int v10; // r8d
  int v11; // r9d
  signed int v12; // ecx
  unsigned int v13; // r12d
  signed int v14; // eax
  int v15; // r8d
  int v16; // r9d
  signed int v17; // ecx
  unsigned int v18; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v20; // rax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  WCHAR *v24; // rbx
  HANDLE v25; // rax
  signed int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  const char *v29; // rax
  __int16 *v30; // rdx
  HANDLE FileW; // rax
  signed int v32; // eax
  HANDLE EventW; // rax
  signed int v34; // eax
  HANDLE v35; // rax
  int v37; // [rsp+50h] [rbp-29h] BYREF
  _DWORD dwBytes[3]; // [rsp+54h] [rbp-25h] BYREF
  const char *v39; // [rsp+60h] [rbp-19h] BYREF
  const char *v40; // [rsp+68h] [rbp-11h] BYREF
  const char *v41; // [rsp+70h] [rbp-9h] BYREF
  const char *v42; // [rsp+78h] [rbp-1h] BYREF
  __int128 v43; // [rsp+80h] [rbp+7h] BYREF
  __int128 v44; // [rsp+90h] [rbp+17h]

  v3 = 0;
  v43 = 0;
  v44 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList != -1 )
    goto LABEL_10;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      dwBytes[0] = 514;
      *(_QWORD *)&dwBytes[1] = "DevObjCreateDeviceInfoList";
      v37 = v8;
      v39 = "GetDxgkAdapter";
      v40 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
      v41 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v8,
        (unsigned int)&dword_180038744,
        v6,
        v7,
        (__int64)&v41,
        (__int64)&v37,
        (__int64)&v40,
        (__int64)dwBytes,
        (__int64)&v39,
        (__int64)&dwBytes[1]);
    }
  }
  else
  {
LABEL_10:
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DISPLAY_DEVICE_ARRIVAL, 0, 18, 0, 0) )
      goto LABEL_13;
    v9 = GetLastError();
    v12 = v9;
    if ( v9 > 0 )
      v12 = (unsigned __int16)v9 | 0x80070000;
    if ( v12 >= 0 )
    {
LABEL_13:
      v43 = 0;
      LODWORD(v43) = 32;
      v44 = 0;
      v13 = 0;
      if ( (unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_DISPLAY_DEVICE_ARRIVAL, 0, &v43) )
      {
        while ( 1 )
        {
          dwBytes[0] = 0;
          DevObjGetDeviceInterfaceDetail(DeviceInfoList, &v43, 0, 0, dwBytes, 0);
          if ( GetLastError() != 122 )
          {
            v14 = GetLastError();
            v17 = v14;
            if ( v14 > 0 )
              v17 = (unsigned __int16)v14 | 0x80070000;
            if ( v17 < 0 )
              break;
          }
          v18 = dwBytes[0];
          ProcessHeap = GetProcessHeap();
          v20 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v18);
          v24 = v20;
          if ( !v20 )
          {
            if ( (unsigned int)dword_180044008 > 2 )
            {
              dwBytes[1] = 567;
              v42 = "DevObjGetDeviceInterfaceDetail";
              v37 = -2147024882;
              v41 = "GetDxgkAdapter";
              v40 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
              v39 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v21,
                (unsigned int)byte_180038645,
                v22,
                v23,
                (__int64)&v39,
                (__int64)&v37,
                (__int64)&v40,
                (__int64)&dwBytes[1],
                (__int64)&v41,
                (__int64)&v42);
            }
            goto LABEL_44;
          }
          memset_0(v20, 0, dwBytes[0]);
          *(_DWORD *)v24 = 8;
          if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, &v43, v24, dwBytes[0], 0, 0)
            && StrStrIW(v24 + 2, L"RdpIdd_IndirectDisplay") )
          {
            v26 = StringCchCopyW((unsigned __int16 *)this + 28, 0x104u, v24 + 2);
            if ( v26 < 0 )
            {
              if ( (unsigned int)dword_180044008 > 2 )
              {
                v29 = "Failed to copy graphics adapter device name";
                dwBytes[1] = 594;
                v30 = (__int16 *)&unk_1800385F0;
                goto LABEL_40;
              }
LABEL_41:
              v35 = GetProcessHeap();
              HeapFree(v35, 0, v24);
              goto LABEL_44;
            }
            v3 = 1;
            FileW = CreateFileW((LPCWSTR)this + 28, 0x10000000u, 3u, 0, 4u, 0x40800080u, 0);
            *((_QWORD *)this + 74) = FileW;
            if ( FileW != (HANDLE)-1LL )
              goto LABEL_34;
            v3 = 0;
            v32 = GetLastError();
            v26 = v32;
            if ( v32 > 0 )
              v26 = (unsigned __int16)v32 | 0x80070000;
            if ( v26 < 0 )
            {
              if ( (unsigned int)dword_180044008 <= 2 )
                goto LABEL_41;
              v29 = "Fail to open instance of RDPIDD";
              dwBytes[1] = 628;
              v30 = (__int16 *)byte_18003859B;
            }
            else
            {
LABEL_34:
              EventW = CreateEventW(0, 0, 0, 0);
              *((_QWORD *)this + 78) = EventW;
              if ( EventW )
                goto LABEL_41;
              v3 = 0;
              v34 = GetLastError();
              v26 = v34;
              if ( v34 > 0 )
                v26 = (unsigned __int16)v34 | 0x80070000;
              if ( v26 >= 0 || (unsigned int)dword_180044008 <= 2 )
                goto LABEL_41;
              v29 = "Fail to create overlapped event";
              dwBytes[1] = 637;
              v30 = &word_180038546;
            }
LABEL_40:
            v42 = v29;
            v41 = "GetDxgkAdapter";
            v40 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
            v39 = "Error HResult failed";
            v37 = v26;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v26,
              (_DWORD)v30,
              v27,
              v28,
              (__int64)&v39,
              (__int64)&v37,
              (__int64)&v40,
              (__int64)&dwBytes[1],
              (__int64)&v41,
              (__int64)&v42);
            goto LABEL_41;
          }
          v25 = GetProcessHeap();
          HeapFree(v25, 0, v24);
          v43 = 0;
          ++v13;
          LODWORD(v43) = 32;
          v44 = 0;
          if ( !(unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_DISPLAY_DEVICE_ARRIVAL, v13, &v43) )
            goto LABEL_44;
        }
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v37 = 557;
          v41 = "DevObjGetDeviceInterfaceDetail";
          dwBytes[1] = v17;
          v40 = "GetDxgkAdapter";
          v39 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
          v42 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v17,
            (unsigned int)word_18003869A,
            v15,
            v16,
            (__int64)&v42,
            (__int64)&dwBytes[1],
            (__int64)&v39,
            (__int64)&v37,
            (__int64)&v40,
            (__int64)&v41);
        }
      }
    }
    else if ( (unsigned int)dword_180044008 > 2 )
    {
      v37 = 529;
      v41 = "DevObjGetClassDevs";
      dwBytes[0] = v12;
      v40 = "GetDxgkAdapter";
      v39 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
      *(_QWORD *)&dwBytes[1] = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v12,
        (unsigned int)&byte_1800386EF,
        v10,
        v11,
        (__int64)&dwBytes[1],
        (__int64)dwBytes,
        (__int64)&v39,
        (__int64)&v37,
        (__int64)&v40,
        (__int64)&v41);
    }
LABEL_44:
    if ( DeviceInfoList != -1 )
      DevObjDestroyDeviceInfoList(DeviceInfoList);
  }
  return v3;
}

```

## disassembly

```asm
0x180008fa4  mov     [rsp-8+arg_8], rbx
0x180008fa9  mov     [rsp-8+arg_10], rsi
0x180008fae  push    rbp
0x180008faf  push    rdi
0x180008fb0  push    r12
0x180008fb2  push    r14
0x180008fb4  push    r15
0x180008fb6  lea     rbp, [rsp-37h]
0x180008fbb  sub     rsp, 0B0h
0x180008fc2  mov     rax, cs:__security_cookie
0x180008fc9  xor     rax, rsp
0x180008fcc  mov     [rbp+57h+var_30], rax
0x180008fd0  xorps   xmm0, xmm0
0x180008fd3  mov     r15, rcx
0x180008fd6  xor     r14d, r14d
0x180008fd9  xor     ecx, ecx
0x180008fdb  xor     r9d, r9d
0x180008fde  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r14
0x180008fe3  xor     r8d, r8d
0x180008fe6  xor     edx, edx
0x180008fe8  movups  [rbp+57h+var_50], xmm0
0x180008fec  movups  [rbp+57h+var_40], xmm0
0x180008ff0  call    cs:__imp_DevObjCreateDeviceInfoList
0x180008ff6  mov     rdi, rax
0x180008ff9  mov     ebx, 80070000h
0x180008ffe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009002  jnz     loc_1800090AD
0x180009008  call    cs:__imp_GetLastError
0x18000900e  mov     ecx, eax
0x180009010  test    eax, eax
0x180009012  jle     short loc_180009019
0x180009014  movzx   ecx, ax
0x180009017  or      ecx, ebx
0x180009019  test    ecx, ecx
0x18000901b  jns     loc_1800090AD
0x180009021  mov     eax, cs:dword_180044008
0x180009027  cmp     eax, 2
0x18000902a  jbe     loc_18000957C
0x180009030  lea     rax, aDevobjcreatede; "DevObjCreateDeviceInfoList"
0x180009037  mov     dword ptr [rbp+57h+dwBytes], 202h
0x18000903e  mov     qword ptr [rbp+57h+dwBytes+4], rax
0x180009042  lea     rdx, dword_180038744
0x180009049  lea     rax, aGetdxgkadapter; "GetDxgkAdapter"
0x180009050  mov     [rbp+57h+var_80], ecx
0x180009053  mov     [rbp+57h+var_70], rax
0x180009057  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000905e  mov     [rbp+57h+var_68], rax
0x180009062  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180009069  mov     [rbp+57h+var_60], rax
0x18000906d  lea     rax, [rbp+57h+dwBytes+4]
0x180009071  mov     [rsp+0D0h+var_88], rax
0x180009076  lea     rax, [rbp+57h+var_70]
0x18000907a  mov     [rsp+0D0h+var_90], rax
0x18000907f  lea     rax, [rbp+57h+dwBytes]
0x180009083  mov     [rsp+0D0h+var_98], rax
0x180009088  lea     rax, [rbp+57h+var_68]
0x18000908c  mov     [rsp+0D0h+hTemplateFile], rax
0x180009091  lea     rax, [rbp+57h+var_80]
0x180009095  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax
0x18000909a  lea     rax, [rbp+57h+var_60]
0x18000909e  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x1800090a3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800090a8  jmp     loc_18000957C
0x1800090ad  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], r14
0x1800090b2  lea     rdx, GUID_DISPLAY_DEVICE_ARRIVAL
0x1800090b9  mov     r9d, 12h
0x1800090bf  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r14
0x1800090c4  xor     r8d, r8d
0x1800090c7  mov     rcx, rdi
0x1800090ca  call    cs:__imp_DevObjGetClassDevs
0x1800090d0  test    eax, eax
0x1800090d2  jnz     loc_180009173
0x1800090d8  call    cs:__imp_GetLastError
0x1800090de  mov     ecx, eax
0x1800090e0  test    eax, eax
0x1800090e2  jle     short loc_1800090E9
0x1800090e4  movzx   ecx, ax
0x1800090e7  or      ecx, ebx
0x1800090e9  test    ecx, ecx
0x1800090eb  jns     loc_180009173
0x1800090f1  mov     eax, cs:dword_180044008
0x1800090f7  cmp     eax, 2
0x1800090fa  jbe     loc_18000956D
0x180009100  lea     rax, aDevobjgetclass; "DevObjGetClassDevs"
0x180009107  mov     [rbp+57h+var_80], 211h
0x18000910e  mov     [rbp+57h+var_60], rax
0x180009112  lea     rdx, byte_1800386EF
0x180009119  lea     rax, aGetdxgkadapter; "GetDxgkAdapter"
0x180009120  mov     dword ptr [rbp+57h+dwBytes], ecx
0x180009123  mov     [rbp+57h+var_68], rax
0x180009127  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000912e  mov     [rbp+57h+var_70], rax
0x180009132  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180009139  mov     qword ptr [rbp+57h+dwBytes+4], rax
0x18000913d  lea     rax, [rbp+57h+var_60]
0x180009141  mov     [rsp+0D0h+var_88], rax
0x180009146  lea     rax, [rbp+57h+var_68]
0x18000914a  mov     [rsp+0D0h+var_90], rax
0x18000914f  lea     rax, [rbp+57h+var_80]
0x180009153  mov     [rsp+0D0h+var_98], rax
0x180009158  lea     rax, [rbp+57h+var_70]
0x18000915c  mov     [rsp+0D0h+hTemplateFile], rax
0x180009161  lea     rax, [rbp+57h+dwBytes]
0x180009165  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax
0x18000916a  lea     rax, [rbp+57h+dwBytes+4]
0x18000916e  jmp     loc_180009563
0x180009173  xorps   xmm0, xmm0
0x180009176  lea     rax, [rbp+57h+var_50]
0x18000917a  movups  [rbp+57h+var_50], xmm0
0x18000917e  xor     r9d, r9d
0x180009181  mov     dword ptr [rbp+57h+var_50], 20h ; ' '
0x180009188  lea     r8, GUID_DISPLAY_DEVICE_ARRIVAL
0x18000918f  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x180009194  xor     edx, edx
0x180009196  mov     rcx, rdi
0x180009199  movups  [rbp+57h+var_40], xmm0
0x18000919d  xor     r12d, r12d
0x1800091a0  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800091a6  test    eax, eax
0x1800091a8  jz      loc_18000956D
0x1800091ae  lea     rax, [rbp+57h+dwBytes]
0x1800091b2  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], r14
0x1800091b7  xor     r9d, r9d
0x1800091ba  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x1800091bf  xor     r8d, r8d
0x1800091c2  mov     dword ptr [rbp+57h+dwBytes], r14d
0x1800091c6  lea     rdx, [rbp+57h+var_50]
0x1800091ca  mov     rcx, rdi
0x1800091cd  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800091d3  call    cs:__imp_GetLastError
0x1800091d9  cmp     eax, 7Ah ; 'z'
0x1800091dc  jz      short loc_1800091F7
0x1800091de  call    cs:__imp_GetLastError
0x1800091e4  mov     ecx, eax
0x1800091e6  test    eax, eax
0x1800091e8  jle     short loc_1800091EF
0x1800091ea  movzx   ecx, ax
0x1800091ed  or      ecx, ebx
0x1800091ef  test    ecx, ecx
0x1800091f1  js      loc_1800092C3
0x1800091f7  mov     ebx, dword ptr [rbp+57h+dwBytes]
0x1800091fa  call    cs:__imp_GetProcessHeap
0x180009200  mov     r8d, ebx; dwBytes
0x180009203  xor     edx, edx; dwFlags
0x180009205  mov     rcx, rax; hHeap
0x180009208  call    cs:__imp_HeapAlloc
0x18000920e  mov     rbx, rax
0x180009211  test    rax, rax
0x180009214  jz      loc_1800094E6
0x18000921a  mov     r8d, dword ptr [rbp+57h+dwBytes]; Size
0x18000921e  xor     edx, edx; Val
0x180009220  mov     rcx, rax; void *
0x180009223  call    memset_0
0x180009228  mov     dword ptr [rbx], 8
0x18000922e  lea     rdx, [rbp+57h+var_50]
0x180009232  mov     r9d, dword ptr [rbp+57h+dwBytes]
0x180009236  mov     r8, rbx
0x180009239  mov     rcx, rdi
0x18000923c  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], r14
0x180009241  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r14
0x180009246  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18000924c  test    eax, eax
0x18000924e  jz      short loc_18000926A
0x180009250  lea     rdx, pszSrch; "RdpIdd_IndirectDisplay"
0x180009257  lea     rcx, [rbx+4]; pszFirst
0x18000925b  call    cs:__imp_StrStrIW
0x180009261  test    rax, rax
0x180009264  jnz     loc_180009345
0x18000926a  call    cs:__imp_GetProcessHeap
0x180009270  mov     r8, rbx; lpMem
0x180009273  xor     edx, edx; dwFlags
0x180009275  mov     rcx, rax; hHeap
0x180009278  call    cs:__imp_HeapFree
0x18000927e  xorps   xmm0, xmm0
0x180009281  lea     rax, [rbp+57h+var_50]
0x180009285  movups  [rbp+57h+var_50], xmm0
0x180009289  inc     r12d
0x18000928c  mov     dword ptr [rbp+57h+var_50], 20h ; ' '
0x180009293  mov     r9d, r12d
0x180009296  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x18000929b  lea     r8, GUID_DISPLAY_DEVICE_ARRIVAL
0x1800092a2  xor     edx, edx
0x1800092a4  mov     rcx, rdi
0x1800092a7  movups  [rbp+57h+var_40], xmm0
0x1800092ab  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800092b1  test    eax, eax
0x1800092b3  jz      loc_18000956D
0x1800092b9  mov     ebx, 80070000h
0x1800092be  jmp     loc_1800091AE
0x1800092c3  mov     eax, cs:dword_180044008
0x1800092c9  cmp     eax, 2
0x1800092cc  jbe     loc_18000956D
0x1800092d2  lea     rax, aDevobjgetdevic; "DevObjGetDeviceInterfaceDetail"
0x1800092d9  mov     [rbp+57h+var_80], 22Dh
0x1800092e0  mov     [rbp+57h+var_60], rax
0x1800092e4  lea     rdx, word_18003869A
0x1800092eb  lea     rax, aGetdxgkadapter; "GetDxgkAdapter"
0x1800092f2  mov     dword ptr [rbp+57h+dwBytes+4], ecx
0x1800092f5  mov     [rbp+57h+var_68], rax
0x1800092f9  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180009300  mov     [rbp+57h+var_70], rax
0x180009304  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000930b  mov     [rbp+57h+var_58], rax
0x18000930f  lea     rax, [rbp+57h+var_60]
0x180009313  mov     [rsp+0D0h+var_88], rax
0x180009318  lea     rax, [rbp+57h+var_68]
0x18000931c  mov     [rsp+0D0h+var_90], rax
0x180009321  lea     rax, [rbp+57h+var_80]
0x180009325  mov     [rsp+0D0h+var_98], rax
0x18000932a  lea     rax, [rbp+57h+var_70]
0x18000932e  mov     [rsp+0D0h+hTemplateFile], rax
0x180009333  lea     rax, [rbp+57h+dwBytes+4]
0x180009337  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax
0x18000933c  lea     rax, [rbp+57h+var_58]
0x180009340  jmp     loc_180009563
0x180009345  lea     r8, [rbx+4]; unsigned __int16 *
0x180009349  mov     edx, 104h; unsigned __int64
0x18000934e  lea     rcx, [r15+38h]; unsigned __int16 *
0x180009352  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009357  mov     ecx, eax
0x180009359  test    eax, eax
0x18000935b  jns     short loc_180009386
0x18000935d  mov     eax, cs:dword_180044008
0x180009363  cmp     eax, 2
0x180009366  jbe     loc_1800094CD
0x18000936c  lea     rax, aFailedToCopyGr; "Failed to copy graphics adapter device "...
0x180009373  mov     dword ptr [rbp+57h+dwBytes+4], 252h
0x18000937a  lea     rdx, unk_1800385F0
0x180009381  jmp     loc_18000946A
0x180009386  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18000938f  lea     rcx, [r15+38h]; lpFileName
0x180009393  mov     r14d, 1
0x180009399  mov     [rsp+0D0h+dwFlagsAndAttributes], 40800080h; dwFlagsAndAttributes
0x1800093a1  xor     r9d, r9d; lpSecurityAttributes
0x1800093a4  mov     [rsp+0D0h+dwCreationDisposition], 4; dwCreationDisposition
0x1800093ac  mov     edx, 10000000h; dwDesiredAccess
0x1800093b1  lea     r8d, [r14+2]; dwShareMode
0x1800093b5  call    cs:__imp_CreateFileW
0x1800093bb  mov     [r15+250h], rax
0x1800093c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800093c6  jnz     short loc_18000940A
0x1800093c8  xor     r14d, r14d
0x1800093cb  call    cs:__imp_GetLastError
0x1800093d1  mov     ecx, eax
0x1800093d3  test    eax, eax
0x1800093d5  jle     short loc_1800093E0
0x1800093d7  movzx   ecx, ax
0x1800093da  or      ecx, 80070000h
0x1800093e0  test    ecx, ecx
0x1800093e2  jns     short loc_18000940A
0x1800093e4  mov     eax, cs:dword_180044008
0x1800093ea  cmp     eax, 2
0x1800093ed  jbe     loc_1800094CD
0x1800093f3  lea     rax, aFailToOpenInst; "Fail to open instance of RDPIDD"
0x1800093fa  mov     dword ptr [rbp+57h+dwBytes+4], 274h
0x180009401  lea     rdx, byte_18003859B
0x180009408  jmp     short loc_18000946A
0x18000940a  xor     r9d, r9d; lpName
0x18000940d  xor     r8d, r8d; bInitialState
0x180009410  xor     edx, edx; bManualReset
0x180009412  xor     ecx, ecx; lpEventAttributes
0x180009414  call    cs:__imp_CreateEventW
0x18000941a  mov     [r15+270h], rax
0x180009421  test    rax, rax
0x180009424  jnz     loc_1800094CD
0x18000942a  xor     r14d, r14d
0x18000942d  call    cs:__imp_GetLastError
0x180009433  mov     ecx, eax
0x180009435  test    eax, eax
0x180009437  jle     short loc_180009442
0x180009439  movzx   ecx, ax
0x18000943c  or      ecx, 80070000h
0x180009442  test    ecx, ecx
0x180009444  jns     loc_1800094CD
0x18000944a  mov     eax, cs:dword_180044008
0x180009450  cmp     eax, 2
0x180009453  jbe     short loc_1800094CD
0x180009455  lea     rax, aFailToCreateOv; "Fail to create overlapped event"
0x18000945c  mov     dword ptr [rbp+57h+dwBytes+4], 27Dh
0x180009463  lea     rdx, word_180038546
0x18000946a  mov     [rbp+57h+var_58], rax
0x18000946e  lea     rax, aGetdxgkadapter; "GetDxgkAdapter"
0x180009475  mov     [rbp+57h+var_60], rax
0x180009479  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180009480  mov     [rbp+57h+var_68], rax
0x180009484  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000948b  mov     [rbp+57h+var_70], rax
0x18000948f  lea     rax, [rbp+57h+var_58]
0x180009493  mov     [rsp+0D0h+var_88], rax
0x180009498  lea     rax, [rbp+57h+var_60]
0x18000949c  mov     [rsp+0D0h+var_90], rax
0x1800094a1  lea     rax, [rbp+57h+dwBytes+4]
0x1800094a5  mov     [rsp+0D0h+var_98], rax
0x1800094aa  lea     rax, [rbp+57h+var_68]
0x1800094ae  mov     [rsp+0D0h+hTemplateFile], rax
0x1800094b3  lea     rax, [rbp+57h+var_80]
0x1800094b7  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax
0x1800094bc  lea     rax, [rbp+57h+var_70]
0x1800094c0  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x1800094c5  mov     [rbp+57h+var_80], ecx
  ... truncated ...
```
