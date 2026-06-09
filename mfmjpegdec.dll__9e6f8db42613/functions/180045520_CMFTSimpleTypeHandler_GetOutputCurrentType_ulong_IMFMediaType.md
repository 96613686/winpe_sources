# CMFTSimpleTypeHandler::GetOutputCurrentType(ulong,IMFMediaType * *)

- ea: `0x180045520`
- end: `0x1800455a6`
- name: `?GetOutputCurrentType@CMFTSimpleTypeHandler@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `134`
- prototype: `int(CMFTSimpleTypeHandler *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180045520`
- `0x180070010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180045558`
- `MFPlat!MFCreateMediaType` at `0x180045558`

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
0x180045520  mov     [rsp+arg_0], rbx
0x180045525  push    rdi
0x180045526  sub     rsp, 20h
0x18004552a  mov     rbx, r8
0x18004552d  mov     rdi, rcx
0x180045530  test    edx, edx
0x180045532  jz      short loc_18004553B
0x180045534  mov     eax, 0C00D36B3h
0x180045539  jmp     short loc_18004559B
0x18004553b  test    rbx, rbx
0x18004553e  jnz     short loc_180045547
0x180045540  mov     eax, 80004003h
0x180045545  jmp     short loc_18004559B
0x180045547  cmp     qword ptr [rcx+50h], 0
0x18004554c  jnz     short loc_180045555
0x18004554e  mov     eax, 0C00D6D60h
0x180045553  jmp     short loc_18004559B
0x180045555  mov     rcx, rbx; ppMFType
0x180045558  call    cs:__imp_MFCreateMediaType
0x18004555e  test    eax, eax
0x180045560  js      short loc_18004559B
0x180045562  mov     rcx, [rdi+50h]
0x180045566  mov     rdx, [rbx]
0x180045569  mov     rax, [rcx]
0x18004556c  mov     rax, [rax+100h]
0x180045573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045578  mov     edi, eax
0x18004557a  test    eax, eax
0x18004557c  jns     short loc_180045599
0x18004557e  mov     rcx, [rbx]
0x180045581  test    rcx, rcx
0x180045584  jz      short loc_180045599
0x180045586  mov     rdx, [rcx]
0x180045589  mov     rax, [rdx+10h]
0x18004558d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045592  mov     qword ptr [rbx], 0
0x180045599  mov     eax, edi
0x18004559b  mov     rbx, [rsp+28h+arg_0]
0x1800455a0  add     rsp, 20h
0x1800455a4  pop     rdi
0x1800455a5  retn
```
