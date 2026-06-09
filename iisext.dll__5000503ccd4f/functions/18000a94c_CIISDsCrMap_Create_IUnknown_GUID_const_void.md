# CIISDsCrMap::Create(IUnknown *,_GUID const &,void * *)

- ea: `0x18000a94c`
- end: `0x18000ac3e`
- name: `?Create@CIISDsCrMap@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `754`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x18000de70`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003970`
- `0x180003a14`
- `0x180003fdc`
- `0x1800045e0`
- `0x1800049a0`
- `0x180004c2c`
- `0x18000a5b0`
- `0x18000a65c`
- `0x18000a94c`
- `0x18000c8d8`
- `0x18000dea0`
- `0x18000dee4`
- `0x18000df38`
- `0x18000e0d4`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000ab84`
- `OLEAUT32!__imp_SysFreeString` at `0x18000abc1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ab84`
- `OLEAUT32!__imp_SysFreeString` at `0x18000abc1`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000ab1c`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000ab1c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000ab8e`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000ab9f`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000abd0`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000abe6`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000ab8e`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000ab9f`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000abd0`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000abe6`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::Create(struct IUnknown *a1, const WCHAR *a2, void **a3)
{
  CIISDsCrMap *v5; // rbx
  LPWSTR *v6; // rdi
  unsigned __int16 *v7; // r15
  int TypeInfoEntry; // esi
  _QWORD *v9; // r14
  CIISDsCrMap *v10; // rax
  CIISDsCrMap *v11; // rax
  LPWSTR *v12; // rax
  LPWSTR v13; // rax
  __int64 v14; // r8
  OLECHAR *v15; // rcx
  int v17; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v18; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+44h] [rbp-2Ch] BYREF
  unsigned __int16 *v21[2]; // [rsp+48h] [rbp-28h] BYREF
  __int128 v22; // [rsp+58h] [rbp-18h]
  __int64 v23; // [rsp+68h] [rbp-8h]
  LPCWSTR pStr; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+58h] BYREF

  pStr = a2;
  CCredentials::Initialize((CCredentials *)&v18, 0, 0, 0);
  v5 = 0;
  pStr = 0;
  v6 = 0;
  v23 = 0;
  v7 = 0;
  v25 = 0;
  TypeInfoEntry = -2147024882;
  *(_OWORD *)v21 = 0;
  v22 = 0;
  v9 = operator new(0x38u);
  if ( v9 )
  {
    v9[2] = 0;
    *v9 = &CAggregateeDispMgr::`vftable';
    v9[3] = 0;
    *((_DWORD *)v9 + 2) = 0;
    v9[4] = 0;
    v9[5] = 0;
    v9[6] = 0;
    v10 = (CIISDsCrMap *)operator new(0x90u);
    if ( !v10
      || (v11 = CIISDsCrMap::CIISDsCrMap(v10), (v5 = v11) == 0)
      || (TypeInfoEntry = CAggregateeDispMgr::LoadTypeInfoEntry(
                            (CAggregateeDispMgr *)v9,
                            &LIBID_IISExt,
                            &IID_IISDsCrMap,
                            v11,
                            v17),
          TypeInfoEntry < 0)
      || (TypeInfoEntry = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
                            a1,
                            &IID_IADs,
                            &v25),
          TypeInfoEntry < 0) )
    {
      CAggregateeDispMgr::~CAggregateeDispMgr((CAggregateeDispMgr *)v9);
      operator delete(v9);
      if ( v5 )
      {
        CIISDsCrMap::~CIISDsCrMap(v5);
        operator delete(v5);
      }
      v5 = 0;
      goto LABEL_25;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    *((_QWORD *)v5 + 13) = v25;
    *((_QWORD *)v5 + 6) = a1;
    CCredentials::operator=((CIISDsCrMap *)((char *)v5 + 80), (struct CCredentials *)&v18);
    *((_QWORD *)v5 + 14) = v9;
    TypeInfoEntry = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR *))(**((_QWORD **)v5 + 13) + 80LL))(
                      *((_QWORD *)v5 + 13),
                      &pStr);
    if ( TypeInfoEntry >= 0 )
    {
      v12 = (LPWSTR *)operator new(0x20u);
      v6 = v12;
      if ( v12 )
      {
        *v12 = 0;
        v12[1] = 0;
        v12[2] = 0;
        v12[3] = 0;
        TypeInfoEntry = CLexer::Initialize((CLexer *)v12, (unsigned __int16 *)pStr);
        if ( TypeInfoEntry < 0 )
          goto LABEL_25;
        TypeInfoEntry = ADsObject((struct CLexer *)v6, (struct _objectinfo *)v21);
        if ( TypeInfoEntry < 0 )
          goto LABEL_25;
        v13 = AllocADsStr(pStr);
        v7 = v13;
        if ( v13 )
        {
          v14 = -1;
          do
            ++v14;
          while ( v13[v14] );
          *v13 = 0;
          TypeInfoEntry = BuildIISPathFromADsPath((struct _objectinfo *)v21, v13, v14 + 1);
          if ( TypeInfoEntry >= 0 )
          {
            TypeInfoEntry = CIISDsCrMap::Init(v5, v21[1], v7);
            if ( TypeInfoEntry >= 0 )
            {
              v15 = (OLECHAR *)pStr;
              *a3 = (void *)(((unsigned __int64)v5 + 32) & -(__int64)(v5 != 0));
              if ( v15 )
                SysFreeString(v15);
              FreeADsStr(v6[1]);
              operator delete(v6);
              FreeADsStr(v7);
              FreeObjectInfo((struct _objectinfo *)v21);
              goto LABEL_33;
            }
          }
          goto LABEL_25;
        }
      }
      else
      {
        v6 = 0;
      }
      TypeInfoEntry = -2147024882;
    }
  }
