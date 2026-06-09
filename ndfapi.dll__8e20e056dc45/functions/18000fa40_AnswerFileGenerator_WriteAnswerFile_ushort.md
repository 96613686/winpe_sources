# AnswerFileGenerator::WriteAnswerFile(ushort * *)

- ea: `0x18000fa40`
- end: `0x18000fca1`
- name: `?WriteAnswerFile@AnswerFileGenerator@@QEAAJPEAPEAG@Z`
- size: `609`
- prototype: `__int64 __fastcall(AnswerFileGenerator *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18000dd58`

## callees

- `0x180004df8`
- `0x18000cb28`
- `0x18000f78c`
- `0x18000fa40`
- `0x18001f652`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fbd3`
- `KERNEL32!GetLastError` at `0x18000fbd3`
- `KERNEL32!CloseHandle` at `0x18000fbcb`
- `KERNEL32!CloseHandle` at `0x18000fbcb`
- `KERNEL32!GetTempPathW` at `0x18000faa7`
- `KERNEL32!GetTempPathW` at `0x18000faa7`
- `KERNEL32!GetTempFileNameW` at `0x18000facf`
- `KERNEL32!GetTempFileNameW` at `0x18000facf`
- `KERNEL32!CreateFileW` at `0x18000fb0b`
- `KERNEL32!CreateFileW` at `0x18000fb0b`
- `KERNEL32!WriteFile` at `0x18000fb8c`
- `KERNEL32!WriteFile` at `0x18000fb8c`
- `ole32!CoTaskMemAlloc` at `0x18000fc47`
- `ole32!CoTaskMemAlloc` at `0x18000fc47`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AnswerFileGenerator::WriteAnswerFile(AnswerFileGenerator *this, unsigned __int16 **a2)
{
  unsigned __int16 **v2; // r15
  DWORD TempPathW; // eax
  void *v5; // rbx
  HANDLE FileW; // rax
  signed int Error; // esi
  volatile signed __int32 *v8; // rdi
  signed int LastError; // eax
  __int64 v10; // rcx
  WCHAR *v11; // rax
  __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  DWORD NumberOfBytesWritten[2]; // [rsp+40h] [rbp-468h] BYREF
  LPCVOID lpBuffer; // [rsp+48h] [rbp-460h] BYREF
  unsigned __int16 **v17; // [rsp+50h] [rbp-458h]
  DWORD *v18; // [rsp+58h] [rbp-450h] BYREF
  WCHAR TempFileName[264]; // [rsp+60h] [rbp-448h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp-238h] BYREF

  v2 = a2;
  v17 = a2;
  memset_0(TempFileName, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  TempPathW = GetTempPathW(0x104u, Buffer);
  try
  {
    if ( TempPathW && GetTempFileNameW(Buffer, L"NDF", 0, TempFileName) )
    {
      v5 = 0;
      *(_QWORD *)NumberOfBytesWritten = 0;
      FileW = CreateFileW(TempFileName, 0x40000000u, 2u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        Error = ATL::AtlHresultFromLastError();
      }
      else
      {
        v5 = FileW;
        *(_QWORD *)NumberOfBytesWritten = FileW;
        Error = 0;
      }
      if ( Error >= 0 )
      {
        lpBuffer = (LPCVOID)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatMessageW(
          &lpBuffer,
          L"<Answers Version=\"1.0\">\n"
           "<Interaction ID=\"IT_EntryPoint\"><value>InContext</value></Interaction>\n"
           "<Interaction ID=\"IT_HelperClassName\"><value>%1!s!</value></Interaction>\n"
           "<Interaction ID=\"IT_HelperAttributes\"><value><![CDATA[<HelperAttributes>%2!s!</HelperAttributes>]]></value>"
           "</Interaction>\n"
           "</Answers>\n",
          *(_QWORD *)this,
          *((_QWORD *)this + 1));
        NumberOfBytesWritten[0] = 0;
        v8 = (volatile signed __int32 *)lpBuffer;
        Error = WriteFile(v5, lpBuffer, 2 * *((_DWORD *)lpBuffer - 4), NumberOfBytesWritten, 0)
              ? 0
              : ATL::AtlHresultFromLastError();
        if ( _InterlockedExchangeAdd(v8 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
      }
      if ( v5 )
        CloseHandle(v5);
    }
    else
    {
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
    }
  }
  catch ( const ATL::CAtlException *v18 )
  {
    NumberOfBytesWritten[0] = *v18;
    Error = NumberOfBytesWritten[0];
    v2 = v17;
  }
  if ( TempPathW && GetTempFileNameW(Buffer, L"NDF", 0, TempFileName) )
  {
    v5 = 0;
    *(_QWORD *)NumberOfBytesWritten = 0;
    FileW = CreateFileW(TempFileName, 0x40000000u, 2u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      Error = ATL::AtlHresultFromLastError();
    }
    else
    {
      v5 = FileW;
      *(_QWORD *)NumberOfBytesWritten = FileW;
      Error = 0;
    }
    if ( Error >= 0 )
    {
      lpBuffer = (LPCVOID)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatMessageW(
        &lpBuffer,
        L"<Answers Version=\"1.0\">\n"
         "<Interaction ID=\"IT_EntryPoint\"><value>InContext</value></Interaction>\n"
         "<Interaction ID=\"IT_HelperClassName\"><value>%1!s!</value></Interaction>\n"
         "<Interaction ID=\"IT_HelperAttributes\"><value><![CDATA[<HelperAttributes>%2!s!</HelperAttributes>]]></value></"
         "Interaction>\n"
         "</Answers>\n",
        *(_QWORD *)this,
        *((_QWORD *)this + 1));
      NumberOfBytesWritten[0] = 0;
      v8 = (volatile signed __int32 *)lpBuffer;
      Error = WriteFile(v5, lpBuffer, 2 * *((_DWORD *)lpBuffer - 4), NumberOfBytesWritten, 0)
            ? 0
            : ATL::AtlHresultFromLastError();
      if ( _InterlockedExchangeAdd(v8 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
    }
    if ( v5 )
      CloseHandle(v5);
  }
  else
  {
    LastError = GetLastError();
    Error = LastError;
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
  }
  NumberOfBytesWritten[0] = *v18;
}

```

