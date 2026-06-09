# Sort::CompeteChildren(int,Err &)

- ea: `0x10045a70`
- end: `0x10045c31`
- name: `?CompeteChildren@Sort@@AAEXHAAVErr@@@Z`
- size: `449`
- prototype: `void __thiscall(Sort *__hidden this, int, struct Err *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10045a10`
- `0x10045c40`
- `0x10045cd0`

## callees

- `0x10045a70`
- `0x10045c40`
- `0x100464d0`

## pseudocode

```c
void __thiscall Sort::CompeteChildren(Sort *this, int a2, struct Err *a3)
{
  int v4; // edi
  _DWORD *v5; // ebx
  int v6; // ecx
  int v7; // edx
  int v8; // eax
  int v9; // eax
  _DWORD *v10; // edx
  _DWORD *v11; // edi
  _DWORD *v12; // ecx
  _DWORD *v13; // edx
  int v14; // [esp+Ch] [ebp-10h]
  int v15; // [esp+10h] [ebp-Ch]
  int *v16; // [esp+14h] [ebp-8h]
  int v17; // [esp+18h] [ebp-4h]

  v4 = *((_DWORD *)this + 6 * a2 + 23);
  v5 = (_DWORD *)((char *)this + 24 * a2);
  v6 = *((_DWORD *)this + 6 * a2 + 24);
  v16 = (int *)((char *)this + 24 * a2 + 96);
  v17 = *((_DWORD *)this + 6 * v4 + 21);
  v7 = *((_DWORD *)this + 6 * v6 + 21);
  v14 = v7;
  v15 = *((_DWORD *)this + 6 * v17 + 26);
  if ( v15 )
  {
    while ( *((_DWORD *)this + 6 * v7 + 26) )
    {
      v8 = SortItemBuffer::CompareSortItems(v15, *((_DWORD *)this + 6 * v7 + 26));
      if ( !v8 )
      {
        v5[21] = v14;
        return;
      }
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 != 1 )
          return;
LABEL_11:
        v5[21] = v17;
        return;
      }
      if ( !*((_DWORD *)this + 7) )
        goto LABEL_11;
      Sort::NextFromTree(this, v4, a3);
      if ( (*(_BYTE *)a3 & 8) != 0 )
        return;
      v4 = v5[23];
      v6 = *v16;
      v17 = *((_DWORD *)this + 6 * v4 + 21);
      v7 = *((_DWORD *)this + 6 * *v16 + 21);
      v14 = v7;
      v15 = *((_DWORD *)this + 6 * v17 + 26);
      if ( !v15 )
        goto LABEL_8;
    }
    v12 = (_DWORD *)((char *)this + 24 * v4);
    v13 = v12 + 23;
    if ( v12[25] )
    {
      v5[21] = a2;
    }
    else
    {
      v5[21] = v12[21];
      *((_DWORD *)this + 6 * *v13 + 22) = a2;
      *((_DWORD *)this + 6 * *((_DWORD *)this + 6 * v4 + 24) + 22) = a2;
    }
    v5[23] = *v13;
    *v16 = *((_DWORD *)this + 6 * v4 + 24);
    v5[25] = v12[25];
    v5[26] = v12[26];
  }
  else
  {
LABEL_8:
    v10 = (_DWORD *)((char *)this + 24 * v6);
    v11 = v10 + 23;
    if ( v10[25] )
    {
      v5[21] = a2;
    }
    else
    {
      v5[21] = v10[21];
      *((_DWORD *)this + 6 * *v11 + 22) = a2;
      *((_DWORD *)this + 6 * *((_DWORD *)this + 6 * v6 + 24) + 22) = a2;
    }
    v5[23] = *v11;
    *v16 = *((_DWORD *)this + 6 * v6 + 24);
    v5[25] = v10[25];
    v5[26] = v10[26];
  }
}

```

## disassembly

