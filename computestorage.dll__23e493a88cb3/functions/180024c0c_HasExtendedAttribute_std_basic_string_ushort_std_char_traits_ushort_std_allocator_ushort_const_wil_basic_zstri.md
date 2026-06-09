# HasExtendedAttribute(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::basic_zstring_view<char>)

- ea: `0x180024c0c`
- end: `0x180024e67`
- name: `?HasExtendedAttribute@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@D@wil@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180024f88`

## callees

- `0x180002690`
- `0x180003bc1`
- `0x180012838`
- `0x1800139b0`
- `0x180013d30`
- `0x180022a0c`
- `0x18002375c`
- `0x180024c0c`
- `0x18002523c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024c68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024cae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024dd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024cae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024dd2`
- `ntdll!NtQueryEaFile` at `0x180024da8`
- `ntdll!NtQueryEaFile` at `0x180024da8`

## string_xrefs

- `0x180024e07`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180024e4f`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall HasExtendedAttribute(char *a1, __int64 a2)
{
  char *v3; // rdi
  char *FileW; // rbx
  size_t v6; // rsi
  char *v7; // rax
  gsl::details *v8; // rcx
  unsigned int v9; // eax
  const char *v10; // rax
  const char *v11; // r9
  PVOID EaList[2]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v13; // [rsp+60h] [rbp+7h]
  PVOID Buffer[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v15; // [rsp+78h] [rbp+1Fh]
  char *v16; // [rsp+80h] [rbp+27h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v3 = a1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  FileW = (char *)CreateFileW((LPCWSTR)a1, 8u, 1u, 0, 3u, 0, 0);
  v16 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( GetLastError() - 2 > 1 )
    {
      v10 = (const char *)std::wstring::c_str(v3);
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x14E,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        v11,
        (unsigned int)"%ls",
        v10);
    }
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return 0;
    goto LABEL_6;
  }
  *(_OWORD *)EaList = 0;
  v13 = 0;
  v6 = *(_QWORD *)(a2 + 8);
  std::vector<enum gsl::byte>::vector<enum gsl::byte>(EaList, v6 + 8);
  v7 = (char *)EaList[0];
  *((_BYTE *)EaList[0] + 4) = v6;
  v8 = (gsl::details *)(v7 + 5);
  if ( v7 == (char *)-5LL && (_BYTE)v6 || v6 == -1 || !*(_QWORD *)a2 && v6 || (unsigned __int8)v6 < v6 )
  {
    gsl::details::terminate(v8);
    JUMPOUT(0x180024E66LL);
  }
  if ( v6 )
    memmove_0(v8, *(const void **)a2, v6);
  *(_OWORD *)Buffer = 0;
  v15 = 0;
  std::vector<enum gsl::byte>::vector<enum gsl::byte>(Buffer, v6 + 12);
  IoStatusBlock = 0;
  v9 = NtQueryEaFile(
         FileW,
         &IoStatusBlock,
         Buffer[0],
         LODWORD(Buffer[1]) - LODWORD(Buffer[0]),
         0,
         EaList[0],
         LODWORD(EaList[1]) - LODWORD(EaList[0]),
         0,
         1u);
  if ( v9 != -2147483643 )
  {
    if ( *((_QWORD *)v3 + 3) > 7u )
      v3 = *(char **)v3;
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
      (const char *)v9,
      (int)"%ls",
      v3);
    std::vector<unsigned char>::~vector<unsigned char>(Buffer);
    std::vector<unsigned char>::~vector<unsigned char>(EaList);
LABEL_6:
    CloseHandle(FileW);
    return 0;
  }
  std::vector<unsigned char>::~vector<unsigned char>(Buffer);
  std::vector<unsigned char>::~vector<unsigned char>(EaList);
  CloseHandle(FileW);
  return 1;
}

```

## disassembly

