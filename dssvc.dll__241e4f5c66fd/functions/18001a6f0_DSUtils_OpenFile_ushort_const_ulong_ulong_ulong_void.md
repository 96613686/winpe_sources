# DSUtils::OpenFile(ushort const *,ulong,ulong,ulong,void * *)

- ea: `0x18001a6f0`
- end: `0x18001a7c3`
- name: `?OpenFile@DSUtils@@YAJPEBGKKKPEAPEAX@Z`
- size: `211`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, DWORD, DWORD, _QWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000ca4c`
- `0x18000d3e4`
- `0x1800125c4`
- `0x18001a7cc`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000f1a0`
- `0x18001a6f0`
- `0x18001ab6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a744`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a726`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a726`

## string_xrefs

- `0x18001a773`: `Failed to open file %s, with DesiredAccess=0x%x, ShareMode=0x%x, FlagsAndAttributes=0x%x, HR=0x%x`
- `0x18001a780`: `DSUtils::OpenFile`

## pseudocode

```c
__int64 __fastcall DSUtils::OpenFile(const WCHAR *this, const unsigned __int16 *a2, DWORD a3, DWORD a4, _QWORD *a5)
{
  int v7; // ebp
  HANDLE FileW; // rax
  __int64 v10; // rcx
  signed int LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // ebx
  DSLogger *v17; // rax
  __int64 v19; // [rsp+28h] [rbp-60h]
  __int64 v20; // [rsp+30h] [rbp-58h]
  _QWORD v21[7]; // [rsp+50h] [rbp-38h] BYREF

  v7 = (int)a2;
  v21[0] = -1;
  FileW = CreateFileW(this, (DWORD)a2, a3, 0, 3u, a4, 0);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::reset(v21, FileW);
  v10 = v21[0];
  if ( v21[0] == -1 )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    v17 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v13,
                        v12,
                        v14,
                        v15);
    LODWORD(v20) = a3;
    LODWORD(v19) = v7;
    DSLogger::LogError(
      v17,
      L"DSUtils::OpenFile",
      0x81u,
      L"Failed to open file %s, with DesiredAccess=0x%x, ShareMode=0x%x, FlagsAndAttributes=0x%x, HR=0x%x",
      this,
      v19,
      v20,
      a4,
      v16);
  }
  else
  {
    v16 = 0;
    if ( a5 )
    {
      v21[0] = -1;
      *a5 = v10;
    }
  }
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(v21);
  return v16;
}

```

## disassembly

```asm
0x18001a6f0  mov     rax, rsp
0x18001a6f3  push    rbx
0x18001a6f4  push    rbp
0x18001a6f5  push    rsi
0x18001a6f6  push    rdi
0x18001a6f7  push    r14
0x18001a6f9  sub     rsp, 60h
0x18001a6fd  mov     edi, r9d
0x18001a700  mov     esi, r8d
0x18001a703  mov     ebp, edx
0x18001a705  mov     r14, rcx
0x18001a708  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFFh
0x18001a710  mov     qword ptr [rax-58h], 0
0x18001a718  mov     [rax-60h], r9d
0x18001a71c  mov     dword ptr [rax-68h], 3
0x18001a723  xor     r9d, r9d; lpSecurityAttributes
0x18001a726  call    cs:__imp_CreateFileW
0x18001a72c  mov     rdx, rax
0x18001a72f  lea     rcx, [rsp+88h+var_38]
0x18001a734  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::reset(void *)
0x18001a739  mov     rcx, [rsp+88h+var_38]
0x18001a73e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a742  jnz     short loc_18001A791
0x18001a744  call    cs:__imp_GetLastError
0x18001a74a  mov     ebx, eax
0x18001a74c  test    eax, eax
0x18001a74e  jle     short loc_18001A759
0x18001a750  movzx   ebx, ax
0x18001a753  or      ebx, 80070000h
0x18001a759  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a75e  mov     [rsp+88h+var_48], ebx
0x18001a762  mov     [rsp+88h+var_50], edi
0x18001a766  mov     dword ptr [rsp+88h+var_58], esi
0x18001a76a  mov     dword ptr [rsp+88h+var_60], ebp
0x18001a76e  mov     [rsp+88h+var_68], r14
0x18001a773  lea     r9, aFailedToOpenFi; "Failed to open file %s, with DesiredAcc"...
0x18001a77a  mov     r8d, 81h; unsigned int
0x18001a780  lea     rdx, aDsutilsOpenfil; "DSUtils::OpenFile"
0x18001a787  mov     rcx, rax; this
0x18001a78a  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001a78f  jmp     short loc_18001A7AC
0x18001a791  xor     ebx, ebx
0x18001a793  mov     rax, qword ptr [rsp+88h+arg_20]
0x18001a79b  test    rax, rax
0x18001a79e  jz      short loc_18001A7AC
0x18001a7a0  mov     [rsp+88h+var_38], 0FFFFFFFFFFFFFFFFh
0x18001a7a9  mov     [rax], rcx
0x18001a7ac  lea     rcx, [rsp+88h+var_38]
0x18001a7b1  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x18001a7b6  mov     eax, ebx
0x18001a7b8  add     rsp, 60h
0x18001a7bc  pop     r14
0x18001a7be  pop     rdi
0x18001a7bf  pop     rsi
0x18001a7c0  pop     rbp
0x18001a7c1  pop     rbx
0x18001a7c2  retn
```