```asm
0x10045a70  mov     edi, edi
0x10045a72  push    ebp
0x10045a73  mov     ebp, esp
0x10045a75  sub     esp, 10h
0x10045a78  push    ebx
0x10045a79  push    esi
0x10045a7a  mov     esi, ecx
0x10045a7c  mov     ecx, [ebp+arg_0]
0x10045a7f  push    edi
0x10045a80  lea     eax, [ecx+ecx*2]
0x10045a83  add     ecx, 4
0x10045a86  mov     edi, [esi+eax*8+5Ch]
0x10045a8a  lea     ebx, [esi+eax*8]
0x10045a8d  lea     eax, [ecx+ecx*2]
0x10045a90  mov     ecx, [esi+eax*8]
0x10045a93  lea     eax, [esi+eax*8]
0x10045a96  mov     [ebp+var_8], eax
0x10045a99  lea     eax, [edi+edi*2]
0x10045a9c  mov     eax, [esi+eax*8+54h]
0x10045aa0  mov     [ebp+var_4], eax
0x10045aa3  lea     eax, [ecx+ecx*2]
0x10045aa6  mov     edx, [esi+eax*8+54h]
0x10045aaa  mov     eax, [ebp+var_4]
0x10045aad  mov     [ebp+var_10], edx
0x10045ab0  lea     eax, [eax+eax*2]
0x10045ab3  mov     eax, [esi+eax*8+68h]
0x10045ab7  mov     [ebp+var_C], eax
0x10045aba  test    eax, eax
0x10045abc  jz      short loc_10045B2F
0x10045abe  mov     edi, edi
0x10045ac0  lea     eax, [edx+edx*2]
0x10045ac3  mov     eax, [esi+eax*8+68h]
0x10045ac7  test    eax, eax
0x10045ac9  jz      loc_10045B78
0x10045acf  push    eax
0x10045ad0  push    [ebp+var_C]
0x10045ad3  call    ?CompareSortItems@SortItemBuffer@@QAE?AW4SortItemCompare@@PAVSortItem@@0@Z; SortItemBuffer::CompareSortItems(SortItem *,SortItem *)
0x10045ad8  sub     eax, 0
0x10045adb  jz      loc_10045B69
0x10045ae1  sub     eax, 1
0x10045ae4  jnz     short loc_10045B51
0x10045ae6  cmp     [esi+1Ch], eax
0x10045ae9  jz      short loc_10045B5A
0x10045aeb  push    [ebp+arg_4]; struct Err *
0x10045aee  mov     ecx, esi; this
0x10045af0  push    edi; int
0x10045af1  call    ?NextFromTree@Sort@@AAEPAVSortItem@@HAAVErr@@@Z; Sort::NextFromTree(int,Err &)
0x10045af6  mov     eax, [ebp+arg_4]
0x10045af9  test    byte ptr [eax], 8
0x10045afc  jnz     loc_10045C28
0x10045b02  mov     eax, [ebp+var_8]
0x10045b05  mov     edi, [ebx+5Ch]
0x10045b08  mov     ecx, [eax]
0x10045b0a  lea     eax, [edi+edi*2]
0x10045b0d  mov     eax, [esi+eax*8+54h]
0x10045b11  mov     [ebp+var_4], eax
0x10045b14  lea     eax, [ecx+ecx*2]
0x10045b17  mov     edx, [esi+eax*8+54h]
0x10045b1b  mov     eax, [ebp+var_4]
0x10045b1e  mov     [ebp+var_10], edx
0x10045b21  lea     eax, [eax+eax*2]
0x10045b24  mov     eax, [esi+eax*8+68h]
0x10045b28  mov     [ebp+var_C], eax
0x10045b2b  test    eax, eax
0x10045b2d  jnz     short loc_10045AC0
0x10045b2f  lea     eax, [ecx+ecx*2]
0x10045b32  cmp     dword ptr [esi+eax*8+64h], 0
0x10045b37  lea     edx, [esi+eax*8]
0x10045b3a  mov     [ebp+var_10], edx
0x10045b3d  lea     edi, [edx+5Ch]
0x10045b40  jz      loc_10045BE2
0x10045b46  mov     eax, [ebp+arg_0]
0x10045b49  mov     [ebx+54h], eax
0x10045b4c  jmp     loc_10045C05
0x10045b51  sub     eax, 1
0x10045b54  jnz     loc_10045C28
0x10045b5a  mov     eax, [ebp+var_4]
0x10045b5d  pop     edi
0x10045b5e  pop     esi
0x10045b5f  mov     [ebx+54h], eax
0x10045b62  pop     ebx
0x10045b63  mov     esp, ebp
0x10045b65  pop     ebp
0x10045b66  retn    8
0x10045b69  mov     eax, [ebp+var_10]
0x10045b6c  pop     edi
0x10045b6d  pop     esi
0x10045b6e  mov     [ebx+54h], eax
0x10045b71  pop     ebx
0x10045b72  mov     esp, ebp
0x10045b74  pop     ebp
0x10045b75  retn    8
0x10045b78  lea     eax, [edi+edi*2]
0x10045b7b  cmp     dword ptr [esi+eax*8+64h], 0
0x10045b80  lea     ecx, [esi+eax*8]
0x10045b83  mov     [ebp+var_10], ecx
0x10045b86  lea     edx, [ecx+5Ch]
0x10045b89  jz      short loc_10045B93
0x10045b8b  mov     eax, [ebp+arg_0]
0x10045b8e  mov     [ebx+54h], eax
0x10045b91  jmp     short loc_10045BB6
0x10045b93  mov     eax, [ecx+54h]
0x10045b96  mov     ecx, [ebp+arg_0]
0x10045b99  mov     [ebx+54h], eax
0x10045b9c  mov     eax, [edx]
0x10045b9e  lea     eax, [eax+eax*2]
0x10045ba1  mov     [esi+eax*8+58h], ecx
0x10045ba5  lea     eax, [edi+edi*2]
0x10045ba8  mov     eax, [esi+eax*8+60h]
0x10045bac  lea     eax, [eax+eax*2]
0x10045baf  mov     [esi+eax*8+58h], ecx
0x10045bb3  mov     ecx, [ebp+var_10]
0x10045bb6  mov     eax, [edx]
0x10045bb8  mov     [ebx+5Ch], eax
0x10045bbb  mov     eax, 4
0x10045bc0  add     eax, edi
0x10045bc2  pop     edi
0x10045bc3  lea     eax, [eax+eax*2]
0x10045bc6  mov     eax, [esi+eax*8]
0x10045bc9  mov     esi, [ebp+var_8]
0x10045bcc  mov     [esi], eax
0x10045bce  mov     eax, [ecx+64h]
0x10045bd1  mov     [ebx+64h], eax
0x10045bd4  mov     eax, [ecx+68h]
0x10045bd7  pop     esi
0x10045bd8  mov     [ebx+68h], eax
0x10045bdb  pop     ebx
0x10045bdc  mov     esp, ebp
0x10045bde  pop     ebp
0x10045bdf  retn    8
0x10045be2  mov     eax, [edx+54h]
0x10045be5  mov     edx, [ebp+arg_0]
0x10045be8  mov     [ebx+54h], eax
0x10045beb  mov     eax, [edi]
0x10045bed  lea     eax, [eax+eax*2]
0x10045bf0  mov     [esi+eax*8+58h], edx
0x10045bf4  lea     eax, [ecx+ecx*2]
0x10045bf7  mov     eax, [esi+eax*8+60h]
0x10045bfb  lea     eax, [eax+eax*2]
0x10045bfe  mov     [esi+eax*8+58h], edx
0x10045c02  mov     edx, [ebp+var_10]
0x10045c05  mov     eax, [edi]
0x10045c07  mov     [ebx+5Ch], eax
0x10045c0a  mov     eax, 4
0x10045c0f  add     eax, ecx
0x10045c11  lea     eax, [eax+eax*2]
0x10045c14  mov     eax, [esi+eax*8]
0x10045c17  mov     esi, [ebp+var_8]
0x10045c1a  mov     [esi], eax
0x10045c1c  mov     eax, [edx+64h]
0x10045c1f  mov     [ebx+64h], eax
0x10045c22  mov     eax, [edx+68h]
0x10045c25  mov     [ebx+68h], eax
0x10045c28  pop     edi
0x10045c29  pop     esi
0x10045c2a  pop     ebx
0x10045c2b  mov     esp, ebp
0x10045c2d  pop     ebp
0x10045c2e  retn    8
```
