# CSessionBaseRW::RemoveNamespaceRecordsByFileRecordRef(ulong,int,long)

- ea: `0x180010b18`
- end: `0x180010d41`
- name: `?RemoveNamespaceRecordsByFileRecordRef@CSessionBaseRW@@IEAAJKHJ@Z`
- size: `553`
- prototype: `__int64 __fastcall(CSessionBaseRW *__hidden this, unsigned int, int, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180010844`
- `0x18001cb74`

## callees

- `0x1800025b0`
- `0x1800031b0`
- `0x180007818`
- `0x180007a1c`
- `0x18000835c`
- `0x18000935c`
- `0x1800093a8`
- `0x1800094d0`
- `0x180009528`
- `0x18000960c`
- `0x180010914`
- `0x180010b18`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::RemoveNamespaceRecordsByFileRecordRef(
        CSessionBaseRW *this,
        unsigned int a2,
        int a3,
        int a4)
{
  CNamespaceRecord *v8; // rax
  __int64 *v9; // rbx
  int v10; // edi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // eax
  __int64 v16; // [rsp+30h] [rbp-58h] BYREF
  __int64 *v17; // [rsp+38h] [rbp-50h] BYREF
  CNamespaceRecord **v18; // [rsp+40h] [rbp-48h] BYREF

  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v17);
  v16 = 0;
  v8 = (CNamespaceRecord *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
    v8 = CNamespaceRecord::CNamespaceRecord(v8, (__int64 *)this + 2, (__int64)this + 24);
  SmartPtr<CNamespaceRecord>::operator=(&v17, v8);
  v9 = v17;
  if ( v17 && *v17 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 2) + 240LL))(
            *((_QWORD *)this + 2),
            a2,
            &v16);
    if ( v10 == -2147023728 )
    {
LABEL_6:
      v10 = 0;
    }
    else if ( v10 >= 0 )
    {
      while ( 1 )
      {
        v10 = CNamespaceRecord::LoadCurrentFromEnum(*v9, &v16);
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              54,
              &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
              (unsigned int)v10);
          goto LABEL_29;
        }
        v18 = (CNamespaceRecord **)v9;
        ++*((_DWORD *)v9 + 2);
        v10 = CSessionBaseRW::RemoveNamespaceRecord(this, &v18, a3, a4);
        if ( v10 < 0 )
          break;
        v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
        v10 = v14;
        if ( v14 == -2147023728 )
          goto LABEL_6;
        if ( v14 < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v12 = 56;
            goto LABEL_11;
          }
          goto LABEL_29;
        }
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 55;
        v13 = *(unsigned int *)(*v9 + 16);
        goto LABEL_12;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 53;
LABEL_11:
        v13 = a2;
LABEL_12:
        WPP_SF_dd(v11[2], v12, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v13, v10);
      }
    }
  }
  else
  {
    v10 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
        "namespaceRecord");
  }
LABEL_29:
  ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&v16);
  SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v17);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180010b18  push    rbx
