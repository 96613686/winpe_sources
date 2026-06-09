# UnlockedSpillBufferReader::ReadBytesX(void *,ulong,ulong *,int *)

- ea: `0x140023260`
- end: `0x1400234e8`
- name: `?ReadBytesX@UnlockedSpillBufferReader@@UEAAXPEAXKPEAKPEAH@Z`
- size: `648`
- prototype: `void(UnlockedSpillBufferReader *__hidden this, void *, unsigned int, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140011728`
- `0x140023260`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140063010`

## import_xrefs

- `KERNEL32!ReadFile` at `0x140023465`
- `KERNEL32!ReadFile` at `0x140023465`

## string_xrefs

- `0x140023495`: `ReadFile failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UnlockedSpillBufferReader::ReadBytesX(
        UnlockedSpillBufferReader *this,
        void *a2,
        unsigned int a3,
        unsigned int *a4,
        int *a5)
{
  const struct SplException::TSystemException *v8; // r8
  const struct _GUID *v9; // r9
  const struct SplException::TSystemException *v10; // r8
  const struct _GUID *v11; // r9
  const struct SplException::TSystemException *v12; // r8
  const struct _GUID *v13; // r9
  const struct SplException::TSystemException *v14; // r8
  const struct _GUID *v15; // r9
  unsigned __int64 v16; // rcx
  DWORD v17; // ebx
  void *v18; // rax
  NCoreLibrary *v19; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // eax
  const struct SplException::TSystemException *v21; // r8
  const struct _GUID *v22; // r9
  unsigned int lpOverlapped; // [rsp+20h] [rbp-E0h]
  unsigned int lpOverlappeda; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v25; // [rsp+28h] [rbp-D8h]
  HINSTANCE v26; // [rsp+30h] [rbp-D0h]
  _BYTE v27[160]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-20h] BYREF

  if ( !a2 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v27, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v27,
      0x80070057,
      v8,
      v9,
      lpOverlapped,
      v25,
      v26);
    SplException::TSystemException::Message((SplException::TSystemException *)v27, "pvBuffer cannot be NULL.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v27);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !a3 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v27, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v27,
      0x80070057,
      v10,
      v11,
      lpOverlapped,
      v25,
      v26);
    SplException::TSystemException::Message((SplException::TSystemException *)v27, "cbBytesRequested cannot be 0.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v27);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !a4 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v27, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v27,
      0x80070057,
      v12,
      v13,
      lpOverlapped,
      v25,
      v26);
    SplException::TSystemException::Message((SplException::TSystemException *)v27, "pcbAvailable cannot be NULL");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v27);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !a5 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v27, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v27,
      0x80070057,
      v14,
      v15,
      lpOverlapped,
      v25,
      v26);
    SplException::TSystemException::Message((SplException::TSystemException *)v27, "pbEndOfFile cannot be NULL");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v27);
    throw (SplException::THResultException *)pExceptionObject;
  }
  *a5 = 1;
  *a4 = 0;
  v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 24LL);
  if ( v16 && *((_QWORD *)this + 1) < v16 )
  {
    *a4 = a3;
    if ( *((_QWORD *)this + 1) + (unsigned __int64)a3 <= v16 )
      *a5 = 0;
    else
      *a4 = v16 - *((_DWORD *)this + 2);
    v17 = *a4;
    v18 = (void *)(*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3), a5);
    if ( !ReadFile(v18, a2, v17, a4, 0) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v27, "-", 0);
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v19);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v27,
        LastErrorAsFailHRNoBreak,
        v21,
        v22,
        lpOverlappeda,
        v25,
        v26);
      SplException::TSystemException::Message((SplException::TSystemException *)v27, "ReadFile failed");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v27);
      throw (SplException::THResultException *)pExceptionObject;
    }
    *((_QWORD *)this + 1) += *a4;
  }
}

