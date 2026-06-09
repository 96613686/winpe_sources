# container::MountManagerProvider::Setup(Schema::Containers::Definition::MountManagerNamespace const &,void *)

- ea: `0x180025aa8`
- end: `0x180025d1b`
- name: `?Setup@MountManagerProvider@container@@YAXAEBUMountManagerNamespace@Definition@Containers@Schema@@PEAX@Z`
- size: `627`
- prototype: `void(container::MountManagerProvider *__hidden this, const struct Schema::Containers::Definition::MountManagerNamespace *, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1800063f0`

## callees

- `0x180002ad0`
- `0x180004c40`
- `0x1800051b0`
- `0x18000bdec`
- `0x18000be30`
- `0x18000de10`
- `0x180022c94`
- `0x180023e64`
- `0x18002562c`
- `0x180025aa8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180025bd7`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180025bd7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025b68`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025b68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025b0f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025b0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025b83`

## string_xrefs

- `0x180025b08`: `\\.\MountPointManager`
- `0x180025cf7`: `onecore\base\gendrv\silos\container\mount_provider.cpp`
- `0x180025d09`: `onecore\base\gendrv\silos\container\mount_provider.cpp`
- `0x180025c4c`: `\Device\MountPointManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall container::MountManagerProvider::Setup(
        container::MountManagerProvider *this,
        const struct Schema::Containers::Definition::MountManagerNamespace *a2,
        void *a3)
{
  _BYTE *FileW; // rbx
  const char *v6; // r9
  const char *v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rdi
  __m128i si128; // xmm6
  wint_t *v11; // rcx
  wint_t v12; // r14
  __int64 v13; // r8
  __int64 v14; // r15
  __int128 *v15; // rcx
  __int64 v16; // rax
  DWORD BytesReturned; // [rsp+48h] [rbp-79h] BYREF
  const struct Schema::Containers::Definition::MountManagerNamespace *InBuffer; // [rsp+50h] [rbp-71h] BYREF
  _BYTE *v19; // [rsp+58h] [rbp-69h]
  __int128 v20; // [rsp+60h] [rbp-61h] BYREF
  __int128 v21; // [rsp+70h] [rbp-51h]
  _BYTE v22[32]; // [rsp+80h] [rbp-41h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-21h] BYREF
  __m128i v24; // [rsp+B0h] [rbp-11h]
  _BYTE Src[32]; // [rsp+C0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  InBuffer = a2;
  BytesReturned = 0;
  FileW = CreateFileW(L"\\\\.\\MountPointManager", 0xC0000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v19 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xD3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\mount_provider.cpp",
      v6);
  if ( !DeviceIoControl(FileW, 0x6DC054u, &InBuffer, 8u, 0, 0, &BytesReturned, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\mount_provider.cpp",
      v7);
  CloseHandle(FileW);
  v8 = *(_QWORD *)this;
  v9 = *((_QWORD *)this + 1);
  if ( v8 != v9 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      v23 = 0;
      v24 = si128;
      LOWORD(v23) = 0;
      container::GetContainerObjectRootPath(a2);
      if ( *(_QWORD *)(v8 + 24) <= 7u )
        v11 = (wint_t *)v8;
      else
        v11 = *(wint_t **)v8;
      v12 = towupper(*v11);
      v19 = v22;
      v14 = std::wstring::wstring(v22, v8 + 32);
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v24.m128i_i64[0]) < 4 )
        std::_Xlen_string();
      v15 = &v23;
      if ( v24.m128i_i64[1] > 7uLL )
        v15 = (__int128 *)v23;
      std::wstring::wstring(Src, v24.m128i_i64[0], v13, L"\\\\?\\", 4, v15, v24.m128i_i64[0]);
      v16 = std::wstring::append(Src, L"\\Device\\MountPointManager");
      v20 = 0;
      v21 = 0u;
      v20 = *(_OWORD *)v16;
      v21 = *(_OWORD *)(v16 + 16);
      *(_QWORD *)(v16 + 16) = 0;
      *(_QWORD *)(v16 + 24) = 7;
      *(_WORD *)v16 = 0;
      container::MountManager::NotifyMountManager(&v20, v12, v14);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(&v23);
      v8 += 64;
    }
    while ( v8 != v9 );
  }
}

```

