# FATDateFromPsz

- ea: `0x14000a894`
- end: `0x14000aa63`
- name: `FATDateFromPsz`
- size: `463`
- prototype: `__int64 __fastcall(char *Str)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b2d8`
- `0x14000bf40`

## callees

- `0x140008620`
- `0x14000a894`

## import_xrefs

- `msvcrt!strchr` at `0x14000a8e9`
- `msvcrt!strchr` at `0x14000a92d`
- `msvcrt!strchr` at `0x14000a8e9`
- `msvcrt!strchr` at `0x14000a92d`
- `msvcrt!atoi` at `0x14000a8d6`
- `msvcrt!atoi` at `0x14000a91e`
- `msvcrt!atoi` at `0x14000a93c`
- `msvcrt!atoi` at `0x14000a8d6`
- `msvcrt!atoi` at `0x14000a91e`
- `msvcrt!atoi` at `0x14000a93c`

## pseudocode

```c
__int16 __fastcall FATDateFromPsz(char *Str, __int64 a2)
{
  unsigned __int64 v4; // rax
  unsigned __int8 v5; // bp
  int v6; // r14d
  char *v7; // rax
  const char *v8; // rbx
  unsigned int v9; // r12d
  char *v10; // rax
  unsigned int v11; // eax
  int v12; // ecx
  __int64 v13; // r9
  int v14; // eax
  const char *v15; // rdx
  __int16 result; // ax

  v4 = -1;
  do
    ++v4;
  while ( Str[v4] );
  if ( v4 < 5 )
    goto LABEL_30;
  v5 = 47;
  if ( Str[2] != 47 )
  {
    if ( Str[4] == 45 )
    {
      v5 = 45;
      goto LABEL_7;
    }
LABEL_30:
    ErrSet(a2, (int)"Bad date format: %1", "%s", Str);
    return 0;
  }
LABEL_7:
  v6 = atoi(Str);
  v7 = strchr(Str, v5);
  if ( v7 && (v8 = v7 + 1, v9 = atoi(v7 + 1), (v10 = strchr(v8, v5)) != 0) )
  {
    v11 = atoi(v10 + 1);
    v12 = v11;
    if ( v5 == 45 )
    {
      v12 = v6;
      v13 = v11;
      v6 = v9;
    }
    else
    {
      v13 = v9;
    }
    if ( (unsigned int)(v13 - 1) > 0x1E || v6 == 2 && (int)v13 > 29 )
    {
      ErrSet(a2, (int)"Bad day (%1) in date: %2", "%d%s", v13, Str);
    }
    else if ( (unsigned int)(v6 - 1) > 0xB )
    {
      ErrSet(a2, (int)"Bad month (%1) in date: %2", "%d%s", v13, Str);
    }
    else
    {
      if ( v12 < 100 )
      {
        if ( v12 >= 80 )
          v12 += 1900;
        else
          v12 += 2000;
      }
      v14 = 1980;
      if ( v12 >= 1980 )
      {
        v14 = 2107;
        if ( v12 <= 2107 )
        {
          *(_DWORD *)(a2 + 512) = 0;
          *(_BYTE *)a2 = 0;
          result = v13 | (32 * (v6 | (16 * (v12 - 60))));
          *(_DWORD *)(a2 + 544) = 0;
          *(_QWORD *)(a2 + 552) = 0;
          return result;
        }
        v15 = "Year (%1) higher than maximum (%2) in date: %3";
      }
      else
      {
        v15 = "Year (%1) lower than minimum (%2) in date: %3";
      }
      ErrSet(a2, (int)v15, "%d%d%s", v12, v14, Str);
    }
  }
  else
  {
    ErrSet(a2, (int)"Missing separator (%1) in date: %2", "%c%s", v5, Str);
  }
  return 0;
}

```

## disassembly

