# OdmlSvcGetCopyrightString

- ea: `0x180008030`
- end: `0x1800080c6`
- name: `OdmlSvcGetCopyrightString`
- size: `150`
- prototype: `__int64 __fastcall(int, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008030`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000806b`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000806b`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800080a2`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800080a2`

## string_xrefs

- `0x18000804d`: `[MosHost] OdmlSvcGetCopyrightString`
- `0x18000805f`: `OdmlSvcGetCopyrightString`
- `0x180008099`: `OdmlSvcGetCopyrightString`

## pseudocode

```c
__int64 __fastcall OdmlSvcGetCopyrightString(int a1, __int64 a2, _DWORD *a3)
{
  int v5; // eax
  unsigned int v6; // ecx
  char v8; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800185C4 != a1 )
    __int2c();
  v8 = 0;
  ZTraceHelperNoThis(5, "OdmlSvcGetCopyrightString", 305, "[MosHost] OdmlSvcGetCopyrightString");
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)qword_1800185D0 + 152LL))(
         qword_1800185D0,
         a2,
         &v8);
  if ( v5 >= 0 )
  {
    v6 = 0;
    *a3 = v8 != 0;
  }
  else
  {
    return (unsigned int)ZTraceReportPropagationNoThis(v5, "OdmlSvcGetCopyrightString", 309);
  }
  return v6;
}

```

## disassembly

```asm
0x180008030  mov     [rsp+arg_8], rbx
0x180008035  push    rdi
0x180008036  sub     rsp, 20h
0x18000803a  mov     eax, cs:dword_1800185C4
0x180008040  mov     rbx, r8
0x180008043  mov     rdi, rdx
0x180008046  nop
0x180008047  cmp     eax, ecx
0x180008049  jz      short loc_18000804D
0x18000804b  int     2Ch; Windows NT - assertion failure
0x18000804d  lea     r9, aMoshostOdmlsvc_11; "[MosHost] OdmlSvcGetCopyrightString"
0x180008054  mov     [rsp+28h+arg_0], 0
0x180008059  mov     r8d, 131h
0x18000805f  lea     rdx, aOdmlsvcgetcopy; "OdmlSvcGetCopyrightString"
0x180008066  mov     ecx, 5
0x18000806b  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180008071  mov     rcx, cs:qword_1800185D0
0x180008078  lea     r8, [rsp+28h+arg_0]
0x18000807d  mov     rdx, rdi
0x180008080  mov     rax, [rcx]
0x180008083  mov     rax, [rax+98h]
0x18000808a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000808f  test    eax, eax
0x180008091  jns     short loc_1800080AC
0x180008093  mov     r8d, 135h
0x180008099  lea     rdx, aOdmlsvcgetcopy; "OdmlSvcGetCopyrightString"
0x1800080a0  mov     ecx, eax
0x1800080a2  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800080a8  mov     ecx, eax
0x1800080aa  jmp     short loc_1800080B9
0x1800080ac  xor     eax, eax
0x1800080ae  xor     ecx, ecx
0x1800080b0  cmp     [rsp+28h+arg_0], al
0x1800080b4  setnz   al
0x1800080b7  mov     [rbx], eax
0x1800080b9  mov     rbx, [rsp+28h+arg_8]
0x1800080be  mov     eax, ecx
0x1800080c0  add     rsp, 20h
0x1800080c4  pop     rdi
0x1800080c5  retn
```
