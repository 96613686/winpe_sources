# CNetDiagClient::LaunchScriptedDiagnostics(int)

- ea: `0x18000dd58`
- end: `0x18000dfdb`
- name: `?LaunchScriptedDiagnostics@CNetDiagClient@@QEAAJH@Z`
- size: `643`
- prototype: `__int64 __fastcall(CNetDiagClient *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18000b810`

## callees

- `0x18000ba60`
- `0x18000bca0`
- `0x18000caf8`
- `0x18000d8f0`
- `0x18000dd58`
- `0x18000eed8`
- `0x18000f300`
- `0x18000f350`
- `0x18000fa40`
- `0x18001f652`
- `0x180021010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000df98`
- `ole32!CoTaskMemFree` at `0x18000df98`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::LaunchScriptedDiagnostics(CNetDiagClient *this)
{
  CNetDiagClient *v1; // r14
  unsigned __int16 *v2; // rbx
  int v3; // esi
  unsigned int v4; // r15d
  int v5; // eax
  wchar_t *v6; // rdx
  __int64 v7; // r8
  HWND v8; // rdx
  void *v9; // r14
  _QWORD v11[2]; // [rsp+20h] [rbp-D8h] BYREF
  ATL::CAtlException *v12; // [rsp+30h] [rbp-C8h] BYREF
  struct tagHELPER_ATTRIBUTE v13; // [rsp+38h] [rbp-C0h] BYREF
  unsigned __int16 *v15; // [rsp+110h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+118h] [rbp+20h] BYREF

  v1 = this;
  pv = 0;
  v11[0] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v11[1] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v2 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v15 = v2;
  v3 = AnswerFileGenerator::SetHelperClass((AnswerFileGenerator *)v11, *((const unsigned __int16 **)v1 + 3));
  if ( v3 < 0 )
    goto LABEL_22;
  v4 = 0;
  if ( !*((_DWORD *)v1 + 8) )
  {
LABEL_6:
    v3 = AnswerFileGenerator::WriteAnswerFile((AnswerFileGenerator *)v11, (unsigned __int16 **)&pv);
    if ( v3 < 0 )
      goto LABEL_19;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( *((_DWORD *)v1 + 4) )
      {
        v6 = off_180023660[*((int *)v1 + 4)];
        if ( v6 )
        {
          v7 = -1;
          do
            ++v7;
          while ( v6[v7] );
        }
        else
        {
          v7 = 0;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v15, v6, v7);
      }
      else
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v15,
          L"%s%s",
          L"NetworkDiagnosticsGeneric",
          *((_QWORD *)v1 + 3));
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
          &v15,
          L" ",
          &qword_180026B78);
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v12) )
      {
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000DF47);
        v3 = *(_DWORD *)v12;
        if ( *(int *)v12 >= 0 )
        {
          v1 = this;
          goto LABEL_17;
        }
        v2 = v15;
LABEL_19:
        v9 = pv;
LABEL_20:
        if ( v9 )
          CoTaskMemFree(v9);
        goto LABEL_22;
      }
    }
LABEL_17:
    v2 = v15;
    v8 = (HWND)*((_QWORD *)v1 + 390);
    v9 = pv;
    v3 = LaunchMSDT((const unsigned __int16 *)pv, v8, v15);
    goto LABEL_20;
  }
  while ( v3 >= 0 )
  {
    memset_0(&v13, 0, sizeof(v13));
    v13 = *(struct tagHELPER_ATTRIBUTE *)(*((_QWORD *)v1 + 5) + 144LL * v4);
    v5 = ((int (__stdcall *)(AnswerFileGenerator *, struct tagHELPER_ATTRIBUTE *const))AnswerFileGenerator::AddHelperAttribute)(
           (AnswerFileGenerator *)v11,
           &v13);
    v3 = v5;
    if ( ++v4 >= *((_DWORD *)v1 + 8) )
    {
      if ( v5 < 0 )
        break;
      goto LABEL_6;
    }
  }
LABEL_22:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v2 - 3) + 8LL))(*((_QWORD *)v2 - 3));
  AnswerFileGenerator::~AnswerFileGenerator((AnswerFileGenerator *)v11);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000dd58  mov     rax, rsp
