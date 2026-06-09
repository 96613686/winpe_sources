# EnableRAFirewallGroup(void)

- ea: `0x180010d70`
- end: `0x180010ea6`
- name: `?EnableRAFirewallGroup@@YAJXZ`
- size: `310`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ebe0`
- `0x180011af8`

## callees

- `0x180010d70`
- `0x180014660`
- `0x1800148c4`
- `0x18001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010d92`
- `OLEAUT32!__imp_SysAllocString` at `0x180010d92`
- `OLEAUT32!__imp_SysFreeString` at `0x180010e93`
- `OLEAUT32!__imp_SysFreeString` at `0x180010e93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010dd6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010dd6`

## string_xrefs

- `0x180010d7a`: `@FirewallAPI.dll,-33002`

## pseudocode

```c
__int64 EnableRAFirewallGroup(void)
{
  const struct _EVENT_DESCRIPTOR *v0; // rdx
  OLECHAR *v1; // rdi
  HRESULT v2; // ebx
  CEventLogger *v3; // rcx
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  signed int v5; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  unsigned int v7; // r9d
  unsigned int v9; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  v9 = 0;
  v1 = SysAllocString(L"@FirewallAPI.dll,-33002");
  if ( !v1 )
  {
    v2 = -2147024882;
    CEventLogger::LogError(
      (CEventLogger *)L"EnableRAFirewallGroup",
      v0,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x296u,
      L"EnableRAFirewallGroup",
      0x8007000E);
    goto LABEL_10;
  }
  v2 = CoCreateInstance(
         &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
         0,
         1u,
         &GUID_98325047_c671_4174_8d81_defcd3f03186,
         &ppv);
  if ( v2 < 0 )
  {
    CEventLogger::LogEvent(v3, &COM_Problem, L"9C4C6277-5027-441E-AFAE-CA1F542DA009");
    CEventLogger::LogError(
      (CEventLogger *)L"EnableRAFirewallGroup",
      v4,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x2A3u,
      L"EnableRAFirewallGroup",
      v2);
    goto LABEL_10;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 56LL))(ppv, &v9);
  v2 = v5;
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, OLECHAR *, __int64))(*(_QWORD *)ppv + 160LL))(
           ppv,
           v9,
           v1,
           0xFFFFFFFFLL);
    v2 = v5;
    if ( v5 >= 0 )
      goto LABEL_10;
    v7 = 684;
  }
  else
  {
    v7 = 680;
  }
  CEventLogger::LogError(
    (CEventLogger *)L"EnableRAFirewallGroup",
    v6,
    L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
    v7,
    L"EnableRAFirewallGroup",
    v5);
LABEL_10:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v1 )
    SysFreeString(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180010d70  mov     [rsp+arg_10], rbx
0x180010d75  push    rdi
0x180010d76  sub     rsp, 30h
0x180010d7a  lea     rcx, psz; "@FirewallAPI.dll,-33002"
0x180010d81  mov     [rsp+38h+arg_8], 0
0x180010d8a  mov     [rsp+38h+arg_0], 0
0x180010d92  call    cs:__imp_SysAllocString
0x180010d98  mov     rdi, rax
0x180010d9b  test    rax, rax
0x180010d9e  jnz     short loc_180010DB8
0x180010da0  mov     ebx, 8007000Eh
0x180010da5  mov     [rsp+38h+var_10], 8007000Eh
0x180010dad  mov     r9d, 296h
0x180010db3  jmp     loc_180010E54
0x180010db8  xor     edx, edx; pUnkOuter
0x180010dba  lea     rax, [rsp+38h+arg_8]
0x180010dbf  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x180010dc6  mov     [rsp+38h+ppv], rax; ppv
0x180010dcb  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x180010dd2  lea     r8d, [rdx+1]; dwClsContext
0x180010dd6  call    cs:__imp_CoCreateInstance
0x180010ddc  mov     ebx, eax
0x180010dde  test    eax, eax
0x180010de0  jns     short loc_180010E01
0x180010de2  lea     r8, a9c4c6277502744; "9C4C6277-5027-441E-AFAE-CA1F542DA009"
0x180010de9  lea     rdx, COM_Problem; struct _EVENT_DESCRIPTOR *
0x180010df0  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x180010df5  mov     r9d, 2A3h
0x180010dfb  mov     [rsp+38h+var_10], ebx
0x180010dff  jmp     short loc_180010E54
0x180010e01  mov     rcx, [rsp+38h+arg_8]
0x180010e06  lea     rdx, [rsp+38h+arg_0]
0x180010e0b  mov     rax, [rcx]
0x180010e0e  mov     rax, [rax+38h]
0x180010e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e17  mov     ebx, eax
0x180010e19  test    eax, eax
0x180010e1b  jns     short loc_180010E25
0x180010e1d  mov     r9d, 2A8h
0x180010e23  jmp     short loc_180010E50
0x180010e25  mov     rcx, [rsp+38h+arg_8]
0x180010e2a  or      r9d, 0FFFFFFFFh
0x180010e2e  mov     edx, [rsp+38h+arg_0]
0x180010e32  mov     r8, rdi
0x180010e35  mov     rax, [rcx]
0x180010e38  mov     rax, [rax+0A0h]
0x180010e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e44  mov     ebx, eax
0x180010e46  test    eax, eax
0x180010e48  jns     short loc_180010E6C
0x180010e4a  mov     r9d, 2ACh; unsigned int
0x180010e50  mov     [rsp+38h+var_10], eax; unsigned int
0x180010e54  lea     rcx, aEnablerafirewa; "EnableRAFirewallGroup"
0x180010e5b  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180010e62  mov     [rsp+38h+ppv], rcx; unsigned __int16 *
0x180010e67  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180010e6c  mov     rcx, [rsp+38h+arg_8]
0x180010e71  test    rcx, rcx
0x180010e74  jz      short loc_180010E8B
0x180010e76  mov     rax, [rcx]
0x180010e79  mov     rax, [rax+10h]
0x180010e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e82  mov     [rsp+38h+arg_8], 0
0x180010e8b  test    rdi, rdi
0x180010e8e  jz      short loc_180010E99
0x180010e90  mov     rcx, rdi; bstrString
0x180010e93  call    cs:__imp_SysFreeString
0x180010e99  mov     eax, ebx
0x180010e9b  mov     rbx, [rsp+38h+arg_10]
0x180010ea0  add     rsp, 30h
0x180010ea4  pop     rdi
0x180010ea5  retn
```
