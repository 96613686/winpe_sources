# CMFTSimpleTypeHandler::GetInputCurrentType(ulong,IMFMediaType * *)

- ea: `0x180045310`
- end: `0x180045396`
- name: `?GetInputCurrentType@CMFTSimpleTypeHandler@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `134`
- prototype: `int(CMFTSimpleTypeHandler *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180045310`
- `0x180070010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180045348`
- `MFPlat!MFCreateMediaType` at `0x180045348`

## pseudocode

```c
HRESULT __fastcall CMFTSimpleTypeHandler::GetInputCurrentType(
        CMFTSimpleTypeHandler *this,
        int a2,
        struct IMFMediaType **a3)
{
  HRESULT result; // eax
  int v6; // edi

  if ( a2 )
    return -1072875853;
  if ( !a3 )
    return -2147467261;
  if ( !*((_QWORD *)this + 6) )
    return -1072861856;
  result = MFCreateMediaType(a3);
  if ( result >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 256LL))(*((_QWORD *)this + 6), *a3);
    if ( v6 < 0 )
    {
      if ( *a3 )
      {
        ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
        *a3 = 0;
      }
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180045310  mov     [rsp+arg_0], rbx
0x180045315  push    rdi
0x180045316  sub     rsp, 20h
0x18004531a  mov     rbx, r8
0x18004531d  mov     rdi, rcx
0x180045320  test    edx, edx
0x180045322  jz      short loc_18004532B
0x180045324  mov     eax, 0C00D36B3h
0x180045329  jmp     short loc_18004538B
0x18004532b  test    rbx, rbx
0x18004532e  jnz     short loc_180045337
0x180045330  mov     eax, 80004003h
0x180045335  jmp     short loc_18004538B
0x180045337  cmp     qword ptr [rcx+30h], 0
0x18004533c  jnz     short loc_180045345
0x18004533e  mov     eax, 0C00D6D60h
0x180045343  jmp     short loc_18004538B
0x180045345  mov     rcx, rbx; ppMFType
0x180045348  call    cs:__imp_MFCreateMediaType
0x18004534e  test    eax, eax
0x180045350  js      short loc_18004538B
0x180045352  mov     rcx, [rdi+30h]
0x180045356  mov     rdx, [rbx]
0x180045359  mov     rax, [rcx]
0x18004535c  mov     rax, [rax+100h]
0x180045363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045368  mov     edi, eax
0x18004536a  test    eax, eax
0x18004536c  jns     short loc_180045389
0x18004536e  mov     rcx, [rbx]
0x180045371  test    rcx, rcx
0x180045374  jz      short loc_180045389
0x180045376  mov     rdx, [rcx]
0x180045379  mov     rax, [rdx+10h]
0x18004537d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045382  mov     qword ptr [rbx], 0
0x180045389  mov     eax, edi
0x18004538b  mov     rbx, [rsp+28h+arg_0]
0x180045390  add     rsp, 20h
0x180045394  pop     rdi
0x180045395  retn
```
