# TableMover::GotoPosition(KeyPos *,Err &)

- ea: `0x10059af0`
- end: `0x10059cf1`
- name: `?GotoPosition@TableMover@@UAEXPAUKeyPos@@AAVErr@@@Z`
- size: `513`
- prototype: `void __thiscall(TableMover *__hidden this, struct KeyPos *, struct Err *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1000eb60`
- `0x10023690`
- `0x10024cf0`
- `0x10024e30`
- `0x10025ee0`
- `0x10048980`
- `0x10048e90`
- `0x100493a0`
- `0x10059af0`

## pseudocode

```c
void __thiscall TableMover::GotoPosition(TableMover *this, struct KeyPos *a2, struct Err *a3)
{
  TableMover *v3; // ebx
  unsigned int v4; // eax
  unsigned int v5; // ecx
  AbstractSpacemap *v6; // edi
  unsigned int v7; // eax
  __int16 v8; // dx
  unsigned int Page; // eax
  unsigned int v10; // edi
  unsigned int v11; // edx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // ecx
  unsigned int v15; // esi
  unsigned int v16; // eax
  unsigned int v17; // [esp+Ch] [ebp-14h]
  AbstractSpacemap *v19; // [esp+14h] [ebp-Ch]
  unsigned int v20; // [esp+14h] [ebp-Ch]
  int v21; // [esp+18h] [ebp-8h]
  unsigned int v22; // [esp+18h] [ebp-8h]
  unsigned int v23; // [esp+1Ch] [ebp-4h]

  v3 = this;
  (*(void (__thiscall **)(_DWORD, struct Err *))(**((_DWORD **)this + 1) + 124))(*((_DWORD *)this + 1), a3);
  v4 = *(_DWORD *)a2;
  v5 = *((_DWORD *)a2 + 1);
  if ( *(_DWORD *)a2 < v5 )
  {
    if ( v4 >= 0x10000 )
    {
      do
      {
        v4 >>= 1;
        v5 >>= 1;
      }
      while ( v4 >= 0x10000 );
      *((_DWORD *)a2 + 1) = v5;
      *(_DWORD *)a2 = v4;
    }
    if ( v4 )
    {
      *((_DWORD *)v3 + 13) = 0;
      *((_DWORD *)v3 + 14) = 0;
      *((_DWORD *)v3 + 15) = 0;
      v6 = (AbstractSpacemap *)(*(int (__thiscall **)(_DWORD))(**((_DWORD **)v3 + 1) + 76))(*((_DWORD *)v3 + 1));
      v19 = v6;
      v21 = (*(_DWORD *)a2 << 16) / *((_DWORD *)a2 + 1);
      v7 = AbstractSpacemap::CountPages(v6, a3);
      if ( v7 )
      {
        v8 = v21;
        v22 = v21 * HIWORD(v7) + ((v21 * (unsigned int)(unsigned __int16)v7) >> 16);
        v17 = (unsigned __int16)(v8 * (v22 + 1));
        Page = AbstractSpacemap::FirstPage(v6, a3);
        v10 = 1;
        v23 = Page;
        v11 = Page;
        if ( v22 > 1 )
        {
          do
          {
            if ( (*(_BYTE *)a3 & 8) != 0 )
              break;
            ++v10;
            v11 = AbstractSpacemap::NextPage(v19, v11, a3);
          }
          while ( v10 < v22 );
          v3 = this;
          v23 = v11;
        }
        do
        {
          Database::ReadPage(
            *(Database **)(*(_DWORD *)(*((_DWORD *)v3 + 1) + 40) + 8),
            (TableMover *)((char *)v3 + 20),
            v11,
            1,
            (void **)a3,
            *(struct Transaction **)(*((_DWORD *)v3 + 1) + 40));
          if ( (*(_BYTE *)a3 & 8) != 0 )
          {
LABEL_17:
            *((_DWORD *)v3 + 2) = 2;
            *((_DWORD *)v3 + 3) = 0;
            return;
          }
          *((_DWORD *)v3 + 7) = *(_DWORD *)(*((_DWORD *)v3 + 5) + 64);
          v12 = DataPage::First((TableMover *)((char *)v3 + 20));
          *((_DWORD *)v3 + 3) = v12;
          if ( v12 )
          {
            v11 = v23;
          }
          else
          {
            v11 = AbstractSpacemap::NextPage(v19, v23, a3);
            v23 = v11;
            if ( !v11 )
              goto LABEL_17;
          }
          v13 = *((_DWORD *)v3 + 3);
        }
        while ( !v13 );
        v14 = 0;
        do
        {
          v15 = v14;
          v20 = v14 + 1;
          v13 = DataPage::Next((TableMover *)((char *)v3 + 20), v13);
          v14 = v20;
          *((_DWORD *)v3 + 3) = v13;
        }
        while ( v13 );
        if ( ((v17 >> 1) + v17 * v20) >> 16 < v20 )
          v15 = ((v17 >> 1) + v17 * v20) >> 16;
        v16 = DataPage::First((TableMover *)((char *)v3 + 20));
        for ( *((_DWORD *)v3 + 3) = v16; v15; --v15 )
        {
          v16 = DataPage::Next((TableMover *)((char *)v3 + 20), v16);
          *((_DWORD *)v3 + 3) = v16;
        }
        *((_DWORD *)v3 + 2) = 0;
      }
      else
      {
        Err::SetError(a3, -1603, 0);
      }
    }
    else
    {
      (*(void (__thiscall **)(TableMover *, int, _DWORD, struct Err *))(*(_DWORD *)v3 + 8))(v3, 1, 0, a3);
    }
  }
  else
  {
    (*(void (__thiscall **)(TableMover *, int, int, struct Err *))(*(_DWORD *)v3 + 8))(v3, 1, 1, a3);
  }
}

```

