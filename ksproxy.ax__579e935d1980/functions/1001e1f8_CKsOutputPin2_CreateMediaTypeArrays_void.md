# CKsOutputPin2::CreateMediaTypeArrays(void)

- ea: `0x1001e1f8`
- end: `0x1001e4c0`
- name: `?CreateMediaTypeArrays@CKsOutputPin2@@QAEJXZ`
- size: `712`
- prototype: `int __thiscall(CKsOutputPin2 *__hidden this)`
- caller_count: `6`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1001b560`
- `0x1001b660`
- `0x1001bb90`
- `0x1001c490`
- `0x1001c6b0`
- `0x1001c710`

## callees

- `0x10017be0`
- `0x1001e1f8`
- `0x1001e4c6`
- `0x1001ff00`
- `0x100202e2`
- `0x1002d510`
- `0x100302a7`
- `0x1003a6f2`
- `0x1003a6fd`
- `0x1003a72c`
- `0x1003af9d`
- `0x1003b5e4`

## pseudocode

```c
int __thiscall CKsOutputPin2::CreateMediaTypeArrays(CKsOutputPin2 *this)
{
  _DWORD *v2; // esi
  int MediaTypeCount; // edi
  int v4; // edi
  void *v5; // eax
  unsigned int *v6; // esi
  void *v7; // ecx
  int v8; // eax
  _DWORD *v10; // ecx
  unsigned int v11; // edx
  union KSDATAFORMAT **v12; // edi
  void *v13; // eax
  void *v14; // eax
  int (__thiscall *v15)(_DWORD, _DWORD, _DWORD, _DWORD *, unsigned int); // ecx
  int (__thiscall *v16)(_DWORD, _DWORD, char *, char *, char *); // ecx
  int v17; // eax
  struct _AMMediaType *v18; // ecx
  _DWORD *v19; // eax
  void *v20; // edx
  void *v21; // [esp+14h] [ebp-20h]
  unsigned int v22; // [esp+18h] [ebp-1Ch]
  _DWORD *Block; // [esp+20h] [ebp-14h]
  int v24; // [esp+24h] [ebp-10h]
  int v25; // [esp+28h] [ebp-Ch]
  struct _AMMediaType *v26; // [esp+30h] [ebp-4h] BYREF

  v25 = 0;
  v2 = (_DWORD *)((char *)this + 808);
  if ( *((_DWORD *)this + 190) && !*v2 )
  {
    CKsOutputPin2::DestroyMediaTypeArrays(this);
    v4 = *((_DWORD *)this + 97);
    v5 = (void *)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)(*((_DWORD *)this + 10) + 108) + 12))(
                   *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 10) + 108) + 12),
                   *((_DWORD *)this + 10) + 108);
    v6 = (unsigned int *)((char *)this + 796);
    MediaTypeCount = KsGetMediaTypeCount(v5, v4, (_DWORD *)this + 199);
    if ( MediaTypeCount < 0 )
      goto LABEL_7;
    v7 = operator new[](saturated_mul(4u, *v6));
    *((_DWORD *)this + 198) = v7;
    if ( !v7 || (memset(v7, 0, 4 * *v6), v10 = operator new[](saturated_mul(4u, *v6)), (Block = v10) == 0) )
    {
      MediaTypeCount = -2147024882;
      goto LABEL_7;
    }
    memset(v10, 0, 4 * *v6);
    v11 = *v6;
    v24 = 0;
    if ( *v6 )
    {
      while ( 1 )
      {
        v12 = (union KSDATAFORMAT **)*((_DWORD *)this + 97);
        v13 = (void *)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)(*((_DWORD *)this + 10) + 108) + 12))(
                        *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 10) + 108) + 12),
                        *((_DWORD *)this + 10) + 108);
        MediaTypeCount = KsGetDriverMediaType((DWORD *)(4 * v24 + *((_DWORD *)this + 198)), v24, v13, v12, v21, v22);
        if ( MediaTypeCount < 0 )
          break;
        v14 = operator new(0x80u);
        Block[v24] = v14;
        if ( !v14 )
        {
          MediaTypeCount = -2147024882;
          break;
        }
        memset(v14, 0, 0x80u);
        v26 = 0;
        MediaTypeCount = CKsOutputPin::GetStreamCaps(
                           (CKsOutputPin *)((char *)this + 300),
                           v24,
                           &v26,
                           (unsigned __int8 *)Block[v24]);
        if ( MediaTypeCount < 0 && Block[v24] )
        {
          operator delete((void *)Block[v24]);
          Block[v24] = 0;
        }
        DeleteMediaType((void *)v26);
        v11 = *((_DWORD *)this + 199);
        if ( ++v24 >= v11 )
          goto LABEL_17;
      }
    }
    else
    {
LABEL_17:
      v15 = *(int (__thiscall **)(_DWORD, _DWORD, _DWORD, _DWORD *, unsigned int))(**((_DWORD **)this + 190) + 12);
      v25 = v15(v15, *((_DWORD *)this + 190), *((_DWORD *)this + 198), Block, v11);
      if ( v25 >= 0 )
      {
        v16 = *(int (__thiscall **)(_DWORD, _DWORD, char *, char *, char *))(**((_DWORD **)this + 190) + 20);
        v17 = v16(v16, *((_DWORD *)this + 190), (char *)this + 800, (char *)this + 804, (char *)this + 808);
        v25 = v17;
        v2 = (_DWORD *)((char *)this + 808);
        if ( v17 >= 0 )
        {
          if ( !*v2 )
            v17 = -2147467259;
          v25 = v17;
        }
LABEL_24:
        v18 = 0;
        v26 = 0;
        if ( *((_DWORD *)this + 199) )
        {
          v19 = Block;
          do
          {
            v20 = (void *)v19[(_DWORD)v18];
            if ( v20 )
            {
              operator delete(v20);
              v19 = Block;
              v18 = v26;
              Block[(_DWORD)v26] = 0;
            }
            v18 = (struct _AMMediaType *)((char *)v18 + 1);
            v26 = v18;
          }
          while ( (unsigned int)v18 < *((_DWORD *)this + 199) );
        }
        operator delete[](Block);
        if ( MediaTypeCount < 0 || v25 < 0 )
          goto LABEL_7;
        goto LABEL_31;
      }
    }
    v2 = (_DWORD *)((char *)this + 808);
    goto LABEL_24;
  }
  MediaTypeCount = 0;
