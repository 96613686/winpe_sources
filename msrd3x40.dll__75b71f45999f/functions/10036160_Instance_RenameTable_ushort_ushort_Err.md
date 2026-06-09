# Instance::RenameTable(ushort *,ushort *,Err &)

- ea: `0x10036160`
- end: `0x100364d8`
- name: `?RenameTable@Instance@@QAEXPAG0AAVErr@@@Z`
- size: `888`
- prototype: `void __thiscall(Instance *__hidden this, unsigned __int16 *, unsigned __int16 *Src, struct Err *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10028b00`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10020ab0`
- `0x10025db0`
- `0x10025f50`
- `0x100260d0`
- `0x10036160`
- `0x10036dc0`
- `0x10037710`
- `0x10037bb0`
- `0x10051890`
- `0x10052140`
- `0x100536a0`
- `0x10057520`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`
- `0x1005f07c`

## pseudocode

```c
void __thiscall Instance::RenameTable(Instance *this, unsigned __int16 *a2, unsigned __int16 *Src, void **a4)
{
  int v5; // eax
  Err *v6; // ecx
  struct Session **v7; // esi
  struct Table *Table; // eax
  int v9; // edi
  Err *v10; // ecx
  unsigned __int16 *v11; // eax
  unsigned __int16 *v12; // esi
  size_t v14; // esi
  const unsigned __int16 *v15; // edi
  struct Instance *v16; // [esp-4h] [ebp-5Ch]
  unsigned __int16 *v17; // [esp+3Ch] [ebp-1Ch]
  unsigned int v18; // [esp+40h] [ebp-18h] BYREF
  struct Instance *v19; // [esp+44h] [ebp-14h]
  unsigned int v20; // [esp+48h] [ebp-10h] BYREF
  int v21; // [esp+54h] [ebp-4h]

  v19 = this;
  LOWORD(v20) = 0;
  v5 = *(_DWORD *)(*((_DWORD *)this + 4) + 104);
  if ( (!v5 || v5 == 3) && (int)*a4 < 8 )
  {
    if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
    {
      if ( a4[3] )
        operator delete[](a4[3]);
      if ( a4[4] )
        operator delete[](a4[4]);
    }
    *a4 = (void *)8;
    a4[1] = (void *)-1809;
    a4[2] = 0;
    a4[3] = 0;
    a4[4] = 0;
  }
  if ( (*(_BYTE *)a4 & 8) == 0 )
  {
    Instance::ReadSysObjRecord(this, 0xF000001u, a2, a4);
    if ( (*(_BYTE *)a4 & 8) == 0 )
    {
      (*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, void **))(**((_DWORD **)this + 5) + 108))(
        *((_DWORD *)this + 5),
        *((_DWORD *)v19 + 10),
        &v20,
        2,
        0,
        a4);
      if ( (*(_BYTE *)a4 & 8) == 0 )
      {
        if ( (_WORD)v20 == 1 )
        {
          v18 = 0;
          if ( !WCSICMP(a2, wszMSysAccounts) || !WCSICMP(a2, wszMSysGroups) )
            Err::SetError(a4, -1304, -8150, a2, 0, v6);
          if ( (*(_BYTE *)a4 & 8) != 0 )
            goto LABEL_26;
          if ( !WCSICMP(Src, wszMSysAccounts) || !WCSICMP(Src, wszMSysGroups) )
            Err::SetError(a4, -1002, -8198, Src, 0, v6);
          if ( (*(_BYTE *)a4 & 8) != 0
            || ((*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, void **))(**((_DWORD **)v19 + 5)
                                                                                             + 108))(
                  *((_DWORD *)v19 + 5),
                  *((_DWORD *)v19 + 8),
                  &v18,
                  4,
                  0,
                  a4),
                (*(_BYTE *)a4 & 8) != 0) )
          {
LABEL_26:
            v7 = (struct Session **)v19;
            v9 = 0;
          }
          else
          {
            v7 = (struct Session **)v19;
            Table = Database::FindTable(*((Database **)v19 + 4), v18);
            v9 = (int)Table;
            if ( Table )
              Table::CompatibleMode((int)Table, v7[3], 2u, (struct Err *)a4);
            else
              v9 = Instance::OpenTable(v7, a2, v18, 2, a4);
          }
          if ( (*(_BYTE *)a4 & 8) == 0 && v9 )
          {
            v10 = *(Err **)(v9 + 76);
            *(_DWORD *)(v9 + 76) = (char *)v10 + 1;
            ++*(_DWORD *)(v9 + 340);
            v21 = 0;
            if ( (*(_DWORD *)(v9 + 44) != 2 || v10) && (*(_DWORD *)(v9 + 48) != 2 || v10) )
            {
              v11 = Src;
              if ( !Src )
                v11 = *(unsigned __int16 **)v9;
              v17 = v11;
              if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
              {
                if ( a4[3] )
                  operator delete[](a4[3]);
                if ( a4[4] )
                  operator delete[](a4[4]);
              }
              *a4 = (void *)8;
              a4[1] = (void *)-1304;
              a4[2] = (void *)-8154;
              a4[3] = 0;
              LOBYTE(v21) = 0;
              Err::CopyString(v10, (wchar_t *)a4 + 8, v17);
            }
            if ( (*(_BYTE *)a4 & 8) == 0 )
            {
              v12 = Src;
              while ( *v12++ )
                ;
              v14 = 2 * (v12 - (Src + 1));
              memcpy(*(void **)v9, Src, v14);
              *(_WORD *)(v14 + *(_DWORD *)v9) = 0;
              *(_DWORD *)(v9 + 4) = v14;
              v7 = (struct Session **)v19;
              v16 = v19;
              *(_DWORD *)(v9 + 64) = *(_DWORD *)(*((_DWORD *)v19 + 3) + 56);
              Table::DDLPerformed((Table *)v9, v16);
            }
            v21 = -1;
            --*(_DWORD *)(v9 + 340);
            if ( (*(_BYTE *)a4 & 8) == 0 )
              Instance::RenameObject((Instance *)v7, L"Tables", a2, Src, (struct Err *)a4);
            Table::Release((Table *)v9, (struct Instance *)v7);
          }
          v15 = Src;
        }
        else
        {
          v15 = Src;
          Instance::RenameObject(v19, L"Tables", a2, Src, (struct Err *)a4);
        }
        if ( ((unsigned __int8)*a4 & 1) == 0 && a4[1] == (void *)-1605 )
        {
          if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
          {
            if ( a4[3] )
              operator delete[](a4[3]);
            if ( a4[4] )
              operator delete[](a4[4]);
          }
          *a4 = (void *)8;
          a4[1] = (void *)-1303;
          a4[2] = (void *)-8162;
          Err::CopyString(v6, (wchar_t *)a4 + 6, v15);
          a4[4] = 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x10036160  mov     edi, edi
0x10036162  push    ebp
0x10036163  mov     ebp, esp
0x10036165  push    0FFFFFFFFh
0x10036167  push    offset ?RenameTable@Instance@@QAEXPAG0AAVErr@@@Z_SEH
0x1003616c  mov     eax, large fs:0
0x10036172  push    eax
0x10036173  sub     esp, 3Ch
0x10036176  push    ebx
0x10036177  push    esi
0x10036178  push    edi
0x10036179  mov     eax, ___security_cookie
0x1003617e  xor     eax, ebp
0x10036180  push    eax
0x10036181  lea     eax, [ebp+var_C]
0x10036184  mov     large fs:0, eax
0x1003618a  mov     esi, ecx
0x1003618c  mov     [ebp+var_14], esi
0x1003618f  mov     ebx, [ebp+arg_8]
0x10036192  xor     eax, eax
0x10036194  mov     word ptr [ebp+var_10], ax
0x10036198  mov     eax, [esi+10h]
0x1003619b  mov     eax, [eax+68h]
0x1003619e  test    eax, eax
0x100361a0  jz      short loc_100361A7
0x100361a2  cmp     eax, 3
0x100361a5  jnz     short loc_100361F7
0x100361a7  mov     eax, [ebx]
0x100361a9  cmp     eax, 8
0x100361ac  jge     short loc_100361F7
0x100361ae  test    eax, 0FFFFFFFEh
0x100361b3  jz      short loc_100361D5
0x100361b5  mov     eax, [ebx+0Ch]
0x100361b8  test    eax, eax
0x100361ba  jz      short loc_100361C5
0x100361bc  push    eax; Block
0x100361bd  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100361c2  add     esp, 4
0x100361c5  mov     eax, [ebx+10h]
0x100361c8  test    eax, eax
0x100361ca  jz      short loc_100361D5
0x100361cc  push    eax; Block
0x100361cd  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100361d2  add     esp, 4
0x100361d5  mov     dword ptr [ebx], 8
0x100361db  mov     dword ptr [ebx+4], 0FFFFF8EFh
0x100361e2  mov     dword ptr [ebx+8], 0
0x100361e9  mov     dword ptr [ebx+0Ch], 0
0x100361f0  mov     dword ptr [ebx+10h], 0
0x100361f7  test    byte ptr [ebx], 8
0x100361fa  mov     edi, [ebp+arg_0]
0x100361fd  jnz     loc_100364AB
0x10036203  push    ebx; struct Err *
0x10036204  push    edi; unsigned __int16 *
0x10036205  push    0F000001h; unsigned int
0x1003620a  mov     ecx, esi; this
0x1003620c  call    ?ReadSysObjRecord@Instance@@QAEXKPBGAAVErr@@@Z; Instance::ReadSysObjRecord(ulong,ushort const *,Err &)
0x10036211  test    byte ptr [ebx], 8
0x10036214  jnz     loc_100364AB
0x1003621a  mov     edi, [esi+14h]
0x1003621d  push    ebx
0x1003621e  push    0
0x10036220  push    2
0x10036222  mov     eax, [edi]
0x10036224  mov     esi, [eax+6Ch]
0x10036227  lea     eax, [ebp+var_10]
0x1003622a  push    eax; unsigned int
0x1003622b  mov     eax, [ebp+var_14]
0x1003622e  mov     ecx, esi
0x10036230  push    dword ptr [eax+28h]; void *
0x10036233  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036239  mov     ecx, edi
0x1003623b  call    esi
0x1003623d  test    byte ptr [ebx], 8
0x10036240  mov     esi, [ebp+var_14]
0x10036243  mov     edi, [ebp+arg_0]
0x10036246  jnz     loc_100364AB
0x1003624c  cmp     word ptr [ebp+var_10], 1
0x10036251  jnz     loc_100364BF
0x10036257  mov     edx, offset _wszMSysAccounts; "MSysAccounts"
0x1003625c  mov     [ebp+var_18], 0
0x10036263  mov     ecx, edi
0x10036265  call    _WCSICMP@8; WCSICMP(x,x)
0x1003626a  test    eax, eax
0x1003626c  jz      short loc_1003627E
0x1003626e  mov     edx, offset _wszMSysGroups; "MSysGroups"
0x10036273  mov     ecx, edi
0x10036275  call    _WCSICMP@8; WCSICMP(x,x)
0x1003627a  test    eax, eax
0x1003627c  jnz     short loc_10036293
0x1003627e  push    ecx
0x1003627f  push    0
0x10036281  push    edi
0x10036282  push    0FFFFE02Ah
0x10036287  push    0FFFFFAE8h
0x1003628c  mov     ecx, ebx
0x1003628e  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x10036293  test    byte ptr [ebx], 8
0x10036296  jnz     loc_10036335
0x1003629c  mov     edi, [ebp+Src]
0x1003629f  mov     edx, offset _wszMSysAccounts; "MSysAccounts"
0x100362a4  mov     ecx, edi
0x100362a6  call    _WCSICMP@8; WCSICMP(x,x)
0x100362ab  test    eax, eax
0x100362ad  jz      short loc_100362BF
0x100362af  mov     edx, offset _wszMSysGroups; "MSysGroups"
0x100362b4  mov     ecx, edi
0x100362b6  call    _WCSICMP@8; WCSICMP(x,x)
0x100362bb  test    eax, eax
0x100362bd  jnz     short loc_100362D4
0x100362bf  push    ecx
0x100362c0  push    0
0x100362c2  push    edi
0x100362c3  push    0FFFFDFFAh
0x100362c8  push    0FFFFFC16h
0x100362cd  mov     ecx, ebx
0x100362cf  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x100362d4  test    byte ptr [ebx], 8
0x100362d7  jnz     short loc_10036335
0x100362d9  mov     edi, [esi+14h]
0x100362dc  push    ebx
0x100362dd  push    0
0x100362df  push    4
0x100362e1  mov     eax, [edi]
0x100362e3  mov     esi, [eax+6Ch]
0x100362e6  lea     eax, [ebp+var_18]
0x100362e9  push    eax; unsigned int
0x100362ea  mov     eax, [ebp+var_14]
0x100362ed  mov     ecx, esi
0x100362ef  push    dword ptr [eax+20h]; void *
0x100362f2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100362f8  mov     ecx, edi
0x100362fa  call    esi
0x100362fc  test    byte ptr [ebx], 8
0x100362ff  jnz     short loc_10036335
0x10036301  mov     esi, [ebp+var_14]
0x10036304  push    [ebp+var_18]; unsigned int
0x10036307  mov     ecx, [esi+10h]; this
0x1003630a  call    ?FindTable@Database@@QAEPAVTable@@K@Z; Database::FindTable(ulong)
0x1003630f  mov     edi, eax
0x10036311  push    ebx
0x10036312  push    2
0x10036314  test    edi, edi
0x10036316  jnz     short loc_10036329
0x10036318  push    [ebp+var_18]
0x1003631b  mov     ecx, esi
0x1003631d  push    [ebp+arg_0]
0x10036320  call    ?OpenTable@Instance@@AAEPAVTable@@PBGKW4TblMode@@AAVErr@@@Z; Instance::OpenTable(ushort const *,ulong,TblMode,Err &)
0x10036325  mov     edi, eax
0x10036327  jmp     short loc_1003633A
0x10036329  push    dword ptr [esi+0Ch]
0x1003632c  mov     ecx, edi
0x1003632e  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x10036333  jmp     short loc_1003633A
0x10036335  mov     esi, [ebp+var_14]
0x10036338  xor     edi, edi
0x1003633a  test    byte ptr [ebx], 8
0x1003633d  jnz     loc_1003644D
0x10036343  test    edi, edi
0x10036345  jz      loc_1003644D
0x1003634b  mov     ecx, [edi+4Ch]
0x1003634e  mov     [ebp+var_20], edi
0x10036351  lea     eax, [ecx+1]
0x10036354  mov     [edi+4Ch], eax
0x10036357  inc     dword ptr [edi+154h]
0x1003635d  mov     [ebp+var_4], 0
0x10036364  cmp     dword ptr [edi+2Ch], 2
0x10036368  jnz     short loc_1003636E
0x1003636a  test    ecx, ecx
0x1003636c  jz      short loc_100363D7
0x1003636e  cmp     dword ptr [edi+30h], 2
0x10036372  jnz     short loc_10036378
0x10036374  test    ecx, ecx
0x10036376  jz      short loc_100363D7
0x10036378  mov     eax, [ebp+Src]
0x1003637b  test    eax, eax
0x1003637d  jnz     short loc_10036381
0x1003637f  mov     eax, [edi]
0x10036381  test    dword ptr [ebx], 0FFFFFFFEh
0x10036387  mov     [ebp+var_1C], eax
0x1003638a  jz      short loc_100363AC
0x1003638c  mov     eax, [ebx+0Ch]
0x1003638f  test    eax, eax
0x10036391  jz      short loc_1003639C
0x10036393  push    eax; Block
0x10036394  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036399  add     esp, 4
0x1003639c  mov     eax, [ebx+10h]
0x1003639f  test    eax, eax
0x100363a1  jz      short loc_100363AC
0x100363a3  push    eax; Block
0x100363a4  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100363a9  add     esp, 4
0x100363ac  mov     dword ptr [ebx], 8
0x100363b2  mov     dword ptr [ebx+4], 0FFFFFAE8h
0x100363b9  mov     dword ptr [ebx+8], 0FFFFE026h
0x100363c0  push    [ebp+var_1C]; unsigned __int16 *
0x100363c3  lea     eax, [ebx+10h]
0x100363c6  mov     dword ptr [ebx+0Ch], 0
0x100363cd  push    eax; unsigned __int16 **
0x100363ce  mov     byte ptr [ebp+var_4], 0
0x100363d2  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x100363d7  test    byte ptr [ebx], 8
0x100363da  jnz     short loc_10036420
0x100363dc  mov     ecx, [ebp+Src]
0x100363df  mov     esi, ecx
0x100363e1  lea     edx, [esi+2]
0x100363e4  mov     ax, [esi]
0x100363e7  add     esi, 2
0x100363ea  test    ax, ax
0x100363ed  jnz     short loc_100363E4
0x100363ef  sub     esi, edx
0x100363f1  sar     esi, 1
0x100363f3  add     esi, esi
0x100363f5  push    esi; Size
0x100363f6  push    ecx; Src
0x100363f7  push    dword ptr [edi]; void *
0x100363f9  call    _memcpy
0x100363fe  mov     eax, [edi]
0x10036400  xor     ecx, ecx
0x10036402  add     esp, 0Ch
0x10036405  mov     [esi+eax], cx
0x10036409  mov     ecx, edi; this
0x1003640b  mov     [edi+4], esi
0x1003640e  mov     esi, [ebp+var_14]
0x10036411  push    esi; struct Instance *
0x10036412  mov     eax, [esi+0Ch]
0x10036415  mov     eax, [eax+38h]
0x10036418  mov     [edi+40h], eax
0x1003641b  call    ?DDLPerformed@Table@@AAEXPAVInstance@@@Z; Table::DDLPerformed(Instance *)
0x10036420  mov     [ebp+var_4], 0FFFFFFFFh
0x10036427  dec     dword ptr [edi+154h]
0x1003642d  test    byte ptr [ebx], 8
0x10036430  jnz     short loc_10036445
0x10036432  push    ebx; struct Err *
0x10036433  push    [ebp+Src]; unsigned __int16 *
0x10036436  mov     ecx, esi; this
0x10036438  push    [ebp+arg_0]; unsigned __int16 *
0x1003643b  push    offset aTables; "Tables"
0x10036440  call    ?RenameObject@Instance@@QAEXPBGPAG1AAVErr@@@Z; Instance::RenameObject(ushort const *,ushort *,ushort *,Err &)
0x10036445  push    esi; struct Instance *
0x10036446  mov     ecx, edi; this
0x10036448  call    ?Release@Table@@QAEJPAVInstance@@@Z; Table::Release(Instance *)
0x1003644d  mov     edi, [ebp+Src]
0x10036450  mov     eax, [ebx]
0x10036452  test    al, 1
0x10036454  jnz     short loc_100364AB
0x10036456  cmp     dword ptr [ebx+4], 0FFFFF9BBh
0x1003645d  jnz     short loc_100364AB
0x1003645f  test    eax, 0FFFFFFFEh
0x10036464  jz      short loc_10036486
0x10036466  mov     eax, [ebx+0Ch]
0x10036469  test    eax, eax
0x1003646b  jz      short loc_10036476
0x1003646d  push    eax; Block
0x1003646e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036473  add     esp, 4
0x10036476  mov     eax, [ebx+10h]
0x10036479  test    eax, eax
0x1003647b  jz      short loc_10036486
0x1003647d  push    eax; Block
0x1003647e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036483  add     esp, 4
0x10036486  push    edi; unsigned __int16 *
0x10036487  lea     eax, [ebx+0Ch]
0x1003648a  mov     dword ptr [ebx], 8
0x10036490  push    eax; unsigned __int16 **
0x10036491  mov     dword ptr [ebx+4], 0FFFFFAE9h
0x10036498  mov     dword ptr [ebx+8], 0FFFFE01Eh
0x1003649f  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x100364a4  mov     dword ptr [ebx+10h], 0
0x100364ab  mov     ecx, [ebp+var_C]
0x100364ae  mov     large fs:0, ecx
0x100364b5  pop     ecx
0x100364b6  pop     edi
0x100364b7  pop     esi
0x100364b8  pop     ebx
0x100364b9  mov     esp, ebp
0x100364bb  pop     ebp
0x100364bc  retn    0Ch
0x100364bf  mov     edi, [ebp+Src]
0x100364c2  mov     ecx, esi; this
0x100364c4  push    ebx; struct Err *
0x100364c5  push    edi; unsigned __int16 *
0x100364c6  push    [ebp+arg_0]; unsigned __int16 *
0x100364c9  push    offset aTables; "Tables"
0x100364ce  call    ?RenameObject@Instance@@QAEXPBGPAG1AAVErr@@@Z; Instance::RenameObject(ushort const *,ushort *,ushort *,Err &)
0x100364d3  jmp     loc_10036450
0x10060bc0  lea     ecx, [ebp+var_20]; this
0x10060bc3  jmp     ??1TblSemaphore@@QAE@XZ; TblSemaphore::~TblSemaphore(void)
0x10060bc8  lea     ecx, [ebp+var_34]; this
0x10060bcb  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060bd0  lea     ecx, [ebp+var_48]; this
0x10060bd3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060bdd  nop
0x10060bde  nop
0x10060bdf  mov     edx, [esp-4+Src]
0x10060be3  lea     eax, [edx+0Ch]
0x10060be6  mov     ecx, [edx-4Ch]
0x10060be9  xor     ecx, eax; StackCookie
  ... truncated ...
```
