# OpenPrimarySourceKey(ushort const *,ushort const *,ushort const *,CSafeReg *)

- ea: `0x18000e908`
- end: `0x18000ea2a`
- name: `?OpenPrimarySourceKey@@YA?AW4PSK@@PEBG00PEAVCSafeReg@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, __int64, CSafeReg *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000d814`
- `0x18000f09c`

## callees

- `0x180001910`
- `0x180001a70`
- `0x180001dd0`
- `0x1800028e0`
- `0x18000513c`
- `0x18000e908`
- `0x18001ae60`
- `0x1800222d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e94b`
- `msvcrt!_wcsicmp` at `0x18000e94b`

## string_xrefs

- `0x18000e95d`: `SYSTEM\CurrentControlSet\Services\EventLog`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OpenPrimarySourceKey(const wchar_t *a1, __int64 a2, __int64 a3, CSafeReg *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  const wchar_t *v9; // r9
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  const unsigned __int16 *v14; // r8
  unsigned __int16 *v16[4]; // [rsp+20h] [rbp-58h] BYREF

  v7 = 1;
  std::wstring::wstring(v16);
  if ( a1 )
  {
    if ( _wcsicmp(v9, a1) )
    {
      std::wstring::assign(v16, L"SYSTEM\\CurrentControlSet\\Services\\EventLog");
      v10 = std::char_traits<unsigned short>::length(L"\\");
      std::wstring::append(v16, L"\\", v10);
      v11 = std::char_traits<unsigned short>::length(a3);
      std::wstring::append(v16, a3, v11);
      v12 = std::char_traits<unsigned short>::length(L"\\");
      std::wstring::append(v16, L"\\", v12);
      v13 = std::char_traits<unsigned short>::length(a1);
      std::wstring::append(v16, a1, v13);
      v14 = (const unsigned __int16 *)v16;
      if ( v16[3] >= (unsigned __int16 *)8 )
        v14 = v16[0];
      v7 = (CSafeReg::Open(a4, HKEY_LOCAL_MACHINE, v14, 1u) >> 31) + 4;
    }
    else
    {
      v7 = 2;
    }
  }
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(v16, v8, 0);
  return v7;
}

```

## disassembly

```asm
0x18000e908  push    rbx
0x18000e90a  push    rbp
0x18000e90b  push    rsi
0x18000e90c  push    rdi
0x18000e90d  sub     rsp, 58h
0x18000e911  mov     rax, cs:__security_cookie
0x18000e918  xor     rax, rsp
0x18000e91b  mov     [rsp+78h+var_38], rax
0x18000e920  mov     rbp, r9
0x18000e923  mov     rsi, r8
0x18000e926  mov     r9, rdx
0x18000e929  mov     rdi, rcx
0x18000e92c  mov     ebx, 1
0x18000e931  lea     rcx, [rsp+78h+var_58]
0x18000e936  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e93b  nop
0x18000e93c  test    rdi, rdi
0x18000e93f  jz      loc_18000EA03
0x18000e945  mov     rdx, rdi; String2
0x18000e948  mov     rcx, r9; String1
0x18000e94b  call    cs:__imp__wcsicmp
0x18000e951  test    eax, eax
0x18000e953  jnz     short loc_18000E95D
0x18000e955  lea     ebx, [rax+2]
0x18000e958  jmp     loc_18000EA03
0x18000e95d  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x18000e964  lea     rcx, [rsp+78h+var_58]
0x18000e969  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e96e  lea     rbx, SubBlock; "\\"
0x18000e975  mov     rcx, rbx
0x18000e978  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000e97d  mov     r8, rax
0x18000e980  mov     rdx, rbx
0x18000e983  lea     rcx, [rsp+78h+var_58]
0x18000e988  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000e98d  mov     rcx, rsi
0x18000e990  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000e995  mov     r8, rax
0x18000e998  mov     rdx, rsi
0x18000e99b  lea     rcx, [rsp+78h+var_58]
0x18000e9a0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000e9a5  mov     rcx, rbx
0x18000e9a8  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000e9ad  mov     r8, rax
0x18000e9b0  mov     rdx, rbx
0x18000e9b3  lea     rcx, [rsp+78h+var_58]
0x18000e9b8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000e9bd  mov     rcx, rdi
0x18000e9c0  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000e9c5  mov     r8, rax
0x18000e9c8  mov     rdx, rdi
0x18000e9cb  lea     rcx, [rsp+78h+var_58]
0x18000e9d0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000e9d5  lea     r8, [rsp+78h+var_58]
0x18000e9da  cmp     [rsp+78h+var_40], 8
0x18000e9e0  cmovnb  r8, [rsp+78h+var_58]; unsigned __int16 *
0x18000e9e6  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000e9ed  mov     r9d, 1; unsigned int
0x18000e9f3  mov     rcx, rbp; this
0x18000e9f6  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x18000e9fb  mov     ebx, eax
0x18000e9fd  sar     ebx, 1Fh
0x18000ea00  add     ebx, 4
0x18000ea03  xor     r8d, r8d
0x18000ea06  mov     dl, 1
0x18000ea08  lea     rcx, [rsp+78h+var_58]
0x18000ea0d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ea12  mov     eax, ebx
0x18000ea14  mov     rcx, [rsp+78h+var_38]
0x18000ea19  xor     rcx, rsp; StackCookie
0x18000ea1c  call    __security_check_cookie
0x18000ea21  add     rsp, 58h
0x18000ea25  pop     rdi
0x18000ea26  pop     rsi
0x18000ea27  pop     rbp
0x18000ea28  pop     rbx
0x18000ea29  retn
```
