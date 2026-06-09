# ErrQodefOpenVtQoDef(x,x,x,x,x)

- ea: `0x10089800`
- end: `0x10089b0b`
- name: `_ErrQodefOpenVtQoDef@20`
- size: `779`
- prototype: `int __stdcall(int, int, void *Src, int, int)`
- caller_count: `7`
- callee_count: `21`
- tags: `authz_impersonation, installer_update`

## callers

- `0x100218e0`
- `0x100880a0`
- `0x1008c570`
- `0x1009fca7`
- `0x1009feb0`
- `0x100b5c3b`
- `0x100f4cb6`

## callees

- `0x1002a600`
- `0x1002a670`
- `0x1003e870`
- `0x10042ed0`
- `0x10043090`
- `0x10043660`
- `0x10043700`
- `0x10043840`
- `0x10043da0`
- `0x100448f0`
- `0x10044b90`
- `0x10044f50`
- `0x100451a0`
- `0x10045320`
- `0x100891ee`
- `0x10089800`
- `0x1008a9f8`
- `0x1008aa70`
- `0x1008b7ad`
- `0x1008b833`
- `0x10116991`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100898ca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100898ca`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10089894`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10089894`

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
                v14 = ErrQodefSeekSq(0, &dword_1000BFD4, v13, 1, 0);
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
0x10089800  mov     edi, edi
0x10089802  push    ebp
0x10089803  mov     ebp, esp
0x10089805  sub     esp, 10h
0x10089808  xor     eax, eax
0x1008980a  push    ebx
0x1008980b  mov     ebx, [ebp+arg_0]
0x1008980e  push    esi
0x1008980f  push    edi
0x10089810  push    eax
0x10089811  push    eax
0x10089812  push    [ebp+arg_C]
0x10089815  push    ebx
0x10089816  call    _ErrAllocateTableidForVSesid@16; ErrAllocateTableidForVSesid(x,x,x,x)
0x1008981b  test    eax, eax
0x1008981d  js      loc_10089A56
0x10089823  lea     ecx, [ebp+var_8]
0x10089826  call    _ErrQodefAllocQodefvt@4; ErrQodefAllocQodefvt(x)
0x1008982b  mov     esi, eax
0x1008982d  test    esi, esi
0x1008982f  js      loc_10089A4A
0x10089835  mov     edi, [ebp+var_8]
0x10089838  mov     ecx, [ebp+arg_4]
0x1008983b  mov     eax, [ebp+arg_10]
0x1008983e  mov     [edi], ebx
0x10089840  mov     [edi+4], ecx
0x10089843  mov     dword ptr [edi+3Ch], 1
0x1008984a  mov     [edi+48h], eax
0x1008984d  cmp     ecx, 0FFFFFFFFh
0x10089850  jz      short loc_10089892
0x10089852  mov     eax, [ebp+Src]
0x10089855  test    eax, eax
0x10089857  jz      short loc_10089892
0x10089859  xor     edx, edx
0x1008985b  cmp     [eax], dx
0x1008985e  jz      short loc_10089892
0x10089860  push    8
0x10089862  push    4
0x10089864  lea     eax, [ebp+var_8]
0x10089867  push    eax
0x10089868  push    ecx
0x10089869  push    ebx
0x1008986a  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1008986f  mov     esi, eax
0x10089871  test    esi, esi
0x10089873  js      loc_10089A56
0x10089879  cmp     [ebp+var_8], 10000h
0x10089880  jz      short loc_1008988B
0x10089882  cmp     [ebp+var_8], 10001h
0x10089889  jnz     short loc_10089892
0x1008988b  mov     dword ptr [edi+64h], 1
0x10089892  push    8; Size
0x10089894  call    ds:__imp__malloc
0x1008989a  mov     [edi+8], eax
0x1008989d  pop     ecx
0x1008989e  test    eax, eax
0x100898a0  jz      loc_10089A43
0x100898a6  mov     edx, [ebp+arg_4]
0x100898a9  lea     ecx, [edi+50h]
0x100898ac  push    ecx
0x100898ad  push    eax
0x100898ae  push    [ebp+Src]
0x100898b1  mov     ecx, ebx
0x100898b3  push    5
0x100898b5  call    _ErrGetObjInfoId@24; ErrGetObjInfoId(x,x,x,x,x,x)
0x100898ba  mov     esi, eax
0x100898bc  test    esi, esi
0x100898be  jns     short loc_100898DC
0x100898c0  lea     ebx, [edi+8]
0x100898c3  cmp     dword ptr [ebx], 0
0x100898c6  jz      short loc_100898D1
0x100898c8  push    dword ptr [ebx]; Block
0x100898ca  call    ds:__imp__free
0x100898d0  pop     ecx
0x100898d1  mov     dword ptr [ebx], 0
0x100898d7  jmp     loc_10089A43
0x100898dc  mov     eax, [edi+8]
0x100898df  lea     edx, [ebp+var_8]
0x100898e2  push    edx
0x100898e3  mov     [ebp+var_8], 4
0x100898ea  mov     ecx, ebx
0x100898ec  mov     dword ptr [eax+4], 1
0x100898f3  lea     eax, [edi+58h]
0x100898f6  mov     edx, [edi+8]
0x100898f9  push    eax
0x100898fa  push    offset _wszSoFlagsColumn; "Flags"
0x100898ff  mov     edx, [edx]
0x10089901  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x10089906  mov     esi, eax
0x10089908  test    esi, esi
0x1008990a  js      loc_10089A39
0x10089910  mov     eax, [edi+58h]
0x10089913  test    eax, 4000000h
0x10089918  jz      short loc_10089939
0x1008991a  xor     eax, eax
0x1008991c  push    eax; int
0x1008991d  push    eax; int
0x1008991e  push    eax; int
0x1008991f  push    0FFFFDDCEh; int
0x10089924  push    eax; void *
0x10089925  push    eax; void *
0x10089926  push    [ebp+Src]; Src
0x10089929  push    ebx; int
0x1008992a  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1008992f  mov     esi, 0FFFFF111h
0x10089934  jmp     loc_10089A39
0x10089939  mov     [edi+5Ch], eax
0x1008993c  and     eax, 18000000h
0x10089941  mov     [edi+60h], eax
0x10089944  mov     eax, [edi+8]
0x10089947  push    2
0x10089949  push    dword ptr [eax]
0x1008994b  push    ebx
0x1008994c  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x10089951  mov     esi, eax
0x10089953  cmp     esi, 0FFFFFBB2h
0x10089959  jz      short loc_1008997D
0x1008995b  cmp     esi, 0FFFFFBADh
0x10089961  jz      short loc_1008997D
0x10089963  cmp     esi, 0FFFFF8EFh
0x10089969  jnz     short loc_10089974
0x1008996b  mov     dword ptr [edi+44h], 1
0x10089972  jmp     short loc_10089984
0x10089974  test    esi, esi
0x10089976  jns     short loc_10089984
0x10089978  jmp     loc_10089A39
0x1008997d  mov     dword ptr [edi+40h], 1
0x10089984  mov     edx, [ebp+arg_4]
0x10089987  lea     eax, [ebp+var_8]
0x1008998a  push    eax
0x1008998b  mov     eax, [ebp+arg_C]
0x1008998e  mov     ecx, ebx
0x10089990  push    dword ptr [eax]
0x10089992  push    [ebp+Src]
0x10089995  call    _ErrREPOpenQuery@20; ErrREPOpenQuery(x,x,x,x,x)
0x1008999a  mov     esi, eax
0x1008999c  test    esi, esi
0x1008999e  js      loc_10089A39
0x100899a4  cmp     [ebp+var_8], 0
0x100899a8  jz      short loc_100899B1
0x100899aa  mov     dword ptr [edi+44h], 1
0x100899b1  push    80000000h
0x100899b6  push    offset _wszSqTable; "MSysQueries"
0x100899bb  lea     eax, [edi+10h]
0x100899be  push    eax
0x100899bf  push    [ebp+arg_4]
0x100899c2  push    ebx
0x100899c3  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x100899c8  mov     esi, eax
0x100899ca  test    esi, esi
0x100899cc  js      short loc_10089A39
0x100899ce  mov     eax, [edi+10h]
0x100899d1  mov     ecx, edi
0x100899d3  mov     [ebp+var_8], eax
0x100899d6  call    _ErrQodefGetColumnidsSq@4; ErrQodefGetColumnidsSq(x)
0x100899db  mov     esi, eax
0x100899dd  test    esi, esi
0x100899df  js      short loc_10089A30
0x100899e1  push    offset _wszSqAttributeIndex; "ObjectIdAttribute"
0x100899e6  push    [ebp+var_8]
0x100899e9  push    ebx
0x100899ea  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x100899ef  mov     esi, eax
0x100899f1  test    esi, esi
0x100899f3  js      short loc_10089A30
0x100899f5  mov     edx, [edi+50h]
0x100899f8  xor     eax, eax
0x100899fa  push    eax
0x100899fb  push    1
0x100899fd  push    ecx
0x100899fe  push    offset dword_1000BFD4
0x10089a03  push    eax
0x10089a04  mov     ecx, edi
0x10089a06  call    _ErrQodefSeekSq@28; ErrQodefSeekSq(x,x,x,x,x,x,x)
0x10089a0b  mov     esi, eax
0x10089a0d  cmp     esi, 0FFFFF9BDh
0x10089a13  jnz     short loc_10089A5D
0x10089a15  xor     eax, eax
0x10089a17  push    eax; int
0x10089a18  push    eax; int
0x10089a19  push    eax; int
0x10089a1a  push    0FFFFE010h; int
0x10089a1f  push    eax; void *
0x10089a20  push    eax; void *
0x10089a21  push    [ebp+Src]; Src
0x10089a24  push    dword ptr [edi]; int
0x10089a26  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10089a2b  mov     esi, 0FFFFF405h
0x10089a30  push    [ebp+var_8]
0x10089a33  push    ebx
0x10089a34  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10089a39  lea     edx, [edi+8]
0x10089a3c  mov     ecx, ebx
0x10089a3e  call    _CloseSysObjCursor@8; CloseSysObjCursor(x,x)
0x10089a43  mov     ecx, edi
0x10089a45  call    _QodefReleaseQodefvt@4; QodefReleaseQodefvt(x)
0x10089a4a  mov     eax, [ebp+arg_C]
0x10089a4d  push    dword ptr [eax]
0x10089a4f  call    _ReleaseTableid@4; ReleaseTableid(x)
0x10089a54  mov     eax, esi
0x10089a56  pop     edi
0x10089a57  pop     esi
0x10089a58  pop     ebx
0x10089a59  leave
0x10089a5a  retn    14h
0x10089a5d  test    esi, esi
0x10089a5f  js      short loc_10089A30
0x10089a61  push    0
0x10089a63  push    1
0x10089a65  push    [ebp+var_8]
0x10089a68  push    ebx
0x10089a69  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x10089a6e  mov     esi, eax
0x10089a70  test    esi, esi
0x10089a72  js      short loc_10089A30
0x10089a74  xor     eax, eax
0x10089a76  push    eax
0x10089a77  push    eax
0x10089a78  push    eax
0x10089a79  push    1
0x10089a7b  lea     eax, [ebp+var_1]
0x10089a7e  push    eax
0x10089a7f  push    dword ptr [edi+20h]
0x10089a82  push    [ebp+var_8]
0x10089a85  push    ebx
0x10089a86  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x10089a8b  mov     esi, eax
0x10089a8d  test    esi, esi
0x10089a8f  js      short loc_10089A30
0x10089a91  cmp     [ebp+var_1], 0FFh
0x10089a95  jnz     short loc_10089AAA
0x10089a97  push    0
0x10089a99  push    0FFFFFFFFh
0x10089a9b  push    [ebp+var_8]
0x10089a9e  push    ebx
0x10089a9f  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x10089aa4  mov     esi, eax
0x10089aa6  test    esi, esi
0x10089aa8  js      short loc_10089A30
0x10089aaa  mov     eax, [ebp+arg_C]
0x10089aad  push    offset _vtfndefQodef
0x10089ab2  push    edi
0x10089ab3  push    dword ptr [eax]
0x10089ab5  call    _ErrUpdateTableid@12; ErrUpdateTableid(x,x,x)
0x10089aba  push    0
0x10089abc  lea     eax, [ebp+var_C]
0x10089abf  push    eax
0x10089ac0  push    dword ptr [edi+10h]
0x10089ac3  push    dword ptr [edi]
0x10089ac5  call    _ErrDispDupCursor@16; ErrDispDupCursor(x,x,x,x)
0x10089aca  mov     esi, eax
0x10089acc  test    esi, esi
0x10089ace  js      loc_10089A30
0x10089ad4  mov     eax, [ebp+var_C]
0x10089ad7  push    offset _wszSqAttributeIndex; "ObjectIdAttribute"
0x10089adc  mov     [edi+14h], eax
0x10089adf  push    [ebp+var_C]
0x10089ae2  push    dword ptr [edi]
0x10089ae4  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10089ae9  mov     esi, eax
0x10089aeb  test    esi, esi
0x10089aed  jns     short loc_10089B04
0x10089aef  push    [ebp+var_C]
0x10089af2  push    ebx
0x10089af3  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10089af8  mov     [ebp+var_C], 0FFFFFFFFh
0x10089aff  jmp     loc_10089A30
0x10089b04  xor     eax, eax
0x10089b06  jmp     loc_10089A56
```
