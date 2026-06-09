# IcfAddrChangeNotificationCreate

- ea: `0x18001fd00`
- end: `0x18001fdd1`
- name: `IcfAddrChangeNotificationCreate`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18001fd00`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18001fd62`
- `fwbase!FwHResultToWindowsError` at `0x18001fd62`
- `fwbase!FwChangeSinkCreate` at `0x18001fd94`
- `fwbase!FwChangeSinkCreate` at `0x18001fd94`
- `fwbase!FwReportReturnError` at `0x18001fd54`
- `fwbase!FwReportReturnError` at `0x18001fd54`

## string_xrefs

- `0x18001fd4d`: `IcfAddrChangeNotificationCreate`

## pseudocode

```c
__int64 __fastcall IcfAddrChangeNotificationCreate(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // eax
  __int64 v8; // [rsp+20h] [rbp-18h] BYREF

  v8 = 0;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  if ( a2 )
  {
    v7 = FwChangeSinkCreate(a1, 1, &v8);
    v4 = v7;
    if ( v7 >= 0 )
    {
      *a2 = v8;
      return FwHResultToWindowsError(v4);
    }
    v5 = (unsigned int)v7;
  }
  else
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
  }
  FwReportReturnError("IcfAddrChangeNotificationCreate", v5);
  return FwHResultToWindowsError(v4);
}

```

## disassembly

```asm
0x18001fd00  mov     [rsp+arg_10], rbx
0x18001fd05  push    rdi
0x18001fd06  sub     rsp, 30h
0x18001fd0a  mov     rax, cs:__security_cookie
0x18001fd11  xor     rax, rsp
0x18001fd14  mov     [rsp+38h+var_10], rax
0x18001fd19  mov     rdi, rdx
0x18001fd1c  mov     [rsp+38h+var_18], 0
0x18001fd25  mov     rbx, rcx
0x18001fd28  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd2f  lea     rax, WPP_GLOBAL_Control
0x18001fd36  cmp     rcx, rax
0x18001fd39  jz      short loc_18001FD41
0x18001fd3b  test    byte ptr [rcx+1Ch], 8
0x18001fd3f  jnz     short loc_18001FDB0
0x18001fd41  test    rdi, rdi
0x18001fd44  jnz     short loc_18001FD87
0x18001fd46  mov     ebx, 80004003h
0x18001fd4b  mov     edx, ebx
0x18001fd4d  lea     rcx, aIcfaddrchangen_0; "IcfAddrChangeNotificationCreate"
0x18001fd54  call    cs:__imp_FwReportReturnError
0x18001fd5b  nop     dword ptr [rax+rax+00h]
0x18001fd60  mov     ecx, ebx
0x18001fd62  call    cs:__imp_FwHResultToWindowsError
0x18001fd69  nop     dword ptr [rax+rax+00h]
0x18001fd6e  mov     rcx, [rsp+38h+var_10]
0x18001fd73  xor     rcx, rsp; StackCookie
0x18001fd76  call    __security_check_cookie
0x18001fd7b  mov     rbx, [rsp+38h+arg_10]
0x18001fd80  add     rsp, 30h
0x18001fd84  pop     rdi
0x18001fd85  retn
0x18001fd87  lea     r8, [rsp+38h+var_18]
0x18001fd8c  mov     edx, 1
0x18001fd91  mov     rcx, rbx
0x18001fd94  call    cs:__imp_FwChangeSinkCreate
0x18001fd9b  nop     dword ptr [rax+rax+00h]
0x18001fda0  mov     ebx, eax
0x18001fda2  test    eax, eax
0x18001fda4  js      short loc_18001FDCA
0x18001fda6  mov     rax, [rsp+38h+var_18]
0x18001fdab  mov     [rdi], rax
0x18001fdae  jmp     short loc_18001FD60
0x18001fdb0  mov     rcx, [rcx+10h]
0x18001fdb4  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18001fdbb  mov     edx, 0Dh
0x18001fdc0  call    WPP_SF_
0x18001fdc5  jmp     loc_18001FD41
0x18001fdca  mov     edx, eax
0x18001fdcc  jmp     loc_18001FD4D
```
