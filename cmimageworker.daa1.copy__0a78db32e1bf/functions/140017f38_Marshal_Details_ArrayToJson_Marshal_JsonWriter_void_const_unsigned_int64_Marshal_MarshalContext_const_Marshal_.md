# Marshal::Details::ArrayToJson(Marshal::JsonWriter &,void const *,unsigned __int64,Marshal::MarshalContext const &,Marshal::Details::BaseTypeData const *,Marshal::Details::JsonTypeData const *,unsigned __int64)

- ea: `0x140017f38`
- end: `0x140018061`
- name: `?ArrayToJson@Details@Marshal@@YA_NAEAVJsonWriter@2@PEBX_KAEBVMarshalContext@2@PEBUBaseTypeData@12@PEBUJsonTypeData@12@2@Z`
- size: `297`
- prototype: `bool __fastcall(Marshal::Details *__hidden this, struct Marshal::JsonWriter *, const void *, unsigned __int64, const struct Marshal::MarshalContext *, const struct Marshal::Details::BaseTypeData *, const struct Marshal::Details::JsonTypeData *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140012250`
- `0x1400122a0`
- `0x1400122f0`
- `0x140012340`

## callees

- `0x140014234`
- `0x140017f38`
- `0x140034010`

## pseudocode

```c
bool __fastcall Marshal::Details::ArrayToJson(
        Marshal::Details *this,
        struct Marshal::JsonWriter *a2,
        const void *a3,
        __int64 a4,
        const struct Marshal::MarshalContext *a5,
        const struct Marshal::Details::BaseTypeData *a6,
        const struct Marshal::Details::JsonTypeData *a7)
{
  _QWORD *v9; // rcx
  const void *v10; // rbp
  unsigned __int64 v12; // r10
  bool v13; // cc
  unsigned __int64 v14; // rsi
  _QWORD *v15; // rcx
  unsigned __int64 v16; // rdx
  _QWORD *v17; // rcx
  unsigned __int64 v18; // rdx

  v9 = *(_QWORD **)this;
  v10 = a3;
  v12 = v9[2];
  if ( v12 >= v9[3] )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v9);
  }
  else
  {
    v13 = v9[3] <= 7u;
    v9[2] = v12 + 1;
    if ( !v13 )
      v9 = (_QWORD *)*v9;
    *(_DWORD *)((char *)v9 + 2 * v12) = 91;
  }
  *((_BYTE *)this + 8) = 1;
  v14 = 0;
  if ( (_QWORD)a7 * (_QWORD)v10 )
  {
    do
    {
      if ( !*((_BYTE *)this + 8) )
      {
        v15 = *(_QWORD **)this;
        v16 = *(_QWORD *)(*(_QWORD *)this + 16LL);
        if ( v16 >= *(_QWORD *)(*(_QWORD *)this + 24LL) )
        {
          std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v15);
        }
        else
        {
          v13 = v15[3] <= 7u;
          v15[2] = v16 + 1;
          if ( !v13 )
            v15 = (_QWORD *)*v15;
          *(_DWORD *)((char *)v15 + 2 * v16) = 44;
        }
      }
      *((_BYTE *)this + 8) = 0;
      (*(void (__fastcall **)(Marshal::Details *, char *, __int64))a6)(this, (char *)a2 + v14, a4);
      v14 += (unsigned __int64)a7;
    }
    while ( v14 < (_QWORD)a7 * (_QWORD)v10 );
    v10 = a3;
  }
  v17 = *(_QWORD **)this;
  v18 = *(_QWORD *)(*(_QWORD *)this + 16LL);
  if ( v18 >= *(_QWORD *)(*(_QWORD *)this + 24LL) )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v17);
  }
  else
  {
    v13 = v17[3] <= 7u;
    v17[2] = v18 + 1;
    if ( !v13 )
      v17 = (_QWORD *)*v17;
    *(_DWORD *)((char *)v17 + 2 * v18) = 93;
  }
  *((_BYTE *)this + 8) = 0;
  return v10 != 0;
}

```

## disassembly