LABEL_25:
  if ( pStr )
    SysFreeString((BSTR)pStr);
  if ( v6 )
  {
    FreeADsStr(v6[1]);
    operator delete(v6);
  }
  if ( v7 )
    FreeADsStr(v7);
  FreeObjectInfo((struct _objectinfo *)v21);
  *a3 = 0;
  if ( v5 )
  {
    CIISDsCrMap::~CIISDsCrMap(v5);
    operator delete(v5);
  }
LABEL_33:
  CCredentials::FreeUserName(&v18);
  CCredentials::FreePassword(&v19, &v20);
  return (unsigned int)TypeInfoEntry;
}

```

## disassembly

```asm
0x18000a94c  mov     [rsp-38h+arg_0], rbx
0x18000a951  mov     [rsp-38h+pStr], rdx
0x18000a956  push    rbp
0x18000a957  push    rsi
0x18000a958  push    rdi
0x18000a959  push    r12
0x18000a95b  push    r13
0x18000a95d  push    r14
0x18000a95f  push    r15
0x18000a961  mov     rbp, rsp
0x18000a964  sub     rsp, 70h
0x18000a968  mov     r13, r8
0x18000a96b  mov     r12, rcx
0x18000a96e  xor     r8d, r8d; unsigned __int16 *
0x18000a971  lea     rcx, [rbp+var_40]; this
0x18000a975  xor     r9d, r9d; unsigned int
0x18000a978  xor     edx, edx; pStr
0x18000a97a  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x18000a97f  xor     ebx, ebx
0x18000a981  xorps   xmm0, xmm0
0x18000a984  xor     eax, eax
0x18000a986  mov     [rbp+pStr], rbx
0x18000a98a  mov     edi, ebx
0x18000a98c  mov     [rbp+var_8], rax
0x18000a990  mov     r15d, ebx
0x18000a993  mov     [rbp+arg_18], rbx
0x18000a997  lea     ecx, [rbx+38h]; Size
0x18000a99a  mov     esi, 8007000Eh
0x18000a99f  movups  xmmword ptr [rbp+var_28], xmm0
0x18000a9a3  movups  [rbp+var_18], xmm0
0x18000a9a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a9ac  mov     r14, rax
0x18000a9af  test    rax, rax
0x18000a9b2  jz      loc_18000AA9E
0x18000a9b8  lea     rax, ??_7CAggregateeDispMgr@@6B@; const CAggregateeDispMgr::`vftable'
0x18000a9bf  mov     [r14+10h], rbx
0x18000a9c3  mov     ecx, 90h; Size
0x18000a9c8  mov     [r14], rax
0x18000a9cb  mov     [r14+18h], rbx
0x18000a9cf  mov     [r14+8], ebx
0x18000a9d3  mov     [r14+20h], rbx
0x18000a9d7  mov     [r14+28h], rbx
0x18000a9db  mov     [r14+30h], rbx
0x18000a9df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a9e4  test    rax, rax
0x18000a9e7  jz      loc_18000AA6E
0x18000a9ed  mov     rcx, rax; this
0x18000a9f0  call    ??0CIISDsCrMap@@QEAA@XZ; CIISDsCrMap::CIISDsCrMap(void)
0x18000a9f5  mov     rbx, rax
0x18000a9f8  test    rax, rax
0x18000a9fb  jz      short loc_18000AA6E
0x18000a9fd  mov     r9, rax; void *
0x18000aa00  lea     r8, IID_IISDsCrMap; struct _GUID *
0x18000aa07  lea     rdx, LIBID_IISExt; struct _GUID *
0x18000aa0e  mov     rcx, r14; this
0x18000aa11  call    ?LoadTypeInfoEntry@CAggregateeDispMgr@@QEAAJAEBU_GUID@@0PEAXJ@Z; CAggregateeDispMgr::LoadTypeInfoEntry(_GUID const &,_GUID const &,void *,long)
0x18000aa16  mov     esi, eax
0x18000aa18  test    eax, eax
0x18000aa1a  js      short loc_18000AA6E
0x18000aa1c  mov     rax, [r12]
0x18000aa20  lea     r8, [rbp+arg_18]
0x18000aa24  lea     rdx, IID_IADs
0x18000aa2b  mov     rcx, r12
0x18000aa2e  mov     rax, [rax]
0x18000aa31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa36  mov     esi, eax
0x18000aa38  test    eax, eax
0x18000aa3a  js      short loc_18000AA6E
0x18000aa3c  mov     rcx, [rbp+arg_18]
0x18000aa40  mov     rax, [rcx]
0x18000aa43  mov     rax, [rax+10h]
0x18000aa47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa4c  mov     rax, [rbp+arg_18]
0x18000aa50  lea     rcx, [rbx+50h]; this
0x18000aa54  lea     rdx, [rbp+var_40]; struct CCredentials *
0x18000aa58  mov     [rbx+68h], rax
0x18000aa5c  mov     [rbx+30h], r12
0x18000aa60  call    ??4CCredentials@@QEAAXAEBV0@@Z; CCredentials::operator=(CCredentials const &)
0x18000aa65  mov     [rbx+70h], r14
0x18000aa69  xor     r14d, r14d
0x18000aa6c  jmp     short loc_18000AAA9
0x18000aa6e  mov     rcx, r14; this
0x18000aa71  xor     r12d, r12d
0x18000aa74  call    ??1CAggregateeDispMgr@@QEAA@XZ; CAggregateeDispMgr::~CAggregateeDispMgr(void)
0x18000aa79  mov     rcx, r14; Block
0x18000aa7c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aa81  xor     r14d, r14d
0x18000aa84  test    rbx, rbx
0x18000aa87  jz      short loc_18000AA99
0x18000aa89  mov     rcx, rbx; this
0x18000aa8c  call    ??1CIISDsCrMap@@QEAA@XZ; CIISDsCrMap::~CIISDsCrMap(void)
0x18000aa91  mov     rcx, rbx; Block
0x18000aa94  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aa99  mov     rbx, r12
0x18000aa9c  jmp     short loc_18000AAA1
0x18000aa9e  xor     r14d, r14d
0x18000aaa1  test    esi, esi
0x18000aaa3  js      loc_18000ABB8
0x18000aaa9  mov     rcx, [rbx+68h]
0x18000aaad  lea     rdx, [rbp+pStr]
0x18000aab1  mov     rax, [rcx]
0x18000aab4  mov     rax, [rax+50h]
0x18000aab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aabd  mov     esi, eax
0x18000aabf  test    eax, eax
0x18000aac1  js      loc_18000ABB8
0x18000aac7  mov     ecx, 20h ; ' '; Size
0x18000aacc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aad1  mov     rdi, rax
0x18000aad4  test    rax, rax
0x18000aad7  jz      loc_18000ABB0
0x18000aadd  mov     [rax], r14
0x18000aae0  mov     rcx, rax; this
0x18000aae3  mov     [rax+8], r14
0x18000aae7  mov     [rax+10h], r15
0x18000aaeb  mov     [rax+18h], r15
0x18000aaef  mov     rdx, [rbp+pStr]; unsigned __int16 *
0x18000aaf3  call    ?Initialize@CLexer@@QEAAJPEAG@Z; CLexer::Initialize(ushort *)
0x18000aaf8  mov     esi, eax
0x18000aafa  test    eax, eax
0x18000aafc  js      loc_18000ABB8
0x18000ab02  lea     rdx, [rbp+var_28]; struct _objectinfo *
0x18000ab06  mov     rcx, rdi; this
0x18000ab09  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x18000ab0e  mov     esi, eax
0x18000ab10  test    eax, eax
0x18000ab12  js      loc_18000ABB8
0x18000ab18  mov     rcx, [rbp+pStr]; pStr
0x18000ab1c  call    cs:__imp_AllocADsStr
0x18000ab22  mov     r15, rax
0x18000ab25  test    rax, rax
0x18000ab28  jz      loc_18000ABB3
0x18000ab2e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ab32  inc     r8
0x18000ab35  cmp     [rax+r8*2], r14w
0x18000ab3a  jnz     short loc_18000AB32
0x18000ab3c  inc     r8; unsigned __int64
0x18000ab3f  mov     [rax], r14w
0x18000ab43  mov     rdx, r15; unsigned __int16 *
0x18000ab46  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x18000ab4a  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x18000ab4f  mov     esi, eax
0x18000ab51  test    eax, eax
0x18000ab53  js      short loc_18000ABB8
0x18000ab55  mov     rdx, [rbp+var_28+8]; unsigned __int16 *
0x18000ab59  mov     r8, r15; unsigned __int16 *
0x18000ab5c  mov     rcx, rbx; this
0x18000ab5f  call    ?Init@CIISDsCrMap@@QEAAJPEAG0@Z; CIISDsCrMap::Init(ushort *,ushort *)
0x18000ab64  mov     esi, eax
0x18000ab66  test    eax, eax
0x18000ab68  js      short loc_18000ABB8
0x18000ab6a  lea     rcx, [rbx+20h]
0x18000ab6e  neg     rbx
0x18000ab71  sbb     rax, rax
0x18000ab74  and     rax, rcx
0x18000ab77  mov     rcx, [rbp+pStr]; bstrString
0x18000ab7b  mov     [r13+0], rax
0x18000ab7f  test    rcx, rcx
0x18000ab82  jz      short loc_18000AB8A
0x18000ab84  call    cs:__imp_SysFreeString
0x18000ab8a  mov     rcx, [rdi+8]; pStr
0x18000ab8e  call    cs:__imp_FreeADsStr
0x18000ab94  mov     rcx, rdi; Block
0x18000ab97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ab9c  mov     rcx, r15; pStr
0x18000ab9f  call    cs:__imp_FreeADsStr
0x18000aba5  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x18000aba9  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x18000abae  jmp     short loc_18000AC0E
0x18000abb0  mov     rdi, r14
0x18000abb3  mov     esi, 8007000Eh
0x18000abb8  mov     rcx, [rbp+pStr]; bstrString
0x18000abbc  test    rcx, rcx
0x18000abbf  jz      short loc_18000ABC7
0x18000abc1  call    cs:__imp_SysFreeString
0x18000abc7  test    rdi, rdi
0x18000abca  jz      short loc_18000ABDE
0x18000abcc  mov     rcx, [rdi+8]; pStr
0x18000abd0  call    cs:__imp_FreeADsStr
0x18000abd6  mov     rcx, rdi; Block
0x18000abd9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000abde  test    r15, r15
0x18000abe1  jz      short loc_18000ABEC
0x18000abe3  mov     rcx, r15; pStr
0x18000abe6  call    cs:__imp_FreeADsStr
0x18000abec  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x18000abf0  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x18000abf5  mov     [r13+0], r14
0x18000abf9  test    rbx, rbx
0x18000abfc  jz      short loc_18000AC0E
0x18000abfe  mov     rcx, rbx; this
0x18000ac01  call    ??1CIISDsCrMap@@QEAA@XZ; CIISDsCrMap::~CIISDsCrMap(void)
0x18000ac06  mov     rcx, rbx; Block
0x18000ac09  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ac0e  lea     rcx, [rbp+var_40]; unsigned __int16 **
0x18000ac12  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x18000ac17  lea     rdx, [rbp+var_2C]; unsigned int *
0x18000ac1b  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x18000ac1f  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x18000ac24  mov     rbx, [rsp+70h+arg_0]
0x18000ac2c  mov     eax, esi
0x18000ac2e  add     rsp, 70h
0x18000ac32  pop     r15
0x18000ac34  pop     r14
0x18000ac36  pop     r13
0x18000ac38  pop     r12
0x18000ac3a  pop     rdi
0x18000ac3b  pop     rsi
0x18000ac3c  pop     rbp
0x18000ac3d  retn
```
