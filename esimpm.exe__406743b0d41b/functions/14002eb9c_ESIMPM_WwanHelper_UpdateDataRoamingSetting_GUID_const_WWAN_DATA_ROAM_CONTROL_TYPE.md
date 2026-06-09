# ESIMPM::WwanHelper::UpdateDataRoamingSetting(_GUID const &,WWAN_DATA_ROAM_CONTROL_TYPE)

- ea: `0x14002eb9c`
- end: `0x14002ec58`
- name: `?UpdateDataRoamingSetting@WwanHelper@ESIMPM@@QEAAKAEBU_GUID@@W4WWAN_DATA_ROAM_CONTROL_TYPE@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(__int64 *, const struct _GUID *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14002bc98`
- `0x14002cfb4`

## callees

- `0x140002f60`
- `0x140014f64`
- `0x140020620`
- `0x14002eb9c`

## import_xrefs

- `wwapi!WwanSetInterface` at `0x14002ec0a`
- `wwapi!WwanSetInterface` at `0x14002ec0a`

## string_xrefs

- `0x14002ec13`: `ESIMPM::WwanHelper::UpdateDataRoamingSetting`

## pseudocode

```c
__int64 __fastcall ESIMPM::WwanHelper::UpdateDataRoamingSetting(__int64 *a1, const struct _GUID *a2, unsigned int a3)
{
  __int64 v3; // rcx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  __int128 *v9; // [rsp+20h] [rbp-68h]
  int v10; // [rsp+40h] [rbp-48h] BYREF
  int v11; // [rsp+44h] [rbp-44h] BYREF
  __int128 v12; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v13; // [rsp+58h] [rbp-30h]

  v3 = *a1;
  v13 = a3;
  v11 = 0;
  v9 = &v12;
  v12 = WWAN_PROFILE_SET_GUID_INTERNET_AO;
  v10 = 0;
  v6 = WwanSetInterface(v3, a2, 16);
  v7 = v6;
  if ( v6 )
  {
    LODWORD(v9) = v6;
    ESIMPM::Log::Error(
      "ESIMPM::WwanHelper::UpdateDataRoamingSetting",
      a2,
      L"DataRoamControl %d failed to set (RetCode 0x%x)",
      a3,
      v9,
      &v11,
      &v10,
      0);
  }
  else
  {
    ESIMPM::Log::Info(
      "ESIMPM::WwanHelper::UpdateDataRoamingSetting",
      a2,
      L"DataRoamControl %d is successfully changed",
      a3,
      &v12,
      &v11,
      &v10,
      0);
  }
  return v7;
}

```

## disassembly

```asm
0x14002eb9c  mov     r11, rsp
0x14002eb9f  push    rbx
0x14002eba0  push    rsi
0x14002eba1  push    rdi
0x14002eba2  sub     rsp, 70h
0x14002eba6  mov     rax, cs:__security_cookie
0x14002ebad  xor     rax, rsp
0x14002ebb0  mov     [rsp+88h+var_28], rax
0x14002ebb5  movups  xmm0, cs:WWAN_PROFILE_SET_GUID_INTERNET_AO
0x14002ebbc  mov     rcx, [rcx]
0x14002ebbf  lea     rax, [r11-48h]
0x14002ebc3  mov     qword ptr [r11-50h], 0
0x14002ebcb  mov     r9d, 14h
0x14002ebd1  mov     [r11-58h], rax
0x14002ebd5  mov     esi, r8d
0x14002ebd8  lea     rax, [r11-44h]
0x14002ebdc  mov     [rsp+88h+var_30], r8d
0x14002ebe1  mov     [r11-60h], rax
0x14002ebe5  mov     rdi, rdx
0x14002ebe8  lea     rax, [r11-40h]
0x14002ebec  mov     [rsp+88h+var_44], 0
0x14002ebf4  lea     r8d, [r9-4]
0x14002ebf8  mov     [r11-68h], rax
0x14002ebfc  movdqu  [rsp+88h+var_40], xmm0
0x14002ec02  mov     [rsp+88h+var_48], 0
0x14002ec0a  call    cs:__imp_WwanSetInterface
0x14002ec10  mov     r9d, esi
0x14002ec13  lea     rcx, aEsimpmWwanhelp_11; "ESIMPM::WwanHelper::UpdateDataRoamingSe"...
0x14002ec1a  mov     ebx, eax
0x14002ec1c  mov     rdx, rdi; struct _GUID *
0x14002ec1f  test    eax, eax
0x14002ec21  jnz     short loc_14002EC31
0x14002ec23  lea     r8, aDataroamcontro_0; "DataRoamControl %d is successfully chan"...
0x14002ec2a  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002ec2f  jmp     short loc_14002EC41
0x14002ec31  lea     r8, aDataroamcontro; "DataRoamControl %d failed to set (RetCo"...
0x14002ec38  mov     [rsp+88h+var_68], ebx
0x14002ec3c  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14002ec41  mov     eax, ebx
0x14002ec43  mov     rcx, [rsp+88h+var_28]
0x14002ec48  xor     rcx, rsp; StackCookie
0x14002ec4b  call    __security_check_cookie
0x14002ec50  add     rsp, 70h
0x14002ec54  pop     rdi
0x14002ec55  pop     rsi
0x14002ec56  pop     rbx
0x14002ec57  retn
```
