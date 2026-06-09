# FillFieldInfoListFromResource

- ea: `0x180008c5c`
- end: `0x180009369`
- name: `FillFieldInfoListFromResource`
- size: `1805`
- prototype: `__int64 __fastcall(const void *, PublisherManifestResource *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008970`
- `0x180026450`

## callees

- `0x180008c5c`
- `0x180009370`
- `0x18000b390`
- `0x180013860`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d46`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FillFieldInfoListFromResource(const void *a1, PublisherManifestResource *a2, __int64 a3)
{
  int v3; // ecx
  unsigned int *v4; // r13
  int v7; // ecx
  int v8; // ecx
  __int64 v9; // rax
  unsigned int v10; // r12d
  __int64 v11; // rax
  signed int v12; // r14d
  HANDLE ProcessHeap; // rax
  DWORD v14; // ebx
  LPVOID v15; // rax
  int v16; // r15d
  unsigned int *v17; // r11
  __int64 v18; // r8
  _DWORD *v19; // r9
  __int64 v20; // rbx
  __int64 v21; // r12
  int v22; // r10d
  signed int v23; // edx
  _DWORD *v24; // rdi
  int v25; // edx
  __int64 result; // rax
  int v27; // ecx
  int v28; // edx
  int v29; // edx
  int v30; // edx
  unsigned int v31; // edx
  unsigned int v32; // r10d
  unsigned int v33; // r8d
  __int64 v34; // rcx
  _DWORD *v35; // rdx
  __int64 v36; // r8
  wchar_t *v37; // rdx
  struct FIELD_INFO *v38; // rdi
  unsigned int v39; // eax
  unsigned int v40; // edx
  int v41; // eax
  wchar_t *v42; // rax
  unsigned int v43; // edx
  __int64 v44; // rax
  int v45; // ecx
  __int64 v46; // rax
  unsigned int v47; // r15d
  unsigned int v48; // r10d
  unsigned int v49; // eax
  unsigned int v50; // edx
  wchar_t *v51; // rax
  unsigned int v52; // edx
  __int64 v53; // rax
  int v54; // [rsp+28h] [rbp-E0h]
  int v55; // [rsp+2Ch] [rbp-DCh]
  int v56; // [rsp+30h] [rbp-D8h]
  __int64 v57; // [rsp+38h] [rbp-D0h]
  _DWORD *v58; // [rsp+40h] [rbp-C8h]
  _DWORD *v59; // [rsp+48h] [rbp-C0h]
  __int64 v60; // [rsp+50h] [rbp-B8h]
  _DWORD *v61; // [rsp+58h] [rbp-B0h]
  unsigned int *v62; // [rsp+60h] [rbp-A8h]
  unsigned int v63; // [rsp+68h] [rbp-A0h]
  unsigned int v64; // [rsp+6Ch] [rbp-9Ch]
  unsigned int v65; // [rsp+70h] [rbp-98h]
  unsigned int v66; // [rsp+74h] [rbp-94h]
  unsigned int v67; // [rsp+78h] [rbp-90h]
  int v68; // [rsp+7Ch] [rbp-8Ch]
  __int64 v69; // [rsp+80h] [rbp-88h]
  _DWORD *v70; // [rsp+88h] [rbp-80h]
  __int128 v71; // [rsp+90h] [rbp-78h] BYREF
  wchar_t *v72; // [rsp+A0h] [rbp-68h]
  _DWORD *v73; // [rsp+A8h] [rbp-60h]
  unsigned int *v74; // [rsp+B0h] [rbp-58h]
  __int64 v75; // [rsp+B8h] [rbp-50h]
  _DWORD *v76; // [rsp+C0h] [rbp-48h]
  __int64 v77; // [rsp+C8h] [rbp-40h]
  wchar_t *v78[2]; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v79; // [rsp+E0h] [rbp-28h]
  wchar_t *v80[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v81; // [rsp+F8h] [rbp-10h]
  wchar_t *v82[2]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v83; // [rsp+110h] [rbp+8h]
  wchar_t *v84[2]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v85; // [rsp+128h] [rbp+20h]
  int v88; // [rsp+190h] [rbp+88h]

  v3 = *(_DWORD *)(a3 + 12);
  v4 = 0;
  v77 = 0;
  v67 = 0;
  v76 = 0;
  v66 = 0;
  v75 = 0;
  v65 = 0;
  v74 = 0;
  v64 = 0;
  v73 = 0;
  v63 = 0;
  v72 = 0;
  v85 = 0;
  v83 = 0;
  v81 = 0;
  v79 = 0;
  v71 = 0;
  *(_OWORD *)v84 = 0;
  *(_OWORD *)v82 = 0;
  *(_OWORD *)v80 = 0;
  *(_OWORD *)v78 = 0;
  if ( v3 )
  {
    v7 = v3 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v45 = v8 - 1;
        if ( v45 )
        {
          if ( v45 != 1 )
            return 50;
          v46 = *((_QWORD *)a2 + 2);
          if ( v46 )
          {
            v47 = *(_DWORD *)(v46 + 8);
            v73 = (_DWORD *)(v46 + 12);
          }
          else
          {
            v73 = 0;
            v47 = 0;
          }
          v63 = v47;
          v12 = v47;
          goto LABEL_10;
        }
        v53 = *((_QWORD *)a2 + 1);
        if ( v53 )
        {
          v10 = *(_DWORD *)(v53 + 8);
          v74 = (unsigned int *)(v53 + 12);
        }
        else
        {
          v74 = 0;
          v10 = 0;
        }
        v64 = v10;
      }
      else
      {
        v9 = *((_QWORD *)a2 + 6);
        if ( v9 )
        {
          v10 = *(_DWORD *)(v9 + 8);
          v75 = v9 + 12;
        }
        else
        {
          v75 = 0;
          v10 = 0;
        }
        v65 = v10;
      }
    }
    else
    {
      v44 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        v10 = *(_DWORD *)(v44 + 8);
        v76 = (_DWORD *)(v44 + 12);
      }
      else
      {
        v76 = 0;
        v10 = 0;
      }
      v66 = v10;
    }
  }
  else
  {
    v11 = *((_QWORD *)a2 + 3);
    if ( v11 )
    {
      v10 = *(_DWORD *)(v11 + 8);
      v77 = v11 + 12;
    }
    else
    {
      v77 = 0;
      v10 = 0;
    }
    v67 = v10;
  }
  v12 = v10;
LABEL_10:
  ProcessHeap = GetProcessHeap();
  v14 = 8;
  v15 = HeapAlloc(ProcessHeap, 8u, 40LL * v12);
  *(_QWORD *)a3 = v15;
  if ( !v15 )
    return v14;
  v16 = -1;
  *(_DWORD *)(a3 + 8) = v12;
  v59 = 0;
  v17 = 0;
  v62 = 0;
  v57 = 0;
  v18 = 0;
  v60 = 0;
  v19 = 0;
  v58 = 0;
  v20 = 0;
  v61 = 0;
  v21 = 0;
  v22 = -1;
  v70 = 0;
  v23 = 0;
  v88 = -1;
  v24 = 0;
  v54 = -1;
  v55 = -1;
  while ( 1 )
  {
    v68 = v23;
    if ( v23 >= v12 )
      return 0;
    v25 = *(_DWORD *)(a3 + 12);
    switch ( v25 )
    {
      case 0:
        v48 = v22 + 1;
        v56 = v48;
        if ( v48 >= v67 )
          return 0;
        if ( v48 )
          v21 += 16;
        else
          v21 = v77;
        v40 = *(_DWORD *)(v21 + 12);
        v69 = v21;
        v41 = *(_DWORD *)(v21 + 8);
        v84[0] = *(wchar_t **)v21;
        LODWORD(v85) = v41;
        result = PublisherManifestResource::GetResourceString(a2, v40, (const wchar_t **)&v84[1]);
        if ( (_DWORD)result )
          return result;
        DWORD2(v71) = v85;
        *(wchar_t **)&v71 = v84[0];
        v42 = v84[1];
        goto LABEL_49;
      case 1:
        v39 = v55 + 1;
        v55 = v39;
        if ( v39 >= v66 )
          return 0;
        if ( v39 )
          v19 += 3;
        else
          v19 = v76;
        v58 = v19;
LABEL_25:
        v27 = v88;
        goto LABEL_26;
      case 2:
        v49 = v54 + 1;
        v54 = v49;
        if ( v49 >= v65 )
          return 0;
        if ( v49 )
          v18 += 16;
        else
          v18 = v75;
        v57 = v18;
        goto LABEL_25;
    }
    if ( v25 != 3 )
    {
      if ( v25 != 4 )
        return 0;
      if ( ++v16 >= v63 )
        return 0;
      if ( v16 )
        v24 += 3;
      else
        v24 = v73;
      v59 = v24;
      goto LABEL_25;
    }
    v27 = v88 + 1;
    if ( v88 + 1 >= v64 )
      return 0;
    if ( v88 == -1 )
      v17 = v74;
    else
      v17 += 7;
    v4 = v17;
LABEL_26:
    v56 = v22;
    v69 = v20;
    v61 = v19;
    v60 = v18;
    v88 = v27;
    v62 = v17;
    v70 = v24;
    v28 = v25 - 1;
    if ( !v28 )
    {
      v50 = v58[2];
      LODWORD(v82[0]) = *v58;
      LODWORD(v83) = v58[1];
      result = PublisherManifestResource::GetResourceString(a2, v50, (const wchar_t **)&v82[1]);
      if ( (_DWORD)result )
        return result;
      DWORD2(v71) = v83;
      *(_QWORD *)&v71 = LODWORD(v82[0]);
      v51 = v82[1];
LABEL_80:
      v72 = v51;
LABEL_38:
      v70 = v24;
      v69 = v20;
      goto LABEL_39;
    }
    v29 = v28 - 1;
    if ( !v29 )
    {
      v52 = *(_DWORD *)(v57 + 4);
      v81 = *(_QWORD *)(v57 + 8);
      result = PublisherManifestResource::GetResourceString(a2, v52, (const wchar_t **)&v80[1]);
      if ( (_DWORD)result )
        return result;
      DWORD2(v71) = HIDWORD(v81);
      *(_QWORD *)&v71 = (unsigned int)v81;
      v51 = v80[1];
      goto LABEL_80;
    }
    v30 = v29 - 1;
    if ( !v30 )
    {
      v31 = v4[6];
      v32 = v4[1];
      if ( v31 )
      {
        v33 = *((_DWORD *)a2 + 34) - *((_DWORD *)a2 + 30);
        if ( v31 < v33 )
          return 13;
        if ( v31 + 4 < v31 )
          return 13;
        if ( v31 + 4 > v33 + *(_DWORD *)(*((_QWORD *)a2 + 17) + 4LL) )
          return 13;
        v34 = v31;
        v35 = (_DWORD *)(v31 + *((_QWORD *)a2 + 15));
        if ( *v35 <= 6u )
          return 13;
        v36 = (unsigned int)*v35;
        if ( v36 + v34 >= (unsigned __int64)*((unsigned int *)a2 + 36)
          || *((_WORD *)v35 + ((unsigned __int64)(v36 - 4) >> 1) + 1) )
        {
          return 13;
        }
        v18 = v60;
        v37 = (wchar_t *)(v35 + 1);
        v27 = v88;
      }
      else
      {
        v37 = 0;
      }
      *(_QWORD *)&v71 = *v4;
      DWORD2(v71) = v32;
      v72 = v37;
      v62 = v17;
      v88 = v27;
      v60 = v18;
      v61 = v19;
      goto LABEL_38;
    }
    if ( v30 != 1 )
      break;
    v43 = v59[2];
    LODWORD(v78[0]) = *v59;
    LODWORD(v79) = v59[1];
    result = PublisherManifestResource::GetResourceString(a2, v43, (const wchar_t **)&v78[1]);
    if ( (_DWORD)result )
      return result;
    DWORD2(v71) = v79;
    *(_QWORD *)&v71 = LODWORD(v78[0]);
    v42 = v78[1];
LABEL_49:
    v72 = v42;
LABEL_39:
    v38 = (struct FIELD_INFO *)(*(_QWORD *)a3 + 40LL * v68);
    v14 = FillFieldInfoFromResource(a1, (__int64)&v71, (__int64)v38);
    if ( v14 )
      goto LABEL_93;
    v20 = v69;
    v23 = v68 + 1;
    v24 = v70;
    v17 = v62;
    v18 = v60;
    v19 = v61;
    v22 = v56;
  }
  v14 = 50;
  v38 = 0;
LABEL_93:
  TdhpClearFieldInfo(v38);
  return v14;
}

```