0x18000dd5b  mov     [rax+10h], edx
0x18000dd5e  mov     [rax+8], rcx
0x18000dd62  push    rbx
0x18000dd63  push    rsi
0x18000dd64  push    rdi
0x18000dd65  push    r14
0x18000dd67  push    r15
0x18000dd69  sub     rsp, 0D0h
0x18000dd70  mov     r14, rcx
0x18000dd73  xor     edi, edi
0x18000dd75  mov     [rax+20h], rdi
0x18000dd79  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000dd80  lea     rbx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000dd87  mov     rcx, rbx
0x18000dd8a  mov     rax, [rax+18h]
0x18000dd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd93  add     rax, 18h
0x18000dd97  mov     [rsp+0F8h+var_D8], rax
0x18000dd9c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000dda3  mov     rcx, rbx
0x18000dda6  mov     rax, [rax+18h]
0x18000ddaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddaf  add     rax, 18h
0x18000ddb3  mov     [rsp+0F8h+var_D0], rax
0x18000ddb8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000ddbf  mov     rcx, rbx
0x18000ddc2  mov     rax, [rax+18h]
0x18000ddc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddcb  lea     rbx, [rax+18h]
0x18000ddcf  mov     [rsp+0F8h+arg_10], rbx
0x18000ddd7  mov     rdx, [r14+18h]; unsigned __int16 *
0x18000dddb  lea     rcx, [rsp+0F8h+var_D8]; this
0x18000dde0  call    ?SetHelperClass@AnswerFileGenerator@@QEAAJPEBG@Z; AnswerFileGenerator::SetHelperClass(ushort const *)
0x18000dde5  mov     esi, eax
0x18000dde7  test    eax, eax
0x18000dde9  js      loc_18000DF9F
0x18000ddef  mov     r15d, edi
0x18000ddf2  cmp     [r14+20h], edi
0x18000ddf6  jbe     loc_18000DEB2
0x18000ddfc  test    esi, esi
0x18000ddfe  js      loc_18000DF9F
0x18000de04  xor     edx, edx; Val
0x18000de06  mov     r8d, 90h; Size
0x18000de0c  lea     rcx, [rsp+0F8h+var_C0]; void *
0x18000de11  call    memset_0
0x18000de16  mov     eax, r15d
0x18000de19  lea     rcx, [rax+rax*8]
0x18000de1d  add     rcx, rcx
0x18000de20  mov     rax, [r14+28h]
0x18000de24  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18000de28  movups  xmmword ptr [rsp+0F8h+var_C0.pwszName], xmm0
0x18000de2d  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x18000de32  movups  xmmword ptr [rsp+0F8h+var_C0.10h], xmm1
0x18000de37  movups  xmm0, xmmword ptr [rax+rcx*8+20h]
0x18000de3c  movups  xmmword ptr [rsp+0F8h+var_C0.10h+10h], xmm0
0x18000de41  movups  xmm1, xmmword ptr [rax+rcx*8+30h]
0x18000de46  movups  xmmword ptr [rsp+0F8h+var_C0.10h+20h], xmm1
0x18000de4b  movups  xmm0, xmmword ptr [rax+rcx*8+40h]
0x18000de50  movups  xmmword ptr [rsp+0F8h+var_C0.10h+30h], xmm0
0x18000de55  movups  xmm1, xmmword ptr [rax+rcx*8+50h]
0x18000de5a  movups  xmmword ptr [rsp+0F8h+var_C0.10h+40h], xmm1
0x18000de62  movups  xmm0, xmmword ptr [rax+rcx*8+60h]
0x18000de67  movups  xmmword ptr [rsp+0F8h+var_C0.10h+50h], xmm0
0x18000de6f  movups  xmm1, xmmword ptr [rax+rcx*8+70h]
0x18000de74  movups  xmmword ptr [rsp+0F8h+var_C0.10h+60h], xmm1
0x18000de7c  movups  xmm0, xmmword ptr [rax+rcx*8+80h]
0x18000de84  movups  xmmword ptr [rsp+0F8h+var_C0.10h+70h], xmm0
0x18000de8c  lea     rdx, [rsp+0F8h+var_C0]; struct tagHELPER_ATTRIBUTE *
0x18000de91  lea     rcx, [rsp+0F8h+var_D8]; this
0x18000de96  call    ?AddHelperAttribute@AnswerFileGenerator@@QEAAJQEAUtagHELPER_ATTRIBUTE@@@Z; AnswerFileGenerator::AddHelperAttribute(tagHELPER_ATTRIBUTE * const)
0x18000de9b  mov     esi, eax
0x18000de9d  inc     r15d
0x18000dea0  cmp     r15d, [r14+20h]
0x18000dea4  jb      loc_18000DDFC
0x18000deaa  test    eax, eax
0x18000deac  js      loc_18000DF9F
0x18000deb2  lea     rdx, [rsp+0F8h+pv]; unsigned __int16 **
0x18000deba  lea     rcx, [rsp+0F8h+var_D8]; this
0x18000debf  call    ?WriteAnswerFile@AnswerFileGenerator@@QEAAJPEAPEAG@Z; AnswerFileGenerator::WriteAnswerFile(ushort * *)
0x18000dec4  mov     esi, eax
0x18000dec6  test    eax, eax
0x18000dec8  js      loc_18000DF88
0x18000dece  cmp     [r14+10h], edi
0x18000ded2  jnz     short loc_18000DF10
0x18000ded4  mov     r9, [r14+18h]
0x18000ded8  mov     r8, cs:off_180023660; "NetworkDiagnosticsGeneric"
0x18000dedf  lea     rdx, aSS_0; "%s%s"
0x18000dee6  lea     rcx, [rsp+0F8h+arg_10]
0x18000deee  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000def3  lea     r8, qword_180026B78
0x18000defa  lea     rdx, SubStr; " "
0x18000df01  lea     rcx, [rsp+0F8h+arg_10]
0x18000df09  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x18000df0e  jmp     short loc_18000DF45
0x18000df10  movsxd  rax, dword ptr [r14+10h]
0x18000df14  lea     rdx, off_180023660; "NetworkDiagnosticsGeneric"
0x18000df1b  mov     rdx, [rdx+rax*8]
0x18000df1f  test    rdx, rdx
0x18000df22  jnz     short loc_18000DF29
0x18000df24  mov     r8d, edi
0x18000df27  jmp     short loc_18000DF37
0x18000df29  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000df2d  inc     r8
0x18000df30  cmp     [rdx+r8*2], di
0x18000df35  jnz     short loc_18000DF2D
0x18000df37  lea     rcx, [rsp+0F8h+arg_10]
0x18000df3f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000df44  nop
0x18000df45  jmp     short loc_18000DF5A
0x18000df47  mov     esi, [rsp+0F8h+arg_8]
0x18000df4e  test    esi, esi
0x18000df50  js      short loc_18000DF80
0x18000df52  mov     r14, [rsp+0F8h+arg_0]
0x18000df5a  mov     rbx, [rsp+0F8h+arg_10]
0x18000df62  mov     r8, rbx; unsigned __int16 *
0x18000df65  mov     rdx, [r14+0C30h]; HWND
0x18000df6c  mov     r14, [rsp+0F8h+pv]
0x18000df74  mov     rcx, r14; unsigned __int16 *
0x18000df77  call    ?LaunchMSDT@@YAJPEBGPEAUHWND__@@0@Z; LaunchMSDT(ushort const *,HWND__ *,ushort const *)
0x18000df7c  mov     esi, eax
0x18000df7e  jmp     short loc_18000DF90
0x18000df80  mov     rbx, [rsp+0F8h+arg_10]
0x18000df88  mov     r14, [rsp+0F8h+pv]
0x18000df90  test    r14, r14
0x18000df93  jz      short loc_18000DF9F
0x18000df95  mov     rcx, r14; pv
0x18000df98  call    cs:__imp_CoTaskMemFree
0x18000df9e  nop
0x18000df9f  lea     rdx, [rbx-18h]
0x18000dfa3  or      eax, 0FFFFFFFFh
0x18000dfa6  lock xadd [rdx+10h], eax
0x18000dfab  sub     eax, 1
0x18000dfae  jg      short loc_18000DFC0
0x18000dfb0  mov     rcx, [rdx]
0x18000dfb3  mov     rax, [rcx]
0x18000dfb6  mov     rax, [rax+8]
0x18000dfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfbf  nop
0x18000dfc0  lea     rcx, [rsp+0F8h+var_D8]; this
0x18000dfc5  call    ??1AnswerFileGenerator@@QEAA@XZ; AnswerFileGenerator::~AnswerFileGenerator(void)
0x18000dfca  mov     eax, esi
0x18000dfcc  add     rsp, 0D0h
0x18000dfd3  pop     r15
0x18000dfd5  pop     r14
0x18000dfd7  pop     rdi
0x18000dfd8  pop     rsi
0x18000dfd9  pop     rbx
0x18000dfda  retn
```
