# Record::Replace(uint,uchar const *,uint,Err &)

- ea: `0x10043d00`
- end: `0x10043f7e`
- name: `?Replace@Record@@QAEXIPBEIAAVErr@@@Z`
- size: `638`
- prototype: `void __thiscall(Record *__hidden this, unsigned int, const unsigned __int8 *Src, size_t Size, struct Err *)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x10016890`
- `0x10016e20`
- `0x100177a0`
- `0x10017c60`
- `0x1003ee10`
- `0x1003f550`

## callees

- `0x10025ee0`
- `0x10043c60`
- `0x10043d00`
- `0x1005e7e8`
- `0x1005f07c`

## pseudocode

```c
void __thiscall Record::Replace(Record *this, unsigned int a2, const unsigned __int8 *Src, size_t Size, void **a5)
{
  int v5; // eax
  unsigned __int8 *v6; // esi
  unsigned int v7; // ecx
  unsigned __int8 *v8; // edi
  unsigned int v9; // ebx
  unsigned int v10; // esi
  int v11; // eax
  unsigned int v12; // ebx
  unsigned __int8 *v13; // edi
  unsigned __int8 *v14; // eax
  Record *v15; // edx
  unsigned int v16; // esi
  size_t v17; // eax
  size_t v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ebx
  unsigned __int8 *v21; // edi
  unsigned __int8 *v22; // ecx
  unsigned __int8 *v23; // ecx
  unsigned __int8 v24; // al
  unsigned int j; // esi
  unsigned __int8 *v26; // eax
  unsigned __int8 *v27; // [esp+0h] [ebp-2Ch]
  size_t v28; // [esp+4h] [ebp-28h]
  unsigned __int8 *v29; // [esp+8h] [ebp-24h]
  unsigned int v30; // [esp+Ch] [ebp-20h]
  unsigned int v31; // [esp+10h] [ebp-1Ch]
  int i; // [esp+18h] [ebp-14h]
  unsigned int v34; // [esp+1Ch] [ebp-10h]
  unsigned int v35; // [esp+20h] [ebp-Ch]
  unsigned __int8 *v36; // [esp+24h] [ebp-8h]
  unsigned __int8 *v37; // [esp+24h] [ebp-8h]
  unsigned __int8 v38; // [esp+2Bh] [ebp-1h]

  if ( !*((_DWORD *)this + 3) && (*((_DWORD *)this + 2) < 4u || !*(_DWORD *)this) )
  {
    Err::SetError(a5, -1206, this);
    return;
  }
  v5 = *((_DWORD *)this + 1);
  v6 = *(unsigned __int8 **)this;
  v7 = (unsigned int)(v5 + 255) >> 8;
  v8 = v6 - 1;
  v35 = v7;
  v9 = ((unsigned int)*v6 + 7) >> 3;
  v10 = 1;
  v11 = v5 - v9;
  v30 = v9;
  v12 = a2;
  v13 = &v8[v11];
  v36 = &v13[-v7];
  v14 = &v13[-v7 - a2];
  v38 = *v14;
  v15 = this;
  for ( i = (unsigned __int8)(*(v14 - 1) - *v14); v10 < v7; ++v10 )
  {
    if ( v13[-v10] > a2 )
      break;
  }
  v16 = v10 - 1;
  v17 = Size - i;
  v27 = (unsigned __int8 *)(*(_DWORD *)this + (v16 << 8) + v38);
  v18 = Size - i + *((_DWORD *)this + 1);
  v28 = Size - i;
  if ( v18 > 0x7DC )
  {
    if ( (int)*a5 < 8 )
    {
      if ( ((unsigned int)*a5 & 0xFFFFFFFE) != 0 )
      {
        if ( a5[3] )
          operator delete[](a5[3]);
        if ( a5[4] )
          operator delete[](a5[4]);
      }
      *a5 = (void *)8;
      a5[1] = (void *)-1026;
      a5[2] = 0;
      a5[3] = 0;
      a5[4] = 0;
    }
    return;
  }
  if ( !v17 )
    goto LABEL_35;
  v19 = (v18 + 255) >> 8;
  v31 = v19;
  if ( v19 != v35 )
  {
    v12 = a2;
    if ( v17 + v19 + *((_DWORD *)this + 1) - v35 <= 0x7DC )
    {
      v29 = v36 + 1;
      v34 = v19 - v35;
      if ( v19 >= v35 )
        Record::MemMove(this, &v36[v34 + 1], v29, v30 + v35, (struct Err *)a5);
      else
        memcpy(v29, &v13[-v19 + 1], v19 + v30);
      v15 = this;
      *((_DWORD *)this + 1) += v31 - v35;
      v13 += v34;
    }
    else
    {
      Err::SetError(a5, -1026, v19);
      v15 = this;
    }
  }
  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    Record::MemMove(v15, &v27[Size], &v27[i], *((_DWORD *)v15 + 1) + *(_DWORD *)v15 - (_DWORD)v27 - i, (struct Err *)a5);
    if ( (*(_BYTE *)a5 & 8) == 0 )
    {
      v20 = v12 + 1;
      v21 = &v13[v28];
      v22 = &v36[v28];
      v37 = &v36[v28];
      *((_DWORD *)this + 1) += v28;
      if ( v20 <= *v21 )
      {
        while ( 1 )
        {
          v23 = &v22[-v20];
          v24 = v28 + *v23;
          *v23 = v24;
          if ( v24 < v23[1] )
          {
            if ( ++v16 >= v31 )
            {
              Err::SetError(a5, -1206, v23);
              return;
            }
            v21[-v16] = v20;
          }
          if ( ++v20 > *v21 )
            break;
          v22 = v37;
        }
      }
      for ( j = v16 + 1; j < v31; *v26 = -1 )
        v26 = &v21[-j++];
LABEL_35:
      if ( (*(_BYTE *)a5 & 8) == 0 )
        memcpy(v27, Src, Size);
    }
  }
}

```

