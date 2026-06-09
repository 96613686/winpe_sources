# HyperVFileIo::WriteAsync(unsigned __int64,void const *,ulong)

- ea: `0x1800819c0`
- end: `0x180081b09`
- name: `?WriteAsync@HyperVFileIo@@UEAAPEAUIHyperVAsyncIo@@_KPEBXK@Z`
- size: `329`
- prototype: `struct IHyperVAsyncIo *__fastcall(HyperVFileIo *__hidden this, unsigned __int64, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800818c0`

## callees

- `0x1800067c0`
- `0x18001587c`
- `0x18001597c`
- `0x18007dfac`
- `0x18007e39c`
- `0x18007eb10`
- `0x180080794`
- `0x1800819c0`
- `0x18008226c`
- `0x1800910b0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081a46`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180081a3c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180081a3c`

## string_xrefs

- `0x180081ad3`: `onecore\vm\common\hypervstorage\hypervfileio.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct _SLIST_ENTRY *__fastcall HyperVFileIo::WriteAsync(
        HyperVFileIo *this,
        unsigned __int64 a2,
        const void *a3,
        DWORD a4)
{
  struct _SLIST_ENTRY *AsyncIo; // rsi
  struct _OVERLAPPED *started; // rax
  DWORD LastError; // ebx
  const struct _GUID *v11; // rax
  const unsigned __int16 *v12; // rdx
  struct HyperVAsyncIo *v14; // rax
  int lpOverlapped; // [rsp+20h] [rbp-88h]
  _BYTE v16[16]; // [rsp+40h] [rbp-68h] BYREF
  struct _GUID v17; // [rsp+50h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  HyperVFileIo::EnsureFileIsConnected(this);
  if ( (*((_BYTE *)this + 144) & 0x20) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5FC,
      (unsigned int)"onecore\\vm\\common\\hypervstorage\\hypervfileio.cpp",
      (const char *)0x800710DDLL,
      lpOverlapped);
  AsyncIo = HyperVFileIo::AllocateAsyncIo((union _SLIST_HEADER *)this);
  *(_QWORD *)&v17.Data1 = AsyncIo;
  started = (struct _OVERLAPPED *)HyperVAsyncIo::StartIo(AsyncIo, 5, a2, a3, a4);
  if ( !WriteFile(*((HANDLE *)this + 9), a3, a4, 0, started) )
  {
    LastError = GetLastError();
    if ( LastError == 38 )
    {
      *((_BYTE *)&AsyncIo[4].Next + 8) = 1;
    }
    else if ( LastError == 997 )
    {
      goto LABEL_5;
    }
    v14 = (struct HyperVAsyncIo *)std::unique_ptr<HyperVAsyncIo,HyperVAsyncIoDeleter>::get(&v17);
    HyperVFileIo::OnSynchronousIoFailure(this, v14, LastError);
    HvsThrowWin32Error(LastError);
  }
LABEL_5:
  v11 = (const struct _GUID *)((__int64 (__fastcall *)(struct _SLIST_ENTRY *, _BYTE *))AsyncIo->Next[4].Next)(
                                AsyncIo,
                                v16);
  v12 = (const unsigned __int16 *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) > 7u )
    v12 = *(const unsigned __int16 **)v12;
  v17 = *(struct _GUID *)((char *)this + 8);
  HyperVStorageTrace::HyperVFileIo_AsyncWriteFile(&v17, v12, *((void **)this + 9), a2, a3, a4, v11);
  return AsyncIo;
}

