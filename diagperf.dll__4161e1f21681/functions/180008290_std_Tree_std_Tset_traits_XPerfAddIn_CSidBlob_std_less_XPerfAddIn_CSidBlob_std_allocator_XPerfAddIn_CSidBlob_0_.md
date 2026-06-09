# std::_Tree<std::_Tset_traits<XPerfAddIn::CSidBlob,std::less<XPerfAddIn::CSidBlob>,std::allocator<XPerfAddIn::CSidBlob>,0>>::_Insert_nohint<XPerfAddIn::CSidBlob,std::_Nil>(bool,XPerfAddIn::CSidBlob &&,std::_Nil)

- ea: `0x180008290`
- end: `0x18000844b`
- name: `??$_Insert_nohint@VCSidBlob@XPerfAddIn@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@VCSidBlob@XPerfAddIn@@U?$less@VCSidBlob@XPerfAddIn@@@std@@V?$allocator@VCSidBlob@XPerfAddIn@@@4@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VCSidBlob@XPerfAddIn@@@std@@@std@@@std@@_N@1@_N$$QEAVCSidBlob@XPerfAddIn@@U_Nil@1@@Z`
- size: `443`
- prototype: `__int64 __fastcall(__int64 **, __int64, __int64, PSID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800089b0`

## callees

