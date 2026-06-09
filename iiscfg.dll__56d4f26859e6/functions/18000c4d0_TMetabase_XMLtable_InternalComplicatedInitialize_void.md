# TMetabase_XMLtable::InternalComplicatedInitialize(void)

- ea: `0x18000c4d0`
- end: `0x18000c83e`
- name: `?InternalComplicatedInitialize@TMetabase_XMLtable@@AEAAJXZ`
- size: `878`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c0b0`

## callees

- `0x18000bbfc`
- `0x18000bdf4`
- `0x18000be58`
- `0x18000c4d0`
- `0x18000cad8`
- `0x18000cbcc`
- `0x18000e128`
- `0x18002e0ca`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000c5c5`
- `ole32!CoTaskMemAlloc` at `0x18000c5c5`
- `IisRTL!PuDbgPrint` at `0x18000c731`
- `IisRTL!PuDbgPrint` at `0x18000c731`
- `ATL!__imp_AtlComQIPtrAssign` at `0x18000c57d`
- `ATL!__imp_AtlComQIPtrAssign` at `0x18000c57d`

## string_xrefs

- `0x18000c72a`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000c718`: `TMetabase_XMLtable::InternalComplicatedInitialize`

## pseudocode

```c
int __fastcall TMetabase_XMLtable::InternalComplicatedInitialize(TMetabase_XMLtable *this)
{
  char *v1; // rdi
  int result; // eax
  __int64 v4; // rcx
  LPVOID v5; // rax
  __int64 i; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int j; // edi
  int v10; // eax
  int v11; // esi
  int *v12; // rax
  __int64 v13; // rdx
  int v14; // ecx
  int *v15; // rax
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  _BYTE *v21; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  int v24; // [rsp+5Ch] [rbp-A4h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  const wchar_t *v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  int v28; // [rsp+74h] [rbp-8Ch]
  __int64 v29; // [rsp+78h] [rbp-88h]
  _BYTE v30[24]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h]
  _DWORD *v32; // [rsp+A0h] [rbp-60h]
  int *v33; // [rsp+A8h] [rbp-58h]
  int *v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+108h] [rbp+8h]
  unsigned int v36; // [rsp+140h] [rbp+40h] BYREF

  v1 = (char *)this + 1688;
  result = CCfgArray<TMetabase_XMLtable::TLocation>::SetSize((char *)this + 1688, 128);
  if ( result >= 0 )
  {
    result = CCfgArray<TMetabase_XMLtable::TLocation>::SetSize(v1, 0);
    if ( result >= 0 )
    {
      TGrowableBuffer::Grow((TMetabase_XMLtable *)((char *)this + 1392), 0x100u);
      TGrowableBuffer::Grow((TMetabase_XMLtable *)((char *)this + 1440), 0x100u);
      TGrowableBuffer::Grow((TMetabase_XMLtable *)((char *)this + 1456), 0x100u);
      if ( *((_QWORD *)this + 222) )
        goto LABEL_10;
      AtlComQIPtrAssign((char *)this + 1808, *((_QWORD *)this + 214), &IID_IMetabaseSchemaCompiler);
      v4 = *((_QWORD *)this + 226);
      if ( !v4 )
        return -2147467259;
      v36 = 0;
      result = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v4 + 32LL))(v4, 0, &v36);
      if ( result >= 0 )
      {
        v5 = CoTaskMemAlloc(saturated_mul(v36, 2u));
        *((_QWORD *)this + 222) = v5;
        if ( !v5 )
          return -2147024882;
        result = (*(__int64 (__fastcall **)(_QWORD, LPVOID, unsigned int *))(**((_QWORD **)this + 226) + 32LL))(
                   *((_QWORD *)this + 226),
                   v5,
                   &v36);
        if ( result >= 0 )
        {
LABEL_10:
          for ( i = 0; i != 9; ++i )
            TGrowableBuffer::Grow((TMetabase_XMLtable *)((char *)this + 16 * i + 1392), 4u);
          result = TMetabase_XMLtable::ObtainPertinentTableMetaInfo(this);
          if ( result >= 0 )
          {
            *((_DWORD *)this + 414) |= **((_DWORD **)this + 236);
            result = TMetabase_XMLtable::GetMetaTable(this, v7, v8, (char *)this + 2272);
            if ( result >= 0 )
            {
              memset_0(v30, 0, 0x90u);
              for ( j = 0; ; ++j )
              {
                v21 = v30;
                v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 284) + 32LL))(
                        *((_QWORD *)this + 284),
                        j,
                        18);
                v11 = v10;
                if ( v10 == -2145318890 )
                  break;
                if ( v10 < 0 )
                {
                  if ( (g_dwDebugFlags & 3) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
                      804,
                      "TMetabase_XMLtable::InternalComplicatedInitialize",
                      "GetColumnValues FAILED with something other than E_ST_NOMOREROWS");
                  return v11;
                }
                v12 = v33;
                v13 = 3LL * j;
                *((_DWORD *)this + v13 + 166) = *v32;
                v14 = *v12;
                v15 = v34;
                *((_DWORD *)this + v13 + 167) = v14;
                v16 = *v15;
                v17 = v35;
                *((_DWORD *)this + 3 * j + 168) = v16;
                v18 = v31;
                *((_QWORD *)this + j + 142) = v17;
                v19 = -1;
                do
                  ++v19;
                while ( *(_WORD *)(v18 + 2 * v19) );
                *((_DWORD *)this + j + 302) = v19;
              }
              if ( j == 9 )
              {
                result = TMetabase_XMLtable::ObtainPertinentTagMetaInfo(this);
                if ( result >= 0 )
                {
                  result = TPublicRowName::Init(
                             (TMetabase_XMLtable *)((char *)this + 1536),
                             (struct tTAGMETARow *)(*((_QWORD *)this + 199) + 48LL * *((unsigned int *)this + 345)),
                             *((_DWORD *)this + 346));
                  if ( result >= 0 )
                  {
                    v20 = *((_QWORD *)this + 214);
                    v22 = *((_QWORD *)this + 222);
                    v23 = 2;
                    v26 = L"ByName";
                    v24 = -268435455;
                    v25 = 130;
                    v27 = 2;
                    v28 = -268435452;
                    v29 = 130;
                    LODWORD(v21) = 3;
                    return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, unsigned int *, _BYTE *, _DWORD, char *))(*(_QWORD *)v20 + 24LL))(
                             v20,
                             L"META",
                             L"COLUMNMETA",
                             &v22,
                             &TMetabase_XMLtable::m_kTwo,
                             v21,
                             0,
                             (char *)this + 2040);
                  }
                }
              }
              else
              {
                return -2145319648;
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c4d0  mov     [rsp-8+arg_8], rbx
0x18000c4d5  mov     [rsp-8+arg_10], rsi
0x18000c4da  push    rbp
0x18000c4db  push    rdi
0x18000c4dc  push    r13
0x18000c4de  push    r14
0x18000c4e0  push    r15
0x18000c4e2  lea     rbp, [rsp-10h]
0x18000c4e7  sub     rsp, 110h
0x18000c4ee  lea     rdi, [rcx+698h]
0x18000c4f5  mov     rbx, rcx
0x18000c4f8  mov     rcx, rdi
0x18000c4fb  mov     edx, 80h
0x18000c500  call    ?SetSize@?$CCfgArray@VTLocation@TMetabase_XMLtable@@@@QEAAJK@Z; CCfgArray<TMetabase_XMLtable::TLocation>::SetSize(ulong)
0x18000c505  xor     r15d, r15d
0x18000c508  test    eax, eax
0x18000c50a  js      loc_18000C822
0x18000c510  xor     edx, edx
0x18000c512  mov     rcx, rdi
0x18000c515  call    ?SetSize@?$CCfgArray@VTLocation@TMetabase_XMLtable@@@@QEAAJK@Z; CCfgArray<TMetabase_XMLtable::TLocation>::SetSize(ulong)
0x18000c51a  test    eax, eax
0x18000c51c  js      loc_18000C822
0x18000c522  lea     rsi, [rbx+570h]
0x18000c529  mov     edi, 100h
0x18000c52e  mov     edx, edi; unsigned __int64
0x18000c530  mov     rcx, rsi; this
0x18000c533  call    ?Grow@TGrowableBuffer@@QEAAX_K@Z; TGrowableBuffer::Grow(unsigned __int64)
0x18000c538  lea     rcx, [rbx+5A0h]; this
0x18000c53f  mov     edx, edi; unsigned __int64
0x18000c541  call    ?Grow@TGrowableBuffer@@QEAAX_K@Z; TGrowableBuffer::Grow(unsigned __int64)
0x18000c546  lea     rcx, [rbx+5B0h]; this
0x18000c54d  mov     edx, edi; unsigned __int64
0x18000c54f  call    ?Grow@TGrowableBuffer@@QEAAX_K@Z; TGrowableBuffer::Grow(unsigned __int64)
0x18000c554  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000c558  cmp     [rbx+6F0h], r15
0x18000c55f  jnz     loc_18000C5FF
0x18000c565  mov     rdx, [rbx+6B0h]
0x18000c56c  lea     rdi, [rbx+710h]
0x18000c573  mov     rcx, rdi
0x18000c576  lea     r8, IID_IMetabaseSchemaCompiler
0x18000c57d  call    cs:__imp_AtlComQIPtrAssign
0x18000c583  mov     rcx, [rdi]
0x18000c586  test    rcx, rcx
0x18000c589  jnz     short loc_18000C595
0x18000c58b  mov     eax, 80004005h
0x18000c590  jmp     loc_18000C822
0x18000c595  mov     [rbp+30h+arg_0], r15d
0x18000c599  lea     r8, [rbp+30h+arg_0]
0x18000c59d  mov     rax, [rcx]
0x18000c5a0  xor     edx, edx
0x18000c5a2  mov     rax, [rax+20h]
0x18000c5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ab  test    eax, eax
0x18000c5ad  js      loc_18000C822
0x18000c5b3  mov     ecx, [rbp+30h+arg_0]
0x18000c5b6  mov     eax, 2
0x18000c5bb  mul     rcx
0x18000c5be  cmovb   rax, r13
0x18000c5c2  mov     rcx, rax; cb
0x18000c5c5  call    cs:__imp_CoTaskMemAlloc
0x18000c5cb  mov     [rbx+6F0h], rax
0x18000c5d2  mov     rdx, rax
0x18000c5d5  test    rax, rax
0x18000c5d8  jnz     short loc_18000C5E4
0x18000c5da  mov     eax, 8007000Eh
0x18000c5df  jmp     loc_18000C822
0x18000c5e4  mov     rcx, [rdi]
0x18000c5e7  lea     r8, [rbp+30h+arg_0]
0x18000c5eb  mov     rax, [rcx]
0x18000c5ee  mov     rax, [rax+20h]
0x18000c5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5f7  test    eax, eax
0x18000c5f9  js      loc_18000C822
0x18000c5ff  mov     rdi, r15
0x18000c602  mov     rcx, rdi
0x18000c605  mov     edx, 4; unsigned __int64
0x18000c60a  shl     rcx, 4
0x18000c60e  add     rcx, rsi; this
0x18000c611  call    ?Grow@TGrowableBuffer@@QEAAX_K@Z; TGrowableBuffer::Grow(unsigned __int64)
0x18000c616  inc     rdi
0x18000c619  cmp     rdi, 9
0x18000c61d  jnz     short loc_18000C602
0x18000c61f  mov     rcx, rbx; this
0x18000c622  call    ?ObtainPertinentTableMetaInfo@TMetabase_XMLtable@@AEAAJXZ; TMetabase_XMLtable::ObtainPertinentTableMetaInfo(void)
0x18000c627  test    eax, eax
0x18000c629  js      loc_18000C822
0x18000c62f  mov     rax, [rbx+760h]
0x18000c636  lea     r14, [rbx+8E0h]
0x18000c63d  mov     r9, r14
0x18000c640  mov     ecx, [rax]
0x18000c642  or      [rbx+678h], ecx
0x18000c648  mov     rcx, rbx
0x18000c64b  call    ?GetMetaTable@TMetabase_XMLtable@@AEBAJPEBG0AEAV?$CComPtr@UISimpleTableRead2@@@ATL@@@Z; TMetabase_XMLtable::GetMetaTable(ushort const *,ushort const *,ATL::CComPtr<ISimpleTableRead2> &)
0x18000c650  test    eax, eax
0x18000c652  js      loc_18000C822
0x18000c658  xor     edx, edx; Val
0x18000c65a  lea     rcx, [rbp+30h+var_B0]; void *
0x18000c65e  mov     r8d, 90h; Size
0x18000c664  call    memset_0
0x18000c669  mov     edi, r15d
0x18000c66c  mov     rcx, [r14]
0x18000c66f  lea     rdx, [rbp+30h+var_B0]
0x18000c673  mov     [rsp+130h+var_108], rdx
0x18000c678  xor     r9d, r9d
0x18000c67b  mov     edx, edi
0x18000c67d  mov     [rsp+130h+var_110], r15
0x18000c682  mov     rax, [rcx]
0x18000c685  lea     r8d, [r9+12h]
0x18000c689  mov     rax, [rax+20h]
0x18000c68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c692  mov     esi, eax
0x18000c694  cmp     eax, 80210816h
0x18000c699  jz      loc_18000C73E
0x18000c69f  test    eax, eax
0x18000c6a1  js      short loc_18000C701
0x18000c6a3  mov     rax, [rbp+30h+var_90]
0x18000c6a7  mov     r8d, edi
0x18000c6aa  mov     ecx, [rax]
0x18000c6ac  mov     rax, [rbp+30h+var_88]
0x18000c6b0  lea     rdx, [r8+r8*2]
0x18000c6b4  mov     [rbx+rdx*4+298h], ecx
0x18000c6bb  mov     ecx, [rax]
0x18000c6bd  mov     rax, [rbp+30h+var_80]
0x18000c6c1  mov     [rbx+rdx*4+29Ch], ecx
0x18000c6c8  lea     rdx, [r8+r8*2]
0x18000c6cc  mov     ecx, [rax]
0x18000c6ce  mov     rax, [rbp+30h+var_28]
0x18000c6d2  mov     [rbx+rdx*4+2A0h], ecx
0x18000c6d9  mov     rcx, [rbp+30h+var_98]
0x18000c6dd  mov     [rbx+r8*8+470h], rax
0x18000c6e5  mov     rax, r13
0x18000c6e8  inc     rax
0x18000c6eb  cmp     [rcx+rax*2], r15w
0x18000c6f0  jnz     short loc_18000C6E8
0x18000c6f2  mov     [rbx+r8*4+4B8h], eax
0x18000c6fa  inc     edi
0x18000c6fc  jmp     loc_18000C66C
0x18000c701  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c708  jz      short loc_18000C737
0x18000c70a  mov     rcx, cs:g_pDebug
0x18000c711  lea     rax, aGetcolumnvalue; "GetColumnValues FAILED with something o"...
0x18000c718  lea     r9, aTmetabaseXmlta; "TMetabase_XMLtable::InternalComplicated"...
0x18000c71f  mov     [rsp+130h+var_110], rax
0x18000c724  mov     r8d, 324h
0x18000c72a  lea     rdx, aInetsrvIisMbCo_6; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000c731  call    cs:__imp_PuDbgPrint
0x18000c737  mov     eax, esi
0x18000c739  jmp     loc_18000C822
0x18000c73e  cmp     edi, 9
0x18000c741  jz      short loc_18000C74D
0x18000c743  mov     eax, 80210520h
0x18000c748  jmp     loc_18000C822
0x18000c74d  mov     rcx, rbx; this
0x18000c750  call    ?ObtainPertinentTagMetaInfo@TMetabase_XMLtable@@AEAAJXZ; TMetabase_XMLtable::ObtainPertinentTagMetaInfo(void)
0x18000c755  test    eax, eax
0x18000c757  js      loc_18000C822
0x18000c75d  mov     eax, [rbx+564h]
0x18000c763  lea     rcx, [rbx+600h]; this
0x18000c76a  mov     r8d, [rbx+568h]; int
0x18000c771  lea     rdx, [rax+rax*2]
0x18000c775  shl     rdx, 4
0x18000c779  add     rdx, [rbx+638h]; struct tTAGMETARow *
0x18000c780  call    ?Init@TPublicRowName@@QEAAJPEAUtTAGMETARow@@H@Z; TPublicRowName::Init(tTAGMETARow *,int)
0x18000c785  test    eax, eax
0x18000c787  js      loc_18000C822
0x18000c78d  mov     rax, [rbx+6F0h]
0x18000c794  lea     rdx, [rbx+7F8h]
0x18000c79b  mov     rcx, [rbx+6B0h]
0x18000c7a2  lea     r9, [rsp+130h+var_E0]
0x18000c7a7  mov     [rsp+130h+var_F8], rdx
0x18000c7ac  lea     r8, aColumnmeta; "COLUMNMETA"
0x18000c7b3  mov     [rsp+130h+var_E0], rax
0x18000c7b8  lea     rdx, ?m_kTwo@TMetabase_XMLtable@@0KA; ulong TMetabase_XMLtable::m_kTwo
0x18000c7bf  lea     rax, aByname; "ByName"
0x18000c7c6  mov     [rsp+130h+var_D8], 2
0x18000c7ce  mov     [rsp+130h+var_C8], rax
0x18000c7d3  mov     [rsp+130h+var_D4], 0F0000001h
0x18000c7db  mov     [rsp+130h+var_D0], 82h
0x18000c7e4  mov     [rsp+130h+var_C0], 2
0x18000c7ec  mov     [rsp+130h+var_BC], 0F0000004h
0x18000c7f4  mov     [rsp+130h+var_B8], 82h
0x18000c7fd  mov     rax, [rcx]
0x18000c800  mov     [rsp+130h+var_100], r15d
0x18000c805  mov     dword ptr [rsp+130h+var_108], 3
0x18000c80d  mov     [rsp+130h+var_110], rdx
0x18000c812  lea     rdx, aMeta; "META"
0x18000c819  mov     rax, [rax+18h]
0x18000c81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c822  lea     r11, [rsp+130h+var_20]
0x18000c82a  mov     rbx, [r11+38h]
0x18000c82e  mov     rsi, [r11+40h]
0x18000c832  mov     rsp, r11
0x18000c835  pop     r15
0x18000c837  pop     r14
0x18000c839  pop     r13
0x18000c83b  pop     rdi
0x18000c83c  pop     rbp
0x18000c83d  retn
```
