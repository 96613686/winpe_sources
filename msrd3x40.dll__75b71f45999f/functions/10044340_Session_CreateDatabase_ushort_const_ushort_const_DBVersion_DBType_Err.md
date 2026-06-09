# Session::CreateDatabase(ushort const *,ushort const *,DBVersion,DBType,Err &)

- ea: `0x10044340`
- end: `0x10044620`
- name: `?CreateDatabase@Session@@QAEPAVInstance@@PBG0W4DBVersion@@W4DBType@@AAVErr@@@Z`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x10027f20`

## callees

- `0x1000eb60`
- `0x10012db0`
- `0x10012dd0`
- `0x1001f440`
- `0x1001fe30`
- `0x10025ee0`
- `0x100358c0`
- `0x10035910`
- `0x10035e10`
- `0x10044340`
- `0x100451d0`
- `0x1004f7b0`
- `0x10050bc0`
- `0x10051150`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f064`

## pseudocode

```c
struct Instance *__thiscall Session::CreateDatabase(
        Session *this,
        const WCHAR *lpFileName,
        int a3,
        int a4,
        int a5,
        struct Err *a6)
{
  struct Instance *v6; // ebx
  PresOrderList *v7; // esi
  Database *v8; // eax
  int v9; // eax
  struct Database *v10; // eax
  Session *v11; // edx
  unsigned int v12; // eax
  Instance *v13; // eax
  int v14; // ecx
  const unsigned __int16 *v15; // ecx
  int v17[3]; // [esp+10h] [ebp-34h] BYREF
  void *Block; // [esp+1Ch] [ebp-28h]
  void *v19; // [esp+20h] [ebp-24h]
  void *v20; // [esp+24h] [ebp-20h]
  int v21; // [esp+28h] [ebp-1Ch]
  PresOrderList *v22; // [esp+2Ch] [ebp-18h] BYREF
  Session *v23; // [esp+30h] [ebp-14h]
  struct Database *v24; // [esp+34h] [ebp-10h]
  int v25; // [esp+40h] [ebp-4h]

  v23 = this;
  v6 = 0;
  v7 = 0;
  v21 = 0;
  v22 = (PresOrderList *)operator new(0x3CCu);
  v25 = 0;
  v8 = Database::Database(v22, *((struct Connection **)v23 + 12), a6);
  v24 = v8;
  v25 = -1;
  if ( !v8 && *(int *)a6 < 8 )
  {
    if ( (*(_DWORD *)a6 & 0xFFFFFFFE) != 0 )
    {
      if ( *((_DWORD *)a6 + 3) )
        operator delete[](*((void **)a6 + 3));
      if ( *((_DWORD *)a6 + 4) )
        operator delete[](*((void **)a6 + 4));
    }
    v8 = v24;
    *(_DWORD *)a6 = 8;
    *((_DWORD *)a6 + 1) = -1011;
    *((_DWORD *)a6 + 2) = 0;
    *((_DWORD *)a6 + 3) = 0;
    *((_DWORD *)a6 + 4) = 0;
  }
  if ( (*(_BYTE *)a6 & 8) == 0 )
    Database::Create(v8, lpFileName, a3, 0, a5, a6);
  v9 = *(_DWORD *)a6;
  if ( (*(_DWORD *)a6 & 8) == 0 )
  {
    v21 = 1;
    v7 = (PresOrderList *)operator new(0x4Cu);
    v22 = v7;
    v25 = 1;
    *((_DWORD *)v7 + 1) = 0;
    *((_DWORD *)v7 + 2) = 0;
    *(_DWORD *)v7 = operator new[](0xCCu);
    if ( (*(_BYTE *)a6 & 8) == 0 )
      *((_DWORD *)v7 + 1) = 50;
    v10 = v24;
    v11 = v23;
    LOBYTE(v25) = 2;
    *((_DWORD *)v7 + 3) = v23;
    *((_DWORD *)v7 + 4) = v10;
    *((_DWORD *)v7 + 5) = 0;
    *((_DWORD *)v7 + 6) = 0;
    *((_DWORD *)v7 + 7) = 0;
    *((_DWORD *)v7 + 8) = 0;
    *((_DWORD *)v7 + 9) = 0;
    *((_DWORD *)v7 + 10) = 0;
    *((_DWORD *)v7 + 11) = 0;
    *((_DWORD *)v7 + 16) = 1;
    *((_DWORD *)v7 + 15) = 0;
    *((_DWORD *)v7 + 17) = 0;
    *((_DWORD *)v7 + 18) = 0;
    v9 = *(_DWORD *)a6;
    if ( (*(_DWORD *)a6 & 8) == 0 )
    {
      v12 = *((_DWORD *)v11 + 2);
      if ( v12 < *((_DWORD *)v11 + 1) || (Collection::Grow(v11, v12 + 1, a6), v11 = v23, (*(_BYTE *)a6 & 8) == 0) )
        *(_DWORD *)(*(_DWORD *)v11 + 4 * (*((_DWORD *)v11 + 2))++) = v7;
      v9 = *(_DWORD *)a6;
      if ( (*(_DWORD *)a6 & 8) == 0 )
      {
        *((_DWORD *)v7 + 15) = Session::GetAccessMethod(v11, v24, a6);
        v9 = *(_DWORD *)a6;
        if ( (*(_DWORD *)a6 & 8) != 0 )
        {
          Session::DropInstance(v23, v7);
          v9 = *(_DWORD *)a6;
        }
      }
    }
    v25 = -1;
  }
  v22 = v24;
  if ( (v9 & 8) == 0 )
    SystemTable::CreateSystemTables(&v22, v7, (void **)a6);
  if ( (*(_BYTE *)a6 & 8) == 0 )
  {
    v20 = operator new(0x4Cu);
    v25 = 3;
    v13 = Instance::Instance((Instance *)v20, v23, v24, a6);
    v25 = -1;
    v6 = v13;
    Instance::Release(v7);
    v7 = 0;
    if ( !v6 )
    {
      Err::SetError(a6, -1011, v14);
      goto LABEL_29;
    }
    if ( (*(_BYTE *)a6 & 8) == 0 )
    {
      SystemTable::AddMSysObjects((SystemTable *)&v22, v6, a6);
LABEL_29:
      if ( (*(_BYTE *)a6 & 8) == 0 )
        goto LABEL_35;
    }
  }
  if ( v6 )
    Instance::Release(v6);
  if ( v7 )
    Instance::Release(v7);
  v6 = 0;
LABEL_35:
  v15 = (const unsigned __int16 *)v24;
  if ( v24 && !_InterlockedExchangeAdd((volatile signed __int32 *)v24 + 18, 0xFFFFFFFF) )
    (**(void (__thiscall ***)(struct Database *, int))v15)(v24, 1);
  if ( (*(_BYTE *)a6 & 8) != 0 && v21 == 1 )
  {
    v17[0] = 1;
    System::DeleteFileByName(v15, lpFileName, (int)v17);
    if ( (v17[0] & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v19 )
        operator delete[](v19);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x10044340  mov     edi, edi
0x10044342  push    ebp
0x10044343  mov     ebp, esp
0x10044345  push    0FFFFFFFFh
0x10044347  push    offset ?CreateDatabase@Session@@QAEPAVInstance@@PBG0W4DBVersion@@W4DBType@@AAVErr@@@Z_SEH
0x1004434c  mov     eax, large fs:0
0x10044352  push    eax
0x10044353  sub     esp, 28h
0x10044356  push    ebx
0x10044357  push    esi
0x10044358  push    edi
0x10044359  mov     eax, ___security_cookie
0x1004435e  xor     eax, ebp
0x10044360  push    eax; unsigned int
0x10044361  lea     eax, [ebp+var_C]
0x10044364  mov     large fs:0, eax
0x1004436a  mov     [ebp+var_14], ecx
0x1004436d  mov     edi, [ebp+arg_10]
0x10044370  xor     ebx, ebx
0x10044372  push    3CCh; Size
0x10044377  xor     esi, esi
0x10044379  mov     [ebp+var_1C], ebx
0x1004437c  call    ??2@YAPAXI@Z; operator new(uint)
0x10044381  add     esp, 4
0x10044384  mov     [ebp+var_18], eax
0x10044387  mov     ecx, [ebp+var_14]
0x1004438a  push    edi; struct Err *
0x1004438b  mov     [ebp+var_4], esi
0x1004438e  push    dword ptr [ecx+30h]; struct Connection *
0x10044391  mov     ecx, eax; this
0x10044393  call    ??0Database@@QAE@PAVConnection@@AAVErr@@@Z; Database::Database(Connection *,Err &)
0x10044398  mov     [ebp+var_10], eax
0x1004439b  mov     [ebp+var_4], 0FFFFFFFFh
0x100443a2  test    eax, eax
0x100443a4  jnz     short loc_100443FA
0x100443a6  mov     ecx, [edi]
0x100443a8  cmp     ecx, 8
0x100443ab  jge     short loc_100443FA
0x100443ad  test    ecx, 0FFFFFFFEh
0x100443b3  jz      short loc_100443D5
0x100443b5  mov     eax, [edi+0Ch]
0x100443b8  test    eax, eax
0x100443ba  jz      short loc_100443C5
0x100443bc  push    eax; Block
0x100443bd  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100443c2  add     esp, 4
0x100443c5  mov     eax, [edi+10h]
0x100443c8  test    eax, eax
0x100443ca  jz      short loc_100443D5
0x100443cc  push    eax; Block
0x100443cd  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100443d2  add     esp, 4
0x100443d5  mov     eax, [ebp+var_10]
0x100443d8  mov     dword ptr [edi], 8
0x100443de  mov     dword ptr [edi+4], 0FFFFFC0Dh
0x100443e5  mov     dword ptr [edi+8], 0
0x100443ec  mov     dword ptr [edi+0Ch], 0
0x100443f3  mov     dword ptr [edi+10h], 0
0x100443fa  test    byte ptr [edi], 8
0x100443fd  jnz     short loc_10044412
0x100443ff  push    edi
0x10044400  push    [ebp+arg_C]
0x10044403  mov     ecx, eax
0x10044405  push    0
0x10044407  push    [ebp+arg_4]
0x1004440a  push    [ebp+lpFileName]
0x1004440d  call    ?Create@Database@@QAEXPBG0W4DBVersion@@W4DBType@@AAVErr@@@Z; Database::Create(ushort const *,ushort const *,DBVersion,DBType,Err &)
0x10044412  mov     eax, [edi]
0x10044414  test    al, 8
0x10044416  jnz     loc_10044513
0x1004441c  push    4Ch ; 'L'; Size
0x1004441e  mov     [ebp+var_1C], 1
0x10044425  call    ??2@YAPAXI@Z; operator new(uint)
0x1004442a  mov     esi, eax
0x1004442c  mov     [ebp+var_18], esi
0x1004442f  mov     [ebp+var_4], 1
0x10044436  push    0CCh; unsigned int
0x1004443b  mov     dword ptr [esi+4], 0
0x10044442  mov     dword ptr [esi+8], 0
0x10044449  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1004444e  add     esp, 8
0x10044451  mov     [esi], eax
0x10044453  test    byte ptr [edi], 8
0x10044456  jnz     short loc_1004445F
0x10044458  mov     dword ptr [esi+4], 32h ; '2'
0x1004445f  mov     eax, [ebp+var_10]
0x10044462  mov     edx, [ebp+var_14]
0x10044465  mov     byte ptr [ebp+var_4], 2
0x10044469  mov     [esi+0Ch], edx
0x1004446c  mov     [esi+10h], eax
0x1004446f  mov     dword ptr [esi+14h], 0
0x10044476  mov     dword ptr [esi+18h], 0
0x1004447d  mov     dword ptr [esi+1Ch], 0
0x10044484  mov     dword ptr [esi+20h], 0
0x1004448b  mov     dword ptr [esi+24h], 0
0x10044492  mov     dword ptr [esi+28h], 0
0x10044499  mov     dword ptr [esi+2Ch], 0
0x100444a0  mov     dword ptr [esi+40h], 1
0x100444a7  mov     dword ptr [esi+3Ch], 0
0x100444ae  mov     dword ptr [esi+44h], 0
0x100444b5  mov     dword ptr [esi+48h], 0
0x100444bc  mov     eax, [edi]
0x100444be  test    al, 8
0x100444c0  jnz     short loc_1004450C
0x100444c2  mov     eax, [edx+8]
0x100444c5  cmp     eax, [edx+4]
0x100444c8  jb      short loc_100444DC
0x100444ca  push    edi; struct Err *
0x100444cb  inc     eax
0x100444cc  mov     ecx, edx; this
0x100444ce  push    eax; unsigned int
0x100444cf  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x100444d4  test    byte ptr [edi], 8
0x100444d7  mov     edx, [ebp+var_14]
0x100444da  jnz     short loc_100444E7
0x100444dc  mov     ecx, [edx+8]
0x100444df  mov     eax, [edx]
0x100444e1  mov     [eax+ecx*4], esi
0x100444e4  inc     dword ptr [edx+8]
0x100444e7  mov     eax, [edi]
0x100444e9  test    al, 8
0x100444eb  jnz     short loc_1004450C
0x100444ed  push    edi; struct Err *
0x100444ee  push    [ebp+var_10]; struct Database *
0x100444f1  mov     ecx, edx; this
0x100444f3  call    ?GetAccessMethod@Session@@QAEPAVIAccMeth@@PAVDatabase@@AAVErr@@@Z; Session::GetAccessMethod(Database *,Err &)
0x100444f8  mov     [esi+3Ch], eax
0x100444fb  mov     eax, [edi]
0x100444fd  test    al, 8
0x100444ff  jz      short loc_1004450C
0x10044501  mov     ecx, [ebp+var_14]; this
0x10044504  push    esi; struct Instance *
0x10044505  call    ?DropInstance@Session@@QAEXPAVInstance@@@Z; Session::DropInstance(Instance *)
0x1004450a  mov     eax, [edi]
0x1004450c  mov     [ebp+var_4], 0FFFFFFFFh
0x10044513  mov     ecx, [ebp+var_10]
0x10044516  mov     [ebp+var_18], ecx
0x10044519  test    al, 8
0x1004451b  jnz     short loc_10044527
0x1004451d  push    edi; struct Err *
0x1004451e  push    esi; struct Instance *
0x1004451f  lea     ecx, [ebp+var_18]; this
0x10044522  call    ?CreateSystemTables@SystemTable@@QAEXPAVInstance@@AAVErr@@@Z; SystemTable::CreateSystemTables(Instance *,Err &)
0x10044527  test    byte ptr [edi], 8
0x1004452a  jnz     short loc_10044587
0x1004452c  push    4Ch ; 'L'; Size
0x1004452e  call    ??2@YAPAXI@Z; operator new(uint)
0x10044533  add     esp, 4
0x10044536  mov     [ebp+var_20], eax
0x10044539  push    edi; struct Err *
0x1004453a  push    [ebp+var_10]; struct Database *
0x1004453d  mov     ecx, eax; this
0x1004453f  mov     [ebp+var_4], 3
0x10044546  push    [ebp+var_14]; struct Session *
0x10044549  call    ??0Instance@@QAE@PAVSession@@PAVDatabase@@AAVErr@@@Z; Instance::Instance(Session *,Database *,Err &)
0x1004454e  mov     ecx, esi; this
0x10044550  mov     [ebp+var_4], 0FFFFFFFFh
0x10044557  mov     ebx, eax
0x10044559  call    ?Release@Instance@@QAEXXZ; Instance::Release(void)
0x1004455e  xor     esi, esi
0x10044560  test    ebx, ebx
0x10044562  jnz     short loc_10044573
0x10044564  push    ecx
0x10044565  push    0FFFFFC0Dh
0x1004456a  mov     ecx, edi
0x1004456c  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10044571  jmp     short loc_10044582
0x10044573  test    byte ptr [edi], 8
0x10044576  jnz     short loc_10044587
0x10044578  push    edi; struct Err *
0x10044579  push    ebx; struct Instance *
0x1004457a  lea     ecx, [ebp+var_18]; this
0x1004457d  call    ?AddMSysObjects@SystemTable@@QAEXPAVInstance@@AAVErr@@@Z; SystemTable::AddMSysObjects(Instance *,Err &)
0x10044582  test    byte ptr [edi], 8
0x10044585  jz      short loc_1004459F
0x10044587  test    ebx, ebx
0x10044589  jz      short loc_10044592
0x1004458b  mov     ecx, ebx; this
0x1004458d  call    ?Release@Instance@@QAEXXZ; Instance::Release(void)
0x10044592  test    esi, esi
0x10044594  jz      short loc_1004459D
0x10044596  mov     ecx, esi; this
0x10044598  call    ?Release@Instance@@QAEXXZ; Instance::Release(void)
0x1004459d  xor     ebx, ebx
0x1004459f  mov     ecx, [ebp+var_10]
0x100445a2  test    ecx, ecx
0x100445a4  jz      short loc_100445C3
0x100445a6  or      eax, 0FFFFFFFFh
0x100445a9  lock xadd [ecx+48h], eax
0x100445ae  jnz     short loc_100445C3
0x100445b0  mov     eax, [ecx]
0x100445b2  push    1; void *
0x100445b4  mov     esi, [eax]
0x100445b6  mov     ecx, esi
0x100445b8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100445be  mov     ecx, [ebp+var_10]
0x100445c1  call    esi
0x100445c3  test    byte ptr [edi], 8
0x100445c6  jz      short loc_1004460A
0x100445c8  cmp     [ebp+var_1C], 1
0x100445cc  jnz     short loc_1004460A
0x100445ce  lea     eax, [ebp+var_34]
0x100445d1  mov     [ebp+var_34], 1
0x100445d8  push    eax
0x100445d9  push    [ebp+lpFileName]; lpFileName
0x100445dc  call    ?DeleteFileByName@System@@QAEXPBGAAVErr@@@Z; System::DeleteFileByName(ushort const *,Err &)
0x100445e1  test    [ebp+var_34], 0FFFFFFFEh
0x100445e8  jz      short loc_1004460A
0x100445ea  mov     eax, [ebp+Block]
0x100445ed  test    eax, eax
0x100445ef  jz      short loc_100445FA
0x100445f1  push    eax; Block
0x100445f2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100445f7  add     esp, 4
0x100445fa  mov     eax, [ebp+var_24]
0x100445fd  test    eax, eax
0x100445ff  jz      short loc_1004460A
0x10044601  push    eax; Block
0x10044602  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10044607  add     esp, 4
0x1004460a  mov     eax, ebx
0x1004460c  mov     ecx, [ebp+var_C]
0x1004460f  mov     large fs:0, ecx
0x10044616  pop     ecx
0x10044617  pop     edi
0x10044618  pop     esi
0x10044619  pop     ebx
0x1004461a  mov     esp, ebp
0x1004461c  pop     ebp
0x1004461d  retn    14h
0x100613b0  push    3CCh; unsigned int
0x100613b5  mov     eax, [ebp+var_18]
0x100613b8  push    eax; Block
0x100613b9  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100613be  add     esp, 8
0x100613c1  retn
0x100613c2  push    4Ch ; 'L'; unsigned int
0x100613c4  mov     eax, [ebp+var_18]
0x100613c7  push    eax; Block
0x100613c8  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100613cd  add     esp, 8
0x100613d0  retn
0x100613d1  mov     ecx, [ebp+var_18]; this
0x100613d4  jmp     ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x100613d9  push    4Ch ; 'L'; unsigned int
0x100613db  mov     eax, [ebp+var_20]
0x100613de  push    eax; Block
0x100613df  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100613e4  add     esp, 8
0x100613e7  retn
0x100613ed  nop
0x100613ee  nop
0x100613ef  mov     edx, [esp-4+arg_4]
0x100613f3  lea     eax, [edx+0Ch]
0x100613f6  mov     ecx, [edx-38h]
0x100613f9  xor     ecx, eax; StackCookie
0x100613fb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061400  mov     eax, offset stru_10063E48
0x10061405  jmp     ___CxxFrameHandler3
```