```asm
0x14000a894  push    rbx
0x14000a896  push    rbp
0x14000a897  push    rsi
0x14000a898  push    rdi
0x14000a899  push    r12
0x14000a89b  push    r14
0x14000a89d  push    r15
0x14000a89f  sub     rsp, 30h
0x14000a8a3  mov     rsi, rdx
0x14000a8a6  mov     rdi, rcx
0x14000a8a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a8ad  inc     rax
0x14000a8b0  cmp     byte ptr [rcx+rax], 0
0x14000a8b4  jnz     short loc_14000A8AD
0x14000a8b6  cmp     rax, 5
0x14000a8ba  jb      loc_14000AA39
0x14000a8c0  mov     bpl, 2Fh ; '/'
0x14000a8c3  cmp     [rcx+2], bpl
0x14000a8c7  jz      short loc_14000A8D6
0x14000a8c9  cmp     byte ptr [rcx+4], 2Dh ; '-'
0x14000a8cd  jnz     loc_14000AA39
0x14000a8d3  mov     bpl, 2Dh ; '-'
0x14000a8d6  call    cs:__imp_atoi
0x14000a8dc  movzx   r15d, bpl
0x14000a8e0  mov     rcx, rdi; Str
0x14000a8e3  mov     edx, r15d; Val
0x14000a8e6  mov     r14d, eax
0x14000a8e9  call    cs:__imp_strchr
0x14000a8ef  test    rax, rax
0x14000a8f2  jnz     short loc_14000A917
0x14000a8f4  mov     r9d, r15d
0x14000a8f7  lea     r8, aCS; "%c%s"
0x14000a8fe  lea     rdx, aMissingSeparat; "Missing separator (%1) in date: %2"
0x14000a905  mov     rcx, rsi
0x14000a908  mov     [rsp+68h+var_48], rdi
0x14000a90d  call    ErrSet
0x14000a912  jmp     loc_14000AA52
0x14000a917  lea     rbx, [rax+1]
0x14000a91b  mov     rcx, rbx; String
0x14000a91e  call    cs:__imp_atoi
0x14000a924  mov     edx, r15d; Val
0x14000a927  mov     rcx, rbx; Str
0x14000a92a  mov     r12d, eax
0x14000a92d  call    cs:__imp_strchr
0x14000a933  test    rax, rax
0x14000a936  jz      short loc_14000A8F4
0x14000a938  lea     rcx, [rax+1]; String
0x14000a93c  call    cs:__imp_atoi
0x14000a942  mov     ecx, eax
0x14000a944  cmp     bpl, 2Dh ; '-'
0x14000a948  jnz     short loc_14000A955
0x14000a94a  mov     ecx, r14d
0x14000a94d  mov     r9d, eax
0x14000a950  mov     r14d, r12d
0x14000a953  jmp     short loc_14000A958
0x14000a955  mov     r9d, r12d
0x14000a958  lea     eax, [r9-1]
0x14000a95c  cmp     eax, 1Eh
0x14000a95f  ja      loc_14000AA26
0x14000a965  cmp     r14d, 2
0x14000a969  jnz     short loc_14000A975
0x14000a96b  cmp     r9d, 1Dh
0x14000a96f  jg      loc_14000AA26
0x14000a975  lea     eax, [r14-1]
0x14000a979  cmp     eax, 0Bh
0x14000a97c  ja      loc_14000AA13
0x14000a982  cmp     ecx, 64h ; 'd'
0x14000a985  jge     short loc_14000A99A
0x14000a987  cmp     ecx, 50h ; 'P'
0x14000a98a  jge     short loc_14000A994
0x14000a98c  add     ecx, 7D0h
0x14000a992  jmp     short loc_14000A99A
0x14000a994  add     ecx, 76Ch
0x14000a99a  mov     eax, 7BCh
0x14000a99f  cmp     ecx, eax
0x14000a9a1  jge     short loc_14000A9CA
0x14000a9a3  lea     rdx, aYear1LowerThan; "Year (%1) lower than minimum (%2) in da"...
0x14000a9aa  mov     r9d, ecx
0x14000a9ad  mov     [rsp+68h+var_40], rdi
0x14000a9b2  mov     rcx, rsi
0x14000a9b5  mov     dword ptr [rsp+68h+var_48], eax
0x14000a9b9  lea     r8, aDDS; "%d%d%s"
0x14000a9c0  call    ErrSet
0x14000a9c5  jmp     loc_14000AA52
0x14000a9ca  mov     eax, 83Bh
0x14000a9cf  cmp     ecx, eax
0x14000a9d1  jle     short loc_14000A9DC
0x14000a9d3  lea     rdx, aYear1HigherTha; "Year (%1) higher than maximum (%2) in d"...
0x14000a9da  jmp     short loc_14000A9AA
0x14000a9dc  lea     eax, [rcx-3Ch]
0x14000a9df  mov     dword ptr [rsi+200h], 0
0x14000a9e9  shl     ax, 4
0x14000a9ed  or      ax, r14w
0x14000a9f1  mov     byte ptr [rsi], 0
0x14000a9f4  shl     ax, 5
0x14000a9f8  or      ax, r9w
0x14000a9fc  mov     dword ptr [rsi+220h], 0
0x14000aa06  mov     qword ptr [rsi+228h], 0
0x14000aa11  jmp     short loc_14000AA54
0x14000aa13  lea     r8, aDS; "%d%s"
0x14000aa1a  lea     rdx, aBadMonth1InDat; "Bad month (%1) in date: %2"
0x14000aa21  jmp     loc_14000A905
0x14000aa26  lea     r8, aDS; "%d%s"
0x14000aa2d  lea     rdx, aBadDay1InDate2; "Bad day (%1) in date: %2"
0x14000aa34  jmp     loc_14000A905
0x14000aa39  mov     r9, rdi
0x14000aa3c  lea     r8, aS_4; "%s"
0x14000aa43  lea     rdx, aBadDateFormat1; "Bad date format: %1"
0x14000aa4a  mov     rcx, rsi
0x14000aa4d  call    ErrSet
0x14000aa52  xor     eax, eax
0x14000aa54  add     rsp, 30h
0x14000aa58  pop     r15
0x14000aa5a  pop     r14
0x14000aa5c  pop     r12
0x14000aa5e  pop     rdi
0x14000aa5f  pop     rsi
0x14000aa60  pop     rbp
0x14000aa61  pop     rbx
0x14000aa62  retn
```
