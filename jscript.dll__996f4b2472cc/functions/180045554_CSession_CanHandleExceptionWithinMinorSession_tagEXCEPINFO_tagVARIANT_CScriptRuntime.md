# CSession::CanHandleExceptionWithinMinorSession(tagEXCEPINFO *,tagVARIANT *,CScriptRuntime *)

- ea: `0x180045554`
- end: `0x18004560a`
- name: `?CanHandleExceptionWithinMinorSession@CSession@@QEAAJPEAUtagEXCEPINFO@@PEAUtagVARIANT@@PEAVCScriptRuntime@@@Z`
- size: `182`
- prototype: `int(CSession *__hidden this, struct tagEXCEPINFO *, struct tagVARIANT *, struct CScriptRuntime *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800452b4`
- `0x180088940`

## callees

- `0x18001612c`
- `0x180045554`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800455d3`
- `OLEAUT32!__imp_VariantClear` at `0x1800455d3`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800455ee`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800455ee`

## pseudocode

```c
HRESULT __fastcall CSession::CanHandleExceptionWithinMinorSession(
        CSession *this,
        struct tagEXCEPINFO *a2,
        struct tagVARIANT *a3,
        struct CScriptRuntime *a4)
{
  __int64 v6; // rcx
  VARIANTARG *v7; // rcx
  char *v8; // rax
  HRESULT result; // eax

  v6 = *((_QWORD *)a4 + 5);
  while ( *((_QWORD *)a4 + 24) == *((_QWORD *)a4 + 23) )
  {
    a4 = (struct CScriptRuntime *)*((_QWORD *)a4 + 2);
    if ( !a4 || v6 != *((_QWORD *)a4 + 5) )
      return -2147467259;
  }
  *((_DWORD *)this + 308) = 0;
  v7 = (VARIANTARG *)((char *)this + 1208);
  if ( a3 )
  {
    if ( v7 != a3 )
    {
      result = VariantCopyInd(v7, a3);
      if ( result < 0 )
        return result;
    }
  }
  else
  {
    VariantClear(v7);
    *((_DWORD *)this + 308) = 1;
  }
  v8 = (char *)*((_QWORD *)this + 136);
  if ( !v8 )
    v8 = (char *)this + 1096;
  if ( v8 + 8 != (char *)a2 )
    CopyException((struct tagEXCEPINFO *)(v8 + 8), a2);
  return 0;
}

```

## disassembly

```asm
0x180045554  mov     [rsp+arg_0], rbx
0x180045559  push    rdi
0x18004555a  sub     rsp, 20h
0x18004555e  mov     rbx, rcx
0x180045561  mov     rdi, rdx
0x180045564  mov     rcx, [r9+28h]
0x180045568  mov     rax, [r9+0B8h]
0x18004556f  cmp     [r9+0C0h], rax
0x180045576  jz      short loc_1800455BD
0x180045578  mov     dword ptr [rbx+4D0h], 0
0x180045582  lea     rcx, [rbx+4B8h]; pvarDest
0x180045589  test    r8, r8
0x18004558c  jz      short loc_1800455D3
0x18004558e  cmp     rcx, r8
0x180045591  jnz     short loc_1800455EB
0x180045593  mov     rax, [rbx+440h]
0x18004559a  test    rax, rax
0x18004559d  jnz     short loc_1800455A6
0x18004559f  lea     rax, [rbx+448h]
0x1800455a6  lea     rcx, [rax+8]; struct tagEXCEPINFO *
0x1800455aa  cmp     rcx, rdi
0x1800455ad  jnz     short loc_180045600
0x1800455af  xor     eax, eax
0x1800455b1  mov     rbx, [rsp+28h+arg_0]
0x1800455b6  add     rsp, 20h
0x1800455ba  pop     rdi
0x1800455bb  retn
0x1800455bd  mov     r9, [r9+10h]
0x1800455c1  test    r9, r9
0x1800455c4  jz      short loc_1800455CC
0x1800455c6  cmp     rcx, [r9+28h]
0x1800455ca  jz      short loc_180045568
0x1800455cc  mov     eax, 80004005h
0x1800455d1  jmp     short loc_1800455B1
0x1800455d3  call    cs:__imp_VariantClear
0x1800455da  nop     dword ptr [rax+rax+00h]
0x1800455df  mov     dword ptr [rbx+4D0h], 1
0x1800455e9  jmp     short loc_180045593
0x1800455eb  mov     rdx, r8; pvargSrc
0x1800455ee  call    cs:__imp_VariantCopyInd
0x1800455f5  nop     dword ptr [rax+rax+00h]
0x1800455fa  test    eax, eax
0x1800455fc  js      short loc_1800455B1
0x1800455fe  jmp     short loc_180045593
0x180045600  mov     rdx, rdi; struct tagEXCEPINFO *
0x180045603  call    ?CopyException@@YAXPEAUtagEXCEPINFO@@PEBU1@@Z; CopyException(tagEXCEPINFO *,tagEXCEPINFO const *)
0x180045608  jmp     short loc_1800455AF
```
