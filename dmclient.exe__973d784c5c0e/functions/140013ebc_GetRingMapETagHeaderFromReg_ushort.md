# GetRingMapETagHeaderFromReg(ushort * *)

- ea: `0x140013ebc`
- end: `0x1400143c3`
- name: `?GetRingMapETagHeaderFromReg@@YAJPEAPEAG@Z`
- size: `1287`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1400143cc`

## callees

- `0x140001418`
- `0x14000b904`
- `0x140013ebc`
- `0x1400156b4`
- `0x140019610`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140014398`
- `msvcrt!??3@YAXPEAX@Z` at `0x140014398`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013f71`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140014208`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013f71`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140014208`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400141b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014305`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400141b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014305`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400141a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400142ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001434c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001436c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400141a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400142ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001434c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001436c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014360`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014380`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014360`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014380`

## string_xrefs

- `0x14001400a`: `Failed determine ring map size in registry.`
- `0x1400140c3`: `Unexpected registry value type.`
- `0x14001418b`: `No data in the registry value.`
- `0x14001428b`: `Failed get ETag from registry.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRingMapETagHeaderFromReg(unsigned __int16 **a1)
{
  signed int StateSeparatedSiufRelativePath; // ebx
  const WCHAR *v3; // rdx
  LSTATUS ValueW; // eax
  int v5; // r8d
  int v6; // r9d
  void *v7; // rdi
  const char *v8; // rax
  char *v9; // rdx
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  void *pvData; // rax
  const WCHAR *v13; // rdx
  LSTATUS v14; // eax
  int v15; // r8d
  int v16; // r9d
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
  StateSeparatedSiufRelativePath = GetStateSeparatedSiufRelativePath(a1, lpSubKey);
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
      if ( (unsigned int)dword_140028000 > 2
        && (qword_140028010 & 0x400000000000LL) != 0
        && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v28 = 0x1000000;
        v24 = 601;
        v29 = "GetRingMapETagHeaderFromReg";
        v30 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
        v25 = StateSeparatedSiufRelativePath;
        v31 = (__int64)"Failed determine ring map size in registry.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          0,
          (unsigned int)&byte_140023917,
          v5,
          v6,
          (__int64)&v31,
          (__int64)&v25,
          (__int64)&v30,
          (__int64)&v29,
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
        if ( (unsigned int)dword_140028000 > 2
          && (qword_140028010 & 0x400000000000LL) != 0
          && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          v31 = 0x1000000;
          v25 = 639;
          v30 = "GetRingMapETagHeaderFromReg";
          v29 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
          v24 = StateSeparatedSiufRelativePath;
          v28 = (__int64)"Failed get ETag from registry.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            0,
            (unsigned int)byte_140023975,
            v15,
            v16,
            (__int64)&v28,
            (__int64)&v24,
            (__int64)&v29,
            (__int64)&v30,
            (__int64)&v25,
            (__int64)&v31);
        }
LABEL_37:
        if ( !v7 )
          goto LABEL_45;
        goto LABEL_44;
      }
      StateSeparatedSiufRelativePath = -2147024664;
      if ( (unsigned int)dword_140028000 > 2
        && (qword_140028010 & 0x400000000000LL) != 0
        && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v25 = 618;
        v30 = "GetRingMapETagHeaderFromReg";
        v29 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
        v24 = -2147024664;
        v8 = "No data in the registry value.";
        v9 = byte_140023CC3;
        goto LABEL_20;
      }
    }
    else
    {
      StateSeparatedSiufRelativePath = -2147024883;
      if ( (unsigned int)dword_140028000 > 2
        && (qword_140028010 & 0x400000000000LL) != 0
        && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v25 = 611;
        v30 = "GetRingMapETagHeaderFromReg";
        v29 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
        v24 = -2147024883;
        v8 = "Unexpected registry value type.";
        v9 = byte_140023C65;
LABEL_20:
        v28 = (__int64)v8;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          0,
          (_DWORD)v9,
          v5,
          v6,
          (__int64)&v28,
          (__int64)&v24,
          (__int64)&v29,
          (__int64)&v30,
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
0x140013ebc  push    rbp
0x140013ebe  push    rbx
0x140013ebf  push    rsi
0x140013ec0  push    rdi
0x140013ec1  push    r14
0x140013ec3  push    r15
0x140013ec5  lea     rbp, [rsp-2Fh]
0x140013eca  sub     rsp, 0B8h
0x140013ed1  mov     rax, cs:__security_cookie
0x140013ed8  xor     rax, rsp
0x140013edb  mov     [rbp+57h+var_40], rax
0x140013edf  mov     r14, rcx
0x140013ee2  mov     [rbp+57h+var_88], 0
0x140013ee9  mov     [rbp+57h+var_84], 0
0x140013ef0  mov     [rbp+57h+var_48], 7
0x140013ef8  mov     [rbp+57h+var_50], 0
0x140013f00  xor     eax, eax
0x140013f02  mov     word ptr [rbp+57h+lpSubKey], ax
0x140013f06  test    rcx, rcx
0x140013f09  jnz     short loc_140013F15
0x140013f0b  mov     ebx, 80004003h
0x140013f10  jmp     loc_14001438D
0x140013f15  mov     qword ptr [rcx], 0
0x140013f1c  lea     rdx, [rbp+57h+lpSubKey]
0x140013f20  call    ?GetStateSeparatedSiufRelativePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetStateSeparatedSiufRelativePath(ushort const *,std::wstring &)
0x140013f25  mov     ebx, eax
0x140013f27  test    eax, eax
0x140013f29  js      loc_14001438D
0x140013f2f  lea     rdx, [rbp+57h+lpSubKey]
0x140013f33  cmp     [rbp+57h+var_48], 8
0x140013f38  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140013f3d  lea     rax, [rbp+57h+var_88]
0x140013f41  mov     [rsp+0E0h+pcbData], rax; pcbData
0x140013f46  mov     [rsp+0E0h+pvData], 0; pvData
0x140013f4f  lea     rax, [rbp+57h+var_84]
0x140013f53  mov     [rsp+0E0h+pdwType], rax; pdwType
0x140013f58  mov     esi, 2
0x140013f5d  mov     r9d, esi; dwFlags
0x140013f60  lea     r8, aRmtag; "RMTag"
0x140013f67  mov     r15, 0FFFFFFFF80000002h
0x140013f6e  mov     rcx, r15; hkey
0x140013f71  call    cs:__imp_RegGetValueW
0x140013f78  nop     dword ptr [rax+rax+00h]
0x140013f7d  mov     ebx, eax
0x140013f7f  cmp     eax, esi
0x140013f81  jnz     short loc_140013F8D
0x140013f83  mov     ebx, 5DD133h
0x140013f88  jmp     loc_14001438D
0x140013f8d  test    eax, eax
0x140013f8f  jz      loc_140014052
0x140013f95  xor     edi, edi
0x140013f97  test    eax, eax
0x140013f99  jle     short loc_140013FA4
0x140013f9b  movzx   ebx, ax
0x140013f9e  or      ebx, 80070000h
0x140013fa4  mov     eax, cs:dword_140028000
0x140013faa  cmp     eax, esi
0x140013fac  jbe     loc_1400142D8
0x140013fb2  mov     rdx, cs:qword_140028018
0x140013fb9  mov     rax, cs:qword_140028010
0x140013fc0  mov     rcx, 400000000000h
0x140013fca  test    rcx, rax
0x140013fcd  jz      loc_1400142D8
0x140013fd3  mov     rax, rdx
0x140013fd6  and     rax, rcx
0x140013fd9  cmp     rax, rdx
0x140013fdc  jnz     loc_1400142D8
0x140013fe2  mov     [rbp+57h+var_80], 1000000h
0x140013fea  mov     [rbp+57h+var_90], 259h
0x140013ff1  lea     rax, aGetringmapetag; "GetRingMapETagHeaderFromReg"
0x140013ff8  mov     [rbp+57h+var_78], rax
0x140013ffc  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014003  mov     [rbp+57h+var_70], rax
0x140014007  mov     [rbp+57h+var_8C], ebx
0x14001400a  lea     rax, aFailedDetermin; "Failed determine ring map size in regis"...
0x140014011  mov     [rbp+57h+var_68], rax
0x140014015  lea     rax, [rbp+57h+var_80]
0x140014019  mov     [rsp+0E0h+var_98], rax
0x14001401e  lea     rax, [rbp+57h+var_90]
0x140014022  mov     [rsp+0E0h+var_A0], rax
0x140014027  lea     rax, [rbp+57h+var_78]
0x14001402b  mov     [rsp+0E0h+var_A8], rax
0x140014030  lea     rax, [rbp+57h+var_70]
0x140014034  mov     [rsp+0E0h+pcbData], rax
0x140014039  lea     rax, [rbp+57h+var_8C]
0x14001403d  mov     [rsp+0E0h+pvData], rax
0x140014042  lea     rax, [rbp+57h+var_68]
0x140014046  lea     rdx, byte_140023917
0x14001404d  jmp     loc_1400142CE
0x140014052  cmp     [rbp+57h+var_84], 1
0x140014056  jz      loc_14001411D
0x14001405c  mov     ebx, 8007000Dh
0x140014061  mov     eax, cs:dword_140028000
0x140014067  cmp     eax, esi
0x140014069  jbe     loc_14001438D
0x14001406f  mov     rdx, cs:qword_140028018
0x140014076  mov     rax, cs:qword_140028010
0x14001407d  mov     rcx, 400000000000h
0x140014087  test    rcx, rax
0x14001408a  jz      loc_14001438D
0x140014090  mov     rax, rdx
0x140014093  and     rax, rcx
0x140014096  cmp     rax, rdx
0x140014099  jnz     loc_14001438D
0x14001409f  mov     [rbp+57h+var_8C], 263h
0x1400140a6  lea     rax, aGetringmapetag; "GetRingMapETagHeaderFromReg"
0x1400140ad  mov     [rbp+57h+var_70], rax
0x1400140b1  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400140b8  mov     [rbp+57h+var_78], rax
0x1400140bc  mov     [rbp+57h+var_90], 8007000Dh
0x1400140c3  lea     rax, aUnexpectedRegi; "Unexpected registry value type."
0x1400140ca  lea     rdx, byte_140023C65
0x1400140d1  mov     [rbp+57h+var_80], rax
0x1400140d5  lea     rax, [rbp+57h+var_68]
0x1400140d9  mov     [rsp+0E0h+var_98], rax
0x1400140de  lea     rax, [rbp+57h+var_8C]
0x1400140e2  mov     [rsp+0E0h+var_A0], rax
0x1400140e7  lea     rax, [rbp+57h+var_70]
0x1400140eb  mov     [rsp+0E0h+var_A8], rax
0x1400140f0  lea     rax, [rbp+57h+var_78]
0x1400140f4  mov     [rsp+0E0h+pcbData], rax
0x1400140f9  lea     rax, [rbp+57h+var_90]
0x1400140fd  mov     [rsp+0E0h+pvData], rax
0x140014102  lea     rax, [rbp+57h+var_80]
0x140014106  mov     [rsp+0E0h+pdwType], rax
0x14001410b  mov     [rbp+57h+var_68], 1000000h
0x140014113  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140014118  jmp     loc_14001438D
0x14001411d  mov     eax, [rbp+57h+var_88]
0x140014120  test    eax, eax
0x140014122  jnz     short loc_14001419E
0x140014124  mov     ebx, 800700E8h
0x140014129  mov     eax, cs:dword_140028000
0x14001412f  cmp     eax, esi
0x140014131  jbe     loc_14001438D
0x140014137  mov     rdx, cs:qword_140028018
0x14001413e  mov     rax, cs:qword_140028010
0x140014145  mov     rcx, 400000000000h
0x14001414f  test    rcx, rax
0x140014152  jz      loc_14001438D
0x140014158  mov     rax, rdx
0x14001415b  and     rax, rcx
0x14001415e  cmp     rax, rdx
0x140014161  jnz     loc_14001438D
0x140014167  mov     [rbp+57h+var_8C], 26Ah
0x14001416e  lea     rax, aGetringmapetag; "GetRingMapETagHeaderFromReg"
0x140014175  mov     [rbp+57h+var_70], rax
0x140014179  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014180  mov     [rbp+57h+var_78], rax
0x140014184  mov     [rbp+57h+var_90], 800700E8h
0x14001418b  lea     rax, aNoDataInTheReg; "No data in the registry value."
0x140014192  lea     rdx, byte_140023CC3
0x140014199  jmp     loc_1400140D1
0x14001419e  mov     rbx, rax
0x1400141a1  call    cs:__imp_GetProcessHeap
0x1400141a8  nop     dword ptr [rax+rax+00h]
0x1400141ad  mov     r8, rbx; dwBytes
0x1400141b0  mov     edx, 8; dwFlags
0x1400141b5  mov     rcx, rax; hHeap
0x1400141b8  call    cs:__imp_HeapAlloc
0x1400141bf  nop     dword ptr [rax+rax+00h]
0x1400141c4  mov     rdi, rax
0x1400141c7  test    rax, rax
0x1400141ca  jnz     short loc_1400141D6
0x1400141cc  mov     ebx, 8007000Eh
0x1400141d1  jmp     loc_14001438D
0x1400141d6  lea     rdx, [rbp+57h+lpSubKey]
0x1400141da  cmp     [rbp+57h+var_48], 8
0x1400141df  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1400141e4  lea     rax, [rbp+57h+var_88]
0x1400141e8  mov     [rsp+0E0h+pcbData], rax; pcbData
0x1400141ed  mov     [rsp+0E0h+pvData], rdi; pvData
0x1400141f2  lea     rax, [rbp+57h+var_84]
0x1400141f6  mov     [rsp+0E0h+pdwType], rax; pdwType
0x1400141fb  mov     r9d, esi; dwFlags
0x1400141fe  lea     r8, aRmtag; "RMTag"
0x140014205  mov     rcx, r15; hkey
0x140014208  call    cs:__imp_RegGetValueW
0x14001420f  nop     dword ptr [rax+rax+00h]
0x140014214  mov     ebx, eax
0x140014216  test    eax, eax
0x140014218  jz      loc_1400142E6
0x14001421e  jle     short loc_140014229
0x140014220  movzx   ebx, ax
0x140014223  or      ebx, 80070000h
0x140014229  mov     eax, cs:dword_140028000
0x14001422f  cmp     eax, esi
0x140014231  jbe     loc_1400142D8
0x140014237  mov     rdx, cs:qword_140028018
0x14001423e  mov     rax, cs:qword_140028010
0x140014245  mov     rcx, 400000000000h
0x14001424f  test    rcx, rax
0x140014252  jz      loc_1400142D8
0x140014258  mov     rax, rdx
0x14001425b  and     rax, rcx
0x14001425e  cmp     rax, rdx
0x140014261  jnz     short loc_1400142D8
0x140014263  mov     [rbp+57h+var_68], 1000000h
0x14001426b  mov     [rbp+57h+var_8C], 27Fh
0x140014272  lea     rax, aGetringmapetag; "GetRingMapETagHeaderFromReg"
0x140014279  mov     [rbp+57h+var_70], rax
0x14001427d  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014284  mov     [rbp+57h+var_78], rax
0x140014288  mov     [rbp+57h+var_90], ebx
0x14001428b  lea     rax, aFailedGetEtagF; "Failed get ETag from registry."
0x140014292  mov     [rbp+57h+var_80], rax
0x140014296  lea     rax, [rbp+57h+var_68]
0x14001429a  mov     [rsp+0E0h+var_98], rax
0x14001429f  lea     rax, [rbp+57h+var_8C]
0x1400142a3  mov     [rsp+0E0h+var_A0], rax
0x1400142a8  lea     rax, [rbp+57h+var_70]
0x1400142ac  mov     [rsp+0E0h+var_A8], rax
0x1400142b1  lea     rax, [rbp+57h+var_78]
0x1400142b5  mov     [rsp+0E0h+pcbData], rax
0x1400142ba  lea     rax, [rbp+57h+var_90]
0x1400142be  mov     [rsp+0E0h+pvData], rax
0x1400142c3  lea     rax, [rbp+57h+var_80]
0x1400142c7  lea     rdx, byte_140023975
0x1400142ce  mov     [rsp+0E0h+pdwType], rax
0x1400142d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400142d8  test    rdi, rdi
0x1400142db  jz      loc_14001438D
0x1400142e1  jmp     loc_14001436C
0x1400142e6  mov     r15d, [rbp+57h+var_88]
0x1400142ea  add     r15d, 1Ch
0x1400142ee  call    cs:__imp_GetProcessHeap
0x1400142f5  nop     dword ptr [rax+rax+00h]
0x1400142fa  mov     rcx, rax; hHeap
0x1400142fd  mov     r8d, r15d; dwBytes
0x140014300  mov     edx, 8; dwFlags
0x140014305  call    cs:__imp_HeapAlloc
0x14001430c  nop     dword ptr [rax+rax+00h]
0x140014311  mov     rsi, rax
0x140014314  test    rax, rax
0x140014317  jnz     short loc_140014320
0x140014319  mov     ebx, 8007000Eh
0x14001431e  jmp     short loc_14001436C
0x140014320  mov     edx, r15d
0x140014323  shr     rdx, 1; unsigned __int64
0x140014326  mov     [rsp+0E0h+pdwType], rdi
0x14001432b  lea     r9, aIfNoneMatch; "If-None-Match:"
0x140014332  lea     r8, aSS_1; "%s%s"
0x140014339  mov     rcx, rsi; unsigned __int16 *
0x14001433c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014341  mov     ebx, eax
0x140014343  test    eax, eax
0x140014345  js      short loc_14001434C
0x140014347  mov     [r14], rsi
0x14001434a  jmp     short loc_14001436C
0x14001434c  call    cs:__imp_GetProcessHeap
0x140014353  nop     dword ptr [rax+rax+00h]
0x140014358  mov     rcx, rax; hHeap
0x14001435b  mov     r8, rsi; lpMem
0x14001435e  xor     edx, edx; dwFlags
0x140014360  call    cs:__imp_HeapFree
0x140014367  nop     dword ptr [rax+rax+00h]
0x14001436c  call    cs:__imp_GetProcessHeap
0x140014373  nop     dword ptr [rax+rax+00h]
0x140014378  mov     rcx, rax; hHeap
0x14001437b  mov     r8, rdi; lpMem
0x14001437e  xor     edx, edx; dwFlags
0x140014380  call    cs:__imp_HeapFree
0x140014387  nop     dword ptr [rax+rax+00h]
0x14001438c  nop
0x14001438d  cmp     [rbp+57h+var_48], 8
0x140014392  jb      short loc_1400143A4
0x140014394  mov     rcx, [rbp+57h+lpSubKey]
0x140014398  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14001439f  nop     dword ptr [rax+rax+00h]
0x1400143a4  mov     eax, ebx
0x1400143a6  mov     rcx, [rbp+57h+var_40]
0x1400143aa  xor     rcx, rsp; StackCookie
0x1400143ad  call    __security_check_cookie
0x1400143b2  add     rsp, 0B8h
0x1400143b9  pop     r15
0x1400143bb  pop     r14
0x1400143bd  pop     rdi
0x1400143be  pop     rsi
0x1400143bf  pop     rbx
0x1400143c0  pop     rbp
0x1400143c1  retn
```
