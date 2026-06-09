# TMetaInferrence::InferIndexMeta(void)

- ea: `0x18001ec74`
- end: `0x18001ee1f`
- name: `?InferIndexMeta@TMetaInferrence@@AEAAXXZ`
- size: `427`
- prototype: `void __fastcall(TMetaInferrence *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001e000`

## callees

- `0x180017ad8`
- `0x18001ec74`
- `0x180020c1c`
- `0x180030010`

## string_xrefs

- `0x18001ee05`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`

## pseudocode

```c
void __fastcall TMetaInferrence::InferIndexMeta(TMetaInferrence *this)
{
  unsigned int i; // edi
  unsigned int *v3; // r14
  const unsigned __int16 *v4; // rax
  const unsigned __int16 *v5; // rax
  unsigned int v6; // ebx
  unsigned int *v7; // r15
  _DWORD *v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  bool v12; // zf
  void (***v13)(_QWORD, const wchar_t *, ...); // rsi
  void (*v14)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v15; // rbx
  __int64 v16; // rax

  for ( i = 0; i < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 288LL))(*((_QWORD *)this + 1)); ++i )
  {
    v3 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 200LL))(
                           *((_QWORD *)this + 1),
                           i);
    v4 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                                     *((_QWORD *)this + 1),
                                     v3[1]);
    TMetaInferrence::ValidateStringAsLegalVariableName(this, v4, 0, 0);
    if ( v3[2] )
    {
      v5 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      TMetaInferrence::ValidateStringAsLegalVariableName(this, v5, 0, 0);
    }
    else
    {
      v3[2] = v3[1];
    }
    v6 = 0;
    v7 = v3 + 4;
    while ( v6 < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 264LL))(*((_QWORD *)this + 1)) )
    {
      v8 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(
                       *((_QWORD *)this + 1),
                       v6);
      v7 = v3 + 4;
      if ( v8[2] == v3[4] && *v8 == *v3 )
        break;
      ++v6;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 264LL))(*((_QWORD *)this + 1));
    v10 = *((_QWORD *)this + 1);
    if ( v9 == v6 )
    {
      v13 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v14 = **v13;
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 144LL))(v10, *v7);
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
      v14(
        v13,
        L"Error in IndexMeta - Table (%s), No ColumnMeta.InternalName matches IndexMeta ColumnInternalName (%s)",
        v16,
        v15);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x1C1u,
        0);
    }
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 176LL))(v10, v6);
    v12 = v3[5] == 0;
    v3[3] = *(_DWORD *)(v11 + 4);
    if ( v12 )
      v3[5] = *((_DWORD *)this + 6);
  }
}

