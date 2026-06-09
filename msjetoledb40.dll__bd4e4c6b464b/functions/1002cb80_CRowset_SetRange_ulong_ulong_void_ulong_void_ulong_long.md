# CRowset::SetRange(ulong,ulong,void *,ulong,void *,ulong,long &)

- ea: `0x1002cb80`
- end: `0x1002cf8b`
- name: `?SetRange@CRowset@@IAGJKKPAXK0KAAJ@Z`
- size: `1035`
- prototype: `int(CRowset *__hidden this, unsigned int, unsigned int, void *, unsigned int, void *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1002f820`

## callees

- `0x1001bdc0`
- `0x1001c380`
- `0x1002c690`
- `0x1002cb80`
- `0x1002cfb0`

## import_xrefs

- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1002cf69`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1002cf69`
- `msjet40!__imp__JetMakeKey@20` at `0x1002cd38`
- `msjet40!__imp__JetMakeKey@20` at `0x1002ce01`
- `msjet40!__imp__JetMakeKey@20` at `0x1002cd38`
- `msjet40!__imp__JetMakeKey@20` at `0x1002ce01`
- `msjet40!__imp__JetMove@16` at `0x1002cecf`
- `msjet40!__imp__JetMove@16` at `0x1002cecf`
- `msjet40!__imp__JetSetIndexRange@12` at `0x1002cbc6`
- `msjet40!__imp__JetSetIndexRange@12` at `0x1002cc8e`
- `msjet40!__imp__JetSetIndexRange@12` at `0x1002cd56`
- `msjet40!__imp__JetSetIndexRange@12` at `0x1002ceaf`
- `msjet40!__imp__JetSetIndexRange@12` at `0x1002cbc6`
- `msjet40!__imp__JetSetIndexRange@12` at `0x1002cc8e`
- `msjet40!__imp__JetSetIndexRange@12` at `0x1002cd56`
- `msjet40!__imp__JetSetIndexRange@12` at `0x1002ceaf`

## pseudocode

