# MosHostGetCopyrightString

- ea: `0x1800075f0`
- end: `0x180007679`
- name: `MosHostGetCopyrightString`
- size: `137`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800075f0`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000761e`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000761e`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007655`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007655`

## string_xrefs

- `0x180007605`: `[MosHost] MosHostGetCopyrightString`
- `0x180007612`: `MosHostGetCopyrightString`
- `0x18000764c`: `MosHostGetCopyrightString`

## pseudocode

```c
__int64 __fastcall MosHostGetCopyrightString(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v5; // eax
  unsigned int v6; // ecx
  char v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  ZTraceHelperNoThis(5, "MosHostGetCopyrightString", 393, "[MosHost] MosHostGetCopyrightString");
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
    return (unsigned int)ZTraceReportPropagationNoThis(v5, "MosHostGetCopyrightString", 395);
  }
  return v6;
}

```

## disassembly

```asm
0x1800075f0  mov     [rsp+arg_0], rbx
0x1800075f5  push    rdi
0x1800075f6  sub     rsp, 20h
0x1800075fa  mov     rdi, r8
0x1800075fd  mov     [rsp+28h+arg_18], 0
0x180007602  mov     rbx, rdx
0x180007605  lea     r9, aMoshostMoshost; "[MosHost] MosHostGetCopyrightString"
0x18000760c  mov     r8d, 189h
0x180007612  lea     rdx, aMoshostgetcopy; "MosHostGetCopyrightString"
0x180007619  mov     ecx, 5
0x18000761e  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180007624  mov     rcx, cs:qword_1800185D0
0x18000762b  lea     r8, [rsp+28h+arg_18]
0x180007630  mov     rdx, rbx
0x180007633  mov     rax, [rcx]
0x180007636  mov     rax, [rax+98h]
0x18000763d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007642  test    eax, eax
0x180007644  jns     short loc_18000765F
0x180007646  mov     r8d, 18Bh
0x18000764c  lea     rdx, aMoshostgetcopy; "MosHostGetCopyrightString"
0x180007653  mov     ecx, eax
0x180007655  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000765b  mov     ecx, eax
0x18000765d  jmp     short loc_18000766C
0x18000765f  xor     eax, eax
0x180007661  xor     ecx, ecx
0x180007663  cmp     [rsp+28h+arg_18], al
0x180007667  setnz   al
0x18000766a  mov     [rdi], eax
0x18000766c  mov     rbx, [rsp+28h+arg_0]
0x180007671  mov     eax, ecx
0x180007673  add     rsp, 20h
0x180007677  pop     rdi
0x180007678  retn
```