LABEL_31:
  if ( *v2 && *((_DWORD *)this + 190) )
  {
    v8 = 1;
    goto LABEL_8;
  }
LABEL_7:
  CKsOutputPin2::DestroyMediaTypeArrays(this);
  v8 = 0;
LABEL_8:
  *((_DWORD *)this + 192) = v8;
  return MediaTypeCount;
}

```

## disassembly

```asm
0x1001e1f8  mov     edi, edi
0x1001e1fa  push    ebp
0x1001e1fb  mov     ebp, esp
0x1001e1fd  and     esp, 0FFFFFFF8h
0x1001e200  sub     esp, 14h
0x1001e203  push    ebx
0x1001e204  mov     ebx, ecx
0x1001e206  xor     eax, eax
0x1001e208  push    esi; unsigned int
0x1001e209  push    edi; struct _AMMediaType *
0x1001e20a  mov     [esp+20h+var_C], eax
0x1001e20e  lea     esi, [ebx+328h]
0x1001e214  cmp     [ebx+2F8h], eax
0x1001e21a  jnz     short loc_1001E223
0x1001e21c  mov     edi, eax
0x1001e21e  jmp     loc_1001E4A4
0x1001e223  cmp     [esi], eax
0x1001e225  ja      short loc_1001E21C
0x1001e227  call    ?DestroyMediaTypeArrays@CKsOutputPin2@@QAEXXZ; CKsOutputPin2::DestroyMediaTypeArrays(void)
0x1001e22c  mov     eax, [ebx+28h]
0x1001e22f  mov     edi, [ebx+184h]
0x1001e235  add     eax, 6Ch ; 'l'
0x1001e238  push    eax
0x1001e239  mov     ecx, [eax]
0x1001e23b  mov     esi, [ecx+0Ch]
0x1001e23e  mov     ecx, esi; this
0x1001e240  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001e246  call    esi
0x1001e248  lea     esi, [ebx+31Ch]
0x1001e24e  push    esi; int
0x1001e24f  push    edi; int
0x1001e250  push    eax; hDevice
0x1001e251  call    _KsGetMediaTypeCount@12; KsGetMediaTypeCount(x,x,x)
0x1001e256  mov     edi, eax
0x1001e258  test    edi, edi
0x1001e25a  js      short loc_1001E281
0x1001e25c  mov     eax, [esi]
0x1001e25e  push    4
0x1001e260  pop     ecx
0x1001e261  mul     ecx
0x1001e263  push    0FFFFFFFFh
0x1001e265  pop     ecx
0x1001e266  cmovb   eax, ecx
0x1001e269  push    eax; unsigned int
0x1001e26a  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1001e26f  pop     ecx
0x1001e270  mov     ecx, eax
0x1001e272  mov     [ebx+318h], ecx
0x1001e278  test    ecx, ecx
0x1001e27a  jnz     short loc_1001E299
0x1001e27c  mov     edi, 8007000Eh
0x1001e281  mov     ecx, ebx; this
0x1001e283  call    ?DestroyMediaTypeArrays@CKsOutputPin2@@QAEXXZ; CKsOutputPin2::DestroyMediaTypeArrays(void)
0x1001e288  xor     eax, eax
0x1001e28a  mov     [ebx+300h], eax
0x1001e290  mov     eax, edi
0x1001e292  pop     edi
0x1001e293  pop     esi
0x1001e294  pop     ebx
0x1001e295  mov     esp, ebp
0x1001e297  pop     ebp
0x1001e298  retn
0x1001e299  mov     eax, [esi]
0x1001e29b  shl     eax, 2
0x1001e29e  push    eax; Size
0x1001e29f  push    0; Val
0x1001e2a1  push    ecx; void *
0x1001e2a2  call    _memset
0x1001e2a7  mov     eax, [esi]
0x1001e2a9  add     esp, 0Ch
0x1001e2ac  push    4
0x1001e2ae  pop     ecx
0x1001e2af  mul     ecx
0x1001e2b1  push    0FFFFFFFFh
0x1001e2b3  pop     ecx
0x1001e2b4  cmovb   eax, ecx
0x1001e2b7  push    eax; unsigned int
0x1001e2b8  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1001e2bd  pop     ecx
0x1001e2be  mov     ecx, eax
0x1001e2c0  mov     [esp+20h+Block], ecx
0x1001e2c4  test    ecx, ecx
0x1001e2c6  jz      short loc_1001E27C
0x1001e2c8  mov     eax, [esi]
0x1001e2ca  shl     eax, 2
0x1001e2cd  push    eax; Size
0x1001e2ce  push    0; Val
0x1001e2d0  push    ecx; void *
0x1001e2d1  call    _memset
0x1001e2d6  mov     edx, [esi]
0x1001e2d8  add     esp, 0Ch
0x1001e2db  mov     [esp+20h+var_10], 0
0x1001e2e3  test    edx, edx
0x1001e2e5  jz      loc_1001E3C5
0x1001e2eb  mov     eax, [ebx+28h]
0x1001e2ee  mov     edi, [ebx+184h]
0x1001e2f4  add     eax, 6Ch ; 'l'
0x1001e2f7  push    eax
0x1001e2f8  mov     ecx, [eax]
0x1001e2fa  mov     esi, [ecx+0Ch]
0x1001e2fd  mov     ecx, esi; this
0x1001e2ff  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001e305  call    esi
0x1001e307  mov     ecx, [esp+20h+var_10]
0x1001e30b  mov     esi, ecx
0x1001e30d  mov     edx, [ebx+318h]
0x1001e313  shl     esi, 2
0x1001e316  push    edi; union KSDATAFORMAT **
0x1001e317  add     edx, esi
0x1001e319  mov     [esp+24h+var_8], esi
0x1001e31d  push    eax; hDevice
0x1001e31e  call    ?KsGetDriverMediaType@@YGJHPAPATKSDATAFORMAT@@PAXK@Z; KsGetDriverMediaType(int,KSDATAFORMAT * *,void *,ulong)
0x1001e323  mov     edi, eax
0x1001e325  test    edi, edi
0x1001e327  js      loc_1001E43D
0x1001e32d  push    80h; Size
0x1001e332  call    ??2@YAPAXI@Z; operator new(uint)
0x1001e337  mov     esi, [esp+24h+Block]
0x1001e33b  mov     edi, [esp+24h+var_8]
0x1001e33f  pop     ecx
0x1001e340  mov     [esi+edi], eax
0x1001e343  test    eax, eax
0x1001e345  jz      loc_1001E438
0x1001e34b  push    80h; Size
0x1001e350  push    0; Val
0x1001e352  push    eax; void *
0x1001e353  call    _memset
0x1001e358  add     esp, 0Ch
0x1001e35b  mov     [esp+20h+var_4], 0
0x1001e363  lea     eax, [esp+20h+var_4]
0x1001e367  push    dword ptr [esi+edi]; unsigned __int8 *
0x1001e36a  push    eax; struct _AMMediaType **
0x1001e36b  push    [esp+28h+var_10]; int
0x1001e36f  lea     eax, [ebx+12Ch]
0x1001e375  push    eax; this
0x1001e376  call    ?GetStreamCaps@CKsOutputPin@@UAGJHPAPAU_AMMediaType@@PAE@Z; CKsOutputPin::GetStreamCaps(int,_AMMediaType * *,uchar *)
0x1001e37b  mov     edi, eax
0x1001e37d  test    edi, edi
0x1001e37f  jns     short loc_1001E3A5
0x1001e381  mov     eax, [esp+20h+var_8]
0x1001e385  cmp     dword ptr [esi+eax], 0
0x1001e389  jz      short loc_1001E3A5
0x1001e38b  push    80h; unsigned int
0x1001e390  push    dword ptr [esi+eax]; Block
0x1001e393  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001e398  mov     eax, [esp+28h+var_8]
0x1001e39c  pop     ecx
0x1001e39d  pop     ecx
0x1001e39e  mov     dword ptr [esi+eax], 0
0x1001e3a5  mov     ecx, [esp+20h+var_4]
0x1001e3a9  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1001e3ae  mov     eax, [esp+20h+var_10]
0x1001e3b2  mov     edx, [ebx+31Ch]
0x1001e3b8  inc     eax
0x1001e3b9  mov     [esp+20h+var_10], eax
0x1001e3bd  cmp     eax, edx
0x1001e3bf  jb      loc_1001E2EB
0x1001e3c5  mov     ecx, [ebx+2F8h]
0x1001e3cb  push    edx
0x1001e3cc  push    [esp+24h+Block]
0x1001e3d0  mov     eax, [ecx]
0x1001e3d2  push    dword ptr [ebx+318h]
0x1001e3d8  push    ecx
0x1001e3d9  mov     esi, [eax+0Ch]
0x1001e3dc  mov     ecx, esi; this
0x1001e3de  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001e3e4  call    esi
0x1001e3e6  mov     [esp+20h+var_C], eax
0x1001e3ea  test    eax, eax
0x1001e3ec  js      short loc_1001E43D
0x1001e3ee  mov     ecx, [ebx+2F8h]
0x1001e3f4  mov     eax, [ecx]
0x1001e3f6  mov     esi, [eax+14h]
0x1001e3f9  lea     eax, [ebx+328h]
0x1001e3ff  push    eax
0x1001e400  lea     eax, [ebx+324h]
0x1001e406  push    eax
0x1001e407  lea     eax, [ebx+320h]
0x1001e40d  push    eax
0x1001e40e  push    ecx
0x1001e40f  mov     ecx, esi; this
0x1001e411  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001e417  call    esi
0x1001e419  mov     [esp+20h+var_C], eax
0x1001e41d  lea     esi, [ebx+328h]
0x1001e423  test    eax, eax
0x1001e425  js      short loc_1001E443
0x1001e427  cmp     dword ptr [esi], 0
0x1001e42a  mov     ecx, 80004005h
0x1001e42f  cmovz   eax, ecx
0x1001e432  mov     [esp+20h+var_C], eax
0x1001e436  jmp     short loc_1001E443
0x1001e438  mov     edi, 8007000Eh
0x1001e43d  lea     esi, [ebx+328h]
0x1001e443  xor     ecx, ecx
0x1001e445  mov     [esp+20h+var_4], ecx
0x1001e449  cmp     [ebx+31Ch], ecx
0x1001e44f  jbe     short loc_1001E485
0x1001e451  mov     eax, [esp+20h+Block]
0x1001e455  mov     edx, [eax+ecx*4]
0x1001e458  test    edx, edx
0x1001e45a  jz      short loc_1001E478
0x1001e45c  push    80h; unsigned int
0x1001e461  push    edx; Block
0x1001e462  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001e467  mov     eax, [esp+28h+Block]
0x1001e46b  pop     ecx
0x1001e46c  pop     ecx
0x1001e46d  mov     ecx, [esp+20h+var_4]
0x1001e471  mov     dword ptr [eax+ecx*4], 0
0x1001e478  inc     ecx
0x1001e479  mov     [esp+20h+var_4], ecx
0x1001e47d  cmp     ecx, [ebx+31Ch]
0x1001e483  jb      short loc_1001E455
0x1001e485  push    [esp+20h+Block]; Block
0x1001e489  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001e48e  pop     ecx
0x1001e48f  test    edi, edi
0x1001e491  js      loc_1001E281
0x1001e497  cmp     [esp+20h+var_C], 0
0x1001e49c  jl      loc_1001E281
0x1001e4a2  xor     eax, eax
0x1001e4a4  cmp     [esi], eax
0x1001e4a6  jbe     loc_1001E281
0x1001e4ac  cmp     [ebx+2F8h], eax
0x1001e4b2  jz      loc_1001E281
0x1001e4b8  xor     eax, eax
0x1001e4ba  inc     eax
0x1001e4bb  jmp     loc_1001E28A
```