```

## disassembly

```asm
0x18001ec74  push    rbx
0x18001ec76  push    rbp
0x18001ec77  push    rsi
0x18001ec78  push    rdi
0x18001ec79  push    r14
0x18001ec7b  push    r15
0x18001ec7d  sub     rsp, 38h
0x18001ec81  mov     rbp, rcx
0x18001ec84  xor     edi, edi
0x18001ec86  mov     rcx, [rbp+8]
0x18001ec8a  mov     rax, [rcx]
0x18001ec8d  mov     rax, [rax+120h]
0x18001ec94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec99  cmp     edi, eax
0x18001ec9b  jnb     loc_18001EE12
0x18001eca1  mov     rcx, [rbp+8]
0x18001eca5  mov     edx, edi
0x18001eca7  mov     rax, [rcx]
0x18001ecaa  mov     rax, [rax+0C8h]
0x18001ecb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecb6  mov     rcx, [rbp+8]
0x18001ecba  mov     r14, rax
0x18001ecbd  mov     rdx, [rcx]
0x18001ecc0  mov     rax, [rdx+90h]
0x18001ecc7  mov     edx, [r14+4]
0x18001eccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecd0  mov     rdx, rax; unsigned __int16 *
0x18001ecd3  xor     r9d, r9d; bool
0x18001ecd6  xor     r8d, r8d; unsigned __int16 *
0x18001ecd9  mov     rcx, rbp; this
0x18001ecdc  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x18001ece1  mov     edx, [r14+8]
0x18001ece5  test    edx, edx
0x18001ece7  jnz     short loc_18001ECF3
0x18001ece9  mov     eax, [r14+4]
0x18001eced  mov     [r14+8], eax
0x18001ecf1  jmp     short loc_18001ED17
0x18001ecf3  mov     rcx, [rbp+8]
0x18001ecf7  mov     rax, [rcx]
0x18001ecfa  mov     rax, [rax+90h]
0x18001ed01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed06  mov     rdx, rax; unsigned __int16 *
0x18001ed09  xor     r9d, r9d; bool
0x18001ed0c  xor     r8d, r8d; unsigned __int16 *
0x18001ed0f  mov     rcx, rbp; this
0x18001ed12  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x18001ed17  xor     ebx, ebx
0x18001ed19  lea     r15, [r14+10h]
0x18001ed1d  mov     rcx, [rbp+8]
0x18001ed21  mov     rax, [rcx]
0x18001ed24  mov     rax, [rax+108h]
0x18001ed2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed30  cmp     ebx, eax
0x18001ed32  jnb     short loc_18001ED60
0x18001ed34  mov     rcx, [rbp+8]
0x18001ed38  mov     edx, ebx
0x18001ed3a  mov     rax, [rcx]
0x18001ed3d  mov     rax, [rax+0B0h]
0x18001ed44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed49  lea     r15, [r14+10h]
0x18001ed4d  mov     ecx, [r15]
0x18001ed50  cmp     [rax+8], ecx
0x18001ed53  jnz     short loc_18001ED5C
0x18001ed55  mov     ecx, [r14]
0x18001ed58  cmp     [rax], ecx
0x18001ed5a  jz      short loc_18001ED60
0x18001ed5c  inc     ebx
0x18001ed5e  jmp     short loc_18001ED1D
0x18001ed60  mov     rcx, [rbp+8]
0x18001ed64  mov     rax, [rcx]
0x18001ed67  mov     rax, [rax+108h]
0x18001ed6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed73  mov     rcx, [rbp+8]
0x18001ed77  cmp     eax, ebx
0x18001ed79  jz      short loc_18001EDA8
0x18001ed7b  mov     rax, [rcx]
0x18001ed7e  mov     edx, ebx
0x18001ed80  mov     rax, [rax+0B0h]
0x18001ed87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed8c  cmp     dword ptr [r14+14h], 0
0x18001ed91  mov     ecx, [rax+4]
0x18001ed94  mov     [r14+0Ch], ecx
0x18001ed98  jnz     short loc_18001EDA1
0x18001ed9a  mov     eax, [rbp+18h]
0x18001ed9d  mov     [r14+14h], eax
0x18001eda1  inc     edi
0x18001eda3  jmp     loc_18001EC86
0x18001eda8  mov     rsi, [rbp+10h]
0x18001edac  mov     edx, [r15]
0x18001edaf  mov     rax, [rsi]
0x18001edb2  mov     rdi, [rax]
0x18001edb5  mov     rax, [rcx]
0x18001edb8  mov     rax, [rax+90h]
0x18001edbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edc4  mov     rcx, [rbp+8]
0x18001edc8  mov     rbx, rax
0x18001edcb  mov     rdx, [rcx]
0x18001edce  mov     rax, [rdx+90h]
0x18001edd5  mov     edx, [r14]
0x18001edd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eddd  mov     r8, rax
0x18001ede0  lea     rdx, aErrorInIndexme; "Error in IndexMeta - Table (%s), No Col"...
0x18001ede7  mov     rax, rdi
0x18001edea  mov     r9, rbx
0x18001eded  mov     rcx, rsi
0x18001edf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edf5  xor     r9d, r9d; unsigned int
0x18001edf8  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001edff  mov     r8d, 1C1h; unsigned int
0x18001ee05  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001ee0c  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001ee12  add     rsp, 38h
0x18001ee16  pop     r15
0x18001ee18  pop     r14
0x18001ee1a  pop     rdi
0x18001ee1b  pop     rsi
0x18001ee1c  pop     rbp
0x18001ee1d  pop     rbx
0x18001ee1e  retn
```