## disassembly

```asm
0x10059af0  mov     edi, edi
0x10059af2  push    ebp
0x10059af3  mov     ebp, esp
0x10059af5  sub     esp, 14h
0x10059af8  push    ebx
0x10059af9  mov     ebx, ecx
0x10059afb  push    esi; unsigned int
0x10059afc  push    edi; void *
0x10059afd  push    [ebp+arg_4]; void *
0x10059b00  mov     edi, [ebx+4]
0x10059b03  mov     [ebp+var_10], ebx
0x10059b06  mov     eax, [edi]
0x10059b08  mov     esi, [eax+7Ch]
0x10059b0b  mov     ecx, esi
0x10059b0d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10059b13  mov     ecx, edi
0x10059b15  call    esi
0x10059b17  mov     edx, [ebp+arg_0]
0x10059b1a  mov     eax, [edx]
0x10059b1c  mov     ecx, [edx+4]
0x10059b1f  cmp     eax, ecx
0x10059b21  jb      short loc_10059B44
0x10059b23  push    [ebp+arg_4]
0x10059b26  push    1; unsigned int
0x10059b28  mov     eax, [ebx]
0x10059b2a  push    1; void *
0x10059b2c  mov     esi, [eax+8]
0x10059b2f  mov     ecx, esi
0x10059b31  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10059b37  mov     ecx, ebx
0x10059b39  call    esi
0x10059b3b  pop     edi
0x10059b3c  pop     esi
0x10059b3d  pop     ebx
0x10059b3e  mov     esp, ebp
0x10059b40  pop     ebp
0x10059b41  retn    8
0x10059b44  cmp     eax, 10000h
0x10059b49  jb      short loc_10059B60
0x10059b4b  nop     dword ptr [eax+eax+00h]
0x10059b50  shr     eax, 1
0x10059b52  shr     ecx, 1
0x10059b54  cmp     eax, 10000h
0x10059b59  jnb     short loc_10059B50
0x10059b5b  mov     [edx+4], ecx
0x10059b5e  mov     [edx], eax
0x10059b60  test    eax, eax
0x10059b62  jnz     short loc_10059B6A
0x10059b64  push    [ebp+arg_4]
0x10059b67  push    eax
0x10059b68  jmp     short loc_10059B28
0x10059b6a  mov     dword ptr [ebx+34h], 0
0x10059b71  mov     dword ptr [ebx+38h], 0
0x10059b78  mov     dword ptr [ebx+3Ch], 0
0x10059b7f  mov     edi, [ebx+4]
0x10059b82  mov     eax, [edi]
0x10059b84  mov     esi, [eax+4Ch]
0x10059b87  mov     ecx, esi
0x10059b89  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10059b8f  mov     ecx, edi
0x10059b91  call    esi
0x10059b93  mov     ecx, [ebp+arg_0]
0x10059b96  mov     edi, eax
0x10059b98  xor     edx, edx
0x10059b9a  mov     esi, [ebp+arg_4]
0x10059b9d  push    esi; struct Err *
0x10059b9e  mov     [ebp+var_C], edi
0x10059ba1  mov     eax, [ecx]
0x10059ba3  shl     eax, 10h
0x10059ba6  div     dword ptr [ecx+4]
0x10059ba9  mov     ecx, edi; this
0x10059bab  mov     [ebp+var_8], eax
0x10059bae  call    ?CountPages@AbstractSpacemap@@QAEKAAVErr@@@Z; AbstractSpacemap::CountPages(Err &)
0x10059bb3  mov     ecx, eax
0x10059bb5  test    ecx, ecx
0x10059bb7  jnz     short loc_10059BCF
0x10059bb9  push    ecx
0x10059bba  push    0FFFFF9BDh
0x10059bbf  mov     ecx, esi
0x10059bc1  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10059bc6  pop     edi
0x10059bc7  pop     esi
0x10059bc8  pop     ebx
0x10059bc9  mov     esp, ebp
0x10059bcb  pop     ebp
0x10059bcc  retn    8
0x10059bcf  mov     edx, [ebp+var_8]
0x10059bd2  movzx   eax, cx
0x10059bd5  imul    eax, edx
0x10059bd8  shr     ecx, 10h
0x10059bdb  imul    ecx, edx
0x10059bde  push    esi; struct Err *
0x10059bdf  shr     eax, 10h
0x10059be2  add     eax, ecx
0x10059be4  mov     ecx, edi; this
0x10059be6  mov     [ebp+var_8], eax
0x10059be9  inc     eax
0x10059bea  imul    eax, edx
0x10059bed  movzx   eax, ax
0x10059bf0  mov     [ebp+var_14], eax
0x10059bf3  call    ?FirstPage@AbstractSpacemap@@QAEKAAVErr@@@Z; AbstractSpacemap::FirstPage(Err &)
0x10059bf8  mov     edi, 1
0x10059bfd  mov     [ebp+var_4], eax
0x10059c00  mov     edx, eax
0x10059c02  cmp     [ebp+var_8], edi
0x10059c05  jbe     short loc_10059C2C
0x10059c07  mov     ebx, [ebp+var_C]
0x10059c0a  nop     word ptr [eax+eax+00h]
0x10059c10  test    byte ptr [esi], 8
0x10059c13  jnz     short loc_10059C26
0x10059c15  push    esi; struct Err *
0x10059c16  push    edx; unsigned int
0x10059c17  mov     ecx, ebx; this
0x10059c19  call    ?NextPage@AbstractSpacemap@@QAEKKAAVErr@@@Z; AbstractSpacemap::NextPage(ulong,Err &)
0x10059c1e  inc     edi
0x10059c1f  mov     edx, eax
0x10059c21  cmp     edi, [ebp+var_8]
0x10059c24  jb      short loc_10059C10
0x10059c26  mov     ebx, [ebp+var_10]
0x10059c29  mov     [ebp+var_4], edx
0x10059c2c  lea     edi, [ebx+14h]
0x10059c2f  nop
0x10059c30  mov     eax, [ebx+4]
0x10059c33  mov     ecx, [eax+28h]
0x10059c36  push    ecx; struct Transaction *
0x10059c37  push    esi; struct Err *
0x10059c38  push    1; char
0x10059c3a  mov     ecx, [ecx+8]; this
0x10059c3d  push    edx; unsigned int
0x10059c3e  push    edi; struct PageRef *
0x10059c3f  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x10059c44  test    byte ptr [esi], 8
0x10059c47  jnz     short loc_10059C74
0x10059c49  mov     eax, [edi]
0x10059c4b  mov     ecx, edi; this
0x10059c4d  mov     eax, [eax+40h]
0x10059c50  mov     [edi+8], eax
0x10059c53  call    ?First@DataPage@@QBEKXZ; DataPage::First(void)
0x10059c58  mov     [ebx+0Ch], eax
0x10059c5b  test    eax, eax
0x10059c5d  jnz     short loc_10059C8B
0x10059c5f  mov     ecx, [ebp+var_C]; this
0x10059c62  push    esi; struct Err *
0x10059c63  push    [ebp+var_4]; unsigned int
0x10059c66  call    ?NextPage@AbstractSpacemap@@QAEKKAAVErr@@@Z; AbstractSpacemap::NextPage(ulong,Err &)
0x10059c6b  mov     edx, eax
0x10059c6d  mov     [ebp+var_4], edx
0x10059c70  test    edx, edx
0x10059c72  jnz     short loc_10059C8E
0x10059c74  pop     edi
0x10059c75  pop     esi
0x10059c76  mov     dword ptr [ebx+8], 2
0x10059c7d  mov     dword ptr [ebx+0Ch], 0
0x10059c84  pop     ebx
0x10059c85  mov     esp, ebp
0x10059c87  pop     ebp
0x10059c88  retn    8
0x10059c8b  mov     edx, [ebp+var_4]
0x10059c8e  mov     eax, [ebx+0Ch]
0x10059c91  test    eax, eax
0x10059c93  jz      short loc_10059C30
0x10059c95  xor     ecx, ecx
0x10059c97  mov     esi, ecx
0x10059c99  inc     ecx
0x10059c9a  mov     [ebp+var_C], ecx
0x10059c9d  mov     ecx, edi; this
0x10059c9f  push    eax; unsigned int
0x10059ca0  call    ?Next@DataPage@@QBEKK@Z; DataPage::Next(ulong)
0x10059ca5  mov     ecx, [ebp+var_C]
0x10059ca8  mov     [ebx+0Ch], eax
0x10059cab  test    eax, eax
0x10059cad  jnz     short loc_10059C97
0x10059caf  mov     edx, [ebp+var_14]
0x10059cb2  mov     eax, ecx
0x10059cb4  imul    eax, edx
0x10059cb7  shr     edx, 1
0x10059cb9  add     eax, edx
0x10059cbb  shr     eax, 10h
0x10059cbe  cmp     eax, ecx
0x10059cc0  mov     ecx, edi; this
0x10059cc2  cmovb   esi, eax
0x10059cc5  call    ?First@DataPage@@QBEKXZ; DataPage::First(void)
0x10059cca  mov     [ebx+0Ch], eax
0x10059ccd  test    esi, esi
0x10059ccf  jz      short loc_10059CE1
0x10059cd1  push    eax; unsigned int
0x10059cd2  mov     ecx, edi; this
0x10059cd4  call    ?Next@DataPage@@QBEKK@Z; DataPage::Next(ulong)
0x10059cd9  mov     [ebx+0Ch], eax
0x10059cdc  sub     esi, 1
0x10059cdf  jnz     short loc_10059CD1
0x10059ce1  pop     edi
0x10059ce2  pop     esi
0x10059ce3  mov     dword ptr [ebx+8], 0
0x10059cea  pop     ebx
0x10059ceb  mov     esp, ebp
0x10059ced  pop     ebp
0x10059cee  retn    8
```
