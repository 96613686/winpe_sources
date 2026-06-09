# CCsrMgr::CreateLpcPort(void)

- ea: `0x180073f4c`
- end: `0x18007408c`
- name: `?CreateLpcPort@CCsrMgr@@AEAAJXZ`
- size: `320`
- prototype: `__int64 __fastcall(CCsrMgr *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180073a34`

## callees

- `0x1800077a0`
- `0x18004e850`
- `0x18004ec20`
- `0x18004f354`
- `0x180073f4c`
- `0x180074094`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180073fee`
- `ntdll!RtlInitUnicodeString` at `0x180073fee`
- `ntdll!NtAlpcCreatePort` at `0x180074033`
- `ntdll!NtAlpcCreatePort` at `0x180074033`

## string_xrefs

- `0x180074053`: `CCsrMgr::CreateLpcPort`
- `0x180073f9b`: `CCsrMgr::CreatePortSecurityDescriptor failed: 0x%x in %s`
- `0x18007404c`: `NtAlpcCreatePort failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CCsrMgr::CreateLpcPort(CCsrMgr *this)
{
  CCsrMgr *v2; // rcx
  int PortSecurityDescriptor; // eax
  void *v4; // rdi
  unsigned int v5; // ebx
  const struct std::nothrow_t *v6; // rdx
  int v7; // eax
  void *v9; // [rsp+20h] [rbp-79h] BYREF
  __int128 v10; // [rsp+28h] [rbp-71h] BYREF
  __int128 v11; // [rsp+38h] [rbp-61h]
  __int128 v12; // [rsp+48h] [rbp-51h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-41h] BYREF
  _DWORD v14[4]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v15; // [rsp+80h] [rbp-19h]
  __int64 v16; // [rsp+90h] [rbp-9h]

  v9 = 0;
  memset_0(v14, 0, 0x48u);
  PortSecurityDescriptor = CCsrMgr::CreatePortSecurityDescriptor(v2, (struct _ACL **)&v9);
  v4 = v9;
  v5 = PortSecurityDescriptor;
  if ( PortSecurityDescriptor >= 0 )
  {
    memset_0(v14, 0, 0x48u);
    v14[0] = 0x20000;
    v15 = 16496;
    v16 = 527872;
    DestinationString = 0;
    v10 = 0;
    v11 = 0;
    v12 = 0;
    RtlInitUnicodeString(&DestinationString, L"\\SmSsWinStationApiPort");
    LODWORD(v10) = 48;
    *(_QWORD *)&v11 = &DestinationString;
    *((_QWORD *)&v10 + 1) = 0;
    DWORD2(v11) = 0;
    v12 = (unsigned __int64)v4;
    v7 = NtAlpcCreatePort((char *)this + 1824, &v10, v14);
    v5 = v7 | 0x10000000;
    if ( v7 < 0 )
      _DbgPrintMessage(8, "NtAlpcCreatePort failed: 0x%x in %s", v5, "CCsrMgr::CreateLpcPort");
  }
  else
  {
    _DbgPrintMessage(
      8,
      "CCsrMgr::CreatePortSecurityDescriptor failed: 0x%x in %s",
      (unsigned int)PortSecurityDescriptor,
      "CCsrMgr::CreateLpcPort");
  }
  if ( v4 )
    operator delete(v4, v6);
  return v5;
}

