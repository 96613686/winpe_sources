# Table::Create(Instance *,ushort const *,ulong,ulong,Err &)

- ea: `0x10052e30`
- end: `0x100533ee`
- name: `?Create@Table@@QAEXPAVInstance@@PBGKKAAVErr@@@Z`
- size: `1470`
- prototype: `void __thiscall(Table *__hidden this, struct Instance *, const unsigned __int16 *, unsigned int, unsigned int, struct Err *)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10035f50`
- `0x10044e20`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10010580`
- `0x10020af0`
- `0x10020e70`
- `0x10024b00`
- `0x10025f50`
- `0x10026020`
- `0x100272b0`
- `0x10042d20`
- `0x10044860`
- `0x10044950`
- `0x10047d30`
- `0x10047e10`
- `0x10047eb0`
- `0x10052e30`
- `0x10057ce0`
- `0x10057e90`
- `0x100591e0`
- `0x10059320`
- `0x1005a700`
- `0x1005a750`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10052f72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10052f72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10052f9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10052f9f`

## pseudocode

```c
void __thiscall Table::Create(
        Table *this,
        struct Transaction **a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        struct Err *a6)
{
  Table *v6; // edi
  struct Err *v7; // ecx
  struct Session *v8; // esi
  int v9; // eax
  bool v10; // zf
  int v11; // ecx
  unsigned int v12; // eax
  int v13; // esi
  PageDesc *v14; // eax
  struct Transaction *v15; // esi
  unsigned int v16; // eax
  int v17; // ecx
  unsigned int v18; // eax
  int v19; // ecx
  int v20; // esi
  void *v21; // eax
  struct Transaction *v22; // esi
  struct Transaction *v23; // esi
  unsigned __int16 *v24; // ecx
  int v26; // ecx
  char v27; // al
  struct Session *v28; // esi
  int v29; // ebx
  int v30; // eax
  unsigned int v31; // ecx
  int v32; // eax
  unsigned int v33; // eax
  double *v34; // [esp+0h] [ebp-DCh]
  unsigned int v35[3]; // [esp+10h] [ebp-CCh] BYREF
  unsigned int v36; // [esp+1Ch] [ebp-C0h] BYREF
  unsigned int v37; // [esp+20h] [ebp-BCh] BYREF
  int v38; // [esp+24h] [ebp-B8h] BYREF
  int v39; // [esp+28h] [ebp-B4h] BYREF
  void *Block; // [esp+2Ch] [ebp-B0h]
  void *v41; // [esp+30h] [ebp-ACh]
  void *v42; // [esp+34h] [ebp-A8h]
  int v43; // [esp+38h] [ebp-A4h] BYREF
  int v44; // [esp+3Ch] [ebp-A0h]
  unsigned int v45; // [esp+44h] [ebp-98h]
  struct Session *v46; // [esp+48h] [ebp-94h]
  unsigned int v47; // [esp+4Ch] [ebp-90h] BYREF
  Table *v48; // [esp+50h] [ebp-8Ch]
  unsigned __int16 *v49; // [esp+54h] [ebp-88h]
  unsigned int v50; // [esp+58h] [ebp-84h] BYREF
  struct Err *v51; // [esp+5Ch] [ebp-80h]
  struct Instance *v52; // [esp+60h] [ebp-7Ch]
  struct Transaction *v53; // [esp+64h] [ebp-78h]
  _BYTE v54[96]; // [esp+68h] [ebp-74h] BYREF
  int v55; // [esp+D8h] [ebp-4h]

  v6 = this;
  v48 = this;
  v7 = (struct Err *)a3;
  v52 = (struct Instance *)a2;
  v8 = a2[3];
  v53 = a2[15];
  LOWORD(v47) = 1;
  v9 = *((_DWORD *)v48 + 9);
  v50 = 0;
  v37 = 251658241;
  v36 = 0;
  v10 = *(_DWORD *)(v9 + 68) == 1;
  v49 = a3;
  LOBYTE(v51) = 0;
  v46 = v8;
  if ( !v10 )
  {
    Session::BeginTransaction(v8, 1, a6);
    if ( (*(_BYTE *)a6 & 8) == 0 )
      *((_DWORD *)v6 + 17) = *((_DWORD *)v8 + 14);
    v11 = *(_DWORD *)a6 >> 3;
    LOBYTE(v11) = ~(_BYTE)v11;
    v7 = (struct Err *)(v11 & 0xFFFFFF01);
    v51 = v7;
  }
  if ( (*(_BYTE *)a6 & 8) != 0 )
    goto LABEL_49;
  v43 = 0;
  v44 = 0;
  v55 = 0;
  v39 = 0;
  Block = 0;
  v41 = 0;
  v42 = 0;
  AbstractSpacemap::AbstractSpacemap((AbstractSpacemap *)v54);
  LOBYTE(v55) = 2;
  v12 = (*(int (__thiscall **)(_DWORD, _DWORD, struct Err *))(**((_DWORD **)v52 + 4) + 4))(*((_DWORD *)v52 + 4), 0, a6);
  v10 = (*(_BYTE *)a6 & 8) == 0;
  v45 = v12;
  v50 = v12;
  if ( !v10 )
    goto LABEL_11;
  v13 = *((_DWORD *)v53 + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 112));
  v14 = Database::FindOrCreate((Database *)v13, v45, a6);
  if ( (*(_BYTE *)a6 & 8) == 0 )
    PageDesc::DontReadPage(v14, (struct PageRef *)&v43, v53, a6);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 112));
  if ( (*(_BYTE *)a6 & 8) != 0 )
  {
LABEL_11:
    v6 = v48;
    v16 = 0;
    v15 = v53;
  }
  else
  {
    v6 = v48;
    TblPage::Initialize(&v39, v44, 78, *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v48 + 9) + 60) + 104));
    v15 = v53;
    v16 = Spacemap::Create((Spacemap *)v54, v53, a6, 0);
  }
  if ( (*(_BYTE *)a6 & 8) != 0
    || (v17 = v44,
        *((_DWORD *)v6 + 7) = v16,
        *(_DWORD *)(v17 + 35) = v16,
        v18 = Spacemap::Create((Spacemap *)v54, v15, a6, v16),
        (*(_BYTE *)a6 & 8) != 0) )
  {
    v20 = v43;
  }
  else
  {
    v19 = v44;
    v20 = v43;
    *((_DWORD *)v6 + 8) = v18;
    *(_DWORD *)(v19 + 39) = v18;
    *(_DWORD *)(v20 + 4 * *(_DWORD *)(v20 + 24) + 28) |= 8u;
    ++*(_DWORD *)(v20 + 64);
    Database::LockTable(*((_DWORD *)v6 + 9), v50, 2, a6, 1);
    if ( (*(_BYTE *)a6 & 8) != 0 )
      Table::ReportLockConflict(v6, v49, a6);
    else
      *((_DWORD *)v6 + 12) = 2;
  }
  Spacemap::~Spacemap((Spacemap *)v54);
  v21 = v41;
  if ( v41 )
  {
    if ( *(_DWORD *)v41 )
      --*(_WORD *)(*(_DWORD *)v41 + 76);
    operator delete(v21, 0xCu);
  }
  else if ( Block )
  {
    operator delete[](Block);
  }
  v55 = -1;
  if ( v20 )
    --*(_WORD *)(v20 + 76);
  if ( (*(_BYTE *)a6 & 8) != 0 )
    goto LABEL_49;
  if ( *(_DWORD *)(*((_DWORD *)v6 + 9) + 68) != 1 )
  {
    v53 = (struct Transaction *)*((_DWORD *)v52 + 5);
    v22 = v53;
    GetDateTime(v34);
    (*(void (__thiscall **)(struct Transaction *, _DWORD, struct Err *))(*(_DWORD *)v22 + 20))(v53, 0, a6);
    if ( (*(_BYTE *)a6 & 8) != 0
      || ((*(void (__thiscall **)(struct Transaction *, _DWORD, unsigned int *, int, _DWORD, struct Err *))(*(_DWORD *)v53 + 100))(
            v53,
            *((_DWORD *)v52 + 7),
            &v37,
            4,
            0,
            a6),
          (*(_BYTE *)a6 & 8) != 0)
      || ((*(void (__thiscall **)(struct Transaction *, _DWORD, unsigned int *, int, _DWORD, struct Err *))(*(_DWORD *)v53 + 100))(
            v53,
            *((_DWORD *)v52 + 8),
            &v50,
            4,
            0,
            a6),
          (*(_BYTE *)a6 & 8) != 0) )
    {
      v23 = v53;
    }
    else
    {
      v23 = v53;
      v24 = v49;
      v48 = *(Table **)(*(_DWORD *)v53 + 100);
      v45 = (unsigned int)(v49 + 1);
      while ( *v24++ )
        ;
      ((void (__thiscall *)(struct Transaction *, _DWORD, unsigned __int16 *, int, _DWORD, struct Err *))v48)(
        v53,
        *((_DWORD *)v52 + 9),
        v49,
        2 * ((int)((int)v24 - v45) >> 1),
        0,
        a6);
    }
    if ( (*(_BYTE *)a6 & 8) == 0 )
    {
      (*(void (__thiscall **)(struct Transaction *, _DWORD, unsigned int *, int, _DWORD, struct Err *))(*(_DWORD *)v23 + 100))(
        v53,
        *((_DWORD *)v52 + 10),
        &v47,
        2,
        0,
        a6);
      if ( (*(_BYTE *)a6 & 8) == 0 )
      {
        (*(void (__thiscall **)(struct Transaction *, _DWORD, unsigned int *, int, _DWORD, struct Err *))(*(_DWORD *)v53 + 100))(
          v53,
          *((_DWORD *)v52 + 11),
          v35,
          8,
          0,
          a6);
        if ( (*(_BYTE *)a6 & 8) == 0 )
        {
          (*(void (__thiscall **)(struct Transaction *, _DWORD, unsigned int *, int, _DWORD, struct Err *))(*(_DWORD *)v53 + 100))(
            v53,
            *((_DWORD *)v52 + 12),
            v35,
            8,
            0,
            a6);
          if ( (*(_BYTE *)a6 & 8) == 0 )
          {
            (*(void (__thiscall **)(struct Transaction *, _DWORD, unsigned int *, int, _DWORD, struct Err *))(*(_DWORD *)v53 + 100))(
              v53,
              *((_DWORD *)v52 + 14),
              &v36,
              4,
              0,
              a6);
            if ( (*(_BYTE *)a6 & 8) == 0 )
              (*(void (__thiscall **)(struct Transaction *, struct Err *))(*(_DWORD *)v53 + 28))(v53, a6);
          }
        }
      }
    }
    if ( (*(_DWORD *)a6 & 8) != 0 && (*(_DWORD *)a6 & 1) == 0 && *((_DWORD *)a6 + 1) == -1605 )
    {
      Err::Reset(a6);
      Err::SetError(a6, -1303, -8162, v49, 0, v26);
    }
  }
  if ( (*(_BYTE *)a6 & 8) != 0 )
  {
LABEL_49:
    v28 = v46;
    v27 = (char)v51;
  }
  else
  {
    v27 = (char)v51;
    v28 = v46;
    if ( (_BYTE)v51 )
    {
      Session::CommitTransaction(v46, (void **)a6, 0);
      v27 = (char)v51;
      if ( (*(_BYTE *)a6 & 8) != 0 )
      {
LABEL_51:
        v29 = 1;
        v38 = 1;
        v55 = 3;
        if ( v27 )
          Table::AbortTransaction(v6, v28, v7);
        v30 = *((_DWORD *)v6 + 12);
        if ( v30 != 9 )
        {
          Database::UnlockTable(*((_DWORD *)v6 + 9), v50, v30, &v38);
          v29 = v38;
          if ( (v38 & 8) == 0 )
            *((_DWORD *)v6 + 12) = 9;
        }
        if ( (v29 & 0xFFFFFFFE) != 0 )
        {
          if ( v41 )
            operator delete[](v41);
          if ( v42 )
            operator delete[](v42);
        }
        return;
      }
      *((_DWORD *)v6 + 17) = -1;
    }
  }
  if ( (*(_BYTE *)a6 & 8) != 0 )
    goto LABEL_51;
  *((_DWORD *)v6 + 15) = *((_DWORD *)v28 + 14);
  *((_DWORD *)v6 + 16) = *((_DWORD *)v28 + 14);
  Table::AddSession(v6, v28, a6);
  if ( (*(_BYTE *)a6 & 8) == 0 )
  {
    v31 = *((_DWORD *)v28 + 5);
    v32 = 0;
    if ( v31 )
    {
      while ( *(Table **)(*((_DWORD *)v28 + 3) + 4 * v32) != v6 )
      {
        if ( ++v32 >= v31 )
          goto LABEL_65;
      }
    }
    else
    {
LABEL_65:
      if ( v32 == v31 && (*((int *)v6 + 15) > 0 || *(_DWORD *)(*((_DWORD *)v6 + 9) + 68) == 1) )
        Table::AddNotify(v6, v28);
    }
    v33 = v50;
    *((_DWORD *)v6 + 11) = 2;
    *((_DWORD *)v6 + 10) = v33;
    *((_BYTE *)v6 + 8) = 78;
  }
}

```

