# CreateOneXResultCopy

- ea: `0x18000f290`
- end: `0x18000f7dc`
- name: `CreateOneXResultCopy`
- size: `1356`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000dd40`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000f290`
- `0x18000f7e4`
- `0x18000ffa0`
- `0x1800106c8`
- `0x18001c474`
- `0x1800214f0`
- `0x18002f705`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18000f4db`
- `MobileNetworking!AllocateMemory` at `0x18000f4db`
- `MobileNetworking!FreeMemory` at `0x18000f3d2`
- `MobileNetworking!FreeMemory` at `0x18000f3e9`
- `MobileNetworking!FreeMemory` at `0x18000f6ff`
- `MobileNetworking!FreeMemory` at `0x18000f716`
- `MobileNetworking!FreeMemory` at `0x18000f752`
- `MobileNetworking!FreeMemory` at `0x18000f769`
- `MobileNetworking!FreeMemory` at `0x18000f3d2`
- `MobileNetworking!FreeMemory` at `0x18000f3e9`
- `MobileNetworking!FreeMemory` at `0x18000f6ff`
- `MobileNetworking!FreeMemory` at `0x18000f716`
- `MobileNetworking!FreeMemory` at `0x18000f752`
- `MobileNetworking!FreeMemory` at `0x18000f769`

## string_xrefs

- `0x18000f3c7`: `CreateOneXResultCopy`
- `0x18000f3de`: `CreateOneXResultCopy`
- `0x18000f4cd`: `CreateOneXResultCopy`
- `0x18000f6f4`: `CreateOneXResultCopy`
- `0x18000f70b`: `CreateOneXResultCopy`
- `0x18000f747`: `CreateOneXResultCopy`
- `0x18000f75e`: `CreateOneXResultCopy`

## pseudocode

```c
__int64 __fastcall CreateOneXResultCopy(__int64 a1, unsigned __int64 *a2, unsigned int *a3)
{
  unsigned int v4; // r12d
  int v6; // eax
  int v7; // r13d
  int v8; // edi
  unsigned int v9; // r14d
  unsigned int OneXAuthParams; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // ecx
  unsigned int v17; // edx
  unsigned int v18; // eax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  __int64 v21; // r12
  int v22; // edx
  unsigned int v23; // edi
  unsigned int v24; // eax
  unsigned int v25; // r12d
  unsigned int v26; // eax
  unsigned int v27; // r13d
  unsigned int v28; // eax
  unsigned int v29; // esi
  void *v30; // rcx
  size_t v31; // r8
  void *v33; // [rsp+38h] [rbp-9h] BYREF
  void *Src; // [rsp+40h] [rbp-1h] BYREF
  unsigned __int64 v35; // [rsp+48h] [rbp+7h] BYREF
  __int64 v36; // [rsp+50h] [rbp+Fh]
  void *v37; // [rsp+A8h] [rbp+67h] BYREF
  size_t Size; // [rsp+B0h] [rbp+6Fh] BYREF
  unsigned int *v39; // [rsp+B8h] [rbp+77h]
  size_t v40; // [rsp+C0h] [rbp+7Fh] BYREF

  v39 = a3;
  v4 = 0;
  LODWORD(v37) = *(_DWORD *)(a1 + 20);
  v36 = *(_QWORD *)(a1 + 104);
  v35 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  LODWORD(v40) = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids);
  *a2 = 0;
  v6 = *(_DWORD *)(a1 + 2400);
  if ( v6 == 8 && *(_DWORD *)(a1 + 2464) == 10 )
  {
    v7 = 1;
  }
  else
  {
    v7 = 0;
    if ( ((v6 - 9) & 0xFFFFFFFD) == 0 && *(_DWORD *)(a1 + 2464) == 12 || *(_DWORD *)(a1 + 2464) == 6 )
    {
      v8 = 1;
      v9 = 56;
LABEL_13:
      OneXAuthParams = GetOneXAuthParams(a1, &Src, &Size);
      v11 = OneXAuthParams;
      if ( OneXAuthParams )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_67;
        v13 = 23;
        goto LABEL_17;
      }
      if ( (int)Size + 7 >= (unsigned int)Size )
      {
        v14 = (Size + 7) & 0xFFFFFFF8;
        v9 = v14 + 56;
        if ( v14 >= 0xFFFFFFC8 )
          goto LABEL_65;
        if ( v7 )
        {
          v15 = *(_DWORD *)(a1 + 64);
          if ( v15 + 7 < v15 )
            goto LABEL_66;
          v16 = v15 + 7;
          v17 = ((v15 + 7) & 0xFFFFFFF8) + v9;
          if ( v17 < v9 )
            goto LABEL_65;
          v18 = *(_DWORD *)(a1 + 48);
          if ( v18 + 7 < v18 )
          {
            v9 += v16 & 0xFFFFFFF8;
            goto LABEL_66;
          }
          v9 = ((v18 + 7) & 0xFFFFFFF8) + v17;
          if ( v9 < v17 )
          {
LABEL_65:
            v9 = -1;
            goto LABEL_66;
          }
        }
        if ( v36 )
        {
          OneXAuthParams = MarshallEapError(v36, &v40, &v33);
          v11 = OneXAuthParams;
          if ( OneXAuthParams )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              goto LABEL_67;
            v13 = 24;
LABEL_17:
            WPP_SF_dd(v12[7], v13, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, (unsigned int)v37, OneXAuthParams);
            goto LABEL_67;
          }
          v4 = v40;
        }
        if ( v4 + 7 >= v4 )
        {
          if ( ((v4 + 7) & 0xFFFFFFF8) + v9 >= v9 )
          {
            v9 += (v4 + 7) & 0xFFFFFFF8;
            goto LABEL_36;
          }
          goto LABEL_65;
        }
      }
