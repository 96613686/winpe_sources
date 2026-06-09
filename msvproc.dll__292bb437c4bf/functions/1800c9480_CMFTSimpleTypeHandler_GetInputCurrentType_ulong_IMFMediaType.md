# CMFTSimpleTypeHandler::GetInputCurrentType(ulong,IMFMediaType * *)

- ea: `0x1800c9480`
- end: `0x1800c9506`
- name: `?GetInputCurrentType@CMFTSimpleTypeHandler@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `134`
- prototype: `int(CMFTSimpleTypeHandler *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800c9480`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800c94b8`
- `MFPlat!MFCreateMediaType` at `0x1800c94b8`

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
0x1800c9480  mov     [rsp+arg_0], rbx
0x1800c9485  push    rdi
0x1800c9486  sub     rsp, 20h
0x1800c948a  mov     rbx, r8
0x1800c948d  mov     rdi, rcx
0x1800c9490  test    edx, edx
0x1800c9492  jz      short loc_1800C949B
0x1800c9494  mov     eax, 0C00D36B3h
0x1800c9499  jmp     short loc_1800C94FB
0x1800c949b  test    rbx, rbx
0x1800c949e  jnz     short loc_1800C94A7
0x1800c94a0  mov     eax, 80004003h
0x1800c94a5  jmp     short loc_1800C94FB
0x1800c94a7  cmp     qword ptr [rcx+30h], 0
0x1800c94ac  jnz     short loc_1800C94B5
0x1800c94ae  mov     eax, 0C00D6D60h
0x1800c94b3  jmp     short loc_1800C94FB
0x1800c94b5  mov     rcx, rbx; ppMFType
0x1800c94b8  call    cs:__imp_MFCreateMediaType
0x1800c94be  test    eax, eax
0x1800c94c0  js      short loc_1800C94FB
0x1800c94c2  mov     rcx, [rdi+30h]
0x1800c94c6  mov     rdx, [rbx]
0x1800c94c9  mov     rax, [rcx]
0x1800c94cc  mov     rax, [rax+100h]
0x1800c94d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c94d8  mov     edi, eax
0x1800c94da  test    eax, eax
0x1800c94dc  jns     short loc_1800C94F9
0x1800c94de  mov     rcx, [rbx]
0x1800c94e1  test    rcx, rcx
0x1800c94e4  jz      short loc_1800C94F9
0x1800c94e6  mov     rdx, [rcx]
0x1800c94e9  mov     rax, [rdx+10h]
0x1800c94ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c94f2  mov     qword ptr [rbx], 0
0x1800c94f9  mov     eax, edi
0x1800c94fb  mov     rbx, [rsp+28h+arg_0]
0x1800c9500  add     rsp, 20h
0x1800c9504  pop     rdi
0x1800c9505  retn
```
