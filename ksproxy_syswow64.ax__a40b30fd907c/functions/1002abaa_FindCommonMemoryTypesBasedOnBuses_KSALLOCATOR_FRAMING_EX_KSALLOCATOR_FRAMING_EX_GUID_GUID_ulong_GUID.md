# FindCommonMemoryTypesBasedOnBuses(KSALLOCATOR_FRAMING_EX *,KSALLOCATOR_FRAMING_EX *,_GUID,_GUID,ulong *,_GUID *)

- ea: `0x1002abaa`
- end: `0x1002ad8e`
- name: `?FindCommonMemoryTypesBasedOnBuses@@YGHPAUKSALLOCATOR_FRAMING_EX@@0U_GUID@@1PAKPAU2@@Z`
- size: `484`
- prototype: `int __userpurge@<eax>(unsigned int *@<edx>, unsigned int *@<ecx>, struct KSALLOCATOR_FRAMING_EX *, struct KSALLOCATOR_FRAMING_EX *Block, struct _GUID, struct _GUID, unsigned int *, struct _GUID *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10022cf8`
- `0x100294a0`
- `0x1002a5bd`

## callees

- `0x1000665f`
- `0x1002abaa`
- `0x1003a6f2`
- `0x1003a72c`
- `0x1003bd04`

## pseudocode

```c
int __userpurge FindCommonMemoryTypesBasedOnBuses@<eax>(
        unsigned int *a1@<edx>,
        unsigned int *a2@<ecx>,
        struct KSALLOCATOR_FRAMING_EX *a3,
        struct KSALLOCATOR_FRAMING_EX *Block,
        struct _GUID a5,
        struct _GUID a6,
        unsigned int *a7,
        struct _GUID *a8)
{
  struct KSALLOCATOR_FRAMING_EX *v8; // edi
  struct KSALLOCATOR_FRAMING_EX *v9; // ebx
  int v10; // edx
  bool v11; // zf
  unsigned int v12; // eax
  unsigned int v13; // esi
  int v14; // ecx
  unsigned int *v15; // esi
  unsigned int i; // edi
  int v17; // ecx
  int result; // eax
  unsigned int *v19; // eax
  unsigned int j; // edx
  int v21; // eax
  int v22; // ecx
  int v23; // ecx
  int v24; // eax
  struct KSALLOCATOR_FRAMING_EX *v25; // edi
  unsigned int *v26; // edi
  unsigned int v27; // [esp+10h] [ebp-30h]
  unsigned int v28; // [esp+14h] [ebp-2Ch]
  unsigned int v29; // [esp+18h] [ebp-28h]
  unsigned int v30; // [esp+1Ch] [ebp-24h]
  int v31; // [esp+20h] [ebp-20h]
  int v32; // [esp+24h] [ebp-1Ch]
  unsigned int v33; // [esp+28h] [ebp-18h]
  unsigned int *v34; // [esp+2Ch] [ebp-14h]
  char v35[4]; // [esp+30h] [ebp-10h]
  unsigned int *v36; // [esp+34h] [ebp-Ch]
  unsigned int v37; // [esp+38h] [ebp-8h]
  int v38; // [esp+3Ch] [ebp-4h]

  v8 = a3;
  v9 = 0;
  v36 = a1;
  v10 = 0;
  v34 = a2;
  v32 = 1;
  v11 = a3->CountItems == 0;
  v38 = 0;
  if ( !v11 )
    v9 = Block;
  v12 = 0;
  v13 = 0;
  v33 = 0;
  v37 = 0;
  if ( *a2 )
  {
    *(_DWORD *)v35 = 0;
    do
    {
      if ( v10 )
        break;
      v14 = 0;
      while ( 1 )
      {
        v13 = v37;
        if ( v34[22 * v12 + 10 + v14] != *(&a5.Data1 + v14) )
          break;
        if ( ++v14 == 4 )
        {
          v15 = &v34[22 * v12 + 6];
          v27 = *v15++;
          v28 = *v15++;
          v29 = *v15;
          v30 = v15[1];
          v13 = v37;
          for ( i = 0; i < v37; ++i )
          {
            v17 = 0;
            while ( *(&v27 + v17) == *(&v9->CountItems + 4 * i + v17) )
            {
              if ( ++v17 == 4 )
                goto LABEL_13;
            }
          }
          v19 = v36;
          for ( j = 0; j < *v36; ++j )
          {
            v21 = (int)&v19[22 * j + 6];
            v22 = 0;
            v31 = v21;
            while ( 1 )
            {
              v13 = v37;
              if ( *(_DWORD *)(v21 + 4 * v22) != *(&v27 + v22) )
                break;
              v21 = v31;
              if ( ++v22 == 4 )
              {
                v23 = 0;
                while ( 1 )
                {
                  v13 = v37;
                  if ( v36[22 * j + 10 + v23] != *(&a6.Data1 + v23) )
                    goto LABEL_37;
                  if ( ++v23 == 4 )
                  {
                    if ( !a3->CountItems )
                    {
                      v24 = *(_DWORD *)v35;
                      if ( v37 == *(_DWORD *)v35 )
                      {
                        v25 = v9;
                        *(_DWORD *)v35 += 25;
                        v9 = (struct KSALLOCATOR_FRAMING_EX *)operator new[](saturated_mul(0x10u, v24 + 25));
                        if ( !v9 )
                        {
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            WPP_SF_q(
                              0xBFu,
                              &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              v35[0]);
                          v32 = 0;
                          v10 = 1;
                          v38 = 1;
                          goto LABEL_14;
                        }
                        if ( v25 && v13 )
                        {
                          memmove(v9, v25, 16 * v13);
                          operator delete[](v25);
                        }
                      }
                    }
                    v10 = v38;
                    v26 = &v9->CountItems + 4 * v13;
                    *v26++ = v27;
                    *v26++ = v28;
                    *v26 = v29;
                    v26[1] = v30;
                    v8 = a3;
                    v13 = v37 + 1;
                    v37 = v13;
                    if ( a3->CountItems == v13 )
                      v10 = 1;
                    v38 = v10;
                    goto LABEL_15;
                  }
                }
              }
            }
LABEL_37:
            v19 = v36;
          }
          break;
        }
      }
LABEL_13:
      v10 = v38;
LABEL_14:
      v8 = a3;
LABEL_15:
      v12 = v33 + 1;
      v33 = v12;
    }
    while ( v12 < *v34 );
  }
  if ( !v8->CountItems )
  {
    v8->CountItems = v13;
    if ( v9 )
      operator delete[](v9);
  }
  result = 0;
  if ( v13 )
    return v32;
  return result;
}

```

