# Cursor::Update(QuickKey &,Err &)

- ea: `0x1001b010`
- end: `0x1001b175`
- name: `?Update@Cursor@@UAEXAAVQuickKey@@AAVErr@@@Z`
- size: `357`
- prototype: `void __thiscall(Cursor *__hidden this, struct QuickKey *, struct Err *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callees

- `0x1000eb60`
- `0x10010600`
- `0x100106b0`
- `0x10011f50`
- `0x1001b010`
- `0x1001c8c0`
- `0x10038630`
- `0x10038650`
- `0x100399c0`
- `0x10052cc0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Cursor::Update(Cursor *this, struct QuickKey *a2, struct Err *a3)
{
  unsigned int inserted; // esi
  unsigned __int8 *v5; // eax
  Table *v6; // edi
  struct Instance *v7; // eax
  int v8; // edx
  int v9; // eax
  int v10; // eax
  _BYTE v12[208]; // [esp+18h] [ebp-110h] BYREF
  int v13; // [esp+E8h] [ebp-40h] BYREF
  void *Block; // [esp+ECh] [ebp-3Ch]
  int v15; // [esp+F0h] [ebp-38h]
  unsigned int v16; // [esp+F4h] [ebp-34h]
  char v17; // [esp+F8h] [ebp-30h] BYREF
  int v18; // [esp+124h] [ebp-4h]

  Block = &v17;
  v13 = 0;
  v15 = 0;
  v16 = 32;
  v18 = 0;
  Key::Assign((Key *)&v13, a2, a3);
  if ( (*(_BYTE *)a3 & 8) == 0 )
  {
    inserted = Cursor::InsertRecord((int)this, 2, 0, a3);
    if ( (*(_BYTE *)a3 & 8) == 0 )
    {
      v5 = v13 + 4 > v16 ? Key::NextByteAlloc((Key *)&v13, 4u, a3) : (unsigned __int8 *)Block + v13;
      if ( (*(_BYTE *)a3 & 8) == 0 )
      {
        *(_DWORD *)v5 = _byteswap_ulong(inserted);
        v13 += 4;
        if ( (*(_BYTE *)a3 & 8) == 0 )
        {
          v6 = (Table *)*((_DWORD *)this + 3);
          v7 = (struct Instance *)(*(int (__thiscall **)(Cursor *))(*(_DWORD *)this + 56))(this);
          Table::AddRecords(v6, v7, 1);
          v8 = *((_DWORD *)this + 3);
          if ( *(int *)(v8 + 24) <= 0 || (v9 = *(_DWORD *)(v8 + 1524), v9 == -1) )
            v10 = 0;
          else
            v10 = *(_DWORD *)(v8 + 4 * v9 + 1396);
          if ( v10 )
          {
            Btree::Btree((Btree *)v12, this, *(struct PhysicalIndex **)(v10 + 8));
            LOBYTE(v18) = 1;
            Btree::AddLastKey((Btree *)v12, (const struct QuickKey *)&v13, a3);
            Btree::~Btree((Btree *)v12);
          }
        }
      }
    }
  }
  if ( v15 == 1 )
  {
    if ( Block )
      operator delete[](Block);
  }
}

