# QueryFileInfoFromDirectoryCache

- ea: `0x140004f20`
- end: `0x1400054b4`
- name: `QueryFileInfoFromDirectoryCache`
- size: `1428`
- prototype: `__int64 __fastcall(unsigned int *Context, PCUNICODE_STRING String1, char, unsigned int, __int64 *, _QWORD *, _DWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004640`
- `0x140004940`
- `0x140005820`
- `0x140014a00`
- `0x1400151a0`
- `0x140015780`

## callees

- `0x140004f20`
- `0x140035520`

## import_xrefs

- `ntoskrnl!bsearch_s` at `0x140004f91`
- `ntoskrnl!bsearch_s` at `0x140005262`
- `ntoskrnl!bsearch_s` at `0x140004f91`
- `ntoskrnl!bsearch_s` at `0x140005262`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140005038`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000529e`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140005038`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000529e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400050f2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005434`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400050f2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005434`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000510a`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000510a`

## pseudocode

```c
__int64 __fastcall QueryFileInfoFromDirectoryCache(
        unsigned int *Context,
        PCUNICODE_STRING String1,
        char a3,
        unsigned int a4,
        __int64 *a5,
        _QWORD *a6,
        _DWORD *a7)
{
  __int64 *v7; // r14
  const void *v9; // rdx
  rsize_t v11; // r8
  int v14; // r15d
  void *v15; // rax
  int v16; // r8d
  unsigned int v17; // ebx
  char v18; // si
  __int64 v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // ebx
  CCHAR v22; // al
  __int64 v23; // rdx
  unsigned int v24; // ecx
  __int64 v25; // rdx
  __int64 *v26; // rbx
  __int64 v27; // rcx
  __int16 v28; // si
  __int64 ConfigurationBlock; // rax
  _DWORD *v31; // r8
  int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  void *v36; // rax
  unsigned int v37; // ebx
  CCHAR MostSignificantBit; // al
  __int64 v39; // rdx
  __int64 v40; // rax
  _QWORD *v41; // rcx
  unsigned int v42; // ebp
  unsigned int v43; // ebp
  __int64 v44; // rcx
  __int64 v45; // rcx
  bool v46; // al
  __int64 v47; // rcx
  UNICODE_STRING String2; // [rsp+30h] [rbp-68h] BYREF
  UNICODE_STRING v49; // [rsp+40h] [rbp-58h] BYREF
  __int64 v50; // [rsp+A0h] [rbp+8h] BYREF

  v7 = &v50;
  v50 = 0;
  v9 = (const void *)*((_QWORD *)Context + 17);
  if ( a5 )
    v7 = a5;
  v11 = Context[31];
  v14 = 4;
  String2 = 0;
  v49 = 0;
  v15 = bsearch_s(String1, v9, v11, 4u, DirCacheLongNameKeyCompare, Context);
  if ( v15 )
  {
    v17 = ((unsigned int)v15 - Context[34]) >> 2;
    v18 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_ZqD(WPP_GLOBAL_Control->AttachedDevice, 12, v16, (_DWORD)String1, (char)Context, v17);
    }
  }
  else
  {
    v36 = bsearch_s(String1, *((const void **)Context + 18), Context[32], 4u, DirCacheShortNameKeyCompare, Context);
    if ( !v36 )
      return 3221226021LL;
    v18 = 1;
    v17 = ((unsigned int)v36 - Context[36]) >> 2;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_ZqD(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        ((unsigned int)v36 - Context[36]) >> 2,
        (_DWORD)String1,
        (char)Context,
        ((unsigned int)v36 - Context[36]) >> 2);
    }
  }
  HIDWORD(a5) = Context[10];
  LODWORD(a5) = v17 | ((*(_DWORD *)&v18 | 0xFFFFFFFE) << 30);
  *v7 = (__int64)a5;
  v19 = *v7;
  if ( HIDWORD(*v7) != Context[10] || (int)v19 >= 0 )
    __int2c();
  v20 = 4 * (*v7 & 0x3FFFFFFF);
  if ( (v19 & 0x40000000) != 0 )
  {
    v37 = *(_DWORD *)(v20 + *((_QWORD *)Context + 18));
    MostSignificantBit = RtlFindMostSignificantBit(v37);
    if ( MostSignificantBit <= 4 )
    {
      v39 = 0;
    }
    else
    {
      v39 = (unsigned int)(MostSignificantBit - 3) >> 1;
      if ( (unsigned int)v39 >= 8 )
        goto LABEL_59;
    }
    _mm_lfence();
    if ( (_DWORD)v39 )
      v24 = v37 - (32 << (2 * v39 - 2));
    else
      v24 = v37;
    v25 = *(_QWORD *)&Context[2 * v39 + 38];
    if ( v25 && v37 < Context[54] )
      goto LABEL_16;
LABEL_59:
    __int2c();
    v26 = 0;
    goto LABEL_17;
  }
  v21 = *(_DWORD *)(v20 + *((_QWORD *)Context + 17));
  v22 = RtlFindMostSignificantBit(v21);
  if ( v22 > 4 )
  {
    v23 = (unsigned int)(v22 - 3) >> 1;
    if ( (unsigned int)v23 < 8 )
      goto LABEL_12;
    goto LABEL_59;
  }
  v23 = 0;
