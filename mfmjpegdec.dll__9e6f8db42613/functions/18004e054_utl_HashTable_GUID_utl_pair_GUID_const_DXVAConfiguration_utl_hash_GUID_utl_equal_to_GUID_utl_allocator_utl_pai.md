# utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_CopyAssignFrom(utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0> const &)

- ea: `0x18004e054`
- end: `0x18004e206`
- name: `?_CopyAssignFrom@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@IEAA_NAEBV12@@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004df40`

## callees

- `0x180043194`
- `0x18004b56c`
- `0x18004b9d0`
- `0x18004ba74`
- `0x18004dbc0`
- `0x18004e030`
- `0x18004e054`

## pseudocode

```c
char __fastcall utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_CopyAssignFrom(
        __int64 a1,
        __int64 a2)
{
  char v4; // bl
  unsigned __int64 v5; // r9
  unsigned __int64 v6; // r8
  unsigned __int8 v7; // al
  __int64 v8; // rdx
  _QWORD *i; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 *v13; // rcx
  _QWORD v15[2]; // [rsp+20h] [rbp-40h] BYREF
  char v16; // [rsp+30h] [rbp-30h]
  __int64 v17; // [rsp+38h] [rbp-28h] BYREF
  __int64 *v18; // [rsp+40h] [rbp-20h]
  __int64 v19; // [rsp+48h] [rbp-18h]
  __int64 v20; // [rsp+50h] [rbp-10h]
  unsigned __int8 v21; // [rsp+58h] [rbp-8h]
  char v22; // [rsp+59h] [rbp-7h]
  char v23; // [rsp+80h] [rbp+20h] BYREF

  if ( a1 == a2 )
    return 1;
  if ( *(_QWORD *)a2 == a2 )
  {
    v4 = 1;
    utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Uninit(a1);
    *(_QWORD *)a1 = a1;
    *(_QWORD *)(a1 + 8) = a1;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_BYTE *)(a1 + 32) = 0;
    *(_BYTE *)(a1 + 33) = *(_BYTE *)(a2 + 33);
  }
  else
  {
    v5 = *(_QWORD *)(a2 + 24);
    v6 = *(unsigned __int8 *)(a2 + 33);
    v17 = (__int64)&v17;
    v18 = &v17;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = v6;
    if ( 8 * (v6 * ((v5 + 7) >> 3) / v6) >= v5
      && ((v7 = utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_BucketsToTableSize(
                  v6 * ((v5 + 7) >> 3),
                  v6 * ((v5 + 7) >> 3) % v6),
           v19)
       && v7 <= v21
       || (LOBYTE(v8) = v7,
           (unsigned __int8)utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Rehash(
                              &v17,
                              v8))) )
    {
      for ( i = *(_QWORD **)a2; i != (_QWORD *)a2; i = (_QWORD *)*i )
      {
        utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindInsertPos(
          &v17,
          v15,
          i + 3);
        if ( v16 )
        {
          v11 = v15[0];
        }
        else
        {
          v12 = utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_NewNodeConstruct<utl::pair<_GUID const,DXVAConfiguration> const &>(
                  v10,
                  i + 3);
          if ( !v12 )
            goto LABEL_18;
          v11 = *(_QWORD *)utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InsertAt(
                             &v17,
                             &v23,
                             v15,
                             v12);
        }
        if ( !v11 )
          goto LABEL_18;
      }
      v4 = 1;
      utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Uninit(a1);
      v13 = v18;
      *(_QWORD *)(v17 + 8) = a1;
      *v13 = a1;
      *(_QWORD *)a1 = v17;
      *(_QWORD *)(a1 + 8) = v18;
      v17 = (__int64)&v17;
      v18 = &v17;
      *(_QWORD *)(a1 + 16) = v19;
      *(_QWORD *)(a1 + 24) = v20;
      *(_BYTE *)(a1 + 32) = v21;
      *(_BYTE *)(a1 + 33) = v22;
      v19 = 0;
      v20 = 0;
    }
    else
    {
LABEL_18:
      v4 = 0;
    }
    utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Uninit(&v17);
  }
  return v4;
}

```

## disassembly

