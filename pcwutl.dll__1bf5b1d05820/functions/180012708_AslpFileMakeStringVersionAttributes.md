# AslpFileMakeStringVersionAttributes

- ea: `0x180012708`
- end: `0x180012910`
- name: `AslpFileMakeStringVersionAttributes`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180010d10`

## callees

- `0x18000e240`
- `0x18000f334`
- `0x180012708`
- `0x180012fa0`
- `0x1800132e0`
- `0x180013374`

## string_xrefs

- `0x1800128ba`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileMakeStringVersionAttributes(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // r14
  __int64 i; // rcx
  __int64 v6; // rax
  unsigned int v7; // edi
  int v8; // eax
  unsigned __int16 *v9; // rsi
  unsigned int v10; // r11d
  const char *v11; // r9
  __int64 v12; // r8
  __int64 v13; // rdi
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // r15
  __int64 v16; // r13
  __int64 v17; // r13
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v22; // [rsp+20h] [rbp-20h]
  unsigned __int16 *v23; // [rsp+28h] [rbp-18h]
  __int64 v24; // [rsp+30h] [rbp-10h] BYREF
  __int64 v25; // [rsp+38h] [rbp-8h] BYREF
  __int64 v26; // [rsp+88h] [rbp+48h] BYREF
  __int64 v27; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int64 v28; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  v28 = 0;
  if ( !a2 )
  {
    for ( i = 0; i != 8; ++i )
    {
      v6 = i;
      *(_DWORD *)(32 * v6 + a1 + 184) |= 2u;
    }
    *(_DWORD *)(a1 + 792) |= 2u;
    return 0;
  }
  v8 = AslpFileVerQueryBlock(a2, L"\\VarFileInfo\\Translation", &v27, &v26);
  v7 = v8;
  if ( v8 == -1073741275 )
  {
    v9 = 0;
    v10 = 0;
  }
  else
  {
    if ( v8 < 0 )
    {
      v11 = "AslpFileVerQueryBlock failed [%x]";
      v12 = 2561;
LABEL_28:
      LODWORD(v22) = v8;
      AslLogCallPrintf(1, "AslpFileMakeStringVersionAttributes", v12, v11, v22);
      return v7;
    }
    v13 = v27;
    v9 = 0;
    if ( (int)AslpFileVerBlockGetValueOffset(&v28, v27, v26) >= 0 && v28 < v14 )
    {
      v9 = (unsigned __int16 *)(v28 + v13);
      v10 = v14 - v28;
    }
  }
  v15 = (unsigned __int64)v10 >> 2;
  do
  {
    v16 = SLODWORD(qword_18001BB30[2 * v2]);
    v23 = (unsigned __int16 *)qword_18001BB30[2 * v2 + 1];
    LODWORD(v26) = qword_18001BB30[2 * v2];
    v8 = AslpFileQueryVersionString(&v24, &v25, a2, v9, v15, v23);
    v7 = v8;
    if ( v8 < 0 )
    {
      if ( v8 != -1073741275 )
      {
        v11 = "AslpFileQueryVersionString failed [%x]";
        v12 = 2616;
        goto LABEL_28;
      }
      *(_DWORD *)(32 * v16 + a1 + 24) |= 2u;
    }
    else
    {
      v17 = v24;
      v8 = AslStringXmlSanitize(v24);
      v7 = v8;
      if ( v8 < 0 )
      {
        v11 = "AslStringXmlSanitize failed [%x]";
        v12 = 2603;
        goto LABEL_28;
      }
      v18 = 32LL * (int)v26;
      v19 = -1;
      *(_DWORD *)(v18 + a1) = 4;
      do
        ++v19;
      while ( *(_WORD *)(v17 + 2 * v19) );
      *(_DWORD *)(v18 + a1 + 24) |= 1u;
      *(_QWORD *)(v18 + a1 + 8) = v19;
      *(_QWORD *)(v18 + a1 + 16) = v17;
    }
    ++v2;
  }
  while ( v2 < 8 );
  if ( v9 && v15 == 1 )
  {
    v20 = *v9;
    *(_DWORD *)(a1 + 792) |= 1u;
    *(_QWORD *)(a1 + 784) = v20;
    *(_DWORD *)(a1 + 768) = 2;
    *(_QWORD *)(a1 + 776) = 4;
  }
  else
  {
    *(_DWORD *)(a1 + 792) |= 2u;
  }
  return 0;
}

```

## disassembly