```c
int __userpurge CRowset::SetRange@<eax>(
        int a1@<edx>,
        _DWORD *a2@<ecx>,
        CRowset *this,
        unsigned int a4,
        unsigned int a5,
        void *a6,
        unsigned int a7,
        unsigned int *a8,
        unsigned int a9,
        int *a10)
{
  unsigned int *v10; // ebx
  unsigned int v12; // ecx
  int Key; // esi
  bool v14; // zf
  JET_SESID v15; // eax
  JET_ERR v16; // eax
  CRowset *v17; // edx
  JET_GRBIT v18; // eax
  JET_ERR v19; // eax
  unsigned int v20; // ebx
  JET_ERR v21; // eax
  JET_ERR v22; // eax
  char v23; // cl
  JET_ERR v24; // eax
  JET_ERR v25; // eax
  char v26; // al
  int v27; // eax
  JET_GRBIT v28; // eax
  JET_ERR v29; // eax
  struct _GUID *v31; // [esp+0h] [ebp-28h]
  const struct _GUID *v32; // [esp+4h] [ebp-24h]
  unsigned int v33; // [esp+Ch] [ebp-1Ch] BYREF
  int v34; // [esp+10h] [ebp-18h]
  int v35; // [esp+14h] [ebp-14h]
  JET_GRBIT grbit; // [esp+18h] [ebp-10h]
  JET_SESID sesid; // [esp+1Ch] [ebp-Ch]
  int v38; // [esp+20h] [ebp-8h] BYREF
  int v39; // [esp+24h] [ebp-4h]

  v10 = a8;
  v34 = a1;
  v12 = a7;
  Key = 0;
  v38 = 0;
  v39 = 0;
  v14 = a2[29] == 4;
  v15 = *(_DWORD *)(a2[14] + 16);
  sesid = v15;
  if ( v14 )
  {
    Key = 265926;
    goto LABEL_72;
  }
  if ( a2[51] == 1 )
  {
    v16 = JetSetIndexRange(v15, a2[27], 0x10u);
    *a8 = v16;
    if ( v16 < 0 )
    {
      Key = -2147467259;
      goto LABEL_72;
    }
    v12 = a7;
    a2[51] = 0;
  }
  v17 = this;
  if ( (v12 & 8) != 0 && this )
  {
    v12 = a7;
    if ( ((1 << ((_BYTE)this - 1)) & a2[50]) != 0 )
    {
      Key = 1;
      v39 = 1;
    }
  }
  else
  {
    v39 = 0;
    if ( !this )
    {
      v33 = v12 & 4;
      v39 = 0;
      if ( (v12 & 4) != 0 )
      {
        v20 = 1;
        v39 = 0;
        if ( a5 )
          v20 = a5;
        v35 = v20;
        v14 = v20 == 0;
        v10 = a8;
        if ( !v14 )
        {
          v39 = 0;
          if ( ((1 << (v35 - 1)) & a2[50]) == 0 )
          {
            if ( a5 > 1 )
            {
              Key = CRowset::MakeKey(a2, v34, a5, a6, 0, 1, a7, &v38, a8);
              if ( Key < 0 )
                goto LABEL_72;
            }
            v21 = JetMakeKey(sesid, a2[27], 0, 0, a5 <= 1);
            *a8 = v21;
            if ( v21 )
            {
              Key = -2147467259;
              goto LABEL_72;
            }
            v22 = JetSetIndexRange(sesid, a2[27], 8u);
            *a8 = v22;
            v39 = 0;
            if ( v22 < 0 )
            {
              Key = -2147467259;
              goto LABEL_72;
            }
            v17 = 0;
          }
          v12 = a7;
        }
      }
      goto LABEL_37;
    }
  }
  if ( (v12 & 0x18) != 0 )
    grbit = 9;
  else
    grbit = ((v12 & 1) == 0) + 8;
  Key = CRowset::MakeKey(a2, v34, this, a4, Key, 0, v12, &v38, a8);
  if ( Key < 0 )
    goto LABEL_72;
  if ( v38 == 1 && (a7 & 4) != 0 )
  {
    v18 = grbit;
    if ( ((1 << ((_BYTE)this - 1)) & a2[50]) == 0 )
      v18 = grbit & 0xFFFFFFFE;
  }
  else
  {
    v18 = grbit;
  }
  v19 = JetSetIndexRange(sesid, a2[27], v18);
  *a8 = v19;
  if ( v19 < 0 )
  {
    Key = -2147467259;
    goto LABEL_72;
  }
  v12 = a7;
  v17 = this;
  v33 = a7 & 4;
LABEL_37:
  v35 = v12 & 0x18;
  if ( a5 || v35 )
  {
    if ( (v12 & 2) != 0 )
    {
      grbit = 4;
      if ( !v35 )
        goto LABEL_51;
    }
    else
    {
      grbit = 5;
      if ( !v35 )
      {
LABEL_51:
        v26 = a5;
        if ( !a5 )
        {
LABEL_54:
          if ( Key < 0 )
            goto LABEL_72;
          if ( v38 == 1 && v33 )
          {
            v14 = ((1 << (v26 - 1)) & a2[50]) == 0;
            v28 = grbit;
            if ( !v14 )
              v28 = grbit & 0xFFFFFFFE;
          }
          else
          {
            v28 = grbit;
          }
          v25 = JetSetIndexRange(sesid, a2[27], v28);
LABEL_63:
          *v10 = v25;
          if ( v25 < 0 )
          {
LABEL_64:
            Key = -2147467259;
            goto LABEL_72;
          }
          goto LABEL_65;
        }
        v27 = CRowset::MakeKey(a2, v34, a5, a6, 0, 0, 0, &v38, v10);
LABEL_53:
        Key = v27;
        v26 = a5;
        goto LABEL_54;
      }
    }
    v27 = CRowset::MakeKey(a2, v34, v17, a4, v39 ^ 1, 0, v12, &v38, v10);
    goto LABEL_53;
  }
  if ( v33 )
  {
    v23 = 1;
    if ( v17 )
      v23 = (char)v17;
    if ( ((1 << (v23 - 1)) & a2[50]) != 0 )
    {
      if ( (unsigned int)v17 > 1 )
      {
        Key = CRowset::MakeKey(a2, v34, v17, a4, 0, 1, 0, &v38, v10);
        if ( Key < 0 )
          goto LABEL_72;
        v17 = this;
      }
      v24 = JetMakeKey(sesid, a2[27], 0, 0, (unsigned int)v17 <= 1);
      *v10 = v24;
      if ( v24 )
      {
        Key = -2147467259;
        goto LABEL_72;
      }
      v25 = JetSetIndexRange(sesid, a2[27], 4u);
      goto LABEL_63;
    }
  }
LABEL_65:
  v29 = JetMove(sesid, a2[27], 0x80000000, 0);
  *v10 = v29;
  if ( v29 == -1603 )
  {
    a2[24] |= 0x200u;
    a2[31] = -1;
  }
  else if ( v29 < 0 )
  {
    goto LABEL_64;
  }
  if ( *v10 == -1603
    || (Key = CRowset::GetCurrentBookmark((CRowset *)0xFFFFFFFF, &v31->Data1, (unsigned int)v32), Key >= 0) )
  {
    *v10 = 0;
    a2[32] = 0;
    a2[51] = 1;
  }
LABEL_72:
  if ( *v10 )
  {
    CExtError::SendJetErrortoOLEAuto(Key, *(char **)(a2[14] + 16), *v10, (int)&IID_IRowsetIndex, (int)v31, v32);
    return Key;
  }
  else
  {
    if ( Key < 0
      && Key != -2147024882
      && !JetGetDatabaseInfo(*(_DWORD *)(a2[14] + 16), *(_DWORD *)(a2[14] + 20), &v33, 4, 3) )
    {
      CExtError::SendHRtoOLEAuto(Key, (__int128 *)&IID_IRowsetIndex, 0, v31, (int)v32);
    }
    return Key;
  }
}

```

