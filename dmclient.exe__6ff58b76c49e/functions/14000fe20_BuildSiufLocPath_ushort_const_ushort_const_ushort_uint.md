# BuildSiufLocPath(ushort const *,ushort const *,ushort *,uint)

- ea: `0x14000fe20`
- end: `0x14001004a`
- name: `?BuildSiufLocPath@@YAJPEBG0PEAGI@Z`
- size: `554`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400105d8`

## callees

- `0x140001414`
- `0x14000b5c4`
- `0x14000fe20`
- `0x140017468`
- `0x1400187b2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001001a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001001a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010029`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010029`

## string_xrefs

- `0x14000fee6`: `GetSiufLocPath failed.`
- `0x14000feba`: `BuildSiufLocPath`
- `0x14000ff9e`: `BuildSiufLocPath`
- `0x14000ffca`: `StringCchPrintfW failed to build loc file path string.`

## pseudocode

```c
__int64 __fastcall BuildSiufLocPath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  int SiufLocPath; // ebx
  int v8; // r9d
  int v9; // r8d
  int v10; // ecx
  char *v11; // rdx
  __int64 *v12; // rax
  HANDLE ProcessHeap; // rax
  const char **v15; // [rsp+30h] [rbp-50h]
  const char **v16; // [rsp+38h] [rbp-48h]
  __int64 *v17; // [rsp+48h] [rbp-38h]
  LPVOID lpMem; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  const char *v21; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+70h] [rbp-10h] BYREF
  int v23; // [rsp+A0h] [rbp+20h] BYREF
  int v24; // [rsp+B8h] [rbp+38h] BYREF

  v24 = a4;
  lpMem = 0;
  if ( !a1 || !a2 || !a3 )
    return (unsigned int)-2147467261;
  SiufLocPath = GetSiufLocPath((unsigned __int16 **)&lpMem);
  if ( SiufLocPath >= 0 )
  {
    memset_0(a3, 0, 0x208u);
    SiufLocPath = StringCchPrintfW(a3, 0x104u, L"%s\\%s-%s", lpMem, a2, a1);
    if ( SiufLocPath < 0 && (unsigned int)dword_140027000 > 2 )
    {
      v10 = qword_140027018;
      if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v22[0] = 0x1000000;
        v21 = "BuildSiufLocPath";
        v11 = byte_140021F85;
        v24 = 404;
        v20 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
        v19 = (__int64)"StringCchPrintfW failed to build loc file path string.";
        v17 = v22;
        v16 = &v21;
        v15 = &v20;
        v12 = &v19;
        goto LABEL_15;
      }
    }
  }
  else if ( (unsigned int)dword_140027000 > 2 )
  {
    v9 = qword_140027018;
    v10 = qword_140027010;
    if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      v19 = 0x1000000;
      v20 = "BuildSiufLocPath";
      v11 = &byte_140021DAF;
      v24 = 387;
      v21 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
      v22[0] = "GetSiufLocPath failed.";
      v17 = &v19;
      v16 = &v20;
      v15 = &v21;
      v12 = v22;
LABEL_15:
      v23 = SiufLocPath;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v10,
        (_DWORD)v11,
        v9,
        v8,
        (__int64)v12,
        (__int64)&v23,
        (__int64)v15,
        (__int64)v16,
        (__int64)&v24,
        (__int64)v17);
    }
  }
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  return (unsigned int)SiufLocPath;
}

```

## disassembly

