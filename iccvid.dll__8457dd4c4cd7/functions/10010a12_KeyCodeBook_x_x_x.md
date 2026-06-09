# KeyCodeBook(x,x,x)

- ea: `0x10010a12`
- end: `0x10010c90`
- name: `_KeyCodeBook@12`
- size: `638`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x10004b3b`
- `0x10010735`

## callees

- `0x100041c0`
- `0x10010a12`
- `0x10011ce4`
- `0x10012b50`

## pseudocode

```c
int __thiscall KeyCodeBook(void *this, int *a2)
{
  int *v2; // ebx
  int v3; // edx
  int v4; // edi
  int v5; // esi
  int v6; // ecx
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  unsigned __int8 *v10; // edx
  int v11; // ecx
  int v12; // ebx
  int v13; // esi
  int v14; // edx
  unsigned int v15; // edi
  int v16; // ecx
  unsigned __int8 v17; // al
  int v18; // esi
  int v19; // ecx
  int v20; // eax
  int v21; // edx
  int v22; // esi
  int v23; // esi
  unsigned __int8 v24; // cl
  char v25; // ch
  int v26; // eax
  int v27; // eax
  int v28; // edi
  int v29; // edx
  int v30; // eax
  __int16 v31; // ax
  int v32; // edx
  int v33; // esi
  int result; // eax
  char v35; // [esp+Fh] [ebp-61h]
  int v36; // [esp+10h] [ebp-60h]
  int v37; // [esp+10h] [ebp-60h]
  int v38; // [esp+14h] [ebp-5Ch]
  unsigned __int8 *v39; // [esp+18h] [ebp-58h]
  int v40; // [esp+1Ch] [ebp-54h]
  int v41; // [esp+20h] [ebp-50h]
  int *v42; // [esp+24h] [ebp-4Ch] BYREF
  int v43; // [esp+28h] [ebp-48h]
  void *v44; // [esp+2Ch] [ebp-44h]
  _DWORD v45[15]; // [esp+30h] [ebp-40h]

  v2 = a2;
  v3 = 0;
  v44 = this;
  v4 = *((__int16 *)a2 + 4);
  v5 = a2[3];
  v6 = *a2;
  v42 = a2;
  v38 = v4;
  v41 = v5;
  do
  {
    v7 = v6;
    v6 += 460;
    *(_BYTE *)(v7 + 6) = v3++;
    *(_BYTE *)(v7 + 7) = 1;
    *(_DWORD *)(v7 + 8) = v6;
  }
  while ( v3 < 256 );
  v8 = 5;
  v9 = 5;
  do
    v45[--v9 + 10] = 0;
  while ( v9 );
  v10 = (unsigned __int8 *)a2[1];
  v39 = v10;
  v36 = 0;
  if ( v5 > 0 )
  {
    do
    {
      v11 = v10[3];
      v12 = v10[2];
      v13 = v10[1];
      v14 = *v10;
      v15 = (unsigned int)(v12 + v14 + v13 + v11 + 2) >> 2;
      v16 = dword_1000170C[v15 - v11]
          + dword_1000170C[v15 - v12]
          + dword_1000170C[v15 - v13]
          + dword_1000170C[v15 - v14];
      if ( (v16 & 0xE000) != 0 )
      {
        v17 = 4;
      }
      else if ( (v16 & 0x1C00) != 0 )
      {
        v17 = 3;
      }
      else if ( (v16 & 0x380) != 0 )
      {
        v17 = 2;
      }
      else
      {
        v17 = (v16 & 0x70) != 0;
      }
      v18 = v17;
      v39[7] = v17;
      v19 = v45[v17 + 10];
      v45[v17 + 10] = v19 + 1;
      v20 = v36;
      if ( !v19 )
      {
        v45[v18 + 5] = v36;
        v45[v18] = v39;
      }
      v10 = v39 + 8;
      ++v36;
      v39 += 8;
    }
    while ( v20 + 1 < v41 );
    v2 = v42;
    v4 = v38;
    v8 = 5;
  }
  v21 = 0;
  do
  {
    v22 = v45[--v8 + 10];
    if ( v22 )
      v21 += (v22 > 1) + 1;
  }
  while ( v8 );
  v23 = *v2;
  v24 = 0;
  v25 = 0;
  LOBYTE(v39) = 0;
  v35 = 0;
  v26 = v4;
  if ( v4 >= v21 )
    v26 = v21;
  v40 = v26;
  v27 = v38;
  do
  {
    v43 = v24;
    v28 = v45[v24 + 10];
    if ( v28 && v27 )
    {
      v29 = v45[v24];
      v37 = v45[v24 + 10];
      *(_DWORD *)v23 = *(_DWORD *)v29;
      *(_WORD *)(v23 + 4) = *(_WORD *)(v29 + 4);
      *(_DWORD *)(v23 + 12) = v28;
      v30 = 1;
      *(_DWORD *)(v23 + 40) = -1;
      *(_BYTE *)(v23 + 7) = 6;
      do
      {
        if ( *(_BYTE *)(v29 + 7) == v24 )
        {
          --v37;
          *(_BYTE *)(v29 + 6) = v25;
        }
        v29 += 8;
      }
      while ( v37 );
      if ( v28 <= 1 || v38 <= 1 )
      {
        *(_DWORD *)(v23 + 40) = 0;
        v32 = -1;
      }
      else
      {
        v42 = *(int **)(v23 + 8);
        v31 = SplitCodeBook(v45[v43 + 5], v39, &v42, v28 * (v38 - v40) / v41 + 1, 1);
        v24 = (unsigned __int8)v39;
        v25 = v35;
        v30 = v31 + 1;
        v32 = -2;
      }
      v38 -= v30;
      v25 += v30;
      v41 -= v28;
      v35 = v25;
      v23 += 460 * v30;
      v40 += v32;
      v27 = v38;
    }
    LOBYTE(v39) = ++v24;
  }
  while ( v24 < 5u );
  v33 = v2[5];
  result = v33 + ConvergeCodeBook(255, 0);
  v2[5] = result;
  return result;
}

