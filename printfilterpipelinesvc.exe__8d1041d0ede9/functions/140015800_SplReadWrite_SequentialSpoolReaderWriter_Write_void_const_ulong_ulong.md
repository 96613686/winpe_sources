# SplReadWrite::SequentialSpoolReaderWriter::Write(void const *,ulong,ulong *)

- ea: `0x140015800`
- end: `0x1400158aa`
- name: `?Write@SequentialSpoolReaderWriter@SplReadWrite@@UEAAJPEBXKPEAK@Z`
- size: `170`
- prototype: `int(SplReadWrite::SequentialSpoolReaderWriter *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140011728`
- `0x140015800`
- `0x140016740`
- `0x140016934`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x14001588d`
- `KERNEL32!ReleaseSemaphore` at `0x14001588d`
- `KERNEL32!WaitForSingleObject` at `0x140015832`
- `KERNEL32!WaitForSingleObject` at `0x140015832`
- `WINSPOOL!WritePrinter` at `0x140015854`
- `WINSPOOL!WritePrinter` at `0x140015854`

## pseudocode

```c
__int64 __fastcall SplReadWrite::SequentialSpoolReaderWriter::Write(
        SplReadWrite::SequentialSpoolReaderWriter *this,
        void *a2,
        DWORD a3,
        unsigned int *a4)
{
  NCoreLibrary *v9; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // ebx
  NCoreLibrary *v11; // rcx
  SplException *v12; // rbx
  struct SplException::TSystemException *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-68h] BYREF
  SplException::TSystemException *v15; // [rsp+20h] [rbp-48h] BYREF
  HANDLE *v16; // [rsp+28h] [rbp-40h]
  std::bad_alloc *v17; // [rsp+30h] [rbp-38h] BYREF
  std::exception *v18; // [rsp+38h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_DWORD *)this + 10) )
    return 2147500033LL;
  v16 = (HANDLE *)((char *)this + 48);
  WaitForSingleObject(*((HANDLE *)this + 6), 0xFFFFFFFF);
  try
  {
    PrnExcept::ImpersonateTokenThroughScope::ImpersonateTokenThroughScope(&TokenHandle, *((HANDLE *)this + 7));
    if ( WritePrinter(*((HANDLE *)this + 4), a2, a3, a4) )
      LastErrorAsFailHRNoBreak = 0;
    else
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v9);
    PrnExcept::ImpersonateTokenThroughScope::~ImpersonateTokenThroughScope(&TokenHandle);
  }
  catch ( SplException::TSystemException *v15 )
  {
    v13 = (struct SplException::TSystemException *)&v14;
    v12 = v15;
    if ( SplException::gpfnExceptionLogger )
      SplException::gpfnExceptionLogger(v15);
    LODWORD(TokenHandle) = SplException::SetErrorInfoFromException(v12, v13);
    LastErrorAsFailHRNoBreak = (unsigned int)TokenHandle;
  }
  catch ( std::bad_alloc *v17 )
  {
    LODWORD(TokenHandle) = -2147024882;
    SetErrorInfo(0, 0);
    LastErrorAsFailHRNoBreak = (unsigned int)TokenHandle;
  }
  catch ( std::exception *v18 )
  {
    LODWORD(TokenHandle) = -2147418113;
    SetErrorInfo(0, 0);
    LastErrorAsFailHRNoBreak = (unsigned int)TokenHandle;
  }
  if ( !ReleaseSemaphore(*v16, 1, 0) )
    return (unsigned int)NCoreLibrary::GetLastErrorAsFailHRNoBreak(v11);
  return LastErrorAsFailHRNoBreak;
}

```

## disassembly

```asm
0x140015800  push    rbx
0x140015802  push    rsi
0x140015803  push    rdi
0x140015804  push    r14
0x140015806  sub     rsp, 48h
0x14001580a  mov     rdi, r9
0x14001580d  mov     esi, r8d
0x140015810  mov     r14, rdx
0x140015813  mov     rbx, rcx
0x140015816  cmp     dword ptr [rcx+28h], 0
0x14001581a  jnz     short loc_140015823
0x14001581c  mov     eax, 80004001h
0x140015821  jmp     short loc_1400158A0
0x140015823  add     rcx, 30h ; '0'
0x140015827  mov     [rsp+68h+var_40], rcx
0x14001582c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001582f  mov     rcx, [rcx]; hHandle
0x140015832  call    cs:__imp_WaitForSingleObject
0x140015838  nop
0x140015839  mov     rdx, [rbx+38h]; Token
0x14001583d  lea     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x140015842  call    ??0ImpersonateTokenThroughScope@PrnExcept@@QEAA@PEAX@Z; PrnExcept::ImpersonateTokenThroughScope::ImpersonateTokenThroughScope(void *)
0x140015847  mov     r9, rdi; pcWritten
0x14001584a  mov     r8d, esi; cbBuf
0x14001584d  mov     rdx, r14; pBuf
0x140015850  mov     rcx, [rbx+20h]; hPrinter
0x140015854  call    cs:__imp_WritePrinter
0x14001585a  test    eax, eax
0x14001585c  jz      short loc_140015862
0x14001585e  xor     ebx, ebx
0x140015860  jmp     short loc_140015869
0x140015862  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140015867  mov     ebx, eax
0x140015869  lea     rcx, [rsp+68h+TokenHandle]; this
0x14001586e  call    ??1ImpersonateTokenThroughScope@PrnExcept@@QEAA@XZ; PrnExcept::ImpersonateTokenThroughScope::~ImpersonateTokenThroughScope(void)
0x140015873  nop
0x140015874  jmp     short loc_14001587E
0x140015876  jmp     short loc_14001587A
0x140015878  jmp     short $+2
0x14001587a  mov     ebx, dword ptr [rsp+68h+TokenHandle]
0x14001587e  xor     r8d, r8d; lpPreviousCount
0x140015881  lea     edx, [r8+1]; lReleaseCount
0x140015885  mov     rcx, [rsp+68h+var_40]
0x14001588a  mov     rcx, [rcx]; hSemaphore
0x14001588d  call    cs:__imp_ReleaseSemaphore
0x140015893  test    eax, eax
0x140015895  jnz     short loc_14001589E
0x140015897  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14001589c  mov     ebx, eax
0x14001589e  mov     eax, ebx
0x1400158a0  add     rsp, 48h
0x1400158a4  pop     r14
0x1400158a6  pop     rdi
0x1400158a7  pop     rsi
0x1400158a8  pop     rbx
0x1400158a9  retn
```
