# DiagnosticsClient::AddRepair(tagRepairInfo *)

- ea: `0x180005800`
- end: `0x1800059b8`
- name: `?AddRepair@DiagnosticsClient@@UEAAJPEAUtagRepairInfo@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(DiagnosticsClient *this, struct tagRepairInfo *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800056bc`
- `0x180005800`
- `0x180005c64`
- `0x18002b300`
- `0x18002b928`
- `0x18002ba00`
- `0x18002bc48`
- `0x18002c2fc`
- `0x18002c802`
- `0x18002c840`

## import_xrefs

- `wdi!WdiAddParameter` at `0x180005902`
- `wdi!WdiAddParameter` at `0x180005902`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000591d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000592f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000595b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000596d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000598f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000591d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000592f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000595b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000596d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000598f`

## string_xrefs

- `0x1800058f5`: `NDFRepairOption`

## pseudocode

```c
__int64 __fastcall DiagnosticsClient::AddRepair(DiagnosticsClient *this, struct tagRepairInfo *a2)
{
  int v5; // ebx
  LPWSTR pwszDescription; // rbx
  LPVOID v7; // rbx
  unsigned int v8; // eax
  LPWSTR pwszParameters; // rcx
  _BYTE v10[8]; // [rsp+30h] [rbp-49h] BYREF
  LPVOID v11; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int64 v12; // [rsp+40h] [rbp-39h] BYREF
  tagRepairInfo v13; // [rsp+50h] [rbp-29h] BYREF

  v11 = 0;
  v12 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 1) )
    return 2147942406LL;
  v13.guid.Data1 = 0;
  memset_0(&v13.guid.Data2, 0, 0x6Cu);
  v5 = CopyRepairInfo(&v13, a2);
  if ( v5 >= 0 )
  {
    DiagnosisTextParser::DiagnosisTextParser((DiagnosisTextParser *)v10);
    pwszDescription = v13.pwszDescription;
    if ( !(unsigned int)DiagnosisTextParser::SetXML((DiagnosisTextParser *)v10, v13.pwszDescription)
      && (int)DiagnosisTextParser::GetReplacedText((DiagnosisTextParser *)v10, &v13.pwszDescription) >= 0 )
    {
      CoTaskMemFree(pwszDescription);
    }
    DiagnosisTextParser::~DiagnosisTextParser((DiagnosisTextParser *)v10);
    v5 = EncodeRepairInfo(&v13, &v11, &v12);
    if ( v5 >= 0 )
    {
      v7 = v11;
      v8 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v12);
      v5 = WdiAddParameter(*((_QWORD *)this + 1), 0, L"NDFRepairOption", v8, v7);
    }
  }
  if ( v11 )
    CoTaskMemFree(v11);
  CoTaskMemFree(v13.pwszClassName);
  v13.pwszClassName = 0;
  CoTaskMemFree(v13.pwszDescription);
  v13.pwszDescription = 0;
  if ( v13.UiInfo.type == UIT_SHELL_COMMAND )
  {
    CoTaskMemFree(v13.UiInfo.ShellInfo.pwszDirectory);
    v13.UiInfo.ShellInfo.pwszDirectory = 0;
    CoTaskMemFree(v13.UiInfo.ShellInfo.pwszFile);
    v13.UiInfo.ShellInfo.pwszFile = 0;
    CoTaskMemFree(v13.UiInfo.pwzNull);
    v13.UiInfo.pwzNull = 0;
    pwszParameters = v13.UiInfo.ShellInfo.pwszParameters;
  }
  else
  {
    if ( v13.UiInfo.type != UIT_HELP_PANE && v13.UiInfo.type != UIT_DUI )
      return (unsigned int)v5;
    pwszParameters = v13.UiInfo.pwzNull;
  }
  CoTaskMemFree(pwszParameters);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005800  mov     [rsp-8+arg_10], rbx
