# ComposeErrorMessgeFromHRESULT(long)

- ea: `0x18001eef4`
- end: `0x18001ef8b`
- name: `?ComposeErrorMessgeFromHRESULT@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800056c0`
- `0x1800135d0`
- `0x1800152e8`
- `0x180016084`
- `0x180016cd4`
- `0x1800172cc`

## callees

- `0x180001910`
- `0x18000513c`
- `0x18000536c`
- `0x18001eef4`
- `0x18001f858`
- `0x18001fff4`
- `0x1800222d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ComposeErrorMessgeFromHRESULT(__int64 a1)
{
  __int64 v2; // r9
  __int64 SystemErrorMessage; // rax
  __int64 v4; // rdx
  _BYTE v6[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(a1);
  if ( (int)v2 < 0 )
  {
    if ( (v2 & 0x1FFF0000) == 0x70000 )
      SystemErrorMessage = GetSystemErrorMessage(v6, (unsigned __int16)v2);
    else
      SystemErrorMessage = FormatString(v6, 300, (unsigned int)v2, v2);
    std::wstring::operator=(a1, SystemErrorMessage);
    LOBYTE(v4) = 1;
    std::wstring::_Tidy(v6, v4, 0);
  }
  return a1;
}

```

## disassembly

```asm
0x18001eef4  push    rbx
0x18001eef6  sub     rsp, 60h
0x18001eefa  mov     rax, cs:__security_cookie
0x18001ef01  xor     rax, rsp
0x18001ef04  mov     [rsp+68h+var_18], rax
0x18001ef09  mov     r9d, edx
0x18001ef0c  mov     rbx, rcx
0x18001ef0f  mov     [rsp+68h+var_40], rcx
0x18001ef14  mov     [rsp+68h+var_48], 0
0x18001ef1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001ef21  mov     [rsp+68h+var_48], 1
0x18001ef29  test    r9d, r9d
0x18001ef2c  jns     short loc_18001EF74
0x18001ef2e  mov     eax, r9d
0x18001ef31  and     eax, 1FFF0000h
0x18001ef36  lea     rcx, [rsp+68h+var_38]
0x18001ef3b  cmp     eax, 70000h
0x18001ef40  jnz     short loc_18001EF4D
0x18001ef42  movzx   edx, r9w
0x18001ef46  call    ?GetSystemErrorMessage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; GetSystemErrorMessage(int)
0x18001ef4b  jmp     short loc_18001EF5A
0x18001ef4d  mov     r8d, r9d
0x18001ef50  mov     edx, 12Ch
0x18001ef55  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x18001ef5a  mov     rdx, rax
0x18001ef5d  mov     rcx, rbx
0x18001ef60  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001ef65  xor     r8d, r8d
0x18001ef68  mov     dl, 1
0x18001ef6a  lea     rcx, [rsp+68h+var_38]
0x18001ef6f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ef74  mov     rax, rbx
0x18001ef77  mov     rcx, [rsp+68h+var_18]
0x18001ef7c  xor     rcx, rsp; StackCookie
0x18001ef7f  call    __security_check_cookie
0x18001ef84  add     rsp, 60h
0x18001ef88  pop     rbx
0x18001ef89  retn
```
