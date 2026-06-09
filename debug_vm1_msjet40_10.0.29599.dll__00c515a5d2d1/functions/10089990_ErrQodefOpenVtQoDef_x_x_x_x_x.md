# ErrQodefOpenVtQoDef(x,x,x,x,x)

- ea: `0x10089990`
- end: `0x10089c9b`
- name: `_ErrQodefOpenVtQoDef@20`
- size: `779`
- prototype: `int __stdcall(int, int, void *Src, int, int)`
- caller_count: `7`
- callee_count: `21`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10021a40`
- `0x10088230`
- `0x1008c700`
- `0x1009fe37`
- `0x100a0040`
- `0x100b5dcb`
- `0x100f4e46`

## callees

- `0x1002a7d0`
- `0x1002a840`
- `0x1003ea00`
- `0x10043060`
- `0x10043220`
- `0x100437f0`
- `0x10043890`
- `0x100439d0`
- `0x10043f30`
- `0x10044a70`
- `0x10044d10`
- `0x100450d0`
- `0x10045320`
- `0x100454a0`
- `0x1008937e`
- `0x10089990`
- `0x1008ab88`
- `0x1008ac00`
- `0x1008b93d`
- `0x1008b9c3`
- `0x10116b41`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10089a5a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10089a5a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10089a24`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10089a24`

## pseudocode

```c
int __stdcall ErrQodefOpenVtQoDef(int a1, int a2, _WORD *Src, _DWORD *a4, int a5)
{
  int result; // eax
  int ObjInfoId; // esi
  int *v7; // edi
  void *v8; // eax
  void **v9; // ebx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  int v15; // [esp+0h] [ebp-1Ch]
  int v16; // [esp+10h] [ebp-Ch] BYREF
  int v17; // [esp+14h] [ebp-8h] BYREF
  char v18; // [esp+1Bh] [ebp-1h] BYREF

  result = ErrAllocateTableidForVSesid(a1, a4, 0, 0);
  if ( result >= 0 )
  {
    ObjInfoId = ErrQodefAllocQodefvt(&v17);
    if ( ObjInfoId < 0 )
    {
LABEL_36:
      ReleaseTableid(*a4);
      return ObjInfoId;
    }
    v7 = (int *)v17;
    *(_DWORD *)v17 = a1;
    v7[1] = a2;
    v7[15] = 1;
    v7[18] = a5;
    if ( a2 != -1 && Src && *Src )
    {
      result = ErrDispGetDatabaseInfo(a1, a2, &v17, 4, 8);
      ObjInfoId = result;
      if ( result < 0 )
        return result;
      if ( v17 == 0x10000 || v17 == 65537 )
        v7[25] = 1;
    }
    v8 = _malloc(8u);
    v7[2] = (int)v8;
    if ( !v8 )
    {
LABEL_35:
      QodefReleaseQodefvt(v15);
      goto LABEL_36;
    }
    ObjInfoId = ErrGetObjInfoId(5, Src, v8, v7 + 20);
    if ( ObjInfoId < 0 )
    {
      v9 = (void **)(v7 + 2);
      if ( v7[2] )
        _free(*v9);
      *v9 = 0;
      goto LABEL_35;
    }
    v10 = v7[2];
    v17 = 4;
    *(_DWORD *)(v10 + 4) = 1;
    ObjInfoId = ErrGetSysField(L"Flags", v7 + 22, &v17);
    if ( ObjInfoId >= 0 )
    {
      v11 = v7[22];
      if ( (v11 & 0x4000000) == 0 )
      {
        v7[23] = v11;
        v7[24] = v11 & 0x18000000;
        v12 = ErrDispPrepareUpdate2(a1, *(_DWORD *)v7[2], 2);
        ObjInfoId = v12;
        if ( v12 == -1102 || v12 == -1107 )
        {
          v7[16] = 1;
        }
        else if ( v12 == -1809 )
        {
          v7[17] = 1;
        }
        else if ( v12 < 0 )
        {
          goto LABEL_34;
        }
        ObjInfoId = ErrREPOpenQuery(Src, *a4, &v17);
        if ( ObjInfoId >= 0 )
        {
          if ( v17 )
            v7[17] = 1;
          ObjInfoId = ErrDispOpenTable(a1, a2, v7 + 4, L"MSysQueries", 0x80000000);
          if ( ObjInfoId >= 0 )
          {
            v17 = v7[4];
            ObjInfoId = ErrQodefGetColumnidsSq(v7);
            if ( ObjInfoId >= 0 )
            {
              ObjInfoId = ErrDispSetCurrentIndex(a1, v17, L"ObjectIdAttribute");
              if ( ObjInfoId >= 0 )
              {
                v14 = ErrQodefSeekSq(0, &dword_1000C084, v13, 1, 0);
                ObjInfoId = v14;
                if ( v14 == -1603 )
                {
                  UtilSetErrorInfoReal(*v7, Src, 0, 0, -8176, 0, 0, 0);
                  ObjInfoId = -3067;
                }
                else if ( v14 >= 0 )
                {
                  ObjInfoId = ErrDispMove2(a1, v17, 1, 0);
                  if ( ObjInfoId >= 0 )
                  {
                    ObjInfoId = ErrDispRetrieveColumn(a1, v17, v7[8], &v18, 1, 0, 0, 0);
                    if ( ObjInfoId >= 0 )
                    {
                      if ( v18 != -1 || (ObjInfoId = ErrDispMove2(a1, v17, -1, 0), ObjInfoId >= 0) )
                      {
                        ErrUpdateTableid(*a4, v7, &vtfndefQodef);
                        ObjInfoId = ErrDispDupCursor(*v7, v7[4], &v16, 0);
                        if ( ObjInfoId >= 0 )
                        {
                          v7[5] = v16;
                          ObjInfoId = ErrDispSetCurrentIndex(*v7, v16, L"ObjectIdAttribute");
                          if ( ObjInfoId >= 0 )
                            return 0;
                          ErrDispCloseTable(a1, v16);
                          v16 = -1;
                        }
                      }
                    }
                  }
                }
              }
            }
            ErrDispCloseTable(a1, v17);
          }
        }
        goto LABEL_34;
      }
      UtilSetErrorInfoReal(a1, Src, 0, 0, -8754, 0, 0, 0);
      ObjInfoId = -3823;
    }
LABEL_34:
    CloseSysObjCursor(a1, v7 + 2);
    goto LABEL_35;
  }
  return result;
}

