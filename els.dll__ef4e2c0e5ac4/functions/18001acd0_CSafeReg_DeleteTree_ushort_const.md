# CSafeReg::DeleteTree(ushort const *)

- ea: `0x18001acd0`
- end: `0x18001adb8`
- name: `?DeleteTree@CSafeReg@@QEAAJPEBG@Z`
- size: `232`
- prototype: `__int64 __fastcall(CSafeReg *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018dd0`
- `0x18001acd0`

## callees

- `0x18001abd8`
- `0x18001acd0`
- `0x18001adf4`
- `0x18001ae60`
- `0x1800222d0`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x18001ad78`
- `ADVAPI32!RegDeleteKeyW` at `0x18001ad78`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSafeReg::DeleteTree(HKEY *this, const unsigned __int16 *a2)
{
  int v4; // ebx
  LSTATUS v5; // eax
  _QWORD v7[2]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF

  while ( 1 )
  {
    v7[0] = 0;
    v4 = CSafeReg::Open((CSafeReg *)v7, *this, a2, 0x2000Eu);
    if ( v4 < 0 )
      break;
    v4 = CSafeReg::Enum((CSafeReg *)v7, 0, SubKey, 0x104u);
    if ( v4 )
      break;
    v4 = CSafeReg::DeleteTree((CSafeReg *)v7, SubKey);
    if ( v4 < 0 )
      break;
    CSafeReg::Close((CSafeReg *)v7);
    CSafeReg::Close((CSafeReg *)v7);
  }
  CSafeReg::Close((CSafeReg *)v7);
  v5 = RegDeleteKeyW(*this, a2);
  if ( v5 )
  {
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
    else
      return (unsigned int)v5;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001acd0  mov     [rsp+arg_10], rbx
0x18001acd5  mov     [rsp+arg_18], rsi
0x18001acda  push    rdi
0x18001acdb  sub     rsp, 250h
0x18001ace2  mov     rax, cs:__security_cookie
0x18001ace9  xor     rax, rsp
0x18001acec  mov     [rsp+258h+var_18], rax
0x18001acf4  mov     rsi, rdx
0x18001acf7  mov     rdi, rcx
0x18001acfa  mov     [rsp+258h+var_238], 0
0x18001ad03  mov     r9d, 2000Eh; unsigned int
0x18001ad09  mov     r8, rsi; unsigned __int16 *
0x18001ad0c  mov     rdx, [rdi]; HKEY
0x18001ad0f  lea     rcx, [rsp+258h+var_238]; this
0x18001ad14  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x18001ad19  mov     ebx, eax
0x18001ad1b  test    eax, eax
0x18001ad1d  js      short loc_18001AD68
0x18001ad1f  mov     r9d, 104h; unsigned int
0x18001ad25  lea     r8, [rsp+258h+SubKey]; unsigned __int16 *
0x18001ad2a  xor     edx, edx; unsigned int
0x18001ad2c  lea     rcx, [rsp+258h+var_238]; this
0x18001ad31  call    ?Enum@CSafeReg@@QEBAJKPEAGK@Z; CSafeReg::Enum(ulong,ushort *,ulong)
0x18001ad36  mov     ebx, eax
0x18001ad38  test    eax, eax
0x18001ad3a  jnz     short loc_18001AD68
0x18001ad3c  lea     rdx, [rsp+258h+SubKey]; unsigned __int16 *
0x18001ad41  lea     rcx, [rsp+258h+var_238]; this
0x18001ad46  call    ?DeleteTree@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteTree(ushort const *)
0x18001ad4b  mov     ebx, eax
0x18001ad4d  test    eax, eax
0x18001ad4f  js      short loc_18001AD68
0x18001ad51  lea     rcx, [rsp+258h+var_238]; this
0x18001ad56  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001ad5b  nop
0x18001ad5c  lea     rcx, [rsp+258h+var_238]; this
0x18001ad61  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001ad66  jmp     short loc_18001ACFA
0x18001ad68  lea     rcx, [rsp+258h+var_238]; this
0x18001ad6d  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001ad72  mov     rdx, rsi; lpSubKey
0x18001ad75  mov     rcx, [rdi]; hKey
0x18001ad78  call    cs:__imp_RegDeleteKeyW
0x18001ad7e  test    eax, eax
0x18001ad80  jz      short loc_18001AD91
0x18001ad82  jg      short loc_18001AD88
0x18001ad84  mov     ebx, eax
0x18001ad86  jmp     short loc_18001AD91
0x18001ad88  movzx   ebx, ax
0x18001ad8b  or      ebx, 80070000h
0x18001ad91  mov     eax, ebx
0x18001ad93  mov     rcx, [rsp+258h+var_18]
0x18001ad9b  xor     rcx, rsp; StackCookie
0x18001ad9e  call    __security_check_cookie
0x18001ada3  lea     r11, [rsp+258h+var_8]
0x18001adab  mov     rbx, [r11+20h]
0x18001adaf  mov     rsi, [r11+28h]
0x18001adb3  mov     rsp, r11
0x18001adb6  pop     rdi
0x18001adb7  retn
```
