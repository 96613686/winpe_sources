# CCatalogServer::CreateEmptyDir(ushort const *)

- ea: `0x18000a310`
- end: `0x18000a418`
- name: `?CreateEmptyDir@CCatalogServer@@UEAAJPEBG@Z`
- size: `264`
- prototype: `__int64 __fastcall(CCatalogServer *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009098`
- `0x18000a310`
- `0x18000ae48`
- `0x18000ae78`
- `0x18000e468`
- `0x180032c98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a39b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a39b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a37f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a37f`

## string_xrefs

- `0x18000a3ad`: `'CreateEmptyDir:CreateDirectory'`
- `0x18000a3c0`: `com\complus\src\comcat\catsrv\reputil.cpp`
- `0x18000a339`: `'CreateEmptyDir'`
- `0x18000a358`: `'CreateEmptyDir -- ImpersonateClient'`

## pseudocode

```c
__int64 __fastcall CCatalogServer::CreateEmptyDir(CCatalogServer *this, const unsigned __int16 *a2)
{
  signed int v4; // eax
  const unsigned __int16 *v5; // r9
  unsigned int v6; // r8d
  DWORD LastError; // eax
  void *ppInterface; // [rsp+20h] [rbp-58h] BYREF
  __int64 v10; // [rsp+28h] [rbp-50h]
  __int64 v11; // [rsp+30h] [rbp-48h]
  signed int v12; // [rsp+38h] [rbp-40h] BYREF
  __int16 v13; // [rsp+3Ch] [rbp-3Ch]
  int v14; // [rsp+40h] [rbp-38h]
  const unsigned __int16 *v15; // [rsp+48h] [rbp-30h]
  __int64 v16; // [rsp+50h] [rbp-28h]
  __int64 v17; // [rsp+58h] [rbp-20h]
  int v18; // [rsp+60h] [rbp-18h]
  int v19; // [rsp+64h] [rbp-14h]
  int v20; // [rsp+A8h] [rbp+30h] BYREF

  ppInterface = 0;
  LODWORD(v10) = 0;
  v11 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = L"'CreateEmptyDir'";
    v6 = 445;
LABEL_12:
    v20 = v4;
    goto LABEL_13;
  }
  v4 = CImpersonate::ImpersonateClient(&ppInterface);
  v20 = v4;
  if ( v4 < 0 )
  {
    v5 = L"'CreateEmptyDir -- ImpersonateClient'";
    v6 = 452;
LABEL_13:
    v12 = v4;
    v14 = -1073737001;
    v13 = 22;
    v15 = v5;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 1;
    CError::WriteToLog((CError *)&v12, L"com\\complus\\src\\comcat\\catsrv\\reputil.cpp", v6, v5, ppInterface, v10, v11);
    goto LABEL_14;
  }
  v20 = CCatalogServer::DeleteRecursive((CCatalogServer *)((char *)this - 112), a2);
  if ( v20 >= 0 && !CreateDirectoryW(a2, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 80 && LastError != 183 )
    {
      v4 = GetLastError();
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      v5 = L"'CreateEmptyDir:CreateDirectory'";
      v6 = 473;
      goto LABEL_12;
    }
  }
LABEL_14:
  CImpersonate::Cleanup((CImpersonate *)&ppInterface, &v20);
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18000a310  push    rbp
0x18000a312  push    rbx
0x18000a313  push    rsi
0x18000a314  push    rdi
0x18000a315  mov     rbp, rsp
0x18000a318  sub     rsp, 78h
0x18000a31c  xor     esi, esi
0x18000a31e  mov     rbx, rdx
0x18000a321  mov     [rbp+ppInterface], rsi
0x18000a325  mov     rdi, rcx
0x18000a328  mov     dword ptr [rbp+var_50], esi
0x18000a32b  mov     [rbp+var_48], rsi
0x18000a32f  test    rdx, rdx
0x18000a332  jnz     short loc_18000A348
0x18000a334  mov     eax, 80070057h
0x18000a339  lea     r9, aCreateemptydir_0; "'CreateEmptyDir'"
0x18000a340  mov     r8d, 1BDh
0x18000a346  jmp     short loc_18000A3BA
0x18000a348  lea     rcx, [rbp+ppInterface]; ppInterface
0x18000a34c  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x18000a351  mov     [rbp+arg_8], eax
0x18000a354  test    eax, eax
0x18000a356  jns     short loc_18000A367
0x18000a358  lea     r9, aCreateemptydir_1; "'CreateEmptyDir -- ImpersonateClient'"
0x18000a35f  mov     r8d, 1C4h
0x18000a365  jmp     short loc_18000A3BD
0x18000a367  lea     rcx, [rdi-70h]; this
0x18000a36b  mov     rdx, rbx; unsigned __int16 *
0x18000a36e  call    ?DeleteRecursive@CCatalogServer@@AEAAJPEBG@Z; CCatalogServer::DeleteRecursive(ushort const *)
0x18000a373  mov     [rbp+arg_8], eax
0x18000a376  test    eax, eax
0x18000a378  js      short loc_18000A3F6
0x18000a37a  xor     edx, edx; lpSecurityAttributes
0x18000a37c  mov     rcx, rbx; lpPathName
0x18000a37f  call    cs:__imp_CreateDirectoryW
0x18000a385  test    eax, eax
0x18000a387  jnz     short loc_18000A3F6
0x18000a389  call    cs:__imp_GetLastError
0x18000a38f  cmp     eax, 50h ; 'P'
0x18000a392  jz      short loc_18000A3F6
0x18000a394  cmp     eax, 0B7h
0x18000a399  jz      short loc_18000A3F6
0x18000a39b  call    cs:__imp_GetLastError
0x18000a3a1  test    eax, eax
0x18000a3a3  jle     short loc_18000A3AD
0x18000a3a5  movzx   eax, ax
0x18000a3a8  or      eax, 80070000h
0x18000a3ad  lea     r9, aCreateemptydir; "'CreateEmptyDir:CreateDirectory'"
0x18000a3b4  mov     r8d, 1D9h; unsigned int
0x18000a3ba  mov     [rbp+arg_8], eax
0x18000a3bd  mov     [rbp+var_40], eax
0x18000a3c0  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrv\\repu"...
0x18000a3c7  mov     eax, 16h
0x18000a3cc  mov     [rbp+var_38], 0C00012D7h
0x18000a3d3  lea     rcx, [rbp+var_40]; this
0x18000a3d7  mov     [rbp+var_3C], ax
0x18000a3db  mov     [rbp+var_30], r9
0x18000a3df  mov     [rbp+var_28], rsi
0x18000a3e3  mov     [rbp+var_20], rsi
0x18000a3e7  mov     [rbp+var_18], esi
0x18000a3ea  mov     [rbp+var_14], 1
0x18000a3f1  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000a3f6  lea     rdx, [rbp+arg_8]; int *
0x18000a3fa  lea     rcx, [rbp+ppInterface]; this
0x18000a3fe  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x18000a403  lea     rcx, [rbp+ppInterface]; this
0x18000a407  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18000a40c  mov     eax, [rbp+arg_8]
0x18000a40f  add     rsp, 78h
0x18000a413  pop     rdi
0x18000a414  pop     rsi
0x18000a415  pop     rbx
0x18000a416  pop     rbp
0x18000a417  retn
```
