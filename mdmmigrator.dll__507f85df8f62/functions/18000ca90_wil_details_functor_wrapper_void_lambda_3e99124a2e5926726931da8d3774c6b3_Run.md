# wil::details::functor_wrapper_void__lambda_3e99124a2e5926726931da8d3774c6b3___::Run

- ea: `0x18000ca90`
- end: `0x18000cb46`
- name: `wil::details::functor_wrapper_void__lambda_3e99124a2e5926726931da8d3774c6b3___::Run`
- size: `182`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c3f8`

## callees

- `0x1800022e0`
- `0x1800076a4`
- `0x1800097fc`
- `0x18000be00`
- `0x18000c554`
- `0x18000ca90`

## string_xrefs

- `0x18000cab4`: `C:\Windows\System32\MDMAgent.exe`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_3e99124a2e5926726931da8d3774c6b3___::Run(__int64 a1)
{
  int **v1; // rdi
  __int64 v2; // rdx
  int *v3; // rbx
  __int64 v4; // r8
  int v6; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+38h] [rbp-30h] BYREF
  int *v8; // [rsp+48h] [rbp-20h]
  __int64 v9; // [rsp+50h] [rbp-18h]

  v1 = *(int ***)(a1 + 8);
  v2 = *(_QWORD *)v1[1];
  v7.Ptr = (ULONGLONG)L"C:\\Windows\\System32\\MDMAgent.exe";
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(&v7.Size, v2);
  v3 = *v1;
  *v3 = ScheduleMigrator::CreateSchedules((ScheduleMigrator *)&v7);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((void **)&v7.Size);
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
  {
    v6 = **v1;
    v8 = &v6;
    v9 = 4;
    McGenEventWrite_EventWriteTransfer(
      &MDM_ENTERPRISE_DIAGNOSTICS_Context,
      (const EVENT_DESCRIPTOR *)SchedulesCreated,
      v4,
      2u,
      &v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ca90  mov     [rsp+arg_8], rbx
0x18000ca95  push    rdi
0x18000ca96  sub     rsp, 60h
0x18000ca9a  mov     rax, cs:__security_cookie
0x18000caa1  xor     rax, rsp
0x18000caa4  mov     [rsp+68h+var_10], rax
0x18000caa9  mov     rdi, [rcx+8]
0x18000caad  mov     rax, [rdi+8]
0x18000cab1  mov     rdx, [rax]
0x18000cab4  lea     rax, aCWindowsSystem; "C:\\Windows\\System32\\MDMAgent.exe"
0x18000cabb  mov     [rsp+68h+var_30], rax
0x18000cac0  lea     rcx, [rsp+68h+var_28]
0x18000cac5  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@AEBV01@@Z; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(std::map<std::wstring,std::wstring> const &)
0x18000caca  nop
0x18000cacb  mov     rbx, [rdi]
0x18000cace  lea     rcx, [rsp+68h+var_30]; this
0x18000cad3  call    ?CreateSchedules@ScheduleMigrator@@QEAAJXZ; ScheduleMigrator::CreateSchedules(void)
0x18000cad8  mov     [rbx], eax
0x18000cada  lea     rcx, [rsp+68h+var_28]
0x18000cadf  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000cae4  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x18000caeb  jz      short loc_18000CB2C
0x18000caed  mov     rax, [rdi]
0x18000caf0  mov     ecx, [rax]
0x18000caf2  mov     [rsp+68h+var_38], ecx
0x18000caf6  lea     rax, [rsp+68h+var_38]
0x18000cafb  mov     [rsp+68h+var_20], rax
0x18000cb00  mov     [rsp+68h+var_18], 4
0x18000cb09  lea     rax, [rsp+68h+var_30]
0x18000cb0e  mov     [rsp+68h+var_48], rax
0x18000cb13  mov     r9d, 2
0x18000cb19  lea     rdx, SchedulesCreated
0x18000cb20  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18000cb27  call    McGenEventWrite_EventWriteTransfer
0x18000cb2c  xor     eax, eax
0x18000cb2e  mov     rcx, [rsp+68h+var_10]
0x18000cb33  xor     rcx, rsp; StackCookie
0x18000cb36  call    __security_check_cookie
0x18000cb3b  mov     rbx, [rsp+68h+arg_8]
0x18000cb40  add     rsp, 60h
0x18000cb44  pop     rdi
0x18000cb45  retn
```
