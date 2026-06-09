# Transaction::Commit(TransactionType,Err &)

- ea: `0x1005d310`
- end: `0x1005d503`
- name: `?Commit@Transaction@@QAEXW4TransactionType@@AAVErr@@@Z`
- size: `499`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1001f2d0`
- `0x10020430`
- `0x10044950`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x1001f2d0`
- `0x10022d30`
- `0x10022e00`
- `0x10024070`
- `0x10025bc0`
- `0x10048340`
- `0x1005d310`
- `0x1005d510`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
int __thiscall Transaction::Commit(int *this, int a2, struct Err *a3)
{
  int v4; // edi
  _DWORD *v5; // esi
  int result; // eax
  _DWORD v7[5]; // [esp+10h] [ebp-38h] BYREF
  _DWORD v8[3]; // [esp+24h] [ebp-24h] BYREF
  void *Block; // [esp+30h] [ebp-18h]
  void *v10; // [esp+34h] [ebp-14h]
  int v11; // [esp+38h] [ebp-10h]
  int v12; // [esp+44h] [ebp-4h]

  v4 = *this;
  if ( *this == 1 )
  {
    v5 = (_DWORD *)this[2];
    if ( *(_DWORD *)(v5[15] + 96) )
    {
      v8[0] = *this;
      v12 = 0;
      if ( (v5[58] & 1) != 0 && !v5[242] && Database::LockAll(v5) == 1 )
      {
        v5[242] = 1;
        AbstractSpacemap::AddPages(v5 + 231, v8, v5 + 69, 1);
        Database::UnlockAll((Database *)v5);
        if ( (v8[0] & 8) != 0
          || (MiniTransaction::Commit((MiniTransaction *)(v5 + 59), (struct Err *)v8), (v8[0] & 8) != 0) )
        {
          v7[0] = 1;
          LOBYTE(v12) = 1;
          Transaction::Abort(v5 + 59, 1, v7);
          Err::~Err((Err *)v7);
        }
        else
        {
          v5[58] &= ~1u;
        }
        v5[242] = 0;
      }
      v12 = -1;
      if ( (v8[0] & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v10 )
          operator delete[](v10);
      }
    }
  }
  result = Database::CommitPDs(this[2], this, a2, a3);
  if ( (*(_BYTE *)a3 & 8) == 0 )
  {
    result = 56 * v4 + this[9];
    v11 = 56 * v4;
    if ( *(_DWORD *)(result - 44) )
    {
      if ( v4 == 1 )
      {
        (*(void (__thiscall **)(int, int, _DWORD, struct Err *))(*(_DWORD *)this[2] + 12))(this[2], result - 40, 0, a3);
        if ( (*(_BYTE *)a3 & 8) == 0 )
          (*(void (__thiscall **)(int, int, int, struct Err *))(*(_DWORD *)this[2] + 12))(
            this[2],
            v11 - 20 + this[9],
            1,
            a3);
      }
      else
      {
        *(_DWORD *)(result - 100) = 1;
        DynaBitmap::Move((DynaBitmap *)(this[9] + 56 * v4 - 96), (struct Bitmap *)(this[9] + 56 * v4 - 40), a3);
        if ( (*(_BYTE *)a3 & 8) == 0 )
          DynaBitmap::Move((DynaBitmap *)(this[9] + v11 - 76), (struct Bitmap *)(this[9] + v11 - 20), a3);
      }
      result = this[9];
      *(_DWORD *)(result + v11 - 44) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1005d310  mov     edi, edi
0x1005d312  push    ebp
0x1005d313  mov     ebp, esp
0x1005d315  push    0FFFFFFFFh
0x1005d317  push    offset ?Commit@Transaction@@QAEXW4TransactionType@@AAVErr@@@Z_SEH
0x1005d31c  mov     eax, large fs:0
0x1005d322  push    eax
0x1005d323  sub     esp, 2Ch
0x1005d326  push    ebx
0x1005d327  push    esi
0x1005d328  push    edi
0x1005d329  mov     eax, ___security_cookie
0x1005d32e  xor     eax, ebp
0x1005d330  push    eax
0x1005d331  lea     eax, [ebp+var_C]
0x1005d334  mov     large fs:0, eax
0x1005d33a  mov     ebx, ecx
0x1005d33c  mov     edi, [ebx]
0x1005d33e  cmp     edi, 1
0x1005d341  jnz     loc_1005D42F
0x1005d347  mov     esi, [ebx+8]
0x1005d34a  mov     eax, [esi+3Ch]
0x1005d34d  cmp     dword ptr [eax+60h], 0
0x1005d351  jz      loc_1005D42F
0x1005d357  mov     [ebp+var_24], edi
0x1005d35a  mov     [ebp+var_4], 0
0x1005d361  test    byte ptr [esi+0E8h], 1
0x1005d368  jz      loc_1005D3FF
0x1005d36e  cmp     dword ptr [esi+3C8h], 0
0x1005d375  jnz     loc_1005D3FF
0x1005d37b  mov     ecx, esi
0x1005d37d  call    ?LockAll@Database@@IAE?AW4DBBool@@XZ; Database::LockAll(void)
0x1005d382  cmp     eax, edi
0x1005d384  jnz     short loc_1005D3FF
0x1005d386  push    edi
0x1005d387  lea     ecx, [esi+114h]
0x1005d38d  mov     [esi+3C8h], edi
0x1005d393  push    ecx
0x1005d394  lea     eax, [ebp+var_24]
0x1005d397  push    eax
0x1005d398  lea     eax, [esi+39Ch]
0x1005d39e  push    eax
0x1005d39f  call    ?AddPages@AbstractSpacemap@@QAEXAAVBitmap@@AAVErr@@W4SMAssertAction@@H@Z; AbstractSpacemap::AddPages(Bitmap &,Err &,SMAssertAction,int)
0x1005d3a4  mov     ecx, esi; this
0x1005d3a6  call    ?UnlockAll@Database@@IAEXXZ; Database::UnlockAll(void)
0x1005d3ab  mov     eax, [ebp+var_24]
0x1005d3ae  test    al, 8
0x1005d3b0  jnz     short loc_1005D3C8
0x1005d3b2  lea     eax, [ebp+var_24]
0x1005d3b5  lea     ecx, [esi+0ECh]; this
0x1005d3bb  push    eax; struct Err *
0x1005d3bc  call    ?Commit@MiniTransaction@@QAEXAAVErr@@@Z; MiniTransaction::Commit(Err &)
0x1005d3c1  mov     eax, [ebp+var_24]
0x1005d3c4  test    al, 8
0x1005d3c6  jz      short loc_1005D3EE
0x1005d3c8  mov     [ebp+var_38], 1
0x1005d3cf  lea     eax, [ebp+var_38]
0x1005d3d2  mov     byte ptr [ebp+var_4], 1
0x1005d3d6  push    eax
0x1005d3d7  lea     ecx, [esi+0ECh]
0x1005d3dd  push    1
0x1005d3df  call    ?Abort@Transaction@@QAEXW4TransactionType@@AAVErr@@@Z; Transaction::Abort(TransactionType,Err &)
0x1005d3e4  lea     ecx, [ebp+var_38]; this
0x1005d3e7  call    ??1Err@@QAE@XZ; Err::~Err(void)
0x1005d3ec  jmp     short loc_1005D3F5
0x1005d3ee  and     dword ptr [esi+0E8h], 0FFFFFFFEh
0x1005d3f5  mov     dword ptr [esi+3C8h], 0
0x1005d3ff  mov     [ebp+var_4], 0FFFFFFFFh
0x1005d406  test    [ebp+var_24], 0FFFFFFFEh
0x1005d40d  jz      short loc_1005D42F
0x1005d40f  mov     eax, [ebp+Block]
0x1005d412  test    eax, eax
0x1005d414  jz      short loc_1005D41F
0x1005d416  push    eax; Block
0x1005d417  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005d41c  add     esp, 4
0x1005d41f  mov     eax, [ebp+var_14]
0x1005d422  test    eax, eax
0x1005d424  jz      short loc_1005D42F
0x1005d426  push    eax; Block
0x1005d427  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005d42c  add     esp, 4
0x1005d42f  mov     esi, [ebp+arg_4]
0x1005d432  mov     ecx, [ebx+8]
0x1005d435  push    esi
0x1005d436  push    [ebp+arg_0]
0x1005d439  push    ebx
0x1005d43a  call    ?CommitPDs@Database@@QAEXAAVTransaction@@W4TransactionType@@AAVErr@@@Z; Database::CommitPDs(Transaction &,TransactionType,Err &)
0x1005d43f  test    byte ptr [esi], 8
0x1005d442  jnz     loc_1005D4EF
0x1005d448  mov     eax, [ebx+24h]
0x1005d44b  lea     ecx, ds:0[edi*8]
0x1005d452  sub     ecx, edi
0x1005d454  shl     ecx, 3
0x1005d457  add     eax, ecx
0x1005d459  mov     [ebp+var_10], ecx
0x1005d45c  cmp     dword ptr [eax-2Ch], 0
0x1005d460  jz      loc_1005D4EF
0x1005d466  push    esi; struct Err *
0x1005d467  cmp     edi, 1
0x1005d46a  jnz     short loc_1005D4B3
0x1005d46c  mov     edi, [ebx+8]
0x1005d46f  add     eax, 0FFFFFFD8h
0x1005d472  push    0; unsigned int
0x1005d474  push    eax; void *
0x1005d475  mov     edx, [edi]
0x1005d477  mov     esi, [edx+0Ch]
0x1005d47a  mov     ecx, esi
0x1005d47c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005d482  mov     ecx, edi
0x1005d484  call    esi
0x1005d486  mov     eax, [ebp+arg_4]
0x1005d489  test    byte ptr [eax], 8
0x1005d48c  jnz     short loc_1005D4E1
0x1005d48e  mov     edi, [ebx+8]
0x1005d491  mov     ecx, [ebp+var_10]
0x1005d494  push    eax
0x1005d495  mov     eax, [ebx+24h]
0x1005d498  add     ecx, 0FFFFFFECh
0x1005d49b  mov     esi, [edi]
0x1005d49d  add     eax, ecx
0x1005d49f  push    1; unsigned int
0x1005d4a1  push    eax; void *
0x1005d4a2  mov     esi, [esi+0Ch]
0x1005d4a5  mov     ecx, esi
0x1005d4a7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005d4ad  mov     ecx, edi
0x1005d4af  call    esi
0x1005d4b1  jmp     short loc_1005D4E1
0x1005d4b3  mov     dword ptr [eax-64h], 1
0x1005d4ba  add     ecx, [ebx+24h]
0x1005d4bd  lea     eax, [ecx-28h]
0x1005d4c0  add     ecx, 0FFFFFFA0h; this
0x1005d4c3  push    eax; struct Bitmap *
0x1005d4c4  call    ?Move@DynaBitmap@@QAEXAAVBitmap@@AAVErr@@@Z; DynaBitmap::Move(Bitmap &,Err &)
0x1005d4c9  test    byte ptr [esi], 8
0x1005d4cc  jnz     short loc_1005D4E1
0x1005d4ce  mov     ecx, [ebp+var_10]
0x1005d4d1  add     ecx, [ebx+24h]
0x1005d4d4  push    esi; struct Err *
0x1005d4d5  lea     eax, [ecx-14h]
0x1005d4d8  add     ecx, 0FFFFFFB4h; this
0x1005d4db  push    eax; struct Bitmap *
0x1005d4dc  call    ?Move@DynaBitmap@@QAEXAAVBitmap@@AAVErr@@@Z; DynaBitmap::Move(Bitmap &,Err &)
0x1005d4e1  mov     eax, [ebx+24h]
0x1005d4e4  mov     ecx, [ebp+var_10]
0x1005d4e7  mov     dword ptr [eax+ecx-2Ch], 0
0x1005d4ef  mov     ecx, [ebp+var_C]
0x1005d4f2  mov     large fs:0, ecx
0x1005d4f9  pop     ecx
0x1005d4fa  pop     edi
0x1005d4fb  pop     esi
0x1005d4fc  pop     ebx
0x1005d4fd  mov     esp, ebp
0x1005d4ff  pop     ebp
0x1005d500  retn    8
0x100626a0  lea     ecx, [ebp+var_24]; this
0x100626a3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100626a8  lea     ecx, [ebp+var_38]; this
0x100626ab  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100626b5  nop
0x100626b6  nop
0x100626b7  mov     edx, [esp-4+arg_4]
0x100626bb  lea     eax, [edx+0Ch]
0x100626be  mov     ecx, [edx-3Ch]
0x100626c1  xor     ecx, eax; StackCookie
0x100626c3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100626c8  mov     eax, offset stru_10064C4C
0x100626cd  jmp     ___CxxFrameHandler3
```
