# HyperVFileIo::SetFileSize(unsigned __int64)

- ea: `0x180081510`
- end: `0x180081609`
- name: `?SetFileSize@HyperVFileIo@@UEAAX_K@Z`
- size: `249`
- prototype: `void __fastcall(HyperVFileIo *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180080840`

## callees

- `0x18001587c`
- `0x18007e39c`
- `0x18007e700`
- `0x18007fd80`
- `0x18007ff40`
- `0x180081510`
- `0x18008226c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008154c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008154c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081598`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18008153e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18008153e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18008158e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18008158e`

## string_xrefs

- `0x1800815e9`: `onecore\vm\common\hypervstorage\hypervfileio.cpp`

## pseudocode

```c
void __fastcall HyperVFileIo::SetFileSize(HyperVFileIo *this, unsigned __int64 a2)
{
  DWORD LastError; // esi
  const unsigned __int16 *v5; // rdi
  const unsigned __int16 *v6; // rdx
  void *v7; // r8
  void *v8; // r8
  unsigned int v9; // [rsp+20h] [rbp-48h]
  struct _GUID v10; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  HyperVFileIo::EnsureFileIsConnected(this);
  if ( (*((_BYTE *)this + 144) & 0x20) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6C5,
      (unsigned int)"onecore\\vm\\common\\hypervstorage\\hypervfileio.cpp",
      (const char *)0x800710DDLL,
      v9);
  if ( SetFilePointerEx(*((HANDLE *)this + 9), (LARGE_INTEGER)a2, 0, 0) )
    LastError = 0;
  else
    LastError = GetLastError();
  v5 = (const unsigned __int16 *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) <= 7u )
    v6 = (const unsigned __int16 *)((char *)this + 40);
  else
    v6 = *(const unsigned __int16 **)v5;
  v7 = (void *)*((_QWORD *)this + 9);
  v10 = *(struct _GUID *)((char *)this + 8);
  HyperVStorageTrace::HyperVFileIo_SetFileSize(&v10, v6, v7, a2, LastError);
  if ( LastError )
    HvsThrowWin32Error(LastError);
  if ( !SetEndOfFile(*((HANDLE *)this + 9)) )
    LastError = GetLastError();
  if ( *((_QWORD *)this + 8) > 7u )
    v5 = *(const unsigned __int16 **)v5;
  v8 = (void *)*((_QWORD *)this + 9);
  v10 = *(struct _GUID *)((char *)this + 8);
  HyperVStorageTrace::HyperVFileIo_SetEndOfFile(&v10, v5, v8, LastError);
  if ( LastError )
    HvsThrowWin32Error(LastError);
  HyperVFileIo::FlushBuffers(this);
}

```

## disassembly

```asm
0x180081510  push    rbx
0x180081512  push    rbp
0x180081513  push    rsi
0x180081514  push    rdi
0x180081515  sub     rsp, 48h
0x180081519  mov     rbp, rdx
0x18008151c  mov     rbx, rcx
0x18008151f  call    ?EnsureFileIsConnected@HyperVFileIo@@AEAAXXZ; HyperVFileIo::EnsureFileIsConnected(void)
0x180081524  test    byte ptr [rbx+90h], 20h
0x18008152b  jnz     loc_1800815E4
0x180081531  mov     rcx, [rbx+48h]; hFile
0x180081535  xor     r9d, r9d; dwMoveMethod
0x180081538  xor     r8d, r8d; lpNewFilePointer
0x18008153b  mov     rdx, rbp; liDistanceToMove
0x18008153e  call    cs:__imp_SetFilePointerEx
0x180081544  test    eax, eax
0x180081546  jz      short loc_18008154C
0x180081548  xor     esi, esi
0x18008154a  jmp     short loc_180081554
0x18008154c  call    cs:__imp_GetLastError
0x180081552  mov     esi, eax
0x180081554  lea     rdi, [rbx+28h]
0x180081558  cmp     qword ptr [rdi+18h], 7
0x18008155d  jbe     short loc_180081564
0x18008155f  mov     rdx, [rdi]
0x180081562  jmp     short loc_180081567
0x180081564  mov     rdx, rdi; unsigned __int16 *
0x180081567  movups  xmm0, xmmword ptr [rbx+8]
0x18008156b  mov     r8, [rbx+48h]; void *
0x18008156f  lea     rcx, [rsp+68h+var_38]; struct _GUID *
0x180081574  mov     r9, rbp; unsigned __int64
0x180081577  mov     [rsp+68h+var_48], esi; unsigned int
0x18008157b  movdqu  xmmword ptr [rsp+68h+var_38.Data1], xmm0
0x180081581  call    ?HyperVFileIo_SetFileSize@HyperVStorageTrace@@SAXU_GUID@@PEBGPEAX_KK@Z; HyperVStorageTrace::HyperVFileIo_SetFileSize(_GUID,ushort const *,void *,unsigned __int64,ulong)
0x180081586  test    esi, esi
0x180081588  jnz     short loc_180081601
0x18008158a  mov     rcx, [rbx+48h]; hFile
0x18008158e  call    cs:__imp_SetEndOfFile
0x180081594  test    eax, eax
0x180081596  jnz     short loc_1800815A0
0x180081598  call    cs:__imp_GetLastError
0x18008159e  mov     esi, eax
0x1800815a0  cmp     qword ptr [rdi+18h], 7
0x1800815a5  jbe     short loc_1800815AA
0x1800815a7  mov     rdi, [rdi]
0x1800815aa  movups  xmm0, xmmword ptr [rbx+8]
0x1800815ae  mov     r8, [rbx+48h]; void *
0x1800815b2  lea     rcx, [rsp+68h+var_38]; struct _GUID
0x1800815b7  mov     r9d, esi; unsigned int
0x1800815ba  mov     rdx, rdi; unsigned __int16 *
0x1800815bd  movdqu  xmmword ptr [rsp+68h+var_38.Data1], xmm0
0x1800815c3  call    ?HyperVFileIo_SetEndOfFile@HyperVStorageTrace@@SAXU_GUID@@PEBGPEAXK@Z; HyperVStorageTrace::HyperVFileIo_SetEndOfFile(_GUID,ushort const *,void *,ulong)
0x1800815c8  test    esi, esi
0x1800815ca  jnz     short loc_1800815DC
0x1800815cc  mov     rcx, rbx; this
0x1800815cf  add     rsp, 48h
0x1800815d3  pop     rdi
0x1800815d4  pop     rsi
0x1800815d5  pop     rbp
0x1800815d6  pop     rbx
0x1800815d7  jmp     ?FlushBuffers@HyperVFileIo@@UEAAXXZ; HyperVFileIo::FlushBuffers(void)
0x1800815dc  mov     ecx, esi; unsigned int
0x1800815de  call    ?HvsThrowWin32Error@@YAXK@Z; HvsThrowWin32Error(ulong)
0x1800815e4  mov     rcx, [rsp+68h]; this
0x1800815e9  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\hypervstorage\\hyp"...
0x1800815f0  mov     r9d, 800710DDh; char *
0x1800815f6  mov     edx, 6C5h; void *
0x1800815fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081601  mov     ecx, esi; unsigned int
0x180081603  call    ?HvsThrowWin32Error@@YAXK@Z; HvsThrowWin32Error(ulong)
```
