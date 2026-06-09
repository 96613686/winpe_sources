# EapUseLegacyTlsStackInternal

- ea: `0x180008db0`
- end: `0x180008e42`
- name: `EapUseLegacyTlsStackInternal`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180007ea0`

## callees

- `0x180008d90`
- `0x180008db0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008e02`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008e02`

## string_xrefs

- `0x180008df4`: `SYSTEM\CurrentControlSet\Services\EapHost`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 EapUseLegacyTlsStackInternal()
{
  unsigned int ValueW; // eax
  __int64 result; // rax
  const char *v2; // r9
  unsigned int v3; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v5; // [rsp+50h] [rbp+8h] BYREF
  DWORD v6; // [rsp+58h] [rbp+10h] BYREF
  __int64 v7; // [rsp+60h] [rbp+18h]

  v7 = 0;
  v5 = 0;
  v6 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\EapHost",
             L"UseLegacyTlsStack",
             0x10u,
             0,
             &v5,
             &v6);
  if ( ValueW == 2 )
    return 0;
  if ( ValueW )
  {
    try
    {
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapuselegacytlsstack.cpp",
        (const char *)ValueW,
        v3);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapuselegacytlsstack.cpp",
        v2);
      return 0;
    }
  }
  result = 1;
  if ( v5 != 1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180008db0  mov     r11, rsp
0x180008db3  sub     rsp, 48h
0x180008db7  mov     qword ptr [r11+18h], 0
0x180008dbf  mov     [rsp+48h+arg_0], 0
0x180008dc7  mov     [rsp+48h+arg_8], 4
0x180008dcf  lea     rax, [r11+10h]
0x180008dd3  mov     [r11-18h], rax
0x180008dd7  lea     rax, [r11+8]
0x180008ddb  mov     [r11-20h], rax
0x180008ddf  mov     qword ptr [r11-28h], 0
0x180008de7  mov     r9d, 10h; dwFlags
0x180008ded  lea     r8, Value; "UseLegacyTlsStack"
0x180008df4  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x180008dfb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008e02  call    cs:__imp_RegGetValueW
0x180008e08  cmp     eax, 2
0x180008e0b  jnz     short loc_180008E11
0x180008e0d  xor     eax, eax
0x180008e0f  jmp     short loc_180008E27
0x180008e11  mov     rcx, [rsp+48h]; this
0x180008e16  test    eax, eax
0x180008e18  jnz     short loc_180008E2C
0x180008e1a  mov     eax, 1
0x180008e1f  cmp     [rsp+48h+arg_0], eax
0x180008e23  jz      short loc_180008E27
0x180008e25  xor     eax, eax
0x180008e27  add     rsp, 48h
0x180008e2b  retn
0x180008e2c  mov     r9d, eax; char *
0x180008e2f  lea     r8, aOnecoreuapNetE_6; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180008e36  mov     edx, 1Eh; void *
0x180008e3b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
