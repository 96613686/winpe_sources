# Marshal::JsonParser::ParseString(std::basic_string_view<ushort,std::char_traits<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool)

- ea: `0x14001b540`
- end: `0x14001b8a2`
- name: `?ParseString@JsonParser@Marshal@@SA_KV?$basic_string_view@GU?$char_traits@G@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@_N@Z`
- size: `866`
- prototype: `unsigned __int64 __fastcall(__int64, _QWORD *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001b484`

## callees

- `0x140002d4e`
- `0x140014234`
- `0x14001b540`

## pseudocode

```c
unsigned __int64 __fastcall Marshal::JsonParser::ParseString(__int64 a1, _QWORD *a2, char a3)
{
  unsigned __int64 i; // rdi
  _WORD *v6; // r8
  int v7; // r9d
  int v8; // r9d
  int v9; // ecx
  int v10; // r9d
  int v11; // ecx
  int v12; // r10d
  int v13; // ecx
  int v14; // edx
  int v15; // ecx
  int v16; // eax
  __int16 v17; // r9
  unsigned __int64 v18; // rdx
  __int16 v19; // r9
  bool v20; // cc
  _QWORD *v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rcx
  _QWORD *v24; // rdx
  unsigned __int64 v25; // rcx
  _QWORD *v26; // rdx
  int pExceptionObject; // [rsp+50h] [rbp+18h] BYREF

  LOBYTE(pExceptionObject) = a3;
  if ( !*(_QWORD *)(a1 + 8) || **(_WORD **)a1 != 34 )
  {
    pExceptionObject = 4;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  for ( i = 1; ; i += v22 )
  {
    if ( i >= *(_QWORD *)(a1 + 8) )
    {
      pExceptionObject = 1;
      throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
    }
    v6 = *(_WORD **)a1;
    v7 = *(unsigned __int16 *)(*(_QWORD *)a1 + 2 * i);
    if ( v7 == 34 )
      break;
    if ( v7 != 92 )
    {
      v25 = a2[2];
      if ( v25 >= a2[3] )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(a2);
      }
      else
      {
        v20 = a2[3] <= 7u;
        a2[2] = v25 + 1;
        if ( v20 )
          v26 = a2;
        else
          v26 = (_QWORD *)*a2;
        *((_WORD *)v26 + v25) = v7;
        *((_WORD *)v26 + v25 + 1) = 0;
      }
      v22 = 1;
      continue;
    }
    if ( i + 1 >= *(_QWORD *)(a1 + 8) )
      goto LABEL_82;
    v8 = (unsigned __int16)v6[i + 1];
    if ( v8 == 117 )
    {
      if ( i + 2 >= *(_QWORD *)(a1 + 8) )
        goto LABEL_15;
      v9 = (unsigned __int16)v6[i + 2];
      v10 = v9 - 48;
      if ( (unsigned int)(v9 - 48) <= 9 )
        goto LABEL_16;
      if ( (unsigned int)(v9 - 65) <= 5 )
      {
        v10 = v9 - 55;
        goto LABEL_16;
      }
      if ( (unsigned int)(v9 - 97) > 5 )
LABEL_15:
        v10 = -1;
      else
        v10 = v9 - 87;
LABEL_16:
      if ( i + 3 >= *(_QWORD *)(a1 + 8) )
        goto LABEL_22;
      v11 = (unsigned __int16)v6[i + 3];
      v12 = v11 - 48;
      if ( (unsigned int)(v11 - 48) <= 9 )
        goto LABEL_23;
      if ( (unsigned int)(v11 - 65) <= 5 )
      {
        v12 = v11 - 55;
        goto LABEL_23;
      }
      if ( (unsigned int)(v11 - 97) > 5 )
LABEL_22:
        v12 = -1;
      else
        v12 = v11 - 87;
LABEL_23:
      if ( i + 4 >= *(_QWORD *)(a1 + 8) )
        goto LABEL_29;
      v13 = (unsigned __int16)v6[i + 4];
      v14 = v13 - 48;
      if ( (unsigned int)(v13 - 48) <= 9 )
        goto LABEL_30;
      if ( (unsigned int)(v13 - 65) <= 5 )
      {
        v14 = v13 - 55;
        goto LABEL_30;
      }
      if ( (unsigned int)(v13 - 97) > 5 )
LABEL_29:
        v14 = -1;
      else
        v14 = v13 - 87;
LABEL_30:
      if ( i + 5 >= *(_QWORD *)(a1 + 8) )
        goto LABEL_36;
      v15 = (unsigned __int16)v6[i + 5];
      v16 = v15 - 48;
      if ( (unsigned int)(v15 - 48) <= 9 )
        goto LABEL_37;
      if ( (unsigned int)(v15 - 65) <= 5 )
      {
        v16 = v15 - 55;
        goto LABEL_37;
      }
      if ( (unsigned int)(v15 - 97) > 5 )
LABEL_36:
        v16 = -1;
      else
        v16 = v15 - 87;
LABEL_37:
      if ( v10 < 0 || v12 < 0 || v14 < 0 || v16 < 0 )
      {
        pExceptionObject = 13;
        throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
      }
      v17 = v14 | (16 * (v12 | (16 * v10)));
      v18 = a2[2];
      v19 = v16 | (16 * v17);
      if ( v18 >= a2[3] )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(a2);
      }
      else
      {
        v20 = a2[3] <= 7u;
        a2[2] = v18 + 1;
        if ( v20 )
          v21 = a2;
        else
          v21 = (_QWORD *)*a2;
        *((_WORD *)v21 + v18) = v19;
        *((_WORD *)v21 + v18 + 1) = 0;
      }
      v22 = 6;
      continue;
    }
    if ( v8 != 34 )
    {
      if ( v8 == 39 )
      {
        pExceptionObject = 13;
        throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
      }
      if ( v8 != 47 && v8 != 92 )
      {
        switch ( v8 )
        {
          case 'b':
            LOWORD(v8) = 8;
            break;
          case 'f':
            LOWORD(v8) = 12;
            break;
          case 'n':
            LOWORD(v8) = 10;
            break;
          case 'r':
            LOWORD(v8) = 13;
            break;
          case 't':
            LOWORD(v8) = 9;
            break;
          default:
LABEL_82:
            pExceptionObject = 13;
            throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
        }
      }
    }
    v23 = a2[2];
    if ( v23 >= a2[3] )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(a2);
    }
    else
    {
      v20 = a2[3] <= 7u;
      a2[2] = v23 + 1;
      if ( v20 )
        v24 = a2;
      else
        v24 = (_QWORD *)*a2;
      *((_WORD *)v24 + v23) = v8;
      *((_WORD *)v24 + v23 + 1) = 0;
    }
    v22 = 2;
  }
  return i + 1;
}

```

