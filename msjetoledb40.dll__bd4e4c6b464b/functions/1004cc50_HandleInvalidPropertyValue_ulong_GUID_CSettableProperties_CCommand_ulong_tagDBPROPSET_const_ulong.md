# HandleInvalidPropertyValue(ulong,_GUID,CSettableProperties &,CCommand *,ulong,tagDBPROPSET * const,ulong)

- ea: `0x1004cc50`
- end: `0x1004cd70`
- name: `?HandleInvalidPropertyValue@@YGJKU_GUID@@AAVCSettableProperties@@PAVCCommand@@KQAUtagDBPROPSET@@K@Z`
- size: `288`
- prototype: `int __stdcall(__int128, struct _GUID, struct CSettableProperties *, struct CCommand *, unsigned int, struct tagDBPROPSET *const, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1001d7f0`
- `0x10028340`
- `0x1002d600`

## callees

- `0x100148a0`
- `0x1001f2d0`
- `0x10020d20`
- `0x1004cc50`

## pseudocode

```c
HRESULT __userpurge HandleInvalidPropertyValue@<eax>(
        CSettableProperties *a1@<edx>,
        unsigned int a2@<ecx>,
        __int128 a3,
        struct _GUID a4,
        struct CSettableProperties *a5,
        struct CCommand *a6,
        unsigned int a7,
        struct tagDBPROPSET *const a8,
        unsigned int a9)
{
  struct JoltProperties *PropertySet; // eax
  struct JoltProperties *v11; // ecx
  struct _GUID v12; // xmm0
  const VARIANTARG *v13; // ecx
  int v15; // edi
  unsigned int v16; // eax
  __int128 *v17; // edx
  unsigned int v18; // esi
  _DWORD *v19; // ecx
  bool v20; // cf
  int v21; // eax
  int v22; // edx
  int v23; // ecx
  unsigned int v24; // [esp+8h] [ebp-20h] BYREF
  struct JoltProperties *v25; // [esp+Ch] [ebp-1Ch]
  int *v26; // [esp+10h] [ebp-18h]
  unsigned int v27; // [esp+14h] [ebp-14h]
  __int128 v28; // [esp+18h] [ebp-10h] BYREF

  v27 = a2;
  PropertySet = CSettableProperties::FindPropertySet(a1, (struct _GUID)a3);
  v11 = PropertySet;
  v25 = PropertySet;
  if ( !PropertySet )
    return -2147467259;
  if ( a4.Data1 )
  {
    v12 = *(struct _GUID *)((char *)PropertySet + 20);
    if ( JoltProperties::BinarySearch(PropertySet, a2, &v24) < 0 )
      v13 = 0;
    else
      v13 = (const VARIANTARG *)(*((_DWORD *)v25 + 4) + 48 * v24);
    return CCommand::CachePropertyInError((CCommand *)a4.Data1, v13, v12);
  }
  v15 = *(_DWORD *)&a4.Data2;
  if ( !*(_DWORD *)&a4.Data2 )
    return -2147467259;
  v16 = 0;
  v24 = 0;
  while ( 1 )
  {
    --v15;
    if ( v16 )
      return 0;
    v17 = &v28;
    v18 = 12;
    v28 = *(_OWORD *)((char *)v11 + 20);
    v26 = (int *)(*(_DWORD *)a4.Data4 + 24 * v15);
    v19 = v26 + 2;
    do
    {
      if ( *v19 != *(_DWORD *)v17 )
        goto LABEL_18;
      ++v19;
      v17 = (__int128 *)((char *)v17 + 4);
      v20 = v18 < 4;
      v18 -= 4;
    }
    while ( !v20 );
    v21 = v26[1];
    if ( !v21 )
    {
LABEL_18:
      v16 = v24;
      goto LABEL_19;
    }
    v22 = *v26;
    while ( 1 )
    {
      --v21;
      v23 = 52 * v21;
      if ( *(_DWORD *)(52 * v21 + v22) == v27 && !*(_DWORD *)(v23 + v22 + 8) )
        break;
      if ( !v21 )
        goto LABEL_18;
    }
    *(_DWORD *)(v23 + v22 + 8) = *(_DWORD *)&a4.Data4[4];
    v16 = 1;
    v24 = 1;
LABEL_19:
    if ( !v15 )
      return 0;
    v11 = v25;
  }
}

```

## disassembly

