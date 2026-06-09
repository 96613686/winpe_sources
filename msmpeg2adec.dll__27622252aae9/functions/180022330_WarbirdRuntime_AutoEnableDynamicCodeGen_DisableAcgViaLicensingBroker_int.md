# WarbirdRuntime::AutoEnableDynamicCodeGen::DisableAcgViaLicensingBroker(int)

- ea: `0x180022330`
- end: `0x180022462`
- name: `?DisableAcgViaLicensingBroker@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NH@Z`
- size: `306`
- prototype: `bool __fastcall(WarbirdRuntime::AutoEnableDynamicCodeGen *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f500`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x180022330`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800223d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800223d9`

## pseudocode

```c
bool __fastcall WarbirdRuntime::AutoEnableDynamicCodeGen::DisableAcgViaLicensingBroker(
        WarbirdRuntime::AutoEnableDynamicCodeGen *this)
{
  int v2; // eax
  GUID *v4; // [rsp+40h] [rbp-268h] BYREF
  __int64 v5; // [rsp+48h] [rbp-260h]
  __int64 v6; // [rsp+50h] [rbp-258h]
  GUID v7; // [rsp+58h] [rbp-250h] BYREF
  GUID v8; // [rsp+68h] [rbp-240h] BYREF
  WCHAR Filename[264]; // [rsp+80h] [rbp-228h] BYREF

  v6 = 0;
  v8 = GUID_d3e9e342_5deb_43b6_849e_6913b85d503a;
  v7 = GUID_80ae3fc2_2580_4483_b427_9215c56e1604;
  memset_0(Filename, 0, 0x208u);
  v5 = 0;
  v4 = &v7;
  v2 = ((__int64 (__fastcall *)(WarbirdRuntime::AutoEnableDynamicCodeGen *, _QWORD, __int64, _QWORD, int, GUID **))WarbirdRuntime::AutoEnableDynamicCodeGen::CoCreateInstanceFromAppProc)(
         this,
         0,
         1,
         0,
         1,
         &v4);
  if ( v2 < 0 )
  {
    if ( v2 == -2147467262 )
    {
      v4 = &v8;
      return (*(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 64LL))(v5, 1) >= 0;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    GetModuleFileNameW(&_ImageBase, Filename, 0x104u);
    return (*(int (__fastcall **)(__int64, __int64, WCHAR *))(*(_QWORD *)v5 + 24LL))(v5, 1, Filename) >= 0;
  }
}

```

## disassembly

```asm
0x180022330  mov     [rsp+arg_8], rbx
0x180022335  push    rdi
0x180022336  sub     rsp, 2A0h
0x18002233d  mov     rax, cs:__security_cookie
0x180022344  xor     rax, rsp
0x180022347  mov     [rsp+2A8h+var_18], rax
0x18002234f  movups  xmm0, xmmword ptr cs:_GUID_d3e9e342_5deb_43b6_849e_6913b85d503a.Data1
0x180022356  mov     rbx, rcx
0x180022359  xor     edi, edi
0x18002235b  movups  xmm1, xmmword ptr cs:_GUID_80ae3fc2_2580_4483_b427_9215c56e1604.Data1
0x180022362  xor     edx, edx; Val
0x180022364  mov     [rsp+2A8h+var_258], rdi
0x180022369  mov     r8d, 208h; Size
0x18002236f  lea     rcx, [rsp+2A8h+Filename]; void *
0x180022377  movups  [rsp+2A8h+var_240], xmm0
0x18002237c  movups  [rsp+2A8h+var_250], xmm1
0x180022381  call    memset_0
0x180022386  lea     rax, [rsp+2A8h+var_250]
0x18002238b  mov     [rsp+2A8h+var_260], rdi
0x180022390  mov     [rsp+2A8h+var_268], rax
0x180022395  mov     edi, 1
0x18002239a  lea     rax, [rsp+2A8h+var_268]
0x18002239f  xor     r9d, r9d
0x1800223a2  mov     [rsp+2A8h+var_280], rax
0x1800223a7  mov     r8d, edi
0x1800223aa  mov     rax, cs:?CoCreateInstanceFromAppProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJAEBU_GUID@@PEAUIUnknown@12@KPEAXKPEAUtagMULTI_QI@12@@ZEA; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::CoCreateInstanceFromAppProc)(_GUID const &,WarbirdRuntime::AutoEnableDynamicCodeGen::IUnknown *,ulong,void *,ulong,WarbirdRuntime::AutoEnableDynamicCodeGen::tagMULTI_QI *)
0x1800223b1  xor     edx, edx
0x1800223b3  mov     rcx, rbx
0x1800223b6  mov     [rsp+2A8h+var_288], edi
0x1800223ba  call    cs:__guard_dispatch_icall_fptr
0x1800223c0  test    eax, eax
0x1800223c2  js      short loc_180022409
0x1800223c4  mov     r8d, 104h; nSize
0x1800223ca  lea     rdx, [rsp+2A8h+Filename]; lpFilename
0x1800223d2  lea     rcx, __ImageBase; hModule
0x1800223d9  call    cs:__imp_GetModuleFileNameW
0x1800223e0  nop     dword ptr [rax+rax+00h]
0x1800223e5  mov     rcx, [rsp+2A8h+var_260]
0x1800223ea  lea     r8, [rsp+2A8h+Filename]
0x1800223f2  mov     edx, edi
0x1800223f4  mov     rax, [rcx]
0x1800223f7  mov     rax, [rax+18h]
0x1800223fb  call    cs:__guard_dispatch_icall_fptr
0x180022401  shr     eax, 1Fh
0x180022404  xor     al, dil
0x180022407  jmp     short loc_180022440
0x180022409  xor     bl, bl
0x18002240b  cmp     eax, 80004002h
0x180022410  jnz     short loc_18002243D
0x180022412  mov     rcx, [rsp+2A8h+var_260]
0x180022417  lea     rax, [rsp+2A8h+var_240]
0x18002241c  mov     [rsp+2A8h+var_268], rax
0x180022421  mov     edx, edi
0x180022423  mov     rax, [rcx]
0x180022426  mov     rax, [rax+40h]
0x18002242a  call    cs:__guard_dispatch_icall_fptr
0x180022430  test    eax, eax
0x180022432  movzx   ecx, bl
0x180022435  cmovns  ecx, edi
0x180022438  movzx   eax, cl
0x18002243b  jmp     short loc_180022440
0x18002243d  movzx   eax, bl
0x180022440  mov     rcx, [rsp+2A8h+var_18]
0x180022448  xor     rcx, rsp; StackCookie
0x18002244b  call    __security_check_cookie
0x180022450  mov     rbx, [rsp+2A8h+arg_8]
0x180022458  add     rsp, 2A0h
0x18002245f  pop     rdi
0x180022460  retn
```
