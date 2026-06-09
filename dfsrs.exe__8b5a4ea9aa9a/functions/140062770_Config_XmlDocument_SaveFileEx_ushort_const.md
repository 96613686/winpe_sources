# Config::XmlDocument::SaveFileEx(ushort const *)

- ea: `0x140062770`
- end: `0x140062a1a`
- name: `?SaveFileEx@XmlDocument@Config@@QEAAPEAVFrsStatus@@PEBG@Z`
- size: `682`
- prototype: `struct FrsStatus *(Config::XmlDocument *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140063940`
- `0x140064d5c`
- `0x140065a7c`

## callees

- `0x14002c548`
- `0x14005c38c`
- `0x14005c620`
- `0x1400626e4`
- `0x140062770`
- `0x1400be540`
- `0x1401af7b0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1400627ff`
- `KERNEL32!WideCharToMultiByte` at `0x140062851`
- `KERNEL32!WideCharToMultiByte` at `0x1400627ff`
- `KERNEL32!WideCharToMultiByte` at `0x140062851`
- `KERNEL32!WriteFile` at `0x14006291c`
- `KERNEL32!WriteFile` at `0x14006291c`
- `KERNEL32!GetLastError` at `0x140062872`
- `KERNEL32!GetLastError` at `0x140062946`
- `KERNEL32!GetLastError` at `0x140062872`
- `KERNEL32!GetLastError` at `0x140062946`
- `KERNEL32!GetCurrentThreadId` at `0x140062864`
- `KERNEL32!GetCurrentThreadId` at `0x140062938`
- `KERNEL32!GetCurrentThreadId` at `0x140062993`
- `KERNEL32!GetCurrentThreadId` at `0x140062864`
- `KERNEL32!GetCurrentThreadId` at `0x140062938`
- `KERNEL32!GetCurrentThreadId` at `0x140062993`
- `OLEAUT32!__imp_SysFreeString` at `0x1400629f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400629f1`
- `OLEAUT32!__imp_SysStringLen` at `0x1400627d1`
- `OLEAUT32!__imp_SysStringLen` at `0x140062827`
- `OLEAUT32!__imp_SysStringLen` at `0x1400627d1`
- `OLEAUT32!__imp_SysStringLen` at `0x140062827`

## string_xrefs

