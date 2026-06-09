# GetFileFromOneSettings(ushort const *,ushort const *,ushort const *,ulong *)

- ea: `0x140012928`
- end: `0x140012e08`
- name: `?GetFileFromOneSettings@@YAJPEBG00PEAK@Z`
- size: `1248`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x140010c40`

## callees

- `0x140001418`
- `0x140001840`
- `0x1400124a0`
- `0x1400126c4`
- `0x140012928`
- `0x140012e10`
- `0x140013438`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012a61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012a87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012dd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012a61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012a87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012dd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012a76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012a9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012de4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012a76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012a9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012da2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012da2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012df6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012df6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140012d92`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140012d92`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x140012d40`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x140012d40`
- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x140012ab0`
- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x140012ab0`

## string_xrefs

- `0x140012cd7`: `GetSiufPayloadFromJson failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetFileFromOneSettings(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  void *v8; // rdi
  __int64 v9; // rcx
  signed int SiufPayloadFromJson; // ebx
  int v11; // r9d
  HANDLE v12; // rax
  HANDLE v13; // rax
  int v15; // r8d
  int v16; // r9d
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rax
  void *File2; // r14
  signed int v21; // eax
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  unsigned int cbMultiByte; // [rsp+50h] [rbp-79h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+54h] [rbp-75h] BYREF
  LPCVOID lpBuffer; // [rsp+58h] [rbp-71h] BYREF
  const char *v27; // [rsp+60h] [rbp-69h] BYREF
  const char *v28; // [rsp+68h] [rbp-61h] BYREF
  __int64 v29; // [rsp+70h] [rbp-59h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-51h] BYREF
  __int64 v31; // [rsp+80h] [rbp-49h] BYREF
  LPCCH lpMultiByteStr; // [rsp+88h] [rbp-41h] BYREF
  unsigned __int16 *v33; // [rsp+90h] [rbp-39h] BYREF
  const char *v34; // [rsp+98h] [rbp-31h] BYREF
  _BYTE v35[32]; // [rsp+A0h] [rbp-29h] BYREF
  const char *v36; // [rsp+C0h] [rbp-9h]
  __int64 v37; // [rsp+C8h] [rbp-1h]
  const unsigned __int16 *v38; // [rsp+D0h] [rbp+7h]
  int v39; // [rsp+D8h] [rbp+Fh]
  int v40; // [rsp+DCh] [rbp+13h]

  lpMultiByteStr = 0;
  cbMultiByte = 0;
  v8 = 0;
  lpBuffer = 0;
  nNumberOfBytesToWrite = 0;
  v33 = 0;
  v9 = 0;
  v31 = 0;
  lpMem = 0;
  if ( !a1 || !a2 || !a4 )
  {
    SiufPayloadFromJson = -2147467261;
    goto LABEL_15;
  }
  SiufPayloadFromJson = BuildETagHeaderFromFile(a2, (unsigned __int16 **)&lpMem);
  if ( SiufPayloadFromJson >= 0 )
  {
    SiufPayloadFromJson = DownloadFromOneSettings(
                            (__int64)a1,
                            (__int64)lpMem,
                            (__int64)a3,
                            a4,
                            &lpMultiByteStr,
                            &cbMultiByte,
                            (__int64)&v33,
                            &v31);
    if ( SiufPayloadFromJson >= 0 )
    {
      if ( *a4 == 200 )
      {
        SiufPayloadFromJson = GetSiufPayloadFromJson(
                                lpMultiByteStr,
                                cbMultiByte,
                                (unsigned __int16 **)&lpBuffer,
                                &nNumberOfBytesToWrite);
        if ( SiufPayloadFromJson >= 0 )
        {
          File2 = (void *)CreateFile2(a2, 0x40000000, 1);
          if ( File2 != (void *)-1LL )
          {
            v8 = (void *)lpBuffer;
            if ( WriteFile(File2, lpBuffer, nNumberOfBytesToWrite, 0, 0) )
            {
              SaveETagToFile(a2, v33);
              if ( v8 )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v8);
              }
              v8 = 0;
            }
            else
            {
              LastError = GetLastError();
              SiufPayloadFromJson = LastError;
              if ( LastError > 0 )
                SiufPayloadFromJson = (unsigned __int16)LastError | 0x80070000;
            }
            CloseHandle(File2);
            goto LABEL_10;
          }
          v21 = GetLastError();
          SiufPayloadFromJson = v21;
          if ( v21 > 0 )
            SiufPayloadFromJson = (unsigned __int16)v21 | 0x80070000;
        }
        else if ( SiufPayloadFromJson == -2089484279 )
        {
          SiufPayloadFromJson = 6148402;
          if ( (unsigned int)dword_140028000 > 5 )
          {
            v19 = -1;
            do
              ++v19;
            while ( a1[v19] );
            v38 = a1;
            v39 = 2 * v19 + 2;
            v40 = 0;
            v36 = "Siufpayload not found. Empty record.";
            v37 = 37;
            tlgWriteTransfer_EventWriteTransfer(&dword_140028000, byte_14002371D, 0, 0, 4, v35);
          }
        }
        else if ( (unsigned int)dword_140028000 > 2
               && (qword_140028010 & 0x400000000000LL) != 0
               && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          v29 = 0x1000000;
          nNumberOfBytesToWrite = 742;
          v28 = "GetFileFromOneSettings";
          v27 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufonesettings\\siufonesettings.cpp";
          cbMultiByte = SiufPayloadFromJson;
          v34 = "GetSiufPayloadFromJson failed.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140028018,
            (unsigned int)byte_140023615,
            v17,
            v18,
            (__int64)&v34,
            (__int64)&cbMultiByte,
            (__int64)&v27,
            (__int64)&v28,
            (__int64)&nNumberOfBytesToWrite,
            (__int64)&v29);
        }
        v8 = (void *)lpBuffer;
      }
    }
    else if ( (unsigned int)dword_140028000 > 2
           && (qword_140028010 & 0x400000000000LL) != 0
           && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      v29 = 0x1000000;
      nNumberOfBytesToWrite = 700;
      v28 = "GetFileFromOneSettings";
      v27 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufonesettings\\siufonesettings.cpp";
      cbMultiByte = SiufPayloadFromJson;
      lpBuffer = "GetFromOneSetting failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140028018,
        (unsigned int)byte_140023741,
        v15,
        v16,
        (__int64)&lpBuffer,
        (__int64)&cbMultiByte,
        (__int64)&v27,
        (__int64)&v28,
        (__int64)&nNumberOfBytesToWrite,
        (__int64)&v29);
    }
  }
  else if ( (unsigned int)dword_140028000 > 2
         && (qword_140028010 & 0x400000000000LL) != 0
         && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
  {
    lpBuffer = (LPCVOID)0x1000000;
    nNumberOfBytesToWrite = 688;
    v27 = "GetFileFromOneSettings";
    v28 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufonesettings\\siufonesettings.cpp";
    cbMultiByte = SiufPayloadFromJson;
    v29 = (__int64)"BuildETagHeaderFromFile failed.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      qword_140028010,
      (unsigned int)byte_140023673,
      qword_140028018,
      v11,
      (__int64)&v29,
      (__int64)&cbMultiByte,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&nNumberOfBytesToWrite,
      (__int64)&lpBuffer);
  }
