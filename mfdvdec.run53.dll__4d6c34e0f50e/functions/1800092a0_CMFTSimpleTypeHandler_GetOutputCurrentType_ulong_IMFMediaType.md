# CMFTSimpleTypeHandler::GetOutputCurrentType(ulong,IMFMediaType * *)

- ea: `0x1800092a0`
- end: `0x180009326`
- name: `?GetOutputCurrentType@CMFTSimpleTypeHandler@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `134`
- prototype: `int(CMFTSimpleTypeHandler *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800092a0`
- `0x18001e010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800092d8`
- `MFPlat!MFCreateMediaType` at `0x1800092d8`

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
0x1800092a0  mov     [rsp+arg_0], rbx
0x1800092a5  push    rdi
0x1800092a6  sub     rsp, 20h
0x1800092aa  mov     rbx, r8
0x1800092ad  mov     rdi, rcx
0x1800092b0  test    edx, edx
0x1800092b2  jz      short loc_1800092BB
0x1800092b4  mov     eax, 0C00D36B3h
0x1800092b9  jmp     short loc_18000931B
0x1800092bb  test    rbx, rbx
0x1800092be  jnz     short loc_1800092C7
0x1800092c0  mov     eax, 80004003h
0x1800092c5  jmp     short loc_18000931B
0x1800092c7  cmp     qword ptr [rcx+50h], 0
0x1800092cc  jnz     short loc_1800092D5
0x1800092ce  mov     eax, 0C00D6D60h
0x1800092d3  jmp     short loc_18000931B
0x1800092d5  mov     rcx, rbx; ppMFType
0x1800092d8  call    cs:__imp_MFCreateMediaType
0x1800092de  test    eax, eax
0x1800092e0  js      short loc_18000931B
0x1800092e2  mov     rcx, [rdi+50h]
0x1800092e6  mov     rdx, [rbx]
0x1800092e9  mov     rax, [rcx]
0x1800092ec  mov     rax, [rax+100h]
0x1800092f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092f8  mov     edi, eax
0x1800092fa  test    eax, eax
0x1800092fc  jns     short loc_180009319
0x1800092fe  mov     rcx, [rbx]
0x180009301  test    rcx, rcx
0x180009304  jz      short loc_180009319
0x180009306  mov     rdx, [rcx]
0x180009309  mov     rax, [rdx+10h]
0x18000930d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009312  mov     qword ptr [rbx], 0
0x180009319  mov     eax, edi
0x18000931b  mov     rbx, [rsp+28h+arg_0]
0x180009320  add     rsp, 20h
0x180009324  pop     rdi
0x180009325  retn
```
