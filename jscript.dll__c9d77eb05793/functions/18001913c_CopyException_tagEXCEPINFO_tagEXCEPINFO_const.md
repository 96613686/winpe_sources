# CopyException(tagEXCEPINFO *,tagEXCEPINFO const *)

- ea: `0x18001913c`
- end: `0x1800191d6`
- name: `?CopyException@@YAXPEAUtagEXCEPINFO@@PEBU1@@Z`
- size: `154`
- prototype: `void __fastcall(struct tagEXCEPINFO *, const struct tagEXCEPINFO *)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1800049f4`
- `0x180044838`
- `0x180073e58`
- `0x180073f4c`
- `0x180074150`
- `0x1800761b0`
- `0x180076314`
- `0x18007a430`
- `0x18007ae50`

## callees

- `0x18000ad40`
- `0x18001913c`
- `0x18001a2dc`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180019178`
- `OLEAUT32!__imp_SysStringLen` at `0x180019196`
- `OLEAUT32!__imp_SysStringLen` at `0x1800191bf`
- `OLEAUT32!__imp_SysStringLen` at `0x180019178`
- `OLEAUT32!__imp_SysStringLen` at `0x180019196`
- `OLEAUT32!__imp_SysStringLen` at `0x1800191bf`

## pseudocode

```c
void __fastcall CopyException(struct tagEXCEPINFO *a1, const struct tagEXCEPINFO *a2)
{
  OLECHAR *bstrSource; // rcx
  UINT v5; // eax
  OLECHAR *bstrDescription; // rcx
  UINT v7; // eax
  OLECHAR *bstrHelpFile; // rcx
  UINT v9; // eax

  FreeExcepInfo(a1);
  *a1 = *a2;
  bstrSource = a2->bstrSource;
  if ( bstrSource )
  {
    v5 = SysStringLen(bstrSource);
    a1->bstrSource = _SysAllocStringLen(a2->bstrSource, v5);
  }
  bstrDescription = a2->bstrDescription;
  if ( bstrDescription )
  {
    v7 = SysStringLen(bstrDescription);
    a1->bstrDescription = _SysAllocStringLen(a2->bstrDescription, v7);
  }
  bstrHelpFile = a2->bstrHelpFile;
  if ( bstrHelpFile )
  {
    v9 = SysStringLen(bstrHelpFile);
    a1->bstrHelpFile = _SysAllocStringLen(a2->bstrHelpFile, v9);
  }
}

```

## disassembly

```asm
0x18001913c  mov     [rsp+arg_0], rbx
0x180019141  push    rdi
0x180019142  sub     rsp, 20h
0x180019146  mov     rbx, rdx
0x180019149  mov     rdi, rcx
0x18001914c  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180019151  movups  xmm0, xmmword ptr [rbx]
0x180019154  movups  xmmword ptr [rdi], xmm0
0x180019157  movups  xmm1, xmmword ptr [rbx+10h]
0x18001915b  movups  xmmword ptr [rdi+10h], xmm1
0x18001915f  movups  xmm0, xmmword ptr [rbx+20h]
0x180019163  movups  xmmword ptr [rdi+20h], xmm0
0x180019167  movups  xmm1, xmmword ptr [rbx+30h]
0x18001916b  movups  xmmword ptr [rdi+30h], xmm1
0x18001916f  mov     rcx, [rbx+8]; pbstr
0x180019173  test    rcx, rcx
0x180019176  jz      short loc_18001918D
0x180019178  call    cs:__imp_SysStringLen
0x18001917e  mov     rcx, [rbx+8]; unsigned __int16 *
0x180019182  mov     edx, eax; unsigned int
0x180019184  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x180019189  mov     [rdi+8], rax
0x18001918d  mov     rcx, [rbx+10h]; pbstr
0x180019191  test    rcx, rcx
0x180019194  jz      short loc_1800191AB
0x180019196  call    cs:__imp_SysStringLen
0x18001919c  mov     rcx, [rbx+10h]; unsigned __int16 *
0x1800191a0  mov     edx, eax; unsigned int
0x1800191a2  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x1800191a7  mov     [rdi+10h], rax
0x1800191ab  mov     rcx, [rbx+18h]; pbstr
0x1800191af  test    rcx, rcx
0x1800191b2  jnz     short loc_1800191BF
0x1800191b4  mov     rbx, [rsp+28h+arg_0]
0x1800191b9  add     rsp, 20h
0x1800191bd  pop     rdi
0x1800191be  retn
0x1800191bf  call    cs:__imp_SysStringLen
0x1800191c5  mov     rcx, [rbx+18h]; unsigned __int16 *
0x1800191c9  mov     edx, eax; unsigned int
0x1800191cb  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x1800191d0  mov     [rdi+18h], rax
0x1800191d4  jmp     short loc_1800191B4
```
