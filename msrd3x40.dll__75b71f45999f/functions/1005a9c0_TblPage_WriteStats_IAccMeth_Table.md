# TblPage::WriteStats(IAccMeth *,Table *)

- ea: `0x1005a9c0`
- end: `0x1005ab6a`
- name: `?WriteStats@TblPage@@QAEXPAVIAccMeth@@PAVTable@@@Z`
- size: `426`
- prototype: `void __thiscall(TblPage *__hidden this, struct IAccMeth *, struct Table *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x10057dd0`

## callees

- `0x1000f750`
- `0x10010580`
- `0x10012db0`
- `0x10023730`
- `0x100572d0`
- `0x1005a9c0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall TblPage::WriteStats(TblPage *this, Database **a2, struct Table *a3)
{
  unsigned int v3; // eax
  bool v4; // zf
  int v5; // esi
  int v6; // edx
  unsigned int v7; // ecx
  unsigned int v8; // eax
  _DWORD *v9; // edi
  unsigned int v10; // edx
  int v11; // ebx
  _DWORD *v12; // ecx
  int v13; // edi
  int v14; // esi
  int v15; // edi
  int v16; // esi
  int v17; // ebx
  int v18; // esi
  int v19; // eax
  int v20; // esi
  void *v21[3]; // [esp+14h] [ebp-44h] BYREF
  void *Block; // [esp+20h] [ebp-38h]
  void *v23; // [esp+24h] [ebp-34h]
  int v24; // [esp+28h] [ebp-30h] BYREF
  int v25; // [esp+2Ch] [ebp-2Ch]
  _DWORD v26[2]; // [esp+34h] [ebp-24h] BYREF
  unsigned int v27; // [esp+3Ch] [ebp-1Ch]
  unsigned int v28; // [esp+40h] [ebp-18h]
  void *v29; // [esp+44h] [ebp-14h]
  int v30; // [esp+48h] [ebp-10h]
  int v31; // [esp+54h] [ebp-4h]

  v24 = 0;
  v25 = 0;
  v31 = 2;
  v26[1] = 0;
  v28 = 0;
  v27 = 0;
  v29 = 0;
  v26[0] = 0;
  v21[0] = (void *)1;
  Database::ReadPageForUpdate(a2[2], (struct PageRef *)&v24, *(_DWORD *)this, v21, (struct Transaction *)a2, 32);
  v3 = (unsigned int)v21[0];
  v4 = ((int)v21[0] & 8) == 0;
  if ( ((int)v21[0] & 8) == 0 )
  {
    v5 = v25 + 8;
    v6 = *((_DWORD *)a3 + 89);
    v7 = *(_DWORD *)(v25 + 12);
    if ( v6 >= 0 || -v6 <= v7 )
      v8 = v6 + v7;
    else
      v8 = 0;
    *(_DWORD *)(v25 + 12) = v8;
    *((_DWORD *)a3 + 88) = v8;
    *((_DWORD *)a3 + 89) = 0;
    Table::GetPhysicalIndexes(a3, (struct Collection *)v26, (struct Err *)v21);
    v3 = (unsigned int)v21[0];
    v9 = (_DWORD *)v26[0];
    v28 = v27;
    v29 = (void *)v26[0];
    v4 = ((int)v21[0] & 8) == 0;
    if ( ((int)v21[0] & 8) == 0 )
    {
      v10 = 0;
      if ( v27 )
      {
        v11 = v5 + 35;
        v30 = v5 + 35;
        do
        {
          v12 = (_DWORD *)v9[v10];
          v13 = *(_DWORD *)(v11 + 8 * v10);
          v14 = v12[11];
          if ( v14 >= 0 || -v14 <= v13 )
            v15 = v14 + v13;
          else
            v15 = 0;
          v16 = v30;
          *(_DWORD *)(v11 + 8 * v10) = v15;
          v17 = v12[13];
          v18 = *(_DWORD *)(v16 + 8 * v10 + 4);
          if ( v17 >= 0 || -v17 <= v18 )
            v19 = v18 + v17;
          else
            v19 = 0;
          v11 = v30;
          *(_DWORD *)(v30 + 8 * v10++ + 4) = v19;
          v12[10] = v15;
          v9 = v29;
          v12[11] = 0;
          v12[12] = v19;
          v12[13] = 0;
        }
        while ( v10 < v28 );
        v3 = (unsigned int)v21[0];
      }
      v4 = (v3 & 8) == 0;
    }
  }
  v20 = v24;
  if ( v4 )
  {
    *(_DWORD *)(v24 + 4 * *(_DWORD *)(v24 + 24) + 28) |= 8u;
    ++*(_DWORD *)(v20 + 64);
    v3 = (unsigned int)v21[0];
  }
  if ( (v3 & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v23 )
      operator delete[](v23);
  }
  if ( v29 )
    operator delete[](v29);
  if ( v20 )
    --*(_WORD *)(v20 + 76);
}

```