## disassembly

```asm
0x10043d00  mov     edi, edi
0x10043d02  push    ebp
0x10043d03  mov     ebp, esp
0x10043d05  sub     esp, 2Ch
0x10043d08  mov     edx, ecx
0x10043d0a  mov     [ebp+var_18], edx
0x10043d0d  cmp     dword ptr [edx+0Ch], 0
0x10043d11  jnz     short loc_10043D32
0x10043d13  cmp     dword ptr [edx+8], 4
0x10043d17  jb      short loc_10043D1E
0x10043d19  cmp     dword ptr [edx], 0
0x10043d1c  jnz     short loc_10043D32
0x10043d1e  push    ecx
0x10043d1f  mov     ecx, [ebp+arg_C]
0x10043d22  push    0FFFFFB4Ah
0x10043d27  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10043d2c  mov     esp, ebp
0x10043d2e  pop     ebp
0x10043d2f  retn    10h
0x10043d32  mov     eax, [edx+4]
0x10043d35  push    ebx
0x10043d36  push    esi
0x10043d37  mov     esi, [edx]
0x10043d39  lea     ecx, [eax+0FFh]
0x10043d3f  push    edi
0x10043d40  shr     ecx, 8
0x10043d43  movzx   ebx, byte ptr [esi]
0x10043d46  lea     edi, [esi-1]
0x10043d49  add     ebx, 7
0x10043d4c  mov     [ebp+var_C], ecx
0x10043d4f  shr     ebx, 3
0x10043d52  mov     esi, 1
0x10043d57  sub     eax, ebx
0x10043d59  mov     [ebp+var_20], ebx
0x10043d5c  mov     ebx, [ebp+arg_0]
0x10043d5f  add     edi, eax
0x10043d61  mov     eax, edi
0x10043d63  sub     eax, ecx
0x10043d65  mov     [ebp+var_8], eax
0x10043d68  sub     eax, ebx
0x10043d6a  mov     dl, [eax]
0x10043d6c  mov     al, [eax-1]
0x10043d6f  sub     al, dl
0x10043d71  mov     [ebp+var_1], dl
0x10043d74  mov     edx, [ebp+var_18]
0x10043d77  movzx   eax, al
0x10043d7a  mov     [ebp+var_14], eax
0x10043d7d  cmp     ecx, esi
0x10043d7f  jbe     short loc_10043D91
0x10043d81  mov     eax, edi
0x10043d83  sub     eax, esi
0x10043d85  movzx   eax, byte ptr [eax]
0x10043d88  cmp     eax, ebx
0x10043d8a  ja      short loc_10043D91
0x10043d8c  inc     esi
0x10043d8d  cmp     esi, ecx
0x10043d8f  jb      short loc_10043D81
0x10043d91  movzx   ecx, [ebp+var_1]
0x10043d95  dec     esi
0x10043d96  mov     eax, esi
0x10043d98  shl     eax, 8
0x10043d9b  add     eax, [edx]
0x10043d9d  add     ecx, eax
0x10043d9f  mov     eax, [ebp+Size]
0x10043da2  sub     eax, [ebp+var_14]
0x10043da5  mov     [ebp+var_2C], ecx
0x10043da8  mov     ecx, [edx+4]
0x10043dab  add     ecx, eax
0x10043dad  mov     [ebp+var_28], eax
0x10043db0  cmp     ecx, 7DCh
0x10043db6  jbe     short loc_10043E18
0x10043db8  mov     esi, [ebp+arg_C]
0x10043dbb  mov     eax, [esi]
0x10043dbd  cmp     eax, 8
0x10043dc0  jge     loc_10043F75
0x10043dc6  test    eax, 0FFFFFFFEh
0x10043dcb  jz      short loc_10043DED
0x10043dcd  mov     eax, [esi+0Ch]
0x10043dd0  test    eax, eax
0x10043dd2  jz      short loc_10043DDD
0x10043dd4  push    eax; Block
0x10043dd5  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10043dda  add     esp, 4
0x10043ddd  mov     eax, [esi+10h]
0x10043de0  test    eax, eax
0x10043de2  jz      short loc_10043DED
0x10043de4  push    eax; Block
0x10043de5  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10043dea  add     esp, 4
0x10043ded  mov     dword ptr [esi], 8
0x10043df3  pop     edi
0x10043df4  mov     dword ptr [esi+4], 0FFFFFBFEh
0x10043dfb  mov     dword ptr [esi+8], 0
0x10043e02  mov     dword ptr [esi+0Ch], 0
0x10043e09  mov     dword ptr [esi+10h], 0
0x10043e10  pop     esi
0x10043e11  pop     ebx
0x10043e12  mov     esp, ebp
0x10043e14  pop     ebp
0x10043e15  retn    10h
0x10043e18  test    eax, eax
0x10043e1a  jz      loc_10043F5C
0x10043e20  add     ecx, 0FFh
0x10043e26  shr     ecx, 8
0x10043e29  mov     [ebp+var_1C], ecx
0x10043e2c  cmp     ecx, [ebp+var_C]
0x10043e2f  jz      short loc_10043EB0
0x10043e31  mov     ebx, [edx+4]
0x10043e34  sub     ebx, [ebp+var_C]
0x10043e37  add     ebx, ecx
0x10043e39  add     ebx, eax
0x10043e3b  cmp     ebx, 7DCh
0x10043e41  mov     ebx, [ebp+arg_0]
0x10043e44  jbe     short loc_10043E59
0x10043e46  push    ecx
0x10043e47  mov     ecx, [ebp+arg_C]
0x10043e4a  push    0FFFFFBFEh
0x10043e4f  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10043e54  mov     edx, [ebp+var_18]
0x10043e57  jmp     short loc_10043EB0
0x10043e59  mov     eax, [ebp+var_8]
0x10043e5c  inc     eax
0x10043e5d  mov     [ebp+var_10], ecx
0x10043e60  mov     [ebp+var_24], eax
0x10043e63  mov     eax, [ebp+var_C]
0x10043e66  sub     [ebp+var_10], eax
0x10043e69  cmp     ecx, eax
0x10043e6b  jnb     short loc_10043E86
0x10043e6d  mov     eax, [ebp+var_20]
0x10043e70  add     eax, ecx
0x10043e72  push    eax; Size
0x10043e73  mov     eax, edi
0x10043e75  sub     eax, ecx
0x10043e77  inc     eax
0x10043e78  push    eax; Src
0x10043e79  push    [ebp+var_24]; void *
0x10043e7c  call    _memcpy
0x10043e81  add     esp, 0Ch
0x10043e84  jmp     short loc_10043EA1
0x10043e86  push    [ebp+arg_C]; struct Err *
0x10043e89  add     eax, [ebp+var_20]
0x10043e8c  mov     ecx, [ebp+var_10]
0x10043e8f  push    eax; Size
0x10043e90  push    [ebp+var_24]; Src
0x10043e93  mov     eax, [ebp+var_8]
0x10043e96  inc     ecx
0x10043e97  add     eax, ecx
0x10043e99  mov     ecx, edx; this
0x10043e9b  push    eax; unsigned __int8 *
0x10043e9c  call    ?MemMove@Record@@AAEXPAEPBEIAAVErr@@@Z; Record::MemMove(uchar *,uchar const *,uint,Err &)
0x10043ea1  mov     edx, [ebp+var_18]
0x10043ea4  mov     eax, [ebp+var_1C]
0x10043ea7  sub     eax, [ebp+var_C]
0x10043eaa  add     [edx+4], eax
0x10043ead  add     edi, [ebp+var_10]
0x10043eb0  mov     eax, [ebp+arg_C]
0x10043eb3  test    byte ptr [eax], 8
0x10043eb6  jnz     loc_10043F75
0x10043ebc  mov     ecx, [ebp+var_2C]
0x10043ebf  push    eax; struct Err *
0x10043ec0  mov     eax, [edx]
0x10043ec2  sub     eax, ecx
0x10043ec4  sub     eax, [ebp+var_14]
0x10043ec7  add     eax, [edx+4]
0x10043eca  push    eax; Size
0x10043ecb  mov     eax, [ebp+var_14]
0x10043ece  add     eax, ecx
0x10043ed0  push    eax; Src
0x10043ed1  mov     eax, [ebp+var_28]
0x10043ed4  add     eax, ecx
0x10043ed6  mov     ecx, edx; this
0x10043ed8  add     eax, [ebp+var_14]
0x10043edb  push    eax; unsigned __int8 *
0x10043edc  call    ?MemMove@Record@@AAEXPAEPBEIAAVErr@@@Z; Record::MemMove(uchar *,uchar const *,uint,Err &)
0x10043ee1  mov     eax, [ebp+arg_C]
0x10043ee4  test    byte ptr [eax], 8
0x10043ee7  jnz     loc_10043F75
0x10043eed  mov     edx, [ebp+var_28]
0x10043ef0  inc     ebx
0x10043ef1  mov     eax, [ebp+var_18]
0x10043ef4  add     edi, edx
0x10043ef6  mov     ecx, [ebp+var_8]
0x10043ef9  add     ecx, edx
0x10043efb  mov     [ebp+var_8], ecx
0x10043efe  add     [eax+4], edx
0x10043f01  movzx   eax, byte ptr [edi]
0x10043f04  cmp     ebx, eax
0x10043f06  ja      short loc_10043F45
0x10043f08  sub     ecx, ebx
0x10043f0a  mov     al, [ecx]
0x10043f0c  add     al, dl
0x10043f0e  mov     [ecx], al
0x10043f10  cmp     al, [ecx+1]
0x10043f13  jnb     short loc_10043F21
0x10043f15  inc     esi
0x10043f16  cmp     esi, [ebp+var_1C]
0x10043f19  jnb     short loc_10043F2E
0x10043f1b  mov     eax, edi
0x10043f1d  sub     eax, esi
0x10043f1f  mov     [eax], bl
0x10043f21  movzx   eax, byte ptr [edi]
0x10043f24  inc     ebx
0x10043f25  cmp     ebx, eax
0x10043f27  ja      short loc_10043F45
0x10043f29  mov     ecx, [ebp+var_8]
0x10043f2c  jmp     short loc_10043F08
0x10043f2e  push    ecx
0x10043f2f  mov     ecx, [ebp+arg_C]
0x10043f32  push    0FFFFFB4Ah
0x10043f37  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10043f3c  pop     edi
0x10043f3d  pop     esi
0x10043f3e  pop     ebx
0x10043f3f  mov     esp, ebp
0x10043f41  pop     ebp
0x10043f42  retn    10h
0x10043f45  mov     ecx, [ebp+var_1C]
0x10043f48  inc     esi
0x10043f49  cmp     esi, ecx
0x10043f4b  jnb     short loc_10043F5C
0x10043f4d  nop     dword ptr [eax]
0x10043f50  mov     eax, edi
0x10043f52  sub     eax, esi
0x10043f54  inc     esi
0x10043f55  mov     byte ptr [eax], 0FFh
0x10043f58  cmp     esi, ecx
0x10043f5a  jb      short loc_10043F50
0x10043f5c  mov     eax, [ebp+arg_C]
0x10043f5f  test    byte ptr [eax], 8
0x10043f62  jnz     short loc_10043F75
0x10043f64  push    [ebp+Size]; Size
0x10043f67  push    [ebp+Src]; Src
0x10043f6a  push    [ebp+var_2C]; void *
0x10043f6d  call    _memcpy
0x10043f72  add     esp, 0Ch
0x10043f75  pop     edi
0x10043f76  pop     esi
0x10043f77  pop     ebx
0x10043f78  mov     esp, ebp
0x10043f7a  pop     ebp
0x10043f7b  retn    10h
```
