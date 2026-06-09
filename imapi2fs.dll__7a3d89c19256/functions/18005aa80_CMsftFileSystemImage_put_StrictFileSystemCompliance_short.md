# CMsftFileSystemImage::put_StrictFileSystemCompliance(short)

- ea: `0x18005aa80`
- end: `0x18005ab04`
- name: `?put_StrictFileSystemCompliance@CMsftFileSystemImage@@UEAAJF@Z`
- size: `132`
- prototype: `__int64 __fastcall(CMsftFileSystemImage *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800040b0`
- `0x1800048e0`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x180048924`
- `0x18005aa80`

## string_xrefs

- `0x18005aa93`: `CMsftFileSystemImage::put_StrictFileSystemCompliance`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMsftFileSystemImage::put_StrictFileSystemCompliance(FileSystemImage ***this, __int16 a2)
{
  char v5; // [rsp+60h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v5, "CMsftFileSystemImage::put_StrictFileSystemCompliance");
  ImapiClearErrorInfo();
  ImapiComObject::LockCS((ImapiComObject *)(this + 10));
  try
  {
    FileSystemImage::SetIsStrict(*this[26], a2 != 0);
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
0x18005aa80  push    rbx
0x18005aa82  push    rsi
0x18005aa83  push    rdi
0x18005aa84  push    r14
0x18005aa86  push    r15
0x18005aa88  sub     rsp, 20h
0x18005aa8c  movzx   r14d, dx
0x18005aa90  mov     rsi, rcx
0x18005aa93  lea     rdx, aCmsftfilesyste_41; "CMsftFileSystemImage::put_StrictFileSys"...
0x18005aa9a  lea     rcx, [rsp+48h+arg_10]; this
0x18005aa9f  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18005aaa4  nop
0x18005aaa5  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18005aaaa  xor     r15d, r15d
0x18005aaad  mov     edi, r15d
0x18005aab0  lea     rbx, [rsi+50h]
0x18005aab4  mov     [rsp+48h+arg_0], rbx
0x18005aab9  mov     rcx, rbx; this
0x18005aabc  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18005aac1  test    r14w, r14w
0x18005aac5  setnz   dl; bool
0x18005aac8  mov     rcx, [rsi+0D0h]
0x18005aacf  mov     rcx, [rcx]; this
0x18005aad2  call    ?SetIsStrict@FileSystemImage@@QEAAX_N@Z; FileSystemImage::SetIsStrict(bool)
0x18005aad7  nop
0x18005aad8  jmp     short loc_18005AAE3
0x18005aada  mov     edi, [rsp+48h+arg_8]
0x18005aade  mov     rbx, [rsp+48h+arg_0]
0x18005aae3  mov     rcx, rbx; this
0x18005aae6  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18005aaeb  nop
0x18005aaec  lea     rcx, [rsp+48h+arg_10]; this
0x18005aaf1  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18005aaf6  mov     eax, edi
0x18005aaf8  add     rsp, 20h
0x18005aafc  pop     r15
0x18005aafe  pop     r14
0x18005ab00  pop     rdi
0x18005ab01  pop     rsi
0x18005ab02  pop     rbx
0x18005ab03  retn
```