```

## disassembly

```asm
0x1800819c0  push    rbx
0x1800819c2  push    rbp
0x1800819c3  push    rsi
0x1800819c4  push    rdi
0x1800819c5  push    r14
0x1800819c7  push    r15
0x1800819c9  sub     rsp, 78h
0x1800819cd  mov     rax, cs:__security_cookie
0x1800819d4  xor     rax, rsp
0x1800819d7  mov     [rsp+0A8h+var_48], rax
0x1800819dc  mov     r14d, r9d
0x1800819df  mov     rbp, r8
0x1800819e2  mov     r15, rdx
0x1800819e5  mov     rdi, rcx
0x1800819e8  call    ?EnsureFileIsConnected@HyperVFileIo@@AEAAXXZ; HyperVFileIo::EnsureFileIsConnected(void)
0x1800819ed  mov     rcx, [rsp+0A8h]; this
0x1800819f5  test    byte ptr [rdi+90h], 20h
0x1800819fc  jnz     loc_180081ACD
0x180081a02  mov     rcx, rdi; this
0x180081a05  call    ?AllocateAsyncIo@HyperVFileIo@@AEAAPEAVHyperVAsyncIo@@XZ; HyperVFileIo::AllocateAsyncIo(void)
0x180081a0a  mov     rsi, rax
0x180081a0d  mov     qword ptr [rsp+0A8h+var_58.Data1], rax
0x180081a12  mov     dword ptr [rsp+0A8h+lpOverlapped], r14d
0x180081a17  mov     r9, rbp
0x180081a1a  mov     r8, r15
0x180081a1d  mov     edx, 5
0x180081a22  mov     rcx, rax
0x180081a25  call    ?StartIo@HyperVAsyncIo@@IEAAPEAU_OVERLAPPED@@W4HyperVAsyncIoOperationType@@_KPEAXK@Z; HyperVAsyncIo::StartIo(HyperVAsyncIoOperationType,unsigned __int64,void *,ulong)
0x180081a2a  mov     [rsp+0A8h+lpOverlapped], rax; lpOverlapped
0x180081a2f  xor     r9d, r9d; lpNumberOfBytesWritten
0x180081a32  mov     r8d, r14d; nNumberOfBytesToWrite
0x180081a35  mov     rdx, rbp; lpBuffer
0x180081a38  mov     rcx, [rdi+48h]; hFile
0x180081a3c  call    cs:__imp_WriteFile
0x180081a42  test    eax, eax
0x180081a44  jnz     short loc_180081A63
0x180081a46  call    cs:__imp_GetLastError
0x180081a4c  mov     ebx, eax
0x180081a4e  cmp     eax, 26h ; '&'
0x180081a51  jz      loc_180081AE5
0x180081a57  cmp     ebx, 3E5h
0x180081a5d  jnz     loc_180081AE9
0x180081a63  mov     rax, [rsi]
0x180081a66  lea     rdx, [rsp+0A8h+var_68]
0x180081a6b  mov     rcx, rsi
0x180081a6e  mov     rax, [rax+40h]
0x180081a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a77  lea     rdx, [rdi+28h]
0x180081a7b  cmp     qword ptr [rdx+18h], 7
0x180081a80  jbe     short loc_180081A85
0x180081a82  mov     rdx, [rdx]; unsigned __int16 *
0x180081a85  movups  xmm0, xmmword ptr [rdi+8]
0x180081a89  movdqu  xmmword ptr [rsp+0A8h+var_58.Data1], xmm0
0x180081a8f  mov     [rsp+0A8h+var_78], rax; struct _GUID *
0x180081a94  mov     [rsp+0A8h+var_80], r14d; unsigned int
0x180081a99  mov     [rsp+0A8h+lpOverlapped], rbp; void *
0x180081a9e  mov     r9, r15; unsigned __int64
0x180081aa1  mov     r8, [rdi+48h]; void *
0x180081aa5  lea     rcx, [rsp+0A8h+var_58]; struct _GUID *
0x180081aaa  call    ?HyperVFileIo_AsyncWriteFile@HyperVStorageTrace@@SAXU_GUID@@PEBGPEAX_KPEBXKAEBU2@@Z; HyperVStorageTrace::HyperVFileIo_AsyncWriteFile(_GUID,ushort const *,void *,unsigned __int64,void const *,ulong,_GUID const &)
0x180081aaf  nop
0x180081ab0  mov     rax, rsi
0x180081ab3  mov     rcx, [rsp+0A8h+var_48]
0x180081ab8  xor     rcx, rsp; StackCookie
0x180081abb  call    __security_check_cookie
0x180081ac0  add     rsp, 78h
0x180081ac4  pop     r15
0x180081ac6  pop     r14
0x180081ac8  pop     rdi
0x180081ac9  pop     rsi
0x180081aca  pop     rbp
0x180081acb  pop     rbx
0x180081acc  retn
0x180081acd  mov     r9d, 800710DDh; char *
0x180081ad3  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\hypervstorage\\hyp"...
0x180081ada  mov     edx, 5FCh; void *
0x180081adf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081ae5  mov     byte ptr [rsi+48h], 1
0x180081ae9  lea     rcx, [rsp+0A8h+var_58]
0x180081aee  call    ?get@?$unique_ptr@VHyperVAsyncIo@@VHyperVAsyncIoDeleter@@@std@@QEBAPEAVHyperVAsyncIo@@XZ; std::unique_ptr<HyperVAsyncIo,HyperVAsyncIoDeleter>::get(void)
0x180081af3  mov     rdx, rax; struct HyperVAsyncIo *
0x180081af6  mov     r8d, ebx; unsigned int
0x180081af9  mov     rcx, rdi; this
0x180081afc  call    ?OnSynchronousIoFailure@HyperVFileIo@@AEAAXPEAVHyperVAsyncIo@@K@Z; HyperVFileIo::OnSynchronousIoFailure(HyperVAsyncIo *,ulong)
0x180081b01  mov     ecx, ebx; unsigned int
0x180081b03  call    ?HvsThrowWin32Error@@YAXK@Z; HvsThrowWin32Error(ulong)
```
