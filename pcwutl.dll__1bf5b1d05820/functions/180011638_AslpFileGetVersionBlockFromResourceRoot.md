# AslpFileGetVersionBlockFromResourceRoot

- ea: `0x180011638`
- end: `0x180011989`
- name: `AslpFileGetVersionBlockFromResourceRoot`
- size: `849`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180011990`

## callees

- `0x18000e240`
- `0x1800107f8`
- `0x180011638`
- `0x180013658`

## string_xrefs

- `0x180011936`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`
- `0x1800118d4`: `Found resource directory entry out of image bounds`
- `0x1800118fc`: `Found resource directory out of image bounds`
- `0x180011913`: `Found resource directory out of image bounds`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlockFromResourceRoot(unsigned __int16 **a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  __int64 v7; // r10
  unsigned __int64 v8; // r15
  unsigned __int64 v11; // r11
  unsigned __int64 v12; // r10
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  int v15; // eax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  int v19; // eax
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // r14
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rsi
  int ImageNtHeader; // ebx
  unsigned __int64 v26; // rax
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rcx
  __int64 v30; // r8
  const char *v31; // r9
  unsigned __int64 v32; // [rsp+90h] [rbp+18h] BYREF

  v5 = *(unsigned __int16 *)(a3 + 14);
  v6 = *(_QWORD *)(a4 + 32);
  v7 = *(unsigned __int16 *)(a3 + 12) + 2LL;
  v8 = *(_QWORD *)(a4 + 40);
  v32 = 0;
  v11 = 0;
  v12 = a3 + 8 * v7;
  if ( v5 )
  {
    while ( v12 >= v6 )
    {
      v13 = v12 + 8;
      if ( v12 >= v12 + 8 )
        break;
      v14 = v8 + v6;
      if ( v12 > v8 + v6 || v13 < v6 || v13 > v14 || v6 > v14 || v8 < 8 )
        break;
      if ( *(_WORD *)v12 != 16 )
      {
        ++v11;
        v12 += 8LL;
        if ( v11 < v5 )
          continue;
      }
      goto LABEL_11;
    }
    v30 = 2097;
    goto LABEL_57;
  }
LABEL_11:
  if ( v11 == v5 )
    return 3221225609LL;
  v15 = *(_DWORD *)(v12 + 4);
  if ( v15 < 0 )
  {
    v16 = a3 + (v15 & 0x7FFFFFFF);
    if ( v16 < v6
      || (v12 = v16 + 16, v16 >= v16 + 16)
      || (v17 = v8 + v6, v16 > v8 + v6)
      || v12 < v6
      || v12 > v17
      || v6 > v17
      || v8 < 0x10 )
    {
      v31 = "Found resource directory out of image bounds";
      v30 = 2124;
      goto LABEL_58;
    }
    if ( !*(_WORD *)(v16 + 14) && !*(_WORD *)(v16 + 12) )
      return 3221225609LL;
    v18 = v16 + 24;
    if ( v12 >= v12 + 8 || v18 < v6 || v18 > v17 )
    {
      v30 = 2134;
      goto LABEL_57;
    }
    v19 = *(_DWORD *)(v12 + 4);
    if ( v19 < 0 )
    {
      v20 = a3 + (v19 & 0x7FFFFFFF);
      if ( v20 < v6 || (v12 = v20 + 16, v20 >= v20 + 16) || v20 > v17 || v12 < v6 || v12 > v17 )
      {
        v31 = "Found resource directory out of image bounds";
        v30 = 2145;
        goto LABEL_58;
      }
      if ( *(_WORD *)(v20 + 14) || *(_WORD *)(v20 + 12) )
      {
        v21 = v20 + 24;
        if ( v12 < v12 + 8 && v21 >= v6 && v21 <= v17 )
          goto LABEL_36;
        v30 = 2155;
LABEL_57:
        v31 = "Found resource directory entry out of image bounds";
LABEL_58:
        AslLogCallPrintf(1, "AslpFileGetVersionBlockFromResourceRoot", v30, v31);
        return 3221226030LL;
      }
      return 3221225609LL;
    }
  }
LABEL_36:
  v22 = a3 + *(unsigned int *)(v12 + 4);
  if ( v22 < v6
    || (v23 = v22 + 16, v22 >= v22 + 16)
    || (v24 = v8 + v6, v22 > v8 + v6)
    || v23 < v6
    || v23 > v24
    || v6 > v24
    || v8 < 0x10 )
  {
    v31 = "Found resource data entry out of image bounds";
    v30 = 2169;
    goto LABEL_58;
  }
  ImageNtHeader = AslpFileGetImageNtHeader(&v32, a4);
  if ( ImageNtHeader >= 0 )
  {
    if ( v32 >= v6 )
    {
      v26 = v32 + 8;
      if ( v32 < v32 + 8 && v32 <= v24 && v26 >= v6 && v26 <= v24 )
      {
        v27 = (unsigned __int16 *)AslpImageRvaToVa(v32, a4);
        if ( (unsigned __int64)v27 >= v6 )
        {
          v28 = v27 + 19;
          if ( v27 < v27 + 19
            && (unsigned __int64)v27 <= v24
            && (unsigned __int64)v28 >= v6
            && (unsigned __int64)v28 <= v24
            && v8 >= 0x26 )
          {
            *a1 = v27;
            *a2 = *v27;
            return 0;
          }
        }
        v31 = "Found version block root but it was out of image bounds";
        v30 = 2185;
        goto LABEL_58;
      }
    }
    ImageNtHeader = -1073741266;
  }
  AslLogCallPrintf(
    1,
    "AslpFileGetVersionBlockFromResourceRoot",
    2179,
    "AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]",
    ImageNtHeader);
  return (unsigned int)ImageNtHeader;
}

