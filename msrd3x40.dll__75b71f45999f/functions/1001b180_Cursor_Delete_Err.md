# Cursor::Delete(Err &)

- ea: `0x1001b180`
- end: `0x1001b2c2`
- name: `?Delete@Cursor@@UAEXAAVErr@@@Z`
- size: `322`
- prototype: `void __thiscall(Cursor *__hidden this, struct Err *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1000eb60`
- `0x10018690`
- `0x1001b180`
- `0x1001cf90`
- `0x10044860`
- `0x10044950`
- `0x10044cb0`
- `0x10052cc0`
- `0x1005e7e8`

## pseudocode

```c
void __thiscall Cursor::Delete(Cursor *this, void **a2)
{
  int v3; // eax
  Session **v4; // esi
  Table *v5; // edi
  struct Instance *v6; // eax

  v3 = *((_DWORD *)this + 4);
  if ( (!v3 || v3 == 4) && (int)*a2 < 8 )
  {
    if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
    {
      if ( a2[3] )
        operator delete[](a2[3]);
      if ( a2[4] )
        operator delete[](a2[4]);
    }
    *a2 = (void *)8;
    a2[1] = (void *)-1809;
    a2[2] = 0;
    a2[3] = 0;
    a2[4] = 0;
  }
  v4 = (Session **)this;
  *((_DWORD *)this + 6) = (*(int (__thiscall **)(_DWORD, void **))(**((_DWORD **)this + 8) + 12))(
                            *((_DWORD *)this + 8),
                            a2);
  if ( (*(_BYTE *)a2 & 8) == 0 )
  {
    if ( *((_DWORD *)this + 11) == 3 )
    {
      if ( *((_DWORD *)this + 89) )
        ColumnLv::ResetLongValues((char *)this + 96);
    }
    else
    {
      (*(void (__thiscall **)(Cursor *, int, void **))(*(_DWORD *)this + 20))(this, 3, a2);
      v4 = (Session **)this;
    }
    if ( (*(_BYTE *)a2 & 8) == 0 )
    {
      Session::BeginTransaction(v4[2], 1, a2);
      if ( (*(_BYTE *)a2 & 8) == 0 )
      {
        if ( (Cursor::DeleteRecord((Cursor *)v4, (struct Err *)a2), (*(_BYTE *)a2 & 8) == 0)
          && (Session::CommitTransaction(v4[2], a2, 0), (*(_BYTE *)a2 & 8) == 0)
          || (Session::AbortTransaction(v4[2], (struct Err *)a2), (*(_BYTE *)a2 & 8) == 0) )
        {
          v5 = v4[3];
          v6 = (struct Instance *)(*((int (__thiscall **)(Cursor *))*v4 + 14))(this);
          Table::AddRecords(v5, v6, -1);
          if ( *((_DWORD *)this + 11) != 3 )
          {
            --*(_DWORD *)(*((_DWORD *)this + 3) + 128);
            *((_DWORD *)this + 11) = 3;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1001b180  mov     edi, edi
0x1001b182  push    ebp
0x1001b183  mov     ebp, esp
0x1001b185  push    ecx
0x1001b186  push    ebx
0x1001b187  mov     ebx, [ebp+arg_0]
0x1001b18a  push    esi; unsigned int
0x1001b18b  push    edi; void *
0x1001b18c  mov     edi, ecx
0x1001b18e  mov     [ebp+var_4], edi
0x1001b191  mov     eax, [edi+10h]
0x1001b194  test    eax, eax
0x1001b196  jz      short loc_1001B19D
0x1001b198  cmp     eax, 4
0x1001b19b  jnz     short loc_1001B1ED
0x1001b19d  mov     eax, [ebx]
0x1001b19f  cmp     eax, 8
0x1001b1a2  jge     short loc_1001B1ED
0x1001b1a4  test    eax, 0FFFFFFFEh
0x1001b1a9  jz      short loc_1001B1CB
0x1001b1ab  mov     eax, [ebx+0Ch]
0x1001b1ae  test    eax, eax
0x1001b1b0  jz      short loc_1001B1BB
0x1001b1b2  push    eax; Block
0x1001b1b3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001b1b8  add     esp, 4
0x1001b1bb  mov     eax, [ebx+10h]
0x1001b1be  test    eax, eax
0x1001b1c0  jz      short loc_1001B1CB
0x1001b1c2  push    eax; Block
0x1001b1c3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001b1c8  add     esp, 4
0x1001b1cb  mov     dword ptr [ebx], 8
0x1001b1d1  mov     dword ptr [ebx+4], 0FFFFF8EFh
0x1001b1d8  mov     dword ptr [ebx+8], 0
0x1001b1df  mov     dword ptr [ebx+0Ch], 0
0x1001b1e6  mov     dword ptr [ebx+10h], 0
0x1001b1ed  mov     edi, [edi+20h]
0x1001b1f0  push    ebx; void *
0x1001b1f1  mov     eax, [edi]
0x1001b1f3  mov     esi, [eax+0Ch]
0x1001b1f6  mov     ecx, esi
0x1001b1f8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001b1fe  mov     ecx, edi
0x1001b200  call    esi
0x1001b202  mov     esi, [ebp+var_4]
0x1001b205  mov     [esi+18h], eax
0x1001b208  test    byte ptr [ebx], 8
0x1001b20b  jnz     loc_1001B2B9
0x1001b211  cmp     dword ptr [esi+2Ch], 3
0x1001b215  jz      short loc_1001B231
0x1001b217  mov     eax, [esi]
0x1001b219  push    ebx; unsigned int
0x1001b21a  push    3; void *
0x1001b21c  mov     esi, [eax+14h]
0x1001b21f  mov     ecx, esi
0x1001b221  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001b227  mov     ecx, [ebp+var_4]
0x1001b22a  call    esi
0x1001b22c  mov     esi, [ebp+var_4]
0x1001b22f  jmp     short loc_1001B242
0x1001b231  cmp     dword ptr [esi+164h], 0
0x1001b238  jbe     short loc_1001B242
0x1001b23a  lea     ecx, [esi+60h]
0x1001b23d  call    ?ResetLongValues@ColumnLv@@SGXPAUtagColParams@@W4ColLvSetToKeep@@@Z; ColumnLv::ResetLongValues(tagColParams *,ColLvSetToKeep)
0x1001b242  test    byte ptr [ebx], 8
0x1001b245  jnz     short loc_1001B2B9
0x1001b247  mov     ecx, [esi+8]
0x1001b24a  push    ebx
0x1001b24b  push    1
0x1001b24d  call    ?BeginTransaction@Session@@QAEXW4TransactionType@@AAVErr@@@Z; Session::BeginTransaction(TransactionType,Err &)
0x1001b252  test    byte ptr [ebx], 8
0x1001b255  jnz     short loc_1001B2B9
0x1001b257  push    ebx; struct Err *
0x1001b258  mov     ecx, esi; this
0x1001b25a  call    ?DeleteRecord@Cursor@@AAEXAAVErr@@@Z; Cursor::DeleteRecord(Err &)
0x1001b25f  test    byte ptr [ebx], 8
0x1001b262  jnz     short loc_1001B274
0x1001b264  mov     ecx, [esi+8]; this
0x1001b267  push    0; unsigned int
0x1001b269  push    ebx; struct Err *
0x1001b26a  call    ?CommitTransaction@Session@@QAEXAAVErr@@K@Z; Session::CommitTransaction(Err &,ulong)
0x1001b26f  test    byte ptr [ebx], 8
0x1001b272  jz      short loc_1001B282
0x1001b274  mov     ecx, [esi+8]; this
0x1001b277  push    ebx; struct Err *
0x1001b278  call    ?AbortTransaction@Session@@QAEXAAVErr@@@Z; Session::AbortTransaction(Err &)
0x1001b27d  test    byte ptr [ebx], 8
0x1001b280  jnz     short loc_1001B2B9
0x1001b282  mov     eax, [esi]
0x1001b284  mov     edi, [esi+0Ch]
0x1001b287  mov     esi, [eax+38h]
0x1001b28a  mov     ecx, esi
0x1001b28c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001b292  mov     ebx, [ebp+var_4]
0x1001b295  mov     ecx, ebx
0x1001b297  call    esi
0x1001b299  push    0FFFFFFFFh; int
0x1001b29b  push    eax; struct Instance *
0x1001b29c  mov     ecx, edi; this
0x1001b29e  call    ?AddRecords@Table@@QAEJPAVInstance@@J@Z; Table::AddRecords(Instance *,long)
0x1001b2a3  cmp     dword ptr [ebx+2Ch], 3
0x1001b2a7  jz      short loc_1001B2B9
0x1001b2a9  mov     eax, [ebx+0Ch]
0x1001b2ac  dec     dword ptr [eax+80h]
0x1001b2b2  mov     dword ptr [ebx+2Ch], 3
0x1001b2b9  pop     edi
0x1001b2ba  pop     esi
0x1001b2bb  pop     ebx
0x1001b2bc  mov     esp, ebp
0x1001b2be  pop     ebp
0x1001b2bf  retn    4
```
