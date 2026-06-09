# CSession::CanHandleExceptionWithinMinorSession(tagEXCEPINFO *,tagVARIANT *,CScriptRuntime *)

- ea: `0x180044838`
- end: `0x1800448e1`
- name: `?CanHandleExceptionWithinMinorSession@CSession@@QEAAJPEAUtagEXCEPINFO@@PEAUtagVARIANT@@PEAVCScriptRuntime@@@Z`
- size: `169`
- prototype: `int(CSession *__hidden this, struct tagEXCEPINFO *, struct tagVARIANT *, struct CScriptRuntime *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180044598`
- `0x180086b40`

## callees

- `0x18001913c`
- `0x180044838`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800448b6`
- `OLEAUT32!__imp_VariantClear` at `0x1800448b6`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800448cb`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800448cb`

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
0x180044838  mov     [rsp+arg_0], rbx
0x18004483d  push    rdi
0x18004483e  sub     rsp, 20h
0x180044842  mov     rbx, rcx
0x180044845  mov     rdi, rdx
0x180044848  mov     rcx, [r9+28h]
0x18004484c  mov     rax, [r9+0B8h]
0x180044853  cmp     [r9+0C0h], rax
0x18004485a  jz      short loc_1800448A0
0x18004485c  mov     dword ptr [rbx+4D0h], 0
0x180044866  lea     rcx, [rbx+4B8h]; pvarDest
0x18004486d  test    r8, r8
0x180044870  jz      short loc_1800448B6
0x180044872  cmp     rcx, r8
0x180044875  jnz     short loc_1800448C8
0x180044877  mov     rax, [rbx+440h]
0x18004487e  test    rax, rax
0x180044881  jnz     short loc_18004488A
0x180044883  lea     rax, [rbx+448h]
0x18004488a  lea     rcx, [rax+8]; struct tagEXCEPINFO *
0x18004488e  cmp     rcx, rdi
0x180044891  jnz     short loc_1800448D7
0x180044893  xor     eax, eax
0x180044895  mov     rbx, [rsp+28h+arg_0]
0x18004489a  add     rsp, 20h
0x18004489e  pop     rdi
0x18004489f  retn
0x1800448a0  mov     r9, [r9+10h]
0x1800448a4  test    r9, r9
0x1800448a7  jz      short loc_1800448AF
0x1800448a9  cmp     rcx, [r9+28h]
0x1800448ad  jz      short loc_18004484C
0x1800448af  mov     eax, 80004005h
0x1800448b4  jmp     short loc_180044895
0x1800448b6  call    cs:__imp_VariantClear
0x1800448bc  mov     dword ptr [rbx+4D0h], 1
0x1800448c6  jmp     short loc_180044877
0x1800448c8  mov     rdx, r8; pvargSrc
0x1800448cb  call    cs:__imp_VariantCopyInd
0x1800448d1  test    eax, eax
0x1800448d3  js      short loc_180044895
0x1800448d5  jmp     short loc_180044877
0x1800448d7  mov     rdx, rdi; struct tagEXCEPINFO *
0x1800448da  call    ?CopyException@@YAXPEAUtagEXCEPINFO@@PEBU1@@Z; CopyException(tagEXCEPINFO *,tagEXCEPINFO const *)
0x1800448df  jmp     short loc_180044893
```
