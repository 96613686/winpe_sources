# CJetParameterList::GetJetParameterInfo(ulong,JET_COLUMNLIST &)

- ea: `0x1004ab50`
- end: `0x1004ae6a`
- name: `?GetJetParameterInfo@CJetParameterList@@QAEJKAAUJET_COLUMNLIST@@@Z`
- size: `794`
- prototype: `int __thiscall(CJetParameterList *__hidden this, unsigned int, struct JET_COLUMNLIST *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x10010b50`

## callees

- `0x1000d4a0`
- `0x10049740`
- `0x1004ab50`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x1004ae43`
- `msjet40!__imp__JetCloseTable@8` at `0x1004ae43`
- `msjet40!__imp__JetMove@16` at `0x1004ae06`
- `msjet40!__imp__JetMove@16` at `0x1004ae06`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004ac2f`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004ad13`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004ad66`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004ac2f`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004ad13`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004ad66`

## pseudocode

```c
int __thiscall CJetParameterList::GetJetParameterInfo(void **this, JET_SESID sesid, struct JET_COLUMNLIST *a3)
{
  void **v3; // edx
  int inserted; // edi
  unsigned int v5; // ecx
  void *v6; // esi
  JET_ERR v7; // eax
  unsigned __int16 *v8; // eax
  int v9; // eax
  JET_ERR v10; // eax
  int v11; // eax
  int v12; // eax
  __int16 v13; // ax
  JET_COLUMNID columnidLangid; // [esp-18h] [ebp-83Ch]
  const unsigned __int16 *v16; // [esp+0h] [ebp-824h]
  unsigned int v17; // [esp+4h] [ebp-820h]
  int v19; // [esp+10h] [ebp-814h]
  unsigned int v20; // [esp+14h] [ebp-810h]
  int v21; // [esp+18h] [ebp-80Ch] BYREF
  unsigned __int16 *v22; // [esp+1Ch] [ebp-808h]
  unsigned int pcbActual; // [esp+20h] [ebp-804h] BYREF
  unsigned __int16 pvData[1022]; // [esp+24h] [ebp-800h] BYREF

  v3 = this;
  inserted = 0;
  if ( a3->cRecord )
  {
    v5 = 0;
    v20 = 0;
    while ( 1 )
    {
      v6 = *v3;
      v19 = 0;
      if ( *v3 )
      {
        while ( *(_DWORD *)v6 != v5 + 1 )
        {
          v6 = (void *)*((_DWORD *)v6 + 10);
          if ( !v6 )
            goto LABEL_6;
        }
        inserted = 0;
        if ( *((_DWORD *)v6 + 2) == 1 )
          *((_DWORD *)v6 + 2) = 2;
      }
      else
      {
LABEL_6:
        inserted = 0;
        v6 = operator new(0x2Cu);
        v22 = (unsigned __int16 *)v6;
        if ( !v6 )
          return -2147024882;
        *((_DWORD *)v6 + 1) = 0;
        *((_DWORD *)v6 + 2) = 0;
        *((_DWORD *)v6 + 5) = 0xFFFF;
        *((_DWORD *)v6 + 6) = 0;
        *((_WORD *)v6 + 14) = 0;
        *((_DWORD *)v6 + 8) = 0;
        *((_DWORD *)v6 + 10) = 0;
        v19 = 1;
        *(_DWORD *)v6 = v20 + 1;
        *((_DWORD *)v6 + 2) = 0;
      }
      *((_DWORD *)v6 + 4) = 65;
      v7 = JetRetrieveColumn(sesid, a3->tableid, a3->columnidcolumnname, pvData, 0x7FCu, &pcbActual, 0, 0);
      if ( v7 )
      {
        if ( v7 != 1004 )
          return -2147467259;
        if ( *((_DWORD *)v6 + 1) )
        {
          operator delete(*((void **)v6 + 1));
          *((_DWORD *)v6 + 1) = 0;
        }
        inserted = 0;
      }
      else
      {
        if ( (pcbActual & 0xFFFFFFFE) >= 0x7FC )
          __report_rangecheckfailure();
        *(unsigned __int16 *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
        if ( *((_DWORD *)v6 + 1) )
        {
          operator delete(*((void **)v6 + 1));
          *((_DWORD *)v6 + 1) = 0;
        }
        v22 = (unsigned __int16 *)(wcslen(pvData) + 1);
        v8 = (unsigned __int16 *)operator new(saturated_mul(2u, (unsigned int)v22));
        *((_DWORD *)v6 + 1) = v8;
        if ( v8 )
          WCSCPY(pvData, v8, v22, v16, v17);
      }
      if ( JetRetrieveColumn(sesid, a3->tableid, a3->columnidcoltyp, &v21, 4u, 0, 0, 0) )
        return -2147467259;
      v9 = v21;
      *((_DWORD *)v6 + 8) = v21;
      *((_WORD *)v6 + 14) = word_100510F0[4 * v21];
      columnidLangid = a3->columnidLangid;
      v22 = (unsigned __int16 *)(v9 == 0);
      v10 = JetRetrieveColumn(sesid, a3->tableid, columnidLangid, &pcbActual, 4u, 0, 0, 0);
      if ( v10 )
      {
        if ( v10 != 1004 )
          return -2147467259;
      }
      if ( v22 == (unsigned __int16 *)1 )
      {
        v11 = 510;
        pcbActual = 510;
      }
      else if ( v10 == 1004 )
      {
        v11 = dword_10051944[2 * v21];
        pcbActual = v11;
      }
      else
      {
        v11 = pcbActual;
      }
      *((_DWORD *)v6 + 9) = v11;
      v12 = *((_DWORD *)v6 + 2);
      if ( v12 == 1 || v12 == 2 )
      {
        v13 = *((_WORD *)v6 + 11);
      }
      else
      {
        if ( v12 )
          goto LABEL_35;
        v13 = *((_WORD *)v6 + 14);
      }
      if ( v13 == 131 )
        *((_WORD *)v6 + 10) = 2588;
LABEL_35:
      if ( v19 == 1 )
      {
        inserted = CJetParameterList::InsertParameter((CJetParameterList *)this, (struct CJetParameter *)v6);
        if ( inserted < 0 )
          return inserted;
      }
      JetMove(sesid, a3->tableid, 1, 0);
      v5 = v20 + 1;
      v20 = v5;
      if ( v5 >= a3->cRecord )
        break;
      v3 = this;
    }
  }
  if ( a3->tableid != -1 )
  {
    JetCloseTable(sesid, a3->tableid);
    a3->tableid = -1;
  }
  return inserted;
}

```

## disassembly

```asm
0x1004ab50  mov     edi, edi
0x1004ab52  push    ebp
0x1004ab53  mov     ebp, esp
0x1004ab55  sub     esp, 818h
0x1004ab5b  mov     eax, ___security_cookie
0x1004ab60  xor     eax, ebp
0x1004ab62  mov     [ebp+var_4], eax
0x1004ab65  push    ebx
0x1004ab66  mov     ebx, [ebp+arg_4]
0x1004ab69  mov     edx, ecx
0x1004ab6b  push    esi; unsigned int
0x1004ab6c  push    edi; unsigned __int16 *
0x1004ab6d  xor     edi, edi
0x1004ab6f  mov     [ebp+var_818], edx
0x1004ab75  mov     eax, [ebx+8]
0x1004ab78  test    eax, eax
0x1004ab7a  jz      loc_1004AE37
0x1004ab80  xor     ecx, ecx
0x1004ab82  mov     [ebp+var_810], ecx
0x1004ab88  test    eax, eax
0x1004ab8a  jz      loc_1004AE37
0x1004ab90  mov     esi, [edx]
0x1004ab92  mov     [ebp+var_814], 0
0x1004ab9c  test    esi, esi
0x1004ab9e  jz      short loc_1004ABB2
0x1004aba0  lea     eax, [ecx+1]
0x1004aba3  cmp     [esi], eax
0x1004aba5  jz      loc_1004AC62
0x1004abab  mov     esi, [esi+28h]
0x1004abae  test    esi, esi
0x1004abb0  jnz     short loc_1004ABA3
0x1004abb2  push    2Ch ; ','; Size
0x1004abb4  xor     edi, edi
0x1004abb6  call    ??2@YAPAXI@Z; operator new(uint)
0x1004abbb  mov     esi, eax
0x1004abbd  add     esp, 4
0x1004abc0  mov     [ebp+var_808], esi
0x1004abc6  test    esi, esi
0x1004abc8  jz      loc_1004AE30
0x1004abce  xor     eax, eax
0x1004abd0  mov     [esi+4], edi
0x1004abd3  mov     [esi+8], edi
0x1004abd6  mov     dword ptr [esi+14h], 0FFFFh
0x1004abdd  mov     [esi+18h], edi
0x1004abe0  mov     [esi+1Ch], ax
0x1004abe4  mov     [esi+20h], eax
0x1004abe7  mov     [esi+28h], eax
0x1004abea  test    esi, esi
0x1004abec  jz      loc_1004AE30
0x1004abf2  mov     eax, [ebp+var_810]
0x1004abf8  inc     eax
0x1004abf9  mov     [ebp+var_814], 1
0x1004ac03  mov     [esi], eax
0x1004ac05  mov     [esi+8], edi
0x1004ac08  push    0; pretinfo
0x1004ac0a  push    0; grbit
0x1004ac0c  lea     eax, [ebp+pcbActual]
0x1004ac12  mov     dword ptr [esi+10h], 41h ; 'A'
0x1004ac19  push    eax; pcbActual
0x1004ac1a  push    7FCh; cbData
0x1004ac1f  lea     eax, [ebp+pvData]
0x1004ac25  push    eax; pvData
0x1004ac26  push    dword ptr [ebx+10h]; columnid
0x1004ac29  push    dword ptr [ebx+4]; tableid
0x1004ac2c  push    [ebp+sesid]; sesid
0x1004ac2f  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1004ac35  test    eax, eax
0x1004ac37  jz      short loc_1004AC73
0x1004ac39  cmp     eax, 3ECh
0x1004ac3e  jnz     loc_1004AE29
0x1004ac44  mov     eax, [esi+4]
0x1004ac47  test    eax, eax
0x1004ac49  jz      short loc_1004AC5B
0x1004ac4b  push    eax; Block
0x1004ac4c  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004ac51  add     esp, 4
0x1004ac54  mov     dword ptr [esi+4], 0
0x1004ac5b  xor     edi, edi
0x1004ac5d  jmp     loc_1004ACFB
0x1004ac62  xor     edi, edi
0x1004ac64  cmp     dword ptr [esi+8], 1
0x1004ac68  jnz     short loc_1004AC08
0x1004ac6a  mov     dword ptr [esi+8], 2
0x1004ac71  jmp     short loc_1004AC08
0x1004ac73  mov     eax, [ebp+pcbActual]
0x1004ac79  and     eax, 0FFFFFFFEh
0x1004ac7c  cmp     eax, 7FCh
0x1004ac81  jnb     loc_1004AE65
0x1004ac87  xor     ecx, ecx
0x1004ac89  mov     [ebp+eax+pvData], cx
0x1004ac91  mov     eax, [esi+4]
0x1004ac94  test    eax, eax
0x1004ac96  jz      short loc_1004ACA8
0x1004ac98  push    eax; Block
0x1004ac99  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004ac9e  add     esp, 4
0x1004aca1  mov     dword ptr [esi+4], 0
0x1004aca8  lea     ecx, [ebp+pvData]
0x1004acae  lea     edx, [ecx+2]
0x1004acb1  mov     ax, [ecx]
0x1004acb4  add     ecx, 2
0x1004acb7  test    ax, ax
0x1004acba  jnz     short loc_1004ACB1
0x1004acbc  sub     ecx, edx
0x1004acbe  sar     ecx, 1
0x1004acc0  lea     eax, [ecx+1]
0x1004acc3  mov     ecx, 2
0x1004acc8  mov     [ebp+var_808], eax
0x1004acce  mul     ecx
0x1004acd0  mov     ecx, 0FFFFFFFFh
0x1004acd5  cmovb   eax, ecx
0x1004acd8  push    eax; Size
0x1004acd9  call    ??2@YAPAXI@Z; operator new(uint)
0x1004acde  add     esp, 4
0x1004ace1  mov     [esi+4], eax
0x1004ace4  test    eax, eax
0x1004ace6  jz      short loc_1004ACFB
0x1004ace8  push    [ebp+var_808]; unsigned __int16 *
0x1004acee  lea     edx, [ebp+pvData]
0x1004acf4  mov     ecx, eax
0x1004acf6  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x1004acfb  push    0; pretinfo
0x1004acfd  push    0; grbit
0x1004acff  push    0; pcbActual
0x1004ad01  push    4; cbData
0x1004ad03  lea     eax, [ebp+var_80C]
0x1004ad09  push    eax; pvData
0x1004ad0a  push    dword ptr [ebx+18h]; columnid
0x1004ad0d  push    dword ptr [ebx+4]; tableid
0x1004ad10  push    [ebp+sesid]; sesid
0x1004ad13  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1004ad19  test    eax, eax
0x1004ad1b  jnz     loc_1004AE29
0x1004ad21  mov     eax, [ebp+var_80C]
0x1004ad27  xor     ecx, ecx
0x1004ad29  mov     [esi+20h], eax
0x1004ad2c  test    eax, eax
0x1004ad2e  mov     eax, [ebp+var_80C]
0x1004ad34  mov     edx, 1
0x1004ad39  push    0; pretinfo
0x1004ad3b  push    0; grbit
0x1004ad3d  push    0; pcbActual
0x1004ad3f  mov     ax, word_100510F0[eax*8]
0x1004ad47  cmovz   ecx, edx
0x1004ad4a  mov     [esi+1Ch], ax
0x1004ad4e  lea     eax, [ebp+pcbActual]
0x1004ad54  push    4; cbData
0x1004ad56  push    eax; pvData
0x1004ad57  push    dword ptr [ebx+20h]; columnid
0x1004ad5a  mov     [ebp+var_808], ecx
0x1004ad60  push    dword ptr [ebx+4]; tableid
0x1004ad63  push    [ebp+sesid]; sesid
0x1004ad66  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1004ad6c  test    eax, eax
0x1004ad6e  jz      short loc_1004AD7B
0x1004ad70  cmp     eax, 3ECh
0x1004ad75  jnz     loc_1004AE29
0x1004ad7b  cmp     [ebp+var_808], 1
0x1004ad82  jnz     short loc_1004AD91
0x1004ad84  mov     eax, 1FEh
0x1004ad89  mov     [ebp+pcbActual], eax
0x1004ad8f  jmp     short loc_1004ADB3
0x1004ad91  cmp     eax, 3ECh
0x1004ad96  jnz     short loc_1004ADAD
0x1004ad98  mov     eax, [ebp+var_80C]
0x1004ad9e  mov     eax, dword_10051944[eax*8]
0x1004ada5  mov     [ebp+pcbActual], eax
0x1004adab  jmp     short loc_1004ADB3
0x1004adad  mov     eax, [ebp+pcbActual]
0x1004adb3  mov     [esi+24h], eax
0x1004adb6  mov     eax, [esi+8]
0x1004adb9  cmp     eax, 1
0x1004adbc  jz      short loc_1004ADCD
0x1004adbe  cmp     eax, 2
0x1004adc1  jz      short loc_1004ADCD
0x1004adc3  test    eax, eax
0x1004adc5  jnz     short loc_1004ADE1
0x1004adc7  movzx   eax, word ptr [esi+1Ch]
0x1004adcb  jmp     short loc_1004ADD1
0x1004adcd  movzx   eax, word ptr [esi+16h]
0x1004add1  mov     ecx, 83h
0x1004add6  cmp     cx, ax
0x1004add9  jnz     short loc_1004ADE1
0x1004addb  mov     word ptr [esi+14h], 0A1Ch
0x1004ade1  cmp     [ebp+var_814], 1
0x1004ade8  jnz     short loc_1004ADFC
0x1004adea  mov     ecx, [ebp+var_818]; this
0x1004adf0  push    esi; struct CJetParameter *
0x1004adf1  call    ?InsertParameter@CJetParameterList@@AAEJPAVCJetParameter@@@Z; CJetParameterList::InsertParameter(CJetParameter *)
0x1004adf6  mov     edi, eax
0x1004adf8  test    edi, edi
0x1004adfa  js      short loc_1004AE50
0x1004adfc  push    0; grbit
0x1004adfe  push    1; cRow
0x1004ae00  push    dword ptr [ebx+4]; tableid
0x1004ae03  push    [ebp+sesid]; sesid
0x1004ae06  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1004ae0c  mov     ecx, [ebp+var_810]
0x1004ae12  inc     ecx
0x1004ae13  mov     [ebp+var_810], ecx
0x1004ae19  cmp     ecx, [ebx+8]
0x1004ae1c  jnb     short loc_1004AE37
0x1004ae1e  mov     edx, [ebp+var_818]
0x1004ae24  jmp     loc_1004AB90
0x1004ae29  mov     edi, 80004005h
0x1004ae2e  jmp     short loc_1004AE50
0x1004ae30  mov     edi, 8007000Eh
0x1004ae35  jmp     short loc_1004AE50
0x1004ae37  mov     eax, [ebx+4]
0x1004ae3a  cmp     eax, 0FFFFFFFFh
0x1004ae3d  jz      short loc_1004AE50
0x1004ae3f  push    eax; tableid
0x1004ae40  push    [ebp+sesid]; sesid
0x1004ae43  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x1004ae49  mov     dword ptr [ebx+4], 0FFFFFFFFh
0x1004ae50  mov     ecx, [ebp+var_4]
0x1004ae53  mov     eax, edi
0x1004ae55  pop     edi
0x1004ae56  pop     esi
0x1004ae57  xor     ecx, ebp; StackCookie
0x1004ae59  pop     ebx
0x1004ae5a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004ae5f  mov     esp, ebp
0x1004ae61  pop     ebp
0x1004ae62  retn    8
0x1004ae65  call    ___report_rangecheckfailure
```
