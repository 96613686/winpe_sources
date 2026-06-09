# StorageReader::GetDataFromParent(void)

- ea: `0x140022250`
- end: `0x1400223d8`
- name: `?GetDataFromParent@StorageReader@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(StorageReader *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1400234f0`
- `0x140024064`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140011728`
- `0x140022250`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14004650c`
- `0x140063010`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x140022358`
- `KERNEL32!SetFilePointerEx` at `0x140022358`

## string_xrefs

- `0x140022388`: `SetFilePointerEx failed`
- `0x14002230f`: `StorageReader::GetDataFromParent(): Both m_pIFileItemRead and m_pBuffer are NULL.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StorageReader::GetDataFromParent(StorageReader *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  int v4; // eax
  int v5; // edx
  const char *v6; // r8
  unsigned int v7; // r9d
  __int64 v8; // rax
  const struct SplException::TSystemException *v9; // r8
  const struct _GUID *v10; // r9
  void *v11; // rax
  NCoreLibrary *v12; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // eax
  const struct SplException::TSystemException *v14; // r8
  const struct _GUID *v15; // r9
  unsigned int v16; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v17; // [rsp+28h] [rbp-D8h]
  HINSTANCE v18; // [rsp+30h] [rbp-D0h]
  _BYTE v19[160]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-20h] BYREF

  if ( !*(_QWORD *)this && !*((_QWORD *)this + 2) )
  {
    v2 = *((_QWORD *)this + 1);
    v3 = *(_QWORD *)(v2 + 96);
    if ( v3 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, StorageReader *))(*(_QWORD *)v3 + 32LL))(v3, this);
      if ( v4 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v4, v5, v6, v7);
      *((_QWORD *)this + 2) = 0;
      *((_DWORD *)this + 6) = 0;
      v8 = 0;
    }
    else
    {
      *((_DWORD *)this + 6) = *(_DWORD *)(v2 + 104);
      v8 = *(_QWORD *)(v2 + 200);
      *((_QWORD *)this + 2) = v8;
    }
    if ( *(_QWORD *)this )
    {
      v11 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 24LL))(*(_QWORD *)this);
      if ( !SetFilePointerEx(v11, 0, 0, 0) )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v19, "-", 0);
        LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v12);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v19,
          LastErrorAsFailHRNoBreak,
          v14,
          v15,
          v16,
          v17,
          v18);
        SplException::TSystemException::Message((SplException::TSystemException *)v19, "SetFilePointerEx failed");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)pExceptionObject,
          (const struct SplException::THResultException *)v19);
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    else if ( !v8 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v19, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v19,
        0x80004005,
        v9,
        v10,
        v16,
        v17,
        v18);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v19,
        "StorageReader::GetDataFromParent(): Both m_pIFileItemRead and m_pBuffer are NULL.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v19);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x140022250  mov     [rsp-8+arg_8], rbx
0x140022255  push    rbp
0x140022256  lea     rbp, [rsp-90h]
0x14002225e  sub     rsp, 190h
0x140022265  mov     rax, cs:__security_cookie
0x14002226c  xor     rax, rsp
0x14002226f  mov     [rbp+90h+var_10], rax
0x140022276  mov     rbx, rcx
0x140022279  cmp     qword ptr [rcx], 0
0x14002227d  jnz     loc_1400223B8
0x140022283  cmp     qword ptr [rcx+10h], 0
0x140022288  jnz     loc_1400223B8
0x14002228e  mov     rdx, [rcx+8]
0x140022292  mov     rcx, [rdx+60h]
0x140022296  test    rcx, rcx
0x140022299  jz      short loc_1400222C9
0x14002229b  mov     rax, [rcx]
0x14002229e  mov     rdx, rbx
0x1400222a1  mov     rax, [rax+20h]
0x1400222a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400222aa  test    eax, eax
0x1400222ac  jns     short loc_1400222B6
0x1400222ae  mov     ecx, eax; this
0x1400222b0  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400222b6  mov     qword ptr [rbx+10h], 0
0x1400222be  mov     dword ptr [rbx+18h], 0
0x1400222c5  xor     eax, eax
0x1400222c7  jmp     short loc_1400222DA
0x1400222c9  mov     eax, [rdx+68h]
0x1400222cc  mov     [rbx+18h], eax
0x1400222cf  mov     rax, [rdx+0C8h]
0x1400222d6  mov     [rbx+10h], rax
0x1400222da  mov     rcx, [rbx]
0x1400222dd  test    rcx, rcx
0x1400222e0  jnz     short loc_14002233F
0x1400222e2  test    rax, rax
0x1400222e5  jnz     loc_1400223B8
0x1400222eb  xor     r8d, r8d; unsigned int
0x1400222ee  lea     rdx, asc_1400696D8; "-"
0x1400222f5  lea     rcx, [rsp+190h+var_150]; this
0x1400222fa  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400222ff  nop
0x140022300  mov     edx, 80004005h; unsigned int
0x140022305  lea     rcx, [rsp+190h+var_150]; this
0x14002230a  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14002230f  lea     rdx, aStoragereaderG; "StorageReader::GetDataFromParent(): Bot"...
0x140022316  lea     rcx, [rsp+190h+var_150]; this
0x14002231b  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140022320  lea     rdx, [rsp+190h+var_150]; struct SplException::THResultException *
0x140022325  lea     rcx, [rbp+90h+pExceptionObject]; this
0x140022329  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14002232e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140022335  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x140022339  call    _CxxThrowException_0
0x14002233f  xor     ebx, ebx
0x140022341  mov     rax, [rcx]
0x140022344  mov     rax, [rax+18h]
0x140022348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002234d  xor     r9d, r9d; dwMoveMethod
0x140022350  xor     r8d, r8d; lpNewFilePointer
0x140022353  mov     edx, ebx; liDistanceToMove
0x140022355  mov     rcx, rax; hFile
0x140022358  call    cs:__imp_SetFilePointerEx
0x14002235e  test    eax, eax
0x140022360  jnz     short loc_1400223B8
0x140022362  xor     r8d, r8d; unsigned int
0x140022365  lea     rdx, asc_1400696D8; "-"
0x14002236c  lea     rcx, [rsp+190h+var_150]; this
0x140022371  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140022376  nop
0x140022377  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14002237c  mov     edx, eax; unsigned int
0x14002237e  lea     rcx, [rsp+190h+var_150]; this
0x140022383  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140022388  lea     rdx, aSetfilepointer_0; "SetFilePointerEx failed"
0x14002238f  lea     rcx, [rsp+190h+var_150]; this
0x140022394  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140022399  lea     rdx, [rsp+190h+var_150]; struct SplException::THResultException *
0x14002239e  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1400223a2  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400223a7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400223ae  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1400223b2  call    _CxxThrowException_0
0x1400223b8  mov     rcx, [rbp+90h+var_10]
0x1400223bf  xor     rcx, rsp; StackCookie
0x1400223c2  call    __security_check_cookie
0x1400223c7  mov     rbx, [rsp+190h+arg_8]
0x1400223cf  add     rsp, 190h
0x1400223d6  pop     rbp
0x1400223d7  retn
```