LABEL_10:
  if ( lpMem )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, lpMem);
  }
  if ( v8 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v8);
  }
  v9 = v31;
LABEL_15:
  if ( v9 )
    OneSettingsFreeDownloadResponse(v9);
  return (unsigned int)SiufPayloadFromJson;
}

```

## disassembly

```asm
0x140012928  push    rbp
0x14001292a  push    rbx
0x14001292b  push    rsi
0x14001292c  push    rdi
0x14001292d  push    r13
0x14001292f  push    r14
0x140012931  push    r15
0x140012933  lea     rbp, [rsp-27h]
0x140012938  sub     rsp, 0F0h
0x14001293f  mov     rax, cs:__security_cookie
0x140012946  xor     rax, rsp
0x140012949  mov     [rbp+57h+var_40], rax
0x14001294d  mov     r14, r9
0x140012950  mov     r13, r8
0x140012953  mov     rsi, rdx
0x140012956  mov     r15, rcx
0x140012959  xor     ebx, ebx
0x14001295b  mov     [rbp+57h+lpMultiByteStr], rbx
0x14001295f  mov     [rbp+57h+cbMultiByte], ebx
0x140012962  mov     edi, ebx
0x140012964  mov     [rbp+57h+lpBuffer], rbx
0x140012968  mov     [rbp+57h+nNumberOfBytesToWrite], ebx
0x14001296b  mov     [rbp+57h+var_90], rbx
0x14001296f  mov     ecx, ebx
0x140012971  mov     [rbp+57h+var_A0], rbx
0x140012975  mov     [rbp+57h+lpMem], rbx
0x140012979  test    r15, r15
0x14001297c  jnz     short loc_140012988
0x14001297e  mov     ebx, 80004003h
0x140012983  jmp     loc_140012AAB
0x140012988  test    rsi, rsi
0x14001298b  jz      short loc_14001297E
0x14001298d  test    r14, r14
0x140012990  jz      short loc_14001297E
0x140012992  lea     rdx, [rbp+57h+lpMem]; unsigned __int16 **
0x140012996  mov     rcx, rsi; unsigned __int16 *
0x140012999  call    ?BuildETagHeaderFromFile@@YAJPEBGPEAPEAG@Z; BuildETagHeaderFromFile(ushort const *,ushort * *)
0x14001299e  mov     ebx, eax
0x1400129a0  test    eax, eax
0x1400129a2  jns     loc_140012ADD
0x1400129a8  mov     ecx, cs:dword_140028000
0x1400129ae  cmp     ecx, 2
0x1400129b1  jbe     loc_140012A58
0x1400129b7  mov     r8, cs:qword_140028018
0x1400129be  mov     rcx, cs:qword_140028010
0x1400129c5  mov     rdx, 400000000000h
0x1400129cf  test    rdx, rcx
0x1400129d2  jz      loc_140012A58
0x1400129d8  mov     rax, r8
0x1400129db  and     rax, rdx
0x1400129de  cmp     rax, r8
0x1400129e1  jnz     short loc_140012A58
0x1400129e3  mov     [rbp+57h+lpBuffer], 1000000h
0x1400129eb  mov     [rbp+57h+nNumberOfBytesToWrite], 2B0h
0x1400129f2  lea     rax, aGetfilefromone; "GetFileFromOneSettings"
0x1400129f9  mov     [rbp+57h+var_C0], rax
0x1400129fd  lea     rax, aOnecoreBaseDia_0; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140012a04  mov     [rbp+57h+var_B8], rax
0x140012a08  mov     [rbp+57h+cbMultiByte], ebx
0x140012a0b  lea     rax, aBuildetagheade; "BuildETagHeaderFromFile failed."
0x140012a12  mov     [rbp+57h+var_B0], rax
0x140012a16  lea     rax, [rbp+57h+lpBuffer]
0x140012a1a  mov     [rsp+120h+var_D8], rax
0x140012a1f  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x140012a23  mov     [rsp+120h+var_E0], rax
0x140012a28  lea     rax, [rbp+57h+var_C0]
0x140012a2c  mov     [rsp+120h+var_E8], rax
0x140012a31  lea     rax, [rbp+57h+var_B8]
0x140012a35  mov     [rsp+120h+var_F0], rax
0x140012a3a  lea     rax, [rbp+57h+cbMultiByte]
0x140012a3e  mov     [rsp+120h+var_F8], rax
0x140012a43  lea     rax, [rbp+57h+var_B0]
0x140012a47  mov     [rsp+120h+lpOverlapped], rax
0x140012a4c  lea     rdx, byte_140023673
0x140012a53  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140012a58  xor     r13d, r13d
0x140012a5b  cmp     [rbp+57h+lpMem], r13
0x140012a5f  jz      short loc_140012A82
0x140012a61  call    cs:__imp_GetProcessHeap
0x140012a68  nop     dword ptr [rax+rax+00h]
0x140012a6d  mov     r8, [rbp+57h+lpMem]; lpMem
0x140012a71  xor     edx, edx; dwFlags
0x140012a73  mov     rcx, rax; hHeap
0x140012a76  call    cs:__imp_HeapFree
0x140012a7d  nop     dword ptr [rax+rax+00h]
0x140012a82  test    rdi, rdi
0x140012a85  jz      short loc_140012AA7
0x140012a87  call    cs:__imp_GetProcessHeap
0x140012a8e  nop     dword ptr [rax+rax+00h]
0x140012a93  mov     r8, rdi; lpMem
0x140012a96  xor     edx, edx; dwFlags
0x140012a98  mov     rcx, rax; hHeap
0x140012a9b  call    cs:__imp_HeapFree
0x140012aa2  nop     dword ptr [rax+rax+00h]
0x140012aa7  mov     rcx, [rbp+57h+var_A0]
0x140012aab  test    rcx, rcx
0x140012aae  jz      short loc_140012ABC
0x140012ab0  call    cs:__imp_OneSettingsFreeDownloadResponse
0x140012ab7  nop     dword ptr [rax+rax+00h]
0x140012abc  mov     eax, ebx
0x140012abe  mov     rcx, [rbp+57h+var_40]
0x140012ac2  xor     rcx, rsp; StackCookie
0x140012ac5  call    __security_check_cookie
0x140012aca  add     rsp, 0F0h
0x140012ad1  pop     r15
0x140012ad3  pop     r14
0x140012ad5  pop     r13
0x140012ad7  pop     rdi
0x140012ad8  pop     rsi
0x140012ad9  pop     rbx
0x140012ada  pop     rbp
0x140012adb  retn
0x140012add  lea     rax, [rbp+57h+var_A0]
0x140012ae1  mov     [rsp+120h+var_E8], rax
0x140012ae6  lea     rax, [rbp+57h+var_90]
0x140012aea  mov     [rsp+120h+var_F0], rax
0x140012aef  lea     rax, [rbp+57h+cbMultiByte]
0x140012af3  mov     [rsp+120h+var_F8], rax
0x140012af8  lea     rax, [rbp+57h+lpMultiByteStr]
0x140012afc  mov     [rsp+120h+lpOverlapped], rax
0x140012b01  mov     r9, r14
0x140012b04  mov     r8, r13
0x140012b07  mov     rdx, [rbp+57h+lpMem]
0x140012b0b  mov     rcx, r15
0x140012b0e  call    ?DownloadFromOneSettings@@YAJPEBG00PEAKPEAPEADPEAIPEAPEAGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUOneSettingsDownloadResponseImpl@@P6AJPEAU1@@Z$1?OneSettingsFreeDownloadResponse@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; DownloadFromOneSettings(ushort const *,ushort const *,ushort const *,ulong *,char * *,uint *,ushort * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<OneSettingsDownloadResponseImpl *,long (*)(OneSettingsDownloadResponseImpl *),&OneSettingsFreeDownloadResponse(OneSettingsDownloadResponseImpl *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadResponseImpl *,OneSettingsDownloadResponseImpl *,0,std::nullptr_t>>> &)
0x140012b13  mov     ebx, eax
0x140012b15  xor     r13d, r13d
0x140012b18  test    eax, eax
0x140012b1a  jns     loc_140012BD9
0x140012b20  mov     eax, cs:dword_140028000
0x140012b26  cmp     eax, 2
0x140012b29  jbe     loc_140012A5B
0x140012b2f  mov     rcx, cs:qword_140028018
0x140012b36  mov     rax, cs:qword_140028010
0x140012b3d  mov     rdx, 400000000000h
0x140012b47  test    rdx, rax
0x140012b4a  jz      loc_140012A5B
0x140012b50  mov     rax, rcx
0x140012b53  and     rax, rdx
0x140012b56  cmp     rax, rcx
0x140012b59  jnz     loc_140012A5B
0x140012b5f  mov     [rbp+57h+var_B0], 1000000h
0x140012b67  mov     [rbp+57h+nNumberOfBytesToWrite], 2BCh
0x140012b6e  lea     rax, aGetfilefromone; "GetFileFromOneSettings"
0x140012b75  mov     [rbp+57h+var_B8], rax
0x140012b79  lea     rax, aOnecoreBaseDia_0; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140012b80  mov     [rbp+57h+var_C0], rax
0x140012b84  mov     [rbp+57h+cbMultiByte], ebx
0x140012b87  lea     rax, aGetfromonesett; "GetFromOneSetting failed."
0x140012b8e  mov     [rbp+57h+lpBuffer], rax
0x140012b92  lea     rax, [rbp+57h+var_B0]
0x140012b96  mov     [rsp+120h+var_D8], rax
0x140012b9b  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x140012b9f  mov     [rsp+120h+var_E0], rax
0x140012ba4  lea     rax, [rbp+57h+var_B8]
0x140012ba8  mov     [rsp+120h+var_E8], rax
0x140012bad  lea     rax, [rbp+57h+var_C0]
0x140012bb1  mov     [rsp+120h+var_F0], rax
0x140012bb6  lea     rax, [rbp+57h+cbMultiByte]
0x140012bba  mov     [rsp+120h+var_F8], rax
0x140012bbf  lea     rax, [rbp+57h+lpBuffer]
0x140012bc3  mov     [rsp+120h+lpOverlapped], rax
0x140012bc8  lea     rdx, byte_140023741
0x140012bcf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140012bd4  jmp     loc_140012A5B
0x140012bd9  cmp     dword ptr [r14], 0C8h
0x140012be0  jnz     loc_140012A5B
0x140012be6  lea     r9, [rbp+57h+nNumberOfBytesToWrite]; unsigned int *
0x140012bea  lea     r8, [rbp+57h+lpBuffer]; unsigned __int16 **
0x140012bee  mov     edx, [rbp+57h+cbMultiByte]; cbMultiByte
0x140012bf1  mov     rcx, [rbp+57h+lpMultiByteStr]; lpMultiByteStr
0x140012bf5  call    ?GetSiufPayloadFromJson@@YAJPEAEIPEAPEAGPEAI@Z; GetSiufPayloadFromJson(uchar *,uint,ushort * *,uint *)
0x140012bfa  mov     ebx, eax
0x140012bfc  test    eax, eax
0x140012bfe  jns     loc_140012D29
0x140012c04  mov     eax, cs:dword_140028000
0x140012c0a  cmp     ebx, 83750009h
0x140012c10  jnz     short loc_140012C82
0x140012c12  mov     ebx, 5DD132h
0x140012c17  cmp     eax, 5
0x140012c1a  jbe     short loc_140012C79
0x140012c1c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012c20  inc     rax
0x140012c23  cmp     [r15+rax*2], r13w
0x140012c28  jnz     short loc_140012C20
0x140012c2a  mov     [rbp+57h+var_50], r15
0x140012c2e  lea     eax, ds:2[rax*2]
0x140012c35  mov     [rbp+57h+var_48], eax
0x140012c38  mov     [rbp+57h+var_44], r13d
0x140012c3c  lea     rax, aSiufpayloadNot; "Siufpayload not found. Empty record."
0x140012c43  mov     [rbp+57h+var_60], rax
0x140012c47  mov     [rbp+57h+var_58], 25h ; '%'
0x140012c4f  lea     rax, [rbp+57h+var_80]
0x140012c53  mov     [rsp+120h+var_F8], rax
0x140012c58  mov     dword ptr [rsp+120h+lpOverlapped], 4
0x140012c60  xor     r9d, r9d
0x140012c63  xor     r8d, r8d
0x140012c66  lea     rdx, byte_14002371D
0x140012c6d  lea     rcx, dword_140028000
0x140012c74  call    _tlgWriteTransfer_EventWriteTransfer
0x140012c79  mov     rdi, [rbp+57h+lpBuffer]
0x140012c7d  jmp     loc_140012A5B
0x140012c82  cmp     eax, 2
0x140012c85  jbe     short loc_140012C79
0x140012c87  mov     rcx, cs:qword_140028018
0x140012c8e  mov     rax, cs:qword_140028010
0x140012c95  mov     rdx, 400000000000h
0x140012c9f  test    rdx, rax
0x140012ca2  jz      short loc_140012C79
0x140012ca4  mov     rax, rcx
0x140012ca7  and     rax, rdx
0x140012caa  cmp     rax, rcx
0x140012cad  jnz     short loc_140012C79
0x140012caf  mov     [rbp+57h+var_B0], 1000000h
0x140012cb7  mov     [rbp+57h+nNumberOfBytesToWrite], 2E6h
0x140012cbe  lea     rax, aGetfilefromone; "GetFileFromOneSettings"
0x140012cc5  mov     [rbp+57h+var_B8], rax
0x140012cc9  lea     rax, aOnecoreBaseDia_0; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140012cd0  mov     [rbp+57h+var_C0], rax
0x140012cd4  mov     [rbp+57h+cbMultiByte], ebx
0x140012cd7  lea     rax, aGetsiufpayload; "GetSiufPayloadFromJson failed."
0x140012cde  mov     [rbp+57h+var_88], rax
0x140012ce2  lea     rax, [rbp+57h+var_B0]
0x140012ce6  mov     [rsp+120h+var_D8], rax
0x140012ceb  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x140012cef  mov     [rsp+120h+var_E0], rax
0x140012cf4  lea     rax, [rbp+57h+var_B8]
0x140012cf8  mov     [rsp+120h+var_E8], rax
0x140012cfd  lea     rax, [rbp+57h+var_C0]
0x140012d01  mov     [rsp+120h+var_F0], rax
0x140012d06  lea     rax, [rbp+57h+cbMultiByte]
0x140012d0a  mov     [rsp+120h+var_F8], rax
0x140012d0f  lea     rax, [rbp+57h+var_88]
0x140012d13  mov     [rsp+120h+lpOverlapped], rax
0x140012d18  lea     rdx, byte_140023615
0x140012d1f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140012d24  jmp     loc_140012C79
0x140012d29  mov     [rsp+120h+lpOverlapped], r13
0x140012d2e  mov     edx, 40000000h
0x140012d33  mov     r9d, 2
0x140012d39  lea     r8d, [r9-1]
0x140012d3d  mov     rcx, rsi
0x140012d40  call    cs:__imp_CreateFile2
0x140012d47  nop     dword ptr [rax+rax+00h]
0x140012d4c  mov     r14, rax
0x140012d4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012d53  cmp     r14, rax
0x140012d56  jnz     short loc_140012D7C
0x140012d58  call    cs:__imp_GetLastError
0x140012d5f  nop     dword ptr [rax+rax+00h]
0x140012d64  mov     ebx, eax
0x140012d66  test    eax, eax
0x140012d68  jle     loc_140012C79
0x140012d6e  movzx   ebx, ax
0x140012d71  or      ebx, 80070000h
0x140012d77  jmp     loc_140012C79
0x140012d7c  mov     [rsp+120h+lpOverlapped], r13; lpOverlapped
0x140012d81  xor     r9d, r9d; lpNumberOfBytesWritten
0x140012d84  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140012d88  mov     rdi, [rbp+57h+lpBuffer]
0x140012d8c  mov     rdx, rdi; lpBuffer
0x140012d8f  mov     rcx, r14; hFile
0x140012d92  call    cs:__imp_WriteFile
0x140012d99  nop     dword ptr [rax+rax+00h]
0x140012d9e  test    eax, eax
0x140012da0  jnz     short loc_140012DBF
0x140012da2  call    cs:__imp_GetLastError
0x140012da9  nop     dword ptr [rax+rax+00h]
0x140012dae  mov     ebx, eax
0x140012db0  test    eax, eax
0x140012db2  jle     short loc_140012DF3
0x140012db4  movzx   ebx, ax
0x140012db7  or      ebx, 80070000h
0x140012dbd  jmp     short loc_140012DF3
0x140012dbf  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x140012dc3  mov     rcx, rsi; unsigned __int16 *
0x140012dc6  call    ?SaveETagToFile@@YAJPEBG0@Z; SaveETagToFile(ushort const *,ushort const *)
0x140012dcb  test    rdi, rdi
0x140012dce  jz      short loc_140012DF0
0x140012dd0  call    cs:__imp_GetProcessHeap
0x140012dd7  nop     dword ptr [rax+rax+00h]
0x140012ddc  mov     r8, rdi; lpMem
0x140012ddf  xor     edx, edx; dwFlags
0x140012de1  mov     rcx, rax; hHeap
0x140012de4  call    cs:__imp_HeapFree
0x140012deb  nop     dword ptr [rax+rax+00h]
0x140012df0  mov     rdi, r13
0x140012df3  mov     rcx, r14; hObject
0x140012df6  call    cs:__imp_CloseHandle
0x140012dfd  nop     dword ptr [rax+rax+00h]
0x140012e02  jmp     loc_140012A5B
```