```asm
0x14000fe20  mov     [rsp-18h+arg_8], rbx
0x14000fe25  mov     [rsp-18h+arg_10], rsi
0x14000fe2a  mov     [rsp-18h+arg_18], r9d
0x14000fe2f  push    rbp
0x14000fe30  push    r14
0x14000fe32  push    r15
0x14000fe34  mov     rbp, rsp
0x14000fe37  sub     rsp, 80h
0x14000fe3e  mov     [rbp+lpMem], 0
0x14000fe46  mov     rsi, r8
0x14000fe49  mov     r14, rdx
0x14000fe4c  mov     r15, rcx
0x14000fe4f  test    rcx, rcx
0x14000fe52  jnz     short loc_14000FE5E
0x14000fe54  mov     ebx, 80004003h
0x14000fe59  jmp     loc_14001002F
0x14000fe5e  test    r14, r14
0x14000fe61  jz      short loc_14000FE54
0x14000fe63  test    rsi, rsi
0x14000fe66  jz      short loc_14000FE54
0x14000fe68  lea     rcx, [rbp+lpMem]; unsigned __int16 **
0x14000fe6c  call    ?GetSiufLocPath@@YAJPEAPEAG@Z; GetSiufLocPath(ushort * *)
0x14000fe71  mov     ebx, eax
0x14000fe73  test    eax, eax
0x14000fe75  jns     loc_14000FF27
0x14000fe7b  mov     ecx, cs:dword_140027000
0x14000fe81  cmp     ecx, 2
0x14000fe84  jbe     loc_140010013
0x14000fe8a  mov     r8, cs:qword_140027018
0x14000fe91  mov     rdx, 400000000000h
0x14000fe9b  mov     rcx, cs:qword_140027010
0x14000fea2  test    rdx, rcx
0x14000fea5  jz      loc_140010013
0x14000feab  mov     rax, r8
0x14000feae  and     rax, rdx
0x14000feb1  cmp     rax, r8
0x14000feb4  jnz     loc_140010013
0x14000feba  lea     rax, aBuildsiuflocpa; "BuildSiufLocPath"
0x14000fec1  mov     [rbp+var_28], 1000000h
0x14000fec9  mov     [rbp+var_20], rax
0x14000fecd  lea     rdx, byte_140021DAF
0x14000fed4  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000fedb  mov     [rbp+arg_18], 183h
0x14000fee2  mov     [rbp+var_18], rax
0x14000fee6  lea     rax, aGetsiuflocpath; "GetSiufLocPath failed."
0x14000feed  mov     [rbp+var_10], rax
0x14000fef1  lea     rax, [rbp+var_28]
0x14000fef5  mov     [rsp+80h+var_38], rax
0x14000fefa  lea     rax, [rbp+arg_18]
0x14000fefe  mov     [rsp+80h+var_40], rax
0x14000ff03  lea     rax, [rbp+var_20]
0x14000ff07  mov     [rsp+80h+var_48], rax
0x14000ff0c  lea     rax, [rbp+var_18]
0x14000ff10  mov     [rsp+80h+var_50], rax
0x14000ff15  lea     rax, [rbp+arg_0]
0x14000ff19  mov     [rsp+80h+var_58], rax
0x14000ff1e  lea     rax, [rbp+var_10]
0x14000ff22  jmp     loc_140010006
0x14000ff27  xor     edx, edx; Val
0x14000ff29  mov     r8d, 208h; Size
0x14000ff2f  mov     rcx, rsi; void *
0x14000ff32  call    memset_0
0x14000ff37  mov     r9, [rbp+lpMem]
0x14000ff3b  lea     r8, aSSS; "%s\\%s-%s"
0x14000ff42  mov     edx, 104h; unsigned __int64
0x14000ff47  mov     [rsp+80h+var_58], r15
0x14000ff4c  mov     rcx, rsi; unsigned __int16 *
0x14000ff4f  mov     [rsp+80h+var_60], r14
0x14000ff54  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000ff59  mov     ebx, eax
0x14000ff5b  test    eax, eax
0x14000ff5d  jns     loc_140010013
0x14000ff63  mov     eax, cs:dword_140027000
0x14000ff69  cmp     eax, 2
0x14000ff6c  jbe     loc_140010013
0x14000ff72  mov     rcx, cs:qword_140027018
0x14000ff79  mov     rdx, 400000000000h
0x14000ff83  mov     rax, cs:qword_140027010
0x14000ff8a  test    rdx, rax
0x14000ff8d  jz      loc_140010013
0x14000ff93  mov     rax, rcx
0x14000ff96  and     rax, rdx
0x14000ff99  cmp     rax, rcx
0x14000ff9c  jnz     short loc_140010013
0x14000ff9e  lea     rax, aBuildsiuflocpa; "BuildSiufLocPath"
0x14000ffa5  mov     [rbp+var_10], 1000000h
0x14000ffad  mov     [rbp+var_18], rax
0x14000ffb1  lea     rdx, byte_140021F85
0x14000ffb8  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000ffbf  mov     [rbp+arg_18], 194h
0x14000ffc6  mov     [rbp+var_20], rax
0x14000ffca  lea     rax, aStringcchprint; "StringCchPrintfW failed to build loc fi"...
0x14000ffd1  mov     [rbp+var_28], rax
0x14000ffd5  lea     rax, [rbp+var_10]
0x14000ffd9  mov     [rsp+80h+var_38], rax
0x14000ffde  lea     rax, [rbp+arg_18]
0x14000ffe2  mov     [rsp+80h+var_40], rax
0x14000ffe7  lea     rax, [rbp+var_18]
0x14000ffeb  mov     [rsp+80h+var_48], rax
0x14000fff0  lea     rax, [rbp+var_20]
0x14000fff4  mov     [rsp+80h+var_50], rax
0x14000fff9  lea     rax, [rbp+arg_0]
0x14000fffd  mov     [rsp+80h+var_58], rax
0x140010002  lea     rax, [rbp+var_28]
0x140010006  mov     [rsp+80h+var_60], rax
0x14001000b  mov     [rbp+arg_0], ebx
0x14001000e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140010013  cmp     [rbp+lpMem], 0
0x140010018  jz      short loc_14001002F
0x14001001a  call    cs:__imp_GetProcessHeap
0x140010020  mov     r8, [rbp+lpMem]; lpMem
0x140010024  xor     edx, edx; dwFlags
0x140010026  mov     rcx, rax; hHeap
0x140010029  call    cs:__imp_HeapFree
0x14001002f  lea     r11, [rsp+80h+var_s0]
0x140010037  mov     eax, ebx
0x140010039  mov     rbx, [r11+28h]
0x14001003d  mov     rsi, [r11+30h]
0x140010041  mov     rsp, r11
0x140010044  pop     r15
0x140010046  pop     r14
0x140010048  pop     rbp
0x140010049  retn
```
