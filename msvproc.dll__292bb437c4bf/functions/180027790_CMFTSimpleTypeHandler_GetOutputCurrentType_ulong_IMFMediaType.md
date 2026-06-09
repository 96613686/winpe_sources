# CMFTSimpleTypeHandler::GetOutputCurrentType(ulong,IMFMediaType * *)

- ea: `0x180027790`
- end: `0x180027816`
- name: `?GetOutputCurrentType@CMFTSimpleTypeHandler@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `134`
- prototype: `int(CMFTSimpleTypeHandler *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180027790`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800277c8`
- `MFPlat!MFCreateMediaType` at `0x1800277c8`

## pseudocode

```c
HRESULT __fastcall CMFTSimpleTypeHandler::GetOutputCurrentType(
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
  if ( !*((_QWORD *)this + 10) )
    return -1072861856;
  result = MFCreateMediaType(a3);
  if ( result >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 256LL))(*((_QWORD *)this + 10), *a3);
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
0x180027790  mov     [rsp+arg_0], rbx
0x180027795  push    rdi
0x180027796  sub     rsp, 20h
0x18002779a  mov     rbx, r8
0x18002779d  mov     rdi, rcx
0x1800277a0  test    edx, edx
0x1800277a2  jz      short loc_1800277AB
0x1800277a4  mov     eax, 0C00D36B3h
0x1800277a9  jmp     short loc_18002780B
0x1800277ab  test    rbx, rbx
0x1800277ae  jnz     short loc_1800277B7
0x1800277b0  mov     eax, 80004003h
0x1800277b5  jmp     short loc_18002780B
0x1800277b7  cmp     qword ptr [rcx+50h], 0
0x1800277bc  jnz     short loc_1800277C5
0x1800277be  mov     eax, 0C00D6D60h
0x1800277c3  jmp     short loc_18002780B
0x1800277c5  mov     rcx, rbx; ppMFType
0x1800277c8  call    cs:__imp_MFCreateMediaType
0x1800277ce  test    eax, eax
0x1800277d0  js      short loc_18002780B
0x1800277d2  mov     rcx, [rdi+50h]
0x1800277d6  mov     rdx, [rbx]
0x1800277d9  mov     rax, [rcx]
0x1800277dc  mov     rax, [rax+100h]
0x1800277e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277e8  mov     edi, eax
0x1800277ea  test    eax, eax
0x1800277ec  jns     short loc_180027809
0x1800277ee  mov     rcx, [rbx]
0x1800277f1  test    rcx, rcx
0x1800277f4  jz      short loc_180027809
0x1800277f6  mov     rdx, [rcx]
0x1800277f9  mov     rax, [rdx+10h]
0x1800277fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027802  mov     qword ptr [rbx], 0
0x180027809  mov     eax, edi
0x18002780b  mov     rbx, [rsp+28h+arg_0]
0x180027810  add     rsp, 20h
0x180027814  pop     rdi
0x180027815  retn
```
