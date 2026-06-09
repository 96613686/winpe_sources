# CImpIAccessor::FInit(int)

- ea: `0x1000bea0`
- end: `0x1000c0be`
- name: `?FInit@CImpIAccessor@@QAGJH@Z`
- size: `542`
- prototype: `int(CImpIAccessor *__hidden this, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x10013f50`
- `0x10028340`

## callees

- `0x1000bb80`
- `0x1000bea0`
- `0x1000c750`
- `0x1000cc30`
- `0x1001c6d0`
- `0x1004ce5d`
- `0x1004dc8d`

## import_xrefs

- `msvcrt!malloc` at `0x1000bf0a`
- `msvcrt!malloc` at `0x1000bf0a`

## pseudocode

```c
int __fastcall CImpIAccessor::FInit(_DWORD *a1, int a2)
{
  _DWORD *v2; // ebx
  _DWORD *v4; // eax
  _DWORD *v5; // esi
  void *v6; // eax
  int v7; // ecx
  int v8; // edx
  _DWORD **v9; // ecx
  int v10; // edi
  unsigned int i; // edi
  _DWORD *v13; // esi
  CImpIAccessor *v14; // ecx
  unsigned int v15; // ecx
  int v16; // edx
  unsigned int *v17; // esi
  int v18; // eax
  _DWORD *v19; // ebx
  int v20; // eax
  int v21; // edx
  int v22; // ecx
  unsigned int v23; // eax
  size_t v24; // [esp-4h] [ebp-24h]
  unsigned int *v25; // [esp+0h] [ebp-20h]
  int *v26; // [esp+0h] [ebp-20h]
  struct CExtBuffer *v27; // [esp+4h] [ebp-1Ch]
  unsigned int v28; // [esp+4h] [ebp-1Ch]
  int v29; // [esp+Ch] [ebp-14h] BYREF
  int v30; // [esp+10h] [ebp-10h]
  unsigned int v31; // [esp+14h] [ebp-Ch]
  _DWORD *v32; // [esp+18h] [ebp-8h]
  int v33; // [esp+1Ch] [ebp-4h] BYREF

  v2 = a1;
  v32 = a1;
  v4 = operator new(0x28u);
  v5 = v4;
  v29 = (int)v4;
  if ( !v4 )
  {
    v2[5] = 0;
    return -2147024882;
  }
  v4[5] = 1;
  *((_BYTE *)v4 + 32) = -1;
  v4[4] = v4 + 8;
  v4[6] = 0;
  v4[9] = 1;
  v4[7] = 1;
  v4[1] = 0;
  v4[2] = 0;
  v2[5] = v4;
  *v4 = 4;
  v6 = _malloc(0x100u);
  v5[2] = v6;
  if ( !v6 )
    return -2147024882;
  v24 = v5[5];
  v5[1] = 64;
  memset((void *)v5[4], -1, v24);
  v7 = v2[2];
  v8 = v2[5];
  if ( a2 )
  {
    v2[4] |= 1u;
    *(_DWORD *)(v7 + 100) = v8;
    v9 = *(_DWORD ***)(v2[2] + 60);
    if ( v9
      && ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**v9)(**v9, v9, &IID_IAccessor, &v33) >= 0
      && v33
      && (v10 = CImpIAccessor::CopyAccessors((CImpIAccessor *)v25, v27),
          (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v33 + 8))(*(_DWORD *)(*(_DWORD *)v33 + 8), v33),
          v10 < 0) )
    {
      return v10;
    }
    else
    {
      CExtBuffer::GetNextUsedItem((CExtBuffer *)1, v25, (unsigned int)v27);
      for ( i = v31; i; v2 = v32 )
      {
        v13 = (_DWORD *)v2[5];
        v14 = (CImpIAccessor *)v13[6];
        if ( i > (unsigned int)v14 + 8 * v13[5] - 1
          || (v15 = i - (_DWORD)v14,
              v16 = v15 & 7,
              v14 = (CImpIAccessor *)(v15 >> 3),
              (*((_BYTE *)v14 + v13[4]) & *((_BYTE *)&Bitmap::ThisBit + v16)) != 0) )
        {
          v17 = 0;
        }
        else
        {
          v17 = *(unsigned int **)(v13[2] + 4 * i);
        }
        v18 = CImpIAccessor::ValidateAccessor(
                *v17,
                (int)v2,
                v14,
                v17[9],
                (unsigned int)(v17 + 10),
                (unsigned int)v14,
                0,
                &v29,
                (unsigned int *const)v14,
                v26,
                v28);
        if ( v18 < 0 )
        {
          v17[1] = v18;
          *v17 = 0;
          v17[2] = 0;
        }
        v19 = (_DWORD *)v2[5];
        i = 0;
        v29 = 0;
        v20 = v19[5];
        v21 = v19[6];
        v30 = v21;
        v22 = 8 * v20 - 1;
        v23 = v19[3];
        v31 = v21 + v22;
        if ( v23 <= v21 + v22 )
        {
          i = v23;
          while ( 1 )
          {
            v23 = i;
            if ( (*(_BYTE *)(((i - v21) >> 3) + v19[4]) & *((_BYTE *)&Bitmap::ThisBit + ((i - v21) & 7))) == 0 )
              break;
            v21 = v30;
            v23 = i + 1;
            i = v23;
            v19[3] = v23;
            if ( v23 > v31 )
            {
              i = v29;
              break;
            }
          }
        }
        v19[3] = v23 + 1;
      }
      v2[4] |= 2u;
      return 0;
    }
  }
  else
  {
    *(_DWORD *)(v7 + 48) = v8;
    return 0;
  }
}

```