```asm
0x18004e054  mov     [rsp-18h+arg_8], rbx
0x18004e059  mov     [rsp-18h+arg_10], rdi
0x18004e05e  push    rbp
0x18004e05f  push    r14
0x18004e061  push    r15
0x18004e063  mov     rbp, rsp
0x18004e066  sub     rsp, 60h
0x18004e06a  mov     r14, rdx
0x18004e06d  mov     rdi, rcx
0x18004e070  cmp     rcx, rdx
0x18004e073  jnz     short loc_18004E07C
0x18004e075  mov     bl, 1
0x18004e077  jmp     loc_18004E1EE
0x18004e07c  cmp     [rdx], r14
0x18004e07f  jnz     short loc_18004E0AF
0x18004e081  mov     bl, 1
0x18004e083  call    ?_Uninit@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Uninit(void)
0x18004e088  mov     [rdi], rdi
0x18004e08b  mov     [rdi+8], rdi
0x18004e08f  mov     qword ptr [rdi+10h], 0
0x18004e097  mov     qword ptr [rdi+18h], 0
0x18004e09f  mov     byte ptr [rdi+20h], 0
0x18004e0a3  mov     al, [r14+21h]
0x18004e0a7  mov     [rdi+21h], al
0x18004e0aa  jmp     loc_18004E1EE
0x18004e0af  mov     r9, [rdx+18h]
0x18004e0b3  lea     rax, [rbp+var_28]
0x18004e0b7  movzx   r8d, byte ptr [rdx+21h]
0x18004e0bc  xor     edx, edx
0x18004e0be  mov     [rbp+var_28], rax
0x18004e0c2  lea     rax, [rbp+var_28]
0x18004e0c6  mov     [rbp+var_20], rax
0x18004e0ca  lea     rcx, [r9+7]
0x18004e0ce  mov     [rbp+var_18], 0
0x18004e0d6  shr     rcx, 3
0x18004e0da  imul    rcx, r8
0x18004e0de  mov     [rbp+var_10], 0
0x18004e0e6  mov     rax, rcx
0x18004e0e9  mov     [rbp+var_8], 0
0x18004e0ed  div     r8
0x18004e0f0  mov     [rbp+var_7], r8b
0x18004e0f4  shl     rax, 3
0x18004e0f8  cmp     rax, r9
0x18004e0fb  jb      loc_18004E1E3
0x18004e101  call    ?_BucketsToTableSize@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@CAE_K@Z; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_BucketsToTableSize(unsigned __int64)
0x18004e106  cmp     [rbp+var_18], 0
0x18004e10b  jz      short loc_18004E112
0x18004e10d  cmp     al, [rbp+var_8]
0x18004e110  jbe     short loc_18004E125
0x18004e112  mov     dl, al
0x18004e114  lea     rcx, [rbp+var_28]
0x18004e118  call    ?_Rehash@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAA_NE@Z; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Rehash(uchar)
0x18004e11d  test    al, al
0x18004e11f  jz      loc_18004E1E3
0x18004e125  mov     rbx, [r14]
0x18004e128  cmp     rbx, r14
0x18004e12b  jz      short loc_18004E17D
0x18004e12d  lea     r8, [rbx+18h]
0x18004e131  lea     rdx, [rbp+var_40]
0x18004e135  lea     rcx, [rbp+var_28]
0x18004e139  call    ?_FindInsertPos@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAA?AU_InsertPosResult@12@AEBU_GUID@@@Z; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindInsertPos(_GUID const &)
0x18004e13e  cmp     [rbp+var_30], 0
0x18004e142  jz      short loc_18004E14A
0x18004e144  mov     rax, [rbp+var_40]
0x18004e148  jmp     short loc_18004E173
0x18004e14a  lea     rdx, [rbx+18h]
0x18004e14e  call    ??$_NewNodeConstruct@AEBU?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAPEAU?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@1@AEBU?$pair@$$CBU_GUID@@UDXVAConfiguration@@@1@@Z; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_NewNodeConstruct<utl::pair<_GUID const,DXVAConfiguration> const &>(utl::pair<_GUID const,DXVAConfiguration> const &)
0x18004e153  test    rax, rax
0x18004e156  jz      loc_18004E1E3
0x18004e15c  mov     r9, rax
0x18004e15f  lea     r8, [rbp+var_40]
0x18004e163  lea     rdx, [rbp+arg_0]
0x18004e167  lea     rcx, [rbp+var_28]
0x18004e16b  call    ?_InsertAt@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@2@@2@AEBU_InsertPosResult@12@PEAU?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@2@@Z; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InsertAt(utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InsertPosResult const &,utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>> *)
0x18004e170  mov     rax, [rax]
0x18004e173  test    rax, rax
0x18004e176  jz      short loc_18004E1E3
0x18004e178  mov     rbx, [rbx]
0x18004e17b  jmp     short loc_18004E128
0x18004e17d  mov     rcx, rdi
0x18004e180  mov     bl, 1
0x18004e182  call    ?_Uninit@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Uninit(void)
0x18004e187  mov     rax, [rbp+var_28]
0x18004e18b  mov     rcx, [rbp+var_20]
0x18004e18f  mov     [rax+8], rdi
0x18004e193  mov     [rcx], rdi
0x18004e196  mov     rax, [rbp+var_28]
0x18004e19a  mov     [rdi], rax
0x18004e19d  mov     rax, [rbp+var_20]
0x18004e1a1  mov     [rdi+8], rax
0x18004e1a5  lea     rax, [rbp+var_28]
0x18004e1a9  mov     [rbp+var_28], rax
0x18004e1ad  lea     rax, [rbp+var_28]
0x18004e1b1  mov     [rbp+var_20], rax
0x18004e1b5  mov     rax, [rbp+var_18]
0x18004e1b9  mov     [rdi+10h], rax
0x18004e1bd  mov     rax, [rbp+var_10]
0x18004e1c1  mov     [rdi+18h], rax
0x18004e1c5  mov     al, [rbp+var_8]
0x18004e1c8  mov     [rdi+20h], al
0x18004e1cb  mov     al, [rbp+var_7]
0x18004e1ce  mov     [rdi+21h], al
0x18004e1d1  mov     [rbp+var_18], 0
0x18004e1d9  mov     [rbp+var_10], 0
0x18004e1e1  jmp     short loc_18004E1E5
0x18004e1e3  xor     bl, bl
0x18004e1e5  lea     rcx, [rbp+var_28]
0x18004e1e9  call    ?_Uninit@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Uninit(void)
0x18004e1ee  lea     r11, [rsp+60h+var_s0]
0x18004e1f3  mov     al, bl
0x18004e1f5  mov     rbx, [r11+28h]
0x18004e1f9  mov     rdi, [r11+30h]
0x18004e1fd  mov     rsp, r11
0x18004e200  pop     r15
0x18004e202  pop     r14
0x18004e204  pop     rbp
0x18004e205  retn
```
