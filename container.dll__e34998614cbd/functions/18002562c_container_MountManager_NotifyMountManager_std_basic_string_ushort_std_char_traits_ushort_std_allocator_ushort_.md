# container::MountManager::NotifyMountManager(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18002562c`
- end: `0x180025837`
- name: `?NotifyMountManager@MountManager@container@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G0@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180025aa8`

## callees

- `0x180002ad0`
- `0x180003614`
- `0x18000362c`
- `0x180004c40`
- `0x1800051b0`
- `0x18000bdec`
- `0x18001d894`
- `0x18001e6dc`
- `0x18002562c`
- `0x180025840`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025769`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025769`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025696`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025696`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800257bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800257bb`

## string_xrefs

- `0x180025801`: `onecore\base\gendrv\silos\container\mount_provider.cpp`
- `0x180025813`: `onecore\base\gendrv\silos\container\mount_provider.cpp`
- `0x180025825`: `onecore\base\gendrv\silos\container\mount_provider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall container::MountManager::NotifyMountManager(const WCHAR *a1, __int64 a2, __int64 a3)
{
  const WCHAR *v4; // rsi
  HANDLE FileW; // rbx
  const char *v6; // r9
  __int64 v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rdi
  void *v10; // r12
  unsigned __int16 v11; // ax
  const void *v12; // rdx
  BOOL v13; // edi
  const char *v14; // r9
  const char *v15; // r9
  DWORD BytesReturned; // [rsp+40h] [rbp-49h] BYREF
  void *lpInBuffer[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v19; // [rsp+58h] [rbp-31h]
  __int64 v20; // [rsp+60h] [rbp-29h]
  HANDLE v21; // [rsp+68h] [rbp-21h]
  _BYTE v22[32]; // [rsp+70h] [rbp-19h] BYREF
  const WCHAR *v23; // [rsp+90h] [rbp+7h]
  __int64 v24; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = a1;
  v23 = a1;
  v24 = a3;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  FileW = CreateFileW(a1, 0xC0000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v21 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\mount_provider.cpp",
      v6);
  v7 = std::wstring::wstring(v22, a3);
  v20 = v7;
  *(_OWORD *)lpInBuffer = 0;
  v19 = 0;
  BytesReturned = 0;
  v8 = *(_QWORD *)(v7 + 16);
  v9 = 2 * v8 + 6;
  if ( 2 * v8 != -6 )
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpInBuffer, 2 * v8 + 6);
  memset_0(lpInBuffer[0], 0, v9);
  v10 = lpInBuffer[0];
  v11 = 2 * *(_WORD *)(v7 + 16);
  *(_WORD *)lpInBuffer[0] = v11;
  if ( *(_QWORD *)(v7 + 24) <= 7u )
    v12 = (const void *)v7;
  else
    v12 = *(const void **)v7;
  memcpy_0((char *)lpInBuffer[0] + 2, v12, v11);
  v13 = DeviceIoControl(FileW, 0x6D402Cu, v10, v9, 0, 0, &BytesReturned, 0);
  std::vector<unsigned char>::~vector<unsigned char>(lpInBuffer);
  std::wstring::~wstring(v7);
  if ( !v13 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\mount_provider.cpp",
      v14);
  std::wstring::wstring(v22, a3);
  if ( !(unsigned int)container::MountManager::SetVolumeNameForRoot(FileW) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\mount_provider.cpp",
      v15);
  CloseHandle(FileW);
  std::wstring::~wstring(v4);
  return std::wstring::~wstring(a3);
}

