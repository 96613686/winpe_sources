# UnlockedSpillBufferReader::SeekX(__int64,ulong,unsigned __int64 *)

- ea: `0x140023ce0`
- end: `0x14002405b`
- name: `?SeekX@UnlockedSpillBufferReader@@UEAAX_JKPEA_K@Z`
- size: `891`
- prototype: `void __fastcall(UnlockedSpillBufferReader *__hidden this, __int64, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140011728`
- `0x140023ce0`
- `0x140024624`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140063010`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x140023e45`
- `KERNEL32!SetFilePointerEx` at `0x140023e45`

## string_xrefs

- `0x140023e79`: `SetFilePointerEx failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UnlockedSpillBufferReader::SeekX(LARGE_INTEGER *this, __int64 a2, int a3, LARGE_INTEGER *a4)
{
  const struct SplException::TSystemException *v6; // r8
  const struct _GUID *v7; // r9
  const struct SplException::TSystemException *v8; // r8
  const struct _GUID *v9; // r9
  unsigned __int64 v10; // r8
  LARGE_INTEGER v11; // rbx
  void *v12; // rax
  NCoreLibrary *v13; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // eax
  const struct SplException::TSystemException *v15; // r8
  const struct _GUID *v16; // r9
  bool v17; // sf
  const struct SplException::TSystemException *v18; // r8
  const struct _GUID *v19; // r9
  const struct SplException::TSystemException *v20; // r8
  const struct _GUID *v21; // r9
  const struct SplException::TSystemException *v22; // r8
  const struct _GUID *v23; // r9
  const struct SplException::TSystemException *v24; // r8
  const struct _GUID *v25; // r9
  unsigned int v26; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v27; // [rsp+28h] [rbp-D8h]
  HINSTANCE v28; // [rsp+30h] [rbp-D0h]
  _BYTE v29[160]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-20h] BYREF

  if ( a3 == 2 )
  {
    if ( a2 > 0 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v29, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v29,
        0x80004005,
        v6,
        v7,
        v26,
        v27,
        v28);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v29,
        "Cannot seek past the end of the stream.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v29);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( a2 < 0 && (unsigned __int64)-a2 > *(_QWORD *)(this[2].QuadPart + 24) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v29, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v29,
        0x80004005,
        v8,
        v9,
        v26,
        v27,
        v28);
      SplException::TSystemException::Message((SplException::TSystemException *)v29, "Cannot seek to negative offset.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v29);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v10 = a2 + *(_QWORD *)(this[2].QuadPart + 24);
  }
  else if ( a3 )
  {
    if ( a2 < 0 && (unsigned __int64)-a2 > this[1].QuadPart )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v29, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v29,
        0x80004005,
        v22,
        v23,
        v26,
        v27,
        v28);
      SplException::TSystemException::Message((SplException::TSystemException *)v29, "Cannot seek to negative offset.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v29);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v10 = a2 + this[1].QuadPart;
    if ( v10 > *(_QWORD *)(this[2].QuadPart + 24) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v29, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v29,
        0x80004005,
        v24,
        v25,
        v26,
        v27,
        v28);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v29,
        "Cannot seek past the end of the stream.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v29);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  else
  {
    v17 = a2 < 0;
    if ( a2 > 0 )
    {
      if ( (unsigned __int64)a2 > *(_QWORD *)(this[2].QuadPart + 24) )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v29, "-", 0);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v29,
          0x80004005,
          v18,
          v19,
          v26,
          v27,
          v28);
        SplException::TSystemException::Message(
          (SplException::TSystemException *)v29,
          "Cannot seek past the end of the stream.");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)pExceptionObject,
          (const struct SplException::THResultException *)v29);
        throw (SplException::THResultException *)pExceptionObject;
      }
      v17 = a2 < 0;
    }
    if ( v17 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v29, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v29,
        0x80004005,
        v20,
        v21,
        v26,
        v27,
        v28);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v29,
        "Cannot use STREAM_SEEK_SET with a negative offset.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v29);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v10 = a2;
  }
  this[1].QuadPart = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = v10;
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v10, (unsigned int)a2);
  }
  if ( a4 )
    *a4 = this[1];
  v11 = this[1];
  v12 = (void *)(*(__int64 (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)this[3].QuadPart + 24LL))(this[3]);
  if ( !SetFilePointerEx(v12, v11, 0, 0) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v29, "-", 0);
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v13);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v29,
      LastErrorAsFailHRNoBreak,
      v15,
      v16,
      v26,
      v27,
      v28);
    SplException::TSystemException::Message((SplException::TSystemException *)v29, "SetFilePointerEx failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v29);
    throw (SplException::THResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x140023ce0  push    rbp
0x140023ce2  push    rbx
0x140023ce3  push    rdi
0x140023ce4  lea     rbp, [rsp-90h]
0x140023cec  sub     rsp, 190h
0x140023cf3  mov     rax, cs:__security_cookie
0x140023cfa  xor     rax, rsp
0x140023cfd  mov     [rbp+0A0h+var_20], rax
0x140023d04  mov     rbx, r9
0x140023d07  mov     rdi, rcx
0x140023d0a  cmp     r8d, 2
0x140023d0e  jnz     loc_140023EA9
0x140023d14  test    rdx, rdx
0x140023d17  jle     short loc_140023D6D
0x140023d19  xor     r8d, r8d; unsigned int
0x140023d1c  lea     rdx, asc_1400696D8; "-"
0x140023d23  lea     rcx, [rsp+1A0h+var_160]; this
0x140023d28  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140023d2d  nop
0x140023d2e  mov     edx, 80004005h; unsigned int
0x140023d33  lea     rcx, [rsp+1A0h+var_160]; this
0x140023d38  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140023d3d  lea     rdx, aCannotSeekPast; "Cannot seek past the end of the stream."
0x140023d44  lea     rcx, [rsp+1A0h+var_160]; this
0x140023d49  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140023d4e  lea     rdx, [rsp+1A0h+var_160]; struct SplException::THResultException *
0x140023d53  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x140023d57  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140023d5c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140023d63  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x140023d67  call    _CxxThrowException_0
0x140023d6d  jns     short loc_140023DD3
0x140023d6f  mov     rcx, [rcx+10h]
0x140023d73  mov     rax, rdx
0x140023d76  neg     rax
0x140023d79  cmp     rax, [rcx+18h]
0x140023d7d  jbe     short loc_140023DD3
0x140023d7f  xor     r8d, r8d; unsigned int
0x140023d82  lea     rdx, asc_1400696D8; "-"
0x140023d89  lea     rcx, [rsp+1A0h+var_160]; this
0x140023d8e  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140023d93  nop
0x140023d94  mov     edx, 80004005h; unsigned int
0x140023d99  lea     rcx, [rsp+1A0h+var_160]; this
0x140023d9e  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140023da3  lea     rdx, aCannotSeekToNe; "Cannot seek to negative offset."
0x140023daa  lea     rcx, [rsp+1A0h+var_160]; this
0x140023daf  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140023db4  lea     rdx, [rsp+1A0h+var_160]; struct SplException::THResultException *
0x140023db9  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x140023dbd  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140023dc2  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140023dc9  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x140023dcd  call    _CxxThrowException_0
0x140023dd3  mov     rax, [rdi+10h]
0x140023dd7  mov     r8, [rax+18h]
0x140023ddb  add     r8, rdx
0x140023dde  mov     [rdi+8], r8
0x140023de2  lea     rax, WPP_GLOBAL_Control
0x140023de9  mov     rcx, cs:WPP_GLOBAL_Control
0x140023df0  cmp     rcx, rax
0x140023df3  jz      short loc_140023E19
0x140023df5  test    byte ptr [rcx+1Ch], 8
0x140023df9  jz      short loc_140023E19
0x140023dfb  cmp     byte ptr [rcx+19h], 2
0x140023dff  jb      short loc_140023E19
0x140023e01  mov     r9d, edx
0x140023e04  mov     edx, 39h ; '9'
0x140023e09  mov     eax, r8d
0x140023e0c  mov     [rsp+1A0h+var_180], eax; unsigned int
0x140023e10  mov     rcx, [rcx+10h]
0x140023e14  call    WPP_SF_dD
0x140023e19  test    rbx, rbx
0x140023e1c  jz      short loc_140023E25
0x140023e1e  mov     rax, [rdi+8]
0x140023e22  mov     [rbx], rax
0x140023e25  mov     rbx, [rdi+8]
0x140023e29  mov     rcx, [rdi+18h]
0x140023e2d  mov     rax, [rcx]
0x140023e30  mov     rax, [rax+18h]
0x140023e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023e39  xor     r9d, r9d; dwMoveMethod
0x140023e3c  xor     r8d, r8d; lpNewFilePointer
0x140023e3f  mov     rdx, rbx; liDistanceToMove
0x140023e42  mov     rcx, rax; hFile
0x140023e45  call    cs:__imp_SetFilePointerEx
0x140023e4b  test    eax, eax
0x140023e4d  jnz     loc_140024041
0x140023e53  xor     r8d, r8d; unsigned int
0x140023e56  lea     rdx, asc_1400696D8; "-"
0x140023e5d  lea     rcx, [rsp+1A0h+var_160]; this
0x140023e62  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140023e67  nop
0x140023e68  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140023e6d  mov     edx, eax; unsigned int
0x140023e6f  lea     rcx, [rsp+1A0h+var_160]; this
0x140023e74  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140023e79  lea     rdx, aSetfilepointer_0; "SetFilePointerEx failed"
0x140023e80  lea     rcx, [rsp+1A0h+var_160]; this
0x140023e85  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140023e8a  lea     rdx, [rsp+1A0h+var_160]; struct SplException::THResultException *
0x140023e8f  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x140023e93  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140023e98  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140023e9f  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x140023ea3  call    _CxxThrowException_0
0x140023ea9  test    r8d, r8d
0x140023eac  jnz     loc_140023F73
0x140023eb2  test    rdx, rdx
0x140023eb5  jle     short loc_140023F15
0x140023eb7  mov     rax, [rcx+10h]
0x140023ebb  cmp     rdx, [rax+18h]
0x140023ebf  jbe     short loc_140023F12
0x140023ec1  lea     rdx, asc_1400696D8; "-"
0x140023ec8  lea     rcx, [rsp+1A0h+var_160]; this
0x140023ecd  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140023ed2  nop
0x140023ed3  mov     edx, 80004005h; unsigned int
0x140023ed8  lea     rcx, [rsp+1A0h+var_160]; this
0x140023edd  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140023ee2  lea     rdx, aCannotSeekPast; "Cannot seek past the end of the stream."
0x140023ee9  lea     rcx, [rsp+1A0h+var_160]; this
0x140023eee  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140023ef3  lea     rdx, [rsp+1A0h+var_160]; struct SplException::THResultException *
0x140023ef8  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x140023efc  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140023f01  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140023f08  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x140023f0c  call    _CxxThrowException_0
0x140023f12  test    rdx, rdx
0x140023f15  jns     short loc_140023F6B
0x140023f17  xor     r8d, r8d; unsigned int
0x140023f1a  lea     rdx, asc_1400696D8; "-"
0x140023f21  lea     rcx, [rsp+1A0h+var_160]; this
0x140023f26  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140023f2b  nop
0x140023f2c  mov     edx, 80004005h; unsigned int
0x140023f31  lea     rcx, [rsp+1A0h+var_160]; this
0x140023f36  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140023f3b  lea     rdx, aCannotUseStrea; "Cannot use STREAM_SEEK_SET with a negat"...
0x140023f42  lea     rcx, [rsp+1A0h+var_160]; this
0x140023f47  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140023f4c  lea     rdx, [rsp+1A0h+var_160]; struct SplException::THResultException *
0x140023f51  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x140023f55  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140023f5a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140023f61  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x140023f65  call    _CxxThrowException_0
0x140023f6b  mov     r8, rdx
0x140023f6e  jmp     loc_140023DDE
0x140023f73  test    rdx, rdx
0x140023f76  jns     short loc_140023FD8
0x140023f78  mov     rax, rdx
0x140023f7b  neg     rax
0x140023f7e  cmp     rax, [rcx+8]
0x140023f82  jbe     short loc_140023FD8
0x140023f84  xor     r8d, r8d; unsigned int
0x140023f87  lea     rdx, asc_1400696D8; "-"
0x140023f8e  lea     rcx, [rsp+1A0h+var_160]; this
0x140023f93  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140023f98  nop
0x140023f99  mov     edx, 80004005h; unsigned int
0x140023f9e  lea     rcx, [rsp+1A0h+var_160]; this
0x140023fa3  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140023fa8  lea     rdx, aCannotSeekToNe; "Cannot seek to negative offset."
0x140023faf  lea     rcx, [rsp+1A0h+var_160]; this
0x140023fb4  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140023fb9  lea     rdx, [rsp+1A0h+var_160]; struct SplException::THResultException *
0x140023fbe  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x140023fc2  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140023fc7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140023fce  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x140023fd2  call    _CxxThrowException_0
0x140023fd8  mov     r8, [rcx+8]
0x140023fdc  add     r8, rdx
0x140023fdf  mov     rax, [rcx+10h]
0x140023fe3  cmp     r8, [rax+18h]
0x140023fe7  jbe     loc_140023DDE
0x140023fed  xor     r8d, r8d; unsigned int
0x140023ff0  lea     rdx, asc_1400696D8; "-"
0x140023ff7  lea     rcx, [rsp+1A0h+var_160]; this
0x140023ffc  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140024001  nop
0x140024002  mov     edx, 80004005h; unsigned int
0x140024007  lea     rcx, [rsp+1A0h+var_160]; this
0x14002400c  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140024011  lea     rdx, aCannotSeekPast; "Cannot seek past the end of the stream."
0x140024018  lea     rcx, [rsp+1A0h+var_160]; this
0x14002401d  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140024022  lea     rdx, [rsp+1A0h+var_160]; struct SplException::THResultException *
0x140024027  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x14002402b  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140024030  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140024037  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x14002403b  call    _CxxThrowException_0
0x140024041  mov     rcx, [rbp+0A0h+var_20]
0x140024048  xor     rcx, rsp; StackCookie
0x14002404b  call    __security_check_cookie
0x140024050  add     rsp, 190h
0x140024057  pop     rdi
0x140024058  pop     rbx
0x140024059  pop     rbp
0x14002405a  retn
```
