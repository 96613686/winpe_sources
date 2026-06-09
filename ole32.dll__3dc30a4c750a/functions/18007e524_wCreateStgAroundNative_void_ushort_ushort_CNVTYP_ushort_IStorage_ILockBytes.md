# wCreateStgAroundNative(void *,ushort,ushort,CNVTYP,ushort,IStorage * *,ILockBytes * *)

- ea: `0x18007e524`
- end: `0x18007e75e`
- name: `?wCreateStgAroundNative@@YAJPEAXGGW4CNVTYP@@GPEAPEAUIStorage@@PEAPEAUILockBytes@@@Z`
- size: `570`
- prototype: `HRESULT __fastcall(void *hNative, unsigned __int16 aClassOld, unsigned __int16 aClassNew, CNVTYP cnvtyp, unsigned __int16 aItem, IStorage **ppstg, ILockBytes **pplkbyt)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007f708`

## callees

- `0x18001a640`
- `0x18002cbb0`
- `0x180052390`
- `0x18007790c`
- `0x18007dc58`
- `0x18007e524`
- `0x180084ba0`
- `0x1800856f0`
- `0x1800a4afc`
- `0x1800a4b80`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18007e69c`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18007e69c`
- `USER32!RegisterClipboardFormatW` at `0x18007e6b5`
- `USER32!RegisterClipboardFormatW` at `0x18007e6b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e629`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e629`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18007e5a1`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18007e5a1`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18007e665`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18007e665`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x18007e5bf`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x18007e5bf`

## pseudocode

```c
__int64 __fastcall wCreateStgAroundNative(
        void *hNative,
        ATOM aClassOld,
        ATOM aClassNew,
        CNVTYP cnvtyp,
        unsigned __int16 aItem,
        IStorage **ppstg,
        ILockBytes **pplkbyt)
{
  unsigned int UserType; // ebx
  CLIPFORMAT v12; // ax
  HRESULT v13; // eax
  int v14; // r8d
  const char *v15; // rax
  IStorage *pstg; // [rsp+20h] [rbp-E0h] BYREF
  ILockBytes *plkbyt; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t *szUserType; // [rsp+30h] [rbp-D0h] BYREF
  void *v19; // [rsp+38h] [rbp-C8h]
  _GUID clsid; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t szClassOld[256]; // [rsp+50h] [rbp-B0h] BYREF

  v19 = hNative;
  pstg = 0;
  plkbyt = 0;
  szUserType = 0;
  *ppstg = 0;
  clsid = 0;
  UserType = CreateILockBytesOnHGlobal(0, 1, &plkbyt);
  if ( !UserType )
  {
    UserType = StgCreateDocfileOnILockBytes(plkbyt, 0x1012u, 0, &pstg);
    if ( !UserType )
    {
      if ( !pstg )
        return 2147549183LL;
      if ( cnvtyp != cnvtypConvertTo )
        aClassNew = aClassOld;
      if ( CLSIDFromAtom(aClassNew, &clsid) )
      {
        UserType = WriteClassStg(pstg, &clsid);
        if ( !UserType )
        {
          UserType = OleRegGetUserType(&clsid, 1u, &szUserType);
          if ( !UserType )
          {
            if ( GlobalGetAtomNameW(aClassOld, szClassOld, 256) )
            {
              v12 = RegisterClipboardFormatW(szClassOld);
              UserType = WriteFmtUserTypeStg(pstg, v12, szUserType);
              if ( !UserType )
              {
                v13 = cnvtyp == cnvtypConvertTo ? SetBitOleStg(pstg, 0xFFFFFFFF, 4u) : WriteOleStg(pstg, 0, 0, 0);
                UserType = v13;
                if ( !v13 )
                {
                  UserType = StSave10NativeData(pstg, v19, v14);
                  if ( !UserType )
                  {
                    if ( !aItem || (v15 = wAtomNameA(aItem), (UserType = StSave10ItemName(pstg, v15)) == 0) )
                    {
                      *ppstg = pstg;
                      *pplkbyt = plkbyt;
                      return 0;
                    }
                  }
                }
              }
            }
            else
            {
              UserType = -2147418113;
            }
          }
        }
      }
      else
      {
        UserType = -2147221164;
      }
    }
  }
  if ( pstg )
    ((void (__fastcall *)(IStorage *))pstg->lpVtbl->Release)(pstg);
  if ( plkbyt )
    ((void (__fastcall *)(ILockBytes *))plkbyt->lpVtbl->Release)(plkbyt);
  CoTaskMemFree(szUserType);
  return UserType;
}

