# Database::Create(ushort * const,ushort * const,DBVersion,DBType,Err &)

- ea: `0x100536bc`
- end: `0x1005380a`
- name: `?Create@Database@@QAEXQAG0W4DBVersion@@W4DBType@@AAVErr@@@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path`

## callers

- `0x1005e0ce`

## callees

- `0x10046e20`
- `0x10047a9f`
- `0x10050f2b`
- `0x1005112a`
- `0x100536bc`
- `0x1005455a`
- `0x10054888`
- `0x100560b7`
- `0x100566c6`
- `0x100576b0`
- `0x10061284`
- `0x10074cbc`
- `0x10074d41`
- `0x10123110`
- `0x10123b3c`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x10053776`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x10053776`

## pseudocode

```c
void __thiscall Database::Create(_DWORD *this, const WCHAR *lpFileName, int a3, int a4, int a5, struct Err *a6)
{
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  struct Err *v10; // ecx
  bool v11; // zf
  unsigned __int16 v12[10]; // [esp+14h] [ebp-38h] BYREF
  void *v13[9]; // [esp+28h] [ebp-24h] BYREF

  v12[0] = 0;
  this[23] = 0;
  this[18] = a5;
  this[22] = a5 == 1;
  this[24] = 1;
  this[21] = 1;
  memset(this + 106, 101, 0x200u);
  if ( a5 == 1 )
  {
    Database::Open((Database *)this, a6);
  }
  else
  {
    Database::ValidateConnectString(this, a3, v12, v7, 0, a6);
    if ( (*(_BYTE *)a6 & 8) != 0 )
      goto LABEL_13;
    if ( !Database::CanNormalize(this[55]) )
      Err::SetError(a6, -5026, v8);
    if ( (*(_BYTE *)a6 & 8) != 0 )
      goto LABEL_13;
    this[6] |= 0x12u;
    File::Open((File *)(this + 1), lpFileName, a6);
    if ( (*(_BYTE *)a6 & 8) != 0 )
      goto LABEL_13;
    Database::AllocateHashTable((Database *)this, a6);
    if ( (*(_BYTE *)a6 & 8) != 0 )
      goto LABEL_13;
    if ( GetFileType((HANDLE)this[1]) != 1 )
      Err::SetError(a6, -1044, v9);
  }
  if ( (*(_BYTE *)a6 & 8) == 0 )
  {
    Database::BuildInitialDatabase((Database *)this, v12, a6);
    if ( (*(_BYTE *)a6 & 8) == 0 )
    {
      this[54] = 9801;
      return;
    }
  }
LABEL_13:
  v13[0] = (void *)1;
  v13[8] = 0;
  if ( this[1] != -1 )
  {
    File::Close((File *)(this + 1), (struct Err *)v13);
    if ( lpFileName )
    {
      if ( a5 != 1 && !JetDeleteFileW(lpFileName) )
        System::ErrGetLastError(v10);
    }
  }
  v11 = ((int)v13[0] & 0xFFFFFFFE) == 0;
  this[18] = 0;
  if ( !v11 )
    Err::Delete(v13);
}

```

## disassembly