0x180010b1a  push    rbp
0x180010b1b  push    rsi
0x180010b1c  push    rdi
0x180010b1d  push    r14
0x180010b1f  push    r15
0x180010b21  sub     rsp, 58h
0x180010b25  mov     r14d, r9d
0x180010b28  mov     r15d, r8d
0x180010b2b  mov     esi, edx
0x180010b2d  mov     rbp, rcx
0x180010b30  lea     rcx, [rsp+88h+var_50]
0x180010b35  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x180010b3a  mov     [rsp+88h+var_58], 0
0x180010b43  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010b4a  mov     ecx, 58h ; 'X'; unsigned __int64
0x180010b4f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010b54  test    rax, rax
0x180010b57  jz      short loc_180010B69
0x180010b59  lea     r8, [rbp+18h]
0x180010b5d  lea     rdx, [rbp+10h]
0x180010b61  mov     rcx, rax; this
0x180010b64  call    ??0CNamespaceRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z; CNamespaceRecord::CNamespaceRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)
0x180010b69  mov     rdx, rax
0x180010b6c  lea     rcx, [rsp+88h+var_50]
0x180010b71  call    ??4?$SmartPtr@VCNamespaceRecord@@@@QEAAAEAV0@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::operator=(CNamespaceRecord *)
0x180010b76  mov     rbx, [rsp+88h+var_50]
0x180010b7b  test    rbx, rbx
0x180010b7e  jz      loc_180010CE4
0x180010b84  cmp     qword ptr [rbx], 0
0x180010b88  jz      loc_180010CE4
0x180010b8e  mov     rcx, [rbp+10h]
0x180010b92  mov     rax, [rcx]
0x180010b95  lea     r8, [rsp+88h+var_58]
0x180010b9a  mov     edx, esi
0x180010b9c  mov     rax, [rax+0F0h]
0x180010ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ba8  mov     edi, eax
0x180010baa  cmp     eax, 80070490h
0x180010baf  jnz     short loc_180010BB8
0x180010bb1  xor     edi, edi
0x180010bb3  jmp     loc_180010D1E
0x180010bb8  test    edi, edi
0x180010bba  jns     short loc_180010BFE
0x180010bbc  lea     rax, WPP_GLOBAL_Control
0x180010bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bca  cmp     rcx, rax
0x180010bcd  jz      loc_180010D1E
0x180010bd3  test    byte ptr [rcx+1Ch], 1
0x180010bd7  jz      loc_180010D1E
0x180010bdd  mov     edx, 35h ; '5'
0x180010be2  mov     r9d, esi
0x180010be5  mov     [rsp+88h+var_68], edi
0x180010be9  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x180010bf0  mov     rcx, [rcx+10h]
0x180010bf4  call    WPP_SF_dd
0x180010bf9  jmp     loc_180010D1E
0x180010bfe  lea     rdx, [rsp+88h+var_58]
0x180010c03  mov     rcx, [rbx]
0x180010c06  call    ?LoadCurrentFromEnum@CNamespaceRecord@@QEAAJAEBV?$CComPtr@UIFhNamespaceRecordEnum@@@ATL@@@Z; CNamespaceRecord::LoadCurrentFromEnum(ATL::CComPtr<IFhNamespaceRecordEnum> const &)
0x180010c0b  mov     edi, eax
0x180010c0d  test    eax, eax
0x180010c0f  js      loc_180010CB1
0x180010c15  mov     [rsp+88h+var_48], rbx
0x180010c1a  inc     dword ptr [rbx+8]
0x180010c1d  mov     r9d, r14d
0x180010c20  mov     r8d, r15d
0x180010c23  lea     rdx, [rsp+88h+var_48]
0x180010c28  mov     rcx, rbp; this
0x180010c2b  call    ?RemoveNamespaceRecord@CSessionBaseRW@@IEAAJV?$SmartPtr@VCNamespaceRecord@@@@HJ@Z; CSessionBaseRW::RemoveNamespaceRecord(SmartPtr<CNamespaceRecord>,int,long)
0x180010c30  mov     edi, eax
0x180010c32  test    eax, eax
0x180010c34  js      short loc_180010C83
0x180010c36  mov     rcx, [rsp+88h+var_58]
0x180010c3b  mov     rax, [rcx]
0x180010c3e  mov     rax, [rax+20h]
0x180010c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c47  mov     edi, eax
0x180010c49  cmp     eax, 80070490h
0x180010c4e  jz      loc_180010BB1
0x180010c54  test    eax, eax
0x180010c56  jns     short loc_180010BFE
0x180010c58  lea     rax, WPP_GLOBAL_Control
0x180010c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c66  cmp     rcx, rax
0x180010c69  jz      loc_180010D1E
0x180010c6f  test    byte ptr [rcx+1Ch], 1
0x180010c73  jz      loc_180010D1E
0x180010c79  mov     edx, 38h ; '8'
0x180010c7e  jmp     loc_180010BE2
0x180010c83  lea     rax, WPP_GLOBAL_Control
0x180010c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c91  cmp     rcx, rax
0x180010c94  jz      loc_180010D1E
0x180010c9a  test    byte ptr [rcx+1Ch], 1
0x180010c9e  jz      short loc_180010D1E
0x180010ca0  mov     r9, [rbx]
0x180010ca3  mov     edx, 37h ; '7'
0x180010ca8  mov     r9d, [r9+10h]
0x180010cac  jmp     loc_180010BE5
0x180010cb1  lea     rax, WPP_GLOBAL_Control
0x180010cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cbf  cmp     rcx, rax
0x180010cc2  jz      short loc_180010D1E
0x180010cc4  test    byte ptr [rcx+1Ch], 1
0x180010cc8  jz      short loc_180010D1E
0x180010cca  mov     edx, 36h ; '6'
0x180010ccf  mov     r9d, edi
0x180010cd2  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x180010cd9  mov     rcx, [rcx+10h]
0x180010cdd  call    WPP_SF_d
0x180010ce2  jmp     short loc_180010D1E
0x180010ce4  mov     edi, 8007000Eh
0x180010ce9  lea     rax, WPP_GLOBAL_Control
0x180010cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cf7  cmp     rcx, rax
0x180010cfa  jz      short loc_180010D1E
0x180010cfc  test    byte ptr [rcx+1Ch], 1
0x180010d00  jz      short loc_180010D1E
0x180010d02  mov     edx, 34h ; '4'
0x180010d07  lea     r9, aNamespacerecor; "namespaceRecord"
0x180010d0e  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x180010d15  mov     rcx, [rcx+10h]
0x180010d19  call    WPP_SF_s
0x180010d1e  lea     rcx, [rsp+88h+var_58]
0x180010d23  call    ??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)
0x180010d28  lea     rcx, [rsp+88h+var_50]
0x180010d2d  call    ??1?$SmartPtr@VCNamespaceRecord@@@@QEAA@XZ; SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(void)
0x180010d32  mov     eax, edi
0x180010d34  add     rsp, 58h
0x180010d38  pop     r15
0x180010d3a  pop     r14
0x180010d3c  pop     rdi
0x180010d3d  pop     rsi
0x180010d3e  pop     rbp
0x180010d3f  pop     rbx
0x180010d40  retn
```