## disassembly

```asm
0x180025aa8  mov     rax, rsp
0x180025aab  mov     [rax+18h], rbx
0x180025aaf  push    rbp
0x180025ab0  push    rsi
0x180025ab1  push    rdi
0x180025ab2  push    r14
0x180025ab4  push    r15
0x180025ab6  lea     rbp, [rax-5Fh]
0x180025aba  sub     rsp, 0F0h
0x180025ac1  movaps  xmmword ptr [rax-38h], xmm6
0x180025ac5  mov     rax, cs:__security_cookie
0x180025acc  xor     rax, rsp
0x180025acf  mov     [rbp+57h+var_38], rax
0x180025ad3  mov     rsi, rdx
0x180025ad6  mov     rdi, rcx
0x180025ad9  mov     [rbp+57h+InBuffer], rdx
0x180025add  mov     [rbp+57h+BytesReturned], 0
0x180025ae4  mov     [rsp+110h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x180025aed  mov     [rsp+110h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180025af5  mov     r8d, 3; dwShareMode
0x180025afb  mov     [rsp+110h+dwCreationDisposition], r8d; dwCreationDisposition
0x180025b00  xor     r9d, r9d; lpSecurityAttributes
0x180025b03  mov     edx, 0C0000000h; dwDesiredAccess
0x180025b08  lea     rcx, aMountpointmana; "\\\\.\\MountPointManager"
0x180025b0f  call    cs:__imp_CreateFileW
0x180025b16  nop     dword ptr [rax+rax+00h]
0x180025b1b  mov     rbx, rax
0x180025b1e  mov     [rbp+57h+var_C0], rax
0x180025b22  mov     rcx, [rbp+5Fh]; this
0x180025b26  dec     rax
0x180025b29  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180025b2d  ja      loc_180025CF7
0x180025b33  mov     [rsp+110h+lpOverlapped], 0; lpOverlapped
0x180025b3c  lea     rax, [rbp+57h+BytesReturned]
0x180025b40  mov     [rsp+110h+hTemplateFile], rax; lpBytesReturned
0x180025b45  mov     [rsp+110h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180025b4d  mov     qword ptr [rsp+110h+dwCreationDisposition], 0; lpOutBuffer
0x180025b56  mov     r9d, 8; nInBufferSize
0x180025b5c  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180025b60  mov     edx, 6DC054h; dwIoControlCode
0x180025b65  mov     rcx, rbx; hDevice
0x180025b68  call    cs:__imp_DeviceIoControl
0x180025b6f  nop     dword ptr [rax+rax+00h]
0x180025b74  mov     rcx, [rbp+5Fh]; this
0x180025b78  test    eax, eax
0x180025b7a  jz      loc_180025D09
0x180025b80  mov     rcx, rbx; hObject
0x180025b83  call    cs:__imp_CloseHandle
0x180025b8a  nop     dword ptr [rax+rax+00h]
0x180025b8f  mov     rbx, [rdi]
0x180025b92  mov     rdi, [rdi+8]
0x180025b96  cmp     rbx, rdi
0x180025b99  jz      loc_180025CC8
0x180025b9f  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180025ba7  xorps   xmm0, xmm0
0x180025baa  movups  [rbp+57h+var_78], xmm0
0x180025bae  movdqu  [rbp+57h+var_68], xmm6
0x180025bb3  xor     eax, eax
0x180025bb5  mov     word ptr [rbp+57h+var_78], ax
0x180025bb9  lea     rdx, [rbp+57h+var_78]
0x180025bbd  mov     rcx, rsi; JobHandle
0x180025bc0  call    ?GetContainerObjectRootPath@container@@YAXPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; container::GetContainerObjectRootPath(void *,std::wstring &)
0x180025bc5  cmp     qword ptr [rbx+18h], 7
0x180025bca  jbe     short loc_180025BD1
0x180025bcc  mov     rcx, [rbx]
0x180025bcf  jmp     short loc_180025BD4
0x180025bd1  mov     rcx, rbx
0x180025bd4  movzx   ecx, word ptr [rcx]; C
0x180025bd7  call    cs:__imp_towupper
0x180025bde  nop     dword ptr [rax+rax+00h]
0x180025be3  movzx   r14d, ax
0x180025be7  lea     rax, [rbp+57h+var_98]
0x180025beb  mov     [rbp+57h+var_C0], rax
0x180025bef  lea     rdx, [rbx+20h]
0x180025bf3  lea     rcx, [rbp+57h+var_98]
0x180025bf7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025bfc  mov     r15, rax
0x180025bff  mov     rdx, qword ptr [rbp+57h+var_68]
0x180025c03  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180025c0d  sub     rcx, rdx
0x180025c10  cmp     rcx, 4
0x180025c14  jb      loc_180025CF1
0x180025c1a  lea     rcx, [rbp+57h+var_78]
0x180025c1e  cmp     qword ptr [rbp+57h+var_68+8], 7
0x180025c23  cmova   rcx, qword ptr [rbp+57h+var_78]
0x180025c28  mov     [rsp+110h+hTemplateFile], rdx
0x180025c2d  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rcx
0x180025c32  mov     qword ptr [rsp+110h+dwCreationDisposition], 4
0x180025c3b  lea     r9, asc_1800397E0; "\\\\?\\"
0x180025c42  lea     rcx, [rbp+57h+Src]
0x180025c46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180025c4b  nop
0x180025c4c  lea     rdx, aDeviceMountpoi; "\\Device\\MountPointManager"
0x180025c53  lea     rcx, [rbp+57h+Src]; Src
0x180025c57  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180025c5c  xorps   xmm0, xmm0
0x180025c5f  movups  [rbp+57h+var_B8], xmm0
0x180025c63  mov     qword ptr [rbp+57h+var_A8], 0
0x180025c6b  mov     qword ptr [rbp+57h+var_A8+8], 0
0x180025c73  movups  xmm0, xmmword ptr [rax]
0x180025c76  movups  [rbp+57h+var_B8], xmm0
0x180025c7a  movups  xmm1, xmmword ptr [rax+10h]
0x180025c7e  movups  [rbp+57h+var_A8], xmm1
0x180025c82  mov     qword ptr [rax+10h], 0
0x180025c8a  mov     qword ptr [rax+18h], 7
0x180025c92  xor     ecx, ecx
0x180025c94  mov     [rax], cx
0x180025c97  mov     r8, r15
0x180025c9a  movzx   edx, r14w
0x180025c9e  lea     rcx, [rbp+57h+var_B8]
0x180025ca2  call    ?NotifyMountManager@MountManager@container@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G0@Z; container::MountManager::NotifyMountManager(std::wstring,ushort,std::wstring)
0x180025ca7  nop
0x180025ca8  lea     rcx, [rbp+57h+Src]
0x180025cac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025cb1  nop
0x180025cb2  lea     rcx, [rbp+57h+var_78]
0x180025cb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025cbb  add     rbx, 40h ; '@'
0x180025cbf  cmp     rbx, rdi
0x180025cc2  jnz     loc_180025BA7
0x180025cc8  mov     rcx, [rbp+57h+var_38]
0x180025ccc  xor     rcx, rsp; StackCookie
0x180025ccf  call    __security_check_cookie
0x180025cd4  lea     r11, [rsp+110h+var_20]
0x180025cdc  mov     rbx, [r11+40h]
0x180025ce0  movaps  xmm6, xmmword ptr [r11-10h]
0x180025ce5  mov     rsp, r11
0x180025ce8  pop     r15
0x180025cea  pop     r14
0x180025cec  pop     rdi
0x180025ced  pop     rsi
0x180025cee  pop     rbp
0x180025cef  retn
0x180025cf1  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180025cf7  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\container"...
0x180025cfe  mov     edx, 0D3h; void *
0x180025d03  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180025d09  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\container"...
0x180025d10  mov     edx, 0DDh; void *
0x180025d15  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
