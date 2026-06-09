# GetDiskHandle(ushort const *)

- ea: `0x180029fc8`
- end: `0x18002a110`
- name: `?GetDiskHandle@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `328`
- prototype: `_QWORD *__fastcall(_QWORD *, _WORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027e8c`

## callees

- `0x180002690`
- `0x180006e10`
- `0x180008fac`
- `0x180029fc8`
- `0x18002a4f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a088`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a088`

## string_xrefs

- `0x18002a0d0`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18002a0c0`: `Failed opening disk: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall GetDiskHandle(_QWORD *a1, _WORD *a2)
{
  unsigned __int64 v3; // r8
  unsigned __int64 v4; // r8
  LPCWSTR *v5; // rax
  LPCWSTR v6; // r9
  __int64 v7; // rdx
  LPCWSTR *v8; // rcx
  LPCWSTR *v9; // rcx
  char *FileW; // rax
  LPCWSTR *v11; // r8
  __int64 v13; // [rsp+48h] [rbp-38h]
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v15; // [rsp+60h] [rbp-20h]
  unsigned __int64 v16; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  HIWORD(v13) = HIWORD(a1);
  *(_OWORD *)lpFileName = 0;
  v15 = 0;
  v16 = 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  std::wstring::_Construct<1,unsigned short const *>((__int64)lpFileName, a2, v3);
  v4 = v16;
  v5 = lpFileName;
  v6 = lpFileName[0];
  if ( v16 > 7 )
    v5 = (LPCWSTR *)lpFileName[0];
  if ( *((_WORD *)v5 + v15 - 1) == 92 )
  {
    v7 = --v15;
    v8 = lpFileName;
    if ( v16 > 7 )
      v8 = (LPCWSTR *)lpFileName[0];
    *((_WORD *)v8 + v7) = 0;
    v4 = v16;
    v6 = lpFileName[0];
  }
  *a1 = 0;
  v9 = lpFileName;
  if ( v4 > 7 )
    v9 = (LPCWSTR *)v6;
  FileW = (char *)CreateFileW((LPCWSTR)v9, 0xC0000000, 3u, 0, 3u, 0, 0);
  *a1 = FileW;
  v11 = lpFileName;
  if ( v16 > 7 )
    v11 = (LPCWSTR *)lpFileName[0];
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0x384,
    (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
    (const char *)((unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL),
    (bool)"Failed opening disk: %ws",
    (const char *)v11);
  std::wstring::~wstring((char **)lpFileName);
  return a1;
}

```

## disassembly

```asm
0x180029fc8  mov     [rsp-8+arg_10], rbx
0x180029fcd  mov     [rsp-8+arg_18], rdi
0x180029fd2  push    rbp
0x180029fd3  mov     rbp, rsp
0x180029fd6  sub     rsp, 80h
0x180029fdd  mov     rax, cs:__security_cookie
0x180029fe4  xor     rax, rsp
0x180029fe7  mov     [rbp+var_10], rax
0x180029feb  mov     rbx, rcx
0x180029fee  mov     [rbp+var_38], rcx
0x180029ff2  xor     edi, edi
0x180029ff4  mov     [rbp+var_40], edi
0x180029ff7  xorps   xmm0, xmm0
0x180029ffa  movups  xmmword ptr [rbp+lpFileName], xmm0
0x180029ffe  mov     [rbp+var_20], rdi
0x18002a002  mov     [rbp+var_18], rdi
0x18002a006  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a00a  inc     r8
0x18002a00d  cmp     [rdx+r8*2], di
0x18002a012  jnz     short loc_18002A00A
0x18002a014  lea     rcx, [rbp+lpFileName]
0x18002a018  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a01d  nop
0x18002a01e  mov     r8, [rbp+var_18]
0x18002a022  lea     rax, [rbp+lpFileName]
0x18002a026  mov     r9, [rbp+lpFileName]
0x18002a02a  cmp     r8, 7
0x18002a02e  cmova   rax, r9
0x18002a032  mov     rdx, [rbp+var_20]
0x18002a036  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x18002a03c  jnz     short loc_18002A05D
0x18002a03e  dec     rdx
0x18002a041  mov     [rbp+var_20], rdx
0x18002a045  lea     rcx, [rbp+lpFileName]
0x18002a049  cmp     r8, 7
0x18002a04d  cmova   rcx, r9
0x18002a051  mov     [rcx+rdx*2], di
0x18002a055  mov     r8, [rbp+var_18]
0x18002a059  mov     r9, [rbp+lpFileName]
0x18002a05d  xor     eax, eax
0x18002a05f  mov     [rbx], rax
0x18002a062  lea     rcx, [rbp+lpFileName]
0x18002a066  cmp     r8, 7
0x18002a06a  cmova   rcx, r9; lpFileName
0x18002a06e  mov     [rsp+80h+hTemplateFile], rdi; hTemplateFile
0x18002a073  mov     [rsp+80h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18002a077  lea     r8d, [rax+3]; dwShareMode
0x18002a07b  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002a080  xor     r9d, r9d; lpSecurityAttributes
0x18002a083  mov     edx, 0C0000000h; dwDesiredAccess
0x18002a088  call    cs:__imp_CreateFileW
0x18002a08f  nop     dword ptr [rax+rax+00h]
0x18002a094  mov     [rbx], rax
0x18002a097  mov     [rbp+var_40], 1
0x18002a09e  lea     r8, [rbp+lpFileName]
0x18002a0a2  cmp     [rbp+var_18], 7
0x18002a0a7  cmova   r8, [rbp+lpFileName]
0x18002a0ac  lea     rcx, [rax-1]
0x18002a0b0  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002a0b4  setbe   dl
0x18002a0b7  mov     rcx, [rbp+8]; this
0x18002a0bb  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r8; char *
0x18002a0c0  lea     rax, aFailedOpeningD; "Failed opening disk: %ws"
0x18002a0c7  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; bool
0x18002a0cc  movzx   r9d, dl; char *
0x18002a0d0  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002a0d7  mov     edx, 384h; void *
0x18002a0dc  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x18002a0e1  nop
0x18002a0e2  lea     rcx, [rbp+lpFileName]
0x18002a0e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a0eb  mov     rax, rbx
0x18002a0ee  mov     rcx, [rbp+var_10]
0x18002a0f2  xor     rcx, rsp; StackCookie
0x18002a0f5  call    __security_check_cookie
0x18002a0fa  lea     r11, [rsp+80h+var_s0]
0x18002a102  mov     rbx, [r11+20h]
0x18002a106  mov     rdi, [r11+28h]
0x18002a10a  mov     rsp, r11
0x18002a10d  pop     rbp
0x18002a10e  retn
```
