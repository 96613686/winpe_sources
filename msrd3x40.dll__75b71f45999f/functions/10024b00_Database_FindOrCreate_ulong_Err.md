# Database::FindOrCreate(ulong,Err &)

- ea: `0x10024b00`
- end: `0x10024cdf`
- name: `?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z`
- size: `479`
- prototype: `struct PageDesc *__thiscall(Database *__hidden this, unsigned int, struct Err *)`
- caller_count: `23`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100105a0`
- `0x10011540`
- `0x10018ff0`
- `0x1001c100`
- `0x1001c8c0`
- `0x1001ccc0`
- `0x10021720`
- `0x10023420`
- `0x10023690`
- `0x10023730`
- `0x100237e0`
- `0x10023830`
- `0x10031300`
- `0x1003ab80`
- `0x1003b600`
- `0x1003c9a0`
- `0x1003f550`
- `0x10046c70`
- `0x10046de0`
- `0x100475f0`
- `0x10047800`
- `0x10052e30`
- `0x1005c7e0`

## callees

- `0x100245a0`
- `0x10024b00`
- `0x10025ee0`
- `0x1005e7e8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10024c0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10024c0d`

## pseudocode

```c
struct PageDesc *__thiscall Database::FindOrCreate(Database *this, unsigned int a2, void **a3)
{
  struct PageDesc *result; // eax
  _DWORD *v5; // eax
  struct PageDesc *PD; // eax
  int v7; // ecx
  struct PageDesc *v8; // esi
  int v9; // eax
  unsigned int v10; // ecx
  char v11; // al
  bool v12; // zf

