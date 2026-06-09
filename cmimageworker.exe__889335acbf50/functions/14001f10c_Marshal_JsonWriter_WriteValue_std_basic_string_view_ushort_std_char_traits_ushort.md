# Marshal::JsonWriter::WriteValue(std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x14001f10c`
- end: `0x14001f365`
- name: `?WriteValue@JsonWriter@Marshal@@QEAAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `601`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140012884`
- `0x14001a9a8`

## callees

- `0x140014234`
- `0x140016398`
- `0x14001f10c`

## pseudocode

```c
__int64 __fastcall Marshal::JsonWriter::WriteValue(void **a1, __int64 *a2)
{
  _QWORD *v4; // rcx
  unsigned __int64 v5; // r8
  bool v6; // cc
  unsigned __int64 v7; // r14
  __int64 v8; // rdi
  unsigned __int64 i; // rbp
  unsigned int v10; // edx
  _QWORD *v11; // rcx
  unsigned __int64 v12; // r8
  _QWORD *v13; // rcx
  unsigned __int16 v14; // ax
  unsigned __int64 v15; // rdx
  __int16 v16; // r9
  unsigned __int64 v17; // rdx
  _QWORD *v18; // rcx
  unsigned __int64 v19; // rdx
  wchar_t *v20; // rdx
  _QWORD *v21; // rcx
  unsigned __int64 v22; // rdx
  __int64 result; // rax

  v4 = *a1;
  v5 = v4[2];
  if ( v5 >= v4[3] )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v4);
  }
  else
  {
    v6 = v4[3] <= 7u;
    v4[2] = v5 + 1;
    if ( !v6 )
      v4 = (_QWORD *)*v4;
    *(_DWORD *)((char *)v4 + 2 * v5) = 34;
  }
  v7 = a2[1];
  if ( v7 )
  {
    v8 = *a2;
    for ( i = 0; i < v7; ++i )
    {
      v10 = *(unsigned __int16 *)(v8 + 2 * i);
      if ( v10 < 0x20 || (_WORD)v10 == 92 || (_WORD)v10 == 34 )
      {
        switch ( v10 )
        {
          case 8u:
            v20 = L"\\b";
            goto LABEL_44;
          case 9u:
            v20 = L"\\t";
            goto LABEL_44;
          case 0xAu:
            v20 = L"\\n";
            goto LABEL_44;
          case 0xCu:
            v20 = L"\\f";
            goto LABEL_44;
          case 0xDu:
            v20 = L"\\r";
LABEL_44:
            std::wstring::operator+=(*a1, v20);
            continue;
          case 0x22u:
          case 0x5Cu:
            v18 = *a1;
            v19 = *((_QWORD *)*a1 + 2);
            if ( v19 >= *((_QWORD *)*a1 + 3) )
            {
              std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v18);
            }
            else
            {
              v6 = v18[3] <= 7u;
              v18[2] = v19 + 1;
              if ( !v6 )
                v18 = (_QWORD *)*v18;
              *(_DWORD *)((char *)v18 + 2 * v19) = 92;
            }
            v16 = *(_WORD *)(v8 + 2 * i);
            break;
          default:
            std::wstring::operator+=(*a1, L"\\u00");
            v13 = *a1;
            v14 = (unsigned __int8)*(_WORD *)(v8 + 2 * i) >> 4;
            v15 = *((_QWORD *)*a1 + 2);
            if ( v15 >= *((_QWORD *)*a1 + 3) )
            {
              std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v13);
            }
            else
            {
              v6 = v13[3] <= 7u;
              v13[2] = v15 + 1;
              if ( !v6 )
                v13 = (_QWORD *)*v13;
              *((_WORD *)v13 + v15) = v14 + (v14 < 0xAu ? 48 : 87);
              *((_WORD *)v13 + v15 + 1) = 0;
            }
            v16 = (*(_WORD *)(v8 + 2 * i) & 0xF) + ((*(_WORD *)(v8 + 2 * i) & 0xFu) < 0xA ? 48 : 87);
            break;
        }
        v11 = *a1;
        v17 = *((_QWORD *)*a1 + 2);
        if ( v17 < *((_QWORD *)*a1 + 3) )
        {
          v11[2] = v17 + 1;
          if ( v11[3] > 7u )
            v11 = (_QWORD *)*v11;
          *((_WORD *)v11 + v17) = v16;
          *((_WORD *)v11 + v17 + 1) = 0;
          continue;
        }
      }
      else
      {
        v11 = *a1;
        v12 = *((_QWORD *)*a1 + 2);
        if ( v12 < *((_QWORD *)*a1 + 3) )
        {
          v6 = v11[3] <= 7u;
          v11[2] = v12 + 1;
          if ( !v6 )
            v11 = (_QWORD *)*v11;
          *((_WORD *)v11 + v12) = v10;
          *((_WORD *)v11 + v12 + 1) = 0;
          continue;
        }
      }
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v11);
    }
  }
  v21 = *a1;
  v22 = *((_QWORD *)*a1 + 2);
  if ( v22 >= *((_QWORD *)*a1 + 3) )
    return std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v21);
  v6 = v21[3] <= 7u;
  result = v22 + 1;
  v21[2] = v22 + 1;
  if ( !v6 )
    v21 = (_QWORD *)*v21;
  *(_DWORD *)((char *)v21 + 2 * v22) = 34;
  return result;
}

```

