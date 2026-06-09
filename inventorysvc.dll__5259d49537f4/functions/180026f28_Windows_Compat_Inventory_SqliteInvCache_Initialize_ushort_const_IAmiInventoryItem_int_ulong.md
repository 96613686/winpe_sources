# Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)

- ea: `0x180026f28`
- end: `0x1800272d3`
- name: `?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z`
- size: `939`
- prototype: `__int64 __fastcall(struct sqlite3 **this, const unsigned __int16 *Src, struct IAmiInventoryItem *, int, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800272dc`

## callees

- `0x180002bf0`
- `0x180005483`
- `0x1800074f0`
- `0x1800152d0`
- `0x18001f558`
- `0x18001f714`
- `0x1800208f0`
- `0x180021ea4`
- `0x180021fc0`
- `0x180022bd4`
- `0x180026f28`
- `0x180028c48`
- `0x18002dee8`
- `0x18002e028`
- `0x18002e128`
- `0x180067f5c`
- `0x1800a1980`
- `0x1800d1010`

## string_xrefs

- `0x180026f72`: `TemplateItem cannot be null [%#x]`
- `0x180026fb8`: `TemplateItem must have a property schema defined [%#x]`
- `0x180026fdc`: `OpenDb failed [%#x]`
- `0x180027207`: `CreateReadItemQuery failed [%#x]`
- `0x180027228`: `CreateWriteItemQuery failed [%#x]`
- `0x180027120`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x180027233`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x180027257`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x180027298`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x1800271ea`: `CreateTable failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::Initialize(
        struct sqlite3 **this,
        const unsigned __int16 *Src,
        struct IAmiInventoryItem *a3,
        int a4,
        unsigned int a5)
{
  unsigned int v9; // r12d
  __int64 v10; // r8
  const char *v11; // r9
  int Table; // eax
  unsigned int v13; // esi
  __int64 *v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rbx
  struct sqlite3 **v17; // rax
  void **v18; // r15
  unsigned __int64 v19; // r14
  struct sqlite3 *v20; // rbx
  size_t v21; // r14
  unsigned __int64 v22; // r12
  struct sqlite3 *v23; // rdx
  void *v24; // rcx
  __int64 v25; // r8
  unsigned __int64 v26; // rdx
  struct sqlite3 *v27; // r14
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  struct sqlite3 *v32; // rbx
  int v33; // ebx
  const char *v34; // rax
  struct sqlite3 *Srca; // [rsp+38h] [rbp-A0h]
  _BYTE v37[32]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v38[32]; // [rsp+60h] [rbp-78h] BYREF

  v9 = a5;
  if ( !a3 )
  {
    v10 = 551;
    v11 = "TemplateItem cannot be null [%#x]";
LABEL_3:
    Table = -2147024809;
    v13 = -2147024809;
    goto LABEL_34;
  }
  v14 = (__int64 *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _BYTE *))(*(_QWORD *)a3 + 64LL))(a3, v37);
  v15 = *v14;
  v16 = v14[1];
  std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v37);
  if ( v15 == v16 )
  {
    v10 = 558;
    v11 = "TemplateItem must have a property schema defined [%#x]";
    goto LABEL_3;
  }
  Table = Windows::Compat::Inventory::SqliteInvCache::OpenDb(Src, this + 1, a4);
  v13 = Table;
  if ( Table >= 0 )
  {
    *((_BYTE *)this + 168) = a4 != 0;
    v17 = (struct sqlite3 **)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _BYTE *))(*(_QWORD *)a3 + 64LL))(
                               a3,
                               v37);
    v18 = (void **)(this + 17);
    if ( this + 17 != v17 )
    {
      Srca = *v17;
      v19 = (v17[1] - *v17) >> 4;
      v20 = (struct sqlite3 *)*v18;
      if ( v19 <= (this[19] - this[17]) >> 4 )
      {
        v22 = (this[18] - v20) >> 4;
        v23 = *v17;
        v24 = *v18;
        if ( v19 > v22 )
        {
          memmove_0(v24, v23, 16 * v22);
          v20 = this[18];
          v19 -= v22;
          v23 = (struct sqlite3 *)((char *)Srca + 16 * v22);
          v24 = v20;
        }
        v21 = 16 * v19;
        memmove_0(v24, v23, v21);
        v9 = a5;
      }
      else
      {
        std::vector<IAmiInventoryItem::_CacheItemProperty>::_Clear_and_reserve_geometric(this + 17, v19);
        v20 = (struct sqlite3 *)*v18;
        v21 = 16 * v19;
        memmove_0(*v18, Srca, v21);
      }
      this[18] = (struct sqlite3 *)((char *)v20 + v21);
    }
    std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v37);
    v26 = -1;
    do
      ++v26;
    while ( Src[v26] );
    if ( v26 > (unsigned __int64)this[12] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        this + 9,
        v26,
        v25,
        Src);
    }
    else
    {
      if ( (unsigned __int64)this[12] <= 7 )
        v27 = (struct sqlite3 *)(this + 9);
      else
        v27 = this[9];
      this[11] = (struct sqlite3 *)v26;
      v28 = 2 * v26;
      memmove_0(v27, Src, 2 * v26);
      *(_WORD *)((char *)v27 + v28) = 0;
    }
    if ( !this[11] )
    {
      AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::Initialize", 575, "Table name conversion failed");
      return v13;
    }
    v29 = std::to_wstring(v38, v9);
    std::operator+<unsigned short>(v37, v30, v29);
    std::wstring::append(this + 9);
    std::wstring::~wstring(v37);
    std::wstring::~wstring(v38);
    if ( (unsigned __int64)this[16] < 9 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        this + 13,
        9,
        v31,
        L"Metadata_");
    }
    else
    {
      v32 = this[13];
      this[15] = (struct sqlite3 *)9;
      memmove_0(v32, L"Metadata_", 0x12u);
      *((_WORD *)v32 + 9) = 0;
    }
    std::to_wstring(v38, v9);
    std::wstring::append(this + 13);
    std::wstring::~wstring(v38);
    Table = Windows::Compat::Inventory::SqliteInvCache::CreateTable((Windows::Compat::Inventory::SqliteInvCache *)this);
    v13 = Table;
    if ( Table >= 0 )
    {
      Table = Windows::Compat::Inventory::SqliteInvCache::CreateReadItemQuery((Windows::Compat::Inventory::SqliteInvCache *)this);
      v13 = Table;
      if ( Table >= 0 )
      {
        Table = Windows::Compat::Inventory::SqliteInvCache::CreateWriteItemQuery((Windows::Compat::Inventory::SqliteInvCache *)this);
        v13 = Table;
        if ( Table >= 0 )
          return v13;
        v10 = 600;
        v11 = "CreateWriteItemQuery failed [%#x]";
      }
      else
      {
        v10 = 593;
        v11 = "CreateReadItemQuery failed [%#x]";
      }
    }
    else
    {
      v10 = 586;
      v11 = "CreateTable failed [%#x]";
    }
  }
  else
  {
    v10 = 565;
    v11 = "OpenDb failed [%#x]";
  }
LABEL_34:
  AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::Initialize", v10, v11, Table);
  if ( this[1] )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::SqliteInvCache::Initialize",
      607,
      "closing database due to failure");
    v33 = sqlite3Close(this[1], 0);
    if ( v33 )
    {
      v34 = (const char *)sqlite3_errmsg(this[1]);
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::Initialize",
        611,
        "sqlite3_close failed: [%d] %hs",
        v33,
        v34);
    }
    this[1] = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x180026f28  push    rbx
0x180026f2a  push    rbp
0x180026f2b  push    rsi
0x180026f2c  push    rdi
0x180026f2d  push    r12
0x180026f2f  push    r13
0x180026f31  push    r14
0x180026f33  push    r15
0x180026f35  sub     rsp, 98h
0x180026f3c  mov     rax, cs:__security_cookie
0x180026f43  xor     rax, rsp
0x180026f46  mov     [rsp+0D8h+var_58], rax
0x180026f4e  mov     r15d, r9d
0x180026f51  mov     r14, r8
0x180026f54  mov     r13, rdx
0x180026f57  mov     rbp, rcx
0x180026f5a  mov     r12d, [rsp+0D8h+arg_20]
0x180026f62  mov     [rsp+0D8h+var_A8], r12d
0x180026f67  test    r8, r8
0x180026f6a  jnz     short loc_180026F88
0x180026f6c  mov     r8d, 227h
0x180026f72  lea     r9, aTemplateitemCa; "TemplateItem cannot be null [%#x]"
0x180026f79  mov     eax, 80070057h
0x180026f7e  mov     esi, eax
0x180026f80  xor     r15d, r15d
0x180026f83  jmp     loc_18002722F
0x180026f88  mov     rax, [r8]
0x180026f8b  lea     rdx, [rsp+0D8h+var_98]
0x180026f90  mov     rcx, r14
0x180026f93  mov     rax, [rax+40h]
0x180026f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f9c  mov     rdi, [rax]
0x180026f9f  mov     rbx, [rax+8]
0x180026fa3  lea     rcx, [rsp+0D8h+var_98]
0x180026fa8  call    ??1?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@QEAA@XZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(void)
0x180026fad  cmp     rdi, rbx
0x180026fb0  jnz     short loc_180026FC1
0x180026fb2  mov     r8d, 22Eh
0x180026fb8  lea     r9, aTemplateitemMu; "TemplateItem must have a property schem"...
0x180026fbf  jmp     short loc_180026F79
0x180026fc1  lea     rdx, [rbp+8]; struct sqlite3 **
0x180026fc5  mov     r8d, r15d; int
0x180026fc8  mov     rcx, r13; unsigned __int16 *
0x180026fcb  call    ?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z; Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)
0x180026fd0  mov     esi, eax
0x180026fd2  test    eax, eax
0x180026fd4  jns     short loc_180026FE5
0x180026fd6  mov     r8d, 235h
0x180026fdc  lea     r9, aOpendbFailedX; "OpenDb failed [%#x]"
0x180026fe3  jmp     short loc_180026F80
0x180026fe5  test    r15d, r15d
0x180026fe8  setnz   al
0x180026feb  mov     [rbp+0A8h], al
0x180026ff1  mov     rax, [r14]
0x180026ff4  lea     rdx, [rsp+0D8h+var_98]
0x180026ff9  mov     rcx, r14
0x180026ffc  mov     rax, [rax+40h]
0x180027000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027005  nop
0x180027006  lea     r15, [rbp+88h]
0x18002700d  cmp     r15, rax
0x180027010  jz      loc_1800270B0
0x180027016  mov     rcx, [rax]
0x180027019  mov     [rsp+0D8h+Src], rcx
0x18002701e  mov     r14, [rax+8]
0x180027022  sub     r14, rcx
0x180027025  sar     r14, 4
0x180027029  mov     rbx, [r15]
0x18002702c  mov     rax, [r15+10h]
0x180027030  sub     rax, rbx
0x180027033  sar     rax, 4
0x180027037  cmp     r14, rax
0x18002703a  jbe     short loc_180027060
0x18002703c  mov     rdx, r14
0x18002703f  mov     rcx, r15
0x180027042  call    ?_Clear_and_reserve_geometric@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAX_K@Z; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Clear_and_reserve_geometric(unsigned __int64)
0x180027047  mov     rbx, [r15]
0x18002704a  shl     r14, 4
0x18002704e  mov     r8, r14; Size
0x180027051  mov     rdx, [rsp+0D8h+Src]; Src
0x180027056  mov     rcx, rbx; void *
0x180027059  call    memmove_0
0x18002705e  jmp     short loc_1800270A8
0x180027060  mov     r12, [r15+8]
0x180027064  sub     r12, rbx
0x180027067  sar     r12, 4
0x18002706b  mov     rdx, rcx; Src
0x18002706e  mov     rcx, rbx; void *
0x180027071  cmp     r14, r12
0x180027074  jbe     short loc_180027097
0x180027076  mov     rdi, r12
0x180027079  shl     rdi, 4
0x18002707d  mov     r8, rdi; Size
0x180027080  call    memmove_0
0x180027085  mov     rbx, [r15+8]
0x180027089  sub     r14, r12
0x18002708c  mov     rdx, [rsp+0D8h+Src]
0x180027091  add     rdx, rdi; Src
0x180027094  mov     rcx, rbx; void *
0x180027097  shl     r14, 4
0x18002709b  mov     r8, r14; Size
0x18002709e  call    memmove_0
0x1800270a3  mov     r12d, [rsp+0D8h+var_A8]
0x1800270a8  lea     rax, [r14+rbx]
0x1800270ac  mov     [r15+8], rax
0x1800270b0  lea     rcx, [rsp+0D8h+var_98]
0x1800270b5  call    ??1?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@QEAA@XZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(void)
0x1800270ba  lea     rdi, [rbp+48h]
0x1800270be  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800270c2  xor     r15d, r15d
0x1800270c5  inc     rdx
0x1800270c8  cmp     [r13+rdx*2+0], r15w
0x1800270ce  jnz     short loc_1800270C5
0x1800270d0  cmp     rdx, [rdi+18h]
0x1800270d4  ja      short loc_180027102
0x1800270d6  cmp     qword ptr [rdi+18h], 7
0x1800270db  jbe     short loc_1800270E2
0x1800270dd  mov     r14, [rdi]
0x1800270e0  jmp     short loc_1800270E5
0x1800270e2  mov     r14, rdi
0x1800270e5  mov     [rdi+10h], rdx
0x1800270e9  lea     rbx, [rdx+rdx]
0x1800270ed  mov     r8, rbx; Size
0x1800270f0  mov     rdx, r13; Src
0x1800270f3  mov     rcx, r14; void *
0x1800270f6  call    memmove_0
0x1800270fb  mov     [rbx+r14], r15w
0x180027100  jmp     short loc_18002710D
0x180027102  mov     r9, r13
0x180027105  mov     rcx, rdi
0x180027108  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002710d  cmp     [rbp+58h], r15
0x180027111  jnz     short loc_180027136
0x180027113  lea     r9, aTableNameConve; "Table name conversion failed"
0x18002711a  mov     r8d, 23Fh
0x180027120  lea     rdx, aWindowsCompatI_28; "Windows::Compat::Inventory::SqliteInvCa"...
0x180027127  mov     ecx, 1
0x18002712c  call    AslLogCallPrintf
0x180027131  jmp     loc_1800272AD
0x180027136  mov     edx, r12d
0x180027139  lea     rcx, [rsp+0D8h+var_78]
0x18002713e  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x180027143  nop
0x180027144  mov     r8, rax
0x180027147  lea     rcx, [rsp+0D8h+var_98]
0x18002714c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180027151  nop
0x180027152  mov     rdx, rax
0x180027155  mov     rcx, rdi; Src
0x180027158  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002715d  nop
0x18002715e  lea     rcx, [rsp+0D8h+var_98]; void *
0x180027163  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027168  nop
0x180027169  lea     rcx, [rsp+0D8h+var_78]; void *
0x18002716e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027173  lea     rdi, [rbp+68h]
0x180027177  mov     edx, 9
0x18002717c  cmp     [rdi+18h], rdx
0x180027180  jb      short loc_1800271A3
0x180027182  mov     rbx, [rdi]
0x180027185  mov     [rdi+10h], rdx
0x180027189  lea     r8d, [rdx+9]; Size
0x18002718d  lea     rdx, aMetadata; "Metadata_"
0x180027194  mov     rcx, rbx; void *
0x180027197  call    memmove_0
0x18002719c  mov     [rbx+12h], r15w
0x1800271a1  jmp     short loc_1800271B2
0x1800271a3  lea     r9, aMetadata; "Metadata_"
0x1800271aa  mov     rcx, rdi
0x1800271ad  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800271b2  mov     edx, r12d
0x1800271b5  lea     rcx, [rsp+0D8h+var_78]
0x1800271ba  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x1800271bf  nop
0x1800271c0  mov     rdx, rax
0x1800271c3  mov     rcx, rdi; Src
0x1800271c6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800271cb  nop
0x1800271cc  lea     rcx, [rsp+0D8h+var_78]; void *
0x1800271d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800271d6  mov     rcx, rbp; this
0x1800271d9  call    ?CreateTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateTable(void)
0x1800271de  mov     esi, eax
0x1800271e0  test    eax, eax
0x1800271e2  jns     short loc_1800271F3
0x1800271e4  mov     r8d, 24Ah
0x1800271ea  lea     r9, aCreatetableFai; "CreateTable failed [%#x]"
0x1800271f1  jmp     short loc_18002722F
0x1800271f3  mov     rcx, rbp; this
0x1800271f6  call    ?CreateReadItemQuery@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateReadItemQuery(void)
0x1800271fb  mov     esi, eax
0x1800271fd  test    eax, eax
0x1800271ff  jns     short loc_180027210
0x180027201  mov     r8d, 251h
0x180027207  lea     r9, aCreatereaditem; "CreateReadItemQuery failed [%#x]"
0x18002720e  jmp     short loc_18002722F
0x180027210  mov     rcx, rbp; this
0x180027213  call    ?CreateWriteItemQuery@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateWriteItemQuery(void)
0x180027218  mov     esi, eax
0x18002721a  test    eax, eax
0x18002721c  jns     loc_1800272AD
0x180027222  mov     r8d, 258h
0x180027228  lea     r9, aCreatewriteite; "CreateWriteItemQuery failed [%#x]"
0x18002722f  mov     [rsp+0D8h+var_B8], eax
0x180027233  lea     rdx, aWindowsCompatI_28; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002723a  mov     ecx, 1
0x18002723f  call    AslLogCallPrintf
0x180027244  cmp     [rbp+8], r15
0x180027248  jz      short loc_1800272AD
0x18002724a  lea     r9, aClosingDatabas; "closing database due to failure"
0x180027251  mov     r8d, 25Fh
0x180027257  lea     rdx, aWindowsCompatI_28; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002725e  mov     ecx, 3
0x180027263  call    AslLogCallPrintf
0x180027268  xor     edx, edx
0x18002726a  mov     rcx, [rbp+8]
0x18002726e  call    sqlite3Close
0x180027273  mov     ebx, eax
0x180027275  test    eax, eax
0x180027277  jz      short loc_1800272A9
0x180027279  mov     rcx, [rbp+8]
0x18002727d  call    sqlite3_errmsg
0x180027282  mov     [rsp+0D8h+var_B0], rax
0x180027287  mov     [rsp+0D8h+var_B8], ebx
0x18002728b  lea     r9, aSqlite3CloseFa; "sqlite3_close failed: [%d] %hs"
0x180027292  mov     r8d, 263h
0x180027298  lea     rdx, aWindowsCompatI_28; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002729f  mov     ecx, 1
0x1800272a4  call    AslLogCallPrintf
0x1800272a9  mov     [rbp+8], r15
0x1800272ad  mov     eax, esi
0x1800272af  mov     rcx, [rsp+0D8h+var_58]
0x1800272b7  xor     rcx, rsp; StackCookie
0x1800272ba  call    __security_check_cookie
0x1800272bf  add     rsp, 98h
0x1800272c6  pop     r15
0x1800272c8  pop     r14
0x1800272ca  pop     r13
0x1800272cc  pop     r12
0x1800272ce  pop     rdi
0x1800272cf  pop     rsi
0x1800272d0  pop     rbp
0x1800272d1  pop     rbx
0x1800272d2  retn
```