```

## disassembly

```asm
0x180011638  mov     rax, rsp
0x18001163b  push    rbx
0x18001163c  push    rbp
0x18001163d  push    rsi
0x18001163e  push    rdi
0x18001163f  push    r12
0x180011641  push    r13
0x180011643  push    r14
0x180011645  push    r15
0x180011647  sub     rsp, 38h
0x18001164b  movzx   r10d, word ptr [r8+0Ch]
0x180011650  mov     r12, rdx
0x180011653  movzx   ebx, word ptr [r8+0Eh]
0x180011658  xor     edx, edx
0x18001165a  mov     rdi, [r9+20h]
0x18001165e  add     r10, 2
0x180011662  mov     r15, [r9+28h]
0x180011666  mov     rbp, r9
0x180011669  mov     [rax+18h], rdx
0x18001166d  mov     r13, rcx
0x180011670  lea     r9d, [rdx+10h]
0x180011674  mov     r11d, edx
0x180011677  lea     r10, [r8+r10*8]
0x18001167b  lea     r14d, [rdx+1]
0x18001167f  test    rbx, rbx
0x180011682  jz      short loc_1800116DD
0x180011684  cmp     r10, rdi
0x180011687  jb      loc_1800118CE
0x18001168d  lea     rax, [r10+8]
0x180011691  cmp     r10, rax
0x180011694  ja      loc_1800118CE
0x18001169a  lea     rcx, [r15+rdi]
0x18001169e  cmp     r10, rcx
0x1800116a1  ja      loc_1800118CE
0x1800116a7  cmp     rax, rdi
0x1800116aa  jb      loc_1800118CE
0x1800116b0  cmp     rax, rcx
0x1800116b3  ja      loc_1800118CE
0x1800116b9  cmp     rdi, rcx
0x1800116bc  ja      loc_1800118CE
0x1800116c2  cmp     r15, 8
0x1800116c6  jb      loc_1800118CE
0x1800116cc  cmp     [r10], r9w
0x1800116d0  jz      short loc_1800116DD
0x1800116d2  add     r11, r14
0x1800116d5  mov     r10, rax
0x1800116d8  cmp     r11, rbx
0x1800116db  jb      short loc_180011684
0x1800116dd  cmp     r11, rbx
0x1800116e0  jz      loc_180011973
0x1800116e6  mov     eax, [r10+4]
0x1800116ea  test    eax, eax
0x1800116ec  jns     loc_1800117E9
0x1800116f2  mov     r9d, 7FFFFFFFh
0x1800116f8  and     rax, r9
0x1800116fb  add     rax, r8
0x1800116fe  cmp     rax, rdi
0x180011701  jb      loc_180011913
0x180011707  lea     r10, [rax+10h]
0x18001170b  cmp     rax, r10
0x18001170e  ja      loc_180011913
0x180011714  lea     rcx, [r15+rdi]
0x180011718  cmp     rax, rcx
0x18001171b  ja      loc_180011913
0x180011721  cmp     r10, rdi
0x180011724  jb      loc_180011913
0x18001172a  cmp     r10, rcx
0x18001172d  ja      loc_180011913
0x180011733  cmp     rdi, rcx
0x180011736  ja      loc_180011913
0x18001173c  cmp     r15, 10h
0x180011740  jb      loc_180011913
0x180011746  cmp     [rax+0Eh], dx
0x18001174a  jnz     short loc_180011756
0x18001174c  cmp     [rax+0Ch], dx
0x180011750  jz      loc_180011973
0x180011756  lea     rax, [r10+8]
0x18001175a  cmp     r10, rax
0x18001175d  ja      loc_18001190B
0x180011763  cmp     rax, rdi
0x180011766  jb      loc_18001190B
0x18001176c  cmp     rax, rcx
0x18001176f  ja      loc_18001190B
0x180011775  mov     eax, [r10+4]
0x180011779  test    eax, eax
0x18001177b  jns     short loc_1800117E3
0x18001177d  and     rax, r9
0x180011780  add     rax, r8
0x180011783  cmp     rax, rdi
0x180011786  jb      loc_1800118FC
0x18001178c  lea     r10, [rax+10h]
0x180011790  cmp     rax, r10
0x180011793  ja      loc_1800118FC
0x180011799  cmp     rax, rcx
0x18001179c  ja      loc_1800118FC
0x1800117a2  cmp     r10, rdi
0x1800117a5  jb      loc_1800118FC
0x1800117ab  cmp     r10, rcx
0x1800117ae  ja      loc_1800118FC
0x1800117b4  cmp     [rax+0Eh], dx
0x1800117b8  jnz     short loc_1800117C4
0x1800117ba  cmp     [rax+0Ch], dx
0x1800117be  jz      loc_180011973
0x1800117c4  lea     rax, [r10+8]
0x1800117c8  cmp     r10, rax
0x1800117cb  ja      loc_1800118F4
0x1800117d1  cmp     rax, rdi
0x1800117d4  jb      loc_1800118F4
0x1800117da  cmp     rax, rcx
0x1800117dd  ja      loc_1800118F4
0x1800117e3  mov     r9d, 10h
0x1800117e9  mov     r14d, [r10+4]
0x1800117ed  add     r14, r8
0x1800117f0  cmp     r14, rdi
0x1800117f3  jb      loc_18001195C
0x1800117f9  lea     rax, [r14+10h]
0x1800117fd  cmp     r14, rax
0x180011800  ja      loc_18001195C
0x180011806  lea     rsi, [r15+rdi]
0x18001180a  cmp     r14, rsi
0x18001180d  ja      loc_18001195C
0x180011813  cmp     rax, rdi
0x180011816  jb      loc_18001195C
0x18001181c  cmp     rax, rsi
0x18001181f  ja      loc_18001195C
0x180011825  cmp     rdi, rsi
0x180011828  ja      loc_18001195C
0x18001182e  cmp     r15, r9
0x180011831  jb      loc_18001195C
0x180011837  mov     rdx, rbp
0x18001183a  lea     rcx, [rsp+78h+arg_10]
0x180011842  call    AslpFileGetImageNtHeader
0x180011847  mov     ebx, eax
0x180011849  test    eax, eax
0x18001184b  js      loc_180011936
0x180011851  mov     rcx, [rsp+78h+arg_10]
0x180011859  cmp     rcx, rdi
0x18001185c  jb      loc_180011931
0x180011862  lea     rax, [rcx+8]
0x180011866  cmp     rcx, rax
0x180011869  ja      loc_180011931
0x18001186f  cmp     rcx, rsi
0x180011872  ja      loc_180011931
0x180011878  cmp     rax, rdi
0x18001187b  jb      loc_180011931
0x180011881  cmp     rax, rsi
0x180011884  ja      loc_180011931
0x18001188a  mov     r8d, [r14]
0x18001188d  mov     rdx, rbp
0x180011890  call    AslpImageRvaToVa
0x180011895  cmp     rax, rdi
0x180011898  jb      loc_180011922
0x18001189e  lea     rcx, [rax+26h]
0x1800118a2  cmp     rax, rcx
0x1800118a5  ja      short loc_180011922
0x1800118a7  cmp     rax, rsi
0x1800118aa  ja      short loc_180011922
0x1800118ac  cmp     rcx, rdi
0x1800118af  jb      short loc_180011922
0x1800118b1  cmp     rcx, rsi
0x1800118b4  ja      short loc_180011922
0x1800118b6  cmp     r15, 26h ; '&'
0x1800118ba  jb      short loc_180011922
0x1800118bc  mov     [r13+0], rax
0x1800118c0  movzx   eax, word ptr [rax]
0x1800118c3  mov     [r12], rax
0x1800118c7  xor     eax, eax
0x1800118c9  jmp     loc_180011978
0x1800118ce  mov     r8d, 831h
0x1800118d4  lea     r9, aFoundResourceD; "Found resource directory entry out of i"...
0x1800118db  mov     ecx, r14d
0x1800118de  lea     rdx, aAslpfilegetver_7; "AslpFileGetVersionBlockFromResourceRoot"
0x1800118e5  call    AslLogCallPrintf
0x1800118ea  mov     eax, 0C000022Eh
0x1800118ef  jmp     loc_180011978
0x1800118f4  mov     r8d, 86Bh
0x1800118fa  jmp     short loc_1800118D4
0x1800118fc  lea     r9, aFoundResourceD_0; "Found resource directory out of image b"...
0x180011903  mov     r8d, 861h
0x180011909  jmp     short loc_1800118DB
0x18001190b  mov     r8d, 856h
0x180011911  jmp     short loc_1800118D4
0x180011913  lea     r9, aFoundResourceD_0; "Found resource directory out of image b"...
0x18001191a  mov     r8d, 84Ch
0x180011920  jmp     short loc_1800118DB
0x180011922  lea     r9, aFoundVersionBl; "Found version block root but it was out"...
0x180011929  mov     r8d, 889h
0x18001192f  jmp     short loc_180011969
0x180011931  mov     ebx, 0C000022Eh
0x180011936  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x18001193d  mov     [rsp+78h+var_58], ebx
0x180011941  mov     r8d, 883h
0x180011947  lea     rdx, aAslpfilegetver_7; "AslpFileGetVersionBlockFromResourceRoot"
0x18001194e  mov     ecx, 1
0x180011953  call    AslLogCallPrintf
0x180011958  mov     eax, ebx
0x18001195a  jmp     short loc_180011978
0x18001195c  lea     r9, aFoundResourceD_1; "Found resource data entry out of image "...
0x180011963  mov     r8d, 879h
0x180011969  mov     ecx, 1
0x18001196e  jmp     loc_1800118DE
0x180011973  mov     eax, 0C0000089h
0x180011978  add     rsp, 38h
0x18001197c  pop     r15
0x18001197e  pop     r14
0x180011980  pop     r13
0x180011982  pop     r12
0x180011984  pop     rdi
0x180011985  pop     rsi
0x180011986  pop     rbp
0x180011987  pop     rbx
0x180011988  retn
```
