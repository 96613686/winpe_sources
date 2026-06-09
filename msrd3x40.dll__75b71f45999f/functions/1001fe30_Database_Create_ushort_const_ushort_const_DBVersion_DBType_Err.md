# Database::Create(ushort const *,ushort const *,DBVersion,DBType,Err &)

- ea: `0x1001fe30`
- end: `0x1002007a`
- name: `?Create@Database@@QAEXPBG0W4DBVersion@@W4DBType@@AAVErr@@@Z`
- size: `586`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path`

## callers

- `0x10018700`
- `0x10044340`

## callees

- `0x1001f350`
- `0x1001fe30`
- `0x10020fa0`
- `0x10021720`
- `0x10023360`
- `0x10024a20`
- `0x10025ee0`
- `0x1002e140`
- `0x1002e4e0`
- `0x1002ebe0`
- `0x10046940`
- `0x1004ed00`
- `0x1004f7b0`
- `0x1005e3b0`
- `0x1005e7e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001ffae`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001ffae`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001ff48`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001ff48`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1001ffbe`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1001ffbe`

## pseudocode

```c
void __thiscall Database::Create(int this, size_t a2, unsigned __int16 **a3, int a4, int a5, struct Err *a6)
{
  HANDLE *v7; // ebx
  int v8; // ecx
  int v9; // eax
  int v10; // ecx
  const WCHAR *v11; // ecx
  void *v12; // eax
  int v13; // ecx
  const WCHAR *v14; // eax
  int v15; // ecx
  bool v16; // zf
  unsigned __int16 v17[6]; // [esp+Ch] [ebp-4Ch] BYREF
  void *v18; // [esp+18h] [ebp-40h]
  void *v19; // [esp+1Ch] [ebp-3Ch]
  int v20; // [esp+20h] [ebp-38h]
  size_t cchDest; // [esp+24h] [ebp-34h]
  void *Block; // [esp+28h] [ebp-30h] BYREF
  unsigned __int16 v23[20]; // [esp+2Ch] [ebp-2Ch] BYREF

  cchDest = a2;
  *(_DWORD *)(this + 96) = a5 == 1;
  *(_DWORD *)(this + 68) = a5;
  *(_DWORD *)(this + 104) = 1;
  *(_DWORD *)(this + 100) = 0;
  *(_DWORD *)(this + 80) = a4;
  if ( a5 == 1 )
  {
    *(_DWORD *)(this + 20) |= 0x72u;
    v7 = (HANDLE *)(this + 4);
    System::AllocateTempFileName(a3, (struct Err *)&Block);
    if ( (*(_BYTE *)a6 & 8) != 0 )
      goto LABEL_28;
    File::ReallyOpen((File *)(this + 4), (LPCWSTR)Block, a6);
    if ( (*(_BYTE *)a6 & 8) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( (*(_BYTE *)a6 & 8) != 0 )
        goto LABEL_28;
    }
    Database::AllocateHashTable((Database *)this, a6);
  }
  else
  {
    Database::ValidateConnectString(this, a3, v23, a3, 0, a6);
    if ( (*(_BYTE *)a6 & 8) == 0 )
    {
      v9 = Collate::Order(*(_WORD *)(this + 86), *(_WORD *)(this + 88), v8);
      *(_DWORD *)(this + 92) = v9;
      if ( v9 == 256 || !Database::CanNormalize(this) )
        Err::SetError(a6, -5026, v10);
    }
    *(_DWORD *)(this + 20) |= 0x12u;
    v7 = (HANDLE *)(this + 4);
    if ( (*(_BYTE *)a6 & 8) != 0 )
      goto LABEL_28;
    v11 = 0;
    Block = 0;
    if ( cchDest )
    {
      v20 = wcslen((const unsigned __int16 *)cchDest) + 1;
      v12 = _malloc(2 * v20);
      Block = v12;
      if ( !v12 )
      {
        Err::SetError(a6, -1011, v13);
        return;
      }
      WCSCPY2((size_t *)v12, cchDest, v20);
      v11 = (const WCHAR *)Block;
    }
    v14 = 0;
    if ( cchDest )
      v14 = v11;
    File::Open((File *)(this + 4), v14, a6);
    if ( (*(_BYTE *)a6 & 8) == 0 )
      Database::AllocateHashTable((Database *)this, a6);
    if ( Block )
      _free(Block);
    if ( (*(_BYTE *)a6 & 8) != 0 )
      goto LABEL_28;
    if ( GetFileType(*v7) != 1 )
      Err::SetError(a6, -1044, v15);
  }
  if ( (*(_BYTE *)a6 & 8) == 0 )
  {
    Database::BuildInitialDatabase((Database *)this, v23, a6);
    if ( (*(_BYTE *)a6 & 8) == 0 )
    {
      *(_DWORD *)(this + 220) = 9801;
      return;
    }
  }
LABEL_28:
  v16 = (char *)*v7 + 1 == 0;
  *(_DWORD *)v17 = 1;
  if ( !v16 )
  {
    File::Close((File *)v7, (struct Err *)v17);
    if ( cchDest )
    {
      if ( a5 != 1 )
        System::DeleteFileByName(v17, (LPCWSTR)cchDest, (int)v17);
    }
  }
  v16 = (*(_DWORD *)v17 & 0xFFFFFFFE) == 0;
  *(_DWORD *)(this + 68) = 0;
  if ( !v16 )
  {
    if ( v18 )
      operator delete[](v18);
    if ( v19 )
      operator delete[](v19);
  }
}

```

