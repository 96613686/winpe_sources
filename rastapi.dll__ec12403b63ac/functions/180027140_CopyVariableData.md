# CopyVariableData

- ea: `0x180027140`
- end: `0x18002726a`
- name: `CopyVariableData`
- size: `298`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800240a8`
- `0x1800244ec`
- `0x180024b38`
- `0x180024e60`

## callees

- `0x180027140`
- `0x180029130`
- `0x180029266`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18002723e`
- `rtutils!TracePrintfA` at `0x18002723e`

## string_xrefs

- `0x1800271ef`: `CopyVariableData: Invalid values- Size(0x%x), Offset(0x%x)`
- `0x180027237`: `CopyVariableData: Invalid values- Size(0x%x), Offset(0x%x)`

## pseudocode

```c
DWORD __fastcall CopyVariableData(_DWORD *a1, DWORD *a2, __int64 a3, __int64 a4, unsigned int a5)
{
  DWORD result; // eax
  DWORD v10; // ebx
  __int64 v11; // r9
  _WORD v12[2]; // [rsp+20h] [rbp-838h] BYREF
  char v13[2044]; // [rsp+24h] [rbp-834h] BYREF

  v12[1] = 0;
  result = (unsigned int)memset_0(v13, 0, sizeof(v13));
  v10 = *a2;
  if ( *a2 )
  {
    result = *a1 - a5;
    v11 = a2[1];
    if ( v10 > result
      || (unsigned int)v11 < a5
      || (unsigned int)v11 >= *a1
      || (result = v11 + v10, (unsigned int)v11 + v10 > *a1) )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          v12[0] = 0;
          FormatRRASErrorString(v12, L"CopyVariableData: Invalid values- Size(0x%x), Offset(0x%x)", v10, v11);
          result = ((__int64 (__fastcall *)(__int64, __int64, _WORD *))gNdpspTemplateFunc)(
                     gNdpspEtwContext,
                     qword_18003EC40,
                     v12);
        }
      }
      else if ( dwTraceId != -1 )
      {
        result = TracePrintfA(dwTraceId, "CopyVariableData: Invalid values- Size(0x%x), Offset(0x%x)", v10, v11);
      }
      *(_QWORD *)a4 = 0;
    }
    else
    {
      memcpy_0((void *)(a3 + *(unsigned int *)(a3 + 8)), (char *)a1 + v11, v10);
      *(_DWORD *)a4 = v10;
      result = *(_DWORD *)(a3 + 8);
      *(_DWORD *)(a4 + 4) = result;
      *(_DWORD *)(a3 + 8) += v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027140  push    rbx
0x180027142  push    rsi
0x180027143  push    rdi
0x180027144  push    r14
0x180027146  push    r15
0x180027148  sub     rsp, 830h
0x18002714f  mov     rax, cs:__security_cookie
0x180027156  xor     rax, rsp
0x180027159  mov     [rsp+858h+var_38], rax
0x180027161  mov     rsi, r8
0x180027164  mov     r15, rdx
0x180027167  mov     r14, rcx
0x18002716a  xor     eax, eax
0x18002716c  xor     edx, edx; Val
0x18002716e  mov     [rsp+858h+var_836], ax
0x180027173  mov     r8d, 7FCh; Size
0x180027179  lea     rcx, [rsp+858h+var_834]; void *
0x18002717e  mov     rdi, r9
0x180027181  call    memset_0
0x180027186  mov     ebx, [r15]
0x180027189  test    ebx, ebx
0x18002718b  jz      loc_18002724B
0x180027191  mov     eax, [r14]
0x180027194  sub     eax, [rsp+858h+arg_20]
0x18002719b  mov     r9d, [r15+4]
0x18002719f  cmp     ebx, eax
0x1800271a1  ja      short loc_1800271DA
0x1800271a3  cmp     r9d, [rsp+858h+arg_20]
0x1800271ab  jb      short loc_1800271DA
0x1800271ad  cmp     r9d, [r14]
0x1800271b0  jnb     short loc_1800271DA
0x1800271b2  lea     eax, [r9+rbx]
0x1800271b6  cmp     eax, [r14]
0x1800271b9  ja      short loc_1800271DA
0x1800271bb  mov     ecx, [rsi+8]
0x1800271be  lea     rdx, [r14+r9]; Src
0x1800271c2  add     rcx, rsi; void *
0x1800271c5  mov     r8d, ebx; Size
0x1800271c8  call    memcpy_0
0x1800271cd  mov     [rdi], ebx
0x1800271cf  mov     eax, [rsi+8]
0x1800271d2  mov     [rdi+4], eax
0x1800271d5  add     [rsi+8], ebx
0x1800271d8  jmp     short loc_18002724B
0x1800271da  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800271e1  jz      short loc_180027229
0x1800271e3  cmp     cs:qword_18003EC40, 0
0x1800271eb  jz      short loc_180027244
0x1800271ed  xor     eax, eax
0x1800271ef  lea     rdx, aCopyvariableda_0; "CopyVariableData: Invalid values- Size("...
0x1800271f6  mov     r8d, ebx
0x1800271f9  mov     [rsp+858h+var_838], ax
0x1800271fe  lea     rcx, [rsp+858h+var_838]
0x180027203  call    FormatRRASErrorString
0x180027208  mov     rdx, cs:qword_18003EC40
0x18002720f  lea     r8, [rsp+858h+var_838]
0x180027214  mov     rcx, cs:gNdpspEtwContext
0x18002721b  mov     rax, cs:gNdpspTemplateFunc
0x180027222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027227  jmp     short loc_180027244
0x180027229  mov     ecx, cs:dwTraceId; dwTraceID
0x18002722f  cmp     ecx, 0FFFFFFFFh
0x180027232  jz      short loc_180027244
0x180027234  mov     r8d, ebx
0x180027237  lea     rdx, aCopyvariableda; "CopyVariableData: Invalid values- Size("...
0x18002723e  call    cs:__imp_TracePrintfA
0x180027244  mov     qword ptr [rdi], 0
0x18002724b  mov     rcx, [rsp+858h+var_38]
0x180027253  xor     rcx, rsp; StackCookie
0x180027256  call    __security_check_cookie
0x18002725b  add     rsp, 830h
0x180027262  pop     r15
0x180027264  pop     r14
0x180027266  pop     rdi
0x180027267  pop     rsi
0x180027268  pop     rbx
0x180027269  retn
```