```asm
0x1004cc50  mov     edi, edi
0x1004cc52  push    ebp
0x1004cc53  mov     ebp, esp
0x1004cc55  and     esp, 0FFFFFFF0h
0x1004cc58  sub     esp, 28h
0x1004cc5b  movups  xmm0, [ebp+arg_0]
0x1004cc5f  push    esi
0x1004cc60  push    edi
0x1004cc61  sub     esp, 10h
0x1004cc64  mov     edi, ecx
0x1004cc66  mov     eax, esp
0x1004cc68  mov     [esp+40h+var_14], edi
0x1004cc6c  mov     ecx, edx; this
0x1004cc6e  movups  xmmword ptr [eax], xmm0
0x1004cc71  call    ?FindPropertySet@CSettableProperties@@QAEPAVJoltProperties@@U_GUID@@@Z; CSettableProperties::FindPropertySet(_GUID)
0x1004cc76  mov     ecx, eax; this
0x1004cc78  mov     [esp+30h+var_1C], ecx
0x1004cc7c  test    ecx, ecx
0x1004cc7e  jz      loc_1004CD63
0x1004cc84  mov     esi, [ebp+arg_10.Data1]
0x1004cc87  test    esi, esi
0x1004cc89  jz      short loc_1004CCCB
0x1004cc8b  movups  xmm0, xmmword ptr [ecx+14h]
0x1004cc8f  lea     eax, [esp+30h+var_20]
0x1004cc93  push    eax; struct JoltProperty *
0x1004cc94  push    edi; unsigned int
0x1004cc95  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1004cc9a  test    eax, eax
0x1004cc9c  js      short loc_1004CCB1
0x1004cc9e  mov     eax, [esp+30h+var_20]
0x1004cca2  lea     ecx, [eax+eax*2]
0x1004cca5  mov     eax, [esp+30h+var_1C]
0x1004cca9  shl     ecx, 4
0x1004ccac  add     ecx, [eax+10h]
0x1004ccaf  jmp     short loc_1004CCB3
0x1004ccb1  xor     ecx, ecx
0x1004ccb3  sub     esp, 10h
0x1004ccb6  mov     eax, esp
0x1004ccb8  push    ecx; struct _GUID
0x1004ccb9  mov     ecx, esi; this
0x1004ccbb  movups  xmmword ptr [eax], xmm0
0x1004ccbe  call    ?CachePropertyInError@CCommand@@QAEJU_GUID@@PAVJoltProperty@@@Z; CCommand::CachePropertyInError(_GUID,JoltProperty *)
0x1004ccc3  pop     edi
0x1004ccc4  pop     esi
0x1004ccc5  mov     esp, ebp
0x1004ccc7  pop     ebp
0x1004ccc8  retn    20h ; ' '
0x1004cccb  mov     edi, dword ptr [ebp+arg_10.Data2]
0x1004ccce  test    edi, edi
0x1004ccd0  jz      loc_1004CD63
0x1004ccd6  xor     eax, eax
0x1004ccd8  mov     [esp+30h+var_20], eax
0x1004ccdc  dec     edi
0x1004ccdd  test    eax, eax
0x1004ccdf  jnz     short loc_1004CD59
0x1004cce1  movups  xmm0, xmmword ptr [ecx+14h]
0x1004cce5  mov     ecx, dword ptr [ebp+arg_10.Data4]
0x1004cce8  lea     eax, [edi+edi*2]
0x1004cceb  lea     edx, [esp+30h+var_10]
0x1004ccef  mov     esi, 0Ch
0x1004ccf4  movups  [esp+30h+var_10], xmm0
0x1004ccf9  lea     eax, [ecx+eax*8]
0x1004ccfc  mov     [esp+30h+var_18], eax
0x1004cd00  lea     ecx, [eax+8]
0x1004cd03  mov     eax, [ecx]
0x1004cd05  cmp     eax, [edx]
0x1004cd07  jnz     short loc_1004CD39
0x1004cd09  add     ecx, 4
0x1004cd0c  add     edx, 4
0x1004cd0f  sub     esi, 4
0x1004cd12  jnb     short loc_1004CD03
0x1004cd14  mov     edx, [esp+30h+var_18]
0x1004cd18  mov     eax, [edx+4]
0x1004cd1b  test    eax, eax
0x1004cd1d  jz      short loc_1004CD39
0x1004cd1f  mov     edx, [edx]
0x1004cd21  mov     esi, [esp+30h+var_14]
0x1004cd25  dec     eax
0x1004cd26  imul    ecx, eax, 34h ; '4'
0x1004cd29  cmp     [ecx+edx], esi
0x1004cd2c  jnz     short loc_1004CD35
0x1004cd2e  cmp     dword ptr [ecx+edx+8], 0
0x1004cd33  jz      short loc_1004CD47
0x1004cd35  test    eax, eax
0x1004cd37  jnz     short loc_1004CD25
0x1004cd39  mov     eax, [esp+30h+var_20]
0x1004cd3d  test    edi, edi
0x1004cd3f  jz      short loc_1004CD59
0x1004cd41  mov     ecx, [esp+30h+var_1C]
0x1004cd45  jmp     short loc_1004CCDC
0x1004cd47  mov     eax, dword ptr [ebp+arg_10.Data4+4]
0x1004cd4a  mov     [ecx+edx+8], eax
0x1004cd4e  mov     eax, 1
0x1004cd53  mov     [esp+30h+var_20], eax
0x1004cd57  jmp     short loc_1004CD3D
0x1004cd59  xor     eax, eax
0x1004cd5b  pop     edi
0x1004cd5c  pop     esi
0x1004cd5d  mov     esp, ebp
0x1004cd5f  pop     ebp
0x1004cd60  retn    20h ; ' '
0x1004cd63  mov     eax, 80004005h
0x1004cd68  pop     edi
0x1004cd69  pop     esi
0x1004cd6a  mov     esp, ebp
0x1004cd6c  pop     ebp
0x1004cd6d  retn    20h ; ' '
```
