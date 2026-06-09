# Marshal::Details::ObjectToJson(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::JsonTypeData const *>)

- ea: `0x14001a9a8`
- end: `0x14001ac1c`
- name: `?ObjectToJson@Details@Marshal@@YA_NAEAVJsonWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUJsonTypeData@Details@Marshal@@@12@@Z`
- size: `628`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140011ffc`
- `0x140012070`
- `0x1400120e0`
- `0x140012150`

## callees

- `0x140014234`
- `0x140014350`
- `0x14001a9a8`
- `0x14001f10c`
- `0x140034010`

## pseudocode

```c
bool __fastcall Marshal::Details::ObjectToJson(_BYTE *a1, __int64 a2, __int64 a3, __int64 *a4, _QWORD *a5, _QWORD *a6)
{
  _QWORD *v7; // rcx
  unsigned __int64 v9; // rdi
  bool v10; // cc
  __int64 v11; // r12
  __int64 v12; // r15
  __int64 v13; // r14
  __int64 v14; // rbp
  __int64 v15; // r8
  __int64 v16; // rdi
  _QWORD *v17; // rcx
  char v18; // r13
  unsigned __int64 v19; // rsi
  unsigned __int64 v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rcx
  unsigned __int64 v23; // rdx
  char v24; // al
  _QWORD *v25; // r8
  unsigned __int64 v26; // rcx
  _WORD *v27; // rdi
  __int64 i; // rcx
  _QWORD *v29; // rcx
  unsigned __int64 v30; // rdx
  _QWORD v32[9]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v33; // [rsp+98h] [rbp+10h]

  v33 = a2;
  v7 = *(_QWORD **)a1;
  v9 = v7[2];
  if ( v9 >= v7[3] )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v7);
    a2 = v33;
  }
  else
  {
    v10 = v7[3] <= 7u;
    v7[2] = v9 + 1;
    if ( !v10 )
      v7 = (_QWORD *)*v7;
    *(_DWORD *)((char *)v7 + 2 * v9) = 123;
  }
  v11 = a4[1];
  v12 = 0;
  v13 = *a4;
  v14 = 0;
  a1[8] = 1;
  if ( v13 != v11 )
  {
    v15 = 44;
    while ( 1 )
    {
      v16 = a2 + *(unsigned int *)(v13 + 8);
      if ( (*(_BYTE *)(v13 + 12) & 1) == 0 )
        goto LABEL_11;
      if ( !(**(unsigned __int8 (__fastcall ***)(__int64, _QWORD, __int64))(*a5 + 8 * v12))(
              v16,
              *(_QWORD *)(v13 + 16),
              44) )
        break;
LABEL_40:
      a2 = v33;
      ++v12;
      v13 += 32;
      v15 = 44;
      if ( v13 == v11 )
        goto LABEL_41;
    }
    v15 = 44;
LABEL_11:
    v17 = *(_QWORD **)a1;
    v18 = a1[8];
    v19 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
    if ( !v18 )
    {
      v20 = v17[3];
      if ( v19 >= v20 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v17);
      }
      else
      {
        v17[2] = v19 + 1;
        if ( v20 > 7 )
          v17 = (_QWORD *)*v17;
        *(_DWORD *)((char *)v17 + 2 * v19) = 44;
      }
    }
    a1[8] = 0;
    v21 = -1;
    do
      ++v21;
    while ( *(_WORD *)(*(_QWORD *)v13 + 2 * v21) );
    v32[0] = *(_QWORD *)v13;
    v32[1] = v21;
    Marshal::JsonWriter::WriteValue(a1, v32, v15);
    v22 = *(_QWORD **)a1;
    v23 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
    if ( v23 >= *(_QWORD *)(*(_QWORD *)a1 + 24LL) )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v22);
    }
    else
    {
      v10 = v22[3] <= 7u;
      v22[2] = v23 + 1;
      if ( !v10 )
        v22 = (_QWORD *)*v22;
      *(_DWORD *)((char *)v22 + 2 * v23) = 58;
    }
    v24 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, __int64))(*a6 + 8 * v12))(a1, v16, a3);
    if ( (*(_BYTE *)(v13 + 12) & 1) == 0 || v24 )
    {
      ++v14;
      goto LABEL_40;
    }
    v25 = *(_QWORD **)a1;
    v26 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
    if ( v19 > v26 )
    {
      if ( v19 - v26 > v25[3] - v26 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(*(void **)a1);
        goto LABEL_38;
      }
      v10 = v25[3] <= 7u;
      v25[2] = v19;
      if ( !v10 )
        v25 = (_QWORD *)*v25;
      v27 = (_WORD *)v25 + v26;
      if ( v19 != v26 )
      {
        for ( i = v19 - v26; i; --i )
          *v27++ = 0;
      }
    }
    else
    {
      v25[2] = v19;
      if ( v25[3] > 7u )
        v25 = (_QWORD *)*v25;
    }
    *((_WORD *)v25 + v19) = 0;
