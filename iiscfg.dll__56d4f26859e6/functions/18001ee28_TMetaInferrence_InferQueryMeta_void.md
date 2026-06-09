# TMetaInferrence::InferQueryMeta(void)

- ea: `0x18001ee28`
- end: `0x18001f026`
- name: `?InferQueryMeta@TMetaInferrence@@AEAAXXZ`
- size: `510`
- prototype: `void __fastcall(TMetaInferrence *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001e000`

## callees

- `0x180017ad8`
- `0x18001ee28`
- `0x180020c1c`
- `0x180030010`

## string_xrefs

- `0x18001f00e`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`

## pseudocode

```c
void __fastcall TMetaInferrence::InferQueryMeta(TMetaInferrence *this)
{
  unsigned int i; // edi
  unsigned int *v3; // r14
  const unsigned __int16 *v4; // rax
  const unsigned __int16 *v5; // rax
  unsigned int j; // ebx
  _DWORD *v7; // rax
  void (***v8)(_QWORD, const wchar_t *, ...); // rsi
  void (*v9)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v10; // rbx
  __int64 v11; // rax

  for ( i = 0; i < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 296LL))(*((_QWORD *)this + 1)); ++i )
  {
    v3 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 208LL))(
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
    if ( !v3[4] )
      v3[4] = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 1) + 40LL))(
                *((_QWORD *)this + 1),
                &word_180034198,
                0xFFFFFFFFLL);
    if ( v3[4] != (*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 1) + 48LL))(
                    *((_QWORD *)this + 1),
                    &word_180034198,
                    0xFFFFFFFFLL)
      && v3[4] != (*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 1) + 48LL))(
                    *((_QWORD *)this + 1),
                    L"__FILE",
                    0xFFFFFFFFLL) )
    {
      for ( j = 0;
            j < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 264LL))(*((_QWORD *)this + 1));
            ++j )
      {
        v7 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(
                         *((_QWORD *)this + 1),
                         j);
        if ( *v7 == *v3 && v7[2] == v3[4] )
          break;
      }
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 264LL))(*((_QWORD *)this + 1)) == j )
      {
        v8 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v9 = **v8;
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                v3[4]);
        v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
        v9(v8, L"Error in QueryMeta - Table (%s), No ColumnMeta.InternalName matches QueryMeta CellName (%s)", v11, v10);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x209u,
          0);
      }
    }
    if ( !v3[5] )
      v3[5] = *((_DWORD *)this + 6);
    if ( !v3[6] )
      v3[6] = *((_DWORD *)this + 6);
  }
}