## disassembly

```asm
0x10052e30  mov     edi, edi
0x10052e32  push    ebp
0x10052e33  mov     ebp, esp
0x10052e35  push    0FFFFFFFFh
0x10052e37  push    offset ?Create@Table@@QAEXPAVInstance@@PBGKKAAVErr@@@Z_SEH
0x10052e3c  mov     eax, large fs:0
0x10052e42  push    eax
0x10052e43  sub     esp, 0C0h
0x10052e49  mov     eax, ___security_cookie
0x10052e4e  xor     eax, ebp
0x10052e50  mov     [ebp+var_14], eax
0x10052e53  push    ebx
0x10052e54  push    esi
0x10052e55  push    edi
0x10052e56  push    eax; unsigned int
0x10052e57  lea     eax, [ebp+var_C]
0x10052e5a  mov     large fs:0, eax
0x10052e60  mov     edi, ecx
0x10052e62  mov     [ebp+var_8C], edi
0x10052e68  mov     eax, [ebp+arg_0]
0x10052e6b  mov     ecx, [ebp+arg_4]
0x10052e6e  mov     ebx, [ebp+arg_10]
0x10052e71  mov     [ebp+var_7C], eax
0x10052e74  mov     esi, [eax+0Ch]
0x10052e77  mov     eax, [eax+3Ch]
0x10052e7a  mov     [ebp+var_78], eax
0x10052e7d  mov     eax, 1
0x10052e82  mov     word ptr [ebp+var_90], ax
0x10052e89  mov     eax, [edi+24h]
0x10052e8c  mov     [ebp+var_84], 0
0x10052e96  mov     [ebp+var_BC], 0F000001h
0x10052ea0  mov     [ebp+var_C0], 0
0x10052eaa  cmp     dword ptr [eax+44h], 1
0x10052eae  mov     [ebp+var_88], ecx
0x10052eb4  mov     byte ptr [ebp+var_80], 0
0x10052eb8  mov     [ebp+var_94], esi
0x10052ebe  jz      short loc_10052EE5
0x10052ec0  push    ebx
0x10052ec1  push    1
0x10052ec3  mov     ecx, esi
0x10052ec5  call    ?BeginTransaction@Session@@QAEXW4TransactionType@@AAVErr@@@Z; Session::BeginTransaction(TransactionType,Err &)
0x10052eca  test    byte ptr [ebx], 8
0x10052ecd  jnz     short loc_10052ED5
0x10052ecf  mov     eax, [esi+38h]
0x10052ed2  mov     [edi+44h], eax
0x10052ed5  mov     ecx, [ebx]
0x10052ed7  shr     ecx, 3
0x10052eda  not     cl
0x10052edc  and     ecx, 0FFFFFF01h
0x10052ee2  mov     [ebp+var_80], ecx
0x10052ee5  test    byte ptr [ebx], 8
0x10052ee8  jnz     loc_100532DC
0x10052eee  mov     [ebp+var_A4], 0
0x10052ef8  mov     [ebp+var_A0], 0
0x10052f02  mov     [ebp+var_4], 0
0x10052f09  mov     [ebp+var_B4], 0
0x10052f13  mov     [ebp+Block], 0
0x10052f1d  mov     [ebp+var_AC], 0
0x10052f27  mov     [ebp+var_A8], 0
0x10052f31  lea     ecx, [ebp+var_74]; this
0x10052f34  call    ??0AbstractSpacemap@@QAE@XZ; AbstractSpacemap::AbstractSpacemap(void)
0x10052f39  mov     edi, [ebp+var_7C]
0x10052f3c  mov     byte ptr [ebp+var_4], 2
0x10052f40  push    ebx; unsigned int
0x10052f41  push    0; void *
0x10052f43  mov     edi, [edi+10h]
0x10052f46  mov     eax, [edi]
0x10052f48  mov     esi, [eax+4]
0x10052f4b  mov     ecx, esi
0x10052f4d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10052f53  mov     ecx, edi
0x10052f55  call    esi
0x10052f57  test    byte ptr [ebx], 8
0x10052f5a  mov     [ebp+var_98], eax
0x10052f60  mov     [ebp+var_84], eax
0x10052f66  jnz     short loc_10052FDD
0x10052f68  mov     edi, [ebp+var_78]
0x10052f6b  mov     esi, [edi+8]
0x10052f6e  lea     eax, [esi+70h]
0x10052f71  push    eax; lpCriticalSection
0x10052f72  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10052f78  push    ebx; struct Err *
0x10052f79  push    [ebp+var_98]; unsigned int
0x10052f7f  mov     ecx, esi; this
0x10052f81  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x10052f86  test    byte ptr [ebx], 8
0x10052f89  jnz     short loc_10052F9B
0x10052f8b  push    ebx; struct Err *
0x10052f8c  push    edi; struct Transaction *
0x10052f8d  lea     ecx, [ebp+var_A4]
0x10052f93  push    ecx; struct PageRef *
0x10052f94  mov     ecx, eax; this
0x10052f96  call    ?DontReadPage@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@AAVErr@@@Z; PageDesc::DontReadPage(PageRef &,Transaction *,Err &)
0x10052f9b  lea     eax, [esi+70h]
0x10052f9e  push    eax; lpCriticalSection
0x10052f9f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10052fa5  test    byte ptr [ebx], 8
0x10052fa8  jnz     short loc_10052FDD
0x10052faa  mov     edi, [ebp+var_8C]
0x10052fb0  lea     ecx, [ebp+var_B4]
0x10052fb6  mov     eax, [edi+24h]
0x10052fb9  mov     eax, [eax+3Ch]
0x10052fbc  push    dword ptr [eax+68h]
0x10052fbf  push    4Eh ; 'N'
0x10052fc1  push    [ebp+var_A0]
0x10052fc7  call    ?Initialize@TblPage@@QAEXPAUtagTHDPage@@EW4DBBool@@@Z; TblPage::Initialize(tagTHDPage *,uchar,DBBool)
0x10052fcc  mov     esi, [ebp+var_78]
0x10052fcf  lea     ecx, [ebp+var_74]; this
0x10052fd2  push    0; unsigned int
0x10052fd4  push    ebx; struct Err *
0x10052fd5  push    esi; struct Transaction *
0x10052fd6  call    ?Create@Spacemap@@QAEKPAVTransaction@@AAVErr@@K@Z; Spacemap::Create(Transaction *,Err &,ulong)
0x10052fdb  jmp     short loc_10052FE8
0x10052fdd  mov     edi, [ebp+var_8C]
0x10052fe3  xor     eax, eax
0x10052fe5  mov     esi, [ebp+var_78]
0x10052fe8  test    byte ptr [ebx], 8
0x10052feb  jnz     short loc_10053057
0x10052fed  mov     ecx, [ebp+var_A0]
0x10052ff3  push    eax; unsigned int
0x10052ff4  mov     [edi+1Ch], eax
0x10052ff7  push    ebx; struct Err *
0x10052ff8  mov     [ecx+23h], eax
0x10052ffb  lea     ecx, [ebp+var_74]; this
0x10052ffe  push    esi; struct Transaction *
0x10052fff  call    ?Create@Spacemap@@QAEKPAVTransaction@@AAVErr@@K@Z; Spacemap::Create(Transaction *,Err &,ulong)
0x10053004  test    byte ptr [ebx], 8
0x10053007  jnz     short loc_10053057
0x10053009  mov     ecx, [ebp+var_A0]
0x1005300f  mov     esi, [ebp+var_A4]
0x10053015  mov     [edi+20h], eax
0x10053018  push    1
0x1005301a  mov     [ecx+27h], eax
0x1005301d  mov     eax, [esi+18h]
0x10053020  push    ebx
0x10053021  push    2
0x10053023  or      dword ptr [esi+eax*4+1Ch], 8
0x10053028  inc     dword ptr [esi+40h]
0x1005302b  push    [ebp+var_84]
0x10053031  mov     ecx, [edi+24h]
0x10053034  call    ?LockTable@Database@@QAEXKW4TblLck@@AAVErr@@W4DBROLock@@@Z; Database::LockTable(ulong,TblLck,Err &,DBROLock)
0x10053039  test    byte ptr [ebx], 8
0x1005303c  jz      short loc_1005304E
0x1005303e  push    ebx; struct Err *
0x1005303f  push    [ebp+var_88]; unsigned __int16 *
0x10053045  mov     ecx, edi; this
0x10053047  call    ?ReportLockConflict@Table@@AAEXPBGAAVErr@@@Z; Table::ReportLockConflict(ushort const *,Err &)
0x1005304c  jmp     short loc_1005305D
0x1005304e  mov     dword ptr [edi+30h], 2
0x10053055  jmp     short loc_1005305D
0x10053057  mov     esi, [ebp+var_A4]
0x1005305d  lea     ecx, [ebp+var_74]; this
0x10053060  call    ??1Spacemap@@QAE@XZ; Spacemap::~Spacemap(void)
0x10053065  mov     eax, [ebp+var_AC]
0x1005306b  test    eax, eax
0x1005306d  jz      short loc_10053086
0x1005306f  mov     ecx, [eax]
0x10053071  test    ecx, ecx
0x10053073  jz      short loc_10053079
0x10053075  dec     word ptr [ecx+4Ch]
0x10053079  push    0Ch; unsigned int
0x1005307b  push    eax; Block
0x1005307c  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10053081  add     esp, 8
0x10053084  jmp     short loc_10053099
0x10053086  mov     eax, [ebp+Block]
0x1005308c  test    eax, eax
0x1005308e  jz      short loc_10053099
0x10053090  push    eax; Block
0x10053091  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10053096  add     esp, 4
0x10053099  mov     [ebp+var_4], 0FFFFFFFFh
0x100530a0  test    esi, esi
0x100530a2  jz      short loc_100530A8
0x100530a4  dec     word ptr [esi+4Ch]
0x100530a8  test    byte ptr [ebx], 8
0x100530ab  jnz     loc_100532DC
0x100530b1  mov     eax, [edi+24h]
0x100530b4  cmp     dword ptr [eax+44h], 1
0x100530b8  jz      loc_100532AF
0x100530be  mov     eax, [ebp+var_7C]
0x100530c1  lea     ecx, [ebp+var_CC]
0x100530c7  mov     esi, [eax+14h]
0x100530ca  mov     [ebp+var_78], esi
0x100530cd  call    ?GetDateTime@@YGXPAN@Z; GetDateTime(double *)
0x100530d2  mov     eax, [esi]
0x100530d4  push    ebx; unsigned int
0x100530d5  push    0; void *
0x100530d7  mov     esi, [eax+14h]
0x100530da  mov     ecx, esi
0x100530dc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100530e2  mov     ecx, [ebp+var_78]
0x100530e5  call    esi
0x100530e7  test    byte ptr [ebx], 8
0x100530ea  jnz     loc_100531A8
0x100530f0  mov     eax, [ebp+var_78]
0x100530f3  push    ebx
0x100530f4  push    0
0x100530f6  push    4
0x100530f8  mov     eax, [eax]
0x100530fa  mov     esi, [eax+64h]
0x100530fd  lea     eax, [ebp+var_BC]
0x10053103  push    eax; unsigned int
0x10053104  mov     eax, [ebp+var_7C]
0x10053107  mov     ecx, esi
0x10053109  push    dword ptr [eax+1Ch]; void *
0x1005310c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10053112  mov     ecx, [ebp+var_78]
0x10053115  call    esi
0x10053117  test    byte ptr [ebx], 8
0x1005311a  jnz     loc_100531A8
0x10053120  mov     eax, [ebp+var_78]
0x10053123  push    ebx
0x10053124  push    0
0x10053126  push    4
0x10053128  mov     eax, [eax]
0x1005312a  mov     esi, [eax+64h]
0x1005312d  lea     eax, [ebp+var_84]
0x10053133  push    eax; unsigned int
0x10053134  mov     eax, [ebp+var_7C]
0x10053137  mov     ecx, esi
0x10053139  push    dword ptr [eax+20h]; void *
0x1005313c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10053142  mov     ecx, [ebp+var_78]
0x10053145  call    esi
0x10053147  test    byte ptr [ebx], 8
0x1005314a  jnz     short loc_100531A8
0x1005314c  mov     esi, [ebp+var_78]
0x1005314f  mov     ecx, [ebp+var_88]
0x10053155  mov     eax, [esi]
0x10053157  mov     edx, [eax+64h]
0x1005315a  lea     eax, [ecx+2]
0x1005315d  mov     [ebp+var_8C], edx
0x10053163  mov     [ebp+var_98], eax
0x10053169  nop     dword ptr [eax+00000000h]
0x10053170  mov     ax, [ecx]
0x10053173  add     ecx, 2
0x10053176  test    ax, ax
0x10053179  jnz     short loc_10053170
0x1005317b  sub     ecx, [ebp+var_98]
0x10053181  sar     ecx, 1
0x10053183  push    ebx
0x10053184  push    0
0x10053186  lea     eax, [ecx+ecx]
0x10053189  mov     ecx, edx
0x1005318b  push    eax
0x1005318c  mov     eax, [ebp+var_7C]
0x1005318f  push    [ebp+var_88]; unsigned int
0x10053195  push    dword ptr [eax+24h]; void *
0x10053198  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005319e  mov     ecx, esi
0x100531a0  call    [ebp+var_8C]
0x100531a6  jmp     short loc_100531AB
0x100531a8  mov     esi, [ebp+var_78]
0x100531ab  test    byte ptr [ebx], 8
0x100531ae  jnz     loc_1005327B
0x100531b4  mov     eax, [esi]
0x100531b6  push    ebx
0x100531b7  push    0
0x100531b9  push    2
0x100531bb  mov     esi, [eax+64h]
0x100531be  lea     eax, [ebp+var_90]
0x100531c4  push    eax; unsigned int
0x100531c5  mov     eax, [ebp+var_7C]
0x100531c8  mov     ecx, esi
0x100531ca  push    dword ptr [eax+28h]; void *
0x100531cd  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100531d3  mov     ecx, [ebp+var_78]
0x100531d6  call    esi
0x100531d8  test    byte ptr [ebx], 8
0x100531db  jnz     loc_1005327B
0x100531e1  mov     eax, [ebp+var_78]
0x100531e4  push    ebx
0x100531e5  push    0
0x100531e7  push    8
0x100531e9  mov     eax, [eax]
0x100531eb  mov     esi, [eax+64h]
0x100531ee  lea     eax, [ebp+var_CC]
0x100531f4  push    eax; unsigned int
0x100531f5  mov     eax, [ebp+var_7C]
0x100531f8  mov     ecx, esi
0x100531fa  push    dword ptr [eax+2Ch]; void *
0x100531fd  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10053203  mov     ecx, [ebp+var_78]
0x10053206  call    esi
0x10053208  test    byte ptr [ebx], 8
0x1005320b  jnz     short loc_1005327B
0x1005320d  mov     eax, [ebp+var_78]
0x10053210  push    ebx
0x10053211  push    0
0x10053213  push    8
0x10053215  mov     eax, [eax]
0x10053217  mov     esi, [eax+64h]
0x1005321a  lea     eax, [ebp+var_CC]
0x10053220  push    eax; unsigned int
0x10053221  mov     eax, [ebp+var_7C]
0x10053224  mov     ecx, esi
0x10053226  push    dword ptr [eax+30h]; void *
0x10053229  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005322f  mov     ecx, [ebp+var_78]
  ... truncated ...
```