## disassembly

```asm
0x1001fe30  mov     edi, edi
0x1001fe32  push    ebp
0x1001fe33  mov     ebp, esp
0x1001fe35  sub     esp, 4Ch
0x1001fe38  mov     eax, ___security_cookie
0x1001fe3d  xor     eax, ebp
0x1001fe3f  mov     [ebp+var_4], eax
0x1001fe42  mov     eax, [ebp+arg_0]
0x1001fe45  mov     edx, [ebp+arg_C]
0x1001fe48  push    ebx
0x1001fe49  push    esi
0x1001fe4a  mov     esi, [ebp+arg_10]
0x1001fe4d  mov     [ebp+cchDest], eax
0x1001fe50  xor     eax, eax
0x1001fe52  push    edi
0x1001fe53  mov     edi, ecx
0x1001fe55  cmp     edx, 1
0x1001fe58  mov     ecx, [ebp+arg_4]; unsigned __int16 **
0x1001fe5b  setz    al
0x1001fe5e  push    esi
0x1001fe5f  mov     [edi+60h], eax
0x1001fe62  mov     eax, [ebp+arg_8]
0x1001fe65  mov     [edi+44h], edx
0x1001fe68  mov     dword ptr [edi+68h], 1
0x1001fe6f  mov     dword ptr [edi+64h], 0
0x1001fe76  mov     [edi+50h], eax
0x1001fe79  jnz     short loc_1001FECA
0x1001fe7b  or      dword ptr [edi+14h], 72h
0x1001fe7f  lea     eax, [ebp+Block]
0x1001fe82  lea     ebx, [edi+4]
0x1001fe85  push    eax; struct Err *
0x1001fe86  call    ?AllocateTempFileName@System@@QAEXPAPAGAAVErr@@@Z; System::AllocateTempFileName(ushort * *,Err &)
0x1001fe8b  test    byte ptr [esi], 8
0x1001fe8e  jnz     loc_1001FFEC
0x1001fe94  push    esi; struct Err *
0x1001fe95  push    [ebp+Block]; lpFileName
0x1001fe98  mov     ecx, ebx; this
0x1001fe9a  call    ?ReallyOpen@File@@AAEXPAGAAVErr@@@Z; File::ReallyOpen(ushort *,Err &)
0x1001fe9f  test    byte ptr [esi], 8
0x1001fea2  jz      short loc_1001FEBD
0x1001fea4  mov     eax, [ebp+Block]
0x1001fea7  test    eax, eax
0x1001fea9  jz      short loc_1001FEB4
0x1001feab  push    eax; Block
0x1001feac  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001feb1  add     esp, 4
0x1001feb4  test    byte ptr [esi], 8
0x1001feb7  jnz     loc_1001FFEC
0x1001febd  push    esi; struct Err *
0x1001febe  mov     ecx, edi; this
0x1001fec0  call    ?AllocateHashTable@Database@@IAEXAAVErr@@@Z; Database::AllocateHashTable(Err &)
0x1001fec5  jmp     loc_1001FFD6
0x1001feca  push    0
0x1001fecc  push    ecx
0x1001fecd  lea     eax, [ebp+var_2C]
0x1001fed0  push    eax
0x1001fed1  push    ecx
0x1001fed2  mov     ecx, edi
0x1001fed4  call    ?ValidateConnectString@Database@@IAEXPBGQAGKW4DBLocale@@AAVErr@@@Z; Database::ValidateConnectString(ushort const *,ushort * const,ulong,DBLocale,Err &)
0x1001fed9  test    byte ptr [esi], 8
0x1001fedc  jnz     short loc_1001FF0E
0x1001fede  mov     dx, [edi+58h]
0x1001fee2  push    ecx
0x1001fee3  mov     cx, [edi+56h]
0x1001fee7  call    ?Order@Collate@@SG?AW4SortOrder@@GGG@Z; Collate::Order(ushort,ushort,ushort)
0x1001feec  mov     [edi+5Ch], eax
0x1001feef  cmp     eax, 100h
0x1001fef4  jz      short loc_1001FF01
0x1001fef6  mov     ecx, edi
0x1001fef8  call    ?CanNormalize@Database@@QAE?AW4DBBool@@XZ; Database::CanNormalize(void)
0x1001fefd  test    eax, eax
0x1001feff  jnz     short loc_1001FF0E
0x1001ff01  push    ecx
0x1001ff02  push    0FFFFEC5Eh
0x1001ff07  mov     ecx, esi
0x1001ff09  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1001ff0e  or      dword ptr [edi+14h], 12h
0x1001ff12  lea     ebx, [edi+4]
0x1001ff15  test    byte ptr [esi], 8
0x1001ff18  jnz     loc_1001FFEC
0x1001ff1e  mov     eax, [ebp+cchDest]
0x1001ff21  xor     ecx, ecx
0x1001ff23  mov     [ebp+Block], ecx
0x1001ff26  test    eax, eax
0x1001ff28  jz      short loc_1001FF88
0x1001ff2a  mov     ecx, eax
0x1001ff2c  lea     edx, [ecx+2]
0x1001ff2f  nop
0x1001ff30  mov     ax, [ecx]
0x1001ff33  add     ecx, 2
0x1001ff36  test    ax, ax
0x1001ff39  jnz     short loc_1001FF30
0x1001ff3b  sub     ecx, edx
0x1001ff3d  sar     ecx, 1
0x1001ff3f  lea     eax, [ecx+1]
0x1001ff42  mov     [ebp+var_38], eax
0x1001ff45  add     eax, eax
0x1001ff47  push    eax; Size
0x1001ff48  call    ds:__imp__malloc
0x1001ff4e  add     esp, 4
0x1001ff51  mov     [ebp+Block], eax
0x1001ff54  test    eax, eax
0x1001ff56  jnz     short loc_1001FF78
0x1001ff58  push    ecx
0x1001ff59  push    0FFFFFC0Dh
0x1001ff5e  mov     ecx, esi
0x1001ff60  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1001ff65  pop     edi
0x1001ff66  pop     esi
0x1001ff67  pop     ebx
0x1001ff68  mov     ecx, [ebp+var_4]
0x1001ff6b  xor     ecx, ebp; StackCookie
0x1001ff6d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ff72  mov     esp, ebp
0x1001ff74  pop     ebp
0x1001ff75  retn    14h
0x1001ff78  push    [ebp+var_38]; int
0x1001ff7b  mov     edx, [ebp+cchDest]; cchDest
0x1001ff7e  mov     ecx, eax; pcchNewDestLength
0x1001ff80  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001ff85  mov     ecx, [ebp+Block]
0x1001ff88  xor     eax, eax
0x1001ff8a  cmp     [ebp+cchDest], eax
0x1001ff8d  push    esi; struct Err *
0x1001ff8e  cmovnz  eax, ecx
0x1001ff91  mov     ecx, ebx; this
0x1001ff93  push    eax; lpFileName
0x1001ff94  call    ?Open@File@@QAEXPBGAAVErr@@@Z; File::Open(ushort const *,Err &)
0x1001ff99  test    byte ptr [esi], 8
0x1001ff9c  jnz     short loc_1001FFA6
0x1001ff9e  push    esi; struct Err *
0x1001ff9f  mov     ecx, edi; this
0x1001ffa1  call    ?AllocateHashTable@Database@@IAEXAAVErr@@@Z; Database::AllocateHashTable(Err &)
0x1001ffa6  mov     eax, [ebp+Block]
0x1001ffa9  test    eax, eax
0x1001ffab  jz      short loc_1001FFB7
0x1001ffad  push    eax; Block
0x1001ffae  call    ds:__imp__free
0x1001ffb4  add     esp, 4
0x1001ffb7  test    byte ptr [esi], 8
0x1001ffba  jnz     short loc_1001FFEC
0x1001ffbc  push    dword ptr [ebx]; hFile
0x1001ffbe  call    ds:__imp__GetFileType@4; GetFileType(x)
0x1001ffc4  cmp     eax, 1
0x1001ffc7  jz      short loc_1001FFD6
0x1001ffc9  push    ecx
0x1001ffca  push    0FFFFFBECh
0x1001ffcf  mov     ecx, esi
0x1001ffd1  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1001ffd6  test    byte ptr [esi], 8
0x1001ffd9  jnz     short loc_1001FFEC
0x1001ffdb  push    esi; struct Err *
0x1001ffdc  lea     eax, [ebp+var_2C]
0x1001ffdf  mov     ecx, edi; this
0x1001ffe1  push    eax; unsigned __int16 *
0x1001ffe2  call    ?BuildInitialDatabase@Database@@IAEXQBGAAVErr@@@Z; Database::BuildInitialDatabase(ushort const * const,Err &)
0x1001ffe7  test    byte ptr [esi], 8
0x1001ffea  jz      short loc_1002005D
0x1001ffec  cmp     dword ptr [ebx], 0FFFFFFFFh
0x1001ffef  mov     dword ptr [ebp+var_4C], 1
0x1001fff6  jz      short loc_1002001A
0x1001fff8  lea     eax, [ebp+var_4C]
0x1001fffb  mov     ecx, ebx; this
0x1001fffd  push    eax; struct Err *
0x1001fffe  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x10020003  mov     eax, [ebp+cchDest]
0x10020006  test    eax, eax
0x10020008  jz      short loc_1002001A
0x1002000a  cmp     [ebp+arg_C], 1
0x1002000e  jz      short loc_1002001A
0x10020010  lea     ecx, [ebp+var_4C]; unsigned __int16 *
0x10020013  push    ecx
0x10020014  push    eax; lpFileName
0x10020015  call    ?DeleteFileByName@System@@QAEXPBGAAVErr@@@Z; System::DeleteFileByName(ushort const *,Err &)
0x1002001a  test    dword ptr [ebp+var_4C], 0FFFFFFFEh
0x10020021  mov     dword ptr [edi+44h], 0
0x10020028  jz      short loc_10020067
0x1002002a  mov     eax, [ebp+var_40]
0x1002002d  test    eax, eax
0x1002002f  jz      short loc_1002003A
0x10020031  push    eax; Block
0x10020032  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10020037  add     esp, 4
0x1002003a  mov     eax, [ebp+var_3C]
0x1002003d  test    eax, eax
0x1002003f  jz      short loc_10020067
0x10020041  push    eax; Block
0x10020042  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10020047  add     esp, 4
0x1002004a  pop     edi
0x1002004b  pop     esi
0x1002004c  pop     ebx
0x1002004d  mov     ecx, [ebp+var_4]
0x10020050  xor     ecx, ebp; StackCookie
0x10020052  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10020057  mov     esp, ebp
0x10020059  pop     ebp
0x1002005a  retn    14h
0x1002005d  mov     dword ptr [edi+0DCh], 2649h
0x10020067  mov     ecx, [ebp+var_4]
0x1002006a  pop     edi
0x1002006b  pop     esi
0x1002006c  xor     ecx, ebp; StackCookie
0x1002006e  pop     ebx
0x1002006f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10020074  mov     esp, ebp
0x10020076  pop     ebp
0x10020077  retn    14h
```
