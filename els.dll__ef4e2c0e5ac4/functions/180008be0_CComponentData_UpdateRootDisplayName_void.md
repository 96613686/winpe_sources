# CComponentData::_UpdateRootDisplayName(void)

- ea: `0x180008be0`
- end: `0x180008d15`
- name: `?_UpdateRootDisplayName@CComponentData@@AEAAXXZ`
- size: `309`
- prototype: `void __fastcall(CComponentData *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800056c0`
- `0x1800065d0`

## callees

- `0x180001910`
- `0x18000513c`
- `0x18000536c`
- `0x180005f64`
- `0x180008be0`
- `0x18001f858`
- `0x18001f960`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180008c4b`
- `msvcrt!_wcsicmp` at `0x180008c4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CComponentData::_UpdateRootDisplayName(CComponentData *this)
{
  const wchar_t *CurrentFocus; // rbx
  const wchar_t *v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  _OWORD v11[3]; // [rsp+20h] [rbp-49h] BYREF
  __int64 v12; // [rsp+50h] [rbp-19h]
  wchar_t *String2[3]; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int64 v14; // [rsp+70h] [rbp+7h]
  _QWORD v15[4]; // [rsp+78h] [rbp+Fh] BYREF
  _BYTE v16[32]; // [rsp+98h] [rbp+2Fh] BYREF

  std::wstring::wstring(v15);
  CurrentFocus = CComponentData::GetCurrentFocus(this);
  GetComputerNameAsString((__int64)String2);
  if ( !CurrentFocus )
  {
    CurrentFocus = (const wchar_t *)String2;
    if ( v14 >= 8 )
      CurrentFocus = String2[0];
  }
  v3 = (const wchar_t *)String2;
  if ( v14 >= 8 )
    v3 = String2[0];
  if ( _wcsicmp(CurrentFocus, v3) )
    v6 = FormatString(v16, 124, CurrentFocus, v5);
  else
    v6 = FormatString(v16, 297, v4, v5);
  std::wstring::operator=(v15, v6);
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(v16, v7, 0);
  memset(v11, 0, sizeof(v11));
  LODWORD(v11[0]) = 2;
  v8 = v15;
  if ( v15[3] >= 8u )
    v8 = (_QWORD *)v15[0];
  *((_QWORD *)&v11[0] + 1) = v8;
  v12 = *((_QWORD *)this + 142);
  (*(void (__fastcall **)(_QWORD, _OWORD *))(**((_QWORD **)this + 145) + 40LL))(*((_QWORD *)this + 145), v11);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(String2, v9, 0);
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v15, v10, 0);
}

```

## disassembly

```asm
0x180008be0  mov     [rsp-8+arg_8], rbx
0x180008be5  mov     [rsp-8+arg_10], rdi
0x180008bea  push    rbp
0x180008beb  lea     rbp, [rsp-57h]
0x180008bf0  sub     rsp, 0C0h
0x180008bf7  mov     rax, cs:__security_cookie
0x180008bfe  xor     rax, rsp
0x180008c01  mov     [rbp+57h+var_8], rax
0x180008c05  mov     rdi, rcx
0x180008c08  lea     rcx, [rbp+57h+var_48]
0x180008c0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180008c11  nop
0x180008c12  mov     rcx, rdi; this
0x180008c15  call    ?GetCurrentFocus@CComponentData@@QEAAPEBGXZ; CComponentData::GetCurrentFocus(void)
0x180008c1a  mov     rbx, rax
0x180008c1d  lea     rcx, [rbp+57h+String2]
0x180008c21  call    ?GetComputerNameAsString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetComputerNameAsString(void)
0x180008c26  nop
0x180008c27  test    rbx, rbx
0x180008c2a  jnz     short loc_180008C3A
0x180008c2c  lea     rbx, [rbp+57h+String2]
0x180008c30  cmp     [rbp+57h+var_50], 8
0x180008c35  cmovnb  rbx, [rbp+57h+String2]
0x180008c3a  lea     rdx, [rbp+57h+String2]
0x180008c3e  cmp     [rbp+57h+var_50], 8
0x180008c43  cmovnb  rdx, [rbp+57h+String2]; String2
0x180008c48  mov     rcx, rbx; String1
0x180008c4b  call    cs:__imp__wcsicmp
0x180008c51  lea     rcx, [rbp+57h+var_28]
0x180008c55  test    eax, eax
0x180008c57  jnz     short loc_180008C65
0x180008c59  mov     edx, 129h
0x180008c5e  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x180008c63  jmp     short loc_180008C72
0x180008c65  mov     r8, rbx
0x180008c68  mov     edx, 7Ch ; '|'
0x180008c6d  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x180008c72  mov     rdx, rax
0x180008c75  lea     rcx, [rbp+57h+var_48]
0x180008c79  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180008c7e  xor     r8d, r8d
0x180008c81  mov     dl, 1
0x180008c83  lea     rcx, [rbp+57h+var_28]
0x180008c87  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180008c8c  xorps   xmm0, xmm0
0x180008c8f  movups  [rbp+57h+var_A0], xmm0
0x180008c93  movups  [rbp+57h+var_90], xmm0
0x180008c97  movups  [rbp+57h+var_80], xmm0
0x180008c9b  mov     dword ptr [rbp+57h+var_A0], 2
0x180008ca2  lea     rax, [rbp+57h+var_48]
0x180008ca6  cmp     [rbp+57h+var_30], 8
0x180008cab  cmovnb  rax, [rbp+57h+var_48]
0x180008cb0  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180008cb4  mov     rax, [rdi+470h]
0x180008cbb  mov     [rbp+57h+var_70], rax
0x180008cbf  mov     rcx, [rdi+488h]
0x180008cc6  mov     rax, [rcx]
0x180008cc9  lea     rdx, [rbp+57h+var_A0]
0x180008ccd  mov     rax, [rax+28h]
0x180008cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cd6  nop
0x180008cd7  xor     r8d, r8d
0x180008cda  mov     dl, 1
0x180008cdc  lea     rcx, [rbp+57h+String2]
0x180008ce0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180008ce5  nop
0x180008ce6  xor     r8d, r8d
0x180008ce9  mov     dl, 1
0x180008ceb  lea     rcx, [rbp+57h+var_48]
0x180008cef  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180008cf4  mov     rcx, [rbp+57h+var_8]
0x180008cf8  xor     rcx, rsp; StackCookie
0x180008cfb  call    __security_check_cookie
0x180008d00  lea     r11, [rsp+0C0h+var_s0]
0x180008d08  mov     rbx, [r11+18h]
0x180008d0c  mov     rdi, [r11+20h]
0x180008d10  mov     rsp, r11
0x180008d13  pop     rbp
0x180008d14  retn
```
