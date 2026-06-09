# StorageReader::ReadData(void *,ulong,ulong *)

- ea: `0x1400234f0`
- end: `0x14002360b`
- name: `?ReadData@StorageReader@@QEAAXPEAXKPEAK@Z`
- size: `283`
- prototype: `void(StorageReader *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x140022dd0`

## callees

- `0x140002070`
- `0x140002c74`
- `0x14000428d`
- `0x140004484`
- `0x140011728`
- `0x140022250`
- `0x1400234f0`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140063010`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1400235a3`
- `KERNEL32!ReadFile` at `0x1400235a3`

## string_xrefs

- `0x1400235d3`: `ReadFile failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StorageReader::ReadData(StorageReader *this, void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned __int64 v5; // rbx
  void *v8; // rax
  NCoreLibrary *v9; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // eax
  const struct SplException::TSystemException *v11; // r8
  const struct _GUID *v12; // r9
  unsigned int lpOverlapped; // [rsp+20h] [rbp-198h]
  const struct win_musl::TStringEllipseBase *v14; // [rsp+28h] [rbp-190h]
  HINSTANCE v15; // [rsp+30h] [rbp-188h]
  _BYTE v16[160]; // [rsp+40h] [rbp-178h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-D8h] BYREF

  v5 = a3;
  StorageReader::GetDataFromParent(this);
  if ( *((_QWORD *)this + 2) )
  {
    *a4 = 0;
    if ( (_DWORD)v5 )
    {
      if ( v5 > (unsigned __int64)*((unsigned int *)this + 6) - *((_QWORD *)this + 4) )
        LODWORD(v5) = *((_DWORD *)this + 6) - *((_DWORD *)this + 8);
      *a4 = v5;
      memcpy_0(a2, (const void *)(*((_QWORD *)this + 2) + *((_QWORD *)this + 4)), (unsigned int)v5);
      *((_QWORD *)this + 4) += *a4;
    }
  }
  else
  {
    v8 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 24LL))(*(_QWORD *)this);
    if ( !ReadFile(v8, a2, v5, a4, 0) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v16, "-", 0);
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v9);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v16,
        LastErrorAsFailHRNoBreak,
        v11,
        v12,
        lpOverlapped,
        v14,
        v15);
      SplException::TSystemException::Message((SplException::TSystemException *)v16, "ReadFile failed");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v16);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x1400234f0  push    rbx
0x1400234f2  push    rbp
0x1400234f3  push    rsi
0x1400234f4  push    rdi
0x1400234f5  sub     rsp, 198h
0x1400234fc  mov     rax, cs:__security_cookie
0x140023503  xor     rax, rsp
0x140023506  mov     [rsp+1B8h+var_38], rax
0x14002350e  mov     rsi, r9
0x140023511  mov     ebx, r8d
0x140023514  mov     rbp, rdx
0x140023517  mov     rdi, rcx
0x14002351a  call    ?GetDataFromParent@StorageReader@@AEAAXXZ; StorageReader::GetDataFromParent(void)
0x14002351f  cmp     qword ptr [rdi+10h], 0
0x140023524  jz      short loc_14002357F
0x140023526  mov     dword ptr [rsi], 0
0x14002352c  test    ebx, ebx
0x14002352e  jz      short loc_140023563
0x140023530  mov     edx, [rdi+18h]
0x140023533  mov     ecx, edx
0x140023535  sub     rcx, [rdi+20h]
0x140023539  cmp     rbx, rcx
0x14002353c  mov     rcx, rsi
0x14002353f  jbe     short loc_140023546
0x140023541  mov     ebx, edx
0x140023543  sub     ebx, [rdi+20h]
0x140023546  mov     eax, ebx
0x140023548  mov     [rcx], ebx
0x14002354a  mov     r8d, ebx; Size
0x14002354d  mov     rdx, [rdi+20h]
0x140023551  add     rdx, [rdi+10h]; Src
0x140023555  mov     rcx, rbp; void *
0x140023558  call    memcpy_0
0x14002355d  mov     eax, [rsi]
0x14002355f  add     [rdi+20h], rax
0x140023563  mov     rcx, [rsp+1B8h+var_38]
0x14002356b  xor     rcx, rsp; StackCookie
0x14002356e  call    __security_check_cookie
0x140023573  add     rsp, 198h
0x14002357a  pop     rdi
0x14002357b  pop     rsi
0x14002357c  pop     rbp
0x14002357d  pop     rbx
0x14002357e  retn
0x14002357f  mov     rcx, [rdi]
0x140023582  mov     rax, [rcx]
0x140023585  mov     rax, [rax+18h]
0x140023589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002358e  mov     rcx, rax; hFile
0x140023591  mov     [rsp+1B8h+lpOverlapped], 0; unsigned int
0x14002359a  mov     r9, rsi; lpNumberOfBytesRead
0x14002359d  mov     r8d, ebx; nNumberOfBytesToRead
0x1400235a0  mov     rdx, rbp; lpBuffer
0x1400235a3  call    cs:__imp_ReadFile
0x1400235a9  test    eax, eax
0x1400235ab  jnz     short loc_140023563
0x1400235ad  xor     r8d, r8d; unsigned int
0x1400235b0  lea     rdx, asc_1400696D8; "-"
0x1400235b7  lea     rcx, [rsp+1B8h+var_178]; this
0x1400235bc  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400235c1  nop
0x1400235c2  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1400235c7  mov     edx, eax; unsigned int
0x1400235c9  lea     rcx, [rsp+1B8h+var_178]; this
0x1400235ce  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400235d3  lea     rdx, aReadfileFailed; "ReadFile failed"
0x1400235da  lea     rcx, [rsp+1B8h+var_178]; this
0x1400235df  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400235e4  lea     rdx, [rsp+1B8h+var_178]; struct SplException::THResultException *
0x1400235e9  lea     rcx, [rsp+1B8h+pExceptionObject]; this
0x1400235f1  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400235f6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400235fd  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x140023605  call    _CxxThrowException_0
```