- `0x180008290`
- `0x18003c188`
- `0x1800cf026`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800082cb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800082d8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008359`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008366`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800082cb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800082d8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008359`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008366`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<XPerfAddIn::CSidBlob,std::less<XPerfAddIn::CSidBlob>,std::allocator<XPerfAddIn::CSidBlob>,0>>::_Insert_nohint<XPerfAddIn::CSidBlob,std::_Nil>(
        __int64 **a1,
        __int64 a2,
        __int64 a3,
        PSID *a4)
{
  __int64 v7; // rbx
  __int64 v8; // rsi
  DWORD LengthSid; // r14d
  DWORD v10; // eax
  int v11; // eax
  char v12; // r14
  __int64 *v13; // rsi
  __int64 i; // rax
  DWORD v15; // r15d
  DWORD v16; // eax
  __int64 result; // rax
  __int64 j; // rax
  __int64 v19; // [rsp+60h] [rbp+8h] BYREF

  v7 = (__int64)*a1;
  v8 = (*a1)[1];
  if ( *(_BYTE *)(v8 + 25) )
  {
    v12 = 1;
    v13 = *a1;
  }
  else
  {
    do
    {
      v7 = v8;
      LengthSid = GetLengthSid(*a4);
      v10 = GetLengthSid(*(PSID *)(v8 + 32));
      if ( LengthSid < v10 || LengthSid == v10 && (v11 = memcmp_0(*a4, *(const void **)(v8 + 32), LengthSid), v11 < 0) )
      {
        v8 = *(_QWORD *)v8;
        v12 = 1;
      }
      else
      {
        v8 = *(_QWORD *)(v8 + 16);
        v12 = 0;
      }
    }
    while ( !*(_BYTE *)(v8 + 25) );
    v13 = (__int64 *)v7;
    if ( !v12 )
      goto LABEL_16;
  }
  if ( v13 != (__int64 *)**a1 )
  {
    if ( *((_BYTE *)v13 + 25) )
    {
      v7 = v13[2];
    }
    else if ( *(_BYTE *)(*v13 + 25) )
    {
      for ( i = v13[1]; !*(_BYTE *)(i + 25) && v7 == *(_QWORD *)i; i = *(_QWORD *)(i + 8) )
        v7 = i;
      if ( !*(_BYTE *)(v7 + 25) )
        v7 = i;
    }
    else
    {
      v7 = *v13;
      for ( j = *(_QWORD *)(*v13 + 16); !*(_BYTE *)(j + 25); j = *(_QWORD *)(v7 + 16) )
        v7 = *(_QWORD *)(v7 + 16);
    }
LABEL_16:
    v15 = GetLengthSid(*(PSID *)(v7 + 32));
    v16 = GetLengthSid(*a4);
    if ( v15 < v16 || v15 == v16 && memcmp_0(*(const void **)(v7 + 32), *a4, v15) < 0 )
    {
      *(_QWORD *)a2 = *std::_Tree<std::_Tset_traits<XPerfAddIn::CSidBlob,std::less<XPerfAddIn::CSidBlob>,std::allocator<XPerfAddIn::CSidBlob>,0>>::_Insert_at<XPerfAddIn::CSidBlob,std::_Nil>(
                         a1,
                         &v19,
                         v12,
                         v13,
                         (const struct _SID **)a4);
      *(_BYTE *)(a2 + 8) = 1;
      return a2;
    }
    else
    {
      *(_QWORD *)a2 = v7;
      *(_BYTE *)(a2 + 8) = 0;
      return a2;
    }
  }
  try
  {
    *(_QWORD *)a2 = *std::_Tree<std::_Tset_traits<XPerfAddIn::CSidBlob,std::less<XPerfAddIn::CSidBlob>,std::allocator<XPerfAddIn::CSidBlob>,0>>::_Insert_at<XPerfAddIn::CSidBlob,std::_Nil>(
                       a1,
                       &v19,
                       1,
                       v13,
                       (const struct _SID **)a4);
    *(_BYTE *)(a2 + 8) = 1;
    result = a2;
  }
  catch ( ... )
  {
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180008290  mov     [rsp+arg_8], rbx
0x180008295  mov     [rsp+arg_10], rsi
0x18000829a  push    rdi
0x18000829b  push    r12
0x18000829d  push    r13
0x18000829f  push    r14
0x1800082a1  push    r15
0x1800082a3  sub     rsp, 30h
0x1800082a7  mov     r12, r9
0x1800082aa  mov     rdi, rdx
0x1800082ad  mov     r13, rcx
0x1800082b0  mov     rbx, [rcx]
0x1800082b3  mov     rsi, [rbx+8]
0x1800082b7  xor     r15d, r15d
0x1800082ba  cmp     [rsi+19h], r15b
0x1800082be  jnz     loc_1800083B1
0x1800082c4  mov     rbx, rsi
0x1800082c7  mov     rcx, [r12]; pSid
0x1800082cb  call    cs:__imp_GetLengthSid
0x1800082d1  mov     r14d, eax
0x1800082d4  mov     rcx, [rsi+20h]; pSid
0x1800082d8  call    cs:__imp_GetLengthSid
0x1800082de  cmp     r14d, eax
0x1800082e1  jb      loc_1800083E3
0x1800082e7  jnz     short loc_180008301
0x1800082e9  mov     r8d, r14d; Size
0x1800082ec  mov     rdx, [rsi+20h]; Buf2
0x1800082f0  mov     rcx, [r12]; Buf1
0x1800082f4  call    memcmp_0
0x1800082f9  test    eax, eax
0x1800082fb  js      loc_1800083E3
0x180008301  mov     rsi, [rsi+10h]
0x180008305  mov     r14b, r15b
0x180008308  cmp     [rsi+19h], r15b
0x18000830c  jz      short loc_1800082C4
0x18000830e  mov     rsi, rbx
0x180008311  test    r14b, r14b
0x180008314  jz      short loc_180008355
0x180008316  mov     rax, [r13+0]
0x18000831a  cmp     rsi, [rax]
0x18000831d  jz      loc_1800083BC
0x180008323  cmp     [rsi+19h], r15b
0x180008327  jnz     loc_1800083EE
0x18000832d  mov     rax, [rsi]
0x180008330  cmp     [rax+19h], r15b
0x180008334  jz      loc_1800083F7
0x18000833a  mov     rax, [rsi+8]
0x18000833e  cmp     [rax+19h], r15b
0x180008342  jnz     short loc_18000834D
0x180008344  cmp     rbx, [rax]
0x180008347  jz      loc_180008413
0x18000834d  cmp     [rbx+19h], r15b
0x180008351  cmovz   rbx, rax
0x180008355  mov     rcx, [rbx+20h]; pSid
0x180008359  call    cs:__imp_GetLengthSid
0x18000835f  mov     r15d, eax
0x180008362  mov     rcx, [r12]; pSid
0x180008366  call    cs:__imp_GetLengthSid
0x18000836c  cmp     r15d, eax
0x18000836f  jb      loc_18000841F
0x180008375  jnz     short loc_18000838F
0x180008377  mov     r8d, r15d; Size
0x18000837a  mov     rdx, [r12]; Buf2
0x18000837e  mov     rcx, [rbx+20h]; Buf1
0x180008382  call    memcmp_0
0x180008387  test    eax, eax
0x180008389  js      loc_18000841F
0x18000838f  mov     [rdi], rbx
0x180008392  mov     byte ptr [rdi+8], 0
0x180008396  mov     rax, rdi
0x180008399  mov     rbx, [rsp+58h+arg_8]
0x18000839e  mov     rsi, [rsp+58h+arg_10]
0x1800083a3  add     rsp, 30h
0x1800083a7  pop     r15
0x1800083a9  pop     r14
0x1800083ab  pop     r13
0x1800083ad  pop     r12
0x1800083af  pop     rdi
0x1800083b0  retn
0x1800083b1  mov     r14b, 1
0x1800083b4  mov     rsi, rbx
0x1800083b7  jmp     loc_180008316
0x1800083bc  mov     [rsp+58h+var_38], r12
0x1800083c1  mov     r9, rsi
0x1800083c4  mov     r8b, 1
0x1800083c7  lea     rdx, [rsp+58h+arg_0]
0x1800083cc  mov     rcx, r13
0x1800083cf  call    ??$_Insert_at@VCSidBlob@XPerfAddIn@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@VCSidBlob@XPerfAddIn@@U?$less@VCSidBlob@XPerfAddIn@@@std@@V?$allocator@VCSidBlob@XPerfAddIn@@@4@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VCSidBlob@XPerfAddIn@@@std@@@std@@@1@_NPEAU?$_Tree_node@VCSidBlob@XPerfAddIn@@PEAX@1@$$QEAVCSidBlob@XPerfAddIn@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<XPerfAddIn::CSidBlob,std::less<XPerfAddIn::CSidBlob>,std::allocator<XPerfAddIn::CSidBlob>,0>>::_Insert_at<XPerfAddIn::CSidBlob,std::_Nil>(bool,std::_Tree_node<XPerfAddIn::CSidBlob,void *> *,XPerfAddIn::CSidBlob &&,std::_Nil)
0x1800083d4  mov     rax, [rax]
0x1800083d7  mov     [rdi], rax
0x1800083da  mov     byte ptr [rdi+8], 1
0x1800083de  mov     rax, rdi
0x1800083e1  jmp     short loc_180008399
0x1800083e3  mov     rsi, [rsi]
0x1800083e6  mov     r14b, 1
0x1800083e9  jmp     loc_180008308
0x1800083ee  mov     rbx, [rsi+10h]
0x1800083f2  jmp     loc_180008355
0x1800083f7  mov     rbx, rax
0x1800083fa  mov     rax, [rax+10h]
0x1800083fe  jmp     short loc_180008408
0x180008400  mov     rbx, [rbx+10h]
0x180008404  mov     rax, [rbx+10h]
0x180008408  cmp     [rax+19h], r15b
0x18000840c  jz      short loc_180008400
0x18000840e  jmp     loc_180008355
0x180008413  mov     rbx, rax
0x180008416  mov     rax, [rax+8]
0x18000841a  jmp     loc_18000833E
0x18000841f  mov     [rsp+58h+var_38], r12
0x180008424  mov     r9, rsi
0x180008427  mov     r8b, r14b
0x18000842a  lea     rdx, [rsp+58h+arg_0]
0x18000842f  mov     rcx, r13
0x180008432  call    ??$_Insert_at@VCSidBlob@XPerfAddIn@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@VCSidBlob@XPerfAddIn@@U?$less@VCSidBlob@XPerfAddIn@@@std@@V?$allocator@VCSidBlob@XPerfAddIn@@@4@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VCSidBlob@XPerfAddIn@@@std@@@std@@@1@_NPEAU?$_Tree_node@VCSidBlob@XPerfAddIn@@PEAX@1@$$QEAVCSidBlob@XPerfAddIn@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<XPerfAddIn::CSidBlob,std::less<XPerfAddIn::CSidBlob>,std::allocator<XPerfAddIn::CSidBlob>,0>>::_Insert_at<XPerfAddIn::CSidBlob,std::_Nil>(bool,std::_Tree_node<XPerfAddIn::CSidBlob,void *> *,XPerfAddIn::CSidBlob &&,std::_Nil)
0x180008437  mov     rax, [rax]
0x18000843a  mov     [rdi], rax
0x18000843d  mov     byte ptr [rdi+8], 1
0x180008441  mov     rax, rdi
0x180008444  jmp     loc_180008399
```
