# GetRingMapETagHeaderFromReg(ushort * *)

- ea: `0x1400144a4`
- end: `0x140014965`
- name: `?GetRingMapETagHeaderFromReg@@YAJPEAPEAG@Z`
- size: `1217`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x140015aec`

## callees

- `0x140001414`
- `0x14000b5c4`
- `0x1400144a4`
- `0x14001785c`
- `0x1400187e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140014941`
- `msvcrt!??3@YAXPEAX@Z` at `0x140014941`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140014559`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400147de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140014559`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400147de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014794`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400148cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014794`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400148cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014783`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400148bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001490d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014921`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014783`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400148bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001490d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014921`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001491b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001492f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001491b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001492f`

## string_xrefs

- `0x1400145ec`: `Failed determine ring map size in registry.`
- `0x1400146a5`: `Unexpected registry value type.`
- `0x14001476d`: `No data in the registry value.`
- `0x14001485b`: `Failed get ETag from registry.`

## pseudocode

```c
__int64 __fastcall GetRingMapETagHeaderFromReg(unsigned __int16 **a1)
{
  int StateSeparatedSiufRelativePath; // ebx
  const WCHAR *v3; // rdx
  LSTATUS ValueW; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  void *v7; // rdi
  const char *v8; // rax
  char *v9; // rdx
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  void *pvData; // rax
  const WCHAR *v13; // rdx
  LSTATUS v14; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  DWORD v17; // r15d
  HANDLE v18; // rax
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rsi
  HANDLE v21; // rax
  HANDLE v22; // rax
  int v24; // [rsp+50h] [rbp-39h] BYREF
  int v25; // [rsp+54h] [rbp-35h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-31h] BYREF
  DWORD pdwType; // [rsp+5Ch] [rbp-2Dh] BYREF
  __int64 v28; // [rsp+60h] [rbp-29h] BYREF
  const char *v29; // [rsp+68h] [rbp-21h] BYREF
  const char *v30; // [rsp+70h] [rbp-19h] BYREF
  __int64 v31; // [rsp+78h] [rbp-11h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int64 v33; // [rsp+98h] [rbp+Fh]

  pcbData = 0;
  pdwType = 0;
  v33 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( !a1 )
  {
    StateSeparatedSiufRelativePath = -2147467261;
    goto LABEL_45;
  }
  *a1 = 0;
  StateSeparatedSiufRelativePath = GetStateSeparatedSiufRelativePath((__int64)a1, lpSubKey);
  if ( StateSeparatedSiufRelativePath >= 0 )
  {
    v3 = (const WCHAR *)lpSubKey;
    if ( v33 >= 8 )
      v3 = lpSubKey[0];
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v3, L"RMTag", 2u, &pdwType, 0, &pcbData);
    StateSeparatedSiufRelativePath = ValueW;
    if ( ValueW == 2 )
    {
      StateSeparatedSiufRelativePath = 6148403;
      goto LABEL_45;
    }
    if ( ValueW )
    {
      v7 = 0;
      if ( ValueW > 0 )
        StateSeparatedSiufRelativePath = (unsigned __int16)ValueW | 0x80070000;
      if ( (unsigned int)dword_140027000 > 2
        && (qword_140027010 & 0x400000000000LL) != 0
        && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v28 = 0x1000000;
        v24 = 601;
        v29 = "GetRingMapETagHeaderFromReg";
        v30 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
        v25 = StateSeparatedSiufRelativePath;
        v31 = (__int64)"Failed determine ring map size in registry.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          0x400000000000LL,
          (__int64)&byte_14002290F,
          v5,
          v6,
          (const unsigned __int16 **)&v31,
          (__int64)&v25,
          (const unsigned __int16 **)&v30,
          (const unsigned __int16 **)&v29,
          (__int64)&v24,
          (__int64)&v28);
      }
      goto LABEL_37;
    }
    if ( pdwType == 1 )
    {
      if ( pcbData )
      {
        v10 = pcbData;
        ProcessHeap = GetProcessHeap();
        pvData = HeapAlloc(ProcessHeap, 8u, v10);
        v7 = pvData;
        if ( !pvData )
        {
          StateSeparatedSiufRelativePath = -2147024882;
          goto LABEL_45;
        }
        v13 = (const WCHAR *)lpSubKey;
        if ( v33 >= 8 )
          v13 = lpSubKey[0];
        v14 = RegGetValueW(HKEY_LOCAL_MACHINE, v13, L"RMTag", 2u, &pdwType, pvData, &pcbData);
        StateSeparatedSiufRelativePath = v14;
        if ( !v14 )
        {
          v17 = pcbData + 28;
          v18 = GetProcessHeap();
          v19 = (unsigned __int16 *)HeapAlloc(v18, 8u, v17);
          v20 = v19;
          if ( v19 )
          {
            StateSeparatedSiufRelativePath = StringCchPrintfW(
                                               v19,
                                               (unsigned __int64)v17 >> 1,
                                               L"%s%s",
                                               L"If-None-Match:",
                                               v7);
            if ( StateSeparatedSiufRelativePath < 0 )
            {
              v21 = GetProcessHeap();
              HeapFree(v21, 0, v20);
            }
            else
            {
              *a1 = v20;
            }
          }
          else
          {
            StateSeparatedSiufRelativePath = -2147024882;
          }
LABEL_44:
          v22 = GetProcessHeap();
          HeapFree(v22, 0, v7);
          goto LABEL_45;
        }
        if ( v14 > 0 )
          StateSeparatedSiufRelativePath = (unsigned __int16)v14 | 0x80070000;
        if ( (unsigned int)dword_140027000 > 2
          && (qword_140027010 & 0x400000000000LL) != 0
          && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
        {
          v31 = 0x1000000;
          v25 = 639;
          v30 = "GetRingMapETagHeaderFromReg";
          v29 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
          v24 = StateSeparatedSiufRelativePath;
          v28 = (__int64)"Failed get ETag from registry.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            0x400000000000LL,
            (__int64)byte_14002296D,
            v15,
            v16,
            (const unsigned __int16 **)&v28,
            (__int64)&v24,
            (const unsigned __int16 **)&v29,
            (const unsigned __int16 **)&v30,
            (__int64)&v25,
            (__int64)&v31);
        }
LABEL_37:
        if ( !v7 )
          goto LABEL_45;
        goto LABEL_44;
      }
      StateSeparatedSiufRelativePath = -2147024664;
      if ( (unsigned int)dword_140027000 > 2
        && (qword_140027010 & 0x400000000000LL) != 0
        && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v25 = 618;
        v30 = "GetRingMapETagHeaderFromReg";
        v29 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
        v24 = -2147024664;
        v8 = "No data in the registry value.";
        v9 = byte_140022CBB;
        goto LABEL_20;
      }
    }
    else
    {
      StateSeparatedSiufRelativePath = -2147024883;
      if ( (unsigned int)dword_140027000 > 2
        && (qword_140027010 & 0x400000000000LL) != 0
        && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v25 = 611;
        v30 = "GetRingMapETagHeaderFromReg";
        v29 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
        v24 = -2147024883;
        v8 = "Unexpected registry value type.";
        v9 = byte_140022C5D;
LABEL_20:
        v28 = (__int64)v8;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          0x400000000000LL,
          (__int64)v9,
          v5,
          v6,
          (const unsigned __int16 **)&v28,
          (__int64)&v24,
          (const unsigned __int16 **)&v29,
          (const unsigned __int16 **)&v30,
          (__int64)&v25,
          (__int64)&v31);
      }
    }
  }
LABEL_45:
  if ( v33 >= 8 )
    operator delete((void *)lpSubKey[0]);
  return (unsigned int)StateSeparatedSiufRelativePath;
}

```

