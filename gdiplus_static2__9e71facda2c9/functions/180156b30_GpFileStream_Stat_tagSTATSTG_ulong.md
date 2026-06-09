# GpFileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x180156b30`
- end: `0x180156c4b`
- name: `?Stat@GpFileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `283`
- prototype: `__int64 __fastcall(GpFileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800599b0`
- `0x18008c194`
- `0x1800f784c`
- `0x180156b30`
- `0x180171428`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180156ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180156ba6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180156c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180156c04`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180156b92`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180156b92`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180156bcf`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180156bcf`

## pseudocode

```c
__int64 __fastcall GpFileStream::Stat(GpFileStream *this, struct tagSTATSTG *a2, char a3)
{
  unsigned int Win32HRESULT; // ecx
  DWORD FileSize; // eax
  const unsigned __int16 *v8; // rdx
  SIZE_T v9; // rsi
  void *v10; // rax
  int v12; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v13; // [rsp+28h] [rbp-10h]

  GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)&v12, (GpFileStream *)((char *)this + 16));
  if ( v12 )
  {
    Win32HRESULT = -2147024726;
  }
  else
  {
    *((_DWORD *)a2 + 2) = 2;
    *((_DWORD *)a2 + 12) = *((_DWORD *)this + 10);
    *((_QWORD *)a2 + 9) = 0;
    *(_OWORD *)((char *)a2 + 56) = 0;
    *((_DWORD *)a2 + 13) = 0;
    FileSize = GetFileSize(*((HANDLE *)this + 3), (LPDWORD)a2 + 5);
    *((_DWORD *)a2 + 4) = FileSize;
    if ( (FileSize != -1 || !GetLastError())
      && GetFileTime(*((HANDLE *)this + 3), (LPFILETIME)a2 + 4, (LPFILETIME)a2 + 5, (LPFILETIME)a2 + 3) )
    {
      if ( (a3 & 1) != 0 )
      {
        *(_QWORD *)a2 = 0;
      }
      else
      {
        v9 = (int)(2 * GpRuntime::UnicodeStringLength(*((GpRuntime **)this + 4), v8) + 2);
        v10 = CoTaskMemAlloc(v9);
        *(_QWORD *)a2 = v10;
        if ( !v10 )
        {
          Win32HRESULT = -2147024882;
          goto LABEL_13;
        }
        memcpy_0(v10, *((const void **)this + 4), v9);
      }
      Win32HRESULT = 0;
      goto LABEL_13;
    }
    Win32HRESULT = GetWin32HRESULT();
  }
LABEL_13:
  _InterlockedDecrement(v13);
  return Win32HRESULT;
}

```

## disassembly

```asm
0x180156b30  mov     [rsp+arg_0], rbx
0x180156b35  mov     [rsp+arg_8], rsi
0x180156b3a  push    rdi
0x180156b3b  sub     rsp, 30h
0x180156b3f  mov     rbx, rdx
0x180156b42  mov     rdi, rcx
0x180156b45  lea     rdx, [rcx+10h]; struct GpRuntime::GpLockable *
0x180156b49  mov     esi, r8d
0x180156b4c  lea     rcx, [rsp+38h+var_18]; this
0x180156b51  call    ??0GpLock@GpRuntime@@QEAA@PEAVGpLockable@1@@Z; GpRuntime::GpLock::GpLock(GpRuntime::GpLockable *)
0x180156b56  cmp     [rsp+38h+var_18], 0
0x180156b5b  jz      short loc_180156B67
0x180156b5d  mov     ecx, 800700AAh
0x180156b62  jmp     loc_180156C30
0x180156b67  mov     dword ptr [rbx+8], 2
0x180156b6e  lea     rdx, [rbx+14h]; lpFileSizeHigh
0x180156b72  mov     eax, [rdi+28h]
0x180156b75  xorps   xmm0, xmm0
0x180156b78  mov     [rbx+30h], eax
0x180156b7b  mov     qword ptr [rbx+48h], 0
0x180156b83  movups  xmmword ptr [rbx+38h], xmm0
0x180156b87  mov     dword ptr [rbx+34h], 0
0x180156b8e  mov     rcx, [rdi+18h]; hFile
0x180156b92  call    cs:__imp_GetFileSize
0x180156b99  nop     dword ptr [rax+rax+00h]
0x180156b9e  mov     [rbx+10h], eax
0x180156ba1  cmp     eax, 0FFFFFFFFh
0x180156ba4  jnz     short loc_180156BBF
0x180156ba6  call    cs:__imp_GetLastError
0x180156bad  nop     dword ptr [rax+rax+00h]
0x180156bb2  test    eax, eax
0x180156bb4  jz      short loc_180156BBF
0x180156bb6  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x180156bbb  mov     ecx, eax
0x180156bbd  jmp     short loc_180156C30
0x180156bbf  mov     rcx, [rdi+18h]; hFile
0x180156bc3  lea     r9, [rbx+18h]; lpLastWriteTime
0x180156bc7  lea     r8, [rbx+28h]; lpLastAccessTime
0x180156bcb  lea     rdx, [rbx+20h]; lpCreationTime
0x180156bcf  call    cs:__imp_GetFileTime
0x180156bd6  nop     dword ptr [rax+rax+00h]
0x180156bdb  test    eax, eax
0x180156bdd  jz      short loc_180156BB6
0x180156bdf  test    sil, 1
0x180156be3  jz      short loc_180156BEE
0x180156be5  mov     qword ptr [rbx], 0
0x180156bec  jmp     short loc_180156C2E
0x180156bee  mov     rcx, [rdi+20h]; this
0x180156bf2  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x180156bf7  lea     eax, ds:2[rax*2]
0x180156bfe  movsxd  rsi, eax
0x180156c01  mov     rcx, rsi; cb
0x180156c04  call    cs:__imp_CoTaskMemAlloc
0x180156c0b  nop     dword ptr [rax+rax+00h]
0x180156c10  mov     [rbx], rax
0x180156c13  test    rax, rax
0x180156c16  jnz     short loc_180156C1F
0x180156c18  mov     ecx, 8007000Eh
0x180156c1d  jmp     short loc_180156C30
0x180156c1f  mov     rdx, [rdi+20h]; Src
0x180156c23  mov     r8, rsi; Size
0x180156c26  mov     rcx, rax; void *
0x180156c29  call    memcpy_0
0x180156c2e  xor     ecx, ecx
0x180156c30  mov     rax, [rsp+38h+var_10]
0x180156c35  mov     rbx, [rsp+38h+arg_0]
0x180156c3a  mov     rsi, [rsp+38h+arg_8]
0x180156c3f  lock dec dword ptr [rax]
0x180156c42  mov     eax, ecx
0x180156c44  add     rsp, 30h
0x180156c48  pop     rdi
0x180156c49  retn
```