```

## disassembly

```asm
0x180073f4c  push    rbp
0x180073f4e  push    rbx
0x180073f4f  push    rsi
0x180073f50  push    rdi
0x180073f51  lea     rbp, [rsp-3Fh]
0x180073f56  sub     rsp, 0D8h
0x180073f5d  mov     rax, cs:__security_cookie
0x180073f64  xor     rax, rsp
0x180073f67  mov     [rbp+57h+var_30], rax
0x180073f6b  xor     edx, edx; Val
0x180073f6d  mov     [rbp+57h+var_D0], 0
0x180073f75  mov     rsi, rcx
0x180073f78  lea     rcx, [rbp+57h+var_80]; void *
0x180073f7c  lea     r8d, [rdx+48h]; Size
0x180073f80  call    memset_0
0x180073f85  lea     rdx, [rbp+57h+var_D0]; void **
0x180073f89  call    ?CreatePortSecurityDescriptor@CCsrMgr@@AEAAJPEAPEAX@Z; CCsrMgr::CreatePortSecurityDescriptor(void * *)
0x180073f8e  mov     rdi, [rbp+57h+var_D0]
0x180073f92  mov     ebx, eax
0x180073f94  test    eax, eax
0x180073f96  jns     short loc_180073FA7
0x180073f98  mov     r8d, eax
0x180073f9b  lea     rdx, aCcsrmgrCreatep_0; "CCsrMgr::CreatePortSecurityDescriptor f"...
0x180073fa2  jmp     loc_180074053
0x180073fa7  xor     edx, edx; Val
0x180073fa9  lea     rcx, [rbp+57h+var_80]; void *
0x180073fad  lea     r8d, [rdx+48h]; Size
0x180073fb1  call    memset_0
0x180073fb6  xorps   xmm1, xmm1
0x180073fb9  mov     [rbp+57h+var_80], 20000h
0x180073fc0  xorps   xmm0, xmm0
0x180073fc3  mov     [rbp+57h+var_70], 4070h
0x180073fcb  lea     rdx, aSmsswinstation; "\\SmSsWinStationApiPort"
0x180073fd2  mov     [rbp+57h+var_60], 80E00h
0x180073fda  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180073fde  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180073fe2  movups  [rbp+57h+var_C8], xmm1
0x180073fe6  movups  [rbp+57h+var_B8], xmm1
0x180073fea  movups  [rbp+57h+var_A8], xmm1
0x180073fee  call    cs:__imp_RtlInitUnicodeString
0x180073ff5  nop     dword ptr [rax+rax+00h]
0x180073ffa  lea     rax, [rbp+57h+DestinationString]
0x180073ffe  mov     dword ptr [rbp+57h+var_C8], 30h ; '0'
0x180074005  lea     rcx, [rsi+720h]
0x18007400c  mov     qword ptr [rbp+57h+var_B8], rax
0x180074010  lea     r8, [rbp+57h+var_80]
0x180074014  mov     qword ptr [rbp+57h+var_C8+8], 0
0x18007401c  lea     rdx, [rbp+57h+var_C8]
0x180074020  mov     dword ptr [rbp+57h+var_B8+8], 0
0x180074027  mov     qword ptr [rbp+57h+var_A8], rdi
0x18007402b  mov     qword ptr [rbp+57h+var_A8+8], 0
0x180074033  call    cs:__imp_NtAlpcCreatePort
0x18007403a  nop     dword ptr [rax+rax+00h]
0x18007403f  mov     ebx, eax
0x180074041  or      ebx, 10000000h
0x180074047  jge     short loc_180074064
0x180074049  mov     r8d, ebx
0x18007404c  lea     rdx, aNtalpccreatepo; "NtAlpcCreatePort failed: 0x%x in %s"
0x180074053  lea     r9, aCcsrmgrCreatel; "CCsrMgr::CreateLpcPort"
0x18007405a  mov     ecx, 8; int
0x18007405f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180074064  test    rdi, rdi
0x180074067  jz      short loc_180074071
0x180074069  mov     rcx, rdi; void *
0x18007406c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180074071  mov     eax, ebx
0x180074073  mov     rcx, [rbp+57h+var_30]
0x180074077  xor     rcx, rsp; StackCookie
0x18007407a  call    __security_check_cookie
0x18007407f  add     rsp, 0D8h
0x180074086  pop     rdi
0x180074087  pop     rsi
0x180074088  pop     rbx
0x180074089  pop     rbp
0x18007408a  retn
```
