# TMetaInferrence::InferTagMeta(void)

- ea: `0x180020a68`
- end: `0x180020c16`
- name: `?InferTagMeta@TMetaInferrence@@AEAAXXZ`
- size: `430`
- prototype: `void __fastcall(TMetaInferrence *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001e000`

## callees

- `0x180017ad8`
- `0x180020a68`
- `0x180020c1c`
- `0x180030010`

## string_xrefs

- `0x180020bfc`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`

## pseudocode

```c
void __fastcall TMetaInferrence::InferTagMeta(TMetaInferrence *this)
{
  unsigned int i; // esi
  unsigned int *v3; // rax
  _DWORD *v4; // rbx
  unsigned int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rbp
  const unsigned __int16 *v8; // rax
  const unsigned __int16 *v9; // rbx
  const unsigned __int16 *v10; // rax
  void (***v11)(_QWORD, const wchar_t *, ...); // rsi
  void (*v12)(_QWORD, const wchar_t *, ...); // r14
  unsigned int v13; // ebp
  const wchar_t *v14; // rax

  for ( i = 0; i < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 328LL))(*((_QWORD *)this + 1)); ++i )
  {
    v3 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 240LL))(
                           *((_QWORD *)this + 1),
                           i);
    v4 = v3;
    if ( !v3[2] )
    {
      v11 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v12 = **v11;
      if ( v3[1] )
        v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1));
      else
        v13 = -1;
      if ( *v4 )
        v14 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      else
        v14 = L"<unknown>";
      v12(v11, L"Error - TagMeta.InternalName is missing on Table (%s), ColumnIndex (%d).", v14, v13);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x402u,
        0);
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 368LL))(
           *((_QWORD *)this + 1),
           *v3,
           v3[1],
           0);
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(*((_QWORD *)this + 1), v5);
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
           *((_QWORD *)this + 1),
           *(unsigned int *)(v6 + 48))
       & 0x80;
    v8 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                                     *((_QWORD *)this + 1),
                                     (unsigned int)v4[2]);
    TMetaInferrence::ValidateStringAsLegalVariableName(
      this,
      v8,
      L"_abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789",
      (_DWORD)v7 == 0);
    if ( v4[3] )
    {
      v9 = L"_abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789[]";
      if ( (_DWORD)v7 )
        v9 = L"_abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
      v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      TMetaInferrence::ValidateStringAsLegalVariableName(this, v10, v9, (_DWORD)v7 == 0);
    }
    else
    {
      v4[3] = v4[2];
    }
  }
}

