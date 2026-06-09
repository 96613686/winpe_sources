# CHost::ReportLoadError(long)

- ea: `0x1400097d0`
- end: `0x14000987b`
- name: `?ReportLoadError@CHost@@QEAAJJ@Z`
- size: `171`
- prototype: `__int64 __fastcall(CHost *__hidden this, DWORD dwMessageId)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140001090`
- `0x1400014b0`
- `0x1400069d0`

## callees

- `0x1400097d0`
- `0x1400098ac`
- `0x14000cd9c`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140009864`
- `OLEAUT32!__imp_SysFreeString` at `0x140009864`

## pseudocode

```c
__int64 __fastcall CHost::ReportLoadError(const unsigned __int16 **this, DWORD dwMessageId)
{
  OLECHAR *v2; // rbx
  unsigned int v4; // eax
  unsigned int v5; // edi
  BSTR bstrString; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  bstrString = 0;
  if ( dwMessageId == -2147155969 || dwMessageId == -2147352319 )
    return 2147811327LL;
  if ( dwMessageId == -2147024894 || dwMessageId == -2147024893 )
  {
    v4 = CHost::ReportError((CHost *)this, Global::g_lResourceBase + 21, 0xCEEu, this[76]);
  }
  else
  {
    FormatHResult(dwMessageId, &bstrString);
    v2 = bstrString;
    v4 = (*((__int64 (__fastcall **)(const unsigned __int16 **, _QWORD, __int64, const unsigned __int16 *, BSTR))*this
          + 1))(
           this,
           (unsigned int)(Global::g_lResourceBase + 20),
           3204,
           this[76],
           bstrString);
  }
  v5 = v4;
  SysFreeString(v2);
  return v5;
}

```

## disassembly

```asm
0x1400097d0  mov     [rsp+arg_0], rbx
0x1400097d5  push    rdi
0x1400097d6  sub     rsp, 30h
0x1400097da  xor     ebx, ebx
0x1400097dc  mov     rdi, rcx
0x1400097df  mov     ecx, 8004FFFFh
0x1400097e4  mov     [rsp+38h+bstrString], rbx
0x1400097e9  mov     eax, edx
0x1400097eb  cmp     edx, ecx
0x1400097ed  jz      short loc_14000986E
0x1400097ef  cmp     eax, 80020101h
0x1400097f4  jz      short loc_14000986E
0x1400097f6  cmp     eax, 80070002h
0x1400097fb  jz      short loc_140009841
0x1400097fd  cmp     eax, 80070003h
0x140009802  jz      short loc_140009841
0x140009804  lea     rdx, [rsp+38h+bstrString]; unsigned __int16 **
0x140009809  mov     ecx, eax; dwMessageId
0x14000980b  call    ?FormatHResult@@YAJJPEAPEAG@Z; FormatHResult(long,ushort * *)
0x140009810  mov     rax, [rdi]
0x140009813  mov     r8d, 0C84h
0x140009819  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x14000981f  mov     rcx, rdi
0x140009822  mov     rbx, [rsp+38h+bstrString]
0x140009827  add     edx, 14h
0x14000982a  mov     r9, [rdi+260h]
0x140009831  mov     rax, [rax+8]
0x140009835  mov     [rsp+38h+var_18], rbx
0x14000983a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000983f  jmp     short loc_14000985F
0x140009841  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x140009847  mov     r8d, 0CEEh; unsigned int
0x14000984d  mov     r9, [rdi+260h]; unsigned __int16 *
0x140009854  add     edx, 15h; unsigned int
0x140009857  mov     rcx, rdi; this
0x14000985a  call    ?ReportError@CHost@@QEAAJIIPEBG@Z; CHost::ReportError(uint,uint,ushort const *)
0x14000985f  mov     rcx, rbx; bstrString
0x140009862  mov     edi, eax
0x140009864  call    cs:__imp_SysFreeString
0x14000986a  mov     eax, edi
0x14000986c  jmp     short loc_140009870
0x14000986e  mov     eax, ecx
0x140009870  mov     rbx, [rsp+38h+arg_0]
0x140009875  add     rsp, 30h
0x140009879  pop     rdi
0x14000987a  retn
```
