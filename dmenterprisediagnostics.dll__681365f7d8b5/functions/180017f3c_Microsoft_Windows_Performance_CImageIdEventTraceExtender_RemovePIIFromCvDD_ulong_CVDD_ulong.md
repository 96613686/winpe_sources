# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(ulong,_CVDD *,ulong *)

- ea: `0x180017f3c`
- end: `0x1800180a8`
- name: `?RemovePIIFromCvDD@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAT_CVDD@@PEAK@Z`
- size: `364`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, unsigned int, union _CVDD *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800129cc`

## callees

- `0x1800029e1`
- `0x18000fe1c`
- `0x180017f3c`

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
0x180017f3c  push    rbx
0x180017f3e  push    rbp
0x180017f3f  push    rsi
0x180017f40  push    rdi
0x180017f41  push    r12
0x180017f43  push    r13
0x180017f45  push    r14
0x180017f47  push    r15
0x180017f49  sub     rsp, 28h
0x180017f4d  xor     r13d, r13d
0x180017f50  mov     r14, r9
0x180017f53  mov     edi, r13d
0x180017f56  mov     r12, r8
0x180017f59  mov     r15d, edx
0x180017f5c  cmp     edi, r15d
0x180017f5f  jnb     loc_180018094
0x180017f65  mov     esi, edi
0x180017f67  cmp     dword ptr [r14+rsi*4], 4
0x180017f6c  jb      loc_180018086
0x180017f72  cmp     dword ptr [r14+rsi*4], 628h
0x180017f7a  ja      loc_18001808D
0x180017f80  imul    rbx, rsi, 628h
0x180017f87  add     rbx, r12
0x180017f8a  mov     ecx, [rbx]
0x180017f8c  sub     ecx, 1
0x180017f8f  jz      loc_18001802D
0x180017f95  sub     ecx, 1
0x180017f98  jz      loc_18001802D
0x180017f9e  sub     ecx, 1
0x180017fa1  jz      short loc_180017FB7
0x180017fa3  sub     ecx, 3031424Bh
0x180017fa9  jz      short loc_180017FF2
0x180017fab  cmp     ecx, 23131104h
0x180017fb1  jnz     loc_180018086
0x180017fb7  mov     edx, 30Ch
0x180017fbc  lea     rcx, [rbx+18h]
0x180017fc0  call    ??$StringCbRChr@D@Performance@Windows@Microsoft@@YAPEADPEAD_KD@Z; Microsoft::Windows::Performance::StringCbRChr<char>(char *,unsigned __int64,char)
0x180017fc5  mov     rbp, rax
0x180017fc8  test    rax, rax
0x180017fcb  jz      loc_180018086
0x180017fd1  mov     r8d, ebx
0x180017fd4  lea     rdx, [rax+1]; Src
0x180017fd8  sub     r8d, ebp
0x180017fdb  lea     rcx, [rbx+18h]; void *
0x180017fdf  add     r8d, 323h; Size
0x180017fe6  call    memmove_0
0x180017feb  sub     ebx, ebp
0x180017fed  add     ebx, 17h
0x180017ff0  jmp     short loc_180018027
0x180017ff2  mov     edx, 104h
0x180017ff7  lea     rcx, [rbx+10h]
0x180017ffb  call    ??$StringCbRChr@D@Performance@Windows@Microsoft@@YAPEADPEAD_KD@Z; Microsoft::Windows::Performance::StringCbRChr<char>(char *,unsigned __int64,char)
0x180018000  mov     rbp, rax
0x180018003  test    rax, rax
0x180018006  jz      short loc_180018086
0x180018008  mov     r8d, ebx
0x18001800b  lea     rdx, [rax+1]; Src
0x18001800f  sub     r8d, ebp
0x180018012  lea     rcx, [rbx+10h]; void *
0x180018016  add     r8d, 113h; Size
0x18001801d  call    memmove_0
0x180018022  sub     ebx, ebp
0x180018024  add     ebx, 0Fh
0x180018027  add     [r14+rsi*4], ebx
0x18001802b  jmp     short loc_180018086
0x18001802d  lea     rcx, [rbx+10h]; void *
0x180018031  mov     rdx, r13
0x180018034  lea     r8, [rcx+618h]
0x18001803b  mov     rax, rcx
0x18001803e  cmp     rax, r8
0x180018041  jnb     short loc_180018057
0x180018043  cmp     [rax], r13w
0x180018047  jz      short loc_180018057
0x180018049  cmp     word ptr [rax], 5Ch ; '\'
0x18001804d  cmovz   rdx, rax
0x180018051  add     rax, 2
0x180018055  jmp     short loc_18001803E
0x180018057  test    rdx, rdx
0x18001805a  jz      short loc_180018086
0x18001805c  mov     rax, rdx
0x18001805f  mov     r8d, 618h
0x180018065  sub     rax, rbx
0x180018068  add     rdx, 2; Src
0x18001806c  sub     rax, 10h
0x180018070  sar     rax, 1
0x180018073  lea     ebx, ds:2[rax*2]
0x18001807a  sub     r8d, ebx; Size
0x18001807d  call    memmove_0
0x180018082  sub     [r14+rsi*4], ebx
0x180018086  inc     edi
0x180018088  jmp     loc_180017F5C
0x18001808d  mov     eax, 8000FFFFh
0x180018092  jmp     short loc_180018096
0x180018094  xor     eax, eax
0x180018096  add     rsp, 28h
0x18001809a  pop     r15
0x18001809c  pop     r14
0x18001809e  pop     r13
0x1800180a0  pop     r12
0x1800180a2  pop     rdi
0x1800180a3  pop     rsi
0x1800180a4  pop     rbp
0x1800180a5  pop     rbx
0x1800180a6  retn
```
