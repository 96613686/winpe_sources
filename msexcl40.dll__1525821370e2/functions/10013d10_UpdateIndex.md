# UpdateIndex

- ea: `0x10013d10`
- end: `0x10013ed3`
- name: `UpdateIndex`
- size: `451`
- prototype: `_DWORD *__userpurge@<eax>(int@<edx>, _DWORD *@<ecx>, int@<ebp>, unsigned int, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x10013ee0`
- `0x10013f50`
- `0x10014020`
- `0x10016fc0`
- `0x10017790`

## callees

- `0x1000dcc0`
- `0x1000df70`
- `0x10013c50`
- `0x10013d10`
- `0x10025f86`
- `0x1002611f`

## pseudocode

```c
_DWORD *__userpurge UpdateIndex@<eax>(int a1@<edx>, _DWORD *a2@<ecx>, int a3@<ebp>, unsigned int a4, int a5)
{
  bool v5; // zf
  unsigned int v6; // edi
  _DWORD *result; // eax
  _DWORD *v8; // esi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  signed int v12; // edx
  __m128i *v13; // eax
  unsigned int v14; // edi
  signed int v15; // ecx
  int v16; // edi
  __m128i v17; // [esp-30h] [ebp-3Ch]
  int v18; // [esp-1Ch] [ebp-28h]
  char *v19; // [esp-18h] [ebp-24h] BYREF
  _DWORD *v20; // [esp-14h] [ebp-20h]
  unsigned int v21; // [esp-10h] [ebp-1Ch]
  _DWORD *i; // [esp-Ch] [ebp-18h]
  __int16 v23; // [esp-8h] [ebp-14h] BYREF
  __int16 v24; // [esp-6h] [ebp-12h]
  _DWORD *v25; // [esp-4h] [ebp-10h]
  int v26; // [esp+0h] [ebp-Ch]
  void *v27; // [esp+4h] [ebp-8h]
  void *retaddr; // [esp+Ch] [ebp+0h]

  v26 = a3;
  v27 = retaddr;
  v5 = *a2 == 0;
  v6 = a4;
  v18 = a1;
  v20 = a2;
  v17 = _mm_shuffle_epi32(_mm_cvtsi32_si128(a4), 0);
  if ( v5 )
  {
    result = 0;
  }
  else
  {
    result = (_DWORD *)a2[12];
    a2 = (_DWORD *)a2[11];
    v20 = a2;
  }
  v8 = (_DWORD *)a2[16];
  for ( i = result; v8; v8 = (_DWORD *)*v8 )
  {
    v9 = v8[1];
    if ( v9 >= a1 )
      v8[1] = v6 + v9;
    v10 = v8[3];
    if ( v10 >= a1 )
      v8[3] = v6 + v10;
    result = i;
    if ( v8[4] >= a1 || v8 == i || !i )
    {
      if ( v8[9] )
      {
        if ( v8 == i )
          UpdateResidentIndex(a1, v6, a5);
        else
          UpdateResidentIndex(a1, v6, 1);
      }
      else
      {
        v5 = *a2 == 1;
        v11 = (int)a2;
        v25 = a2;
        if ( v5 )
        {
          v11 = a2[11];
          v25 = (_DWORD *)v11;
        }
        BFSetFilePosition(*(int **)(v11 + 20), 0, v8[4]);
        if ( !ExcelReadRecordHeader((int)v25, &v23) && v23 == 523 && !ExcelReadTotalRecord((int)v25, &v23, &v19) )
        {
          v12 = 0;
          v13 = (__m128i *)(v19 + 8);
          v14 = (unsigned int)(v24 - 8) >> 2;
          if ( v14 >= 0x10 )
          {
            v21 = (unsigned int)(v24 - 8) >> 2;
            v21 -= v14 & 0x8000000F;
            v15 = v21;
            do
            {
              v12 += 16;
              *v13 = _mm_add_epi32(*v13, v17);
              v13[1] = _mm_add_epi32(v13[1], v17);
              v13[2] = _mm_add_epi32(v13[2], v17);
              v13[3] = _mm_add_epi32(v13[3], v17);
              v13 += 4;
            }
            while ( v12 < v15 );
          }
          for ( ; v12 < (int)v14; ++v12 )
          {
            v13->m128i_i32[0] += a4;
            v13 = (__m128i *)((char *)v13 + 4);
          }
          v16 = (int)v25;
          BFSetFilePosition((int *)v25[5], 0, v8[4] + 4);
          BFWriteFile(*(_DWORD *)(v16 + 20), v19, v24);
          v6 = a4;
        }
      }
      result = (_DWORD *)v8[4];
      a1 = v18;
      a2 = v20;
      if ( (int)result >= v18 )
      {
        result = (_DWORD *)((char *)result + v6);
        v8[4] = result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x10013d10  mov     edi, edi
0x10013d12  push    ebx
0x10013d13  mov     ebx, esp
0x10013d15  sub     esp, 8
0x10013d18  and     esp, 0FFFFFFF0h
0x10013d1b  add     esp, 4
0x10013d1e  push    ebp
0x10013d1f  mov     ebp, [ebx+4]
0x10013d22  mov     [esp+0Ch+var_8], ebp
0x10013d26  mov     ebp, esp
0x10013d28  sub     esp, 38h
0x10013d2b  cmp     dword ptr [ecx], 0
0x10013d2e  push    esi
0x10013d2f  push    edi
0x10013d30  mov     edi, [ebx+8]
0x10013d33  mov     [ebp-1Ch], edx
0x10013d36  mov     [ebp-14h], ecx
0x10013d39  movd    xmm0, edi
0x10013d3d  pshufd  xmm0, xmm0, 0
0x10013d42  movaps  xmmword ptr [ebp-30h], xmm0
0x10013d46  jnz     short loc_10013D4C
0x10013d48  xor     eax, eax
0x10013d4a  jmp     short loc_10013D55
0x10013d4c  mov     eax, [ecx+30h]
0x10013d4f  mov     ecx, [ecx+2Ch]
0x10013d52  mov     [ebp-14h], ecx
0x10013d55  mov     esi, [ecx+40h]
0x10013d58  mov     [ebp-0Ch], eax
0x10013d5b  test    esi, esi
0x10013d5d  jz      loc_10013EC8
0x10013d63  mov     eax, [esi+4]
0x10013d66  cmp     eax, edx
0x10013d68  jl      short loc_10013D6F
0x10013d6a  add     eax, edi
0x10013d6c  mov     [esi+4], eax
0x10013d6f  mov     eax, [esi+0Ch]
0x10013d72  cmp     eax, edx
0x10013d74  jl      short loc_10013D7B
0x10013d76  add     eax, edi
0x10013d78  mov     [esi+0Ch], eax
0x10013d7b  mov     eax, [ebp-0Ch]
0x10013d7e  cmp     [esi+10h], edx
0x10013d81  jge     short loc_10013D8F
0x10013d83  cmp     esi, eax
0x10013d85  jz      short loc_10013D8F
0x10013d87  test    eax, eax
0x10013d89  jnz     loc_10013EBE
0x10013d8f  cmp     dword ptr [esi+24h], 0
0x10013d93  jnz     loc_10013E98
0x10013d99  cmp     dword ptr [ecx], 1
0x10013d9c  mov     eax, ecx
0x10013d9e  mov     [ebp-4], ecx
0x10013da1  jnz     short loc_10013DA9
0x10013da3  mov     eax, [ecx+2Ch]
0x10013da6  mov     [ebp-4], eax
0x10013da9  push    dword ptr [esi+10h]
0x10013dac  mov     ecx, [eax+14h]
0x10013daf  xor     edx, edx
0x10013db1  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10013db6  mov     ecx, [ebp-4]
0x10013db9  lea     edx, [ebp-8]
0x10013dbc  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x10013dc1  test    eax, eax
0x10013dc3  jnz     loc_10013EAC
0x10013dc9  mov     eax, 20Bh
0x10013dce  cmp     [ebp-8], ax
0x10013dd2  jnz     loc_10013EAC
0x10013dd8  mov     ecx, [ebp-4]
0x10013ddb  lea     eax, [ebp-18h]
0x10013dde  push    eax
0x10013ddf  lea     edx, [ebp-8]
0x10013de2  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x10013de7  test    eax, eax
0x10013de9  jnz     loc_10013EAC
0x10013def  movsx   edi, word ptr [ebp-6]
0x10013df3  xor     edx, edx
0x10013df5  mov     eax, [ebp-18h]
0x10013df8  add     eax, 8
0x10013dfb  lea     edi, [edi-8]
0x10013dfe  shr     edi, 2
0x10013e01  test    edi, edi
0x10013e03  jz      short loc_10013E5E
0x10013e05  cmp     edi, 10h
0x10013e08  jb      short loc_10013E5E
0x10013e0a  mov     ecx, edi
0x10013e0c  and     ecx, 8000000Fh
0x10013e12  jns     short loc_10013E19
0x10013e14  dec     ecx
0x10013e15  or      ecx, 0FFFFFFF0h
0x10013e18  inc     ecx
0x10013e19  movaps  xmm1, xmmword ptr [ebp-30h]
0x10013e1d  mov     [ebp-10h], edi
0x10013e20  sub     [ebp-10h], ecx
0x10013e23  mov     ecx, [ebp-10h]
0x10013e26  movups  xmm0, xmmword ptr [eax]
0x10013e29  add     edx, 10h
0x10013e2c  paddd   xmm0, xmm1
0x10013e30  movups  xmmword ptr [eax], xmm0
0x10013e33  movups  xmm0, xmmword ptr [eax+10h]
0x10013e37  paddd   xmm0, xmm1
0x10013e3b  movups  xmmword ptr [eax+10h], xmm0
0x10013e3f  movups  xmm0, xmmword ptr [eax+20h]
0x10013e43  paddd   xmm0, xmm1
0x10013e47  movups  xmmword ptr [eax+20h], xmm0
0x10013e4b  movups  xmm0, xmmword ptr [eax+30h]
0x10013e4f  paddd   xmm0, xmm1
0x10013e53  movups  xmmword ptr [eax+30h], xmm0
0x10013e57  add     eax, 40h ; '@'
0x10013e5a  cmp     edx, ecx
0x10013e5c  jl      short loc_10013E26
0x10013e5e  cmp     edx, edi
0x10013e60  jge     short loc_10013E6F
0x10013e62  mov     ecx, [ebx+8]
0x10013e65  add     [eax], ecx
0x10013e67  lea     eax, [eax+4]
0x10013e6a  inc     edx
0x10013e6b  cmp     edx, edi
0x10013e6d  jl      short loc_10013E65
0x10013e6f  mov     eax, [esi+10h]
0x10013e72  xor     edx, edx
0x10013e74  mov     edi, [ebp-4]
0x10013e77  add     eax, 4
0x10013e7a  push    eax
0x10013e7b  mov     ecx, [edi+14h]
0x10013e7e  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10013e83  movsx   eax, word ptr [ebp-6]
0x10013e87  mov     edx, [ebp-18h]
0x10013e8a  mov     ecx, [edi+14h]
0x10013e8d  push    eax
0x10013e8e  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10013e93  mov     edi, [ebx+8]
0x10013e96  jmp     short loc_10013EAC
0x10013e98  cmp     esi, eax
0x10013e9a  jnz     short loc_10013EA1
0x10013e9c  push    dword ptr [ebx+0Ch]
0x10013e9f  jmp     short loc_10013EA3
0x10013ea1  push    1
0x10013ea3  push    edi
0x10013ea4  push    edx
0x10013ea5  mov     edx, esi
0x10013ea7  call    UpdateResidentIndex
0x10013eac  mov     eax, [esi+10h]
0x10013eaf  mov     edx, [ebp-1Ch]
0x10013eb2  mov     ecx, [ebp-14h]
0x10013eb5  cmp     eax, edx
0x10013eb7  jl      short loc_10013EBE
0x10013eb9  add     eax, edi
0x10013ebb  mov     [esi+10h], eax
0x10013ebe  mov     esi, [esi]
0x10013ec0  test    esi, esi
0x10013ec2  jnz     loc_10013D63
0x10013ec8  pop     edi
0x10013ec9  pop     esi
0x10013eca  mov     esp, ebp
0x10013ecc  pop     ebp
0x10013ecd  mov     esp, ebx
0x10013ecf  pop     ebx
0x10013ed0  retn    8
```
