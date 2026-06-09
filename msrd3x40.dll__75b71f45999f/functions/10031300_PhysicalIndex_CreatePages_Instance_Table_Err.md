# PhysicalIndex::CreatePages(Instance *,Table *,Err &)

- ea: `0x10031300`
- end: `0x10031578`
- name: `?CreatePages@PhysicalIndex@@QAEXPAVInstance@@PAVTable@@AAVErr@@@Z`
- size: `632`
- prototype: `void __thiscall(PhysicalIndex *__hidden this, struct Instance *, struct Table *, struct Err *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x10055260`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10010580`
- `0x10024b00`
- `0x10031300`
- `0x10031d70`
- `0x10042d20`
- `0x10047d30`
- `0x10047e10`
- `0x10047eb0`
- `0x10048100`
- `0x100481d0`
- `0x10049b80`
- `0x1005d1d0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100313bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100313bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100313ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100313ea`

## pseudocode

```c
void __thiscall PhysicalIndex::CreatePages(
        PhysicalIndex *this,
        struct Transaction **a2,
        struct Table *a3,
        struct Err *a4)
{
  int v5; // esi
  struct Transaction *v6; // edi
  int v7; // esi
  PageDesc *v8; // eax
  int v9; // ecx
  int v10; // ecx
  int v11; // [esp+14h] [ebp-A0h]
  _DWORD v12[3]; // [esp+18h] [ebp-9Ch] BYREF
  void *Block; // [esp+24h] [ebp-90h]
  void *v14; // [esp+28h] [ebp-8Ch]
  _DWORD v15[3]; // [esp+2Ch] [ebp-88h] BYREF
  struct Transaction *v16; // [esp+38h] [ebp-7Ch]
  struct Transaction **v17; // [esp+3Ch] [ebp-78h]
  _BYTE v18[28]; // [esp+40h] [ebp-74h] BYREF
  int v19; // [esp+5Ch] [ebp-58h]
  int v20; // [esp+6Ch] [ebp-48h]
  int v21; // [esp+B0h] [ebp-4h]

  v16 = this;
  v5 = 0;
  v17 = a2;
  v15[0] = 0;
  v15[1] = 0;
  v21 = 0;
  AbstractSpacemap::AbstractSpacemap((AbstractSpacemap *)v18);
  LOBYTE(v21) = 1;
  *((_DWORD *)this + 14) = Spacemap::Create((Spacemap *)v18, a2[15], a4, *((_DWORD *)a3 + 7));
  if ( (*(_BYTE *)a4 & 8) == 0 )
  {
    v6 = v16;
    v11 = (*(int (__thiscall **)(struct Transaction *, _DWORD, struct Err *))(*(_DWORD *)v17[4] + 4))(v17[4], 0, a4);
    *((_DWORD *)v16 + 6) = v11;
    if ( (*(_BYTE *)a4 & 8) != 0 )
      goto LABEL_14;
    v16 = v17[15];
    v7 = *((_DWORD *)v16 + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 112));
    v8 = Database::FindOrCreate((Database *)v7, v11, (void **)a4);
    if ( (*(_BYTE *)a4 & 8) == 0 )
      PageDesc::DontReadPage(v8, (struct PageRef *)v15, v16, a4);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 112));
    if ( (*(_BYTE *)a4 & 8) != 0
      || (AbstractSpacemap::AddPage(*((_DWORD *)v6 + 6), a4, v9), (*(_BYTE *)a4 & 8) != 0)
      || (IndexPage::Initialize((IndexPage *)v15, 0x104u, *((_DWORD *)a3 + 10), 0, 0, a4),
          v10 = v15[0],
          *(_DWORD *)(v15[0] + 4 * *(_DWORD *)(v15[0] + 24) + 28) |= 8u,
          ++*(_DWORD *)(v10 + 64),
          (*(_BYTE *)a4 & 8) != 0) )
    {
      v12[0] = 1;
      LOBYTE(v21) = 2;
      Transaction::FreePage(v17[15], *((_DWORD *)v6 + 6), 1, v12);
      if ( (v12[0] & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v14 )
          operator delete[](v14);
      }
      if ( (*(_BYTE *)a4 & 8) != 0 )
      {
LABEL_14:
        v12[0] = 1;
        LOBYTE(v21) = 3;
        AbstractSpacemap::Delete((AbstractSpacemap *)v18, (struct Err *)v12);
        if ( (v12[0] & 0xFFFFFFFE) != 0 )
        {
          if ( Block )
            operator delete[](Block);
          if ( v14 )
            operator delete[](v14);
        }
      }
    }
    v5 = v15[0];
  }
  LOBYTE(v21) = 4;
  v12[0] = 1;
  AbstractSpacemap::Close((AbstractSpacemap *)v18, (struct Err *)v12);
  if ( (v12[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v14 )
      operator delete[](v14);
  }
  if ( v20 )
    --*(_WORD *)(v20 + 76);
  if ( v19 )
    --*(_WORD *)(v19 + 76);
  if ( v5 )
    --*(_WORD *)(v5 + 76);
}