```

## disassembly

```asm
0x10089990  mov     edi, edi
0x10089992  push    ebp
0x10089993  mov     ebp, esp
0x10089995  sub     esp, 10h
0x10089998  xor     eax, eax
0x1008999a  push    ebx
0x1008999b  mov     ebx, [ebp+arg_0]
0x1008999e  push    esi
0x1008999f  push    edi
0x100899a0  push    eax
0x100899a1  push    eax
0x100899a2  push    [ebp+arg_C]
0x100899a5  push    ebx
0x100899a6  call    _ErrAllocateTableidForVSesid@16; ErrAllocateTableidForVSesid(x,x,x,x)
0x100899ab  test    eax, eax
0x100899ad  js      loc_10089BE6
0x100899b3  lea     ecx, [ebp+var_8]
0x100899b6  call    _ErrQodefAllocQodefvt@4; ErrQodefAllocQodefvt(x)
0x100899bb  mov     esi, eax
0x100899bd  test    esi, esi
0x100899bf  js      loc_10089BDA
0x100899c5  mov     edi, [ebp+var_8]
0x100899c8  mov     ecx, [ebp+arg_4]
0x100899cb  mov     eax, [ebp+arg_10]
0x100899ce  mov     [edi], ebx
0x100899d0  mov     [edi+4], ecx
0x100899d3  mov     dword ptr [edi+3Ch], 1
0x100899da  mov     [edi+48h], eax
0x100899dd  cmp     ecx, 0FFFFFFFFh
0x100899e0  jz      short loc_10089A22
0x100899e2  mov     eax, [ebp+Src]
0x100899e5  test    eax, eax
0x100899e7  jz      short loc_10089A22
0x100899e9  xor     edx, edx
0x100899eb  cmp     [eax], dx
0x100899ee  jz      short loc_10089A22
0x100899f0  push    8
0x100899f2  push    4
0x100899f4  lea     eax, [ebp+var_8]
0x100899f7  push    eax
0x100899f8  push    ecx
0x100899f9  push    ebx
0x100899fa  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x100899ff  mov     esi, eax
0x10089a01  test    esi, esi
0x10089a03  js      loc_10089BE6
0x10089a09  cmp     [ebp+var_8], 10000h
0x10089a10  jz      short loc_10089A1B
0x10089a12  cmp     [ebp+var_8], 10001h
0x10089a19  jnz     short loc_10089A22
0x10089a1b  mov     dword ptr [edi+64h], 1
0x10089a22  push    8; Size
0x10089a24  call    ds:__imp__malloc
0x10089a2a  mov     [edi+8], eax
0x10089a2d  pop     ecx
0x10089a2e  test    eax, eax
0x10089a30  jz      loc_10089BD3
0x10089a36  mov     edx, [ebp+arg_4]
0x10089a39  lea     ecx, [edi+50h]
0x10089a3c  push    ecx
0x10089a3d  push    eax
0x10089a3e  push    [ebp+Src]
0x10089a41  mov     ecx, ebx
0x10089a43  push    5
0x10089a45  call    _ErrGetObjInfoId@24; ErrGetObjInfoId(x,x,x,x,x,x)
0x10089a4a  mov     esi, eax
0x10089a4c  test    esi, esi
0x10089a4e  jns     short loc_10089A6C
0x10089a50  lea     ebx, [edi+8]
0x10089a53  cmp     dword ptr [ebx], 0
0x10089a56  jz      short loc_10089A61
0x10089a58  push    dword ptr [ebx]; Block
0x10089a5a  call    ds:__imp__free
0x10089a60  pop     ecx
0x10089a61  mov     dword ptr [ebx], 0
0x10089a67  jmp     loc_10089BD3
0x10089a6c  mov     eax, [edi+8]
0x10089a6f  lea     edx, [ebp+var_8]
0x10089a72  push    edx
0x10089a73  mov     [ebp+var_8], 4
0x10089a7a  mov     ecx, ebx
0x10089a7c  mov     dword ptr [eax+4], 1
0x10089a83  lea     eax, [edi+58h]
0x10089a86  mov     edx, [edi+8]
0x10089a89  push    eax
0x10089a8a  push    offset _wszSoFlagsColumn; "Flags"
0x10089a8f  mov     edx, [edx]
0x10089a91  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x10089a96  mov     esi, eax
0x10089a98  test    esi, esi
0x10089a9a  js      loc_10089BC9
0x10089aa0  mov     eax, [edi+58h]
0x10089aa3  test    eax, 4000000h
0x10089aa8  jz      short loc_10089AC9
0x10089aaa  xor     eax, eax
0x10089aac  push    eax; int
0x10089aad  push    eax; int
0x10089aae  push    eax; int
0x10089aaf  push    0FFFFDDCEh; int
0x10089ab4  push    eax; void *
0x10089ab5  push    eax; void *
0x10089ab6  push    [ebp+Src]; Src
0x10089ab9  push    ebx; int
0x10089aba  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10089abf  mov     esi, 0FFFFF111h
0x10089ac4  jmp     loc_10089BC9
0x10089ac9  mov     [edi+5Ch], eax
0x10089acc  and     eax, 18000000h
0x10089ad1  mov     [edi+60h], eax
0x10089ad4  mov     eax, [edi+8]
0x10089ad7  push    2
0x10089ad9  push    dword ptr [eax]
0x10089adb  push    ebx
0x10089adc  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x10089ae1  mov     esi, eax
0x10089ae3  cmp     esi, 0FFFFFBB2h
0x10089ae9  jz      short loc_10089B0D
0x10089aeb  cmp     esi, 0FFFFFBADh
0x10089af1  jz      short loc_10089B0D
0x10089af3  cmp     esi, 0FFFFF8EFh
0x10089af9  jnz     short loc_10089B04
0x10089afb  mov     dword ptr [edi+44h], 1
0x10089b02  jmp     short loc_10089B14
0x10089b04  test    esi, esi
0x10089b06  jns     short loc_10089B14
0x10089b08  jmp     loc_10089BC9
0x10089b0d  mov     dword ptr [edi+40h], 1
0x10089b14  mov     edx, [ebp+arg_4]
0x10089b17  lea     eax, [ebp+var_8]
0x10089b1a  push    eax
0x10089b1b  mov     eax, [ebp+arg_C]
0x10089b1e  mov     ecx, ebx
0x10089b20  push    dword ptr [eax]
0x10089b22  push    [ebp+Src]
0x10089b25  call    _ErrREPOpenQuery@20; ErrREPOpenQuery(x,x,x,x,x)
0x10089b2a  mov     esi, eax
0x10089b2c  test    esi, esi
0x10089b2e  js      loc_10089BC9
0x10089b34  cmp     [ebp+var_8], 0
0x10089b38  jz      short loc_10089B41
0x10089b3a  mov     dword ptr [edi+44h], 1
0x10089b41  push    80000000h
0x10089b46  push    offset _wszSqTable; "MSysQueries"
0x10089b4b  lea     eax, [edi+10h]
0x10089b4e  push    eax
0x10089b4f  push    [ebp+arg_4]
0x10089b52  push    ebx
0x10089b53  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10089b58  mov     esi, eax
0x10089b5a  test    esi, esi
0x10089b5c  js      short loc_10089BC9
0x10089b5e  mov     eax, [edi+10h]
0x10089b61  mov     ecx, edi
0x10089b63  mov     [ebp+var_8], eax
0x10089b66  call    _ErrQodefGetColumnidsSq@4; ErrQodefGetColumnidsSq(x)
0x10089b6b  mov     esi, eax
0x10089b6d  test    esi, esi
0x10089b6f  js      short loc_10089BC0
0x10089b71  push    offset _wszSqAttributeIndex; "ObjectIdAttribute"
0x10089b76  push    [ebp+var_8]
0x10089b79  push    ebx
0x10089b7a  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10089b7f  mov     esi, eax
0x10089b81  test    esi, esi
0x10089b83  js      short loc_10089BC0
0x10089b85  mov     edx, [edi+50h]
0x10089b88  xor     eax, eax
0x10089b8a  push    eax
0x10089b8b  push    1
0x10089b8d  push    ecx
0x10089b8e  push    offset dword_1000C084
0x10089b93  push    eax
0x10089b94  mov     ecx, edi
0x10089b96  call    _ErrQodefSeekSq@28; ErrQodefSeekSq(x,x,x,x,x,x,x)
0x10089b9b  mov     esi, eax
0x10089b9d  cmp     esi, 0FFFFF9BDh
0x10089ba3  jnz     short loc_10089BED
0x10089ba5  xor     eax, eax
0x10089ba7  push    eax; int
0x10089ba8  push    eax; int
0x10089ba9  push    eax; int
0x10089baa  push    0FFFFE010h; int
0x10089baf  push    eax; void *
0x10089bb0  push    eax; void *
0x10089bb1  push    [ebp+Src]; Src
0x10089bb4  push    dword ptr [edi]; int
0x10089bb6  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10089bbb  mov     esi, 0FFFFF405h
0x10089bc0  push    [ebp+var_8]
0x10089bc3  push    ebx
0x10089bc4  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10089bc9  lea     edx, [edi+8]
0x10089bcc  mov     ecx, ebx
0x10089bce  call    _CloseSysObjCursor@8; CloseSysObjCursor(x,x)
0x10089bd3  mov     ecx, edi
0x10089bd5  call    _QodefReleaseQodefvt@4; QodefReleaseQodefvt(x)
0x10089bda  mov     eax, [ebp+arg_C]
0x10089bdd  push    dword ptr [eax]
0x10089bdf  call    _ReleaseTableid@4; ReleaseTableid(x)
0x10089be4  mov     eax, esi
0x10089be6  pop     edi
0x10089be7  pop     esi
0x10089be8  pop     ebx
0x10089be9  leave
0x10089bea  retn    14h
0x10089bed  test    esi, esi
0x10089bef  js      short loc_10089BC0
0x10089bf1  push    0
0x10089bf3  push    1
0x10089bf5  push    [ebp+var_8]
0x10089bf8  push    ebx
0x10089bf9  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x10089bfe  mov     esi, eax
0x10089c00  test    esi, esi
0x10089c02  js      short loc_10089BC0
0x10089c04  xor     eax, eax
0x10089c06  push    eax
0x10089c07  push    eax
0x10089c08  push    eax
0x10089c09  push    1
0x10089c0b  lea     eax, [ebp+var_1]
0x10089c0e  push    eax
0x10089c0f  push    dword ptr [edi+20h]
0x10089c12  push    [ebp+var_8]
0x10089c15  push    ebx
0x10089c16  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x10089c1b  mov     esi, eax
0x10089c1d  test    esi, esi
0x10089c1f  js      short loc_10089BC0
0x10089c21  cmp     [ebp+var_1], 0FFh
0x10089c25  jnz     short loc_10089C3A
0x10089c27  push    0
0x10089c29  push    0FFFFFFFFh
0x10089c2b  push    [ebp+var_8]
0x10089c2e  push    ebx
0x10089c2f  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x10089c34  mov     esi, eax
0x10089c36  test    esi, esi
0x10089c38  js      short loc_10089BC0
0x10089c3a  mov     eax, [ebp+arg_C]
0x10089c3d  push    offset _vtfndefQodef
0x10089c42  push    edi
0x10089c43  push    dword ptr [eax]
0x10089c45  call    _ErrUpdateTableid@12; ErrUpdateTableid(x,x,x)
0x10089c4a  push    0
0x10089c4c  lea     eax, [ebp+var_C]
0x10089c4f  push    eax
0x10089c50  push    dword ptr [edi+10h]
0x10089c53  push    dword ptr [edi]
0x10089c55  call    _ErrDispDupCursor@16; ErrDispDupCursor(x,x,x,x)
0x10089c5a  mov     esi, eax
0x10089c5c  test    esi, esi
0x10089c5e  js      loc_10089BC0
0x10089c64  mov     eax, [ebp+var_C]
0x10089c67  push    offset _wszSqAttributeIndex; "ObjectIdAttribute"
0x10089c6c  mov     [edi+14h], eax
0x10089c6f  push    [ebp+var_C]
0x10089c72  push    dword ptr [edi]
0x10089c74  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10089c79  mov     esi, eax
0x10089c7b  test    esi, esi
0x10089c7d  jns     short loc_10089C94
0x10089c7f  push    [ebp+var_C]
0x10089c82  push    ebx
0x10089c83  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10089c88  mov     [ebp+var_C], 0FFFFFFFFh
0x10089c8f  jmp     loc_10089BC0
0x10089c94  xor     eax, eax
0x10089c96  jmp     loc_10089BE6
```
