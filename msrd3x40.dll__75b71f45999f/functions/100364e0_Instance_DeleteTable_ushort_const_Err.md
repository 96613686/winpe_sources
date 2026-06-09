# Instance::DeleteTable(ushort const *,Err &)

- ea: `0x100364e0`
- end: `0x10036616`
- name: `?DeleteTable@Instance@@QAEXPBGAAVErr@@@Z`
- size: `310`
- prototype: `void __thiscall(Instance *__hidden this, const unsigned __int16 *, struct Err *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10037190`

## callees

- `0x1000eb60`
- `0x100364e0`
- `0x10037710`
- `0x10037bb0`
- `0x10052140`
- `0x100536a0`
- `0x10053950`
- `0x1005e7e8`

## pseudocode

```c
void __thiscall Instance::DeleteTable(Instance *this, unsigned __int16 *a2, void **a3)
{
  Instance *v3; // edi
  int v4; // eax
  int v5; // eax
  int v6; // ecx
  unsigned int v7; // edx
  struct Instance *v8; // eax
  Table *v9; // esi
  struct Instance *v11; // [esp+Ch] [ebp-8h]
  unsigned int v12; // [esp+10h] [ebp-4h] BYREF

  v3 = this;
  v12 = 0;
  v4 = *(_DWORD *)(*((_DWORD *)this + 4) + 104);
  if ( (!v4 || v4 == 3) && (int)*a3 < 8 )
  {
    if ( ((unsigned int)*a3 & 0xFFFFFFFE) != 0 )
    {
      if ( a3[3] )
        operator delete[](a3[3]);
      if ( a3[4] )
        operator delete[](a3[4]);
    }
    *a3 = (void *)8;
    a3[1] = (void *)-1809;
    a3[2] = 0;
    a3[3] = 0;
    a3[4] = 0;
  }
  if ( (*(_BYTE *)a3 & 8) != 0
    || (Instance::ReadSysObjRecord(v3, 0xF000001u, a2, a3), (*(_BYTE *)a3 & 8) != 0)
    || ((*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, void **))(**((_DWORD **)v3 + 5) + 108))(
          *((_DWORD *)v3 + 5),
          *((_DWORD *)this + 8),
          &v12,
          4,
          0,
          a3),
        v3 = this,
        (*(_BYTE *)a3 & 8) != 0) )
  {
    v9 = 0;
  }
  else
  {
    v5 = *((_DWORD *)this + 4);
    v6 = 0;
    v7 = *(_DWORD *)(v5 + 56);
    if ( !v7 )
      goto LABEL_17;
    v8 = *(struct Instance **)(v5 + 48);
    v11 = v8;
    while ( 1 )
    {
      v9 = (Table *)*((_DWORD *)v8 + v6);
      if ( *((_DWORD *)v9 + 10) == v12 )
        break;
      v8 = v11;
      if ( ++v6 >= v7 )
        goto LABEL_17;
    }
    if ( v9 )
      Table::CompatibleMode((int)v9, *((struct Session **)v3 + 3), 2u, (struct Err *)a3);
    else
LABEL_17:
      v9 = Instance::OpenTable((struct Session **)v3, a2, v12, 2, (struct Err *)a3);
  }
  if ( (*(_BYTE *)a3 & 8) == 0 )
  {
    if ( v9 )
    {
      ++*((_DWORD *)v9 + 19);
      Table::Delete((struct Database **)v9, v3, a3);
      Table::Release(v9, v3);
    }
  }
}

```

## disassembly