```

## disassembly

```asm
0x10010a12  mov     edi, edi
0x10010a14  push    ebp
0x10010a15  mov     ebp, esp
0x10010a17  and     esp, 0FFFFFFF8h
0x10010a1a  sub     esp, 64h
0x10010a1d  mov     eax, ___security_cookie
0x10010a22  xor     eax, esp
0x10010a24  mov     [esp+64h+var_4], eax
0x10010a28  push    ebx
0x10010a29  mov     ebx, [ebp+arg_0]
0x10010a2c  xor     edx, edx
0x10010a2e  push    esi
0x10010a2f  push    edi
0x10010a30  mov     [esp+70h+var_44], ecx
0x10010a34  movsx   edi, word ptr [ebx+8]
0x10010a38  mov     esi, [ebx+0Ch]
0x10010a3b  mov     ecx, [ebx]
0x10010a3d  mov     [esp+70h+var_4C], ebx
0x10010a41  mov     [esp+70h+var_5C], edi
0x10010a45  mov     [esp+70h+var_50], esi
0x10010a49  mov     eax, ecx
0x10010a4b  add     ecx, 1CCh
0x10010a51  mov     [eax+6], dl
0x10010a54  inc     edx
0x10010a55  mov     byte ptr [eax+7], 1
0x10010a59  mov     [eax+8], ecx
0x10010a5c  cmp     edx, 100h
0x10010a62  jl      short loc_10010A49
0x10010a64  push    5
0x10010a66  pop     ecx
0x10010a67  mov     eax, ecx
0x10010a69  sub     eax, 1
0x10010a6c  mov     [esp+eax*4+70h+var_18], 0
0x10010a74  jnz     short loc_10010A69
0x10010a76  mov     edx, [ebx+4]
0x10010a79  mov     [esp+70h+var_58], edx
0x10010a7d  mov     [esp+70h+var_60], 0
0x10010a85  test    esi, esi
0x10010a87  jle     loc_10010B49
0x10010a8d  movzx   ecx, byte ptr [edx+3]
0x10010a91  movzx   ebx, byte ptr [edx+2]
0x10010a95  movzx   esi, byte ptr [edx+1]
0x10010a99  movzx   edx, byte ptr [edx]
0x10010a9c  lea     edi, [ecx+2]
0x10010a9f  mov     [esp+70h+var_54], ecx
0x10010aa3  lea     eax, [edx+esi]
0x10010aa6  add     eax, ebx
0x10010aa8  add     edi, eax
0x10010aaa  shr     edi, 2
0x10010aad  mov     ecx, edi
0x10010aaf  mov     eax, edi
0x10010ab1  sub     ecx, edx
0x10010ab3  sub     eax, esi
0x10010ab5  mov     ecx, ds:dword_1000170C[ecx*4]
0x10010abc  add     ecx, ds:dword_1000170C[eax*4]
0x10010ac3  mov     eax, edi
0x10010ac5  sub     edi, [esp+70h+var_54]
0x10010ac9  sub     eax, ebx
0x10010acb  add     ecx, ds:dword_1000170C[eax*4]
0x10010ad2  add     ecx, ds:dword_1000170C[edi*4]
0x10010ad9  test    ecx, 0E000h
0x10010adf  jz      short loc_10010AE5
0x10010ae1  mov     al, 4
0x10010ae3  jmp     short loc_10010B03
0x10010ae5  test    ecx, 1C00h
0x10010aeb  jz      short loc_10010AF1
0x10010aed  mov     al, 3
0x10010aef  jmp     short loc_10010B03
0x10010af1  test    ecx, 380h
0x10010af7  jz      short loc_10010AFD
0x10010af9  mov     al, 2
0x10010afb  jmp     short loc_10010B03
0x10010afd  test    cl, 70h
0x10010b00  setnz   al
0x10010b03  mov     edx, [esp+70h+var_58]
0x10010b07  movzx   esi, al
0x10010b0a  mov     [edx+7], al
0x10010b0d  mov     ecx, [esp+esi*4+70h+var_18]
0x10010b11  lea     eax, [ecx+1]
0x10010b14  mov     [esp+esi*4+70h+var_18], eax
0x10010b18  mov     eax, [esp+70h+var_60]
0x10010b1c  test    ecx, ecx
0x10010b1e  jnz     short loc_10010B28
0x10010b20  mov     [esp+esi*4+70h+var_2C], eax
0x10010b24  mov     [esp+esi*4+70h+var_40], edx
0x10010b28  inc     eax
0x10010b29  add     edx, 8
0x10010b2c  mov     [esp+70h+var_60], eax
0x10010b30  mov     [esp+70h+var_58], edx
0x10010b34  cmp     eax, [esp+70h+var_50]
0x10010b38  jl      loc_10010A8D
0x10010b3e  mov     ebx, [esp+70h+var_4C]
0x10010b42  mov     edi, [esp+70h+var_5C]
0x10010b46  push    5
0x10010b48  pop     ecx
0x10010b49  xor     edx, edx
0x10010b4b  lea     eax, [ecx-1]
0x10010b4e  mov     esi, [esp+eax*4+70h+var_18]
0x10010b52  mov     ecx, eax
0x10010b54  test    esi, esi
0x10010b56  jz      short loc_10010B63
0x10010b58  xor     eax, eax
0x10010b5a  cmp     esi, 1
0x10010b5d  setnle  al
0x10010b60  inc     eax
0x10010b61  add     edx, eax
0x10010b63  test    ecx, ecx
0x10010b65  jnz     short loc_10010B4B
0x10010b67  mov     esi, [ebx]
0x10010b69  xor     cl, cl
0x10010b6b  xor     ch, ch
0x10010b6d  mov     byte ptr [esp+70h+var_58], cl
0x10010b71  cmp     edi, edx
0x10010b73  mov     [esp+70h+var_61], ch
0x10010b77  mov     eax, edi
0x10010b79  cmovge  eax, edx
0x10010b7c  mov     [esp+70h+var_54], eax
0x10010b80  mov     eax, [esp+70h+var_5C]
0x10010b84  movzx   edx, cl
0x10010b87  mov     [esp+70h+var_48], edx
0x10010b8b  mov     edi, [esp+edx*4+70h+var_18]
0x10010b8f  test    edi, edi
0x10010b91  jz      loc_10010C53
0x10010b97  test    eax, eax
0x10010b99  jz      loc_10010C53
0x10010b9f  mov     edx, [esp+edx*4+70h+var_40]
0x10010ba3  mov     [esp+70h+var_60], edi
0x10010ba7  mov     eax, [edx]
0x10010ba9  mov     [esi], eax
0x10010bab  mov     ax, [edx+4]
0x10010baf  mov     [esi+4], ax
0x10010bb3  xor     eax, eax
0x10010bb5  mov     [esi+0Ch], edi
0x10010bb8  inc     eax
0x10010bb9  mov     dword ptr [esi+28h], 0FFFFFFFFh
0x10010bc0  mov     byte ptr [esi+7], 6
0x10010bc4  cmp     [edx+7], cl
0x10010bc7  jnz     short loc_10010BD0
0x10010bc9  dec     [esp+70h+var_60]
0x10010bcd  mov     [edx+6], ch
0x10010bd0  add     edx, 8
0x10010bd3  cmp     [esp+70h+var_60], 0
0x10010bd8  jnz     short loc_10010BC4
0x10010bda  cmp     edi, 1
0x10010bdd  jle     short loc_10010C2B
0x10010bdf  mov     edx, [esp+70h+var_5C]
0x10010be3  cmp     edx, 1
0x10010be6  jle     short loc_10010C2B
0x10010be8  mov     eax, [esi+8]
0x10010beb  mov     [esp+70h+var_4C], eax
0x10010bef  mov     eax, edx
0x10010bf1  sub     eax, [esp+70h+var_54]
0x10010bf5  imul    eax, edi
0x10010bf8  push    1
0x10010bfa  cdq
0x10010bfb  idiv    [esp+74h+var_50]
0x10010bff  movzx   edx, ch
0x10010c02  mov     ecx, ebx
0x10010c04  inc     eax
0x10010c05  push    eax
0x10010c06  lea     eax, [esp+78h+var_4C]
0x10010c0a  push    eax
0x10010c0b  mov     eax, [esp+7Ch+var_48]
0x10010c0f  push    [esp+7Ch+var_58]
0x10010c13  push    [esp+eax*4+80h+var_2C]
0x10010c17  call    _SplitCodeBook@28; SplitCodeBook(x,x,x,x,x,x,x)
0x10010c1c  mov     cl, byte ptr [esp+70h+var_58]
0x10010c20  mov     ch, [esp+70h+var_61]
0x10010c24  cwde
0x10010c25  push    0FFFFFFFEh
0x10010c27  inc     eax
0x10010c28  pop     edx
0x10010c29  jmp     short loc_10010C35
0x10010c2b  mov     dword ptr [esi+28h], 0
0x10010c32  or      edx, 0FFFFFFFFh
0x10010c35  sub     [esp+70h+var_5C], eax
0x10010c39  add     ch, al
0x10010c3b  sub     [esp+70h+var_50], edi
0x10010c3f  imul    eax, 1CCh
0x10010c45  mov     [esp+70h+var_61], ch
0x10010c49  add     esi, eax
0x10010c4b  add     [esp+70h+var_54], edx
0x10010c4f  mov     eax, [esp+70h+var_5C]
0x10010c53  inc     cl
0x10010c55  mov     byte ptr [esp+70h+var_58], cl
0x10010c59  cmp     cl, 5
0x10010c5c  jb      loc_10010B84
0x10010c62  mov     ecx, [esp+70h+var_44]
0x10010c66  mov     edx, ebx
0x10010c68  mov     esi, [ebx+14h]
0x10010c6b  push    0
0x10010c6d  push    0FFh
0x10010c72  call    _ConvergeCodeBook@16; ConvergeCodeBook(x,x,x,x)
0x10010c77  mov     ecx, [esp+70h+var_4]
0x10010c7b  add     eax, esi
0x10010c7d  pop     edi
0x10010c7e  pop     esi
0x10010c7f  mov     [ebx+14h], eax
0x10010c82  pop     ebx
0x10010c83  xor     ecx, esp; StackCookie
0x10010c85  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10010c8a  mov     esp, ebp
0x10010c8c  pop     ebp
0x10010c8d  retn    4
```
