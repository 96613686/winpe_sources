# CMsftFileSystemImage::RollbackToChangePoint(long)

- ea: `0x180057c80`
- end: `0x180057d01`
- name: `?RollbackToChangePoint@CMsftFileSystemImage@@UEAAJJ@Z`
- size: `129`
- prototype: `int(CMsftFileSystemImage *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800040b0`
- `0x1800048e0`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x180047c94`
- `0x180057c80`

## string_xrefs

- `0x180057c93`: `CMsftFileSystemImage::RollbackToChangePoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMsftFileSystemImage::RollbackToChangePoint(FileSystemImage ***this, unsigned int a2)
{
  char v5; // [rsp+58h] [rbp+20h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v5, "CMsftFileSystemImage::RollbackToChangePoint");
  ImapiClearErrorInfo();
  ImapiComObject::LockCS((ImapiComObject *)(this + 10));
  try
  {
    FileSystemImage::RollbackRecover(*this[26], a2, 0);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_MsftFileSystemImage);
  }
  ImapiComObject::UnlockCS((ImapiComObject *)(this + 10));
  MethodTrace::~MethodTrace((MethodTrace *)&v5);
  return 0;
}

```

## disassembly

```asm
0x180057c80  mov     [rsp+arg_8], rbx
0x180057c85  push    rsi
0x180057c86  push    rdi
0x180057c87  push    r14
0x180057c89  sub     rsp, 20h
0x180057c8d  mov     r14d, edx
0x180057c90  mov     rsi, rcx
0x180057c93  lea     rdx, aCmsftfilesyste_9; "CMsftFileSystemImage::RollbackToChangeP"...
0x180057c9a  lea     rcx, [rsp+38h+arg_18]; this
0x180057c9f  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180057ca4  nop
0x180057ca5  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180057caa  xor     edi, edi
0x180057cac  lea     rbx, [rsi+50h]
0x180057cb0  mov     [rsp+38h+arg_10], rbx
0x180057cb5  mov     rcx, rbx; this
0x180057cb8  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180057cbd  mov     rcx, [rsi+0D0h]
0x180057cc4  xor     r8d, r8d; bool
0x180057cc7  mov     edx, r14d; unsigned int
0x180057cca  mov     rcx, [rcx]; this
0x180057ccd  call    ?RollbackRecover@FileSystemImage@@AEAAXK_N@Z; FileSystemImage::RollbackRecover(ulong,bool)
0x180057cd2  nop
0x180057cd3  jmp     short loc_180057CDE
0x180057cd5  mov     edi, [rsp+38h+arg_0]
0x180057cd9  mov     rbx, [rsp+38h+arg_10]
0x180057cde  mov     rcx, rbx; this
0x180057ce1  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180057ce6  nop
0x180057ce7  lea     rcx, [rsp+38h+arg_18]; this
0x180057cec  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180057cf1  mov     eax, edi
0x180057cf3  mov     rbx, [rsp+38h+arg_8]
0x180057cf8  add     rsp, 20h
0x180057cfc  pop     r14
0x180057cfe  pop     rdi
0x180057cff  pop     rsi
0x180057d00  retn
```