## disassembly

```asm
0x1002abaa  mov     edi, edi
0x1002abac  push    ebp
0x1002abad  mov     ebp, esp
0x1002abaf  sub     esp, 34h
0x1002abb2  push    ebx
0x1002abb3  push    esi
0x1002abb4  push    edi
0x1002abb5  mov     edi, [ebp+arg_0]
0x1002abb8  xor     ebx, ebx
0x1002abba  mov     [ebp+var_C], edx
0x1002abbd  xor     edx, edx
0x1002abbf  mov     [ebp+var_14], ecx
0x1002abc2  mov     [ebp+var_1C], 1
0x1002abc9  cmp     [edi], edx
0x1002abcb  mov     [ebp+var_4], edx
0x1002abce  cmovnz  ebx, [ebp+Block]
0x1002abd2  xor     eax, eax
0x1002abd4  xor     esi, esi
0x1002abd6  mov     [ebp+var_18], eax
0x1002abd9  mov     [ebp+var_8], esi
0x1002abdc  cmp     [ecx], eax
0x1002abde  jbe     short loc_1002AC4E
0x1002abe0  xor     ecx, ecx
0x1002abe2  mov     dword ptr [ebp+var_10], ecx
0x1002abe5  test    edx, edx
0x1002abe7  jnz     short loc_1002AC4E
0x1002abe9  mov     edi, [ebp+var_14]
0x1002abec  imul    edx, eax, 58h ; 'X'
0x1002abef  add     edi, edx
0x1002abf1  xor     ecx, ecx
0x1002abf3  mov     eax, [edi+ecx*4+28h]
0x1002abf7  lea     esi, [ebp+arg_8]
0x1002abfa  cmp     eax, [esi+ecx*4]
0x1002abfd  mov     esi, [ebp+var_8]
0x1002ac00  jnz     short loc_1002AC3A
0x1002ac02  inc     ecx
0x1002ac03  cmp     ecx, 4
0x1002ac06  jnz     short loc_1002ABF3
0x1002ac08  mov     esi, [ebp+var_14]
0x1002ac0b  lea     edi, [ebp+var_30]
0x1002ac0e  add     esi, 18h
0x1002ac11  add     esi, edx
0x1002ac13  movsd
0x1002ac14  movsd
0x1002ac15  movsd
0x1002ac16  movsd
0x1002ac17  mov     esi, [ebp+var_8]
0x1002ac1a  xor     edi, edi
0x1002ac1c  test    esi, esi
0x1002ac1e  jz      short loc_1002AC74
0x1002ac20  mov     edx, edi
0x1002ac22  shl     edx, 4
0x1002ac25  add     edx, ebx
0x1002ac27  xor     ecx, ecx
0x1002ac29  lea     eax, [ebp+var_30]
0x1002ac2c  mov     eax, [eax+ecx*4]
0x1002ac2f  cmp     eax, [edx+ecx*4]
0x1002ac32  jnz     short loc_1002AC6F
0x1002ac34  inc     ecx
0x1002ac35  cmp     ecx, 4
0x1002ac38  jnz     short loc_1002AC29
0x1002ac3a  mov     edx, [ebp+var_4]
0x1002ac3d  mov     edi, [ebp+arg_0]
0x1002ac40  mov     eax, [ebp+var_18]
0x1002ac43  mov     ecx, [ebp+var_14]
0x1002ac46  inc     eax
0x1002ac47  mov     [ebp+var_18], eax
0x1002ac4a  cmp     eax, [ecx]
0x1002ac4c  jb      short loc_1002ABE5
0x1002ac4e  cmp     dword ptr [edi], 0
0x1002ac51  jnz     short loc_1002AC60
0x1002ac53  mov     [edi], esi
0x1002ac55  test    ebx, ebx
0x1002ac57  jz      short loc_1002AC60
0x1002ac59  push    ebx; Block
0x1002ac5a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002ac5f  pop     ecx
0x1002ac60  xor     eax, eax
0x1002ac62  test    esi, esi
0x1002ac64  pop     edi
0x1002ac65  cmovnz  eax, [ebp+var_1C]
0x1002ac69  pop     esi
0x1002ac6a  pop     ebx
0x1002ac6b  leave
0x1002ac6c  retn    28h ; '('
0x1002ac6f  inc     edi
0x1002ac70  cmp     edi, esi
0x1002ac72  jb      short loc_1002AC20
0x1002ac74  mov     eax, [ebp+var_C]
0x1002ac77  xor     edx, edx
0x1002ac79  cmp     [eax], edx
0x1002ac7b  jbe     short loc_1002AC3A
0x1002ac7d  imul    edi, edx, 58h ; 'X'
0x1002ac80  add     eax, 18h
0x1002ac83  add     eax, edi
0x1002ac85  xor     ecx, ecx
0x1002ac87  mov     [ebp+var_20], eax
0x1002ac8a  mov     eax, [eax+ecx*4]
0x1002ac8d  lea     esi, [ebp+var_30]
0x1002ac90  cmp     eax, [esi+ecx*4]
0x1002ac93  mov     esi, [ebp+var_8]
0x1002ac96  jnz     loc_1002AD33
0x1002ac9c  mov     eax, [ebp+var_20]
0x1002ac9f  inc     ecx
0x1002aca0  cmp     ecx, 4
0x1002aca3  jnz     short loc_1002AC8A
0x1002aca5  add     edi, [ebp+var_C]
0x1002aca8  xor     ecx, ecx
0x1002acaa  mov     eax, [edi+ecx*4+28h]
0x1002acae  lea     esi, [ebp+arg_18]
0x1002acb1  cmp     eax, [esi+ecx*4]
0x1002acb4  mov     esi, [ebp+var_8]
0x1002acb7  jnz     short loc_1002AD33
0x1002acb9  inc     ecx
0x1002acba  cmp     ecx, 4
0x1002acbd  jnz     short loc_1002ACAA
0x1002acbf  mov     eax, [ebp+arg_0]
0x1002acc2  cmp     dword ptr [eax], 0
0x1002acc5  jnz     loc_1002AD63
0x1002accb  mov     eax, dword ptr [ebp+var_10]
0x1002acce  cmp     esi, eax
0x1002acd0  jnz     loc_1002AD63
0x1002acd6  push    10h
0x1002acd8  add     eax, 19h
0x1002acdb  mov     edi, ebx
0x1002acdd  pop     ecx
0x1002acde  mov     dword ptr [ebp+var_10], eax
0x1002ace1  mul     ecx
0x1002ace3  push    0FFFFFFFFh
0x1002ace5  pop     ecx
0x1002ace6  cmovb   eax, ecx
0x1002ace9  push    eax; unsigned int
0x1002acea  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1002acef  mov     ebx, eax
0x1002acf1  pop     ecx
0x1002acf2  test    ebx, ebx
0x1002acf4  jnz     short loc_1002AD44
0x1002acf6  mov     eax, _WPP_GLOBAL_Control
0x1002acfb  cmp     eax, offset _WPP_GLOBAL_Control
0x1002ad00  jz      short loc_1002AD21
0x1002ad02  cmp     byte ptr [eax+19h], 2
0x1002ad06  jb      short loc_1002AD21
0x1002ad08  mov     ecx, dword ptr [ebp+var_10]
0x1002ad0b  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002ad10  push    ecx; char
0x1002ad11  push    dword ptr [eax+14h]
0x1002ad14  mov     ecx, 0BFh; MessageNumber
0x1002ad19  push    dword ptr [eax+10h]; LoggerHandle
0x1002ad1c  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002ad21  xor     edx, edx
0x1002ad23  mov     [ebp+var_1C], 0
0x1002ad2a  inc     edx
0x1002ad2b  mov     [ebp+var_4], edx
0x1002ad2e  jmp     loc_1002AC3D
0x1002ad33  mov     eax, [ebp+var_C]
0x1002ad36  inc     edx
0x1002ad37  cmp     edx, [eax]
0x1002ad39  jb      loc_1002AC7D
0x1002ad3f  jmp     loc_1002AC3A
0x1002ad44  test    edi, edi
0x1002ad46  jz      short loc_1002AD63
0x1002ad48  test    esi, esi
0x1002ad4a  jz      short loc_1002AD63
0x1002ad4c  mov     eax, esi
0x1002ad4e  shl     eax, 4
0x1002ad51  push    eax; Size
0x1002ad52  push    edi; Src
0x1002ad53  push    ebx; void *
0x1002ad54  call    _memmove
0x1002ad59  add     esp, 0Ch
0x1002ad5c  push    edi; Block
0x1002ad5d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002ad62  pop     ecx
0x1002ad63  mov     edi, esi
0x1002ad65  mov     edx, [ebp+var_4]
0x1002ad68  shl     edi, 4
0x1002ad6b  lea     esi, [ebp+var_30]
0x1002ad6e  add     edi, ebx
0x1002ad70  push    1
0x1002ad72  pop     eax
0x1002ad73  movsd
0x1002ad74  movsd
0x1002ad75  movsd
0x1002ad76  movsd
0x1002ad77  mov     esi, [ebp+var_8]
0x1002ad7a  mov     edi, [ebp+arg_0]
0x1002ad7d  inc     esi
0x1002ad7e  mov     [ebp+var_8], esi
0x1002ad81  cmp     [edi], esi
0x1002ad83  cmovz   edx, eax
0x1002ad86  mov     [ebp+var_4], edx
0x1002ad89  jmp     loc_1002AC40
```