## disassembly

```asm
0x1002cb80  mov     edi, edi
0x1002cb82  push    ebp
0x1002cb83  mov     ebp, esp
0x1002cb85  sub     esp, 1Ch
0x1002cb88  push    ebx
0x1002cb89  mov     ebx, [ebp+arg_14]
0x1002cb8c  push    esi; int
0x1002cb8d  push    edi; struct _GUID *
0x1002cb8e  mov     edi, ecx
0x1002cb90  mov     [ebp+var_18], edx
0x1002cb93  mov     ecx, [ebp+arg_10]
0x1002cb96  xor     esi, esi
0x1002cb98  mov     [ebp+var_8], esi
0x1002cb9b  mov     [ebp+var_4], esi
0x1002cb9e  cmp     dword ptr [edi+74h], 4
0x1002cba2  mov     eax, [edi+38h]
0x1002cba5  mov     eax, [eax+10h]
0x1002cba8  mov     [ebp+sesid], eax
0x1002cbab  jnz     short loc_1002CBB7
0x1002cbad  mov     esi, 40EC6h
0x1002cbb2  jmp     loc_1002CF28
0x1002cbb7  cmp     dword ptr [edi+0CCh], 1
0x1002cbbe  jnz     short loc_1002CBE5
0x1002cbc0  push    10h; grbit
0x1002cbc2  push    dword ptr [edi+6Ch]; tableidSrc
0x1002cbc5  push    eax; sesid
0x1002cbc6  call    ds:__imp__JetSetIndexRange@12; JetSetIndexRange(x,x,x)
0x1002cbcc  mov     [ebx], eax
0x1002cbce  test    eax, eax
0x1002cbd0  jns     short loc_1002CBDC
0x1002cbd2  mov     esi, 80004005h
0x1002cbd7  jmp     loc_1002CF28
0x1002cbdc  mov     ecx, [ebp+arg_10]
0x1002cbdf  mov     [edi+0CCh], esi
0x1002cbe5  mov     edx, [ebp+this]
0x1002cbe8  mov     eax, 1
0x1002cbed  test    cl, 8
0x1002cbf0  jz      short loc_1002CC10
0x1002cbf2  test    edx, edx
0x1002cbf4  jz      short loc_1002CC10
0x1002cbf6  lea     ecx, [edx-1]
0x1002cbf9  shl     eax, cl
0x1002cbfb  mov     ecx, [ebp+arg_10]
0x1002cbfe  test    [edi+0C8h], eax
0x1002cc04  jz      short loc_1002CC1B
0x1002cc06  mov     esi, 1
0x1002cc0b  mov     [ebp+var_4], esi
0x1002cc0e  jmp     short loc_1002CC1B
0x1002cc10  mov     [ebp+var_4], esi
0x1002cc13  test    edx, edx
0x1002cc15  jz      loc_1002CCB7
0x1002cc1b  test    ecx, 18h
0x1002cc21  jz      short loc_1002CC2C
0x1002cc23  mov     [ebp+grbit], 9
0x1002cc2a  jmp     short loc_1002CC39
0x1002cc2c  mov     eax, ecx
0x1002cc2e  not     eax
0x1002cc30  and     eax, 1
0x1002cc33  add     eax, 8
0x1002cc36  mov     [ebp+grbit], eax
0x1002cc39  push    ebx
0x1002cc3a  lea     eax, [ebp+var_8]
0x1002cc3d  push    eax
0x1002cc3e  push    ecx
0x1002cc3f  push    0
0x1002cc41  push    esi
0x1002cc42  push    [ebp+arg_4]
0x1002cc45  mov     ecx, edi
0x1002cc47  push    edx
0x1002cc48  mov     edx, [ebp+var_18]
0x1002cc4b  call    ?MakeKey@CRowset@@AAGJKKPAXHW4eKeyForm@1@KAAHAAJ@Z; CRowset::MakeKey(ulong,ulong,void *,int,CRowset::eKeyForm,ulong,int &,long &)
0x1002cc50  mov     esi, eax
0x1002cc52  test    esi, esi
0x1002cc54  js      loc_1002CF28
0x1002cc5a  cmp     [ebp+var_8], 1
0x1002cc5e  jnz     short loc_1002CC84
0x1002cc60  test    [ebp+arg_10], 4
0x1002cc67  jz      short loc_1002CC84
0x1002cc69  mov     ecx, [ebp+this]
0x1002cc6c  mov     eax, 1
0x1002cc71  dec     ecx
0x1002cc72  shl     eax, cl
0x1002cc74  test    [edi+0C8h], eax
0x1002cc7a  mov     eax, [ebp+grbit]
0x1002cc7d  jnz     short loc_1002CC87
0x1002cc7f  and     eax, 0FFFFFFFEh
0x1002cc82  jmp     short loc_1002CC87
0x1002cc84  mov     eax, [ebp+grbit]
0x1002cc87  push    eax; grbit
0x1002cc88  push    dword ptr [edi+6Ch]; tableidSrc
0x1002cc8b  push    [ebp+sesid]; sesid
0x1002cc8e  call    ds:__imp__JetSetIndexRange@12; JetSetIndexRange(x,x,x)
0x1002cc94  mov     [ebx], eax
0x1002cc96  test    eax, eax
0x1002cc98  jns     short loc_1002CCA4
0x1002cc9a  mov     esi, 80004005h
0x1002cc9f  jmp     loc_1002CF28
0x1002cca4  mov     ecx, [ebp+arg_10]
0x1002cca7  mov     eax, ecx
0x1002cca9  mov     edx, [ebp+this]
0x1002ccac  and     eax, 4
0x1002ccaf  mov     [ebp+var_1C], eax
0x1002ccb2  jmp     loc_1002CD79
0x1002ccb7  mov     [ebp+var_1C], ecx
0x1002ccba  and     [ebp+var_1C], 4
0x1002ccbe  mov     [ebp+var_4], esi
0x1002ccc1  jz      loc_1002CD7E
0x1002ccc7  cmp     [ebp+arg_8], esi
0x1002ccca  mov     ebx, eax
0x1002cccc  mov     [ebp+var_4], esi
0x1002cccf  cmovnz  ebx, [ebp+arg_8]
0x1002ccd3  mov     [ebp+var_14], ebx
0x1002ccd6  test    ebx, ebx
0x1002ccd8  mov     ebx, [ebp+arg_14]
0x1002ccdb  jz      loc_1002CD7E
0x1002cce1  mov     ecx, [ebp+var_14]
0x1002cce4  dec     ecx
0x1002cce5  mov     [ebp+var_4], esi
0x1002cce8  shl     eax, cl
0x1002ccea  test    [edi+0C8h], eax
0x1002ccf0  jnz     loc_1002CD76
0x1002ccf6  mov     eax, [ebp+arg_8]
0x1002ccf9  cmp     eax, 1
0x1002ccfc  jbe     short loc_1002CD22
0x1002ccfe  mov     edx, [ebp+var_18]
0x1002cd01  lea     ecx, [ebp+var_8]
0x1002cd04  push    ebx
0x1002cd05  push    ecx
0x1002cd06  push    [ebp+arg_10]
0x1002cd09  mov     ecx, edi
0x1002cd0b  push    1
0x1002cd0d  push    0
0x1002cd0f  push    [ebp+arg_C]
0x1002cd12  push    eax
0x1002cd13  call    ?MakeKey@CRowset@@AAGJKKPAXHW4eKeyForm@1@KAAHAAJ@Z; CRowset::MakeKey(ulong,ulong,void *,int,CRowset::eKeyForm,ulong,int &,long &)
0x1002cd18  mov     esi, eax
0x1002cd1a  test    esi, esi
0x1002cd1c  js      loc_1002CF28
0x1002cd22  mov     eax, 1
0x1002cd27  cmp     eax, [ebp+arg_8]
0x1002cd2a  sbb     eax, eax
0x1002cd2c  inc     eax
0x1002cd2d  push    eax; grbit
0x1002cd2e  push    0; cbData
0x1002cd30  push    0; pvData
0x1002cd32  push    dword ptr [edi+6Ch]; tableid
0x1002cd35  push    [ebp+sesid]; sesid
0x1002cd38  call    ds:__imp__JetMakeKey@20; JetMakeKey(x,x,x,x,x)
0x1002cd3e  mov     [ebx], eax
0x1002cd40  test    eax, eax
0x1002cd42  jz      short loc_1002CD4E
0x1002cd44  mov     esi, 80004005h
0x1002cd49  jmp     loc_1002CF28
0x1002cd4e  push    8; grbit
0x1002cd50  push    dword ptr [edi+6Ch]; tableidSrc
0x1002cd53  push    [ebp+sesid]; sesid
0x1002cd56  call    ds:__imp__JetSetIndexRange@12; JetSetIndexRange(x,x,x)
0x1002cd5c  mov     [ebx], eax
0x1002cd5e  mov     [ebp+var_4], 0
0x1002cd65  test    eax, eax
0x1002cd67  jns     short loc_1002CD73
0x1002cd69  mov     esi, 80004005h
0x1002cd6e  jmp     loc_1002CF28
0x1002cd73  mov     edx, [ebp+this]
0x1002cd76  mov     ecx, [ebp+arg_10]
0x1002cd79  mov     eax, 1
0x1002cd7e  mov     [ebp+var_14], ecx
0x1002cd81  and     [ebp+var_14], 18h
0x1002cd85  cmp     [ebp+arg_8], 0
0x1002cd89  jnz     loc_1002CE1E
0x1002cd8f  cmp     [ebp+var_14], 0
0x1002cd93  jnz     loc_1002CE1E
0x1002cd99  cmp     [ebp+var_1C], 0
0x1002cd9d  jz      loc_1002CEC2
0x1002cda3  test    edx, edx
0x1002cda5  mov     ecx, eax
0x1002cda7  cmovnz  ecx, edx
0x1002cdaa  test    ecx, ecx
0x1002cdac  jz      loc_1002CEC2
0x1002cdb2  dec     ecx
0x1002cdb3  shl     eax, cl
0x1002cdb5  test    [edi+0C8h], eax
0x1002cdbb  jz      loc_1002CEC2
0x1002cdc1  cmp     edx, 1
0x1002cdc4  jbe     short loc_1002CDEC
0x1002cdc6  push    ebx
0x1002cdc7  lea     eax, [ebp+var_8]
0x1002cdca  mov     ecx, edi
0x1002cdcc  push    eax
0x1002cdcd  push    0
0x1002cdcf  push    1
0x1002cdd1  push    0
0x1002cdd3  push    [ebp+arg_4]
0x1002cdd6  push    edx
0x1002cdd7  mov     edx, [ebp+var_18]
0x1002cdda  call    ?MakeKey@CRowset@@AAGJKKPAXHW4eKeyForm@1@KAAHAAJ@Z; CRowset::MakeKey(ulong,ulong,void *,int,CRowset::eKeyForm,ulong,int &,long &)
0x1002cddf  mov     esi, eax
0x1002cde1  test    esi, esi
0x1002cde3  js      loc_1002CF28
0x1002cde9  mov     edx, [ebp+this]
0x1002cdec  mov     eax, 1
0x1002cdf1  cmp     eax, edx
0x1002cdf3  sbb     eax, eax
0x1002cdf5  inc     eax
0x1002cdf6  push    eax; grbit
0x1002cdf7  push    0; cbData
0x1002cdf9  push    0; pvData
0x1002cdfb  push    dword ptr [edi+6Ch]; tableid
0x1002cdfe  push    [ebp+sesid]; sesid
0x1002ce01  call    ds:__imp__JetMakeKey@20; JetMakeKey(x,x,x,x,x)
0x1002ce07  mov     [ebx], eax
0x1002ce09  test    eax, eax
0x1002ce0b  jz      short loc_1002CE17
0x1002ce0d  mov     esi, 80004005h
0x1002ce12  jmp     loc_1002CF28
0x1002ce17  push    4
0x1002ce19  jmp     loc_1002CEA9
0x1002ce1e  test    cl, 2
0x1002ce21  jnz     short loc_1002CE83
0x1002ce23  cmp     [ebp+var_14], 0
0x1002ce27  mov     [ebp+grbit], 5
0x1002ce2e  jnz     short loc_1002CE90
0x1002ce30  mov     eax, [ebp+arg_8]
0x1002ce33  test    eax, eax
0x1002ce35  jz      short loc_1002CE55
0x1002ce37  push    ebx
0x1002ce38  lea     ecx, [ebp+var_8]
0x1002ce3b  push    ecx
0x1002ce3c  push    0
0x1002ce3e  push    0
0x1002ce40  push    0
0x1002ce42  push    [ebp+arg_C]
0x1002ce45  push    eax
0x1002ce46  mov     edx, [ebp+var_18]
0x1002ce49  mov     ecx, edi
0x1002ce4b  call    ?MakeKey@CRowset@@AAGJKKPAXHW4eKeyForm@1@KAAHAAJ@Z; CRowset::MakeKey(ulong,ulong,void *,int,CRowset::eKeyForm,ulong,int &,long &)
0x1002ce50  mov     esi, eax
0x1002ce52  mov     eax, [ebp+arg_8]
0x1002ce55  test    esi, esi
0x1002ce57  js      loc_1002CF28
0x1002ce5d  cmp     [ebp+var_8], 1
0x1002ce61  jnz     short loc_1002CEA5
0x1002ce63  cmp     [ebp+var_1C], 0
0x1002ce67  jz      short loc_1002CEA5
0x1002ce69  lea     ecx, [eax-1]
0x1002ce6c  mov     eax, 1
0x1002ce71  shl     eax, cl
0x1002ce73  test    [edi+0C8h], eax
0x1002ce79  mov     eax, [ebp+grbit]
0x1002ce7c  jz      short loc_1002CEA8
0x1002ce7e  and     eax, 0FFFFFFFEh
0x1002ce81  jmp     short loc_1002CEA8
0x1002ce83  cmp     [ebp+var_14], 0
0x1002ce87  mov     [ebp+grbit], 4
0x1002ce8e  jz      short loc_1002CE30
0x1002ce90  push    ebx
0x1002ce91  lea     eax, [ebp+var_8]
0x1002ce94  push    eax
0x1002ce95  mov     eax, [ebp+var_4]
0x1002ce98  push    ecx
0x1002ce99  push    0
0x1002ce9b  xor     eax, 1
0x1002ce9e  push    eax
0x1002ce9f  push    [ebp+arg_4]
0x1002cea2  push    edx
0x1002cea3  jmp     short loc_1002CE46
0x1002cea5  mov     eax, [ebp+grbit]
0x1002cea8  push    eax; grbit
0x1002cea9  push    dword ptr [edi+6Ch]; tableidSrc
0x1002ceac  push    [ebp+sesid]; sesid
0x1002ceaf  call    ds:__imp__JetSetIndexRange@12; JetSetIndexRange(x,x,x)
0x1002ceb5  mov     [ebx], eax
0x1002ceb7  test    eax, eax
0x1002ceb9  jns     short loc_1002CEC2
0x1002cebb  mov     esi, 80004005h
0x1002cec0  jmp     short loc_1002CF28
0x1002cec2  push    0; grbit
0x1002cec4  push    80000000h; cRow
0x1002cec9  push    dword ptr [edi+6Ch]; tableid
0x1002cecc  push    [ebp+sesid]; sesid
0x1002cecf  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1002ced5  mov     [ebx], eax
0x1002ced7  cmp     eax, 0FFFFF9BDh
0x1002cedc  jz      short loc_1002CEE7
0x1002cede  test    eax, eax
0x1002cee0  js      short loc_1002CEBB
0x1002cee2  lea     edx, [edi+7Ch]
0x1002cee5  jmp     short loc_1002CEF7
0x1002cee7  or      dword ptr [edi+60h], 200h
0x1002ceee  lea     edx, [edi+7Ch]
0x1002cef1  mov     dword ptr [edx], 0FFFFFFFFh
0x1002cef7  cmp     dword ptr [ebx], 0FFFFF9BDh
0x1002cefd  jz      short loc_1002CF0E
0x1002ceff  push    0FFFFFFFFh; this
0x1002cf01  mov     ecx, edi
0x1002cf03  call    ?GetCurrentBookmark@CRowset@@IAGJPAKK@Z; CRowset::GetCurrentBookmark(ulong *,ulong)
0x1002cf08  mov     esi, eax
0x1002cf0a  test    esi, esi
0x1002cf0c  js      short loc_1002CF28
0x1002cf0e  mov     dword ptr [ebx], 0
  ... truncated ...
```
