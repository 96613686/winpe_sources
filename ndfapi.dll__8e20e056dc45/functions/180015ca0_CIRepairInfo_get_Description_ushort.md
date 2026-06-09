# CIRepairInfo::get_Description(ushort * *)

- ea: `0x180015ca0`
- end: `0x180015d39`
- name: `?get_Description@CIRepairInfo@@UEAAJPEAPEAG@Z`
- size: `153`
- prototype: `__int64 __fastcall(CIRepairInfo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update`

## callees

- `0x180015ca0`
- `0x18001dd0c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180015d1e`
- `ole32!CoTaskMemFree` at `0x180015d1e`
- `OLEAUT32!__imp_SysAllocString` at `0x180015d06`
- `OLEAUT32!__imp_SysAllocString` at `0x180015d06`

## pseudocode

```c
__int64 __fastcall CIRepairInfo::get_Description(CIRepairInfo *this, unsigned __int16 **a2)
{
  __int64 v2; // rax
  OLECHAR *v6; // rdi
  DiagnosisTextParserImpl *v7; // rcx
  int ReplacedText; // eax
  int v9; // ebx
  unsigned __int16 *v10; // rax
  OLECHAR *psz; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 10);
  if ( !v2 )
    return 2147942421LL;
  v6 = 0;
  psz = 0;
  if ( !*((_DWORD *)this + 22) )
  {
    v6 = *(OLECHAR **)(v2 + 24);
    v9 = 0;
    goto LABEL_10;
  }
  v7 = (DiagnosisTextParserImpl *)*((_QWORD *)this + 12);
  if ( v7 )
  {
    ReplacedText = DiagnosisTextParserImpl::GetReplacedText(v7, &psz);
    v6 = psz;
    v9 = ReplacedText;
  }
  else
  {
    v9 = -2147024882;
  }
  if ( v9 >= 0 )
  {
LABEL_10:
    v10 = SysAllocString(v6);
    *a2 = v10;
    if ( !v10 )
      v9 = -2147024882;
    if ( *((_DWORD *)this + 22) )
      CoTaskMemFree(v6);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180015ca0  mov     [rsp+arg_8], rbx
0x180015ca5  mov     [rsp+arg_10], rbp
0x180015caa  push    rsi
0x180015cab  push    rdi
0x180015cac  push    r14
0x180015cae  sub     rsp, 20h
0x180015cb2  mov     rax, [rcx+50h]
0x180015cb6  mov     r14, rdx
0x180015cb9  mov     rsi, rcx
0x180015cbc  test    rax, rax
0x180015cbf  jnz     short loc_180015CC8
0x180015cc1  mov     eax, 80070015h
0x180015cc6  jmp     short loc_180015D26
0x180015cc8  xor     edi, edi
0x180015cca  mov     ebp, 8007000Eh
0x180015ccf  mov     [rsp+38h+psz], rdi
0x180015cd4  cmp     [rcx+58h], edi
0x180015cd7  jz      short loc_180015CFD
0x180015cd9  mov     rcx, [rcx+60h]; this
0x180015cdd  test    rcx, rcx
0x180015ce0  jz      short loc_180015CF5
0x180015ce2  lea     rdx, [rsp+38h+psz]; unsigned __int16 **
0x180015ce7  call    ?GetReplacedText@DiagnosisTextParserImpl@@QEAAJPEAPEAG@Z; DiagnosisTextParserImpl::GetReplacedText(ushort * *)
0x180015cec  mov     rdi, [rsp+38h+psz]
0x180015cf1  mov     ebx, eax
0x180015cf3  jmp     short loc_180015CF7
0x180015cf5  mov     ebx, ebp
0x180015cf7  test    ebx, ebx
0x180015cf9  js      short loc_180015D24
0x180015cfb  jmp     short loc_180015D03
0x180015cfd  mov     rdi, [rax+18h]
0x180015d01  xor     ebx, ebx
0x180015d03  mov     rcx, rdi; psz
0x180015d06  call    cs:__imp_SysAllocString
0x180015d0c  test    rax, rax
0x180015d0f  mov     [r14], rax
0x180015d12  cmovz   ebx, ebp
0x180015d15  cmp     dword ptr [rsi+58h], 0
0x180015d19  jz      short loc_180015D24
0x180015d1b  mov     rcx, rdi; pv
0x180015d1e  call    cs:__imp_CoTaskMemFree
0x180015d24  mov     eax, ebx
0x180015d26  mov     rbx, [rsp+38h+arg_8]
0x180015d2b  mov     rbp, [rsp+38h+arg_10]
0x180015d30  add     rsp, 20h
0x180015d34  pop     r14
0x180015d36  pop     rdi
0x180015d37  pop     rsi
0x180015d38  retn
```
