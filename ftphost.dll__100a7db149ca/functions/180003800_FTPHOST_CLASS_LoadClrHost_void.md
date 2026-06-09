# FTPHOST_CLASS::LoadClrHost(void)

- ea: `0x180003800`
- end: `0x1800038e6`
- name: `?LoadClrHost@FTPHOST_CLASS@@QEAAJXZ`
- size: `230`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180003630`

## callees

- `0x180003800`
- `0x180003afc`
- `0x1800043f6`
- `0x180004420`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180003848`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180003848`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800038bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800038bd`
- `ADVAPI32!RegGetValueW` at `0x18000388e`
- `ADVAPI32!RegGetValueW` at `0x18000388e`

## string_xrefs

- `0x180003882`: `System\CurrentControlSet\Services\FTPSVC\Parameters`

## pseudocode

```c
__int64 __fastcall FTPHOST_CLASS::LoadClrHost(RTL_SRWLOCK *this)
{
  unsigned int ClrHostingHelper; // edi
  struct IClrHostingHelper **v3; // rcx
  const unsigned __int16 *v4; // rdx
  DWORD pdwType; // [rsp+40h] [rbp-68h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-64h] BYREF
  _BYTE pvData[64]; // [rsp+50h] [rbp-58h] BYREF

  pdwType = 1;
  ClrHostingHelper = 0;
  memset_0(pvData, 0, sizeof(pvData));
  pcbData[0] = 64;
  AcquireSRWLockExclusive(this + 3);
  if ( !FTPHOST_CLASS::sm_pClrHostingHelper )
  {
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\FTPSVC\\Parameters",
           L"CLRVersion",
           2u,
           &pdwType,
           pvData,
           pcbData)
      || pdwType != 1
      || (v4 = (const unsigned __int16 *)pvData, pcbData[0] <= 2) )
    {
      v4 = L"v4.0.30319";
    }
    ClrHostingHelper = CoCreateClrHostingHelper(v3, v4);
  }
  ReleaseSRWLockExclusive(this + 3);
  return ClrHostingHelper;
}

```

## disassembly

```asm
0x180003800  mov     [rsp+arg_8], rbx
0x180003805  push    rdi
0x180003806  sub     rsp, 0A0h
0x18000380d  mov     rax, cs:__security_cookie
0x180003814  xor     rax, rsp
0x180003817  mov     [rsp+0A8h+var_18], rax
0x18000381f  mov     rbx, rcx
0x180003822  mov     [rsp+0A8h+var_68], 1
0x18000382a  xor     edi, edi
0x18000382c  lea     rcx, [rsp+0A8h+var_58]; void *
0x180003831  xor     edx, edx; Val
0x180003833  lea     r8d, [rdi+40h]; Size
0x180003837  call    memset_0
0x18000383c  lea     rcx, [rbx+18h]; SRWLock
0x180003840  mov     [rsp+0A8h+var_64], 40h ; '@'
0x180003848  call    cs:__imp_AcquireSRWLockExclusive
0x18000384e  cmp     cs:?sm_pClrHostingHelper@FTPHOST_CLASS@@0PEAUIClrHostingHelper@@EA, rdi; IClrHostingHelper * FTPHOST_CLASS::sm_pClrHostingHelper
0x180003855  jnz     short loc_1800038B9
0x180003857  lea     rax, [rsp+0A8h+var_64]
0x18000385c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180003863  mov     [rsp+0A8h+pcbData], rax; pcbData
0x180003868  lea     r9d, [rdi+2]; dwFlags
0x18000386c  lea     rax, [rsp+0A8h+var_58]
0x180003871  mov     [rsp+0A8h+pvData], rax; pvData
0x180003876  lea     r8, Value; "CLRVersion"
0x18000387d  lea     rax, [rsp+0A8h+var_68]
0x180003882  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\FT"...
0x180003889  mov     [rsp+0A8h+pdwType], rax; pdwType
0x18000388e  call    cs:__imp_RegGetValueW
0x180003894  test    eax, eax
0x180003896  jnz     short loc_1800038AB
0x180003898  cmp     [rsp+0A8h+var_68], 1
0x18000389d  jnz     short loc_1800038AB
0x18000389f  cmp     [rsp+0A8h+var_64], 2
0x1800038a4  lea     rdx, [rsp+0A8h+var_58]
0x1800038a9  ja      short loc_1800038B2
0x1800038ab  lea     rdx, aV4030319; "v4.0.30319"
0x1800038b2  call    ?CoCreateClrHostingHelper@@YAJPEAPEAUIClrHostingHelper@@PEBG@Z; CoCreateClrHostingHelper(IClrHostingHelper * *,ushort const *)
0x1800038b7  mov     edi, eax
0x1800038b9  lea     rcx, [rbx+18h]; SRWLock
0x1800038bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800038c3  mov     eax, edi
0x1800038c5  mov     rcx, [rsp+0A8h+var_18]
0x1800038cd  xor     rcx, rsp; StackCookie
0x1800038d0  call    __security_check_cookie
0x1800038d5  mov     rbx, [rsp+0A8h+arg_8]
0x1800038dd  add     rsp, 0A0h
0x1800038e4  pop     rdi
0x1800038e5  retn
```