```

## disassembly

```asm
0x180020a68  push    rbx
0x180020a6a  push    rbp
0x180020a6b  push    rsi
0x180020a6c  push    rdi
0x180020a6d  push    r14
0x180020a6f  push    r15
0x180020a71  sub     rsp, 38h
0x180020a75  mov     rdi, rcx
0x180020a78  lea     r15, aAbcdefghijklmn; "_abcdefghijklmnopqrstuvwxyzABCDEFGHIJKL"...
0x180020a7f  xor     esi, esi
0x180020a81  mov     rcx, [rdi+8]
0x180020a85  mov     rax, [rcx]
0x180020a88  mov     rax, [rax+148h]
0x180020a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a94  cmp     esi, eax
0x180020a96  jnb     loc_180020C09
0x180020a9c  mov     rcx, [rdi+8]
0x180020aa0  mov     edx, esi
0x180020aa2  mov     rax, [rcx]
0x180020aa5  mov     rax, [rax+0F0h]
0x180020aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ab1  mov     rbx, rax
0x180020ab4  cmp     dword ptr [rax+8], 0
0x180020ab8  jz      loc_180020B87
0x180020abe  mov     rcx, [rdi+8]
0x180020ac2  xor     r9d, r9d
0x180020ac5  mov     r8d, [rbx+4]
0x180020ac9  mov     rdx, [rcx]
0x180020acc  mov     rax, [rdx+170h]
0x180020ad3  mov     edx, [rbx]
0x180020ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ada  mov     rcx, [rdi+8]
0x180020ade  mov     r8d, eax
0x180020ae1  mov     rdx, [rcx]
0x180020ae4  mov     rax, [rdx+0B0h]
0x180020aeb  mov     edx, r8d
0x180020aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020af3  mov     rcx, [rdi+8]
0x180020af7  mov     r8, rax
0x180020afa  mov     rdx, [rcx]
0x180020afd  mov     rax, [rdx+98h]
0x180020b04  mov     edx, [r8+30h]
0x180020b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b0d  mov     rcx, [rdi+8]
0x180020b11  mov     ebp, eax
0x180020b13  and     ebp, 80h
0x180020b19  setz    r14b
0x180020b1d  mov     rdx, [rcx]
0x180020b20  mov     rax, [rdx+90h]
0x180020b27  mov     edx, [rbx+8]
0x180020b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b2f  mov     r9b, r14b; bool
0x180020b32  mov     r8, r15; unsigned __int16 *
0x180020b35  mov     rdx, rax; unsigned __int16 *
0x180020b38  mov     rcx, rdi; this
0x180020b3b  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x180020b40  mov     edx, [rbx+0Ch]
0x180020b43  test    edx, edx
0x180020b45  jnz     short loc_180020B4F
0x180020b47  mov     eax, [rbx+8]
0x180020b4a  mov     [rbx+0Ch], eax
0x180020b4d  jmp     short loc_180020B80
0x180020b4f  mov     rcx, [rdi+8]
0x180020b53  lea     rbx, aAbcdefghijklmn_0; "_abcdefghijklmnopqrstuvwxyzABCDEFGHIJKL"...
0x180020b5a  test    ebp, ebp
0x180020b5c  cmovnz  rbx, r15
0x180020b60  mov     rax, [rcx]
0x180020b63  mov     rax, [rax+90h]
0x180020b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b6f  mov     rdx, rax; unsigned __int16 *
0x180020b72  mov     r9b, r14b; bool
0x180020b75  mov     r8, rbx; unsigned __int16 *
0x180020b78  mov     rcx, rdi; this
0x180020b7b  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x180020b80  inc     esi
0x180020b82  jmp     loc_180020A81
0x180020b87  mov     rsi, [rdi+10h]
0x180020b8b  mov     edx, [rbx+4]
0x180020b8e  mov     rax, [rsi]
0x180020b91  mov     r14, [rax]
0x180020b94  test    edx, edx
0x180020b96  jz      short loc_180020BAF
0x180020b98  mov     rcx, [rdi+8]
0x180020b9c  mov     rax, [rcx]
0x180020b9f  mov     rax, [rax+98h]
0x180020ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bab  mov     ebp, eax
0x180020bad  jmp     short loc_180020BB2
0x180020baf  or      ebp, 0FFFFFFFFh
0x180020bb2  mov     edx, [rbx]
0x180020bb4  test    edx, edx
0x180020bb6  jz      short loc_180020BCD
0x180020bb8  mov     rcx, [rdi+8]
0x180020bbc  mov     rax, [rcx]
0x180020bbf  mov     rax, [rax+90h]
0x180020bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bcb  jmp     short loc_180020BD4
0x180020bcd  lea     rax, aUnknown; "<unknown>"
0x180020bd4  mov     r8, rax
0x180020bd7  lea     rdx, aErrorTagmetaIn; "Error - TagMeta.InternalName is missing"...
0x180020bde  mov     rax, r14
0x180020be1  mov     r9d, ebp
0x180020be4  mov     rcx, rsi
0x180020be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bec  xor     r9d, r9d; unsigned int
0x180020bef  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x180020bf6  mov     r8d, 402h; unsigned int
0x180020bfc  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180020c03  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180020c09  add     rsp, 38h
0x180020c0d  pop     r15
0x180020c0f  pop     r14
0x180020c11  pop     rdi
0x180020c12  pop     rsi
0x180020c13  pop     rbp
0x180020c14  pop     rbx
0x180020c15  retn
```