LABEL_12:
  _mm_lfence();
  if ( (_DWORD)v23 )
    v24 = v21 - (32 << (2 * v23 - 2));
  else
    v24 = v21;
  v25 = *(_QWORD *)&Context[2 * v23 + 38];
  if ( !v25 || v21 >= Context[54] )
    goto LABEL_59;
LABEL_16:
  v26 = (__int64 *)(v25 + (v24 << 7));
LABEL_17:
  String2.MaximumLength = 2 * (*((_WORD *)v26 + 43) >> 4);
  String2.Length = String2.MaximumLength;
  String2.Buffer = (PWSTR)v26 + (*((_WORD *)v26 + 43) & 0xF) + 44;
  v49.MaximumLength = 2 * (*((_WORD *)v26 + 43) & 0xF);
  v49.Length = v49.MaximumLength;
  v49.Buffer = (PWSTR)(v26 + 11);
  if ( !RtlEqualUnicodeString(String1, &String2, 1u) && !RtlEqualUnicodeString(String1, &v49, 1u) )
    __int2c();
  v28 = *((_WORD *)v26 + 42);
  ConfigurationBlock = MRxSmbGetConfigurationBlock(v27);
  if ( (a4 != -262143 || *(_BYTE *)(ConfigurationBlock + 429) == 1) && (v28 & 4) != 0 )
    return 3221225494LL;
  if ( (v28 & 1) != 0 )
    return 3221225763LL;
  if ( (v26[9] & 0x400) != 0 && !a3 )
    return 3221225494LL;
  if ( a4 == 7 )
  {
    if ( Context[13] == 63 || (v26[9] & 0x400) == 0 )
      goto LABEL_80;
    return 3221225494LL;
  }
  if ( a4 == 4 )
  {
    if ( *a7 >= 0x28u )
    {
      v34 = *v26;
      v35 = (__int64)a6;
      *a7 -= 40;
      *(_QWORD *)v35 = v34;
      *(_QWORD *)(v35 + 8) = v26[1];
      *(_QWORD *)(v35 + 16) = v26[2];
      *(_QWORD *)(v35 + 24) = v26[3];
      *(_DWORD *)(v35 + 32) = *((_DWORD *)v26 + 18);
      return 0;
    }
    return 3221225507LL;
  }
  if ( a4 <= 0x22 )
  {
    if ( a4 == 34 )
    {
      v31 = a7;
      v32 = *a7;
      if ( *a7 >= 0x38u )
      {
        v14 = 56;
        v33 = (__int64)a6;
        a6[5] = v26[4];
        *(_QWORD *)(v33 + 32) = v26[5];
        *(_QWORD *)v33 = *v26;
        *(_QWORD *)(v33 + 8) = v26[1];
        *(_QWORD *)(v33 + 16) = v26[2];
        *(_QWORD *)(v33 + 24) = v26[3];
        *(_DWORD *)(v33 + 48) = *((_DWORD *)v26 + 18);
        goto LABEL_32;
      }
      goto LABEL_62;
    }
    v42 = a4 - 5;
    if ( v42 )
    {
      v43 = v42 - 1;
      if ( v43 )
      {
        if ( v43 != 1 )
          return 3221225475LL;
LABEL_80:
        v31 = a7;
        v32 = *a7;
        if ( *a7 >= 4u )
        {
          *(_DWORD *)a6 = *((_DWORD *)v26 + 19);
          goto LABEL_32;
        }
LABEL_62:
        v14 = 0;
        goto LABEL_32;
      }
      v44 = v26[6];
      if ( v44 != -1 )
      {
        v31 = a7;
        v32 = *a7;
        if ( *a7 < 8u )
          goto LABEL_62;
        v14 = 8;
        *a6 = v44;
LABEL_32:
        if ( v14 )
        {
          *v31 = v32 - v14;
          return 0;
        }
        return 3221225507LL;
      }
      return 3221225494LL;
    }
    v31 = a7;
    v32 = *a7;
    if ( *a7 < 0x18u )
      goto LABEL_62;
    v45 = (__int64)a6;
    a6[1] = v26[4];
    *(_QWORD *)v45 = v26[5];
    *(_BYTE *)(v45 + 20) = 0;
    v46 = (v26[9] & 0x10) != 0;
    *(_DWORD *)(v45 + 16) = 1;
    *(_BYTE *)(v45 + 21) = v46;
LABEL_91:
    v14 = 24;
    goto LABEL_32;
  }
  if ( a4 == -262143 )
  {
    v40 = v26[6];
    if ( v40 != -1 )
    {
      v31 = a7;
      v32 = *a7;
      if ( *a7 >= 0x20u )
      {
        v41 = a6;
        v14 = 32;
        *a6 = v40;
        v41[1] = *((_QWORD *)Context + 10);
        v41[2] = *((_QWORD *)Context + 11);
        v41[3] = *((_QWORD *)Context + 12);
        goto LABEL_32;
      }
      goto LABEL_62;
    }
    return 3221225494LL;
  }
  if ( a4 == 59 )
  {
    if ( v26[7] == -1 && v26[8] == -1 || !*((_BYTE *)Context + 232) )
      return 3221225494LL;
    v31 = a7;
    v32 = *a7;
    if ( *a7 < 0x18u )
      goto LABEL_62;
    v47 = (__int64)a6;
    *a6 = *((_QWORD *)Context + 28);
    *(_OWORD *)(v47 + 8) = *(_OWORD *)(v26 + 7);
    goto LABEL_91;
  }
  return 3221225475LL;
}