## disassembly

```asm
0x18000fa40  mov     [rsp+arg_10], rbx
0x18000fa45  mov     [rsp+arg_18], rsi
0x18000fa4a  push    rdi
0x18000fa4b  push    r14
0x18000fa4d  push    r15
0x18000fa4f  sub     rsp, 490h
0x18000fa56  mov     rax, cs:__security_cookie
0x18000fa5d  xor     rax, rsp
0x18000fa60  mov     [rsp+4A8h+var_28], rax
0x18000fa68  mov     r15, rdx
0x18000fa6b  mov     rdi, rcx
0x18000fa6e  mov     [rsp+4A8h+var_458], rdx
0x18000fa73  mov     ebx, 208h
0x18000fa78  mov     r8d, ebx; Size
0x18000fa7b  xor     edx, edx; Val
0x18000fa7d  lea     rcx, [rsp+4A8h+TempFileName]; void *
0x18000fa82  call    memset_0
0x18000fa87  nop
0x18000fa88  mov     r8d, ebx; Size
0x18000fa8b  xor     edx, edx; Val
0x18000fa8d  lea     rcx, [rsp+4A8h+Buffer]; void *
0x18000fa95  call    memset_0
0x18000fa9a  lea     rdx, [rsp+4A8h+Buffer]; lpBuffer
0x18000faa2  mov     ecx, 104h; nBufferLength
0x18000faa7  call    cs:__imp_GetTempPathW
0x18000faad  xor     r14d, r14d
0x18000fab0  test    eax, eax
0x18000fab2  jz      loc_18000FBD3
0x18000fab8  lea     r9, [rsp+4A8h+TempFileName]; lpTempFileName
0x18000fabd  xor     r8d, r8d; uUnique
0x18000fac0  lea     rdx, PrefixString; "NDF"
0x18000fac7  lea     rcx, [rsp+4A8h+Buffer]; lpPathName
0x18000facf  call    cs:__imp_GetTempFileNameW
0x18000fad5  test    eax, eax
0x18000fad7  jz      loc_18000FBD3
0x18000fadd  mov     ebx, r14d
0x18000fae0  mov     qword ptr [rsp+4A8h+NumberOfBytesWritten], rbx
0x18000fae5  mov     [rsp+4A8h+hTemplateFile], r14; hTemplateFile
0x18000faea  mov     [rsp+4A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000faf2  mov     [rsp+4A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000fafa  xor     r9d, r9d; lpSecurityAttributes
0x18000fafd  mov     edx, 40000000h; dwDesiredAccess
0x18000fb02  lea     r8d, [r14+2]; dwShareMode
0x18000fb06  lea     rcx, [rsp+4A8h+TempFileName]; lpFileName
0x18000fb0b  call    cs:__imp_CreateFileW
0x18000fb11  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fb15  jnz     short loc_18000FB20
0x18000fb17  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000fb1c  mov     esi, eax
0x18000fb1e  jmp     short loc_18000FB2B
0x18000fb20  mov     rbx, rax
0x18000fb23  mov     qword ptr [rsp+4A8h+NumberOfBytesWritten], rax
0x18000fb28  mov     esi, r14d
0x18000fb2b  test    esi, esi
0x18000fb2d  js      loc_18000FBC3
0x18000fb33  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000fb3a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000fb41  mov     rax, [rax+18h]
0x18000fb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb4a  add     rax, 18h
0x18000fb4e  mov     [rsp+4A8h+lpBuffer], rax
0x18000fb53  mov     r9, [rdi+8]
0x18000fb57  mov     r8, [rdi]
0x18000fb5a  lea     rdx, aAnswersVersion; "<Answers Version=\"1.0\">\n<Interaction"...
0x18000fb61  lea     rcx, [rsp+4A8h+lpBuffer]
0x18000fb66  call    ?FormatMessageW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::FormatMessageW(ushort const *,...)
0x18000fb6b  mov     [rsp+4A8h+NumberOfBytesWritten], r14d
0x18000fb70  mov     rdi, [rsp+4A8h+lpBuffer]
0x18000fb75  mov     r8d, [rdi-10h]
0x18000fb79  add     r8d, r8d; nNumberOfBytesToWrite
0x18000fb7c  mov     qword ptr [rsp+4A8h+dwCreationDisposition], r14; lpOverlapped
0x18000fb81  lea     r9, [rsp+4A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000fb86  mov     rdx, rdi; lpBuffer
0x18000fb89  mov     rcx, rbx; hFile
0x18000fb8c  call    cs:__imp_WriteFile
0x18000fb92  test    eax, eax
0x18000fb94  jnz     short loc_18000FB9F
0x18000fb96  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000fb9b  mov     esi, eax
0x18000fb9d  jmp     short loc_18000FBA2
0x18000fb9f  mov     esi, r14d
0x18000fba2  lea     rdx, [rdi-18h]
0x18000fba6  or      eax, 0FFFFFFFFh
0x18000fba9  lock xadd [rdx+10h], eax
0x18000fbae  sub     eax, 1
0x18000fbb1  jg      short loc_18000FBC3
0x18000fbb3  mov     rcx, [rdx]
0x18000fbb6  mov     rax, [rcx]
0x18000fbb9  mov     rax, [rax+8]
0x18000fbbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbc2  nop
0x18000fbc3  test    rbx, rbx
0x18000fbc6  jz      short loc_18000FBE8
0x18000fbc8  mov     rcx, rbx; hObject
0x18000fbcb  call    cs:__imp_CloseHandle
0x18000fbd1  jmp     short loc_18000FBE8
0x18000fbd3  call    cs:__imp_GetLastError
0x18000fbd9  test    eax, eax
0x18000fbdb  mov     esi, eax
0x18000fbdd  jle     short loc_18000FBE8
0x18000fbdf  movzx   esi, ax
0x18000fbe2  or      esi, 80070000h
0x18000fbe8  jmp     short loc_18000FBF6
0x18000fbea  xor     r14d, r14d
0x18000fbed  mov     esi, [rsp+4A8h+NumberOfBytesWritten]
0x18000fbf1  mov     r15, [rsp+4A8h+var_458]
0x18000fbf6  test    esi, esi
0x18000fbf8  js      short loc_18000FC76
0x18000fbfa  test    r15, r15
0x18000fbfd  jz      short loc_18000FC71
0x18000fbff  mov     edx, 0FFFEh
0x18000fc04  mov     ecx, edx
0x18000fc06  lea     rax, [rsp+4A8h+TempFileName]
0x18000fc0b  cmp     [rax], r14w
0x18000fc0f  jz      short loc_18000FC1B
0x18000fc11  add     rax, 2
0x18000fc15  sub     rcx, 1
0x18000fc19  jnz     short loc_18000FC0B
0x18000fc1b  mov     rax, rcx
0x18000fc1e  neg     rax
0x18000fc21  sbb     esi, esi
0x18000fc23  not     esi
0x18000fc25  and     esi, 80070057h
0x18000fc2b  mov     rax, rcx
0x18000fc2e  sub     rdx, rcx
0x18000fc31  neg     rax
0x18000fc34  sbb     rbx, rbx
0x18000fc37  and     rbx, rdx
0x18000fc3a  test    rcx, rcx
0x18000fc3d  jz      short loc_18000FC76
0x18000fc3f  lea     rcx, ds:2[rbx*2]; cb
0x18000fc47  call    cs:__imp_CoTaskMemAlloc
0x18000fc4d  mov     [r15], rax
0x18000fc50  test    rax, rax
0x18000fc53  jnz     short loc_18000FC5C
0x18000fc55  mov     esi, 8007000Eh
0x18000fc5a  jmp     short loc_18000FC76
0x18000fc5c  lea     rdx, [rbx+1]; unsigned __int64
0x18000fc60  lea     r8, [rsp+4A8h+TempFileName]; unsigned __int16 *
0x18000fc65  mov     rcx, rax; unsigned __int16 *
0x18000fc68  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fc6d  mov     esi, eax
0x18000fc6f  jmp     short loc_18000FC76
0x18000fc71  mov     esi, 80070057h
0x18000fc76  mov     eax, esi
0x18000fc78  mov     rcx, [rsp+4A8h+var_28]
0x18000fc80  xor     rcx, rsp; StackCookie
0x18000fc83  call    __security_check_cookie
0x18000fc88  lea     r11, [rsp+4A8h+var_18]
0x18000fc90  mov     rbx, [r11+30h]
0x18000fc94  mov     rsi, [r11+38h]
0x18000fc98  mov     rsp, r11
0x18000fc9b  pop     r15
0x18000fc9d  pop     r14
0x18000fc9f  pop     rdi
0x18000fca0  retn
```
