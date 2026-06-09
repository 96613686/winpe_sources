# CPacketReceiver::LoadConfiguration(void)

- ea: `0x180014e98`
- end: `0x180014f80`
- name: `?LoadConfiguration@CPacketReceiver@@AEAAJXZ`
- size: `232`
- prototype: `__int64 __fastcall(CPacketReceiver *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000d3b0`
- `0x180014d54`

## callees

- `0x180014740`
- `0x180014e98`
- `0x1800160b4`
- `0x18001d31c`
- `0x18002c000`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180014eab`
- `OLEAUT32!__imp_VariantInit` at `0x180014eab`

## string_xrefs

- `0x180014f33`: `SYSTEM\CurrentControlSet\Services\EapHost\Configuration`
- `0x180014f3d`: `GetRegistryValue(%S\%S) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPacketReceiver::LoadConfiguration(CPacketReceiver *this)
{
  BOOL v2; // edi
  const OLECHAR **v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int RegistryValue; // eax
  char v8; // bl
  unsigned int v9; // edi
  VARIANTARG pvarg; // [rsp+40h] [rbp-48h] BYREF

  v2 = 0;
  VariantInit(&pvarg);
  RegistryValue = GetRegistryValue(v4, v3, v5, v6, &pvarg);
  v8 = RegistryValue;
  if ( !RegistryValue )
  {
    v2 = pvarg.lVal == 1;
LABEL_3:
    *((_DWORD *)this + 42) = v2;
    v9 = 0;
    goto LABEL_4;
  }
  if ( RegistryValue == 2 )
    goto LABEL_3;
  if ( RegistryValue > 0 )
    v9 = (unsigned __int16)RegistryValue | 0x80070000;
  else
    v9 = RegistryValue;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("GetRegistryValue(%S\\%S) failed with 0x%x");
    WPP_SF_sSSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)L"SYSTEM\\CurrentControlSet\\Services\\EapHost\\Configuration",
      (__int64)L"REG_DWORD",
      v8);
  }
LABEL_4:
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  return v9;
}

```

## disassembly

```asm
0x180014e98  push    rbx
0x180014e9a  push    rbp
0x180014e9b  push    rsi
0x180014e9c  push    rdi
0x180014e9d  sub     rsp, 68h
0x180014ea1  mov     rsi, rcx
0x180014ea4  xor     edi, edi
0x180014ea6  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180014eab  call    cs:__imp_VariantInit
0x180014eb1  nop
0x180014eb2  lea     rax, [rsp+88h+pvarg]
0x180014eb7  mov     [rsp+88h+var_68], rax; pvarg
0x180014ebc  call    GetRegistryValue
0x180014ec1  mov     ebx, eax
0x180014ec3  test    eax, eax
0x180014ec5  jnz     short loc_180014EEE
0x180014ec7  cmp     dword ptr [rsp+88h+pvarg+8], 1
0x180014ecc  jnz     short loc_180014ED1
0x180014ece  lea     edi, [rax+1]
0x180014ed1  mov     [rsi+0A8h], edi
0x180014ed7  xor     edi, edi
0x180014ed9  lea     rcx, [rsp+88h+pvarg]; this
0x180014ede  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180014ee3  mov     eax, edi
0x180014ee5  add     rsp, 68h
0x180014ee9  pop     rdi
0x180014eea  pop     rsi
0x180014eeb  pop     rbp
0x180014eec  pop     rbx
0x180014eed  retn
0x180014eee  cmp     ebx, 2
0x180014ef1  jz      short loc_180014ED1
0x180014ef3  test    ebx, ebx
0x180014ef5  jg      short loc_180014EFB
0x180014ef7  mov     edi, ebx
0x180014ef9  jmp     short loc_180014F04
0x180014efb  movzx   edi, bx
0x180014efe  or      edi, 80070000h
0x180014f04  lea     rcx, WPP_GLOBAL_Control
0x180014f0b  mov     rax, cs:WPP_GLOBAL_Control
0x180014f12  cmp     rax, rcx
0x180014f15  jz      short loc_180014ED9
0x180014f17  cmp     byte ptr [rax+19h], 2
0x180014f1b  jb      short loc_180014ED9
0x180014f1d  test    dword ptr [rax+1Ch], 100h
0x180014f24  jz      short loc_180014ED9
0x180014f26  mov     r9d, ebx
0x180014f29  lea     rsi, String1; "REG_DWORD"
0x180014f30  mov     r8, rsi
0x180014f33  lea     rbp, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x180014f3a  mov     rdx, rbp
0x180014f3d  lea     rcx, aGetregistryval; "GetRegistryValue(%S\\%S) failed with 0x"...
0x180014f44  call    WppDbgPrint
0x180014f49  mov     edx, 0Bh
0x180014f4e  mov     dword ptr [rsp+88h+var_58], ebx; char
0x180014f52  mov     [rsp+88h+var_60], rsi; __int64
0x180014f57  mov     [rsp+88h+var_68], rbp; __int64
0x180014f5c  lea     r9, aNpsrad; "NPSRAD"
0x180014f63  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180014f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f71  mov     rcx, [rcx+10h]; LoggerHandle
0x180014f75  call    WPP_SF_sSSD
0x180014f7a  jmp     loc_180014ED9
```