```asm
0x180024c0c  mov     [rsp-8+arg_10], rbx
0x180024c11  mov     [rsp-8+arg_18], rsi
0x180024c16  push    rbp
0x180024c17  push    rdi
0x180024c18  push    r14
0x180024c1a  lea     rbp, [rsp-47h]
0x180024c1f  sub     rsp, 0A0h
0x180024c26  mov     rax, cs:__security_cookie
0x180024c2d  xor     rax, rsp
0x180024c30  mov     [rbp+57h+var_18], rax
0x180024c34  mov     r14, rdx
0x180024c37  mov     rdi, rcx
0x180024c3a  cmp     qword ptr [rcx+18h], 7
0x180024c3f  jbe     short loc_180024C44
0x180024c41  mov     rcx, [rcx]; lpFileName
0x180024c44  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x180024c4d  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180024c55  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180024c5d  xor     r9d, r9d; lpSecurityAttributes
0x180024c60  lea     edx, [r9+8]; dwDesiredAccess
0x180024c64  lea     r8d, [r9+1]; dwShareMode
0x180024c68  call    cs:__imp_CreateFileW
0x180024c6f  nop     dword ptr [rax+rax+00h]
0x180024c74  mov     rbx, rax
0x180024c77  mov     [rbp+57h+var_30], rax
0x180024c7b  inc     rax
0x180024c7e  test    rax, 0FFFFFFFFFFFFFFFEh
0x180024c84  jnz     short loc_180024CE1
0x180024c86  call    cs:__imp_GetLastError
0x180024c8d  nop     dword ptr [rax+rax+00h]
0x180024c92  mov     r9d, eax
0x180024c95  lea     edx, [rax-2]
0x180024c98  cmp     edx, 1
0x180024c9b  ja      loc_180024E32
0x180024ca1  lea     rax, [rbx-1]
0x180024ca5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024ca9  ja      short loc_180024CBA
0x180024cab  mov     rcx, rbx; hObject
0x180024cae  call    cs:__imp_CloseHandle
0x180024cb5  nop     dword ptr [rax+rax+00h]
0x180024cba  xor     al, al
0x180024cbc  mov     rcx, [rbp+57h+var_18]
0x180024cc0  xor     rcx, rsp; StackCookie
0x180024cc3  call    __security_check_cookie
0x180024cc8  lea     r11, [rsp+0B0h+var_10]
0x180024cd0  mov     rbx, [r11+30h]
0x180024cd4  mov     rsi, [r11+38h]
0x180024cd8  mov     rsp, r11
0x180024cdb  pop     r14
0x180024cdd  pop     rdi
0x180024cde  pop     rbp
0x180024cdf  retn
0x180024ce1  xorps   xmm0, xmm0
0x180024ce4  xor     eax, eax
0x180024ce6  movups  xmmword ptr [rbp+57h+EaList], xmm0
0x180024cea  mov     [rbp+57h+var_50], rax
0x180024cee  mov     rsi, [r14+8]
0x180024cf2  lea     rdx, [rsi+8]
0x180024cf6  lea     rcx, [rbp+57h+EaList]
0x180024cfa  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x180024cff  nop
0x180024d00  mov     rax, [rbp+57h+EaList]
0x180024d04  movzx   r8d, sil
0x180024d08  mov     [rax+4], r8b
0x180024d0c  lea     rcx, [rax+5]; this
0x180024d10  test    rcx, rcx
0x180024d13  jnz     short loc_180024D1E
0x180024d15  test    r8b, r8b
0x180024d18  jnz     loc_180024E61
0x180024d1e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180024d22  jz      loc_180024E61
0x180024d28  mov     rdx, [r14]; Src
0x180024d2b  test    rdx, rdx
0x180024d2e  jnz     short loc_180024D39
0x180024d30  test    rsi, rsi
0x180024d33  jnz     loc_180024E61
0x180024d39  cmp     r8, rsi
0x180024d3c  jb      loc_180024E61
0x180024d42  test    rsi, rsi
0x180024d45  jz      short loc_180024D4F
0x180024d47  mov     r8, rsi; Size
0x180024d4a  call    memmove_0
0x180024d4f  xorps   xmm0, xmm0
0x180024d52  xor     eax, eax
0x180024d54  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180024d58  mov     [rbp+57h+var_38], rax
0x180024d5c  lea     rdx, [rsi+0Ch]
0x180024d60  lea     rcx, [rbp+57h+Buffer]
0x180024d64  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x180024d69  nop
0x180024d6a  xorps   xmm0, xmm0
0x180024d6d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180024d71  mov     rcx, [rbp+57h+EaList]
0x180024d75  mov     r8, [rbp+57h+Buffer]; Buffer
0x180024d79  mov     eax, dword ptr [rbp+57h+EaList+8]
0x180024d7c  sub     eax, ecx
0x180024d7e  mov     r9d, dword ptr [rbp+57h+Buffer+8]
0x180024d82  sub     r9d, r8d; Length
0x180024d85  mov     [rsp+0B0h+RestartScan], 1; RestartScan
0x180024d8a  mov     [rsp+0B0h+EaIndex], 0; EaIndex
0x180024d93  mov     dword ptr [rsp+0B0h+hTemplateFile], eax; EaListLength
0x180024d97  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rcx; EaList
0x180024d9c  mov     byte ptr [rsp+0B0h+dwCreationDisposition], 0; ReturnSingleEntry
0x180024da1  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180024da5  mov     rcx, rbx; FileHandle
0x180024da8  call    cs:__imp_NtQueryEaFile
0x180024daf  nop     dword ptr [rax+rax+00h]
0x180024db4  cmp     eax, 80000005h
0x180024db9  jnz     short loc_180024DE5
0x180024dbb  lea     rcx, [rbp+57h+Buffer]
0x180024dbf  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180024dc4  nop
0x180024dc5  lea     rcx, [rbp+57h+EaList]
0x180024dc9  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180024dce  nop
0x180024dcf  mov     rcx, rbx; hObject
0x180024dd2  call    cs:__imp_CloseHandle
0x180024dd9  nop     dword ptr [rax+rax+00h]
0x180024dde  mov     al, 1
0x180024de0  jmp     loc_180024CBC
0x180024de5  cmp     qword ptr [rdi+18h], 7
0x180024dea  jbe     short loc_180024DEF
0x180024dec  mov     rdi, [rdi]
0x180024def  mov     rcx, [rbp+5Fh]; this
0x180024df3  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rdi; char *
0x180024df8  lea     rdx, aLs; "%ls"
0x180024dff  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rdx; int
0x180024e04  mov     r9d, eax; char *
0x180024e07  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180024e0e  mov     edx, 167h; void *
0x180024e13  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024e18  nop
0x180024e19  lea     rcx, [rbp+57h+Buffer]
0x180024e1d  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180024e22  nop
0x180024e23  lea     rcx, [rbp+57h+EaList]
0x180024e27  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180024e2c  nop
0x180024e2d  jmp     loc_180024CAB
0x180024e32  mov     rcx, rdi
0x180024e35  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180024e3a  mov     rcx, [rbp+5Fh]; this
0x180024e3e  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax; char *
0x180024e43  lea     rdx, aLs; "%ls"
0x180024e4a  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rdx; unsigned int
0x180024e4f  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180024e56  mov     edx, 14Eh; void *
0x180024e5b  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180024e61  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