```

## disassembly

```asm
0x140023260  push    rbp
0x140023262  push    rbx
0x140023263  push    rsi
0x140023264  push    rdi
0x140023265  push    r14
0x140023267  lea     rbp, [rsp-90h]
0x14002326f  sub     rsp, 190h
0x140023276  mov     rax, cs:__security_cookie
0x14002327d  xor     rax, rsp
0x140023280  mov     [rbp+0B0h+var_30], rax
0x140023287  mov     rsi, r9
0x14002328a  mov     r14, rdx
0x14002328d  mov     rdi, rcx
0x140023290  mov     rdx, [rbp+0B0h+arg_20]
0x140023297  test    r14, r14
0x14002329a  jnz     short loc_1400232F0
0x14002329c  xor     r8d, r8d; unsigned int
0x14002329f  lea     rdx, asc_1400696D8; "-"
0x1400232a6  lea     rcx, [rsp+1B0h+var_170]; this
0x1400232ab  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400232b0  nop
0x1400232b1  mov     edx, 80070057h; unsigned int
0x1400232b6  lea     rcx, [rsp+1B0h+var_170]; this
0x1400232bb  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400232c0  lea     rdx, aPvbufferCannot; "pvBuffer cannot be NULL."
0x1400232c7  lea     rcx, [rsp+1B0h+var_170]; this
0x1400232cc  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400232d1  lea     rdx, [rsp+1B0h+var_170]; struct SplException::THResultException *
0x1400232d6  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x1400232da  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400232df  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400232e6  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1400232ea  call    _CxxThrowException_0
0x1400232f0  test    r8d, r8d
0x1400232f3  jnz     short loc_140023346
0x1400232f5  lea     rdx, asc_1400696D8; "-"
0x1400232fc  lea     rcx, [rsp+1B0h+var_170]; this
0x140023301  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140023306  nop
0x140023307  mov     edx, 80070057h; unsigned int
0x14002330c  lea     rcx, [rsp+1B0h+var_170]; this
0x140023311  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140023316  lea     rdx, aCbbytesrequest; "cbBytesRequested cannot be 0."
0x14002331d  lea     rcx, [rsp+1B0h+var_170]; this
0x140023322  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140023327  lea     rdx, [rsp+1B0h+var_170]; struct SplException::THResultException *
0x14002332c  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x140023330  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140023335  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14002333c  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x140023340  call    _CxxThrowException_0
0x140023346  test    rsi, rsi
0x140023349  jnz     short loc_14002339F
0x14002334b  xor     r8d, r8d; unsigned int
0x14002334e  lea     rdx, asc_1400696D8; "-"
0x140023355  lea     rcx, [rsp+1B0h+var_170]; this
0x14002335a  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14002335f  nop
0x140023360  mov     edx, 80070057h; unsigned int
0x140023365  lea     rcx, [rsp+1B0h+var_170]; this
0x14002336a  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14002336f  lea     rdx, aPcbavailableCa; "pcbAvailable cannot be NULL"
0x140023376  lea     rcx, [rsp+1B0h+var_170]; this
0x14002337b  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140023380  lea     rdx, [rsp+1B0h+var_170]; struct SplException::THResultException *
0x140023385  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x140023389  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14002338e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140023395  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x140023399  call    _CxxThrowException_0
0x14002339f  test    rdx, rdx
0x1400233a2  jnz     short loc_1400233F8
0x1400233a4  xor     r8d, r8d; unsigned int
0x1400233a7  lea     rdx, asc_1400696D8; "-"
0x1400233ae  lea     rcx, [rsp+1B0h+var_170]; this
0x1400233b3  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400233b8  nop
0x1400233b9  mov     edx, 80070057h; unsigned int
0x1400233be  lea     rcx, [rsp+1B0h+var_170]; this
0x1400233c3  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400233c8  lea     rdx, aPbendoffileCan; "pbEndOfFile cannot be NULL"
0x1400233cf  lea     rcx, [rsp+1B0h+var_170]; this
0x1400233d4  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400233d9  lea     rdx, [rsp+1B0h+var_170]; struct SplException::THResultException *
0x1400233de  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x1400233e2  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400233e7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400233ee  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1400233f2  call    _CxxThrowException_0
0x1400233f8  mov     dword ptr [rdx], 1
0x1400233fe  mov     dword ptr [r9], 0
0x140023405  mov     rax, [rcx+10h]
0x140023409  mov     rcx, [rax+18h]
0x14002340d  test    rcx, rcx
0x140023410  jz      loc_1400234CB
0x140023416  cmp     [rdi+8], rcx
0x14002341a  jnb     loc_1400234CB
0x140023420  mov     [r9], r8d
0x140023423  mov     eax, r8d
0x140023426  add     rax, [rdi+8]
0x14002342a  cmp     rax, rcx
0x14002342d  jbe     short loc_140023437
0x14002342f  sub     ecx, [rdi+8]
0x140023432  mov     [r9], ecx
0x140023435  jmp     short loc_14002343D
0x140023437  mov     dword ptr [rdx], 0
0x14002343d  mov     ebx, [r9]
0x140023440  mov     rcx, [rdi+18h]
0x140023444  mov     rax, [rcx]
0x140023447  mov     rax, [rax+18h]
0x14002344b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023450  mov     [rsp+1B0h+lpOverlapped], 0; unsigned int
0x140023459  mov     r9, rsi; lpNumberOfBytesRead
0x14002345c  mov     r8d, ebx; nNumberOfBytesToRead
0x14002345f  mov     rdx, r14; lpBuffer
0x140023462  mov     rcx, rax; hFile
0x140023465  call    cs:__imp_ReadFile
0x14002346b  test    eax, eax
0x14002346d  jnz     short loc_1400234C5
0x14002346f  xor     r8d, r8d; unsigned int
0x140023472  lea     rdx, asc_1400696D8; "-"
0x140023479  lea     rcx, [rsp+1B0h+var_170]; this
0x14002347e  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140023483  nop
0x140023484  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140023489  mov     edx, eax; unsigned int
0x14002348b  lea     rcx, [rsp+1B0h+var_170]; this
0x140023490  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140023495  lea     rdx, aReadfileFailed; "ReadFile failed"
0x14002349c  lea     rcx, [rsp+1B0h+var_170]; this
0x1400234a1  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400234a6  lea     rdx, [rsp+1B0h+var_170]; struct SplException::THResultException *
0x1400234ab  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x1400234af  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400234b4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400234bb  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1400234bf  call    _CxxThrowException_0
0x1400234c5  mov     eax, [rsi]
0x1400234c7  add     [rdi+8], rax
0x1400234cb  mov     rcx, [rbp+0B0h+var_30]
0x1400234d2  xor     rcx, rsp; StackCookie
0x1400234d5  call    __security_check_cookie
0x1400234da  add     rsp, 190h
0x1400234e1  pop     r14
0x1400234e3  pop     rdi
0x1400234e4  pop     rsi
0x1400234e5  pop     rbx
0x1400234e6  pop     rbp
0x1400234e7  retn
```