```asm
0x180012708  mov     [rsp-38h+arg_0], rbx
0x18001270d  push    rbp
0x18001270e  push    rsi
0x18001270f  push    rdi
0x180012710  push    r12
0x180012712  push    r13
0x180012714  push    r14
0x180012716  push    r15
0x180012718  mov     rbp, rsp
0x18001271b  sub     rsp, 40h
0x18001271f  xor     r14d, r14d
0x180012722  mov     r12, rdx
0x180012725  mov     [rbp+var_10], r14
0x180012729  mov     rbx, rcx
0x18001272c  mov     [rbp+var_8], r14
0x180012730  mov     [rbp+arg_10], r14
0x180012734  mov     [rbp+arg_8], r14
0x180012738  mov     [rbp+arg_18], r14
0x18001273c  test    rdx, rdx
0x18001273f  jnz     short loc_18001276B
0x180012741  mov     ecx, r14d
0x180012744  mov     rax, rcx
0x180012747  inc     rcx
0x18001274a  shl     rax, 5
0x18001274e  or      dword ptr [rax+rbx+0B8h], 2
0x180012756  cmp     rcx, 8
0x18001275a  jnz     short loc_180012744
0x18001275c  or      dword ptr [rbx+318h], 2
0x180012763  mov     edi, r14d
0x180012766  jmp     loc_1800128F6
0x18001276b  lea     r9, [rbp+arg_8]
0x18001276f  mov     rcx, r12
0x180012772  lea     r8, [rbp+arg_10]
0x180012776  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18001277d  call    AslpFileVerQueryBlock
0x180012782  mov     edi, eax
0x180012784  cmp     eax, 0C0000225h
0x180012789  jnz     short loc_180012793
0x18001278b  mov     rsi, r14
0x18001278e  mov     r11d, r14d
0x180012791  jmp     short loc_1800127DA
0x180012793  test    eax, eax
0x180012795  jns     short loc_1800127A9
0x180012797  lea     r9, aAslpfileverque_0; "AslpFileVerQueryBlock failed [%x]"
0x18001279e  mov     r8d, 0A01h
0x1800127a4  jmp     loc_1800128E1
0x1800127a9  mov     rdi, [rbp+arg_10]
0x1800127ad  lea     rcx, [rbp+arg_18]
0x1800127b1  mov     r8, [rbp+arg_8]
0x1800127b5  mov     rdx, rdi
0x1800127b8  mov     rsi, r14
0x1800127bb  mov     r11d, r14d
0x1800127be  call    AslpFileVerBlockGetValueOffset
0x1800127c3  test    eax, eax
0x1800127c5  js      short loc_1800127DA
0x1800127c7  mov     rax, [rbp+arg_18]
0x1800127cb  cmp     rax, r8
0x1800127ce  jnb     short loc_1800127DA
0x1800127d0  mov     r11d, r8d
0x1800127d3  lea     rsi, [rax+rdi]
0x1800127d7  sub     r11d, eax
0x1800127da  mov     r15d, r11d
0x1800127dd  shr     r15, 2
0x1800127e1  lea     rcx, qword_18001BB30
0x1800127e8  mov     rax, r14
0x1800127eb  add     rax, rax
0x1800127ee  lea     rdx, [rbp+var_8]
0x1800127f2  mov     r9, rsi
0x1800127f5  mov     r8, r12
0x1800127f8  movsxd  r13, dword ptr [rcx+rax*8]
0x1800127fc  mov     rax, [rcx+rax*8+8]
0x180012801  lea     rcx, [rbp+var_10]
0x180012805  mov     [rsp+40h+var_18], rax
0x18001280a  mov     [rsp+40h+var_20], r15
0x18001280f  mov     dword ptr [rbp+arg_8], r13d
0x180012813  call    AslpFileQueryVersionString
0x180012818  xor     edx, edx
0x18001281a  mov     edi, eax
0x18001281c  test    eax, eax
0x18001281e  js      short loc_180012867
0x180012820  mov     r13, [rbp+var_10]
0x180012824  mov     rcx, r13
0x180012827  call    AslStringXmlSanitize
0x18001282c  xor     edx, edx
0x18001282e  mov     edi, eax
0x180012830  test    eax, eax
0x180012832  js      loc_1800128BA
0x180012838  movsxd  rax, dword ptr [rbp+arg_8]
0x18001283c  shl     rax, 5
0x180012840  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180012844  mov     dword ptr [rax+rbx], 4
0x18001284b  inc     rcx
0x18001284e  cmp     [r13+rcx*2+0], dx
0x180012854  jnz     short loc_18001284B
0x180012856  or      dword ptr [rax+rbx+18h], 1
0x18001285b  mov     [rax+rbx+8], rcx
0x180012860  mov     [rax+rbx+10h], r13
0x180012865  jmp     short loc_18001287A
0x180012867  cmp     eax, 0C0000225h
0x18001286c  jnz     short loc_1800128D4
0x18001286e  mov     rax, r13
0x180012871  shl     rax, 5
0x180012875  or      dword ptr [rax+rbx+18h], 2
0x18001287a  inc     r14
0x18001287d  cmp     r14, 8
0x180012881  jb      loc_1800127E1
0x180012887  test    rsi, rsi
0x18001288a  jz      short loc_1800128C9
0x18001288c  cmp     r15, 1
0x180012890  jnz     short loc_1800128C9
0x180012892  movzx   eax, word ptr [rsi]
0x180012895  or      [rbx+318h], r15d
0x18001289c  mov     [rbx+310h], rax
0x1800128a3  mov     dword ptr [rbx+300h], 2
0x1800128ad  mov     qword ptr [rbx+308h], 4
0x1800128b8  jmp     short loc_1800128D0
0x1800128ba  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x1800128c1  mov     r8d, 0A2Bh
0x1800128c7  jmp     short loc_1800128E1
0x1800128c9  or      dword ptr [rbx+318h], 2
0x1800128d0  mov     edi, edx
0x1800128d2  jmp     short loc_1800128F6
0x1800128d4  lea     r9, aAslpfilequeryv_0; "AslpFileQueryVersionString failed [%x]"
0x1800128db  mov     r8d, 0A38h
0x1800128e1  lea     rdx, aAslpfilemakest; "AslpFileMakeStringVersionAttributes"
0x1800128e8  mov     dword ptr [rsp+40h+var_20], eax
0x1800128ec  mov     ecx, 1
0x1800128f1  call    AslLogCallPrintf
0x1800128f6  mov     rbx, [rsp+40h+arg_0]
0x1800128fe  mov     eax, edi
0x180012900  add     rsp, 40h
0x180012904  pop     r15
0x180012906  pop     r14
0x180012908  pop     r13
0x18001290a  pop     r12
0x18001290c  pop     rdi
0x18001290d  pop     rsi
0x18001290e  pop     rbp
0x18001290f  retn
```