```

## disassembly

```asm
0x18001ee28  push    rbx
0x18001ee2a  push    rbp
0x18001ee2b  push    rsi
0x18001ee2c  push    rdi
0x18001ee2d  push    r14
0x18001ee2f  sub     rsp, 30h
0x18001ee33  xor     esi, esi
0x18001ee35  mov     rbp, rcx
0x18001ee38  mov     edi, esi
0x18001ee3a  mov     rcx, [rbp+8]
0x18001ee3e  mov     rax, [rcx]
0x18001ee41  mov     rax, [rax+128h]
0x18001ee48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee4d  cmp     edi, eax
0x18001ee4f  jnb     loc_18001F01B
0x18001ee55  mov     rcx, [rbp+8]
0x18001ee59  mov     edx, edi
0x18001ee5b  mov     rax, [rcx]
0x18001ee5e  mov     rax, [rax+0D0h]
0x18001ee65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee6a  mov     rcx, [rbp+8]
0x18001ee6e  mov     r14, rax
0x18001ee71  mov     rax, [rcx]
0x18001ee74  mov     edx, [r14+4]
0x18001ee78  mov     rax, [rax+90h]
0x18001ee7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee84  mov     rdx, rax; unsigned __int16 *
0x18001ee87  xor     r9d, r9d; bool
0x18001ee8a  xor     r8d, r8d; unsigned __int16 *
0x18001ee8d  mov     rcx, rbp; this
0x18001ee90  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x18001ee95  mov     edx, [r14+8]
0x18001ee99  test    edx, edx
0x18001ee9b  jnz     short loc_18001EEA7
0x18001ee9d  mov     eax, [r14+4]
0x18001eea1  mov     [r14+8], eax
0x18001eea5  jmp     short loc_18001EECB
0x18001eea7  mov     rcx, [rbp+8]
0x18001eeab  mov     rax, [rcx]
0x18001eeae  mov     rax, [rax+90h]
0x18001eeb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eeba  mov     rdx, rax; unsigned __int16 *
0x18001eebd  xor     r9d, r9d; bool
0x18001eec0  xor     r8d, r8d; unsigned __int16 *
0x18001eec3  mov     rcx, rbp; this
0x18001eec6  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x18001eecb  cmp     [r14+10h], esi
0x18001eecf  jnz     short loc_18001EEF0
0x18001eed1  mov     rcx, [rbp+8]
0x18001eed5  lea     rdx, word_180034198
0x18001eedc  or      r8d, 0FFFFFFFFh
0x18001eee0  mov     rax, [rcx]
0x18001eee3  mov     rax, [rax+28h]
0x18001eee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eeec  mov     [r14+10h], eax
0x18001eef0  mov     rcx, [rbp+8]
0x18001eef4  lea     rdx, word_180034198
0x18001eefb  or      r8d, 0FFFFFFFFh
0x18001eeff  mov     rax, [rcx]
0x18001ef02  mov     rax, [rax+30h]
0x18001ef06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef0b  cmp     [r14+10h], eax
0x18001ef0f  jz      short loc_18001EF8B
0x18001ef11  mov     rcx, [rbp+8]
0x18001ef15  lea     rdx, aFile; "__FILE"
0x18001ef1c  or      r8d, 0FFFFFFFFh
0x18001ef20  mov     rax, [rcx]
0x18001ef23  mov     rax, [rax+30h]
0x18001ef27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef2c  cmp     [r14+10h], eax
0x18001ef30  jz      short loc_18001EF8B
0x18001ef32  mov     ebx, esi
0x18001ef34  mov     rcx, [rbp+8]
0x18001ef38  mov     rax, [rcx]
0x18001ef3b  mov     rax, [rax+108h]
0x18001ef42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef47  cmp     ebx, eax
0x18001ef49  jnb     short loc_18001EF74
0x18001ef4b  mov     rcx, [rbp+8]
0x18001ef4f  mov     edx, ebx
0x18001ef51  mov     rax, [rcx]
0x18001ef54  mov     rax, [rax+0B0h]
0x18001ef5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef60  mov     ecx, [r14]
0x18001ef63  cmp     [rax], ecx
0x18001ef65  jnz     short loc_18001EF70
0x18001ef67  mov     ecx, [r14+10h]
0x18001ef6b  cmp     [rax+8], ecx
0x18001ef6e  jz      short loc_18001EF74
0x18001ef70  inc     ebx
0x18001ef72  jmp     short loc_18001EF34
0x18001ef74  mov     rcx, [rbp+8]
0x18001ef78  mov     rax, [rcx]
0x18001ef7b  mov     rax, [rax+108h]
0x18001ef82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef87  cmp     eax, ebx
0x18001ef89  jz      short loc_18001EFAC
0x18001ef8b  cmp     [r14+14h], esi
0x18001ef8f  jnz     short loc_18001EF98
0x18001ef91  mov     eax, [rbp+18h]
0x18001ef94  mov     [r14+14h], eax
0x18001ef98  cmp     [r14+18h], esi
0x18001ef9c  jnz     short loc_18001EFA5
0x18001ef9e  mov     eax, [rbp+18h]
0x18001efa1  mov     [r14+18h], eax
0x18001efa5  inc     edi
0x18001efa7  jmp     loc_18001EE3A
0x18001efac  mov     rsi, [rbp+10h]
0x18001efb0  mov     rcx, [rbp+8]
0x18001efb4  mov     edx, [r14+10h]
0x18001efb8  mov     rax, [rsi]
0x18001efbb  mov     rdi, [rax]
0x18001efbe  mov     rax, [rcx]
0x18001efc1  mov     rax, [rax+90h]
0x18001efc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efcd  mov     rcx, [rbp+8]
0x18001efd1  mov     rbx, rax
0x18001efd4  mov     edx, [r14]
0x18001efd7  mov     r8, [rcx]
0x18001efda  mov     rax, [r8+90h]
0x18001efe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efe6  mov     r8, rax
0x18001efe9  lea     rdx, aErrorInQueryme; "Error in QueryMeta - Table (%s), No Col"...
0x18001eff0  mov     rax, rdi
0x18001eff3  mov     r9, rbx
0x18001eff6  mov     rcx, rsi
0x18001eff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001effe  xor     r9d, r9d; unsigned int
0x18001f001  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001f008  mov     r8d, 209h; unsigned int
0x18001f00e  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001f015  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001f01b  add     rsp, 30h
0x18001f01f  pop     r14
0x18001f021  pop     rdi
0x18001f022  pop     rsi
0x18001f023  pop     rbp
0x18001f024  pop     rbx
0x18001f025  retn
```