```

## disassembly

```asm
0x18002562c  mov     [rsp-8+arg_18], rbx
0x180025631  push    rbp
0x180025632  push    rsi
0x180025633  push    rdi
0x180025634  push    r12
0x180025636  push    r13
0x180025638  push    r14
0x18002563a  push    r15
0x18002563c  lea     rbp, [rsp-27h]
0x180025641  sub     rsp, 0B0h
0x180025648  mov     rax, cs:__security_cookie
0x18002564f  xor     rax, rsp
0x180025652  mov     [rbp+57h+var_40], rax
0x180025656  mov     r15, r8
0x180025659  movzx   r13d, dx
0x18002565d  mov     rsi, rcx
0x180025660  mov     [rbp+57h+var_50], rcx
0x180025664  mov     [rbp+57h+var_48], r8
0x180025668  cmp     qword ptr [rcx+18h], 7
0x18002566d  jbe     short loc_180025672
0x18002566f  mov     rcx, [rcx]; lpFileName
0x180025672  mov     [rsp+0E0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x18002567b  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180025683  mov     r8d, 3; dwShareMode
0x180025689  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002568e  xor     r9d, r9d; lpSecurityAttributes
0x180025691  mov     edx, 0C0000000h; dwDesiredAccess
0x180025696  call    cs:__imp_CreateFileW
0x18002569d  nop     dword ptr [rax+rax+00h]
0x1800256a2  mov     rbx, rax
0x1800256a5  mov     [rbp+57h+var_78], rax
0x1800256a9  mov     rcx, [rbp+5Fh]; this
0x1800256ad  inc     rax
0x1800256b0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800256b6  jz      loc_180025813
0x1800256bc  mov     rdx, r15
0x1800256bf  lea     rcx, [rbp+57h+var_70]
0x1800256c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800256c8  mov     r14, rax
0x1800256cb  mov     [rbp+57h+var_80], rax
0x1800256cf  xorps   xmm0, xmm0
0x1800256d2  movdqu  xmmword ptr [rbp+57h+lpInBuffer], xmm0
0x1800256d7  mov     [rbp+57h+var_88], 0
0x1800256df  mov     [rbp+57h+BytesReturned], 0
0x1800256e6  mov     rcx, [rax+10h]
0x1800256ea  lea     rdi, ds:6[rcx*2]
0x1800256f2  test    rdi, rdi
0x1800256f5  jz      short loc_180025703
0x1800256f7  mov     rdx, rdi
0x1800256fa  lea     rcx, [rbp+57h+lpInBuffer]
0x1800256fe  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180025703  mov     r8, rdi; Size
0x180025706  xor     edx, edx; Val
0x180025708  mov     rcx, [rbp+57h+lpInBuffer]; void *
0x18002570c  call    memset_0
0x180025711  mov     r12, [rbp+57h+lpInBuffer]
0x180025715  movzx   eax, word ptr [r14+10h]
0x18002571a  add     ax, ax
0x18002571d  mov     [r12], ax
0x180025722  cmp     qword ptr [r14+18h], 7
0x180025727  jbe     short loc_18002572E
0x180025729  mov     rdx, [r14]
0x18002572c  jmp     short loc_180025731
0x18002572e  mov     rdx, r14; Src
0x180025731  movzx   r8d, ax; Size
0x180025735  mov     rcx, [rbp+57h+lpInBuffer]
0x180025739  add     rcx, 2; void *
0x18002573d  call    memcpy_0
0x180025742  mov     r9d, edi; nInBufferSize
0x180025745  xor     ecx, ecx
0x180025747  mov     [rsp+0E0h+lpOverlapped], rcx; lpOverlapped
0x18002574c  lea     rax, [rbp+57h+BytesReturned]
0x180025750  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x180025755  mov     [rsp+0E0h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x180025759  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rcx; lpOutBuffer
0x18002575e  mov     r8, r12; lpInBuffer
0x180025761  mov     edx, 6D402Ch; dwIoControlCode
0x180025766  mov     rcx, rbx; hDevice
0x180025769  call    cs:__imp_DeviceIoControl
0x180025770  nop     dword ptr [rax+rax+00h]
0x180025775  mov     edi, eax
0x180025777  lea     rcx, [rbp+57h+lpInBuffer]
0x18002577b  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180025780  nop
0x180025781  mov     rcx, r14
0x180025784  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025789  mov     rcx, [rbp+5Fh]; this
0x18002578d  test    edi, edi
0x18002578f  jz      loc_180025825
0x180025795  mov     rdx, r15
0x180025798  lea     rcx, [rbp+57h+var_70]
0x18002579c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800257a1  mov     r8, rax
0x1800257a4  movzx   edx, r13w
0x1800257a8  mov     rcx, rbx; hDevice
0x1800257ab  call    ?SetVolumeNameForRoot@MountManager@container@@YAHPEAXGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; container::MountManager::SetVolumeNameForRoot(void *,ushort,std::wstring)
0x1800257b0  mov     rcx, [rbp+5Fh]; this
0x1800257b4  test    eax, eax
0x1800257b6  jz      short loc_180025801
0x1800257b8  mov     rcx, rbx; hObject
0x1800257bb  call    cs:__imp_CloseHandle
0x1800257c2  nop     dword ptr [rax+rax+00h]
0x1800257c7  nop
0x1800257c8  mov     rcx, rsi
0x1800257cb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800257d0  nop
0x1800257d1  mov     rcx, r15
0x1800257d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800257d9  mov     rcx, [rbp+57h+var_40]
0x1800257dd  xor     rcx, rsp; StackCookie
0x1800257e0  call    __security_check_cookie
0x1800257e5  mov     rbx, [rsp+0E0h+arg_18]
0x1800257ed  add     rsp, 0B0h
0x1800257f4  pop     r15
0x1800257f6  pop     r14
0x1800257f8  pop     r13
0x1800257fa  pop     r12
0x1800257fc  pop     rdi
0x1800257fd  pop     rsi
0x1800257fe  pop     rbp
0x1800257ff  retn
0x180025801  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\container"...
0x180025808  mov     edx, 10Ch; void *
0x18002580d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180025813  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\container"...
0x18002581a  mov     edx, 106h; void *
0x18002581f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180025825  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\container"...
0x18002582c  mov     edx, 109h; void *
0x180025831  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