## disassembly

```asm
0x180008c5c  mov     rax, rsp
0x180008c5f  mov     [rax+10h], rbx
0x180008c63  mov     [rax+18h], r8
0x180008c67  mov     [rax+8], rcx
0x180008c6b  push    rbp
0x180008c6c  push    rsi
0x180008c6d  push    rdi
0x180008c6e  push    r12
0x180008c70  push    r13
0x180008c72  push    r14
0x180008c74  push    r15
0x180008c76  lea     rbp, [rax-68h]
0x180008c7a  sub     rsp, 130h
0x180008c81  mov     ecx, [r8+0Ch]
0x180008c85  xor     r13d, r13d
0x180008c88  xor     eax, eax
0x180008c8a  mov     [rbp+60h+var_A0], r13
0x180008c8e  mov     dword ptr [rsp+160h+var_F0], r13d
0x180008c93  xorps   xmm0, xmm0
0x180008c96  mov     [rbp+60h+var_A8], r13
0x180008c9a  xorps   xmm1, xmm1
0x180008c9d  mov     [rsp+160h+var_F4], r13d
0x180008ca2  mov     rdi, r8
0x180008ca5  mov     [rbp+60h+var_B0], r13
0x180008ca9  mov     rsi, rdx
0x180008cac  mov     [rsp+160h+var_F8], r13d
0x180008cb1  mov     [rbp+60h+var_B8], r13
0x180008cb5  mov     [rsp+160h+var_FC], r13d
0x180008cba  mov     [rbp+60h+var_C0], r13
0x180008cbe  mov     [rsp+160h+var_100], r13d
0x180008cc3  mov     [rbp+60h+var_C8], rax
0x180008cc7  mov     [rbp+60h+var_40], rax
0x180008ccb  mov     [rbp+60h+var_58], rax
0x180008ccf  mov     [rbp+60h+var_70], rax
0x180008cd3  mov     [rbp+60h+var_88], rax
0x180008cd7  movups  [rbp+60h+var_D8], xmm0
0x180008cdb  movups  xmmword ptr [rbp+60h+var_50], xmm1
0x180008cdf  movups  xmmword ptr [rbp+60h+var_68], xmm0
0x180008ce3  movups  xmmword ptr [rbp+60h+var_80], xmm1
0x180008ce7  movups  xmmword ptr [rbp+60h+var_98], xmm0
0x180008ceb  test    ecx, ecx
0x180008ced  jz      short loc_180008D1F
0x180008cef  sub     ecx, 1
0x180008cf2  jz      loc_180009151
0x180008cf8  sub     ecx, 1
0x180008cfb  jnz     loc_18000917F
0x180008d01  mov     rax, [rdx+30h]
0x180008d05  test    rax, rax
0x180008d08  jz      loc_1800091D6
0x180008d0e  mov     r12d, [rax+8]
0x180008d12  lea     rcx, [rax+0Ch]
0x180008d16  mov     [rbp+60h+var_B0], rcx
0x180008d1a  jmp     loc_1800091DD
0x180008d1f  mov     rax, [rdx+18h]
0x180008d23  test    rax, rax
0x180008d26  jnz     loc_18000916E
0x180008d2c  mov     [rbp+60h+var_A0], r13
0x180008d30  mov     r12d, r13d
0x180008d33  mov     dword ptr [rsp+160h+var_F0], r12d
0x180008d38  mov     r14d, r12d
0x180008d3b  movsxd  rax, r14d
0x180008d3e  lea     rbx, [rax+rax*4]
0x180008d42  shl     rbx, 3
0x180008d46  call    cs:__imp_GetProcessHeap
0x180008d4c  mov     r8, rbx; dwBytes
0x180008d4f  mov     ebx, 8
0x180008d54  mov     edx, ebx; dwFlags
0x180008d56  mov     rcx, rax; hHeap
0x180008d59  call    cs:__imp_HeapAlloc
0x180008d5f  mov     [rdi], rax
0x180008d62  test    rax, rax
0x180008d65  jz      loc_180008E00
0x180008d6b  or      r15d, 0FFFFFFFFh
0x180008d6f  mov     [rdi+8], r14d
0x180008d73  xor     r10d, r10d
0x180008d76  mov     [rsp+160h+var_120], r13
0x180008d7b  mov     r11d, r10d
0x180008d7e  mov     qword ptr [rsp+160h+var_108], r10
0x180008d83  mov     [rsp+160h+var_130], r10
0x180008d88  mov     r8d, r10d
0x180008d8b  mov     [rsp+160h+var_118], r10
0x180008d90  mov     r9d, r10d
0x180008d93  mov     [rsp+160h+var_128], r10
0x180008d98  mov     ebx, r10d
0x180008d9b  mov     [rsp+160h+var_110], r10
0x180008da0  mov     r12d, r10d
0x180008da3  mov     r10d, r15d
0x180008da6  mov     [rbp+60h+var_E0], r13
0x180008daa  mov     edx, r13d
0x180008dad  mov     [rbp+60h+arg_18], r15d
0x180008db4  mov     rdi, r13
0x180008db7  mov     [rsp+160h+var_140], r15d
0x180008dbc  mov     [rsp+24h], r15d
0x180008dc1  mov     dword ptr [rsp+160h+var_F0+4], edx
0x180008dc5  cmp     edx, r14d
0x180008dc8  jge     short loc_180008DFE
0x180008dca  mov     rdx, [rbp+60h+arg_10]
0x180008dd1  mov     edx, [rdx+0Ch]
0x180008dd4  mov     ecx, edx
0x180008dd6  test    edx, edx
0x180008dd8  jz      loc_1800091AE
0x180008dde  sub     ecx, 1
0x180008de1  jz      loc_18000900E
0x180008de7  sub     ecx, 1
0x180008dea  jz      loc_180009206
0x180008df0  sub     ecx, 1
0x180008df3  jz      loc_1800090DA
0x180008df9  cmp     ecx, 1
0x180008dfc  jz      short loc_180008E1D
0x180008dfe  xor     ebx, ebx
0x180008e00  mov     eax, ebx
0x180008e02  mov     rbx, [rsp+160h+arg_8]
0x180008e0a  add     rsp, 130h
0x180008e11  pop     r15
0x180008e13  pop     r14
0x180008e15  pop     r13
0x180008e17  pop     r12
0x180008e19  pop     rdi
0x180008e1a  pop     rsi
0x180008e1b  pop     rbp
0x180008e1c  retn
0x180008e1d  inc     r15d
0x180008e20  cmp     r15d, [rsp+160h+var_100]
0x180008e25  jnb     short loc_180008DFE
0x180008e27  test    r15d, r15d
0x180008e2a  jnz     loc_180009038
0x180008e30  mov     rdi, [rbp+60h+var_C0]
0x180008e34  mov     [rsp+160h+var_120], rdi
0x180008e39  mov     ecx, [rbp+60h+arg_18]
0x180008e3f  mov     al, 1
0x180008e41  test    al, al
0x180008e43  jz      short loc_180008DFE
0x180008e45  mov     eax, [rsp+24h]
0x180008e49  mov     [rsp+24h], eax
0x180008e4d  mov     rax, [rsp+160h+var_128]
0x180008e52  mov     [rsp+160h+var_128], rax
0x180008e57  mov     eax, [rsp+160h+var_140]
0x180008e5b  mov     [rsp+160h+var_140], eax
0x180008e5f  mov     rax, [rsp+160h+var_130]
0x180008e64  mov     [rsp+160h+var_130], rax
0x180008e69  xor     eax, eax
0x180008e6b  mov     dword ptr [rsp+160h+var_138], r10d
0x180008e70  mov     [rsp+78h], rbx
0x180008e75  mov     [rsp+160h+var_110], r9
0x180008e7a  mov     [rsp+160h+var_118], r8
0x180008e7f  mov     [rbp+60h+arg_18], ecx
0x180008e85  mov     qword ptr [rsp+160h+var_108], r11
0x180008e8a  mov     [rbp+60h+var_E0], rdi
0x180008e8e  test    edx, edx
0x180008e90  jz      loc_180009041
0x180008e96  sub     edx, 1
0x180008e99  jz      loc_180009234
0x180008e9f  sub     edx, 1
0x180008ea2  jz      loc_1800092C5
0x180008ea8  sub     edx, 1
0x180008eab  jnz     loc_180009109
0x180008eb1  mov     edx, [r13+18h]
0x180008eb5  mov     r10d, [r13+4]
0x180008eb9  test    edx, edx
0x180008ebb  jz      loc_180009343
0x180008ec1  mov     r8d, [rsi+88h]
0x180008ec8  sub     r8d, [rsi+78h]
0x180008ecc  cmp     edx, r8d
0x180008ecf  jb      loc_180009004
0x180008ed5  lea     r9d, [rdx+4]
0x180008ed9  cmp     r9d, edx
0x180008edc  jb      loc_180009004
0x180008ee2  mov     rax, [rsi+88h]
0x180008ee9  mov     eax, [rax+4]
0x180008eec  add     eax, r8d
0x180008eef  cmp     r9d, eax
0x180008ef2  ja      loc_180009004
0x180008ef8  mov     ecx, edx
0x180008efa  mov     rdx, [rsi+78h]
0x180008efe  add     rdx, rcx
0x180008f01  cmp     dword ptr [rdx], 6
0x180008f04  jbe     loc_180009004
0x180008f0a  mov     r8d, [rdx]
0x180008f0d  mov     eax, [rsi+90h]
0x180008f13  add     rcx, r8
0x180008f16  cmp     rcx, rax
0x180008f19  jnb     loc_180009004
0x180008f1f  lea     rax, [r8-4]
0x180008f23  xor     ecx, ecx
0x180008f25  shr     rax, 1
0x180008f28  cmp     [rdx+rax*2+2], cx
0x180008f2d  jnz     loc_180009004
0x180008f33  mov     r8, [rsp+160h+var_118]
0x180008f38  add     rdx, 4
0x180008f3c  mov     r9, [rsp+160h+var_110]
0x180008f41  mov     ecx, [rbp+60h+arg_18]
0x180008f47  mov     eax, [r13+0]
0x180008f4b  mov     qword ptr [rbp+60h+var_D8], rax
0x180008f4f  mov     rax, [rsp+160h+var_120]
0x180008f54  mov     [rsp+160h+var_120], rax
0x180008f59  mov     rax, [rsp+160h+var_130]
0x180008f5e  mov     [rsp+160h+var_130], rax
0x180008f63  mov     eax, [rsp+160h+var_140]
0x180008f67  mov     [rsp+160h+var_140], eax
0x180008f6b  mov     rax, [rsp+160h+var_128]
0x180008f70  mov     [rsp+160h+var_128], rax
0x180008f75  mov     dword ptr [rbp+60h+var_D8+8], r10d
0x180008f79  mov     [rbp+60h+var_C8], rdx
0x180008f7d  mov     qword ptr [rsp+160h+var_108], r11
0x180008f82  mov     [rbp+60h+arg_18], ecx
0x180008f88  mov     [rsp+160h+var_118], r8
0x180008f8d  mov     [rsp+160h+var_110], r9
0x180008f92  mov     eax, [rsp+24h]
0x180008f96  mov     [rsp+24h], eax
0x180008f9a  mov     eax, dword ptr [rsp+160h+var_138]
0x180008f9e  mov     dword ptr [rsp+160h+var_138], eax
0x180008fa2  mov     [rbp+60h+var_E0], rdi
0x180008fa6  mov     [rsp+78h], rbx
0x180008fab  movsxd  rax, dword ptr [rsp+160h+var_F0+4]
0x180008fb0  lea     rdx, [rbp+60h+var_D8]
0x180008fb4  lea     rcx, [rax+rax*4]
0x180008fb8  mov     rax, [rbp+60h+arg_10]
0x180008fbf  mov     rax, [rax]
0x180008fc2  lea     rdi, [rax+rcx*8]
0x180008fc6  mov     rcx, [rbp+60h+lpSource]; lpSource
0x180008fca  mov     r8, rdi
0x180008fcd  call    FillFieldInfoFromResource
0x180008fd2  mov     ebx, eax
0x180008fd4  test    eax, eax
0x180008fd6  jnz     loc_18000935C
0x180008fdc  mov     edx, dword ptr [rsp+160h+var_F0+4]
0x180008fe0  mov     rbx, [rsp+78h]
0x180008fe5  inc     edx
0x180008fe7  mov     rdi, [rbp+60h+var_E0]
0x180008feb  mov     r11, qword ptr [rsp+160h+var_108]
0x180008ff0  mov     r8, [rsp+160h+var_118]
0x180008ff5  mov     r9, [rsp+160h+var_110]
0x180008ffa  mov     r10d, dword ptr [rsp+160h+var_138]
0x180008fff  jmp     loc_180008DC1
0x180009004  mov     eax, 0Dh
0x180009009  jmp     loc_180008E02
0x18000900e  mov     eax, [rsp+24h]
0x180009012  inc     eax
0x180009014  mov     [rsp+24h], eax
0x180009018  cmp     eax, [rsp+160h+var_F4]
0x18000901c  jnb     loc_180008DFE
0x180009022  test    eax, eax
0x180009024  jnz     loc_180009100
0x18000902a  mov     r9, [rbp+60h+var_A8]
0x18000902e  mov     [rsp+160h+var_128], r9
0x180009033  jmp     loc_180008E39
0x180009038  add     rdi, 0Ch
0x18000903c  jmp     loc_180008E34
0x180009041  mov     rax, [rsp+160h+var_130]
0x180009046  mov     [rsp+160h+var_130], rax
0x18000904b  mov     eax, [rsp+160h+var_140]
0x18000904f  mov     [rsp+160h+var_140], eax
0x180009053  mov     rax, [rsp+160h+var_128]
0x180009058  mov     [rsp+160h+var_128], rax
0x18000905d  mov     eax, [rsp+24h]
0x180009061  mov     [rsp+24h], eax
0x180009065  mov     rax, [rsp+160h+var_120]
0x18000906a  mov     [rsp+160h+var_120], rax
0x18000906f  mov     [rbp+60h+var_E0], rdi
0x180009073  mov     qword ptr [rsp+160h+var_108], r11
0x180009078  mov     [rbp+60h+arg_18], ecx
0x18000907e  mov     [rsp+160h+var_118], r8
0x180009083  mov     [rsp+160h+var_110], r9
0x180009088  mov     dword ptr [rsp+160h+var_138], r10d
0x18000908d  mov     eax, [rbx]
0x18000908f  lea     r8, [rbp+60h+var_50+8]; wchar_t **
0x180009093  mov     ecx, [rbx+4]
0x180009096  mov     edx, [rbx+0Ch]; unsigned int
0x180009099  shl     rcx, 20h
0x18000909d  or      rcx, rax
0x1800090a0  mov     [rsp+78h], rbx
0x1800090a5  mov     eax, [rbx+8]
0x1800090a8  mov     [rbp+60h+var_50], rcx
0x1800090ac  mov     rcx, rsi; this
0x1800090af  mov     dword ptr [rbp+60h+var_40], eax
0x1800090b2  call    ?GetResourceString@PublisherManifestResource@@QEBAKKAEAPEB_W@Z; PublisherManifestResource::GetResourceString(ulong,wchar_t const * &)
0x1800090b7  test    eax, eax
0x1800090b9  jnz     loc_180008E02
0x1800090bf  mov     eax, dword ptr [rbp+60h+var_40]
0x1800090c2  mov     dword ptr [rbp+60h+var_D8+8], eax
0x1800090c5  mov     rax, [rbp+60h+var_50]
0x1800090c9  mov     qword ptr [rbp+60h+var_D8], rax
0x1800090cd  mov     rax, [rbp+60h+var_50+8]
0x1800090d1  mov     [rbp+60h+var_C8], rax
0x1800090d5  jmp     loc_180008FAB
0x1800090da  mov     ecx, [rbp+60h+arg_18]
0x1800090e0  inc     ecx
0x1800090e2  cmp     ecx, [rsp+160h+var_FC]
0x1800090e6  jnb     loc_180008DFE
0x1800090ec  test    ecx, ecx
0x1800090ee  jz      loc_18000922B
0x1800090f4  add     r11, 1Ch
0x1800090f8  mov     r13, r11
0x1800090fb  jmp     loc_180008E3F
0x180009100  add     r9, 0Ch
0x180009104  jmp     loc_18000902E
0x180009109  cmp     edx, 1
0x18000910c  jnz     loc_180009354
0x180009112  mov     rbx, [rsp+160h+var_120]
0x180009117  lea     r8, [rbp+60h+var_98+8]; wchar_t **
  ... truncated ...
```
