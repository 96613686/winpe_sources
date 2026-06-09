# CIRootCauseInfo::get_Description(ushort * *)

- ea: `0x180015d40`
- end: `0x180015dd8`
- name: `?get_Description@CIRootCauseInfo@@UEAAJPEAPEAG@Z`
- size: `152`
- prototype: `__int64 __fastcall(CIRootCauseInfo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180015d40`
- `0x18001dd0c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180015dbd`
- `ole32!CoTaskMemFree` at `0x180015dbd`
- `OLEAUT32!__imp_SysAllocString` at `0x180015da5`
- `OLEAUT32!__imp_SysAllocString` at `0x180015da5`

## pseudocode

```c
__int64 __fastcall CIRootCauseInfo::get_Description(CIRootCauseInfo *this, unsigned __int16 **a2)
{
  OLECHAR **v2; // rax
  OLECHAR *v6; // rdi
  DiagnosisTextParserImpl *v7; // rcx
  int ReplacedText; // eax
  int v9; // ebx
  unsigned __int16 *v10; // rax
  OLECHAR *psz; // [rsp+40h] [rbp+8h] BYREF

  v2 = (OLECHAR **)*((_QWORD *)this + 9);
  if ( !v2 )
    return 2147942421LL;
  v6 = 0;
  psz = 0;
  if ( !*((_DWORD *)this + 20) )
  {
    v6 = *v2;
    v9 = 0;
    goto LABEL_10;
  }
  v7 = (DiagnosisTextParserImpl *)*((_QWORD *)this + 11);
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
    if ( *((_DWORD *)this + 20) )
      CoTaskMemFree(v6);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180015d40  mov     [rsp+arg_8], rbx
0x180015d45  mov     [rsp+arg_10], rbp
0x180015d4a  push    rsi
0x180015d4b  push    rdi
0x180015d4c  push    r14
0x180015d4e  sub     rsp, 20h
0x180015d52  mov     rax, [rcx+48h]
0x180015d56  mov     r14, rdx
0x180015d59  mov     rsi, rcx
0x180015d5c  test    rax, rax
0x180015d5f  jnz     short loc_180015D68
0x180015d61  mov     eax, 80070015h
0x180015d66  jmp     short loc_180015DC5
0x180015d68  xor     edi, edi
0x180015d6a  mov     ebp, 8007000Eh
0x180015d6f  mov     [rsp+38h+psz], rdi
0x180015d74  cmp     [rcx+50h], edi
0x180015d77  jz      short loc_180015D9D
0x180015d79  mov     rcx, [rcx+58h]; this
0x180015d7d  test    rcx, rcx
0x180015d80  jz      short loc_180015D95
0x180015d82  lea     rdx, [rsp+38h+psz]; unsigned __int16 **
0x180015d87  call    ?GetReplacedText@DiagnosisTextParserImpl@@QEAAJPEAPEAG@Z; DiagnosisTextParserImpl::GetReplacedText(ushort * *)
0x180015d8c  mov     rdi, [rsp+38h+psz]
0x180015d91  mov     ebx, eax
0x180015d93  jmp     short loc_180015D97
0x180015d95  mov     ebx, ebp
0x180015d97  test    ebx, ebx
0x180015d99  js      short loc_180015DC3
0x180015d9b  jmp     short loc_180015DA2
0x180015d9d  mov     rdi, [rax]
0x180015da0  xor     ebx, ebx
0x180015da2  mov     rcx, rdi; psz
0x180015da5  call    cs:__imp_SysAllocString
0x180015dab  test    rax, rax
0x180015dae  mov     [r14], rax
0x180015db1  cmovz   ebx, ebp
0x180015db4  cmp     dword ptr [rsi+50h], 0
0x180015db8  jz      short loc_180015DC3
0x180015dba  mov     rcx, rdi; pv
0x180015dbd  call    cs:__imp_CoTaskMemFree
0x180015dc3  mov     eax, ebx
0x180015dc5  mov     rbx, [rsp+38h+arg_8]
0x180015dca  mov     rbp, [rsp+38h+arg_10]
0x180015dcf  add     rsp, 20h
0x180015dd3  pop     r14
0x180015dd5  pop     rdi
0x180015dd6  pop     rsi
0x180015dd7  retn
```
