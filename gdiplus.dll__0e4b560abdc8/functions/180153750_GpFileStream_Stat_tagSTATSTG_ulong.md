# GpFileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x180153750`
- end: `0x180153867`
- name: `?Stat@GpFileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `279`
- prototype: `__int64 __fastcall(GpFileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cc00`
- `0x180064e70`
- `0x1800e7040`
- `0x180153750`
- `0x1801740cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801537c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801537c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18015381d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18015381d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801537af`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801537af`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1801537ec`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1801537ec`

## pseudocode

```c
__int64 __fastcall GpFileStream::Stat(GpFileStream *this, struct tagSTATSTG *a2, char a3)
{
  unsigned int Win32HRESULT; // ebx
  DWORD FileSize; // eax
  const unsigned __int16 *v8; // rdx
  SIZE_T v9; // rbp
  void *v10; // rax
  int v12; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v13; // [rsp+28h] [rbp-10h]

  GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)&v12, (GpFileStream *)((char *)this + 16));
  Win32HRESULT = 0;
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
    if ( FileSize == -1 && GetLastError()
      || !GetFileTime(*((HANDLE *)this + 3), (LPFILETIME)a2 + 4, (LPFILETIME)a2 + 5, (LPFILETIME)a2 + 3) )
    {
      Win32HRESULT = GetWin32HRESULT();
    }
    else if ( (a3 & 1) != 0 )
    {
      *(_QWORD *)a2 = 0;
    }
    else
    {
      v9 = (int)(2 * GpRuntime::UnicodeStringLength(*((GpRuntime **)this + 4), v8) + 2);
      v10 = CoTaskMemAlloc(v9);
      *(_QWORD *)a2 = v10;
      if ( v10 )
        memcpy_0(v10, *((const void **)this + 4), v9);
      else
        Win32HRESULT = -2147024882;
    }
  }
  _InterlockedDecrement(v13);
  return Win32HRESULT;
}

```

## disassembly

```asm
0x180153750  mov     rax, rsp
0x180153753  mov     [rax+8], rbx
0x180153757  mov     [rax+10h], rbp
0x18015375b  mov     [rax+18h], rsi
0x18015375f  push    rdi
0x180153760  sub     rsp, 30h
0x180153764  mov     rdi, rdx
0x180153767  mov     rsi, rcx
0x18015376a  lea     rdx, [rcx+10h]; struct GpRuntime::GpLockable *
0x18015376e  mov     ebp, r8d
0x180153771  lea     rcx, [rax-18h]; this
0x180153775  call    ??0GpLock@GpRuntime@@QEAA@PEAVGpLockable@1@@Z; GpRuntime::GpLock::GpLock(GpRuntime::GpLockable *)
0x18015377a  xor     ebx, ebx
0x18015377c  cmp     [rsp+38h+var_18], ebx
0x180153780  jz      short loc_18015378C
0x180153782  mov     ebx, 800700AAh
0x180153787  jmp     loc_180153847
0x18015378c  mov     dword ptr [rdi+8], 2
0x180153793  lea     rdx, [rdi+14h]; lpFileSizeHigh
0x180153797  mov     eax, [rsi+28h]
0x18015379a  xorps   xmm0, xmm0
0x18015379d  mov     [rdi+30h], eax
0x1801537a0  mov     [rdi+48h], rbx
0x1801537a4  movups  xmmword ptr [rdi+38h], xmm0
0x1801537a8  mov     [rdi+34h], ebx
0x1801537ab  mov     rcx, [rsi+18h]; hFile
0x1801537af  call    cs:__imp_GetFileSize
0x1801537b6  nop     dword ptr [rax+rax+00h]
0x1801537bb  mov     [rdi+10h], eax
0x1801537be  cmp     eax, 0FFFFFFFFh
0x1801537c1  jnz     short loc_1801537DC
0x1801537c3  call    cs:__imp_GetLastError
0x1801537ca  nop     dword ptr [rax+rax+00h]
0x1801537cf  test    eax, eax
0x1801537d1  jz      short loc_1801537DC
0x1801537d3  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x1801537d8  mov     ebx, eax
0x1801537da  jmp     short loc_180153847
0x1801537dc  mov     rcx, [rsi+18h]; hFile
0x1801537e0  lea     r9, [rdi+18h]; lpLastWriteTime
0x1801537e4  lea     r8, [rdi+28h]; lpLastAccessTime
0x1801537e8  lea     rdx, [rdi+20h]; lpCreationTime
0x1801537ec  call    cs:__imp_GetFileTime
0x1801537f3  nop     dword ptr [rax+rax+00h]
0x1801537f8  test    eax, eax
0x1801537fa  jz      short loc_1801537D3
0x1801537fc  test    bpl, 1
0x180153800  jz      short loc_180153807
0x180153802  mov     [rdi], rbx
0x180153805  jmp     short loc_180153847
0x180153807  mov     rcx, [rsi+20h]; this
0x18015380b  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x180153810  lea     eax, ds:2[rax*2]
0x180153817  movsxd  rbp, eax
0x18015381a  mov     rcx, rbp; cb
0x18015381d  call    cs:__imp_CoTaskMemAlloc
0x180153824  nop     dword ptr [rax+rax+00h]
0x180153829  mov     [rdi], rax
0x18015382c  test    rax, rax
0x18015382f  jnz     short loc_180153838
0x180153831  mov     ebx, 8007000Eh
0x180153836  jmp     short loc_180153847
0x180153838  mov     rdx, [rsi+20h]; Src
0x18015383c  mov     r8, rbp; Size
0x18015383f  mov     rcx, rax; void *
0x180153842  call    memcpy_0
0x180153847  mov     rax, [rsp+38h+var_10]
0x18015384c  mov     rbp, [rsp+38h+arg_8]
0x180153851  mov     rsi, [rsp+38h+arg_10]
0x180153856  lock dec dword ptr [rax]
0x180153859  mov     eax, ebx
0x18015385b  mov     rbx, [rsp+38h+arg_0]
0x180153860  add     rsp, 30h
0x180153864  pop     rdi
0x180153865  retn
```