- `0x14006289b`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x14006296f`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x1400629bc`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x14006288f`: `Config::XmlDocument::SaveFileEx`
- `0x140062963`: `Config::XmlDocument::SaveFileEx`
- `0x1400629b0`: `Config::XmlDocument::SaveFileEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct FrsStatus *__fastcall Config::XmlDocument::SaveFileEx(Config::XmlDocument *this, const unsigned __int16 *a2)
{
  __int64 v3; // rsi
  WCHAR *v4; // rbx
  struct FrsStatus *v5; // rdi
  UINT v6; // eax
  unsigned int v7; // eax
  int cbMultiByte; // r14d
  CHAR *lpMultiByteStr; // r15
  UINT v10; // eax
  DWORD CurrentThreadId; // edi
  DWORD LastError; // eax
  DWORD v13; // edi
  DWORD v14; // eax
  DWORD v15; // eax
  __int64 v16; // rcx
  BSTR pbstr; // [rsp+50h] [rbp-20h] BYREF
  CHAR *v19; // [rsp+58h] [rbp-18h] BYREF
  HANDLE hFile; // [rsp+60h] [rbp-10h] BYREF
  int v21; // [rsp+68h] [rbp-8h]
  DWORD NumberOfBytesWritten; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 *v23; // [rsp+B8h] [rbp+48h] BYREF

  v3 = 0;
  v23 = 0;
  v4 = 0;
  pbstr = 0;
  v19 = 0;
  hFile = (HANDLE)-1LL;
  v21 = 1;
  v5 = Config::XmlDocument::Save(this, &v23);
  if ( v5 )
    goto LABEL_10;
  ATL::CComBSTR::Attach((ATL::CComBSTR *)&pbstr, v23);
  v4 = pbstr;
  v6 = SysStringLen(pbstr);
  v7 = WideCharToMultiByte(0xFDE9u, 0, v4, v6, 0, 0, 0, 0);
  cbMultiByte = v7;
  lpMultiByteStr = 0;
  if ( !v7
    || (lpMultiByteStr = (CHAR *)operator_new(v7),
        v19 = lpMultiByteStr,
        v10 = SysStringLen(v4),
        (cbMultiByte = WideCharToMultiByte(0xFDE9u, 0, v4, v10, lpMultiByteStr, cbMultiByte, 0, 0)) == 0) )
  {
    CurrentThreadId = GetCurrentThreadId();
    LastError = GetLastError();
    v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                               LastError,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                               "Config::XmlDocument::SaveFileEx",
                               749,
                               CurrentThreadId,
                               0);
    if ( v5 )
      goto LABEL_10;
  }
  v5 = FileUtil::FrsCreateFile(a2, 2u, 0x80u, 7u, 5u, 0x4020u, &hFile);
  if ( v5 )
  {
LABEL_10:
    v15 = GetCurrentThreadId();
    v3 = FrsStatusList::PushNewError(
           v16,
           *((unsigned int *)v5 + 1),
           *((unsigned int *)v5 + 2),
           *(unsigned int *)v5,
           "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
           "Config::XmlDocument::SaveFileEx",
           787,
           v15,
           v5);
  }
  else
  {
    while ( cbMultiByte )
    {
      NumberOfBytesWritten = 0;
      if ( !WriteFile(hFile, lpMultiByteStr, cbMultiByte, &NumberOfBytesWritten, 0) )
      {
        v13 = GetCurrentThreadId();
        v14 = GetLastError();
        v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                   v14,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                   "Config::XmlDocument::SaveFileEx",
                                   777,
                                   v13,
                                   0);
        if ( !v5 )
          break;
        goto LABEL_10;
      }
      cbMultiByte -= NumberOfBytesWritten;
      lpMultiByteStr += NumberOfBytesWritten;
    }
  }
  CloseHandleEx(&hFile);
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v19);
  SysFreeString(v4);
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x140062770  mov     [rsp-28h+arg_0], rbx
0x140062775  mov     [rsp-28h+arg_8], rsi
0x14006277a  push    rbp
0x14006277b  push    rdi
0x14006277c  push    r12
0x14006277e  push    r14
0x140062780  push    r15
0x140062782  mov     rbp, rsp
0x140062785  sub     rsp, 70h
0x140062789  mov     r12, rdx
0x14006278c  xor     esi, esi
0x14006278e  mov     [rbp+arg_18], rsi
0x140062792  mov     ebx, esi
0x140062794  mov     [rbp+pbstr], rbx
0x140062798  mov     [rbp+var_18], rsi
0x14006279c  or      [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1400627a1  mov     [rbp+var_8], 1
0x1400627a8  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x1400627ac  call    ?Save@XmlDocument@Config@@QEAAPEAVFrsStatus@@PEAPEAG@Z; Config::XmlDocument::Save(ushort * *)
0x1400627b1  mov     rdi, rax
0x1400627b4  test    rax, rax
0x1400627b7  jnz     loc_140062993
0x1400627bd  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x1400627c1  lea     rcx, [rbp+pbstr]; this
0x1400627c5  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x1400627ca  mov     rbx, [rbp+pbstr]
0x1400627ce  mov     rcx, rbx; pbstr
0x1400627d1  call    cs:__imp_SysStringLen
0x1400627d8  nop     dword ptr [rax+rax+00h]
0x1400627dd  mov     [rsp+70h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x1400627e2  mov     [rsp+70h+lpDefaultChar], rsi; lpDefaultChar
0x1400627e7  mov     [rsp+70h+cbMultiByte], esi; cbMultiByte
0x1400627eb  mov     [rsp+70h+lpMultiByteStr], rsi; lpMultiByteStr
0x1400627f0  mov     r9d, eax; cchWideChar
0x1400627f3  mov     r8, rbx; lpWideCharStr
0x1400627f6  xor     edx, edx; dwFlags
0x1400627f8  mov     edi, 0FDE9h
0x1400627fd  mov     ecx, edi; CodePage
0x1400627ff  call    cs:__imp_WideCharToMultiByte
0x140062806  nop     dword ptr [rax+rax+00h]
0x14006280b  mov     r14d, eax
0x14006280e  mov     r15d, esi
0x140062811  test    eax, eax
0x140062813  jz      short loc_140062864
0x140062815  mov     ecx, r14d; unsigned __int64
0x140062818  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x14006281d  mov     r15, rax
0x140062820  mov     [rbp+var_18], rax
0x140062824  mov     rcx, rbx; pbstr
0x140062827  call    cs:__imp_SysStringLen
0x14006282e  nop     dword ptr [rax+rax+00h]
0x140062833  mov     [rsp+70h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x140062838  mov     [rsp+70h+lpDefaultChar], rsi; lpDefaultChar
0x14006283d  mov     [rsp+70h+cbMultiByte], r14d; cbMultiByte
0x140062842  mov     [rsp+70h+lpMultiByteStr], r15; lpMultiByteStr
0x140062847  mov     r9d, eax; cchWideChar
0x14006284a  mov     r8, rbx; lpWideCharStr
0x14006284d  xor     edx, edx; dwFlags
0x14006284f  mov     ecx, edi; CodePage
0x140062851  call    cs:__imp_WideCharToMultiByte
0x140062858  nop     dword ptr [rax+rax+00h]
0x14006285d  mov     r14d, eax
0x140062860  test    eax, eax
0x140062862  jnz     short loc_1400628C3
0x140062864  call    cs:__imp_GetCurrentThreadId
0x14006286b  nop     dword ptr [rax+rax+00h]
0x140062870  mov     edi, eax
0x140062872  call    cs:__imp_GetLastError
0x140062879  nop     dword ptr [rax+rax+00h]
0x14006287e  mov     [rsp+70h+var_30], rsi
0x140062883  mov     dword ptr [rsp+70h+lpUsedDefaultChar], edi
0x140062887  mov     dword ptr [rsp+70h+lpDefaultChar], 2EDh
0x14006288f  lea     rcx, aConfigXmldocum_5; "Config::XmlDocument::SaveFileEx"
0x140062896  mov     qword ptr [rsp+70h+cbMultiByte], rcx
0x14006289b  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x1400628a2  mov     [rsp+70h+lpMultiByteStr], rcx
0x1400628a7  mov     r9d, 1
0x1400628ad  xor     r8d, r8d
0x1400628b0  mov     edx, eax
0x1400628b2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400628b7  mov     rdi, rax
0x1400628ba  test    rax, rax
0x1400628bd  jnz     loc_140062993
0x1400628c3  lea     rax, [rbp+hFile]
0x1400628c7  mov     [rsp+70h+lpDefaultChar], rax; void **
0x1400628cc  mov     [rsp+70h+cbMultiByte], 4020h; unsigned int
0x1400628d4  mov     dword ptr [rsp+70h+lpMultiByteStr], 5; unsigned int
0x1400628dc  mov     edx, 2; unsigned int
0x1400628e1  lea     r9d, [rdx+5]; unsigned int
0x1400628e5  lea     r8d, [rdx+7Eh]; unsigned int
0x1400628e9  mov     rcx, r12; unsigned __int16 *
0x1400628ec  call    ?FrsCreateFile@FileUtil@@SAPEAVFrsStatus@@PEBGKKKKKPEAPEAX@Z; FileUtil::FrsCreateFile(ushort const *,ulong,ulong,ulong,ulong,ulong,void * *)
0x1400628f1  mov     rdi, rax
0x1400628f4  test    rax, rax
0x1400628f7  jnz     loc_140062993
0x1400628fd  test    r14d, r14d
0x140062900  jz      loc_1400629DA
0x140062906  mov     [rbp+NumberOfBytesWritten], esi
0x140062909  mov     [rsp+70h+lpMultiByteStr], rsi; lpOverlapped
0x14006290e  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140062912  mov     r8d, r14d; nNumberOfBytesToWrite
0x140062915  mov     rdx, r15; lpBuffer
0x140062918  mov     rcx, [rbp+hFile]; hFile
0x14006291c  call    cs:__imp_WriteFile
0x140062923  nop     dword ptr [rax+rax+00h]
0x140062928  test    eax, eax
0x14006292a  jz      short loc_140062938
0x14006292c  sub     r14d, [rbp+NumberOfBytesWritten]
0x140062930  mov     eax, [rbp+NumberOfBytesWritten]
0x140062933  add     r15, rax
0x140062936  jmp     short loc_1400628FD
0x140062938  call    cs:__imp_GetCurrentThreadId
0x14006293f  nop     dword ptr [rax+rax+00h]
0x140062944  mov     edi, eax
0x140062946  call    cs:__imp_GetLastError
0x14006294d  nop     dword ptr [rax+rax+00h]
0x140062952  mov     [rsp+70h+var_30], rsi
0x140062957  mov     dword ptr [rsp+70h+lpUsedDefaultChar], edi
0x14006295b  mov     dword ptr [rsp+70h+lpDefaultChar], 309h
0x140062963  lea     rcx, aConfigXmldocum_5; "Config::XmlDocument::SaveFileEx"
0x14006296a  mov     qword ptr [rsp+70h+cbMultiByte], rcx
0x14006296f  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140062976  mov     [rsp+70h+lpMultiByteStr], rcx
0x14006297b  mov     r9d, 1
0x140062981  xor     r8d, r8d
0x140062984  mov     edx, eax
0x140062986  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14006298b  mov     rdi, rax
0x14006298e  test    rax, rax
0x140062991  jz      short loc_1400629DA
0x140062993  call    cs:__imp_GetCurrentThreadId
0x14006299a  nop     dword ptr [rax+rax+00h]
0x14006299f  mov     [rsp+70h+var_30], rdi
0x1400629a4  mov     dword ptr [rsp+70h+lpUsedDefaultChar], eax
0x1400629a8  mov     dword ptr [rsp+70h+lpDefaultChar], 313h
0x1400629b0  lea     rax, aConfigXmldocum_5; "Config::XmlDocument::SaveFileEx"
0x1400629b7  mov     qword ptr [rsp+70h+cbMultiByte], rax
0x1400629bc  lea     rax, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x1400629c3  mov     [rsp+70h+lpMultiByteStr], rax
0x1400629c8  mov     r9d, [rdi]
0x1400629cb  mov     r8d, [rdi+8]
0x1400629cf  mov     edx, [rdi+4]
0x1400629d2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400629d7  mov     rsi, rax
0x1400629da  lea     rcx, [rbp+hFile]; void **
0x1400629de  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x1400629e3  nop
0x1400629e4  lea     rcx, [rbp+var_18]
0x1400629e8  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1400629ed  nop
0x1400629ee  mov     rcx, rbx; bstrString
0x1400629f1  call    cs:__imp_SysFreeString
0x1400629f8  nop     dword ptr [rax+rax+00h]
0x1400629fd  mov     rax, rsi
0x140062a00  lea     r11, [rsp+70h+var_s0]
0x140062a05  mov     rbx, [r11+30h]
0x140062a09  mov     rsi, [r11+38h]
0x140062a0d  mov     rsp, r11
0x140062a10  pop     r15
0x140062a12  pop     r14
0x140062a14  pop     r12
0x140062a16  pop     rdi
0x140062a17  pop     rbp
0x140062a18  retn
```
