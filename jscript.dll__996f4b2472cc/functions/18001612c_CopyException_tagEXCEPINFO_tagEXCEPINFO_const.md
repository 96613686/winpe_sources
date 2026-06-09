# CopyException(tagEXCEPINFO *,tagEXCEPINFO const *)

- ea: `0x18001612c`
- end: `0x1800161d9`
- name: `?CopyException@@YAXPEAUtagEXCEPINFO@@PEBU1@@Z`
- size: `173`
- prototype: `void __fastcall(struct tagEXCEPINFO *, const struct tagEXCEPINFO *)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1800047c0`
- `0x180045554`
- `0x18007533c`
- `0x18007543c`
- `0x180075640`
- `0x1800776d8`
- `0x180077848`
- `0x18007bc00`
- `0x18007c630`

## callees

- `0x180007e68`
- `0x18001612c`
- `0x180017330`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180016168`
- `OLEAUT32!__imp_SysStringLen` at `0x18001618c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800161bc`
- `OLEAUT32!__imp_SysStringLen` at `0x180016168`
- `OLEAUT32!__imp_SysStringLen` at `0x18001618c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800161bc`

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
0x18001612c  mov     [rsp+arg_0], rbx
0x180016131  push    rdi
0x180016132  sub     rsp, 20h
0x180016136  mov     rbx, rdx
0x180016139  mov     rdi, rcx
0x18001613c  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180016141  movups  xmm0, xmmword ptr [rbx]
0x180016144  movups  xmmword ptr [rdi], xmm0
0x180016147  movups  xmm1, xmmword ptr [rbx+10h]
0x18001614b  movups  xmmword ptr [rdi+10h], xmm1
0x18001614f  movups  xmm0, xmmword ptr [rbx+20h]
0x180016153  movups  xmmword ptr [rdi+20h], xmm0
0x180016157  movups  xmm1, xmmword ptr [rbx+30h]
0x18001615b  movups  xmmword ptr [rdi+30h], xmm1
0x18001615f  mov     rcx, [rbx+8]; pbstr
0x180016163  test    rcx, rcx
0x180016166  jz      short loc_180016183
0x180016168  call    cs:__imp_SysStringLen
0x18001616f  nop     dword ptr [rax+rax+00h]
0x180016174  mov     rcx, [rbx+8]; unsigned __int16 *
0x180016178  mov     edx, eax; unsigned int
0x18001617a  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18001617f  mov     [rdi+8], rax
0x180016183  mov     rcx, [rbx+10h]; pbstr
0x180016187  test    rcx, rcx
0x18001618a  jz      short loc_1800161A7
0x18001618c  call    cs:__imp_SysStringLen
0x180016193  nop     dword ptr [rax+rax+00h]
0x180016198  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18001619c  mov     edx, eax; unsigned int
0x18001619e  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x1800161a3  mov     [rdi+10h], rax
0x1800161a7  mov     rcx, [rbx+18h]; pbstr
0x1800161ab  test    rcx, rcx
0x1800161ae  jnz     short loc_1800161BC
0x1800161b0  mov     rbx, [rsp+28h+arg_0]
0x1800161b5  add     rsp, 20h
0x1800161b9  pop     rdi
0x1800161ba  retn
0x1800161bc  call    cs:__imp_SysStringLen
0x1800161c3  nop     dword ptr [rax+rax+00h]
0x1800161c8  mov     rcx, [rbx+18h]; unsigned __int16 *
0x1800161cc  mov     edx, eax; unsigned int
0x1800161ce  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x1800161d3  mov     [rdi+18h], rax
0x1800161d7  jmp     short loc_1800161B0
```
