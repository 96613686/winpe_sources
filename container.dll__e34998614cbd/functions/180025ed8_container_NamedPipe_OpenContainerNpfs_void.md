# container::NamedPipe::OpenContainerNpfs(void *)

- ea: `0x180025ed8`
- end: `0x180026054`
- name: `?OpenContainerNpfs@NamedPipe@container@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX@Z`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18002605c`

## callees

- `0x180002ad0`
- `0x1800051b0`
- `0x18000bdec`
- `0x18000ca10`
- `0x18000de10`
- `0x1800227ec`
- `0x180023e64`
- `0x180025ed8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025fea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025fea`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall container::NamedPipe::OpenContainerNpfs(_QWORD *a1, void *a2)
{
  void *v3; // rax
  __int64 v4; // rax
  const WCHAR *v5; // rcx
  HANDLE FileW; // rax
  const char *v7; // r9
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v10; // [rsp+60h] [rbp-29h]
  _OWORD v11[2]; // [rsp+70h] [rbp-19h] BYREF
  _OWORD v12[2]; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v13[32]; // [rsp+B0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v11[0] = 0;
  v11[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v11[0]) = 0;
  container::GetContainerObjectRootPath(a2);
  memset(v12, 0, sizeof(v12));
  std::wstring::_Construct<1,unsigned short const *>(v12);
  v3 = (void *)std::operator+<unsigned short>(v13, v12, v11);
  v4 = std::wstring::append(v3, L"\\Device\\NamedPipe");
  *(_OWORD *)lpFileName = 0;
  v10 = 0;
  *(_OWORD *)lpFileName = *(_OWORD *)v4;
  v10 = *(_OWORD *)(v4 + 16);
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 7;
  *(_WORD *)v4 = 0;
  std::wstring::~wstring(v13);
  std::wstring::~wstring(v12);
  v5 = (const WCHAR *)lpFileName;
  if ( *((_QWORD *)&v10 + 1) > 7u )
    v5 = lpFileName[0];
  FileW = CreateFileW(v5, 0x40000000u, 3u, 0, 3u, 0x80u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\namedpipe_provider.cpp",
      v7);
  *a1 = FileW;
  std::wstring::~wstring(lpFileName);
  std::wstring::~wstring(v11);
  return a1;
}

```

## disassembly

```asm
0x180025ed8  mov     [rsp-8+arg_10], rbx
0x180025edd  push    rbp
0x180025ede  lea     rbp, [rsp-57h]
0x180025ee3  sub     rsp, 0E0h
0x180025eea  mov     rax, cs:__security_cookie
0x180025ef1  xor     rax, rsp
0x180025ef4  mov     [rbp+57h+var_10], rax
0x180025ef8  mov     r8, rdx
0x180025efb  mov     rbx, rcx
0x180025efe  mov     [rbp+57h+var_98], rcx
0x180025f02  xorps   xmm0, xmm0
0x180025f05  movups  [rbp+57h+var_70], xmm0
0x180025f09  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180025f11  movdqu  [rbp+57h+var_60], xmm1
0x180025f16  xor     eax, eax
0x180025f18  mov     word ptr [rbp+57h+var_70], ax
0x180025f1c  lea     rdx, [rbp+57h+var_70]
0x180025f20  mov     rcx, r8; JobHandle
0x180025f23  call    ?GetContainerObjectRootPath@container@@YAXPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; container::GetContainerObjectRootPath(void *,std::wstring &)
0x180025f28  xorps   xmm0, xmm0
0x180025f2b  movups  [rbp+57h+var_50], xmm0
0x180025f2f  xorps   xmm1, xmm1
0x180025f32  movdqu  [rbp+57h+var_40], xmm1
0x180025f37  mov     r8d, 4
0x180025f3d  lea     rdx, asc_1800397E0; "\\\\?\\"
0x180025f44  lea     rcx, [rbp+57h+var_50]
0x180025f48  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180025f4d  nop
0x180025f4e  lea     r8, [rbp+57h+var_70]
0x180025f52  lea     rdx, [rbp+57h+var_50]
0x180025f56  lea     rcx, [rbp+57h+var_30]
0x180025f5a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180025f5f  nop
0x180025f60  lea     rdx, aDeviceNamedpip; "\\Device\\NamedPipe"
0x180025f67  mov     rcx, rax; Src
0x180025f6a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180025f6f  mov     rcx, rax
0x180025f72  xorps   xmm0, xmm0
0x180025f75  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x180025f79  xorps   xmm1, xmm1
0x180025f7c  movdqu  [rbp+57h+var_80], xmm1
0x180025f81  movups  xmm0, xmmword ptr [rax]
0x180025f84  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x180025f88  movups  xmm1, xmmword ptr [rax+10h]
0x180025f8c  movups  [rbp+57h+var_80], xmm1
0x180025f90  mov     qword ptr [rax+10h], 0
0x180025f98  mov     qword ptr [rax+18h], 7
0x180025fa0  xor     eax, eax
0x180025fa2  mov     [rcx], ax
0x180025fa5  lea     rcx, [rbp+57h+var_30]
0x180025fa9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025fae  nop
0x180025faf  lea     rcx, [rbp+57h+var_50]
0x180025fb3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025fb8  lea     rcx, [rbp+57h+lpFileName]
0x180025fbc  cmp     qword ptr [rbp+57h+var_80+8], 7
0x180025fc1  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180025fc6  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x180025fcf  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180025fd7  mov     r8d, 3; dwShareMode
0x180025fdd  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180025fe2  xor     r9d, r9d; lpSecurityAttributes
0x180025fe5  mov     edx, 40000000h; dwDesiredAccess
0x180025fea  call    cs:__imp_CreateFileW
0x180025ff1  nop     dword ptr [rax+rax+00h]
0x180025ff6  mov     [rbp+57h+var_98], rax
0x180025ffa  mov     rcx, [rbp+5Fh]; this
0x180025ffe  lea     rdx, [rax+1]
0x180026002  test    rdx, 0FFFFFFFFFFFFFFFEh
0x180026009  jz      short loc_180026042
0x18002600b  mov     [rbx], rax
0x18002600e  lea     rcx, [rbp+57h+lpFileName]
0x180026012  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026017  nop
0x180026018  lea     rcx, [rbp+57h+var_70]
0x18002601c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026021  mov     rax, rbx
0x180026024  mov     rcx, [rbp+57h+var_10]
0x180026028  xor     rcx, rsp; StackCookie
0x18002602b  call    __security_check_cookie
0x180026030  mov     rbx, [rsp+0E0h+arg_10]
0x180026038  add     rsp, 0E0h
0x18002603f  pop     rbp
0x180026040  retn
0x180026042  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\container"...
0x180026049  mov     edx, 81h; void *
0x18002604e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
