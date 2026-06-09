# DifRegisterPlugin

- ea: `0x140538640`
- end: `0x140538a30`
- name: `DifRegisterPlugin`
- size: `1008`
- prototype: ``
- caller_count: `14`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1406350d0`
- `0x140635fd0`
- `0x140636c70`
- `0x140636fe0`
- `0x140638d80`
- `0x140638e90`
- `0x140639540`
- `0x140639800`
- `0x140678ff0`
- `0x1406d8090`
- `0x1406d8680`
- `0x140bd3f80`
- `0x140bd9060`
- `0x140bdc8a0`

## callees

- `0x1402b0d54`
- `0x140538640`
- `0x140538a38`
- `0x140538c68`
- `0x14063c5c4`
- `0x1406f4480`
- `0x140bae410`
- `0x140bae8e0`
- `0x140bc5494`
- `0x140bc54d4`
- `0x140bc5534`

## string_xrefs

- `0x140538a08`: `Loading plugin %d failed!!!\n`
- `0x1405386de`: `API %d is not available for the plugin %d.\n`

## pseudocode

```c
__int64 __fastcall DifRegisterPlugin(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  __int64 v4; // r12
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rsi
  unsigned int v9; // r9d
  __int64 v10; // rdi
  __int64 v11; // rax
  size_t v12; // rdi
  void *Pool2; // rax
  void *v14; // rbp
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // r15
  __int64 v18; // r14
  __int64 v19; // rax
  __int64 **v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  char v28; // al
  __int64 v29; // rax
  _QWORD *v30; // rdx
  _QWORD *v31; // rax
  __int64 v32; // rax
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  _QWORD *v35; // rax
  __int64 v36; // rax
  __int64 v38; // [rsp+70h] [rbp+8h]
  unsigned int v39; // [rsp+78h] [rbp+10h]
  unsigned int v40; // [rsp+80h] [rbp+18h]

  v39 = a2;
  v38 = a1;
  v4 = a3;
  if ( a3 >= 0x40 || (v5 = *((_DWORD *)&qword_140E4E1E0 + ((unsigned __int64)a3 >> 5)), !_bittest(&v5, a3 & 0x1F)) )
  {
    v6 = -1073738636;
LABEL_54:
    sub_140538C68("Loading plugin %d failed!!!\n", a2);
    sub_140538A38((unsigned int)v4);
    return v6;
  }
  v6 = 0;
  if ( byte_140E4E230[a3] )
    return v6;
  v7 = 0;
  while ( 1 )
  {
    v40 = v7;
    if ( v7 >= a2 )
      break;
    v8 = a1 + 32LL * v7;
    v9 = *(_DWORD *)(v8 + 8);
    if ( v9 < 0x80000000 && !(unsigned __int8)sub_140BC5534(v9) )
    {
      sub_140538C68("API %d is not available for the plugin %d.\n", v9, v4);
      goto LABEL_43;
    }
    v10 = sub_1402B0D54(v9);
    if ( v10 )
    {
      if ( *(_QWORD *)(v8 + 16) )
      {
        v29 = sub_14063C5C4(v8, 1, (unsigned int)v4);
        if ( !v29 )
          goto LABEL_45;
        v30 = *(_QWORD **)(v10 + 40);
        if ( *v30 != v10 + 32 )
          goto LABEL_47;
        v31 = (_QWORD *)(v29 + 16);
        v31[1] = v30;
        *v31 = v10 + 32;
        *v30 = v31;
        *(_QWORD *)(v10 + 40) = v31;
      }
      if ( *(_QWORD *)(v8 + 24) )
      {
        v32 = sub_14063C5C4(v8, 0, (unsigned int)v4);
        if ( !v32 )
          goto LABEL_45;
        v33 = (_QWORD *)(v10 + 48);
        v34 = *(_QWORD *)(v10 + 48);
        if ( *(_QWORD *)(v34 + 8) != v10 + 48 )
LABEL_47:
          __fastfail(3u);
        v35 = (_QWORD *)(v32 + 16);
        v35[1] = v33;
        *v35 = v34;
        *(_QWORD *)(v34 + 8) = v35;
        *v33 = v35;
      }
      goto LABEL_43;
    }
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(*(_QWORD *)v8 + v11) );
    v12 = v11 + 1;
    Pool2 = (void *)ExAllocatePool2(64, v11 + 1, 1883334212);
    v14 = Pool2;
    if ( !Pool2 )
      goto LABEL_45;
    memmove(Pool2, *(const void **)v8, v12);
    v15 = ExAllocatePool2(64, 64, 1883334212);
    v16 = v15;
    if ( !v15 )
    {
      v6 = -1073741801;
      ExFreePoolWithTag(v14, 0x4E666944u);
      goto LABEL_54;
    }
    *(_QWORD *)v15 = v14;
    v17 = v15 + 32;
    v18 = v15 + 48;
    *(_DWORD *)(v15 + 8) = *(_DWORD *)(v8 + 8);
    *(_QWORD *)(v15 + 40) = v15 + 32;
    *(_QWORD *)(v15 + 32) = v15 + 32;
    *(_QWORD *)(v15 + 56) = v15 + 48;
    *(_QWORD *)(v15 + 48) = v15 + 48;
    if ( *(_QWORD *)(v8 + 16) )
    {
      v19 = sub_14063C5C4(v8, 1, (unsigned int)v4);
      if ( !v19 )
        goto LABEL_44;
      v20 = *(__int64 ***)(v17 + 8);
      if ( *v20 != (__int64 *)v17 )
        goto LABEL_47;
      v21 = (__int64 *)(v19 + 16);
      v21[1] = (__int64)v20;
      *v21 = v17;
      *v20 = v21;
      *(_QWORD *)(v17 + 8) = v21;
    }
    if ( *(_QWORD *)(v8 + 24) )
    {
      v22 = sub_14063C5C4(v8, 0, (unsigned int)v4);
      if ( !v22 )
      {
LABEL_44:
        ExFreePoolWithTag(v14, 0x4E666944u);
        ExFreePoolWithTag((PVOID)v16, 0x4E666944u);
LABEL_45:
        v6 = -1073741801;
        goto LABEL_54;
      }
      v23 = *(_QWORD *)v18;
      if ( *(_QWORD *)(*(_QWORD *)v18 + 8LL) != v18 )
        goto LABEL_47;
      v24 = (_QWORD *)(v22 + 16);
      v24[1] = v18;
      *v24 = v23;
      *(_QWORD *)(v23 + 8) = v24;
      *(_QWORD *)v18 = v24;
    }
    v25 = (_QWORD *)*((_QWORD *)&xmmword_140EF20D0 + 1);
    if ( **((__int128 ***)&xmmword_140EF20D0 + 1) != &xmmword_140EF20D0 )
      goto LABEL_47;
    *(_QWORD *)(v16 + 16) = &xmmword_140EF20D0;
    *(_QWORD *)(v16 + 24) = v25;
    *v25 = v16 + 16;
    *((_QWORD *)&xmmword_140EF20D0 + 1) = v16 + 16;
    v26 = *(unsigned int *)(v16 + 8);
    if ( (unsigned int)v26 >= 0x10000000 )
    {
      if ( (unsigned int)v26 >= 0x50000000 )
      {
        if ( (unsigned int)v26 >= 0x80000000 || (unsigned int)(v26 - 1342177280) >= 0x21 )
          goto LABEL_43;
        v28 = sub_140BC5494(v26, off_1400090D0[(unsigned int)(v26 - 1342177280)], v16);
        goto LABEL_33;
      }
      if ( (_DWORD)v26 != 0x10000000 )
        goto LABEL_43;
      v27 = *(_QWORD *)&funcs_140471498;
    }
    else
    {
      if ( (unsigned int)v26 >= 0x378 )
        goto LABEL_43;
      v27 = (__int64)*(&off_1400091E0 + v26);
    }
    v28 = sub_140BC54D4(v26, v27, v16);
LABEL_33:
    if ( !v28 )
    {
      sub_140538C68("Binding failure for 0x%x\n", *(_DWORD *)(v16 + 8));
      v6 = -1073738625;
      goto LABEL_54;
    }
LABEL_43:
    a2 = v39;
    v7 = v40 + 1;
    a1 = v38;
  }
  if ( a4 )
  {
    v36 = ExAllocatePool2(64, 40, 1883334212);
    if ( !v36 )
      goto LABEL_45;
    *(_OWORD *)v36 = *(_OWORD *)a4;
    *(_OWORD *)(v36 + 16) = *(_OWORD *)(a4 + 16);
    *(_QWORD *)(v36 + 32) = *(_QWORD *)(a4 + 32);
  }
  else
  {
    v36 = 0;
  }
  qword_140E4E270[v4] = v36;
  byte_140E4E230[v4] = 1;
  return v6;
}

