# CRecvFromPipe::LoadConfiguration(void)

- ea: `0x1800178b8`
- end: `0x18001799d`
- name: `?LoadConfiguration@CRecvFromPipe@@AEAAJXZ`
- size: `229`
- prototype: `__int64 __fastcall(CRecvFromPipe *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000b560`
- `0x18000d3b0`

## callees

- `0x180014740`
- `0x1800160b4`
- `0x1800178b8`
- `0x18001d31c`
- `0x18002c000`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800178cb`
- `OLEAUT32!__imp_VariantInit` at `0x1800178cb`

## string_xrefs

- `0x180017950`: `SYSTEM\CurrentControlSet\Services\EapHost\Configuration`
- `0x18001795a`: `GetRegistryValue(%S\%S) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecvFromPipe::LoadConfiguration(CRecvFromPipe *this)
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
    *((_DWORD *)this + 2) = v2;
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
0x1800178b8  push    rbx
0x1800178ba  push    rbp
0x1800178bb  push    rsi
0x1800178bc  push    rdi
0x1800178bd  sub     rsp, 68h
0x1800178c1  mov     rsi, rcx
0x1800178c4  xor     edi, edi
0x1800178c6  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1800178cb  call    cs:__imp_VariantInit
0x1800178d1  nop
0x1800178d2  lea     rax, [rsp+88h+pvarg]
0x1800178d7  mov     [rsp+88h+var_68], rax; pvarg
0x1800178dc  call    GetRegistryValue
0x1800178e1  mov     ebx, eax
0x1800178e3  test    eax, eax
0x1800178e5  jnz     short loc_18001790B
0x1800178e7  cmp     dword ptr [rsp+88h+pvarg+8], 1
0x1800178ec  jnz     short loc_1800178F1
0x1800178ee  lea     edi, [rax+1]
0x1800178f1  mov     [rsi+8], edi
0x1800178f4  xor     edi, edi
0x1800178f6  lea     rcx, [rsp+88h+pvarg]; this
0x1800178fb  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180017900  mov     eax, edi
0x180017902  add     rsp, 68h
0x180017906  pop     rdi
0x180017907  pop     rsi
0x180017908  pop     rbp
0x180017909  pop     rbx
0x18001790a  retn
0x18001790b  cmp     ebx, 2
0x18001790e  jz      short loc_1800178F1
0x180017910  test    ebx, ebx
0x180017912  jg      short loc_180017918
0x180017914  mov     edi, ebx
0x180017916  jmp     short loc_180017921
0x180017918  movzx   edi, bx
0x18001791b  or      edi, 80070000h
0x180017921  lea     rcx, WPP_GLOBAL_Control
0x180017928  mov     rax, cs:WPP_GLOBAL_Control
0x18001792f  cmp     rax, rcx
0x180017932  jz      short loc_1800178F6
0x180017934  cmp     byte ptr [rax+19h], 2
0x180017938  jb      short loc_1800178F6
0x18001793a  test    dword ptr [rax+1Ch], 100h
0x180017941  jz      short loc_1800178F6
0x180017943  mov     r9d, ebx
0x180017946  lea     rsi, String1; "REG_DWORD"
0x18001794d  mov     r8, rsi
0x180017950  lea     rbp, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x180017957  mov     rdx, rbp
0x18001795a  lea     rcx, aGetregistryval; "GetRegistryValue(%S\\%S) failed with 0x"...
0x180017961  call    WppDbgPrint
0x180017966  mov     edx, 0Ah
0x18001796b  mov     dword ptr [rsp+88h+var_58], ebx; char
0x18001796f  mov     [rsp+88h+var_60], rsi; __int64
0x180017974  mov     [rsp+88h+var_68], rbp; __int64
0x180017979  lea     r9, aNpsrad; "NPSRAD"
0x180017980  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180017987  mov     rcx, cs:WPP_GLOBAL_Control
0x18001798e  mov     rcx, [rcx+10h]; LoggerHandle
0x180017992  call    WPP_SF_sSSD
0x180017997  jmp     loc_1800178F6
```
