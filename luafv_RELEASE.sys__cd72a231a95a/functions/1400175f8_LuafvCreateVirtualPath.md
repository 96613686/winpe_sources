# LuafvCreateVirtualPath

- ea: `0x1400175f8`
- end: `0x1400177d7`
- name: `LuafvCreateVirtualPath`
- size: `479`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, struct _FLT_CALLBACK_DATA *, __m128i *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x140018f20`
- `0x140022d98`

## callees

- `0x140017278`
- `0x1400175f8`
- `0x1400177e0`
- `0x140017e10`
- `0x140018030`
- `0x14002194c`
- `0x140023058`
- `0x140023cc4`

## pseudocode

```c
__int64 __fastcall LuafvCreateVirtualPath(PFLT_INSTANCE Instance, struct _FLT_CALLBACK_DATA *a2, __m128i *a3)
{
  __int64 v3; // rax
  unsigned int v5; // r14d
  __int64 v8; // r9
  unsigned int v9; // esi
  int v10; // ebx
  char v11; // di
  unsigned __int16 v12; // dx
  char v13; // al
  int v14; // r14d
  int UserStorePath; // eax
  __m128i v17; // [rsp+30h] [rbp-48h] BYREF
  __m128i v18; // [rsp+40h] [rbp-38h] BYREF
  __int128 v19; // [rsp+50h] [rbp-28h] BYREF
  __int128 v20; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v21; // [rsp+D0h] [rbp+58h]

  v3 = a3[6].m128i_i64[1];
  v17 = 0;
  v18 = 0;
  v5 = *(unsigned __int16 *)(v3 + 40);
  v21 = v5;
  v8 = 2;
  v19 = 0;
  v20 = 0;
  if ( *(_BYTE *)(v3 + 80) )
    v9 = 0;
  else
    v9 = v5 - *(unsigned __int16 *)(*(_QWORD *)(v3 + 16) + 88LL) - 2;
  v10 = 0;
  v11 = 1;
  v17 = a3[3];
  v12 = _mm_cvtsi128_si32(*a3);
  v18 = *a3;
  if ( v12 >= 2u && *(_WORD *)(v18.m128i_i64[1] + 2 * ((unsigned __int64)v12 >> 1) - 2) == 92 )
  {
    v17.m128i_i16[0] -= 2;
    v18.m128i_i16[0] = v12 - 2;
  }
  while ( 1 )
  {
    v13 = v11 ? LuafvSplitRootPathLeft(&v17, &v19, 0, v8) : LuafvSplitPathRight(&v17, &v19, 0, v8);
    if ( !v13 || !v11 && !(_WORD)v19 )
      break;
    if ( v17.m128i_u16[0] <= v5 )
    {
      if ( v17.m128i_u16[0] > v9 )
      {
        if ( v11 )
          LuafvSplitRootPathLeft(&v18, &v20, 0, v8);
        UserStorePath = LuafvCreateUserStorePath(Instance);
        goto LABEL_28;
      }
      if ( v17.m128i_u16[0] == v9 )
      {
        UserStorePath = LuafvCreateStoreRootPath(Instance, 0);
LABEL_28:
        v10 = UserStorePath;
        goto LABEL_29;
      }
      v10 = 0;
LABEL_34:
      v11 = 0;
    }
    else
    {
      if ( v11 )
        LuafvSplitRootPathLeft(&v18, &v20, 0, v8);
      else
        LuafvSplitPathRight(&v18, &v20, 0, v8);
      v14 = LuafvCopyFile(Instance, a2, &v18, &v17, 0, 1);
      if ( v14 >= 0 )
        LuafvUpdateFileTableForFileChange(&v17, 0);
      v10 = 0;
      if ( v14 != -1073741771 )
        v10 = v14;
      v5 = v21;
LABEL_29:
      if ( v10 >= 0 )
        goto LABEL_34;
      if ( !v11 || v10 != -1073741766 )
        return (unsigned int)v10;
    }
  }
  if ( v10 >= 0 )
    LuafvLogUtcEvent(qword_14000E230, qword_14000E240, 0, a2, a3, 2);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400175f8  push    rbp
0x1400175fa  push    rbx
0x1400175fb  push    rsi
0x1400175fc  push    rdi
0x1400175fd  push    r12
0x1400175ff  push    r13
0x140017601  push    r14
0x140017603  push    r15
0x140017605  mov     rbp, rsp
0x140017608  sub     rsp, 78h
0x14001760c  mov     rax, [r8+68h]
0x140017610  xorps   xmm0, xmm0
0x140017613  movups  [rbp+var_48], xmm0
0x140017617  mov     r15, r8
0x14001761a  xor     r8d, r8d
0x14001761d  movups  [rbp+var_38], xmm0
0x140017621  movzx   r14d, word ptr [rax+28h]
0x140017626  mov     r13, rdx
0x140017629  xorps   xmm1, xmm1
0x14001762c  mov     [rbp+arg_10], r14d
0x140017630  mov     r12, rcx
0x140017633  mov     r9d, 2
0x140017639  movups  [rbp+var_28], xmm1
0x14001763d  movups  [rbp+var_18], xmm1
0x140017641  cmp     [rax+50h], r8b
0x140017645  jz      short loc_14001764C
0x140017647  mov     esi, r8d
0x14001764a  jmp     short loc_14001765C
0x14001764c  mov     rax, [rax+10h]
0x140017650  mov     esi, r14d
0x140017653  movzx   ecx, word ptr [rax+58h]
0x140017657  sub     esi, ecx
0x140017659  sub     esi, r9d
0x14001765c  movups  xmm0, xmmword ptr [r15+30h]
0x140017661  mov     ebx, r8d
0x140017664  mov     dil, 1
0x140017667  movdqu  [rbp+var_48], xmm0
0x14001766c  movups  xmm0, xmmword ptr [r15]
0x140017670  movd    edx, xmm0
0x140017674  movups  [rbp+var_38], xmm0
0x140017678  cmp     dx, r9w
0x14001767c  jb      short loc_1400176A0
0x14001767e  mov     rax, qword ptr [rbp+var_38+8]
0x140017682  movzx   ecx, dx
0x140017685  shr     rcx, 1
0x140017688  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14001768e  jnz     short loc_1400176A0
0x140017690  mov     eax, 0FFFEh
0x140017695  add     dx, ax
0x140017698  add     word ptr [rbp+var_48], ax
0x14001769c  mov     word ptr [rbp+var_38], dx
0x1400176a0  lea     rdx, [rbp+var_28]
0x1400176a4  lea     rcx, [rbp+var_48]
0x1400176a8  test    dil, dil
0x1400176ab  jz      short loc_1400176B4
0x1400176ad  call    LuafvSplitRootPathLeft
0x1400176b2  jmp     short loc_1400176B9
0x1400176b4  call    LuafvSplitPathRight
0x1400176b9  xor     r8d, r8d
0x1400176bc  test    al, al
0x1400176be  jz      loc_14001779C
0x1400176c4  test    dil, dil
0x1400176c7  jnz     short loc_1400176D4
0x1400176c9  cmp     word ptr [rbp+var_28], r8w
0x1400176ce  jz      loc_14001779C
0x1400176d4  movzx   eax, word ptr [rbp+var_48]
0x1400176d8  cmp     eax, r14d
0x1400176db  jbe     short loc_140017743
0x1400176dd  lea     rdx, [rbp+var_18]
0x1400176e1  lea     rcx, [rbp+var_38]
0x1400176e5  test    dil, dil
0x1400176e8  jz      short loc_1400176F1
0x1400176ea  call    LuafvSplitRootPathLeft
0x1400176ef  jmp     short loc_1400176F6
0x1400176f1  call    LuafvSplitPathRight
0x1400176f6  mov     [rsp+78h+var_50], 1; char
0x1400176fb  lea     r9, [rbp+var_48]
0x1400176ff  lea     r8, [rbp+var_38]
0x140017703  mov     [rsp+78h+var_58], 0; __int64
0x14001770c  mov     rdx, r13
0x14001770f  mov     rcx, r12; Instance
0x140017712  call    LuafvCopyFile
0x140017717  xor     r8d, r8d
0x14001771a  mov     r14d, eax
0x14001771d  test    eax, eax
0x14001771f  js      short loc_14001772F
0x140017721  xor     edx, edx
0x140017723  lea     rcx, [rbp+var_48]
0x140017727  call    LuafvUpdateFileTableForFileChange
0x14001772c  xor     r8d, r8d
0x14001772f  cmp     r14d, 0C0000035h
0x140017736  mov     ebx, r8d
0x140017739  cmovnz  ebx, r14d
0x14001773d  mov     r14d, [rbp+arg_10]
0x140017741  jmp     short loc_14001777A
0x140017743  cmp     eax, esi
0x140017745  jbe     short loc_140017769
0x140017747  test    dil, dil
0x14001774a  jz      short loc_140017759
0x14001774c  lea     rdx, [rbp+var_18]
0x140017750  lea     rcx, [rbp+var_38]
0x140017754  call    LuafvSplitRootPathLeft
0x140017759  mov     r8, [r15+68h]
0x14001775d  xor     edx, edx
0x14001775f  mov     rcx, r12; Instance
0x140017762  call    LuafvCreateUserStorePath
0x140017767  jmp     short loc_140017775
0x140017769  jnz     short loc_140017791
0x14001776b  xor     edx, edx
0x14001776d  mov     rcx, r12; FltObject
0x140017770  call    LuafvCreateStoreRootPath
0x140017775  xor     r8d, r8d
0x140017778  mov     ebx, eax
0x14001777a  test    ebx, ebx
0x14001777c  jns     short loc_140017794
0x14001777e  test    dil, dil
0x140017781  jz      short loc_1400177C3
0x140017783  cmp     ebx, 0C000003Ah
0x140017789  jz      loc_1400176A0
0x14001778f  jmp     short loc_1400177C3
0x140017791  mov     ebx, r8d
0x140017794  mov     dil, r8b
0x140017797  jmp     loc_1400176A0
0x14001779c  test    ebx, ebx
0x14001779e  js      short loc_1400177C3
0x1400177a0  mov     dword ptr [rsp+78h+var_50], 2
0x1400177a8  lea     rdx, qword_14000E240
0x1400177af  mov     r9, r13
0x1400177b2  mov     [rsp+78h+var_58], r15
0x1400177b7  lea     rcx, qword_14000E230
0x1400177be  call    LuafvLogUtcEvent
0x1400177c3  mov     eax, ebx
0x1400177c5  add     rsp, 78h
0x1400177c9  pop     r15
0x1400177cb  pop     r14
0x1400177cd  pop     r13
0x1400177cf  pop     r12
0x1400177d1  pop     rdi
0x1400177d2  pop     rsi
0x1400177d3  pop     rbx
0x1400177d4  pop     rbp
0x1400177d5  retn
```