```asm
0x100364e0  mov     edi, edi
0x100364e2  push    ebp
0x100364e3  mov     ebp, esp
0x100364e5  sub     esp, 8
0x100364e8  push    ebx
0x100364e9  mov     ebx, [ebp+arg_4]
0x100364ec  push    esi
0x100364ed  push    edi
0x100364ee  mov     edi, ecx
0x100364f0  mov     [ebp+var_4], 0
0x100364f7  mov     [ebp+var_8], edi
0x100364fa  mov     eax, [edi+10h]
0x100364fd  mov     eax, [eax+68h]
0x10036500  test    eax, eax
0x10036502  jz      short loc_10036509
0x10036504  cmp     eax, 3
0x10036507  jnz     short loc_10036559
0x10036509  mov     eax, [ebx]
0x1003650b  cmp     eax, 8
0x1003650e  jge     short loc_10036559
0x10036510  test    eax, 0FFFFFFFEh
0x10036515  jz      short loc_10036537
0x10036517  mov     eax, [ebx+0Ch]
0x1003651a  test    eax, eax
0x1003651c  jz      short loc_10036527
0x1003651e  push    eax; Block
0x1003651f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036524  add     esp, 4
0x10036527  mov     eax, [ebx+10h]
0x1003652a  test    eax, eax
0x1003652c  jz      short loc_10036537
0x1003652e  push    eax; Block
0x1003652f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036534  add     esp, 4
0x10036537  mov     dword ptr [ebx], 8
0x1003653d  mov     dword ptr [ebx+4], 0FFFFF8EFh
0x10036544  mov     dword ptr [ebx+8], 0
0x1003654b  mov     dword ptr [ebx+0Ch], 0
0x10036552  mov     dword ptr [ebx+10h], 0
0x10036559  test    byte ptr [ebx], 8
0x1003655c  jnz     loc_100365EE
0x10036562  push    ebx; struct Err *
0x10036563  push    [ebp+arg_0]; unsigned __int16 *
0x10036566  mov     ecx, edi; this
0x10036568  push    0F000001h; unsigned int
0x1003656d  call    ?ReadSysObjRecord@Instance@@QAEXKPBGAAVErr@@@Z; Instance::ReadSysObjRecord(ulong,ushort const *,Err &)
0x10036572  test    byte ptr [ebx], 8
0x10036575  jnz     short loc_100365EE
0x10036577  mov     edi, [edi+14h]
0x1003657a  lea     eax, [ebp+var_4]
0x1003657d  push    ebx
0x1003657e  push    0
0x10036580  push    4
0x10036582  mov     esi, [edi]
0x10036584  push    eax; unsigned int
0x10036585  mov     eax, [ebp+var_8]
0x10036588  mov     esi, [esi+6Ch]
0x1003658b  mov     ecx, esi
0x1003658d  push    dword ptr [eax+20h]; void *
0x10036590  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036596  mov     ecx, edi
0x10036598  call    esi
0x1003659a  test    byte ptr [ebx], 8
0x1003659d  mov     edi, [ebp+var_8]
0x100365a0  jnz     short loc_100365EE
0x100365a2  mov     eax, [edi+10h]
0x100365a5  xor     ecx, ecx
0x100365a7  mov     edx, [eax+38h]
0x100365aa  test    edx, edx
0x100365ac  jz      short loc_100365C7
0x100365ae  mov     eax, [eax+30h]
0x100365b1  mov     [ebp+var_8], eax
0x100365b4  mov     esi, [eax+ecx*4]
0x100365b7  mov     eax, [esi+28h]
0x100365ba  cmp     eax, [ebp+var_4]
0x100365bd  jz      short loc_100365DB
0x100365bf  mov     eax, [ebp+var_8]
0x100365c2  inc     ecx
0x100365c3  cmp     ecx, edx
0x100365c5  jb      short loc_100365B4
0x100365c7  push    ebx
0x100365c8  push    2
0x100365ca  push    [ebp+var_4]
0x100365cd  mov     ecx, edi
0x100365cf  push    [ebp+arg_0]
0x100365d2  call    ?OpenTable@Instance@@AAEPAVTable@@PBGKW4TblMode@@AAVErr@@@Z; Instance::OpenTable(ushort const *,ulong,TblMode,Err &)
0x100365d7  mov     esi, eax
0x100365d9  jmp     short loc_100365F0
0x100365db  test    esi, esi
0x100365dd  jz      short loc_100365C7
0x100365df  push    ebx
0x100365e0  push    2
0x100365e2  push    dword ptr [edi+0Ch]
0x100365e5  mov     ecx, esi
0x100365e7  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x100365ec  jmp     short loc_100365F0
0x100365ee  xor     esi, esi
0x100365f0  test    byte ptr [ebx], 8
0x100365f3  jnz     short loc_1003660D
0x100365f5  test    esi, esi
0x100365f7  jz      short loc_1003660D
0x100365f9  inc     dword ptr [esi+4Ch]
0x100365fc  mov     ecx, esi; this
0x100365fe  push    ebx; struct Err *
0x100365ff  push    edi; struct Instance *
0x10036600  call    ?Delete@Table@@QAEXPAVInstance@@AAVErr@@@Z; Table::Delete(Instance *,Err &)
0x10036605  push    edi; struct Instance *
0x10036606  mov     ecx, esi; this
0x10036608  call    ?Release@Table@@QAEJPAVInstance@@@Z; Table::Release(Instance *)
0x1003660d  pop     edi
0x1003660e  pop     esi
0x1003660f  pop     ebx
0x10036610  mov     esp, ebp
0x10036612  pop     ebp
0x10036613  retn    8
```