```

## disassembly

```asm
0x1001b010  mov     edi, edi
0x1001b012  push    ebp
0x1001b013  mov     ebp, esp
0x1001b015  push    0FFFFFFFFh
0x1001b017  push    offset ?Update@Cursor@@UAEXAAVQuickKey@@AAVErr@@@Z_SEH
0x1001b01c  mov     eax, large fs:0
0x1001b022  push    eax
0x1001b023  sub     esp, 10Ch
0x1001b029  mov     eax, ___security_cookie
0x1001b02e  xor     eax, ebp
0x1001b030  mov     [ebp+var_10], eax
0x1001b033  push    ebx
0x1001b034  push    esi
0x1001b035  push    edi; unsigned int
0x1001b036  push    eax; void *
0x1001b037  lea     eax, [ebp+var_C]
0x1001b03a  mov     large fs:0, eax
0x1001b040  mov     edi, ecx
0x1001b042  mov     [ebp+var_114], edi
0x1001b048  mov     eax, [ebp+arg_0]
0x1001b04b  lea     ecx, [ebp+var_30]
0x1001b04e  mov     ebx, [ebp+arg_4]
0x1001b051  xor     esi, esi
0x1001b053  mov     [ebp+Block], ecx
0x1001b056  mov     [ebp+var_40], esi
0x1001b059  mov     [ebp+var_38], esi
0x1001b05c  mov     [ebp+var_34], 20h ; ' '
0x1001b063  push    ebx; struct Err *
0x1001b064  push    eax; struct QuickKey *
0x1001b065  lea     ecx, [ebp+var_40]; this
0x1001b068  mov     [ebp+var_4], esi
0x1001b06b  call    ?Assign@Key@@QAEXABVQuickKey@@AAVErr@@@Z; Key::Assign(QuickKey const &,Err &)
0x1001b070  test    byte ptr [ebx], 8
0x1001b073  jnz     loc_1001B141
0x1001b079  push    ebx
0x1001b07a  push    esi
0x1001b07b  push    2
0x1001b07d  mov     ecx, edi
0x1001b07f  call    ?InsertRecord@Cursor@@AAEKW4CurInsType@@KAAVErr@@@Z; Cursor::InsertRecord(CurInsType,ulong,Err &)
0x1001b084  test    byte ptr [ebx], 8
0x1001b087  mov     esi, eax
0x1001b089  jnz     loc_1001B141
0x1001b08f  mov     edx, [ebp+var_40]
0x1001b092  lea     ecx, [edx+4]
0x1001b095  cmp     ecx, [ebp+var_34]
0x1001b098  ja      short loc_1001B0A1
0x1001b09a  mov     eax, [ebp+Block]
0x1001b09d  add     eax, edx
0x1001b09f  jmp     short loc_1001B0AC
0x1001b0a1  push    ebx; struct Err *
0x1001b0a2  push    4; unsigned int
0x1001b0a4  lea     ecx, [ebp+var_40]; this
0x1001b0a7  call    ?NextByteAlloc@Key@@AAEPAEIAAVErr@@@Z; Key::NextByteAlloc(uint,Err &)
0x1001b0ac  test    byte ptr [ebx], 8
0x1001b0af  jnz     loc_1001B141
0x1001b0b5  bswap   esi
0x1001b0b7  mov     [eax], esi
0x1001b0b9  add     [ebp+var_40], 4
0x1001b0bd  test    byte ptr [ebx], 8
0x1001b0c0  jnz     short loc_1001B141
0x1001b0c2  mov     eax, [ebp+var_114]
0x1001b0c8  mov     edi, [edi+0Ch]
0x1001b0cb  mov     eax, [eax]
0x1001b0cd  mov     esi, [eax+38h]
0x1001b0d0  mov     ecx, esi
0x1001b0d2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001b0d8  mov     ecx, [ebp+var_114]
0x1001b0de  call    esi
0x1001b0e0  push    1; int
0x1001b0e2  push    eax; struct Instance *
0x1001b0e3  mov     ecx, edi; this
0x1001b0e5  call    ?AddRecords@Table@@QAEJPAVInstance@@J@Z; Table::AddRecords(Instance *,long)
0x1001b0ea  mov     ecx, [ebp+var_114]
0x1001b0f0  mov     edx, [ecx+0Ch]
0x1001b0f3  cmp     dword ptr [edx+18h], 0
0x1001b0f7  jle     short loc_1001B10D
0x1001b0f9  mov     eax, [edx+5F4h]
0x1001b0ff  cmp     eax, 0FFFFFFFFh
0x1001b102  jz      short loc_1001B10D
0x1001b104  mov     eax, [edx+eax*4+574h]
0x1001b10b  jmp     short loc_1001B10F
0x1001b10d  xor     eax, eax
0x1001b10f  test    eax, eax
0x1001b111  jz      short loc_1001B141
0x1001b113  push    dword ptr [eax+8]; struct PhysicalIndex *
0x1001b116  push    ecx; struct Cursor *
0x1001b117  lea     ecx, [ebp+var_110]; this
0x1001b11d  call    ??0Btree@@QAE@PAVCursor@@PAVPhysicalIndex@@@Z; Btree::Btree(Cursor *,PhysicalIndex *)
0x1001b122  push    ebx; struct Err *
0x1001b123  lea     eax, [ebp+var_40]
0x1001b126  mov     byte ptr [ebp+var_4], 1
0x1001b12a  push    eax; struct QuickKey *
0x1001b12b  lea     ecx, [ebp+var_110]; this
0x1001b131  call    ?AddLastKey@Btree@@QAEXABVQuickKey@@AAVErr@@@Z; Btree::AddLastKey(QuickKey const &,Err &)
0x1001b136  lea     ecx, [ebp+var_110]; this
0x1001b13c  call    ??1Btree@@QAE@XZ; Btree::~Btree(void)
0x1001b141  cmp     [ebp+var_38], 1
0x1001b145  jnz     short loc_1001B157
0x1001b147  mov     eax, [ebp+Block]
0x1001b14a  test    eax, eax
0x1001b14c  jz      short loc_1001B157
0x1001b14e  push    eax; Block
0x1001b14f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001b154  add     esp, 4
0x1001b157  mov     ecx, [ebp+var_C]
0x1001b15a  mov     large fs:0, ecx
0x1001b161  pop     ecx
0x1001b162  pop     edi
0x1001b163  pop     esi
0x1001b164  pop     ebx
0x1001b165  mov     ecx, [ebp+var_10]
0x1001b168  xor     ecx, ebp; StackCookie
0x1001b16a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001b16f  mov     esp, ebp
0x1001b171  pop     ebp
0x1001b172  retn    8
0x1005ff70  lea     ecx, [ebp+var_40]; this
0x1005ff73  jmp     ??1Key@@QAE@XZ; Key::~Key(void)
0x1005ff78  lea     ecx, [ebp+var_110]; this
0x1005ff7e  jmp     ??1Btree@@QAE@XZ; Btree::~Btree(void)
0x1005ff88  nop
0x1005ff89  nop
0x1005ff8a  mov     edx, [esp-4+arg_4]
0x1005ff8e  lea     eax, [edx+0Ch]
0x1005ff91  mov     ecx, [edx-11Ch]
0x1005ff97  xor     ecx, eax; StackCookie
0x1005ff99  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005ff9e  mov     ecx, [edx-4]
0x1005ffa1  xor     ecx, eax; StackCookie
0x1005ffa3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005ffa8  mov     eax, offset stru_10062FE0
0x1005ffad  jmp     ___CxxFrameHandler3
```
