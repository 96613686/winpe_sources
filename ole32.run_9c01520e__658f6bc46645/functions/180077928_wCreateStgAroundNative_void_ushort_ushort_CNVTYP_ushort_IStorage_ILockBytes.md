# wCreateStgAroundNative(void *,ushort,ushort,CNVTYP,ushort,IStorage * *,ILockBytes * *)

- ea: `0x180077928`
- end: `0x180077b8a`
- name: `?wCreateStgAroundNative@@YAJPEAXGGW4CNVTYP@@GPEAPEAUIStorage@@PEAPEAUILockBytes@@@Z`
- size: `610`
- prototype: `HRESULT __fastcall(void *hNative, unsigned __int16 aClassOld, unsigned __int16 aClassNew, CNVTYP cnvtyp, unsigned __int16 aItem, IStorage **ppstg, ILockBytes **pplkbyt)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180078d84`

## callees

- `0x18000ea30`
- `0x1800304d0`
- `0x180046460`
- `0x1800700e8`
- `0x180076f88`
- `0x180077928`
- `0x18007f2a4`
- `0x18007fdd0`
- `0x1800ab800`
- `0x1800ab880`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180077abd`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180077abd`
- `USER32!RegisterClipboardFormatW` at `0x180077adc`
- `USER32!RegisterClipboardFormatW` at `0x180077adc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077a39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077a39`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800779a4`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800779a4`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x180077a7c`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x180077a7c`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800779c8`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800779c8`

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
0x180077928  mov     [rsp-8+arg_18], rbx
0x18007792d  push    rbp
0x18007792e  push    rsi
0x18007792f  push    rdi
0x180077930  push    r12
0x180077932  push    r13
0x180077934  push    r14
0x180077936  push    r15
0x180077938  lea     rbp, [rsp-160h]
0x180077940  sub     rsp, 260h
0x180077947  mov     rax, cs:__security_cookie
0x18007794e  xor     rax, rsp
0x180077951  mov     [rbp+190h+var_40], rax
0x180077958  mov     r12, [rbp+190h+arg_28]
0x18007795f  xor     eax, eax
0x180077961  movzx   esi, [rbp+190h+arg_20]
0x180077968  movzx   edi, aClassNew
0x18007796c  mov     r13, [rbp+190h+arg_30]
0x180077973  lea     r8, [rsp+290h+plkbyt]; pplkbyt
0x180077978  movzx   r15d, aClassOld
0x18007797c  mov     [rsp+290h+var_258], hNative
0x180077981  xorps   xmm0, xmm0
0x180077984  mov     [rsp+290h+pstg], rax
0x180077989  lea     edx, [rax+1]; fDeleteOnRelease
0x18007798c  mov     [rsp+290h+plkbyt], rax
0x180077991  xor     ecx, ecx; hGlobal
0x180077993  mov     [rsp+290h+szUserType], rax
0x180077998  mov     r14d, cnvtyp
0x18007799b  mov     [r12], rax
0x18007799f  movups  xmmword ptr [rsp+290h+clsid.Data1], xmm0
0x1800779a4  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800779ab  nop     dword ptr [rax+rax+00h]
0x1800779b0  mov     ebx, eax
0x1800779b2  test    eax, eax
0x1800779b4  jnz     short $errRtn_61
0x1800779b6  mov     hNative, [rsp+290h+plkbyt]; plkbyt
0x1800779bb  lea     r9, [rsp+290h+pstg]; ppstgOpen
0x1800779c0  xor     r8d, r8d; reserved
0x1800779c3  mov     edx, 1012h; grfMode
0x1800779c8  call    cs:__imp_StgCreateDocfileOnILockBytes
0x1800779cf  nop     dword ptr [rax+rax+00h]
0x1800779d4  mov     ebx, eax
0x1800779d6  test    eax, eax
0x1800779d8  jnz     short $errRtn_61
0x1800779da  cmp     [rsp+290h+pstg], 0
0x1800779e0  jnz     short loc_1800779E9
0x1800779e2  mov     eax, 8000FFFFh
0x1800779e7  jmp     short loc_180077A47
0x1800779e9  cmp     r14d, 1
0x1800779ed  lea     rdx, [rsp+290h+clsid]; lpclsid
0x1800779f2  cmovnz  di, r15w
0x1800779f7  movzx   ecx, di; aClass
0x1800779fa  call    ?CLSIDFromAtom@@YAHGPEAU_GUID@@@Z; CLSIDFromAtom(ushort,_GUID *)
0x1800779ff  test    eax, eax
0x180077a01  jnz     short loc_180077A72
0x180077a03  mov     ebx, 80040154h
0x180077a08  mov     hNative, [rsp+290h+pstg]
0x180077a0d  test    hNative, hNative
0x180077a10  jz      short loc_180077A1E
0x180077a12  mov     rax, [hNative]
0x180077a15  mov     rax, [rax+10h]
0x180077a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a1e  mov     hNative, [rsp+290h+plkbyt]
0x180077a23  test    hNative, hNative
0x180077a26  jz      short loc_180077A34
0x180077a28  mov     rax, [hNative]
0x180077a2b  mov     rax, [rax+10h]
0x180077a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a34  mov     hNative, [rsp+290h+szUserType]; pv
0x180077a39  call    cs:__imp_CoTaskMemFree
0x180077a40  nop     dword ptr [rax+rax+00h]
0x180077a45  mov     eax, ebx
0x180077a47  mov     hNative, [rbp+190h+var_40]
0x180077a4e  xor     hNative, rsp; StackCookie
0x180077a51  call    __security_check_cookie
0x180077a56  mov     rbx, [rsp+290h+arg_18]
0x180077a5e  add     rsp, 260h
0x180077a65  pop     r15
0x180077a67  pop     r14
0x180077a69  pop     r13
0x180077a6b  pop     r12
0x180077a6d  pop     rdi
0x180077a6e  pop     rsi
0x180077a6f  pop     rbp
0x180077a70  retn
0x180077a72  mov     hNative, [rsp+290h+pstg]; pStg
0x180077a77  lea     rdx, [rsp+290h+clsid]; rclsid
0x180077a7c  call    cs:__imp_WriteClassStg
0x180077a83  nop     dword ptr [rax+rax+00h]
0x180077a88  mov     ebx, eax
0x180077a8a  test    eax, eax
0x180077a8c  jnz     $errRtn_61
0x180077a92  lea     r8, [rsp+290h+szUserType]; pszUserType
0x180077a97  lea     edx, [rax+1]; dwFormOfType
0x180077a9a  lea     hNative, [rsp+290h+clsid]; clsid
0x180077a9f  call    OleRegGetUserType
0x180077aa4  mov     ebx, eax
0x180077aa6  test    eax, eax
0x180077aa8  jnz     $errRtn_61
0x180077aae  mov     r8d, 100h; nSize
0x180077ab4  lea     rdx, [rsp+290h+szClassOld]; lpBuffer
0x180077ab9  movzx   ecx, r15w; nAtom
0x180077abd  call    cs:__imp_GlobalGetAtomNameW
0x180077ac4  nop     dword ptr [rax+rax+00h]
0x180077ac9  test    eax, eax
0x180077acb  jnz     short loc_180077AD7
0x180077acd  mov     ebx, 8000FFFFh
0x180077ad2  jmp     $errRtn_61
0x180077ad7  lea     hNative, [rsp+290h+szClassOld]; lpszFormat
0x180077adc  call    cs:__imp_RegisterClipboardFormatW
0x180077ae3  nop     dword ptr [rax+rax+00h]
0x180077ae8  mov     r8, [rsp+290h+szUserType]; lpszUserType
0x180077aed  movzx   edx, ax; cf
0x180077af0  mov     hNative, [rsp+290h+pstg]; pstg
0x180077af5  call    WriteFmtUserTypeStg
0x180077afa  mov     ebx, eax
0x180077afc  test    eax, eax
0x180077afe  jnz     $errRtn_61
0x180077b04  mov     hNative, [rsp+290h+pstg]; pstg
0x180077b09  cmp     r14d, 1
0x180077b0d  jnz     short loc_180077B1D
0x180077b0f  lea     r8d, [rax+4]; value
0x180077b13  or      edx, 0FFFFFFFFh; mask
0x180077b16  call    SetBitOleStg
0x180077b1b  jmp     short loc_180077B2A
0x180077b1d  xor     cnvtyp, cnvtyp; ppstmOut
0x180077b20  xor     r8d, r8d; dwReserved
0x180077b23  xor     edx, edx; pOleObj
0x180077b25  call    WriteOleStg
0x180077b2a  mov     ebx, eax
0x180077b2c  test    eax, eax
0x180077b2e  jnz     $errRtn_61
0x180077b34  mov     rdx, [rsp+290h+var_258]; hNative
0x180077b39  mov     hNative, [rsp+290h+pstg]; pstgSave
0x180077b3e  call    ?StSave10NativeData@@YAJPEAUIStorage@@PEAXH@Z; StSave10NativeData(IStorage *,void *,int)
0x180077b43  mov     ebx, eax
0x180077b45  test    eax, eax
0x180077b47  jnz     $errRtn_61
0x180077b4d  test    si, si
0x180077b50  jz      short loc_180077B71
0x180077b52  movzx   ecx, si; atom
0x180077b55  call    ?wAtomNameA@@YAPEADG@Z; wAtomNameA(ushort)
0x180077b5a  mov     hNative, [rsp+290h+pstg]; pstg
0x180077b5f  mov     rdx, rax; szItemNameAnsi
0x180077b62  call    ?StSave10ItemName@@YAJPEAUIStorage@@PEBD@Z; StSave10ItemName(IStorage *,char const *)
0x180077b67  mov     ebx, eax
0x180077b69  test    eax, eax
0x180077b6b  jnz     $errRtn_61
0x180077b71  mov     rax, [rsp+290h+pstg]
0x180077b76  mov     [r12], rax
0x180077b7a  mov     rax, [rsp+290h+plkbyt]
0x180077b7f  mov     [r13+0], rax
0x180077b83  xor     eax, eax
0x180077b85  jmp     loc_180077A47
```
