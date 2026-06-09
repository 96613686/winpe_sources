# Database::Create(ushort * const,ushort * const,DBVersion,DBType,Err &)

- ea: `0x1005352c`
- end: `0x1005367a`
- name: `?Create@Database@@QAEXQAG0W4DBVersion@@W4DBType@@AAVErr@@@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path`

## callers

- `0x1005df3e`

## callees

- `0x10046ca0`
- `0x1004791f`
- `0x10050d9b`
- `0x10050f9a`
- `0x1005352c`
- `0x100543ca`
- `0x100546f8`
- `0x10055f27`
- `0x10056536`
- `0x10057520`
- `0x100610f0`
- `0x10074b2c`
- `0x10074bb1`
- `0x10122f60`
- `0x1012398c`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x100535e6`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x100535e6`

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
0x1005352c  push    30h
0x1005352e  mov     eax, offset loc_10125324
0x10053533  call    __EH_prolog3_GS
0x10053538  mov     esi, ecx
0x1005353a  mov     eax, [ebp+arg_4]
0x1005353d  xor     edx, edx
0x1005353f  mov     ecx, [ebp+arg_C]
0x10053542  inc     edx
0x10053543  mov     ebx, [ebp+lpFileName]
0x10053546  mov     edi, [ebp+arg_10]
0x10053549  mov     [ebp+var_3C], eax
0x1005354c  xor     eax, eax
0x1005354e  cmp     ecx, edx
0x10053550  mov     [ebp+var_38], ax
0x10053554  mov     [esi+5Ch], eax
0x10053557  setz    al
0x1005355a  mov     [esi+48h], ecx
0x1005355d  push    200h; Size
0x10053562  mov     [esi+58h], eax
0x10053565  lea     eax, [esi+1A8h]
0x1005356b  push    65h ; 'e'; Val
0x1005356d  push    eax; void *
0x1005356e  mov     [esi+60h], edx
0x10053571  mov     [esi+54h], edx
0x10053574  call    _memset
0x10053579  add     esp, 0Ch
0x1005357c  cmp     [ebp+arg_C], 1
0x10053580  push    edi; struct Err *
0x10053581  jnz     short loc_1005358C
0x10053583  mov     ecx, esi; this
0x10053585  call    ?Open@Database@@QAEXAAVErr@@@Z; Database::Open(Err &)
0x1005358a  jmp     short loc_100535FE
0x1005358c  push    0
0x1005358e  push    ecx
0x1005358f  lea     eax, [ebp+var_38]
0x10053592  mov     ecx, esi
0x10053594  push    eax
0x10053595  push    [ebp+var_3C]
0x10053598  call    ?ValidateConnectString@Database@@IAEXPAGQAGJW4DBLocale@@AAVErr@@@Z; Database::ValidateConnectString(ushort *,ushort * const,long,DBLocale,Err &)
0x1005359d  test    byte ptr [edi], 8
0x100535a0  jnz     short loc_10053614
0x100535a2  push    dword ptr [esi+0DCh]
0x100535a8  call    ?CanNormalize@Database@@QAE?AW4DBBool@@K@Z; Database::CanNormalize(ulong)
0x100535ad  test    eax, eax
0x100535af  jnz     short loc_100535BE
0x100535b1  push    ecx
0x100535b2  push    0FFFFEC5Eh
0x100535b7  mov     ecx, edi
0x100535b9  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100535be  test    byte ptr [edi], 8
0x100535c1  jnz     short loc_10053614
0x100535c3  or      dword ptr [esi+18h], 12h
0x100535c7  lea     ecx, [esi+4]; this
0x100535ca  push    edi; struct Err *
0x100535cb  push    ebx; lpFileName
0x100535cc  call    ?Open@File@@QAEXPAGAAVErr@@@Z; File::Open(ushort *,Err &)
0x100535d1  test    byte ptr [edi], 8
0x100535d4  jnz     short loc_10053614
0x100535d6  push    edi; struct Err *
0x100535d7  mov     ecx, esi; this
0x100535d9  call    ?AllocateHashTable@Database@@IAEXAAVErr@@@Z; Database::AllocateHashTable(Err &)
0x100535de  test    byte ptr [edi], 8
0x100535e1  jnz     short loc_10053614
0x100535e3  push    dword ptr [esi+4]; hFile
0x100535e6  call    ds:__imp__GetFileType@4; GetFileType(x)
0x100535ec  cmp     eax, 1
0x100535ef  jz      short loc_100535FE
0x100535f1  push    ecx
0x100535f2  push    0FFFFFBECh
0x100535f7  mov     ecx, edi
0x100535f9  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100535fe  test    byte ptr [edi], 8
0x10053601  jnz     short loc_10053614
0x10053603  push    edi; struct Err *
0x10053604  lea     eax, [ebp+var_38]
0x10053607  mov     ecx, esi; this
0x10053609  push    eax; unsigned __int16 *
0x1005360a  call    ?BuildInitialDatabase@Database@@IAEXQBGAAVErr@@@Z; Database::BuildInitialDatabase(ushort const * const,Err &)
0x1005360f  test    byte ptr [edi], 8
0x10053612  jz      short loc_10053668
0x10053614  xor     edi, edi
0x10053616  inc     edi
0x10053617  mov     [ebp+var_24], edi
0x1005361a  lea     ecx, [esi+4]; this
0x1005361d  mov     [ebp+var_4], 0
0x10053624  cmp     dword ptr [ecx], 0FFFFFFFFh
0x10053627  jz      short loc_1005364E
0x10053629  lea     eax, [ebp+var_24]
0x1005362c  push    eax; struct Err *
0x1005362d  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x10053632  test    ebx, ebx
0x10053634  jz      short loc_1005364E
0x10053636  cmp     [ebp+arg_C], edi
0x10053639  jz      short loc_1005364E
0x1005363b  push    ebx; lpFileName
0x1005363c  call    _JetDeleteFileW@4; JetDeleteFileW(x)
0x10053641  test    eax, eax
0x10053643  jnz     short loc_1005364E
0x10053645  lea     eax, [ebp+var_24]
0x10053648  push    eax
0x10053649  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1005364e  test    [ebp+var_24], 0FFFFFFFEh
0x10053655  mov     dword ptr [esi+48h], 0
0x1005365c  jz      short loc_10053672
0x1005365e  lea     ecx, [ebp+var_24]; this
0x10053661  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10053666  jmp     short loc_10053672
0x10053668  mov     dword ptr [esi+0D8h], 2649h
0x10053672  call    __EH_epilog3_GS
0x10053677  retn    14h
0x10125317  lea     ecx, [ebp+var_24]; this
0x1012531a  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10125324  nop
0x10125325  nop
0x10125326  mov     edx, [esp-4+arg_4]
0x1012532a  lea     eax, [edx+0Ch]
0x1012532d  mov     ecx, [edx-40h]
0x10125330  xor     ecx, eax; StackCookie
0x10125332  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10125337  mov     ecx, [edx-4]
0x1012533a  xor     ecx, eax; StackCookie
0x1012533c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10125341  mov     eax, offset stru_10127DD0
0x10125346  jmp     ___CxxFrameHandler3
```
