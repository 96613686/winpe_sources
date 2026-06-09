# CCsrMgr::CreateLpcPort(void)

- ea: `0x18006fefc`
- end: `0x18007002f`
- name: `?CreateLpcPort@CCsrMgr@@AEAAJXZ`
- size: `307`
- prototype: `__int64 __fastcall(CCsrMgr *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006fa1c`

## callees

- `0x1800074c0`
- `0x18004b460`
- `0x18004b830`
- `0x18004bf44`
- `0x18006fefc`
- `0x180070038`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18006ff9e`
- `ntdll!RtlInitUnicodeString` at `0x18006ff9e`
- `ntdll!NtAlpcCreatePort` at `0x18006ffdd`
- `ntdll!NtAlpcCreatePort` at `0x18006ffdd`

## string_xrefs

- `0x18006fff7`: `CCsrMgr::CreateLpcPort`
- `0x18006ff4b`: `CCsrMgr::CreatePortSecurityDescriptor failed: 0x%x in %s`
- `0x18006fff0`: `NtAlpcCreatePort failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CCsrMgr::CreateLpcPort(CCsrMgr *this)
{
  CCsrMgr *v2; // rcx
  int v3; // eax
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
  v3 = CCsrMgr::CreatePortSecurityDescriptor(v2, &v9);
  v4 = v9;
  v5 = v3;
  if ( v3 >= 0 )
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
      (unsigned int)v3,
      "CCsrMgr::CreateLpcPort");
  }
  if ( v4 )
    operator delete(v4, v6);
  return v5;
}

```

## disassembly

```asm
0x18006fefc  push    rbp
0x18006fefe  push    rbx
0x18006feff  push    rsi
0x18006ff00  push    rdi
0x18006ff01  lea     rbp, [rsp-3Fh]
0x18006ff06  sub     rsp, 0D8h
0x18006ff0d  mov     rax, cs:__security_cookie
0x18006ff14  xor     rax, rsp
0x18006ff17  mov     [rbp+57h+var_30], rax
0x18006ff1b  xor     edx, edx; Val
0x18006ff1d  mov     [rbp+57h+var_D0], 0
0x18006ff25  mov     rsi, rcx
0x18006ff28  lea     rcx, [rbp+57h+var_80]; void *
0x18006ff2c  lea     r8d, [rdx+48h]; Size
0x18006ff30  call    memset_0
0x18006ff35  lea     rdx, [rbp+57h+var_D0]; void **
0x18006ff39  call    ?CreatePortSecurityDescriptor@CCsrMgr@@AEAAJPEAPEAX@Z; CCsrMgr::CreatePortSecurityDescriptor(void * *)
0x18006ff3e  mov     rdi, [rbp+57h+var_D0]
0x18006ff42  mov     ebx, eax
0x18006ff44  test    eax, eax
0x18006ff46  jns     short loc_18006FF57
0x18006ff48  mov     r8d, eax
0x18006ff4b  lea     rdx, aCcsrmgrCreatep_0; "CCsrMgr::CreatePortSecurityDescriptor f"...
0x18006ff52  jmp     loc_18006FFF7
0x18006ff57  xor     edx, edx; Val
0x18006ff59  lea     rcx, [rbp+57h+var_80]; void *
0x18006ff5d  lea     r8d, [rdx+48h]; Size
0x18006ff61  call    memset_0
0x18006ff66  xorps   xmm1, xmm1
0x18006ff69  mov     [rbp+57h+var_80], 20000h
0x18006ff70  xorps   xmm0, xmm0
0x18006ff73  mov     [rbp+57h+var_70], 4070h
0x18006ff7b  lea     rdx, aSmsswinstation; "\\SmSsWinStationApiPort"
0x18006ff82  mov     [rbp+57h+var_60], 80E00h
0x18006ff8a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006ff8e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18006ff92  movups  [rbp+57h+var_C8], xmm1
0x18006ff96  movups  [rbp+57h+var_B8], xmm1
0x18006ff9a  movups  [rbp+57h+var_A8], xmm1
0x18006ff9e  call    cs:__imp_RtlInitUnicodeString
0x18006ffa4  lea     rax, [rbp+57h+DestinationString]
0x18006ffa8  mov     dword ptr [rbp+57h+var_C8], 30h ; '0'
0x18006ffaf  lea     rcx, [rsi+720h]
0x18006ffb6  mov     qword ptr [rbp+57h+var_B8], rax
0x18006ffba  lea     r8, [rbp+57h+var_80]
0x18006ffbe  mov     qword ptr [rbp+57h+var_C8+8], 0
0x18006ffc6  lea     rdx, [rbp+57h+var_C8]
0x18006ffca  mov     dword ptr [rbp+57h+var_B8+8], 0
0x18006ffd1  mov     qword ptr [rbp+57h+var_A8], rdi
0x18006ffd5  mov     qword ptr [rbp+57h+var_A8+8], 0
0x18006ffdd  call    cs:__imp_NtAlpcCreatePort
0x18006ffe3  mov     ebx, eax
0x18006ffe5  or      ebx, 10000000h
0x18006ffeb  jge     short loc_180070008
0x18006ffed  mov     r8d, ebx
0x18006fff0  lea     rdx, aNtalpccreatepo; "NtAlpcCreatePort failed: 0x%x in %s"
0x18006fff7  lea     r9, aCcsrmgrCreatel; "CCsrMgr::CreateLpcPort"
0x18006fffe  mov     ecx, 8; int
0x180070003  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180070008  test    rdi, rdi
0x18007000b  jz      short loc_180070015
0x18007000d  mov     rcx, rdi; void *
0x180070010  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180070015  mov     eax, ebx
0x180070017  mov     rcx, [rbp+57h+var_30]
0x18007001b  xor     rcx, rsp; StackCookie
0x18007001e  call    __security_check_cookie
0x180070023  add     rsp, 0D8h
0x18007002a  pop     rdi
0x18007002b  pop     rsi
0x18007002c  pop     rbx
0x18007002d  pop     rbp
0x18007002e  retn
```
