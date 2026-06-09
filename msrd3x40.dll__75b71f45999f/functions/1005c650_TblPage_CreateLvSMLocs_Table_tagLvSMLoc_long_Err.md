# TblPage::CreateLvSMLocs(Table *,tagLvSMLoc *,long,Err &)

- ea: `0x1005c650`
- end: `0x1005c7d0`
- name: `?CreateLvSMLocs@TblPage@@AAEJPAVTable@@PAUtagLvSMLoc@@JAAVErr@@@Z`
- size: `384`
- prototype: `int __thiscall(TblPage *this, struct Table *, struct tagLvSMLoc *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1005ab70`

## callees

- `0x1000eb60`
- `0x10025ee0`
- `0x1005c650`
- `0x1005e7e8`

## pseudocode

```c
int __thiscall TblPage::CreateLvSMLocs(TblPage *this, struct Table *a2, struct tagLvSMLoc *a3, int a4, void **a5)
{
  struct tagLvSMLoc *v5; // edi
  int v6; // ecx
  __int16 v7; // ax
  int v8; // eax
  unsigned int v9; // eax
  int v10; // eax
  int v11; // ecx
  unsigned int v12; // eax
  int v13; // ecx
  unsigned int v14; // eax
  int v15; // ecx
  int v16; // eax
  int v18; // [esp+8h] [ebp-4h]

  v5 = a3;
  v6 = 1;
  v18 = 1;
  if ( *(_WORD *)a3 != 0xFFFF )
  {
    while ( v6 < 255 )
    {
      v7 = *(_WORD *)v5;
      if ( *(_WORD *)v5 > 0xFFu || v7 >= *((_DWORD *)a2 + 3) )
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
          v6 = v18;
          *a5 = (void *)8;
          a5[1] = (void *)-1206;
          a5[2] = 0;
          a5[3] = 0;
          a5[4] = 0;
        }
        return 10 * v6;
      }
      if ( (unsigned int)v7 > 0xFE )
        v8 = 0;
      else
        v8 = *((_DWORD *)a2 + v7 + 94);
      if ( (*(unsigned __int8 (__thiscall **)(int))(*(_DWORD *)v8 + 16))(v8) != 11 )
      {
        v9 = *(__int16 *)v5;
        v10 = v9 > 0xFE ? 0 : *((_DWORD *)a2 + v9 + 94);
        if ( (*(unsigned __int8 (__thiscall **)(int))(*(_DWORD *)v10 + 16))(v10) != 12 )
        {
          Err::SetError(a5, -1206, v11);
          return 10 * v18;
        }
      }
      v12 = *(__int16 *)v5;
      if ( v12 > 0xFE )
        v13 = 0;
      else
        v13 = *((_DWORD *)a2 + v12 + 94);
      *(_DWORD *)(v13 + 204) = *(_DWORD *)((char *)v5 + 2);
      v14 = *(__int16 *)v5;
      if ( v14 > 0xFE )
        v15 = 0;
      else
        v15 = *((_DWORD *)a2 + v14 + 94);
      v16 = *(_DWORD *)((char *)v5 + 6);
      v5 = (struct tagLvSMLoc *)((char *)v5 + 10);
      *(_DWORD *)(v15 + 208) = v16;
      v6 = ++v18;
      if ( *(_WORD *)v5 == 0xFFFF )
        return 10 * v6;
    }
  }
  return 10 * v6;
}

```

## disassembly

