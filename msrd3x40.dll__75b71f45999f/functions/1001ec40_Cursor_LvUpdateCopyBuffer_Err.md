# Cursor::LvUpdateCopyBuffer(Err &)

- ea: `0x1001ec40`
- end: `0x1001efd5`
- name: `?LvUpdateCopyBuffer@Cursor@@AAEXAAVErr@@@Z`
- size: `917`
- prototype: `void __thiscall(Cursor *__hidden this, struct Err *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x1001aaa0`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x1001ec40`
- `0x1003cc10`
- `0x1003ee10`
- `0x1003f460`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Cursor::LvUpdateCopyBuffer(Cursor *this, void **a2)
{
  Cursor *v2; // edi
  void **v3; // esi
  struct tagColParams *v4; // ebx
  unsigned int v5; // edx
  int v6; // eax
  int v7; // ecx
  LongValue *v8; // eax
  int v9; // ecx
  int v10; // edx
  unsigned int v11; // edi
  int v12; // ebx
  LongValue *v13; // eax
  unsigned int v14; // ecx
  LongValue *v15; // esi
  LongValue *v16; // edi
  _DWORD *v17; // eax
  int v18; // [esp-Ch] [ebp-60h]
  int v19; // [esp-8h] [ebp-5Ch]
  unsigned int v20[3]; // [esp+10h] [ebp-44h] BYREF
  void *Block; // [esp+1Ch] [ebp-38h]
  void *v22; // [esp+20h] [ebp-34h]
  _DWORD v23[3]; // [esp+24h] [ebp-30h] BYREF
  void *v24; // [esp+30h] [ebp-24h]
  void *v25; // [esp+34h] [ebp-20h]
  struct tagColParams *v26; // [esp+38h] [ebp-1Ch]
  LongValue *v27; // [esp+3Ch] [ebp-18h]
  unsigned int v28; // [esp+40h] [ebp-14h]
  Cursor *v29; // [esp+44h] [ebp-10h]
  int v30; // [esp+50h] [ebp-4h]

  v2 = this;
  v29 = this;
  v3 = a2;
  v4 = (Cursor *)((char *)this + 96);
  v5 = 0;
  *((_DWORD *)this + 24) = *((_DWORD *)this + 13);
  v26 = (Cursor *)((char *)this + 96);
  while ( (*(_BYTE *)v3 & 8) == 0 )
  {
    if ( v5 >= *((_DWORD *)v2 + 89) )
      break;
    v6 = *((_DWORD *)v2 + 87);
    v7 = v5++;
    v28 = v5;
    v8 = *(LongValue **)(v6 + 4 * v7);
    v27 = v8;
    if ( !v8 )
      break;
    if ( *(_DWORD *)(*((_DWORD *)v8 + 1) + 2084) )
    {
      LvDataNew::SetupFinalLocation(v18, v19, v3);
      if ( (*(_BYTE *)v3 & 8) == 0 )
      {
        LongValue::SaveRecordData(v27, v4);
        LongValue::UpdateCopyBuffer(v27, v4, (struct Err *)v3);
      }
      if ( (*(_BYTE *)v3 & 1) == 0 && v3[1] == (void *)-1026 )
      {
        v9 = 1;
        v23[0] = 1;
        v30 = 0;
        while ( 1 )
        {
          v10 = *((_DWORD *)v2 + 3);
          v11 = *(_DWORD *)(v10 + 368);
          if ( v11 == -1 )
          {
LABEL_24:
            v16 = v27;
LABEL_25:
            v3 = a2;
            goto LABEL_26;
          }
          while ( 1 )
          {
            v20[0] = 1;
            LOBYTE(v30) = 1;
            v12 = v11 > 0xFE ? 0 : *(_DWORD *)(v10 + 4 * v11 + 376);
            v13 = (LongValue *)(*(int (__thiscall **)(int, struct tagColParams *, unsigned int *))(*(_DWORD *)v12 + 48))(
                                 v12,
                                 v26,
                                 v20);
            v14 = v20[0];
            v15 = v13;
            if ( v13 )
            {
              v4 = v26;
              if ( (v20[0] & 8) == 0 )
              {
                LongValue::SaveRecordData(v13, v26);
                LongValue::UpdateCopyBuffer(v15, v4, (struct Err *)v20);
                v14 = v20[0];
                if ( (v20[0] & 8) == 0 )
                  break;
              }
            }
            LOBYTE(v30) = 0;
            if ( (v14 & 0xFFFFFFFE) != 0 )
            {
              if ( Block )
                operator delete[](Block);
              if ( v22 )
                operator delete[](v22);
            }
            v10 = *((_DWORD *)v29 + 3);
            v11 = *(_DWORD *)(*(_DWORD *)(v10 + 360) + 8 * v11);
            if ( v11 == -1 )
            {
              v9 = v23[0];
              v4 = v26;
              goto LABEL_24;
            }
          }
          LOBYTE(v30) = 0;
          if ( (v20[0] & 0xFFFFFFFE) != 0 )
          {
            if ( Block )
              operator delete[](Block);
            if ( v22 )
              operator delete[](v22);
          }
          v16 = v27;
          LongValue::UpdateCopyBuffer(v27, v4, (struct Err *)v23);
          v9 = v23[0];
          if ( (v23[0] & 8) == 0 )
            break;
          if ( (v23[0] & 1) != 0 || v23[1] != -1026 )
            goto LABEL_25;
          if ( (v23[0] & 0xFFFFFFFE) != 0 )
          {
            if ( v24 )
              operator delete[](v24);
            if ( v25 )
              operator delete[](v25);
          }
          v2 = v29;
          v9 = 1;
          v23[0] = 1;
        }
        v3 = a2;
        if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
        {
          if ( a2[3] )
          {
            operator delete[](a2[3]);
            v9 = v23[0];
          }
          if ( a2[4] )
          {
            operator delete[](a2[4]);
            v9 = v23[0];
          }
        }
        *a2 = (void *)1;
LABEL_26:
        if ( (*(_BYTE *)v3 & 1) == 0 && v3[1] == (void *)-1026 && !*(_DWORD *)(*((_DWORD *)v16 + 1) + 2052) )
        {
          if ( (v9 & 0xFFFFFFFE) != 0 )
          {
            if ( v24 )
              operator delete[](v24);
            if ( v25 )
              operator delete[](v25);
          }
          v17 = (_DWORD *)*((_DWORD *)v16 + 1);
          v9 = 1;
          v23[0] = 1;
          if ( v17[521] )
          {
            if ( !v17[513] && !v17[520] )
            {
              if ( v17[516] )
              {
                v17[513] = 1;
                v17[521] = 1;
                v9 = v23[0];
                if ( (v23[0] & 8) == 0 )
                {
                  LongValue::UpdateCopyBuffer(v16, v4, (struct Err *)v23);
                  v9 = v23[0];
                  if ( (v23[0] & 8) == 0 )
                  {
                    if ( ((unsigned int)*v3 & 0xFFFFFFFE) != 0 )
                    {
                      if ( v3[3] )
                      {
                        operator delete[](v3[3]);
                        v9 = v23[0];
                      }
                      if ( v3[4] )
                      {
                        operator delete[](v3[4]);
                        v9 = v23[0];
                      }
                    }
                    *v3 = (void *)1;
                  }
                }
              }
            }
          }
        }
        v30 = -1;
        if ( (v9 & 0xFFFFFFFE) != 0 )
        {
          if ( v24 )
            operator delete[](v24);
          if ( v25 )
            operator delete[](v25);
        }
        v2 = v29;
      }
      v5 = v28;
    }
  }
}

```

