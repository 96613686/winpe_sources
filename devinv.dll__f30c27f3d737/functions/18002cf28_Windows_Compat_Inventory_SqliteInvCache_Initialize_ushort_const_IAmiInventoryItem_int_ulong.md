# Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)

- ea: `0x18002cf28`
- end: `0x18002d2c9`
- name: `?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z`
- size: `929`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *Src, struct IAmiInventoryItem *, int, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18002d2d0`

## callees

- `0x180005e40`
- `0x180006eb8`
- `0x18000fa50`
- `0x1800103e0`
- `0x180010a10`
- `0x180025af8`
- `0x180028694`
- `0x180028824`
- `0x1800294c8`
- `0x18002cf28`
- `0x18002e1f8`
- `0x180031560`
- `0x1800316a0`
- `0x1800317a0`
- `0x180066c10`
- `0x1800b01bc`
- `0x1800e9be0`
- `0x180116010`

## string_xrefs

- `0x18002cf6c`: `TemplateItem cannot be null [%#x]`
- `0x18002cfaf`: `TemplateItem must have a property schema defined [%#x]`
- `0x18002cfd6`: `OpenDb failed [%#x]`
- `0x18002d200`: `CreateReadItemQuery failed [%#x]`
- `0x18002d221`: `CreateWriteItemQuery failed [%#x]`
- `0x18002d118`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x18002d22c`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x18002d250`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x18002d291`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x18002d1e3`: `CreateTable failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::Initialize(
        struct sqlite3 **this,
        const unsigned __int16 *Src,
        struct IAmiInventoryItem *a3,
        int a4)
{
  int Table; // eax
  unsigned int v9; // esi
  __int64 v10; // r8
  const char *v11; // r9
  __int64 *v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rbx
  struct sqlite3 **v15; // rax
  void **v16; // r15
  unsigned __int64 v17; // r14
  struct sqlite3 *v18; // rbx
  size_t v19; // r14
  unsigned __int64 v20; // r12
  struct sqlite3 *v21; // rdx
  void *v22; // rcx
  __int64 v23; // r8
  unsigned __int64 v24; // rdx
  struct sqlite3 *v25; // r14
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  struct sqlite3 *v30; // rbx
  int v31; // ebx
  const char *v32; // rax
  struct sqlite3 *Srca; // [rsp+30h] [rbp-98h]
  _BYTE v35[32]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v36[32]; // [rsp+58h] [rbp-70h] BYREF

  if ( a3 )
  {
    v12 = (__int64 *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _BYTE *))(*(_QWORD *)a3 + 64LL))(a3, v35);
    v13 = *v12;
    v14 = v12[1];
    std::vector<_GUID>::~vector<_GUID>(v35);
    if ( v13 == v14 )
    {
      Table = -2147024809;
      v9 = -2147024809;
      v10 = 558;
      v11 = "TemplateItem must have a property schema defined [%#x]";
    }
    else
    {
      Table = Windows::Compat::Inventory::SqliteInvCache::OpenDb(Src, this + 1, a4);
      v9 = Table;
      if ( Table >= 0 )
      {
        *((_BYTE *)this + 168) = a4 != 0;
        v15 = (struct sqlite3 **)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _BYTE *))(*(_QWORD *)a3 + 64LL))(
                                   a3,
                                   v35);
        v16 = (void **)(this + 17);
        if ( this + 17 != v15 )
        {
          Srca = *v15;
          v17 = (v15[1] - *v15) >> 4;
          v18 = (struct sqlite3 *)*v16;
          if ( v17 <= (this[19] - this[17]) >> 4 )
          {
            v20 = (this[18] - v18) >> 4;
            v21 = *v15;
            v22 = *v16;
            if ( v17 > v20 )
            {
              memmove_0(v22, v21, 16 * v20);
              v18 = this[18];
              v17 -= v20;
              v21 = (struct sqlite3 *)((char *)Srca + 16 * v20);
              v22 = v18;
            }
            v19 = 16 * v17;
            memmove_0(v22, v21, v19);
          }
          else
          {
            std::vector<IAmiInventoryItem::_CacheItemProperty>::_Clear_and_reserve_geometric(this + 17, v17);
            v18 = (struct sqlite3 *)*v16;
            v19 = 16 * v17;
            memmove_0(*v16, Srca, v19);
          }
          this[18] = (struct sqlite3 *)((char *)v18 + v19);
        }
        std::vector<_GUID>::~vector<_GUID>(v35);
        v24 = -1;
        do
          ++v24;
        while ( Src[v24] );
        if ( v24 > (unsigned __int64)this[12] )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            this + 9,
            v24,
            v23,
            Src);
        }
        else
        {
          if ( (unsigned __int64)this[12] <= 7 )
            v25 = (struct sqlite3 *)(this + 9);
          else
            v25 = this[9];
          this[11] = (struct sqlite3 *)v24;
          v26 = 2 * v24;
          memmove_0(v25, Src, 2 * v24);
          *(_WORD *)((char *)v25 + v26) = 0;
        }
        if ( !this[11] )
        {
          AslLogCallPrintf(
            1,
            "Windows::Compat::Inventory::SqliteInvCache::Initialize",
            575,
            "Table name conversion failed");
          return v9;
        }
        v27 = std::to_wstring(v36, 2);
        std::operator+<unsigned short>(v35, v28, v27);
        std::wstring::append(this + 9);
        std::wstring::~wstring(v35);
        std::wstring::~wstring(v36);
        if ( (unsigned __int64)this[16] < 9 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            this + 13,
            9,
            v29,
            L"Metadata_");
        }
        else
        {
          v30 = this[13];
          this[15] = (struct sqlite3 *)9;
          memmove_0(v30, L"Metadata_", 0x12u);
          *((_WORD *)v30 + 9) = 0;
        }
        std::to_wstring(v36, 2);
        std::wstring::append(this + 13);
        std::wstring::~wstring(v36);
        Table = Windows::Compat::Inventory::SqliteInvCache::CreateTable((Windows::Compat::Inventory::SqliteInvCache *)this);
        v9 = Table;
        if ( Table >= 0 )
        {
          Table = Windows::Compat::Inventory::SqliteInvCache::CreateReadItemQuery((Windows::Compat::Inventory::SqliteInvCache *)this);
          v9 = Table;
          if ( Table >= 0 )
          {
            Table = Windows::Compat::Inventory::SqliteInvCache::CreateWriteItemQuery((Windows::Compat::Inventory::SqliteInvCache *)this);
            v9 = Table;
            if ( Table >= 0 )
              return v9;
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
    }
  }
  else
  {
    Table = -2147024809;
    v9 = -2147024809;
    v10 = 551;
    v11 = "TemplateItem cannot be null [%#x]";
  }
  AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::Initialize", v10, v11, Table);
  if ( this[1] )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::SqliteInvCache::Initialize",
      607,
      "closing database due to failure");
    v31 = sqlite3Close(this[1], 0);
    if ( v31 )
    {
      v32 = (const char *)sqlite3_errmsg(this[1]);
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::Initialize",
        611,
        "sqlite3_close failed: [%d] %hs",
        v31,
        v32);
    }
    this[1] = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18002cf28  push    rbx
0x18002cf2a  push    rbp
0x18002cf2b  push    rsi
0x18002cf2c  push    rdi
0x18002cf2d  push    r12
0x18002cf2f  push    r13
0x18002cf31  push    r14
0x18002cf33  push    r15
0x18002cf35  sub     rsp, 88h
0x18002cf3c  mov     rax, cs:__security_cookie
0x18002cf43  xor     rax, rsp
0x18002cf46  mov     [rsp+0C8h+var_50], rax
0x18002cf4b  mov     r15d, r9d
0x18002cf4e  mov     r14, r8
0x18002cf51  mov     r13, rdx
0x18002cf54  mov     rbp, rcx
0x18002cf57  xor     r12d, r12d
0x18002cf5a  test    r8, r8
0x18002cf5d  jnz     short loc_18002CF78
0x18002cf5f  mov     eax, 80070057h
0x18002cf64  mov     esi, eax
0x18002cf66  mov     r8d, 227h
0x18002cf6c  lea     r9, aTemplateitemCa; "TemplateItem cannot be null [%#x]"
0x18002cf73  jmp     loc_18002D228
0x18002cf78  mov     rax, [r8]
0x18002cf7b  lea     rdx, [rsp+0C8h+var_90]
0x18002cf80  mov     rcx, r14
0x18002cf83  mov     rax, [rax+40h]
0x18002cf87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf8c  mov     rdi, [rax]
0x18002cf8f  mov     rbx, [rax+8]
0x18002cf93  lea     rcx, [rsp+0C8h+var_90]
0x18002cf98  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x18002cf9d  cmp     rdi, rbx
0x18002cfa0  jnz     short loc_18002CFBB
0x18002cfa2  mov     eax, 80070057h
0x18002cfa7  mov     esi, eax
0x18002cfa9  mov     r8d, 22Eh
0x18002cfaf  lea     r9, aTemplateitemMu; "TemplateItem must have a property schem"...
0x18002cfb6  jmp     loc_18002D228
0x18002cfbb  lea     rdx, [rbp+8]; struct sqlite3 **
0x18002cfbf  mov     r8d, r15d; int
0x18002cfc2  mov     rcx, r13; unsigned __int16 *
0x18002cfc5  call    ?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z; Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)
0x18002cfca  mov     esi, eax
0x18002cfcc  test    eax, eax
0x18002cfce  jns     short loc_18002CFE2
0x18002cfd0  mov     r8d, 235h
0x18002cfd6  lea     r9, aOpendbFailedX; "OpenDb failed [%#x]"
0x18002cfdd  jmp     loc_18002D228
0x18002cfe2  test    r15d, r15d
0x18002cfe5  setnz   al
0x18002cfe8  mov     [rbp+0A8h], al
0x18002cfee  mov     rax, [r14]
0x18002cff1  lea     rdx, [rsp+0C8h+var_90]
0x18002cff6  mov     rcx, r14
0x18002cff9  mov     rax, [rax+40h]
0x18002cffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d002  nop
0x18002d003  lea     r15, [rbp+88h]
0x18002d00a  cmp     r15, rax
0x18002d00d  jz      loc_18002D0AB
0x18002d013  mov     rcx, [rax]
0x18002d016  mov     [rsp+0C8h+Src], rcx
0x18002d01b  mov     r14, [rax+8]
0x18002d01f  sub     r14, rcx
0x18002d022  sar     r14, 4
0x18002d026  mov     rbx, [r15]
0x18002d029  mov     rax, [r15+10h]
0x18002d02d  sub     rax, rbx
0x18002d030  sar     rax, 4
0x18002d034  cmp     r14, rax
0x18002d037  jbe     short loc_18002D05D
0x18002d039  mov     rdx, r14
0x18002d03c  mov     rcx, r15
0x18002d03f  call    ?_Clear_and_reserve_geometric@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAX_K@Z; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Clear_and_reserve_geometric(unsigned __int64)
0x18002d044  mov     rbx, [r15]
0x18002d047  shl     r14, 4
0x18002d04b  mov     r8, r14; Size
0x18002d04e  mov     rdx, [rsp+0C8h+Src]; Src
0x18002d053  mov     rcx, rbx; void *
0x18002d056  call    memmove_0
0x18002d05b  jmp     short loc_18002D0A3
0x18002d05d  mov     r12, [r15+8]
0x18002d061  sub     r12, rbx
0x18002d064  sar     r12, 4
0x18002d068  mov     rdx, rcx; Src
0x18002d06b  mov     rcx, rbx; void *
0x18002d06e  cmp     r14, r12
0x18002d071  jbe     short loc_18002D094
0x18002d073  mov     rdi, r12
0x18002d076  shl     rdi, 4
0x18002d07a  mov     r8, rdi; Size
0x18002d07d  call    memmove_0
0x18002d082  mov     rbx, [r15+8]
0x18002d086  sub     r14, r12
0x18002d089  mov     rdx, [rsp+0C8h+Src]
0x18002d08e  add     rdx, rdi; Src
0x18002d091  mov     rcx, rbx; void *
0x18002d094  shl     r14, 4
0x18002d098  mov     r8, r14; Size
0x18002d09b  call    memmove_0
0x18002d0a0  xor     r12d, r12d
0x18002d0a3  lea     rax, [r14+rbx]
0x18002d0a7  mov     [r15+8], rax
0x18002d0ab  lea     rcx, [rsp+0C8h+var_90]
0x18002d0b0  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x18002d0b5  lea     rdi, [rbp+48h]
0x18002d0b9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002d0bd  inc     rdx
0x18002d0c0  cmp     [r13+rdx*2+0], r12w
0x18002d0c6  jnz     short loc_18002D0BD
0x18002d0c8  cmp     rdx, [rdi+18h]
0x18002d0cc  ja      short loc_18002D0FA
0x18002d0ce  cmp     qword ptr [rdi+18h], 7
0x18002d0d3  jbe     short loc_18002D0DA
0x18002d0d5  mov     r14, [rdi]
0x18002d0d8  jmp     short loc_18002D0DD
0x18002d0da  mov     r14, rdi
0x18002d0dd  mov     [rdi+10h], rdx
0x18002d0e1  lea     rbx, [rdx+rdx]
0x18002d0e5  mov     r8, rbx; Size
0x18002d0e8  mov     rdx, r13; Src
0x18002d0eb  mov     rcx, r14; void *
0x18002d0ee  call    memmove_0
0x18002d0f3  mov     [rbx+r14], r12w
0x18002d0f8  jmp     short loc_18002D105
0x18002d0fa  mov     r9, r13
0x18002d0fd  mov     rcx, rdi
0x18002d100  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002d105  cmp     [rbp+58h], r12
0x18002d109  jnz     short loc_18002D12E
0x18002d10b  lea     r9, aTableNameConve; "Table name conversion failed"
0x18002d112  mov     r8d, 23Fh
0x18002d118  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002d11f  mov     ecx, 1
0x18002d124  call    AslLogCallPrintf
0x18002d129  jmp     loc_18002D2A6
0x18002d12e  mov     esi, 2
0x18002d133  mov     edx, esi
0x18002d135  lea     rcx, [rsp+0C8h+var_70]
0x18002d13a  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18002d13f  nop
0x18002d140  mov     r8, rax
0x18002d143  lea     rcx, [rsp+0C8h+var_90]
0x18002d148  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18002d14d  nop
0x18002d14e  mov     rdx, rax
0x18002d151  mov     rcx, rdi; Src
0x18002d154  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002d159  nop
0x18002d15a  lea     rcx, [rsp+0C8h+var_90]; void *
0x18002d15f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d164  nop
0x18002d165  lea     rcx, [rsp+0C8h+var_70]; void *
0x18002d16a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d16f  lea     rdi, [rbp+68h]
0x18002d173  lea     edx, [rsi+7]
0x18002d176  cmp     [rdi+18h], rdx
0x18002d17a  jb      short loc_18002D19D
0x18002d17c  mov     rbx, [rdi]
0x18002d17f  mov     [rdi+10h], rdx
0x18002d183  lea     r8d, [rsi+10h]; Size
0x18002d187  lea     rdx, aMetadata; "Metadata_"
0x18002d18e  mov     rcx, rbx; void *
0x18002d191  call    memmove_0
0x18002d196  mov     [rbx+12h], r12w
0x18002d19b  jmp     short loc_18002D1AC
0x18002d19d  lea     r9, aMetadata; "Metadata_"
0x18002d1a4  mov     rcx, rdi
0x18002d1a7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002d1ac  mov     edx, esi
0x18002d1ae  lea     rcx, [rsp+0C8h+var_70]
0x18002d1b3  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18002d1b8  nop
0x18002d1b9  mov     rdx, rax
0x18002d1bc  mov     rcx, rdi; Src
0x18002d1bf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002d1c4  nop
0x18002d1c5  lea     rcx, [rsp+0C8h+var_70]; void *
0x18002d1ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d1cf  mov     rcx, rbp; this
0x18002d1d2  call    ?CreateTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateTable(void)
0x18002d1d7  mov     esi, eax
0x18002d1d9  test    eax, eax
0x18002d1db  jns     short loc_18002D1EC
0x18002d1dd  mov     r8d, 24Ah
0x18002d1e3  lea     r9, aCreatetableFai; "CreateTable failed [%#x]"
0x18002d1ea  jmp     short loc_18002D228
0x18002d1ec  mov     rcx, rbp; this
0x18002d1ef  call    ?CreateReadItemQuery@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateReadItemQuery(void)
0x18002d1f4  mov     esi, eax
0x18002d1f6  test    eax, eax
0x18002d1f8  jns     short loc_18002D209
0x18002d1fa  mov     r8d, 251h
0x18002d200  lea     r9, aCreatereaditem; "CreateReadItemQuery failed [%#x]"
0x18002d207  jmp     short loc_18002D228
0x18002d209  mov     rcx, rbp; this
0x18002d20c  call    ?CreateWriteItemQuery@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateWriteItemQuery(void)
0x18002d211  mov     esi, eax
0x18002d213  test    eax, eax
0x18002d215  jns     loc_18002D2A6
0x18002d21b  mov     r8d, 258h
0x18002d221  lea     r9, aCreatewriteite; "CreateWriteItemQuery failed [%#x]"
0x18002d228  mov     [rsp+0C8h+var_A8], eax
0x18002d22c  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002d233  mov     ecx, 1
0x18002d238  call    AslLogCallPrintf
0x18002d23d  cmp     [rbp+8], r12
0x18002d241  jz      short loc_18002D2A6
0x18002d243  lea     r9, aClosingDatabas; "closing database due to failure"
0x18002d24a  mov     r8d, 25Fh
0x18002d250  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002d257  mov     ecx, 3
0x18002d25c  call    AslLogCallPrintf
0x18002d261  xor     edx, edx
0x18002d263  mov     rcx, [rbp+8]
0x18002d267  call    sqlite3Close
0x18002d26c  mov     ebx, eax
0x18002d26e  test    eax, eax
0x18002d270  jz      short loc_18002D2A2
0x18002d272  mov     rcx, [rbp+8]
0x18002d276  call    sqlite3_errmsg
0x18002d27b  mov     [rsp+0C8h+var_A0], rax
0x18002d280  mov     [rsp+0C8h+var_A8], ebx
0x18002d284  lea     r9, aSqlite3CloseFa; "sqlite3_close failed: [%d] %hs"
0x18002d28b  mov     r8d, 263h
0x18002d291  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002d298  mov     ecx, 1
0x18002d29d  call    AslLogCallPrintf
0x18002d2a2  mov     [rbp+8], r12
0x18002d2a6  mov     eax, esi
0x18002d2a8  mov     rcx, [rsp+0C8h+var_50]
0x18002d2ad  xor     rcx, rsp; StackCookie
0x18002d2b0  call    __security_check_cookie
0x18002d2b5  add     rsp, 88h
0x18002d2bc  pop     r15
0x18002d2be  pop     r14
0x18002d2c0  pop     r13
0x18002d2c2  pop     r12
0x18002d2c4  pop     rdi
0x18002d2c5  pop     rsi
0x18002d2c6  pop     rbp
0x18002d2c7  pop     rbx
0x18002d2c8  retn
```
