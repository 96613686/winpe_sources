# CMFTSimpleTypeHandler::GetInputCurrentType(ulong,IMFMediaType * *)

- ea: `0x1800090a0`
- end: `0x180009126`
- name: `?GetInputCurrentType@CMFTSimpleTypeHandler@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `134`
- prototype: `int(CMFTSimpleTypeHandler *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800090a0`
- `0x18001e010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800090d8`
- `MFPlat!MFCreateMediaType` at `0x1800090d8`

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
0x1800090a0  mov     [rsp+arg_0], rbx
0x1800090a5  push    rdi
0x1800090a6  sub     rsp, 20h
0x1800090aa  mov     rbx, r8
0x1800090ad  mov     rdi, rcx
0x1800090b0  test    edx, edx
0x1800090b2  jz      short loc_1800090BB
0x1800090b4  mov     eax, 0C00D36B3h
0x1800090b9  jmp     short loc_18000911B
0x1800090bb  test    rbx, rbx
0x1800090be  jnz     short loc_1800090C7
0x1800090c0  mov     eax, 80004003h
0x1800090c5  jmp     short loc_18000911B
0x1800090c7  cmp     qword ptr [rcx+30h], 0
0x1800090cc  jnz     short loc_1800090D5
0x1800090ce  mov     eax, 0C00D6D60h
0x1800090d3  jmp     short loc_18000911B
0x1800090d5  mov     rcx, rbx; ppMFType
0x1800090d8  call    cs:__imp_MFCreateMediaType
0x1800090de  test    eax, eax
0x1800090e0  js      short loc_18000911B
0x1800090e2  mov     rcx, [rdi+30h]
0x1800090e6  mov     rdx, [rbx]
0x1800090e9  mov     rax, [rcx]
0x1800090ec  mov     rax, [rax+100h]
0x1800090f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f8  mov     edi, eax
0x1800090fa  test    eax, eax
0x1800090fc  jns     short loc_180009119
0x1800090fe  mov     rcx, [rbx]
0x180009101  test    rcx, rcx
0x180009104  jz      short loc_180009119
0x180009106  mov     rdx, [rcx]
0x180009109  mov     rax, [rdx+10h]
0x18000910d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009112  mov     qword ptr [rbx], 0
0x180009119  mov     eax, edi
0x18000911b  mov     rbx, [rsp+28h+arg_0]
0x180009120  add     rsp, 20h
0x180009124  pop     rdi
0x180009125  retn
```
