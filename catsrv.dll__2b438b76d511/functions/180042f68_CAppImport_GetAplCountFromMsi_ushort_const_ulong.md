# CAppImport::GetAplCountFromMsi(ushort const *,ulong *)

- ea: `0x180042f68`
- end: `0x180043084`
- name: `?GetAplCountFromMsi@CAppImport@@AEAAJPEBGPEAK@Z`
- size: `284`
- prototype: `int(CAppImport *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800434f0`

## callees

- `0x180042ce8`
- `0x180042d04`
- `0x180042d34`
- `0x180042f68`

## import_xrefs

- `msi!__imp_MsiCreateRecord` at `0x180042fee`
- `msi!__imp_MsiCreateRecord` at `0x180042fee`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180042fd2`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180042fd2`
- `msi!__imp_MsiOpenDatabaseW` at `0x180042fa8`
- `msi!__imp_MsiOpenDatabaseW` at `0x180042fa8`
- `msi!__imp_MsiViewExecute` at `0x180042fe1`
- `msi!__imp_MsiViewExecute` at `0x180042fe1`
- `msi!__imp_MsiViewFetch` at `0x18004301b`
- `msi!__imp_MsiViewFetch` at `0x180043038`
- `msi!__imp_MsiViewFetch` at `0x18004301b`
- `msi!__imp_MsiViewFetch` at `0x180043038`

## string_xrefs

- `0x180042fc8`: `SELECT `File` FROM `Complus`, `File` WHERE `Complus`.`Component_` = `File`.`Component_``

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAppImport::GetAplCountFromMsi(CAppImport *this, const unsigned __int16 *a2, unsigned int *a3)
{
  MSIHANDLE *v5; // rax
  unsigned int v6; // ebx
  MSIHANDLE *v7; // rax
  MSIHANDLE Record; // eax
  MSIHANDLE *v9; // rax
  unsigned int v10; // edi
  MSIHANDLE *v11; // rax
  UINT v12; // eax
  UINT v13; // ecx
  MSIHANDLE hDatabase[4]; // [rsp+20h] [rbp-10h] BYREF
  MSIHANDLE v16; // [rsp+50h] [rbp+20h] BYREF
  int v17; // [rsp+54h] [rbp+24h]
  MSIHANDLE hView; // [rsp+68h] [rbp+38h] BYREF

  v17 = HIDWORD(this);
  hDatabase[0] = 0;
  hView = 0;
  v16 = 0;
  v5 = PMSIHANDLE::operator&(hDatabase);
  if ( !MsiOpenDatabaseW(a2, 0, v5) )
  {
    v7 = PMSIHANDLE::operator&(&hView);
    if ( !MsiDatabaseOpenViewW(
            hDatabase[0],
            L"SELECT `File` FROM `Complus`, `File` WHERE `Complus`.`Component_` = `File`.`Component_`",
            v7)
      && !MsiViewExecute(hView, 0) )
    {
      Record = MsiCreateRecord(1u);
      PMSIHANDLE::operator=(&v16, Record);
      if ( !v16 )
      {
        v6 = -2147024882;
        goto LABEL_14;
      }
      v9 = PMSIHANDLE::operator&(&v16);
      if ( !MsiViewFetch(hView, v9) )
      {
        v10 = 0;
        do
        {
          ++v10;
          v11 = PMSIHANDLE::operator&(&v16);
          v12 = MsiViewFetch(hView, v11);
        }
        while ( !v12 );
        v13 = 0;
        if ( v12 != 259 )
          v13 = v12;
        if ( !v13 )
        {
          v6 = 0;
          *a3 = v10;
          goto LABEL_14;
        }
      }
    }
  }
  v6 = -2146368504;
LABEL_14:
  PMSIHANDLE::~PMSIHANDLE(&v16);
  PMSIHANDLE::~PMSIHANDLE(&hView);
  PMSIHANDLE::~PMSIHANDLE(hDatabase);
  return v6;
}