  if ( a2 <= 0x80000 )
  {
    v5 = *(_DWORD **)(*((_DWORD *)this + 40) + 4 * (a2 & (*((_DWORD *)this + 41) - 1)));
    if ( !v5 )
      goto LABEL_15;
    while ( a2 != v5[3] )
    {
      v5 = (_DWORD *)v5[1];
      if ( !v5 )
        goto LABEL_15;
    }
    result = (struct PageDesc *)v5[4];
    if ( !result )
    {
LABEL_15:
      PD = Database::AllocatePD(this, (struct Err *)a3);
      v8 = PD;
      if ( PD )
      {
        v9 = *((_DWORD *)PD + 4);
        *(_DWORD *)v8 = &HashObject::`vftable';
        *((_DWORD *)v8 + 1) = 0;
        *((_DWORD *)v8 + 4) = v9;
        *((_DWORD *)v8 + 2) = (char *)this + 160;
        *((_DWORD *)v8 + 3) = a2;
        v10 = a2 & (*((_DWORD *)this + 41) - 1);
        *((_DWORD *)v8 + 1) = *(_DWORD *)(*((_DWORD *)this + 40) + 4 * v10);
        *(_DWORD *)(*((_DWORD *)this + 40) + 4 * v10) = v8;
        *(_DWORD *)v8 = &PageDesc::`vftable';
        *((_DWORD *)v8 + 19) = 0;
        *((_DWORD *)v8 + 16) = 1;
        *((_DWORD *)v8 + 5) = this;
        *((_DWORD *)v8 + 15) = 0;
        *((_DWORD *)v8 + 17) = 0;
        *((_DWORD *)v8 + 18) = GetTickCount();
        v11 = *((_BYTE *)v8 + 82);
        *((_BYTE *)v8 + 81) = 0;
        v12 = *((_DWORD *)this + 17) == 1;
        *((_BYTE *)v8 + 80) = 0;
        *((_DWORD *)v8 + 6) = 0;
        *((_BYTE *)v8 + 82) = v11 & 0xF0 | v12;
        *((_DWORD *)v8 + 7) = (a2 << 8) | *((_DWORD *)v8 + 7) & 0xF0 | 3;
        *((_DWORD *)v8 + 8) = *((_DWORD *)v8 + 8) & 0xF0 | 5;
        *((_DWORD *)v8 + 9) = *((_DWORD *)v8 + 9) & 0xF0 | 5;
        *((_DWORD *)v8 + 10) = *((_DWORD *)v8 + 10) & 0xF0 | 5;
        *((_DWORD *)v8 + 11) = *((_DWORD *)v8 + 11) & 0xF0 | 5;
        *((_DWORD *)v8 + 12) = *((_DWORD *)v8 + 12) & 0xF0 | 5;
        *((_DWORD *)v8 + 13) = *((_DWORD *)v8 + 13) & 0xF0 | 5;
        *((_DWORD *)v8 + 14) = *((_DWORD *)v8 + 14) & 0xF0 | 5;
        *((_DWORD *)v8 + 4) = v8;
        return v8;
      }
      else
      {
        Err::SetError(a3, -1011, v7);
        return 0;
      }
    }
  }
  else
  {
    if ( (int)*a3 < 8 )
    {
      if ( ((unsigned int)*a3 & 0xFFFFFFFE) != 0 )
      {
        if ( a3[3] )
          operator delete[](a3[3]);
        if ( a3[4] )
          operator delete[](a3[4]);
      }
      *a3 = (void *)8;
      a3[1] = (void *)-1003;
      a3[2] = 0;
      a3[3] = 0;
      a3[4] = 0;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x10024b00  mov     edi, edi
0x10024b02  push    ebp
0x10024b03  mov     ebp, esp
0x10024b05  push    ecx
0x10024b06  push    ebx
0x10024b07  push    esi
0x10024b08  push    edi
0x10024b09  mov     edi, [ebp+arg_0]
0x10024b0c  mov     ebx, ecx
0x10024b0e  mov     [ebp+var_4], ebx
0x10024b11  cmp     edi, 80000h
0x10024b17  jbe     short loc_10024B77
0x10024b19  mov     esi, [ebp+arg_4]
0x10024b1c  mov     eax, [esi]
0x10024b1e  cmp     eax, 8
0x10024b21  jge     short loc_10024B6C
0x10024b23  test    eax, 0FFFFFFFEh
0x10024b28  jz      short loc_10024B4A
0x10024b2a  mov     eax, [esi+0Ch]
0x10024b2d  test    eax, eax
0x10024b2f  jz      short loc_10024B3A
0x10024b31  push    eax; Block
0x10024b32  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10024b37  add     esp, 4
0x10024b3a  mov     eax, [esi+10h]
0x10024b3d  test    eax, eax
0x10024b3f  jz      short loc_10024B4A
0x10024b41  push    eax; Block
0x10024b42  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10024b47  add     esp, 4
0x10024b4a  mov     dword ptr [esi], 8
0x10024b50  mov     dword ptr [esi+4], 0FFFFFC15h
0x10024b57  mov     dword ptr [esi+8], 0
0x10024b5e  mov     dword ptr [esi+0Ch], 0
0x10024b65  mov     dword ptr [esi+10h], 0
0x10024b6c  pop     edi
0x10024b6d  pop     esi
0x10024b6e  xor     eax, eax
0x10024b70  pop     ebx
0x10024b71  mov     esp, ebp
0x10024b73  pop     ebp
0x10024b74  retn    8
0x10024b77  mov     ecx, [ebx+0A4h]
0x10024b7d  mov     eax, [ebx+0A0h]
0x10024b83  dec     ecx
0x10024b84  and     ecx, edi
0x10024b86  mov     eax, [eax+ecx*4]
0x10024b89  test    eax, eax
0x10024b8b  jz      short loc_10024BA9
0x10024b8d  nop     dword ptr [eax]
0x10024b90  cmp     edi, [eax+0Ch]
0x10024b93  jz      short loc_10024B9E
0x10024b95  mov     eax, [eax+4]
0x10024b98  test    eax, eax
0x10024b9a  jnz     short loc_10024B90
0x10024b9c  jmp     short loc_10024BA9
0x10024b9e  mov     eax, [eax+10h]
0x10024ba1  test    eax, eax
0x10024ba3  jnz     loc_10024CD6
0x10024ba9  push    [ebp+arg_4]; struct Err *
0x10024bac  mov     ecx, ebx; this
0x10024bae  call    ?AllocatePD@Database@@QAEPAVPageDesc@@AAVErr@@@Z; Database::AllocatePD(Err &)
0x10024bb3  mov     esi, eax
0x10024bb5  mov     [ebp+var_4], esi
0x10024bb8  test    esi, esi
0x10024bba  jz      loc_10024CC4
0x10024bc0  mov     eax, [esi+10h]
0x10024bc3  lea     edx, [ebx+0A0h]
0x10024bc9  mov     dword ptr [esi], offset ??_7HashObject@@6B@; const HashObject::`vftable'
0x10024bcf  mov     dword ptr [esi+4], 0
0x10024bd6  mov     [esi+10h], eax
0x10024bd9  mov     [esi+8], edx
0x10024bdc  mov     [esi+0Ch], edi
0x10024bdf  mov     ecx, [edx+4]
0x10024be2  mov     eax, [edx]
0x10024be4  dec     ecx
0x10024be5  and     ecx, edi
0x10024be7  mov     eax, [eax+ecx*4]
0x10024bea  mov     [esi+4], eax
0x10024bed  mov     eax, [edx]
0x10024bef  mov     [eax+ecx*4], esi
0x10024bf2  xor     eax, eax
0x10024bf4  mov     dword ptr [esi], offset ??_7PageDesc@@6B@; const PageDesc::`vftable'
0x10024bfa  mov     [esi+4Ch], eax
0x10024bfd  mov     dword ptr [esi+40h], 1
0x10024c04  mov     [esi+14h], ebx
0x10024c07  mov     [esi+3Ch], eax
0x10024c0a  mov     [esi+44h], eax
0x10024c0d  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10024c13  mov     [esi+48h], eax
0x10024c16  mov     al, [esi+52h]
0x10024c19  mov     byte ptr [esi+51h], 0
0x10024c1d  cmp     dword ptr [ebx+44h], 1
0x10024c21  mov     byte ptr [esi+50h], 0
0x10024c25  setz    cl
0x10024c28  mov     dword ptr [esi+18h], 0
0x10024c2f  and     al, 0FEh
0x10024c31  shl     edi, 8
0x10024c34  or      cl, al
0x10024c36  and     cl, 0F1h
0x10024c39  mov     [esi+52h], cl
0x10024c3c  mov     eax, [esi+1Ch]
0x10024c3f  and     eax, 0F0h
0x10024c44  or      eax, edi
0x10024c46  and     eax, 0FFFFFFF7h
0x10024c49  or      eax, 3
0x10024c4c  mov     [esi+1Ch], eax
0x10024c4f  mov     eax, [esi+20h]
0x10024c52  and     eax, 0F0h
0x10024c57  or      eax, 5
0x10024c5a  mov     [esi+20h], eax
0x10024c5d  mov     eax, [esi+24h]
0x10024c60  and     eax, 0F0h
0x10024c65  or      eax, 5
0x10024c68  mov     [esi+24h], eax
0x10024c6b  mov     eax, [esi+28h]
0x10024c6e  and     eax, 0F0h
0x10024c73  or      eax, 5
0x10024c76  mov     [esi+28h], eax
0x10024c79  mov     eax, [esi+2Ch]
0x10024c7c  and     eax, 0F0h
0x10024c81  or      eax, 5
0x10024c84  mov     [esi+2Ch], eax
0x10024c87  mov     eax, [esi+30h]
0x10024c8a  and     eax, 0F0h
0x10024c8f  or      eax, 5
0x10024c92  mov     [esi+30h], eax
0x10024c95  mov     eax, [esi+34h]
0x10024c98  and     eax, 0F0h
0x10024c9d  or      eax, 5
0x10024ca0  mov     [esi+34h], eax
0x10024ca3  mov     ecx, [esi+38h]
0x10024ca6  and     ecx, 0F0h
0x10024cac  or      ecx, 5
0x10024caf  mov     [esi+38h], ecx
0x10024cb2  mov     [esi+10h], esi
0x10024cb5  test    esi, esi
0x10024cb7  jz      short loc_10024CC6
0x10024cb9  pop     edi
0x10024cba  mov     eax, esi
0x10024cbc  pop     esi
0x10024cbd  pop     ebx
0x10024cbe  mov     esp, ebp
0x10024cc0  pop     ebp
0x10024cc1  retn    8
0x10024cc4  xor     esi, esi
0x10024cc6  push    ecx
0x10024cc7  mov     ecx, [ebp+arg_4]
0x10024cca  push    0FFFFFC0Dh
0x10024ccf  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10024cd4  mov     eax, esi
0x10024cd6  pop     edi
0x10024cd7  pop     esi
0x10024cd8  pop     ebx
0x10024cd9  mov     esp, ebp
0x10024cdb  pop     ebp
0x10024cdc  retn    8
```