```

## disassembly

```asm
0x140538640  mov     [rsp+arg_18], r9
0x140538645  mov     [rsp+arg_8], edx
0x140538649  mov     [rsp+arg_0], rcx
0x14053864e  push    rbx
0x14053864f  push    rbp
0x140538650  push    rsi
0x140538651  push    rdi
0x140538652  push    r12
0x140538654  push    r13
0x140538656  push    r14
0x140538658  push    r15
0x14053865a  sub     rsp, 28h
0x14053865e  mov     r12d, r8d
0x140538661  cmp     r8d, 40h ; '@'
0x140538665  jnb     loc_140538A03
0x14053866b  mov     al, r12b
0x14053866e  lea     rsi, cs:140000000h
0x140538675  and     al, 1Fh
0x140538677  movzx   r10d, al
0x14053867b  mov     eax, r12d
0x14053867e  shr     rax, 5
0x140538682  mov     eax, dword ptr rva qword_140E4E1E0[rsi+rax*4]
0x140538689  bt      eax, r10d
0x14053868d  jnb     loc_140538A03
0x140538693  xor     r15d, r15d
0x140538696  mov     ebx, r15d
0x140538699  cmp     rva byte_140E4E230[rsi+r12], r15b
0x1405386a1  jnz     loc_140538A1C
0x1405386a7  mov     eax, r15d
0x1405386aa  mov     [rsp+68h+arg_10], eax
0x1405386b1  cmp     eax, edx
0x1405386b3  jnb     loc_1405389A7
0x1405386b9  mov     esi, eax
0x1405386bb  shl     rsi, 5
0x1405386bf  add     rsi, rcx
0x1405386c2  mov     r9d, [rsi+8]
0x1405386c6  cmp     r9d, 80000000h
0x1405386cd  jnb     short loc_1405386F2
0x1405386cf  mov     ecx, r9d
0x1405386d2  call    sub_140BC5534
0x1405386d7  test    al, al
0x1405386d9  jnz     short loc_1405386F2
0x1405386db  mov     r8d, r12d
0x1405386de  lea     rcx, aApiDIsNotAvail; "API %d is not available for the plugin "...
0x1405386e5  mov     edx, r9d
0x1405386e8  call    sub_140538C68
0x1405386ed  jmp     loc_140538954
0x1405386f2  mov     ecx, r9d
0x1405386f5  call    sub_1402B0D54
0x1405386fa  mov     rdi, rax
0x1405386fd  test    rax, rax
0x140538700  jnz     loc_1405388DB
0x140538706  mov     rcx, [rsi]
0x140538709  or      rax, 0FFFFFFFFFFFFFFFFh
0x14053870d  inc     rax
0x140538710  cmp     [rcx+rax], r15b
0x140538714  jnz     short loc_14053870D
0x140538716  lea     rdi, [rax+1]
0x14053871a  mov     r8d, 70416644h
0x140538720  mov     rdx, rdi
0x140538723  mov     ecx, 40h ; '@'
0x140538728  call    ExAllocatePool2
0x14053872d  mov     rbp, rax
0x140538730  test    rax, rax
0x140538733  jz      loc_140538985
0x140538739  mov     rdx, [rsi]; Src
0x14053873c  mov     r8, rdi; Size
0x14053873f  mov     rcx, rax; void *
0x140538742  call    memmove
0x140538747  mov     edx, 40h ; '@'
0x14053874c  mov     r8d, 70416644h
0x140538752  mov     ecx, edx
0x140538754  call    ExAllocatePool2
0x140538759  mov     rdi, rax
0x14053875c  test    rax, rax
0x14053875f  jz      loc_14053898C
0x140538765  mov     [rax], rbp
0x140538768  lea     r15, [rax+20h]
0x14053876c  mov     ecx, [rsi+8]
0x14053876f  lea     r14, [rax+30h]
0x140538773  mov     [rax+8], ecx
0x140538776  mov     [rax+28h], r15
0x14053877a  mov     [r15], r15
0x14053877d  mov     [rax+38h], r14
0x140538781  mov     [r14], r14
0x140538784  cmp     [rsi+10h], rbx
0x140538788  jz      short loc_1405387C2
0x14053878a  mov     r8d, r12d
0x14053878d  mov     edx, 1
0x140538792  mov     rcx, rsi
0x140538795  call    sub_14063C5C4
0x14053879a  test    rax, rax
0x14053879d  jz      loc_14053896B
0x1405387a3  mov     rcx, [r15+8]
0x1405387a7  cmp     [rcx], r15
0x1405387aa  jnz     loc_1405389A0
0x1405387b0  add     rax, 10h
0x1405387b4  mov     [rax+8], rcx
0x1405387b8  mov     [rax], r15
0x1405387bb  mov     [rcx], rax
0x1405387be  mov     [r15+8], rax
0x1405387c2  xor     r15d, r15d
0x1405387c5  cmp     [rsi+18h], r15
0x1405387c9  jz      short loc_140538800
0x1405387cb  mov     r8d, r12d
0x1405387ce  xor     edx, edx
0x1405387d0  mov     rcx, rsi
0x1405387d3  call    sub_14063C5C4
0x1405387d8  test    rax, rax
0x1405387db  jz      loc_14053896B
0x1405387e1  mov     rcx, [r14]
0x1405387e4  cmp     [rcx+8], r14
0x1405387e8  jnz     loc_1405389A0
0x1405387ee  add     rax, 10h
0x1405387f2  mov     [rax+8], r14
0x1405387f6  mov     [rax], rcx
0x1405387f9  mov     [rcx+8], rax
0x1405387fd  mov     [r14], rax
0x140538800  mov     rcx, qword ptr cs:xmmword_140EF20D0+8
0x140538807  lea     r8, xmmword_140EF20D0
0x14053880e  cmp     [rcx], r8
0x140538811  jnz     loc_1405389A0
0x140538817  lea     rax, [rdi+10h]
0x14053881b  mov     [rax], r8
0x14053881e  mov     [rax+8], rcx
0x140538822  mov     [rcx], rax
0x140538825  mov     qword ptr cs:xmmword_140EF20D0+8, rax
0x14053882c  mov     ecx, [rdi+8]
0x14053882f  cmp     ecx, 10000000h
0x140538835  jnb     short loc_140538854
0x140538837  cmp     ecx, 378h
0x14053883d  jnb     loc_140538954
0x140538843  lea     rax, cs:140000000h
0x14053884a  mov     rdx, ds:rva off_1400091E0[rax+rcx*8]
0x140538852  jmp     short loc_14053887C
0x140538854  cmp     ecx, 50000000h
0x14053885a  jnb     short loc_140538886
0x14053885c  lea     eax, [rcx-10000000h]
0x140538862  cmp     eax, 1
0x140538865  jnb     loc_140538954
0x14053886b  mov     edx, eax
0x14053886d  lea     rax, cs:140000000h
0x140538874  mov     rdx, ds:rva funcs_140471498[rax+rdx*8]
0x14053887c  mov     r8, rdi
0x14053887f  call    sub_140BC54D4
0x140538884  jmp     short loc_1405388BA
0x140538886  cmp     ecx, 80000000h
0x14053888c  jnb     loc_140538954
0x140538892  lea     eax, [rcx-50000000h]
0x140538898  cmp     eax, 21h ; '!'
0x14053889b  jnb     loc_140538954
0x1405388a1  mov     edx, eax
0x1405388a3  mov     r8, rdi
0x1405388a6  lea     rax, cs:140000000h
0x1405388ad  mov     rdx, ds:rva off_1400090D0[rax+rdx*8]
0x1405388b5  call    sub_140BC5494
0x1405388ba  test    al, al
0x1405388bc  jnz     loc_140538954
0x1405388c2  mov     edx, [rdi+8]
0x1405388c5  lea     rcx, aBindingFailure; "Binding failure for 0x%x\n"
0x1405388cc  call    sub_140538C68
0x1405388d1  mov     ebx, 0C0000C7Fh
0x1405388d6  jmp     loc_140538A08
0x1405388db  cmp     [rsi+10h], r15
0x1405388df  jz      short loc_14053891D
0x1405388e1  mov     r8d, r12d
0x1405388e4  mov     edx, 1
0x1405388e9  mov     rcx, rsi
0x1405388ec  call    sub_14063C5C4
0x1405388f1  test    rax, rax
0x1405388f4  jz      loc_140538985
0x1405388fa  lea     rcx, [rdi+20h]
0x1405388fe  mov     rdx, [rcx+8]
0x140538902  cmp     [rdx], rcx
0x140538905  jnz     loc_1405389A0
0x14053890b  add     rax, 10h
0x14053890f  mov     [rax+8], rdx
0x140538913  mov     [rax], rcx
0x140538916  mov     [rdx], rax
0x140538919  mov     [rcx+8], rax
0x14053891d  cmp     [rsi+18h], r15
0x140538921  jz      short loc_140538954
0x140538923  mov     r8d, r12d
0x140538926  xor     edx, edx
0x140538928  mov     rcx, rsi
0x14053892b  call    sub_14063C5C4
0x140538930  test    rax, rax
0x140538933  jz      short loc_140538985
0x140538935  lea     rcx, [rdi+30h]
0x140538939  mov     rdx, [rcx]
0x14053893c  cmp     [rdx+8], rcx
0x140538940  jnz     short loc_1405389A0
0x140538942  add     rax, 10h
0x140538946  mov     [rax+8], rcx
0x14053894a  mov     [rax], rdx
0x14053894d  mov     [rdx+8], rax
0x140538951  mov     [rcx], rax
0x140538954  mov     eax, [rsp+68h+arg_10]
0x14053895b  mov     edx, [rsp+68h+arg_8]
0x14053895f  inc     eax
0x140538961  mov     rcx, [rsp+68h+arg_0]
0x140538966  jmp     loc_1405386AA
0x14053896b  mov     edx, 4E666944h; Tag
0x140538970  mov     rcx, rbp; P
0x140538973  call    ExFreePoolWithTag
0x140538978  mov     edx, 4E666944h; Tag
0x14053897d  mov     rcx, rdi; P
0x140538980  call    ExFreePoolWithTag
0x140538985  mov     ebx, 0C0000017h
0x14053898a  jmp     short loc_140538A08
0x14053898c  mov     edx, 4E666944h; Tag
0x140538991  mov     rcx, rbp; P
0x140538994  mov     ebx, 0C0000017h
0x140538999  call    ExFreePoolWithTag
0x14053899e  jmp     short loc_140538A08
0x1405389a0  mov     ecx, 3
0x1405389a5  int     29h; Win8: RtlFailFast(ecx)
0x1405389a7  mov     rdi, [rsp+68h+arg_18]
0x1405389af  test    rdi, rdi
0x1405389b2  jnz     short loc_1405389B9
0x1405389b4  mov     rax, r15
0x1405389b7  jmp     short loc_1405389E9
0x1405389b9  mov     edx, 28h ; '('
0x1405389be  mov     r8d, 70416644h
0x1405389c4  lea     ecx, [rdx+18h]
0x1405389c7  call    ExAllocatePool2
0x1405389cc  test    rax, rax
0x1405389cf  jz      short loc_140538985
0x1405389d1  movups  xmm0, xmmword ptr [rdi]
0x1405389d4  movups  xmmword ptr [rax], xmm0
0x1405389d7  movups  xmm1, xmmword ptr [rdi+10h]
0x1405389db  movups  xmmword ptr [rax+10h], xmm1
0x1405389df  movsd   xmm0, qword ptr [rdi+20h]
0x1405389e4  movsd   qword ptr [rax+20h], xmm0
0x1405389e9  lea     rcx, cs:140000000h
0x1405389f0  mov     rva qword_140E4E270[rcx+r12*8], rax
0x1405389f8  mov     rva byte_140E4E230[rcx+r12], 1
0x140538a01  jmp     short loc_140538A1C
0x140538a03  mov     ebx, 0C0000C74h
0x140538a08  lea     rcx, aLoadingPluginD; "Loading plugin %d failed!!!\n"
0x140538a0f  call    sub_140538C68
0x140538a14  mov     ecx, r12d
0x140538a17  call    sub_140538A38
0x140538a1c  mov     eax, ebx
0x140538a1e  add     rsp, 28h
0x140538a22  pop     r15
0x140538a24  pop     r14
0x140538a26  pop     r13
0x140538a28  pop     r12
0x140538a2a  pop     rdi
0x140538a2b  pop     rsi
0x140538a2c  pop     rbp
0x140538a2d  pop     rbx
0x140538a2e  retn
```
