# NpCommonQueryInformation

- ea: `0x1400143d0`
- end: `0x1400146c7`
- name: `NpCommonQueryInformation`
- size: `759`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140014370`

## callees

- `0x1400143d0`
- `0x1400146d0`
- `0x140014818`
- `0x1400148d8`
- `0x1400149c4`
- `0x140014a74`

## pseudocode

```c
__int64 __fastcall NpCommonQueryInformation(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rdi
  __int64 v4; // rbx
  int v5; // edx
  int v6; // ecx
  __int64 v7; // r12
  __int16 *v8; // rax
  __int16 v9; // r8
  unsigned __int64 v10; // r14
  __int64 v11; // rsi
  unsigned int PipeInfo; // eax
  unsigned int v13; // r15d
  unsigned int v15; // eax
  unsigned int StandardInfo; // eax
  unsigned int PositionInfo; // eax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  int v23; // ecx
  int v24; // eax
  int v25; // eax
  __int64 v26; // [rsp+60h] [rbp+8h] BYREF

  v26 = a1;
  v2 = a2[23];
  v4 = *(_QWORD *)(v2 + 48);
  v5 = *(_DWORD *)(v2 + 8);
  v6 = *(_DWORD *)(v2 + 16);
  v7 = a2[3];
  v8 = *(__int16 **)(v4 + 24);
  LODWORD(v26) = v5;
  v9 = *v8;
  if ( *v8 == 514 )
  {
    v10 = *(_QWORD *)(v4 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
    v11 = (*(_QWORD *)(v4 + 32) >> 1) & 1LL;
  }
  else
  {
    if ( v9 != 518 )
      return 3221225485LL;
    v10 = 0;
    LODWORD(v11) = 0;
  }
  if ( (*(_QWORD *)(v4 + 32) & 1) == 0 )
    return 3221225648LL;
  if ( v6 != 24 )
  {
    switch ( v6 )
    {
      case 4:
        *(_DWORD *)(v7 + 36) = 0;
        v5 -= 40;
        *(_QWORD *)v7 = 0;
        v18 = 128;
        *(_QWORD *)(v7 + 8) = 0;
        *(_QWORD *)(v7 + 16) = 0;
        if ( !v10 )
          v18 = 16;
        *(_QWORD *)(v7 + 24) = 0;
        *(_DWORD *)(v7 + 32) = v18;
        v13 = 0;
        goto LABEL_8;
      case 5:
        StandardInfo = NpQueryStandardInfo(v4, v10, v7, (unsigned int)&v26, v11);
        v5 = v26;
        v13 = StandardInfo;
        goto LABEL_8;
      case 6:
        v19 = 0;
        v5 -= 8;
        *(_QWORD *)v7 = 0;
        if ( v10 )
          v19 = *(int *)(v10 + 456);
        *(_QWORD *)v7 = v19;
        v13 = 0;
        goto LABEL_8;
      case 7:
        v5 -= 4;
        *(_DWORD *)v7 = 0;
        v13 = 0;
        goto LABEL_8;
      case 9:
        v15 = NpQueryNameInfo(v4, v10, v7, &v26);
        v5 = v26;
        v13 = v15;
        goto LABEL_8;
      case 14:
        PositionInfo = NpQueryPositionInfo(v4, v10, v7, (unsigned int)&v26, v11);
        v5 = v26;
        v13 = PositionInfo;
        goto LABEL_8;
      case 18:
        LODWORD(v26) = v5 - 52;
        *(_DWORD *)(v7 + 36) = 0;
        v20 = 128;
        *(_QWORD *)v7 = 0;
        *(_QWORD *)(v7 + 8) = 0;
        *(_QWORD *)(v7 + 16) = 0;
        *(_QWORD *)(v7 + 24) = 0;
        if ( !v10 )
          v20 = 16;
        *(_DWORD *)(v7 + 32) = v20;
        v13 = 0;
        v21 = NpQueryStandardInfo(v4, v10, (int)v7 + 40, (unsigned int)&v26, v11);
        if ( v21 < 0 )
          v13 = v21;
        v22 = 0;
        v23 = v26 - 8;
        *(_QWORD *)(v7 + 64) = 0;
        if ( v10 )
          v22 = *(int *)(v10 + 456);
        *(_QWORD *)(v7 + 64) = v22;
        LODWORD(v26) = v23 - 4;
        *(_DWORD *)(v7 + 72) = 0;
        v24 = NpQueryPositionInfo(v4, v10, (int)v7 + 80, (unsigned int)&v26, v11);
        if ( v24 < 0 )
          v13 = v24;
        v25 = NpQueryNameInfo(v4, v10, v7 + 96, &v26);
        v5 = v26;
        if ( v25 < 0 )
          v13 = v25;
        goto LABEL_8;
      case 23:
        if ( v9 != 514 )
          goto LABEL_11;
        PipeInfo = NpQueryPipeInfo(v4, v10, v7, (unsigned int)&v26, v11);
        goto LABEL_7;
      default:
        goto LABEL_11;
    }
  }
  if ( v9 == 514 )
  {
    PipeInfo = NpQueryPipeLocalInfo(v4, v10, v7, (unsigned int)&v26, v11);
LABEL_7:
    v5 = v26;
    v13 = PipeInfo;
  }
  else
  {
LABEL_11:
    v13 = -1073741811;
  }
LABEL_8:
  a2[7] = (unsigned int)(*(_DWORD *)(v2 + 8) - v5);
  return v13;
}

```

## disassembly

```asm
0x1400143d0  mov     [rsp+arg_8], rbx
0x1400143d5  mov     [rsp+arg_10], rbp
0x1400143da  mov     [rsp+arg_0], rcx
0x1400143df  push    rsi
0x1400143e0  push    rdi
0x1400143e1  push    r12
0x1400143e3  push    r14
0x1400143e5  push    r15
0x1400143e7  sub     rsp, 30h
0x1400143eb  mov     rdi, [rdx+0B8h]
0x1400143f2  mov     rbp, rdx
0x1400143f5  mov     r10d, 202h
0x1400143fb  mov     rbx, [rdi+30h]
0x1400143ff  mov     edx, [rdi+8]
0x140014402  mov     ecx, [rdi+10h]
0x140014405  mov     r12, [rbp+18h]
0x140014409  mov     rax, [rbx+18h]
0x14001440d  mov     dword ptr [rsp+58h+arg_0], edx
0x140014411  movzx   r8d, word ptr [rax]
0x140014415  cmp     r8w, r10w
0x140014419  jnz     loc_1400144D5
0x14001441f  mov     r14, [rbx+20h]
0x140014423  mov     rsi, [rbx+20h]
0x140014427  and     r14, 0FFFFFFFFFFFFFFFCh
0x14001442b  shr     rsi, 1
0x14001442e  and     esi, 1
0x140014431  mov     rax, [rbx+20h]
0x140014435  test    al, 1
0x140014437  jz      loc_140014586
0x14001443d  cmp     ecx, 18h
0x140014440  jnz     short loc_14001448E
0x140014442  cmp     r8w, r10w
0x140014446  jnz     def_1400144AB; jumptable 00000001400144AB default case, cases 8,10-13,15-17,19-22
0x14001444c  lea     r9, [rsp+58h+arg_0]
0x140014451  mov     [rsp+58h+var_38], esi
0x140014455  mov     r8, r12
0x140014458  mov     rdx, r14
0x14001445b  mov     rcx, rbx
0x14001445e  call    NpQueryPipeLocalInfo
0x140014463  mov     edx, dword ptr [rsp+58h+arg_0]
0x140014467  mov     r15d, eax
0x14001446a  mov     eax, [rdi+8]
0x14001446d  sub     eax, edx
0x14001446f  mov     [rbp+38h], rax
0x140014473  mov     eax, r15d
0x140014476  mov     rbx, [rsp+58h+arg_8]
0x14001447b  mov     rbp, [rsp+58h+arg_10]
0x140014480  add     rsp, 30h
0x140014484  pop     r15
0x140014486  pop     r14
0x140014488  pop     r12
0x14001448a  pop     rdi
0x14001448b  pop     rsi
0x14001448c  retn
0x14001448e  add     ecx, 0FFFFFFFCh; switch 20 cases
0x140014491  cmp     ecx, 13h
0x140014494  ja      short def_1400144AB; jumptable 00000001400144AB default case, cases 8,10-13,15-17,19-22
0x140014496  movsxd  rax, ecx
0x140014499  lea     r9, cs:140000000h
0x1400144a0  mov     ecx, ds:(jpt_1400144AB - 140000000h)[r9+rax*4]
0x1400144a8  add     rcx, r9
0x1400144ab  jmp     rcx; switch jump
0x1400144b1  lea     r9, [rsp+58h+arg_0]; jumptable 00000001400144AB case 9
0x1400144b6  mov     r8, r12
0x1400144b9  mov     rdx, r14
0x1400144bc  mov     rcx, rbx
0x1400144bf  call    NpQueryNameInfo
0x1400144c4  mov     edx, dword ptr [rsp+58h+arg_0]
0x1400144c8  mov     r15d, eax
0x1400144cb  jmp     short loc_14001446A
0x1400144cd  mov     r15d, 0C000000Dh; jumptable 00000001400144AB default case, cases 8,10-13,15-17,19-22
0x1400144d3  jmp     short loc_14001446A
0x1400144d5  mov     eax, 206h
0x1400144da  cmp     ax, r8w
0x1400144de  jnz     short loc_14001450D
0x1400144e0  xor     r14d, r14d
0x1400144e3  xor     esi, esi
0x1400144e5  jmp     loc_140014431
0x1400144ea  lea     r9, [rsp+58h+arg_0]; jumptable 00000001400144AB case 5
0x1400144ef  mov     [rsp+58h+var_38], esi
0x1400144f3  mov     r8, r12
0x1400144f6  mov     rdx, r14
0x1400144f9  mov     rcx, rbx
0x1400144fc  call    NpQueryStandardInfo
0x140014501  mov     edx, dword ptr [rsp+58h+arg_0]
0x140014505  mov     r15d, eax
0x140014508  jmp     loc_14001446A
0x14001450d  mov     eax, 0C000000Dh
0x140014512  jmp     loc_140014476
0x140014517  lea     r9, [rsp+58h+arg_0]; jumptable 00000001400144AB case 14
0x14001451c  mov     [rsp+58h+var_38], esi
0x140014520  mov     r8, r12
0x140014523  mov     rdx, r14
0x140014526  mov     rcx, rbx
0x140014529  call    NpQueryPositionInfo
0x14001452e  mov     edx, dword ptr [rsp+58h+arg_0]
0x140014532  mov     r15d, eax
0x140014535  jmp     loc_14001446A
0x14001453a  mov     dword ptr [r12+24h], 0; jumptable 00000001400144AB case 4
0x140014543  add     edx, 0FFFFFFD8h
0x140014546  test    r14, r14
0x140014549  mov     qword ptr [r12], 0
0x140014551  mov     eax, 80h
0x140014556  mov     qword ptr [r12+8], 0
0x14001455f  mov     ecx, 10h
0x140014564  mov     qword ptr [r12+10h], 0
0x14001456d  cmovz   eax, ecx
0x140014570  mov     qword ptr [r12+18h], 0
0x140014579  mov     [r12+20h], eax
0x14001457e  xor     r15d, r15d
0x140014581  jmp     loc_14001446A
0x140014586  mov     eax, 0C00000B0h
0x14001458b  jmp     loc_140014476
0x140014590  cmp     r8w, r10w; jumptable 00000001400144AB case 23
0x140014594  jnz     def_1400144AB; jumptable 00000001400144AB default case, cases 8,10-13,15-17,19-22
0x14001459a  lea     r9, [rsp+58h+arg_0]
0x14001459f  mov     [rsp+58h+var_38], esi
0x1400145a3  mov     r8, r12
0x1400145a6  mov     rdx, r14
0x1400145a9  mov     rcx, rbx
0x1400145ac  call    NpQueryPipeInfo
0x1400145b1  jmp     loc_140014463
0x1400145b6  xor     eax, eax; jumptable 00000001400144AB case 6
0x1400145b8  add     edx, 0FFFFFFF8h
0x1400145bb  mov     [r12], rax
0x1400145bf  test    r14, r14
0x1400145c2  jz      short loc_1400145CB
0x1400145c4  movsxd  rax, dword ptr [r14+1C8h]
0x1400145cb  mov     [r12], rax
0x1400145cf  xor     r15d, r15d
0x1400145d2  jmp     loc_14001446A
0x1400145d7  add     edx, 0FFFFFFCCh; jumptable 00000001400144AB case 18
0x1400145da  mov     [rsp+58h+var_38], esi
0x1400145de  mov     dword ptr [rsp+58h+arg_0], edx
0x1400145e2  lea     r8, [r12+28h]
0x1400145e7  mov     dword ptr [r12+24h], 0
0x1400145f0  lea     r9, [rsp+58h+arg_0]
0x1400145f5  mov     eax, 80h
0x1400145fa  mov     qword ptr [r12], 0
0x140014602  mov     ecx, 10h
0x140014607  mov     qword ptr [r12+8], 0
0x140014610  mov     qword ptr [r12+10h], 0
0x140014619  test    r14, r14
0x14001461c  mov     qword ptr [r12+18h], 0
0x140014625  mov     rdx, r14
0x140014628  cmovz   eax, ecx
0x14001462b  mov     rcx, rbx
0x14001462e  mov     [r12+20h], eax
0x140014633  xor     r15d, r15d
0x140014636  call    NpQueryStandardInfo
0x14001463b  mov     ecx, dword ptr [rsp+58h+arg_0]
0x14001463f  test    eax, eax
0x140014641  cmovs   r15d, eax
0x140014645  xor     eax, eax
0x140014647  add     ecx, 0FFFFFFF8h
0x14001464a  mov     [r12+40h], rax
0x14001464f  test    r14, r14
0x140014652  jz      short loc_14001465B
0x140014654  movsxd  rax, dword ptr [r14+1C8h]
0x14001465b  mov     [r12+40h], rax
0x140014660  lea     r8, [r12+50h]
0x140014665  add     ecx, 0FFFFFFFCh
0x140014668  mov     [rsp+58h+var_38], esi
0x14001466c  mov     dword ptr [rsp+58h+arg_0], ecx
0x140014670  lea     r9, [rsp+58h+arg_0]
0x140014675  xor     eax, eax
0x140014677  mov     rcx, rbx
0x14001467a  mov     rdx, r14
0x14001467d  mov     [r12+48h], eax
0x140014682  call    NpQueryPositionInfo
0x140014687  test    eax, eax
0x140014689  lea     r8, [r12+60h]
0x14001468e  lea     r9, [rsp+58h+arg_0]
0x140014693  mov     rdx, r14
0x140014696  mov     rcx, rbx
0x140014699  cmovs   r15d, eax
0x14001469d  call    NpQueryNameInfo
0x1400146a2  mov     edx, dword ptr [rsp+58h+arg_0]
0x1400146a6  test    eax, eax
0x1400146a8  jns     loc_14001446A
0x1400146ae  mov     r15d, eax
0x1400146b1  jmp     loc_14001446A
0x1400146b6  xor     eax, eax; jumptable 00000001400144AB case 7
0x1400146b8  add     edx, 0FFFFFFFCh
0x1400146bb  mov     [r12], eax
0x1400146bf  xor     r15d, r15d
0x1400146c2  jmp     loc_14001446A
```