```

## disassembly

```asm
0x18007e524  mov     [rsp-8+arg_18], rbx
0x18007e529  push    rbp
0x18007e52a  push    rsi
0x18007e52b  push    rdi
0x18007e52c  push    r12
0x18007e52e  push    r13
0x18007e530  push    r14
0x18007e532  push    r15
0x18007e534  lea     rbp, [rsp-160h]
0x18007e53c  sub     rsp, 260h
0x18007e543  mov     rax, cs:__security_cookie
0x18007e54a  xor     rax, rsp
0x18007e54d  mov     [rbp+190h+var_40], rax
0x18007e554  mov     r12, [rbp+190h+arg_28]
0x18007e55b  xor     eax, eax
0x18007e55d  movzx   r14d, [rbp+190h+arg_20]
0x18007e565  movzx   edi, aClassNew
0x18007e569  mov     r13, [rbp+190h+arg_30]
0x18007e570  lea     r8, [rsp+290h+plkbyt]; pplkbyt
0x18007e575  movzx   r15d, aClassOld
0x18007e579  mov     [rsp+290h+var_258], hNative
0x18007e57e  xorps   xmm0, xmm0
0x18007e581  mov     [rsp+290h+pstg], rax
0x18007e586  lea     edx, [rax+1]; fDeleteOnRelease
0x18007e589  mov     [rsp+290h+plkbyt], rax
0x18007e58e  xor     ecx, ecx; hGlobal
0x18007e590  mov     [rsp+290h+szUserType], rax
0x18007e595  mov     esi, cnvtyp
0x18007e598  mov     [r12], rax
0x18007e59c  movups  xmmword ptr [rsp+290h+clsid.Data1], xmm0
0x18007e5a1  call    cs:__imp_CreateILockBytesOnHGlobal
0x18007e5a7  mov     ebx, eax
0x18007e5a9  test    eax, eax
0x18007e5ab  jnz     short $errRtn_94
0x18007e5ad  mov     hNative, [rsp+290h+plkbyt]; plkbyt
0x18007e5b2  lea     r9, [rsp+290h+pstg]; ppstgOpen
0x18007e5b7  xor     r8d, r8d; reserved
0x18007e5ba  mov     edx, 1012h; grfMode
0x18007e5bf  call    cs:__imp_StgCreateDocfileOnILockBytes
0x18007e5c5  mov     ebx, eax
0x18007e5c7  test    eax, eax
0x18007e5c9  jnz     short $errRtn_94
0x18007e5cb  cmp     [rsp+290h+pstg], 0
0x18007e5d1  jnz     short loc_18007E5DA
0x18007e5d3  mov     eax, 8000FFFFh
0x18007e5d8  jmp     short loc_18007E631
0x18007e5da  cmp     esi, 1
0x18007e5dd  lea     rdx, [rsp+290h+clsid]; lpclsid
0x18007e5e2  cmovnz  di, r15w
0x18007e5e7  movzx   ecx, di; aClass
0x18007e5ea  call    ?CLSIDFromAtom@@YAHGPEAU_GUID@@@Z; CLSIDFromAtom(ushort,_GUID *)
0x18007e5ef  test    eax, eax
0x18007e5f1  jnz     short loc_18007E65B
0x18007e5f3  mov     ebx, 80040154h
0x18007e5f8  mov     hNative, [rsp+290h+pstg]
0x18007e5fd  test    hNative, hNative
0x18007e600  jz      short loc_18007E60E
0x18007e602  mov     rax, [hNative]
0x18007e605  mov     rax, [rax+10h]
0x18007e609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e60e  mov     hNative, [rsp+290h+plkbyt]
0x18007e613  test    hNative, hNative
0x18007e616  jz      short loc_18007E624
0x18007e618  mov     rax, [hNative]
0x18007e61b  mov     rax, [rax+10h]
0x18007e61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e624  mov     hNative, [rsp+290h+szUserType]; pv
0x18007e629  call    cs:__imp_CoTaskMemFree
0x18007e62f  mov     eax, ebx
0x18007e631  mov     hNative, [rbp+190h+var_40]
0x18007e638  xor     hNative, rsp; StackCookie
0x18007e63b  call    __security_check_cookie
0x18007e640  mov     rbx, [rsp+290h+arg_18]
0x18007e648  add     rsp, 260h
0x18007e64f  pop     r15
0x18007e651  pop     r14
0x18007e653  pop     r13
0x18007e655  pop     r12
0x18007e657  pop     rdi
0x18007e658  pop     rsi
0x18007e659  pop     rbp
0x18007e65a  retn
0x18007e65b  mov     hNative, [rsp+290h+pstg]; pStg
0x18007e660  lea     rdx, [rsp+290h+clsid]; rclsid
0x18007e665  call    cs:__imp_WriteClassStg
0x18007e66b  mov     ebx, eax
0x18007e66d  test    eax, eax
0x18007e66f  jnz     short $errRtn_94
0x18007e671  lea     r8, [rsp+290h+szUserType]; pszUserType
0x18007e676  lea     edx, [rax+1]; dwFormOfType
0x18007e679  lea     hNative, [rsp+290h+clsid]; clsid
0x18007e67e  call    OleRegGetUserType
0x18007e683  mov     ebx, eax
0x18007e685  test    eax, eax
0x18007e687  jnz     $errRtn_94
0x18007e68d  mov     r8d, 100h; nSize
0x18007e693  lea     rdx, [rsp+290h+szClassOld]; lpBuffer
0x18007e698  movzx   ecx, r15w; nAtom
0x18007e69c  call    cs:__imp_GlobalGetAtomNameW
0x18007e6a2  test    eax, eax
0x18007e6a4  jnz     short loc_18007E6B0
0x18007e6a6  mov     ebx, 8000FFFFh
0x18007e6ab  jmp     $errRtn_94
0x18007e6b0  lea     hNative, [rsp+290h+szClassOld]; lpszFormat
0x18007e6b5  call    cs:__imp_RegisterClipboardFormatW
0x18007e6bb  mov     r8, [rsp+290h+szUserType]; lpszUserType
0x18007e6c0  movzx   edx, ax; cf
0x18007e6c3  mov     hNative, [rsp+290h+pstg]; pstg
0x18007e6c8  call    WriteFmtUserTypeStg
0x18007e6cd  mov     ebx, eax
0x18007e6cf  test    eax, eax
0x18007e6d1  jnz     $errRtn_94
0x18007e6d7  mov     hNative, [rsp+290h+pstg]; pstg
0x18007e6dc  cmp     esi, 1
0x18007e6df  jnz     short loc_18007E6EF
0x18007e6e1  lea     r8d, [rax+4]; value
0x18007e6e5  or      edx, 0FFFFFFFFh; mask
0x18007e6e8  call    SetBitOleStg
0x18007e6ed  jmp     short loc_18007E6FC
0x18007e6ef  xor     cnvtyp, cnvtyp; ppstmOut
0x18007e6f2  xor     r8d, r8d; dwReserved
0x18007e6f5  xor     edx, edx; pOleObj
0x18007e6f7  call    WriteOleStg
0x18007e6fc  mov     ebx, eax
0x18007e6fe  test    eax, eax
0x18007e700  jnz     $errRtn_94
0x18007e706  mov     rdx, [rsp+290h+var_258]; hNative
0x18007e70b  mov     hNative, [rsp+290h+pstg]; pstgSave
0x18007e710  call    ?StSave10NativeData@@YAJPEAUIStorage@@PEAXH@Z; StSave10NativeData(IStorage *,void *,int)
0x18007e715  mov     ebx, eax
0x18007e717  test    eax, eax
0x18007e719  jnz     $errRtn_94
0x18007e71f  test    r14w, r14w
0x18007e723  jz      short loc_18007E745
0x18007e725  movzx   ecx, r14w; atom
0x18007e729  call    ?wAtomNameA@@YAPEADG@Z; wAtomNameA(ushort)
0x18007e72e  mov     hNative, [rsp+290h+pstg]; pstg
0x18007e733  mov     rdx, rax; szItemNameAnsi
0x18007e736  call    ?StSave10ItemName@@YAJPEAUIStorage@@PEBD@Z; StSave10ItemName(IStorage *,char const *)
0x18007e73b  mov     ebx, eax
0x18007e73d  test    eax, eax
0x18007e73f  jnz     $errRtn_94
0x18007e745  mov     rax, [rsp+290h+pstg]
0x18007e74a  mov     [r12], rax
0x18007e74e  mov     rax, [rsp+290h+plkbyt]
0x18007e753  mov     [r13+0], rax
0x18007e757  xor     eax, eax
0x18007e759  jmp     loc_18007E631
```