## disassembly

```asm
0x1001ec40  mov     edi, edi
0x1001ec42  push    ebp
0x1001ec43  mov     ebp, esp
0x1001ec45  push    0FFFFFFFFh
0x1001ec47  push    offset ?LvUpdateCopyBuffer@Cursor@@AAEXAAVErr@@@Z_SEH
0x1001ec4c  mov     eax, large fs:0
0x1001ec52  push    eax
0x1001ec53  sub     esp, 38h
0x1001ec56  push    ebx
0x1001ec57  push    esi
0x1001ec58  push    edi
0x1001ec59  mov     eax, ___security_cookie
0x1001ec5e  xor     eax, ebp
0x1001ec60  push    eax
0x1001ec61  lea     eax, [ebp+var_C]
0x1001ec64  mov     large fs:0, eax
0x1001ec6a  mov     edi, ecx
0x1001ec6c  mov     [ebp+var_10], edi
0x1001ec6f  mov     esi, [ebp+arg_0]
0x1001ec72  lea     ebx, [edi+60h]
0x1001ec75  mov     eax, [edi+34h]
0x1001ec78  xor     edx, edx
0x1001ec7a  mov     [ebx], eax
0x1001ec7c  mov     [ebp+var_1C], ebx
0x1001ec7f  test    byte ptr [esi], 8
0x1001ec82  jnz     loc_1001EEF4
0x1001ec88  nop     dword ptr [eax+eax+00000000h]
0x1001ec90  cmp     edx, [edi+164h]
0x1001ec96  jnb     loc_1001EEF4
0x1001ec9c  mov     eax, [edi+15Ch]
0x1001eca2  mov     ecx, edx
0x1001eca4  inc     edx
0x1001eca5  mov     [ebp+var_14], edx
0x1001eca8  mov     eax, [eax+ecx*4]
0x1001ecab  mov     [ebp+var_18], eax
0x1001ecae  test    eax, eax
0x1001ecb0  jz      loc_1001EEF4
0x1001ecb6  mov     ecx, [eax+4]
0x1001ecb9  cmp     dword ptr [ecx+824h], 0
0x1001ecc0  jz      loc_1001EEEB
0x1001ecc6  push    esi
0x1001ecc7  sub     esp, 8
0x1001ecca  call    ?SetupFinalLocation@LvDataNew@@QAEXPAUtagColParams@@W4LvLocation@@AAVErr@@@Z; LvDataNew::SetupFinalLocation(tagColParams *,LvLocation,Err &)
0x1001eccf  test    byte ptr [esi], 8
0x1001ecd2  jnz     short loc_1001ECE7
0x1001ecd4  mov     ecx, [ebp+var_18]; this
0x1001ecd7  push    ebx; struct tagColParams *
0x1001ecd8  call    ?SaveRecordData@LongValue@@QAEXPAUtagColParams@@@Z; LongValue::SaveRecordData(tagColParams *)
0x1001ecdd  mov     ecx, [ebp+var_18]; this
0x1001ece0  push    esi; struct Err *
0x1001ece1  push    ebx; struct tagColParams *
0x1001ece2  call    ?UpdateCopyBuffer@LongValue@@QAEXPAUtagColParams@@AAVErr@@@Z; LongValue::UpdateCopyBuffer(tagColParams *,Err &)
0x1001ece7  test    byte ptr [esi], 1
0x1001ecea  jnz     loc_1001EEE8
0x1001ecf0  cmp     dword ptr [esi+4], 0FFFFFBFEh
0x1001ecf7  jnz     loc_1001EEE8
0x1001ecfd  mov     ecx, 1
0x1001ed02  mov     [ebp+var_30], ecx
0x1001ed05  mov     [ebp+var_4], 0
0x1001ed0c  nop     dword ptr [eax+00h]
0x1001ed10  mov     edx, [edi+0Ch]
0x1001ed13  mov     edi, [edx+170h]
0x1001ed19  cmp     edi, 0FFFFFFFFh
0x1001ed1c  jz      loc_1001EDD7
0x1001ed22  mov     [ebp+var_44], 1
0x1001ed29  mov     byte ptr [ebp+var_4], 1
0x1001ed2d  test    edi, edi
0x1001ed2f  js      short loc_1001ED42
0x1001ed31  cmp     edi, 0FFh
0x1001ed37  jnb     short loc_1001ED42
0x1001ed39  mov     ebx, [edx+edi*4+178h]
0x1001ed40  jmp     short loc_1001ED44
0x1001ed42  xor     ebx, ebx
0x1001ed44  mov     eax, [ebx]
0x1001ed46  mov     esi, [eax+30h]
0x1001ed49  lea     eax, [ebp+var_44]
0x1001ed4c  push    eax; unsigned int
0x1001ed4d  push    [ebp+var_1C]; void *
0x1001ed50  mov     ecx, esi
0x1001ed52  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001ed58  mov     ecx, ebx
0x1001ed5a  call    esi
0x1001ed5c  mov     ecx, [ebp+var_44]
0x1001ed5f  mov     esi, eax
0x1001ed61  test    esi, esi
0x1001ed63  jz      short loc_1001ED8D
0x1001ed65  mov     ebx, [ebp+var_1C]
0x1001ed68  test    cl, 8
0x1001ed6b  jnz     short loc_1001ED8D
0x1001ed6d  push    ebx; struct tagColParams *
0x1001ed6e  mov     ecx, esi; this
0x1001ed70  call    ?SaveRecordData@LongValue@@QAEXPAUtagColParams@@@Z; LongValue::SaveRecordData(tagColParams *)
0x1001ed75  lea     eax, [ebp+var_44]
0x1001ed78  mov     ecx, esi; this
0x1001ed7a  push    eax; struct Err *
0x1001ed7b  push    ebx; struct tagColParams *
0x1001ed7c  call    ?UpdateCopyBuffer@LongValue@@QAEXPAUtagColParams@@AAVErr@@@Z; LongValue::UpdateCopyBuffer(tagColParams *,Err &)
0x1001ed81  mov     ecx, [ebp+var_44]
0x1001ed84  test    cl, 8
0x1001ed87  jz      loc_1001EF08
0x1001ed8d  mov     byte ptr [ebp+var_4], 0
0x1001ed91  test    ecx, 0FFFFFFFEh
0x1001ed97  jz      short loc_1001EDB9
0x1001ed99  mov     eax, [ebp+Block]
0x1001ed9c  test    eax, eax
0x1001ed9e  jz      short loc_1001EDA9
0x1001eda0  push    eax; Block
0x1001eda1  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001eda6  add     esp, 4
0x1001eda9  mov     eax, [ebp+var_34]
0x1001edac  test    eax, eax
0x1001edae  jz      short loc_1001EDB9
0x1001edb0  push    eax; Block
0x1001edb1  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001edb6  add     esp, 4
0x1001edb9  mov     eax, [ebp+var_10]
0x1001edbc  mov     edx, [eax+0Ch]
0x1001edbf  mov     eax, [edx+168h]
0x1001edc5  mov     edi, [eax+edi*8]
0x1001edc8  cmp     edi, 0FFFFFFFFh
0x1001edcb  jnz     loc_1001ED22
0x1001edd1  mov     ecx, [ebp+var_30]
0x1001edd4  mov     ebx, [ebp+var_1C]
0x1001edd7  mov     edi, [ebp+var_18]
0x1001edda  mov     esi, [ebp+arg_0]
0x1001eddd  test    byte ptr [esi], 1
0x1001ede0  jnz     loc_1001EEB6
0x1001ede6  cmp     dword ptr [esi+4], 0FFFFFBFEh
0x1001eded  jnz     loc_1001EEB6
0x1001edf3  mov     eax, [edi+4]
0x1001edf6  cmp     dword ptr [eax+804h], 0
0x1001edfd  jnz     loc_1001EEB6
0x1001ee03  test    ecx, 0FFFFFFFEh
0x1001ee09  jz      short loc_1001EE2B
0x1001ee0b  mov     eax, [ebp+var_24]
0x1001ee0e  test    eax, eax
0x1001ee10  jz      short loc_1001EE1B
0x1001ee12  push    eax; Block
0x1001ee13  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ee18  add     esp, 4
0x1001ee1b  mov     eax, [ebp+var_20]
0x1001ee1e  test    eax, eax
0x1001ee20  jz      short loc_1001EE2B
0x1001ee22  push    eax; Block
0x1001ee23  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ee28  add     esp, 4
0x1001ee2b  mov     eax, [edi+4]
0x1001ee2e  mov     ecx, 1
0x1001ee33  mov     [ebp+var_30], ecx
0x1001ee36  cmp     dword ptr [eax+824h], 0
0x1001ee3d  jz      short loc_1001EEB6
0x1001ee3f  cmp     dword ptr [eax+804h], 0
0x1001ee46  jnz     short loc_1001EEB6
0x1001ee48  cmp     dword ptr [eax+820h], 0
0x1001ee4f  jnz     short loc_1001EEB6
0x1001ee51  cmp     dword ptr [eax+810h], 0
0x1001ee58  jz      short loc_1001EEB6
0x1001ee5a  mov     [eax+804h], ecx
0x1001ee60  mov     [eax+824h], ecx
0x1001ee66  mov     ecx, [ebp+var_30]
0x1001ee69  test    cl, 8
0x1001ee6c  jnz     short loc_1001EEB6
0x1001ee6e  lea     eax, [ebp+var_30]
0x1001ee71  mov     ecx, edi; this
0x1001ee73  push    eax; struct Err *
0x1001ee74  push    ebx; struct tagColParams *
0x1001ee75  call    ?UpdateCopyBuffer@LongValue@@QAEXPAUtagColParams@@AAVErr@@@Z; LongValue::UpdateCopyBuffer(tagColParams *,Err &)
0x1001ee7a  mov     ecx, [ebp+var_30]
0x1001ee7d  test    cl, 8
0x1001ee80  jnz     short loc_1001EEB6
0x1001ee82  test    dword ptr [esi], 0FFFFFFFEh
0x1001ee88  jz      short loc_1001EEB0
0x1001ee8a  mov     eax, [esi+0Ch]
0x1001ee8d  test    eax, eax
0x1001ee8f  jz      short loc_1001EE9D
0x1001ee91  push    eax; Block
0x1001ee92  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ee97  mov     ecx, [ebp+var_30]
0x1001ee9a  add     esp, 4
0x1001ee9d  mov     eax, [esi+10h]
0x1001eea0  test    eax, eax
0x1001eea2  jz      short loc_1001EEB0
0x1001eea4  push    eax; Block
0x1001eea5  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001eeaa  mov     ecx, [ebp+var_30]
0x1001eead  add     esp, 4
0x1001eeb0  mov     dword ptr [esi], 1
0x1001eeb6  mov     [ebp+var_4], 0FFFFFFFFh
0x1001eebd  test    ecx, 0FFFFFFFEh
0x1001eec3  jz      short loc_1001EEE5
0x1001eec5  mov     eax, [ebp+var_24]
0x1001eec8  test    eax, eax
0x1001eeca  jz      short loc_1001EED5
0x1001eecc  push    eax; Block
0x1001eecd  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001eed2  add     esp, 4
0x1001eed5  mov     eax, [ebp+var_20]
0x1001eed8  test    eax, eax
0x1001eeda  jz      short loc_1001EEE5
0x1001eedc  push    eax; Block
0x1001eedd  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001eee2  add     esp, 4
0x1001eee5  mov     edi, [ebp+var_10]
0x1001eee8  mov     edx, [ebp+var_14]
0x1001eeeb  test    byte ptr [esi], 8
0x1001eeee  jz      loc_1001EC90
0x1001eef4  mov     ecx, [ebp+var_C]
0x1001eef7  mov     large fs:0, ecx
0x1001eefe  pop     ecx
0x1001eeff  pop     edi
0x1001ef00  pop     esi
0x1001ef01  pop     ebx
0x1001ef02  mov     esp, ebp
0x1001ef04  pop     ebp
0x1001ef05  retn    4
0x1001ef08  mov     byte ptr [ebp+var_4], 0
0x1001ef0c  test    ecx, 0FFFFFFFEh
0x1001ef12  jz      short loc_1001EF34
0x1001ef14  mov     eax, [ebp+Block]
0x1001ef17  test    eax, eax
0x1001ef19  jz      short loc_1001EF24
0x1001ef1b  push    eax; Block
0x1001ef1c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ef21  add     esp, 4
0x1001ef24  mov     eax, [ebp+var_34]
0x1001ef27  test    eax, eax
0x1001ef29  jz      short loc_1001EF34
0x1001ef2b  push    eax; Block
0x1001ef2c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ef31  add     esp, 4
0x1001ef34  mov     edi, [ebp+var_18]
0x1001ef37  lea     eax, [ebp+var_30]
0x1001ef3a  push    eax; struct Err *
0x1001ef3b  push    ebx; struct tagColParams *
0x1001ef3c  mov     ecx, edi; this
0x1001ef3e  call    ?UpdateCopyBuffer@LongValue@@QAEXPAUtagColParams@@AAVErr@@@Z; LongValue::UpdateCopyBuffer(tagColParams *,Err &)
0x1001ef43  mov     ecx, [ebp+var_30]
0x1001ef46  test    cl, 8
0x1001ef49  jz      short loc_1001EF99
0x1001ef4b  test    cl, 1
0x1001ef4e  jnz     loc_1001EDDA
0x1001ef54  cmp     [ebp+var_2C], 0FFFFFBFEh
0x1001ef5b  jnz     loc_1001EDDA
0x1001ef61  test    ecx, 0FFFFFFFEh
0x1001ef67  jz      short loc_1001EF89
0x1001ef69  mov     eax, [ebp+var_24]
0x1001ef6c  test    eax, eax
0x1001ef6e  jz      short loc_1001EF79
0x1001ef70  push    eax; Block
0x1001ef71  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ef76  add     esp, 4
0x1001ef79  mov     eax, [ebp+var_20]
0x1001ef7c  test    eax, eax
0x1001ef7e  jz      short loc_1001EF89
0x1001ef80  push    eax; Block
0x1001ef81  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ef86  add     esp, 4
0x1001ef89  mov     edi, [ebp+var_10]
0x1001ef8c  mov     ecx, 1
0x1001ef91  mov     [ebp+var_30], ecx
0x1001ef94  jmp     loc_1001ED10
0x1001ef99  mov     esi, [ebp+arg_0]
0x1001ef9c  test    dword ptr [esi], 0FFFFFFFEh
0x1001efa2  jz      short loc_1001EFCA
0x1001efa4  mov     eax, [esi+0Ch]
0x1001efa7  test    eax, eax
0x1001efa9  jz      short loc_1001EFB7
0x1001efab  push    eax; Block
0x1001efac  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001efb1  mov     ecx, [ebp+var_30]
0x1001efb4  add     esp, 4
0x1001efb7  mov     eax, [esi+10h]
0x1001efba  test    eax, eax
0x1001efbc  jz      short loc_1001EFCA
0x1001efbe  push    eax; Block
0x1001efbf  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001efc4  mov     ecx, [ebp+var_30]
0x1001efc7  add     esp, 4
0x1001efca  mov     dword ptr [esi], 1
0x1001efd0  jmp     loc_1001EDDD
0x10060310  lea     ecx, [ebp+var_30]; this
0x10060313  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060318  lea     ecx, [ebp+var_44]; this
0x1006031b  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060325  nop
0x10060326  nop
0x10060327  mov     edx, [esp-4+arg_4]
0x1006032b  lea     eax, [edx+0Ch]
0x1006032e  mov     ecx, [edx-48h]
0x10060331  xor     ecx, eax; StackCookie
0x10060333  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060338  mov     eax, offset stru_10063290
0x1006033d  jmp     ___CxxFrameHandler3
```
