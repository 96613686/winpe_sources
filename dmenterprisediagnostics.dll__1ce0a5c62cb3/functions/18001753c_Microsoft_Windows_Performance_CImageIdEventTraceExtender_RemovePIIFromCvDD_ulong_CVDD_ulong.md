# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(ulong,_CVDD *,ulong *)

- ea: `0x18001753c`
- end: `0x1800176a7`
- name: `?RemovePIIFromCvDD@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAT_CVDD@@PEAK@Z`
- size: `363`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, unsigned int, union _CVDD *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800121e8`

## callees

- `0x1800029c1`
- `0x18000f730`
- `0x18001753c`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        unsigned int a2,
        union _CVDD *a3,
        unsigned int *a4)
{
  unsigned int i; // edi
  char *v8; // rbx
  __int64 v9; // rax
  int v10; // ebp
  int v11; // ebx
  __int64 v12; // rax
  int v13; // ebp
  void *v14; // rcx
  char *v15; // rdx
  char *j; // rax
  int v17; // ebx

  for ( i = 0; i < a2; ++i )
  {
    if ( a4[i] < 4 )
      continue;
    if ( a4[i] > 0x628 )
      return 2147549183LL;
    v8 = (char *)a3 + 1576 * i;
    if ( *(_DWORD *)v8 != 1 && *(_DWORD *)v8 != 2 )
    {
      switch ( *(_DWORD *)v8 )
      {
        case 3:
          goto LABEL_10;
        case 0x3031424E:
          v12 = Microsoft::Windows::Performance::StringCbRChr<char>(v8 + 16, 260);
          v13 = v12;
          if ( !v12 )
            continue;
          memmove_0(v8 + 16, (const void *)(v12 + 1), (unsigned int)((_DWORD)v8 - v12 + 275));
          v11 = (_DWORD)v8 - v13 + 15;
          break;
        case 0x53445352:
LABEL_10:
          v9 = Microsoft::Windows::Performance::StringCbRChr<char>(v8 + 24, 780);
          v10 = v9;
          if ( !v9 )
            continue;
          memmove_0(v8 + 24, (const void *)(v9 + 1), (unsigned int)((_DWORD)v8 - v9 + 803));
          v11 = (_DWORD)v8 - v10 + 23;
          break;
        default:
          continue;
      }
      a4[i] += v11;
      continue;
    }
    v14 = v8 + 16;
    v15 = 0;
    for ( j = v8 + 16; j < v8 + 1576 && *(_WORD *)j; j += 2 )
    {
      if ( *(_WORD *)j == 92 )
        v15 = j;
    }
    if ( v15 )
    {
      v17 = 2 * ((v15 - v8 - 16) >> 1) + 2;
      memmove_0(v14, v15 + 2, (unsigned int)(1560 - v17));
      a4[i] -= v17;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001753c  push    rbx
0x18001753e  push    rbp
0x18001753f  push    rsi
0x180017540  push    rdi
0x180017541  push    r12
0x180017543  push    r13
0x180017545  push    r14
0x180017547  push    r15
0x180017549  sub     rsp, 28h
0x18001754d  xor     r13d, r13d
0x180017550  mov     r14, r9
0x180017553  mov     edi, r13d
0x180017556  mov     r12, r8
0x180017559  mov     r15d, edx
0x18001755c  cmp     edi, r15d
0x18001755f  jnb     loc_180017694
0x180017565  mov     esi, edi
0x180017567  cmp     dword ptr [r14+rsi*4], 4
0x18001756c  jb      loc_180017686
0x180017572  cmp     dword ptr [r14+rsi*4], 628h
0x18001757a  ja      loc_18001768D
0x180017580  imul    rbx, rsi, 628h
0x180017587  add     rbx, r12
0x18001758a  mov     ecx, [rbx]
0x18001758c  sub     ecx, 1
0x18001758f  jz      loc_18001762D
0x180017595  sub     ecx, 1
0x180017598  jz      loc_18001762D
0x18001759e  sub     ecx, 1
0x1800175a1  jz      short loc_1800175B7
0x1800175a3  sub     ecx, 3031424Bh
0x1800175a9  jz      short loc_1800175F2
0x1800175ab  cmp     ecx, 23131104h
0x1800175b1  jnz     loc_180017686
0x1800175b7  mov     edx, 30Ch
0x1800175bc  lea     rcx, [rbx+18h]
0x1800175c0  call    ??$StringCbRChr@D@Performance@Windows@Microsoft@@YAPEADPEAD_KD@Z; Microsoft::Windows::Performance::StringCbRChr<char>(char *,unsigned __int64,char)
0x1800175c5  mov     rbp, rax
0x1800175c8  test    rax, rax
0x1800175cb  jz      loc_180017686
0x1800175d1  mov     r8d, ebx
0x1800175d4  lea     rdx, [rax+1]; Src
0x1800175d8  sub     r8d, ebp
0x1800175db  lea     rcx, [rbx+18h]; void *
0x1800175df  add     r8d, 323h; Size
0x1800175e6  call    memmove_0
0x1800175eb  sub     ebx, ebp
0x1800175ed  add     ebx, 17h
0x1800175f0  jmp     short loc_180017627
0x1800175f2  mov     edx, 104h
0x1800175f7  lea     rcx, [rbx+10h]
0x1800175fb  call    ??$StringCbRChr@D@Performance@Windows@Microsoft@@YAPEADPEAD_KD@Z; Microsoft::Windows::Performance::StringCbRChr<char>(char *,unsigned __int64,char)
0x180017600  mov     rbp, rax
0x180017603  test    rax, rax
0x180017606  jz      short loc_180017686
0x180017608  mov     r8d, ebx
0x18001760b  lea     rdx, [rax+1]; Src
0x18001760f  sub     r8d, ebp
0x180017612  lea     rcx, [rbx+10h]; void *
0x180017616  add     r8d, 113h; Size
0x18001761d  call    memmove_0
0x180017622  sub     ebx, ebp
0x180017624  add     ebx, 0Fh
0x180017627  add     [r14+rsi*4], ebx
0x18001762b  jmp     short loc_180017686
0x18001762d  lea     rcx, [rbx+10h]; void *
0x180017631  mov     rdx, r13
0x180017634  lea     r8, [rcx+618h]
0x18001763b  mov     rax, rcx
0x18001763e  cmp     rax, r8
0x180017641  jnb     short loc_180017657
0x180017643  cmp     [rax], r13w
0x180017647  jz      short loc_180017657
0x180017649  cmp     word ptr [rax], 5Ch ; '\'
0x18001764d  cmovz   rdx, rax
0x180017651  add     rax, 2
0x180017655  jmp     short loc_18001763E
0x180017657  test    rdx, rdx
0x18001765a  jz      short loc_180017686
0x18001765c  mov     rax, rdx
0x18001765f  mov     r8d, 618h
0x180017665  sub     rax, rbx
0x180017668  add     rdx, 2; Src
0x18001766c  sub     rax, 10h
0x180017670  sar     rax, 1
0x180017673  lea     ebx, ds:2[rax*2]
0x18001767a  sub     r8d, ebx; Size
0x18001767d  call    memmove_0
0x180017682  sub     [r14+rsi*4], ebx
0x180017686  inc     edi
0x180017688  jmp     loc_18001755C
0x18001768d  mov     eax, 8000FFFFh
0x180017692  jmp     short loc_180017696
0x180017694  xor     eax, eax
0x180017696  add     rsp, 28h
0x18001769a  pop     r15
0x18001769c  pop     r14
0x18001769e  pop     r13
0x1800176a0  pop     r12
0x1800176a2  pop     rdi
0x1800176a3  pop     rsi
0x1800176a4  pop     rbp
0x1800176a5  pop     rbx
0x1800176a6  retn
```