```asm
0x1005c650  mov     edi, edi
0x1005c652  push    ebp
0x1005c653  mov     ebp, esp
0x1005c655  sub     esp, 8
0x1005c658  push    edi
0x1005c659  mov     edi, [ebp+arg_4]
0x1005c65c  mov     ecx, 1
0x1005c661  mov     [ebp+var_4], ecx
0x1005c664  cmp     word ptr [edi], 0FFFFh
0x1005c668  jz      loc_1005C7C4
0x1005c66e  push    ebx; unsigned int
0x1005c66f  mov     ebx, [ebp+arg_0]
0x1005c672  push    esi; void *
0x1005c673  mov     edx, 0FFh
0x1005c678  cmp     ecx, edx
0x1005c67a  jge     loc_1005C7C2
0x1005c680  movzx   eax, word ptr [edi]
0x1005c683  cmp     ax, dx
0x1005c686  ja      loc_1005C76C
0x1005c68c  cwde
0x1005c68d  cmp     eax, [ebx+0Ch]
0x1005c690  jge     loc_1005C76C
0x1005c696  test    eax, eax
0x1005c698  js      short loc_1005C6A7
0x1005c69a  cmp     eax, edx
0x1005c69c  jnb     short loc_1005C6A7
0x1005c69e  mov     eax, [ebx+eax*4+178h]
0x1005c6a5  jmp     short loc_1005C6A9
0x1005c6a7  xor     eax, eax
0x1005c6a9  mov     [ebp+var_8], eax
0x1005c6ac  mov     eax, [eax]
0x1005c6ae  mov     esi, [eax+10h]
0x1005c6b1  mov     ecx, esi
0x1005c6b3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005c6b9  mov     ecx, [ebp+var_8]
0x1005c6bc  call    esi
0x1005c6be  cmp     al, 0Bh
0x1005c6c0  jz      short loc_1005C6F4
0x1005c6c2  movsx   eax, word ptr [edi]
0x1005c6c5  test    eax, eax
0x1005c6c7  js      short loc_1005C6D9
0x1005c6c9  cmp     eax, 0FFh
0x1005c6ce  jnb     short loc_1005C6D9
0x1005c6d0  mov     eax, [ebx+eax*4+178h]
0x1005c6d7  jmp     short loc_1005C6DB
0x1005c6d9  xor     eax, eax
0x1005c6db  mov     [ebp+var_8], eax
0x1005c6de  mov     eax, [eax]
0x1005c6e0  mov     esi, [eax+10h]
0x1005c6e3  mov     ecx, esi
0x1005c6e5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005c6eb  mov     ecx, [ebp+var_8]
0x1005c6ee  call    esi
0x1005c6f0  cmp     al, 0Ch
0x1005c6f2  jnz     short loc_1005C74D
0x1005c6f4  movsx   eax, word ptr [edi]
0x1005c6f7  test    eax, eax
0x1005c6f9  js      short loc_1005C70B
0x1005c6fb  cmp     eax, 0FFh
0x1005c700  jnb     short loc_1005C70B
0x1005c702  mov     ecx, [ebx+eax*4+178h]
0x1005c709  jmp     short loc_1005C70D
0x1005c70b  xor     ecx, ecx
0x1005c70d  mov     eax, [edi+2]
0x1005c710  mov     [ecx+0CCh], eax
0x1005c716  movsx   eax, word ptr [edi]
0x1005c719  test    eax, eax
0x1005c71b  js      short loc_1005C72D
0x1005c71d  cmp     eax, 0FFh
0x1005c722  jnb     short loc_1005C72D
0x1005c724  mov     ecx, [ebx+eax*4+178h]
0x1005c72b  jmp     short loc_1005C72F
0x1005c72d  xor     ecx, ecx
0x1005c72f  mov     eax, [edi+6]
0x1005c732  add     edi, 0Ah
0x1005c735  mov     [ecx+0D0h], eax
0x1005c73b  mov     ecx, [ebp+var_4]
0x1005c73e  inc     ecx
0x1005c73f  cmp     word ptr [edi], 0FFFFh
0x1005c743  mov     [ebp+var_4], ecx
0x1005c746  jz      short loc_1005C7C2
0x1005c748  jmp     loc_1005C673
0x1005c74d  push    ecx
0x1005c74e  mov     ecx, [ebp+arg_C]
0x1005c751  push    0FFFFFB4Ah
0x1005c756  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005c75b  mov     ecx, [ebp+var_4]
0x1005c75e  pop     esi
0x1005c75f  pop     ebx
0x1005c760  pop     edi
0x1005c761  lea     eax, [ecx+ecx*4]
0x1005c764  add     eax, eax
0x1005c766  mov     esp, ebp
0x1005c768  pop     ebp
0x1005c769  retn    10h
0x1005c76c  mov     esi, [ebp+arg_C]
0x1005c76f  mov     eax, [esi]
0x1005c771  cmp     eax, 8
0x1005c774  jge     short loc_1005C7C2
0x1005c776  test    eax, 0FFFFFFFEh
0x1005c77b  jz      short loc_1005C79D
0x1005c77d  mov     eax, [esi+0Ch]
0x1005c780  test    eax, eax
0x1005c782  jz      short loc_1005C78D
0x1005c784  push    eax; Block
0x1005c785  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c78a  add     esp, 4
0x1005c78d  mov     eax, [esi+10h]
0x1005c790  test    eax, eax
0x1005c792  jz      short loc_1005C79D
0x1005c794  push    eax; Block
0x1005c795  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c79a  add     esp, 4
0x1005c79d  mov     ecx, [ebp+var_4]
0x1005c7a0  mov     dword ptr [esi], 8
0x1005c7a6  mov     dword ptr [esi+4], 0FFFFFB4Ah
0x1005c7ad  mov     dword ptr [esi+8], 0
0x1005c7b4  mov     dword ptr [esi+0Ch], 0
0x1005c7bb  mov     dword ptr [esi+10h], 0
0x1005c7c2  pop     esi
0x1005c7c3  pop     ebx
0x1005c7c4  lea     eax, [ecx+ecx*4]
0x1005c7c7  add     eax, eax
0x1005c7c9  pop     edi
0x1005c7ca  mov     esp, ebp
0x1005c7cc  pop     ebp
0x1005c7cd  retn    10h
```