LABEL_66:
      v11 = 534;
      goto LABEL_67;
    }
  }
  v8 = 0;
  v9 = 56;
  if ( v7 )
    goto LABEL_13;
LABEL_36:
  OneXAuthParams = AllocateMemory(v9, &v35, "CreateOneXResultCopy", 384);
  v11 = OneXAuthParams;
  if ( OneXAuthParams )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_67;
    v13 = 25;
    goto LABEL_17;
  }
  v19 = v35;
  *(_QWORD *)v35 = *(_QWORD *)(a1 + 28);
  *(_DWORD *)(v19 + 8) = *(_DWORD *)(a1 + 36);
  *(_DWORD *)(v35 + 12) = *(_DWORD *)(a1 + 40);
  *(_DWORD *)(v35 + 16) = *(_DWORD *)(a1 + 44);
  v20 = v35;
  if ( !v35 )
  {
    v22 = 87;
LABEL_64:
    v11 = v22;
    goto LABEL_67;
  }
  v21 = -1;
  v11 = 534;
  if ( v35 + 56 >= v35 )
    v21 = v35 + 56;
  v22 = v35 + 56 < v35 ? 0x216 : 0;
  v37 = (void *)v21;
  if ( v35 + 56 < v35 )
    goto LABEL_64;
  if ( !v7 && !v8 )
    goto LABEL_61;
  v23 = Size;
  *(_DWORD *)(v35 + 24) = 56;
  *(_DWORD *)(v35 + 20) = v23;
  memcpy_0((void *)v21, Src, v23);
  v24 = AddAlignedSizeToPointer(v23, v21, &v37);
  if ( v24 )
    goto LABEL_62;
  if ( v23 + 7 < v23 )
    goto LABEL_67;
  v25 = ((v23 + 7) & 0xFFFFFFF8) + 56;
  if ( v25 < 0x38 )
    goto LABEL_67;
  if ( !v7 )
    goto LABEL_56;
  *(_DWORD *)(v35 + 48) = v25;
  *(_DWORD *)(v35 + 44) = *(_DWORD *)(a1 + 64);
  memcpy_0(v37, *(const void **)(a1 + 72), *(unsigned int *)(a1 + 64));
  v24 = AddAlignedSizeToPointer(*(unsigned int *)(a1 + 64), v37, &v37);
  if ( v24 )
    goto LABEL_62;
  v26 = *(_DWORD *)(a1 + 64);
  if ( v26 + 7 < v26 )
    goto LABEL_67;
  v27 = ((v26 + 7) & 0xFFFFFFF8) + v25;
  if ( v27 < v25 )
    goto LABEL_67;
  *(_DWORD *)(v35 + 40) = v27;
  *(_DWORD *)(v35 + 36) = *(_DWORD *)(a1 + 48);
  memcpy_0(v37, *(const void **)(a1 + 56), *(unsigned int *)(a1 + 48));
  v24 = AddAlignedSizeToPointer(*(unsigned int *)(a1 + 48), v37, &v37);
  if ( v24 )
  {
LABEL_62:
    v11 = v24;
LABEL_67:
    FreeMemory(&v33, "CreateOneXResultCopy", 455);
    FreeMemory(&Src, "CreateOneXResultCopy", 456);
    FreeOneXResult(&v35, v9);
    goto LABEL_68;
  }
  v28 = *(_DWORD *)(a1 + 48);
  if ( v28 + 7 < v28 )
    goto LABEL_67;
  v25 = ((v28 + 7) & 0xFFFFFFF8) + v27;
  if ( v25 < v27 )
    goto LABEL_67;
