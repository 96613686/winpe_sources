# ESIMPM::WwanHelper::UpdateAutoConnectSetting(_GUID const &,bool)

- ea: `0x14002eaf8`
- end: `0x14002eb95`
- name: `?UpdateAutoConnectSetting@WwanHelper@ESIMPM@@QEAAKAEBU_GUID@@_N@Z`
- size: `157`
- prototype: `__int64 __fastcall(ESIMPM::WwanHelper *this, const struct _GUID *, unsigned __int8)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14002aa1c`
- `0x14002acf8`
- `0x14002cfb4`

## callees

- `0x140014f64`
- `0x140020620`
- `0x14002eaf8`

## import_xrefs

- `wwapi!WwanSetInterface` at `0x14002eb4f`
- `wwapi!WwanSetInterface` at `0x14002eb4f`

## string_xrefs

- `0x14002eb5a`: `ESIMPM::WwanHelper::UpdateAutoConnectSetting`

## pseudocode

```c
__int64 __fastcall ESIMPM::WwanHelper::UpdateAutoConnectSetting(
        ESIMPM::WwanHelper *this,
        const struct _GUID *a2,
        unsigned __int8 a3)
{
  __int64 v3; // rcx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int *v8; // [rsp+20h] [rbp-28h]
  unsigned int v9; // [rsp+60h] [rbp+18h] BYREF
  int v10; // [rsp+68h] [rbp+20h]

  v3 = *(_QWORD *)this;
  v9 = a3 ^ 1;
  v10 = 0;
  v8 = &v9;
  v5 = WwanSetInterface(v3, a2, 39);
  v6 = v5;
  if ( v5 )
  {
    LODWORD(v8) = v5;
    ESIMPM::Log::Error(
      "ESIMPM::WwanHelper::UpdateAutoConnectSetting",
      a2,
      L"DisallowAutoConnect %d failed to set (RetCode 0x%x)",
      v9,
      v8);
  }
  else
  {
    ESIMPM::Log::Info(
      "ESIMPM::WwanHelper::UpdateAutoConnectSetting",
      a2,
      L"DisallowAutoConnect %d is successfully changed",
      v9);
  }
  return v6;
}

```

## disassembly

```asm
0x14002eaf8  mov     r11, rsp
0x14002eafb  mov     [r11+10h], rbx
0x14002eaff  push    rdi
0x14002eb00  sub     rsp, 40h
0x14002eb04  mov     rcx, [rcx]
0x14002eb07  mov     r9d, 4
0x14002eb0d  movzx   eax, r8b
0x14002eb11  mov     rdi, rdx
0x14002eb14  xor     eax, 1
0x14002eb17  mov     qword ptr [r11-10h], 0
0x14002eb1f  mov     [rsp+48h+arg_10], eax
0x14002eb23  lea     rax, [r11+8]
0x14002eb27  mov     [r11-18h], rax
0x14002eb2b  lea     r8d, [r9+23h]
0x14002eb2f  lea     rax, [r11+20h]
0x14002eb33  mov     [rsp+48h+arg_18], 0
0x14002eb3b  mov     [r11-20h], rax
0x14002eb3f  lea     rax, [r11+18h]
0x14002eb43  mov     [r11-28h], rax
0x14002eb47  mov     [rsp+48h+arg_0], 0
0x14002eb4f  call    cs:__imp_WwanSetInterface
0x14002eb55  mov     r9d, [rsp+48h+arg_10]
0x14002eb5a  lea     rcx, aEsimpmWwanhelp_8; "ESIMPM::WwanHelper::UpdateAutoConnectSe"...
0x14002eb61  mov     ebx, eax
0x14002eb63  mov     rdx, rdi; struct _GUID *
0x14002eb66  test    eax, eax
0x14002eb68  jnz     short loc_14002EB78
0x14002eb6a  lea     r8, aDisallowautoco; "DisallowAutoConnect %d is successfully "...
0x14002eb71  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002eb76  jmp     short loc_14002EB88
0x14002eb78  lea     r8, aDisallowautoco_0; "DisallowAutoConnect %d failed to set (R"...
0x14002eb7f  mov     [rsp+48h+var_28], ebx
0x14002eb83  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14002eb88  mov     eax, ebx
0x14002eb8a  mov     rbx, [rsp+48h+arg_8]
0x14002eb8f  add     rsp, 40h
0x14002eb93  pop     rdi
0x14002eb94  retn
```
