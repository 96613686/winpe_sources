# DiagnosticsClient::AddRootCause(ushort const *)

- ea: `0x1800059c0`
- end: `0x180005a90`
- name: `?AddRootCause@DiagnosticsClient@@UEAAJPEBG@Z`
- size: `208`
- prototype: `__int64 __fastcall(DiagnosticsClient *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056bc`
- `0x1800059c0`
- `0x18002b928`
- `0x18002ba00`
- `0x18002bc48`
- `0x18002c2fc`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180005a3a`
- `msvcrt!wcsnlen` at `0x180005a3a`
- `wdi!WdiAddParameter` at `0x180005a62`
- `wdi!WdiAddParameter` at `0x180005a62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a6d`

## pseudocode

```c
__int64 __fastcall DiagnosticsClient::AddRootCause(DiagnosticsClient *this, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rbx
  unsigned __int16 *v5; // rdi
  int ReplacedText; // eax
  size_t v7; // rax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  char v10; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int16 *v11; // [rsp+50h] [rbp+18h] BYREF

  v2 = a2;
  if ( !a2 )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 1) )
    return 2147942406LL;
  v5 = 0;
  v11 = 0;
  DiagnosisTextParser::DiagnosisTextParser((DiagnosisTextParser *)&v10);
  if ( !(unsigned int)DiagnosisTextParser::SetXML((DiagnosisTextParser *)&v10, v2) )
  {
    ReplacedText = DiagnosisTextParser::GetReplacedText((DiagnosisTextParser *)&v10, &v11);
    v5 = v11;
    if ( ReplacedText >= 0 )
      v2 = v11;
  }
  v7 = wcsnlen(v2, 0x400u);
  v8 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(2 * v7 + 2);
  v9 = WdiAddParameter(*((_QWORD *)this + 1), 0, L"NDFRootCause", v8, v2);
  CoTaskMemFree(v5);
  DiagnosisTextParser::~DiagnosisTextParser((DiagnosisTextParser *)&v10);
  return v9;
}

```

## disassembly

```asm
0x1800059c0  mov     [rsp+arg_0], rbx
0x1800059c5  mov     [rsp+arg_18], rsi
0x1800059ca  push    rdi
0x1800059cb  sub     rsp, 30h
0x1800059cf  mov     rbx, rdx
0x1800059d2  mov     rsi, rcx
0x1800059d5  test    rdx, rdx
0x1800059d8  jnz     short loc_1800059E4
0x1800059da  mov     eax, 80070057h
0x1800059df  jmp     loc_180005A80
0x1800059e4  cmp     qword ptr [rcx+8], 0
0x1800059e9  jnz     short loc_1800059F5
0x1800059eb  mov     eax, 80070006h
0x1800059f0  jmp     loc_180005A80
0x1800059f5  xor     edi, edi
0x1800059f7  mov     [rsp+38h+arg_10], rdi
0x1800059fc  lea     rcx, [rsp+38h+arg_8]; this
0x180005a01  call    ??0DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::DiagnosisTextParser(void)
0x180005a06  nop
0x180005a07  mov     rdx, rbx; unsigned __int16 *
0x180005a0a  lea     rcx, [rsp+38h+arg_8]; this
0x180005a0f  call    ?SetXML@DiagnosisTextParser@@QEAAJPEBG@Z; DiagnosisTextParser::SetXML(ushort const *)
0x180005a14  test    eax, eax
0x180005a16  jnz     short loc_180005A32
0x180005a18  lea     rdx, [rsp+38h+arg_10]; unsigned __int16 **
0x180005a1d  lea     rcx, [rsp+38h+arg_8]; this
0x180005a22  call    ?GetReplacedText@DiagnosisTextParser@@QEAAJPEAPEAG@Z; DiagnosisTextParser::GetReplacedText(ushort * *)
0x180005a27  mov     rdi, [rsp+38h+arg_10]
0x180005a2c  test    eax, eax
0x180005a2e  cmovns  rbx, rdi
0x180005a32  mov     edx, 400h; MaxCount
0x180005a37  mov     rcx, rbx; Source
0x180005a3a  call    cs:__imp_wcsnlen
0x180005a40  lea     rcx, ds:2[rax*2]
0x180005a48  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180005a4d  mov     [rsp+38h+var_18], rbx
0x180005a52  mov     r9d, eax
0x180005a55  lea     r8, aNdfrootcause; "NDFRootCause"
0x180005a5c  xor     edx, edx
0x180005a5e  mov     rcx, [rsi+8]
0x180005a62  call    cs:__imp_WdiAddParameter
0x180005a68  mov     ebx, eax
0x180005a6a  mov     rcx, rdi; pv
0x180005a6d  call    cs:__imp_CoTaskMemFree
0x180005a73  nop
0x180005a74  lea     rcx, [rsp+38h+arg_8]; this
0x180005a79  call    ??1DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::~DiagnosisTextParser(void)
0x180005a7e  mov     eax, ebx
0x180005a80  mov     rbx, [rsp+38h+arg_0]
0x180005a85  mov     rsi, [rsp+38h+arg_18]
0x180005a8a  add     rsp, 30h
0x180005a8e  pop     rdi
0x180005a8f  retn
```