LABEL_56:
  if ( v36 )
  {
    v29 = v40;
    v30 = v37;
    v31 = (unsigned int)v40;
    *(_DWORD *)(v35 + 28) = v40;
    *(_DWORD *)(v35 + 32) = v25;
    memcpy_0(v30, v33, v31);
    v24 = AddAlignedSizeToPointer(v29, v37, &v37);
    if ( !v24 )
    {
      if ( v29 + 7 < v29 || v25 + ((v29 + 7) & 0xFFFFFFF8) < v25 )
        goto LABEL_67;
      goto LABEL_60;
    }
    goto LABEL_62;
  }
LABEL_60:
  v20 = v35;
LABEL_61:
  v11 = 0;
  *a2 = v20;
  *v39 = v9;
  FreeMemory(&v33, "CreateOneXResultCopy", 455);
  FreeMemory(&Src, "CreateOneXResultCopy", 456);
LABEL_68:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18000f290  mov     rax, rsp
0x18000f293  mov     [rax+18h], r8
0x18000f297  push    rbp
0x18000f298  push    rbx
0x18000f299  lea     rbp, [rax-5Fh]
0x18000f29d  sub     rsp, 88h
0x18000f2a4  mov     [rax-18h], rsi
0x18000f2a8  xor     ebx, ebx
0x18000f2aa  mov     [rax-20h], rdi
0x18000f2ae  mov     rsi, rcx
0x18000f2b1  mov     [rax-28h], r12
0x18000f2b5  mov     r12d, ebx
0x18000f2b8  mov     [rax-40h], r15
0x18000f2bc  mov     r15, rdx
0x18000f2bf  mov     eax, [rcx+14h]
0x18000f2c2  mov     dword ptr [rbp+57h+arg_0], eax
0x18000f2c5  mov     rax, [rcx+68h]
0x18000f2c9  mov     [rbp+57h+var_48], rax
0x18000f2cd  mov     [rbp+57h+var_50], rbx
0x18000f2d1  mov     [rbp+57h+Src], rbx
0x18000f2d5  mov     dword ptr [rbp+57h+Size], ebx
0x18000f2d8  mov     dword ptr [rbp+57h+arg_18], ebx
0x18000f2db  mov     [rbp+57h+var_60], rbx
0x18000f2df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2e6  lea     rax, WPP_GLOBAL_Control
0x18000f2ed  cmp     rcx, rax
0x18000f2f0  jz      short loc_18000F310
0x18000f2f2  test    dword ptr [rcx+44h], 800h
0x18000f2f9  jz      short loc_18000F310
0x18000f2fb  mov     rcx, [rcx+38h]
0x18000f2ff  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x18000f306  mov     edx, 16h
0x18000f30b  call    WPP_SF_
0x18000f310  mov     [r15], rbx
0x18000f313  mov     eax, [rsi+960h]
0x18000f319  mov     [rsp+90h+var_28], r13
0x18000f31e  mov     [rsp+90h+var_30], r14
0x18000f323  cmp     eax, 8
0x18000f326  jnz     short loc_18000F339
0x18000f328  cmp     dword ptr [rsi+9A0h], 0Ah
0x18000f32f  jnz     short loc_18000F339
0x18000f331  mov     r13d, 1
0x18000f337  jmp     short loc_18000F358
0x18000f339  add     eax, 0FFFFFFF7h
0x18000f33c  mov     r13d, ebx
0x18000f33f  test    eax, 0FFFFFFFDh
0x18000f344  jnz     short loc_18000F34F
0x18000f346  cmp     dword ptr [rsi+9A0h], 0Ch
0x18000f34d  jz      short loc_18000F36A
0x18000f34f  cmp     dword ptr [rsi+9A0h], 6
0x18000f356  jz      short loc_18000F36A
0x18000f358  mov     edi, ebx
0x18000f35a  mov     r14d, 38h ; '8'
0x18000f360  test    r13d, r13d
0x18000f363  jnz     short loc_18000F375
0x18000f365  jmp     loc_18000F4C7
0x18000f36a  mov     edi, 1
0x18000f36f  mov     r14d, 38h ; '8'
0x18000f375  lea     r8, [rbp+57h+Size]
0x18000f379  mov     rcx, rsi
0x18000f37c  lea     rdx, [rbp+57h+Src]
0x18000f380  call    GetOneXAuthParams
0x18000f385  mov     ebx, eax
0x18000f387  test    eax, eax
0x18000f389  jz      short loc_18000F3F4
0x18000f38b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f392  lea     rdi, WPP_GLOBAL_Control
0x18000f399  cmp     rcx, rdi
0x18000f39c  jz      short loc_18000F3C1
0x18000f39e  test    byte ptr [rcx+44h], 1
0x18000f3a2  jz      short loc_18000F3C1
0x18000f3a4  mov     edx, 17h
0x18000f3a9  mov     r9d, dword ptr [rbp+57h+arg_0]
0x18000f3ad  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x18000f3b4  mov     rcx, [rcx+38h]
0x18000f3b8  mov     [rsp+20h], eax
0x18000f3bc  call    WPP_SF_dd
0x18000f3c1  mov     r8d, 1C7h
0x18000f3c7  lea     rdx, aCreateonexresu; "CreateOneXResultCopy"
0x18000f3ce  lea     rcx, [rbp+57h+var_60]
0x18000f3d2  call    cs:__imp_FreeMemory
0x18000f3d8  mov     r8d, 1C8h
0x18000f3de  lea     rdx, aCreateonexresu; "CreateOneXResultCopy"
0x18000f3e5  lea     rcx, [rbp+57h+Src]
0x18000f3e9  call    cs:__imp_FreeMemory
0x18000f3ef  jmp     loc_18000F776
0x18000f3f4  mov     eax, dword ptr [rbp+57h+Size]
0x18000f3f7  lea     ecx, [rax+7]
0x18000f3fa  cmp     ecx, eax
0x18000f3fc  jb      loc_18000F73C
0x18000f402  and     ecx, 0FFFFFFF8h
0x18000f405  lea     r14d, [rcx+38h]
0x18000f409  cmp     r14d, 38h ; '8'
0x18000f40d  jb      loc_18000F736
0x18000f413  test    r13d, r13d
0x18000f416  jz      short loc_18000F458
0x18000f418  mov     eax, [rsi+40h]
0x18000f41b  lea     ecx, [rax+7]
0x18000f41e  cmp     ecx, eax
0x18000f420  jb      loc_18000F73C
0x18000f426  and     ecx, 0FFFFFFF8h
0x18000f429  lea     edx, [rcx+r14]
0x18000f42d  cmp     edx, r14d
0x18000f430  jb      loc_18000F736
0x18000f436  mov     eax, [rsi+30h]
0x18000f439  lea     ecx, [rax+7]
0x18000f43c  cmp     ecx, eax
0x18000f43e  jnb     short loc_18000F448
0x18000f440  mov     r14d, edx
0x18000f443  jmp     loc_18000F73C
0x18000f448  and     ecx, 0FFFFFFF8h
0x18000f44b  lea     r14d, [rcx+rdx]
0x18000f44f  cmp     r14d, edx
0x18000f452  jb      loc_18000F736
0x18000f458  mov     rax, [rbp+57h+var_48]
0x18000f45c  test    rax, rax
0x18000f45f  jz      short loc_18000F4A6
0x18000f461  lea     r8, [rbp+57h+var_60]
0x18000f465  mov     rcx, rax
0x18000f468  lea     rdx, [rbp+57h+arg_18]
0x18000f46c  call    MarshallEapError
0x18000f471  mov     ebx, eax
0x18000f473  test    eax, eax
0x18000f475  jz      short loc_18000F4A2
0x18000f477  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f47e  lea     rdi, WPP_GLOBAL_Control
0x18000f485  cmp     rcx, rdi
0x18000f488  jz      loc_18000F3C1
0x18000f48e  test    byte ptr [rcx+44h], 1
0x18000f492  jz      loc_18000F3C1
0x18000f498  mov     edx, 18h
0x18000f49d  jmp     loc_18000F3A9
0x18000f4a2  mov     r12d, dword ptr [rbp+57h+arg_18]
0x18000f4a6  lea     eax, [r12+7]
0x18000f4ab  cmp     eax, r12d
0x18000f4ae  jb      loc_18000F73C
0x18000f4b4  and     eax, 0FFFFFFF8h
0x18000f4b7  lea     ecx, [rax+r14]
0x18000f4bb  cmp     ecx, r14d
0x18000f4be  jb      loc_18000F736
0x18000f4c4  mov     r14d, ecx
0x18000f4c7  mov     r9d, 180h
0x18000f4cd  lea     r8, aCreateonexresu; "CreateOneXResultCopy"
0x18000f4d4  lea     rdx, [rbp+57h+var_50]
0x18000f4d8  mov     ecx, r14d
0x18000f4db  call    cs:__imp_AllocateMemory
0x18000f4e1  mov     ebx, eax
0x18000f4e3  test    eax, eax
0x18000f4e5  jz      short loc_18000F512
0x18000f4e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4ee  lea     rdi, WPP_GLOBAL_Control
0x18000f4f5  cmp     rcx, rdi
0x18000f4f8  jz      loc_18000F3C1
0x18000f4fe  test    byte ptr [rcx+44h], 1
0x18000f502  jz      loc_18000F3C1
0x18000f508  mov     edx, 19h
0x18000f50d  jmp     loc_18000F3A9
0x18000f512  mov     rcx, [rbp+57h+var_50]
0x18000f516  movsd   xmm0, qword ptr [rsi+1Ch]
0x18000f51b  movsd   qword ptr [rcx], xmm0
0x18000f51f  mov     eax, [rsi+24h]
0x18000f522  mov     [rcx+8], eax
0x18000f525  mov     ecx, [rsi+28h]
0x18000f528  mov     rax, [rbp+57h+var_50]
0x18000f52c  mov     [rax+0Ch], ecx
0x18000f52f  mov     ecx, [rsi+2Ch]
0x18000f532  mov     rax, [rbp+57h+var_50]
0x18000f536  mov     [rax+10h], ecx
0x18000f539  mov     rcx, [rbp+57h+var_50]
0x18000f53d  test    rcx, rcx
0x18000f540  jz      loc_18000F72D
0x18000f546  lea     rax, [rcx+38h]
0x18000f54a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000f551  cmp     rax, rcx
0x18000f554  mov     ebx, 216h
0x18000f559  cmovnb  r12, rax
0x18000f55d  sbb     edx, edx
0x18000f55f  and     edx, ebx
0x18000f561  mov     [rbp+57h+arg_0], r12
0x18000f565  cmp     rax, rcx
0x18000f568  jb      loc_18000F732
0x18000f56e  test    r13d, r13d
0x18000f571  jnz     short loc_18000F57D
0x18000f573  xor     eax, eax
0x18000f575  test    edi, edi
0x18000f577  jz      loc_18000F6E2
0x18000f57d  mov     edi, dword ptr [rbp+57h+Size]
0x18000f580  mov     dword ptr [rcx+18h], 38h ; '8'
0x18000f587  mov     r8d, edi; Size
0x18000f58a  mov     rax, [rbp+57h+var_50]
0x18000f58e  mov     rcx, r12; void *
0x18000f591  mov     [rax+14h], edi
0x18000f594  mov     rdx, [rbp+57h+Src]; Src
0x18000f598  call    memcpy_0
0x18000f59d  lea     r8, [rbp+57h+arg_0]
0x18000f5a1  mov     rdx, r12
0x18000f5a4  mov     ecx, edi
0x18000f5a6  call    AddAlignedSizeToPointer
0x18000f5ab  test    eax, eax
0x18000f5ad  jnz     loc_18000F729
0x18000f5b3  lea     r12d, [rdi+7]
0x18000f5b7  cmp     r12d, edi
0x18000f5ba  jb      loc_18000F741
0x18000f5c0  and     r12d, 0FFFFFFF8h
0x18000f5c4  add     r12d, 38h ; '8'
0x18000f5c8  cmp     r12d, 38h ; '8'
0x18000f5cc  jb      loc_18000F741
0x18000f5d2  test    r13d, r13d
0x18000f5d5  jz      loc_18000F68D
0x18000f5db  mov     rax, [rbp+57h+var_50]
0x18000f5df  mov     [rax+30h], r12d
0x18000f5e3  mov     ecx, [rsi+40h]
0x18000f5e6  mov     rax, [rbp+57h+var_50]
0x18000f5ea  mov     [rax+2Ch], ecx
0x18000f5ed  mov     r8d, [rsi+40h]; Size
0x18000f5f1  mov     rdx, [rsi+48h]; Src
0x18000f5f5  mov     rcx, [rbp+57h+arg_0]; void *
0x18000f5f9  call    memcpy_0
0x18000f5fe  mov     rdx, [rbp+57h+arg_0]
0x18000f602  lea     r8, [rbp+57h+arg_0]
0x18000f606  mov     ecx, [rsi+40h]
0x18000f609  call    AddAlignedSizeToPointer
0x18000f60e  test    eax, eax
0x18000f610  jnz     loc_18000F729
0x18000f616  mov     eax, [rsi+40h]
0x18000f619  lea     ecx, [rax+7]
0x18000f61c  cmp     ecx, eax
0x18000f61e  jb      loc_18000F741
0x18000f624  and     ecx, 0FFFFFFF8h
0x18000f627  lea     r13d, [rcx+r12]
0x18000f62b  cmp     r13d, r12d
0x18000f62e  jb      loc_18000F741
0x18000f634  mov     rax, [rbp+57h+var_50]
0x18000f638  mov     [rax+28h], r13d
0x18000f63c  mov     ecx, [rsi+30h]
0x18000f63f  mov     rax, [rbp+57h+var_50]
0x18000f643  mov     [rax+24h], ecx
0x18000f646  mov     r8d, [rsi+30h]; Size
0x18000f64a  mov     rdx, [rsi+38h]; Src
0x18000f64e  mov     rcx, [rbp+57h+arg_0]; void *
0x18000f652  call    memcpy_0
0x18000f657  mov     rdx, [rbp+57h+arg_0]
0x18000f65b  lea     r8, [rbp+57h+arg_0]
0x18000f65f  mov     ecx, [rsi+30h]
0x18000f662  call    AddAlignedSizeToPointer
0x18000f667  test    eax, eax
0x18000f669  jnz     loc_18000F729
0x18000f66f  mov     eax, [rsi+30h]
0x18000f672  lea     ecx, [rax+7]
0x18000f675  cmp     ecx, eax
0x18000f677  jb      loc_18000F741
0x18000f67d  and     ecx, 0FFFFFFF8h
0x18000f680  lea     r12d, [rcx+r13]
0x18000f684  cmp     r12d, r13d
0x18000f687  jb      loc_18000F741
0x18000f68d  xor     eax, eax
0x18000f68f  cmp     [rbp+57h+var_48], rax
0x18000f693  jz      short loc_18000F6DE
0x18000f695  mov     rax, [rbp+57h+var_50]
0x18000f699  mov     esi, dword ptr [rbp+57h+arg_18]
0x18000f69c  mov     rcx, [rbp+57h+arg_0]; void *
0x18000f6a0  mov     r8d, esi; Size
0x18000f6a3  mov     [rax+1Ch], esi
0x18000f6a6  mov     rax, [rbp+57h+var_50]
0x18000f6aa  mov     [rax+20h], r12d
0x18000f6ae  mov     rdx, [rbp+57h+var_60]; Src
0x18000f6b2  call    memcpy_0
0x18000f6b7  mov     rdx, [rbp+57h+arg_0]
0x18000f6bb  lea     r8, [rbp+57h+arg_0]
0x18000f6bf  mov     ecx, esi
0x18000f6c1  call    AddAlignedSizeToPointer
0x18000f6c6  test    eax, eax
0x18000f6c8  jnz     short loc_18000F729
0x18000f6ca  lea     eax, [rsi+7]
0x18000f6cd  cmp     eax, esi
0x18000f6cf  jb      short loc_18000F741
0x18000f6d1  and     eax, 0FFFFFFF8h
0x18000f6d4  add     eax, r12d
0x18000f6d7  cmp     eax, r12d
0x18000f6da  jb      short loc_18000F741
0x18000f6dc  xor     eax, eax
0x18000f6de  mov     rcx, [rbp+57h+var_50]
0x18000f6e2  mov     ebx, eax
0x18000f6e4  mov     [r15], rcx
0x18000f6e7  mov     rax, [rbp+57h+arg_10]
0x18000f6eb  mov     [rax], r14d
0x18000f6ee  mov     r8d, 1C7h
0x18000f6f4  lea     rdx, aCreateonexresu; "CreateOneXResultCopy"
0x18000f6fb  lea     rcx, [rbp+57h+var_60]
0x18000f6ff  call    cs:__imp_FreeMemory
0x18000f705  mov     r8d, 1C8h
0x18000f70b  lea     rdx, aCreateonexresu; "CreateOneXResultCopy"
0x18000f712  lea     rcx, [rbp+57h+Src]
0x18000f716  call    cs:__imp_FreeMemory
0x18000f71c  lea     rdi, WPP_GLOBAL_Control
0x18000f723  test    ebx, ebx
0x18000f725  jnz     short loc_18000F776
0x18000f727  jmp     short loc_18000F782
0x18000f729  mov     ebx, eax
0x18000f72b  jmp     short loc_18000F741
  ... truncated ...
```
