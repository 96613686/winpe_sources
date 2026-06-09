# CSnapin::_UpdateDescriptionText(CLogInfo *)

- ea: `0x18001de94`
- end: `0x18001dfb9`
- name: `?_UpdateDescriptionText@CSnapin@@AEAAXPEAVCLogInfo@@@Z`
- size: `293`
- prototype: `void __fastcall(CSnapin *__hidden this, struct CLogInfo *)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18001d4cc`
- `0x18001d5c0`
- `0x18001daf4`

## callees

- `0x180001910`
- `0x18000513c`
- `0x18000536c`
- `0x18001de94`
- `0x18001f688`
- `0x18001f858`
- `0x1800222d0`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSnapin::_UpdateDescriptionText(CSnapin *this, struct CLogInfo *a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v7; // rdx
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  _QWORD *v10; // rdx
  __int64 v11; // rdx
  _QWORD v12[4]; // [rsp+20h] [rbp-39h] BYREF
  unsigned __int16 v13[16]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v14[32]; // [rsp+60h] [rbp+7h] BYREF
  unsigned __int16 v15[16]; // [rsp+80h] [rbp+27h] BYREF

  std::wstring::wstring(v12);
  FormatNumber(*((_DWORD *)this + 26), v15, 0xEu);
  if ( (*((_WORD *)a2 + 12) & 0x200) != 0 )
  {
    v6 = FormatString(v13, 288, v4, v5);
LABEL_3:
    std::wstring::operator=(v12, v6);
    v8 = v13;
    goto LABEL_7;
  }
  if ( (*((_BYTE *)a2 + 24) & 2) == 0 )
  {
    v6 = FormatString(v13, 290, v15, v5);
    goto LABEL_3;
  }
  FormatNumber(*((_DWORD *)this + 202), v13, 0xEu);
  v9 = FormatString(v14, 289, v15, v13);
  std::wstring::operator=(v12, v9);
  v8 = (unsigned __int16 *)v14;
LABEL_7:
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(v8, v7, 0);
  v10 = v12;
  if ( v12[3] >= 8u )
    v10 = (_QWORD *)v12[0];
  (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 203) + 128LL))(*((_QWORD *)this + 203), v10);
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v12, v11, 0);
}

```

## disassembly

```asm
0x18001de94  mov     [rsp-8+arg_8], rbx
0x18001de99  mov     [rsp-8+arg_10], rdi
0x18001de9e  push    rbp
0x18001de9f  lea     rbp, [rsp-57h]
0x18001dea4  sub     rsp, 0B0h
0x18001deab  mov     rax, cs:__security_cookie
0x18001deb2  xor     rax, rsp
0x18001deb5  mov     [rbp+57h+var_10], rax
0x18001deb9  mov     rbx, rdx
0x18001debc  mov     rdi, rcx
0x18001debf  lea     rcx, [rbp+57h+var_90]
0x18001dec3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001dec8  nop
0x18001dec9  mov     r8d, 0Eh; unsigned int
0x18001decf  lea     rdx, [rbp+57h+var_30]; unsigned __int16 *
0x18001ded3  mov     ecx, [rdi+68h]; unsigned int
0x18001ded6  call    ?FormatNumber@@YAIKPEAGK@Z; FormatNumber(ulong,ushort *,ulong)
0x18001dedb  mov     eax, 200h
0x18001dee0  test    [rbx+18h], ax
0x18001dee4  jz      short loc_18001DF06
0x18001dee6  mov     edx, 120h
0x18001deeb  lea     rcx, [rbp+57h+var_70]
0x18001deef  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x18001def4  mov     rdx, rax
0x18001def7  lea     rcx, [rbp+57h+var_90]
0x18001defb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001df00  lea     rcx, [rbp+57h+var_70]
0x18001df04  jmp     short loc_18001DF5B
0x18001df06  test    byte ptr [rbx+18h], 2
0x18001df0a  jnz     short loc_18001DF20
0x18001df0c  lea     r8, [rbp+57h+var_30]
0x18001df10  mov     edx, 122h
0x18001df15  lea     rcx, [rbp+57h+var_70]
0x18001df19  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x18001df1e  jmp     short loc_18001DEF4
0x18001df20  mov     r8d, 0Eh; unsigned int
0x18001df26  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18001df2a  mov     ecx, [rdi+328h]; unsigned int
0x18001df30  call    ?FormatNumber@@YAIKPEAGK@Z; FormatNumber(ulong,ushort *,ulong)
0x18001df35  lea     r9, [rbp+57h+var_70]
0x18001df39  lea     r8, [rbp+57h+var_30]
0x18001df3d  mov     edx, 121h
0x18001df42  lea     rcx, [rbp+57h+var_50]
0x18001df46  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x18001df4b  mov     rdx, rax
0x18001df4e  lea     rcx, [rbp+57h+var_90]
0x18001df52  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001df57  lea     rcx, [rbp+57h+var_50]
0x18001df5b  xor     r8d, r8d
0x18001df5e  mov     dl, 1
0x18001df60  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001df65  mov     rcx, [rdi+658h]
0x18001df6c  mov     rax, [rcx]
0x18001df6f  lea     rdx, [rbp+57h+var_90]
0x18001df73  cmp     [rbp+57h+var_78], 8
0x18001df78  cmovnb  rdx, [rbp+57h+var_90]
0x18001df7d  mov     rax, [rax+80h]
0x18001df84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df89  nop
0x18001df8a  xor     r8d, r8d
0x18001df8d  mov     dl, 1
0x18001df8f  lea     rcx, [rbp+57h+var_90]
0x18001df93  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001df98  mov     rcx, [rbp+57h+var_10]
0x18001df9c  xor     rcx, rsp; StackCookie
0x18001df9f  call    __security_check_cookie
0x18001dfa4  lea     r11, [rsp+0B0h+var_s0]
0x18001dfac  mov     rbx, [r11+18h]
0x18001dfb0  mov     rdi, [r11+20h]
0x18001dfb4  mov     rsp, r11
0x18001dfb7  pop     rbp
0x18001dfb8  retn
```