```

## disassembly

```asm
0x10031300  mov     edi, edi
0x10031302  push    ebp
0x10031303  mov     ebp, esp
0x10031305  push    0FFFFFFFFh
0x10031307  push    offset ?CreatePages@PhysicalIndex@@QAEXPAVInstance@@PAVTable@@AAVErr@@@Z_SEH
0x1003130c  mov     eax, large fs:0
0x10031312  push    eax
0x10031313  sub     esp, 98h
0x10031319  mov     eax, ___security_cookie
0x1003131e  xor     eax, ebp
0x10031320  mov     [ebp+var_14], eax
0x10031323  push    ebx
0x10031324  push    esi
0x10031325  push    edi
0x10031326  push    eax
0x10031327  lea     eax, [ebp+var_C]
0x1003132a  mov     large fs:0, eax
0x10031330  mov     edi, ecx
0x10031332  mov     [ebp+var_7C], edi
0x10031335  mov     eax, [ebp+arg_0]
0x10031338  xor     esi, esi
0x1003133a  mov     ebx, [ebp+arg_8]
0x1003133d  mov     [ebp+var_78], eax
0x10031340  mov     [ebp+var_88], esi
0x10031346  mov     [ebp+var_84], esi
0x1003134c  lea     ecx, [ebp+var_74]; this
0x1003134f  mov     [ebp+var_4], esi
0x10031352  call    ??0AbstractSpacemap@@QAE@XZ; AbstractSpacemap::AbstractSpacemap(void)
0x10031357  mov     eax, [ebp+arg_4]
0x1003135a  lea     ecx, [ebp+var_74]; this
0x1003135d  mov     byte ptr [ebp+var_4], 1
0x10031361  push    dword ptr [eax+1Ch]; unsigned int
0x10031364  mov     eax, [ebp+var_78]
0x10031367  push    ebx; struct Err *
0x10031368  push    dword ptr [eax+3Ch]; struct Transaction *
0x1003136b  call    ?Create@Spacemap@@QAEKPAVTransaction@@AAVErr@@K@Z; Spacemap::Create(Transaction *,Err &,ulong)
0x10031370  mov     [edi+38h], eax
0x10031373  test    byte ptr [ebx], 8
0x10031376  jnz     loc_100314ED
0x1003137c  mov     eax, [ebp+var_78]
0x1003137f  push    ebx; unsigned int
0x10031380  push    0; void *
0x10031382  mov     edi, [eax+10h]
0x10031385  mov     eax, [edi]
0x10031387  mov     esi, [eax+4]
0x1003138a  mov     ecx, esi
0x1003138c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10031392  mov     ecx, edi
0x10031394  call    esi
0x10031396  mov     edi, [ebp+var_7C]
0x10031399  mov     [ebp+var_A0], eax
0x1003139f  mov     [edi+18h], eax
0x100313a2  test    byte ptr [ebx], 8
0x100313a5  jnz     loc_10031498
0x100313ab  mov     eax, [ebp+var_78]
0x100313ae  mov     eax, [eax+3Ch]
0x100313b1  mov     [ebp+var_7C], eax
0x100313b4  mov     esi, [eax+8]
0x100313b7  lea     eax, [esi+70h]
0x100313ba  push    eax; lpCriticalSection
0x100313bb  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100313c1  push    ebx; struct Err *
0x100313c2  push    [ebp+var_A0]; unsigned int
0x100313c8  mov     ecx, esi; this
0x100313ca  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x100313cf  test    byte ptr [ebx], 8
0x100313d2  jnz     short loc_100313E6
0x100313d4  push    ebx; struct Err *
0x100313d5  push    [ebp+var_7C]; struct Transaction *
0x100313d8  lea     ecx, [ebp+var_88]
0x100313de  push    ecx; struct PageRef *
0x100313df  mov     ecx, eax; this
0x100313e1  call    ?DontReadPage@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@AAVErr@@@Z; PageDesc::DontReadPage(PageRef &,Transaction *,Err &)
0x100313e6  lea     eax, [esi+70h]
0x100313e9  push    eax; lpCriticalSection
0x100313ea  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100313f0  test    byte ptr [ebx], 8
0x100313f3  jnz     short loc_1003143C
0x100313f5  push    ecx
0x100313f6  push    ebx
0x100313f7  push    dword ptr [edi+18h]
0x100313fa  lea     ecx, [ebp+var_74]
0x100313fd  call    ?AddPage@AbstractSpacemap@@QAEXKAAVErr@@W4SMAssertAction@@@Z; AbstractSpacemap::AddPage(ulong,Err &,SMAssertAction)
0x10031402  test    byte ptr [ebx], 8
0x10031405  jnz     short loc_1003143C
0x10031407  mov     eax, [ebp+arg_4]
0x1003140a  lea     ecx, [ebp+var_88]; this
0x10031410  push    ebx; struct Err *
0x10031411  push    0; unsigned int
0x10031413  push    0; unsigned int
0x10031415  push    dword ptr [eax+28h]; unsigned int
0x10031418  push    104h; unsigned __int16
0x1003141d  call    ?Initialize@IndexPage@@QAEXGKKKAAVErr@@@Z; IndexPage::Initialize(ushort,ulong,ulong,ulong,Err &)
0x10031422  mov     ecx, [ebp+var_88]
0x10031428  mov     eax, [ecx+18h]
0x1003142b  or      dword ptr [ecx+eax*4+1Ch], 8
0x10031430  inc     dword ptr [ecx+40h]
0x10031433  test    byte ptr [ebx], 8
0x10031436  jz      loc_100314E7
0x1003143c  mov     [ebp+var_9C], 1
0x10031446  lea     eax, [ebp+var_9C]
0x1003144c  mov     byte ptr [ebp+var_4], 2
0x10031450  push    eax
0x10031451  mov     eax, [ebp+var_78]
0x10031454  push    1
0x10031456  push    dword ptr [edi+18h]
0x10031459  mov     ecx, [eax+3Ch]
0x1003145c  call    ?FreePage@Transaction@@QAEXKW4FreeDisposition@@AAVErr@@@Z; Transaction::FreePage(ulong,FreeDisposition,Err &)
0x10031461  test    [ebp+var_9C], 0FFFFFFFEh
0x1003146b  jz      short loc_10031493
0x1003146d  mov     eax, [ebp+Block]
0x10031473  test    eax, eax
0x10031475  jz      short loc_10031480
0x10031477  push    eax; Block
0x10031478  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003147d  add     esp, 4
0x10031480  mov     eax, [ebp+var_8C]
0x10031486  test    eax, eax
0x10031488  jz      short loc_10031493
0x1003148a  push    eax; Block
0x1003148b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10031490  add     esp, 4
0x10031493  test    byte ptr [ebx], 8
0x10031496  jz      short loc_100314E7
0x10031498  mov     [ebp+var_9C], 1
0x100314a2  lea     eax, [ebp+var_9C]
0x100314a8  mov     byte ptr [ebp+var_4], 3
0x100314ac  push    eax; struct Err *
0x100314ad  lea     ecx, [ebp+var_74]; this
0x100314b0  call    ?Delete@AbstractSpacemap@@QAEXAAVErr@@@Z; AbstractSpacemap::Delete(Err &)
0x100314b5  test    [ebp+var_9C], 0FFFFFFFEh
0x100314bf  jz      short loc_100314E7
0x100314c1  mov     eax, [ebp+Block]
0x100314c7  test    eax, eax
0x100314c9  jz      short loc_100314D4
0x100314cb  push    eax; Block
0x100314cc  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100314d1  add     esp, 4
0x100314d4  mov     eax, [ebp+var_8C]
0x100314da  test    eax, eax
0x100314dc  jz      short loc_100314E7
0x100314de  push    eax; Block
0x100314df  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100314e4  add     esp, 4
0x100314e7  mov     esi, [ebp+var_88]
0x100314ed  lea     eax, [ebp+var_9C]
0x100314f3  mov     byte ptr [ebp+var_4], 4
0x100314f7  push    eax; struct Err *
0x100314f8  lea     ecx, [ebp+var_74]; this
0x100314fb  mov     [ebp+var_9C], 1
0x10031505  call    ?Close@AbstractSpacemap@@QAEXAAVErr@@@Z; AbstractSpacemap::Close(Err &)
0x1003150a  test    [ebp+var_9C], 0FFFFFFFEh
0x10031514  jz      short loc_1003153C
0x10031516  mov     eax, [ebp+Block]
0x1003151c  test    eax, eax
0x1003151e  jz      short loc_10031529
0x10031520  push    eax; Block
0x10031521  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10031526  add     esp, 4
0x10031529  mov     eax, [ebp+var_8C]
0x1003152f  test    eax, eax
0x10031531  jz      short loc_1003153C
0x10031533  push    eax; Block
0x10031534  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10031539  add     esp, 4
0x1003153c  mov     eax, [ebp+var_48]
0x1003153f  test    eax, eax
0x10031541  jz      short loc_10031547
0x10031543  dec     word ptr [eax+4Ch]
0x10031547  mov     eax, [ebp+var_58]
0x1003154a  test    eax, eax
0x1003154c  jz      short loc_10031552
0x1003154e  dec     word ptr [eax+4Ch]
0x10031552  test    esi, esi
0x10031554  jz      short loc_1003155A
0x10031556  dec     word ptr [esi+4Ch]
0x1003155a  mov     ecx, [ebp+var_C]
0x1003155d  mov     large fs:0, ecx
0x10031564  pop     ecx
0x10031565  pop     edi
0x10031566  pop     esi
0x10031567  pop     ebx
0x10031568  mov     ecx, [ebp+var_14]
0x1003156b  xor     ecx, ebp; StackCookie
0x1003156d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10031572  mov     esp, ebp
0x10031574  pop     ebp
0x10031575  retn    0Ch
0x1005f070  jmp     ds:__imp____std_terminate
0x10060910  lea     ecx, [ebp+var_88]; this
0x10060916  jmp     ??1DataPage@@QAE@XZ; DataPage::~DataPage(void)
0x1006091b  lea     ecx, [ebp+var_74]; this
0x1006091e  jmp     ??1Spacemap@@QAE@XZ; Spacemap::~Spacemap(void)
0x10060923  lea     ecx, [ebp+var_9C]; this
0x10060929  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x1006092e  lea     ecx, [ebp+var_9C]; this
0x10060934  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x1006093e  nop
0x1006093f  nop
0x10060940  mov     edx, [esp-4+arg_4]
0x10060944  lea     eax, [edx+0Ch]
0x10060947  mov     ecx, [edx-0A8h]
0x1006094d  xor     ecx, eax; StackCookie
0x1006094f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060954  mov     ecx, [edx-8]
0x10060957  xor     ecx, eax; StackCookie
0x10060959  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006095e  mov     eax, offset stru_100636E0
0x10060963  jmp     ___CxxFrameHandler3
```
