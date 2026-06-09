# CJetParameterList::ReadStorageParameter(tagDBBINDING *,void * *,ulong *,ulong *)

- ea: `0x1004ae80`
- end: `0x1004b24c`
- name: `?ReadStorageParameter@CJetParameterList@@QAEJPAUtagDBBINDING@@PAPAXPAK2@Z`
- size: `972`
- prototype: `int __thiscall(CJetParameterList *__hidden this, struct tagDBBINDING *, void **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1004a120`

## callees

- `0x1001c6d0`
- `0x1004ae80`
- `0x1004d420`

## pseudocode

```c
int __thiscall CJetParameterList::ReadStorageParameter(
        CJetParameterList *this,
        struct tagDBBINDING *a2,
        void **a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int v5; // ebx
  unsigned int v7; // edi
  int v8; // eax
  int v9; // edi
  GUID *v10; // ecx
  unsigned int v11; // esi
  int v12; // edx
  int v13; // eax
  bool v14; // cf
  unsigned __int8 v15; // al
  unsigned __int8 v16; // al
  unsigned __int8 Data1_high; // al
  int v18; // eax
  int v19; // edx
  GUID *v20; // ecx
  unsigned int v21; // esi
  int v22; // eax
  bool v23; // cf
  unsigned __int8 v24; // al
  unsigned __int8 v25; // al
  unsigned __int8 v26; // al
  unsigned int v27; // eax
  unsigned int v28; // edx
  unsigned __int64 v29; // rax
  int v30; // edi
  int v31; // esi
  int v32; // eax
  unsigned int v33; // kr00_4
  int v34; // [esp+14h] [ebp-84h]
  int v35; // [esp+1Ch] [ebp-7Ch]
  _DWORD ***v36; // [esp+24h] [ebp-74h]
  int v37; // [esp+28h] [ebp-70h] BYREF
  int v38; // [esp+2Ch] [ebp-6Ch]
  int v39; // [esp+30h] [ebp-68h]
  int v40; // [esp+34h] [ebp-64h] BYREF
  void **v41; // [esp+38h] [ebp-60h]
  __int64 v42; // [esp+3Ch] [ebp-5Ch]
  unsigned int v43; // [esp+44h] [ebp-54h] BYREF
  _BYTE v44[8]; // [esp+48h] [ebp-50h] BYREF
  unsigned int v45; // [esp+50h] [ebp-48h]

  v5 = 0;
  v41 = a3;
  *a5 = 0;
  v43 = 0;
  v39 = 0;
  v37 = 0;
  v40 = 0;
  if ( !a2->pObject )
    return -2147467259;
  v36 = (_DWORD ***)*a3;
  if ( (a2->dwPart & 2) != 0 )
  {
    v7 = *a4;
    if ( *a4 )
    {
      if ( v7 >= 0x1FE )
        goto LABEL_7;
      goto LABEL_6;
    }
  }
  if ( *a4 )
  {
LABEL_6:
    v7 = 510;
LABEL_7:
    v8 = (*(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12))(
           *(_DWORD *)(*(_DWORD *)Sys + 12),
           Sys,
           v7);
    v38 = v8;
    *v41 = (void *)v8;
    if ( v8 )
    {
      v10 = &IID_ISequentialStream;
      v11 = 12;
      LODWORD(v42) = &a2->pObject->iid;
      v12 = v42;
      while ( v10->Data1 == *(_DWORD *)v12 )
      {
        v10 = (GUID *)((char *)v10 + 4);
        v12 += 4;
        v14 = v11 < 4;
        v11 -= 4;
        if ( v14 )
        {
          v13 = 0;
          goto LABEL_21;
        }
      }
      v14 = LOBYTE(v10->Data1) < *(_BYTE *)v12;
      if ( LOBYTE(v10->Data1) == *(_BYTE *)v12
        && (v15 = BYTE1(v10->Data1), v14 = v15 < *(_BYTE *)(v12 + 1), v15 == *(_BYTE *)(v12 + 1))
        && (v16 = BYTE2(v10->Data1), v14 = v16 < *(_BYTE *)(v12 + 2), v16 == *(_BYTE *)(v12 + 2))
        && (Data1_high = HIBYTE(v10->Data1), v14 = Data1_high < *(_BYTE *)(v12 + 3), Data1_high == *(_BYTE *)(v12 + 3)) )
      {
        v13 = 0;
      }
      else
      {
        v13 = v14 ? -1 : 1;
      }
LABEL_21:
      if ( v13 )
      {
        v19 = v42;
        v20 = &IID_ILockBytes;
        v21 = 12;
        while ( v20->Data1 == *(_DWORD *)v19 )
        {
          v20 = (GUID *)((char *)v20 + 4);
          v19 += 4;
          v14 = v21 < 4;
          v21 -= 4;
          if ( v14 )
          {
            v22 = 0;
            goto LABEL_42;
          }
        }
        v23 = LOBYTE(v20->Data1) < *(_BYTE *)v19;
        if ( LOBYTE(v20->Data1) == *(_BYTE *)v19
          && (v24 = BYTE1(v20->Data1), v23 = v24 < *(_BYTE *)(v19 + 1), v24 == *(_BYTE *)(v19 + 1))
          && (v25 = BYTE2(v20->Data1), v23 = v25 < *(_BYTE *)(v19 + 2), v25 == *(_BYTE *)(v19 + 2))
          && (v26 = HIBYTE(v20->Data1), v23 = v26 < *(_BYTE *)(v19 + 3), v26 == *(_BYTE *)(v19 + 3)) )
        {
          v22 = 0;
        }
        else
        {
          v22 = v23 ? -1 : 1;
        }
LABEL_42:
        if ( v22 )
        {
          v9 = -2147467259;
        }
        else
        {
          if ( ((int (__thiscall *)(_DWORD, _DWORD, _DWORD, int *))***v36)(***v36, *v36, v42, &v40) >= 0 )
          {
            v27 = (*(int (__thiscall **)(_DWORD, int, _BYTE *, int))(*(_DWORD *)v40 + 36))(
                    *(_DWORD *)(*(_DWORD *)v40 + 36),
                    v40,
                    v44,
                    1);
            v28 = v7;
            v34 = v27 >> 31;
            if ( v45 > v7 )
              v28 = v45;
            v39 = v28;
            HIDWORD(v29) = 0;
            v42 = 0;
            while ( 1 )
            {
              v43 = 0;
              v35 = (*(int (__thiscall **)(_DWORD, int, _DWORD, _DWORD, int, unsigned int, unsigned int *))(*(_DWORD *)v40 + 12))(
                      *(_DWORD *)(*(_DWORD *)v40 + 12),
                      v40,
                      v42,
                      HIDWORD(v29),
                      v38,
                      v7,
                      &v43);
              if ( v35 < 0 || !v43 )
                v34 = 1;
              if ( v7 )
              {
                v5 += v43;
                if ( v43 < v7 )
                  goto LABEL_30;
                v30 = 2 * v39;
                v31 = *(_DWORD *)Sys;
                v39 *= 2;
                v32 = (*(int (__thiscall **)(_DWORD, int, void *, int))(v31 + 16))(
                        *(_DWORD *)(v31 + 16),
                        Sys,
                        *v41,
                        v39);
                *v41 = (void *)v32;
                if ( !v32 )
                  goto LABEL_8;
                v38 = v5 + v32;
                v33 = v42;
                LODWORD(v42) = v43 + v42;
                v29 = __PAIR64__(HIDWORD(v42), v43) + v33;
                v7 = v30 - v5;
                HIDWORD(v42) = HIDWORD(v29);
              }
              else
              {
                HIDWORD(v29) = HIDWORD(v42);
              }
              if ( v34 )
                goto LABEL_30;
            }
          }
          v9 = -2147217887;
        }
      }
      else
      {
        HIDWORD(v42) = v7;
        if ( ((int (__thiscall *)(_DWORD, _DWORD, _DWORD, int *))***v36)(***v36, *v36, v42, &v37) >= 0 )
        {
          do
          {
            v43 = 0;
            v35 = (*(int (__thiscall **)(_DWORD, int, int, _DWORD, unsigned int *))(*(_DWORD *)v37 + 12))(
                    *(_DWORD *)(*(_DWORD *)v37 + 12),
                    v37,
                    v38,
                    HIDWORD(v42),
                    &v43);
            if ( v35 < 0 || !v43 )
            {
              v39 = 1;
              if ( !v43 )
                continue;
            }
            v5 += v43;
            if ( v43 < HIDWORD(v42) )
              break;
            v7 *= 2;
            v18 = (*(int (__thiscall **)(_DWORD, int, void *, unsigned int))(*(_DWORD *)Sys + 16))(
                    *(_DWORD *)(*(_DWORD *)Sys + 16),
                    Sys,
                    *v41,
                    v7);
            *v41 = (void *)v18;
            v38 = v5 + v18;
            HIDWORD(v42) = v7 - v5;
          }
          while ( !v39 );
LABEL_30:
          if ( v5 )
          {
            v9 = 0;
            *a5 = v5;
          }
          else
          {
            v9 = v35;
            if ( v35 >= 0 )
              *a5 = 0;
          }
        }
        else
        {
          v9 = -2147217887;
        }
      }
    }
    else
    {
LABEL_8:
      v9 = -2147217887;
    }
    goto LABEL_61;
  }
  v9 = 0;
  *a3 = 0;
  *a5 = 0;
LABEL_61:
  if ( v37 && !(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v37 + 8))(*(_DWORD *)(*(_DWORD *)v37 + 8), v37) )
    v37 = 0;
  if ( v40 && !(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v40 + 8))(*(_DWORD *)(*(_DWORD *)v40 + 8), v40) )
    v40 = 0;
  if ( v36 )
    ((void (__thiscall *)(_DWORD, _DWORD))(**v36)[2])((**v36)[2], *v36);
  return v9;
}

```

