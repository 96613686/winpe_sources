# DifRegisterPlugin

- ea: `0x14053fcf0`
- end: `0x1405400e0`
- name: `DifRegisterPlugin`
- size: `1008`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64)`
- caller_count: `14`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x14063abc0`
- `0x14063bac0`
- `0x14063c760`
- `0x14063cad0`
- `0x14063e870`
- `0x14063e980`
- `0x14063f030`
- `0x14063f2f0`
- `0x14067eae0`
- `0x1406dabe0`
- `0x1406db1d0`
- `0x140bd6f80`
- `0x140bdc060`
- `0x140bdf8a0`

## callees

- `0x1402c0554`
- `0x14053fcf0`
- `0x1405400e8`
- `0x140540318`
- `0x1406420b4`
- `0x1406f6f80`
- `0x140bb1410`
- `0x140bb19f0`
- `0x140bc8494`
- `0x140bc84d4`
- `0x140bc8534`

## string_xrefs

- `0x14053fd8e`: `API %d is not available for the plugin %d.\n`
- `0x1405400b8`: `Loading plugin %d failed!!!\n`

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
  __int64 APIThunkContextById; // rdi
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
  __int64 APIThunkContext; // rax
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
  if ( a3 >= 0x40 || (v5 = *((_DWORD *)&VfRuleClasses + ((unsigned __int64)a3 >> 5)), !_bittest(&v5, a3 & 0x1F)) )
  {
    v6 = -1073738636;
LABEL_54:
    DifiDbgPrint("Loading plugin %d failed!!!\n", a2);
    DifDeregisterPlugin((unsigned int)v4);
    return v6;
  }
  v6 = 0;
  if ( DifPluginStates[a3] )
    return v6;
  v7 = 0;
  while ( 1 )
  {
    v40 = v7;
    if ( v7 >= a2 )
      break;
    v8 = a1 + 32LL * v7;
    v9 = *(_DWORD *)(v8 + 8);
    if ( v9 < 0x80000000 && !(unsigned __int8)VfCheckDifDdiExist(v9) )
    {
      DifiDbgPrint("API %d is not available for the plugin %d.\n", v9, v4);
      goto LABEL_43;
    }
    APIThunkContextById = DifGetAPIThunkContextById(v9);
    if ( APIThunkContextById )
    {
      if ( *(_QWORD *)(v8 + 16) )
      {
        APIThunkContext = DifCreateAPIThunkContext(v8, 1, v4);
        if ( !APIThunkContext )
          goto LABEL_45;
        v30 = *(_QWORD **)(APIThunkContextById + 40);
        if ( *v30 != APIThunkContextById + 32 )
          goto LABEL_47;
        v31 = (_QWORD *)(APIThunkContext + 16);
        v31[1] = v30;
        *v31 = APIThunkContextById + 32;
        *v30 = v31;
        *(_QWORD *)(APIThunkContextById + 40) = v31;
      }
      if ( *(_QWORD *)(v8 + 24) )
      {
        v32 = DifCreateAPIThunkContext(v8, 0, v4);
        if ( !v32 )
          goto LABEL_45;
        v33 = (_QWORD *)(APIThunkContextById + 48);
        v34 = *(_QWORD *)(APIThunkContextById + 48);
        if ( *(_QWORD *)(v34 + 8) != APIThunkContextById + 48 )
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
      v19 = DifCreateAPIThunkContext(v8, 1, v4);
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
      v22 = DifCreateAPIThunkContext(v8, 0, v4);
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
    v25 = (_QWORD *)*((_QWORD *)&DifAPIThunkContextHead + 1);
    if ( **((__int128 ***)&DifAPIThunkContextHead + 1) != &DifAPIThunkContextHead )
      goto LABEL_47;
    *(_QWORD *)(v16 + 16) = &DifAPIThunkContextHead;
    *(_QWORD *)(v16 + 24) = v25;
    *v25 = v16 + 16;
    *((_QWORD *)&DifAPIThunkContextHead + 1) = v16 + 16;
    v26 = *(unsigned int *)(v16 + 8);
    if ( (unsigned int)v26 >= 0x10000000 )
    {
      if ( (unsigned int)v26 >= 0x50000000 )
      {
        if ( (unsigned int)v26 >= 0x80000000 || (unsigned int)(v26 - 1342177280) >= 0x21 )
          goto LABEL_43;
        v28 = VfBindDifCallbackWrappers(v26, off_1400090C0[(unsigned int)(v26 - 1342177280)], v16);
        goto LABEL_33;
      }
      if ( (_DWORD)v26 != 0x10000000 )
        goto LABEL_43;
      v27 = *(_QWORD *)&CLFS_LSN_NULL_EXT;
    }
    else
    {
      if ( (unsigned int)v26 >= 0x378 )
        goto LABEL_43;
      v27 = (__int64)*(&off_1400091D0 + v26);
    }
    v28 = VfBindDifDDIWrappers(v26, v27, v16);
LABEL_33:
    if ( !v28 )
    {
      DifiDbgPrint("Binding failure for 0x%x\n", *(_DWORD *)(v16 + 8));
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
  DifPluginSettings[v4] = v36;
  DifPluginStates[v4] = 1;
  return v6;
}

```

## disassembly

```asm
0x14053fcf0  mov     [rsp+arg_18], r9
0x14053fcf5  mov     [rsp+arg_8], edx
0x14053fcf9  mov     [rsp+arg_0], rcx
0x14053fcfe  push    rbx
0x14053fcff  push    rbp
0x14053fd00  push    rsi
0x14053fd01  push    rdi
0x14053fd02  push    r12
0x14053fd04  push    r13
0x14053fd06  push    r14
0x14053fd08  push    r15
0x14053fd0a  sub     rsp, 28h
0x14053fd0e  mov     r12d, r8d
0x14053fd11  cmp     r8d, 40h ; '@'
0x14053fd15  jnb     loc_1405400B3
0x14053fd1b  mov     al, r12b
0x14053fd1e  lea     rsi, cs:140000000h
0x14053fd25  and     al, 1Fh
0x14053fd27  movzx   r10d, al
0x14053fd2b  mov     eax, r12d
0x14053fd2e  shr     rax, 5
0x14053fd32  mov     eax, dword ptr rva VfRuleClasses[rsi+rax*4]
0x14053fd39  bt      eax, r10d
0x14053fd3d  jnb     loc_1405400B3
0x14053fd43  xor     r15d, r15d
0x14053fd46  mov     ebx, r15d
0x14053fd49  cmp     rva DifPluginStates[rsi+r12], r15b
0x14053fd51  jnz     loc_1405400CC
0x14053fd57  mov     eax, r15d
0x14053fd5a  mov     [rsp+68h+arg_10], eax
0x14053fd61  cmp     eax, edx
0x14053fd63  jnb     loc_140540057
0x14053fd69  mov     esi, eax
0x14053fd6b  shl     rsi, 5
0x14053fd6f  add     rsi, rcx
0x14053fd72  mov     r9d, [rsi+8]
0x14053fd76  cmp     r9d, 80000000h
0x14053fd7d  jnb     short loc_14053FDA2
0x14053fd7f  mov     ecx, r9d
0x14053fd82  call    VfCheckDifDdiExist
0x14053fd87  test    al, al
0x14053fd89  jnz     short loc_14053FDA2
0x14053fd8b  mov     r8d, r12d
0x14053fd8e  lea     rcx, aApiDIsNotAvail; "API %d is not available for the plugin "...
0x14053fd95  mov     edx, r9d
0x14053fd98  call    DifiDbgPrint
0x14053fd9d  jmp     loc_140540004
0x14053fda2  mov     ecx, r9d
0x14053fda5  call    DifGetAPIThunkContextById
0x14053fdaa  mov     rdi, rax
0x14053fdad  test    rax, rax
0x14053fdb0  jnz     loc_14053FF8B
0x14053fdb6  mov     rcx, [rsi]
0x14053fdb9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14053fdbd  inc     rax
0x14053fdc0  cmp     [rcx+rax], r15b
0x14053fdc4  jnz     short loc_14053FDBD
0x14053fdc6  lea     rdi, [rax+1]
0x14053fdca  mov     r8d, 70416644h
0x14053fdd0  mov     rdx, rdi
0x14053fdd3  mov     ecx, 40h ; '@'
0x14053fdd8  call    ExAllocatePool2
0x14053fddd  mov     rbp, rax
0x14053fde0  test    rax, rax
0x14053fde3  jz      loc_140540035
0x14053fde9  mov     rdx, [rsi]; Src
0x14053fdec  mov     r8, rdi; Size
0x14053fdef  mov     rcx, rax; void *
0x14053fdf2  call    memmove
0x14053fdf7  mov     edx, 40h ; '@'
0x14053fdfc  mov     r8d, 70416644h
0x14053fe02  mov     ecx, edx
0x14053fe04  call    ExAllocatePool2
0x14053fe09  mov     rdi, rax
0x14053fe0c  test    rax, rax
0x14053fe0f  jz      loc_14054003C
0x14053fe15  mov     [rax], rbp
0x14053fe18  lea     r15, [rax+20h]
0x14053fe1c  mov     ecx, [rsi+8]
0x14053fe1f  lea     r14, [rax+30h]
0x14053fe23  mov     [rax+8], ecx
0x14053fe26  mov     [rax+28h], r15
0x14053fe2a  mov     [r15], r15
0x14053fe2d  mov     [rax+38h], r14
0x14053fe31  mov     [r14], r14
0x14053fe34  cmp     [rsi+10h], rbx
0x14053fe38  jz      short loc_14053FE72
0x14053fe3a  mov     r8d, r12d
0x14053fe3d  mov     edx, 1
0x14053fe42  mov     rcx, rsi
0x14053fe45  call    DifCreateAPIThunkContext
0x14053fe4a  test    rax, rax
0x14053fe4d  jz      loc_14054001B
0x14053fe53  mov     rcx, [r15+8]
0x14053fe57  cmp     [rcx], r15
0x14053fe5a  jnz     loc_140540050
0x14053fe60  add     rax, 10h
0x14053fe64  mov     [rax+8], rcx
0x14053fe68  mov     [rax], r15
0x14053fe6b  mov     [rcx], rax
0x14053fe6e  mov     [r15+8], rax
0x14053fe72  xor     r15d, r15d
0x14053fe75  cmp     [rsi+18h], r15
0x14053fe79  jz      short loc_14053FEB0
0x14053fe7b  mov     r8d, r12d
0x14053fe7e  xor     edx, edx
0x14053fe80  mov     rcx, rsi
0x14053fe83  call    DifCreateAPIThunkContext
0x14053fe88  test    rax, rax
0x14053fe8b  jz      loc_14054001B
0x14053fe91  mov     rcx, [r14]
0x14053fe94  cmp     [rcx+8], r14
0x14053fe98  jnz     loc_140540050
0x14053fe9e  add     rax, 10h
0x14053fea2  mov     [rax+8], r14
0x14053fea6  mov     [rax], rcx
0x14053fea9  mov     [rcx+8], rax
0x14053fead  mov     [r14], rax
0x14053feb0  mov     rcx, qword ptr cs:DifAPIThunkContextHead+8
0x14053feb7  lea     r8, DifAPIThunkContextHead
0x14053febe  cmp     [rcx], r8
0x14053fec1  jnz     loc_140540050
0x14053fec7  lea     rax, [rdi+10h]
0x14053fecb  mov     [rax], r8
0x14053fece  mov     [rax+8], rcx
0x14053fed2  mov     [rcx], rax
0x14053fed5  mov     qword ptr cs:DifAPIThunkContextHead+8, rax
0x14053fedc  mov     ecx, [rdi+8]
0x14053fedf  cmp     ecx, 10000000h
0x14053fee5  jnb     short loc_14053FF04
0x14053fee7  cmp     ecx, 378h
0x14053feed  jnb     loc_140540004
0x14053fef3  lea     rax, cs:140000000h
0x14053fefa  mov     rdx, ds:rva off_1400091D0[rax+rcx*8]
0x14053ff02  jmp     short loc_14053FF2C
0x14053ff04  cmp     ecx, 50000000h
0x14053ff0a  jnb     short loc_14053FF36
0x14053ff0c  lea     eax, [rcx-10000000h]
0x14053ff12  cmp     eax, 1
0x14053ff15  jnb     loc_140540004
0x14053ff1b  mov     edx, eax
0x14053ff1d  lea     rax, cs:140000000h
0x14053ff24  mov     rdx, ds:rva CLFS_LSN_NULL_EXT[rax+rdx*8]
0x14053ff2c  mov     r8, rdi
0x14053ff2f  call    VfBindDifDDIWrappers
0x14053ff34  jmp     short loc_14053FF6A
0x14053ff36  cmp     ecx, 80000000h
0x14053ff3c  jnb     loc_140540004
0x14053ff42  lea     eax, [rcx-50000000h]
0x14053ff48  cmp     eax, 21h ; '!'
0x14053ff4b  jnb     loc_140540004
0x14053ff51  mov     edx, eax
0x14053ff53  mov     r8, rdi
0x14053ff56  lea     rax, cs:140000000h
0x14053ff5d  mov     rdx, ds:rva off_1400090C0[rax+rdx*8]
0x14053ff65  call    VfBindDifCallbackWrappers
0x14053ff6a  test    al, al
0x14053ff6c  jnz     loc_140540004
0x14053ff72  mov     edx, [rdi+8]
0x14053ff75  lea     rcx, aBindingFailure; "Binding failure for 0x%x\n"
0x14053ff7c  call    DifiDbgPrint
0x14053ff81  mov     ebx, 0C0000C7Fh
0x14053ff86  jmp     loc_1405400B8
0x14053ff8b  cmp     [rsi+10h], r15
0x14053ff8f  jz      short loc_14053FFCD
0x14053ff91  mov     r8d, r12d
0x14053ff94  mov     edx, 1
0x14053ff99  mov     rcx, rsi
0x14053ff9c  call    DifCreateAPIThunkContext
0x14053ffa1  test    rax, rax
0x14053ffa4  jz      loc_140540035
0x14053ffaa  lea     rcx, [rdi+20h]
0x14053ffae  mov     rdx, [rcx+8]
0x14053ffb2  cmp     [rdx], rcx
0x14053ffb5  jnz     loc_140540050
0x14053ffbb  add     rax, 10h
0x14053ffbf  mov     [rax+8], rdx
0x14053ffc3  mov     [rax], rcx
0x14053ffc6  mov     [rdx], rax
0x14053ffc9  mov     [rcx+8], rax
0x14053ffcd  cmp     [rsi+18h], r15
0x14053ffd1  jz      short loc_140540004
0x14053ffd3  mov     r8d, r12d
0x14053ffd6  xor     edx, edx
0x14053ffd8  mov     rcx, rsi
0x14053ffdb  call    DifCreateAPIThunkContext
0x14053ffe0  test    rax, rax
0x14053ffe3  jz      short loc_140540035
0x14053ffe5  lea     rcx, [rdi+30h]
0x14053ffe9  mov     rdx, [rcx]
0x14053ffec  cmp     [rdx+8], rcx
0x14053fff0  jnz     short loc_140540050
0x14053fff2  add     rax, 10h
0x14053fff6  mov     [rax+8], rcx
0x14053fffa  mov     [rax], rdx
0x14053fffd  mov     [rdx+8], rax
0x140540001  mov     [rcx], rax
0x140540004  mov     eax, [rsp+68h+arg_10]
0x14054000b  mov     edx, [rsp+68h+arg_8]
0x14054000f  inc     eax
0x140540011  mov     rcx, [rsp+68h+arg_0]
0x140540016  jmp     loc_14053FD5A
0x14054001b  mov     edx, 4E666944h; Tag
0x140540020  mov     rcx, rbp; P
0x140540023  call    ExFreePoolWithTag
0x140540028  mov     edx, 4E666944h; Tag
0x14054002d  mov     rcx, rdi; P
0x140540030  call    ExFreePoolWithTag
0x140540035  mov     ebx, 0C0000017h
0x14054003a  jmp     short loc_1405400B8
0x14054003c  mov     edx, 4E666944h; Tag
0x140540041  mov     rcx, rbp; P
0x140540044  mov     ebx, 0C0000017h
0x140540049  call    ExFreePoolWithTag
0x14054004e  jmp     short loc_1405400B8
0x140540050  mov     ecx, 3
0x140540055  int     29h; Win8: RtlFailFast(ecx)
0x140540057  mov     rdi, [rsp+68h+arg_18]
0x14054005f  test    rdi, rdi
0x140540062  jnz     short loc_140540069
0x140540064  mov     rax, r15
0x140540067  jmp     short loc_140540099
0x140540069  mov     edx, 28h ; '('
0x14054006e  mov     r8d, 70416644h
0x140540074  lea     ecx, [rdx+18h]
0x140540077  call    ExAllocatePool2
0x14054007c  test    rax, rax
0x14054007f  jz      short loc_140540035
0x140540081  movups  xmm0, xmmword ptr [rdi]
0x140540084  movups  xmmword ptr [rax], xmm0
0x140540087  movups  xmm1, xmmword ptr [rdi+10h]
0x14054008b  movups  xmmword ptr [rax+10h], xmm1
0x14054008f  movsd   xmm0, qword ptr [rdi+20h]
0x140540094  movsd   qword ptr [rax+20h], xmm0
0x140540099  lea     rcx, cs:140000000h
0x1405400a0  mov     rva DifPluginSettings[rcx+r12*8], rax
0x1405400a8  mov     rva DifPluginStates[rcx+r12], 1
0x1405400b1  jmp     short loc_1405400CC
0x1405400b3  mov     ebx, 0C0000C74h
0x1405400b8  lea     rcx, aLoadingPluginD; "Loading plugin %d failed!!!\n"
0x1405400bf  call    DifiDbgPrint
0x1405400c4  mov     ecx, r12d
0x1405400c7  call    DifDeregisterPlugin
0x1405400cc  mov     eax, ebx
0x1405400ce  add     rsp, 28h
0x1405400d2  pop     r15
0x1405400d4  pop     r14
0x1405400d6  pop     r13
0x1405400d8  pop     r12
0x1405400da  pop     rdi
0x1405400db  pop     rsi
0x1405400dc  pop     rbp
0x1405400dd  pop     rbx
0x1405400de  retn
```
