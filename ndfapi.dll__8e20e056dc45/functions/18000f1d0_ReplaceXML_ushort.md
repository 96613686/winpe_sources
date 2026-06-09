# ReplaceXML(ushort * *)

- ea: `0x18000f1d0`
- end: `0x18000f25b`
- name: `?ReplaceXML@@YAJPEAPEAG@Z`
- size: `139`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180019af8`

## callees

- `0x18000f1d0`
- `0x18001d5d0`
- `0x18001d688`
- `0x18001dd0c`
- `0x18001e244`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000f225`
- `ole32!CoTaskMemFree` at `0x18000f225`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReplaceXML(unsigned __int16 **a1)
{
  DiagnosisTextParserImpl *v2; // rbx
  int v3; // eax
  int ReplacedText; // ebx
  unsigned __int16 *v6; // [rsp+30h] [rbp+8h] BYREF
  DiagnosisTextParserImpl *v7; // [rsp+38h] [rbp+10h] BYREF

  DiagnosisTextParser::DiagnosisTextParser((DiagnosisTextParser *)&v7);
  v2 = v7;
  if ( !v7 )
    goto LABEL_8;
  v3 = DiagnosisTextParserImpl::SetXML((void **)v7, *a1);
  if ( !v3 )
  {
    v6 = 0;
    if ( v2 )
    {
      ReplacedText = DiagnosisTextParserImpl::GetReplacedText(v2, &v6);
      if ( ReplacedText >= 0 )
      {
        CoTaskMemFree(*a1);
        *a1 = v6;
      }
      goto LABEL_9;
    }
LABEL_8:
    ReplacedText = -2147024882;
    goto LABEL_9;
  }
  ReplacedText = 0;
  if ( v3 < 0 )
    ReplacedText = v3;
LABEL_9:
  DiagnosisTextParser::~DiagnosisTextParser(&v7);
  return (unsigned int)ReplacedText;
}

```

## disassembly

```asm
0x18000f1d0  mov     [rsp+arg_10], rbx
0x18000f1d5  push    rdi
0x18000f1d6  sub     rsp, 20h
0x18000f1da  mov     rdi, rcx
0x18000f1dd  lea     rcx, [rsp+28h+arg_8]; this
0x18000f1e2  call    ??0DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::DiagnosisTextParser(void)
0x18000f1e7  nop
0x18000f1e8  mov     rbx, [rsp+28h+arg_8]
0x18000f1ed  test    rbx, rbx
0x18000f1f0  jz      short loc_18000F23F
0x18000f1f2  mov     rdx, [rdi]; unsigned __int16 *
0x18000f1f5  mov     rcx, rbx; this
0x18000f1f8  call    ?SetXML@DiagnosisTextParserImpl@@QEAAJPEBG@Z; DiagnosisTextParserImpl::SetXML(ushort const *)
0x18000f1fd  test    eax, eax
0x18000f1ff  jnz     short loc_18000F235
0x18000f201  mov     [rsp+28h+arg_0], 0
0x18000f20a  test    rbx, rbx
0x18000f20d  jz      short loc_18000F23F
0x18000f20f  lea     rdx, [rsp+28h+arg_0]; unsigned __int16 **
0x18000f214  mov     rcx, rbx; this
0x18000f217  call    ?GetReplacedText@DiagnosisTextParserImpl@@QEAAJPEAPEAG@Z; DiagnosisTextParserImpl::GetReplacedText(ushort * *)
0x18000f21c  mov     ebx, eax
0x18000f21e  test    eax, eax
0x18000f220  js      short loc_18000F244
0x18000f222  mov     rcx, [rdi]; pv
0x18000f225  call    cs:__imp_CoTaskMemFree
0x18000f22b  mov     rax, [rsp+28h+arg_0]
0x18000f230  mov     [rdi], rax
0x18000f233  jmp     short loc_18000F244
0x18000f235  xor     ebx, ebx
0x18000f237  test    eax, eax
0x18000f239  jns     short loc_18000F244
0x18000f23b  mov     ebx, eax
0x18000f23d  jmp     short loc_18000F244
0x18000f23f  mov     ebx, 8007000Eh
0x18000f244  lea     rcx, [rsp+28h+arg_8]; this
0x18000f249  call    ??1DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::~DiagnosisTextParser(void)
0x18000f24e  mov     eax, ebx
0x18000f250  mov     rbx, [rsp+28h+arg_10]
0x18000f255  add     rsp, 20h
0x18000f259  pop     rdi
0x18000f25a  retn
```
