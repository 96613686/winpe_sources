# container::NamedPipeProvider::Setup(Schema::Containers::Definition::NamedPipeNamespace const &,void *)

- ea: `0x18002605c`
- end: `0x1800261eb`
- name: `?Setup@NamedPipeProvider@container@@YAXAEBUNamedPipeNamespace@Definition@Containers@Schema@@PEAX@Z`
- size: `399`
- prototype: `void __fastcall(container::NamedPipeProvider *__hidden this, const struct Schema::Containers::Definition::NamedPipeNamespace *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting, installer_update`

## callers

- `0x1800063f0`

## callees

- `0x180004c40`
- `0x18000b4bc`
- `0x18000bdec`
- `0x180025d24`
- `0x180025ed8`
- `0x18002605c`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18002610c`
- `ntdll!NtFsControlFile` at `0x18002610c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800260a4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800260a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002619f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002619f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall container::NamedPipeProvider::Setup(
        container::NamedPipeProvider *this,
        const struct Schema::Containers::Definition::NamedPipeNamespace *a2,
        void *a3)
{
  _BYTE *FileW; // rbx
  const char *v6; // r9
  NTSTATUS v7; // eax
  __int64 v8; // rsi
  __int64 v9; // r14
  const struct Schema::Containers::Definition::NamedPipeNamespace *v10; // rdi
  void *v11; // rbx
  void *v12; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-39h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v15[32]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v16[32]; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  const struct Schema::Containers::Definition::NamedPipeNamespace *InputBuffer; // [rsp+D0h] [rbp+77h] BYREF
  _BYTE *v19; // [rsp+D8h] [rbp+7Fh]

  FileW = CreateFileW(L"\\\\.\\pipe", 0x40000000u, 3u, 0, 3u, 0x80u, 0);
  v19 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\namedpipe_provider.cpp",
      v6);
  InputBuffer = a2;
  IoStatusBlock = 0;
  v7 = NtFsControlFile(FileW, 0, 0, 0, &IoStatusBlock, 0x118048u, &InputBuffer, 8u, 0, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\namedpipe_provider.cpp",
      (const char *)(unsigned int)v7,
      dwCreationDisposition);
  CloseHandle(FileW);
  if ( *((_QWORD *)this + 1) != *(_QWORD *)this )
  {
    container::NamedPipe::OpenContainerNpfs(&InputBuffer, a2);
    v8 = *(_QWORD *)this;
    v9 = *((_QWORD *)this + 1);
    v10 = InputBuffer;
    while ( v8 != v9 )
    {
      v19 = v15;
      v11 = (void *)std::wstring::wstring(v15, v8 + 32);
      v12 = (void *)std::wstring::wstring(v16, v8);
      container::NamedPipe::CreateSymlink(v10, v12, v11);
      v8 += 64;
    }
    if ( (unsigned __int64)v10 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v10);
  }
}