## disassembly

```asm
0x14001b540  mov     [rsp+arg_0], rbx
0x14001b545  mov     [rsp+arg_8], rsi
0x14001b54a  mov     byte ptr [rsp+pExceptionObject], r8b
0x14001b54f  push    rdi
0x14001b550  push    r13
0x14001b552  push    r15
0x14001b554  sub     rsp, 20h
0x14001b558  cmp     qword ptr [rcx+8], 0
0x14001b55d  mov     rbx, rdx
0x14001b560  mov     rsi, rcx
0x14001b563  jbe     loc_14001B83A
0x14001b569  mov     rax, [rcx]
0x14001b56c  mov     r13d, 22h ; '"'
0x14001b572  cmp     [rax], r13w
0x14001b576  jnz     loc_14001B83A
0x14001b57c  lea     r15d, [r13-21h]
0x14001b580  mov     edi, r15d
0x14001b583  cmp     rdi, [rsi+8]
0x14001b587  jnb     loc_14001B823
0x14001b58d  mov     r8, [rsi]
0x14001b590  movzx   r9d, word ptr [r8+rdi*2]
0x14001b595  cmp     r9d, r13d
0x14001b598  jz      loc_14001B80A
0x14001b59e  cmp     r9d, 27h ; '''
0x14001b5a2  jz      loc_14001B7C8
0x14001b5a8  cmp     r9d, 5Ch ; '\'
0x14001b5ac  jnz     loc_14001B7C8
0x14001b5b2  lea     rax, [rdi+1]
0x14001b5b6  cmp     rax, [rsi+8]
0x14001b5ba  jnb     loc_14001B888
0x14001b5c0  movzx   r9d, word ptr [r8+rax*2]
0x14001b5c5  cmp     r9d, 75h ; 'u'
0x14001b5c9  jnz     loc_14001B727
0x14001b5cf  lea     rax, [rdi+2]
0x14001b5d3  cmp     rax, [rsi+8]
0x14001b5d7  jnb     short loc_14001B604
0x14001b5d9  movzx   ecx, word ptr [r8+rax*2]
0x14001b5de  lea     r9d, [rcx-30h]
0x14001b5e2  cmp     r9d, 9
0x14001b5e6  jbe     short loc_14001B608
0x14001b5e8  lea     eax, [rcx-41h]
0x14001b5eb  cmp     eax, 5
0x14001b5ee  ja      short loc_14001B5F6
0x14001b5f0  lea     r9d, [rcx-37h]
0x14001b5f4  jmp     short loc_14001B608
0x14001b5f6  lea     eax, [rcx-61h]
0x14001b5f9  cmp     eax, 5
0x14001b5fc  ja      short loc_14001B604
0x14001b5fe  lea     r9d, [rcx-57h]
0x14001b602  jmp     short loc_14001B608
0x14001b604  or      r9d, 0FFFFFFFFh
0x14001b608  lea     rax, [rdi+3]
0x14001b60c  cmp     rax, [rsi+8]
0x14001b610  jnb     short loc_14001B63D
0x14001b612  movzx   ecx, word ptr [r8+rax*2]
0x14001b617  lea     r10d, [rcx-30h]
0x14001b61b  cmp     r10d, 9
0x14001b61f  jbe     short loc_14001B641
0x14001b621  lea     eax, [rcx-41h]
0x14001b624  cmp     eax, 5
0x14001b627  ja      short loc_14001B62F
0x14001b629  lea     r10d, [rcx-37h]
0x14001b62d  jmp     short loc_14001B641
0x14001b62f  lea     eax, [rcx-61h]
0x14001b632  cmp     eax, 5
0x14001b635  ja      short loc_14001B63D
0x14001b637  lea     r10d, [rcx-57h]
0x14001b63b  jmp     short loc_14001B641
0x14001b63d  or      r10d, 0FFFFFFFFh
0x14001b641  lea     rax, [rdi+4]
0x14001b645  cmp     rax, [rsi+8]
0x14001b649  jnb     short loc_14001B672
0x14001b64b  movzx   ecx, word ptr [r8+rax*2]
0x14001b650  lea     edx, [rcx-30h]
0x14001b653  cmp     edx, 9
0x14001b656  jbe     short loc_14001B675
0x14001b658  lea     eax, [rcx-41h]
0x14001b65b  cmp     eax, 5
0x14001b65e  ja      short loc_14001B665
0x14001b660  lea     edx, [rcx-37h]
0x14001b663  jmp     short loc_14001B675
0x14001b665  lea     eax, [rcx-61h]
0x14001b668  cmp     eax, 5
0x14001b66b  ja      short loc_14001B672
0x14001b66d  lea     edx, [rcx-57h]
0x14001b670  jmp     short loc_14001B675
0x14001b672  or      edx, 0FFFFFFFFh
0x14001b675  lea     rax, [rdi+5]
0x14001b679  cmp     rax, [rsi+8]
0x14001b67d  jnb     short loc_14001B6A6
0x14001b67f  movzx   ecx, word ptr [r8+rax*2]
0x14001b684  lea     eax, [rcx-30h]
0x14001b687  cmp     eax, 9
0x14001b68a  jbe     short loc_14001B6A9
0x14001b68c  lea     eax, [rcx-41h]
0x14001b68f  cmp     eax, 5
0x14001b692  ja      short loc_14001B699
0x14001b694  lea     eax, [rcx-37h]
0x14001b697  jmp     short loc_14001B6A9
0x14001b699  lea     eax, [rcx-61h]
0x14001b69c  cmp     eax, 5
0x14001b69f  ja      short loc_14001B6A6
0x14001b6a1  lea     eax, [rcx-57h]
0x14001b6a4  jmp     short loc_14001B6A9
0x14001b6a6  or      eax, 0FFFFFFFFh
0x14001b6a9  test    r9d, r9d
0x14001b6ac  js      loc_14001B854
0x14001b6b2  test    r10d, r10d
0x14001b6b5  js      loc_14001B854
0x14001b6bb  test    edx, edx
0x14001b6bd  js      loc_14001B854
0x14001b6c3  test    eax, eax
0x14001b6c5  js      loc_14001B854
0x14001b6cb  shl     r9w, 4
0x14001b6d0  or      r9w, r10w
0x14001b6d4  shl     r9w, 4
0x14001b6d9  or      r9w, dx
0x14001b6dd  mov     rdx, [rbx+10h]
0x14001b6e1  shl     r9w, 4
0x14001b6e6  or      r9w, ax
0x14001b6ea  cmp     rdx, [rbx+18h]
0x14001b6ee  jnb     short loc_14001B715
0x14001b6f0  cmp     qword ptr [rbx+18h], 7
0x14001b6f5  lea     rax, [rdx+1]
0x14001b6f9  mov     [rbx+10h], rax
0x14001b6fd  jbe     short loc_14001B704
0x14001b6ff  mov     rcx, [rbx]
0x14001b702  jmp     short loc_14001B707
0x14001b704  mov     rcx, rbx
0x14001b707  xor     eax, eax
0x14001b709  mov     [rcx+rdx*2], r9w
0x14001b70e  mov     [rcx+rdx*2+2], ax
0x14001b713  jmp     short loc_14001B71D
0x14001b715  mov     rcx, rbx; Src
0x14001b718  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001b71d  mov     eax, 6
0x14001b722  jmp     loc_14001B802
0x14001b727  cmp     r9d, r13d
0x14001b72a  jz      short loc_14001B78A
0x14001b72c  cmp     r9d, 27h ; '''
0x14001b730  jz      loc_14001B86E
0x14001b736  cmp     r9d, 2Fh ; '/'
0x14001b73a  jz      short loc_14001B78A
0x14001b73c  cmp     r9d, 5Ch ; '\'
0x14001b740  jz      short loc_14001B78A
0x14001b742  cmp     r9d, 62h ; 'b'
0x14001b746  jz      short loc_14001B784
0x14001b748  cmp     r9d, 66h ; 'f'
0x14001b74c  jz      short loc_14001B77C
0x14001b74e  cmp     r9d, 6Eh ; 'n'
0x14001b752  jz      short loc_14001B774
0x14001b754  cmp     r9d, 72h ; 'r'
0x14001b758  jz      short loc_14001B76C
0x14001b75a  cmp     r9d, 74h ; 't'
0x14001b75e  jnz     loc_14001B888
0x14001b764  mov     r9d, 9
0x14001b76a  jmp     short loc_14001B78A
0x14001b76c  mov     r9d, 0Dh
0x14001b772  jmp     short loc_14001B78A
0x14001b774  mov     r9d, 0Ah
0x14001b77a  jmp     short loc_14001B78A
0x14001b77c  mov     r9d, 0Ch
0x14001b782  jmp     short loc_14001B78A
0x14001b784  mov     r9d, 8
0x14001b78a  mov     rcx, [rbx+10h]
0x14001b78e  cmp     rcx, [rbx+18h]
0x14001b792  jnb     short loc_14001B7B9
0x14001b794  cmp     qword ptr [rbx+18h], 7
0x14001b799  lea     rax, [rcx+1]
0x14001b79d  mov     [rbx+10h], rax
0x14001b7a1  jbe     short loc_14001B7A8
0x14001b7a3  mov     rdx, [rbx]
0x14001b7a6  jmp     short loc_14001B7AB
0x14001b7a8  mov     rdx, rbx
0x14001b7ab  xor     eax, eax
0x14001b7ad  mov     [rdx+rcx*2], r9w
0x14001b7b2  mov     [rdx+rcx*2+2], ax
0x14001b7b7  jmp     short loc_14001B7C1
0x14001b7b9  mov     rcx, rbx; Src
0x14001b7bc  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001b7c1  mov     eax, 2
0x14001b7c6  jmp     short loc_14001B802
0x14001b7c8  mov     rcx, [rbx+10h]
0x14001b7cc  cmp     rcx, [rbx+18h]
0x14001b7d0  jnb     short loc_14001B7F7
0x14001b7d2  cmp     qword ptr [rbx+18h], 7
0x14001b7d7  lea     rax, [rcx+1]
0x14001b7db  mov     [rbx+10h], rax
0x14001b7df  jbe     short loc_14001B7E6
0x14001b7e1  mov     rdx, [rbx]
0x14001b7e4  jmp     short loc_14001B7E9
0x14001b7e6  mov     rdx, rbx
0x14001b7e9  xor     eax, eax
0x14001b7eb  mov     [rdx+rcx*2], r9w
0x14001b7f0  mov     [rdx+rcx*2+2], ax
0x14001b7f5  jmp     short loc_14001B7FF
0x14001b7f7  mov     rcx, rbx; Src
0x14001b7fa  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001b7ff  mov     rax, r15
0x14001b802  add     rdi, rax
0x14001b805  jmp     loc_14001B583
0x14001b80a  mov     rbx, [rsp+38h+arg_0]
0x14001b80f  lea     rax, [rdi+1]
0x14001b813  mov     rsi, [rsp+38h+arg_8]
0x14001b818  add     rsp, 20h
0x14001b81c  pop     r15
0x14001b81e  pop     r13
0x14001b820  pop     rdi
0x14001b821  retn
0x14001b823  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b82a  mov     [rsp+38h+pExceptionObject], r15d
0x14001b82f  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x14001b834  call    _CxxThrowException_0
0x14001b83a  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b841  mov     [rsp+38h+pExceptionObject], 4
0x14001b849  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x14001b84e  call    _CxxThrowException_0
0x14001b854  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b85b  mov     [rsp+38h+pExceptionObject], 0Dh
0x14001b863  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x14001b868  call    _CxxThrowException_0
0x14001b86e  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b875  mov     [rsp+38h+pExceptionObject], 0Dh
0x14001b87d  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x14001b882  call    _CxxThrowException_0
0x14001b888  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b88f  mov     [rsp+38h+pExceptionObject], 0Dh
0x14001b897  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x14001b89c  call    _CxxThrowException_0
```
