# NamedPipeAdaptor::BeginWritePipe(void)

- ea: `0x14002c470`
- end: `0x14002c53b`
- name: `?BeginWritePipe@NamedPipeAdaptor@@AEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(NamedPipeAdaptor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002d770`

## callees

- `0x140002204`
- `0x140008168`
- `0x14002c470`
- `0x14002cc10`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c50b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c50b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002c501`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002c501`

## string_xrefs

- `0x14002c51d`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`

## pseudocode

```c
__int64 __fastcall NamedPipeAdaptor::BeginWritePipe(NamedPipeAdaptor *this)
{
  __int64 v2; // rcx
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *ModeName; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  if ( (unsigned int)dword_140088090 > 5 )
  {
    v9 = *((_QWORD *)this + 39) - *((_QWORD *)this + 38);
    ModeName = NamedPipeAdaptor::GetModeName(this);
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v2 + 48) + 48LL))(v2 + 48);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v3,
      (unsigned int)word_14007FCAA,
      v4,
      v5,
      (__int64)&v11,
      (__int64)&ModeName,
      (__int64)&v9);
  }
  if ( WriteFile(
         *((HANDLE *)this + 25),
         *((LPCVOID *)this + 38),
         *((_DWORD *)this + 78) - *((_QWORD *)this + 38),
         0,
         (LPOVERLAPPED)((char *)this + 272))
    || GetLastError() == 997 )
  {
    return 0;
  }
  else
  {
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1F5,
             (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
             v6);
  }
}

```

## disassembly

```asm
0x14002c470  push    rbx
0x14002c472  sub     rsp, 40h
0x14002c476  mov     eax, cs:dword_140088090
0x14002c47c  mov     rbx, rcx
0x14002c47f  cmp     eax, 5
0x14002c482  jbe     short loc_14002C4E0
0x14002c484  mov     rax, [rcx+138h]
0x14002c48b  sub     rax, [rcx+130h]
0x14002c492  mov     [rsp+48h+arg_0], rax
0x14002c497  call    ?GetModeName@NamedPipeAdaptor@@AEBAPEBGXZ; NamedPipeAdaptor::GetModeName(void)
0x14002c49c  mov     [rsp+48h+arg_8], rax
0x14002c4a1  add     rcx, 30h ; '0'
0x14002c4a5  mov     rax, [rcx]
0x14002c4a8  mov     rax, [rax+30h]
0x14002c4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c4b1  mov     [rsp+48h+arg_10], rax
0x14002c4b6  lea     rdx, word_14007FCAA
0x14002c4bd  lea     rax, [rsp+48h+arg_0]
0x14002c4c2  mov     [rsp+48h+var_18], rax
0x14002c4c7  lea     rax, [rsp+48h+arg_8]
0x14002c4cc  mov     [rsp+48h+var_20], rax
0x14002c4d1  lea     rax, [rsp+48h+arg_10]
0x14002c4d6  mov     [rsp+48h+lpOverlapped], rax
0x14002c4db  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14002c4e0  mov     rcx, [rbx+0C8h]; hFile
0x14002c4e7  lea     rax, [rbx+110h]
0x14002c4ee  mov     rdx, [rax+20h]; lpBuffer
0x14002c4f2  xor     r9d, r9d; lpNumberOfBytesWritten
0x14002c4f5  mov     r8d, [rax+28h]
0x14002c4f9  sub     r8d, edx; nNumberOfBytesToWrite
0x14002c4fc  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x14002c501  call    cs:__imp_WriteFile
0x14002c507  test    eax, eax
0x14002c509  jnz     short loc_14002C533
0x14002c50b  call    cs:__imp_GetLastError
0x14002c511  cmp     eax, 3E5h
0x14002c516  jz      short loc_14002C533
0x14002c518  mov     rcx, [rsp+48h]; this
0x14002c51d  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002c524  mov     edx, 1F5h; void *
0x14002c529  add     rsp, 40h
0x14002c52d  pop     rbx
0x14002c52e  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002c533  xor     eax, eax
0x14002c535  add     rsp, 40h
0x14002c539  pop     rbx
0x14002c53a  retn
```