```

## disassembly

```asm
0x18002605c  mov     [rsp-8+arg_0], rbx
0x180026061  mov     [rsp-8+arg_8], rsi
0x180026066  push    rbp
0x180026067  push    rdi
0x180026068  push    r14
0x18002606a  lea     rbp, [rsp-47h]
0x18002606f  sub     rsp, 0A0h
0x180026076  mov     rsi, rdx
0x180026079  mov     rdi, rcx
0x18002607c  xor     r14d, r14d
0x18002607f  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x180026084  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002608c  lea     r8d, [r14+3]; dwShareMode
0x180026090  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180026095  xor     r9d, r9d; lpSecurityAttributes
0x180026098  mov     edx, 40000000h; dwDesiredAccess
0x18002609d  lea     rcx, aPipe; "\\\\.\\pipe"
0x1800260a4  call    cs:__imp_CreateFileW
0x1800260ab  nop     dword ptr [rax+rax+00h]
0x1800260b0  mov     rbx, rax
0x1800260b3  mov     [rbp+57h+arg_18], rax
0x1800260b7  mov     rcx, [rbp+5Fh]; this
0x1800260bb  inc     rax
0x1800260be  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800260c4  jz      loc_1800261D9
0x1800260ca  mov     [rbp+57h+InputBuffer], rsi
0x1800260ce  xorps   xmm0, xmm0
0x1800260d1  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800260d5  mov     [rsp+0B0h+OutputBufferLength], r14d; OutputBufferLength
0x1800260da  mov     [rsp+0B0h+OutputBuffer], r14; OutputBuffer
0x1800260df  mov     [rsp+0B0h+InputBufferLength], 8; InputBufferLength
0x1800260e7  lea     rax, [rbp+57h+InputBuffer]
0x1800260eb  mov     [rsp+0B0h+hTemplateFile], rax; InputBuffer
0x1800260f0  mov     [rsp+0B0h+dwFlagsAndAttributes], 118048h; FsControlCode
0x1800260f8  lea     rax, [rbp+57h+IoStatusBlock]
0x1800260fc  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x180026101  xor     r9d, r9d; ApcContext
0x180026104  xor     r8d, r8d; ApcRoutine
0x180026107  xor     edx, edx; Event
0x180026109  mov     rcx, rbx; FileHandle
0x18002610c  call    cs:__imp_NtFsControlFile
0x180026113  nop     dword ptr [rax+rax+00h]
0x180026118  mov     rcx, [rbp+5Fh]; this
0x18002611c  test    eax, eax
0x18002611e  js      loc_1800261C4
0x180026124  mov     rcx, rbx; hObject
0x180026127  call    cs:__imp_CloseHandle
0x18002612e  nop     dword ptr [rax+rax+00h]
0x180026133  mov     rax, [rdi+8]
0x180026137  cmp     rax, [rdi]
0x18002613a  jz      short loc_1800261AB
0x18002613c  mov     rdx, rsi
0x18002613f  lea     rcx, [rbp+57h+InputBuffer]
0x180026143  call    ?OpenContainerNpfs@NamedPipe@container@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX@Z; container::NamedPipe::OpenContainerNpfs(void *)
0x180026148  nop
0x180026149  mov     rsi, [rdi]
0x18002614c  mov     r14, [rdi+8]
0x180026150  mov     rdi, [rbp+57h+InputBuffer]
0x180026154  jmp     short loc_18002618D
0x180026156  lea     rax, [rbp+57h+var_50]
0x18002615a  mov     [rbp+57h+arg_18], rax
0x18002615e  lea     rdx, [rsi+20h]
0x180026162  lea     rcx, [rbp+57h+var_50]
0x180026166  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002616b  mov     rbx, rax
0x18002616e  mov     rdx, rsi
0x180026171  lea     rcx, [rbp+57h+var_30]
0x180026175  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002617a  nop
0x18002617b  mov     r8, rbx; void *
0x18002617e  mov     rdx, rax; Src
0x180026181  mov     rcx, rdi; FileHandle
0x180026184  call    ?CreateSymlink@NamedPipe@container@@YAXPEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; container::NamedPipe::CreateSymlink(void *,std::wstring,std::wstring)
0x180026189  add     rsi, 40h ; '@'
0x18002618d  cmp     rsi, r14
0x180026190  jnz     short loc_180026156
0x180026192  lea     rax, [rdi-1]
0x180026196  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002619a  ja      short loc_1800261AB
0x18002619c  mov     rcx, rdi; hObject
0x18002619f  call    cs:__imp_CloseHandle
0x1800261a6  nop     dword ptr [rax+rax+00h]
0x1800261ab  lea     r11, [rsp+0B0h+var_10]
0x1800261b3  mov     rbx, [r11+20h]
0x1800261b7  mov     rsi, [r11+28h]
0x1800261bb  mov     rsp, r11
0x1800261be  pop     r14
0x1800261c0  pop     rdi
0x1800261c1  pop     rbp
0x1800261c2  retn
0x1800261c4  mov     r9d, eax; char *
0x1800261c7  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\container"...
0x1800261ce  mov     edx, 0A2h; void *
0x1800261d3  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1800261d9  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\container"...
0x1800261e0  mov     edx, 93h; void *
0x1800261e5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