## disassembly

```asm
0x1000bea0  mov     edi, edi
0x1000bea2  push    ebp
0x1000bea3  mov     ebp, esp
0x1000bea5  sub     esp, 14h
0x1000bea8  push    ebx
0x1000bea9  push    esi; unsigned int
0x1000beaa  push    edi; int *
0x1000beab  mov     ebx, ecx
0x1000bead  mov     edi, edx
0x1000beaf  push    28h ; '('; Size
0x1000beb1  mov     [ebp+var_8], ebx
0x1000beb4  call    ??2@YAPAXI@Z; operator new(uint)
0x1000beb9  mov     esi, eax
0x1000bebb  add     esp, 4
0x1000bebe  mov     [ebp+var_14], esi
0x1000bec1  test    esi, esi
0x1000bec3  jz      loc_1000C0AB
0x1000bec9  lea     ecx, [esi+20h]
0x1000becc  mov     dword ptr [esi+14h], 1
0x1000bed3  mov     byte ptr [ecx], 0FFh
0x1000bed6  mov     [esi+10h], ecx
0x1000bed9  mov     dword ptr [esi+18h], 0
0x1000bee0  mov     dword ptr [esi+24h], 1
0x1000bee7  mov     dword ptr [esi+1Ch], 1
0x1000beee  mov     dword ptr [esi+4], 0
0x1000bef5  mov     dword ptr [esi+8], 0
0x1000befc  mov     [ebx+14h], esi
0x1000beff  push    100h; Size
0x1000bf04  mov     dword ptr [esi], 4
0x1000bf0a  call    ds:__imp__malloc
0x1000bf10  add     esp, 4
0x1000bf13  mov     [esi+8], eax
0x1000bf16  test    eax, eax
0x1000bf18  jz      loc_1000C0B2
0x1000bf1e  push    dword ptr [esi+14h]; Size
0x1000bf21  mov     dword ptr [esi+4], 40h ; '@'
0x1000bf28  push    0FFFFFFFFh; Val
0x1000bf2a  push    dword ptr [esi+10h]; void *
0x1000bf2d  call    _memset
0x1000bf32  mov     ecx, [ebx+8]
0x1000bf35  add     esp, 0Ch
0x1000bf38  mov     edx, [ebx+14h]
0x1000bf3b  test    edi, edi
0x1000bf3d  jz      loc_1000C09F
0x1000bf43  or      dword ptr [ebx+10h], 1
0x1000bf47  mov     [ecx+64h], edx
0x1000bf4a  mov     eax, [ebx+8]
0x1000bf4d  mov     ecx, [eax+3Ch]
0x1000bf50  test    ecx, ecx
0x1000bf52  jz      short loc_1000BFA1
0x1000bf54  mov     eax, [ecx]
0x1000bf56  mov     esi, [eax]
0x1000bf58  lea     eax, [ebp+var_4]
0x1000bf5b  push    eax
0x1000bf5c  push    offset _IID_IAccessor
0x1000bf61  push    ecx
0x1000bf62  mov     ecx, esi
0x1000bf64  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000bf6a  call    esi
0x1000bf6c  test    eax, eax
0x1000bf6e  js      short loc_1000BFA1
0x1000bf70  mov     ecx, [ebp+var_4]
0x1000bf73  test    ecx, ecx
0x1000bf75  jz      short loc_1000BFA1
0x1000bf77  mov     edx, [ebx+14h]
0x1000bf7a  call    ?CopyAccessors@CImpIAccessor@@AAGJPAVCExtBuffer@@@Z; CImpIAccessor::CopyAccessors(CExtBuffer *)
0x1000bf7f  mov     ecx, [ebp+var_4]
0x1000bf82  mov     edi, eax
0x1000bf84  push    ecx
0x1000bf85  mov     edx, [ecx]
0x1000bf87  mov     esi, [edx+8]
0x1000bf8a  mov     ecx, esi
0x1000bf8c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000bf92  call    esi
0x1000bf94  test    edi, edi
0x1000bf96  jns     short loc_1000BFA1
0x1000bf98  mov     eax, edi
0x1000bf9a  pop     edi
0x1000bf9b  pop     esi
0x1000bf9c  pop     ebx
0x1000bf9d  mov     esp, ebp
0x1000bf9f  pop     ebp
0x1000bfa0  retn
0x1000bfa1  mov     ecx, [ebx+14h]
0x1000bfa4  lea     edx, [ebp+var_C]
0x1000bfa7  push    1; this
0x1000bfa9  call    ?GetNextUsedItem@CExtBuffer@@QAGXAAKK@Z; CExtBuffer::GetNextUsedItem(ulong &,ulong)
0x1000bfae  mov     edi, [ebp+var_C]
0x1000bfb1  test    edi, edi
0x1000bfb3  jz      loc_1000C092
0x1000bfb9  nop     dword ptr [eax+00000000h]
0x1000bfc0  mov     esi, [ebx+14h]
0x1000bfc3  mov     eax, [esi+14h]
0x1000bfc6  mov     ecx, [esi+18h]
0x1000bfc9  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1000bfd0  add     eax, ecx
0x1000bfd2  cmp     edi, eax
0x1000bfd4  ja      short loc_1000BFF8
0x1000bfd6  mov     eax, [esi+10h]
0x1000bfd9  mov     edx, edi
0x1000bfdb  sub     edx, ecx
0x1000bfdd  mov     ecx, edx
0x1000bfdf  and     edx, 7
0x1000bfe2  shr     ecx, 3
0x1000bfe5  mov     al, [ecx+eax]
0x1000bfe8  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1000bfee  jnz     short loc_1000BFF8
0x1000bff0  mov     eax, [esi+8]
0x1000bff3  mov     esi, [eax+edi*4]
0x1000bff6  jmp     short loc_1000BFFA
0x1000bff8  xor     esi, esi
0x1000bffa  mov     edx, [esi]
0x1000bffc  lea     eax, [ebp+var_14]
0x1000bfff  push    ecx; unsigned int *
0x1000c000  push    eax; int *
0x1000c001  push    0; struct tagDBBINDING *
0x1000c003  push    ecx; unsigned int
0x1000c004  lea     eax, [esi+28h]
0x1000c007  push    eax; unsigned int
0x1000c008  push    dword ptr [esi+24h]; unsigned int
0x1000c00b  push    ecx; this
0x1000c00c  mov     ecx, ebx
0x1000c00e  call    ?ValidateAccessor@CImpIAccessor@@AAGJKKKQBUtagDBBINDING@@PAJQAKPAHK@Z; CImpIAccessor::ValidateAccessor(ulong,ulong,ulong,tagDBBINDING const * const,long *,ulong * const,int *,ulong)
0x1000c013  test    eax, eax
0x1000c015  jns     short loc_1000C027
0x1000c017  mov     [esi+4], eax
0x1000c01a  mov     dword ptr [esi], 0
0x1000c020  mov     dword ptr [esi+8], 0
0x1000c027  mov     ebx, [ebx+14h]
0x1000c02a  xor     edi, edi
0x1000c02c  mov     [ebp+var_14], edi
0x1000c02f  mov     eax, [ebx+14h]
0x1000c032  mov     edx, [ebx+18h]
0x1000c035  mov     [ebp+var_10], edx
0x1000c038  lea     ecx, ds:0FFFFFFFFh[eax*8]
0x1000c03f  mov     eax, [ebx+0Ch]
0x1000c042  add     ecx, edx
0x1000c044  mov     [ebp+var_C], ecx
0x1000c047  cmp     eax, ecx
0x1000c049  ja      short loc_1000C083
0x1000c04b  mov     edi, eax
0x1000c04d  nop     dword ptr [eax]
0x1000c050  mov     ecx, [ebx+10h]
0x1000c053  mov     esi, edi
0x1000c055  sub     esi, edx
0x1000c057  mov     eax, edi
0x1000c059  mov     edx, esi
0x1000c05b  and     esi, 7
0x1000c05e  shr     edx, 3
0x1000c061  mov     cl, [edx+ecx]
0x1000c064  test    ds:?ThisBit@Bitmap@@1QBEB[esi], cl; uchar const * const Bitmap::ThisBit
0x1000c06a  jz      short loc_1000C081
0x1000c06c  mov     edx, [ebp+var_10]
0x1000c06f  lea     eax, [edi+1]
0x1000c072  mov     edi, eax
0x1000c074  mov     [ebx+0Ch], eax
0x1000c077  cmp     eax, [ebp+var_C]
0x1000c07a  jbe     short loc_1000C050
0x1000c07c  mov     edi, [ebp+var_14]
0x1000c07f  jmp     short loc_1000C083
0x1000c081  mov     edi, eax
0x1000c083  inc     eax
0x1000c084  mov     [ebx+0Ch], eax
0x1000c087  mov     ebx, [ebp+var_8]
0x1000c08a  test    edi, edi
0x1000c08c  jnz     loc_1000BFC0
0x1000c092  or      dword ptr [ebx+10h], 2
0x1000c096  xor     eax, eax
0x1000c098  pop     edi
0x1000c099  pop     esi
0x1000c09a  pop     ebx
0x1000c09b  mov     esp, ebp
0x1000c09d  pop     ebp
0x1000c09e  retn
0x1000c09f  pop     edi
0x1000c0a0  pop     esi
0x1000c0a1  mov     [ecx+30h], edx
0x1000c0a4  xor     eax, eax
0x1000c0a6  pop     ebx
0x1000c0a7  mov     esp, ebp
0x1000c0a9  pop     ebp
0x1000c0aa  retn
0x1000c0ab  mov     dword ptr [ebx+14h], 0
0x1000c0b2  mov     eax, 8007000Eh
0x1000c0b7  pop     edi
0x1000c0b8  pop     esi
0x1000c0b9  pop     ebx
0x1000c0ba  mov     esp, ebp
0x1000c0bc  pop     ebp
0x1000c0bd  retn
```