```

## disassembly

```asm
0x140004f20  mov     r11, rsp
0x140004f23  push    rbx
0x140004f24  push    rbp
0x140004f25  push    rsi
0x140004f26  push    rdi
0x140004f27  push    r12
0x140004f29  push    r13
0x140004f2b  push    r14
0x140004f2d  push    r15
0x140004f2f  sub     rsp, 58h
0x140004f33  mov     rax, [rsp+98h+arg_20]
0x140004f3b  lea     r14, [r11+8]
0x140004f3f  test    rax, rax
0x140004f42  mov     [r11-70h], rcx
0x140004f46  mov     r12, rdx
0x140004f49  mov     qword ptr [r11+8], 0
0x140004f51  mov     rdx, [rcx+88h]; Base
0x140004f58  cmovnz  r14, rax
0x140004f5c  movzx   r13d, r8b
0x140004f60  lea     rax, DirCacheLongNameKeyCompare
0x140004f67  mov     r8d, [rcx+7Ch]; NumOfElements
0x140004f6b  mov     ebp, r9d
0x140004f6e  mov     rdi, rcx
0x140004f71  mov     [r11-78h], rax
0x140004f75  xorps   xmm0, xmm0
0x140004f78  xorps   xmm1, xmm1
0x140004f7b  mov     r15d, 4
0x140004f81  mov     rcx, r12; Key
0x140004f84  mov     r9d, r15d; SizeOfElements
0x140004f87  movups  xmmword ptr [rsp+98h+String2.Length], xmm0
0x140004f8c  movups  xmmword ptr [rsp+98h+var_58.Length], xmm1
0x140004f91  call    cs:__imp_bsearch_s
0x140004f98  nop     dword ptr [rax+rax+00h]
0x140004f9d  mov     rbx, rax
0x140004fa0  test    rax, rax
0x140004fa3  jz      loc_14000523D
0x140004fa9  sub     ebx, [rdi+88h]
0x140004faf  shr     ebx, 2
0x140004fb2  xor     esi, esi
0x140004fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140004fbb  lea     rax, WPP_GLOBAL_Control
0x140004fc2  cmp     rcx, rax
0x140004fc5  jz      short loc_140004FD4
0x140004fc7  test    dword ptr [rcx+2Ch], 100h
0x140004fce  jnz     loc_1400053F8
0x140004fd4  mov     eax, [rdi+28h]
0x140004fd7  or      esi, 0FFFFFFFEh
0x140004fda  mov     dword ptr [rsp+98h+arg_20+4], eax
0x140004fe1  shl     esi, 1Eh
0x140004fe4  or      esi, ebx
0x140004fe6  mov     dword ptr [rsp+98h+arg_20], esi
0x140004fed  mov     rax, [rsp+98h+arg_20]
0x140004ff5  mov     [r14], rax
0x140004ff8  mov     rcx, [r14]
0x140004ffb  mov     rax, rcx
0x140004ffe  shr     rax, 20h
0x140005002  cmp     eax, [rdi+28h]
0x140005005  jnz     loc_14000535D
0x14000500b  test    ecx, ecx
0x14000500d  jns     loc_140005410
0x140005013  mov     eax, ecx
0x140005015  and     eax, 3FFFFFFFh
0x14000501a  lea     rdx, ds:0[rax*4]
0x140005022  bt      ecx, 1Eh
0x140005026  jb      loc_140005292
0x14000502c  mov     rax, [rdi+88h]
0x140005033  mov     ebx, [rdx+rax]
0x140005036  mov     ecx, ebx; Set
0x140005038  call    cs:__imp_RtlFindMostSignificantBit
0x14000503f  nop     dword ptr [rax+rax+00h]
0x140005044  cmp     al, r15b
0x140005047  jle     loc_140005284
0x14000504d  movsx   edx, al
0x140005050  sub     edx, 3
0x140005053  shr     edx, 1
0x140005055  cmp     edx, 8
0x140005058  jnb     loc_140005417
0x14000505e  lfence
0x140005061  test    edx, edx
0x140005063  jz      loc_14000528B
0x140005069  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x140005070  mov     eax, 20h ; ' '
0x140005075  shl     eax, cl
0x140005077  mov     ecx, ebx
0x140005079  sub     ecx, eax
0x14000507b  mov     rdx, [rdi+rdx*8+98h]
0x140005083  test    rdx, rdx
0x140005086  jz      loc_1400053DE
0x14000508c  cmp     ebx, [rdi+0D8h]
0x140005092  jnb     loc_1400053D5
0x140005098  shl     ecx, 7
0x14000509b  mov     ebx, ecx
0x14000509d  add     rbx, rdx
0x1400050a0  movzx   eax, word ptr [rbx+56h]
0x1400050a4  lea     rdx, [rsp+98h+String2]; String2
0x1400050a9  shr     ax, 4
0x1400050ad  mov     r8b, 1; CaseInSensitive
0x1400050b0  add     ax, ax
0x1400050b3  mov     rcx, r12; String1
0x1400050b6  mov     [rsp+98h+String2.MaximumLength], ax
0x1400050bb  mov     [rsp+98h+String2.Length], ax
0x1400050c0  movzx   eax, word ptr [rbx+56h]
0x1400050c4  and     eax, 0Fh
0x1400050c7  add     rax, 2Ch ; ','
0x1400050cb  lea     rax, [rbx+rax*2]
0x1400050cf  mov     [rsp+98h+String2.Buffer], rax
0x1400050d4  movzx   eax, word ptr [rbx+56h]
0x1400050d8  and     ax, 0Fh
0x1400050dc  add     ax, ax
0x1400050df  mov     [rsp+98h+var_58.MaximumLength], ax
0x1400050e4  mov     [rsp+98h+var_58.Length], ax
0x1400050e9  lea     rax, [rbx+58h]
0x1400050ed  mov     [rsp+98h+var_58.Buffer], rax
0x1400050f2  call    cs:__imp_RtlEqualUnicodeString
0x1400050f9  nop     dword ptr [rax+rax+00h]
0x1400050fe  test    al, al
0x140005100  jz      loc_140005429
0x140005106  movzx   esi, word ptr [rbx+54h]
0x14000510a  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140005111  nop     dword ptr [rax+rax+00h]
0x140005116  cmp     ebp, 0FFFC0001h
0x14000511c  jz      short loc_140005178
0x14000511e  test    r15b, sil
0x140005121  jnz     loc_14000537B
0x140005127  test    sil, 1
0x14000512b  jnz     loc_14000544F
0x140005131  mov     eax, [rbx+48h]
0x140005134  and     eax, 400h
0x140005139  jnz     loc_140005372
0x14000513f  cmp     ebp, 7
0x140005142  jz      loc_140005459
0x140005148  cmp     ebp, r15d
0x14000514b  jnz     short loc_140005183
0x14000514d  mov     r8, [rsp+98h+arg_30]
0x140005155  mov     edx, [r8]
0x140005158  cmp     edx, 28h ; '('
0x14000515b  jnb     loc_1400051FE
0x140005161  mov     eax, 0C0000023h
0x140005166  add     rsp, 58h
0x14000516a  pop     r15
0x14000516c  pop     r14
0x14000516e  pop     r13
0x140005170  pop     r12
0x140005172  pop     rdi
0x140005173  pop     rsi
0x140005174  pop     rbp
0x140005175  pop     rbx
0x140005176  retn
0x140005178  cmp     byte ptr [rax+1ADh], 1
0x14000517f  jz      short loc_14000511E
0x140005181  jmp     short loc_140005127
0x140005183  cmp     ebp, 22h ; '"'
0x140005186  ja      loc_140005305
0x14000518c  jnz     loc_140005470
0x140005192  mov     r8, [rsp+98h+arg_30]
0x14000519a  mov     edx, [r8]
0x14000519d  cmp     edx, 38h ; '8'
0x1400051a0  jb      loc_1400053F0
0x1400051a6  mov     rax, [rbx+20h]
0x1400051aa  mov     r15d, 38h ; '8'
0x1400051b0  mov     rcx, [rsp+98h+arg_28]
0x1400051b8  mov     [rcx+28h], rax
0x1400051bc  mov     rax, [rbx+28h]
0x1400051c0  mov     [rcx+20h], rax
0x1400051c4  mov     rax, [rbx]
0x1400051c7  mov     [rcx], rax
0x1400051ca  mov     rax, [rbx+8]
0x1400051ce  mov     [rcx+8], rax
0x1400051d2  mov     rax, [rbx+10h]
0x1400051d6  mov     [rcx+10h], rax
0x1400051da  mov     rax, [rbx+18h]
0x1400051de  mov     [rcx+18h], rax
0x1400051e2  mov     eax, [rbx+48h]
0x1400051e5  mov     [rcx+30h], eax
0x1400051e8  test    r15d, r15d
0x1400051eb  jz      loc_140005161
0x1400051f1  sub     edx, r15d
0x1400051f4  mov     [r8], edx
0x1400051f7  xor     eax, eax
0x1400051f9  jmp     loc_140005166
0x1400051fe  mov     rax, [rbx]
0x140005201  mov     r15d, 28h ; '('
0x140005207  mov     rcx, [rsp+98h+arg_28]
0x14000520f  sub     edx, r15d
0x140005212  mov     [r8], edx
0x140005215  mov     [rcx], rax
0x140005218  mov     rax, [rbx+8]
0x14000521c  mov     [rcx+8], rax
0x140005220  mov     rax, [rbx+10h]
0x140005224  mov     [rcx+10h], rax
0x140005228  mov     rax, [rbx+18h]
0x14000522c  mov     [rcx+18h], rax
0x140005230  mov     eax, [rbx+48h]
0x140005233  mov     [rcx+20h], eax
0x140005236  xor     eax, eax
0x140005238  jmp     loc_140005166
0x14000523d  mov     r8d, [rdi+80h]; NumOfElements
0x140005244  lea     rax, DirCacheShortNameKeyCompare
0x14000524b  mov     rdx, [rdi+90h]; Base
0x140005252  mov     r9, r15; SizeOfElements
0x140005255  mov     [rsp+98h+Context], rdi; Context
0x14000525a  mov     rcx, r12; Key
0x14000525d  mov     [rsp+98h+PtFuncCompare], rax; PtFuncCompare
0x140005262  call    cs:__imp_bsearch_s
0x140005269  nop     dword ptr [rax+rax+00h]
0x14000526e  mov     r8, rax
0x140005271  test    rax, rax
0x140005274  jnz     loc_140005385
0x14000527a  mov     eax, 0C0000225h
0x14000527f  jmp     loc_140005166
0x140005284  xor     edx, edx
0x140005286  jmp     loc_14000505E
0x14000528b  mov     ecx, ebx
0x14000528d  jmp     loc_14000507B
0x140005292  mov     rax, [rdi+90h]
0x140005299  mov     ebx, [rdx+rax]
0x14000529c  mov     ecx, ebx; Set
0x14000529e  call    cs:__imp_RtlFindMostSignificantBit
0x1400052a5  nop     dword ptr [rax+rax+00h]
0x1400052aa  cmp     al, r15b
0x1400052ad  jle     loc_140005364
0x1400052b3  movsx   edx, al
0x1400052b6  sub     edx, 3
0x1400052b9  shr     edx, 1
0x1400052bb  cmp     edx, 8
0x1400052be  jnb     loc_140005420
0x1400052c4  lfence
0x1400052c7  test    edx, edx
0x1400052c9  jz      loc_14000536B
0x1400052cf  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x1400052d6  mov     eax, 20h ; ' '
0x1400052db  shl     eax, cl
0x1400052dd  mov     ecx, ebx
0x1400052df  sub     ecx, eax
0x1400052e1  mov     rdx, [rdi+rdx*8+98h]
0x1400052e9  test    rdx, rdx
0x1400052ec  jz      loc_1400053E7
0x1400052f2  cmp     ebx, [rdi+0D8h]
0x1400052f8  jb      loc_140005098
0x1400052fe  int     2Ch; Windows NT - assertion failure
0x140005300  jmp     loc_1400053D7
0x140005305  cmp     ebp, 0FFFC0001h
0x14000530b  jnz     loc_140005490
0x140005311  mov     rax, [rbx+30h]
0x140005315  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140005319  jz      short loc_14000537B
0x14000531b  mov     r8, [rsp+98h+arg_30]
0x140005323  mov     edx, [r8]
0x140005326  cmp     edx, 20h ; ' '
0x140005329  jb      loc_1400053F0
0x14000532f  mov     rcx, [rsp+98h+arg_28]
0x140005337  mov     r15d, 20h ; ' '
0x14000533d  mov     [rcx], rax
0x140005340  mov     rax, [rdi+50h]
0x140005344  mov     [rcx+8], rax
0x140005348  mov     rax, [rdi+58h]
0x14000534c  mov     [rcx+10h], rax
0x140005350  mov     rax, [rdi+60h]
0x140005354  mov     [rcx+18h], rax
0x140005358  jmp     loc_1400051E8
0x14000535d  int     2Ch; Windows NT - assertion failure
0x14000535f  jmp     loc_140005013
0x140005364  xor     edx, edx
0x140005366  jmp     loc_1400052C4
0x14000536b  mov     ecx, ebx
0x14000536d  jmp     loc_1400052E1
0x140005372  test    r13b, r13b
0x140005375  jnz     loc_14000513F
0x14000537b  mov     eax, 0C0000016h
0x140005380  jmp     loc_140005166
0x140005385  sub     r8d, [rdi+90h]
0x14000538c  mov     esi, 1
0x140005391  shr     r8d, 2
0x140005395  mov     ebx, r8d
0x140005398  mov     rcx, cs:WPP_GLOBAL_Control
0x14000539f  lea     rax, WPP_GLOBAL_Control
0x1400053a6  cmp     rcx, rax
0x1400053a9  jz      loc_140004FD4
0x1400053af  test    dword ptr [rcx+2Ch], 100h
0x1400053b6  jz      loc_140004FD4
0x1400053bc  cmp     [rcx+29h], r15b
0x1400053c0  jb      loc_140004FD4
0x1400053c6  mov     edx, 0Dh
0x1400053cb  mov     dword ptr [rsp+98h+Context], r8d
0x1400053d0  jmp     loc_1400384EA
0x1400053d5  int     2Ch; Windows NT - assertion failure
0x1400053d7  xor     ebx, ebx
0x1400053d9  jmp     loc_1400050A0
0x1400053de  int     2Ch; Windows NT - assertion failure
0x1400053e0  xor     ebx, ebx
0x1400053e2  jmp     loc_1400050A0
0x1400053e7  int     2Ch; Windows NT - assertion failure
0x1400053e9  xor     ebx, ebx
0x1400053eb  jmp     loc_1400050A0
0x1400053f0  xor     r15d, r15d
0x1400053f3  jmp     loc_1400051E8
0x1400053f8  cmp     [rcx+29h], r15b
0x1400053fc  jb      loc_140004FD4
0x140005402  mov     edx, 0Ch
0x140005407  mov     dword ptr [rsp+98h+Context], ebx
  ... truncated ...
```
