# RtfToHtmlConverter::ConvertRtfFileToTempHtml(ushort const *,ushort * *)

- ea: `0x18001adf0`
- end: `0x18001afa1`
- name: `?ConvertRtfFileToTempHtml@RtfToHtmlConverter@@SAJPEBGPEAPEAG@Z`
- size: `433`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x18008c82c`

## callees

- `0x180003470`
- `0x18000391c`
- `0x180003ffc`
- `0x180008524`
- `0x180008544`
- `0x18000b358`
- `0x18001ad58`
- `0x18001adf0`
- `0x18001afa8`
- `0x18001b1b8`
- `0x18001b770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aee7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aee7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af32`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001ae95`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001ae95`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001ae46`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001ae46`

## pseudocode

```c
__int64 __fastcall RtfToHtmlConverter::ConvertRtfFileToTempHtml(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  const char *v4; // r9
  __int64 v5; // rdx
  int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  RtfToHtmlConverter *v10; // rdi
  __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  size_t v13; // r9
  __int64 v14; // [rsp+20h] [rbp-E0h]
  RtfToHtmlConverter *v15; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR TempFileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR PathName[264]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  memset_0(PathName, 0, 0x208u);
  if ( !(unsigned int)GetTempPath2W(260, PathName) )
  {
    v5 = 292;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"shell\\oobe\\machine\\rtfutil\\rtftohtml.cpp",
             v4);
  }
  memset_0(TempFileName, 0, 0x208u);
  if ( !GetTempFileNameW(PathName, L"r2u", 0, TempFileName) )
  {
    v5 = 294;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"shell\\oobe\\machine\\rtfutil\\rtftohtml.cpp",
             v4);
  }
  v7 = RtfHelper::s_ConvertRtfFileToUnicode(a1, TempFileName);
  if ( v7 < 0 )
  {
    v8 = 295;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shell\\oobe\\machine\\rtfutil\\rtftohtml.cpp",
      (const char *)(unsigned int)v7,
      v14);
    return (unsigned int)v7;
  }
  v15 = 0;
  EnterCriticalSection(&RtfToHtmlConverter::_cs);
  v9 = RtfToHtmlConverter::Create(&v15);
  v10 = v15;
  v7 = v9;
  if ( !v9 )
    v7 = RtfToHtmlConverter::InternalRtfToHtml(v15, TempFileName);
  if ( v10 )
  {
    RtfToHtmlConverter::~RtfToHtmlConverter(v10);
    operator delete(v10, (const struct std::nothrow_t *)0x30);
  }
  LeaveCriticalSection(&RtfToHtmlConverter::_cs);
  if ( v7 < 0 )
  {
    v8 = 296;
    goto LABEL_8;
  }
  v13 = -1;
  do
    ++v13;
  while ( TempFileName[v13] );
  v7 = _AllocStringWorker<CTCoAllocPolicy>(v12, v11, TempFileName, v13, v14, (void **)a2);
  if ( v7 < 0 )
  {
    v8 = 297;
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x18001adf0  mov     [rsp-8+arg_10], rbx
0x18001adf5  mov     [rsp-8+arg_18], rsi
0x18001adfa  push    rbp
0x18001adfb  push    rdi
0x18001adfc  push    r14
0x18001adfe  lea     rbp, [rsp-370h]
0x18001ae06  sub     rsp, 470h
0x18001ae0d  mov     rax, cs:__security_cookie
0x18001ae14  xor     rax, rsp
0x18001ae17  mov     [rbp+380h+var_20], rax
0x18001ae1e  mov     rsi, rdx
0x18001ae21  mov     rbx, rcx
0x18001ae24  mov     edi, 208h
0x18001ae29  lea     rcx, [rbp+380h+PathName]; void *
0x18001ae30  mov     r8d, edi; Size
0x18001ae33  xor     edx, edx; Val
0x18001ae35  call    memset_0
0x18001ae3a  lea     rdx, [rbp+380h+PathName]
0x18001ae41  mov     ecx, 104h
0x18001ae46  call    cs:__imp_GetTempPath2W
0x18001ae4c  xor     r14d, r14d
0x18001ae4f  test    eax, eax
0x18001ae51  jnz     short loc_18001AE70
0x18001ae53  mov     edx, 124h; void *
0x18001ae58  mov     rcx, [rbp+388h]; this
0x18001ae5f  lea     r8, aShellOobeMachi_36; "shell\\oobe\\machine\\rtfutil\\rtftohtm"...
0x18001ae66  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ae6b  jmp     loc_18001AF7A
0x18001ae70  mov     r8, rdi; Size
0x18001ae73  lea     rcx, [rsp+480h+TempFileName]; void *
0x18001ae78  xor     edx, edx; Val
0x18001ae7a  call    memset_0
0x18001ae7f  lea     r9, [rsp+480h+TempFileName]; lpTempFileName
0x18001ae84  xor     r8d, r8d; uUnique
0x18001ae87  lea     rdx, PrefixString; "r2u"
0x18001ae8e  lea     rcx, [rbp+380h+PathName]; lpPathName
0x18001ae95  call    cs:__imp_GetTempFileNameW
0x18001ae9b  test    eax, eax
0x18001ae9d  jnz     short loc_18001AEA6
0x18001ae9f  mov     edx, 126h
0x18001aea4  jmp     short loc_18001AE58
0x18001aea6  lea     rdx, [rsp+480h+TempFileName]; unsigned __int16 *
0x18001aeab  mov     rcx, rbx; unsigned __int16 *
0x18001aeae  call    ?s_ConvertRtfFileToUnicode@RtfHelper@@SAJPEBG0@Z; RtfHelper::s_ConvertRtfFileToUnicode(ushort const *,ushort const *)
0x18001aeb3  mov     ebx, eax
0x18001aeb5  test    eax, eax
0x18001aeb7  jns     short loc_18001AEDB
0x18001aeb9  mov     edx, 127h; void *
0x18001aebe  mov     rcx, [rbp+388h]; this
0x18001aec5  lea     r8, aShellOobeMachi_36; "shell\\oobe\\machine\\rtfutil\\rtftohtm"...
0x18001aecc  mov     r9d, ebx; char *
0x18001aecf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aed4  mov     eax, ebx
0x18001aed6  jmp     loc_18001AF7A
0x18001aedb  lea     rcx, ?_cs@RtfToHtmlConverter@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001aee2  mov     [rsp+480h+var_450], r14
0x18001aee7  call    cs:__imp_EnterCriticalSection
0x18001aeed  lea     rcx, [rsp+480h+var_450]; struct RtfToHtmlConverter **
0x18001aef2  call    ?Create@RtfToHtmlConverter@@KAJPEAPEAV1@@Z; RtfToHtmlConverter::Create(RtfToHtmlConverter * *)
0x18001aef7  mov     rdi, [rsp+480h+var_450]
0x18001aefc  mov     ebx, eax
0x18001aefe  test    eax, eax
0x18001af00  jnz     short loc_18001AF11
0x18001af02  lea     rdx, [rsp+480h+TempFileName]; unsigned __int16 *
0x18001af07  mov     rcx, rdi; this
0x18001af0a  call    ?InternalRtfToHtml@RtfToHtmlConverter@@IEAAJPEAGK@Z; RtfToHtmlConverter::InternalRtfToHtml(ushort *,ulong)
0x18001af0f  mov     ebx, eax
0x18001af11  test    rdi, rdi
0x18001af14  jz      short loc_18001AF2B
0x18001af16  mov     rcx, rdi; this
0x18001af19  call    ??1RtfToHtmlConverter@@IEAA@XZ; RtfToHtmlConverter::~RtfToHtmlConverter(void)
0x18001af1e  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x18001af23  mov     rcx, rdi; void *
0x18001af26  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001af2b  lea     rcx, ?_cs@RtfToHtmlConverter@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001af32  call    cs:__imp_LeaveCriticalSection
0x18001af38  test    ebx, ebx
0x18001af3a  jns     short loc_18001AF46
0x18001af3c  mov     edx, 128h
0x18001af41  jmp     loc_18001AEBE
0x18001af46  lea     rax, [rsp+480h+TempFileName]
0x18001af4b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001af4f  inc     r9
0x18001af52  cmp     [rax+r9*2], r14w
0x18001af57  jnz     short loc_18001AF4F
0x18001af59  lea     r8, [rsp+480h+TempFileName]
0x18001af5e  mov     [rsp+480h+var_458], rsi
0x18001af63  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18001af68  mov     ebx, eax
0x18001af6a  test    eax, eax
0x18001af6c  jns     short loc_18001AF78
0x18001af6e  mov     edx, 129h
0x18001af73  jmp     loc_18001AEBE
0x18001af78  xor     eax, eax
0x18001af7a  mov     rcx, [rbp+380h+var_20]
0x18001af81  xor     rcx, rsp; StackCookie
0x18001af84  call    __security_check_cookie
0x18001af89  lea     r11, [rsp+480h+var_10]
0x18001af91  mov     rbx, [r11+30h]
0x18001af95  mov     rsi, [r11+38h]
0x18001af99  mov     rsp, r11
0x18001af9c  pop     r14
0x18001af9e  pop     rdi
0x18001af9f  pop     rbp
0x18001afa0  retn
```
