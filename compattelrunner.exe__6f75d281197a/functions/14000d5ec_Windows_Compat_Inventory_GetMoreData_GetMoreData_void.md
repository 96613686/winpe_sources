# Windows::Compat::Inventory::GetMoreData::~GetMoreData(void)

- ea: `0x14000d5ec`
- end: `0x14000d6fa`
- name: `??1GetMoreData@Inventory@Compat@Windows@@QEAA@XZ`
- size: `270`
- prototype: `void __fastcall(Windows::Compat::Inventory::GetMoreData *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000b2a8`
- `0x14000c2f8`

## callees

- `0x140001e34`
- `0x14000d5ec`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14000d673`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14000d699`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14000d673`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14000d699`
- `msvcp_win!_Thrd_join` at `0x14000d68a`
- `msvcp_win!_Thrd_join` at `0x14000d68a`
- `msvcp_win!_Thrd_id` at `0x14000d664`
- `msvcp_win!_Thrd_id` at `0x14000d664`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14000d6c4`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14000d6c4`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x14000d6d8`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x14000d6d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d64d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d6b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d64d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d6b5`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x14000d63a`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x14000d63a`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::GetMoreData::~GetMoreData(Windows::Compat::Inventory::GetMoreData *this)
{
  char *FileA; // rax
  _Thrd_t *v3; // rsi
  _Thrd_id_t Id; // ebx
  char *v5; // rcx
  FILE *v6; // rcx
  _DWORD *v7; // rcx
  _Thrd_t v8; // [rsp+40h] [rbp-18h] BYREF

  *((_BYTE *)this + 24) = 1;
  if ( (unsigned __int64)(*((_QWORD *)this + 2) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileA = (char *)CreateFileA("\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
    if ( (unsigned __int64)(FileA - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileA);
  }
  v3 = *(_Thrd_t **)this;
  if ( *(_QWORD *)this && v3->_Id )
  {
    Id = v3->_Id;
    if ( Id == _Thrd_id() )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    v8 = *v3;
    if ( _Thrd_join(&v8, 0) )
    {
      std::_Throw_Cpp_error(2);
      __debugbreak();
    }
    *v3 = 0;
  }
  v5 = (char *)*((_QWORD *)this + 2);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  v6 = (FILE *)*((_QWORD *)this + 1);
  if ( v6 )
    fclose(v6);
  v7 = *(_DWORD **)this;
  if ( *(_QWORD *)this )
  {
    if ( v7[2] )
    {
      _o_terminate();
      __debugbreak();
    }
    operator delete(v7, 0x10u);
  }
}

```

## disassembly

```asm
0x14000d5ec  mov     [rsp+arg_0], rbx
0x14000d5f1  mov     [rsp+arg_8], rsi
0x14000d5f6  push    rdi
0x14000d5f7  sub     rsp, 50h
0x14000d5fb  mov     rdi, rcx
0x14000d5fe  mov     byte ptr [rcx+18h], 1
0x14000d602  mov     rax, [rcx+10h]
0x14000d606  dec     rax
0x14000d609  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d60d  ja      short loc_14000D653
0x14000d60f  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x14000d618  mov     [rsp+58h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14000d620  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x14000d628  xor     r9d, r9d; lpSecurityAttributes
0x14000d62b  xor     r8d, r8d; dwShareMode
0x14000d62e  mov     edx, 40000000h; dwDesiredAccess
0x14000d633  lea     rcx, Name; "\\\\.\\pipe\\GmdAslLogger"
0x14000d63a  call    cs:__imp_CreateFileA
0x14000d640  lea     rcx, [rax-1]
0x14000d644  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14000d648  ja      short loc_14000D653
0x14000d64a  mov     rcx, rax; hObject
0x14000d64d  call    cs:__imp_CloseHandle
0x14000d653  mov     rsi, [rdi]
0x14000d656  test    rsi, rsi
0x14000d659  jz      short loc_14000D6A7
0x14000d65b  cmp     dword ptr [rsi+8], 0
0x14000d65f  jz      short loc_14000D6A7
0x14000d661  mov     ebx, [rsi+8]
0x14000d664  call    cs:__imp__Thrd_id
0x14000d66a  cmp     ebx, eax
0x14000d66c  jnz     short loc_14000D67A
0x14000d66e  mov     ecx, 5
0x14000d673  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14000d679  int     3; Trap to Debugger
0x14000d67a  movups  xmm0, xmmword ptr [rsi]
0x14000d67d  movdqu  xmmword ptr [rsp+58h+var_18._Hnd], xmm0
0x14000d683  xor     edx, edx; int *
0x14000d685  lea     rcx, [rsp+58h+var_18]; _Thrd_t
0x14000d68a  call    cs:__imp__Thrd_join
0x14000d690  test    eax, eax
0x14000d692  jz      short loc_14000D6A0
0x14000d694  mov     ecx, 2
0x14000d699  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14000d69f  int     3; Trap to Debugger
0x14000d6a0  xorps   xmm0, xmm0
0x14000d6a3  movdqu  xmmword ptr [rsi], xmm0
0x14000d6a7  mov     rcx, [rdi+10h]; hObject
0x14000d6ab  lea     rax, [rcx-1]
0x14000d6af  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d6b3  ja      short loc_14000D6BB
0x14000d6b5  call    cs:__imp_CloseHandle
0x14000d6bb  mov     rcx, [rdi+8]; Stream
0x14000d6bf  test    rcx, rcx
0x14000d6c2  jz      short loc_14000D6CA
0x14000d6c4  call    cs:__imp_fclose
0x14000d6ca  mov     rcx, [rdi]; void *
0x14000d6cd  test    rcx, rcx
0x14000d6d0  jz      short loc_14000D6EA
0x14000d6d2  cmp     dword ptr [rcx+8], 0
0x14000d6d6  jz      short loc_14000D6DF
0x14000d6d8  call    cs:__imp__o_terminate
0x14000d6de  int     3; Trap to Debugger
0x14000d6df  mov     edx, 10h; unsigned __int64
0x14000d6e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d6e9  nop
0x14000d6ea  mov     rbx, [rsp+58h+arg_0]
0x14000d6ef  mov     rsi, [rsp+58h+arg_8]
0x14000d6f4  add     rsp, 50h
0x14000d6f8  pop     rdi
0x14000d6f9  retn
```