LABEL_38:
    a1[8] = v18;
    goto LABEL_40;
  }
LABEL_41:
  v29 = *(_QWORD **)a1;
  v30 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
  if ( v30 >= *(_QWORD *)(*(_QWORD *)a1 + 24LL) )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v29);
  }
  else
  {
    v10 = v29[3] <= 7u;
    v29[2] = v30 + 1;
    if ( !v10 )
      v29 = (_QWORD *)*v29;
    *(_DWORD *)((char *)v29 + 2 * v30) = 125;
  }
  a1[8] = 0;
  return v14 != 0;
}

```

## disassembly

```asm
0x14001a9a8  mov     [rsp+arg_0], rbx
0x14001a9ad  mov     [rsp+arg_10], r8
0x14001a9b2  mov     [rsp+arg_8], rdx
0x14001a9b7  push    rbp
0x14001a9b8  push    rsi
0x14001a9b9  push    rdi
0x14001a9ba  push    r12
0x14001a9bc  push    r13
0x14001a9be  push    r14
0x14001a9c0  push    r15
0x14001a9c2  sub     rsp, 50h
0x14001a9c6  mov     rbx, rcx
0x14001a9c9  xor     r10d, r10d
0x14001a9cc  mov     rcx, [rcx]; Src
0x14001a9cf  mov     r14, r9
0x14001a9d2  mov     rdi, [rcx+10h]
0x14001a9d6  cmp     rdi, [rcx+18h]
0x14001a9da  jnb     short loc_14001A9F7
0x14001a9dc  cmp     qword ptr [rcx+18h], 7
0x14001a9e1  lea     rax, [rdi+1]
0x14001a9e5  mov     [rcx+10h], rax
0x14001a9e9  jbe     short loc_14001A9EE
0x14001a9eb  mov     rcx, [rcx]
0x14001a9ee  mov     dword ptr [rcx+rdi*2], 7Bh ; '{'
0x14001a9f5  jmp     short loc_14001AA0D
0x14001a9f7  mov     r9d, 7Bh ; '{'
0x14001a9fd  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001aa02  mov     rdx, [rsp+88h+arg_8]
0x14001aa0a  xor     r10d, r10d
0x14001aa0d  mov     r12, [r14+8]
0x14001aa11  mov     r15, r10
0x14001aa14  mov     r14, [r14]
0x14001aa17  mov     rbp, r10
0x14001aa1a  mov     byte ptr [rbx+8], 1
0x14001aa1e  cmp     r14, r12
0x14001aa21  jz      loc_14001ABC3
0x14001aa27  mov     r8d, 2Ch ; ','
0x14001aa2d  mov     edi, [r14+8]
0x14001aa31  add     rdi, rdx
0x14001aa34  test    byte ptr [r14+0Ch], 1
0x14001aa39  jz      short loc_14001AA68
0x14001aa3b  mov     rax, [rsp+88h+arg_20]
0x14001aa43  mov     rdx, [r14+10h]
0x14001aa47  mov     rax, [rax]
0x14001aa4a  mov     rcx, [rax+r15*8]
0x14001aa4e  mov     rax, [rcx]
0x14001aa51  mov     rcx, rdi
0x14001aa54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aa59  xor     r10d, r10d
0x14001aa5c  test    al, al
0x14001aa5e  jnz     loc_14001ABA5
0x14001aa64  lea     r8d, [r10+2Ch]
0x14001aa68  mov     rcx, [rbx]; Src
0x14001aa6b  mov     r13b, [rbx+8]
0x14001aa6f  mov     rsi, [rcx+10h]
0x14001aa73  test    r13b, r13b
0x14001aa76  jnz     short loc_14001AAA6
0x14001aa78  mov     rdx, [rcx+18h]
0x14001aa7c  cmp     rsi, rdx
0x14001aa7f  jnb     short loc_14001AA9B
0x14001aa81  lea     rax, [rsi+1]
0x14001aa85  mov     [rcx+10h], rax
0x14001aa89  cmp     rdx, 7
0x14001aa8d  jbe     short loc_14001AA92
0x14001aa8f  mov     rcx, [rcx]
0x14001aa92  mov     dword ptr [rcx+rsi*2], 2Ch ; ','
0x14001aa99  jmp     short loc_14001AAA6
0x14001aa9b  mov     r9d, r8d
0x14001aa9e  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001aaa3  xor     r10d, r10d
0x14001aaa6  mov     [rbx+8], r10b
0x14001aaaa  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001aaae  mov     rcx, [r14]
0x14001aab1  inc     rax
0x14001aab4  cmp     [rcx+rax*2], r10w
0x14001aab9  jnz     short loc_14001AAB1
0x14001aabb  mov     [rsp+88h+var_48], rcx
0x14001aac0  lea     rdx, [rsp+88h+var_48]
0x14001aac5  mov     rcx, rbx
0x14001aac8  mov     [rsp+88h+var_40], rax
0x14001aacd  call    ?WriteValue@JsonWriter@Marshal@@QEAAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Marshal::JsonWriter::WriteValue(std::basic_string_view<ushort>)
0x14001aad2  mov     rcx, [rbx]; Src
0x14001aad5  mov     rdx, [rcx+10h]
0x14001aad9  cmp     rdx, [rcx+18h]
0x14001aadd  jnb     short loc_14001AAFA
0x14001aadf  cmp     qword ptr [rcx+18h], 7
0x14001aae4  lea     rax, [rdx+1]
0x14001aae8  mov     [rcx+10h], rax
0x14001aaec  jbe     short loc_14001AAF1
0x14001aaee  mov     rcx, [rcx]
0x14001aaf1  mov     dword ptr [rcx+rdx*2], 3Ah ; ':'
0x14001aaf8  jmp     short loc_14001AB05
0x14001aafa  mov     r9d, 3Ah ; ':'
0x14001ab00  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001ab05  mov     rax, [rsp+88h+arg_28]
0x14001ab0d  mov     rdx, rdi
0x14001ab10  mov     r8, [rsp+88h+arg_10]
0x14001ab18  mov     rax, [rax]
0x14001ab1b  mov     rcx, [rax+r15*8]
0x14001ab1f  mov     rax, [rcx]
0x14001ab22  mov     rcx, rbx
0x14001ab25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ab2a  xor     r10d, r10d
0x14001ab2d  test    byte ptr [r14+0Ch], 1
0x14001ab32  jz      short loc_14001ABA2
0x14001ab34  test    al, al
0x14001ab36  jnz     short loc_14001ABA2
0x14001ab38  mov     r8, [rbx]
0x14001ab3b  mov     rcx, [r8+10h]
0x14001ab3f  cmp     rsi, rcx
0x14001ab42  ja      short loc_14001AB54
0x14001ab44  mov     [r8+10h], rsi
0x14001ab48  cmp     qword ptr [r8+18h], 7
0x14001ab4d  jbe     short loc_14001AB87
0x14001ab4f  mov     r8, [r8]
0x14001ab52  jmp     short loc_14001AB87
0x14001ab54  mov     rax, [r8+18h]
0x14001ab58  mov     rdx, rsi
0x14001ab5b  sub     rdx, rcx
0x14001ab5e  sub     rax, rcx
0x14001ab61  cmp     rdx, rax
0x14001ab64  ja      short loc_14001AB8E
0x14001ab66  cmp     qword ptr [r8+18h], 7
0x14001ab6b  mov     [r8+10h], rsi
0x14001ab6f  jbe     short loc_14001AB74
0x14001ab71  mov     r8, [r8]
0x14001ab74  lea     rdi, [r8+rcx*2]
0x14001ab78  test    rdx, rdx
0x14001ab7b  jz      short loc_14001AB87
0x14001ab7d  movzx   eax, r10w
0x14001ab81  mov     rcx, rdx
0x14001ab84  rep stosw
0x14001ab87  mov     [r8+rsi*2], r10w
0x14001ab8c  jmp     short loc_14001AB9C
0x14001ab8e  mov     r9, rdx
0x14001ab91  mov     rcx, r8; Src
0x14001ab94  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x14001ab99  xor     r10d, r10d
0x14001ab9c  mov     [rbx+8], r13b
0x14001aba0  jmp     short loc_14001ABA5
0x14001aba2  inc     rbp
0x14001aba5  mov     rdx, [rsp+88h+arg_8]
0x14001abad  inc     r15
0x14001abb0  add     r14, 20h ; ' '
0x14001abb4  mov     r8d, 2Ch ; ','
0x14001abba  cmp     r14, r12
0x14001abbd  jnz     loc_14001AA2D
0x14001abc3  mov     rcx, [rbx]; Src
0x14001abc6  mov     rdx, [rcx+10h]
0x14001abca  cmp     rdx, [rcx+18h]
0x14001abce  jnb     short loc_14001ABEB
0x14001abd0  cmp     qword ptr [rcx+18h], 7
0x14001abd5  lea     rax, [rdx+1]
0x14001abd9  mov     [rcx+10h], rax
0x14001abdd  jbe     short loc_14001ABE2
0x14001abdf  mov     rcx, [rcx]
0x14001abe2  mov     dword ptr [rcx+rdx*2], 7Dh ; '}'
0x14001abe9  jmp     short loc_14001ABF9
0x14001abeb  mov     r9d, 7Dh ; '}'
0x14001abf1  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001abf6  xor     r10d, r10d
0x14001abf9  test    rbp, rbp
0x14001abfc  mov     [rbx+8], r10b
0x14001ac00  mov     rbx, [rsp+88h+arg_0]
0x14001ac08  setnz   al
0x14001ac0b  add     rsp, 50h
0x14001ac0f  pop     r15
0x14001ac11  pop     r14
0x14001ac13  pop     r13
0x14001ac15  pop     r12
0x14001ac17  pop     rdi
0x14001ac18  pop     rsi
0x14001ac19  pop     rbp
0x14001ac1a  retn
```