```

## disassembly

```asm
0x180042f68  mov     [rsp-18h+arg_8], rbx
0x180042f6d  mov     [rsp-18h+arg_0], rcx
0x180042f72  push    rbp
0x180042f73  push    rsi
0x180042f74  push    rdi
0x180042f75  mov     rbp, rsp
0x180042f78  sub     rsp, 30h
0x180042f7c  mov     rsi, r8
0x180042f7f  mov     rbx, rdx
0x180042f82  mov     [rbp+hDatabase], 0
0x180042f89  mov     [rbp+hView], 0
0x180042f90  mov     dword ptr [rbp+arg_0], 0
0x180042f97  lea     rcx, [rbp+hDatabase]
0x180042f9b  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180042fa0  mov     r8, rax; phDatabase
0x180042fa3  xor     edx, edx; szPersist
0x180042fa5  mov     rcx, rbx; szDatabasePath
0x180042fa8  call    cs:__imp_MsiOpenDatabaseW
0x180042fae  test    eax, eax
0x180042fb0  jz      short loc_180042FBC
0x180042fb2  mov     ebx, 80110408h
0x180042fb7  jmp     loc_180043058
0x180042fbc  lea     rcx, [rbp+hView]
0x180042fc0  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180042fc5  mov     r8, rax; phView
0x180042fc8  lea     rdx, aSelectFileFrom; "SELECT `File` FROM `Complus`, `File` WH"...
0x180042fcf  mov     ecx, [rbp+hDatabase]; hDatabase
0x180042fd2  call    cs:__imp_MsiDatabaseOpenViewW
0x180042fd8  test    eax, eax
0x180042fda  jnz     short loc_180042FB2
0x180042fdc  xor     edx, edx; hRecord
0x180042fde  mov     ecx, [rbp+hView]; hView
0x180042fe1  call    cs:__imp_MsiViewExecute
0x180042fe7  test    eax, eax
0x180042fe9  jnz     short loc_180042FB2
0x180042feb  lea     ecx, [rax+1]; cParams
0x180042fee  call    cs:__imp_MsiCreateRecord
0x180042ff4  mov     edx, eax
0x180042ff6  lea     rcx, [rbp+arg_0]
0x180042ffa  call    ??4PMSIHANDLE@@QEAAXK@Z; PMSIHANDLE::operator=(ulong)
0x180042fff  cmp     dword ptr [rbp+arg_0], 0
0x180043003  jnz     short loc_18004300C
0x180043005  mov     ebx, 8007000Eh
0x18004300a  jmp     short loc_180043058
0x18004300c  lea     rcx, [rbp+arg_0]
0x180043010  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180043015  mov     rdx, rax; phRecord
0x180043018  mov     ecx, [rbp+hView]; hView
0x18004301b  call    cs:__imp_MsiViewFetch
0x180043021  test    eax, eax
0x180043023  jnz     short loc_180042FB2
0x180043025  xor     edi, edi
0x180043027  inc     edi
0x180043029  lea     rcx, [rbp+arg_0]
0x18004302d  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180043032  mov     rdx, rax; phRecord
0x180043035  mov     ecx, [rbp+hView]; hView
0x180043038  call    cs:__imp_MsiViewFetch
0x18004303e  test    eax, eax
0x180043040  jz      short loc_180043027
0x180043042  xor     ecx, ecx
0x180043044  cmp     eax, 103h
0x180043049  cmovnz  ecx, eax
0x18004304c  test    ecx, ecx
0x18004304e  jnz     loc_180042FB2
0x180043054  xor     ebx, ebx
0x180043056  mov     [rsi], edi
0x180043058  lea     rcx, [rbp+arg_0]; this
0x18004305c  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x180043061  nop
0x180043062  lea     rcx, [rbp+hView]; this
0x180043066  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x18004306b  nop
0x18004306c  lea     rcx, [rbp+hDatabase]; this
0x180043070  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x180043075  mov     eax, ebx
0x180043077  mov     rbx, [rsp+30h+arg_8]
0x18004307c  add     rsp, 30h
0x180043080  pop     rdi
0x180043081  pop     rsi
0x180043082  pop     rbp
0x180043083  retn
```