```asm
0x100536bc  push    30h
0x100536be  mov     eax, offset loc_101254D4
0x100536c3  call    __EH_prolog3_GS
0x100536c8  mov     esi, ecx
0x100536ca  mov     eax, [ebp+arg_4]
0x100536cd  xor     edx, edx
0x100536cf  mov     ecx, [ebp+arg_C]
0x100536d2  inc     edx
0x100536d3  mov     ebx, [ebp+lpFileName]
0x100536d6  mov     edi, [ebp+arg_10]
0x100536d9  mov     [ebp+var_3C], eax
0x100536dc  xor     eax, eax
0x100536de  cmp     ecx, edx
0x100536e0  mov     [ebp+var_38], ax
0x100536e4  mov     [esi+5Ch], eax
0x100536e7  setz    al
0x100536ea  mov     [esi+48h], ecx
0x100536ed  push    200h; Size
0x100536f2  mov     [esi+58h], eax
0x100536f5  lea     eax, [esi+1A8h]
0x100536fb  push    65h ; 'e'; Val
0x100536fd  push    eax; void *
0x100536fe  mov     [esi+60h], edx
0x10053701  mov     [esi+54h], edx
0x10053704  call    _memset
0x10053709  add     esp, 0Ch
0x1005370c  cmp     [ebp+arg_C], 1
0x10053710  push    edi; struct Err *
0x10053711  jnz     short loc_1005371C
0x10053713  mov     ecx, esi; this
0x10053715  call    ?Open@Database@@QAEXAAVErr@@@Z; Database::Open(Err &)
0x1005371a  jmp     short loc_1005378E
0x1005371c  push    0
0x1005371e  push    ecx
0x1005371f  lea     eax, [ebp+var_38]
0x10053722  mov     ecx, esi
0x10053724  push    eax
0x10053725  push    [ebp+var_3C]
0x10053728  call    ?ValidateConnectString@Database@@IAEXPAGQAGJW4DBLocale@@AAVErr@@@Z; Database::ValidateConnectString(ushort *,ushort * const,long,DBLocale,Err &)
0x1005372d  test    byte ptr [edi], 8
0x10053730  jnz     short loc_100537A4
0x10053732  push    dword ptr [esi+0DCh]
0x10053738  call    ?CanNormalize@Database@@QAE?AW4DBBool@@K@Z; Database::CanNormalize(ulong)
0x1005373d  test    eax, eax
0x1005373f  jnz     short loc_1005374E
0x10053741  push    ecx
0x10053742  push    0FFFFEC5Eh
0x10053747  mov     ecx, edi
0x10053749  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005374e  test    byte ptr [edi], 8
0x10053751  jnz     short loc_100537A4
0x10053753  or      dword ptr [esi+18h], 12h
0x10053757  lea     ecx, [esi+4]; this
0x1005375a  push    edi; struct Err *
0x1005375b  push    ebx; lpFileName
0x1005375c  call    ?Open@File@@QAEXPAGAAVErr@@@Z; File::Open(ushort *,Err &)
0x10053761  test    byte ptr [edi], 8
0x10053764  jnz     short loc_100537A4
0x10053766  push    edi; struct Err *
0x10053767  mov     ecx, esi; this
0x10053769  call    ?AllocateHashTable@Database@@IAEXAAVErr@@@Z; Database::AllocateHashTable(Err &)
0x1005376e  test    byte ptr [edi], 8
0x10053771  jnz     short loc_100537A4
0x10053773  push    dword ptr [esi+4]; hFile
0x10053776  call    ds:__imp__GetFileType@4; GetFileType(x)
0x1005377c  cmp     eax, 1
0x1005377f  jz      short loc_1005378E
0x10053781  push    ecx
0x10053782  push    0FFFFFBECh
0x10053787  mov     ecx, edi
0x10053789  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005378e  test    byte ptr [edi], 8
0x10053791  jnz     short loc_100537A4
0x10053793  push    edi; struct Err *
0x10053794  lea     eax, [ebp+var_38]
0x10053797  mov     ecx, esi; this
0x10053799  push    eax; unsigned __int16 *
0x1005379a  call    ?BuildInitialDatabase@Database@@IAEXQBGAAVErr@@@Z; Database::BuildInitialDatabase(ushort const * const,Err &)
0x1005379f  test    byte ptr [edi], 8
0x100537a2  jz      short loc_100537F8
0x100537a4  xor     edi, edi
0x100537a6  inc     edi
0x100537a7  mov     [ebp+var_24], edi
0x100537aa  lea     ecx, [esi+4]; this
0x100537ad  mov     [ebp+var_4], 0
0x100537b4  cmp     dword ptr [ecx], 0FFFFFFFFh
0x100537b7  jz      short loc_100537DE
0x100537b9  lea     eax, [ebp+var_24]
0x100537bc  push    eax; struct Err *
0x100537bd  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x100537c2  test    ebx, ebx
0x100537c4  jz      short loc_100537DE
0x100537c6  cmp     [ebp+arg_C], edi
0x100537c9  jz      short loc_100537DE
0x100537cb  push    ebx; lpFileName
0x100537cc  call    _JetDeleteFileW@4; JetDeleteFileW(x)
0x100537d1  test    eax, eax
0x100537d3  jnz     short loc_100537DE
0x100537d5  lea     eax, [ebp+var_24]
0x100537d8  push    eax
0x100537d9  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x100537de  test    [ebp+var_24], 0FFFFFFFEh
0x100537e5  mov     dword ptr [esi+48h], 0
0x100537ec  jz      short loc_10053802
0x100537ee  lea     ecx, [ebp+var_24]; this
0x100537f1  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100537f6  jmp     short loc_10053802
0x100537f8  mov     dword ptr [esi+0D8h], 2649h
0x10053802  call    __EH_epilog3_GS
0x10053807  retn    14h
0x101254c7  lea     ecx, [ebp+var_24]; this
0x101254ca  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x101254d4  nop
0x101254d5  nop
0x101254d6  mov     edx, [esp-4+arg_4]
0x101254da  lea     eax, [edx+0Ch]
0x101254dd  mov     ecx, [edx-40h]
0x101254e0  xor     ecx, eax; StackCookie
0x101254e2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x101254e7  mov     ecx, [edx-4]
0x101254ea  xor     ecx, eax; StackCookie
0x101254ec  call    @__security_check_cookie@4; __security_check_cookie(x)
0x101254f1  mov     eax, offset stru_10127F80
0x101254f6  jmp     ___CxxFrameHandler3
```