```asm
0x140017f38  mov     [rsp+arg_0], rbx
0x140017f3d  mov     [rsp+arg_8], rbp
0x140017f42  mov     [rsp+arg_10], r8
0x140017f47  push    rsi
0x140017f48  push    rdi
0x140017f49  push    r12
0x140017f4b  push    r14
0x140017f4d  push    r15
0x140017f4f  sub     rsp, 20h
0x140017f53  mov     rbx, rcx
0x140017f56  mov     r15, r9
0x140017f59  mov     rcx, [rcx]; Src
0x140017f5c  mov     rbp, r8
0x140017f5f  mov     r12, rdx
0x140017f62  mov     r10, [rcx+10h]
0x140017f66  cmp     r10, [rcx+18h]
0x140017f6a  jnb     short loc_140017F88
0x140017f6c  cmp     qword ptr [rcx+18h], 7
0x140017f71  lea     rax, [r10+1]
0x140017f75  mov     [rcx+10h], rax
0x140017f79  jbe     short loc_140017F7E
0x140017f7b  mov     rcx, [rcx]
0x140017f7e  mov     dword ptr [rcx+r10*2], 5Bh ; '['
0x140017f86  jmp     short loc_140017F93
0x140017f88  mov     r9d, 5Bh ; '['
0x140017f8e  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x140017f93  mov     rdi, rbp
0x140017f96  mov     byte ptr [rbx+8], 1
0x140017f9a  imul    rdi, [rsp+48h+arg_30]
0x140017fa3  xor     esi, esi
0x140017fa5  test    rdi, rdi
0x140017fa8  jz      short loc_14001800C
0x140017faa  mov     r14, [rsp+48h+arg_28]
0x140017faf  lea     ebp, [rsi+2Ch]
0x140017fb2  cmp     byte ptr [rbx+8], 0
0x140017fb6  jnz     short loc_140017FE4
0x140017fb8  mov     rcx, [rbx]; Src
0x140017fbb  mov     rdx, [rcx+10h]
0x140017fbf  cmp     rdx, [rcx+18h]
0x140017fc3  jnb     short loc_140017FDC
0x140017fc5  cmp     qword ptr [rcx+18h], 7
0x140017fca  lea     rax, [rdx+1]
0x140017fce  mov     [rcx+10h], rax
0x140017fd2  jbe     short loc_140017FD7
0x140017fd4  mov     rcx, [rcx]
0x140017fd7  mov     [rcx+rdx*2], ebp
0x140017fda  jmp     short loc_140017FE4
0x140017fdc  mov     r9d, ebp
0x140017fdf  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x140017fe4  mov     byte ptr [rbx+8], 0
0x140017fe8  lea     rdx, [rsi+r12]
0x140017fec  mov     rax, [r14]
0x140017fef  mov     r8, r15
0x140017ff2  mov     rcx, rbx
0x140017ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017ffa  add     rsi, [rsp+48h+arg_30]
0x140018002  cmp     rsi, rdi
0x140018005  jb      short loc_140017FB2
0x140018007  mov     rbp, [rsp+48h+arg_10]
0x14001800c  mov     rcx, [rbx]; Src
0x14001800f  mov     rdx, [rcx+10h]
0x140018013  cmp     rdx, [rcx+18h]
0x140018017  jnb     short loc_140018034
0x140018019  cmp     qword ptr [rcx+18h], 7
0x14001801e  lea     rax, [rdx+1]
0x140018022  mov     [rcx+10h], rax
0x140018026  jbe     short loc_14001802B
0x140018028  mov     rcx, [rcx]
0x14001802b  mov     dword ptr [rcx+rdx*2], 5Dh ; ']'
0x140018032  jmp     short loc_14001803F
0x140018034  mov     r9d, 5Dh ; ']'
0x14001803a  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001803f  test    rbp, rbp
0x140018042  mov     byte ptr [rbx+8], 0
0x140018046  mov     rbx, [rsp+48h+arg_0]
0x14001804b  mov     rbp, [rsp+48h+arg_8]
0x140018050  setnz   al
0x140018053  add     rsp, 20h
0x140018057  pop     r15
0x140018059  pop     r14
0x14001805b  pop     r12
0x14001805d  pop     rdi
0x14001805e  pop     rsi
0x14001805f  retn
```