## disassembly

```asm
0x1400144a4  push    rbp
0x1400144a6  push    rbx
0x1400144a7  push    rsi
0x1400144a8  push    rdi
0x1400144a9  push    r14
0x1400144ab  push    r15
0x1400144ad  lea     rbp, [rsp-2Fh]
0x1400144b2  sub     rsp, 0B8h
0x1400144b9  mov     rax, cs:__security_cookie
0x1400144c0  xor     rax, rsp
0x1400144c3  mov     [rbp+57h+var_40], rax
0x1400144c7  mov     r14, rcx
0x1400144ca  mov     [rbp+57h+var_88], 0
0x1400144d1  mov     [rbp+57h+var_84], 0
0x1400144d8  mov     [rbp+57h+var_48], 7
0x1400144e0  mov     [rbp+57h+var_50], 0
0x1400144e8  xor     eax, eax
0x1400144ea  mov     word ptr [rbp+57h+lpSubKey], ax
0x1400144ee  test    rcx, rcx
0x1400144f1  jnz     short loc_1400144FD
0x1400144f3  mov     ebx, 80004003h
0x1400144f8  jmp     loc_140014936
0x1400144fd  mov     qword ptr [rcx], 0
0x140014504  lea     rdx, [rbp+57h+lpSubKey]
0x140014508  call    ?GetStateSeparatedSiufRelativePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetStateSeparatedSiufRelativePath(ushort const *,std::wstring &)
0x14001450d  mov     ebx, eax
0x14001450f  test    eax, eax
0x140014511  js      loc_140014936
0x140014517  lea     rdx, [rbp+57h+lpSubKey]
0x14001451b  cmp     [rbp+57h+var_48], 8
0x140014520  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140014525  lea     rax, [rbp+57h+var_88]
0x140014529  mov     [rsp+0E0h+pcbData], rax; pcbData
0x14001452e  mov     [rsp+0E0h+pvData], 0; pvData
0x140014537  lea     rax, [rbp+57h+var_84]
0x14001453b  mov     [rsp+0E0h+pdwType], rax; pdwType
0x140014540  mov     esi, 2
0x140014545  mov     r9d, esi; dwFlags
0x140014548  lea     r8, aRmtag; "RMTag"
0x14001454f  mov     r15, 0FFFFFFFF80000002h
0x140014556  mov     rcx, r15; hkey
0x140014559  call    cs:__imp_RegGetValueW
0x14001455f  mov     ebx, eax
0x140014561  cmp     eax, esi
0x140014563  jnz     short loc_14001456F
0x140014565  mov     ebx, 5DD133h
0x14001456a  jmp     loc_140014936
0x14001456f  test    eax, eax
0x140014571  jz      loc_140014634
0x140014577  xor     edi, edi
0x140014579  test    eax, eax
0x14001457b  jle     short loc_140014586
0x14001457d  movzx   ebx, ax
0x140014580  or      ebx, 80070000h
0x140014586  mov     eax, cs:dword_140027000
0x14001458c  cmp     eax, esi
0x14001458e  jbe     loc_1400148A8
0x140014594  mov     rdx, cs:qword_140027018
0x14001459b  mov     rax, cs:qword_140027010
0x1400145a2  mov     rcx, 400000000000h
0x1400145ac  test    rcx, rax
0x1400145af  jz      loc_1400148A8
0x1400145b5  mov     rax, rdx
0x1400145b8  and     rax, rcx
0x1400145bb  cmp     rax, rdx
0x1400145be  jnz     loc_1400148A8
0x1400145c4  mov     [rbp+57h+var_80], 1000000h
0x1400145cc  mov     [rbp+57h+var_90], 259h
0x1400145d3  lea     rax, aGetringmapetag; "GetRingMapETagHeaderFromReg"
0x1400145da  mov     [rbp+57h+var_78], rax
0x1400145de  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400145e5  mov     [rbp+57h+var_70], rax
0x1400145e9  mov     [rbp+57h+var_8C], ebx
0x1400145ec  lea     rax, aFailedDetermin; "Failed determine ring map size in regis"...
0x1400145f3  mov     [rbp+57h+var_68], rax
0x1400145f7  lea     rax, [rbp+57h+var_80]
0x1400145fb  mov     [rsp+0E0h+var_98], rax
0x140014600  lea     rax, [rbp+57h+var_90]
0x140014604  mov     [rsp+0E0h+var_A0], rax
0x140014609  lea     rax, [rbp+57h+var_78]
0x14001460d  mov     [rsp+0E0h+var_A8], rax
0x140014612  lea     rax, [rbp+57h+var_70]
0x140014616  mov     [rsp+0E0h+pcbData], rax
0x14001461b  lea     rax, [rbp+57h+var_8C]
0x14001461f  mov     [rsp+0E0h+pvData], rax
0x140014624  lea     rax, [rbp+57h+var_68]
0x140014628  lea     rdx, byte_14002290F
0x14001462f  jmp     loc_14001489E
0x140014634  cmp     [rbp+57h+var_84], 1
0x140014638  jz      loc_1400146FF
0x14001463e  mov     ebx, 8007000Dh
0x140014643  mov     eax, cs:dword_140027000
0x140014649  cmp     eax, esi
0x14001464b  jbe     loc_140014936
0x140014651  mov     rdx, cs:qword_140027018
0x140014658  mov     rax, cs:qword_140027010
0x14001465f  mov     rcx, 400000000000h
0x140014669  test    rcx, rax
0x14001466c  jz      loc_140014936
0x140014672  mov     rax, rdx
0x140014675  and     rax, rcx
0x140014678  cmp     rax, rdx
0x14001467b  jnz     loc_140014936
0x140014681  mov     [rbp+57h+var_8C], 263h
0x140014688  lea     rax, aGetringmapetag; "GetRingMapETagHeaderFromReg"
0x14001468f  mov     [rbp+57h+var_70], rax
0x140014693  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14001469a  mov     [rbp+57h+var_78], rax
0x14001469e  mov     [rbp+57h+var_90], 8007000Dh
0x1400146a5  lea     rax, aUnexpectedRegi; "Unexpected registry value type."
0x1400146ac  lea     rdx, byte_140022C5D
0x1400146b3  mov     [rbp+57h+var_80], rax
0x1400146b7  lea     rax, [rbp+57h+var_68]
0x1400146bb  mov     [rsp+0E0h+var_98], rax
0x1400146c0  lea     rax, [rbp+57h+var_8C]
0x1400146c4  mov     [rsp+0E0h+var_A0], rax
0x1400146c9  lea     rax, [rbp+57h+var_70]
0x1400146cd  mov     [rsp+0E0h+var_A8], rax
0x1400146d2  lea     rax, [rbp+57h+var_78]
0x1400146d6  mov     [rsp+0E0h+pcbData], rax
0x1400146db  lea     rax, [rbp+57h+var_90]
0x1400146df  mov     [rsp+0E0h+pvData], rax
0x1400146e4  lea     rax, [rbp+57h+var_80]
0x1400146e8  mov     [rsp+0E0h+pdwType], rax
0x1400146ed  mov     [rbp+57h+var_68], 1000000h
0x1400146f5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400146fa  jmp     loc_140014936
0x1400146ff  mov     eax, [rbp+57h+var_88]
0x140014702  test    eax, eax
0x140014704  jnz     short loc_140014780
0x140014706  mov     ebx, 800700E8h
0x14001470b  mov     eax, cs:dword_140027000
0x140014711  cmp     eax, esi
0x140014713  jbe     loc_140014936
0x140014719  mov     rdx, cs:qword_140027018
0x140014720  mov     rax, cs:qword_140027010
0x140014727  mov     rcx, 400000000000h
0x140014731  test    rcx, rax
0x140014734  jz      loc_140014936
0x14001473a  mov     rax, rdx
0x14001473d  and     rax, rcx
0x140014740  cmp     rax, rdx
0x140014743  jnz     loc_140014936
0x140014749  mov     [rbp+57h+var_8C], 26Ah
0x140014750  lea     rax, aGetringmapetag; "GetRingMapETagHeaderFromReg"
0x140014757  mov     [rbp+57h+var_70], rax
0x14001475b  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014762  mov     [rbp+57h+var_78], rax
0x140014766  mov     [rbp+57h+var_90], 800700E8h
0x14001476d  lea     rax, aNoDataInTheReg; "No data in the registry value."
0x140014774  lea     rdx, byte_140022CBB
0x14001477b  jmp     loc_1400146B3
0x140014780  mov     rbx, rax
0x140014783  call    cs:__imp_GetProcessHeap
0x140014789  mov     r8, rbx; dwBytes
0x14001478c  mov     edx, 8; dwFlags
0x140014791  mov     rcx, rax; hHeap
0x140014794  call    cs:__imp_HeapAlloc
0x14001479a  mov     rdi, rax
0x14001479d  test    rax, rax
0x1400147a0  jnz     short loc_1400147AC
0x1400147a2  mov     ebx, 8007000Eh
0x1400147a7  jmp     loc_140014936
0x1400147ac  lea     rdx, [rbp+57h+lpSubKey]
0x1400147b0  cmp     [rbp+57h+var_48], 8
0x1400147b5  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1400147ba  lea     rax, [rbp+57h+var_88]
0x1400147be  mov     [rsp+0E0h+pcbData], rax; pcbData
0x1400147c3  mov     [rsp+0E0h+pvData], rdi; pvData
0x1400147c8  lea     rax, [rbp+57h+var_84]
0x1400147cc  mov     [rsp+0E0h+pdwType], rax; pdwType
0x1400147d1  mov     r9d, esi; dwFlags
0x1400147d4  lea     r8, aRmtag; "RMTag"
0x1400147db  mov     rcx, r15; hkey
0x1400147de  call    cs:__imp_RegGetValueW
0x1400147e4  mov     ebx, eax
0x1400147e6  test    eax, eax
0x1400147e8  jz      loc_1400148B3
0x1400147ee  jle     short loc_1400147F9
0x1400147f0  movzx   ebx, ax
0x1400147f3  or      ebx, 80070000h
0x1400147f9  mov     eax, cs:dword_140027000
0x1400147ff  cmp     eax, esi
0x140014801  jbe     loc_1400148A8
0x140014807  mov     rdx, cs:qword_140027018
0x14001480e  mov     rax, cs:qword_140027010
0x140014815  mov     rcx, 400000000000h
0x14001481f  test    rcx, rax
0x140014822  jz      loc_1400148A8
0x140014828  mov     rax, rdx
0x14001482b  and     rax, rcx
0x14001482e  cmp     rax, rdx
0x140014831  jnz     short loc_1400148A8
0x140014833  mov     [rbp+57h+var_68], 1000000h
0x14001483b  mov     [rbp+57h+var_8C], 27Fh
0x140014842  lea     rax, aGetringmapetag; "GetRingMapETagHeaderFromReg"
0x140014849  mov     [rbp+57h+var_70], rax
0x14001484d  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014854  mov     [rbp+57h+var_78], rax
0x140014858  mov     [rbp+57h+var_90], ebx
0x14001485b  lea     rax, aFailedGetEtagF; "Failed get ETag from registry."
0x140014862  mov     [rbp+57h+var_80], rax
0x140014866  lea     rax, [rbp+57h+var_68]
0x14001486a  mov     [rsp+0E0h+var_98], rax
0x14001486f  lea     rax, [rbp+57h+var_8C]
0x140014873  mov     [rsp+0E0h+var_A0], rax
0x140014878  lea     rax, [rbp+57h+var_70]
0x14001487c  mov     [rsp+0E0h+var_A8], rax
0x140014881  lea     rax, [rbp+57h+var_78]
0x140014885  mov     [rsp+0E0h+pcbData], rax
0x14001488a  lea     rax, [rbp+57h+var_90]
0x14001488e  mov     [rsp+0E0h+pvData], rax
0x140014893  lea     rax, [rbp+57h+var_80]
0x140014897  lea     rdx, byte_14002296D
0x14001489e  mov     [rsp+0E0h+pdwType], rax
0x1400148a3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400148a8  test    rdi, rdi
0x1400148ab  jz      loc_140014936
0x1400148b1  jmp     short loc_140014921
0x1400148b3  mov     r15d, [rbp+57h+var_88]
0x1400148b7  add     r15d, 1Ch
0x1400148bb  call    cs:__imp_GetProcessHeap
0x1400148c1  mov     rcx, rax; hHeap
0x1400148c4  mov     r8d, r15d; dwBytes
0x1400148c7  mov     edx, 8; dwFlags
0x1400148cc  call    cs:__imp_HeapAlloc
0x1400148d2  mov     rsi, rax
0x1400148d5  test    rax, rax
0x1400148d8  jnz     short loc_1400148E1
0x1400148da  mov     ebx, 8007000Eh
0x1400148df  jmp     short loc_140014921
0x1400148e1  mov     edx, r15d
0x1400148e4  shr     rdx, 1; unsigned __int64
0x1400148e7  mov     [rsp+0E0h+pdwType], rdi
0x1400148ec  lea     r9, aIfNoneMatch; "If-None-Match:"
0x1400148f3  lea     r8, aSS_1; "%s%s"
0x1400148fa  mov     rcx, rsi; unsigned __int16 *
0x1400148fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014902  mov     ebx, eax
0x140014904  test    eax, eax
0x140014906  js      short loc_14001490D
0x140014908  mov     [r14], rsi
0x14001490b  jmp     short loc_140014921
0x14001490d  call    cs:__imp_GetProcessHeap
0x140014913  mov     rcx, rax; hHeap
0x140014916  mov     r8, rsi; lpMem
0x140014919  xor     edx, edx; dwFlags
0x14001491b  call    cs:__imp_HeapFree
0x140014921  call    cs:__imp_GetProcessHeap
0x140014927  mov     rcx, rax; hHeap
0x14001492a  mov     r8, rdi; lpMem
0x14001492d  xor     edx, edx; dwFlags
0x14001492f  call    cs:__imp_HeapFree
0x140014935  nop
0x140014936  cmp     [rbp+57h+var_48], 8
0x14001493b  jb      short loc_140014947
0x14001493d  mov     rcx, [rbp+57h+lpSubKey]
0x140014941  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140014947  mov     eax, ebx
0x140014949  mov     rcx, [rbp+57h+var_40]
0x14001494d  xor     rcx, rsp; StackCookie
0x140014950  call    __security_check_cookie
0x140014955  add     rsp, 0B8h
0x14001495c  pop     r15
0x14001495e  pop     r14
0x140014960  pop     rdi
0x140014961  pop     rsi
0x140014962  pop     rbx
0x140014963  pop     rbp
0x140014964  retn
```
