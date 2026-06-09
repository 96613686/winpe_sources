# GetFileFromOneSettings(ushort const *,ushort const *,ushort const *,ulong *)

- ea: `0x140011fec`
- end: `0x140012483`
- name: `?GetFileFromOneSettings@@YAJPEBG00PEAK@Z`
- size: `1175`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1400105d8`

## callees

- `0x140001414`
- `0x14000182c`
- `0x140011c10`
- `0x140011dec`
- `0x140011fec`
- `0x14001248c`
- `0x140012a50`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012125`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001213f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001245d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012125`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001213f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001245d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012134`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001214d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001246b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012134`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001214d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001246b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400123f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400123f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012435`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012477`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012477`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001242b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001242b`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1400123e5`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1400123e5`
- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x14001215c`
- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x14001215c`

## string_xrefs

- `0x14001237c`: `GetSiufPayloadFromJson failed.`

## pseudocode

```c
__int64 __fastcall GetFileFromOneSettings(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  int v5; // r13d
  void *v8; // rdi
  __int64 v9; // rcx
  int SiufPayloadFromJson; // ebx
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

  v5 = (int)a3;
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
                            (_DWORD)a1,
                            (_DWORD)lpMem,
                            v5,
                            (_DWORD)a4,
                            (__int64)&lpMultiByteStr,
                            (__int64)&cbMultiByte,
                            (__int64)&v33,
                            (__int64)&v31);
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
          if ( (unsigned int)dword_140027000 > 5 )
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
            tlgWriteTransfer_EventWriteTransfer(&dword_140027000, byte_140022715, 0, 0, 4, v35);
          }
        }
        else if ( (unsigned int)dword_140027000 > 2
               && (qword_140027010 & 0x400000000000LL) != 0
               && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
        {
          v29 = 0x1000000;
          nNumberOfBytesToWrite = 742;
          v28 = "GetFileFromOneSettings";
          v27 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufonesettings\\siufonesettings.cpp";
          cbMultiByte = SiufPayloadFromJson;
          v34 = "GetSiufPayloadFromJson failed.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140027018,
            (unsigned int)byte_14002260D,
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
    else if ( (unsigned int)dword_140027000 > 2
           && (qword_140027010 & 0x400000000000LL) != 0
           && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      v29 = 0x1000000;
      nNumberOfBytesToWrite = 700;
      v28 = "GetFileFromOneSettings";
      v27 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufonesettings\\siufonesettings.cpp";
      cbMultiByte = SiufPayloadFromJson;
      lpBuffer = "GetFromOneSetting failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140027018,
        (unsigned int)byte_140022739,
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
  else if ( (unsigned int)dword_140027000 > 2
         && (qword_140027010 & 0x400000000000LL) != 0
         && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
  {
    lpBuffer = (LPCVOID)0x1000000;
    nNumberOfBytesToWrite = 688;
    v27 = "GetFileFromOneSettings";
    v28 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufonesettings\\siufonesettings.cpp";
    cbMultiByte = SiufPayloadFromJson;
    v29 = (__int64)"BuildETagHeaderFromFile failed.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      qword_140027010,
      (unsigned int)byte_14002266B,
      qword_140027018,
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
    OneSettingsFreeDownloadResponse();
  return (unsigned int)SiufPayloadFromJson;
}

```

## disassembly

```asm
0x140011fec  push    rbp
0x140011fee  push    rbx
0x140011fef  push    rsi
0x140011ff0  push    rdi
0x140011ff1  push    r13
0x140011ff3  push    r14
0x140011ff5  push    r15
0x140011ff7  lea     rbp, [rsp-27h]
0x140011ffc  sub     rsp, 0F0h
0x140012003  mov     rax, cs:__security_cookie
0x14001200a  xor     rax, rsp
0x14001200d  mov     [rbp+57h+var_40], rax
0x140012011  mov     r14, r9
0x140012014  mov     r13, r8
0x140012017  mov     rsi, rdx
0x14001201a  mov     r15, rcx
0x14001201d  xor     ebx, ebx
0x14001201f  mov     [rbp+57h+lpMultiByteStr], rbx
0x140012023  mov     [rbp+57h+cbMultiByte], ebx
0x140012026  mov     edi, ebx
0x140012028  mov     [rbp+57h+lpBuffer], rbx
0x14001202c  mov     [rbp+57h+nNumberOfBytesToWrite], ebx
0x14001202f  mov     [rbp+57h+var_90], rbx
0x140012033  mov     ecx, ebx
0x140012035  mov     [rbp+57h+var_A0], rbx
0x140012039  mov     [rbp+57h+lpMem], rbx
0x14001203d  test    r15, r15
0x140012040  jnz     short loc_14001204C
0x140012042  mov     ebx, 80004003h
0x140012047  jmp     loc_140012157
0x14001204c  test    rsi, rsi
0x14001204f  jz      short loc_140012042
0x140012051  test    r14, r14
0x140012054  jz      short loc_140012042
0x140012056  lea     rdx, [rbp+57h+lpMem]; unsigned __int16 **
0x14001205a  mov     rcx, rsi; unsigned __int16 *
0x14001205d  call    ?BuildETagHeaderFromFile@@YAJPEBGPEAPEAG@Z; BuildETagHeaderFromFile(ushort const *,ushort * *)
0x140012062  mov     ebx, eax
0x140012064  test    eax, eax
0x140012066  jns     loc_140012182
0x14001206c  mov     ecx, cs:dword_140027000
0x140012072  cmp     ecx, 2
0x140012075  jbe     loc_14001211C
0x14001207b  mov     r8, cs:qword_140027018
0x140012082  mov     rcx, cs:qword_140027010
0x140012089  mov     rdx, 400000000000h
0x140012093  test    rdx, rcx
0x140012096  jz      loc_14001211C
0x14001209c  mov     rax, r8
0x14001209f  and     rax, rdx
0x1400120a2  cmp     rax, r8
0x1400120a5  jnz     short loc_14001211C
0x1400120a7  mov     [rbp+57h+lpBuffer], 1000000h
0x1400120af  mov     [rbp+57h+nNumberOfBytesToWrite], 2B0h
0x1400120b6  lea     rax, aGetfilefromone; "GetFileFromOneSettings"
0x1400120bd  mov     [rbp+57h+var_C0], rax
0x1400120c1  lea     rax, aOnecoreBaseDia_0; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400120c8  mov     [rbp+57h+var_B8], rax
0x1400120cc  mov     [rbp+57h+cbMultiByte], ebx
0x1400120cf  lea     rax, aBuildetagheade; "BuildETagHeaderFromFile failed."
0x1400120d6  mov     [rbp+57h+var_B0], rax
0x1400120da  lea     rax, [rbp+57h+lpBuffer]
0x1400120de  mov     [rsp+120h+var_D8], rax
0x1400120e3  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x1400120e7  mov     [rsp+120h+var_E0], rax
0x1400120ec  lea     rax, [rbp+57h+var_C0]
0x1400120f0  mov     [rsp+120h+var_E8], rax
0x1400120f5  lea     rax, [rbp+57h+var_B8]
0x1400120f9  mov     [rsp+120h+var_F0], rax
0x1400120fe  lea     rax, [rbp+57h+cbMultiByte]
0x140012102  mov     [rsp+120h+var_F8], rax
0x140012107  lea     rax, [rbp+57h+var_B0]
0x14001210b  mov     [rsp+120h+lpOverlapped], rax
0x140012110  lea     rdx, byte_14002266B
0x140012117  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14001211c  xor     r13d, r13d
0x14001211f  cmp     [rbp+57h+lpMem], r13
0x140012123  jz      short loc_14001213A
0x140012125  call    cs:__imp_GetProcessHeap
0x14001212b  mov     r8, [rbp+57h+lpMem]; lpMem
0x14001212f  xor     edx, edx; dwFlags
0x140012131  mov     rcx, rax; hHeap
0x140012134  call    cs:__imp_HeapFree
0x14001213a  test    rdi, rdi
0x14001213d  jz      short loc_140012153
0x14001213f  call    cs:__imp_GetProcessHeap
0x140012145  mov     r8, rdi; lpMem
0x140012148  xor     edx, edx; dwFlags
0x14001214a  mov     rcx, rax; hHeap
0x14001214d  call    cs:__imp_HeapFree
0x140012153  mov     rcx, [rbp+57h+var_A0]
0x140012157  test    rcx, rcx
0x14001215a  jz      short loc_140012162
0x14001215c  call    cs:__imp_OneSettingsFreeDownloadResponse
0x140012162  mov     eax, ebx
0x140012164  mov     rcx, [rbp+57h+var_40]
0x140012168  xor     rcx, rsp; StackCookie
0x14001216b  call    __security_check_cookie
0x140012170  add     rsp, 0F0h
0x140012177  pop     r15
0x140012179  pop     r14
0x14001217b  pop     r13
0x14001217d  pop     rdi
0x14001217e  pop     rsi
0x14001217f  pop     rbx
0x140012180  pop     rbp
0x140012181  retn
0x140012182  lea     rax, [rbp+57h+var_A0]
0x140012186  mov     [rsp+120h+var_E8], rax
0x14001218b  lea     rax, [rbp+57h+var_90]
0x14001218f  mov     [rsp+120h+var_F0], rax
0x140012194  lea     rax, [rbp+57h+cbMultiByte]
0x140012198  mov     [rsp+120h+var_F8], rax
0x14001219d  lea     rax, [rbp+57h+lpMultiByteStr]
0x1400121a1  mov     [rsp+120h+lpOverlapped], rax
0x1400121a6  mov     r9, r14
0x1400121a9  mov     r8, r13
0x1400121ac  mov     rdx, [rbp+57h+lpMem]
0x1400121b0  mov     rcx, r15
0x1400121b3  call    ?DownloadFromOneSettings@@YAJPEBG00PEAKPEAPEADPEAIPEAPEAGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUOneSettingsDownloadResponseImpl@@P6AJPEAU1@@Z$1?OneSettingsFreeDownloadResponse@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; DownloadFromOneSettings(ushort const *,ushort const *,ushort const *,ulong *,char * *,uint *,ushort * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<OneSettingsDownloadResponseImpl *,long (*)(OneSettingsDownloadResponseImpl *),&OneSettingsFreeDownloadResponse(OneSettingsDownloadResponseImpl *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadResponseImpl *,OneSettingsDownloadResponseImpl *,0,std::nullptr_t>>> &)
0x1400121b8  mov     ebx, eax
0x1400121ba  xor     r13d, r13d
0x1400121bd  test    eax, eax
0x1400121bf  jns     loc_14001227E
0x1400121c5  mov     eax, cs:dword_140027000
0x1400121cb  cmp     eax, 2
0x1400121ce  jbe     loc_14001211F
0x1400121d4  mov     rcx, cs:qword_140027018
0x1400121db  mov     rax, cs:qword_140027010
0x1400121e2  mov     rdx, 400000000000h
0x1400121ec  test    rdx, rax
0x1400121ef  jz      loc_14001211F
0x1400121f5  mov     rax, rcx
0x1400121f8  and     rax, rdx
0x1400121fb  cmp     rax, rcx
0x1400121fe  jnz     loc_14001211F
0x140012204  mov     [rbp+57h+var_B0], 1000000h
0x14001220c  mov     [rbp+57h+nNumberOfBytesToWrite], 2BCh
0x140012213  lea     rax, aGetfilefromone; "GetFileFromOneSettings"
0x14001221a  mov     [rbp+57h+var_B8], rax
0x14001221e  lea     rax, aOnecoreBaseDia_0; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140012225  mov     [rbp+57h+var_C0], rax
0x140012229  mov     [rbp+57h+cbMultiByte], ebx
0x14001222c  lea     rax, aGetfromonesett; "GetFromOneSetting failed."
0x140012233  mov     [rbp+57h+lpBuffer], rax
0x140012237  lea     rax, [rbp+57h+var_B0]
0x14001223b  mov     [rsp+120h+var_D8], rax
0x140012240  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x140012244  mov     [rsp+120h+var_E0], rax
0x140012249  lea     rax, [rbp+57h+var_B8]
0x14001224d  mov     [rsp+120h+var_E8], rax
0x140012252  lea     rax, [rbp+57h+var_C0]
0x140012256  mov     [rsp+120h+var_F0], rax
0x14001225b  lea     rax, [rbp+57h+cbMultiByte]
0x14001225f  mov     [rsp+120h+var_F8], rax
0x140012264  lea     rax, [rbp+57h+lpBuffer]
0x140012268  mov     [rsp+120h+lpOverlapped], rax
0x14001226d  lea     rdx, byte_140022739
0x140012274  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140012279  jmp     loc_14001211F
0x14001227e  cmp     dword ptr [r14], 0C8h
0x140012285  jnz     loc_14001211F
0x14001228b  lea     r9, [rbp+57h+nNumberOfBytesToWrite]; unsigned int *
0x14001228f  lea     r8, [rbp+57h+lpBuffer]; unsigned __int16 **
0x140012293  mov     edx, [rbp+57h+cbMultiByte]; cbMultiByte
0x140012296  mov     rcx, [rbp+57h+lpMultiByteStr]; lpMultiByteStr
0x14001229a  call    ?GetSiufPayloadFromJson@@YAJPEAEIPEAPEAGPEAI@Z; GetSiufPayloadFromJson(uchar *,uint,ushort * *,uint *)
0x14001229f  mov     ebx, eax
0x1400122a1  test    eax, eax
0x1400122a3  jns     loc_1400123CE
0x1400122a9  mov     eax, cs:dword_140027000
0x1400122af  cmp     ebx, 83750009h
0x1400122b5  jnz     short loc_140012327
0x1400122b7  mov     ebx, 5DD132h
0x1400122bc  cmp     eax, 5
0x1400122bf  jbe     short loc_14001231E
0x1400122c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400122c5  inc     rax
0x1400122c8  cmp     [r15+rax*2], r13w
0x1400122cd  jnz     short loc_1400122C5
0x1400122cf  mov     [rbp+57h+var_50], r15
0x1400122d3  lea     eax, ds:2[rax*2]
0x1400122da  mov     [rbp+57h+var_48], eax
0x1400122dd  mov     [rbp+57h+var_44], r13d
0x1400122e1  lea     rax, aSiufpayloadNot; "Siufpayload not found. Empty record."
0x1400122e8  mov     [rbp+57h+var_60], rax
0x1400122ec  mov     [rbp+57h+var_58], 25h ; '%'
0x1400122f4  lea     rax, [rbp+57h+var_80]
0x1400122f8  mov     [rsp+120h+var_F8], rax
0x1400122fd  mov     dword ptr [rsp+120h+lpOverlapped], 4
0x140012305  xor     r9d, r9d
0x140012308  xor     r8d, r8d
0x14001230b  lea     rdx, byte_140022715
0x140012312  lea     rcx, dword_140027000
0x140012319  call    _tlgWriteTransfer_EventWriteTransfer
0x14001231e  mov     rdi, [rbp+57h+lpBuffer]
0x140012322  jmp     loc_14001211F
0x140012327  cmp     eax, 2
0x14001232a  jbe     short loc_14001231E
0x14001232c  mov     rcx, cs:qword_140027018
0x140012333  mov     rax, cs:qword_140027010
0x14001233a  mov     rdx, 400000000000h
0x140012344  test    rdx, rax
0x140012347  jz      short loc_14001231E
0x140012349  mov     rax, rcx
0x14001234c  and     rax, rdx
0x14001234f  cmp     rax, rcx
0x140012352  jnz     short loc_14001231E
0x140012354  mov     [rbp+57h+var_B0], 1000000h
0x14001235c  mov     [rbp+57h+nNumberOfBytesToWrite], 2E6h
0x140012363  lea     rax, aGetfilefromone; "GetFileFromOneSettings"
0x14001236a  mov     [rbp+57h+var_B8], rax
0x14001236e  lea     rax, aOnecoreBaseDia_0; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140012375  mov     [rbp+57h+var_C0], rax
0x140012379  mov     [rbp+57h+cbMultiByte], ebx
0x14001237c  lea     rax, aGetsiufpayload; "GetSiufPayloadFromJson failed."
0x140012383  mov     [rbp+57h+var_88], rax
0x140012387  lea     rax, [rbp+57h+var_B0]
0x14001238b  mov     [rsp+120h+var_D8], rax
0x140012390  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x140012394  mov     [rsp+120h+var_E0], rax
0x140012399  lea     rax, [rbp+57h+var_B8]
0x14001239d  mov     [rsp+120h+var_E8], rax
0x1400123a2  lea     rax, [rbp+57h+var_C0]
0x1400123a6  mov     [rsp+120h+var_F0], rax
0x1400123ab  lea     rax, [rbp+57h+cbMultiByte]
0x1400123af  mov     [rsp+120h+var_F8], rax
0x1400123b4  lea     rax, [rbp+57h+var_88]
0x1400123b8  mov     [rsp+120h+lpOverlapped], rax
0x1400123bd  lea     rdx, byte_14002260D
0x1400123c4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400123c9  jmp     loc_14001231E
0x1400123ce  mov     [rsp+120h+lpOverlapped], r13
0x1400123d3  mov     edx, 40000000h
0x1400123d8  mov     r9d, 2
0x1400123de  lea     r8d, [r9-1]
0x1400123e2  mov     rcx, rsi
0x1400123e5  call    cs:__imp_CreateFile2
0x1400123eb  mov     r14, rax
0x1400123ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400123f2  cmp     r14, rax
0x1400123f5  jnz     short loc_140012415
0x1400123f7  call    cs:__imp_GetLastError
0x1400123fd  mov     ebx, eax
0x1400123ff  test    eax, eax
0x140012401  jle     loc_14001231E
0x140012407  movzx   ebx, ax
0x14001240a  or      ebx, 80070000h
0x140012410  jmp     loc_14001231E
0x140012415  mov     [rsp+120h+lpOverlapped], r13; lpOverlapped
0x14001241a  xor     r9d, r9d; lpNumberOfBytesWritten
0x14001241d  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140012421  mov     rdi, [rbp+57h+lpBuffer]
0x140012425  mov     rdx, rdi; lpBuffer
0x140012428  mov     rcx, r14; hFile
0x14001242b  call    cs:__imp_WriteFile
0x140012431  test    eax, eax
0x140012433  jnz     short loc_14001244C
0x140012435  call    cs:__imp_GetLastError
0x14001243b  mov     ebx, eax
0x14001243d  test    eax, eax
0x14001243f  jle     short loc_140012474
0x140012441  movzx   ebx, ax
0x140012444  or      ebx, 80070000h
0x14001244a  jmp     short loc_140012474
0x14001244c  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x140012450  mov     rcx, rsi; unsigned __int16 *
0x140012453  call    ?SaveETagToFile@@YAJPEBG0@Z; SaveETagToFile(ushort const *,ushort const *)
0x140012458  test    rdi, rdi
0x14001245b  jz      short loc_140012471
0x14001245d  call    cs:__imp_GetProcessHeap
0x140012463  mov     r8, rdi; lpMem
0x140012466  xor     edx, edx; dwFlags
0x140012468  mov     rcx, rax; hHeap
0x14001246b  call    cs:__imp_HeapFree
0x140012471  mov     rdi, r13
0x140012474  mov     rcx, r14; hObject
0x140012477  call    cs:__imp_CloseHandle
0x14001247d  jmp     loc_14001211F
```