## disassembly

```asm
0x1004ae80  mov     edi, edi
0x1004ae82  push    ebp
0x1004ae83  mov     ebp, esp
0x1004ae85  sub     esp, 8Ch
0x1004ae8b  mov     eax, ___security_cookie
0x1004ae90  xor     eax, ebp
0x1004ae92  mov     [ebp+var_4], eax
0x1004ae95  mov     ecx, [ebp+arg_0]
0x1004ae98  xor     eax, eax
0x1004ae9a  mov     edx, [ebp+arg_8]
0x1004ae9d  push    ebx
0x1004ae9e  push    esi
0x1004ae9f  mov     esi, [ebp+arg_4]
0x1004aea2  xor     ebx, ebx
0x1004aea4  push    edi
0x1004aea5  mov     edi, [ebp+arg_C]
0x1004aea8  mov     dword ptr [ebp+var_80+4], ecx
0x1004aeab  mov     [ebp+var_60], esi
0x1004aeae  mov     [ebp+var_88], edi
0x1004aeb4  mov     [edi], eax
0x1004aeb6  mov     [ebp+var_54], 0
0x1004aebd  mov     [ebp+var_68], eax
0x1004aec0  mov     [ebp+var_70], eax
0x1004aec3  mov     [ebp+var_64], eax
0x1004aec6  cmp     [ecx+14h], eax
0x1004aec9  jnz     short loc_1004AEE3
0x1004aecb  mov     eax, 80004005h
0x1004aed0  pop     edi
0x1004aed1  pop     esi
0x1004aed2  pop     ebx
0x1004aed3  mov     ecx, [ebp+var_4]
0x1004aed6  xor     ecx, ebp; StackCookie
0x1004aed8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004aedd  mov     esp, ebp
0x1004aedf  pop     ebp
0x1004aee0  retn    10h
0x1004aee3  test    byte ptr [ecx+1Ch], 2
0x1004aee7  mov     eax, [esi]
0x1004aee9  mov     [ebp+var_74], eax
0x1004aeec  jz      short loc_1004AF2E
0x1004aeee  mov     edi, [edx]
0x1004aef0  test    edi, edi
0x1004aef2  jz      short loc_1004AF2E
0x1004aef4  cmp     edi, 1FEh
0x1004aefa  jnb     short loc_1004AF01
0x1004aefc  mov     edi, 1FEh
0x1004af01  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1004af07  push    edi
0x1004af08  push    ecx
0x1004af09  mov     eax, [ecx]
0x1004af0b  mov     esi, [eax+0Ch]
0x1004af0e  mov     ecx, esi
0x1004af10  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004af16  call    esi
0x1004af18  mov     ecx, [ebp+var_60]
0x1004af1b  mov     [ebp+var_6C], eax
0x1004af1e  mov     [ecx], eax
0x1004af20  test    eax, eax
0x1004af22  jnz     short loc_1004AF43
0x1004af24  mov     edi, 80040E21h
0x1004af29  jmp     loc_1004B1E2
0x1004af2e  cmp     [edx], ebx
0x1004af30  jnz     short loc_1004AEFC
0x1004af32  mov     eax, [ebp+var_88]
0x1004af38  xor     edi, edi
0x1004af3a  mov     [esi], ebx
0x1004af3c  mov     [eax], ebx
0x1004af3e  jmp     loc_1004B1E2
0x1004af43  mov     eax, dword ptr [ebp+var_80+4]
0x1004af46  mov     ecx, offset _IID_ISequentialStream
0x1004af4b  mov     esi, 0Ch
0x1004af50  mov     eax, [eax+14h]
0x1004af53  add     eax, 4
0x1004af56  mov     dword ptr [ebp+var_5C], eax
0x1004af59  mov     edx, eax
0x1004af5b  nop     dword ptr [eax+eax+00h]
0x1004af60  mov     eax, [ecx]
0x1004af62  cmp     eax, [edx]
0x1004af64  jnz     short loc_1004AF75
0x1004af66  add     ecx, 4
0x1004af69  add     edx, 4
0x1004af6c  sub     esi, 4
0x1004af6f  jnb     short loc_1004AF60
0x1004af71  xor     eax, eax
0x1004af73  jmp     short loc_1004AF9C
0x1004af75  mov     al, [ecx]
0x1004af77  cmp     al, [edx]
0x1004af79  jnz     short loc_1004AF97
0x1004af7b  mov     al, [ecx+1]
0x1004af7e  cmp     al, [edx+1]
0x1004af81  jnz     short loc_1004AF97
0x1004af83  mov     al, [ecx+2]
0x1004af86  cmp     al, [edx+2]
0x1004af89  jnz     short loc_1004AF97
0x1004af8b  mov     al, [ecx+3]
0x1004af8e  cmp     al, [edx+3]
0x1004af91  jnz     short loc_1004AF97
0x1004af93  xor     eax, eax
0x1004af95  jmp     short loc_1004AF9C
0x1004af97  sbb     eax, eax
0x1004af99  or      eax, 1
0x1004af9c  test    eax, eax
0x1004af9e  jnz     loc_1004B05F
0x1004afa4  mov     ecx, [ebp+var_74]
0x1004afa7  mov     dword ptr [ebp+var_5C+4], edi
0x1004afaa  mov     ecx, [ecx]
0x1004afac  mov     eax, [ecx]
0x1004afae  mov     esi, [eax]
0x1004afb0  lea     eax, [ebp+var_70]
0x1004afb3  push    eax
0x1004afb4  push    dword ptr [ebp+var_5C]
0x1004afb7  push    ecx
0x1004afb8  mov     ecx, esi
0x1004afba  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004afc0  call    esi
0x1004afc2  test    eax, eax
0x1004afc4  jns     short loc_1004AFD0
0x1004afc6  mov     edi, 80040E21h
0x1004afcb  jmp     loc_1004B1E2
0x1004afd0  mov     ecx, [ebp+var_70]
0x1004afd3  mov     [ebp+var_54], 0
0x1004afda  mov     eax, [ecx]
0x1004afdc  mov     esi, [eax+0Ch]
0x1004afdf  lea     eax, [ebp+var_54]
0x1004afe2  push    eax
0x1004afe3  push    dword ptr [ebp+var_5C+4]
0x1004afe6  push    [ebp+var_6C]
0x1004afe9  push    ecx
0x1004afea  mov     ecx, esi
0x1004afec  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004aff2  call    esi
0x1004aff4  mov     ecx, [ebp+var_54]
0x1004aff7  mov     dword ptr [ebp+var_80+4], eax
0x1004affa  test    eax, eax
0x1004affc  js      short loc_1004B002
0x1004affe  test    ecx, ecx
0x1004b000  jnz     short loc_1004B00D
0x1004b002  mov     [ebp+var_68], 1
0x1004b009  test    ecx, ecx
0x1004b00b  jz      short loc_1004B042
0x1004b00d  add     ebx, ecx
0x1004b00f  cmp     ecx, dword ptr [ebp+var_5C+4]
0x1004b012  jb      short loc_1004B048
0x1004b014  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1004b019  add     edi, edi
0x1004b01b  mov     ecx, [ebp+var_60]
0x1004b01e  push    edi
0x1004b01f  mov     esi, [eax]
0x1004b021  push    dword ptr [ecx]
0x1004b023  push    eax
0x1004b024  mov     esi, [esi+10h]
0x1004b027  mov     ecx, esi
0x1004b029  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004b02f  call    esi
0x1004b031  mov     ecx, [ebp+var_60]
0x1004b034  mov     [ecx], eax
0x1004b036  add     eax, ebx
0x1004b038  mov     [ebp+var_6C], eax
0x1004b03b  mov     eax, edi
0x1004b03d  sub     eax, ebx
0x1004b03f  mov     dword ptr [ebp+var_5C+4], eax
0x1004b042  cmp     [ebp+var_68], 0
0x1004b046  jz      short loc_1004AFD0
0x1004b048  test    ebx, ebx
0x1004b04a  jz      loc_1004B1CC
0x1004b050  mov     eax, [ebp+var_88]
0x1004b056  xor     edi, edi
0x1004b058  mov     [eax], ebx
0x1004b05a  jmp     loc_1004B1E2
0x1004b05f  mov     edx, dword ptr [ebp+var_5C]
0x1004b062  mov     ecx, offset _IID_ILockBytes
0x1004b067  mov     esi, 0Ch
0x1004b06c  nop     dword ptr [eax+00h]
0x1004b070  mov     eax, [ecx]
0x1004b072  cmp     eax, [edx]
0x1004b074  jnz     short loc_1004B085
0x1004b076  add     ecx, 4
0x1004b079  add     edx, 4
0x1004b07c  sub     esi, 4
0x1004b07f  jnb     short loc_1004B070
0x1004b081  xor     eax, eax
0x1004b083  jmp     short loc_1004B0AC
0x1004b085  mov     al, [ecx]
0x1004b087  cmp     al, [edx]
0x1004b089  jnz     short loc_1004B0A7
0x1004b08b  mov     al, [ecx+1]
0x1004b08e  cmp     al, [edx+1]
0x1004b091  jnz     short loc_1004B0A7
0x1004b093  mov     al, [ecx+2]
0x1004b096  cmp     al, [edx+2]
0x1004b099  jnz     short loc_1004B0A7
0x1004b09b  mov     al, [ecx+3]
0x1004b09e  cmp     al, [edx+3]
0x1004b0a1  jnz     short loc_1004B0A7
0x1004b0a3  xor     eax, eax
0x1004b0a5  jmp     short loc_1004B0AC
0x1004b0a7  sbb     eax, eax
0x1004b0a9  or      eax, 1
0x1004b0ac  test    eax, eax
0x1004b0ae  jnz     loc_1004B1DD
0x1004b0b4  mov     ecx, [ebp+var_74]
0x1004b0b7  xorps   xmm0, xmm0
0x1004b0ba  movlpd  [ebp+var_80], xmm0
0x1004b0bf  mov     ecx, [ecx]
0x1004b0c1  mov     eax, [ecx]
0x1004b0c3  mov     esi, [eax]
0x1004b0c5  lea     eax, [ebp+var_64]
0x1004b0c8  push    eax
0x1004b0c9  push    dword ptr [ebp+var_5C]
0x1004b0cc  push    ecx
0x1004b0cd  mov     ecx, esi
0x1004b0cf  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004b0d5  call    esi
0x1004b0d7  test    eax, eax
0x1004b0d9  jns     short loc_1004B0E5
0x1004b0db  mov     edi, 80040E21h
0x1004b0e0  jmp     loc_1004B1E2
0x1004b0e5  mov     eax, [ebp+var_64]
0x1004b0e8  lea     ecx, [ebp+var_50]
0x1004b0eb  push    1
0x1004b0ed  push    ecx
0x1004b0ee  push    eax
0x1004b0ef  mov     esi, [eax]
0x1004b0f1  mov     esi, [esi+24h]
0x1004b0f4  mov     ecx, esi
0x1004b0f6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004b0fc  call    esi
0x1004b0fe  shr     eax, 1Fh
0x1004b101  mov     edx, edi
0x1004b103  cmp     [ebp+var_48], edi
0x1004b106  mov     [ebp+var_84], eax
0x1004b10c  cmova   edx, [ebp+var_48]
0x1004b110  mov     eax, dword ptr [ebp+var_80]
0x1004b113  mov     [ebp+var_68], edx
0x1004b116  mov     edx, dword ptr [ebp+var_80+4]
0x1004b119  mov     dword ptr [ebp+var_5C+4], edx
0x1004b11c  mov     dword ptr [ebp+var_5C], eax
0x1004b11f  nop
0x1004b120  mov     ecx, [ebp+var_64]
0x1004b123  mov     [ebp+var_54], 0
0x1004b12a  mov     eax, [ecx]
0x1004b12c  mov     esi, [eax+0Ch]
0x1004b12f  lea     eax, [ebp+var_54]
0x1004b132  push    eax
0x1004b133  push    edi
0x1004b134  push    [ebp+var_6C]
0x1004b137  push    edx
0x1004b138  push    dword ptr [ebp+var_5C]
0x1004b13b  push    ecx
0x1004b13c  mov     ecx, esi
0x1004b13e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004b144  call    esi
0x1004b146  mov     dword ptr [ebp+var_80+4], eax
0x1004b149  test    eax, eax
0x1004b14b  mov     eax, [ebp+var_54]
0x1004b14e  js      short loc_1004B154
0x1004b150  test    eax, eax
0x1004b152  jnz     short loc_1004B15E
0x1004b154  mov     [ebp+var_84], 1
0x1004b15e  test    edi, edi
0x1004b160  jz      short loc_1004B1B7
0x1004b162  add     ebx, eax
0x1004b164  cmp     eax, edi
0x1004b166  jb      loc_1004B048
0x1004b16c  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1004b171  mov     edi, [ebp+var_68]
0x1004b174  mov     ecx, [ebp+var_60]
0x1004b177  add     edi, edi
0x1004b179  push    edi
0x1004b17a  mov     esi, [eax]
0x1004b17c  mov     [ebp+var_68], edi
0x1004b17f  push    dword ptr [ecx]
0x1004b181  mov     esi, [esi+10h]
0x1004b184  mov     ecx, esi
0x1004b186  push    eax
0x1004b187  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004b18d  call    esi
0x1004b18f  mov     ecx, [ebp+var_60]
0x1004b192  mov     [ecx], eax
0x1004b194  test    eax, eax
0x1004b196  jz      loc_1004AF24
0x1004b19c  mov     edx, dword ptr [ebp+var_5C+4]
0x1004b19f  add     eax, ebx
0x1004b1a1  mov     [ebp+var_6C], eax
0x1004b1a4  mov     eax, dword ptr [ebp+var_5C]
0x1004b1a7  add     eax, [ebp+var_54]
0x1004b1aa  mov     dword ptr [ebp+var_5C], eax
0x1004b1ad  adc     edx, 0
0x1004b1b0  sub     edi, ebx
0x1004b1b2  mov     dword ptr [ebp+var_5C+4], edx
0x1004b1b5  jmp     short loc_1004B1BA
0x1004b1b7  mov     edx, dword ptr [ebp+var_5C+4]
0x1004b1ba  cmp     [ebp+var_84], 0
0x1004b1c1  jz      loc_1004B120
0x1004b1c7  jmp     loc_1004B048
0x1004b1cc  mov     edi, dword ptr [ebp+var_80+4]
0x1004b1cf  test    edi, edi
0x1004b1d1  js      short loc_1004B1E2
0x1004b1d3  mov     eax, [ebp+var_88]
0x1004b1d9  mov     [eax], ebx
  ... truncated ...
```