0x180005805  mov     [rsp-8+arg_18], rdi
0x18000580a  push    rbp
0x18000580b  lea     rbp, [rsp-57h]
0x180005810  sub     rsp, 0D0h
0x180005817  mov     rax, cs:__security_cookie
0x18000581e  xor     rax, rsp
0x180005821  mov     [rbp+57h+var_10], rax
0x180005825  mov     rbx, rdx
0x180005828  mov     rdi, rcx
0x18000582b  mov     [rbp+57h+var_98], 0
0x180005833  mov     [rbp+57h+var_90], 0
0x18000583b  test    rdx, rdx
0x18000583e  jnz     short loc_18000584A
0x180005840  mov     eax, 80070057h
0x180005845  jmp     loc_180005997
0x18000584a  cmp     qword ptr [rcx+8], 0
0x18000584f  jnz     short loc_18000585B
0x180005851  mov     eax, 80070006h
0x180005856  jmp     loc_180005997
0x18000585b  mov     [rbp+57h+var_80.guid.Data1], 0
0x180005862  xor     edx, edx; Val
0x180005864  lea     r8d, [rdx+6Ch]; Size
0x180005868  lea     rcx, [rbp+57h+var_80.guid.Data2]; void *
0x18000586c  call    memset_0
0x180005871  mov     rdx, rbx; struct tagRepairInfo *
0x180005874  lea     rcx, [rbp+57h+var_80]; struct tagRepairInfo *
0x180005878  call    ?CopyRepairInfo@@YAJPEAUtagRepairInfo@@PEBU1@@Z; CopyRepairInfo(tagRepairInfo *,tagRepairInfo const *)
0x18000587d  mov     ebx, eax
0x18000587f  test    eax, eax
0x180005881  js      loc_18000590A
0x180005887  lea     rcx, [rbp+57h+var_A0]; this
0x18000588b  call    ??0DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::DiagnosisTextParser(void)
0x180005890  nop
0x180005891  mov     rbx, [rbp+57h+var_80.pwszDescription]
0x180005895  mov     rdx, rbx; unsigned __int16 *
0x180005898  lea     rcx, [rbp+57h+var_A0]; this
0x18000589c  call    ?SetXML@DiagnosisTextParser@@QEAAJPEBG@Z; DiagnosisTextParser::SetXML(ushort const *)
0x1800058a1  test    eax, eax
0x1800058a3  jnz     short loc_1800058C0
0x1800058a5  lea     rdx, [rbp+57h+var_80.pwszDescription]; unsigned __int16 **
0x1800058a9  lea     rcx, [rbp+57h+var_A0]; this
0x1800058ad  call    ?GetReplacedText@DiagnosisTextParser@@QEAAJPEAPEAG@Z; DiagnosisTextParser::GetReplacedText(ushort * *)
0x1800058b2  test    eax, eax
0x1800058b4  js      short loc_1800058C0
0x1800058b6  mov     rcx, rbx; pv
0x1800058b9  call    cs:__imp_CoTaskMemFree
0x1800058bf  nop
0x1800058c0  lea     rcx, [rbp+57h+var_A0]; this
0x1800058c4  call    ??1DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::~DiagnosisTextParser(void)
0x1800058c9  lea     r8, [rbp+57h+var_90]
0x1800058cd  lea     rdx, [rbp+57h+var_98]
0x1800058d1  lea     rcx, [rbp+57h+var_80]
0x1800058d5  call    EncodeRepairInfo
0x1800058da  mov     ebx, eax
0x1800058dc  test    eax, eax
0x1800058de  js      short loc_18000590A
0x1800058e0  mov     rbx, [rbp+57h+var_98]
0x1800058e4  mov     rcx, [rbp+57h+var_90]
0x1800058e8  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800058ed  mov     [rsp+0D0h+var_B0], rbx
0x1800058f2  mov     r9d, eax
0x1800058f5  lea     r8, aNdfrepairoptio; "NDFRepairOption"
0x1800058fc  xor     edx, edx
0x1800058fe  mov     rcx, [rdi+8]
0x180005902  call    cs:__imp_WdiAddParameter
0x180005908  mov     ebx, eax
0x18000590a  mov     rcx, [rbp+57h+var_98]; pv
0x18000590e  test    rcx, rcx
0x180005911  jz      short loc_180005919
0x180005913  call    cs:__imp_CoTaskMemFree
0x180005919  mov     rcx, [rbp+57h+var_80.pwszClassName]; pv
0x18000591d  call    cs:__imp_CoTaskMemFree
0x180005923  mov     [rbp+57h+var_80.pwszClassName], 0
0x18000592b  mov     rcx, [rbp+57h+var_80.pwszDescription]; pv
0x18000592f  call    cs:__imp_CoTaskMemFree
0x180005935  mov     [rbp+57h+var_80.pwszDescription], 0
0x18000593d  mov     eax, [rbp+57h+var_80.UiInfo.type]
0x180005940  cmp     eax, 2
0x180005943  jnz     short loc_180005981
0x180005945  mov     rcx, qword ptr [rbp+57h+var_80.UiInfo.8+18h]; pv
0x180005949  call    cs:__imp_CoTaskMemFree
0x18000594f  mov     qword ptr [rbp+57h+var_80.UiInfo.8+18h], 0
0x180005957  mov     rcx, qword ptr [rbp+57h+var_80.UiInfo.8+8]; pv
0x18000595b  call    cs:__imp_CoTaskMemFree
0x180005961  mov     qword ptr [rbp+57h+var_80.UiInfo.8+8], 0
0x180005969  mov     rcx, qword ptr [rbp+57h+var_80.UiInfo.8]; pv
0x18000596d  call    cs:__imp_CoTaskMemFree
0x180005973  mov     qword ptr [rbp+57h+var_80.UiInfo.8], 0
0x18000597b  mov     rcx, qword ptr [rbp+57h+var_80.UiInfo.8+10h]
0x18000597f  jmp     short loc_18000598F
0x180005981  cmp     eax, 3
0x180005984  jz      short loc_18000598B
0x180005986  cmp     eax, 4
0x180005989  jnz     short loc_180005995
0x18000598b  mov     rcx, qword ptr [rbp+57h+var_80.UiInfo.8]; pv
0x18000598f  call    cs:__imp_CoTaskMemFree
0x180005995  mov     eax, ebx
0x180005997  mov     rcx, [rbp+57h+var_10]
0x18000599b  xor     rcx, rsp; StackCookie
0x18000599e  call    __security_check_cookie
0x1800059a3  lea     r11, [rsp+0D0h+var_s0]
0x1800059ab  mov     rbx, [r11+20h]
0x1800059af  mov     rdi, [r11+28h]
0x1800059b3  mov     rsp, r11
0x1800059b6  pop     rbp
0x1800059b7  retn
```
