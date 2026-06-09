# UnlockedSpillBuffer::InternalWriteBytesX(void const *,ulong,ulong *)

- ea: `0x1400226ec`
- end: `0x1400227e1`
- name: `?InternalWriteBytesX@UnlockedSpillBuffer@@QEAAXPEBXKPEAK@Z`
- size: `245`
- prototype: `void(UnlockedSpillBuffer *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140021b38`
- `0x140022038`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140011728`
- `0x1400226ec`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140063010`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14002274e`
- `KERNEL32!WriteFile` at `0x14002274e`

## string_xrefs

- `0x14002277e`: `WriteFile failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UnlockedSpillBuffer::InternalWriteBytesX(
        UnlockedSpillBuffer *this,
        const void *a2,
        DWORD a3,
        unsigned int *a4)
{
  void *v8; // rax
  NCoreLibrary *v9; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // eax
  const struct SplException::TSystemException *v11; // r8
  const struct _GUID *v12; // r9
  DWORD v13; // ecx
  unsigned int lpOverlapped; // [rsp+20h] [rbp-1A8h]
  const struct win_musl::TStringEllipseBase *v15; // [rsp+28h] [rbp-1A0h]
  HINSTANCE v16; // [rsp+30h] [rbp-198h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-188h] BYREF
  _BYTE v18[160]; // [rsp+50h] [rbp-178h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-D8h] BYREF

  if ( a3 )
  {
    NumberOfBytesWritten = a3;
    v8 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5));
    if ( !WriteFile(v8, a2, a3, &NumberOfBytesWritten, 0) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v18, "-", 0);
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v9);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v18,
        LastErrorAsFailHRNoBreak,
        v11,
        v12,
        lpOverlapped,
        v15,
        v16);
      SplException::TSystemException::Message((SplException::TSystemException *)v18, "WriteFile failed");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v18);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v13 = NumberOfBytesWritten;
    *((_QWORD *)this + 3) += NumberOfBytesWritten;
    if ( a4 )
      *a4 = v13;
  }
  else
  {
    *a4 = 0;
  }
}

```

## disassembly

```asm
0x1400226ec  push    rbx
0x1400226ee  push    rbp
0x1400226ef  push    rsi
0x1400226f0  push    rdi
0x1400226f1  sub     rsp, 1A8h
0x1400226f8  mov     rax, cs:__security_cookie
0x1400226ff  xor     rax, rsp
0x140022702  mov     [rsp+1C8h+var_38], rax
0x14002270a  mov     rbx, r9
0x14002270d  mov     esi, r8d
0x140022710  mov     rbp, rdx
0x140022713  mov     rdi, rcx
0x140022716  test    r8d, r8d
0x140022719  jnz     short loc_140022723
0x14002271b  mov     [r9], r8d
0x14002271e  jmp     loc_1400227C5
0x140022723  mov     [rsp+1C8h+NumberOfBytesWritten], esi
0x140022727  mov     rcx, [rcx+28h]
0x14002272b  mov     rax, [rcx]
0x14002272e  mov     rax, [rax+18h]
0x140022732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022737  mov     rcx, rax; hFile
0x14002273a  mov     [rsp+1C8h+lpOverlapped], 0; unsigned int
0x140022743  lea     r9, [rsp+1C8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140022748  mov     r8d, esi; nNumberOfBytesToWrite
0x14002274b  mov     rdx, rbp; lpBuffer
0x14002274e  call    cs:__imp_WriteFile
0x140022754  test    eax, eax
0x140022756  jnz     short loc_1400227B6
0x140022758  xor     r8d, r8d; unsigned int
0x14002275b  lea     rdx, asc_1400696D8; "-"
0x140022762  lea     rcx, [rsp+1C8h+var_178]; this
0x140022767  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14002276c  nop
0x14002276d  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140022772  mov     edx, eax; unsigned int
0x140022774  lea     rcx, [rsp+1C8h+var_178]; this
0x140022779  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14002277e  lea     rdx, aWritefileFaile; "WriteFile failed"
0x140022785  lea     rcx, [rsp+1C8h+var_178]; this
0x14002278a  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14002278f  lea     rdx, [rsp+1C8h+var_178]; struct SplException::THResultException *
0x140022794  lea     rcx, [rsp+1C8h+pExceptionObject]; this
0x14002279c  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400227a1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400227a8  lea     rcx, [rsp+1C8h+pExceptionObject]; pExceptionObject
0x1400227b0  call    _CxxThrowException_0
0x1400227b6  mov     ecx, [rsp+1C8h+NumberOfBytesWritten]
0x1400227ba  add     [rdi+18h], rcx
0x1400227be  test    rbx, rbx
0x1400227c1  jz      short loc_1400227C5
0x1400227c3  mov     [rbx], ecx
0x1400227c5  mov     rcx, [rsp+1C8h+var_38]
0x1400227cd  xor     rcx, rsp; StackCookie
0x1400227d0  call    __security_check_cookie
0x1400227d5  add     rsp, 1A8h
0x1400227dc  pop     rdi
0x1400227dd  pop     rsi
0x1400227de  pop     rbp
0x1400227df  pop     rbx
0x1400227e0  retn
```