## disassembly

```asm
0x14001f10c  push    rbx
0x14001f10e  push    rbp
0x14001f10f  push    rsi
0x14001f110  push    rdi
0x14001f111  push    r14
0x14001f113  push    r15
0x14001f115  sub     rsp, 28h
0x14001f119  mov     rbx, rcx
0x14001f11c  mov     rdi, rdx
0x14001f11f  mov     rcx, [rcx]; Src
0x14001f122  mov     r8, [rcx+10h]
0x14001f126  cmp     r8, [rcx+18h]
0x14001f12a  jnb     short loc_14001F149
0x14001f12c  cmp     qword ptr [rcx+18h], 7
0x14001f131  lea     rax, [r8+1]
0x14001f135  mov     [rcx+10h], rax
0x14001f139  jbe     short loc_14001F13E
0x14001f13b  mov     rcx, [rcx]
0x14001f13e  mov     esi, 22h ; '"'
0x14001f143  mov     [rcx+r8*2], esi
0x14001f147  jmp     short loc_14001F156
0x14001f149  mov     esi, 22h ; '"'
0x14001f14e  mov     r9d, esi
0x14001f151  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001f156  mov     r14, [rdi+8]
0x14001f15a  test    r14, r14
0x14001f15d  jz      loc_14001F327
0x14001f163  mov     rdi, [rdi]
0x14001f166  xor     ebp, ebp
0x14001f168  lea     r15d, [rbp+5Ch]
0x14001f16c  movzx   edx, word ptr [rdi+rbp*2]
0x14001f170  cmp     edx, 20h ; ' '
0x14001f173  jb      short loc_14001F1BF
0x14001f175  cmp     dx, r15w
0x14001f179  jz      short loc_14001F1BF
0x14001f17b  cmp     dx, si
0x14001f17e  jz      short loc_14001F1BF
0x14001f180  mov     rcx, [rbx]; Src
0x14001f183  mov     r8, [rcx+10h]
0x14001f187  cmp     r8, [rcx+18h]
0x14001f18b  jnb     short loc_14001F1B1
0x14001f18d  cmp     qword ptr [rcx+18h], 7
0x14001f192  lea     rax, [r8+1]
0x14001f196  mov     [rcx+10h], rax
0x14001f19a  jbe     short loc_14001F19F
0x14001f19c  mov     rcx, [rcx]
0x14001f19f  xor     eax, eax
0x14001f1a1  mov     [rcx+r8*2], dx
0x14001f1a6  mov     [rcx+r8*2+2], ax
0x14001f1ac  jmp     loc_14001F31B
0x14001f1b1  movzx   r9d, dx
0x14001f1b5  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001f1ba  jmp     loc_14001F31B
0x14001f1bf  mov     ecx, edx
0x14001f1c1  sub     ecx, 8
0x14001f1c4  jz      loc_14001F30C
0x14001f1ca  sub     ecx, 1
0x14001f1cd  jz      loc_14001F303
0x14001f1d3  sub     ecx, 1
0x14001f1d6  jz      loc_14001F2FA
0x14001f1dc  sub     ecx, 2
0x14001f1df  jz      loc_14001F2F1
0x14001f1e5  sub     ecx, 1
0x14001f1e8  jz      loc_14001F2E8
0x14001f1ee  sub     ecx, 15h
0x14001f1f1  jz      loc_14001F2B4
0x14001f1f7  cmp     ecx, 3Ah ; ':'
0x14001f1fa  jz      loc_14001F2B4
0x14001f200  mov     rcx, [rbx]; Src
0x14001f203  lea     rdx, aU00; "\\u00"
0x14001f20a  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14001f20f  mov     rcx, [rbx]; Src
0x14001f212  movzx   eax, word ptr [rdi+rbp*2]
0x14001f216  shr     ax, 4
0x14001f21a  and     ax, 0Fh
0x14001f21e  mov     rdx, [rcx+10h]
0x14001f222  cmp     ax, 0Ah
0x14001f226  sbb     r9w, r9w
0x14001f22a  and     r9w, 0FFD9h
0x14001f230  add     r9w, 57h ; 'W'
0x14001f235  add     r9w, ax
0x14001f239  cmp     rdx, [rcx+18h]
0x14001f23d  jnb     short loc_14001F25F
0x14001f23f  cmp     qword ptr [rcx+18h], 7
0x14001f244  lea     rax, [rdx+1]
0x14001f248  mov     [rcx+10h], rax
0x14001f24c  jbe     short loc_14001F251
0x14001f24e  mov     rcx, [rcx]
0x14001f251  xor     eax, eax
0x14001f253  mov     [rcx+rdx*2], r9w
0x14001f258  mov     [rcx+rdx*2+2], ax
0x14001f25d  jmp     short loc_14001F264
0x14001f25f  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001f264  movzx   eax, word ptr [rdi+rbp*2]
0x14001f268  and     ax, 0Fh
0x14001f26c  cmp     ax, 0Ah
0x14001f270  sbb     r9w, r9w
0x14001f274  and     r9w, 0FFD9h
0x14001f27a  add     r9w, 57h ; 'W'
0x14001f27f  add     r9w, ax
0x14001f283  mov     rcx, [rbx]
0x14001f286  mov     rdx, [rcx+10h]
0x14001f28a  cmp     rdx, [rcx+18h]
0x14001f28e  jnb     loc_14001F1B5
0x14001f294  lea     rax, [rdx+1]
0x14001f298  mov     [rcx+10h], rax
0x14001f29c  cmp     qword ptr [rcx+18h], 7
0x14001f2a1  jbe     short loc_14001F2A6
0x14001f2a3  mov     rcx, [rcx]
0x14001f2a6  xor     eax, eax
0x14001f2a8  mov     [rcx+rdx*2], r9w
0x14001f2ad  mov     [rcx+rdx*2+2], ax
0x14001f2b2  jmp     short loc_14001F31B
0x14001f2b4  mov     rcx, [rbx]; Src
0x14001f2b7  mov     rdx, [rcx+10h]
0x14001f2bb  cmp     rdx, [rcx+18h]
0x14001f2bf  jnb     short loc_14001F2D9
0x14001f2c1  cmp     qword ptr [rcx+18h], 7
0x14001f2c6  lea     rax, [rdx+1]
0x14001f2ca  mov     [rcx+10h], rax
0x14001f2ce  jbe     short loc_14001F2D3
0x14001f2d0  mov     rcx, [rcx]
0x14001f2d3  mov     [rcx+rdx*2], r15d
0x14001f2d7  jmp     short loc_14001F2E1
0x14001f2d9  mov     r9d, r15d
0x14001f2dc  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001f2e1  movzx   r9d, word ptr [rdi+rbp*2]
0x14001f2e6  jmp     short loc_14001F283
0x14001f2e8  lea     rdx, aR; "\\r"
0x14001f2ef  jmp     short loc_14001F313
0x14001f2f1  lea     rdx, asc_14003737C; "\\f"
0x14001f2f8  jmp     short loc_14001F313
0x14001f2fa  lea     rdx, aN; "\\n"
0x14001f301  jmp     short loc_14001F313
0x14001f303  lea     rdx, aT; "\\t"
0x14001f30a  jmp     short loc_14001F313
0x14001f30c  lea     rdx, aB; "\\b"
0x14001f313  mov     rcx, [rbx]; Src
0x14001f316  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14001f31b  inc     rbp
0x14001f31e  cmp     rbp, r14
0x14001f321  jb      loc_14001F16C
0x14001f327  mov     rcx, [rbx]; Src
0x14001f32a  mov     rdx, [rcx+10h]
0x14001f32e  cmp     rdx, [rcx+18h]
0x14001f332  jnb     short loc_14001F34F
0x14001f334  cmp     qword ptr [rcx+18h], 7
0x14001f339  lea     rax, [rdx+1]
0x14001f33d  mov     [rcx+10h], rax
0x14001f341  jbe     short loc_14001F346
0x14001f343  mov     rcx, [rcx]
0x14001f346  mov     dword ptr [rcx+rdx*2], 22h ; '"'
0x14001f34d  jmp     short loc_14001F357
0x14001f34f  mov     r9d, esi
0x14001f352  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001f357  add     rsp, 28h
0x14001f35b  pop     r15
0x14001f35d  pop     r14
0x14001f35f  pop     rdi
0x14001f360  pop     rsi
0x14001f361  pop     rbp
0x14001f362  pop     rbx
0x14001f363  retn
```