## disassembly

```asm
0x1005a9c0  mov     edi, edi
0x1005a9c2  push    ebp
0x1005a9c3  mov     ebp, esp
0x1005a9c5  push    0FFFFFFFFh
0x1005a9c7  push    offset ?WriteStats@TblPage@@QAEXPAVIAccMeth@@PAVTable@@@Z_SEH
0x1005a9cc  mov     eax, large fs:0
0x1005a9d2  push    eax
0x1005a9d3  sub     esp, 3Ch
0x1005a9d6  push    ebx
0x1005a9d7  push    esi
0x1005a9d8  push    edi
0x1005a9d9  mov     eax, ___security_cookie
0x1005a9de  xor     eax, ebp
0x1005a9e0  push    eax
0x1005a9e1  lea     eax, [ebp+var_C]
0x1005a9e4  mov     large fs:0, eax
0x1005a9ea  mov     eax, ecx
0x1005a9ec  xor     esi, esi
0x1005a9ee  mov     [ebp+var_30], esi
0x1005a9f1  mov     [ebp+var_2C], esi
0x1005a9f4  mov     [ebp+var_4], esi
0x1005a9f7  xor     ebx, ebx
0x1005a9f9  xor     edi, edi
0x1005a9fb  mov     [ebp+var_20], esi
0x1005a9fe  mov     [ebp+var_18], ebx
0x1005aa01  mov     [ebp+var_1C], ebx
0x1005aa04  mov     [ebp+var_14], edi
0x1005aa07  mov     [ebp+var_24], edi
0x1005aa0a  mov     [ebp+var_44], 1
0x1005aa11  mov     ecx, [ebp+arg_0]
0x1005aa14  lea     edx, [ebp+var_44]
0x1005aa17  push    20h ; ' '; char
0x1005aa19  push    ecx; struct Transaction *
0x1005aa1a  push    edx; struct Err *
0x1005aa1b  mov     byte ptr [ebp+var_4], 2
0x1005aa1f  push    dword ptr [eax]; unsigned int
0x1005aa21  mov     ecx, [ecx+8]; this
0x1005aa24  lea     eax, [ebp+var_30]
0x1005aa27  push    eax; struct PageRef *
0x1005aa28  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1005aa2d  mov     eax, [ebp+var_44]
0x1005aa30  test    al, 8
0x1005aa32  jnz     loc_1005AB04
0x1005aa38  mov     esi, [ebp+var_2C]
0x1005aa3b  mov     edi, [ebp+arg_4]
0x1005aa3e  add     esi, 8
0x1005aa41  mov     edx, [edi+164h]
0x1005aa47  mov     ecx, [esi+4]
0x1005aa4a  test    edx, edx
0x1005aa4c  jns     short loc_1005AA5A
0x1005aa4e  mov     eax, edx
0x1005aa50  neg     eax
0x1005aa52  cmp     eax, ecx
0x1005aa54  jbe     short loc_1005AA5A
0x1005aa56  xor     eax, eax
0x1005aa58  jmp     short loc_1005AA5D
0x1005aa5a  lea     eax, [edx+ecx]
0x1005aa5d  mov     [esi+4], eax
0x1005aa60  mov     ecx, edi; this
0x1005aa62  mov     [edi+160h], eax
0x1005aa68  lea     eax, [ebp+var_44]
0x1005aa6b  push    eax; struct Err *
0x1005aa6c  lea     eax, [ebp+var_24]
0x1005aa6f  mov     dword ptr [edi+164h], 0
0x1005aa79  push    eax; struct Collection *
0x1005aa7a  call    ?GetPhysicalIndexes@Table@@QBEXAAVCollection@@AAVErr@@@Z; Table::GetPhysicalIndexes(Collection &,Err &)
0x1005aa7f  mov     eax, [ebp+var_44]
0x1005aa82  mov     ebx, [ebp+var_1C]
0x1005aa85  mov     edi, [ebp+var_24]
0x1005aa88  mov     [ebp+var_18], ebx
0x1005aa8b  mov     [ebp+var_14], edi
0x1005aa8e  test    al, 8
0x1005aa90  jnz     short loc_1005AB04
0x1005aa92  xor     edx, edx
0x1005aa94  test    ebx, ebx
0x1005aa96  jz      short loc_1005AB02
0x1005aa98  lea     ebx, [esi+23h]
0x1005aa9b  mov     [ebp+var_10], ebx
0x1005aa9e  mov     edi, edi
0x1005aaa0  mov     ecx, [edi+edx*4]
0x1005aaa3  mov     edi, [ebx+edx*8]
0x1005aaa6  mov     esi, [ecx+2Ch]
0x1005aaa9  test    esi, esi
0x1005aaab  jns     short loc_1005AAB9
0x1005aaad  mov     eax, esi
0x1005aaaf  neg     eax
0x1005aab1  cmp     eax, edi
0x1005aab3  jle     short loc_1005AAB9
0x1005aab5  xor     edi, edi
0x1005aab7  jmp     short loc_1005AABB
0x1005aab9  add     edi, esi
0x1005aabb  mov     esi, [ebp+var_10]
0x1005aabe  mov     [ebx+edx*8], edi
0x1005aac1  mov     ebx, [ecx+34h]
0x1005aac4  mov     esi, [esi+edx*8+4]
0x1005aac8  test    ebx, ebx
0x1005aaca  jns     short loc_1005AAD8
0x1005aacc  mov     eax, ebx
0x1005aace  neg     eax
0x1005aad0  cmp     eax, esi
0x1005aad2  jle     short loc_1005AAD8
0x1005aad4  xor     eax, eax
0x1005aad6  jmp     short loc_1005AADB
0x1005aad8  lea     eax, [esi+ebx]
0x1005aadb  mov     ebx, [ebp+var_10]
0x1005aade  mov     [ebx+edx*8+4], eax
0x1005aae2  inc     edx
0x1005aae3  mov     [ecx+28h], edi
0x1005aae6  mov     edi, [ebp+var_14]
0x1005aae9  mov     dword ptr [ecx+2Ch], 0
0x1005aaf0  mov     [ecx+30h], eax
0x1005aaf3  mov     dword ptr [ecx+34h], 0
0x1005aafa  cmp     edx, [ebp+var_18]
0x1005aafd  jb      short loc_1005AAA0
0x1005aaff  mov     eax, [ebp+var_44]
0x1005ab02  test    al, 8
0x1005ab04  mov     esi, [ebp+var_30]
0x1005ab07  jnz     short loc_1005AB17
0x1005ab09  mov     eax, [esi+18h]
0x1005ab0c  or      dword ptr [esi+eax*4+1Ch], 8
0x1005ab11  inc     dword ptr [esi+40h]
0x1005ab14  mov     eax, [ebp+var_44]
0x1005ab17  test    eax, 0FFFFFFFEh
0x1005ab1c  jz      short loc_1005AB3E
0x1005ab1e  mov     eax, [ebp+Block]
0x1005ab21  test    eax, eax
0x1005ab23  jz      short loc_1005AB2E
0x1005ab25  push    eax; Block
0x1005ab26  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005ab2b  add     esp, 4
0x1005ab2e  mov     eax, [ebp+var_34]
0x1005ab31  test    eax, eax
0x1005ab33  jz      short loc_1005AB3E
0x1005ab35  push    eax; Block
0x1005ab36  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005ab3b  add     esp, 4
0x1005ab3e  mov     eax, [ebp+var_14]
0x1005ab41  test    eax, eax
0x1005ab43  jz      short loc_1005AB4E
0x1005ab45  push    eax; Block
0x1005ab46  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005ab4b  add     esp, 4
0x1005ab4e  test    esi, esi
0x1005ab50  jz      short loc_1005AB56
0x1005ab52  dec     word ptr [esi+4Ch]
0x1005ab56  mov     ecx, [ebp+var_C]
0x1005ab59  mov     large fs:0, ecx
0x1005ab60  pop     ecx
0x1005ab61  pop     edi
0x1005ab62  pop     esi
0x1005ab63  pop     ebx
0x1005ab64  mov     esp, ebp
0x1005ab66  pop     ebp
0x1005ab67  retn    8
0x10062390  lea     ecx, [ebp+var_30]; this
0x10062393  jmp     ??1DataPage@@QAE@XZ; DataPage::~DataPage(void)
0x10062398  lea     ecx, [ebp+var_24]; this
0x1006239b  jmp     ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x100623a0  lea     ecx, [ebp+var_44]; this
0x100623a3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100623ad  nop
0x100623ae  nop
0x100623af  mov     edx, [esp-4+arg_4]
0x100623b3  lea     eax, [edx+0Ch]
0x100623b6  mov     ecx, [edx-4Ch]
0x100623b9  xor     ecx, eax; StackCookie
0x100623bb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100623c0  mov     eax, offset stru_100649F4
0x100623c5  jmp     ___CxxFrameHandler3
```
